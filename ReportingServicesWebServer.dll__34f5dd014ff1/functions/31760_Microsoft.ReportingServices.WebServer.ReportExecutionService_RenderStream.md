# Microsoft.ReportingServices.WebServer.ReportExecutionService::RenderStream

- ea: `0x31760`
- end: `0x31799`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::RenderStream`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23f20`

## callees

- `0x31760`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31760`: `ReportExecutionService.RenderStream`

## pseudocode

```c

```

## disassembly

```asm
0x31760  ldstr    aReportexecutio_19// "ReportExecutionService.RenderStream"
0x31765  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3176a  stloc.0
0x3176b  ldarg.0
0x3176c  ldarg.0
0x3176d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31772  ldnull
0x31773  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31778  ldarg.0
0x31779  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3177e  ldarg.1
0x3177f  ldarg.2
0x31780  ldarg.3
0x31781  ldarg.s  4
0x31783  ldarg.s  5
0x31785  ldarg.s  6
0x31787  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::RenderStream(string, string, string, unsigned int8[]&, string&, string&)
0x3178c  leave.s  loc_31798
0x3178e  ldloc.0
0x3178f  brfalse.s loc_31797
0x31791  ldloc.0
0x31792  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31797  endfinally
0x31798  ret
```
