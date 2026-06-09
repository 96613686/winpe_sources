# System.Windows.Documents.Hyperlink::.cctor

- ea: `0xe0e40`
- end: `0xe103b`
- name: `System.Windows.Documents.Hyperlink::.cctor`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x159e0`
- `0x15a20`
- `0x15a30`

## string_xrefs

- `0xe0e40`: `Command`
- `0xe0e75`: `CommandParameter`
- `0xe0e9e`: `CommandTarget`
- `0xe0ec7`: `NavigateUri`
- `0xe0f96`: `IsHyperlinkPressed`

## pseudocode

```c

```

## disassembly

```asm
0xe0e40  ldstr    aCommand// "Command"
0xe0e45  ldtoken  [System]System.Windows.Input.ICommand
0xe0e4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0e4f  ldtoken  System.Windows.Documents.Hyperlink
0xe0e54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0e59  ldnull
0xe0e5a  ldnull
0xe0e5b  ldftn    void System.Windows.Documents.Hyperlink::OnCommandChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0e61  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0e66  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0xe0e6b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0e70  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::CommandProperty
0xe0e75  ldstr    aCommandparamet// "CommandParameter"
0xe0e7a  ldtoken  [mscorlib]System.Object
0xe0e7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0e84  ldtoken  System.Windows.Documents.Hyperlink
0xe0e89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0e8e  ldnull
0xe0e8f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe0e94  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0e99  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::CommandParameterProperty
0xe0e9e  ldstr    aCommandtarget// "CommandTarget"
0xe0ea3  ldtoken  [PresentationCore]System.Windows.IInputElement
0xe0ea8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0ead  ldtoken  System.Windows.Documents.Hyperlink
0xe0eb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0eb7  ldnull
0xe0eb8  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe0ebd  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0ec2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::CommandTargetProperty
0xe0ec7  ldstr    aNavigateuri// "NavigateUri"
0xe0ecc  ldtoken  [System]System.Uri
0xe0ed1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0ed6  ldtoken  System.Windows.Documents.Hyperlink
0xe0edb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0ee0  ldnull
0xe0ee1  ldnull
0xe0ee2  ldftn    void System.Windows.Documents.Hyperlink::OnNavigateUriChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0xe0ee8  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0xe0eed  ldnull
0xe0eee  ldftn    object System.Windows.Documents.Hyperlink::CoerceNavigateUri(class [WindowsBase]System.Windows.DependencyObject d, object value)
0xe0ef4  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0xe0ef9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0xe0efe  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0f03  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::NavigateUriProperty
0xe0f08  ldstr    aTargetname// "TargetName"
0xe0f0d  ldtoken  [mscorlib]System.String
0xe0f12  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f17  ldtoken  System.Windows.Documents.Hyperlink
0xe0f1c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f21  ldsfld   string [mscorlib]System.String::Empty
0xe0f26  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe0f2b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0f30  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::TargetNameProperty
0xe0f35  ldstr    aRequestnavigat_0// "RequestNavigate"
0xe0f3a  ldc.i4.1
0xe0f3b  ldtoken  System.Windows.Navigation.RequestNavigateEventHandler
0xe0f40  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f45  ldtoken  System.Windows.Documents.Hyperlink
0xe0f4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f4f  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe0f54  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Documents.Hyperlink::RequestNavigateEvent
0xe0f59  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.Primitives.ButtonBase::ClickEvent
0xe0f5e  ldtoken  System.Windows.Documents.Hyperlink
0xe0f63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f68  callvirt instance class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type)
0xe0f6d  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Documents.Hyperlink::ClickEvent
0xe0f72  ldstr    aRequestsetstat// "RequestSetStatusBar"
0xe0f77  ldc.i4.1
0xe0f78  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0xe0f7d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f82  ldtoken  System.Windows.Documents.Hyperlink
0xe0f87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0f8c  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe0f91  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Documents.Hyperlink::RequestSetStatusBarEvent
0xe0f96  ldstr    aIshyperlinkpre// "IsHyperlinkPressed"
0xe0f9b  ldtoken  [mscorlib]System.Boolean
0xe0fa0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0fa5  ldtoken  System.Windows.Documents.Hyperlink
0xe0faa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0faf  ldc.i4.0
0xe0fb0  box      [mscorlib]System.Boolean
0xe0fb5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe0fba  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0fbf  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.Hyperlink::IsHyperlinkPressedProperty
0xe0fc4  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkContentElement::DefaultStyleKeyProperty
0xe0fc9  ldtoken  System.Windows.Documents.Hyperlink
0xe0fce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0fd3  ldtoken  System.Windows.Documents.Hyperlink
0xe0fd8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0fdd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe0fe2  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe0fe7  ldtoken  System.Windows.Documents.Hyperlink
0xe0fec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0ff1  call     class [WindowsBase]System.Windows.DependencyObjectType [WindowsBase]System.Windows.DependencyObjectType::FromSystemTypeInternal(class [mscorlib]System.Type)
0xe0ff6  stsfld   class [WindowsBase]System.Windows.DependencyObjectType System.Windows.Documents.Hyperlink::_dType
0xe0ffb  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.ContentElement::FocusableProperty
0xe1000  ldtoken  System.Windows.Documents.Hyperlink
0xe1005  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe100a  ldc.i4.1
0xe100b  box      [mscorlib]System.Boolean
0xe1010  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xe1015  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xe101a  ldtoken  System.Windows.Documents.Hyperlink
0xe101f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe1024  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::QueryCursorEvent
0xe1029  ldnull
0xe102a  ldftn    void System.Windows.Documents.Hyperlink::OnQueryCursor(object sender, class [PresentationCore]System.Windows.Input.QueryCursorEventArgs e)
0xe1030  newobj   instance void [PresentationCore]System.Windows.Input.QueryCursorEventHandler::.ctor(object, native int)
0xe1035  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0xe103a  ret
```
