<template>
    <form ref="createPostForm" @submit="createPostHandler">
        <h2>Create a Post</h2>
        <textarea
            rows="4"
            cols="20"
            ref="textareaRef"
            required="true"
            minlength="10"
        ></textarea>
        <TheButton>Create Post</TheButton>
    </form>
</template>
<script setup>
import TheButton from '../atoms/TheButton.vue';
import { onMounted, ref } from 'vue';

const textareaRef = ref(null);
const createPostForm = ref(null);
const createPostHandler = (event) => {
    event.preventDefault();
    if(createPostForm.value.reportValidity()){
        //code to create post
    };
}

onMounted( () => {
    textareaRef.value.focus();
});
</script>
<style scoped>
form {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-bottom: 16px;
    padding-bottom: 16px;
    border-bottom: 1px solid var(--color-border);
}
</style>