<template>
  <div 
    class="wall-column" 
    :id="`wall-${id}`"
  >
    <figure 
      v-for="(item, index) in items"
      :id="item.id"
      :key="index"
    >
      <img 
        :src="item.path"
        @load="onload"
      >
      <aside>
        <div class="desc">
          <span>{{
            item.desc.length > 40
              ? item.desc.slice(0, 40) + '...'
              : item.desc
          }}</span>
        </div>
      </aside>
    </figure>
  </div>
</template>
<script>
/*
 * Column组件，简单地渲染一个列表
 */
export default {
  name: 'Column',
  template: '',
  props: ["items", "id"],
  methods: {
    onload() {
      this.$emit('load');
    }
  }
}
</script>
