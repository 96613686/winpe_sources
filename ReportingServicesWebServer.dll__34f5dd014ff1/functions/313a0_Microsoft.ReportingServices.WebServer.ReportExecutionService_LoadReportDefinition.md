# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition

- ea: `0x313a0`
- end: `0x313dc`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadReportDefinition`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x313a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x313a0`: `ReportExecutionService.LoadReportDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x313a0  ldstr    aReportexecutio_7// "ReportExecutionService.LoadReportDefini"...
0x313a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x313aa  stloc.0
0x313ab  ldarg.0
0x313ac  ldarg.0
0x313ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x313b2  ldnull
0x313b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x313b8  ldarg.0
0x313b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x313be  ldarg.1
0x313bf  ldloca.s 1
0x313c1  ldarg.3
0x313c2  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadReportDefinition(unsigned int8[], class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Warning[]&)
0x313c7  ldarg.2
0x313c8  ldloc.1
0x313c9  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x313ce  stind.ref
0x313cf  leave.s  loc_313DB
0x313d1  ldloc.0
0x313d2  brfalse.s loc_313DA
0x313d4  ldloc.0
0x313d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x313da  endfinally
0x313db  ret
```
