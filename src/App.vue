
<script setup>
const message = 'Hello World';
const message2 = 'hola como estan!';
const message3 = '<p><b>hola</b> como estan!</p>';
const link = "https://yahoo.co.jp";
const color = true;
/*
const users = [
  { id: 1, name: 'John Doe', email: 'john@test.com', admin: true },
  { id: 2, name: 'Jane Doe', email: 'jane@example.com', admin: false },
  { id: 3, name: 'Kevin MacDonald', email: 'kevin@test.com', admin: false },
];
*/

import axios from 'axios'
/*
axios.get('https://jsonplaceholder.typicode.com/users')
  .then(function(response){
    console.log(response.data)
    alert(response.data[1].name)
  })
  .catch(function(error){
    console.log(error)
  })
*/
axios.get('https://jsonplaceholder.typicode.com/users')
  .then(response => this.users = response.data)
  .catch(error => console.log(error))



</script>

<template>
<h1>Vue 3 入門</h1>
<p>{{ message }}</p>
<p v-text="message2"></p>
<p class='active' v-html="message3"></p>
<p :class="{ active: color }">色変化</p>
<a :href="link">やふー</a>
<p v-for="user in users" :key="user">{{ user }}</p>
<p v-text="message2"></p>
</template>


<style>
.active {
  color: red;
  font-weight: 900;
}
</style>