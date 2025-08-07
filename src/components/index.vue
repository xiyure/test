<template>
  <div ref="input">
    <el-button type="primary" @click="toggle">Toggle Fullscreen</el-button>
    <el-button type="success" @click="show">Show Dialog</el-button>
    <el-dialog v-model="showDialog">
      <el-input type="textarea" :autosize="{ minRows: 5, maxRows: 10 }"></el-input>
    </el-dialog>
  </div>
</template>

<script setup lang="tsx">
import { ref } from "vue";
import { useFullscreen } from "@vueuse/core";

const input = ref<HTMLDivElement>();
const { toggle } = useFullscreen(input);
const showDialog = ref(false);

function show() {
  showDialog.value = true;
}
</script>
