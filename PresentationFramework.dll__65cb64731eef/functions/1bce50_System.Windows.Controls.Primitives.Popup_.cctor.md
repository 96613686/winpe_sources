# System.Windows.Controls.Primitives.Popup::.cctor

- ea: `0x1bce50`
- end: `0x1bd23a`
- name: `System.Windows.Controls.Primitives.Popup::.cctor`
- size: `1002`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x159e0`
- `0x15a20`
- `0x15a30`
- `0x15a60`

## string_xrefs

- `0x1bcebd`: `IsOpen`
- `0x1bcf76`: `StaysOpen`

## pseudocode

```c

```

## disassembly

```asm
0x1bce50  ldstr    aTreatmouseplac// "TreatMousePlacementAsBottom"
0x1bce55  ldtoken  [mscorlib]System.Boolean
0x1bce5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bce5f  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bce64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bce69  ldc.i4.0
0x1bce6a  box      [mscorlib]System.Boolean
0x1bce6f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1bce74  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bce79  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::TreatMousePlacementAsBottomProperty
0x1bce7e  ldstr    aChild_0// "Child"
0x1bce83  ldtoken  [PresentationCore]System.Windows.UIElement
0x1bce88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bce8d  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bce92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bce97  ldnull
0x1bce98  ldnull
0x1bce99  ldftn    void System.Windows.Controls.Primitives.Popup::OnChildChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bce9f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bcea4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bcea9  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bceae  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::ChildProperty
0x1bceb3  newobj   instance void class [WindowsBase]System.Windows.UncommonField`1<class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Controls.Primitives.Popup>>::.ctor()
0x1bceb8  stsfld   class [WindowsBase]System.Windows.UncommonField`1<class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Controls.Primitives.Popup>> System.Windows.Controls.Primitives.Popup::RegisteredPopupsField
0x1bcebd  ldstr    aIsopen// "IsOpen"
0x1bcec2  ldtoken  [mscorlib]System.Boolean
0x1bcec7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcecc  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bced1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bced6  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1bcedb  ldc.i4   0x100
0x1bcee0  ldnull
0x1bcee1  ldftn    void System.Windows.Controls.Primitives.Popup::OnIsOpenChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bcee7  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bceec  ldnull
0x1bceed  ldftn    object System.Windows.Controls.Primitives.Popup::CoerceIsOpen(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x1bcef3  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1bcef8  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1bcefd  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bcf02  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::IsOpenProperty
0x1bcf07  ldstr    aPlacement// "Placement"
0x1bcf0c  ldtoken  System.Windows.Controls.Primitives.PlacementMode
0x1bcf11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf16  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bcf1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf20  ldc.i4.2
0x1bcf21  box      System.Windows.Controls.Primitives.PlacementMode
0x1bcf26  ldnull
0x1bcf27  ldftn    void System.Windows.Controls.Primitives.Popup::OnPlacementChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bcf2d  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bcf32  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bcf37  ldnull
0x1bcf38  ldftn    bool System.Windows.Controls.Primitives.Popup::IsValidPlacementMode(object o)
0x1bcf3e  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x1bcf43  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x1bcf48  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementProperty
0x1bcf4d  ldstr    aCustompopuppla// "CustomPopupPlacementCallback"
0x1bcf52  ldtoken  System.Windows.Controls.Primitives.CustomPopupPlacementCallback
0x1bcf57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf5c  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bcf61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf66  ldnull
0x1bcf67  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1bcf6c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bcf71  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::CustomPopupPlacementCallbackProperty
0x1bcf76  ldstr    aStaysopen// "StaysOpen"
0x1bcf7b  ldtoken  [mscorlib]System.Boolean
0x1bcf80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf85  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bcf8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcf8f  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x1bcf94  ldnull
0x1bcf95  ldftn    void System.Windows.Controls.Primitives.Popup::OnStaysOpenChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bcf9b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bcfa0  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bcfa5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bcfaa  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::StaysOpenProperty
0x1bcfaf  ldstr    aHorizontaloffs// "HorizontalOffset"
0x1bcfb4  ldtoken  [mscorlib]System.Double
0x1bcfb9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcfbe  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bcfc3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bcfc8  ldc.r8   0.0
0x1bcfd1  box      [mscorlib]System.Double
0x1bcfd6  ldnull
0x1bcfd7  ldftn    void System.Windows.Controls.Primitives.Popup::OnOffsetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bcfdd  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bcfe2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bcfe7  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bcfec  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::HorizontalOffsetProperty
0x1bcff1  ldstr    aVerticaloffset// "VerticalOffset"
0x1bcff6  ldtoken  [mscorlib]System.Double
0x1bcffb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd000  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd005  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd00a  ldc.r8   0.0
0x1bd013  box      [mscorlib]System.Double
0x1bd018  ldnull
0x1bd019  ldftn    void System.Windows.Controls.Primitives.Popup::OnOffsetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bd01f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bd024  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bd029  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd02e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::VerticalOffsetProperty
0x1bd033  ldstr    aPlacementtarge// "PlacementTarget"
0x1bd038  ldtoken  [PresentationCore]System.Windows.UIElement
0x1bd03d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd042  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd047  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd04c  ldnull
0x1bd04d  ldnull
0x1bd04e  ldftn    void System.Windows.Controls.Primitives.Popup::OnPlacementTargetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bd054  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bd059  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bd05e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd063  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementTargetProperty
0x1bd068  ldstr    aPlacementrecta// "PlacementRectangle"
0x1bd06d  ldtoken  [WindowsBase]System.Windows.Rect
0x1bd072  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd077  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd07c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd081  call     valuetype [WindowsBase]System.Windows.Rect [WindowsBase]System.Windows.Rect::get_Empty()
0x1bd086  box      [WindowsBase]System.Windows.Rect
0x1bd08b  ldnull
0x1bd08c  ldftn    void System.Windows.Controls.Primitives.Popup::OnOffsetChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bd092  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bd097  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1bd09c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd0a1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementRectangleProperty
0x1bd0a6  ldstr    aPopupanimation// "PopupAnimation"
0x1bd0ab  ldtoken  System.Windows.Controls.Primitives.PopupAnimation
0x1bd0b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd0b5  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd0ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd0bf  ldc.i4.0
0x1bd0c0  box      System.Windows.Controls.Primitives.PopupAnimation
0x1bd0c5  ldnull
0x1bd0c6  ldnull
0x1bd0c7  ldftn    object System.Windows.Controls.Primitives.Popup::CoercePopupAnimation(class [WindowsBase]System.Windows.DependencyObject o, object value)
0x1bd0cd  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1bd0d2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1bd0d7  ldnull
0x1bd0d8  ldftn    bool System.Windows.Controls.Primitives.Popup::IsValidPopupAnimation(object o)
0x1bd0de  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x1bd0e3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x1bd0e8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PopupAnimationProperty
0x1bd0ed  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::AllowsTransparencyProperty
0x1bd0f2  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd0f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd0fc  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1bd101  ldnull
0x1bd102  ldftn    void System.Windows.Controls.Primitives.Popup::OnAllowsTransparencyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1bd108  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1bd10d  ldnull
0x1bd10e  ldftn    object System.Windows.Controls.Primitives.Popup::CoerceAllowsTransparency(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x1bd114  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1bd119  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1bd11e  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd123  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::AllowsTransparencyProperty
0x1bd128  ldstr    aHasdropshadow// "HasDropShadow"
0x1bd12d  ldtoken  [mscorlib]System.Boolean
0x1bd132  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd137  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd13c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd141  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1bd146  ldnull
0x1bd147  ldnull
0x1bd148  ldftn    object System.Windows.Controls.Primitives.Popup::CoerceHasDropShadow(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x1bd14e  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1bd153  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1bd158  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd15d  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.Primitives.Popup::HasDropShadowPropertyKey
0x1bd162  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.Primitives.Popup::HasDropShadowPropertyKey
0x1bd167  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x1bd16c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::HasDropShadowProperty
0x1bd171  newobj   instance void [PresentationCore]System.Windows.EventPrivateKey::.ctor()
0x1bd176  stsfld   class [PresentationCore]System.Windows.EventPrivateKey System.Windows.Controls.Primitives.Popup::OpenedKey
0x1bd17b  newobj   instance void [PresentationCore]System.Windows.EventPrivateKey::.ctor()
0x1bd180  stsfld   class [PresentationCore]System.Windows.EventPrivateKey System.Windows.Controls.Primitives.Popup::ClosedKey
0x1bd185  newobj   instance void class [WindowsBase]System.Windows.UncommonField`1<class [mscorlib]System.Exception>::.ctor()
0x1bd18a  stsfld   class [WindowsBase]System.Windows.UncommonField`1<class [mscorlib]System.Exception> System.Windows.Controls.Primitives.Popup::SavedExceptionField
0x1bd18f  ldc.i4.0
0x1bd190  ldc.i4.0
0x1bd191  ldc.i4.0
0x1bd192  ldc.i4.0
0x1bd193  ldc.i4   0x96
0x1bd198  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32, int32)
0x1bd19d  stsfld   valuetype [mscorlib]System.TimeSpan System.Windows.Controls.Primitives.Popup::AnimationDelayTime
0x1bd1a2  newobj   instance void class [WindowsBase]System.Windows.UncommonField`1<class System.Windows.Controls.Primitives.PopupRoot>::.ctor()
0x1bd1a7  stsfld   class [WindowsBase]System.Windows.UncommonField`1<class System.Windows.Controls.Primitives.PopupRoot> System.Windows.Controls.Primitives.Popup::ParentPopupRootField
0x1bd1ac  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd1b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd1b6  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::LostMouseCaptureEvent
0x1bd1bb  ldnull
0x1bd1bc  ldftn    void System.Windows.Controls.Primitives.Popup::OnLostMouseCapture(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x1bd1c2  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x1bd1c7  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bd1cc  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd1d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd1d6  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.DragDrop::DragDropStartedEvent
0x1bd1db  ldnull
0x1bd1dc  ldftn    void System.Windows.Controls.Primitives.Popup::OnDragDropStarted(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0x1bd1e2  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0x1bd1e7  ldc.i4.1
0x1bd1e8  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1bd1ed  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd1f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd1f7  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.DragDrop::DragDropCompletedEvent
0x1bd1fc  ldnull
0x1bd1fd  ldftn    void System.Windows.Controls.Primitives.Popup::OnDragDropCompleted(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0x1bd203  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0x1bd208  ldc.i4.1
0x1bd209  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1bd20e  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::VisibilityProperty
0x1bd213  ldtoken  System.Windows.Controls.Primitives.Popup
0x1bd218  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd21d  ldsfld   object [PresentationCore]MS.Internal.KnownBoxes.VisibilityBoxes::CollapsedBox
0x1bd222  ldnull
0x1bd223  ldnull
0x1bd224  ldftn    object System.Windows.Controls.Primitives.Popup::CoerceVisibility(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x1bd22a  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1bd22f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1bd234  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bd239  ret
```
