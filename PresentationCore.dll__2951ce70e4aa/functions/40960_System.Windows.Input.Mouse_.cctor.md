# System.Windows.Input.Mouse::.cctor

- ea: `0x40960`
- end: `0x40b7d`
- name: `System.Windows.Input.Mouse::.cctor`
- size: `541`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1cce0`

## string_xrefs

- `0x40960`: `PreviewMouseMove`
- `0x40984`: `MouseMove`
- `0x409a8`: `PreviewMouseDownOutsideCapturedElement`
- `0x409cc`: `PreviewMouseUpOutsideCapturedElement`

## pseudocode

```c

```

## disassembly

```asm
0x40960  ldstr    aPreviewmousemo// "PreviewMouseMove"
0x40965  ldc.i4.0
0x40966  ldtoken  System.Windows.Input.MouseEventHandler
0x4096b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40970  ldtoken  System.Windows.Input.Mouse
0x40975  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4097a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4097f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseMoveEvent
0x40984  ldstr    aMousemove// "MouseMove"
0x40989  ldc.i4.1
0x4098a  ldtoken  System.Windows.Input.MouseEventHandler
0x4098f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40994  ldtoken  System.Windows.Input.Mouse
0x40999  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4099e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x409a3  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseMoveEvent
0x409a8  ldstr    aPreviewmousedo// "PreviewMouseDownOutsideCapturedElement"
0x409ad  ldc.i4.0
0x409ae  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x409b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x409b8  ldtoken  System.Windows.Input.Mouse
0x409bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x409c2  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x409c7  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseDownOutsideCapturedElementEvent
0x409cc  ldstr    aPreviewmouseup// "PreviewMouseUpOutsideCapturedElement"
0x409d1  ldc.i4.0
0x409d2  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x409d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x409dc  ldtoken  System.Windows.Input.Mouse
0x409e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x409e6  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x409eb  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseUpOutsideCapturedElementEvent
0x409f0  ldstr    aPreviewmousedo_0// "PreviewMouseDown"
0x409f5  ldc.i4.0
0x409f6  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x409fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a00  ldtoken  System.Windows.Input.Mouse
0x40a05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a0a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40a0f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseDownEvent
0x40a14  ldstr    aMousedown// "MouseDown"
0x40a19  ldc.i4.1
0x40a1a  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x40a1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a24  ldtoken  System.Windows.Input.Mouse
0x40a29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a2e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40a33  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseDownEvent
0x40a38  ldstr    aPreviewmouseup_0// "PreviewMouseUp"
0x40a3d  ldc.i4.0
0x40a3e  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x40a43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a48  ldtoken  System.Windows.Input.Mouse
0x40a4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a52  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40a57  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseUpEvent
0x40a5c  ldstr    aMouseup// "MouseUp"
0x40a61  ldc.i4.1
0x40a62  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x40a67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a6c  ldtoken  System.Windows.Input.Mouse
0x40a71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a76  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40a7b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseUpEvent
0x40a80  ldstr    aPreviewmousewh// "PreviewMouseWheel"
0x40a85  ldc.i4.0
0x40a86  ldtoken  System.Windows.Input.MouseWheelEventHandler
0x40a8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a90  ldtoken  System.Windows.Input.Mouse
0x40a95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a9a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40a9f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseWheelEvent
0x40aa4  ldstr    aMousewheel// "MouseWheel"
0x40aa9  ldc.i4.1
0x40aaa  ldtoken  System.Windows.Input.MouseWheelEventHandler
0x40aaf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40ab4  ldtoken  System.Windows.Input.Mouse
0x40ab9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40abe  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40ac3  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseWheelEvent
0x40ac8  ldstr    aMouseenter// "MouseEnter"
0x40acd  ldc.i4.2
0x40ace  ldtoken  System.Windows.Input.MouseEventHandler
0x40ad3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40ad8  ldtoken  System.Windows.Input.Mouse
0x40add  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40ae2  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40ae7  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseEnterEvent
0x40aec  ldstr    aMouseleave// "MouseLeave"
0x40af1  ldc.i4.2
0x40af2  ldtoken  System.Windows.Input.MouseEventHandler
0x40af7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40afc  ldtoken  System.Windows.Input.Mouse
0x40b01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b06  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40b0b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseLeaveEvent
0x40b10  ldstr    aGotmousecaptur// "GotMouseCapture"
0x40b15  ldc.i4.1
0x40b16  ldtoken  System.Windows.Input.MouseEventHandler
0x40b1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b20  ldtoken  System.Windows.Input.Mouse
0x40b25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b2a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40b2f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::GotMouseCaptureEvent
0x40b34  ldstr    aLostmousecaptu// "LostMouseCapture"
0x40b39  ldc.i4.1
0x40b3a  ldtoken  System.Windows.Input.MouseEventHandler
0x40b3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b44  ldtoken  System.Windows.Input.Mouse
0x40b49  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b4e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40b53  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::LostMouseCaptureEvent
0x40b58  ldstr    aQuerycursor// "QueryCursor"
0x40b5d  ldc.i4.1
0x40b5e  ldtoken  System.Windows.Input.QueryCursorEventHandler
0x40b63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b68  ldtoken  System.Windows.Input.Mouse
0x40b6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b72  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x40b77  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::QueryCursorEvent
0x40b7c  ret
```
