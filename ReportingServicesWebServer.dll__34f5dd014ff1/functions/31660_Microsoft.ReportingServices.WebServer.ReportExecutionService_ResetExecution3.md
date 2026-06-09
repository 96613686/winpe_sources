# Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution3

- ea: `0x31660`
- end: `0x31691`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution3`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24270`

## callees

- `0x31660`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31660`: `ReportExecutionService.ResetExecution2`

## pseudocode

```c

```

## disassembly

```asm
0x31660  ldstr    aReportexecutio_15// "ReportExecutionService.ResetExecution2"
0x31665  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3166a  stloc.0
0x3166b  ldarg.0
0x3166c  ldarg.0
0x3166d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31672  ldnull
0x31673  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31678  ldarg.0
0x31679  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3167e  ldarg.1
0x3167f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::ResetExecution(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31684  leave.s  loc_31690
0x31686  ldloc.0
0x31687  brfalse.s loc_3168F
0x31689  ldloc.0
0x3168a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3168f  endfinally
0x31690  ret
```
