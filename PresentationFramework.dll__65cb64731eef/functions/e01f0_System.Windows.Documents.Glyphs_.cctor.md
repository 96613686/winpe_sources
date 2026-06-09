# System.Windows.Documents.Glyphs::.cctor

- ea: `0xe01f0`
- end: `0xe04c7`
- name: `System.Windows.Documents.Glyphs::.cctor`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x15a50`
- `0x15a60`

## string_xrefs

- `0xe02d8`: `FontRenderingEmSize`
- `0xe03a4`: `FontUri`
- `0xe0417`: `IsSideways`

## pseudocode

```c

```

## disassembly

```asm
0xe01f0  ldstr    aFill// "Fill"
0xe01f5  ldtoken  [PresentationCore]System.Windows.Media.Brush
0xe01fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe01ff  ldtoken  System.Windows.Documents.Glyphs
0xe0204  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0209  ldnull
0xe020a  ldc.i4.0
0xe020b  ldnull
0xe020c  ldftn    void System.Windows.Documents.Glyphs::FillChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0212  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0217  ldnull
0xe0218  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0xe021d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0222  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::FillProperty
0xe0227  ldstr    aIndices// "Indices"
0xe022c  ldtoken  [mscorlib]System.String
0xe0231  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0236  ldtoken  System.Windows.Documents.Glyphs
0xe023b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0240  ldsfld   string [mscorlib]System.String::Empty
0xe0245  ldc.i4.s 0x11
0xe0247  ldnull
0xe0248  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe024e  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0253  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0258  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe025d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::IndicesProperty
0xe0262  ldstr    aUnicodestring// "UnicodeString"
0xe0267  ldtoken  [mscorlib]System.String
0xe026c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0271  ldtoken  System.Windows.Documents.Glyphs
0xe0276  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe027b  ldsfld   string [mscorlib]System.String::Empty
0xe0280  ldc.i4.s 0x11
0xe0282  ldnull
0xe0283  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0289  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe028e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0293  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0298  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::UnicodeStringProperty
0xe029d  ldstr    aCaretstops// "CaretStops"
0xe02a2  ldtoken  [mscorlib]System.String
0xe02a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe02ac  ldtoken  System.Windows.Documents.Glyphs
0xe02b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe02b6  ldsfld   string [mscorlib]System.String::Empty
0xe02bb  ldc.i4.s 0x10
0xe02bd  ldnull
0xe02be  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe02c4  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe02c9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe02ce  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe02d3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::CaretStopsProperty
0xe02d8  ldstr    aFontrenderinge// "FontRenderingEmSize"
0xe02dd  ldtoken  [mscorlib]System.Double
0xe02e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe02e7  ldtoken  System.Windows.Documents.Glyphs
0xe02ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe02f1  ldc.r8   0.0
0xe02fa  box      [mscorlib]System.Double
0xe02ff  ldc.i4.s 0x11
0xe0301  ldnull
0xe0302  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0308  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe030d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0312  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0317  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::FontRenderingEmSizeProperty
0xe031c  ldstr    aOriginx// "OriginX"
0xe0321  ldtoken  [mscorlib]System.Double
0xe0326  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe032b  ldtoken  System.Windows.Documents.Glyphs
0xe0330  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0335  ldc.r8   NaN
0xe033e  box      [mscorlib]System.Double
0xe0343  ldc.i4.s 0x11
0xe0345  ldnull
0xe0346  ldftn    void System.Windows.Documents.Glyphs::OriginPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe034c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0351  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0356  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe035b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::OriginXProperty
0xe0360  ldstr    aOriginy// "OriginY"
0xe0365  ldtoken  [mscorlib]System.Double
0xe036a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe036f  ldtoken  System.Windows.Documents.Glyphs
0xe0374  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0379  ldc.r8   NaN
0xe0382  box      [mscorlib]System.Double
0xe0387  ldc.i4.s 0x11
0xe0389  ldnull
0xe038a  ldftn    void System.Windows.Documents.Glyphs::OriginPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0390  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0395  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe039a  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe039f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::OriginYProperty
0xe03a4  ldstr    aFonturi// "FontUri"
0xe03a9  ldtoken  [System]System.Uri
0xe03ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe03b3  ldtoken  System.Windows.Documents.Glyphs
0xe03b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe03bd  ldnull
0xe03be  ldc.i4.s 0x11
0xe03c0  ldnull
0xe03c1  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe03c7  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe03cc  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe03d1  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe03d6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::FontUriProperty
0xe03db  ldstr    aStylesimulatio// "StyleSimulations"
0xe03e0  ldtoken  [PresentationCore]System.Windows.Media.StyleSimulations
0xe03e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe03ea  ldtoken  System.Windows.Documents.Glyphs
0xe03ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe03f4  ldc.i4.0
0xe03f5  box      [PresentationCore]System.Windows.Media.StyleSimulations
0xe03fa  ldc.i4.s 0x11
0xe03fc  ldnull
0xe03fd  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0403  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0408  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe040d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0412  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::StyleSimulationsProperty
0xe0417  ldstr    aIssideways// "IsSideways"
0xe041c  ldtoken  [mscorlib]System.Boolean
0xe0421  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0426  ldtoken  System.Windows.Documents.Glyphs
0xe042b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0430  ldc.i4.0
0xe0431  box      [mscorlib]System.Boolean
0xe0436  ldc.i4.s 0x11
0xe0438  ldnull
0xe0439  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe043f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0444  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0449  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe044e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::IsSidewaysProperty
0xe0453  ldstr    aBidilevel// "BidiLevel"
0xe0458  ldtoken  [mscorlib]System.Int32
0xe045d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0462  ldtoken  System.Windows.Documents.Glyphs
0xe0467  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe046c  ldc.i4.0
0xe046d  box      [mscorlib]System.Int32
0xe0472  ldc.i4.s 0x11
0xe0474  ldnull
0xe0475  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe047b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0480  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0485  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe048a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::BidiLevelProperty
0xe048f  ldstr    aDevicefontname// "DeviceFontName"
0xe0494  ldtoken  [mscorlib]System.String
0xe0499  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe049e  ldtoken  System.Windows.Documents.Glyphs
0xe04a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe04a8  ldnull
0xe04a9  ldc.i4.s 0x10
0xe04ab  ldnull
0xe04ac  ldftn    void System.Windows.Documents.Glyphs::GlyphRunPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe04b2  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe04b7  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe04bc  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe04c1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Glyphs::DeviceFontNameProperty
0xe04c6  ret
```
