# Microsoft.VisualStudio.Setup.Engine::Install

- ea: `0x9200`
- end: `0x93e7`
- name: `Microsoft.VisualStudio.Setup.Engine::Install`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x280`
- `0x420`
- `0x7f30`
- `0x7ff0`
- `0x8010`
- `0x8280`
- `0x9200`
- `0x93f0`
- `0x9430`
- `0x95c0`
- `0x9980`
- `0x9a20`
- `0x9fe0`
- `0xb8e0`
- `0xba80`
- `0xca30`
- `0xcab0`
- `0xcfa0`
- `0x14800`
- `0x3f250`

## string_xrefs

- `0x9232`: `Install`
- `0x9266`: `Install operation correlation: `
- `0x9305`: `InstallOperation`

## pseudocode

```c

```

## disassembly

```asm
0x9200  ldarg.1
0x9201  ldstr    aProduct// "product"
0x9206  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x920b  ldarg.2
0x920c  ldstr    aDestination// "destination"
0x9211  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x9216  ldarg.0
0x9217  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0x921c  ldarg.0
0x921d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x9222  call     bool Microsoft.VisualStudio.Setup.Engine::IsResumedRepair(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance)
0x9227  brfalse.s loc_9231
0x9229  ldarg.0
0x922a  ldarg.3
0x922b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::Repair([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x9230  ret
0x9231  ldarg.0
0x9232  ldstr    aInstall// "Install"
0x9237  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.VisualStudio.Setup.Engine::InitializeTelemetryProperties(string operation)
0x923c  stloc.0
0x923d  ldnull
0x923e  stloc.1
0x923f  ldarg.0
0x9240  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x9245  dup
0x9246  brtrue.s loc_924C
0x9248  pop
0x9249  ldnull
0x924a  br.s     loc_9259
0x924c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTANCEOPERATIONEVENT
0x9251  ldloc.0
0x9252  ldc.i4.0
0x9253  ldc.i4.0
0x9254  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x9259  stloc.1
0x925a  ldarg.0
0x925b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x9260  dup
0x9261  brtrue.s loc_9266
0x9263  pop
0x9264  br.s     loc_9286
0x9266  ldstr    aInstallOperati// "Install operation correlation: "
0x926b  ldloc.1
0x926c  brtrue.s loc_9271
0x926e  ldnull
0x926f  br.s     loc_9277
0x9271  ldloc.1
0x9272  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_OperationCorrelation()
0x9277  call     string [mscorlib]System.String::Concat(string, string)
0x927c  call     T0x2B000003
0x9281  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x9286  ldarg.0
0x9287  ldfld    class Microsoft.VisualStudio.Setup.IInstanceReferenceManager Microsoft.VisualStudio.Setup.Engine::referenceManager
0x928c  ldc.i4.1
0x928d  callvirt instance void Microsoft.VisualStudio.Setup.IPackageReferenceManager::set_BootstrapperAction(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction value)
0x9292  ldarg.0
0x9293  ldloc.1
0x9294  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x9299  ldarg.0
0x929a  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x929f  dup
0x92a0  brtrue.s loc_92A6
0x92a2  pop
0x92a3  ldnull
0x92a4  br.s     loc_92B8
0x92a6  ldc.i4.0
0x92a7  call     T0x2B000065
0x92ac  dup
0x92ad  brtrue.s loc_92B3
0x92af  pop
0x92b0  ldnull
0x92b1  br.s     loc_92B8
0x92b3  callvirt instance class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager Microsoft.VisualStudio.Setup.Services.IWindowsRestartManagerFactory::Create()
0x92b8  stloc.2
0x92b9  ldarg.0
0x92ba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Engine::cache
0x92bf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x92c4  stloc.3
0x92c5  ldarg.0
0x92c6  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x92cb  ldarg.2
0x92cc  ldloc.3
0x92cd  ldarg.0
0x92ce  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x92d3  ldc.i4.0
0x92d4  call     T0x2B000066
0x92d9  call     void Microsoft.VisualStudio.Setup.Engine::VerifyInstallationPath(class [mscorlib]System.IServiceProvider services, string installationPath, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance, [opt] class Microsoft.VisualStudio.Setup.Cache.IQuery query)
0x92de  ldarg.2
0x92df  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x92e4  starg.s  2
0x92e6  ldarg.0
0x92e7  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool> Microsoft.VisualStudio.Setup.Engine::packages
0x92ec  call     T0x2B00005F
0x92f1  brtrue.s loc_92FE
0x92f3  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_CatalogError_NotLoaded()
0x92f8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x92fd  throw
0x92fe  ldarg.0
0x92ff  ldarg.2
0x9300  call     instance void Microsoft.VisualStudio.Setup.Engine::SetDriveState(string installDir)
0x9305  ldstr    aInstalloperati// "InstallOperation"
0x930a  stloc.s  4
0x930c  ldarg.0
0x930d  ldloc.s  4
0x930f  call     instance void Microsoft.VisualStudio.Setup.Engine::LogSystemMetrics(string measurementScope)
0x9314  ldarg.2
0x9315  ldarg.0
0x9316  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x931b  ldarg.0
0x931c  ldloc.1
0x931d  ldc.i4.1
0x931e  ldloc.s  4
0x9320  call     class UsedDriveSpace UsedDriveSpace::MeasureSpaceBeforeOperation(string targetDir, class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.IEngineContext engineContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, bool logWatermark, string measurementScope)
0x9325  stloc.s  5
0x9327  ldarg.1
0x9328  ldc.i4.3
0x9329  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::set_RequestedState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState)
0x932e  ldarg.0
0x932f  ldarg.1
0x9330  ldarg.2
0x9331  ldc.i4.1
0x9332  ldloc.1
0x9333  call     instance class Microsoft.VisualStudio.Setup.InstallOperation Microsoft.VisualStudio.Setup.Engine::CreateInstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, string destination, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x9338  stloc.s  6
0x933a  ldarg.0
0x933b  ldarg.2
0x933c  ldarg.1
0x933d  ldc.i4.1
0x933e  ldloc.2
0x933f  ldloc.1
0x9340  ldloc.s  6
0x9342  call     instance void Microsoft.VisualStudio.Setup.Engine::RunPrecheck(string destination, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation installOperation, class Microsoft.VisualStudio.Setup.InstallOperation install)
0x9347  ldarg.0
0x9348  ldarg.2
0x9349  ldarg.1
0x934a  call     instance void Microsoft.VisualStudio.Setup.Engine::GetDefaultNgenApplication(string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product)
0x934f  ldarg.0
0x9350  ldloc.s  6
0x9352  ldc.i4.1
0x9353  ldloc.1
0x9354  ldarg.3
0x9355  call     instance void Microsoft.VisualStudio.Setup.Engine::RunCoreOperation(class Microsoft.VisualStudio.Setup.InstallOperation coreOperation, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, valuetype [mscorlib]System.Threading.CancellationToken token)
0x935a  ldloc.s  5
0x935c  brfalse.s loc_9369
0x935e  ldloc.s  5
0x9360  ldloc.1
0x9361  ldarg.2
0x9362  ldarg.0
0x9363  call     instance class UsedDriveSpace UsedDriveSpace::MeasureSpaceAfterOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation, string targetDir, class Microsoft.VisualStudio.Setup.IEngineContext engineContext)
0x9368  pop
0x9369  ldarg.0
0x936a  ldarg.1
0x936b  ldc.i4.1
0x936c  ldnull
0x936d  call     instance void Microsoft.VisualStudio.Setup.Engine::BuildDependencyGraph(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, [opt] bool overwrite, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x9372  ldarg.0
0x9373  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x9378  stloc.s  7
0x937a  leave.s  loc_93E4
0x937c  ldloc.s  6
0x937e  brfalse.s loc_9387
0x9380  ldloc.s  6
0x9382  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9387  endfinally
0x9388  pop
0x9389  rethrow
0x938b  stloc.s  8
0x938d  ldarg.0
0x938e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x9393  dup
0x9394  brtrue.s loc_9399
0x9396  pop
0x9397  br.s     loc_93AC
0x9399  ldloc.s  8
0x939b  ldloc.s  8
0x939d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x93a2  call     T0x2B000003
0x93a7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x93ac  rethrow
0x93ae  ldarg.0
0x93af  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x93b4  dup
0x93b5  brtrue.s loc_93BB
0x93b7  pop
0x93b8  ldc.i4.0
0x93b9  br.s     loc_93C0
0x93bb  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsLaunchable(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance)
0x93c0  brfalse.s loc_93C9
0x93c2  ldarg.0
0x93c3  ldloc.2
0x93c4  call     instance void Microsoft.VisualStudio.Setup.Engine::TryRestartRmService(class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService)
0x93c9  ldloc.2
0x93ca  brfalse.s loc_93D2
0x93cc  ldloc.2
0x93cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93d2  endfinally
0x93d3  ldloc.1
0x93d4  brfalse.s loc_93DC
0x93d6  ldloc.1
0x93d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x93dc  ldarg.0
0x93dd  ldnull
0x93de  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x93e3  endfinally
0x93e4  ldloc.s  7
0x93e6  ret
```
