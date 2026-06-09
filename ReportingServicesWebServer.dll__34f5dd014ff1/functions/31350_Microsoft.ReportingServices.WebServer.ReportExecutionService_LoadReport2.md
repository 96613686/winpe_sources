# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport2

- ea: `0x31350`
- end: `0x31393`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport2`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31350`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31350`: `ReportExecutionService.LoadReport2`

## pseudocode

```c

```

## disassembly

```asm
0x31350  ldstr    aReportexecutio_6// "ReportExecutionService.LoadReport2"
0x31355  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3135a  stloc.0
0x3135b  ldarg.1
0x3135c  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::GetParentPathForSharePoint(string)
0x31361  stloc.2
0x31362  ldarg.0
0x31363  ldarg.0
0x31364  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31369  ldloc.2
0x3136a  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x3136f  ldarg.0
0x31370  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31375  ldarg.1
0x31376  ldarg.2
0x31377  ldloca.s 1
0x31379  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReport(string, string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x3137e  ldarg.3
0x3137f  ldloc.1
0x31380  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x31385  stind.ref
0x31386  leave.s  loc_31392
0x31388  ldloc.0
0x31389  brfalse.s loc_31391
0x3138b  ldloc.0
0x3138c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31391  endfinally
0x31392  ret
```
