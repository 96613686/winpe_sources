# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials3

- ea: `0x314e0`
- end: `0x31512`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials3`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23cf0`
- `0x23d30`

## callees

- `0x314e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x314e0`: `ReportExecutionService.SetExecutionCredentials3`

## pseudocode

```c

```

## disassembly

```asm
0x314e0  ldstr    aReportexecutio_11// "ReportExecutionService.SetExecutionCred"...
0x314e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x314ea  stloc.0
0x314eb  ldarg.0
0x314ec  ldarg.0
0x314ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x314f2  ldnull
0x314f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x314f8  ldarg.0
0x314f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x314fe  ldarg.1
0x314ff  ldarg.2
0x31500  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionCredentials(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.DataSourceCredentials[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31505  leave.s  loc_31511
0x31507  ldloc.0
0x31508  brfalse.s loc_31510
0x3150a  ldloc.0
0x3150b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31510  endfinally
0x31511  ret
```
