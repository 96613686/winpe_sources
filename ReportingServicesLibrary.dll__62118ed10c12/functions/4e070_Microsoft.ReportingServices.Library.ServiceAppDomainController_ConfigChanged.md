# Microsoft.ReportingServices.Library.ServiceAppDomainController::ConfigChanged

- ea: `0x4e070`
- end: `0x4e0d0`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::ConfigChanged`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4e070`
- `0x4ecc0`

## string_xrefs

- `0x4e091`: `Config file changed; ignoring it since a previous change has been intercepted.`
- `0x4e0ae`: `Config file changed; stopping the RPC server`

## pseudocode

```c

```

## disassembly

```asm
0x4e070  ldarg.0
0x4e071  ldflda   int32 Microsoft.ReportingServices.Library.ServiceAppDomainController::m_configChanged
0x4e076  ldc.i4.1
0x4e077  ldc.i4.0
0x4e078  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x4e07d  brfalse.s loc_4E09C
0x4e07f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4e084  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4e089  brfalse.s loc_4E09B
0x4e08b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4e090  ldc.i4.3
0x4e091  ldstr    aConfigFileChan// "Config file changed; ignoring it since "...
0x4e096  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4e09b  ret
0x4e09c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4e0a1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4e0a6  brfalse.s loc_4E0B8
0x4e0a8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4e0ad  ldc.i4.3
0x4e0ae  ldstr    aConfigFileChan_0// "Config file changed; stopping the RPC s"...
0x4e0b3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4e0b8  ldarg.0
0x4e0b9  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StopRPCServer()
0x4e0be  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ResetKeyManager()
0x4e0c3  ldarg.0
0x4e0c4  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.ServiceAppDomainController::m_resetEvent
0x4e0c9  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x4e0ce  pop
0x4e0cf  ret
```
