# System.Windows.Media.Imaging.BitmapImage::.cctor

- ea: `0xf8f20`
- end: `0xf915e`
- name: `System.Windows.Media.Imaging.BitmapImage::.cctor`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbfb60`

## string_xrefs

- `0xf8f88`: `UriSource`
- `0xf8f53`: `UriCachePolicy`
- `0xf90e9`: `CreateOptions`
- `0xf9123`: `CacheOption`

## pseudocode

```c

```

## disassembly

```asm
0xf8f20  ldnull
0xf8f21  stsfld   class [System]System.Net.Cache.RequestCachePolicy System.Windows.Media.Imaging.BitmapImage::s_UriCachePolicy
0xf8f26  ldnull
0xf8f27  stsfld   class [System]System.Uri System.Windows.Media.Imaging.BitmapImage::s_UriSource
0xf8f2c  ldnull
0xf8f2d  stsfld   class [mscorlib]System.IO.Stream System.Windows.Media.Imaging.BitmapImage::s_StreamSource
0xf8f32  call     valuetype [WindowsBase]System.Windows.Int32Rect [WindowsBase]System.Windows.Int32Rect::get_Empty()
0xf8f37  stsfld   valuetype [WindowsBase]System.Windows.Int32Rect System.Windows.Media.Imaging.BitmapImage::s_SourceRect
0xf8f3c  ldc.i4.0
0xf8f3d  stsfld   valuetype System.Windows.Media.Imaging.BitmapCreateOptions System.Windows.Media.Imaging.BitmapImage::s_CreateOptions
0xf8f42  ldc.i4.0
0xf8f43  stsfld   valuetype System.Windows.Media.Imaging.BitmapCacheOption System.Windows.Media.Imaging.BitmapImage::s_CacheOption
0xf8f48  ldtoken  System.Windows.Media.Imaging.BitmapImage
0xf8f4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf8f52  stloc.0
0xf8f53  ldstr    aUricachepolicy// "UriCachePolicy"
0xf8f58  ldtoken  [System]System.Net.Cache.RequestCachePolicy
0xf8f5d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf8f62  ldloc.0
0xf8f63  ldnull
0xf8f64  ldnull
0xf8f65  ldftn    void System.Windows.Media.Imaging.BitmapImage::UriCachePolicyPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf8f6b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf8f70  ldnull
0xf8f71  ldc.i4.0
0xf8f72  ldnull
0xf8f73  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceUriCachePolicy(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf8f79  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf8f7e  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf8f83  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::UriCachePolicyProperty
0xf8f88  ldstr    aUrisource_0// "UriSource"
0xf8f8d  ldtoken  [System]System.Uri
0xf8f92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf8f97  ldloc.0
0xf8f98  ldnull
0xf8f99  ldnull
0xf8f9a  ldftn    void System.Windows.Media.Imaging.BitmapImage::UriSourcePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf8fa0  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf8fa5  ldnull
0xf8fa6  ldc.i4.0
0xf8fa7  ldnull
0xf8fa8  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceUriSource(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf8fae  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf8fb3  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf8fb8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::UriSourceProperty
0xf8fbd  ldstr    aStreamsource// "StreamSource"
0xf8fc2  ldtoken  [mscorlib]System.IO.Stream
0xf8fc7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf8fcc  ldloc.0
0xf8fcd  ldnull
0xf8fce  ldnull
0xf8fcf  ldftn    void System.Windows.Media.Imaging.BitmapImage::StreamSourcePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf8fd5  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf8fda  ldnull
0xf8fdb  ldc.i4.0
0xf8fdc  ldnull
0xf8fdd  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceStreamSource(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf8fe3  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf8fe8  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf8fed  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::StreamSourceProperty
0xf8ff2  ldstr    aDecodepixelwid// "DecodePixelWidth"
0xf8ff7  ldtoken  [mscorlib]System.Int32
0xf8ffc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf9001  ldloc.0
0xf9002  ldc.i4.0
0xf9003  box      [mscorlib]System.Int32
0xf9008  ldnull
0xf9009  ldftn    void System.Windows.Media.Imaging.BitmapImage::DecodePixelWidthPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf900f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf9014  ldnull
0xf9015  ldc.i4.0
0xf9016  ldnull
0xf9017  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceDecodePixelWidth(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf901d  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf9022  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf9027  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::DecodePixelWidthProperty
0xf902c  ldstr    aDecodepixelhei// "DecodePixelHeight"
0xf9031  ldtoken  [mscorlib]System.Int32
0xf9036  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf903b  ldloc.0
0xf903c  ldc.i4.0
0xf903d  box      [mscorlib]System.Int32
0xf9042  ldnull
0xf9043  ldftn    void System.Windows.Media.Imaging.BitmapImage::DecodePixelHeightPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf9049  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf904e  ldnull
0xf904f  ldc.i4.0
0xf9050  ldnull
0xf9051  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceDecodePixelHeight(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf9057  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf905c  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf9061  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::DecodePixelHeightProperty
0xf9066  ldstr    aRotation_0// "Rotation"
0xf906b  ldtoken  System.Windows.Media.Imaging.Rotation
0xf9070  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf9075  ldloc.0
0xf9076  ldc.i4.0
0xf9077  box      System.Windows.Media.Imaging.Rotation
0xf907c  ldnull
0xf907d  ldftn    void System.Windows.Media.Imaging.BitmapImage::RotationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf9083  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf9088  ldnull
0xf9089  ldftn    bool System.Windows.Media.Imaging.ValidateEnums::IsRotationValid(object valueObject)
0xf908f  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0xf9094  ldc.i4.0
0xf9095  ldnull
0xf9096  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceRotation(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf909c  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf90a1  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf90a6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::RotationProperty
0xf90ab  ldstr    aSourcerect// "SourceRect"
0xf90b0  ldtoken  [WindowsBase]System.Windows.Int32Rect
0xf90b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf90ba  ldloc.0
0xf90bb  call     valuetype [WindowsBase]System.Windows.Int32Rect [WindowsBase]System.Windows.Int32Rect::get_Empty()
0xf90c0  box      [WindowsBase]System.Windows.Int32Rect
0xf90c5  ldnull
0xf90c6  ldftn    void System.Windows.Media.Imaging.BitmapImage::SourceRectPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf90cc  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf90d1  ldnull
0xf90d2  ldc.i4.0
0xf90d3  ldnull
0xf90d4  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceSourceRect(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf90da  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf90df  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf90e4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::SourceRectProperty
0xf90e9  ldstr    aCreateoptions// "CreateOptions"
0xf90ee  ldtoken  System.Windows.Media.Imaging.BitmapCreateOptions
0xf90f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf90f8  ldloc.0
0xf90f9  ldc.i4.0
0xf90fa  box      System.Windows.Media.Imaging.BitmapCreateOptions
0xf90ff  ldnull
0xf9100  ldftn    void System.Windows.Media.Imaging.BitmapImage::CreateOptionsPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf9106  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf910b  ldnull
0xf910c  ldc.i4.0
0xf910d  ldnull
0xf910e  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceCreateOptions(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf9114  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf9119  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf911e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::CreateOptionsProperty
0xf9123  ldstr    aCacheoption// "CacheOption"
0xf9128  ldtoken  System.Windows.Media.Imaging.BitmapCacheOption
0xf912d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf9132  ldloc.0
0xf9133  ldc.i4.0
0xf9134  box      System.Windows.Media.Imaging.BitmapCacheOption
0xf9139  ldnull
0xf913a  ldftn    void System.Windows.Media.Imaging.BitmapImage::CacheOptionPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xf9140  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xf9145  ldnull
0xf9146  ldc.i4.0
0xf9147  ldnull
0xf9148  ldftn    object System.Windows.Media.Imaging.BitmapImage::CoerceCacheOption(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xf914e  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xf9153  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Animatable::RegisterProperty(string name, class [mscorlib]System.Type propertyType, class [mscorlib]System.Type ownerType, object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback changed, class [WindowsBase]System.Windows.ValidateValueCallback validate, bool isIndependentlyAnimated, class [WindowsBase]System.Windows.CoerceValueCallback coerced)
0xf9158  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Imaging.BitmapImage::CacheOptionProperty
0xf915d  ret
```
