# System.Windows.Controls.PopupControlService::.cctor

- ea: `0x1863b0`
- end: `0x186462`
- name: `System.Windows.Controls.PopupControlService::.cctor`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x159e0`
- `0x15a20`

## string_xrefs

- `0x1863b0`: `Opened`
- `0x1863f8`: `ServiceOwned`

## pseudocode

```c

```

## disassembly

```asm
0x1863b0  ldstr    aOpened// "Opened"
0x1863b5  ldc.i4.1
0x1863b6  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x1863bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1863c0  ldtoken  System.Windows.Controls.PopupControlService
0x1863c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1863ca  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1863cf  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.PopupControlService::ContextMenuOpenedEvent
0x1863d4  ldstr    aClosed// "Closed"
0x1863d9  ldc.i4.1
0x1863da  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x1863df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1863e4  ldtoken  System.Windows.Controls.PopupControlService
0x1863e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1863ee  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1863f3  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.PopupControlService::ContextMenuClosedEvent
0x1863f8  ldstr    aServiceowned// "ServiceOwned"
0x1863fd  ldtoken  [mscorlib]System.Boolean
0x186402  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x186407  ldtoken  System.Windows.Controls.PopupControlService
0x18640c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x186411  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x186416  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18641b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x186420  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.PopupControlService::ServiceOwnedProperty
0x186425  ldstr    aOwner_0// "Owner"
0x18642a  ldtoken  [WindowsBase]System.Windows.DependencyObject
0x18642f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x186434  ldtoken  System.Windows.Controls.PopupControlService
0x186439  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18643e  ldnull
0x18643f  ldnull
0x186440  ldftn    void System.Windows.Controls.PopupControlService::OnOwnerChanged(class [WindowsBase]System.Windows.DependencyObject o, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x186446  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x18644b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x186450  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x186455  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.PopupControlService::OwnerProperty
0x18645a  ldc.i4.s 0x49
0x18645c  stsfld   int32 System.Windows.Controls.PopupControlService::ShortDelay
0x186461  ret
```
