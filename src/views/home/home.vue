<template>
    <div>
        <h3>欢迎 {{name}}</h3>
        <a href="#" @click="quit">注销登录</a>
    </div>
</template>

<script>
/*引入公共方法*/
import { setCookie,getCookie,delCookie } from '../../assets/js/cookie.js'
    export default{
        data(){
            return{
                name: ''
            }
        },
        methods:{
            quit(){
                /*删除cookie*/
                delCookie('username')

                let uname = getCookie('username')
            this.name = uname
            /*如果cookie不存在，则跳转到登录页*/
            if(uname == ""){
                this.$router.push('/')
            }
            }

        }
    }
</script>