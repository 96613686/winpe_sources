# System.Windows.ColorConvertedBitmapExtension::ProvideValue

- ea: `0x1c1b0`
- end: `0x1c2d1`
- name: `System.Windows.ColorConvertedBitmapExtension::ProvideValue`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1c1b0`
- `0x1c2e0`
- `0x38c40`
- `0x38c70`

## string_xrefs

- `0x1c1b8`: `ColorConvertedBitmapExtensionNoSourceImage`
- `0x1c1d0`: `ColorConvertedBitmapExtensionNoSourceProfile`
- `0x1c1f9`: `MarkupExtensionNoContext`
- `0x1c214`: `IUriContext`

## pseudocode

```c

```

## disassembly

```asm
0x1c1b0  ldarg.0
0x1c1b1  ldfld    string System.Windows.ColorConvertedBitmapExtension::_image
0x1c1b6  brtrue.s loc_1C1C8
0x1c1b8  ldstr    aColorconverted_0// "ColorConvertedBitmapExtensionNoSourceIm"...
0x1c1bd  call     string System.Windows.SR::Get(string id)
0x1c1c2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c1c7  throw
0x1c1c8  ldarg.0
0x1c1c9  ldfld    string System.Windows.ColorConvertedBitmapExtension::_sourceProfile
0x1c1ce  brtrue.s loc_1C1E0
0x1c1d0  ldstr    aColorconverted_1// "ColorConvertedBitmapExtensionNoSourcePr"...
0x1c1d5  call     string System.Windows.SR::Get(string id)
0x1c1da  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c1df  throw
0x1c1e0  ldarg.1
0x1c1e1  ldtoken  [System.Xaml]System.Windows.Markup.IUriContext
0x1c1e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c1eb  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1c1f0  isinst   [System.Xaml]System.Windows.Markup.IUriContext
0x1c1f5  stloc.0
0x1c1f6  ldloc.0
0x1c1f7  brtrue.s loc_1C225
0x1c1f9  ldstr    aMarkupextensio_0// "MarkupExtensionNoContext"
0x1c1fe  ldc.i4.2
0x1c1ff  newarr   [mscorlib]System.Object
0x1c204  dup
0x1c205  ldc.i4.0
0x1c206  ldarg.0
0x1c207  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c20c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c211  stelem.ref
0x1c212  dup
0x1c213  ldc.i4.1
0x1c214  ldstr    aIuricontext// "IUriContext"
0x1c219  stelem.ref
0x1c21a  call     string System.Windows.SR::Get(string id, object[] args)
0x1c21f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c224  throw
0x1c225  ldarg.0
0x1c226  ldloc.0
0x1c227  callvirt instance class [System]System.Uri [System.Xaml]System.Windows.Markup.IUriContext::get_BaseUri()
0x1c22c  stfld    class [System]System.Uri System.Windows.ColorConvertedBitmapExtension::_baseUri
0x1c231  ldarg.0
0x1c232  ldarg.0
0x1c233  ldfld    string System.Windows.ColorConvertedBitmapExtension::_image
0x1c238  call     instance class [System]System.Uri System.Windows.ColorConvertedBitmapExtension::GetResolvedUri(string uri)
0x1c23d  stloc.1
0x1c23e  ldarg.0
0x1c23f  ldarg.0
0x1c240  ldfld    string System.Windows.ColorConvertedBitmapExtension::_sourceProfile
0x1c245  call     instance class [System]System.Uri System.Windows.ColorConvertedBitmapExtension::GetResolvedUri(string uri)
0x1c24a  stloc.2
0x1c24b  ldarg.0
0x1c24c  ldarg.0
0x1c24d  ldfld    string System.Windows.ColorConvertedBitmapExtension::_destinationProfile
0x1c252  call     instance class [System]System.Uri System.Windows.ColorConvertedBitmapExtension::GetResolvedUri(string uri)
0x1c257  stloc.3
0x1c258  ldloc.2
0x1c259  newobj   instance void [PresentationCore]System.Windows.Media.ColorContext::.ctor(class [System]System.Uri)
0x1c25e  stloc.s  4
0x1c260  ldloc.3
0x1c261  ldnull
0x1c262  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1c267  brtrue.s loc_1C275
0x1c269  call     valuetype [PresentationCore]System.Windows.Media.PixelFormat [PresentationCore]System.Windows.Media.PixelFormats::get_Default()
0x1c26e  newobj   instance void [PresentationCore]System.Windows.Media.ColorContext::.ctor(valuetype [PresentationCore]System.Windows.Media.PixelFormat)
0x1c273  br.s     loc_1C27B
0x1c275  ldloc.3
0x1c276  newobj   instance void [PresentationCore]System.Windows.Media.ColorContext::.ctor(class [System]System.Uri)
0x1c27b  stloc.s  5
0x1c27d  ldloc.1
0x1c27e  ldc.i4.s 0xC
0x1c280  ldc.i4.2
0x1c281  call     class [PresentationCore]System.Windows.Media.Imaging.BitmapDecoder [PresentationCore]System.Windows.Media.Imaging.BitmapDecoder::Create(class [System]System.Uri, valuetype [PresentationCore]System.Windows.Media.Imaging.BitmapCreateOptions, valuetype [PresentationCore]System.Windows.Media.Imaging.BitmapCacheOption)
0x1c286  stloc.s  6
0x1c288  ldloc.s  6
0x1c28a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [PresentationCore]System.Windows.Media.Imaging.BitmapFrame> [PresentationCore]System.Windows.Media.Imaging.BitmapDecoder::get_Frames()
0x1c28f  ldc.i4.0
0x1c290  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [PresentationCore]System.Windows.Media.Imaging.BitmapFrame>::get_Item(!!T0)
0x1c295  stloc.s  7
0x1c297  ldloc.s  7
0x1c299  call     valuetype [PresentationCore]System.Windows.Media.PixelFormat [PresentationCore]System.Windows.Media.PixelFormats::get_Bgra32()
0x1c29e  ldnull
0x1c29f  ldc.r8   0.0
0x1c2a8  newobj   instance void [PresentationCore]System.Windows.Media.Imaging.FormatConvertedBitmap::.ctor(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource, valuetype [PresentationCore]System.Windows.Media.PixelFormat, class [PresentationCore]System.Windows.Media.Imaging.BitmapPalette, float64)
0x1c2ad  stloc.s  8
0x1c2af  ldloc.s  8
0x1c2b1  stloc.s  9
0x1c2b3  ldloc.s  8
0x1c2b5  ldloc.s  4
0x1c2b7  ldloc.s  5
0x1c2b9  call     valuetype [PresentationCore]System.Windows.Media.PixelFormat [PresentationCore]System.Windows.Media.PixelFormats::get_Bgra32()
0x1c2be  newobj   instance void [PresentationCore]System.Windows.Media.Imaging.ColorConvertedBitmap::.ctor(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource, class [PresentationCore]System.Windows.Media.ColorContext, class [PresentationCore]System.Windows.Media.ColorContext, valuetype [PresentationCore]System.Windows.Media.PixelFormat)
0x1c2c3  stloc.s  0xA
0x1c2c5  ldloc.s  0xA
0x1c2c7  stloc.s  9
0x1c2c9  leave.s  loc_1C2CE
0x1c2cb  pop
0x1c2cc  leave.s  loc_1C2CE
0x1c2ce  ldloc.s  9
0x1c2d0  ret
```
