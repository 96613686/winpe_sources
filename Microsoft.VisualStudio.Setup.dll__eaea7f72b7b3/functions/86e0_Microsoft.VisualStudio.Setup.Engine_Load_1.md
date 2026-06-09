# Microsoft.VisualStudio.Setup.Engine::Load_1

- ea: `0x86e0`
- end: `0x890a`
- name: `Microsoft.VisualStudio.Setup.Engine::Load_1`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x8460`

## callees

- `0x7d90`
- `0x7da0`
- `0x7dc0`
- `0x86e0`
- `0x8910`
- `0x9fe0`
- `0xa980`
- `0xfcf0`
- `0x199a0`
- `0x240f0`
- `0x3e0e0`

## string_xrefs

- `0x873a`: `https://aka.ms/vspreinstall`
- `0x86e6`: `services`
- `0x872d`: `ManifestTestSignFail_Args1`
- `0x8753`: `ManifestSignatureVerificationFailed`
- `0x8821`: `Failed to back up and lock down catalog file: 0x{0:x8}. Using original path '{1}' instead.`
- `0x888f`: `Catalog Exception: UpdateRequiredException. Expected when there is an engine update.`

## pseudocode

```c

```

## disassembly

```asm
0x86e0  ldarg.0
0x86e1  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x86e6  ldstr    aServices// "services"
0x86eb  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x86f0  ldarg.0
0x86f1  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0x86f6  ldarg.2
0x86f7  brtrue.s loc_8763
0x86f9  ldnull
0x86fa  stloc.1
0x86fb  ldarg.0
0x86fc  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x8701  ldc.i4.0
0x8702  call     T0x2B000011
0x8707  ldarg.0
0x8708  ldfld    bool Microsoft.VisualStudio.Setup.Engine::shouldCreateLayout
0x870d  brfalse.s loc_8716
0x870f  ldarg.0
0x8710  call     instance string Microsoft.VisualStudio.Setup.Engine::get_LayoutDirectory()
0x8715  stloc.1
0x8716  ldarg.1
0x8717  ldnull
0x8718  ldloc.1
0x8719  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext, string)
0x871e  stloc.2
0x871f  ldloc.2
0x8720  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x8725  ldc.i4.4
0x8726  bne.un.s loc_8746
0x8728  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x872d  ldstr    aManifesttestsi// "ManifestTestSignFail_Args1"
0x8732  ldc.i4.1
0x8733  newarr   [mscorlib]System.Object
0x8738  dup
0x8739  ldc.i4.0
0x873a  ldstr    aHttpsAkaMsVspr// "https://aka.ms/vspreinstall"
0x873f  stelem.ref
0x8740  newobj   instance void Microsoft.VisualStudio.Setup.Security.ManifestSignatureVerificationFailedException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x8745  throw
0x8746  ldloc.2
0x8747  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x874c  brfalse.s loc_8763
0x874e  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x8753  ldstr    aManifestsignat// "ManifestSignatureVerificationFailed"
0x8758  call     T0x2B000003
0x875d  newobj   instance void Microsoft.VisualStudio.Setup.Security.ManifestSignatureVerificationFailedException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x8762  throw
0x8763  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x8768  dup
0x8769  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x876e  ldstr    aLoadcatalog// "LoadCatalog"
0x8773  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x8778  stloc.0
0x8779  ldarg.0
0x877a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x877f  dup
0x8780  brtrue.s loc_8786
0x8782  pop
0x8783  ldnull
0x8784  br.s     loc_8793
0x8786  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::LOADCATALOGEVENT
0x878b  ldloc.0
0x878c  ldc.i4.0
0x878d  ldc.i4.0
0x878e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x8793  stloc.3
0x8794  ldarg.0
0x8795  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x879a  dup
0x879b  brtrue.s loc_87A0
0x879d  pop
0x879e  br.s     loc_87C0
0x87a0  ldstr    aCatalogLoadOpe// "Catalog load operation correlation: "
0x87a5  ldloc.3
0x87a6  brtrue.s loc_87AB
0x87a8  ldnull
0x87a9  br.s     loc_87B1
0x87ab  ldloc.3
0x87ac  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_OperationCorrelation()
0x87b1  call     string [mscorlib]System.String::Concat(string, string)
0x87b6  call     T0x2B000003
0x87bb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x87c0  ldarg.1
0x87c1  brtrue.s loc_87DC
0x87c3  ldloc.3
0x87c4  brfalse.s loc_87D1
0x87c6  ldloc.3
0x87c7  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::NULLPATHSTRING
0x87cc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x87d1  ldstr    aPath// "path"
0x87d6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x87db  throw
0x87dc  ldarg.0
0x87dd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Engine::fileSystem
0x87e2  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetTempFileName()
0x87e7  stloc.s  4
0x87e9  ldarg.0
0x87ea  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Engine::fileSystem
0x87ef  ldarg.1
0x87f0  ldloc.s  4
0x87f2  ldc.i4.2
0x87f3  ldc.i4   0x1F4
0x87f8  call     void Microsoft.VisualStudio.Setup.Extensions::CopyFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string source, string destination, [opt] int32 retryCount, [opt] int32 retryDelay)
0x87fd  ldarg.0
0x87fe  ldfld    class Microsoft.VisualStudio.Setup.Services.ILockService Microsoft.VisualStudio.Setup.Engine::lockService
0x8803  dup
0x8804  brtrue.s loc_8809
0x8806  pop
0x8807  br.s     loc_8811
0x8809  ldloc.s  4
0x880b  callvirt instance class [mscorlib]System.IDisposable Microsoft.VisualStudio.Setup.Services.ILockService::Lock(string path)
0x8810  pop
0x8811  leave.s  loc_8847
0x8813  stloc.s  5
0x8815  ldarg.0
0x8816  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x881b  dup
0x881c  brtrue.s loc_8821
0x881e  pop
0x881f  br.s     loc_8842
0x8821  ldstr    aFailedToBackUp// "Failed to back up and lock down catalog"...
0x8826  ldloc.s  5
0x8828  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x882d  box      [mscorlib]System.Int32
0x8832  ldarg.1
0x8833  call     string [mscorlib]System.String::Format(string, object, object)
0x8838  call     T0x2B000003
0x883d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8842  ldarg.1
0x8843  stloc.s  4
0x8845  leave.s  loc_8847
0x8847  ldarg.0
0x8848  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Engine::fileSystem
0x884d  ldloc.s  4
0x884f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x8854  brtrue.s loc_8859
0x8856  ldarg.1
0x8857  stloc.s  4
0x8859  nop
0x885a  ldarg.0
0x885b  ldloc.s  4
0x885d  call     instance void Microsoft.VisualStudio.Setup.Engine::set_CatalogPath(string value)
0x8862  ldarg.0
0x8863  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x8868  ldarg.0
0x8869  call     instance string Microsoft.VisualStudio.Setup.Engine::get_CatalogPath()
0x886e  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::Parse(class [mscorlib]System.IServiceProvider, string)
0x8873  stloc.s  6
0x8875  ldarg.0
0x8876  ldloc.s  6
0x8878  callvirt instance class [mscorlib]System.Version class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Manifest`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_EngineVersion()
0x887d  call     instance void Microsoft.VisualStudio.Setup.Engine::CheckForEngineUpdate(class [mscorlib]System.Version manifestEngineVersion)
0x8882  ldarg.0
0x8883  ldloc.s  6
0x8885  ldloc.3
0x8886  call     instance void Microsoft.VisualStudio.Setup.Engine::Load(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog catalog, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation loadOperation)
0x888b  leave.s  loc_8909
0x888d  stloc.s  7
0x888f  ldstr    aCatalogExcepti_0// "Catalog Exception: UpdateRequiredExcept"...
0x8894  stloc.s  8
0x8896  ldloc.3
0x8897  brfalse.s loc_88A6
0x8899  ldloc.3
0x889a  ldloc.s  8
0x889c  ldloc.s  7
0x889e  ldloc.s  8
0x88a0  ldc.i4.0
0x88a1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x88a6  ldarg.0
0x88a7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x88ac  dup
0x88ad  brtrue.s loc_88B2
0x88af  pop
0x88b0  br.s     loc_88C3
0x88b2  ldloc.s  7
0x88b4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x88b9  call     T0x2B000003
0x88be  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x88c3  rethrow
0x88c5  stloc.s  9
0x88c7  ldstr    aCatalogExcepti_1// "Catalog Exception"
0x88cc  stloc.s  0xA
0x88ce  ldloc.3
0x88cf  brfalse.s loc_88DE
0x88d1  ldloc.3
0x88d2  ldloc.s  0xA
0x88d4  ldloc.s  9
0x88d6  ldloc.s  0xA
0x88d8  ldc.i4.1
0x88d9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x88de  ldarg.0
0x88df  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x88e4  dup
0x88e5  brtrue.s loc_88EA
0x88e7  pop
0x88e8  br.s     loc_88FD
0x88ea  ldloc.s  9
0x88ec  ldloc.s  9
0x88ee  callvirt instance string [mscorlib]System.Exception::get_Message()
0x88f3  call     T0x2B000003
0x88f8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x88fd  rethrow
0x88ff  ldloc.3
0x8900  brfalse.s loc_8908
0x8902  ldloc.3
0x8903  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8908  endfinally
0x8909  ret
```
