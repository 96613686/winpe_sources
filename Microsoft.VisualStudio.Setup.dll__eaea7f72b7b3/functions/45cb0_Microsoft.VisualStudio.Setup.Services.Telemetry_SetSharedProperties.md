# Microsoft.VisualStudio.Setup.Services.Telemetry::SetSharedProperties

- ea: `0x45cb0`
- end: `0x45ec3`
- name: `Microsoft.VisualStudio.Setup.Services.Telemetry::SetSharedProperties`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x45c30`
- `0x45c60`
- `0x45cb0`
- `0x46920`

## string_xrefs

- `0x45d4d`: `Removed telemetry property `
- `0x45e9d`: `Removed telemetry property `

## pseudocode

```c

```

## disassembly

```asm
0x45cb0  ldarg.1
0x45cb1  ldstr    aObjtelemetryco// "objTelemetryContext"
0x45cb6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x45cbb  ldarg.0
0x45cbc  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45cc1  callvirt instance bool [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryDisposableObject::get_IsDisposed()
0x45cc6  brfalse.s loc_45CC9
0x45cc8  ret
0x45cc9  ldarg.0
0x45cca  stloc.0
0x45ccb  ldc.i4.0
0x45ccc  stloc.1
0x45ccd  ldloc.0
0x45cce  ldloca.s 1
0x45cd0  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x45cd5  ldarg.1
0x45cd6  unbox.any Microsoft.VisualStudio.Setup.TelemetryContext
0x45cdb  stloc.2
0x45cdc  ldloc.2
0x45cdd  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x45ce2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45ce7  brtrue.s loc_45D31
0x45ce9  ldarg.0
0x45cea  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45cef  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWILLOWINSTALLSESSIONID
0x45cf4  ldloc.2
0x45cf5  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x45cfa  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::SetSharedProperty(string, object)
0x45cff  ldarg.0
0x45d00  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45d05  dup
0x45d06  brtrue.s loc_45D0B
0x45d08  pop
0x45d09  br.s     loc_45D66
0x45d0b  ldstr    aTelemetryPrope// "Telemetry property "
0x45d10  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWILLOWINSTALLSESSIONID
0x45d15  ldstr    asc_999AA// " : "
0x45d1a  ldloc.2
0x45d1b  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x45d20  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x45d25  call     T0x2B000003
0x45d2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45d2f  br.s     loc_45D66
0x45d31  ldarg.0
0x45d32  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45d37  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWILLOWINSTALLSESSIONID
0x45d3c  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::RemoveSharedProperty(string)
0x45d41  ldarg.0
0x45d42  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45d47  dup
0x45d48  brtrue.s loc_45D4D
0x45d4a  pop
0x45d4b  br.s     loc_45D66
0x45d4d  ldstr    aRemovedTelemet// "Removed telemetry property "
0x45d52  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SHAREDWILLOWINSTALLSESSIONID
0x45d57  call     string [mscorlib]System.String::Concat(string, string)
0x45d5c  call     T0x2B000003
0x45d61  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45d66  ldarg.0
0x45d67  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45d6c  dup
0x45d6d  brtrue.s loc_45D72
0x45d6f  pop
0x45d70  br.s     loc_45DAA
0x45d72  ldstr    aTelemetryPrope_0// "Telemetry property MachineId : {0}"
0x45d77  ldarg.0
0x45d78  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45d7d  dup
0x45d7e  brtrue.s loc_45D8C
0x45d80  pop
0x45d81  ldloca.s 3
0x45d83  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x45d89  ldloc.3
0x45d8a  br.s     loc_45D96
0x45d8c  call     instance valuetype [mscorlib]System.Guid [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::get_MachineId()
0x45d91  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x45d96  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x45d9b  call     string [mscorlib]System.String::Format(string, object)
0x45da0  call     T0x2B000003
0x45da5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45daa  ldarg.0
0x45dab  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45db0  dup
0x45db1  brtrue.s loc_45DB6
0x45db3  pop
0x45db4  br.s     loc_45DDC
0x45db6  ldstr    aTelemetryPrope_1// "Telemetry property SessionId : "
0x45dbb  ldarg.0
0x45dbc  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45dc1  dup
0x45dc2  brtrue.s loc_45DC8
0x45dc4  pop
0x45dc5  ldnull
0x45dc6  br.s     loc_45DCD
0x45dc8  call     instance string [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::get_SessionId()
0x45dcd  call     string [mscorlib]System.String::Concat(string, string)
0x45dd2  call     T0x2B000003
0x45dd7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45ddc  ldloc.2
0x45ddd  ldfld    string[] Microsoft.VisualStudio.Setup.TelemetryContext::SerializedCorrelations
0x45de2  brfalse.s loc_45E2C
0x45de4  ldloc.2
0x45de5  ldfld    string[] Microsoft.VisualStudio.Setup.TelemetryContext::SerializedCorrelations
0x45dea  stloc.s  4
0x45dec  ldc.i4.0
0x45ded  stloc.s  5
0x45def  br.s     loc_45E24
0x45df1  ldloc.s  4
0x45df3  ldloc.s  5
0x45df5  ldelem.ref
0x45df6  call     valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation::Deserialize(string)
0x45dfb  newobj   instance void Microsoft.VisualStudio.Setup.Services.TelemetryEventCorrelationFacade::.ctor(valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetryEventCorrelation telemetryEventCorrelation)
0x45e00  stloc.s  6
0x45e02  ldarg.0
0x45e03  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation> Microsoft.VisualStudio.Setup.Services.Telemetry::get_SerializedCorrelations()
0x45e08  ldloc.s  6
0x45e0a  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation>::Contains(var<u1>)
0x45e0f  brtrue.s loc_45E1E
0x45e11  ldarg.0
0x45e12  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation> Microsoft.VisualStudio.Setup.Services.Telemetry::get_SerializedCorrelations()
0x45e17  ldloc.s  6
0x45e19  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryEventCorrelation>::Add(var<u1>)
0x45e1e  ldloc.s  5
0x45e20  ldc.i4.1
0x45e21  add
0x45e22  stloc.s  5
0x45e24  ldloc.s  5
0x45e26  ldloc.s  4
0x45e28  ldlen
0x45e29  conv.i4
0x45e2a  blt.s    loc_45DF1
0x45e2c  ldloc.2
0x45e2d  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x45e32  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45e37  brtrue.s loc_45E81
0x45e39  ldarg.0
0x45e3a  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45e3f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::USERREQUESTEDOPERATION
0x45e44  ldloc.2
0x45e45  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x45e4a  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::SetSharedProperty(string, object)
0x45e4f  ldarg.0
0x45e50  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45e55  dup
0x45e56  brtrue.s loc_45E5B
0x45e58  pop
0x45e59  leave.s  loc_45EC2
0x45e5b  ldstr    aTelemetryPrope// "Telemetry property "
0x45e60  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::USERREQUESTEDOPERATION
0x45e65  ldstr    asc_999AA// " : "
0x45e6a  ldloc.2
0x45e6b  ldfld    string Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x45e70  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x45e75  call     T0x2B000003
0x45e7a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45e7f  leave.s  loc_45EC2
0x45e81  ldarg.0
0x45e82  call     instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x45e87  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::USERREQUESTEDOPERATION
0x45e8c  callvirt instance void [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession::RemoveSharedProperty(string)
0x45e91  ldarg.0
0x45e92  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Telemetry::logger
0x45e97  dup
0x45e98  brtrue.s loc_45E9D
0x45e9a  pop
0x45e9b  leave.s  loc_45EC2
0x45e9d  ldstr    aRemovedTelemet// "Removed telemetry property "
0x45ea2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::USERREQUESTEDOPERATION
0x45ea7  call     string [mscorlib]System.String::Concat(string, string)
0x45eac  call     T0x2B000003
0x45eb1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x45eb6  leave.s  loc_45EC2
0x45eb8  ldloc.1
0x45eb9  brfalse.s loc_45EC1
0x45ebb  ldloc.0
0x45ebc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x45ec1  endfinally
0x45ec2  ret
```
