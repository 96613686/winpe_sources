# Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters2

- ea: `0x31560`
- end: `0x3159c`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::SetExecutionParameters2`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31560`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31560`: `ReportExecutionService.SetExecutionParameters`

## pseudocode

```c

```

## disassembly

```asm
0x31560  ldstr    aReportexecutio_12// "ReportExecutionService.SetExecutionPara"...
0x31565  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3156a  stloc.0
0x3156b  ldarg.0
0x3156c  ldarg.0
0x3156d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31572  ldnull
0x31573  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31578  ldarg.0
0x31579  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3157e  ldarg.1
0x3157f  ldarg.2
0x31580  ldloca.s 1
0x31582  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::SetExecutionParameters(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue[], string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31587  ldarg.3
0x31588  ldloc.1
0x31589  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x3158e  stind.ref
0x3158f  leave.s  loc_3159B
0x31591  ldloc.0
0x31592  brfalse.s loc_3159A
0x31594  ldloc.0
0x31595  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3159a  endfinally
0x3159b  ret
```
