# System.Windows.Input.Stylus::.cctor

- ea: `0x45f80`
- end: `0x46351`
- name: `System.Windows.Input.Stylus::.cctor`
- size: `977`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1cce0`

## string_xrefs

- `0x46010`: `PreviewStylusMove`
- `0x46034`: `StylusMove`
- `0x46058`: `PreviewStylusInAirMove`
- `0x4607c`: `StylusInAirMove`

## pseudocode

```c

```

## disassembly

```asm
0x45f80  ldstr    aPreviewstylusd// "PreviewStylusDown"
0x45f85  ldc.i4.0
0x45f86  ldtoken  System.Windows.Input.StylusDownEventHandler
0x45f8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45f90  ldtoken  System.Windows.Input.Stylus
0x45f95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45f9a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x45f9f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusDownEvent
0x45fa4  ldstr    aStylusdown// "StylusDown"
0x45fa9  ldc.i4.1
0x45faa  ldtoken  System.Windows.Input.StylusDownEventHandler
0x45faf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45fb4  ldtoken  System.Windows.Input.Stylus
0x45fb9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45fbe  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x45fc3  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusDownEvent
0x45fc8  ldstr    aPreviewstylusu// "PreviewStylusUp"
0x45fcd  ldc.i4.0
0x45fce  ldtoken  System.Windows.Input.StylusEventHandler
0x45fd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45fd8  ldtoken  System.Windows.Input.Stylus
0x45fdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45fe2  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x45fe7  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusUpEvent
0x45fec  ldstr    aStylusup// "StylusUp"
0x45ff1  ldc.i4.1
0x45ff2  ldtoken  System.Windows.Input.StylusEventHandler
0x45ff7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45ffc  ldtoken  System.Windows.Input.Stylus
0x46001  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46006  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4600b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusUpEvent
0x46010  ldstr    aPreviewstylusm// "PreviewStylusMove"
0x46015  ldc.i4.0
0x46016  ldtoken  System.Windows.Input.StylusEventHandler
0x4601b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46020  ldtoken  System.Windows.Input.Stylus
0x46025  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4602a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4602f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusMoveEvent
0x46034  ldstr    aStylusmove// "StylusMove"
0x46039  ldc.i4.1
0x4603a  ldtoken  System.Windows.Input.StylusEventHandler
0x4603f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46044  ldtoken  System.Windows.Input.Stylus
0x46049  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4604e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46053  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusMoveEvent
0x46058  ldstr    aPreviewstylusi// "PreviewStylusInAirMove"
0x4605d  ldc.i4.0
0x4605e  ldtoken  System.Windows.Input.StylusEventHandler
0x46063  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46068  ldtoken  System.Windows.Input.Stylus
0x4606d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46072  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46077  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusInAirMoveEvent
0x4607c  ldstr    aStylusinairmov// "StylusInAirMove"
0x46081  ldc.i4.1
0x46082  ldtoken  System.Windows.Input.StylusEventHandler
0x46087  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4608c  ldtoken  System.Windows.Input.Stylus
0x46091  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46096  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4609b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusInAirMoveEvent
0x460a0  ldstr    aStylusenter// "StylusEnter"
0x460a5  ldc.i4.2
0x460a6  ldtoken  System.Windows.Input.StylusEventHandler
0x460ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x460b0  ldtoken  System.Windows.Input.Stylus
0x460b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x460ba  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x460bf  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusEnterEvent
0x460c4  ldstr    aStylusleave// "StylusLeave"
0x460c9  ldc.i4.2
0x460ca  ldtoken  System.Windows.Input.StylusEventHandler
0x460cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x460d4  ldtoken  System.Windows.Input.Stylus
0x460d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x460de  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x460e3  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusLeaveEvent
0x460e8  ldstr    aPreviewstylusi_0// "PreviewStylusInRange"
0x460ed  ldc.i4.0
0x460ee  ldtoken  System.Windows.Input.StylusEventHandler
0x460f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x460f8  ldtoken  System.Windows.Input.Stylus
0x460fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46102  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46107  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusInRangeEvent
0x4610c  ldstr    aStylusinrange// "StylusInRange"
0x46111  ldc.i4.1
0x46112  ldtoken  System.Windows.Input.StylusEventHandler
0x46117  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4611c  ldtoken  System.Windows.Input.Stylus
0x46121  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46126  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4612b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusInRangeEvent
0x46130  ldstr    aPreviewstyluso// "PreviewStylusOutOfRange"
0x46135  ldc.i4.0
0x46136  ldtoken  System.Windows.Input.StylusEventHandler
0x4613b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46140  ldtoken  System.Windows.Input.Stylus
0x46145  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4614a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4614f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusOutOfRangeEvent
0x46154  ldstr    aStylusoutofran// "StylusOutOfRange"
0x46159  ldc.i4.1
0x4615a  ldtoken  System.Windows.Input.StylusEventHandler
0x4615f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46164  ldtoken  System.Windows.Input.Stylus
0x46169  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4616e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46173  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusOutOfRangeEvent
0x46178  ldstr    aPreviewstyluss// "PreviewStylusSystemGesture"
0x4617d  ldc.i4.0
0x4617e  ldtoken  System.Windows.Input.StylusSystemGestureEventHandler
0x46183  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46188  ldtoken  System.Windows.Input.Stylus
0x4618d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46192  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46197  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusSystemGestureEvent
0x4619c  ldstr    aStylussystemge// "StylusSystemGesture"
0x461a1  ldc.i4.1
0x461a2  ldtoken  System.Windows.Input.StylusSystemGestureEventHandler
0x461a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461ac  ldtoken  System.Windows.Input.Stylus
0x461b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461b6  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x461bb  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusSystemGestureEvent
0x461c0  ldstr    aGotstyluscaptu// "GotStylusCapture"
0x461c5  ldc.i4.1
0x461c6  ldtoken  System.Windows.Input.StylusEventHandler
0x461cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461d0  ldtoken  System.Windows.Input.Stylus
0x461d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461da  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x461df  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::GotStylusCaptureEvent
0x461e4  ldstr    aLoststyluscapt// "LostStylusCapture"
0x461e9  ldc.i4.1
0x461ea  ldtoken  System.Windows.Input.StylusEventHandler
0x461ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461f4  ldtoken  System.Windows.Input.Stylus
0x461f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x461fe  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46203  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::LostStylusCaptureEvent
0x46208  ldstr    aStylusbuttondo// "StylusButtonDown"
0x4620d  ldc.i4.1
0x4620e  ldtoken  System.Windows.Input.StylusButtonEventHandler
0x46213  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46218  ldtoken  System.Windows.Input.Stylus
0x4621d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46222  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46227  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusButtonDownEvent
0x4622c  ldstr    aStylusbuttonup// "StylusButtonUp"
0x46231  ldc.i4.1
0x46232  ldtoken  System.Windows.Input.StylusButtonEventHandler
0x46237  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4623c  ldtoken  System.Windows.Input.Stylus
0x46241  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46246  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4624b  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::StylusButtonUpEvent
0x46250  ldstr    aPreviewstylusb// "PreviewStylusButtonDown"
0x46255  ldc.i4.0
0x46256  ldtoken  System.Windows.Input.StylusButtonEventHandler
0x4625b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46260  ldtoken  System.Windows.Input.Stylus
0x46265  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4626a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x4626f  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusButtonDownEvent
0x46274  ldstr    aPreviewstylusb_0// "PreviewStylusButtonUp"
0x46279  ldc.i4.0
0x4627a  ldtoken  System.Windows.Input.StylusButtonEventHandler
0x4627f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46284  ldtoken  System.Windows.Input.Stylus
0x46289  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4628e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x46293  stsfld   class System.Windows.RoutedEvent System.Windows.Input.Stylus::PreviewStylusButtonUpEvent
0x46298  ldstr    aIspressandhold// "IsPressAndHoldEnabled"
0x4629d  ldtoken  [mscorlib]System.Boolean
0x462a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462a7  ldtoken  System.Windows.Input.Stylus
0x462ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462b1  ldc.i4.1
0x462b2  box      [mscorlib]System.Boolean
0x462b7  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x462bc  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x462c1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.Stylus::IsPressAndHoldEnabledProperty
0x462c6  ldstr    aIsflicksenable// "IsFlicksEnabled"
0x462cb  ldtoken  [mscorlib]System.Boolean
0x462d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462d5  ldtoken  System.Windows.Input.Stylus
0x462da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462df  ldc.i4.1
0x462e0  box      [mscorlib]System.Boolean
0x462e5  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x462ea  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x462ef  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.Stylus::IsFlicksEnabledProperty
0x462f4  ldstr    aIstapfeedbacke// "IsTapFeedbackEnabled"
0x462f9  ldtoken  [mscorlib]System.Boolean
0x462fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46303  ldtoken  System.Windows.Input.Stylus
0x46308  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4630d  ldc.i4.1
0x4630e  box      [mscorlib]System.Boolean
0x46313  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x46318  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x4631d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.Stylus::IsTapFeedbackEnabledProperty
0x46322  ldstr    aIstouchfeedbac// "IsTouchFeedbackEnabled"
0x46327  ldtoken  [mscorlib]System.Boolean
0x4632c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46331  ldtoken  System.Windows.Input.Stylus
0x46336  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4633b  ldc.i4.1
0x4633c  box      [mscorlib]System.Boolean
0x46341  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x46346  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x4634b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.Stylus::IsTouchFeedbackEnabledProperty
0x46350  ret
```
