# System.Windows.Input.AccessKeyManager::.cctor

- ea: `0x36e20`
- end: `0x36e68`
- name: `System.Windows.Input.AccessKeyManager::.cctor`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1cce0`

## string_xrefs

- `0x36e20`: `AccessKeyPressed`
- `0x36e44`: `AccessKeyElement`

## pseudocode

```c

```

## disassembly

```asm
0x36e20  ldstr    aAccesskeypress// "AccessKeyPressed"
0x36e25  ldc.i4.1
0x36e26  ldtoken  System.Windows.Input.AccessKeyPressedEventHandler
0x36e2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36e30  ldtoken  System.Windows.Input.AccessKeyManager
0x36e35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36e3a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x36e3f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.AccessKeyManager::AccessKeyPressedEvent
0x36e44  ldstr    aAccesskeyeleme// "AccessKeyElement"
0x36e49  ldtoken  [mscorlib]System.WeakReference
0x36e4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36e53  ldtoken  System.Windows.Input.AccessKeyManager
0x36e58  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36e5d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x36e62  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.AccessKeyManager::AccessKeyElementProperty
0x36e67  ret
```
