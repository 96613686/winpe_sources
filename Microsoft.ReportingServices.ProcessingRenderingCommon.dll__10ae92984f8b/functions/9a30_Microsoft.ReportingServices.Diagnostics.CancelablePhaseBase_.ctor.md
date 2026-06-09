# Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::.ctor

- ea: `0x9a30`
- end: `0x9a8c`
- name: `Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::.ctor`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xa960`
- `0xd3d0`
- `0xd700`
- `0xd7b0`
- `0xd970`
- `0x101d0`
- `0x10200`
- `0x15b90`

## pseudocode

```c

```

## disassembly

```asm
0x9a30  ldarg.0
0x9a31  call     instance void [mscorlib]System.Object::.ctor()
0x9a36  ldarg.0
0x9a37  call     class Microsoft.ReportingServices.Diagnostics.RunningJobList Microsoft.ReportingServices.Diagnostics.RunningJobList::get_Current()
0x9a3c  ldarg.1
0x9a3d  ldarg.2
0x9a3e  ldarg.3
0x9a3f  ldarg.s  4
0x9a41  ldarg.s  5
0x9a43  call     class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x9a48  callvirt instance class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.RunningJobList::AddJob(string jobId, class Microsoft.ReportingServices.Diagnostics.ExternalItemPath requestPath, valuetype Microsoft.ReportingServices.Diagnostics.JobActionEnum action, class Microsoft.ReportingServices.Diagnostics.JobType type, class Microsoft.ReportingServices.Diagnostics.UserContext userContext, class Microsoft.ReportingServices.Diagnostics.RequestContext optionalCtx)
0x9a4d  stfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_jobCtx
0x9a52  ldarg.0
0x9a53  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_jobCtx
0x9a58  callvirt instance class Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_ExecutionInfo()
0x9a5d  ldarg.s  6
0x9a5f  callvirt instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_ExecutionLogLevel(valuetype Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel value)
0x9a64  ldarg.0
0x9a65  ldarg.0
0x9a66  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_jobCtx
0x9a6b  callvirt instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_InitialAndOnlyThreadCtx()
0x9a70  stfld    class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_crtThreadCtx
0x9a75  ldarg.0
0x9a76  ldflda   valuetype PreservedContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_preservedContext
0x9a7b  call     instance void PreservedContext::Capture()
0x9a80  ldarg.0
0x9a81  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_jobCtx
0x9a86  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::set_JobContext(class Microsoft.ReportingServices.Diagnostics.RunningJobContext value)
0x9a8b  ret
```
