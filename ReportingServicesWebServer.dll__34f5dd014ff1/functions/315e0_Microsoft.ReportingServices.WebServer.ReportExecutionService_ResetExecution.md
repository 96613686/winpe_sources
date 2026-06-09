# Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution

- ea: `0x315e0`
- end: `0x3161a`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x315e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x315e0`: `ReportExecutionService.ResetExecution`

## pseudocode

```c

```

## disassembly

```asm
0x315e0  ldstr    aReportexecutio_14// "ReportExecutionService.ResetExecution"
0x315e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x315ea  stloc.0
0x315eb  ldarg.0
0x315ec  ldarg.0
0x315ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x315f2  ldnull
0x315f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x315f8  ldarg.0
0x315f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x315fe  ldloca.s 1
0x31600  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::ResetExecution(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31605  ldarg.1
0x31606  ldloc.1
0x31607  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x3160c  stind.ref
0x3160d  leave.s  loc_31619
0x3160f  ldloc.0
0x31610  brfalse.s loc_31618
0x31612  ldloc.0
0x31613  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31618  endfinally
0x31619  ret
```
