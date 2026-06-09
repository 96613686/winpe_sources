# Microsoft.ReportingServices.WebServer.ReportExecutionService::FindString

- ea: `0x31a20`
- end: `0x31a55`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::FindString`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23ff0`

## callees

- `0x31a20`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31a20`: `ReportExecutionService.FindString`

## pseudocode

```c

```

## disassembly

```asm
0x31a20  ldstr    aReportexecutio_30// "ReportExecutionService.FindString"
0x31a25  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31a2a  stloc.0
0x31a2b  ldarg.0
0x31a2c  ldarg.0
0x31a2d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31a32  ldnull
0x31a33  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31a38  ldarg.0
0x31a39  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31a3e  ldarg.1
0x31a3f  ldarg.2
0x31a40  ldarg.3
0x31a41  ldarg.s  4
0x31a43  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::FindString(int32, int32, string, int32&)
0x31a48  leave.s  loc_31A54
0x31a4a  ldloc.0
0x31a4b  brfalse.s loc_31A53
0x31a4d  ldloc.0
0x31a4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31a53  endfinally
0x31a54  ret
```
