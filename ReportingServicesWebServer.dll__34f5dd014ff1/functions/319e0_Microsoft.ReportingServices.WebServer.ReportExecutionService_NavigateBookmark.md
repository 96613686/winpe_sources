# Microsoft.ReportingServices.WebServer.ReportExecutionService::NavigateBookmark

- ea: `0x319e0`
- end: `0x31a13`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::NavigateBookmark`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24050`

## callees

- `0x319e0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x319e0`: `ReportExecutionService.NavigateBookmark`

## pseudocode

```c

```

## disassembly

```asm
0x319e0  ldstr    aReportexecutio_29// "ReportExecutionService.NavigateBookmark"
0x319e5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x319ea  stloc.0
0x319eb  ldarg.0
0x319ec  ldarg.0
0x319ed  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x319f2  ldnull
0x319f3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x319f8  ldarg.0
0x319f9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x319fe  ldarg.1
0x319ff  ldarg.2
0x31a00  ldarg.3
0x31a01  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::NavigateBookmark(string, int32&, string&)
0x31a06  leave.s  loc_31A12
0x31a08  ldloc.0
0x31a09  brfalse.s loc_31A11
0x31a0b  ldloc.0
0x31a0c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31a11  endfinally
0x31a12  ret
```
