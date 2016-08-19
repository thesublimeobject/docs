# Images

## File Naming and Folder Structure

### Folders

when the final PSD is delivered to the web team, please send along all images and icons that are finalized in structured folders. i know that a lot of times not all of the images are finalized at this point, and that's okay; but please send along all finalized images at the time of delivery. the structure of your folders should look something like this (example from p9):

```
/img
	/banner
	/bg
	/logo
	/logos
	/social
	/icons
	/favicons
	/team
	/misc
```

this is generalized and isn't the same for every site, but we try to keep it as consistent as possible, as it makes developing and fetching the images *much* easier when they are in a structured and logical format. please do not use capital letters or spaces in your folder names. if the design team delivers files in a consistent and structures format, like so, it saves us a lot of time re-naming and re-structuring the folders and files.

### File Naming

1. as above, please never use spaces or capital letters when naming files. 
2. when naming files, default to camel-case `thisIsAFileName.jpg`, or in cases where the file is a modified object itself, use `--`.
3. for example, in the /banner folder, there is likely several banners for different pages. to name these, i usually use a structure such as this:

```
/img 
	/banner
		banner--home.jpg
		banner--consumer.jpg
		banner--contact.jpg
```
this is descriptive on multiple layers, and extremely helpful to us.

another example of this, which might make more intuitive sense, is when naming icons or logos:

```
/img
	/icons
		arrow--down.svg
		arrow--up.svg
		firetruck.svg
		gears.svg
	/logo
		logo.svg
		logo--white.svg
		logo--reverse.svg
		logo--color.svg
```

for many SVGs, we can change the color by writing CSS, although for some more complexly-colored logos it is very difficult to change the color patterns. so while it is encouraged to generally save most icons in whatever the base color is, please save all versions of the logos (unless in the exceptional case that they are one-colored).

### What file-type should I use?

1. Use and SVG for all images that can possibly be rendered as a vector. The file sizes are *much* smaller. For example, the NWEF logo saved as an svg is ~3k; when saved as a JPG it is ~10K; and when saved as a PNG it is ~8K. This might not seem like a huge difference to you, but on a page where there are maybe 40 images, it makes a huge difference. especially since JPGs and PNGs need to make a new server request for every image (very costly), while SVGs are rendered and drawn by the browser in real-time, negating the need for a server request.
2. any image that contains transparency should be saved as a PNG.
3. anything else should be saved as a JPG.
4. if you need to save something as a GIF, you'll already know it.

## Sizing

For the most part, sizing can be static because that WP will automatically resize the images based on the options I have selected when you import each image into WP. Nonetheless, ocassionally we might need differently sized images for whatever reason, accommodating for desktop, mobile, tablet, etc. Depending on the context of the image, these sizes will vary widely; but most commonly these are some decent guidelines to follow for differently sized devices. I'll use a banner (or full-bleed) image as an example:

1. large: 1600px-2400px, ~1920px; the higher end of this range is really only necessary for extremely important images that need to be very sharp, perhaps a landing image for example.
2. medium: 1024px-1280px
3. small: 640px-768px

** as we begin to have more time to optimize for different devices, we may need to increase some of these sizes to accomodate for retina screens too, which we do not always do. retina screens tend to be 1.5x-2x the pixel density of a normal screen, which means for an image to look natively crisp a banner image may need to be as large as 4000px-5000px. these file sizes are very, very large, but can be optimized to only be delivered to computers which actualyl have a retina screen.

#### how do i know what size it needs to be?
sometimes, i will not have built out a development size yet, and you might need to ask me. that's fine. i can estimate it, usually. but, it's also very easy to figure out what size you might need on your own. 

let's say that you have an image that will probably be about the same size as the blocks on [vexata](http://vex.kbddev.io).

