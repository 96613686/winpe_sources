# System.Windows.DragDrop::.cctor

- ea: `0x1b750`
- end: `0x1b949`
- name: `System.Windows.DragDrop::.cctor`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cce0`

## string_xrefs

- `0x1b7e0`: `PreviewDragEnter`
- `0x1b804`: `DragEnter`
- `0x1b924`: `DragDropCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x1b750  ldstr    aPreviewqueryco// "PreviewQueryContinueDrag"
0x1b755  ldc.i4.0
0x1b756  ldtoken  System.Windows.QueryContinueDragEventHandler
0x1b75b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b760  ldtoken  System.Windows.DragDrop
0x1b765  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b76a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b76f  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewQueryContinueDragEvent
0x1b774  ldstr    aQuerycontinued// "QueryContinueDrag"
0x1b779  ldc.i4.1
0x1b77a  ldtoken  System.Windows.QueryContinueDragEventHandler
0x1b77f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b784  ldtoken  System.Windows.DragDrop
0x1b789  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b78e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b793  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::QueryContinueDragEvent
0x1b798  ldstr    aPreviewgivefee// "PreviewGiveFeedback"
0x1b79d  ldc.i4.0
0x1b79e  ldtoken  System.Windows.GiveFeedbackEventHandler
0x1b7a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7a8  ldtoken  System.Windows.DragDrop
0x1b7ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7b2  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b7b7  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewGiveFeedbackEvent
0x1b7bc  ldstr    aGivefeedback// "GiveFeedback"
0x1b7c1  ldc.i4.1
0x1b7c2  ldtoken  System.Windows.GiveFeedbackEventHandler
0x1b7c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7cc  ldtoken  System.Windows.DragDrop
0x1b7d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7d6  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b7db  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::GiveFeedbackEvent
0x1b7e0  ldstr    aPreviewdragent// "PreviewDragEnter"
0x1b7e5  ldc.i4.0
0x1b7e6  ldtoken  System.Windows.DragEventHandler
0x1b7eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7f0  ldtoken  System.Windows.DragDrop
0x1b7f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7fa  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b7ff  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragEnterEvent
0x1b804  ldstr    aDragenter// "DragEnter"
0x1b809  ldc.i4.1
0x1b80a  ldtoken  System.Windows.DragEventHandler
0x1b80f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b814  ldtoken  System.Windows.DragDrop
0x1b819  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b81e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b823  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragEnterEvent
0x1b828  ldstr    aPreviewdragove// "PreviewDragOver"
0x1b82d  ldc.i4.0
0x1b82e  ldtoken  System.Windows.DragEventHandler
0x1b833  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b838  ldtoken  System.Windows.DragDrop
0x1b83d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b842  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b847  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragOverEvent
0x1b84c  ldstr    aDragover// "DragOver"
0x1b851  ldc.i4.1
0x1b852  ldtoken  System.Windows.DragEventHandler
0x1b857  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b85c  ldtoken  System.Windows.DragDrop
0x1b861  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b866  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b86b  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragOverEvent
0x1b870  ldstr    aPreviewdraglea// "PreviewDragLeave"
0x1b875  ldc.i4.0
0x1b876  ldtoken  System.Windows.DragEventHandler
0x1b87b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b880  ldtoken  System.Windows.DragDrop
0x1b885  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b88a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b88f  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDragLeaveEvent
0x1b894  ldstr    aDragleave// "DragLeave"
0x1b899  ldc.i4.1
0x1b89a  ldtoken  System.Windows.DragEventHandler
0x1b89f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8a4  ldtoken  System.Windows.DragDrop
0x1b8a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8ae  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b8b3  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragLeaveEvent
0x1b8b8  ldstr    aPreviewdrop// "PreviewDrop"
0x1b8bd  ldc.i4.0
0x1b8be  ldtoken  System.Windows.DragEventHandler
0x1b8c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8c8  ldtoken  System.Windows.DragDrop
0x1b8cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8d2  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b8d7  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::PreviewDropEvent
0x1b8dc  ldstr    aDrop// "Drop"
0x1b8e1  ldc.i4.1
0x1b8e2  ldtoken  System.Windows.DragEventHandler
0x1b8e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8ec  ldtoken  System.Windows.DragDrop
0x1b8f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b8f6  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b8fb  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DropEvent
0x1b900  ldstr    aDragdropstarte// "DragDropStarted"
0x1b905  ldc.i4.1
0x1b906  ldtoken  System.Windows.RoutedEventHandler
0x1b90b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b910  ldtoken  System.Windows.DragDrop
0x1b915  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b91a  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b91f  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragDropStartedEvent
0x1b924  ldstr    aDragdropcomple// "DragDropCompleted"
0x1b929  ldc.i4.1
0x1b92a  ldtoken  System.Windows.RoutedEventHandler
0x1b92f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b934  ldtoken  System.Windows.DragDrop
0x1b939  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b93e  call     class System.Windows.RoutedEvent System.Windows.EventManager::RegisterRoutedEvent(string name, valuetype System.Windows.RoutingStrategy routingStrategy, class [mscorlib]System.Type handlerType, class [mscorlib]System.Type ownerType)
0x1b943  stsfld   class System.Windows.RoutedEvent System.Windows.DragDrop::DragDropCompletedEvent
0x1b948  ret
```
