# Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo2

- ea: `0x317e0`
- end: `0x3181a`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::GetExecutionInfo2`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x317e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x317e0`: `ReportExecutionService.GetExecutionInfo2`

## pseudocode

```c

```

## disassembly

```asm
0x317e0  ldstr    aReportexecutio_21// "ReportExecutionService.GetExecutionInfo"...
0x317e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x317ea  stloc.0
0x317eb  ldarg.0
0x317ec  ldarg.0
0x317ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x317f2  ldnull
0x317f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x317f8  ldarg.0
0x317f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x317fe  ldloca.s 1
0x31800  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::GetExecutionInfo(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31805  ldarg.1
0x31806  ldloc.1
0x31807  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x3180c  stind.ref
0x3180d  leave.s  loc_31819
0x3180f  ldloc.0
0x31810  brfalse.s loc_31818
0x31812  ldloc.0
0x31813  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31818  endfinally
0x31819  ret
```
