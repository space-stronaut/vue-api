<template>
    <ul 
    :for="message in messages"
    >
        <li>{{message.name}}</li>
    </ul>    
</template>

<script>
export default {
  name: 'Data',
  data() {
      return{
          messages : []
      }
  },
  mounted(){
      fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(json => (this.messages = json))
  }
}
</script>
