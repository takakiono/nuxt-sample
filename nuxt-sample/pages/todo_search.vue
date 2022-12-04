<template>
    <div>
        <h1>TODO</h1>

        <div class="form">
            <form @submit.prevent="todoAdd">
                <label>やること</label>
                <input v-model="todo">
                <button type="submit">Add</button>
            </form>
        </div>

        <!-- todo一覧表示 -->
        <ul>
            <li type="circle" v-for="task in tasks" v-bind:key=task>{{ task.name }}, {{ task.limit}}</li>
        </ul>

        <NuxtLink to="/">Home page</NuxtLink>
    </div>
</template>

<script>
export default {
    data(){
        return{
            tasks: [
                {
                    name:'task01',
                    limit:'2022/10/14',
                    completeFlag:false,
                },
                {
                    name:'task01',
                    limit:'2022/10/14',
                    completeFlag:false,
                }
            ],
            todo:'',
        }
    },
    methods:{
        todoAdd() {
            this.tasks.push({
                name:this.todo,
                limit:'2022/10/14',
                completeFlag:false,
            });
            this.todo = '';
        }
    },
}
</script>