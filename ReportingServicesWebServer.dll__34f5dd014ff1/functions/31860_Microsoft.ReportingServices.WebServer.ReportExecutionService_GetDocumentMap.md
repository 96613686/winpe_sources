# Microsoft.ReportingServices.WebServer.ReportExecutionService::GetDocumentMap

- ea: `0x31860`
- end: `0x31891`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::GetDocumentMap`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x241b0`

## callees

- `0x31860`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31860`: `ReportExecutionService.GetDocumentMap`

## pseudocode

```c

```

## disassembly

```asm
0x31860  ldstr    aReportexecutio_23// "ReportExecutionService.GetDocumentMap"
0x31865  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3186a  stloc.0
0x3186b  ldarg.0
0x3186c  ldarg.0
0x3186d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31872  ldnull
0x31873  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31878  ldarg.0
0x31879  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3187e  ldarg.1
0x3187f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::GetDocumentMap(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DocumentMapNode&)
0x31884  leave.s  loc_31890
0x31886  ldloc.0
0x31887  brfalse.s loc_3188F
0x31889  ldloc.0
0x3188a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3188f  endfinally
0x31890  ret
```
