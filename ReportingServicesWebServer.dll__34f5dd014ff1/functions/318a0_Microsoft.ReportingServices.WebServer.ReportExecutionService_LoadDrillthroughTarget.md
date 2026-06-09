# Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget

- ea: `0x318a0`
- end: `0x318db`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::LoadDrillthroughTarget`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x318a0`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x318a0`: `ReportExecutionService.LoadDrillthroughTarget`

## pseudocode

```c

```

## disassembly

```asm
0x318a0  ldstr    aReportexecutio_24// "ReportExecutionService.LoadDrillthrough"...
0x318a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x318aa  stloc.0
0x318ab  ldarg.0
0x318ac  ldarg.0
0x318ad  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x318b2  ldnull
0x318b3  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x318b8  ldarg.0
0x318b9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x318be  ldarg.1
0x318bf  ldloca.s 1
0x318c1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::LoadDrillthroughTarget(string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x318c6  ldarg.2
0x318c7  ldloc.1
0x318c8  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::ConvertFromExecutionInfo2(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo2)
0x318cd  stind.ref
0x318ce  leave.s  loc_318DA
0x318d0  ldloc.0
0x318d1  brfalse.s loc_318D9
0x318d3  ldloc.0
0x318d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x318d9  endfinally
0x318da  ret
```
