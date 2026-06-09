# Microsoft.ReportingServices.Library.QueuePollWorker::HeartbeatTimerAction

- ea: `0x1e10`
- end: `0x1e91`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::HeartbeatTimerAction`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fe0`

## callees

- `0x10e0`
- `0x1130`
- `0x13e0`
- `0x1550`
- `0x1590`
- `0x1e10`

## pseudocode

```c

```

## disassembly

```asm
0x1e10  ldarg.0
0x1e11  call     instance bool Microsoft.ReportingServices.Library.PollWorker::get_ContinueWorking()
0x1e16  brtrue.s loc_1E19
0x1e18  ret
0x1e19  nop
0x1e1a  ldarg.0
0x1e1b  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::SetHeartbeat()
0x1e20  ldarg.0
0x1e21  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatIterations
0x1e26  ldc.i4.3
0x1e27  rem
0x1e28  brtrue.s loc_1E47
0x1e2a  ldarg.0
0x1e2b  ldarg.0
0x1e2c  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::get_HeartbeatInterval()
0x1e31  stloc.0
0x1e32  ldloca.s 0
0x1e34  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0x1e39  ldc.i4.3
0x1e3a  mul
0x1e3b  callvirt instance void Microsoft.ReportingServices.Library.QueuePollWorker::CleanInactiveRows(int32 minutes)
0x1e40  ldarg.0
0x1e41  ldc.i4.0
0x1e42  stfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatIterations
0x1e47  ldarg.0
0x1e48  ldarg.0
0x1e49  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatIterations
0x1e4e  ldc.i4.1
0x1e4f  add
0x1e50  stfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatIterations
0x1e55  leave.s  loc_1E90
0x1e57  stloc.1
0x1e58  ldarg.0
0x1e59  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1e5e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1e63  brfalse.s loc_1E8E
0x1e65  ldarg.0
0x1e66  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1e6b  ldc.i4.1
0x1e6c  ldstr    aExceptionInHea// "Exception in HeartbeatTimerAction({0}):"...
0x1e71  ldc.i4.2
0x1e72  newarr   [mscorlib]System.Object
0x1e77  dup
0x1e78  ldc.i4.0
0x1e79  ldarg.0
0x1e7a  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1e7f  stelem.ref
0x1e80  dup
0x1e81  ldc.i4.1
0x1e82  ldloc.1
0x1e83  callvirt instance string [mscorlib]System.Object::ToString()
0x1e88  stelem.ref
0x1e89  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1e8e  leave.s  loc_1E90
0x1e90  ret
```
