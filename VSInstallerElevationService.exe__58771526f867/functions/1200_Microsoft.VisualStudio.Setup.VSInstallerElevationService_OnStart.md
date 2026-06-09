# Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnStart

- ea: `0x1200`
- end: `0x1361`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnStart`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xc90`
- `0xcc0`
- `0x1200`
- `0x1410`
- `0x1460`
- `0x1550`
- `0x15d0`
- `0x15f0`

## string_xrefs

- `0x120d`: `Starting elevation service...`
- `0x126c`: `Service is disabled by policy. Shutting down.`
- `0x12bc`: `Service is disabled by remote settings. Shutting down.`
- `0x1339`: `Failed to run elevation service manager, shutting down the service.`
- `0x1351`: `Elevation service is running.`

## pseudocode

```c

```

## disassembly

```asm
0x1200  ldarg.0
0x1201  ldarg.0
0x1202  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateServices()
0x1207  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x120c  ldarg.0
0x120d  ldstr    aStartingElevat// "Starting elevation service..."
0x1212  call     T0x2B000005
0x1217  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage(string message, string[] args)
0x121c  ldarg.0
0x121d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1222  ldc.i4.1
0x1223  call     T0x2B000006
0x1228  stloc.0
0x1229  ldarg.0
0x122a  ldloc.0
0x122b  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunOperationName
0x1230  ldnull
0x1231  ldc.i4.0
0x1232  ldc.i4.0
0x1233  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x1238  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x123d  ldarg.0
0x123e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1243  ldc.i4.1
0x1244  call     T0x2B000007
0x1249  callvirt instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ElevationServiceSupport [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ElevationServiceSupport()
0x124e  brtrue.s loc_1282
0x1250  ldarg.0
0x1251  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x1256  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x125b  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByPolicyPropertyName
0x1260  ldc.i4.1
0x1261  box      [mscorlib]System.Boolean
0x1266  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x126b  ldarg.0
0x126c  ldstr    aServiceIsDisab// "Service is disabled by policy. Shutting"...
0x1271  call     T0x2B000005
0x1276  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage(string message, string[] args)
0x127b  ldarg.0
0x127c  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Stop()
0x1281  ret
0x1282  ldarg.0
0x1283  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1288  ldc.i4.1
0x1289  call     T0x2B000008
0x128e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::FeaturesPath
0x1293  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::DisableElevationService
0x1298  ldc.i4.0
0x1299  callvirt T0x2B000009
0x129e  brfalse.s loc_12D2
0x12a0  ldarg.0
0x12a1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x12a6  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x12ab  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByRemoteSettingsPropertyName
0x12b0  ldc.i4.1
0x12b1  box      [mscorlib]System.Boolean
0x12b6  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x12bb  ldarg.0
0x12bc  ldstr    aServiceIsDisab_0// "Service is disabled by remote settings."...
0x12c1  call     T0x2B000005
0x12c6  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage(string message, string[] args)
0x12cb  ldarg.0
0x12cc  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Stop()
0x12d1  ret
0x12d2  ldarg.0
0x12d3  ldarg.0
0x12d4  call     instance class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateElevationServiceManager()
0x12d9  stfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x12de  ldarg.0
0x12df  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x12e4  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x12e9  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByPolicyPropertyName
0x12ee  ldc.i4.0
0x12ef  box      [mscorlib]System.Boolean
0x12f4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x12f9  ldarg.0
0x12fa  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x12ff  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x1304  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationServiceRunDisabledByRemoteSettingsPropertyName
0x1309  ldc.i4.0
0x130a  box      [mscorlib]System.Boolean
0x130f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1314  ldarg.0
0x1315  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x131a  ldarg.0
0x131b  ldftn    instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnServiceFailure(class [mscorlib]System.Exception ex)
0x1321  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x1326  callvirt instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::add_RunError(class [mscorlib]System.Action`1<class [mscorlib]System.Exception> value)
0x132b  ldarg.0
0x132c  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x1331  callvirt instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::Run()
0x1336  leave.s  loc_1350
0x1338  stloc.1
0x1339  ldstr    aFailedToRunEle// "Failed to run elevation service manager"...
0x133e  stloc.2
0x133f  ldarg.0
0x1340  ldloc.2
0x1341  ldloc.1
0x1342  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogError(string message, class [mscorlib]System.Exception ex)
0x1347  ldarg.0
0x1348  ldloc.1
0x1349  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnServiceFailure(class [mscorlib]System.Exception ex)
0x134e  leave.s  loc_1350
0x1350  ldarg.0
0x1351  ldstr    aElevationServi// "Elevation service is running."
0x1356  call     T0x2B000005
0x135b  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage(string message, string[] args)
0x1360  ret
```
