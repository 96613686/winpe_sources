# Microsoft.ReportingServices.Library.EventQueueWorker::ProcessSingleEvent

- ea: `0x2420`
- end: `0x24f7`
- name: `Microsoft.ReportingServices.Library.EventQueueWorker::ProcessSingleEvent`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x2390`

## callees

- `0x2060`
- `0x2080`
- `0x2190`
- `0x2240`
- `0x2260`
- `0x2270`
- `0x2420`
- `0x2500`
- `0x25b0`

## pseudocode

```c

```

## disassembly

```asm
0x2420  newobj   instance void Microsoft.ReportingServices.Library.CatalogQuery::.ctor()
0x2425  stloc.0
0x2426  ldloc.0
0x2427  callvirt instance void Microsoft.ReportingServices.Library.CatalogQuery::WillClose()
0x242c  ldarg.1
0x242d  ldloc.0
0x242e  ldarg.2
0x242f  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventType
0x2434  ldarg.2
0x2435  ldfld    string Microsoft.ReportingServices.Library.EventQueueItem::EventData
0x243a  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventHandler::HandleEvent(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.ICatalogQuery, string, string)
0x243f  ldloc.0
0x2440  callvirt instance void Microsoft.ReportingServices.Library.CatalogQuery::Commit()
0x2445  leave.s  loc_2450
0x2447  pop
0x2448  ldloc.0
0x2449  callvirt instance void Microsoft.ReportingServices.Library.CatalogQuery::AbortTransaction()
0x244e  rethrow
0x2450  leave.s  loc_2459
0x2452  ldloc.0
0x2453  callvirt instance void Microsoft.ReportingServices.Library.CatalogQuery::Close()
0x2458  endfinally
0x2459  ldarg.0
0x245a  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver Microsoft.ReportingServices.Library.EventQueueWorker::get_EventResolver()
0x245f  brfalse.s loc_246C
0x2461  ldarg.0
0x2462  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver Microsoft.ReportingServices.Library.EventQueueWorker::get_EventResolver()
0x2467  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.IEventResolver::ItemPlacedInEventQueue()
0x246c  leave    loc_24F3
0x2471  isinst   [mscorlib]System.Exception
0x2476  dup
0x2477  brtrue.s loc_247D
0x2479  pop
0x247a  ldc.i4.0
0x247b  br.s     loc_2488
0x247d  stloc.1
0x247e  ldarg.0
0x247f  ldloc.1
0x2480  call     instance bool Microsoft.ReportingServices.Library.EventQueueWorker::IsDeadLockException(class [mscorlib]System.Exception ex)
0x2485  ldc.i4.0
0x2486  cgt.un
0x2488  endfilter
0x248a  pop
0x248b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x2490  ldc.i4.2
0x2491  ldstr    aDeadlockDetect// "Deadlock detected running event: {0}. E"...
0x2496  ldarg.2
0x2497  callvirt instance string Microsoft.ReportingServices.Library.QueueItem::ItemString()
0x249c  ldloc.1
0x249d  callvirt instance string [mscorlib]System.Object::ToString()
0x24a2  call     string [mscorlib]System.String::Format(string, object, object)
0x24a7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x24ac  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x24b1  ldstr    aErrorProcessin// "Error processing event with data: {0}. "...
0x24b6  ldarg.2
0x24b7  callvirt instance string Microsoft.ReportingServices.Library.QueueItem::ItemString()
0x24bc  ldloc.1
0x24bd  callvirt instance string [mscorlib]System.Object::ToString()
0x24c2  call     string [mscorlib]System.String::Format(string, object, object)
0x24c7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x24cc  ldc.i4.0
0x24cd  stloc.2
0x24ce  leave.s  loc_24F5
0x24d0  stloc.3
0x24d1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x24d6  ldstr    aErrorProcessin// "Error processing event with data: {0}. "...
0x24db  ldarg.2
0x24dc  callvirt instance string Microsoft.ReportingServices.Library.QueueItem::ItemString()
0x24e1  ldloc.3
0x24e2  callvirt instance string [mscorlib]System.Object::ToString()
0x24e7  call     string [mscorlib]System.String::Format(string, object, object)
0x24ec  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x24f1  leave.s  loc_24F3
0x24f3  ldc.i4.1
0x24f4  ret
0x24f5  ldloc.2
0x24f6  ret
```
