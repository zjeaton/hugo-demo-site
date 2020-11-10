+++
title = "Modal Image Pop-up"
date = "2020-10-20"
+++

![happy cat on its back with eyes closed](smiling-cat.jpg#float-right)

This is a demo of the functionality of the modal image pop-up that I wrote. If you would like the code for it, [head to the gist](https://gist.github.com/zjeaton/0cdd7e4bed9d292ab6f3d76b0369f16d). File placement is explained there.  

One feature of this gist is the ability to use a hashtag with the image filename, which allows for css styling. The image to the right of this paragraph was placed using this: `![happy cat on its back with eyes closed](smiling-cat.jpg#float-right)`

![bowl of granola and a glass of orange juice](granola-orange-juice.jpg#float-left)

I will share the image positioning styles that I use at the [end of this post](#custom-css). The pic to the left is formatted as `![bowl of granola and a glass of orange juice](granola-orange-juice.jpg#float-left)`. The three pics below this paragraph are positioned this way:

<div class="clearfix"></div>

```md
<div class="clearfix"></div>

![a colorful building and pink sky](colorful-building.jpg#left)
![a rocket with the letters USAF](usaf-rocket.jpg#right)
![the most adorable dachshund](dachshund.jpg#center)

<div class="clearfix"></div>
```
![a colorful building and pink sky](colorful-building.jpg#left)
![a rocket with the letters USAF](usaf-rocket.jpg#right)
![the most adorable dachshund](dachshund.jpg#center)

<div class="clearfix"></div>

The clearfix divs are there to prevent content below from hanging on the pics/content above. I try to avoid using html in my markdown, but the clearfix is pretty unobtrusive.

## Custom CSS

These styles are added to my custom css page and are used for image positioning within my content. I find this is all I need for a nice page layout.

```css
/* styles for floated images in post pages */
img[src$='#float-left'],
img[src$='#float-left-vert'],
img[src$='#left'],
img[src$='#float-left-60'],
img[src$='#float-left-50'],
img[src$='#float-left-40'] {
  float: left;
  margin-bottom: 1em;
  margin-top: 0em;
}

img[src$='#float-right'],
img[src$='#float-right-vert'],
img[src$='#right'],
img[src$='#float-right-60'],
img[src$='#float-right-50'],
img[src$='#float-right-40'] {
  float: right;
  margin-bottom: 1em;
  margin-top: 0em;
}

img[src$='#float-left'],
img[src$='#float-left-vert'],
img[src$='#float-left-40'] {
  margin-right: .7em;
}

img[src$='#float-right'],
img[src$='#float-right-vert'],
img[src$='#float-right-40'] {
  margin-left: .7em;
}

img[src$='#left'] {
  max-width: 32.5%;
}

img[src$='#right'] {
  max-width: 32.5%;
}

img[src$='#center'] {
  display: block;
  margin: auto;
  max-width: 32.5%;
  margin-bottom: 1em;
  margin-top: 0em;
}

img[src$='#float-left'] { 
  max-width: 50%;
}

img[src$='#float-left-vert'] { 
  max-width: 30%;
}

img[src$='#float-right'] {
  max-width: 50%;
}

img[src$='#float-right-vert'] {
  max-width: 30%;
}

@media (min-width: 650px) {
  img[src$='#float-left'],
  img[src$='#float-right'] {
    max-width: 45%;
  }
}

@media (min-width: 800px) {
  img[src$='#float-left'],
  img[src$='#float-right'] {
    max-width: 40%;
  }
}

img[src$='#float-left-60'] {
  width: calc(60% - .35em);
}

img[src$='#float-left-50'] {
  width: calc(50% - .35em);
  padding-right: .35em;
}

img[src$='#float-left-40'] {
  width: calc(40% - .35em);
}

img[src$='#float-right-60'] {
  width: calc(50% - .35em);
}

img[src$='#float-right-50'] {
  width: calc(50% - .35em);
  padding-left: .35em;
}

img[src$='#float-right-40'] {
  width: calc(40% - .35em);
}

.clearfix::before,
.clearfix::after {
  display: table;
  content: " ";
}

.clearfix::after {
  clear: both;
}
```