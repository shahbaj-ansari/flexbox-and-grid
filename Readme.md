# **Flexbox and Grid**
[Part 1 : CSS Flexbox](#css-flexbox)

[Part 2 : CSS Grid](#css-grid)

# **CSS Flexbox**

## Contents :
* Background 
* Basic Concept about CSS Flexbox
* Properties of Flexbox Container
* Properties of Flexbox Items

---
## Background 
The Flexible Box Module provides us a more efficient way to lay-out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word “flex”).

The main idea behind the flex layout is to give the container the ability to alter its items’ width/height and order to best fill the available space mostly to accommodate to all kind of display devices and screen sizes.

---

## Basic Concept about CSS Flexbox 
A Flexbox has a set of properties some of them are meant to be set on Flexbox Container to set the behaviour of its child and some are meant to be set on its Child (Flex Items) to set the behaviour of any child.
  * **Flexbox Container  :** 
 A Flexbox container is a box within which its child reside.Here we can define the behaviour of its children.

* **Flexbox Item  :** 
The direct child elements of a flex container automatically becomes flexible (flex) items.
* **main axis  :**
The main axis of a flex container is the primary axis along which flex items are laid out. By default it's on horizontal direction for row-wise flexbox but if we change to column-wise the primary axis will be in vertical direction.
* **cross axis  :**
The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction. 
* **main size  :** 
The length of the Flex container along the main axis is called main size.  
* **cross size  :**
The length of the Flex container along the cross axis is called cross size.  
* **main start and main end :**
The new flex items start from main start and move towards main end.
cross size.  
* **cross start and cross end :**
If flex-line has occupied full main size then the new flex line will start at cross start and succesive flex-lines will move towards cross end.

<img src="https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg" width="70%" >
---
## **Flexbox Container Properties** 

### **display**
The flex container becomes flexible by setting the display property to flex or inline flex.
```css
.container {
  display: flex;
}
```

### **flex-direction**
This property defines in which direction the container wants to place the flex items.
* **row (default)**: left to right
* **row-reverse**: right to left
* **column** : top to bottom.
* **column-reverse** : bottom to top

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg" width="60%">

### **flex-wrap**
The flex-wrap property specifies whether the flex items should wrap or not.
```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
  * **nowrap (default)**: all flex items will be on one line.

 * **wrap**: flex items will wrap onto multiple lines, from top to bottom.

 * **wrap-reverse**: flex items will wrap onto multiple lines from bottom to top.

### **flex-flow**
It is a shorthand property to set both flex-direction and flex flow.default calue is _row no-wrap_.
```css
.container {
  display: flex;
  flex-flow: row wrap;
}
```

### **justify-content**
This propert is used to align flex-item along the main axis.
```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly ;
}
```
* **flex-start (default)**: It aligns the flex items at the beginning of the container.
* **flex-end**: It aligns the flex items at the end of the container.
* **space-between**: It displays the flex items with equal space between the lines.
* **space-around**: The space-around value displays the flex items with space before, between, and after the lines.

### **align-items**
This Property is used to align flex items along the cross-axis.
```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```
*  **stretch (default)** : It stretches the flex items to fill the container.
* **flex-start** : It aligns the flex items at the top of the container.
* **flex-end** : It aligns the flex items at the bottom of the container.
* **center** : It aligns the flex items in the middle of the container.
* **baseline** : It aligns the flex items such as their baselines aligns.

## **Flexbox Item Properties** 
The direct child elements of a flex container automatically becomes flex items.

### **order**
This property specifies the order of the flex items. by default it is 0 for an item.
![order](https://css-tricks.com/wp-content/uploads/2018/10/order.sv)
```css
.item {
  order: 2;
}
```

### **flex-grow**
The flex-grow property specifies how much a flex item will grow relative to the rest of the flex items.by default it is 0.
If all items have flex-grow set to 1, then each flex item will be og equal lenght along main axis.
```css
.item {
  flex-grow: 1;
}
```
### **flex-shrink**
The flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items. default value is 1.
```css
.item {
  flex-shrink: 2;
}
```
### **flex-basis**
The flex-basis property sets the initial length of a flex item. It can be a length (e.g. 20%, 5rem,20px, etc.)
```css
.item {
  flex-basis: 20px;
}
```

### **flex**
The flex property is a shorthand property for the flex-grow, flex-shrink, and flex-basis properties.
```css
.item {
  flex: 1 1 0;
}
```
### **self-align**
The align-self property specifies the alignment for the selected item inside the flexible container.
The align-self property overrides the default alignment set by the container's align-items property.
```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

---
---
# CSS Grid
## Contents :
* Background 
* Properties of Grid Container
* Properties of Grid Items
---

## Background
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages.
CSS Grid Layout excels at dividing a page into major regions or defining the relationship in terms of size, position, and layer.

