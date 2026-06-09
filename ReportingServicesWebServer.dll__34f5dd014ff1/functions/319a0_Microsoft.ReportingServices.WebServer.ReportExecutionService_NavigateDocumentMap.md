# Microsoft.ReportingServices.WebServer.ReportExecutionService::NavigateDocumentMap

- ea: `0x319a0`
- end: `0x319d2`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::NavigateDocumentMap`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24080`

## callees

- `0x319a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x319a0`: `ReportExecutionService.NavigateDocumentMap`

## pseudocode

```c

```

## disassembly

```asm
0x319a0  ldstr    aReportexecutio_28// "ReportExecutionService.NavigateDocument"...
0x319a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x319aa  stloc.0
0x319ab  ldarg.0
0x319ac  ldarg.0
0x319ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x319b2  ldnull
0x319b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x319b8  ldarg.0
0x319b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x319be  ldarg.1
0x319bf  ldarg.2
0x319c0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::NavigateDocumentMap(string, int32&)
0x319c5  leave.s  loc_319D1
0x319c7  ldloc.0
0x319c8  brfalse.s loc_319D0
0x319ca  ldloc.0
0x319cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x319d0  endfinally
0x319d1  ret
```
