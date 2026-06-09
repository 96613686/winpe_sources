# Microsoft.ReportingServices.WebServer.ReportExecutionService::ToggleItem

- ea: `0x31960`
- end: `0x31992`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ToggleItem`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x24020`

## callees

- `0x31960`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31960`: `ReportExecutionService.ToggleItem`

## pseudocode

```c

```

## disassembly

```asm
0x31960  ldstr    aReportexecutio_27// "ReportExecutionService.ToggleItem"
0x31965  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3196a  stloc.0
0x3196b  ldarg.0
0x3196c  ldarg.0
0x3196d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31972  ldnull
0x31973  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31978  ldarg.0
0x31979  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3197e  ldarg.1
0x3197f  ldarg.2
0x31980  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::ToggleItem(string, bool&)
0x31985  leave.s  loc_31991
0x31987  ldloc.0
0x31988  brfalse.s loc_31990
0x3198a  ldloc.0
0x3198b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31990  endfinally
0x31991  ret
```
