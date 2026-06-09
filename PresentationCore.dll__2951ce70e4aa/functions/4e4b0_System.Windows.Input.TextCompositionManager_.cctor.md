# System.Windows.Input.TextCompositionManager::.cctor

- ea: `0x4e4b0`
- end: `0x4e595`
- name: `System.Windows.Input.TextCompositionManager::.cctor`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1cce0`

## string_xrefs

- `0x4e4f8`: `PreviewTextInputUpdate`
- `0x4e51c`: `TextInputUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x4e4b0  ldstr    aPreviewtextinp// "PreviewTextInputStart"
0x4e4b5  ldc.i4.0
0x4e4b6  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e4bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e4c0  ldtoken  System.Windows.Input.TextCompositionManager
0x4e4c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e4ca  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e4cf  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputStartEvent
0x4e4d4  ldstr    aTextinputstart// "TextInputStart"
0x4e4d9  ldc.i4.1
0x4e4da  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e4df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e4e4  ldtoken  System.Windows.Input.TextCompositionManager
0x4e4e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e4ee  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e4f3  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::TextInputStartEvent
0x4e4f8  ldstr    aPreviewtextinp_0// "PreviewTextInputUpdate"
0x4e4fd  ldc.i4.0
0x4e4fe  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e503  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e508  ldtoken  System.Windows.Input.TextCompositionManager
0x4e50d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e512  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e517  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputUpdateEvent
0x4e51c  ldstr    aTextinputupdat// "TextInputUpdate"
0x4e521  ldc.i4.1
0x4e522  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e527  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e52c  ldtoken  System.Windows.Input.TextCompositionManager
0x4e531  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e536  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e53b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::TextInputUpdateEvent
0x4e540  ldstr    aPreviewtextinp_1// "PreviewTextInput"
0x4e545  ldc.i4.0
0x4e546  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e54b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e550  ldtoken  System.Windows.Input.TextCompositionManager
0x4e555  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e55a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e55f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputEvent
0x4e564  ldstr    aTextinput// "TextInput"
0x4e569  ldc.i4.1
0x4e56a  ldtoken  System.Windows.Input.TextCompositionEventHandler
0x4e56f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e574  ldtoken  System.Windows.Input.TextCompositionManager
0x4e579  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e57e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4e583  stsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::TextInputEvent
0x4e588  ldc.i4.0
0x4e589  stsfld   bool System.Windows.Input.TextCompositionManager::_isHexNumpadRegistryChecked
0x4e58e  ldc.i4.0
0x4e58f  stsfld   bool System.Windows.Input.TextCompositionManager::_isHexNumpadEnabled
0x4e594  ret
```
