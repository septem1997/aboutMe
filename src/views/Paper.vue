<template>
    <div class="container" >
        <div class="qrCode">
            <img src="../assets/qrCode.png">
            <div>扫码查看线上简历</div>
        </div>
        <div class="notPrint">
            <div class="floatBtns ">
                <div class="downloadBtn floatButton" @click="downloadResume">
                    <font-awesome-icon  icon="download"/>
                    <div class="text">下载简历</div>
                </div>
            </div>
        </div>
        <div class="backBtn" @click="$router.replace('/')" :style="'transform: translateY('+position+'px)'"><font-awesome-icon icon="home"/></div>


        <div class="left">
            <div class="avatar">
                <img  src="../assets/head.jpg">
            </div>
            <div class="personInfo">
                <div class="row" v-for="(item,index) in personalInfo" :key="index">
                    <font-awesome-icon :icon="item.icon"/>
                    &nbsp;{{item.val}}
                </div>
            </div>
            <h3 style="margin-left: 10px">
                <font-awesome-icon icon="book"/>
                &nbsp;技能关键词
            </h3>
            <div class="skillKeyWord">
                <div class="word" v-for="(item,index) in skills" :key="index">{{item}}</div>
            </div>
        </div>
        <div class="right">
            <div class="name">陈校培</div>
            <div class="title">
                <font-awesome-icon icon="glasses"/>&nbsp;个人优势
            </div>
            <div>
                热爱学习和探索各类计算机技术，熟悉常见的数据结构和算法，可从零独立开发应用，包括前端页面编写、数据库设计、服务器接口编写及最终部署上线
            </div>
            <div class="title">
                <font-awesome-icon icon="th-large"/>&nbsp;个人项目
            </div>
            <div class="projectName">巴士到哪了</div>
            <div>微信小程序，基于wepy（类Vue小程序框架）开发的公交出行助手，整合了路径规划和公交车实时信息功能（仅限珠海），源码详见Coding.net</div>
            <div class="projectName">每日一文UWP</div>
            <div>一款win10端文章阅读类应用，每天更新推送一篇优质文章，具有完善的字体显示设置、评论区等功能，目前已在win10应用商店上架</div>
            <div class="projectName">贪吃蛇游戏</div>
            <div>使用Cocos游戏引擎（语言为JS）开发的贪吃蛇游戏，相比一般贪吃蛇游戏新增了关卡、特殊道具等特性，源码详见github</div>
            <div class="title">
                <font-awesome-icon icon="briefcase"/>&nbsp;工作经历
            </div>
            <div class="projectName">珠海金刚科技有限公司</div>
            <div class="workTitle"><div>Java后端/Web前端</div><div class="workTime">2018-07~2019-02</div></div>
            <div class="workContent">
                <strong>工作内容： </strong>1. 担任公司前端主程，负责赌场账房系统（后台管理系统，采用JQ框架）的业务开发以及底层框架的完善；负责赌场查数系统（移动端App，采用VUE和PWA技术）的开发。
                <br>
                2. 同时负责部分后端业务，搭建了webSocket通讯模块，采用POI技术实现了数据报表的导出。
            </div>
            <div class="workContent">
                <strong>主要业绩： </strong>1. 重写ajax请求方法，以非侵入式方式为接口调用添加了拦截器和loading动画，有效提高数据接口开发效率。
                <br>2. 完善流水单据的打印，利用Promise特性解决了打印顺序不同步的问题，封装打印公共方法，极大降低了同类需求开发成本。
                <br>3. 改进前端框架，独立编写了国际化多语言模块，使得公司产品可面向海外用户。
                <br>4. 搭建了webSocket通讯模块，分离了数据报表导出等耗时操作，提高服务器稳定性和运行性能。
            </div>

            <div class="projectName">小笋科技(深圳)有限公司</div>
            <div class="workTitle"><div>Java后端/Web前端</div><div class="workTime">2017-07~2018-06</div></div>
            <div class="workContent">
                <strong>工作内容： </strong>1. 共享单车业务，负责后台管理系统及微信公众号的开发。
                <br>2. 类美团点评app，项目技术负责人，负责整个项目的研发，涉及到后端管理系统、微信公众号、小程序、微信支付、即时聊天、线上商城等内容。
            </div>
            <div class="workContent">
                <strong>主要业绩： </strong>1. 为产品开发了即时聊天系统(web端和小程序端)，仿微信界面，可发送图片、语音和位置，具有聊天记录本地缓存和线上同步等功能。
                <br>2. 利用反射和注解实现了前端增删改查html代码自动生成，减少此类重复繁琐的开发工作，让团队更专注于其他特殊需求。
                <br>3. 基于POI和JAVA反射技术实现了excel表格导出自动化工具，市场部人员无需了解sql知识即可根据自己需求导出表格数据，极大减少繁杂多样的sql查询需求工作。
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        components: {},
        methods:{
            downloadResume(){
              window.open('http://pn5jqyvqw.bkt.clouddn.com/%E9%99%88%E6%A0%A1%E5%9F%B9-%E7%AE%80%E5%8E%86.pdf')
            }
        },
        mounted(){
            let that = this
            document.body.onmousewheel = function(event) {
                let e = event || window.event;
                if (e.wheelDelta) {
                    if (e.wheelDelta > 0) {
                        that.position = 0
                    }
                    if (e.wheelDelta < 0) {
                        that.position = -60
                    }
                } else if (e.detail) {
                    if (e.detail > 0) {
                        that.position = 0
                    }
                    if (e.detail < 0) {
                        that.position = -60
                    }
                }
            };
        },
        data() {
            return {
                position:0,
                skills: [
                    'HTML',
                    'CSS',
                    'JavaScript',
                    'Vue',
                    'LayUI',
                    'jQuery',
                    'Webpack',
                    'Stylus',
                    'PWA',
                    '微信公众号',
                    '小程序',
                    'Java',
                    'Spring',
                    'Mybatis',
                    'Hibernate',
                    'MySql',
                    'Redis',
                    'C#',
                    'UWP',
                    'Git',
                    'android',
                    'PhotoShop',
                    'WebStorm',
                    'IDEA',
                    'Visual Studio'
                ],
                personalInfo: [
                    {
                        val: '22岁',
                        icon: 'calendar-alt'
                    }, {
                        val: '2年工作经验',
                        icon: 'briefcase'
                    }, {
                        val: '16675644396',
                        icon: 'phone'
                    }, {
                        val: '750627595@qq.com',
                        icon: 'envelope'
                    },{
                        val:'github.com/septem1997',
                        icon:'code'
                    }
                ]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @media only screen and (max-width: 768px)
        .container
            flex-direction column
            width 100%
        .right
            width 100%
        .left
            width 100%
        .notPrint
            display none
    @media screen and (min-width: 769px)
        .container
            flex-direction row
            width: 21cm
            height: 297mm
            margin: 10px auto
            box-shadow: 0 2px 2px 0 rgba(0, 0, 0, .14), 0 3px 1px -2px rgba(0, 0, 0, .2), 0 1px 5px 0 rgba(0, 0, 0, .12)
            overflow: hidden
            border-radius: 4px
        .left
            width 240px
            padding 6px
            box-sizing border-box

    .backBtn
        position fixed
        transition: transform 300ms
        top 5px
        left @top
        width 36px
        height @width
        background-color #7C4DFF
        opacity 0.5
        cursor pointer
        display flex
        align-items center
        justify-content center
        border-radius 50%
        svg
            color white
    .floatBtns
        position fixed
        display flex
        flex-direction column
        bottom 48px
        right 48px
        color white
        width 120px
        text-align center
        align-items center

        .printBtn
            background-color #FF4081
        .downloadBtn
            background-color #7C4DFF
        .floatButton
            cursor pointer
            margin-top 16px
            transition: all 300ms
            width 64px
            height @width
            border-radius @width
            box-shadow: 0 4px 4px 0 rgba(0,0,0,0.14), 0 5px 7px -2px rgba(0,0,0,0.2), 0 4px 5px 0 rgba(0,0,0,0.12)
            .text
                font-size 18px
                display none
                margin-top 18px
                white-space nowrap
            svg
                font-size 32px
                margin-top 16px
        .floatButton:hover
            width 120px
            opacity .8
            .text
                display block
            svg
                display none


    .qrCode
        position absolute
        text-align center
        color white
        display none
        width 200px
        z-index 999
        bottom 20px
        left 20px
        img
            margin 0 auto
            width 100%
            height auto
    .workTitle
        display flex
        justify-content space-between
    .workContent
        margin-top 5px
        font-size 14px
    .name
        font-size 32px
        margin-top 15px
    .projectName
        font-size 18px
        font-weight bold
        margin 8px 0
    .right
        flex: 1
        padding: 0 20px
        box-sizing border-box
        display flex
        flex-direction column
        align-items stretch

    .title
        color: #29B6F6
        font-size: 22px
        border-bottom: #29B6F6 1px solid
        margin-top 24px
        margin-bottom 5px

    .skillKeyWord
        display: flex
        flex-wrap: wrap
        justify-content: space-evenly
        padding 5px 0

    .word
        margin: 4px
        padding: 6px
        border-radius: 16px
        border: white 1px solid
        font-size: 16px


    .container
        display: flex



    .left
        background-color: #29B6F6
        display: flex
        flex-direction: column
        color: white


    .avatar
        margin: 40px auto
        width: 120px
        height: 120px
        border: 1px solid whitesmoke
        background-color: white
        img
            width 100%
            height 100%


    .personInfo
        margin-left: 22px
        font-size: 15px


    .personInfo
        .row
            margin-top: 10px
            svg
                width 20px
                text-align center

</style>
