# SCSS
----
## 变量
**scss使用$声明变量**
```sass
    //声明变量
    $bgcolor:#ffff;
    //使用变量
    body{
        background-color: $color;
    }
```
----
## 插值语法
**#{}**
```sass
    //运算
    border:#{1+1}px solid red;
    //变量
    $name:margin;
    #{$name}:20px;
```
----
## 嵌套选择
**scss后代选择器嵌套使用**
### CSS
```css
ul{
    background-color:#ffff;
}
ul li {
    color:#0000;
}
ul li>a{
    font-size:16px;
}
ul:after{
    display:block;
    content:'';
}
```
----
### SCSS
```scss
    ul{
        background-color:#ffff;
        li{
            color:#0000;
            >a{
            font-size:16px;
        }
        }
        //&在内部指向父选择器
        //&=>ul
        &:after{
            display:block;
            content:'';
        }
    }
```
### 支持复杂选择器
在嵌套规则中可以写任何css代码，包括群组选择器（,），子代选择器（>），同层相邻组合选择器（+）、同层全体组合选择器（~）等等
----
## 导入文件
@import导入一个scss文件
注意变量覆盖问题
----
## 混入 @mixin
重复的片段可以使用@mixin来定义
类似一个函数可以传入参数
```scss
    /*声明mixin*/
    @mixin border-radius{
        color:skyblue;
        border-radius:5px;  
    }
    /*使用mixin*/
    @include border-radius;
```
参数
```scss
    @mixin fontDefault($size,$color){
        font-size:$size;
        color:$color;
    }
    @include fontDefault(5px,red);
    //设置默认参数
    @mixin fontDefault($size：16px,$color:#0000){
        font-size:$size;
        color:$color;
    }

    
```
