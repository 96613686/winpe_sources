# Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort

- ea: `0x31a60`
- end: `0x31aac`
- name: `Microsoft.ReportingServices.WebServer.ReportExecutionService::Sort`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31a60`
- `0x31ca0`
- `0x31d60`

## string_xrefs

- `0x31a60`: `ReportExecutionService.Sort`

## pseudocode

```c

```

## disassembly

```asm
0x31a60  ldstr    aReportexecutio_31// "ReportExecutionService.Sort"
0x31a65  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31a6a  stloc.0
0x31a6b  ldarg.0
0x31a6c  ldarg.0
0x31a6d  call     instance class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.ReportExecutionService::get_TrustedUserHeaderValue()
0x31a72  ldnull
0x31a73  call     instance void Microsoft.ReportingServices.WebServer.ReportExecutionService::Initialize(class Microsoft.ReportingServices.WebServer.TrustedUserHeader userHeader, string item)
0x31a78  ldarg.0
0x31a79  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl Microsoft.ReportingServices.WebServer.ReportExecutionService::m_impl
0x31a7e  ldarg.1
0x31a7f  ldarg.2
0x31a80  ldarg.3
0x31a81  ldc.i4.0
0x31a82  ldarg.s  4
0x31a84  ldarg.s  5
0x31a86  ldloca.s 1
0x31a88  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ReportExecution2005Impl::Sort(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.SortDirectionEnum, bool, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.PageCountMode, int32&, string&, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3&)
0x31a8d  ldloc.1
0x31a8e  brfalse.s loc_31A9B
0x31a90  ldarg.s  6
0x31a92  ldloc.1
0x31a93  ldfld    int32 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::NumPages
0x31a98  stind.i4
0x31a99  leave.s  loc_31AAB
0x31a9b  ldarg.s  6
0x31a9d  ldc.i4.0
0x31a9e  stind.i4
0x31a9f  leave.s  loc_31AAB
0x31aa1  ldloc.0
0x31aa2  brfalse.s loc_31AAA
0x31aa4  ldloc.0
0x31aa5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31aaa  endfinally
0x31aab  ret
```
