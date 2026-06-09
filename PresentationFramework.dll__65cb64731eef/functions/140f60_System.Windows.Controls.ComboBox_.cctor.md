# System.Windows.Controls.ComboBox::.cctor

- ea: `0x140f60`
- end: `0x141439`
- name: `System.Windows.Controls.ComboBox::.cctor`
- size: `1241`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x159e0`
- `0x159f0`
- `0x15a00`
- `0x15a20`
- `0x15a30`
- `0x15a50`
- `0x15a60`
- `0x26790`
- `0x145370`
- `0x24e850`

## string_xrefs

- `0x140fa8`: `IsDropDownOpen`
- `0x1410eb`: `SelectionBoxItemTemplate`
- `0x14115b`: `StaysOpenOnEdit`

## pseudocode

```c

```

## disassembly

```asm
0x140f60  ldstr    aMaxdropdownhei// "MaxDropDownHeight"
0x140f65  ldtoken  [mscorlib]System.Double
0x140f6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140f6f  ldtoken  System.Windows.Controls.ComboBox
0x140f74  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140f79  call     float64 System.Windows.SystemParameters::get_PrimaryScreenHeight()
0x140f7e  ldc.r8   3.0
0x140f87  div
0x140f88  box      [mscorlib]System.Double
0x140f8d  ldnull
0x140f8e  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x140f94  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x140f99  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x140f9e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x140fa3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::MaxDropDownHeightProperty
0x140fa8  ldstr    aIsdropdownopen// "IsDropDownOpen"
0x140fad  ldtoken  [mscorlib]System.Boolean
0x140fb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140fb7  ldtoken  System.Windows.Controls.ComboBox
0x140fbc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140fc1  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x140fc6  ldc.i4   0x100
0x140fcb  ldnull
0x140fcc  ldftn    void System.Windows.Controls.ComboBox::OnIsDropDownOpenChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x140fd2  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x140fd7  ldnull
0x140fd8  ldftn    object System.Windows.Controls.ComboBox::CoerceIsDropDownOpen(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x140fde  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x140fe3  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x140fe8  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x140fed  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::IsDropDownOpenProperty
0x140ff2  ldstr    aShouldpreserve// "ShouldPreserveUserEnteredPrefix"
0x140ff7  ldtoken  [mscorlib]System.Boolean
0x140ffc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141001  ldtoken  System.Windows.Controls.ComboBox
0x141006  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14100b  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x141010  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x141015  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x14101a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::ShouldPreserveUserEnteredPrefixProperty
0x14101f  ldstr    aIseditable// "IsEditable"
0x141024  ldtoken  [mscorlib]System.Boolean
0x141029  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14102e  ldtoken  System.Windows.Controls.ComboBox
0x141033  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141038  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x14103d  ldnull
0x14103e  ldftn    void System.Windows.Controls.ComboBox::OnIsEditableChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x141044  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x141049  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x14104e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141053  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::IsEditableProperty
0x141058  ldstr    aText// "Text"
0x14105d  ldtoken  [mscorlib]System.String
0x141062  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141067  ldtoken  System.Windows.Controls.ComboBox
0x14106c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141071  ldsfld   string [mscorlib]System.String::Empty
0x141076  ldc.i4   0x500
0x14107b  ldnull
0x14107c  ldftn    void System.Windows.Controls.ComboBox::OnTextChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x141082  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x141087  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x14108c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141091  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::TextProperty
0x141096  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.TextBoxBase::IsReadOnlyProperty
0x14109b  ldtoken  System.Windows.Controls.ComboBox
0x1410a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1410a5  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x1410aa  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::IsReadOnlyProperty
0x1410af  ldstr    aSelectionboxit// "SelectionBoxItem"
0x1410b4  ldtoken  [mscorlib]System.Object
0x1410b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1410be  ldtoken  System.Windows.Controls.ComboBox
0x1410c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1410c8  ldsfld   string [mscorlib]System.String::Empty
0x1410cd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1410d2  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1410d7  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemPropertyKey
0x1410dc  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemPropertyKey
0x1410e1  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x1410e6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::SelectionBoxItemProperty
0x1410eb  ldstr    aSelectionboxit_0// "SelectionBoxItemTemplate"
0x1410f0  ldtoken  System.Windows.DataTemplate
0x1410f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1410fa  ldtoken  System.Windows.Controls.ComboBox
0x1410ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141104  ldnull
0x141105  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x14110a  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x14110f  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemTemplatePropertyKey
0x141114  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemTemplatePropertyKey
0x141119  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x14111e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::SelectionBoxItemTemplateProperty
0x141123  ldstr    aSelectionboxit_1// "SelectionBoxItemStringFormat"
0x141128  ldtoken  [mscorlib]System.String
0x14112d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141132  ldtoken  System.Windows.Controls.ComboBox
0x141137  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14113c  ldnull
0x14113d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x141142  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141147  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemStringFormatPropertyKey
0x14114c  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::SelectionBoxItemStringFormatPropertyKey
0x141151  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x141156  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::SelectionBoxItemStringFormatProperty
0x14115b  ldstr    aStaysopenonedi// "StaysOpenOnEdit"
0x141160  ldtoken  [mscorlib]System.Boolean
0x141165  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14116a  ldtoken  System.Windows.Controls.ComboBox
0x14116f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141174  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x141179  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x14117e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141183  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::StaysOpenOnEditProperty
0x141188  ldstr    aIsselectionbox// "IsSelectionBoxHighlighted"
0x14118d  ldtoken  [mscorlib]System.Boolean
0x141192  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141197  ldtoken  System.Windows.Controls.ComboBox
0x14119c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1411a1  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x1411a6  ldnull
0x1411a7  ldnull
0x1411a8  ldftn    object System.Windows.Controls.ComboBox::CoerceIsSelectionBoxHighlighted(object o, object value)
0x1411ae  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1411b3  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1411b8  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1411bd  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::IsSelectionBoxHighlightedPropertyKey
0x1411c2  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ComboBox::IsSelectionBoxHighlightedPropertyKey
0x1411c7  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x1411cc  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::IsSelectionBoxHighlightedProperty
0x1411d1  newobj   instance void [PresentationCore]System.Windows.EventPrivateKey::.ctor()
0x1411d6  stsfld   class [PresentationCore]System.Windows.EventPrivateKey System.Windows.Controls.ComboBox::DropDownOpenedKey
0x1411db  newobj   instance void [PresentationCore]System.Windows.EventPrivateKey::.ctor()
0x1411e0  stsfld   class [PresentationCore]System.Windows.EventPrivateKey System.Windows.Controls.ComboBox::DropDownClosedKey
0x1411e5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.KeyboardNavigation::TabNavigationProperty
0x1411ea  ldtoken  System.Windows.Controls.ComboBox
0x1411ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1411f4  ldc.i4.5
0x1411f5  box      System.Windows.Input.KeyboardNavigationMode
0x1411fa  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1411ff  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141204  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.KeyboardNavigation::ControlTabNavigationProperty
0x141209  ldtoken  System.Windows.Controls.ComboBox
0x14120e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141213  ldc.i4.3
0x141214  box      System.Windows.Input.KeyboardNavigationMode
0x141219  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x14121e  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141223  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.KeyboardNavigation::DirectionalNavigationProperty
0x141228  ldtoken  System.Windows.Controls.ComboBox
0x14122d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141232  ldc.i4.3
0x141233  box      System.Windows.Input.KeyboardNavigationMode
0x141238  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x14123d  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141242  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::IsEnabledProperty
0x141247  ldtoken  System.Windows.Controls.ComboBox
0x14124c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141251  ldnull
0x141252  ldnull
0x141253  ldftn    object System.Windows.Controls.ComboBox::CoerceToolTipIsEnabled(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x141259  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x14125e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x141263  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141268  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x14126d  ldtoken  System.Windows.Controls.ComboBox
0x141272  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141277  ldtoken  System.Windows.Controls.ComboBox
0x14127c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141281  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x141286  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x14128b  ldtoken  System.Windows.Controls.ComboBox
0x141290  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141295  call     class [WindowsBase]System.Windows.DependencyObjectType [WindowsBase]System.Windows.DependencyObjectType::FromSystemTypeInternal(class [mscorlib]System.Type)
0x14129a  stsfld   class [WindowsBase]System.Windows.DependencyObjectType System.Windows.Controls.ComboBox::_dType
0x14129f  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::IsTextSearchEnabledProperty
0x1412a4  ldtoken  System.Windows.Controls.ComboBox
0x1412a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1412ae  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x1412b3  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1412b8  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1412bd  ldtoken  System.Windows.Controls.ComboBox
0x1412c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1412c7  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::LostMouseCaptureEvent
0x1412cc  ldnull
0x1412cd  ldftn    void System.Windows.Controls.ComboBox::OnLostMouseCapture(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x1412d3  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x1412d8  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x1412dd  ldtoken  System.Windows.Controls.ComboBox
0x1412e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1412e7  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseDownEvent
0x1412ec  ldnull
0x1412ed  ldftn    void System.Windows.Controls.ComboBox::OnMouseButtonDown(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x1412f3  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x1412f8  ldc.i4.1
0x1412f9  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1412fe  ldtoken  System.Windows.Controls.ComboBox
0x141303  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141308  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseMoveEvent
0x14130d  ldnull
0x14130e  ldftn    void System.Windows.Controls.ComboBox::OnMouseMove(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x141314  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x141319  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x14131e  ldtoken  System.Windows.Controls.ComboBox
0x141323  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141328  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::PreviewMouseDownEvent
0x14132d  ldnull
0x14132e  ldftn    void System.Windows.Controls.ComboBox::OnPreviewMouseButtonDown(object sender, class [PresentationCore]System.Windows.Input.MouseButtonEventArgs e)
0x141334  newobj   instance void [PresentationCore]System.Windows.Input.MouseButtonEventHandler::.ctor(object, native int)
0x141339  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x14133e  ldtoken  System.Windows.Controls.ComboBox
0x141343  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141348  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseWheelEvent
0x14134d  ldnull
0x14134e  ldftn    void System.Windows.Controls.ComboBox::OnMouseWheel(object sender, class [PresentationCore]System.Windows.Input.MouseWheelEventArgs e)
0x141354  newobj   instance void [PresentationCore]System.Windows.Input.MouseWheelEventHandler::.ctor(object, native int)
0x141359  ldc.i4.1
0x14135a  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x14135f  ldtoken  System.Windows.Controls.ComboBox
0x141364  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141369  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.UIElement::GotFocusEvent
0x14136e  ldnull
0x14136f  ldftn    void System.Windows.Controls.ComboBox::OnGotFocus(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0x141375  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0x14137a  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x14137f  ldtoken  System.Windows.Controls.ComboBox
0x141384  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141389  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ContextMenuService::ContextMenuOpeningEvent
0x14138e  ldnull
0x14138f  ldftn    void System.Windows.Controls.ComboBox::OnContextMenuOpen(object sender, class System.Windows.Controls.ContextMenuEventArgs e)
0x141395  newobj   instance void System.Windows.Controls.ContextMenuEventHandler::.ctor(object object, native int method)
0x14139a  ldc.i4.1
0x14139b  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1413a0  ldtoken  System.Windows.Controls.ComboBox
0x1413a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1413aa  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ContextMenuService::ContextMenuClosingEvent
0x1413af  ldnull
0x1413b0  ldftn    void System.Windows.Controls.ComboBox::OnContextMenuClose(object sender, class System.Windows.Controls.ContextMenuEventArgs e)
0x1413b6  newobj   instance void System.Windows.Controls.ContextMenuEventHandler::.ctor(object object, native int method)
0x1413bb  ldc.i4.1
0x1413bc  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x1413c1  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::IsEnabledProperty
0x1413c6  ldtoken  System.Windows.Controls.ComboBox
0x1413cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1413d0  ldnull
0x1413d1  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1413d7  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1413dc  newobj   instance void [PresentationCore]System.Windows.UIPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x1413e1  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1413e6  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey [PresentationCore]System.Windows.UIElement::IsMouseOverPropertyKey
0x1413eb  ldtoken  System.Windows.Controls.ComboBox
0x1413f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1413f5  ldnull
0x1413f6  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1413fc  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x141401  newobj   instance void [PresentationCore]System.Windows.UIPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x141406  callvirt instance void [WindowsBase]System.Windows.DependencyPropertyKey::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x14140b  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.Primitives.Selector::IsSelectionActivePropertyKey
0x141410  ldtoken  System.Windows.Controls.ComboBox
0x141415  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14141a  ldnull
0x14141b  ldftn    void System.Windows.Controls.Control::OnVisualStatePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x141421  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x141426  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x14142b  callvirt instance void [WindowsBase]System.Windows.DependencyPropertyKey::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x141430  ldc.i4.s 0x20
0x141432  conv.i8
0x141433  call     void MS.Internal.Telemetry.PresentationFramework.ControlsTraceLogger::AddControl(valuetype MS.Internal.Telemetry.PresentationFramework.TelemetryControls control)
0x141438  ret
```
