<script setup lang="ts">
import { ref } from 'vue';

const isOpen = ref(false); // Toggle state for mobile menu
</script>

<template>
  <nav class="bg-blue-600 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <!-- Logo -->
      <router-link to="/" class="text-white text-xl font-bold">
        MyApp
      </router-link>

      <!-- Desktop Links -->
      <div class="hidden md:flex space-x-6">
        <router-link to="/dashboard" class="text-white hover:underline">
          Dashboard
        </router-link>
        <router-link to="/login" class="text-white hover:underline">
          Login
        </router-link>
      </div>

      <!-- Mobile Menu Button -->
      <button @click="isOpen = !isOpen" class="md:hidden text-white focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                d="M4 6h16M4 12h16m-7 6h7" />
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <div v-if="isOpen" class="md:hidden mt-2 bg-blue-700 p-4 space-y-2">
      <router-link to="/dashboard" class="block text-white hover:underline">
        Dashboard
      </router-link>
      <router-link to="/login" class="block text-white hover:underline">
        Login
      </router-link>
    </div>
  </nav>
</template>
