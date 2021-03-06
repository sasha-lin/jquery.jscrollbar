﻿# jquery.jscrollbar 2.0.0

jquery.jscrollbar 是一个基于jQuery的滚动条插件，支持水平滚动条和垂直滚动条

---------------


## 主要功能

* 支持水平滚动条
* 支持垂直滚动条
* 自动判断水平滚动条和垂直滚动条是否显示
* 支持外部接口调用来滚动内容
* 支持鼠标滚动
* 支持滚动条显示位置设置(外部|悬浮)

## 2.0.X简介

jquery.jscrollbar 2.0.0已经进行重构，相对于1.0.x：

* 去除了对[`jquery.jqdrag`](https://github.com/daiying-zhang/jquery.jqdrag)插件以及`jquery.mousewheel`的依赖
* 更轻量
    * `1.0.2`: 2.36KB gzipped (7.36KB uncompressed) + jqdrag + jquery.mousewheel
    * `2.0.0`: 1.86KB gzipped (4.33KB uncompressed)
* 更新内容时支持
    * 相对定位
    * 定位到顶部
    * 定位到底部
    * 定位到右侧
    
## 使用步骤

1.在`head`中引入样式表文件：

    <link rel="stylesheet" href="../src/jquery.jscrollbar.css"/>

2.在`body`中引入下列文件:

    <script type="text/javascript" src="your-path/jquery-1.8.1.min.js"></script>
    <script type="text/javascript" src="your-path/min/jquery.jscrollbar-2.0.0.min.js"></script>
    
3.设置内容区域的大小:

    <!--设置区域大小，包括滚动条-->
    <div style="width:1300px;height:600px;">Some long text or other elements...</div>
    
4.调用插件：

    $(function(){
        $('#test1,#test2').jscrollbar({
            //some options
        });
    });
    
## 示例代码

    $(function(){
        $('#test1,#test2').jscrollbar({
            width:12, 
            position:'inner'
        });

        setTimeout(function(){
                //jQuery的链式调用，可以使用jQuery操作DOM的方法  [推荐]
                $('#test1').jscrollbar('scrollBy','x',10)
                           .jscrollbar('scrollTo','x',300);
        },2000)
    });

## 重要提示

当调用插件方法`jscrollbar`后，调用该方法的元素结构已经发生改变，如果要更改滚动区域的内容（比如插入新内容），
需要首先获取内容显示区域所对应的元素(内容区域拥有`jscrollbar`的`class`属性)，然后进行操作，比如：

    var $test1 = $('#test1').jscrollbar();
    var $content = $test1.find('.jscrollbar');

    $content.append('<h3>This text is append by JavaScript</h3>');

## E-Mail

如果你有什么好的意见或者建议，或者发现Bug，欢迎与我交流：
<97532151@qq.com>

## Site

<http://imf2e.com>

<http://www.imf2e.com/jquery.jscrollbar/>
