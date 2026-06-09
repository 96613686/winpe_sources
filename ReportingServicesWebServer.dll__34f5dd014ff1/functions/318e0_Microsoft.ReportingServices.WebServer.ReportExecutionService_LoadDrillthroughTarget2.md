# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget2

- ea: `0x318e0`
- end: `0x3191b`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget2`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x318e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x318e0`: `ReportExecutionService.LoadDrillthroughTarget2`

## pseudocode

```c

```

## disassembly

```asm
0x318e0  ldstr    aReportexecutio_25// "ReportExecutionService.LoadDrillthrough"...
0x318e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x318ea  stloc.0
0x318eb  ldarg.0
0x318ec  ldarg.0
0x318ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x318f2  ldnull
0x318f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x318f8  ldarg.0
0x318f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x318fe  ldarg.1
0x318ff  ldloca.s 1
0x31901  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadDrillthroughTarget(string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31906  ldarg.2
0x31907  ldloc.1
0x31908  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x3190d  stind.ref
0x3190e  leave.s  loc_3191A
0x31910  ldloc.0
0x31911  brfalse.s loc_31919
0x31913  ldloc.0
0x31914  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31919  endfinally
0x3191a  ret
```
