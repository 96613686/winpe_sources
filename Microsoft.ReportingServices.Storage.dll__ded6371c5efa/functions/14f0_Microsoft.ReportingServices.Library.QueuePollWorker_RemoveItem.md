# Microsoft.ReportingServices.Library.QueuePollWorker::RemoveItem

- ea: `0x14f0`
- end: `0x1524`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::RemoveItem`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1830`

## callees

- `0x14f0`
- `0x2020`

## pseudocode

```c

```

## disassembly

```asm
0x14f0  ldarg.0
0x14f1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x14f6  stloc.0
0x14f7  ldc.i4.0
0x14f8  stloc.1
0x14f9  ldloc.0
0x14fa  ldloca.s 1
0x14fc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1501  ldarg.0
0x1502  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1507  ldarg.1
0x1508  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x150d  box      [mscorlib]System.Guid
0x1512  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x1517  leave.s  loc_1523
0x1519  ldloc.1
0x151a  brfalse.s loc_1522
0x151c  ldloc.0
0x151d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1522  endfinally
0x1523  ret
```
