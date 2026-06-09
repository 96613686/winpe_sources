# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials2

- ea: `0x314a0`
- end: `0x314db`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionCredentials2`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x314a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x314a0`: `ReportExecutionService.SetExecutionCredentials2`

## pseudocode

```c

```

## disassembly

```asm
0x314a0  ldstr    aReportexecutio_10// "ReportExecutionService.SetExecutionCred"...
0x314a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x314aa  stloc.0
0x314ab  ldarg.0
0x314ac  ldarg.0
0x314ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x314b2  ldnull
0x314b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x314b8  ldarg.0
0x314b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x314be  ldarg.1
0x314bf  ldloca.s 1
0x314c1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionCredentials(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.DataSourceCredentials[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x314c6  ldarg.2
0x314c7  ldloc.1
0x314c8  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x314cd  stind.ref
0x314ce  leave.s  loc_314DA
0x314d0  ldloc.0
0x314d1  brfalse.s loc_314D9
0x314d3  ldloc.0
0x314d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x314d9  endfinally
0x314da  ret
```
