# Microsoft.ReportingServices.WebServer.ReportExecutionService::GetRenderResource

- ea: `0x31b40`
- end: `0x31b75`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::GetRenderResource`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31b40`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31b40`: `ReportExecutionService.GetRenderResource`

## pseudocode

```c

```

## disassembly

```asm
0x31b40  ldstr    aReportexecutio_34// "ReportExecutionService.GetRenderResourc"...
0x31b45  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31b4a  stloc.0
0x31b4b  ldarg.0
0x31b4c  ldarg.0
0x31b4d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31b52  ldnull
0x31b53  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31b58  ldarg.0
0x31b59  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31b5e  ldarg.1
0x31b5f  ldarg.2
0x31b60  ldarg.3
0x31b61  ldarg.s  4
0x31b63  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::GetRenderResource(string, string, unsigned int8[]&, string&)
0x31b68  leave.s  loc_31B74
0x31b6a  ldloc.0
0x31b6b  brfalse.s loc_31B73
0x31b6d  ldloc.0
0x31b6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31b73  endfinally
0x31b74  ret
```
