# Microsoft.ReportingServices.Diagnostics.RSConfiguration::ValidatePostLoad

- ea: `0x5e80`
- end: `0x5fc7`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::ValidatePostLoad`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x3460`
- `0x34a0`
- `0x34e0`
- `0x34f0`
- `0x5e80`
- `0x6cc0`
- `0xabc0`

## pseudocode

```c

```

## disassembly

```asm
0x5e80  ldarg.0
0x5e81  callvirt instance bool Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_AuthPersistence()
0x5e86  brfalse.s loc_5EA2
0x5e88  ldarg.0
0x5e89  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_AuthenticationTypes()
0x5e8e  ldc.i4.8
0x5e8f  and
0x5e90  brfalse.s loc_5EA2
0x5e92  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5e97  ldc.i4.3
0x5e98  ldstr    aAuthpersistenc// "AuthPersistence does not apply to basic"...
0x5e9d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5ea2  ldarg.0
0x5ea3  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_AuthenticationTypes()
0x5ea8  ldc.i4.7
0x5ea9  and
0x5eaa  brfalse  loc_5FC6
0x5eaf  ldarg.0
0x5eb0  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtendedProtectionLevel Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ExtendedProtectionLevel()
0x5eb5  ldc.i4.4
0x5eb6  bne.un.s loc_5ECF
0x5eb8  ldc.i4.1
0x5eb9  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_DisableEPAuthTypes(bool value)
0x5ebe  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5ec3  ldc.i4.1
0x5ec4  ldstr    aMissingOrInval// "Missing or Invalid ExtendedProtectionLe"...
0x5ec9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5ece  ret
0x5ecf  ldarg.0
0x5ed0  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtendedProtectionLevel Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ExtendedProtectionLevel()
0x5ed5  brfalse  loc_5FC6
0x5eda  ldarg.0
0x5edb  ldc.i4.1
0x5edc  ldloca.s 0
0x5ede  ldloca.s 1
0x5ee0  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckSslAndHttpUrlReservations(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication application, [out] bool& IsSslUrlReserved, [out] bool& IsHttpUrlReserved)
0x5ee5  ldarg.0
0x5ee6  ldc.i4.2
0x5ee7  ldloca.s 2
0x5ee9  ldloca.s 3
0x5eeb  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckSslAndHttpUrlReservations(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication application, [out] bool& IsSslUrlReserved, [out] bool& IsHttpUrlReserved)
0x5ef0  ldarg.0
0x5ef1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtendedProtectionScenario Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ExtendedProtectionScenario()
0x5ef6  ldc.i4.4
0x5ef7  bne.un.s loc_5F10
0x5ef9  ldc.i4.1
0x5efa  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_DisableEPAuthTypes(bool value)
0x5eff  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f04  ldc.i4.1
0x5f05  ldstr    aMissingOrInval_0// "Missing or Invalid ExtendedProtectionSc"...
0x5f0a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f0f  ret
0x5f10  ldarg.0
0x5f11  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtendedProtectionScenario Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ExtendedProtectionScenario()
0x5f16  ldc.i4.1
0x5f17  bne.un.s loc_5F6F
0x5f19  ldloc.0
0x5f1a  brtrue.s loc_5F34
0x5f1c  ldc.i4.1
0x5f1d  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_DisableEPAuthTypes(bool value)
0x5f22  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f27  ldc.i4.1
0x5f28  ldstr    aSslIsRequiredO// "SSL is required on Report Server connec"...
0x5f2d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f32  br.s     loc_5F47
0x5f34  ldloc.1
0x5f35  brfalse.s loc_5F47
0x5f37  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f3c  ldc.i4.2
0x5f3d  ldstr    aHttpTrafficToR// "HTTP traffic to Report Server will fail"...
0x5f42  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f47  ldloc.2
0x5f48  brtrue.s loc_5F5B
0x5f4a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f4f  ldc.i4.1
0x5f50  ldstr    aSslIsRequiredO_0// "SSL is required on Report Manager conne"...
0x5f55  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f5a  ret
0x5f5b  ldloc.3
0x5f5c  brfalse.s loc_5FC6
0x5f5e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f63  ldc.i4.2
0x5f64  ldstr    aHttpTrafficToR_0// "HTTP traffic to Report Manager will fai"...
0x5f69  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f6e  ret
0x5f6f  ldarg.0
0x5f70  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtendedProtectionScenario Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ExtendedProtectionScenario()
0x5f75  brtrue.s loc_5FC6
0x5f77  ldloc.0
0x5f78  brtrue.s loc_5F8C
0x5f7a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f7f  ldc.i4.2
0x5f80  ldstr    aDirectConnecti// "Direct connections to Report Server wil"...
0x5f85  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f8a  br.s     loc_5F9F
0x5f8c  ldloc.1
0x5f8d  brfalse.s loc_5F9F
0x5f8f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5f94  ldc.i4.2
0x5f95  ldstr    aHttpTrafficToR_1// "HTTP traffic to Report Server may fail "...
0x5f9a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5f9f  ldloc.2
0x5fa0  brtrue.s loc_5FB3
0x5fa2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5fa7  ldc.i4.2
0x5fa8  ldstr    aDirectConnecti_0// "Direct connections to Report Manager wi"...
0x5fad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5fb2  ret
0x5fb3  ldloc.3
0x5fb4  brfalse.s loc_5FC6
0x5fb6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5fbb  ldc.i4.2
0x5fbc  ldstr    aHttpTrafficToR_2// "HTTP traffic to Report Manager may fail"...
0x5fc1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5fc6  ret
```
