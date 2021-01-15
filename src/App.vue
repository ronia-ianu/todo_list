<template>
<<<<<<< HEAD
<div class="wrapper">
    <div id="newtodo">
      <input type="text" name="todo-text" v-model.trim="newTodoText"
        id="todo-text" placeholder="New todo">
      <button v-on:click="addTodo()">Add</button>
    </div>
    <ul class="todo" v-if="todos.length">
      <li v-for="todo in todos" :key="todo.id">
        <span>{{ todo.text }}</span>
        <button v-on:click="removeTodo(todo)">Remove</button>
=======
  <div class="wrapper">
    <h1>What should I do?</h1>
    <div class="newtodo">
      <input
        type="text"
        name="todo-text"
        v-model.trim="newTodoText"
        class="todo-text"
        placeholder="New todo"
      />
      <datepicker v-on:update="dateUpdated"> </datepicker> 
      <button class="todo-add-button" v-on:click="addTodo()">Add</button>
    </div>
    
    <ul v-if="todos.length">
      <li class="todo">
        <span class="todo-text list-header">Todo</span>
        <span class="todo-text date-header">DueDate</span>
        <span class="todo-empty-button list-header"></span>
      </li>

      <li class="todo" v-for="todo in todos" :key="todo.id">
       <todo :todo="todo" v-on:remove="removeTodo(todo)"/>
>>>>>>> feat/fullstack
      </li>
    </ul>
    <p class="none" v-else>Add a new todo in the input above</p>
  </div>
</template>

<script>
<<<<<<< HEAD
export default {
  name: 'App',
  components: {
  },
   data () {
      return {
          newTodoText: "",
          todos: []
      }
  },
  methods: {
      addTodo () {
            // check if this.newTodoText is set (prevent adding of empty items)
            if (this.newTodoText) {
                // this.todos.push() adds a new entry to the back of a list
                // a todo item consists of the text and an id, and we will simply use the current time for the id
                this.todos.push({
                    text: this.newTodoText,
                    id: Date.now()
                })
                // after addind the todo item, clear the text
                this.newTodoText = ''
            }
        },
        removeTodo (item) {
            // the function gets a todo item as an argument
            // this.todos.filter() filters out all occurences of this item from the list this.todos
            // we simply re-assign the filtered list of todos to list.todos
            this.todos = this.todos.filter(_item => _item !== item)
        }
        
  }
}
</script>

<style>
*, *::before, *::after {
  box-sizing: border-box;
}

html, body {
  font: 16px/1.2 BlinkMacSystemFont, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
=======
import datepicker from './components/datepicker.vue'
import todo from './components/todo.vue'
import API from './api'

const apiURL='http://localhost:8081/todos'

export default {
  name: "App",
  components: {
    todo, datepicker
  },
  data() {
    return {
      newTodoText: "",
      newToDoDate: "",
      todos: [],
    };
  },
  mounted() {
    this.api = API(apiURL)
    this.getAllTodos
  }
  
  methods: {
    getAllTodos(){

    },
    addTodo() {
      if (this.newTodoText) {

        this.todos.push({
          text: this.newTodoText,
          date: this.newToDoDate,
          id: Date.now(),
          done: false
        });
        

        this.newToDoText = "";
      
      }
    },
    this.todos.sort((todoA, todoB) => -todoA.date.diff(todoB.date)),
    
    removeTodo (item) {
      this.todos = this.todos.filter((_item) => _item !== item);
    },
    dateUpdated (date) {
      this.newToDoDate = date.clone()

    }
  },
};
</script>

<style>
html,
body {
  font: 16px/1.2 BlinkMacSystemFont, -apple-system, "Segoe UI", Roboto,
    Helvetica, Arial, sans-serif;
>>>>>>> feat/fullstack
  padding: 10px;
}

.wrapper {
  width: 75%;
  margin: 0 auto;
}

<<<<<<< HEAD
#newtodo {
  width: 100%;
}

input {
  width: 90%;
}

button {
=======
.newtodo {
  display: flex;
  width: 100%;
}

.todo {
  display: flex;
  width: 100%;
  margin-bottom: 5px;
}

.list-header {
  text-align: center;
  padding: 5px;
  margin-left: 2px;
  margin-right: 2px;
  background-color: #eee;
  color: black;
}

.todo-text {
  flex: 4;
  text-align: center;
}

.todo-date {
  flex: 3;
  text-align: center;
}

.todo-add-button {
  flex: 1;
>>>>>>> feat/fullstack
  border: 1px solid green;
  background: green;
  color: white;
  font-size: 0.8rem;
  padding: 2px 4px;
  cursor: pointer;
<<<<<<< HEAD
  width: 10%;
}


form #todo-text {
  width: 100%;
  padding: 10px;
  border: 1px solid #777;
}

ul, li {
=======
  margin-left: 2px;
  margin-right: 2px;
  outline: none;
}

.todo-remove-button {
  flex: 1;
  border: 1px solid red;
  background-color: red;
  color: white;
  font-size: 0.8rem;
  padding: 2px 4px;
  cursor: pointer;
  margin-left: 2px;
  margin-right: 2px;
}

.todo-empty-button {
  flex: 1;
  padding: 2px 4px;
  margin-left: 2px;
  margin-right: 2px;
}

ul, li {
  list-style-type: none;
>>>>>>> feat/fullstack
  margin: 0;
  padding: 0;
}

<<<<<<< HEAD
p.none {
  color: #888;
  font-size: small;
}

.todo li {
  display: flex;
  margin: 5px 0;
}

.todo li span {
  flex: 1;
}


.todo li button {
  border: 1px solid red;
  background: red;
=======
ul {
    margin-top: 40px;
}

button {
  border: 1px solid green;
  background: green;
>>>>>>> feat/fullstack
  color: white;
  font-size: 0.8rem;
  padding: 2px 4px;
  cursor: pointer;
}
<<<<<<< HEAD
=======

p.none {
  color: #888;
  font-size: small;
}
>>>>>>> feat/fullstack
</style>
