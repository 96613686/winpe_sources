# Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo

- ea: `0x317a0`
- end: `0x317da`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24140`

## callees

- `0x317a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x317a0`: `ReportExecutionService.GetExecutionInfo`

## pseudocode

```c

```

## disassembly

```asm
0x317a0  ldstr    aReportexecutio_20// "ReportExecutionService.GetExecutionInfo"
0x317a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x317aa  stloc.0
0x317ab  ldarg.0
0x317ac  ldarg.0
0x317ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x317b2  ldnull
0x317b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x317b8  ldarg.0
0x317b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x317be  ldloca.s 1
0x317c0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::GetExecutionInfo(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x317c5  ldarg.1
0x317c6  ldloc.1
0x317c7  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x317cc  stind.ref
0x317cd  leave.s  loc_317D9
0x317cf  ldloc.0
0x317d0  brfalse.s loc_317D8
0x317d2  ldloc.0
0x317d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x317d8  endfinally
0x317d9  ret
```
