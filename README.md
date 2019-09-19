# ImageEditor
Image edit library on android platform, based on opengl es 2.0.

[Demo prebuilt apk (Chineese)](https://github.com/CreateChance/ImageEditor/raw/master/bin/ImageEditorDemoChineese.apk)

[Demo prebuilt apk (English)](https://github.com/CreateChance/ImageEditor/raw/master/bin/ImageEditorDemoEnglish.apk)

# Note
This library is still under developing, so do not use it on you product! 
## This is forked branch. All the screens are in english. Originally it's in Chineese.

Any contribution is welcome!
# Thanks
Part filter shader is from gpuimage: https://github.com/BradLarson/GPUImage

Transitions are from gl-transition: https://gl-transitions.com/

They did a great job!

ImageEditor library use FreeType 2.9.1 to render text to opengl texture, freetype site: https://www.freetype.org

Demo's icon is from: https://icons8.com , it is a good place to find beautiful icons for android and iOS.

Demo's font(chinese and english) is from: https://www.freechinesefont.com/, and they are free!

# Demo Screenshot

[See This](https://github.com/CreateChance/ImageEditor/wiki/ScreenShot)

# How to use?
It's easy to use, you just send operators to IEManager instance, and all is done!

For example, add lut filer to image like this:
1. create an operator
```
filterOp = new LookupFilterOperator.Builder()
                            .intensity(INTENSITY_VALUE)
                            .lookup(BitmapFactory.decodeStream(LOOK_UP_TABLE_STREAM)
                            .build();
```
2. add to IEManager api class
```
if (opAdded) {
    // you can render it right now.
    IEManager.getInstance().updateOperator(0, filterOp, true);
    // or render it later.
    IEManager.getInstance().updateOperator(0, filterOp, false);
} else {
    IEManager.getInstance().addOperator(0, filterOp, true);
}
```
That's all you need to do!
For more details about usage, [See This](https://github.com/CreateChance/ImageEditor/wiki/Helper).
# How to build?
To build this library, you need android sdk, ndk and gradle.
