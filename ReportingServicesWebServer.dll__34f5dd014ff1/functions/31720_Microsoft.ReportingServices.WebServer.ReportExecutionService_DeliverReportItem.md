# Microsoft.ReportingServices.WebServer.ReportExecutionService::DeliverReportItem

- ea: `0x31720`
- end: `0x31759`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::DeliverReportItem`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x23f40`

## callees

- `0x31720`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31720`: `ReportExecutionService.DeliverReportItem`

## pseudocode

```c

```

## disassembly

```asm
0x31720  ldstr    aReportexecutio_18// "ReportExecutionService.DeliverReportIte"...
0x31725  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3172a  stloc.0
0x3172b  ldarg.0
0x3172c  ldarg.0
0x3172d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31732  ldnull
0x31733  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31738  ldarg.0
0x31739  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3173e  ldarg.1
0x3173f  ldarg.2
0x31740  ldarg.3
0x31741  ldarg.s  4
0x31743  ldarg.s  5
0x31745  ldarg.s  6
0x31747  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::DeliverReportItem(string, string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExtensionSettings, string, string, string)
0x3174c  leave.s  loc_31758
0x3174e  ldloc.0
0x3174f  brfalse.s loc_31757
0x31751  ldloc.0
0x31752  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31757  endfinally
0x31758  ret
```
