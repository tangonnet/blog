# flex
https://css-tricks.com/snippets/css/a-guide-to-flexbox/

## flexbug

https://github.com/philipwalton/flexbugs

## 容器的属性
flex-direction: row | row-reverse | column | column-reverse;
flex-wrap: nowrap | wrap | wrap-reverse;
flex-flow: <flex-direction> || <flex-wrap>;
justify-content: flex-start | flex-end | center | space-between | space-around;
align-items: flex-start | flex-end | center | baseline | stretch;　
  * cross axis 排列方式；stretch（默认） 为整个容器的高度；
align-content: flex-start | flex-end | center | space-between | space-around | stretch;
  * align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。(可以理解为多行时垂直方向的排列方式)

### flex-wrap: nowrap | wrap | wrap-reverse;
  nowrap（默认）：不换行

### justify-content: flex-start | flex-end | center | space-between | space-around
space-between: 左右和边缘对齐
space-around：左右和边缘有空白

## 项目的属性
order: <integer>;
flex-grow: <number>;
flex-shrink: <number>;
flex-basis: <length> | auto;
flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]  
align-self: auto | flex-start | flex-end | center | baseline | stretch;

### order属性
order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

### flex-grow属性
flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。

### flex-shrink属性
flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。
负值对该属性无效。

### lex-basis属性
flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。


## display:box和display:flex的区别

display: box; is a version of 2009.
display: flexbox; is a version of 2011.
display: flex; is the actual version.


https://www.html5rocks.com/en/tutorials/flexbox/quick/
Flexbox gives us a new value for the display property (the box value), and eight new properties:

box-orient
box-pack
box-align
box-flex
box-flex-group
box-ordinal-group
box-direction
box-lines

### display: box
This new value for the display style opts this element and its immediate children into the flexible box model. The flexbox model works only with immediate children.
* box-orient
Values: horizontal（水平） | vertical（垂直） | inherit
How should the box's children be aligned? There are two additional values inline-axis (the real default) and block-axis, but they map to horizontal and vertical respectively.
* box-pack
Values: start | end | center（中对齐） | justify(两端对齐)
Sets the alignment of the box along the box-orient axis. So if box-orient is horizontal it will chose how the box's children are aligned horizontally, and vice-versa.
* box-align
Values: start | end | center | baseline | stretch
Basically box-pack's brother property. Sets how the box's children are aligned in the box. If the orientation is horizontal it will decide the alignment vertically and vice-versa.

### Styles used on the box's children

box-flex
Values: 0 | Any integer
The flexibility ratio for this child. If a child had 1 and its sibling had 2, any additional space in the parent box would be consumed twice as much by the sibling. It defaults to 0 which is inflexible.
