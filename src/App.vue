<template>
  <div>
    <Titulo />
    <div>
      <label for="">Tarea</label>
      <input type="text" placeholder="Ingrese nueva tarea" v-model="nuevaTarea"/>
      <button @click="agregarTarea()">Crear</button>

      <h2>Lista</h2>
      <ul>
        <li v-for="(tarea, index) in tareas" :key="index">
          <div>{{ index }}: {{ tarea.texto }}</div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Titulo from "@/components/Titulo.vue";

export default {
  name: "App",
  components: {
    Titulo,
  },
  data: () => ({
    nuevaTarea: "",
    tareas: [],
  }),
  methods: {
    agregarTarea(){
      this.tareas.push({texto: this.nuevaTarea})
      this.nuevaTarea = ""
    },
  },
};
</script>