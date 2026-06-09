# System.Windows.Controls.MenuItem::.cctor

- ea: `0x17e820`
- end: `0x17ee5c`
- name: `System.Windows.Controls.MenuItem::.cctor`
- size: `1596`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x159e0`
- `0x15a00`
- `0x15a20`
- `0x15a30`
- `0x15a40`
- `0x15a50`
- `0x15a60`
- `0x22a90`
- `0x239d0`
- `0x239f0`
- `0x23a20`
- `0x23a40`
- `0x1781a0`

## string_xrefs

- `0x17e8b0`: `SubmenuOpened`
- `0x17e961`: `IsSubmenuOpen`
- `0x17ead7`: `StaysOpenOnClick`
- `0x17ec1e`: `InsideContextMenu`

## pseudocode

```c

```

## disassembly

```asm
0x17e820  ldstr    aClick// "Click"
0x17e825  ldc.i4.1
0x17e826  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e82b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e830  ldtoken  System.Windows.Controls.MenuItem
0x17e835  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e83a  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e83f  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::ClickEvent
0x17e844  ldstr    aPreviewclick// "PreviewClick"
0x17e849  ldc.i4.1
0x17e84a  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e84f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e854  ldtoken  System.Windows.Controls.MenuItem
0x17e859  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e85e  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e863  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::PreviewClickEvent
0x17e868  ldstr    aChecked// "Checked"
0x17e86d  ldc.i4.1
0x17e86e  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e873  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e878  ldtoken  System.Windows.Controls.MenuItem
0x17e87d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e882  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e887  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::CheckedEvent
0x17e88c  ldstr    aUnchecked// "Unchecked"
0x17e891  ldc.i4.1
0x17e892  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e897  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e89c  ldtoken  System.Windows.Controls.MenuItem
0x17e8a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e8a6  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e8ab  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::UncheckedEvent
0x17e8b0  ldstr    aSubmenuopened// "SubmenuOpened"
0x17e8b5  ldc.i4.1
0x17e8b6  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e8bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e8c0  ldtoken  System.Windows.Controls.MenuItem
0x17e8c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e8ca  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e8cf  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::SubmenuOpenedEvent
0x17e8d4  ldstr    aSubmenuclosed// "SubmenuClosed"
0x17e8d9  ldc.i4.1
0x17e8da  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17e8df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e8e4  ldtoken  System.Windows.Controls.MenuItem
0x17e8e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e8ee  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17e8f3  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MenuItem::SubmenuClosedEvent
0x17e8f8  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandProperty
0x17e8fd  ldtoken  System.Windows.Controls.MenuItem
0x17e902  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e907  ldnull
0x17e908  ldnull
0x17e909  ldftn    void System.Windows.Controls.MenuItem::OnCommandChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17e90f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17e914  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17e919  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17e91e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::CommandProperty
0x17e923  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandParameterProperty
0x17e928  ldtoken  System.Windows.Controls.MenuItem
0x17e92d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e932  ldnull
0x17e933  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17e938  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17e93d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::CommandParameterProperty
0x17e942  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.ButtonBase::CommandTargetProperty
0x17e947  ldtoken  System.Windows.Controls.MenuItem
0x17e94c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e951  ldnull
0x17e952  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17e957  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17e95c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::CommandTargetProperty
0x17e961  ldstr    aIssubmenuopen// "IsSubmenuOpen"
0x17e966  ldtoken  [mscorlib]System.Boolean
0x17e96b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e970  ldtoken  System.Windows.Controls.MenuItem
0x17e975  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e97a  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17e97f  ldc.i4   0x100
0x17e984  ldnull
0x17e985  ldftn    void System.Windows.Controls.MenuItem::OnIsSubmenuOpenChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17e98b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17e990  ldnull
0x17e991  ldftn    object System.Windows.Controls.MenuItem::CoerceIsSubmenuOpen(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x17e997  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x17e99c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x17e9a1  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17e9a6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsSubmenuOpenProperty
0x17e9ab  ldstr    aRole// "Role"
0x17e9b0  ldtoken  System.Windows.Controls.MenuItemRole
0x17e9b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e9ba  ldtoken  System.Windows.Controls.MenuItem
0x17e9bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e9c4  ldc.i4.0
0x17e9c5  box      System.Windows.Controls.MenuItemRole
0x17e9ca  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17e9cf  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17e9d4  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::RolePropertyKey
0x17e9d9  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::RolePropertyKey
0x17e9de  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x17e9e3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::RoleProperty
0x17e9e8  ldstr    aIscheckable// "IsCheckable"
0x17e9ed  ldtoken  [mscorlib]System.Boolean
0x17e9f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e9f7  ldtoken  System.Windows.Controls.MenuItem
0x17e9fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ea01  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17ea06  ldnull
0x17ea07  ldftn    void System.Windows.Controls.MenuItem::OnIsCheckableChanged(class [WindowsBase]System.Windows.DependencyObject target, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17ea0d  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17ea12  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17ea17  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ea1c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsCheckableProperty
0x17ea21  ldstr    aIspressed// "IsPressed"
0x17ea26  ldtoken  [mscorlib]System.Boolean
0x17ea2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ea30  ldtoken  System.Windows.Controls.MenuItem
0x17ea35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ea3a  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17ea3f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ea44  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ea49  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsPressedPropertyKey
0x17ea4e  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsPressedPropertyKey
0x17ea53  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x17ea58  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsPressedProperty
0x17ea5d  ldstr    aIshighlighted// "IsHighlighted"
0x17ea62  ldtoken  [mscorlib]System.Boolean
0x17ea67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ea6c  ldtoken  System.Windows.Controls.MenuItem
0x17ea71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ea76  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17ea7b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ea80  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ea85  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsHighlightedPropertyKey
0x17ea8a  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsHighlightedPropertyKey
0x17ea8f  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x17ea94  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsHighlightedProperty
0x17ea99  ldstr    aIschecked// "IsChecked"
0x17ea9e  ldtoken  [mscorlib]System.Boolean
0x17eaa3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eaa8  ldtoken  System.Windows.Controls.MenuItem
0x17eaad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eab2  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17eab7  ldc.i4   0x500
0x17eabc  ldnull
0x17eabd  ldftn    void System.Windows.Controls.MenuItem::OnIsCheckedChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17eac3  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17eac8  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17eacd  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ead2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsCheckedProperty
0x17ead7  ldstr    aStaysopenoncli// "StaysOpenOnClick"
0x17eadc  ldtoken  [mscorlib]System.Boolean
0x17eae1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eae6  ldtoken  System.Windows.Controls.MenuItem
0x17eaeb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eaf0  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17eaf5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17eafa  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17eaff  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::StaysOpenOnClickProperty
0x17eb04  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Selector::IsSelectedProperty
0x17eb09  ldtoken  System.Windows.Controls.MenuItem
0x17eb0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eb13  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17eb18  ldc.i4   0x100
0x17eb1d  ldnull
0x17eb1e  ldftn    void System.Windows.Controls.MenuItem::OnIsSelectedChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17eb24  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17eb29  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17eb2e  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17eb33  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsSelectedProperty
0x17eb38  ldstr    aInputgesturete// "InputGestureText"
0x17eb3d  ldtoken  [mscorlib]System.String
0x17eb42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eb47  ldtoken  System.Windows.Controls.MenuItem
0x17eb4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eb51  ldsfld   string [mscorlib]System.String::Empty
0x17eb56  ldnull
0x17eb57  ldftn    void System.Windows.Controls.MenuItem::OnInputGestureTextChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17eb5d  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17eb62  ldnull
0x17eb63  ldftn    object System.Windows.Controls.MenuItem::CoerceInputGestureText(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x17eb69  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x17eb6e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x17eb73  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17eb78  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::InputGestureTextProperty
0x17eb7d  ldstr    aIcon_0// "Icon"
0x17eb82  ldtoken  [mscorlib]System.Object
0x17eb87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eb8c  ldtoken  System.Windows.Controls.MenuItem
0x17eb91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eb96  ldnull
0x17eb97  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17eb9c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17eba1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IconProperty
0x17eba6  ldstr    aIssuspendingpo// "IsSuspendingPopupAnimation"
0x17ebab  ldtoken  [mscorlib]System.Boolean
0x17ebb0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ebb5  ldtoken  System.Windows.Controls.MenuItem
0x17ebba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ebbf  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17ebc4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ebc9  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ebce  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsSuspendingPopupAnimationPropertyKey
0x17ebd3  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.MenuItem::IsSuspendingPopupAnimationPropertyKey
0x17ebd8  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x17ebdd  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::IsSuspendingPopupAnimationProperty
0x17ebe2  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.MenuBase::ItemContainerTemplateSelectorProperty
0x17ebe7  ldtoken  System.Windows.Controls.MenuItem
0x17ebec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ebf1  newobj   instance void System.Windows.Controls.DefaultItemContainerTemplateSelector::.ctor()
0x17ebf6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ebfb  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ec00  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::ItemContainerTemplateSelectorProperty
0x17ec05  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.MenuBase::UsesItemContainerTemplateProperty
0x17ec0a  ldtoken  System.Windows.Controls.MenuItem
0x17ec0f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec14  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x17ec19  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::UsesItemContainerTemplateProperty
0x17ec1e  ldstr    aInsidecontextm// "InsideContextMenu"
0x17ec23  ldtoken  [mscorlib]System.Boolean
0x17ec28  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec2d  ldtoken  System.Windows.Controls.MenuItem
0x17ec32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec37  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x17ec3c  ldc.i4.s 0x20
0x17ec3e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x17ec43  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ec48  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::InsideContextMenuProperty
0x17ec4d  ldstr    aBooleanfieldst// "BooleanFieldStore"
0x17ec52  ldtoken  BoolField
0x17ec57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec5c  ldtoken  System.Windows.Controls.MenuItem
0x17ec61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec66  ldc.i4.0
0x17ec67  box      BoolField
0x17ec6c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ec71  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ec76  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MenuItem::BooleanFieldStoreProperty
0x17ec7b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.HeaderedItemsControl::HeaderProperty
0x17ec80  ldtoken  System.Windows.Controls.MenuItem
0x17ec85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ec8a  ldnull
0x17ec8b  ldnull
0x17ec8c  ldftn    object System.Windows.Controls.MenuItem::CoerceHeader(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x17ec92  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x17ec97  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x17ec9c  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17eca1  ldtoken  System.Windows.Controls.MenuItem
0x17eca6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ecab  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.AccessKeyManager::AccessKeyPressedEvent
0x17ecb0  ldnull
0x17ecb1  ldftn    void System.Windows.Controls.MenuItem::OnAccessKeyPressed(object sender, class [PresentationCore]System.Windows.Input.AccessKeyPressedEventArgs e)
0x17ecb7  newobj   instance void [PresentationCore]System.Windows.Input.AccessKeyPressedEventHandler::.ctor(object, native int)
0x17ecbc  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x17ecc1  ldtoken  System.Windows.Controls.MenuItem
0x17ecc6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17eccb  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.MenuBase::IsSelectedChangedEvent
0x17ecd0  ldnull
0x17ecd1  ldftn    void System.Windows.Controls.MenuItem::OnIsSelectedChanged(object sender, class System.Windows.RoutedPropertyChangedEventArgs`1<bool> e)
0x17ecd7  newobj   instance void class System.Windows.RoutedPropertyChangedEventHandler`1<bool>::.ctor(object, native int)
0x17ecdc  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x17ece1  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::ForegroundProperty
0x17ece6  ldtoken  System.Windows.Controls.MenuItem
0x17eceb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ecf0  call     class [PresentationCore]System.Windows.Media.SolidColorBrush System.Windows.SystemColors::get_MenuTextBrush()
0x17ecf5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ecfa  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ecff  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::FontFamilyProperty
0x17ed04  ldtoken  System.Windows.Controls.MenuItem
0x17ed09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed0e  call     class [PresentationCore]System.Windows.Media.FontFamily System.Windows.SystemFonts::get_MessageFontFamily()
0x17ed13  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ed18  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ed1d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::FontSizeProperty
0x17ed22  ldtoken  System.Windows.Controls.MenuItem
0x17ed27  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed2c  call     float64 System.Windows.SystemFonts::get_MessageFontSize()
0x17ed31  box      [mscorlib]System.Double
0x17ed36  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ed3b  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ed40  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::FontStyleProperty
0x17ed45  ldtoken  System.Windows.Controls.MenuItem
0x17ed4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed4f  call     valuetype [PresentationCore]System.Windows.FontStyle System.Windows.SystemFonts::get_MessageFontStyle()
0x17ed54  box      [PresentationCore]System.Windows.FontStyle
0x17ed59  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ed5e  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ed63  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::FontWeightProperty
0x17ed68  ldtoken  System.Windows.Controls.MenuItem
0x17ed6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed72  call     valuetype [PresentationCore]System.Windows.FontWeight System.Windows.SystemFonts::get_MessageFontWeight()
0x17ed77  box      [PresentationCore]System.Windows.FontWeight
0x17ed7c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17ed81  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17ed86  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::IsEnabledProperty
0x17ed8b  ldtoken  System.Windows.Controls.MenuItem
0x17ed90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed95  ldnull
0x17ed96  ldnull
0x17ed97  ldftn    object System.Windows.Controls.MenuItem::CoerceToolTipIsEnabled(class [WindowsBase]System.Windows.DependencyObject d, object value)
  ... truncated ...
```
