# Microsoft.ReportingServices.Library.EventQueueWorker::QueueWorker

- ea: `0x2390`
- end: `0x2415`
- name: `Microsoft.ReportingServices.Library.EventQueueWorker::QueueWorker`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2060`
- `0x2390`
- `0x2420`
- `0x25b0`

## string_xrefs

- `0x23f1`: `No extension defined for event {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2390  ldarg.1
0x2391  castclass Microsoft.ReportingServices.Library.EventQueueItem
0x2396  stloc.0
0x2397  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x239c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x23a1  brfalse.s loc_23C1
0x23a3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x23a8  ldstr    aHandlingEventW// "Handling event with data: {0}."
0x23ad  ldc.i4.1
0x23ae  newarr   [mscorlib]System.Object
0x23b3  dup
0x23b4  ldc.i4.0
0x23b5  ldloc.0
0x23b6  callvirt instance string Microsoft.ReportingServices.Library.QueueItem::ItemString()
0x23bb  stelem.ref
0x23bc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x23c1  ldnull
0x23c2  stloc.1
0x23c3  ldarg.0
0x23c4  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver Microsoft.ReportingServices.Library.EventQueueWorker::get_EventResolver()
0x23c9  brfalse.s loc_23DD
0x23cb  ldarg.0
0x23cc  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver Microsoft.ReportingServices.Library.EventQueueWorker::get_EventResolver()
0x23d1  ldloc.0
0x23d2  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x23d7  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventHandler [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver::ResolveEvent(string)
0x23dc  stloc.1
0x23dd  ldloc.1
0x23de  brtrue.s loc_240C
0x23e0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x23e5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x23ea  brfalse.s loc_240A
0x23ec  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x23f1  ldstr    aNoExtensionDef// "No extension defined for event {0}"
0x23f6  ldc.i4.1
0x23f7  newarr   [mscorlib]System.Object
0x23fc  dup
0x23fd  ldc.i4.0
0x23fe  ldloc.0
0x23ff  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x2404  stelem.ref
0x2405  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x240a  ldc.i4.1
0x240b  ret
0x240c  ldarg.0
0x240d  ldloc.1
0x240e  ldloc.0
0x240f  call     instance bool Microsoft.ReportingServices.Library.EventQueueWorker::ProcessSingleEvent(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventHandler eventHandler, class Microsoft.ReportingServices.Library.EventQueueItem item)
0x2414  ret
```
