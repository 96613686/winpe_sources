# Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort2

- ea: `0x31ab0`
- end: `0x31af4`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort2`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31ab0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31ab0`: `ReportExecutionService.Sort2`

## pseudocode

```c

```

## disassembly

```asm
0x31ab0  ldstr    aReportexecutio_32// "ReportExecutionService.Sort2"
0x31ab5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31aba  stloc.0
0x31abb  ldarg.0
0x31abc  ldarg.0
0x31abd  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31ac2  ldnull
0x31ac3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31ac8  ldarg.0
0x31ac9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31ace  ldarg.1
0x31acf  ldarg.2
0x31ad0  ldarg.3
0x31ad1  ldarg.s  4
0x31ad3  ldarg.s  5
0x31ad5  ldarg.s  6
0x31ad7  ldloca.s 1
0x31ad9  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::Sort(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.SortDirectionEnum, bool, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.PageCountMode, int32&, string&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31ade  ldarg.s  7
0x31ae0  ldloc.1
0x31ae1  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x31ae6  stind.ref
0x31ae7  leave.s  loc_31AF3
0x31ae9  ldloc.0
0x31aea  brfalse.s loc_31AF2
0x31aec  ldloc.0
0x31aed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31af2  endfinally
0x31af3  ret
```
