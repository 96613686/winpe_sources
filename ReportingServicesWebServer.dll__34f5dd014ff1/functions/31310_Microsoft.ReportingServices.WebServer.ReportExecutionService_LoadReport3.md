# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport3

- ea: `0x31310`
- end: `0x3134a`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport3`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24590`

## callees

- `0x31310`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31310`: `ReportExecutionService.LoadReport3`

## pseudocode

```c

```

## disassembly

```asm
0x31310  ldstr    aReportexecutio_5// "ReportExecutionService.LoadReport3"
0x31315  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3131a  stloc.0
0x3131b  ldarg.1
0x3131c  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::GetParentPathForSharePoint(string)
0x31321  stloc.1
0x31322  ldarg.0
0x31323  ldarg.0
0x31324  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31329  ldloc.1
0x3132a  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x3132f  ldarg.0
0x31330  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31335  ldarg.1
0x31336  ldarg.2
0x31337  ldarg.3
0x31338  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReport(string, string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x3133d  leave.s  loc_31349
0x3133f  ldloc.0
0x31340  brfalse.s loc_31348
0x31342  ldloc.0
0x31343  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31348  endfinally
0x31349  ret
```
