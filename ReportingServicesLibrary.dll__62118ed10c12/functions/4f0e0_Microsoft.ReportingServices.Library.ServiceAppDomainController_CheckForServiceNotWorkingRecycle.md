# Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForServiceNotWorkingRecycle

- ea: `0x4f0e0`
- end: `0x4f144`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForServiceNotWorkingRecycle`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f3b0`

## callees

- `0x4d370`
- `0x4df60`
- `0x4f0e0`

## string_xrefs

- `0x4f10e`: `Recycling app domain because Windows Service AppDomain is not active.`
- `0x4f139`: `Polling thread is not working but will not be recycled because we are under a debugger`

## pseudocode

```c

```

## disassembly

```asm
0x4f0e0  ldarg.0
0x4f0e1  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4f0e6  brfalse.s loc_4F143
0x4f0e8  ldarg.0
0x4f0e9  call     instance class Microsoft.ReportingServices.Library.IServiceAppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::get_WorkerDomainProxy()
0x4f0ee  callvirt instance bool Microsoft.ReportingServices.Library.IServiceAppDomain::get_IsServiceWorking()
0x4f0f3  brtrue.s loc_4F143
0x4f0f5  call     bool [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer::IsDebuggerAttached()
0x4f0fa  brtrue.s loc_4F127
0x4f0fc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f101  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f106  brfalse.s loc_4F118
0x4f108  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f10d  ldc.i4.3
0x4f10e  ldstr    aRecyclingAppDo// "Recycling app domain because Windows Se"...
0x4f113  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f118  ldarg.1
0x4f119  ldc.i4.1
0x4f11a  stfld    bool Recycle::cycleWindowsServiceAppDomain
0x4f11f  ldarg.1
0x4f120  ldc.i4.1
0x4f121  stfld    bool Recycle::ensureWindowsAppDomainUnload
0x4f126  ret
0x4f127  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f12c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f131  brfalse.s loc_4F143
0x4f133  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f138  ldc.i4.3
0x4f139  ldstr    aPollingThreadI// "Polling thread is not working but will "...
0x4f13e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f143  ret
```
