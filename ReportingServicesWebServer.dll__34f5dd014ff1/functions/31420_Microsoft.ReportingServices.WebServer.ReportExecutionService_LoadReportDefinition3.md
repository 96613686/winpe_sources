# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition3

- ea: `0x31420`
- end: `0x31453`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition3`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31420`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31420`: `ReportExecutionService.LoadReportDefinition2`

## pseudocode

```c

```

## disassembly

```asm
0x31420  ldstr    aReportexecutio_8// "ReportExecutionService.LoadReportDefini"...
0x31425  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3142a  stloc.0
0x3142b  ldarg.0
0x3142c  ldarg.0
0x3142d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31432  ldnull
0x31433  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31438  ldarg.0
0x31439  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3143e  ldarg.1
0x3143f  ldarg.2
0x31440  ldarg.3
0x31441  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReportDefinition(unsigned int8[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Warning[]&)
0x31446  leave.s  loc_31452
0x31448  ldloc.0
0x31449  brfalse.s loc_31451
0x3144b  ldloc.0
0x3144c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31451  endfinally
0x31452  ret
```
