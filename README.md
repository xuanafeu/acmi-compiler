# ACMI-Compiler

## What is this ?

This is an ACMI compiler more precisely a .flt file converter.
For Falcon BMS 4.33 and it should work with pretty much any version of falcon starting from OpenFalcon (Haven't tested anything before that, but the code was old AF so ...)

This program is meant to compile .flt files into .vhs file. 


.flt files are created and filled on the fly by falcon (wheter it's falcon BMS or openfalcon) and they are compiled into more readable .vhs files when exiting the 3D environment. The flt file is then deleted and you're left with a .vhs file that you can put into Falcon ACMI viewer (if you hate yourself) or Tacview


Now, you probably know that compiling big ACMI files takes a LOT of time, so I made this program to use the full potential of your computer to convert a .flt into .vhs 


## Modifications to the original code

So, what did I do ? 

- Changed the pointer lists to Vectors 
- Removed *continue*  that are both slow and make the code less readable
- Removed useless function that are only here for the ACMI Viewer in Falcon
- Added thread support for heavy task parallelization 

## Things be aware if you want to modify this code

- Building in Debug in Visual Studio will make the code slower because VS add a lot of debugging stuff to the vector (it's nearly **25 times slower** ) So use *release* if you want to evaluate your code performance

- The code uses some C++ 11 and C++ 14 features, feel free to use as much recent C++ you deem necessary to make the compilation faster

- the .licenseheader comes from a Visual Studio plugin called : [License Header Manager](https://marketplace.visualstudio.com/items?itemName=StefanWenig.LicenseHeaderManager#qna) , you don't need it to do PR or anything, I'm just lazy and it updates header automatically

## Special thanks

Thanks to this website for putting me on the path to find some falcon source code and an excellent .pdf describing how Falcon changed over the years

https://sites.google.com/site/falcon4sourcecode/

https://github.com/FreeFalcon/freefalcon-central