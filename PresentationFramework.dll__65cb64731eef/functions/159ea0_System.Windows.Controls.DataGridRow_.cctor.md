# System.Windows.Controls.DataGridRow::.cctor

- ea: `0x159ea0`
- end: `0x15a3f7`
- name: `System.Windows.Controls.DataGridRow::.cctor`
- size: `1367`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x147c0`
- `0x159e0`
- `0x159f0`
- `0x15a00`
- `0x15a20`
- `0x15a30`
- `0x15a40`
- `0x15a50`
- `0x17b7f0`

## string_xrefs

- `0x159fef`: `HeaderTemplate`
- `0x15a030`: `HeaderTemplateSelector`
- `0x15a071`: `ValidationErrorTemplate`
- `0x15a0b2`: `DetailsTemplate`
- `0x15a0f3`: `DetailsTemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x159ea0  ldc.i4.s 0x10
0x159ea2  newarr   [mscorlib]System.Byte
0x159ea7  dup
0x159ea8  ldtoken  valuetype __StaticArrayInitTypeSize=16 <PrivateImplementationDetails>::C21C6FDF112940C6A129249CDB427B33AFC6E769F447A26C9C2D3077D2349022
0x159ead  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x159eb2  stsfld   unsigned int8[] System.Windows.Controls.DataGridRow::_idealStateMapping
0x159eb7  ldc.i4.s 0xA
0x159eb9  newarr   [mscorlib]System.Byte
0x159ebe  dup
0x159ebf  ldtoken  valuetype __StaticArrayInitTypeSize=10 <PrivateImplementationDetails>::EB28F133A98C9BA4A8B90452A88224F2BADA592AA2DF028AA87861494451C65C
0x159ec4  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x159ec9  stsfld   unsigned int8[] System.Windows.Controls.DataGridRow::_fallbackStateMapping
0x159ece  ldc.i4.s 0xA
0x159ed0  newarr   [mscorlib]System.String
0x159ed5  dup
0x159ed6  ldc.i4.0
0x159ed7  ldstr    aMouseover// "MouseOver"
0x159edc  stelem.ref
0x159edd  dup
0x159ede  ldc.i4.1
0x159edf  ldstr    aMouseoverUnfoc// "MouseOver_Unfocused_Editing"
0x159ee4  stelem.ref
0x159ee5  dup
0x159ee6  ldc.i4.2
0x159ee7  ldstr    aMouseoverEditi// "MouseOver_Editing"
0x159eec  stelem.ref
0x159eed  dup
0x159eee  ldc.i4.3
0x159eef  ldstr    aMouseoverUnfoc_0// "MouseOver_Unfocused_Selected"
0x159ef4  stelem.ref
0x159ef5  dup
0x159ef6  ldc.i4.4
0x159ef7  ldstr    aMouseoverSelec// "MouseOver_Selected"
0x159efc  stelem.ref
0x159efd  dup
0x159efe  ldc.i4.5
0x159eff  ldstr    aNormal// "Normal"
0x159f04  stelem.ref
0x159f05  dup
0x159f06  ldc.i4.6
0x159f07  ldstr    aUnfocusedEditi// "Unfocused_Editing"
0x159f0c  stelem.ref
0x159f0d  dup
0x159f0e  ldc.i4.7
0x159f0f  ldstr    aNormalEditing// "Normal_Editing"
0x159f14  stelem.ref
0x159f15  dup
0x159f16  ldc.i4.8
0x159f17  ldstr    aUnfocusedSelec// "Unfocused_Selected"
0x159f1c  stelem.ref
0x159f1d  dup
0x159f1e  ldc.i4.s 9
0x159f20  ldstr    aNormalSelected// "Normal_Selected"
0x159f25  stelem.ref
0x159f26  stsfld   string[] System.Windows.Controls.DataGridRow::_stateNames
0x159f2b  ldstr    aItem_1// "Item"
0x159f30  ldtoken  [mscorlib]System.Object
0x159f35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159f3a  ldtoken  System.Windows.Controls.DataGridRow
0x159f3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159f44  ldnull
0x159f45  ldnull
0x159f46  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x159f4c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x159f51  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x159f56  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x159f5b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::ItemProperty
0x159f60  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::ItemsPanelProperty
0x159f65  ldtoken  System.Windows.Controls.DataGridRow
0x159f6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159f6f  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x159f74  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::ItemsPanelProperty
0x159f79  ldstr    aHeader// "Header"
0x159f7e  ldtoken  [mscorlib]System.Object
0x159f83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159f88  ldtoken  System.Windows.Controls.DataGridRow
0x159f8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159f92  ldnull
0x159f93  ldnull
0x159f94  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowAndRowHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x159f9a  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x159f9f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x159fa4  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x159fa9  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::HeaderProperty
0x159fae  ldstr    aHeaderstyle// "HeaderStyle"
0x159fb3  ldtoken  System.Windows.Style
0x159fb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159fbd  ldtoken  System.Windows.Controls.DataGridRow
0x159fc2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159fc7  ldnull
0x159fc8  ldnull
0x159fc9  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowAndRowHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x159fcf  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x159fd4  ldnull
0x159fd5  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceHeaderStyle(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x159fdb  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x159fe0  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x159fe5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x159fea  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::HeaderStyleProperty
0x159fef  ldstr    aHeadertemplate// "HeaderTemplate"
0x159ff4  ldtoken  System.Windows.DataTemplate
0x159ff9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x159ffe  ldtoken  System.Windows.Controls.DataGridRow
0x15a003  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a008  ldnull
0x15a009  ldnull
0x15a00a  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowAndRowHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a010  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a015  ldnull
0x15a016  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceHeaderTemplate(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a01c  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a021  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a026  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a02b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::HeaderTemplateProperty
0x15a030  ldstr    aHeadertemplate_0// "HeaderTemplateSelector"
0x15a035  ldtoken  System.Windows.Controls.DataTemplateSelector
0x15a03a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a03f  ldtoken  System.Windows.Controls.DataGridRow
0x15a044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a049  ldnull
0x15a04a  ldnull
0x15a04b  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowAndRowHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a051  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a056  ldnull
0x15a057  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceHeaderTemplateSelector(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a05d  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a062  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a067  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a06c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::HeaderTemplateSelectorProperty
0x15a071  ldstr    aValidationerro// "ValidationErrorTemplate"
0x15a076  ldtoken  System.Windows.Controls.ControlTemplate
0x15a07b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a080  ldtoken  System.Windows.Controls.DataGridRow
0x15a085  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a08a  ldnull
0x15a08b  ldnull
0x15a08c  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a092  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a097  ldnull
0x15a098  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceValidationErrorTemplate(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a09e  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a0a3  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a0a8  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a0ad  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::ValidationErrorTemplateProperty
0x15a0b2  ldstr    aDetailstemplat// "DetailsTemplate"
0x15a0b7  ldtoken  System.Windows.DataTemplate
0x15a0bc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a0c1  ldtoken  System.Windows.Controls.DataGridRow
0x15a0c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a0cb  ldnull
0x15a0cc  ldnull
0x15a0cd  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyDetailsTemplatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a0d3  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a0d8  ldnull
0x15a0d9  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceDetailsTemplate(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a0df  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a0e4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a0e9  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a0ee  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::DetailsTemplateProperty
0x15a0f3  ldstr    aDetailstemplat_0// "DetailsTemplateSelector"
0x15a0f8  ldtoken  System.Windows.Controls.DataTemplateSelector
0x15a0fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a102  ldtoken  System.Windows.Controls.DataGridRow
0x15a107  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a10c  ldnull
0x15a10d  ldnull
0x15a10e  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyDetailsTemplatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a114  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a119  ldnull
0x15a11a  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceDetailsTemplateSelector(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a120  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a125  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a12a  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a12f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::DetailsTemplateSelectorProperty
0x15a134  ldstr    aDetailsvisibil// "DetailsVisibility"
0x15a139  ldtoken  [PresentationCore]System.Windows.Visibility
0x15a13e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a143  ldtoken  System.Windows.Controls.DataGridRow
0x15a148  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a14d  ldc.i4.2
0x15a14e  box      [PresentationCore]System.Windows.Visibility
0x15a153  ldnull
0x15a154  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyDetailsVisibilityChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a15a  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a15f  ldnull
0x15a160  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceDetailsVisibility(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a166  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a16b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a170  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a175  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::DetailsVisibilityProperty
0x15a17a  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::AlternationIndexProperty
0x15a17f  ldtoken  System.Windows.Controls.DataGridRow
0x15a184  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a189  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x15a18e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::AlternationIndexProperty
0x15a193  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Selector::IsSelectedProperty
0x15a198  ldtoken  System.Windows.Controls.DataGridRow
0x15a19d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a1a2  ldc.i4.0
0x15a1a3  box      [mscorlib]System.Boolean
0x15a1a8  ldc.i4   0x500
0x15a1ad  ldnull
0x15a1ae  ldftn    void System.Windows.Controls.DataGridRow::OnIsSelectedChanged(object sender, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a1b4  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a1b9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15a1be  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a1c3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::IsSelectedProperty
0x15a1c8  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.Selector::SelectedEvent
0x15a1cd  ldtoken  System.Windows.Controls.DataGridRow
0x15a1d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a1d7  callvirt instance class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type)
0x15a1dc  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.DataGridRow::SelectedEvent
0x15a1e1  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.Selector::UnselectedEvent
0x15a1e6  ldtoken  System.Windows.Controls.DataGridRow
0x15a1eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a1f0  callvirt instance class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type)
0x15a1f5  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.DataGridRow::UnselectedEvent
0x15a1fa  ldstr    aIsediting// "IsEditing"
0x15a1ff  ldtoken  [mscorlib]System.Boolean
0x15a204  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a209  ldtoken  System.Windows.Controls.DataGridRow
0x15a20e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a213  ldc.i4.0
0x15a214  box      [mscorlib]System.Boolean
0x15a219  ldnull
0x15a21a  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowAndRowHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a220  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a225  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15a22a  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a22f  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridRow::IsEditingPropertyKey
0x15a234  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridRow::IsEditingPropertyKey
0x15a239  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15a23e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::IsEditingProperty
0x15a243  ldstr    aIsnewitem// "IsNewItem"
0x15a248  ldtoken  [mscorlib]System.Boolean
0x15a24d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a252  ldtoken  System.Windows.Controls.DataGridRow
0x15a257  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a25c  ldc.i4.0
0x15a25d  box      [mscorlib]System.Boolean
0x15a262  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15a267  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a26c  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridRow::IsNewItemPropertyKey
0x15a271  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridRow::IsNewItemPropertyKey
0x15a276  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x15a27b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::IsNewItemProperty
0x15a280  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::VisibilityProperty
0x15a285  ldtoken  System.Windows.Controls.DataGridRow
0x15a28a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a28f  ldnull
0x15a290  ldnull
0x15a291  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceVisibility(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a297  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a29c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a2a1  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a2a6  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x15a2ab  ldtoken  System.Windows.Controls.DataGridRow
0x15a2b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a2b5  ldtoken  System.Windows.Controls.DataGridRow
0x15a2ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a2bf  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15a2c4  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a2c9  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridRow::ItemsPanelProperty
0x15a2ce  ldtoken  System.Windows.Controls.DataGridRow
0x15a2d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a2d8  ldtoken  System.Windows.Controls.DataGridCellsPanel
0x15a2dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a2e2  newobj   instance void System.Windows.FrameworkElementFactory::.ctor(class [mscorlib]System.Type type)
0x15a2e7  newobj   instance void System.Windows.Controls.ItemsPanelTemplate::.ctor(class System.Windows.FrameworkElementFactory root)
0x15a2ec  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15a2f1  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a2f6  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::FocusableProperty
0x15a2fb  ldtoken  System.Windows.Controls.DataGridRow
0x15a300  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a305  ldc.i4.0
0x15a306  box      [mscorlib]System.Boolean
0x15a30b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x15a310  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a315  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::BackgroundProperty
0x15a31a  ldtoken  System.Windows.Controls.DataGridRow
0x15a31f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a324  ldnull
0x15a325  ldnull
0x15a326  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a32c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a331  ldnull
0x15a332  ldftn    object System.Windows.Controls.DataGridRow::OnCoerceBackground(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15a338  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15a33d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15a342  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a347  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::BindingGroupProperty
0x15a34c  ldtoken  System.Windows.Controls.DataGridRow
0x15a351  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15a356  ldnull
0x15a357  ldftn    void System.Windows.Controls.DataGridRow::OnNotifyRowPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15a35d  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15a362  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15a367  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15a36c  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::SnapsToDevicePixelsProperty
0x15a371  ldtoken  System.Windows.Controls.DataGridRow
  ... truncated ...
```
