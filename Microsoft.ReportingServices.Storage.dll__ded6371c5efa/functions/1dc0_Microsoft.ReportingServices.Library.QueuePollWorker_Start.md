# Microsoft.ReportingServices.Library.QueuePollWorker::Start

- ea: `0x1dc0`
- end: `0x1e04`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::Start`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1150`
- `0x1dc0`
- `0x1f50`

## pseudocode

```c

```

## disassembly

```asm
0x1dc0  ldarg.0
0x1dc1  call     instance void Microsoft.ReportingServices.Library.PollWorker::Start()
0x1dc6  ldarg.0
0x1dc7  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatTimer
0x1dcc  brfalse.s loc_1DCF
0x1dce  ret
0x1dcf  ldarg.0
0x1dd0  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1dd5  stloc.0
0x1dd6  ldc.i4.0
0x1dd7  stloc.1
0x1dd8  ldloc.0
0x1dd9  ldloca.s 1
0x1ddb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1de0  ldarg.0
0x1de1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1de6  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x1deb  leave.s  loc_1DF7
0x1ded  ldloc.1
0x1dee  brfalse.s loc_1DF6
0x1df0  ldloc.0
0x1df1  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1df6  endfinally
0x1df7  ldarg.0
0x1df8  ldarg.0
0x1df9  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::CreateHeartbeatTimer()
0x1dfe  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatTimer
0x1e03  ret
```
