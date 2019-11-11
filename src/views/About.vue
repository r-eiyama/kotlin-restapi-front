<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ul>
      <li v-for="(user, key) in users" :key="key">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      users: []
    };
  },
  mounted: function() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(response => (this.users = response.data));
  }
};
</script>
