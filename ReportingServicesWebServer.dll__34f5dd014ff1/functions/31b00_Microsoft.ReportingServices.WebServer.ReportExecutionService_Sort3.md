# Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort3

- ea: `0x31b00`
- end: `0x31b3f`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort3`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x240f0`

## callees

- `0x31b00`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31b00`: `ReportExecutionService.Sort3`

## pseudocode

```c

```

## disassembly

```asm
0x31b00  ldstr    aReportexecutio_33// "ReportExecutionService.Sort3"
0x31b05  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31b0a  stloc.0
0x31b0b  ldarg.0
0x31b0c  ldarg.0
0x31b0d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31b12  ldnull
0x31b13  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31b18  ldarg.0
0x31b19  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31b1e  ldarg.1
0x31b1f  ldarg.2
0x31b20  ldarg.3
0x31b21  ldarg.s  4
0x31b23  ldarg.s  5
0x31b25  ldarg.s  6
0x31b27  ldloca.s 1
0x31b29  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::Sort(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.SortDirectionEnum, bool, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.PageCountMode, int32&, string&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31b2e  ldarg.s  7
0x31b30  ldloc.1
0x31b31  stind.ref
0x31b32  leave.s  loc_31B3E
0x31b34  ldloc.0
0x31b35  brfalse.s loc_31B3D
0x31b37  ldloc.0
0x31b38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31b3d  endfinally
0x31b3e  ret
```
