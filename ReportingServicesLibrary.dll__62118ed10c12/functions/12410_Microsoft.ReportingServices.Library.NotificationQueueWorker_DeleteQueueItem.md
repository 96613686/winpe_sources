# Microsoft.ReportingServices.Library.NotificationQueueWorker::DeleteQueueItem

- ea: `0x12410`
- end: `0x12486`
- name: `Microsoft.ReportingServices.Library.NotificationQueueWorker::DeleteQueueItem`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x12410`
- `0x12490`

## string_xrefs

- `0x12426`: `@Attempt`
- `0x12472`: `SetNotificationAttempt`

## pseudocode

```c

```

## disassembly

```asm
0x12410  ldarg.1
0x12411  castclass Microsoft.ReportingServices.Library.NotificationQueueItem
0x12416  stloc.0
0x12417  ldloc.0
0x12418  ldfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteItem
0x1241d  brtrue.s loc_1247E
0x1241f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x12424  stloc.1
0x12425  ldloc.1
0x12426  ldstr    aAttempt// "@Attempt"
0x1242b  ldloc.0
0x1242c  ldfld    class Microsoft.ReportingServices.Library.NotificationImpl Microsoft.ReportingServices.Library.NotificationQueueItem::Notification
0x12431  ldfld    int32 Microsoft.ReportingServices.Library.NotificationImpl::m_attempt
0x12436  box      [mscorlib]System.Int32
0x1243b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x12440  ldloc.1
0x12441  ldstr    aSecondstoadd// "@SecondsToAdd"
0x12446  ldloc.0
0x12447  ldfld    int32 Microsoft.ReportingServices.Library.NotificationQueueItem::SecondsBeforeRetry
0x1244c  box      [mscorlib]System.Int32
0x12451  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x12456  ldloc.1
0x12457  ldstr    aNotificationid_0// "@NotificationID"
0x1245c  ldloc.0
0x1245d  ldfld    class Microsoft.ReportingServices.Library.NotificationImpl Microsoft.ReportingServices.Library.NotificationQueueItem::Notification
0x12462  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_NotificationID
0x12467  box      [mscorlib]System.Guid
0x1246c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x12471  ldarg.0
0x12472  ldstr    aSetnotificatio// "SetNotificationAttempt"
0x12477  ldloc.1
0x12478  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::ExecuteStoredProcedure(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1247d  ret
0x1247e  ldarg.0
0x1247f  ldloc.0
0x12480  call     instance void Microsoft.ReportingServices.Library.NotificationQueueWorker::DeleteNotification(class Microsoft.ReportingServices.Library.NotificationQueueItem item)
0x12485  ret
```
