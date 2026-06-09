# System.Windows.Controls.Primitives.ButtonBase::.cctor

- ea: `0x1b20f0`
- end: `0x1b22c6`
- name: `System.Windows.Controls.Primitives.ButtonBase::.cctor`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x159e0`
- `0x15a20`
- `0x15a40`

## string_xrefs

- `0x1b2114`: `Command`
- `0x1b2149`: `CommandParameter`
- `0x1b2172`: `CommandTarget`

## pseudocode

```c

```

## disassembly

```asm
0x1b20f0  ldstr    aClick// "Click"
0x1b20f5  ldc.i4.1
0x1b20f6  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x1b20fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2100  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2105  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b210a  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1b210f  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.ButtonBase::ClickEvent
0x1b2114  ldstr    aCommand// "Command"
0x1b2119  ldtoken  [System]System.Windows.Input.ICommand
0x1b211e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2123  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2128  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b212d  ldnull
0x1b212e  ldnull
0x1b212f  ldftn    void System.Windows.Controls.Primitives.ButtonBase::OnCommandChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1b2135  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1b213a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1b213f  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b2144  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandProperty
0x1b2149  ldstr    aCommandparamet// "CommandParameter"
0x1b214e  ldtoken  [mscorlib]System.Object
0x1b2153  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2158  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b215d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2162  ldnull
0x1b2163  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1b2168  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b216d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandParameterProperty
0x1b2172  ldstr    aCommandtarget// "CommandTarget"
0x1b2177  ldtoken  [PresentationCore]System.Windows.IInputElement
0x1b217c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2181  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2186  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b218b  ldnull
0x1b218c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1b2191  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b2196  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandTargetProperty
0x1b219b  ldstr    aIspressed// "IsPressed"
0x1b21a0  ldtoken  [mscorlib]System.Boolean
0x1b21a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b21aa  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b21af  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b21b4  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1b21b9  ldnull
0x1b21ba  ldftn    void System.Windows.Controls.Primitives.ButtonBase::OnIsPressedChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1b21c0  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1b21c5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1b21ca  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b21cf  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.Primitives.ButtonBase::IsPressedPropertyKey
0x1b21d4  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.Primitives.ButtonBase::IsPressedPropertyKey
0x1b21d9  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x1b21de  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::IsPressedProperty
0x1b21e3  ldstr    aClickmode// "ClickMode"
0x1b21e8  ldtoken  System.Windows.Controls.ClickMode
0x1b21ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b21f2  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b21f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b21fc  ldc.i4.0
0x1b21fd  box      System.Windows.Controls.ClickMode
0x1b2202  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1b2207  ldnull
0x1b2208  ldftn    bool System.Windows.Controls.Primitives.ButtonBase::IsValidClickMode(object o)
0x1b220e  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x1b2213  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x1b2218  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::ClickModeProperty
0x1b221d  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2222  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2227  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.AccessKeyManager::AccessKeyPressedEvent
0x1b222c  ldnull
0x1b222d  ldftn    void System.Windows.Controls.Primitives.ButtonBase::OnAccessKeyPressed(object sender, class [PresentationCore]System.Windows.Input.AccessKeyPressedEventArgs e)
0x1b2233  newobj   instance void [PresentationCore]System.Windows.Input.AccessKeyPressedEventHandler::.ctor(object, native int)
0x1b2238  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1b223d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.KeyboardNavigation::AcceptsReturnProperty
0x1b2242  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2247  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b224c  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x1b2251  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1b2256  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b225b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.Input.InputMethod::IsInputMethodEnabledProperty
0x1b2260  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2265  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b226a  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1b226f  ldc.i4.s 0x20
0x1b2271  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x1b2276  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b227b  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey [PresentationCore]System.Windows.UIElement::IsMouseOverPropertyKey
0x1b2280  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b2285  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b228a  ldnull
0x1b228b  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1b2291  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1b2296  newobj   instance void [PresentationCore]System.Windows.UIPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x1b229b  callvirt instance void [WindowsBase]System.Windows.DependencyPropertyKey::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b22a0  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::IsEnabledProperty
0x1b22a5  ldtoken  System.Windows.Controls.Primitives.ButtonBase
0x1b22aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b22af  ldnull
0x1b22b0  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1b22b6  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1b22bb  newobj   instance void [PresentationCore]System.Windows.UIPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x1b22c0  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1b22c5  ret
```
