# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport

- ea: `0x312c0`
- end: `0x31303`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReport`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x312c0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x312c0`: `ReportExecutionService.LoadReport`

## pseudocode

```c

```

## disassembly

```asm
0x312c0  ldstr    aReportexecutio_4// "ReportExecutionService.LoadReport"
0x312c5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x312ca  stloc.0
0x312cb  ldarg.1
0x312cc  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::GetParentPathForSharePoint(string)
0x312d1  stloc.2
0x312d2  ldarg.0
0x312d3  ldarg.0
0x312d4  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x312d9  ldloc.2
0x312da  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x312df  ldarg.0
0x312e0  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x312e5  ldarg.1
0x312e6  ldarg.2
0x312e7  ldloca.s 1
0x312e9  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReport(string, string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x312ee  ldarg.3
0x312ef  ldloc.1
0x312f0  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x312f5  stind.ref
0x312f6  leave.s  loc_31302
0x312f8  ldloc.0
0x312f9  brfalse.s loc_31301
0x312fb  ldloc.0
0x312fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31301  endfinally
0x31302  ret
```
