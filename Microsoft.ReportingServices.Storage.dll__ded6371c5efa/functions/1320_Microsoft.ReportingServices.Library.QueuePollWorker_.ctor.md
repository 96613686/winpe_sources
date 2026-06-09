# Microsoft.ReportingServices.Library.QueuePollWorker::.ctor

- ea: `0x1320`
- end: `0x13d5`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::.ctor`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x22e0`
- `0x22f0`

## callees

- `0x10c0`
- `0x1320`
- `0x7a50`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1326  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x132b  ldarg.0
0x132c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1331  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastEmptyPoll
0x1336  ldarg.0
0x1337  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x133c  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastPoll
0x1341  ldarg.0
0x1342  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x1347  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_pollInterval
0x134c  ldarg.0
0x134d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1352  stfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1357  ldarg.0
0x1358  ldc.i4.0
0x1359  ldc.i4.5
0x135a  ldc.i4.0
0x135b  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x1360  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatInterval
0x1365  ldarg.0
0x1366  ldc.i4.0
0x1367  ldc.i4.0
0x1368  ldc.i4.3
0x1369  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x136e  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_successInterval
0x1373  ldarg.0
0x1374  ldc.i4.0
0x1375  ldc.i4.s 0x1E
0x1377  ldc.i4.0
0x1378  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x137d  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_fullQueueStateInterval
0x1382  ldarg.0
0x1383  ldc.i4.0
0x1384  ldc.i4.1
0x1385  ldc.i4.0
0x1386  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x138b  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_fullQueueTraceInterval
0x1390  ldarg.0
0x1391  call     instance void Microsoft.ReportingServices.Library.PollWorker::.ctor()
0x1396  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x139b  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_PollingInterval()
0x13a0  stloc.0
0x13a1  ldarg.0
0x13a2  ldc.i4.0
0x13a3  ldc.i4.0
0x13a4  ldloc.0
0x13a5  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x13aa  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_pollInterval
0x13af  ldarg.0
0x13b0  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13b5  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_MaxQueueThreads()
0x13ba  stfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x13bf  ldarg.0
0x13c0  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x13c5  brtrue.s loc_13D4
0x13c7  ldarg.0
0x13c8  ldc.i4.2
0x13c9  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x13ce  mul
0x13cf  stfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x13d4  ret
```
