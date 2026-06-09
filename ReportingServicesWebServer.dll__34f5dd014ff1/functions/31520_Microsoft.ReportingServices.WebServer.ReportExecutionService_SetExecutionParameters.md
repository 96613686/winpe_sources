# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters

- ea: `0x31520`
- end: `0x3155c`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31520`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31520`: `ReportExecutionService.SetExecutionParameters`

## pseudocode

```c

```

## disassembly

```asm
0x31520  ldstr    aReportexecutio_12// "ReportExecutionService.SetExecutionPara"...
0x31525  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3152a  stloc.0
0x3152b  ldarg.0
0x3152c  ldarg.0
0x3152d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31532  ldnull
0x31533  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31538  ldarg.0
0x31539  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3153e  ldarg.1
0x3153f  ldarg.2
0x31540  ldloca.s 1
0x31542  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionParameters(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue[], string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31547  ldarg.3
0x31548  ldloc.1
0x31549  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x3154e  stind.ref
0x3154f  leave.s  loc_3155B
0x31551  ldloc.0
0x31552  brfalse.s loc_3155A
0x31554  ldloc.0
0x31555  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3155a  endfinally
0x3155b  ret
```
