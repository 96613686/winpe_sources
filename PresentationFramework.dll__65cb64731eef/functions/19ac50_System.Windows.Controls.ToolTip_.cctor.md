# System.Windows.Controls.ToolTip::.cctor

- ea: `0x19ac50`
- end: `0x19aec7`
- name: `System.Windows.Controls.ToolTip::.cctor`
- size: `631`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x159e0`
- `0x15a00`
- `0x15a50`
- `0x22a40`

## string_xrefs

- `0x19acd4`: `IsOpen`
- `0x19ae0a`: `Opened`

## pseudocode

```c

```

## disassembly

```asm
0x19ac50  ldstr    aFromkeyboard// "FromKeyboard"
0x19ac55  ldtoken  [mscorlib]System.Boolean
0x19ac5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ac5f  ldtoken  System.Windows.Controls.ToolTip
0x19ac64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ac69  ldc.i4.0
0x19ac6a  box      [mscorlib]System.Boolean
0x19ac6f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19ac74  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ac79  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::FromKeyboardProperty
0x19ac7e  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::HorizontalOffsetProperty
0x19ac83  ldtoken  System.Windows.Controls.ToolTip
0x19ac88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ac8d  ldnull
0x19ac8e  ldnull
0x19ac8f  ldftn    object System.Windows.Controls.ToolTip::CoerceHorizontalOffset(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19ac95  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19ac9a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19ac9f  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19aca4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::HorizontalOffsetProperty
0x19aca9  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::VerticalOffsetProperty
0x19acae  ldtoken  System.Windows.Controls.ToolTip
0x19acb3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19acb8  ldnull
0x19acb9  ldnull
0x19acba  ldftn    object System.Windows.Controls.ToolTip::CoerceVerticalOffset(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19acc0  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19acc5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19acca  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19accf  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::VerticalOffsetProperty
0x19acd4  ldstr    aIsopen// "IsOpen"
0x19acd9  ldtoken  [mscorlib]System.Boolean
0x19acde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ace3  ldtoken  System.Windows.Controls.ToolTip
0x19ace8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19aced  ldc.i4.0
0x19acee  box      [mscorlib]System.Boolean
0x19acf3  ldc.i4   0x100
0x19acf8  ldnull
0x19acf9  ldftn    void System.Windows.Controls.ToolTip::OnIsOpenChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x19acff  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x19ad04  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x19ad09  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ad0e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::IsOpenProperty
0x19ad13  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::HasDropShadowProperty
0x19ad18  ldtoken  System.Windows.Controls.ToolTip
0x19ad1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ad22  ldnull
0x19ad23  ldnull
0x19ad24  ldftn    object System.Windows.Controls.ToolTip::CoerceHasDropShadow(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19ad2a  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19ad2f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19ad34  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ad39  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::HasDropShadowProperty
0x19ad3e  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementTargetProperty
0x19ad43  ldtoken  System.Windows.Controls.ToolTip
0x19ad48  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ad4d  ldnull
0x19ad4e  ldnull
0x19ad4f  ldftn    object System.Windows.Controls.ToolTip::CoercePlacementTarget(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19ad55  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19ad5a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19ad5f  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ad64  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::PlacementTargetProperty
0x19ad69  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementRectangleProperty
0x19ad6e  ldtoken  System.Windows.Controls.ToolTip
0x19ad73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ad78  ldnull
0x19ad79  ldnull
0x19ad7a  ldftn    object System.Windows.Controls.ToolTip::CoercePlacementRectangle(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19ad80  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19ad85  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19ad8a  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ad8f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::PlacementRectangleProperty
0x19ad94  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementProperty
0x19ad99  ldtoken  System.Windows.Controls.ToolTip
0x19ad9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ada3  ldnull
0x19ada4  ldnull
0x19ada5  ldftn    object System.Windows.Controls.ToolTip::CoercePlacement(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x19adab  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x19adb0  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x19adb5  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19adba  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::PlacementProperty
0x19adbf  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::CustomPopupPlacementCallbackProperty
0x19adc4  ldtoken  System.Windows.Controls.ToolTip
0x19adc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19adce  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x19add3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::CustomPopupPlacementCallbackProperty
0x19add8  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::StaysOpenProperty
0x19addd  ldtoken  System.Windows.Controls.ToolTip
0x19ade2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ade7  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x19adec  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::StaysOpenProperty
0x19adf1  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::ShowsToolTipOnKeyboardFocusProperty
0x19adf6  ldtoken  System.Windows.Controls.ToolTip
0x19adfb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae00  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x19ae05  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTip::ShowsToolTipOnKeyboardFocusProperty
0x19ae0a  ldstr    aOpened// "Opened"
0x19ae0f  ldc.i4.1
0x19ae10  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x19ae15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae1a  ldtoken  System.Windows.Controls.ToolTip
0x19ae1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae24  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19ae29  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTip::OpenedEvent
0x19ae2e  ldstr    aClosed// "Closed"
0x19ae33  ldc.i4.1
0x19ae34  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x19ae39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae3e  ldtoken  System.Windows.Controls.ToolTip
0x19ae43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae48  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19ae4d  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTip::ClosedEvent
0x19ae52  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x19ae57  ldtoken  System.Windows.Controls.ToolTip
0x19ae5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae61  ldtoken  System.Windows.Controls.ToolTip
0x19ae66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae6b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19ae70  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ae75  ldtoken  System.Windows.Controls.ToolTip
0x19ae7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae7f  call     class [WindowsBase]System.Windows.DependencyObjectType [WindowsBase]System.Windows.DependencyObjectType::FromSystemTypeInternal(class [mscorlib]System.Type)
0x19ae84  stsfld   class [WindowsBase]System.Windows.DependencyObjectType System.Windows.Controls.ToolTip::_dType
0x19ae89  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::BackgroundProperty
0x19ae8e  ldtoken  System.Windows.Controls.ToolTip
0x19ae93  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae98  call     class [PresentationCore]System.Windows.Media.SolidColorBrush System.Windows.SystemColors::get_InfoBrush()
0x19ae9d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19aea2  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19aea7  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::FocusableProperty
0x19aeac  ldtoken  System.Windows.Controls.ToolTip
0x19aeb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19aeb6  ldc.i4.0
0x19aeb7  box      [mscorlib]System.Boolean
0x19aebc  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19aec1  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19aec6  ret
```
