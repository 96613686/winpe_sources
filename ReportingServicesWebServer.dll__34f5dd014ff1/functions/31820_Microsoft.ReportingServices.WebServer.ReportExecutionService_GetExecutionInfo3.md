# Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo3

- ea: `0x31820`
- end: `0x31851`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo3`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23e50`
- `0x24590`

## callees

- `0x31820`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31820`: `ReportExecutionService.GetExecutionInfo3`

## pseudocode

```c

```

## disassembly

```asm
0x31820  ldstr    aReportexecutio_22// "ReportExecutionService.GetExecutionInfo"...
0x31825  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3182a  stloc.0
0x3182b  ldarg.0
0x3182c  ldarg.0
0x3182d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31832  ldnull
0x31833  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31838  ldarg.0
0x31839  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3183e  ldarg.1
0x3183f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::GetExecutionInfo(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31844  leave.s  loc_31850
0x31846  ldloc.0
0x31847  brfalse.s loc_3184F
0x31849  ldloc.0
0x3184a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3184f  endfinally
0x31850  ret
```
