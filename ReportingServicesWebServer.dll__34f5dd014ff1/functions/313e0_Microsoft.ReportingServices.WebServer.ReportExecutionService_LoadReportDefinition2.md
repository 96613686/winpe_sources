# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition2

- ea: `0x313e0`
- end: `0x3141c`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition2`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x313e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x313e0`: `ReportExecutionService.LoadReportDefinition2`

## pseudocode

```c

```

## disassembly

```asm
0x313e0  ldstr    aReportexecutio_8// "ReportExecutionService.LoadReportDefini"...
0x313e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x313ea  stloc.0
0x313eb  ldarg.0
0x313ec  ldarg.0
0x313ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x313f2  ldnull
0x313f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x313f8  ldarg.0
0x313f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x313fe  ldarg.1
0x313ff  ldloca.s 1
0x31401  ldarg.3
0x31402  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReportDefinition(unsigned int8[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Warning[]&)
0x31407  ldarg.2
0x31408  ldloc.1
0x31409  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x3140e  stind.ref
0x3140f  leave.s  loc_3141B
0x31411  ldloc.0
0x31412  brfalse.s loc_3141A
0x31414  ldloc.0
0x31415  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3141a  endfinally
0x3141b  ret
```
