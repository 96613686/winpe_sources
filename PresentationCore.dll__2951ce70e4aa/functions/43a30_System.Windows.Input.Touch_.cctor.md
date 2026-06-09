# System.Windows.Input.Touch::.cctor

- ea: `0x43a30`
- end: `0x43b99`
- name: `System.Windows.Input.Touch::.cctor`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1cce0`

## string_xrefs

- `0x43a78`: `PreviewTouchMove`
- `0x43a9c`: `TouchMove`

## pseudocode

```c

```

## disassembly

```asm
0x43a30  ldstr    aPreviewtouchdo// "PreviewTouchDown"
0x43a35  ldc.i4.0
0x43a36  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43a3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a40  ldtoken  System.Windows.Input.Touch
0x43a45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a4a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43a4f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::PreviewTouchDownEvent
0x43a54  ldstr    aTouchdown// "TouchDown"
0x43a59  ldc.i4.1
0x43a5a  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43a5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a64  ldtoken  System.Windows.Input.Touch
0x43a69  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a6e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43a73  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchDownEvent
0x43a78  ldstr    aPreviewtouchmo// "PreviewTouchMove"
0x43a7d  ldc.i4.0
0x43a7e  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43a83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a88  ldtoken  System.Windows.Input.Touch
0x43a8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43a92  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43a97  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::PreviewTouchMoveEvent
0x43a9c  ldstr    aTouchmove// "TouchMove"
0x43aa1  ldc.i4.1
0x43aa2  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43aa7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43aac  ldtoken  System.Windows.Input.Touch
0x43ab1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43ab6  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43abb  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchMoveEvent
0x43ac0  ldstr    aPreviewtouchup// "PreviewTouchUp"
0x43ac5  ldc.i4.0
0x43ac6  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43acb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43ad0  ldtoken  System.Windows.Input.Touch
0x43ad5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43ada  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43adf  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::PreviewTouchUpEvent
0x43ae4  ldstr    aTouchup// "TouchUp"
0x43ae9  ldc.i4.1
0x43aea  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43aef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43af4  ldtoken  System.Windows.Input.Touch
0x43af9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43afe  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43b03  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchUpEvent
0x43b08  ldstr    aGottouchcaptur// "GotTouchCapture"
0x43b0d  ldc.i4.1
0x43b0e  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43b13  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b18  ldtoken  System.Windows.Input.Touch
0x43b1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b22  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43b27  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::GotTouchCaptureEvent
0x43b2c  ldstr    aLosttouchcaptu// "LostTouchCapture"
0x43b31  ldc.i4.1
0x43b32  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43b37  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b3c  ldtoken  System.Windows.Input.Touch
0x43b41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b46  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43b4b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::LostTouchCaptureEvent
0x43b50  ldstr    aTouchenter// "TouchEnter"
0x43b55  ldc.i4.2
0x43b56  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43b5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b60  ldtoken  System.Windows.Input.Touch
0x43b65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b6a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43b6f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchEnterEvent
0x43b74  ldstr    aTouchleave// "TouchLeave"
0x43b79  ldc.i4.2
0x43b7a  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.Input.TouchEventArgs>
0x43b7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b84  ldtoken  System.Windows.Input.Touch
0x43b89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43b8e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x43b93  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchLeaveEvent
0x43b98  ret
```
