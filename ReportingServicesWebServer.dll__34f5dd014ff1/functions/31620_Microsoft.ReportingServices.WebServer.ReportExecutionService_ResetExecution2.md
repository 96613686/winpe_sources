# Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution2

- ea: `0x31620`
- end: `0x3165a`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::ResetExecution2`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31620`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31620`: `ReportExecutionService.ResetExecution`

## pseudocode

```c

```

## disassembly

```asm
0x31620  ldstr    aReportexecutio_14// "ReportExecutionService.ResetExecution"
0x31625  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3162a  stloc.0
0x3162b  ldarg.0
0x3162c  ldarg.0
0x3162d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31632  ldnull
0x31633  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31638  ldarg.0
0x31639  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x3163e  ldloca.s 1
0x31640  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::ResetExecution(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31645  ldarg.1
0x31646  ldloc.1
0x31647  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2::ConvertFromExecutionInfo3(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3)
0x3164c  stind.ref
0x3164d  leave.s  loc_31659
0x3164f  ldloc.0
0x31650  brfalse.s loc_31658
0x31652  ldloc.0
0x31653  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31658  endfinally
0x31659  ret
```
