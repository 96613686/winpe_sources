# Microsoft.ReportingServices.Library.QueuePollWorker::get_NumberOfItemsToRetrieve

- ea: `0x19b0`
- end: `0x1a43`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::get_NumberOfItemsToRetrieve`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2580`

## callees

- `0x19b0`
- `0x7a50`
- `0x7ab0`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldc.i4.0
0x19b1  stloc.0
0x19b2  ldarg.0
0x19b3  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x19b8  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x19bd  brtrue.s loc_19C7
0x19bf  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x19c4  stloc.0
0x19c5  br.s     loc_1A13
0x19c7  call     float64 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessCPUPercentage()
0x19cc  stloc.1
0x19cd  ldloc.1
0x19ce  ldc.r8   0.75
0x19d7  ble.un.s loc_19ED
0x19d9  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x19de  conv.r8
0x19df  ldc.r8   0.25
0x19e8  mul
0x19e9  conv.i4
0x19ea  stloc.0
0x19eb  br.s     loc_1A13
0x19ed  ldloc.1
0x19ee  ldc.r8   0.5
0x19f7  ble.un.s loc_1A0D
0x19f9  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x19fe  conv.r8
0x19ff  ldc.r8   0.5
0x1a08  mul
0x1a09  conv.i4
0x1a0a  stloc.0
0x1a0b  br.s     loc_1A13
0x1a0d  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x1a12  stloc.0
0x1a13  ldloc.0
0x1a14  ldarg.0
0x1a15  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1a1a  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x1a1f  add
0x1a20  ldarg.0
0x1a21  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x1a26  ble.s    loc_1A3B
0x1a28  ldarg.0
0x1a29  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x1a2e  ldarg.0
0x1a2f  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1a34  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x1a39  sub
0x1a3a  stloc.0
0x1a3b  ldloc.0
0x1a3c  ldc.i4.0
0x1a3d  bgt.s    loc_1A41
0x1a3f  ldc.i4.1
0x1a40  stloc.0
0x1a41  ldloc.0
0x1a42  ret
```
