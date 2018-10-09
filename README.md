# stusy-CSS
learn CSS


盒子模型
W3C标准/IE盒子模型
标准盒子模型：宽度=内容宽度（content）+ border + padding + margin
IE盒子模型：宽度=内容宽度（content + border + padding）+ margin

box-sizing
用来控制元素的盒子模型的解析模式。默认为content-box
content-box: W3C标准盒子模型，设置元素的width/height属性是指content部分的宽/高。
border-box: IE传统盒子模型，设置元素的width/height属性是指(content + border + paddubg)部分的宽/高

块级/行内元素及其区别
常用块级元素
div/table/h1-h6/p/form/ol等，以及html5新增的section/canvas/audio/video等等。
块级元素：

会另起一行
可以设置width、margin、border、padding、width属性
默认宽度是容器的100%
行内元素
a/input/textarea/button/label/select等等
行内元素：

和其他元素在同一行
宽度/高度是内容的宽度/高度
可以设置margin-left和margin-right属性，无法设置margin-top和margin-bottom属性
border和padding可以设置，但是border-top和padding-top到页面顶部后就不再增加
BFC（块级格式化上下文: block formatting context）
BFC规定了内部的Block Box如何布局.。可参考理解CSS的BFC
特征:

内部的Box会在垂直方向上一个接一个放置
Box垂直方向的距离由margin决定，属于同一个BFC的两个相邻Box的margin会发生重叠
每个元素的margin box 的左边，与包含块border box的左边相接触
BFC的区域不会与float box重叠
BFC是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素
计算BFC的高度时，浮动元素也会参与计算
触发BFC条件：

float的值不为none
position的值不为static或者relative
display的值为inline-block、table-cell、table-caption、inline-flex或者flex其中之一
overflow的值不为visiabl
::before和:before中双冒号和单冒号区别
单冒号:用于CSS3中的伪类，双冒号::用于CSS3中的伪元素
::brfore就是一个子元素的存在，定义在元素主体内容之前的一个伪元素，并不存在于DOM中。
:before 和 :after 这两个伪元素，是在CSS2.1里新出现的。起初，伪元素的前缀使用的是单冒号语法，但随着Web的进化，在CSS3的规范里，伪元素的语法被修改成使用双冒号，成为::before ::after

常见兼容性问题
渐进识别的方式，从总体中逐渐排除局部。首先，巧妙的使用“9”这一标记，将IE浏览器从所有情况中分离出来。接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。
    div {
        background-color: #ffffff; /* 所有识别 */
        background-color: #fbfbfb; /* IE6、7、8识别 */
        +background-color: #fcfcfc; /* IE7识别 */
        _background-color: #fdfdfd; /* IE6识别 */
    }
Chrome支持小于12px 的文字
p { font-size: 10px; -webkit-transform: scale(0.8); } //0.8是缩放比例
position: flxed在android下无效
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no"/>
