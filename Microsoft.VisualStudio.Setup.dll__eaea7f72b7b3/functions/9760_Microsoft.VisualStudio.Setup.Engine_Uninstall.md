# Microsoft.VisualStudio.Setup.Engine::Uninstall

- ea: `0x9760`
- end: `0x98cd`
- name: `Microsoft.VisualStudio.Setup.Engine::Uninstall`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f30`
- `0x7ff0`
- `0x93f0`
- `0x9430`
- `0x9760`
- `0x9920`
- `0x9a20`
- `0x9fe0`
- `0xba80`
- `0xcab0`
- `0xcfa0`
- `0x14800`
- `0x195b0`
- `0x195c0`
- `0x3f250`

## string_xrefs

- `0x976c`: `Uninstall`
- `0x97a0`: `Uninstall operation correlation: `
- `0x9843`: `UninstallOperation`

## pseudocode

```c

```

## disassembly

```asm
0x9760  ldarg.0
0x9761  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0x9766  leave.s  loc_976B
0x9768  pop
0x9769  leave.s  loc_976B
0x976b  ldarg.0
0x976c  ldstr    aUninstall// "Uninstall"
0x9771  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.VisualStudio.Setup.Engine::InitializeTelemetryProperties(string operation)
0x9776  stloc.0
0x9777  ldnull
0x9778  stloc.1
0x9779  ldarg.0
0x977a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x977f  dup
0x9780  brtrue.s loc_9786
0x9782  pop
0x9783  ldnull
0x9784  br.s     loc_9793
0x9786  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTANCEOPERATIONEVENT
0x978b  ldloc.0
0x978c  ldc.i4.0
0x978d  ldc.i4.0
0x978e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x9793  stloc.1
0x9794  ldarg.0
0x9795  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x979a  dup
0x979b  brtrue.s loc_97A0
0x979d  pop
0x979e  br.s     loc_97C0
0x97a0  ldstr    aUninstallOpera// "Uninstall operation correlation: "
0x97a5  ldloc.1
0x97a6  brtrue.s loc_97AB
0x97a8  ldnull
0x97a9  br.s     loc_97B1
0x97ab  ldloc.1
0x97ac  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_OperationCorrelation()
0x97b1  call     string [mscorlib]System.String::Concat(string, string)
0x97b6  call     T0x2B000003
0x97bb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x97c0  ldarg.0
0x97c1  ldfld    class Microsoft.VisualStudio.Setup.IInstanceReferenceManager Microsoft.VisualStudio.Setup.Engine::referenceManager
0x97c6  ldc.i4.3
0x97c7  callvirt instance void Microsoft.VisualStudio.Setup.IPackageReferenceManager::set_BootstrapperAction(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction value)
0x97cc  ldarg.0
0x97cd  ldloc.1
0x97ce  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x97d3  ldarg.0
0x97d4  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x97d9  dup
0x97da  brtrue.s loc_97E0
0x97dc  pop
0x97dd  ldnull
0x97de  br.s     loc_97F2
0x97e0  ldc.i4.0
0x97e1  call     T0x2B000065
0x97e6  dup
0x97e7  brtrue.s loc_97ED
0x97e9  pop
0x97ea  ldnull
0x97eb  br.s     loc_97F2
0x97ed  callvirt instance class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager Microsoft.VisualStudio.Setup.Services.IWindowsRestartManagerFactory::Create()
0x97f2  stloc.2
0x97f3  ldnull
0x97f4  stloc.3
0x97f5  ldnull
0x97f6  stloc.s  4
0x97f8  ldnull
0x97f9  stloc.s  5
0x97fb  ldarg.0
0x97fc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Engine::get_Instance()
0x9801  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_Product()
0x9806  brfalse.s loc_9843
0x9808  ldarg.0
0x9809  call     instance class Microsoft.VisualStudio.Setup.RegisteredProductInfo Microsoft.VisualStudio.Setup.Engine::GetRegisteredProduct()
0x980e  dup
0x980f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product Microsoft.VisualStudio.Setup.RegisteredProductInfo::get_Product()
0x9814  stloc.3
0x9815  callvirt instance string Microsoft.VisualStudio.Setup.RegisteredProductInfo::get_InstallationPath()
0x981a  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x981f  stloc.s  4
0x9821  ldloc.3
0x9822  ldc.i4.1
0x9823  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::set_RequestedState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState)
0x9828  ldarg.0
0x9829  ldloc.3
0x982a  ldloc.s  4
0x982c  ldc.i4.3
0x982d  ldloc.1
0x982e  call     instance class Microsoft.VisualStudio.Setup.InstallOperation Microsoft.VisualStudio.Setup.Engine::CreateInstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, string destination, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x9833  stloc.s  5
0x9835  ldarg.0
0x9836  ldloc.s  4
0x9838  ldloc.3
0x9839  ldc.i4.3
0x983a  ldloc.2
0x983b  ldloc.1
0x983c  ldloc.s  5
0x983e  call     instance void Microsoft.VisualStudio.Setup.Engine::RunPrecheck(string destination, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation installOperation, class Microsoft.VisualStudio.Setup.InstallOperation install)
0x9843  ldstr    aUninstallopera// "UninstallOperation"
0x9848  stloc.s  6
0x984a  ldarg.0
0x984b  ldloc.s  6
0x984d  call     instance void Microsoft.VisualStudio.Setup.Engine::LogSystemMetrics(string measurementScope)
0x9852  ldloc.s  5
0x9854  dup
0x9855  brtrue.s loc_9863
0x9857  pop
0x9858  ldarg.0
0x9859  ldloc.3
0x985a  ldloc.s  4
0x985c  ldc.i4.3
0x985d  ldloc.1
0x985e  call     instance class Microsoft.VisualStudio.Setup.InstallOperation Microsoft.VisualStudio.Setup.Engine::CreateInstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, string destination, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation)
0x9863  stloc.s  5
0x9865  ldloc.s  5
0x9867  stloc.s  7
0x9869  ldarg.0
0x986a  ldloc.s  5
0x986c  ldc.i4.3
0x986d  ldloc.1
0x986e  ldarg.1
0x986f  call     instance void Microsoft.VisualStudio.Setup.Engine::RunCoreOperation(class Microsoft.VisualStudio.Setup.InstallOperation coreOperation, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, valuetype [mscorlib]System.Threading.CancellationToken token)
0x9874  leave.s  loc_9882
0x9876  ldloc.s  7
0x9878  brfalse.s loc_9881
0x987a  ldloc.s  7
0x987c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9881  endfinally
0x9882  leave.s  loc_98CC
0x9884  pop
0x9885  rethrow
0x9887  stloc.s  8
0x9889  ldarg.0
0x988a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x988f  dup
0x9890  brtrue.s loc_9895
0x9892  pop
0x9893  br.s     loc_98A8
0x9895  ldloc.s  8
0x9897  ldloc.s  8
0x9899  callvirt instance string [mscorlib]System.Exception::get_Message()
0x989e  call     T0x2B000003
0x98a3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x98a8  rethrow
0x98aa  ldarg.0
0x98ab  ldloc.2
0x98ac  call     instance void Microsoft.VisualStudio.Setup.Engine::TryRestartRmService(class Microsoft.VisualStudio.Setup.Services.IWindowsRestartManager rmService)
0x98b1  ldloc.2
0x98b2  brfalse.s loc_98BA
0x98b4  ldloc.2
0x98b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x98ba  endfinally
0x98bb  ldloc.1
0x98bc  brfalse.s loc_98C4
0x98be  ldloc.1
0x98bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x98c4  ldarg.0
0x98c5  ldnull
0x98c6  call     instance void Microsoft.VisualStudio.Setup.Engine::set_InstallOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation value)
0x98cb  endfinally
0x98cc  ret
```
