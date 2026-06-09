# System.Windows.Data.Binding::.cctor

- ea: `0x75c00`
- end: `0x75ca9`
- name: `System.Windows.Data.Binding::.cctor`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x15a40`
- `0x233a00`

## string_xrefs

- `0x75c00`: `SourceUpdated`
- `0x75c24`: `TargetUpdated`
- `0x75c48`: `XmlNamespaceManager`

## pseudocode

```c

```

## disassembly

```asm
0x75c00  ldstr    aSourceupdated// "SourceUpdated"
0x75c05  ldc.i4.1
0x75c06  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Data.DataTransferEventArgs>
0x75c0b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c10  ldtoken  System.Windows.Data.Binding
0x75c15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c1a  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x75c1f  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Data.Binding::SourceUpdatedEvent
0x75c24  ldstr    aTargetupdated// "TargetUpdated"
0x75c29  ldc.i4.1
0x75c2a  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Data.DataTransferEventArgs>
0x75c2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c34  ldtoken  System.Windows.Data.Binding
0x75c39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c3e  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x75c43  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Data.Binding::TargetUpdatedEvent
0x75c48  ldstr    aXmlnamespacema_1// "XmlNamespaceManager"
0x75c4d  ldtoken  [mscorlib]System.Object
0x75c52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c57  ldtoken  System.Windows.Data.Binding
0x75c5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c61  ldnull
0x75c62  ldc.i4.s 0x20
0x75c64  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x75c69  ldnull
0x75c6a  ldftn    bool System.Windows.Data.Binding::IsValidXmlNamespaceManager(object value)
0x75c70  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x75c75  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x75c7a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Data.Binding::XmlNamespaceManagerProperty
0x75c7f  ldstr    aBindingDonothi// "Binding.DoNothing"
0x75c84  newobj   instance void [WindowsBase]MS.Internal.NamedObject::.ctor(string)
0x75c89  stsfld   object System.Windows.Data.Binding::DoNothing
0x75c8e  ldnull
0x75c8f  newobj   instance void MS.Internal.Data.ExplicitObjectRef::.ctor(object o)
0x75c94  stsfld   class MS.Internal.Data.ObjectRef System.Windows.Data.Binding::UnsetSource
0x75c99  ldsfld   object System.Windows.Data.BindingExpression::StaticSource
0x75c9e  newobj   instance void MS.Internal.Data.ExplicitObjectRef::.ctor(object o)
0x75ca3  stsfld   class MS.Internal.Data.ObjectRef System.Windows.Data.Binding::StaticSourceRef
0x75ca8  ret
```
