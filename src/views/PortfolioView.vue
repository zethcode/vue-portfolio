<template>
    <div class="container mx-auto px-4 py-8">
      <h1 class="text-4xl font-bold mb-8">My Portfolio</h1>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <div>
          <h2 class="text-2xl font-bold mb-4">About Me</h2>
          <p class="text-gray-700">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ut
            perspiciatis unde omnis iste natus error sit voluptatem accusantium
            doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo
            inventore veritatis et quasi architecto beatae vitae dicta sunt
            explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut
            odit aut fugit, sed quia consequuntur magni dolores eos qui ratione
            voluptatem sequi nesciunt.
          </p>
        </div>
        <div>
          <h2 class="text-2xl font-bold mb-4">Skills</h2>
          <ul class="list-disc space-y-2">
            <li>Skill 1</li>
            <li>Skill 2</li>
            <li>Skill 3</li>
          </ul>
        </div>
      </div>
      <div class="mt-8">
        <h2 class="text-2xl font-bold mb-4">Projects</h2>
        <p v-if="!projects.length">No projects yet!</p>
        <ul v-else class="grid grid-cols-1 md:grid-cols-2 gap-4">
          <li v-for="project in projects" :key="project.id">
            <div class="card rounded-lg shadow-md">
              <div class="card-header bg-gray-200 p-4">
                <h3 class="text-xl font-bold">{{ project.title }}</h3>
              </div>
              <div class="card-body p-4">
                <p class="text-gray-700">{{ project.description }}</p>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
</template>
  
<script lang="ts">
    import { defineComponent } from 'vue';

    interface Project {
    id: number;
    title: string;
    description: string;
    }
  
    export default defineComponent({
    data() {
        return {
        projects: [] as Project[],
        };
    },
    });
</script>
  
<style scoped lang="tailwind">
/* Add your custom Tailwind styles here */
</style>