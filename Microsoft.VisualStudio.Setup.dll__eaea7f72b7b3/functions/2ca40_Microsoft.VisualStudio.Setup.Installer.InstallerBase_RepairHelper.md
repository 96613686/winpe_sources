# Microsoft.VisualStudio.Setup.Installer.InstallerBase::RepairHelper

- ea: `0x2ca40`
- end: `0x2cdd8`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerBase::RepairHelper`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x280`
- `0x420`
- `0x11d60`
- `0x2b900`
- `0x2b920`
- `0x2b940`
- `0x2b9a0`
- `0x2b9c0`
- `0x2ba10`
- `0x2baa0`
- `0x2be90`
- `0x2c170`
- `0x2ca40`
- `0x2d260`
- `0x2d2d0`
- `0x3eb00`
- `0x6c790`
- `0x6c7b0`
- `0x6c7d0`
- `0x6c800`

## string_xrefs

- `0x2ca6b`: `Repair-Package`
- `0x2cc26`: `Repairing {0}`
- `0x2cd12`: `User canceled during package repair.`

## pseudocode

```c

```

## disassembly

```asm
0x2ca40  ldnull
0x2ca41  stloc.0
0x2ca42  ldarg.1
0x2ca43  ldarg.0
0x2ca44  dup
0x2ca45  ldvirtftn instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2ca4b  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs>::.ctor(object, native int)
0x2ca50  ldc.i4.2
0x2ca51  ldnull
0x2ca52  ldc.i4.1
0x2ca53  newobj   instance void DefaultProgressReport::.ctor(class InstallData pkgData, class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs> onProgress, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] string packageDisplayInfo, [opt] bool completeProgressInDispose)
0x2ca58  stloc.1
0x2ca59  ldarg.1
0x2ca5a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2ca5f  stloc.2
0x2ca60  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2ca65  dup
0x2ca66  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x2ca6b  ldstr    aRepairPackage// "Repair-Package"
0x2ca70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ca75  dup
0x2ca76  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEIDPROPERTY
0x2ca7b  ldloc.2
0x2ca7c  brtrue.s loc_2CA81
0x2ca7e  ldnull
0x2ca7f  br.s     loc_2CA87
0x2ca81  ldloc.2
0x2ca82  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2ca87  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ca8c  dup
0x2ca8d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEUNIQUEIDPROPERTY
0x2ca92  ldloc.2
0x2ca93  brtrue.s loc_2CA98
0x2ca95  ldnull
0x2ca96  br.s     loc_2CA9E
0x2ca98  ldloc.2
0x2ca99  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2ca9e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2caa3  dup
0x2caa4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGELANGUAGEPROPERTY
0x2caa9  ldloc.2
0x2caaa  brtrue.s loc_2CAAF
0x2caac  ldnull
0x2caad  br.s     loc_2CAB5
0x2caaf  ldloc.2
0x2cab0  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2cab5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2caba  dup
0x2cabb  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGESTATEPROPERTY
0x2cac0  ldloc.2
0x2cac1  brtrue.s loc_2CAC6
0x2cac3  ldnull
0x2cac4  br.s     loc_2CADB
0x2cac6  ldloc.2
0x2cac7  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_CurrentState()
0x2cacc  stloc.s  4
0x2cace  ldloca.s 4
0x2cad0  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x2cad6  callvirt instance string [mscorlib]System.Object::ToString()
0x2cadb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cae0  dup
0x2cae1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEREQUESTEDSTATEPROPERTY
0x2cae6  ldloc.2
0x2cae7  brtrue.s loc_2CAEC
0x2cae9  ldnull
0x2caea  br.s     loc_2CB01
0x2caec  ldloc.2
0x2caed  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x2caf2  stloc.s  5
0x2caf4  ldloca.s 5
0x2caf6  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState
0x2cafc  callvirt instance string [mscorlib]System.Object::ToString()
0x2cb01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb06  dup
0x2cb07  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGECHIPPROPERTY
0x2cb0c  ldloc.2
0x2cb0d  brtrue.s loc_2CB12
0x2cb0f  ldnull
0x2cb10  br.s     loc_2CB18
0x2cb12  ldloc.2
0x2cb13  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Chip()
0x2cb18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb1d  dup
0x2cb1e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEPRODUCTARCHPROPERTY
0x2cb23  ldloc.2
0x2cb24  brtrue.s loc_2CB29
0x2cb26  ldnull
0x2cb27  br.s     loc_2CB2F
0x2cb29  ldloc.2
0x2cb2a  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ProductArch()
0x2cb2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb34  dup
0x2cb35  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEMACHINEARCHPROPERTY
0x2cb3a  ldloc.2
0x2cb3b  brtrue.s loc_2CB40
0x2cb3d  ldnull
0x2cb3e  br.s     loc_2CB46
0x2cb40  ldloc.2
0x2cb41  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_MachineArch()
0x2cb46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb4b  dup
0x2cb4c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEVERSIONPROPERTY
0x2cb51  ldloc.2
0x2cb52  brtrue.s loc_2CB57
0x2cb54  ldnull
0x2cb55  br.s     loc_2CB5D
0x2cb57  ldloc.2
0x2cb58  call     instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x2cb5d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb62  dup
0x2cb63  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGETYPEPROPERTY
0x2cb68  ldloc.2
0x2cb69  brtrue.s loc_2CB77
0x2cb6b  ldloca.s 6
0x2cb6d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2cb73  ldloc.s  6
0x2cb75  br.s     loc_2CB82
0x2cb77  ldloc.2
0x2cb78  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Type()
0x2cb7d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>::.ctor(var<u1>)
0x2cb82  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2cb87  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cb8c  dup
0x2cb8d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x2cb92  ldloc.2
0x2cb93  brtrue.s loc_2CB98
0x2cb95  ldnull
0x2cb96  br.s     loc_2CBA8
0x2cb98  ldloc.2
0x2cb99  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_TelemetryCorrelatedParents()
0x2cb9e  ldstr    asc_82420// ";"
0x2cba3  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2cba8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cbad  dup
0x2cbae  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
0x2cbb3  ldloc.2
0x2cbb4  brtrue.s loc_2CBB9
0x2cbb6  ldnull
0x2cbb7  br.s     loc_2CBC9
0x2cbb9  ldloc.2
0x2cbba  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_AncestorWorkloads()
0x2cbbf  ldstr    asc_82420// ";"
0x2cbc4  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2cbc9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cbce  stloc.3
0x2cbcf  ldloc.3
0x2cbd0  ldarg.0
0x2cbd1  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_AdditionalTelemetryProperties()
0x2cbd6  call     T0x2B000064
0x2cbdb  ldarg.0
0x2cbdc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_TelemetryService()
0x2cbe1  dup
0x2cbe2  brtrue.s loc_2CBE8
0x2cbe4  pop
0x2cbe5  ldnull
0x2cbe6  br.s     loc_2CBF5
0x2cbe8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x2cbed  ldloc.3
0x2cbee  ldc.i4.0
0x2cbef  ldc.i4.0
0x2cbf0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x2cbf5  stloc.s  7
0x2cbf7  ldloc.2
0x2cbf8  brtrue.s loc_2CC20
0x2cbfa  ldarg.1
0x2cbfb  callvirt instance string InstallData::get_LocalPath()
0x2cc00  brtrue.s loc_2CC20
0x2cc02  ldloc.s  7
0x2cc04  brfalse.s loc_2CC12
0x2cc06  ldloc.s  7
0x2cc08  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::NULLPATHSTRING
0x2cc0d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2cc12  ldc.i4.4
0x2cc13  ldc.i4.0
0x2cc14  ldnull
0x2cc15  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2cc1a  stloc.0
0x2cc1b  br       loc_2CD0C
0x2cc20  ldarg.0
0x2cc21  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2cc26  ldstr    aRepairing0// "Repairing {0}"
0x2cc2b  ldc.i4.1
0x2cc2c  newarr   [mscorlib]System.Object
0x2cc31  dup
0x2cc32  ldc.i4.0
0x2cc33  ldarg.0
0x2cc34  ldarg.1
0x2cc35  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2cc3a  ldarg.1
0x2cc3b  callvirt instance string InstallData::get_LocalPath()
0x2cc40  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetPackageNameForLogging(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, string localPath)
0x2cc45  stelem.ref
0x2cc46  newobj   instance void Microsoft.VisualStudio.Setup.LogActionWrapper::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger log, string actionName, object[] args)
0x2cc4b  stloc.s  8
0x2cc4d  ldarg.1
0x2cc4e  callvirt instance string InstallData::get_InstallDir()
0x2cc53  stloc.s  9
0x2cc55  ldnull
0x2cc56  stloc.s  0xA
0x2cc58  ldarg.0
0x2cc59  call     instance class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_PolicyService()
0x2cc5e  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_DiagnosticMode()
0x2cc63  brfalse.s loc_2CC83
0x2cc65  ldloc.s  9
0x2cc67  ldarg.0
0x2cc68  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2cc6d  ldarg.0
0x2cc6e  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x2cc73  ldloc.s  7
0x2cc75  ldc.i4.0
0x2cc76  ldloc.2
0x2cc77  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2cc7c  call     class UsedDriveSpace UsedDriveSpace::MeasureSpaceBeforeOperation(string targetDir, class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.IEngineContext engineContext, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, bool logWatermark, string measurementScope)
0x2cc81  stloc.s  0xA
0x2cc83  ldarg.0
0x2cc84  ldloc.s  9
0x2cc86  ldloc.2
0x2cc87  ldarg.1
0x2cc88  callvirt instance string InstallData::get_LocalPath()
0x2cc8d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::RepairCore(string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string localPath)
0x2cc92  stloc.0
0x2cc93  ldloc.s  0xA
0x2cc95  brfalse.s loc_2CCA9
0x2cc97  ldloc.s  0xA
0x2cc99  ldloc.s  7
0x2cc9b  ldloc.s  9
0x2cc9d  ldarg.0
0x2cc9e  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x2cca3  call     instance class UsedDriveSpace UsedDriveSpace::MeasureSpaceAfterOperation(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation, string targetDir, class Microsoft.VisualStudio.Setup.IEngineContext engineContext)
0x2cca8  pop
0x2cca9  ldloc.0
0x2ccaa  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLRESULTPROPERTY
0x2ccaf  ldloc.s  7
0x2ccb1  brtrue.s loc_2CCB6
0x2ccb3  ldnull
0x2ccb4  br.s     loc_2CCBD
0x2ccb6  ldloc.s  7
0x2ccb8  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2ccbd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x2ccc2  ldloc.0
0x2ccc3  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult)
0x2ccc8  brfalse.s loc_2CCDD
0x2ccca  ldloc.s  7
0x2cccc  brfalse.s loc_2CCFE
0x2ccce  ldloc.s  7
0x2ccd0  ldloc.0
0x2ccd1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2ccd6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x2ccdb  br.s     loc_2CCFE
0x2ccdd  ldloc.s  7
0x2ccdf  brfalse.s loc_2CCFE
0x2cce1  ldloc.s  7
0x2cce3  ldstr    a01_0// "{0} - {1}"
0x2cce8  ldc.i4.2
0x2cce9  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x2ccee  ldloc.0
0x2ccef  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2ccf4  call     string [mscorlib]System.String::Format(string, object, object)
0x2ccf9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2ccfe  leave.s  loc_2CD0C
0x2cd00  ldloc.s  8
0x2cd02  brfalse.s loc_2CD0B
0x2cd04  ldloc.s  8
0x2cd06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cd0b  endfinally
0x2cd0c  leave    loc_2CDB7
0x2cd11  pop
0x2cd12  ldstr    aUserCanceledDu_2// "User canceled during package repair."
0x2cd17  stloc.s  0xB
0x2cd19  ldloc.s  7
0x2cd1b  brfalse.s loc_2CD26
0x2cd1d  ldloc.s  7
0x2cd1f  ldloc.s  0xB
0x2cd21  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x2cd26  ldarg.0
0x2cd27  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2cd2c  ldloc.s  0xB
0x2cd2e  call     T0x2B000003
0x2cd33  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2cd38  ldc.i4.7
0x2cd39  ldc.i4.0
0x2cd3a  ldnull
0x2cd3b  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2cd40  stloc.s  0xC
0x2cd42  leave    loc_2CDD5
0x2cd47  stloc.s  0xD
0x2cd49  ldloc.s  7
0x2cd4b  brfalse.s loc_2CD61
0x2cd4d  ldloc.s  7
0x2cd4f  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::EXCEPTIONSTRING
0x2cd54  ldloc.s  0xD
0x2cd56  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::EXCEPTIONSTRING
0x2cd5b  ldc.i4.1
0x2cd5c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x2cd61  ldarg.0
0x2cd62  ldarg.1
0x2cd63  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2cd68  ldc.i4.2
0x2cd69  ldloc.s  0xD
0x2cd6b  callvirt instance string [mscorlib]System.Object::ToString()
  ... truncated ...
```
