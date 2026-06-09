# Microsoft.ReportingServices.Library.DBPoll::.ctor

- ea: `0xa70`
- end: `0xaf1`
- name: `Microsoft.ReportingServices.Library.DBPoll::.ctor`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xa60`
- `0xa70`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.0
0xa71  ldc.i4.1
0xa72  stfld    bool Microsoft.ReportingServices.Library.DBPoll::m_continuePolling
0xa77  ldarg.0
0xa78  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0xa7d  stfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0xa82  ldarg.0
0xa83  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa88  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xa8d  ldarg.0
0xa8e  ldc.i4.0
0xa8f  ldc.i4.0
0xa90  ldc.i4.1
0xa91  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa96  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.DBPoll::m_pollInterval
0xa9b  ldarg.0
0xa9c  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0xaa1  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.DBPoll::m_maxNoPollActivity
0xaa6  ldarg.0
0xaa7  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xaac  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.DBPoll::m_pollTimeStamp
0xab1  ldarg.0
0xab2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xab7  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.DBPoll::m_lastCheckTimeStamp
0xabc  ldarg.0
0xabd  call     instance void [mscorlib]System.Object::.ctor()
0xac2  ldarg.0
0xac3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xac8  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.DBPoll::m_pollTimeStamp
0xacd  ldarg.0
0xace  ldc.i4.0
0xacf  ldc.i4.0
0xad0  call     int32 Microsoft.ReportingServices.Library.DBPoll::get_MaxInactivity()
0xad5  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xada  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.DBPoll::m_maxNoPollActivity
0xadf  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext Microsoft.ReportingServices.Library.DBPoll::m_serviceInstanceContext
0xae4  brtrue.s loc_AF0
0xae6  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ServiceInstanceContext()
0xaeb  stsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext Microsoft.ReportingServices.Library.DBPoll::m_serviceInstanceContext
0xaf0  ret
```
