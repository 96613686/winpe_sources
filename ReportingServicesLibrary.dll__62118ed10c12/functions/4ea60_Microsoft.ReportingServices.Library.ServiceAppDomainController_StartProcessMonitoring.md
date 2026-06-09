# Microsoft.ReportingServices.Library.ServiceAppDomainController::StartProcessMonitoring

- ea: `0x4ea60`
- end: `0x4eb73`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::StartProcessMonitoring`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x4e180`

## callees

- `0x4ea60`

## string_xrefs

- `0x4ea75`: `ServiceAppDomainController.StartProcessMonitoring: Globals.Configuration.ProcessTimeout >= 0`
- `0x4ea94`: `ServiceAppDomainController.StartProcessMonitoring: Globals.Configuration.ProcessTimeout >= 0`
- `0x4eacc`: `Gc extension timeout is disabled. ProcessTimeoutGcExtension was {0}.`
- `0x4eb23`: `Error starting process monitor thread. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4ea60  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4ea65  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4ea6a  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeout()
0x4ea6f  ldc.i4.0
0x4ea70  clt
0x4ea72  ldc.i4.0
0x4ea73  ceq
0x4ea75  ldstr    aServiceappdoma// "ServiceAppDomainController.StartProcess"...
0x4ea7a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4ea7f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4ea84  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4ea89  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeoutGcExtension()
0x4ea8e  ldc.i4.0
0x4ea8f  clt
0x4ea91  ldc.i4.0
0x4ea92  ceq
0x4ea94  ldstr    aServiceappdoma// "ServiceAppDomainController.StartProcess"...
0x4ea99  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4ea9e  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eaa3  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeout()
0x4eaa8  ldc.i4.0
0x4eaa9  ble      loc_4EB3E
0x4eaae  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eab3  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeoutGcExtension()
0x4eab8  brtrue.s loc_4EAEE
0x4eaba  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eabf  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4eac4  brfalse.s loc_4EAEE
0x4eac6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eacb  ldc.i4.3
0x4eacc  ldstr    aGcExtensionTim// "Gc extension timeout is disabled. Proce"...
0x4ead1  ldc.i4.1
0x4ead2  newarr   [mscorlib]System.Object
0x4ead7  dup
0x4ead8  ldc.i4.0
0x4ead9  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eade  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeoutGcExtension()
0x4eae3  box      [mscorlib]System.Int32
0x4eae8  stelem.ref
0x4eae9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4eaee  nop
0x4eaef  ldarg.0
0x4eaf0  ldfld    class [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer Microsoft.ReportingServices.Library.ServiceAppDomainController::m_rpcServer
0x4eaf5  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eafa  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeout()
0x4eaff  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eb04  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeoutGcExtension()
0x4eb09  callvirt instance void [ReportingServicesNativeServer]RSRemoteRpcServer.RpcServer::StartProcessMonitor(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32)
0x4eb0e  leave.s  loc_4EB72
0x4eb10  stloc.0
0x4eb11  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eb16  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4eb1b  brfalse.s loc_4EB3C
0x4eb1d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eb22  ldc.i4.1
0x4eb23  ldstr    aErrorStartingP// "Error starting process monitor thread. "...
0x4eb28  ldc.i4.1
0x4eb29  newarr   [mscorlib]System.Object
0x4eb2e  dup
0x4eb2f  ldc.i4.0
0x4eb30  ldloc.0
0x4eb31  callvirt instance string [mscorlib]System.Object::ToString()
0x4eb36  stelem.ref
0x4eb37  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4eb3c  rethrow
0x4eb3e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eb43  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x4eb48  brfalse.s loc_4EB72
0x4eb4a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4eb4f  ldc.i4.2
0x4eb50  ldstr    aProcessMonitor// "Process monitor is disabled. ProcessTim"...
0x4eb55  ldc.i4.1
0x4eb56  newarr   [mscorlib]System.Object
0x4eb5b  dup
0x4eb5c  ldc.i4.0
0x4eb5d  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x4eb62  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ProcessTimeout()
0x4eb67  box      [mscorlib]System.Int32
0x4eb6c  stelem.ref
0x4eb6d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4eb72  ret
```
