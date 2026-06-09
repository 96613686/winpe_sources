# Microsoft.ReportingServices.Library.ConnectionManager::InitEncryption

- ea: `0x33e0`
- end: `0x3418`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::InitEncryption`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3360`
- `0x33a0`

## callees

- `0x33e0`
- `0x80e0`

## pseudocode

```c

```

## disassembly

```asm
0x33e0  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_IsInitialized()
0x33e5  brfalse.s loc_33E8
0x33e7  ret
0x33e8  newobj   instance void Microsoft.ReportingServices.Library.UpgradeMutex::.ctor()
0x33ed  stloc.0
0x33ee  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x33f3  ldc.i4.s 0x6B
0x33f5  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::ResetWriteOnceEvent(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event)
0x33fa  ldarg.0
0x33fb  ldftn    instance void Microsoft.ReportingServices.Library.ConnectionManager::<InitEncryption>b__56_0()
0x3401  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0x3406  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0x340b  leave.s  loc_3417
0x340d  ldloc.0
0x340e  brfalse.s loc_3416
0x3410  ldloc.0
0x3411  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3416  endfinally
0x3417  ret
```
