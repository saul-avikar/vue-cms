<template>
	<div class="page-template">
		<TheHeader />
		<TheNavBar />
		<router-view class="content" />
		<TheFooter />
	</div>
</template>

<script>
	import TheHeader from "@/components/the-header";
	import TheNavBar from "@/components/the-nav-bar";
	import TheFooter from "@/components/the-footer";

	export default {
		components: {
			TheHeader,
			TheNavBar,
			TheFooter
		}
	};
</script>

<style scoped>
	>>> .main,
	>>> .loading-container,
	>>> .error-container,
	>>> .not-found-container {
		grid-area: content;
	}

	.page-template {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	.header {
		height: 150px;
	}

	.nav-bar {
		height: 30px;
	}

	.content {
		flex: 1;
			display: grid;

			grid-template-columns: 20% 60% 20%;
			grid-template-rows: auto;

			/* The "."s can be replaced with widgets */
			grid-template-areas:
				".	content		."
				".	comments	."
				".	.			.";
	}

	.footer {
		height: 30px;
	}
</style>
