<script lang="ts" setup>
import { computed } from 'vue'
import { useLang } from '../../composables/lang'
import homeLocale from '../../../i18n/pages/home.json'
const lang = useLang()

const homeLang = computed(() => homeLocale[lang.value])
</script>

<template>
  <div class="cards">
    <ul class="container">
      <li>
        <div class="card">
          <img src="/images/guide.png" alt="" />
          <h3>{{ homeLang['3'] }}</h3>
          <p>{{ homeLang['4'] }}</p>
          <a :href="`/${lang}/guide/design.html`">{{ homeLang['5'] }}</a>
        </div>
      </li>
      <li>
        <div class="card">
          <img src="/images/component.png" alt="" />
          <h3>{{ homeLang['6'] }}</h3>
          <p>{{ homeLang['7'] }}</p>
          <a :href="`/${lang}/component/layout.html`">
            {{ homeLang['5'] }}
          </a>
        </div>
      </li>
      <li>
        <div class="card">
          <img src="/images/resource.png" alt="" />
          <h3>{{ homeLang['8'] }}</h3>
          <p>{{ homeLang['9'] }}</p>
          <a :href="`/${lang}/resource/index.html`"> {{ homeLang['5'] }} </a>
        </div>
      </li>
    </ul>
  </div>
</template>

<style lang="scss">
.home-page {
  .cards {
    margin: 0 auto 110px;
    width: 1140px;

    .container {
      padding: 0;
      margin: 0 -11px;
      width: auto;
      &::before,
      &::after {
        display: table;
        content: '';
      }
      &::after {
        clear: both;
      }
    }

    li {
      width: 33.3%;
      padding: 0 19px;
      box-sizing: border-box;
      float: left;
      list-style: none;
    }

    img {
      width: 160px;
      height: 120px;
    }
  }
  .card {
    height: 430px;
    width: 100%;
    background: var(--bg-color);
    border: 1px solid var(--border-color);
    border-radius: 5px;
    box-sizing: border-box;
    text-align: center;
    position: relative;
    transition: all 0.3s ease-in-out;
    bottom: 0;

    img {
      margin: 66px auto 60px;
    }
    h3 {
      margin: 0;
      font-size: 18px;
      color: #1f2f3d;
      font-weight: normal;
    }
    p {
      font-size: 14px;
      color: #99a9bf;
      padding: 0 25px;
      line-height: 20px;
    }
    a {
      height: 53px;
      line-height: 52px;
      font-size: 14px;
      color: var(--brand-color);
      text-align: center;
      border: 0;
      border-top: 1px solid var(--border-color);
      padding: 0;
      cursor: pointer;
      width: 100%;
      position: absolute;
      bottom: 0;
      left: 0;
      background-color: var(--bg-color);
      border-radius: 0 0 5px 5px;
      transition: all 0.3s;
      text-decoration: none;
      display: block;

      &:hover {
        color: #fff;
        background: var(--brand-color);
      }
    }
    &:hover {
      bottom: 6px;
      box-shadow: 0 6px 18px 0 rgba(232, 237, 250, 0.5);
    }
  }
  @media (max-width: 1140px) {
    .cards {
      width: 100%;
      .container {
        width: 100%;
        margin: 0;
      }
    }
    .banner .container {
      width: 100%;
      box-sizing: border-box;
    }
    .banner img {
      right: 0;
    }
  }
}
</style>
