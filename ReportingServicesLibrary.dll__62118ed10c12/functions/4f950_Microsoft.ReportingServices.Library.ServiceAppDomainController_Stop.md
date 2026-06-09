# Microsoft.ReportingServices.Library.ServiceAppDomainController::Stop

- ea: `0x4f950`
- end: `0x4fa3e`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::Stop`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d0d0`

## callees

- `0xf0b0`
- `0x4eb80`
- `0x4ecc0`
- `0x4f950`
- `0x4fa40`
- `0x4fb50`

## string_xrefs

- `0x4f96b`: `***********Exception caught shutting down Monitoring thread**************`
- `0x4f9a4`: `***********Exception caught shutting down RPC service**************`
- `0x4f9fe`: `***********Exception caught shutting down service**************`
- `0x4fa2d`: `Service shutting down.`

## pseudocode

```c

```

## disassembly

```asm
0x4f950  ldarg.0
0x4f951  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StopProcessMonitoring()
0x4f956  leave.s  loc_4F988
0x4f958  stloc.0
0x4f959  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f95e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4f963  brfalse.s loc_4F986
0x4f965  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f96a  ldc.i4.1
0x4f96b  ldstr    aExceptionCaugh_0// "***********Exception caught shutting do"...
0x4f970  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f975  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f97a  ldc.i4.1
0x4f97b  ldloc.0
0x4f97c  callvirt instance string [mscorlib]System.Object::ToString()
0x4f981  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f986  leave.s  loc_4F988
0x4f988  nop
0x4f989  ldarg.0
0x4f98a  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StopRPCServer()
0x4f98f  leave.s  loc_4F9C1
0x4f991  stloc.1
0x4f992  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f997  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4f99c  brfalse.s loc_4F9BF
0x4f99e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f9a3  ldc.i4.1
0x4f9a4  ldstr    aExceptionCaugh_1// "***********Exception caught shutting do"...
0x4f9a9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f9ae  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f9b3  ldc.i4.1
0x4f9b4  ldloc.1
0x4f9b5  callvirt instance string [mscorlib]System.Object::ToString()
0x4f9ba  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f9bf  leave.s  loc_4F9C1
0x4f9c1  nop
0x4f9c2  ldarg.0
0x4f9c3  ldc.i4.0
0x4f9c4  stfld    bool Microsoft.ReportingServices.Library.ServiceAppDomainController::m_continue
0x4f9c9  ldarg.0
0x4f9ca  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StopHttpEndpoints()
0x4f9cf  ldc.i4.2
0x4f9d0  ldc.i4.0
0x4f9d1  call     void Microsoft.ReportingServices.Library.Global::UnloadAppDomain(valuetype [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.RsAppDomainType appDomainType, bool memoryRecycle)
0x4f9d6  ldarg.0
0x4f9d7  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.ServiceAppDomainController::m_resetEvent
0x4f9dc  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x4f9e1  pop
0x4f9e2  ldarg.0
0x4f9e3  ldc.i4.0
0x4f9e4  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::InternalStop(valuetype AppDomainStopMode stopMode)
0x4f9e9  leave.s  loc_4FA1B
0x4f9eb  stloc.2
0x4f9ec  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f9f1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4f9f6  brfalse.s loc_4FA19
0x4f9f8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f9fd  ldc.i4.1
0x4f9fe  ldstr    aExceptionCaugh_2// "***********Exception caught shutting do"...
0x4fa03  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4fa08  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4fa0d  ldc.i4.1
0x4fa0e  ldloc.2
0x4fa0f  callvirt instance string [mscorlib]System.Object::ToString()
0x4fa14  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4fa19  leave.s  loc_4FA1B
0x4fa1b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4fa20  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4fa25  brfalse.s loc_4FA37
0x4fa27  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4fa2c  ldc.i4.3
0x4fa2d  ldstr    aServiceShuttin// "Service shutting down."
0x4fa32  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4fa37  ldarg.0
0x4fa38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fa3d  ret
```
