1. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the img element (including its margins)?

<div>
  <img src="#" alt="test" />
</div>

div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

img {
  border: 4px solid red;
  box-sizing: content-box;
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}

Width = 500 + 19 + 11 + 20 + 20  + 8 + 2 = 580
height = 300 + 20 +10 +10 + 10 + 8 + 2 = 360

2. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the section element (including its margins)? How does this differ from the result of the previous practice problem?

<div>
  <section>content</section>
</div>

div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

section {
  border: 4px solid red;
  box-sizing: content-box;
  display: block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}

width = 500 + 8 + 30 + 40 + 2 = 580
height = 300 + 8 + 30 + 20 + 2 = 360

3. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the em element (including its margins)?

<div>
  <em>content</em>
</div>

div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

em {
  border: 4px solid red;
  box-sizing: content-box;
  display: inline;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}

width = 8 + 30 + 40 + 500 + 2 = 580
height = 8 + 300 + 30 + 20 + 2 =360
*****INCORRECT****
Because em is inline the width, height, top and bottom margins are ignored
**Corrected
Assuming em requires 50px width
- 50 assumed width
- 8 for left and right borders
- 40 for left and right padding
- 11 for left margin
- 19 for right margin
- 2 for left and right borders of div
= 130px horizontal

Assume em requires 20px height
- 20 assumed height
- 8 for top and bottom borders
- 20 for top and bottom padding
- 0 for top and bottom margins (IGNORED due to inline)
- 2 for top and bottom borders of the div
= 50px height

4. Given the code below, what is the minimum width and height (in pixels) that the div needs to be to entirely contain the article element (including its margins)?

<div>
  <article>content</article>
</div>

div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

article {
  border: 4px solid red;
  box-sizing: border-box;
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}

Inline-block does NOT ignore height, width or margins
border-box width and height include padding and borders

width = 30 + 500 + 2 = 532
height = 300 + 30 + 2 = 332

5. Given the code below:

<div>
  <tag1>content</tag1><tag2>content</tag2>
</div>

div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: content-box;
  display: inline-block;
  margin: 0;
  padding: 0;
  width: 720px;
}

tag1, tag2 {
  box-sizing: border-box;
  height: 240px;
  margin: 0;
  padding: 0;
  width: 360px;
}

tag1 {
  background-color: yellow;
}

tag2 {
  background-color: lime;
}
Which of the following element pairs will display side-by-side in the <div>? Select all that apply:

Both elements are block elements.
Both elements are inline elements.
Both elements are inline-block elements.
One element is a block element, and one is an inline element.
One element is a block element, and one is an inline-block element.
One element is an inline element, and one is an inline-block element.

Answer = 2,3,6 (block elements never appear inline / side by side)

6. Will the following code display the two article boxes side-by-side? If not, why not? How would you fix it so that it places the boxes side-by-side?

<section>
  <article>content</article><article>more content</article>
</section>

section {
  background-color: yellow;
  border: 1px solid red;
  box-sizing: content-box;
  display: inline-block;
  height: 400px;
  margin: 0;
  padding: 20px;
  width: 900px;
}

article {
  background-color: lime;
  border: 1px solid blue;
  height: 100%;
  margin: 0;
  padding: 10px;
  width: 50%;
}

They will not display side by side as <article> is a block element. THis can be fixed by adding the display: inline-block property/value to article so they will be inline. In order to make them fit, we must also add the box-sizing: border-box; property/value to article. THis will allow the article to ignore the padding and border of the article.

7. Challenge. Given our solution to the previous question, what will happen if we put the article tags on separate lines?

<section>
  <article>content</article>
  <article>more content</article>
</section>

They should still appear side by side. As inline-block elements they will continue to render side by side before beginning a new line as long as there is width available. The lines in HTML are not translated into the rendering of the page.
***Incorrect****
The browser will see whitespace between the article elements (a newline and several spaces). The broswer condenses down this whitespace to a single space which will push are width over the available width on a single line.