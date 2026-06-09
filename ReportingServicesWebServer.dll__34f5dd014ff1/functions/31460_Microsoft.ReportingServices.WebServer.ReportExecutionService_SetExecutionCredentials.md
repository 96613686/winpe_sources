# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials

- ea: `0x31460`
- end: `0x3149b`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31460`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31460`: `ReportExecutionService.SetExecutionCredentials`

## pseudocode

```c

```

## disassembly

```asm
0x31460  ldstr    aReportexecutio_9// "ReportExecutionService.SetExecutionCred"...
0x31465  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3146a  stloc.0
0x3146b  ldarg.0
0x3146c  ldarg.0
0x3146d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31472  ldnull
0x31473  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31478  ldarg.0
0x31479  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3147e  ldarg.1
0x3147f  ldloca.s 1
0x31481  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionCredentials(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.DataSourceCredentials[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31486  ldarg.2
0x31487  ldloc.1
0x31488  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x3148d  stind.ref
0x3148e  leave.s  loc_3149A
0x31490  ldloc.0
0x31491  brfalse.s loc_31499
0x31493  ldloc.0
0x31494  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31499  endfinally
0x3149a  ret
```
