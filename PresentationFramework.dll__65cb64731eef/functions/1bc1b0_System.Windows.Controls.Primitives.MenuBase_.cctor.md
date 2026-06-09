# System.Windows.Controls.Primitives.MenuBase::.cctor

- ea: `0x1bc1b0`
- end: `0x1bc3cf`
- name: `System.Windows.Controls.Primitives.MenuBase::.cctor`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x159e0`
- `0x15a40`
- `0x1781a0`

## string_xrefs

- `0x1bc1b0`: `ItemContainerTemplateSelector`
- `0x1bc1dd`: `UsesItemContainerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1bc1b0  ldstr    aItemcontainert_1// "ItemContainerTemplateSelector"
0x1bc1b5  ldtoken  System.Windows.Controls.ItemContainerTemplateSelector
0x1bc1ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc1bf  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc1c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc1c9  newobj   instance void System.Windows.Controls.DefaultItemContainerTemplateSelector::.ctor()
0x1bc1ce  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1bc1d3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bc1d8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.MenuBase::ItemContainerTemplateSelectorProperty
0x1bc1dd  ldstr    aUsesitemcontai// "UsesItemContainerTemplate"
0x1bc1e2  ldtoken  [mscorlib]System.Boolean
0x1bc1e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc1ec  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc1f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc1f6  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bc1fb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.MenuBase::UsesItemContainerTemplateProperty
0x1bc200  ldstr    aIsselectedchan// "IsSelectedChanged"
0x1bc205  ldc.i4.1
0x1bc206  ldtoken  class System.Windows.RoutedPropertyChangedEventHandler`1<bool>
0x1bc20b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc210  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc215  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc21a  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bc21f  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.MenuBase::IsSelectedChangedEvent
0x1bc224  newobj   instance void [PresentationCore]System.Windows.EventPrivateKey::.ctor()
0x1bc229  stsfld   class [PresentationCore]System.Windows.EventPrivateKey System.Windows.Controls.Primitives.MenuBase::InternalMenuModeChangedKey
0x1bc22e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc233  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc238  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::PreviewClickEvent
0x1bc23d  ldnull
0x1bc23e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnMenuItemPreviewClick(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0x1bc244  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0x1bc249  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc24e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc253  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc258  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseDownEvent
0x1bc25d  ldnull
0x1bc25e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnMouseButtonDown(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc264  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc269  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc26e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc273  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc278  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseUpEvent
0x1bc27d  ldnull
0x1bc27e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnMouseButtonUp(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc284  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc289  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc28e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc293  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc298  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::LostMouseCaptureEvent
0x1bc29d  ldnull
0x1bc29e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnLostMouseCapture(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x1bc2a4  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x1bc2a9  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc2ae  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc2b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc2b8  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.MenuBase::IsSelectedChangedEvent
0x1bc2bd  ldnull
0x1bc2be  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnIsSelectedChanged(object sender, class System.Windows.RoutedPropertyChangedEventArgs`1<bool> e)
0x1bc2c4  newobj   instance void class System.Windows.RoutedPropertyChangedEventHandler`1<bool>::.ctor(object, native int)
0x1bc2c9  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc2ce  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc2d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc2d8  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseDownEvent
0x1bc2dd  ldnull
0x1bc2de  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnPromotedMouseButton(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc2e4  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc2e9  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc2ee  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc2f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc2f8  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseUpEvent
0x1bc2fd  ldnull
0x1bc2fe  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnPromotedMouseButton(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc304  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc309  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc30e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc313  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc318  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::PreviewMouseDownOutsideCapturedElementEvent
0x1bc31d  ldnull
0x1bc31e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnClickThroughThunk(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc324  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc329  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc32e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc333  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc338  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::PreviewMouseUpOutsideCapturedElementEvent
0x1bc33d  ldnull
0x1bc33e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnClickThroughThunk(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1bc344  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1bc349  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1bc34e  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc353  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc358  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::PreviewKeyboardInputProviderAcquireFocusEvent
0x1bc35d  ldnull
0x1bc35e  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnPreviewKeyboardInputProviderAcquireFocus(object sender, class [PresentationCore]System.Windows.Input.KeyboardInputProviderAcquireFocusEventArgs e)
0x1bc364  newobj   instance void [PresentationCore]System.Windows.Input.KeyboardInputProviderAcquireFocusEventHandler::.ctor(object, native int)
0x1bc369  ldc.i4.1
0x1bc36a  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1bc36f  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc374  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc379  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::KeyboardInputProviderAcquireFocusEvent
0x1bc37e  ldnull
0x1bc37f  ldftn    void System.Windows.Controls.Primitives.MenuBase::OnKeyboardInputProviderAcquireFocus(object sender, class [PresentationCore]System.Windows.Input.KeyboardInputProviderAcquireFocusEventArgs e)
0x1bc385  newobj   instance void [PresentationCore]System.Windows.Input.KeyboardInputProviderAcquireFocusEventHandler::.ctor(object, native int)
0x1bc38a  ldc.i4.1
0x1bc38b  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1bc390  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.Input.FocusManager::IsFocusScopeProperty
0x1bc395  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc39a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc39f  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x1bc3a4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1bc3a9  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bc3ae  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.Input.InputMethod::IsInputMethodSuspendedProperty
0x1bc3b3  ldtoken  System.Windows.Controls.Primitives.MenuBase
0x1bc3b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bc3bd  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x1bc3c2  ldc.i4.s 0x20
0x1bc3c4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x1bc3c9  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1bc3ce  ret
```
