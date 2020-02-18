<template>
  <div>
    <input @input ="setSearchTerm" />
    <button @click="onInput">Search</button>
  </div>
</template>

<script>
  export default {
    name: 'SearchBar',
    data() {
      return {
        searchTerm: ''
      };
    },
    methods: {
      onInput: function() {
        this.$emit('termChange', this.searchTerm);
      },
      setSearchTerm(event) {
        this.searchTerm = event.target.value;
      }
    }
  };
</script>

<style scoped>
  input {
    width: 75%;
  }
  div {
    text-align: center;
    margin: 20px;
    display: flex;
  }
  button {
    margin-left: 10px;
  }
</style>
