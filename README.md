📦 CSS Flexbox – Complete Notes (README.md)
📌 Introduction

Flexbox (Flexible Box Layout Module) is a one-dimensional CSS layout system used to align and distribute space among items in a container, even when their size is unknown or dynamic.

Works in row OR column

Best for components, not full-page layouts

Solves alignment, spacing, and responsiveness issues

🎯 Why Flexbox?

Before Flexbox:

Vertical centering was painful

Layouts broke on screen resize

Float & position hacks everywhere

With Flexbox:

Easy alignment

Responsive by default

Clean, readable CSS

🧱 Basic Terminology
Term	Description
Flex Container	Parent element with display: flex
Flex Items	Direct children of the container
Main Axis	Primary direction (row / column)
Cross Axis	Perpendicular to main axis

Default:
Main Axis → Horizontal
Cross Axis → Vertical

🛠️ Creating a Flex Container
.container {
  display: flex;
}

<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>


⚠️ Only direct children become flex items.

🔀 flex-direction

Defines the direction of the main axis.

.container {
  flex-direction: row;
}

Values
Value	Description
row	Left → Right (default)
row-reverse	Right → Left
column	Top → Bottom
column-reverse	Bottom → Top
Example
.container {
  display: flex;
  flex-direction: column;
}


➡ Items stack vertically.

🔁 flex-wrap

Controls whether items wrap to the next line.

.container {
  flex-wrap: wrap;
}

Values
Value	Behavior
nowrap	Single line (default)
wrap	Wraps to next line
wrap-reverse	Reverse wrapping
Example
.container {
  display: flex;
  flex-wrap: wrap;
}

.item {
  width: 200px;
}


➡ Items wrap when space is insufficient.

🔗 flex-flow (Shorthand)
flex-flow: row wrap;


Equivalent to:

flex-direction: row;
flex-wrap: wrap;

📏 justify-content (Main Axis Alignment)

Aligns items along the main axis.

justify-content: center;

Values
Value	Use Case
flex-start	Default
center	Center items
flex-end	End alignment
space-between	Equal space between
space-around	Space around items
space-evenly	Equal spacing everywhere
Example
.container {
  display: flex;
  justify-content: space-between;
}

📐 align-items (Cross Axis Alignment)

Aligns items along the cross axis.

align-items: center;

Values
Value	Meaning
stretch	Default
center	Center vertically
flex-start	Top
flex-end	Bottom
baseline	Align text baseline
Example
.container {
  display: flex;
  height: 200px;
  align-items: center;
}

🎯 Perfect Centering (Most Important Example)
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}


➡ Centers content horizontally and vertically.

📦 align-content (Multiple Rows Only)

⚠️ Works only when flex-wrap: wrap is enabled

align-content: space-between;


Controls spacing between rows, not items.

Example
.container {
  display: flex;
  flex-wrap: wrap;
  height: 400px;
  align-content: space-around;
}

👶 Flex Item Properties
🔢 order

Changes visual order.

.item1 { order: 2; }
.item2 { order: 1; }


➡ Item2 appears first.

📈 flex-grow

Controls how much free space an item consumes.

.item {
  flex-grow: 1;
}


Example:

.item1 { flex-grow: 1; }
.item2 { flex-grow: 2; }


➡ Item2 takes twice the space.

📉 flex-shrink

Controls shrinking when space is limited.

.item {
  flex-shrink: 0;
}

📏 flex-basis

Initial size before grow/shrink.

.item {
  flex-basis: 200px;
}

⚡ flex (Shorthand)
flex: 1 1 200px;


Equivalent to:

flex-grow: 1;
flex-shrink: 1;
flex-basis: 200px;

🎯 align-self

Overrides alignment for one item.

.item {
  align-self: flex-end;
}

🧠 Real-World Examples
🔹 Navigation Bar
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

🔹 Card Layout
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

🔹 Sidebar + Content Layout
.layout {
  display: flex;
}

.sidebar {
  width: 250px;
}

.content {
  flex-grow: 1;
}

❌ Common Mistakes

Using align-content instead of align-items

Forgetting flex-wrap

Expecting Flexbox to work on nested elements

Using Flexbox instead of Grid for 2D layouts

🆚 Flexbox vs Grid
Feature	Flexbox	Grid
Dimension	1D	2D
Best For	Components	Full layouts
Control	Content-based	Layout-based
✅ Final Notes

Flexbox is mandatory knowledge

If alignment confuses you → revisit main vs cross axis

Master Flexbox before learning Grid