1. go to that site, whichever one it is, vexata in this case (use chrome).
2. scroll down to the image's location.
3. right-click the image, and select `inspect`.
4. the code inspector should pop up from the bottom with that image highlighted in the console. if you hover over this highlighted element with your mouse, it will also become highlighted in the browser showing you both the class of the image, and more importantly, the dimensions (584 x 584 in this case). this is a great way to estimate the sizes of the images you might need, and the same way that bryan and i do it. in order to be safe, you'll probably want to expand your browser to see the maximum size of that image. i'm just on my laptop right now, so if i expanded my screen on a monitor it might end up that the image expands slightly as the page expands, and in this case, you're going to want to choose the largest possible size in order to be sure that you do not pick and image that is too small. the more you try this, the easier it will be to understand the range of sizes needed for certain areas of the websites you're designing.


## JPGs

1. `cmd + opt + shift + s` OR `export => save for web`
2. JPEG
3. Progressive
4. quality between 60 and 80 depending on the type of image and how high the resolution needs to be for the type of image. this tends to be situation dependent.
5. For the most part, you never want and image to really be any bigger than 100K. This is obviously situationally dependent, also. Some of the larger banner images that need to be slightly higher quality can, at times, be ~300K or so depending on their dimensions. But at all costs, try to keep them as small as possible without sacrificing too much intergrity.

## PNGs

### pngquant
1. [Download](https://github.com/pornel/pngquant-photoshop)
2. unzip
3. open terminal (cmd + space => terminal)
4. `cd "/Volumes/Macintosh HD/Applications"`
5. Open photoshop, and check which version you're running: Photoshop CC... => About Photoshop CC (I'm running 2015.5
6. `cd "Photoshop CC 2015.5"`
7. `mkdir Plug-ins && cd Plug-ins`
8. `open .` (this will open a Finder window in this directory)
9. copy the pngquant.plugin file from the zip into this directory.
10. restart photoshop

### saving PNGs
1. save as...
2. select "PNG for Web (pngquant)"


## SVGs

1. Trim the SVG to the edges. Occasionally when you do this, even if they are cropped correctly, they can be rendered in a way that part of the edges are cut off to some degree. Due to this, it's okay to leave a tiny bit of whitespace as a bounding box around the vector itself. Generally, this is a good idea as long as there's not too much space. This means ~1-2px maximally. This tends to happen more regularly, for whatever reason, with logos. Since these are obviously the most important part of a site, I recommend taking the safe route and usually leaving this bit of space around logos.
2. `cmd + shift + s` OR `save as...`
3. select "svg" => `save...`
4. All of the setting which are preselected should almost always be fine, except for one, which is under "Advanced Options." The property *CSS Elements* needs to be set to __style attributes__. This is *extremely important*.

# Videos

all videos should be compressed. I suggest downloading [Miro](https://www.macupdate.com/app/mac/33832/miro-video-converter), which is what I use, unless you know of a better option.

1. open Miro and drag the file, or choose it using the file navigator.
2. choose `format => video`
3. save/compress the file as both `webm` and `mp4`. the `webm` format is typically much smaller, although only about 2/3 of the browsers support it, so we have to serve `mp4` as a fallback.


# Fonts

1. please do not use more than two fonts except in very rare situations.
2. additionally, keep versions of weights and styles to a minimum. if you find yourself with the option of *several* weights (extra light, light, regular, book, medium, demi, bold), please be conservative and consistent. each weight and style used downloads at least two new glyph files, which can pile up very quickly. aside from images, fonts are the most expensive thing on a website, and typically, even more than images, block the initial rendering/loading of a site.
3. while i know that the new "libraries" feature in Adobe CC may help with the transfer of font-faces from design to dev, until we get this working cleanly, please be clear about which styles and weights you are using in the project.

# Colors

1. basically just refer to #3 from fonts. the same logic applies here.
2. do not use 593 different greys. only add a new grey when needed. usually no more than 2-4 different greys is necesssary. 
3. please always include the main color for the body copy. rarely does anyone do this, but still, please never, ever use straight black (#000) for the body copy unless there is a very good design reason for this. it's always harder to read than something more muted like #333, or something more fun like #3E454C.

