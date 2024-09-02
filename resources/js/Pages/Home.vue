<template>
    <div>
      <h1>Welcome to the Home Page</h1>
      <div v-if="!user">
        <p>You need to <Link :href="route('login')">log in</Link> or <Link :href="route('register')">register</Link>.</p>
      </div>
      <div v-else>
        <p>Welcome, {{ user.name }}!</p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';
  
  const props = defineProps({
    user: Object,
    canLogin: Boolean,
    canRegister: Boolean,
  });
  </script>
  