# Microsoft.VisualStudio.Setup.Installer.InstallerBase::InstallHelper

- ea: `0x2c5e0`
- end: `0x2ca37`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerBase::InstallHelper`
- size: `1111`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callees

- `0x280`
- `0x420`
- `0xfed0`
- `0x11d60`
- `0x2b900`
- `0x2b920`
- `0x2b940`
- `0x2b9a0`
- `0x2b9c0`
- `0x2b9e0`
- `0x2b9f0`
- `0x2ba10`
- `0x2baa0`
- `0x2be80`
- `0x2c050`
- `0x2c170`
- `0x2c5e0`
- `0x2d260`
- `0x2d2d0`
- `0x3eb00`
- `0x6c790`
- `0x6c7b0`
- `0x6c7d0`
- `0x6c800`

## string_xrefs

- `0x2c60b`: `Install-Package`
- `0x2c7c3`: `Installing {0}`
- `0x2c8af`: `User canceled during package install.`
- `0x2c8e6`: `Package install Exception.`
- `0x2c9aa`: `Package install Exception.`

## pseudocode

```c

```

## disassembly

```asm
0x2c5e0  ldnull
0x2c5e1  stloc.0
0x2c5e2  ldarg.1
0x2c5e3  ldarg.0
0x2c5e4  dup
0x2c5e5  ldvirtftn instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2c5eb  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs>::.ctor(object, native int)
0x2c5f0  ldc.i4.1
0x2c5f1  ldnull
0x2c5f2  ldc.i4.1
0x2c5f3  newobj   instance void DefaultProgressReport::.ctor(class InstallData pkgData, class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs> onProgress, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] string packageDisplayInfo, [opt] bool completeProgressInDispose)
0x2c5f8  stloc.1
0x2c5f9  ldarg.1
0x2c5fa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2c5ff  stloc.2
0x2c600  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2c605  dup
0x2c606  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x2c60b  ldstr    aInstallPackage// "Install-Package"
0x2c610  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c615  dup
0x2c616  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEIDPROPERTY
0x2c61b  ldloc.2
0x2c61c  brtrue.s loc_2C621
0x2c61e  ldnull
0x2c61f  br.s     loc_2C627
0x2c621  ldloc.2
0x2c622  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2c627  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c62c  dup
0x2c62d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEUNIQUEIDPROPERTY
0x2c632  ldloc.2
0x2c633  brtrue.s loc_2C638
0x2c635  ldnull
0x2c636  br.s     loc_2C63E
0x2c638  ldloc.2
0x2c639  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2c63e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c643  dup
0x2c644  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGELANGUAGEPROPERTY
0x2c649  ldloc.2
0x2c64a  brtrue.s loc_2C64F
0x2c64c  ldnull
0x2c64d  br.s     loc_2C655
0x2c64f  ldloc.2
0x2c650  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2c655  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c65a  dup
0x2c65b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGESTATEPROPERTY
0x2c660  ldloc.2
0x2c661  brtrue.s loc_2C666
0x2c663  ldnull
0x2c664  br.s     loc_2C67B
0x2c666  ldloc.2
0x2c667  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_CurrentState()
0x2c66c  stloc.s  4
0x2c66e  ldloca.s 4
0x2c670  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x2c676  callvirt instance string [mscorlib]System.Object::ToString()
0x2c67b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c680  dup
0x2c681  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEREQUESTEDSTATEPROPERTY
0x2c686  ldloc.2
0x2c687  brtrue.s loc_2C68C
0x2c689  ldnull
0x2c68a  br.s     loc_2C6A1
0x2c68c  ldloc.2
0x2c68d  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x2c692  stloc.s  5
0x2c694  ldloca.s 5
0x2c696  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState
0x2c69c  callvirt instance string [mscorlib]System.Object::ToString()
0x2c6a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c6a6  dup
0x2c6a7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGECHIPPROPERTY
0x2c6ac  ldloc.2
0x2c6ad  brtrue.s loc_2C6B2
0x2c6af  ldnull
0x2c6b0  br.s     loc_2C6B8
0x2c6b2  ldloc.2
0x2c6b3  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Chip()
0x2c6b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c6bd  dup
0x2c6be  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEPRODUCTARCHPROPERTY
0x2c6c3  ldloc.2
0x2c6c4  brtrue.s loc_2C6C9
0x2c6c6  ldnull
0x2c6c7  br.s     loc_2C6CF
0x2c6c9  ldloc.2
0x2c6ca  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ProductArch()
0x2c6cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c6d4  dup
0x2c6d5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEMACHINEARCHPROPERTY
0x2c6da  ldloc.2
0x2c6db  brtrue.s loc_2C6E0
0x2c6dd  ldnull
0x2c6de  br.s     loc_2C6E6
0x2c6e0  ldloc.2
0x2c6e1  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_MachineArch()
0x2c6e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c6eb  dup
0x2c6ec  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEVERSIONPROPERTY
0x2c6f1  ldloc.2
0x2c6f2  brtrue.s loc_2C6F7
0x2c6f4  ldnull
0x2c6f5  br.s     loc_2C6FD
0x2c6f7  ldloc.2
0x2c6f8  call     instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x2c6fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c702  dup
0x2c703  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGETYPEPROPERTY
0x2c708  ldloc.2
0x2c709  brtrue.s loc_2C717
0x2c70b  ldloca.s 6
0x2c70d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2c713  ldloc.s  6
0x2c715  br.s     loc_2C722
0x2c717  ldloc.2
0x2c718  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Type()
0x2c71d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>::.ctor(var<u1>)
0x2c722  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2c727  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c72c  dup
0x2c72d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x2c732  ldloc.2
0x2c733  brtrue.s loc_2C738
0x2c735  ldnull
0x2c736  br.s     loc_2C748
0x2c738  ldloc.2
0x2c739  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_TelemetryCorrelatedParents()
0x2c73e  ldstr    asc_82420// ";"
0x2c743  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2c748  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c74d  dup
0x2c74e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
0x2c753  ldloc.2
0x2c754  brtrue.s loc_2C759
0x2c756  ldnull
0x2c757  br.s     loc_2C769
0x2c759  ldloc.2
0x2c75a  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_AncestorWorkloads()
0x2c75f  ldstr    asc_82420// ";"
0x2c764  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2c769  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2c76e  stloc.3
0x2c76f  ldloc.3
0x2c770  ldarg.0
0x2c771  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_AdditionalTelemetryProperties()
0x2c776  call     T0x2B000064
0x2c77b  ldarg.0
0x2c77c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_TelemetryService()
0x2c781  dup
0x2c782  brtrue.s loc_2C788
0x2c784  pop
0x2c785  ldnull
0x2c786  br.s     loc_2C795
0x2c788  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x2c78d  ldloc.3
0x2c78e  ldc.i4.0
0x2c78f  ldc.i4.0
0x2c790  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x2c795  stloc.s  7
0x2c797  ldarg.1
0x2c798  callvirt instance string InstallData::get_LocalPath()
0x2c79d  brtrue.s loc_2C7BD
0x2c79f  ldloc.s  7
0x2c7a1  brfalse.s loc_2C7AF
0x2c7a3  ldloc.s  7
0x2c7a5  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::NULLPATHSTRING
0x2c7aa  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2c7af  ldc.i4.4
0x2c7b0  ldc.i4.0
0x2c7b1  ldnull
0x2c7b2  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2c7b7  stloc.0
0x2c7b8  br       loc_2C8A9
0x2c7bd  ldarg.0
0x2c7be  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2c7c3  ldstr    aInstalling0// "Installing {0}"
0x2c7c8  ldc.i4.1
0x2c7c9  newarr   [mscorlib]System.Object
0x2c7ce  dup
0x2c7cf  ldc.i4.0
0x2c7d0  ldarg.0
0x2c7d1  ldarg.1
0x2c7d2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2c7d7  ldarg.1
0x2c7d8  callvirt instance string InstallData::get_LocalPath()
0x2c7dd  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetPackageNameForLogging(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, string localPath)
0x2c7e2  stelem.ref
0x2c7e3  newobj   instance void Microsoft.VisualStudio.Setup.LogActionWrapper::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger log, string actionName, object[] args)
0x2c7e8  stloc.s  8
0x2c7ea  ldarg.1
0x2c7eb  callvirt instance string InstallData::get_InstallDir()
0x2c7f0  stloc.s  9
0x2c7f2  ldnull
0x2c7f3  stloc.s  0xA
0x2c7f5  ldarg.0
0x2c7f6  call     instance class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_PolicyService()
0x2c7fb  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DiagnosticMode()
0x2c800  brfalse.s loc_2C820
0x2c802  ldloc.s  9
0x2c804  ldarg.0
0x2c805  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2c80a  ldarg.0
0x2c80b  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x2c810  ldloc.s  7
0x2c812  ldc.i4.0
0x2c813  ldloc.2
0x2c814  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2c819  call     class UsedDriveSpace UsedDriveSpace::MeasureSpaceBeforeOperation(string targetDir, class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.IEngineContext engineContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, bool logWatermark, string measurementScope)
0x2c81e  stloc.s  0xA
0x2c820  ldarg.0
0x2c821  ldarg.1
0x2c822  callvirt instance string InstallData::get_LocalPath()
0x2c827  ldloc.s  9
0x2c829  ldloc.2
0x2c82a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::InstallCore(string localPath, string installDir, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg)
0x2c82f  stloc.0
0x2c830  ldloc.s  0xA
0x2c832  brfalse.s loc_2C846
0x2c834  ldloc.s  0xA
0x2c836  ldloc.s  7
0x2c838  ldloc.s  9
0x2c83a  ldarg.0
0x2c83b  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x2c840  call     instance class UsedDriveSpace UsedDriveSpace::MeasureSpaceAfterOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation, string targetDir, class Microsoft.VisualStudio.Setup.IEngineContext engineContext)
0x2c845  pop
0x2c846  ldloc.0
0x2c847  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLRESULTPROPERTY
0x2c84c  ldloc.s  7
0x2c84e  brtrue.s loc_2C853
0x2c850  ldnull
0x2c851  br.s     loc_2C85A
0x2c853  ldloc.s  7
0x2c855  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2c85a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x2c85f  ldloc.0
0x2c860  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult)
0x2c865  brfalse.s loc_2C87A
0x2c867  ldloc.s  7
0x2c869  brfalse.s loc_2C89B
0x2c86b  ldloc.s  7
0x2c86d  ldloc.0
0x2c86e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2c873  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x2c878  br.s     loc_2C89B
0x2c87a  ldloc.s  7
0x2c87c  brfalse.s loc_2C89B
0x2c87e  ldloc.s  7
0x2c880  ldstr    a01_0// "{0} - {1}"
0x2c885  ldc.i4.2
0x2c886  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x2c88b  ldloc.0
0x2c88c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2c891  call     string [mscorlib]System.String::Format(string, object, object)
0x2c896  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2c89b  leave.s  loc_2C8A9
0x2c89d  ldloc.s  8
0x2c89f  brfalse.s loc_2C8A8
0x2c8a1  ldloc.s  8
0x2c8a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c8a8  endfinally
0x2c8a9  leave    loc_2CA23
0x2c8ae  pop
0x2c8af  ldstr    aUserCanceledDu_1// "User canceled during package install."
0x2c8b4  stloc.s  0xB
0x2c8b6  ldloc.s  7
0x2c8b8  brfalse.s loc_2C8C3
0x2c8ba  ldloc.s  7
0x2c8bc  ldloc.s  0xB
0x2c8be  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x2c8c3  ldarg.0
0x2c8c4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2c8c9  ldloc.s  0xB
0x2c8cb  call     T0x2B000003
0x2c8d0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2c8d5  ldc.i4.7
0x2c8d6  ldc.i4.0
0x2c8d7  ldnull
0x2c8d8  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2c8dd  stloc.s  0xC
0x2c8df  leave    loc_2CA34
0x2c8e4  stloc.s  0xD
0x2c8e6  ldstr    aPackageInstall// "Package install Exception."
0x2c8eb  stloc.s  0xE
0x2c8ed  ldstr    aUnableToGetHas// "Unable to get Hash"
0x2c8f2  stloc.s  0xF
0x2c8f4  ldarg.0
0x2c8f5  ldarg.1
0x2c8f6  callvirt instance string InstallData::get_LocalPath()
0x2c8fb  ldloc.2
0x2c8fc  ldloca.s 0x10
0x2c8fe  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x2c903  brtrue.s loc_2C912
0x2c905  ldarg.1
0x2c906  callvirt instance string InstallData::get_InstallDir()
0x2c90b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::IsValidDirectoryPath(string)
0x2c910  brtrue.s loc_2C950
0x2c912  ldarg.0
  ... truncated ...
```
