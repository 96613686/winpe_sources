# Microsoft.VisualStudio.Setup.Engine::Repair

- ea: `0x95c0`
- end: `0x9756`
- name: `Microsoft.VisualStudio.Setup.Engine::Repair`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9200`

## callees

- `0x280`
- `0x420`
- `0x7f30`
- `0x7ff0`
- `0x93f0`
- `0x9430`
- `0x95c0`
- `0x9920`
- `0x9980`
- `0x9a20`
- `0x9fe0`
- `0xb8e0`
- `0xba80`
- `0xca30`
- `0xcab0`
- `0xcfa0`
- `0x14800`
- `0x195b0`
- `0x195c0`
- `0x3f250`

## string_xrefs

- `0x95c7`: `Repair`
- `0x95fb`: `Repair operation correlation: `
- `0x9667`: `RepairOperation`

## pseudocode

```c

```

## disassembly

```asm
0x95c0  ldarg.0
0x95c1  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0x95c6  ldarg.0
0x95c7  ldstr    aRepair// "Repair"
0x95cc  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.VisualStudio.Setup.Engine::InitializeTelemetryProperties(string operation)
0x95d1  stloc.0
0x95d2  ldnull
0x95d3  stloc.1
0x95d4  ldarg.0
0x95d5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x95da  dup
0x95db  brtrue.s loc_95E1
0x95dd  pop
0x95de  ldnull
0x95df  br.s     loc_95EE
0x95e1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTANCEOPERATIONEVENT
0x95e6  ldloc.0
0x95e7  ldc.i4.0
0x95e8  ldc.i4.0
0x95e9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x95ee  stloc.1
0x95ef  ldarg.0
0x95f0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x95f5  dup
0x95f6  brtrue.s loc_95FB
0x95f8  pop
0x95f9  br.s     loc_961B
0x95fb  ldstr    aRepairOperatio// "Repair operation correlation: "
0x9600  ldloc.1
0x9601  brtrue.s loc_9606
0x9603  ldnull
0x9604  br.s     loc_960C
0x9606  ldloc.1
0x9607  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_OperationCorrelation()
0x960c  call     string [mscorlib]System.String::Concat(string, string)
0x9611  call     T0x2B000003
0x9616  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x961b  ldarg.0
0x961c  ldfld    class Microsoft.VisualStudio.Setup.IInstanceReferenceManager Microsoft.VisualStudio.Setup.Engine::referenceManager
0x9621  ldc.i4.2
0x9622  callvirt instance void Microsoft.VisualStudio.Setup.IPackageReferenceManager::set_BootstrapperAction(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction value)
0x9627  ldarg.0
0x9628  ldloc.1
0x9629  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x962e  ldarg.0
0x962f  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x9634  dup
0x9635  brtrue.s loc_963B
0x9637  pop
0x9638  ldnull
0x9639  br.s     loc_964D
0x963b  ldc.i4.0
0x963c  call     T0x2B000065
0x9641  dup
0x9642  brtrue.s loc_9648
0x9644  pop
0x9645  ldnull
0x9646  br.s     loc_964D
0x9648  callvirt instance class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager Microsoft.VisualStudio.Setup.Services.IWindowsRestartManagerFactory::Create()
0x964d  stloc.2
0x964e  ldarg.0
0x964f  call     instance class Microsoft.VisualStudio.Setup.RegisteredProductInfo Microsoft.VisualStudio.Setup.Engine::GetRegisteredProduct()
0x9654  dup
0x9655  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product Microsoft.VisualStudio.Setup.RegisteredProductInfo::get_Product()
0x965a  stloc.3
0x965b  callvirt instance string Microsoft.VisualStudio.Setup.RegisteredProductInfo::get_InstallationPath()
0x9660  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x9665  stloc.s  4
0x9667  ldstr    aRepairoperatio// "RepairOperation"
0x966c  stloc.s  5
0x966e  ldarg.0
0x966f  ldloc.s  5
0x9671  call     instance void Microsoft.VisualStudio.Setup.Engine::LogSystemMetrics(string measurementScope)
0x9676  ldloc.s  4
0x9678  ldarg.0
0x9679  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x967e  ldarg.0
0x967f  ldloc.1
0x9680  ldc.i4.1
0x9681  ldloc.s  5
0x9683  call     class UsedDriveSpace UsedDriveSpace::MeasureSpaceBeforeOperation(string targetDir, class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.IEngineContext engineContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, bool logWatermark, string measurementScope)
0x9688  stloc.s  6
0x968a  ldarg.0
0x968b  ldloc.3
0x968c  ldloc.s  4
0x968e  ldc.i4.2
0x968f  ldloc.1
0x9690  call     instance class Microsoft.VisualStudio.Setup.InstallOperation Microsoft.VisualStudio.Setup.Engine::CreateInstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, string destination, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x9695  stloc.s  7
0x9697  ldarg.0
0x9698  ldloc.s  4
0x969a  ldloc.3
0x969b  ldc.i4.2
0x969c  ldloc.2
0x969d  ldloc.1
0x969e  ldloc.s  7
0x96a0  call     instance void Microsoft.VisualStudio.Setup.Engine::RunPrecheck(string destination, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation installOperation, class Microsoft.VisualStudio.Setup.InstallOperation install)
0x96a5  ldarg.0
0x96a6  ldloc.s  4
0x96a8  ldloc.3
0x96a9  call     instance void Microsoft.VisualStudio.Setup.Engine::GetDefaultNgenApplication(string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product)
0x96ae  ldarg.0
0x96af  ldloc.s  4
0x96b1  call     instance void Microsoft.VisualStudio.Setup.Engine::SetDriveState(string installDir)
0x96b6  ldarg.0
0x96b7  ldloc.s  7
0x96b9  ldc.i4.2
0x96ba  ldloc.1
0x96bb  ldarg.1
0x96bc  call     instance void Microsoft.VisualStudio.Setup.Engine::RunCoreOperation(class Microsoft.VisualStudio.Setup.InstallOperation coreOperation, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, valuetype [mscorlib]System.Threading.CancellationToken token)
0x96c1  ldloc.s  6
0x96c3  brfalse.s loc_96D5
0x96c5  ldloc.s  4
0x96c7  brfalse.s loc_96D5
0x96c9  ldloc.s  6
0x96cb  ldloc.1
0x96cc  ldloc.s  4
0x96ce  ldarg.0
0x96cf  callvirt instance class UsedDriveSpace UsedDriveSpace::MeasureSpaceAfterOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation, string targetDir, class Microsoft.VisualStudio.Setup.IEngineContext engineContext)
0x96d4  pop
0x96d5  ldloc.3
0x96d6  brfalse.s loc_96E1
0x96d8  ldarg.0
0x96d9  ldloc.3
0x96da  ldc.i4.1
0x96db  ldnull
0x96dc  call     instance void Microsoft.VisualStudio.Setup.Engine::BuildDependencyGraph(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, [opt] bool overwrite, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x96e1  ldarg.0
0x96e2  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x96e7  stloc.s  8
0x96e9  leave.s  loc_9753
0x96eb  ldloc.s  7
0x96ed  brfalse.s loc_96F6
0x96ef  ldloc.s  7
0x96f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96f6  endfinally
0x96f7  pop
0x96f8  rethrow
0x96fa  stloc.s  9
0x96fc  ldarg.0
0x96fd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x9702  dup
0x9703  brtrue.s loc_9708
0x9705  pop
0x9706  br.s     loc_971B
0x9708  ldloc.s  9
0x970a  ldloc.s  9
0x970c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9711  call     T0x2B000003
0x9716  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x971b  rethrow
0x971d  ldarg.0
0x971e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x9723  dup
0x9724  brtrue.s loc_972A
0x9726  pop
0x9727  ldc.i4.0
0x9728  br.s     loc_972F
0x972a  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsLaunchable(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance)
0x972f  brfalse.s loc_9738
0x9731  ldarg.0
0x9732  ldloc.2
0x9733  call     instance void Microsoft.VisualStudio.Setup.Engine::TryRestartRmService(class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService)
0x9738  ldloc.2
0x9739  brfalse.s loc_9741
0x973b  ldloc.2
0x973c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9741  endfinally
0x9742  ldloc.1
0x9743  brfalse.s loc_974B
0x9745  ldloc.1
0x9746  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x974b  ldarg.0
0x974c  ldnull
0x974d  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x9752  endfinally
0x9753  ldloc.s  8
0x9755  ret
```
