# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget3

- ea: `0x31920`
- end: `0x31952`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget3`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x240b0`

## callees

- `0x31920`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31920`: `ReportExecutionService.LoadDrillthroughTarget3`

## pseudocode

```c

```

## disassembly

```asm
0x31920  ldstr    aReportexecutio_26// "ReportExecutionService.LoadDrillthrough"...
0x31925  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3192a  stloc.0
0x3192b  ldarg.0
0x3192c  ldarg.0
0x3192d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31932  ldnull
0x31933  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31938  ldarg.0
0x31939  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3193e  ldarg.1
0x3193f  ldarg.2
0x31940  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadDrillthroughTarget(string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31945  leave.s  loc_31951
0x31947  ldloc.0
0x31948  brfalse.s loc_31950
0x3194a  ldloc.0
0x3194b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31950  endfinally
0x31951  ret
```
