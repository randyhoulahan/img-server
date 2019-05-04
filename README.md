
# Circus Image Server
-------------------
Requirements
s3 bucket static hosting
cloudfront dist

Process Flow
1. request to cdn, returns if exists else 
2. returns request from object store, if it does not exists, object store temp redirects 307 if  matching 404 and key prefix to:
3. serverless function: serverless function processes image changes temp redirecting 307 to new resource using object store api uri

Original

https://images.circusliving.com/lizmcgrath1.jpg

## Formats
convert to: jpg,jpeg,webp,png,tiff

inputs: jpeg, png, webp, gif, svg

https://images.circusliving.com/lizmcgrath1.jpeg

https://images.circusliving.com/lizmcgrath1.webp

https://images.circusliving.com/lizmcgrath1.png

https://images.circusliving.com/lizmcgrath1.tiff

## Compression
convert to: jpg,jpeg,webp,png,tiff with a 10% to 90% compression.

https://images.circusliving.com/lizmcgrath1.min.jpg default: 80%

https://images.circusliving.com/lizmcgrath1.min1.jpg
default: 10%

https://images.circusliving.com/lizmcgrath1.min9.jpg
default: 90%

## resize:
https://images.circusliving.com/100x100/lizmcgrath1.jpg

keeps aspect ratio and uses 80% compression

## crop:
https://images.circusliving.com/c:southwest/lizmcgrath1.jpg

Smart crop options:

north, northeast, east, southeast, south, southwest, west, northwest, center

or

entropy: focus on the region with the highest Shannon entropy.https://en.wikipedia.org/wiki/Entropy_%28information_theory%29

or

attention: focus on the region with the highest luminance frequency, colour saturation and presence of skin tones.

## tint:
https://images.circusliving.com/t:255,0,0/lizmcgrath1.jpg

Tints the image with an RGB value.

## black & white ... greyscale
https://images.circusliving.com/greyscale/lizmcgrath1.jpg

## flip
https://images.circusliving.com/flip/lizmcgrath1.jpg

## flop
https://images.circusliving.com/flop/lizmcgrath1.jpg

## rotate
https://images.circusliving.com/r:90/lizmcgrath1.jpg

Rotate 90,180,270 degrees

## extract (crop with dementions)
https://images.circusliving.com/e:100,100,300,100/lizmcgrath1.jpg

Extract has 4 parameters left, top, width, height



todo:
svg optimize
animated gif optimize
automate cloudfront dist creation
automate bucket /key/prefix creation
azure version
google cloud version

