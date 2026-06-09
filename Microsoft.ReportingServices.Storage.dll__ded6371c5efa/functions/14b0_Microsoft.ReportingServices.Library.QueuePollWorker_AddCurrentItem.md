# Microsoft.ReportingServices.Library.QueuePollWorker::AddCurrentItem

- ea: `0x14b0`
- end: `0x14e5`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::AddCurrentItem`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400`

## callees

- `0x14b0`
- `0x2020`

## pseudocode

```c

```

## disassembly

```asm
0x14b0  ldarg.0
0x14b1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x14b6  stloc.0
0x14b7  ldc.i4.0
0x14b8  stloc.1
0x14b9  ldloc.0
0x14ba  ldloca.s 1
0x14bc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x14c1  ldarg.0
0x14c2  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x14c7  ldarg.1
0x14c8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x14cd  box      [mscorlib]System.Guid
0x14d2  ldarg.1
0x14d3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x14d8  leave.s  loc_14E4
0x14da  ldloc.1
0x14db  brfalse.s loc_14E3
0x14dd  ldloc.0
0x14de  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x14e3  endfinally
0x14e4  ret
```
