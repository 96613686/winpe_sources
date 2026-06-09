# Microsoft.ReportingServices.Library.QueuePollWorker::CreateHeartbeatTimer

- ea: `0x1f50`
- end: `0x1fcb`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::CreateHeartbeatTimer`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1dc0`

## callees

- `0x1130`
- `0x13e0`
- `0x1f50`
- `0x9190`

## pseudocode

```c

```

## disassembly

```asm
0x1f50  ldnull
0x1f51  stloc.0
0x1f52  ldarg.0
0x1f53  ldftn    instance void Microsoft.ReportingServices.Library.QueuePollWorker::<CreateHeartbeatTimer>b__54_0()
0x1f59  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1f5e  newobj   instance void ActionTimer::.ctor(class [mscorlib]System.Action action)
0x1f63  stloc.0
0x1f64  ldloc.0
0x1f65  ldc.i4.0
0x1f66  ldarg.0
0x1f67  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::get_HeartbeatInterval()
0x1f6c  stloc.1
0x1f6d  ldloca.s 1
0x1f6f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x1f74  call     int32 [mscorlib]System.Convert::ToInt32(float64)
0x1f79  ldarg.0
0x1f7a  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1f7f  ldstr    aHeartbeattimer// " HeartbeatTimer"
0x1f84  call     string [mscorlib]System.String::Concat(string, string)
0x1f89  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Start(int32, int32, string)
0x1f8e  leave.s  loc_1FC9
0x1f90  stloc.2
0x1f91  ldarg.0
0x1f92  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1f97  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1f9c  brfalse.s loc_1FC7
0x1f9e  ldarg.0
0x1f9f  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1fa4  ldc.i4.1
0x1fa5  ldstr    aErrorStarting0// "Error starting {0} heartbeat timer: {1}"
0x1faa  ldc.i4.2
0x1fab  newarr   [mscorlib]System.Object
0x1fb0  dup
0x1fb1  ldc.i4.0
0x1fb2  ldarg.0
0x1fb3  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1fb8  stelem.ref
0x1fb9  dup
0x1fba  ldc.i4.1
0x1fbb  ldloc.2
0x1fbc  callvirt instance string [mscorlib]System.Object::ToString()
0x1fc1  stelem.ref
0x1fc2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1fc7  leave.s  loc_1FC9
0x1fc9  ldloc.0
0x1fca  ret
```
