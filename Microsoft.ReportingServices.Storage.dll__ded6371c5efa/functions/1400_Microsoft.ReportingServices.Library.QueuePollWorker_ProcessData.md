# Microsoft.ReportingServices.Library.QueuePollWorker::ProcessData

- ea: `0x1400`
- end: `0x14b0`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::ProcessData`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1130`
- `0x1400`
- `0x14b0`
- `0x1560`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x1400  ldc.i4.0
0x1401  stloc.0
0x1402  br.s     loc_1435
0x1404  ldloc.0
0x1405  ldc.i4.1
0x1406  add
0x1407  stloc.0
0x1408  ldarg.0
0x1409  ldarg.1
0x140a  callvirt instance class Microsoft.ReportingServices.Library.QueueItem Microsoft.ReportingServices.Library.QueuePollWorker::GetNextQueueItem(class [System.Data]System.Data.IDataRecord record)
0x140f  stloc.1
0x1410  ldloc.1
0x1411  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1416  callvirt instance void Microsoft.ReportingServices.Library.QueueItem::set_TimeEntered(valuetype [mscorlib]System.DateTime value)
0x141b  ldarg.0
0x141c  ldloc.1
0x141d  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::AddCurrentItem(class Microsoft.ReportingServices.Library.QueueItem item)
0x1422  ldarg.0
0x1423  ldftn    instance void Microsoft.ReportingServices.Library.QueuePollWorker::WorkItemStart(object state)
0x1429  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x142e  ldloc.1
0x142f  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0x1434  pop
0x1435  ldarg.1
0x1436  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x143b  brtrue.s loc_1404
0x143d  ldloc.0
0x143e  ldc.i4.0
0x143f  ble.s    loc_1492
0x1441  ldarg.0
0x1442  ldc.i4.1
0x1443  stfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_workLastPoll
0x1448  ldarg.0
0x1449  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x144e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1453  brfalse.s loc_14A4
0x1455  ldarg.0
0x1456  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x145b  ldstr    a0Processing1Mo// "{0} processing {1} more items. {2} Tota"...
0x1460  ldc.i4.3
0x1461  newarr   [mscorlib]System.Object
0x1466  dup
0x1467  ldc.i4.0
0x1468  ldarg.0
0x1469  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x146e  stelem.ref
0x146f  dup
0x1470  ldc.i4.1
0x1471  ldloc.0
0x1472  box      [mscorlib]System.Int32
0x1477  stelem.ref
0x1478  dup
0x1479  ldc.i4.2
0x147a  ldarg.0
0x147b  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1480  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x1485  box      [mscorlib]System.Int32
0x148a  stelem.ref
0x148b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1490  br.s     loc_14A4
0x1492  ldarg.0
0x1493  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1498  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastEmptyPoll
0x149d  ldarg.0
0x149e  ldc.i4.0
0x149f  stfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_workLastPoll
0x14a4  ldarg.0
0x14a5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x14aa  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastPoll
0x14af  ret
```
