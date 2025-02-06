<template>
    <div class="welcome-container">
        <h1>Welcome to Our Website!</h1>
        <p>We're glad to have you here. Explore and enjoy your time with us.</p>
    </div>
</template>

<script lang="ts" setup>
const categoryStore = useCategoryStore();
const { data: categories } = await useAsyncData("categories", () => {
    return categoryStore.fetchCategories();
});
</script>

<style scoped lang="scss">
.welcome-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f5f5f5;
    color: #333;
    text-align: center;
    padding: 20px;

    h1 {
        font-size: 3rem;
        margin-bottom: 1rem;
    }

    p {
        font-size: 1.5rem;
        max-width: 600px;
    }
}
</style>
