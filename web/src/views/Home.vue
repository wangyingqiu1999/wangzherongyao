<template>
  <div>
    <swiper :options="swiperOption">
      <swiper-slide>
        <img class="w-100" src="../assets/images/e3bf3b30328abaaef040bf2446158f22.jpeg">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/e3bf3b30328abaaef040bf2446158f22.jpeg">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/e3bf3b30328abaaef040bf2446158f22.jpeg">
      </swiper-slide>
      
      <div class="swiper-pagination pagination-home text-right px-3 pb-2" slot="pagination"></div>
    </swiper>
    <!--end of swiper -->

    <div class="nav-icons bg-white mt-3 text-center pt-3 text-dark-1">
      <div class="d-flex flex-wrap">
        <div class="nav-item mb-3" v-for="n in 10" :key="n">
        <i class="sprite sprite-news"></i>
        <div class="py-2">爆料站</div>
        </div>
      </div>
      <div class="bg-light py-2 fs-sm">
        <i class="sprite sprite-arrow mr-1"></i>
        <span>收起</span>
      </div>
    </div>
    <!--end of nav icons -->

    <m-list-card icon="menu" title="新闻资讯" :categories="newsCats">
      <template #items="{category}">
        <div class="py-2" v-for="(news, i) in category.newsList" :key="i">
          <span>[{{news.categoryName}}]</span>
          <span>|</span>
          <span>{{news.title}}</span>
          <span>{{news.date}}</span>
        </div>
      </template>
      
    </m-list-card>


  </div>
</template>

<script>
  export default {
    data() {
      return {
        swiperOption: {
          pagination: {
            el: ".pagination-home"
          }
        },
        newsCats: [
          {
            name: "热门",
            // eslint-disable-next-line no-unused-vars
            newsList: new Array(5).fill(1).map(v => ({
              categoryName: '公告',
              title: '2月13日全服不停机更新公告',
              date: '02/13'
            }))
          },
          {
            name: "新闻",
            // eslint-disable-next-line no-unused-vars
            newsList: new Array(5).fill(1).map(v => ({
              categoryName: '新闻',
              title: '2月13日全服不停机更新公告',
              date: '02/13'
            }))
          },
          {
            name: "热门",
            // eslint-disable-next-line no-unused-vars
            newsList: new Array(5).fill(1).map(v => ({
              categoryName: '公告',
              title: '2月13日全服不停机更新公告',
              date: '02/13'
            }))
          },
          {
            name: "热门",
            // eslint-disable-next-line no-unused-vars
            newsList: new Array(5).fill(1).map(v => ({
              categoryName: '公告',
              title: '2月13日全服不停机更新公告',
              date: '02/13'
            }))
          },
          {
            name: "热门",
            // eslint-disable-next-line no-unused-vars
            newsList: new Array(5).fill(1).map(v => ({
              categoryName: '公告',
              title: '2月13日全服不停机更新公告',
              date: '02/13'
            }))
          },
        ]
      }
    },
  }
</script>

<style lang="scss">
@import '../assets/scss/variables';

  .pagination-home {
    .swiper-pagination-bullet {
      opacity: 1;
      border-radius: 0.1538rem;
      background: map-get($colors, 'white');
      &.swiper-pagination-bullet-active {
        background: map-get($colors, 'info');
      }
    }
  }

  .nav-icons {
    border-top: 1px solid $border-color;
    border-bottom: 1px solid $border-color;
    .nav-item {
      width: 25%;
      border-right: 1px solid $border-color;
      &:nth-child(4n) {
        border-right: none;
      }
    }
  }
</style>