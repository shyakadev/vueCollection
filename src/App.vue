<template>
  <div id="app">
  
  <div v-for="item in items" :key="item.id">
    {{item.title}}
  </div>
  </div>
</template>

<script>
 //import HelloWorld from './components/HelloWorld'
import Firebase from 'firebase'

let config = {
    apiKey: "AIzaSyC87i8r-7OsqQ3CrYwGr5_BzatO0ME5ekI",
    authDomain: "collexa2.firebaseapp.com",
    databaseURL: "https://collexa2.firebaseio.com",
    projectId: "collexa2",
    storageBucket: "",
    messagingSenderId: "792975064262"
}

let app = Firebase.initializeApp(config);
let db = app.database();
let itemsRef = db.ref("items");

export default {
  name: 'App',
  firebase: {
    items: itemsRef
  }
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
