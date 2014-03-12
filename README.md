PROGRAM: GetPixels v1

AUTHOR: Jenner Hanni <jeh.wicker@gmail.com> 
LICENSE: http://creativecommons.org/licenses/by-sa/4.0/
DATE: 11-March-2014

Reference:

[OpenCV 2.4.5.0 docs](http://docs.opencv.org/index.html)
[Stack Overflow](http://stackoverflow.com/questions/7899108/opencv-get-pixel-information-from-mat-image)

GetPixels is a simple tool that turns a color image into a text file
of grayscale pixels and back into a grayscale image. It's written for
a program exploring convolution kernels in image processing.

Usage: ./GetPixels.o <operation> <input file> <output file> <width> <height>

<operation>    1 for image -> text file
               2 for text file -> image
<image file>   relative path name to an image file
<pixel file>   relative path name to a text file of pixels
<width>        width of the image in pixels
<height>       height of the image in pixels

Example:

To get a text file of the pixels of a 800x600 mountain.png, try this:
  ./GetPixels.o 1 mountain.png pixels.txt 800 600
To reconstruct an image from that pixel file, try this:
  ./GetPixels.o 2 mountainReconstructed.png pixels.txt 240 320

Note: mountain.png and mountainReconstructed.png should be identical.

I built the program with OpenCV 2.4.8 and these GCC flags:
  g++ -o GetPixels.o GetPixels.cpp `pkg-config --cflags --libs opencv` \
  -L/usr/local/lib -lopencv_core -lopencv_highgui


