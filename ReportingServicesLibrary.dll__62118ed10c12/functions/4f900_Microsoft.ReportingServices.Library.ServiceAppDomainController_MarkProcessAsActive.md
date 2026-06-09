# Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive

- ea: `0x4f900`
- end: `0x4f94d`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::MarkProcessAsActive`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d010`
- `0x4f240`
- `0x4f3b0`
- `0x4f600`
- `0x4f6e0`

## callees

- `0x4f900`

## string_xrefs

- `0x4f912`: `ServiceAppDomainController::MarkProcessAsActive - Mark the WindowsService (worker) AppDomain as active.`
- `0x4f942`: `ServiceAppDomainController::MarkProcessAsActive - m_rpcServer is null; Cannot mark the WindowsService (worker) AppDomain as active.`

## pseudocode

```c

```

## disassembly

```asm
0x4f900  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f905  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x4f90a  brfalse.s loc_4F91C
0x4f90c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f911  ldc.i4.4
0x4f912  ldstr    aServiceappdoma_5// "ServiceAppDomainController::MarkProcess"...
0x4f917  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f91c  ldarg.0
0x4f91d  ldfld    class [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_rpcServer
0x4f922  brfalse.s loc_4F930
0x4f924  ldarg.0
0x4f925  ldfld    class [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_rpcServer
0x4f92a  callvirt instance void [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer::MarkProcessAsActive()
0x4f92f  ret
0x4f930  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f935  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f93a  brfalse.s loc_4F94C
0x4f93c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f941  ldc.i4.3
0x4f942  ldstr    aServiceappdoma_6// "ServiceAppDomainController::MarkProcess"...
0x4f947  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f94c  ret
```
