<template lang="html">
    <div class="clearfixed">
        <div class="product-list"  v-for="(val,index) in productList" :key="index">
            <router-link to="/pdp" class="product-img">
                <!-- <img :src="val.imgSrc" alt=""> -->
                <img v-lazy="val.imgSrc" alt="">
                <div class="new-product" v-show="val.tag.length>0">
                    <span>{{val.tag}}</span>
                </div>
            </router-link>
            <div class="product-detail">
                <router-link to="/pdp">
                    <p class="product-brand">{{val.productBrand}}</p>
                    <p class="product-name">{{val.productName}}</p>
                    <div class="product-price">
                        <span class="now-price">{{val.nowPrice}}</span>
                        <del class="old-price">{{val.oldPrice}}</del>
                    </div>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        "productList":{
            type:Array
        }
    },
    data(){
        return{

        }
    },
    mounted:function(){
        console.log(123);
    }
}
</script>

<style lang="less">
.product-list{
    width:50%;
    float:left;
    box-sizing: border-box;
    border:1px solid #f2f0ee;
}

</style>
