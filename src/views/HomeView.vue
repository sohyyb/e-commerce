<template>
  <div class="container">
    <div class="head">
      <div class="navs">
        <h1>sneakers</h1>
        <ul>
          <li>collections</li>
          <li>men</li>
          <li>women</li>
          <li>about</li>
          <li>contact</li>
        </ul>
      </div>
      <div class="profile">
        <img class="cart" src="../assets/pic/icon-cart.svg">
        <img class="avatar" src="../assets/pic/image-avatar.png">
      </div>
    </div>
    <div class="section-1">
      <div class="sides">
        <div class="side-1">
          <img :src="image_url" :class="{ active: image == 1 }" alt="">
          <div class="images">
            <img @click.prevent="changePic('/src/assets/pic/image-product-1.jpg', 1)"
              src="../assets/pic/image-product-1.jpg" :class="{ active: image == 1 }" alt="">
            <img @click.prevent="changePic('/src/assets/pic/image-product-2.jpg', 2)"
              src="../assets/pic/image-product-2.jpg" :class="{ active: image == 2 }" alt="">
            <img @click.prevent="changePic('/src/assets/pic/image-product-3.jpg', 3)"
              src="../assets/pic/image-product-3.jpg" :class="{ active: image == 3 }" alt="">
            <img @click.prevent="changePic('/src/assets/pic/image-product-4.jpg', 4)"
              src="../assets/pic/image-product-4.jpg" :class="{ active: image == 4 }" alt="">
          </div>
        </div>
        <div class="side-2">
          <p class="sub">sneaker company</p>
          <h1>Fall Limite sneakers</h1>
          <p class="desc">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Assumenda quam, recusandae deleniti
            minima dicta
            quisquam aperiam! Ratione voluptatum perspiciatis perferendis aliquid quia? Quod omnis distinctio culpa,
            natus quas </p>
          <span class="price">$125
            <span class="discount">50%</span>
          </span>
          <span class="before-disc">$250</span>
          <div class="add-cart">
            <div class="control">
              <button @click.prevent="count > 1 && count--" :disabled="count == 1 ? true : false"
                class="decrease">-</button>
              <span>{{ count }}</span>
              <button @click.prevent="count++">+</button>
            </div>
            <button class="add"><img class="cart" src="../assets/pic/icon-cart.svg">Add To Cart</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { ref } from 'vue';

export default {
  setup() {
    const count = ref(1)
    const image = ref(1);
    const image_url = ref("/src/assets/pic/image-product-1.jpg")
    const changePic = (path, index) => {
      image_url.value = path
      image.value = index
    }
    return {
      image,
      image_url,
      changePic,
      count
    }
  }
}
</script>
    