---
## Properties of CSS Grid Container
An HTML element becomes a grid container when its display property is set to grid or inline-grid.
```css
.container {
  display: grid; /* or inline grid*/
}
```

### **grid-template-columns**
The grid-template-columns property defines the number of columns in a grid layout, and it can define the width of each column.
The value is a space-separated-list, where each value defines the width of the respective column.

If we want our grid layout to contain 4 columns,we should specify the width of the 4 columns, or "auto" if all columns should havebe of same width.
```css
.container {
  display: grid;
  grid-template-columns: auto auto auto auto;
}
```
---
### **grid-template-rows**
The grid-template-rows property defines the height of each row.The value is a space-separated-list, where each value defines the height of the respective row.
```css
.container {
  display: grid;
  grid-template-rows: 80px 200px;
}
```
---
### **justify-content**
The justify-content property is used to align the whole grid inside the container. To let the justify-content work the total width of grid must be less than the container's width.
```css
.container {
  display: grid;
  justify-content: space-evenly | space-around | space-between | center | start | end;
}
```
---
### **align-content**
The align-content property is used to vertically align the whole grid inside the container. To let the justify-content work the total height of grid must be less than the container's height.
```css
.container {
  display: grid;
  align-content: center | space-evenly | space-around | space-between | start | end;
}
```
---
## Properties of CSS Grid Items
---
### grid-column-start, grid-column-end, grid-row-start, grid-row-end
 These four properties are used to set the location of a grid Item, grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.
```css
 .item {
  grid-column-start: <number> | <name> | span <number> | span <name> | auto;
  grid-column-end: <number> | <name> | span <number> | span <name> | auto;
  grid-row-start: <number> | <name> | span <number> | span <name> | auto;
  grid-row-end: <number> | <name> | span <number> | span <name> | auto;
}
```
---
 * **line**: can be a number to refer to a numbered grid line, or a name to refer to a named grid line
* **span number**: – the item will span across the provided number of grid tracks
* **span <name>**: – the item will span across until it hits the next line with the provided name
* **auto** – indicates auto-placement, an automatic span, or a default span of one.

example
```css
.item-a {
  grid-column-start: 2;
  grid-column-end: five;
  grid-row-start: row1-start;
  grid-row-end: 3;
}
```

<img src="https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row-start-end-01.svg" width="60%">

---
### grid-column, grid-row
It is a Shorthand property for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.
```css
.item {
  grid-column: <start-line> / <end-line> | <start-line> / span <value>;
  grid-row: <start-line> / <end-line> | <start-line> / span <value>;
}
```
Example;
```css
.item {
  grid-column: 3 / span 2; /* strart from 3rd column and span 2 columns*/
  grid-row: third-line / 4; /* start from 3rd row and end before 4th row*/
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/grid-column-row.svg" width="60%">

---
### grid-area
The grid-area property can be used as a shorthand property for the grid-row-start, grid-column-start, grid-row-end and the grid-column-end properties.

Values:

* **name** – a name of our choice
* **row-start  / column-start / row-end / column-end** 
* **number**
```css
.item {
  grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
}
```
Example
```css
.item-d {
  grid-area: 1 / col4-start / last-line / 6;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/grid-area.svg" width="60%">

----
### justify-self
This property aligns a grid item inside a cell along the row axis. This value applies to a grid item inside a single cell.

```css
.item {
  justify-self: start | end | center | stretch;
}
```
Values:
**start** – aligns the grid item to be flush with the start edge of the cell.

**end** – aligns the grid item to be flush with the end edge of the cell.

**center** – (default) aligns the grid item in the center of the cell.

**stretch** – fills the whole width of the cell (this is the default)
Example
```css
.item-a {
  justify-self: start;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/justify-self-start.svg" width="50%>

```css
.item-a {
  justify-self: end;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/justify-self-end.svg" width="50%">

---
### align-self
This property aligns a grid item inside a cell along the column axis. This value applies to the content inside a single grid item.
```css
.item {
  align-self: start | end | center | stretch;
}
```
Values:

**start** – aligns the grid item to be flush with the start edge of the cell.

**end** – aligns the grid item to be flush with the end edge of the cell.

**center** – aligns the grid item in the center of the cell.

**stretch** – (default) fills the whole height of the cell.
Example 1
```css
.item-a {
  align-self: start;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/align-self-start.svg" width=50%>

Example 2
```css
.item-a {
  align-self: end;
}
```
<img src="https://css-tricks.com/wp-content/uploads/2018/11/align-self-end.svg" width="50%">

Example 3
```css
.item-a {
  align-self: center;
}
```
<img src=https://css-tricks.com/wp-content/uploads/2018/11/align-self-center.svg width="50%" height="auto">

---
## **CSS Flexbox vs CSS Grid**

---
### bibliography
[w3shools](https://www.w3schools.com/css/default.asp)

[css-tricks](https://css-tricks.com/snippets)

[mozila-web-docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
