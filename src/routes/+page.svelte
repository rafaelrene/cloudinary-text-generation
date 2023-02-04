<script lang="ts">
	let value = '';
	let src = '';

	const handleGenerate = () => {
		const encodedValue = encodeURIComponent(value);

		src = `https://res.cloudinary.com/dto7aabea/image/upload/c_crop,h_619,w_440/co_rgb:989898,l_text:arial_64_normal_left:${encodedValue}/c_lpad,h_619,w_420/fl_layer_apply,g_center/v1675533105/gs/none-of-these_tsiyi8.png`;
	};
</script>

<div class="w-96 border-red-500 mx-auto flex flex-col gap-4">
	<input type="text" bind:value class="text-gray-900" />
	<button
		class="p-2 text-gray-100 bg-blue-500 cursor-pointer disabled:cursor-not-allowed disabled:bg-blue-900"
		on:click={handleGenerate}
		disabled={value.length === 0}
	>
		Generate
	</button>

	{#if src.length !== 0}
		<img alt="none-of-these" height="619" {src} width="440" />
	{/if}
</div>
