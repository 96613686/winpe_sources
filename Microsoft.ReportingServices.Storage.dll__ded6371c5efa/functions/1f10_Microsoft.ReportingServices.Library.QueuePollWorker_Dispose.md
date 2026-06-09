# Microsoft.ReportingServices.Library.QueuePollWorker::Dispose

- ea: `0x1f10`
- end: `0x1f43`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::Dispose`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1300`
- `0x1ea0`
- `0x1f00`

## callees

- `0x1f10`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_disposed
0x1f16  brtrue.s loc_1F42
0x1f18  ldarg.1
0x1f19  brfalse.s loc_1F21
0x1f1b  ldarg.0
0x1f1c  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x1f21  ldarg.0
0x1f22  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatTimer
0x1f27  brfalse.s loc_1F3B
0x1f29  ldarg.0
0x1f2a  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatTimer
0x1f2f  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase::Stop()
0x1f34  ldarg.0
0x1f35  ldnull
0x1f36  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.TimerActionBase Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatTimer
0x1f3b  ldarg.0
0x1f3c  ldc.i4.1
0x1f3d  stfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_disposed
0x1f42  ret
```
