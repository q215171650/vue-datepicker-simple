# vue-datepicker-simple

一款非常简单的基于vue的日期选择器


## 可以不看的前言

分享这款小插件的初衷也是感觉像github和npm这样的平台，面向国人友好的库还是非常少，当初真的是找不到一款合适的日期选择插件，诚然代码是全世界通用，但是一些具体的直接面向用户的组件还是会有语言地域差异。如果你也喜欢这款插件，可以在 [github](https://github.com/dai-siki/vue-datepicker-simple) 点击star，让更多国人可以看到。


## 更新日志

### @1.4.0
- 兼容vue@2.0+（需要引入对应的组件，绑定value语法有不同，参考示例2）

### @1.3.0
- 添加了"placeholder"属性

### @1.2.0
- 添加了"向前看"功能（只能选今天及以后）

### @1.1.0
- 添加了年份选择功能
- 可以自定义日期格式


## demo

简单的示例1（vue@1.0+） [点我](http://dai-siki.github.io/vue-datepicker-simple/example/demo.html).

简单的示例2（vue@2.0+） [点我](http://dai-siki.github.io/vue-datepicker-simple/example2/demo.html).


## 截图

![screenshot](screenshot/01.png)
![screenshot](screenshot/02.png)


## 依赖

基于 vue.js@1.0+ 和 vue.js@2.0+ 版本。模块使用es6编写（需babel转译）。


## 安装

#### npm

```shell
$ npm install vue-datepicker-simple
```

## 使用

使用方法非常简单，参考示例。源码也很清晰，如果你想支持其他语言或调整样式，大可以自行修改相关文件。如果使用过程中遇到什么问题可以反馈给我，我会尽快修复。

#### 相关参数

| 名称              | 类型               | 默认             | 说明                                         |
| ----------------- | ----------------- | ---------------- | --------------------------------------------- |
| value             | String         | today            | 要绑定的日期变量,值为空则日期面板初始化今天    |
| field             | String            | ""               | 会给input标签添加name及id                   |
| format            | String            | 'yyyy-mm-dd'     | 日期格式                                    |
| forward           | Boolean           | false            | 是否向前看（只能选择今天及以后）              |
| placeholder       | String            | ""               | 你懂的                                     |


#### 示例(vue@1.0+)

```html

<div id="app">
	<label for="myDate">选择您的新婚之日</label>
	<date-picker field="myDate"
				 placeholder="选择日期"
				 :value.sync="date"
				 format="yyyy/mm/dd"
				 :forward="true"></date-picker>
</div>

<script>
import 'babel-polyfill'; //因为使用了es6的一些方法，需要babel垫片，如果你项目中已有相关兼容性方案，可忽略
import Vue from 'vue';
import myDatepicker from 'vue-datepicker-simple';

new Vue({
    el: '#app',
    data:{
        date: ''
    },
    components:{
        'date-picker': myDatepicker
    }
});

</script>

```

#### 示例(vue@2.0+)

```html

<div id="app">
	<label for="myDate">选择您的新婚之日</label>
	<date-picker field="myDate"
				 placeholder="选择日期"
				 v-model="date"
				 format="yyyy/mm/dd"
				 :forward="true"></date-picker>
</div>

<script>
import 'babel-polyfill'; //因为使用了es6的一些方法，需要babel垫片，如果你项目中已有相关兼容性方案，可忽略
import Vue from 'vue';
import myDatepicker from 'vue-datepicker-simple/datepicker-2.vue'; //引入对应的组件

new Vue({
    el: '#app',
    data:{
        date: ''
    },
    components:{
        'date-picker': myDatepicker
    }
});

</script>

```
