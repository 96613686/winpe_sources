# Microsoft.ReportingServices.WebServer.ReportExecutionService::Render2

- ea: `0x316e0`
- end: `0x3171f`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Render2`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x316e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x316e0`: `ReportExecutionService.Render2`

## pseudocode

```c

```

## disassembly

```asm
0x316e0  ldstr    aReportexecutio_17// "ReportExecutionService.Render2"
0x316e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x316ea  stloc.0
0x316eb  ldarg.0
0x316ec  ldarg.0
0x316ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x316f2  ldnull
0x316f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x316f8  ldarg.0
0x316f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x316fe  ldarg.1
0x316ff  ldarg.2
0x31700  ldarg.3
0x31701  ldarg.s  4
0x31703  ldarg.s  5
0x31705  ldarg.s  6
0x31707  ldarg.s  7
0x31709  ldarg.s  8
0x3170b  ldarg.s  9
0x3170d  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::Render(string, string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.PageCountMode, unsigned int8[]&, string&, string&, string&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Warning[]&, string[]&)
0x31712  leave.s  loc_3171E
0x31714  ldloc.0
0x31715  brfalse.s loc_3171D
0x31717  ldloc.0
0x31718  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3171d  endfinally
0x3171e  ret
```
