# System.Windows.Controls.DocumentViewer::.cctor

- ea: `0x15ee50`
- end: `0x15f34e`
- name: `System.Windows.Controls.DocumentViewer::.cctor`
- size: `1278`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x159e0`
- `0x15a20`
- `0x15a50`
- `0x15a60`
- `0x15ff60`
- `0x160780`
- `0x24e850`

## string_xrefs

- `0x15f1b3`: `CanMoveUp`
- `0x15f1f0`: `CanMoveDown`
- `0x15f22d`: `CanMoveLeft`
- `0x15f26a`: `CanMoveRight`

## pseudocode

```c

```

## disassembly

```asm
0x15ee50  ldstr    aHorizontaloffs// "HorizontalOffset"
0x15ee55  ldtoken  [mscorlib]System.Double
0x15ee5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ee5f  ldtoken  System.Windows.Controls.DocumentViewer
0x15ee64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ee69  ldc.r8   0.0
0x15ee72  box      [mscorlib]System.Double
0x15ee77  ldc.i4   0x100
0x15ee7c  ldnull
0x15ee7d  ldftn    void System.Windows.Controls.DocumentViewer::OnHorizontalOffsetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15ee83  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15ee88  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15ee8d  ldnull
0x15ee8e  ldftn    bool System.Windows.Controls.DocumentViewer::ValidateOffset(object value)
0x15ee94  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x15ee99  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x15ee9e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::HorizontalOffsetProperty
0x15eea3  ldstr    aVerticaloffset// "VerticalOffset"
0x15eea8  ldtoken  [mscorlib]System.Double
0x15eead  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15eeb2  ldtoken  System.Windows.Controls.DocumentViewer
0x15eeb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15eebc  ldc.r8   0.0
0x15eec5  box      [mscorlib]System.Double
0x15eeca  ldc.i4   0x100
0x15eecf  ldnull
0x15eed0  ldftn    void System.Windows.Controls.DocumentViewer::OnVerticalOffsetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15eed6  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15eedb  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15eee0  ldnull
0x15eee1  ldftn    bool System.Windows.Controls.DocumentViewer::ValidateOffset(object value)
0x15eee7  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x15eeec  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x15eef1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::VerticalOffsetProperty
0x15eef6  ldstr    aExtentwidth// "ExtentWidth"
0x15eefb  ldtoken  [mscorlib]System.Double
0x15ef00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ef05  ldtoken  System.Windows.Controls.DocumentViewer
0x15ef0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ef0f  ldc.r8   0.0
0x15ef18  box      [mscorlib]System.Double
0x15ef1d  ldnull
0x15ef1e  ldftn    void System.Windows.Controls.DocumentViewer::OnExtentWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15ef24  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15ef29  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15ef2e  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15ef33  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ExtentWidthPropertyKey
0x15ef38  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ExtentWidthPropertyKey
0x15ef3d  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15ef42  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ExtentWidthProperty
0x15ef47  ldstr    aExtentheight// "ExtentHeight"
0x15ef4c  ldtoken  [mscorlib]System.Double
0x15ef51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ef56  ldtoken  System.Windows.Controls.DocumentViewer
0x15ef5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ef60  ldc.r8   0.0
0x15ef69  box      [mscorlib]System.Double
0x15ef6e  ldnull
0x15ef6f  ldftn    void System.Windows.Controls.DocumentViewer::OnExtentHeightChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15ef75  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15ef7a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15ef7f  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15ef84  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ExtentHeightPropertyKey
0x15ef89  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ExtentHeightPropertyKey
0x15ef8e  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15ef93  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ExtentHeightProperty
0x15ef98  ldstr    aViewportwidth// "ViewportWidth"
0x15ef9d  ldtoken  [mscorlib]System.Double
0x15efa2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15efa7  ldtoken  System.Windows.Controls.DocumentViewer
0x15efac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15efb1  ldc.r8   0.0
0x15efba  box      [mscorlib]System.Double
0x15efbf  ldnull
0x15efc0  ldftn    void System.Windows.Controls.DocumentViewer::OnViewportWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15efc6  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15efcb  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15efd0  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15efd5  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ViewportWidthPropertyKey
0x15efda  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ViewportWidthPropertyKey
0x15efdf  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15efe4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ViewportWidthProperty
0x15efe9  ldstr    aViewportheight// "ViewportHeight"
0x15efee  ldtoken  [mscorlib]System.Double
0x15eff3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15eff8  ldtoken  System.Windows.Controls.DocumentViewer
0x15effd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f002  ldc.r8   0.0
0x15f00b  box      [mscorlib]System.Double
0x15f010  ldnull
0x15f011  ldftn    void System.Windows.Controls.DocumentViewer::OnViewportHeightChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f017  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f01c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15f021  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f026  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ViewportHeightPropertyKey
0x15f02b  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::ViewportHeightPropertyKey
0x15f030  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f035  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ViewportHeightProperty
0x15f03a  ldstr    aShowpageborder// "ShowPageBorders"
0x15f03f  ldtoken  [mscorlib]System.Boolean
0x15f044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f049  ldtoken  System.Windows.Controls.DocumentViewer
0x15f04e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f053  ldc.i4.1
0x15f054  box      [mscorlib]System.Boolean
0x15f059  ldc.i4   0x100
0x15f05e  ldnull
0x15f05f  ldftn    void System.Windows.Controls.DocumentViewer::OnShowPageBordersChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f065  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f06a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15f06f  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f074  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ShowPageBordersProperty
0x15f079  ldstr    aZoom// "Zoom"
0x15f07e  ldtoken  [mscorlib]System.Double
0x15f083  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f088  ldtoken  System.Windows.Controls.DocumentViewer
0x15f08d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f092  ldc.r8   100.0
0x15f09b  box      [mscorlib]System.Double
0x15f0a0  ldc.i4   0x100
0x15f0a5  ldnull
0x15f0a6  ldftn    void System.Windows.Controls.DocumentViewer::OnZoomChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f0ac  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f0b1  ldnull
0x15f0b2  ldftn    object System.Windows.Controls.DocumentViewer::CoerceZoom(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x15f0b8  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15f0bd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15f0c2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f0c7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::ZoomProperty
0x15f0cc  ldstr    aMaxpagesacross// "MaxPagesAcross"
0x15f0d1  ldtoken  [mscorlib]System.Int32
0x15f0d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f0db  ldtoken  System.Windows.Controls.DocumentViewer
0x15f0e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f0e5  ldc.i4.1
0x15f0e6  box      [mscorlib]System.Int32
0x15f0eb  ldc.i4   0x100
0x15f0f0  ldnull
0x15f0f1  ldftn    void System.Windows.Controls.DocumentViewer::OnMaxPagesAcrossChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f0f7  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f0fc  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15f101  ldnull
0x15f102  ldftn    bool System.Windows.Controls.DocumentViewer::ValidateMaxPagesAcross(object value)
0x15f108  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x15f10d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x15f112  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::MaxPagesAcrossProperty
0x15f117  ldstr    aVerticalpagesp// "VerticalPageSpacing"
0x15f11c  ldtoken  [mscorlib]System.Double
0x15f121  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f126  ldtoken  System.Windows.Controls.DocumentViewer
0x15f12b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f130  ldc.r8   10.0
0x15f139  box      [mscorlib]System.Double
0x15f13e  ldnull
0x15f13f  ldftn    void System.Windows.Controls.DocumentViewer::OnVerticalPageSpacingChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f145  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f14a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15f14f  ldnull
0x15f150  ldftn    bool System.Windows.Controls.DocumentViewer::ValidatePageSpacing(object value)
0x15f156  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x15f15b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x15f160  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::VerticalPageSpacingProperty
0x15f165  ldstr    aHorizontalpage// "HorizontalPageSpacing"
0x15f16a  ldtoken  [mscorlib]System.Double
0x15f16f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f174  ldtoken  System.Windows.Controls.DocumentViewer
0x15f179  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f17e  ldc.r8   10.0
0x15f187  box      [mscorlib]System.Double
0x15f18c  ldnull
0x15f18d  ldftn    void System.Windows.Controls.DocumentViewer::OnHorizontalPageSpacingChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15f193  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15f198  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15f19d  ldnull
0x15f19e  ldftn    bool System.Windows.Controls.DocumentViewer::ValidatePageSpacing(object value)
0x15f1a4  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x15f1a9  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x15f1ae  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::HorizontalPageSpacingProperty
0x15f1b3  ldstr    aCanmoveup// "CanMoveUp"
0x15f1b8  ldtoken  [mscorlib]System.Boolean
0x15f1bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f1c2  ldtoken  System.Windows.Controls.DocumentViewer
0x15f1c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f1cc  ldc.i4.0
0x15f1cd  box      [mscorlib]System.Boolean
0x15f1d2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f1d7  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f1dc  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveUpPropertyKey
0x15f1e1  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveUpPropertyKey
0x15f1e6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f1eb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanMoveUpProperty
0x15f1f0  ldstr    aCanmovedown// "CanMoveDown"
0x15f1f5  ldtoken  [mscorlib]System.Boolean
0x15f1fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f1ff  ldtoken  System.Windows.Controls.DocumentViewer
0x15f204  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f209  ldc.i4.0
0x15f20a  box      [mscorlib]System.Boolean
0x15f20f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f214  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f219  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveDownPropertyKey
0x15f21e  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveDownPropertyKey
0x15f223  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f228  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanMoveDownProperty
0x15f22d  ldstr    aCanmoveleft// "CanMoveLeft"
0x15f232  ldtoken  [mscorlib]System.Boolean
0x15f237  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f23c  ldtoken  System.Windows.Controls.DocumentViewer
0x15f241  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f246  ldc.i4.0
0x15f247  box      [mscorlib]System.Boolean
0x15f24c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f251  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f256  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveLeftPropertyKey
0x15f25b  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveLeftPropertyKey
0x15f260  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f265  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanMoveLeftProperty
0x15f26a  ldstr    aCanmoveright// "CanMoveRight"
0x15f26f  ldtoken  [mscorlib]System.Boolean
0x15f274  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f279  ldtoken  System.Windows.Controls.DocumentViewer
0x15f27e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f283  ldc.i4.0
0x15f284  box      [mscorlib]System.Boolean
0x15f289  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f28e  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f293  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveRightPropertyKey
0x15f298  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanMoveRightPropertyKey
0x15f29d  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f2a2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanMoveRightProperty
0x15f2a7  ldstr    aCanincreasezoo// "CanIncreaseZoom"
0x15f2ac  ldtoken  [mscorlib]System.Boolean
0x15f2b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f2b6  ldtoken  System.Windows.Controls.DocumentViewer
0x15f2bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f2c0  ldc.i4.1
0x15f2c1  box      [mscorlib]System.Boolean
0x15f2c6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f2cb  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f2d0  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanIncreaseZoomPropertyKey
0x15f2d5  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanIncreaseZoomPropertyKey
0x15f2da  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f2df  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanIncreaseZoomProperty
0x15f2e4  ldstr    aCandecreasezoo// "CanDecreaseZoom"
0x15f2e9  ldtoken  [mscorlib]System.Boolean
0x15f2ee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f2f3  ldtoken  System.Windows.Controls.DocumentViewer
0x15f2f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15f2fd  ldc.i4.1
0x15f2fe  box      [mscorlib]System.Boolean
0x15f303  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15f308  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15f30d  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanDecreaseZoomPropertyKey
0x15f312  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DocumentViewer::CanDecreaseZoomPropertyKey
0x15f317  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15f31c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DocumentViewer::CanDecreaseZoomProperty
0x15f321  ldc.i4.s 0x16
0x15f323  newarr   [mscorlib]System.Double
0x15f328  dup
0x15f329  ldtoken  valuetype __StaticArrayInitTypeSize=176 <PrivateImplementationDetails>::F6EFA5666FCF8975523DDDDC7617313445607246B77DF5BA514BC49CA5120234
0x15f32e  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x15f333  stsfld   float64[] System.Windows.Controls.DocumentViewer::_zoomLevelCollection
0x15f338  call     void System.Windows.Controls.DocumentViewer::CreateCommandBindings()
0x15f33d  call     void System.Windows.Controls.DocumentViewer::RegisterMetadata()
0x15f342  ldc.i4   0x400
0x15f347  conv.i8
0x15f348  call     void MS.Internal.Telemetry.PresentationFramework.ControlsTraceLogger::AddControl(valuetype MS.Internal.Telemetry.PresentationFramework.TelemetryControls control)
0x15f34d  ret
```
