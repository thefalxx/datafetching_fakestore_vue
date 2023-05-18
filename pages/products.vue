<template>
    <div>
        <header>

            
            <nav class="bg-white border-gray-200 dark:bg-gray-900">
            <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
                <button data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 ml-3 text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-default" aria-expanded="false">
                <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
                </button>
                <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700 text-white">
                            <li><NuxtLink to="/">Home</NuxtLink></li>
                            <li><NuxtLink to="/products">Products</NuxtLink></li>
                    
                </ul>
                </div>
            </div>
            </nav>


        </header>

        <br>
        <h2 class="flex justify-center font-bold ">PRODUCTS</h2>

    </div>
    
    <div>
        <div class="flex-center grid grid-cols-3 justify-between gap-3">

            <!-- <div v-for="x in products" class="flex=center pl-20 pr-20 pb-20 pt-20"> -->

            <div v-for="(x, index) in products" :key="index" class="flex=center pl-20 pr-20 pb-20 pt-20">

                    <NuxtLink :to="`/products/${x.id}`"> 
                        <img class="h-28 w-28 border-black bg-gray-300" :src="x.image" alt="Product Image">
                    </NuxtLink>
                    <br>
                    <NuxtLink :to="`/products/${x.id}`">
                        Title: {{ x.title }}
                    </NuxtLink>
                    <br>
                    <NuxtLink :to="`/products/${x.id}`">
                        Price: {{ x.price }}
                    </NuxtLink>
                    <br>
                    <NuxtLink :to="`/products/${x.id}`">
                        Category: {{ x.category }}
                    </NuxtLink>

            </div>

        </div>
        
    </div>
</template>

<script setup>

    definePageMeta({
        layout: 'products'
    })

    const{data: products} = await useFetch('https://fakestoreapi.com/products')

</script>

<style scoped>

h2 {
    margin-bottom: 20px;
    font-size: 36px;
}

p{
    margin: 20px 0;
}
</style>