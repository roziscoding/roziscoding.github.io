<script setup lang="ts">
import type { Link } from '~/shared/link'

defineProps<{
  link: Link
}>()

const language = useState<'pt' | 'en'>('language', () => 'pt')
</script>

<template>
  <article class="h-full">
    <NesCard class="h-full">
      <a class="h-full hover:no-underline hover:text-[#e5e7eb]" :href="link.url" target="_blank">
        <RandomColorText>
          <h3>{{ link.title }}</h3>
        </RandomColorText>
        <p>{{ link.description[language] }}</p>
      </a>
    </NesCard>
  </article>
</template>
