# Microsoft.ReportingServices.Library.EventQueueWorker::DeleteQueueItem

- ea: `0x2550`
- end: `0x2579`
- name: `Microsoft.ReportingServices.Library.EventQueueWorker::DeleteQueueItem`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1230`
- `0x2020`

## string_xrefs

- `0x256d`: `DeleteEvent`

## pseudocode

```c

```

## disassembly

```asm
0x2550  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2555  stloc.0
0x2556  ldloc.0
0x2557  ldstr    aId// "@ID"
0x255c  ldarg.1
0x255d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x2562  box      [mscorlib]System.Guid
0x2567  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x256c  ldarg.0
0x256d  ldstr    aDeleteevent// "DeleteEvent"
0x2572  ldloc.0
0x2573  call     instance void Microsoft.ReportingServices.Library.PollWorker::ExecuteStoredProcedure(string spName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> spParameterBag)
0x2578  ret
```
