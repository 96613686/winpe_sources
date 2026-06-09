# System.Windows.UIElement::.cctor

- ea: `0x22b70`
- end: `0x23d3a`
- name: `System.Windows.UIElement::.cctor`
- size: `4554`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x1cce0`
- `0x1cd70`
- `0x1ce90`
- `0x1e600`
- `0x1fa80`
- `0x2baf0`
- `0x2bb60`
- `0x2cfd0`
- `0x2d430`
- `0x2d4a0`
- `0x2e740`
- `0x2e750`
- `0x2e760`
- `0x2e770`
- `0x2e800`
- `0x45080`
- `0x450c0`
- `0x95ae0`

## string_xrefs

- `0x23715`: `CacheMode`

## pseudocode

```c

```

## disassembly

```asm
0x22b70  ldtoken  System.Windows.UIElement
0x22b75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22b7a  stsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22b7f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseDownEvent
0x22b84  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22b89  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22b8e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseDownEvent
0x22b93  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseDownEvent
0x22b98  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22b9d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22ba2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseDownEvent
0x22ba7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseUpEvent
0x22bac  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22bb1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22bb6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseUpEvent
0x22bbb  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseUpEvent
0x22bc0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22bc5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22bca  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseUpEvent
0x22bcf  ldstr    aPreviewmousele// "PreviewMouseLeftButtonDown"
0x22bd4  ldc.i4.2
0x22bd5  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22bda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22bdf  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22be4  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22be9  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseLeftButtonDownEvent
0x22bee  ldstr    aMouseleftbutto// "MouseLeftButtonDown"
0x22bf3  ldc.i4.2
0x22bf4  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22bf9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22bfe  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c03  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22c08  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseLeftButtonDownEvent
0x22c0d  ldstr    aPreviewmousele_0// "PreviewMouseLeftButtonUp"
0x22c12  ldc.i4.2
0x22c13  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22c18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c1d  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c22  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22c27  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseLeftButtonUpEvent
0x22c2c  ldstr    aMouseleftbutto_0// "MouseLeftButtonUp"
0x22c31  ldc.i4.2
0x22c32  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22c37  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c3c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c41  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22c46  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseLeftButtonUpEvent
0x22c4b  ldstr    aPreviewmouseri// "PreviewMouseRightButtonDown"
0x22c50  ldc.i4.2
0x22c51  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22c56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c5b  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c60  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22c65  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseRightButtonDownEvent
0x22c6a  ldstr    aMouserightbutt// "MouseRightButtonDown"
0x22c6f  ldc.i4.2
0x22c70  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22c75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c7a  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c7f  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22c84  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseRightButtonDownEvent
0x22c89  ldstr    aPreviewmouseri_0// "PreviewMouseRightButtonUp"
0x22c8e  ldc.i4.2
0x22c8f  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22c94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22c99  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22c9e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22ca3  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseRightButtonUpEvent
0x22ca8  ldstr    aMouserightbutt_0// "MouseRightButtonUp"
0x22cad  ldc.i4.2
0x22cae  ldtoken  System.Windows.Input.MouseButtonEventHandler
0x22cb3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22cb8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22cbd  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x22cc2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseRightButtonUpEvent
0x22cc7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseMoveEvent
0x22ccc  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22cd1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22cd6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseMoveEvent
0x22cdb  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseMoveEvent
0x22ce0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22ce5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22cea  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseMoveEvent
0x22cef  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::PreviewMouseWheelEvent
0x22cf4  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22cf9  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22cfe  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewMouseWheelEvent
0x22d03  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseWheelEvent
0x22d08  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d0d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d12  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseWheelEvent
0x22d17  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseEnterEvent
0x22d1c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d21  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d26  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseEnterEvent
0x22d2b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::MouseLeaveEvent
0x22d30  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d35  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d3a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::MouseLeaveEvent
0x22d3f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::GotMouseCaptureEvent
0x22d44  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d49  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d4e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::GotMouseCaptureEvent
0x22d53  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::LostMouseCaptureEvent
0x22d58  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d5d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d62  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::LostMouseCaptureEvent
0x22d67  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Mouse::QueryCursorEvent
0x22d6c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d71  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d76  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::QueryCursorEvent
0x22d7b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusDownEvent
0x22d80  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d85  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d8a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusDownEvent
0x22d8f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusDownEvent
0x22d94  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22d99  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22d9e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusDownEvent
0x22da3  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusUpEvent
0x22da8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22dad  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22db2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusUpEvent
0x22db7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusUpEvent
0x22dbc  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22dc1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22dc6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusUpEvent
0x22dcb  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusMoveEvent
0x22dd0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22dd5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22dda  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusMoveEvent
0x22ddf  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusMoveEvent
0x22de4  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22de9  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22dee  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusMoveEvent
0x22df3  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusInAirMoveEvent
0x22df8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22dfd  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e02  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusInAirMoveEvent
0x22e07  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusInAirMoveEvent
0x22e0c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e11  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e16  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusInAirMoveEvent
0x22e1b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusEnterEvent
0x22e20  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e25  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e2a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusEnterEvent
0x22e2f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusLeaveEvent
0x22e34  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e39  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e3e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusLeaveEvent
0x22e43  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusInRangeEvent
0x22e48  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e4d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e52  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusInRangeEvent
0x22e57  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusInRangeEvent
0x22e5c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e61  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e66  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusInRangeEvent
0x22e6b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusOutOfRangeEvent
0x22e70  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e75  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e7a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusOutOfRangeEvent
0x22e7f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusOutOfRangeEvent
0x22e84  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e89  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22e8e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusOutOfRangeEvent
0x22e93  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusSystemGestureEvent
0x22e98  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22e9d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22ea2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusSystemGestureEvent
0x22ea7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusSystemGestureEvent
0x22eac  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22eb1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22eb6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusSystemGestureEvent
0x22ebb  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::GotStylusCaptureEvent
0x22ec0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22ec5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22eca  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::GotStylusCaptureEvent
0x22ecf  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::LostStylusCaptureEvent
0x22ed4  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22ed9  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22ede  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::LostStylusCaptureEvent
0x22ee3  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusButtonDownEvent
0x22ee8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22eed  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22ef2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusButtonDownEvent
0x22ef7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusButtonUpEvent
0x22efc  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f01  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f06  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::StylusButtonUpEvent
0x22f0b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusButtonDownEvent
0x22f10  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f15  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f1a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusButtonDownEvent
0x22f1f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusButtonUpEvent
0x22f24  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f29  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f2e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewStylusButtonUpEvent
0x22f33  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::PreviewKeyDownEvent
0x22f38  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f3d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f42  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewKeyDownEvent
0x22f47  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::KeyDownEvent
0x22f4c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f51  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f56  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::KeyDownEvent
0x22f5b  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::PreviewKeyUpEvent
0x22f60  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f65  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f6a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewKeyUpEvent
0x22f6f  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::KeyUpEvent
0x22f74  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f79  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f7e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::KeyUpEvent
0x22f83  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::PreviewGotKeyboardFocusEvent
0x22f88  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22f8d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22f92  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewGotKeyboardFocusEvent
0x22f97  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::GotKeyboardFocusEvent
0x22f9c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22fa1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22fa6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::GotKeyboardFocusEvent
0x22fab  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::PreviewLostKeyboardFocusEvent
0x22fb0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22fb5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22fba  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewLostKeyboardFocusEvent
0x22fbf  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Keyboard::LostKeyboardFocusEvent
0x22fc4  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22fc9  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22fce  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::LostKeyboardFocusEvent
0x22fd3  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::PreviewTextInputEvent
0x22fd8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22fdd  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22fe2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewTextInputEvent
0x22fe7  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.TextCompositionManager::TextInputEvent
0x22fec  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x22ff1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x22ff6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::TextInputEvent
0x22ffb  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewQueryContinueDragEvent
0x23000  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23005  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x2300a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewQueryContinueDragEvent
0x2300f  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::QueryContinueDragEvent
0x23014  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23019  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x2301e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::QueryContinueDragEvent
0x23023  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewGiveFeedbackEvent
0x23028  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x2302d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x23032  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewGiveFeedbackEvent
0x23037  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::GiveFeedbackEvent
0x2303c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23041  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x23046  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::GiveFeedbackEvent
0x2304b  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragEnterEvent
0x23050  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23055  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x2305a  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewDragEnterEvent
0x2305f  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragEnterEvent
0x23064  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23069  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x2306e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::DragEnterEvent
0x23073  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragOverEvent
0x23078  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x2307d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x23082  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewDragOverEvent
0x23087  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragOverEvent
0x2308c  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23091  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x23096  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::DragOverEvent
0x2309b  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragLeaveEvent
0x230a0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x230a5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x230aa  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewDragLeaveEvent
0x230af  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragLeaveEvent
0x230b4  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x230b9  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x230be  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::DragLeaveEvent
0x230c3  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDropEvent
0x230c8  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x230cd  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x230d2  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewDropEvent
0x230d7  ldsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DropEvent
0x230dc  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x230e1  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x230e6  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::DropEvent
0x230eb  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::PreviewTouchDownEvent
0x230f0  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x230f5  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x230fa  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewTouchDownEvent
0x230ff  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchDownEvent
0x23104  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x23109  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x2310e  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::TouchDownEvent
0x23113  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::PreviewTouchMoveEvent
0x23118  ldsfld   class [mscorlib]System.Type System.Windows.UIElement::_typeofThis
0x2311d  callvirt instance class System.Windows.RoutedEvent System.Windows.RoutedEvent::AddOwner(class [mscorlib]System.Type ownerType)
0x23122  stsfld   class System.Windows.RoutedEvent System.Windows.UIElement::PreviewTouchMoveEvent
0x23127  ldsfld   class System.Windows.RoutedEvent System.Windows.Input.Touch::TouchMoveEvent
  ... truncated ...
```
