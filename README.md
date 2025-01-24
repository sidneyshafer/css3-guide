# CSS Sandbox Part 1

>Snippets, examples, and code breakdowns for learning the basics of CSS..

## Table of Contents

* **[CSS Basics](#css-basics)**
    * [External CSS](#external-css)
    * [Internal CSS](#internal-css)
    * [Inline CSS](#inline-css---not-recommend-as-best-practice)
    * [CSS Rules and Specificity](#css-rules-and-specificity)
    * [Best Practices](#best-practices)
* **[Selectors](#selectors)**
    * [Element Selector](#element-selector)
    * [Class Selector](#class-selector)
    * [ID Selector](#id-selector)
    * [Multiple Selectors](#multiple-selectors)
    * [Nested Selector](#nested-selector)
    * [Selector Best Practices](#selector-best-practices)
* **[Fonts](#fonts)**
    * [Font Family](#font-family)
    * [Google Fonts](#google-fonts)
    * [Font Size](#font-size)
    * [Line Height](#line-height)
    * [Font Weight](#font-weight)
    * [Font Style](#font-style)
* **[Colors](#colors)**
    * [The Color Property](#the-color-property)
    * [Color Definitions in the CSS](#color-definitions-in-the-css)
    * [Colors Best Practices](#color-best-practices)
* **[Backgrounds and Borders](#backgrounds-and-borders)**
    * [Background Properties](#background-properties)
    * [Using Background Shorthand Property](#using-background-shorthand-property)
    * [Border Properties](#border-properties)
    * [Individual Border Sides](#individual-border-sides)
    * [Common Border Styles](#common-border-styles)
    * [Using Border Shorthand Property](#using-border-shorthand-property)
* **[CSS Box Model](#css-box-model)**
    * [Box Model Overview](#box-model-overview)
    * [CSS Reset](#css-reset)
    * [Padding](#padding)
    * [Margin](#margin)
* **[Float and Align Properties](#float-and-align-properties)**
    * [Text Alignment](#text-alignment)
    * [Clearfix](#clearfix)
    * [Float Layout](#float-layout)

## CSS Basics

>CSS stands for **Cascading Style Sheets**

### External CSS
```
<link rel="stylesheet" href="css/style.css">
```
* Links to an external CSS file. In this case, it is located at `css/style.css` (in a folder named `css`).
* External CSS keeps styles separate from HTML, improving maintainability and reusability across multiple webpages.
* Any CSS rules in `css/style.css` are applied to this document.

### Internal CSS
```
<style>
    h2 {
        color: green;
    }
</style>
```
* Internal CSS requires the `<style></style>` element within the `<head>` tag.
* Internal CSS applies styles to this specific HTML document without requiring an external file.
* Internal styles are only applied to the document in which it is defined in.
* This is useful for quick styles or when external styles may not be practical.
* In this example, the `<h2>` elements in the document will have green text (`color: green`).

### Inline CSS - Not Recommend as Best Practice
```
<h1 style="color: red;">Heading One</h1>
```
* Adds CSS directly to the `style` attribute of an HTML element.
* Inline CSS is used for quick, specific styling for individual elements.
* **Generally not recommended because it mixes style with structure, making it harder to maintain.**

### CSS Rules and Specificity
Document styles follow a **CSS specificity hierarchy**:
1. **Inline CSS** has the highest specificity and overrides both internal and external CSS.
2. **Internal CSS** takes precedence over external CSS but can be overridden by inline styles.
3. **External CSS** has the lowest specificity but provides a global, maintainable styling approach.

### Best Practices
1. **Use External CSS**: Keep styling separate from HTML, making the code cleaner and easier to maintain.
2. **Limit Internal CSS**: Useful for specific pages or testing, but not ideal for large projects.
3. **Avoid Inline CSS**: Difficult to maintain and does not support reusability.

>See full source code for this section [01-basic.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/01-basic.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Selectors

>CSS selectors are used to apply styles to specific elements based on their type, class, ID, or hierarchy.

### Element Selector
```
body {
    background-color: #333;
}
```
* Targets all `<body>` elements.
* Element selectors apply styles to all elements of a specific type.
* In this example, sets the `background-color` property to a dark gray (`#333`).


### Class Selector
```
.primary-heading {
    color: green;
}
...

<h2 class="primary-heading">Welcome</h2>
```
* Targets all elements with the class `primary-heading`.
* Class names start with a period (`.`).
* Classes are reusable and can be applied to multiple elements.

### ID Selector
```
#welcome {
   background-color: #f4f4f4;
}
...

<div id="welcome">
```
* Targets the element with the ID `welcome`.
* An ID starts with a hash symbol (`#`).
* IDs are unique and are used to style a single element. They should not be used on multiple elements in a document.

### Multiple Selectors
```
#welcome, #about {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 5px;
}
```
* Targets the elements with the IDs `welcome` and `about`.
* Multiple selectors allow applying the same styles to several elements, separated by commas.

### Nested Selector
```
#welcome p {
    font-size: 20px;
}
...

<div id="welcome">
      <h2 class="primary-heading">Welcome</h2>
      <p>...</p>  <!-- Targets this element -->
</div>
```
* In this case, targets `<p>` elements that are children of the element with the ID `welcome`.
* Nested (or descendant) selectors target elements based on their parent-child relationship.
* These styles will set the font size of the paragraph inside `#welcome` to `20px`.

### Selector Best Practices
* **Use Classes (`.classname`) for Reusability**: Prefer classes for styles that might apply to multiple elements.
* **Use IDs (`#id`) Sparingly**: IDs should be unique to each element within each document and used only when necessary.
* **Leverage Specificity**: Combine selectors (e.g., `#welcome p`) for precise targeting without overusing inline styles.
* **Keep Styles Organized**: Group related styles together (e.g., `#welcome` and `#about`).

>See full source code for this section [02-selectors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/02-selectors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Fonts

### `font-family`
```
body {
    font-family: 'Roboto', sans-serif;
}
```
* The `font-family` property defines the typeface for text. 
* In this example, `'Roboto'` is the **primary font** used for the document (Roboto is a **[Google Font](#google-fonts)**).
* `sans-serif` is the generic **fallback font**. If the browser cannot load Roboto, it will use any available sans-serif font.

### Google Fonts

```
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```
* Statement importing a font from the Google Fonts library using the `<link>` tag in the HTML document.
* This fetches the `'Roboto'` font from Google Fonts and makes it available for use in the stylesheet.

>See more about using **[Google Fonts](https://fonts.google.com/)**

### `font-size`
```
body {
   font-size: 18px;
}
```
* The `font-size` property controls the size of the text.
* In this example, font size is set to `18px` for the entire document, meaning all text inherits this size unless overridden by more specific rules.

### `line-height`
```
body {
   line-height: 1.6em;
}
```
* The `line-height` property controls the vertical spacing between lines of text.
* Line height improves readability by adding spacing between lines of text.
* In this example, the value `1.6em` means the line height is 1.6 times the font size (`18px × 1.6 = 28.8px`).

### `font-weight`
```
#welcome p span {
   font-weight: bold;
}
```
* The `font-weight` property controls the thickness of the font.
* The `bold` value increases the font's weight, making the text appear thicker.
* Font weight values are specified by keyword or numeric values.

**Keyword Font Weight Values**
| Keyword   | Description |
| --------- | ----------- |
| `normal`  | The default font weight, which is equal to **400** |
| `bold`    | The bold font weight, which is equal to **700** |
| `lighter` | Makes the font weight one level lighter than the parent element |
| `bolder`  | Makes the font weight one level heavier than the parent element |

**Numeric Font Weight Values**
| Keyword   | Description |
| --------- | ----------- |
| `100`     | Thin |
| `200`     | Extra light |
| `300`     | Light |
| `400`     | Normal |
| `500`     | Medium |
| `600`     | Semi bold |
| `700`     | Bold |
| `800`     | Extra bold |
| `900`     | Black |

### `font-style`
```
#about p span {
   font-style: italic;
}
```
* The `font-style` property defines whether text is normal, italicized, or oblique.
* The `italic` value applies an italic style to the font, slanting it to the right.

>See full source code for this section [03-fonts.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/03-fonts.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Colors

### The `color` Property
* The `color` property is used to set the text color of an element.
* The value of the `color` property can be specified using:
    * Named colors
    * RGB values
    * Hexadecimal values

### Color Definitions in the CSS

**Color Name**
```
h1 {
   color: red;
}
```
* The text color is set to `red`, a predefined color name.
* CSS supports a set of standard color names (e.g., red, blue, green, etc.). 
* While convenient, they are limited in number and often not specific enough for detailed designs.

**RGB Color**
```
h2 {
   color: rgb(255, 255, 120);
}
```
* The `rgb()` function allows specifying colors using the Red, Green, and Blue values (in that specific order).
* Each color value (Red, Green, and Blue) can range from 0 (none of that color) to 255 (full intensity of that color).
* RGB provides precise control over the color, and allows for blending and transparency when combined with `rgba()`.
* In the example above:
    * Red: Full intensity (255).
    * Green: Full intensity (255).
    * Blue: Medium intensity (120).

**Hexadecimal Color**
```
h3 {
   color: #088faf;
}
```
* Hexadecimal colors are defined using a `#` followed by six hexadecimal digits (base 16).
* The format is `#RRGGBB`, where:
    * `RR` represents the red component.
    * `GG` represents the green component.
    * `BB` represents the blue component.
* The values range from 00 to FF, which is the same as 0 to 255 in RGB. 
* Setting all three values to 00 results in black, and setting all three values to FF results in white.
* Some common hexadecimal colors include: `#333` (dark gray), `#ccc` (medium-light gray), `#ddd` (lighter gray), `#f4f4f4` (very light gray)

### Color Best Practices
* Use a consistent color format throughout a project for maintainability.
* Consider accessibility, such as sufficient contrast for readability.

>See full source code for this section [04-colors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/04-colors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Backgrounds and Borders

### Background Properties
| Property           | Description |
| ------------------ | ----------- |
| `background-color` | Specifies the background color to be used |
| `background-image` | Specifies one or more background images to be used |
| `background-position` | Specifies the position of the background images |
| `background-size` | Specifies the size of the background images |
| `background-repeat` | Specifies how to repeat the background images |
| `background-origin` | Specifies the positioning area of the background images |
| `background-clip` | Specifies the painting area of the background images |
| `background-attachment` | Specifies whether the background images are fixed or scrolls with the rest of the page |

```
#box-1 {
   background-color: #ccc;
}
```
* Sets the background color to a light gray using the color code `#ccc`.

## Using Background Shorthand Property

**Example 1**
```
#box-2 {
   background: #333;
}
```
* When using the shorthand property, the order of the property values are:
    1. `background-color`
    2. `background-image`
    3. `background-repeat`
    4. `background-attachment`
    5. `background-position`

* Does not matter if one of the property values is missing, as long as the other ones are in this order.

**Example 2**
```
#box-3 {
   background: url('./img/stars.jpg') no-repeat center center/cover;
}
```
* Sets the background to an image located at `./img/stars.jpg`.
* `no-repeat`: prevents the image from repeating.
* `center center`: centers the image both horizontally and vertically.
* `cover`: ensures the image covers the entire area of the box while maintaining its aspect ratio.

**Example 3**
```
#box-4 {
    background: url('./img/leaf.png') no-repeat center center;
    background-attachment: fixed;
}
```
* Sets the background to an image located at `./img/leaf.png`.
* `no-repeat`: prevents the image from repeating.
* `center center`: centers the image both horizontally and vertically.
* `background-attachment: fixed;`
    * Fixes the background image so that it does not scroll with the rest of the page. 
    * The image remains static while the content scrolls.

## Border Properties
| Property           | Description |
| ------------------ | ----------- |
| `border-style`     | Determines the type of border |
| `border-width`     | Sets the width of the border |
| `border-color`     | Specifies the border color |
| `border-radius`    | Creates rounded corners for elements |

## Individual Border Sides
* CSS allows you to style each side of a border individually, giving flexibility in design (top, right, bottom, and left):
    * `border-top-[type]`
    * `border-right-[type]`
    * `border-bottom-[type]`
    * `border-left-[type]`

* `[type]` is optional and can be any border property type, including: `style`, `width`, `color`, or `radius`.

**Example**
```
#box-2 {
    border-top: blue solid 5px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}
```
* `border-top: blue solid 5px;`
    * Sets the top border to a color of `blue`, a border style of `solid`, and a border width of `5px`.
* `border-top-left-radius: 10px;`
    * Defines a border radius of `10px` at the top left corner.
* `border-top-right-radius: 10px;`
    * Defines a border radius of `10px` at the top right corner.

## Common Border Styles
The `border-style` property specifies the type of border. Below is a list of common border style types.

| Border Style | Description |
| ------------ | ----------- |
| `dotted`     | Defines a dotted border |
| `dashed`     | Defines a dashed border |
| `solid`      | Defines a solid border  |
| `double`     | Defines a double border |
| `groove`     | Defines a 3D grooved border. The effect depends on the `border-color` value |
| `ridge`      | Defines a 3D ridged border. The effect depends on the `border-color` value |
| `inset`      | Defines a 3D inset border. The effect depends on the `border-color` value |
| `outset`     | Defines a 3D outset border. The effect depends on the `border-color` value |
| `none`       | Defines no border |
| `hidden`     | Defines a hidden border |

>Read more about border styles and code examples [CSS Border Style](https://www.w3schools.com/css/css_border.asp)

## Using Border Shorthand Property
```
#box-1 {
    border: 3px solid red;
}
```
* The `border` property is a shorthand property for the following individual border properties:
    * `border-width`
    * `border-style`
    * `border-color`
* In this example, border width is set to `3px`, border style is set to `solid`, and border color is set to `red`.
* Border shorthand can also be used in conjunction with more precise border sides:
    * `border-top`
    * `border-right`
    * `border-bottom`
    * `border-left`

    * Example: `border-top: blue solid 5px;`

>Read more about borders and border properties [CSS Borders](https://www.geeksforgeeks.org/css-borders/)

>See full source code for this section [05-backgrounds-borders.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/05-backgrounds-borders.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## CSS Box Model

## Box Model Overview
![CSS Box Model Image](/source-code/img/box-model.png)

The box model consists of four layers:
* **Content**: The actual text or element inside the box.
* **Padding**: Space between the content and the border.
* **Border**: Surrounds the padding; it adds a defined boundary to the element.
* **Margin**: Space outside the border to separate the element from others.

### CSS Reset
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
* **Universal Selector (`*`)**: Applies style rules to all elements in a document.
* `margin: 0;` and `padding: 0;`: Removes default browser margins and padding.
* `box-sizing: border-box;`: Ensures the width and height of elements include the padding and border but exclude the margin.

### Padding
```
.box {
    /* Padding on all sides */
    padding: 20px;

    /* Padding per side */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;

    /* Padding shorthand = top, right, bottom, left */
    padding: 10px 20px 10px 20px;

    /* Padding shorthand = top/bottom left/right */
    padding: 10px 20px;
}
```
* **Padding is the space between the content and the element's border.**
* Specifying the padding for each side of an element:
    * `padding-top`
    * `padding-right`
    * `padding-bottom`
    * `padding-left`

**Padding Shorthand Property**
* The `padding` property is a shorthand property for the following patterns:
    * `padding-top`
    * `padding-right`
    * `padding-bottom`
    * `padding-left`

**Padding Property Values**
* `length` - specifies a padding in `px`, `pt`, `cm`, `em`, `rem`, etc.
* `%` - specifies a padding in % of the width of the containing element
* `inherit` - specifies that the padding should be inherited from the parent element

* Example with **four** values:
    * `padding: 10px 20px 10px 20px;`
    * Top padding are 10px
    * Right padding are 20px
    * Bottom padding are 10px
    * Left padding are 20px

* Example with **three** values:
    * `padding: 10px 20px 30px;`
    * Top padding are 10px
    * Right **and** left paddings are 20px
    * Bottom padding are 30px

* Example with **two** values:
    * `padding: 10px 20px;`
    * Top **and** bottom paddings are 10px
    * Right **and** left paddings are 20px

* Example with **one** value:
    * `padding: 20px;`
    * Top, bottom, right, and left paddings are all 20px

### Margin
```
.box {
    /* Margin on all sides */
    margin: 20px;
    
    /* Margin per side */
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 10px;
    margin-left: 20px;

    /* Margin shorthand = top, right, bottom, left */
    margin: 10px 20px 10px 20px;

    /* Margin shorthand = top/bottom left/right */
    margin: 10px 20px;
}
```
* **Margin is the space outside the border, separating the element from adjacent elements.**
* Margin properties function similar to padding.
* Specifying the margin for each side of an element:
    * `margin-top`
    * `margin-right`
    * `margin-bottom`
    * `margin-left`

**Margin Property Values**
* `auto` - the browser calculates the margin
* `length` - specifies a margin in `px`, `pt`, `cm`, `em`, `rem`, etc.
* `%` - specifies a margin in % of the width of the containing element
* `inherit` - specifies that the margin should be inherited from the parent element

**Margin Shorthand Property**
* The `margin` property is a shorthand property for the following patterns:
    * `margin-top`
    * `margin-right`
    * `margin-bottom`
    * `margin-left`

* Example with **four** values:
    * `margin: 10px 20px 10px 20px;`
    * Top margin are 10px
    * Right margin are 20px
    * Bottom margin are 10px
    * Left margin are 20px

* Example with **three** values:
    * `margin: 10px 20px 30px;`
    * Top margin are 10px
    * Right **and** left margins are 20px
    * Bottom margin are 30px

* Example with **two** values:
    * `margin: 10px 20px;`
    * Top **and** bottom margins are 10px
    * Right **and** left margins are 20px

* Example with **one** value:
    * `margin: 20px;`
    * Top, bottom, right, and left margins are all 20px

>See full source code for this section [06-box-model.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/06-box-model.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Float and Align Properties

### Text Alignment
```
.box p {
    text-align: left;
    text-align: center;
    text-align: right;
    text-align: justify;
}
```
The `text-align` property aligns text within an element.

**Text Align Values**
| Value    | Description |
| -------- | ----------- |
| `left`   | Aligns text to the left (**default**) |
| `center` | Centers text horizontally |
| `right`  | Aligns text to the right |
| `justify`| Distributes text evenly across the width of the element, making the lines appear neat and straight |

### Clearfix
```
.clr {
   clear: both;
}

...

<div class="container">
      <div id="box-1" class="box">
         ...
      </div>
      <div id="box-2" class="box">
        ...
      </div>
      <div id="box-3" class="box">
        ...
      </div>
      <div class="clr"></div>
      <div id="box-4" class="box">
        ...
      </div>
</div>
```
* Ensures that elements following floated elements start below them, not next to them.
* In this example, it is used to clear the float after `#box-2` and `#box-3`, allowing `#box-4` to appear on a new line.

### Float Layout
```
#box-2 {
   float: left;
   width: 68%;
}
```
* `float: left;`: Positions the `#box-2` element to the left within the parent element (which in this case is `.container`).
* `width: 68%;`: Specifies a width for `#box-2` to occupy 68% of the container's width.

```
#box-3 {
   float: right;
   width: 30%;
}
```
* `float: right;`: Positions the `#box-3` element to the right within the parent element (which in this case is `.container`).
* `width: 30%;`: Specifies a width for `#box-3` to occupy 30% of the container's width.

>See full source code for this section [07-float-align.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/07-float-align.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>