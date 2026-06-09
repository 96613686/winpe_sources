# System.Windows.Input.CommandDevice::.cctor

- ea: `0x30860`
- end: `0x30885`
- name: `System.Windows.Input.CommandDevice::.cctor`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1cce0`

## string_xrefs

- `0x30860`: `CommandDevice`

## pseudocode

```c

```

## disassembly

```asm
0x30860  ldstr    aCommanddevice// "CommandDevice"
0x30865  ldc.i4.1
0x30866  ldtoken  System.Windows.Input.CommandDeviceEventHandler
0x3086b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30870  ldtoken  System.Windows.Input.CommandDevice
0x30875  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3087a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x3087f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.CommandDevice::CommandDeviceEvent
0x30884  ret
```
