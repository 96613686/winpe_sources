# Microsoft.ReportingServices.WebServer.ReportExecutionService::ListRenderingExtensions

- ea: `0x31b80`
- end: `0x31bb1`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ListRenderingExtensions`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x24210`

## callees

- `0x31b80`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31b80`: `ReportExecutionService.ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x31b80  ldstr    aReportexecutio_35// "ReportExecutionService.ListRenderingExt"...
0x31b85  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31b8a  stloc.0
0x31b8b  ldarg.0
0x31b8c  ldarg.0
0x31b8d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31b92  ldnull
0x31b93  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31b98  ldarg.0
0x31b99  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31b9e  ldarg.1
0x31b9f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::ListRenderingExtensions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.Extension[]&)
0x31ba4  leave.s  loc_31BB0
0x31ba6  ldloc.0
0x31ba7  brfalse.s loc_31BAF
0x31ba9  ldloc.0
0x31baa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31baf  endfinally
0x31bb0  ret
```
