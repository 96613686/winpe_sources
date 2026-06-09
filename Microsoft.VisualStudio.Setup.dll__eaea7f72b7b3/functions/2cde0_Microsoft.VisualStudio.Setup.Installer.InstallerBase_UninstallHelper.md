# Microsoft.VisualStudio.Setup.Installer.InstallerBase::UninstallHelper

- ea: `0x2cde0`
- end: `0x2d1aa`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerBase::UninstallHelper`
- size: `970`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11d60`
- `0x2af00`
- `0x2b940`
- `0x2b9a0`
- `0x2ba10`
- `0x2baa0`
- `0x2bea0`
- `0x2c170`
- `0x2cde0`
- `0x2d260`
- `0x2d2d0`
- `0x6c790`
- `0x6c7b0`
- `0x6c7d0`
- `0x6c800`

## string_xrefs

- `0x2ce2a`: `Skipping uninstall of '`
- `0x2ce63`: `Uninstall-Package`
- `0x2d026`: `Uninstalling {0}`
- `0x2d0d0`: `User canceled during package uninstall.`

## pseudocode

```c

```

## disassembly

```asm
0x2cde0  ldnull
0x2cde1  stloc.0
0x2cde2  ldarg.1
0x2cde3  ldarg.0
0x2cde4  dup
0x2cde5  ldvirtftn instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2cdeb  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs>::.ctor(object, native int)
0x2cdf0  ldc.i4.3
0x2cdf1  ldnull
0x2cdf2  ldc.i4.1
0x2cdf3  newobj   instance void DefaultProgressReport::.ctor(class InstallData pkgData, class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs> onProgress, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] string packageDisplayInfo, [opt] bool completeProgressInDispose)
0x2cdf8  stloc.1
0x2cdf9  ldarg.1
0x2cdfa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2cdff  stloc.2
0x2ce00  ldarg.0
0x2ce01  ldloc.2
0x2ce02  call     T0x2B00016F
0x2ce07  stloc.3
0x2ce08  ldc.i4.0
0x2ce09  stloc.s  4
0x2ce0b  ldloc.3
0x2ce0c  brfalse.s loc_2CE13
0x2ce0e  ldloc.3
0x2ce0f  stloc.2
0x2ce10  ldc.i4.1
0x2ce11  stloc.s  4
0x2ce13  ldloc.2
0x2ce14  brfalse.s loc_2CE58
0x2ce16  ldloc.2
0x2ce17  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsPermanent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package)
0x2ce1c  brfalse.s loc_2CE58
0x2ce1e  ldarg.0
0x2ce1f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2ce24  dup
0x2ce25  brtrue.s loc_2CE2A
0x2ce27  pop
0x2ce28  br.s     loc_2CE49
0x2ce2a  ldstr    aSkippingUninst// "Skipping uninstall of '"
0x2ce2f  ldloc.2
0x2ce30  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2ce35  ldstr    aBecauseItIsPer// "' because it is permanent."
0x2ce3a  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ce3f  call     T0x2B000003
0x2ce44  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2ce49  ldc.i4.1
0x2ce4a  ldc.i4.0
0x2ce4b  ldnull
0x2ce4c  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2ce51  stloc.s  6
0x2ce53  leave    loc_2D1A7
0x2ce58  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2ce5d  dup
0x2ce5e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x2ce63  ldstr    aUninstallPacka// "Uninstall-Package"
0x2ce68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ce6d  dup
0x2ce6e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEIDPROPERTY
0x2ce73  ldloc.2
0x2ce74  brtrue.s loc_2CE79
0x2ce76  ldnull
0x2ce77  br.s     loc_2CE7F
0x2ce79  ldloc.2
0x2ce7a  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2ce7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ce84  dup
0x2ce85  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEUNIQUEIDPROPERTY
0x2ce8a  ldloc.2
0x2ce8b  brtrue.s loc_2CE90
0x2ce8d  ldnull
0x2ce8e  br.s     loc_2CE96
0x2ce90  ldloc.2
0x2ce91  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2ce96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ce9b  dup
0x2ce9c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGELANGUAGEPROPERTY
0x2cea1  ldloc.2
0x2cea2  brtrue.s loc_2CEA7
0x2cea4  ldnull
0x2cea5  br.s     loc_2CEAD
0x2cea7  ldloc.2
0x2cea8  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2cead  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ceb2  dup
0x2ceb3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGESTATEPROPERTY
0x2ceb8  ldloc.2
0x2ceb9  brtrue.s loc_2CEBE
0x2cebb  ldnull
0x2cebc  br.s     loc_2CED3
0x2cebe  ldloc.2
0x2cebf  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_CurrentState()
0x2cec4  stloc.s  7
0x2cec6  ldloca.s 7
0x2cec8  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState
0x2cece  callvirt instance string [mscorlib]System.Object::ToString()
0x2ced3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2ced8  dup
0x2ced9  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEREQUESTEDSTATEPROPERTY
0x2cede  ldloc.2
0x2cedf  brtrue.s loc_2CEE4
0x2cee1  ldnull
0x2cee2  br.s     loc_2CEF9
0x2cee4  ldloc.2
0x2cee5  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x2ceea  stloc.s  8
0x2ceec  ldloca.s 8
0x2ceee  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState
0x2cef4  callvirt instance string [mscorlib]System.Object::ToString()
0x2cef9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cefe  dup
0x2ceff  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGECHIPPROPERTY
0x2cf04  ldloc.2
0x2cf05  brtrue.s loc_2CF0A
0x2cf07  ldnull
0x2cf08  br.s     loc_2CF10
0x2cf0a  ldloc.2
0x2cf0b  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Chip()
0x2cf10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cf15  dup
0x2cf16  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEPRODUCTARCHPROPERTY
0x2cf1b  ldloc.2
0x2cf1c  brtrue.s loc_2CF21
0x2cf1e  ldnull
0x2cf1f  br.s     loc_2CF27
0x2cf21  ldloc.2
0x2cf22  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_ProductArch()
0x2cf27  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cf2c  dup
0x2cf2d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEMACHINEARCHPROPERTY
0x2cf32  ldloc.2
0x2cf33  brtrue.s loc_2CF38
0x2cf35  ldnull
0x2cf36  br.s     loc_2CF3E
0x2cf38  ldloc.2
0x2cf39  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_MachineArch()
0x2cf3e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cf43  dup
0x2cf44  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEVERSIONPROPERTY
0x2cf49  ldloc.2
0x2cf4a  brtrue.s loc_2CF4F
0x2cf4c  ldnull
0x2cf4d  br.s     loc_2CF55
0x2cf4f  ldloc.2
0x2cf50  call     instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x2cf55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cf5a  dup
0x2cf5b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGETYPEPROPERTY
0x2cf60  ldloc.2
0x2cf61  brtrue.s loc_2CF6F
0x2cf63  ldloca.s 9
0x2cf65  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2cf6b  ldloc.s  9
0x2cf6d  br.s     loc_2CF7A
0x2cf6f  ldloc.2
0x2cf70  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Type()
0x2cf75  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>::.ctor(var<u1>)
0x2cf7a  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType>
0x2cf7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cf84  dup
0x2cf85  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PARENTSPROPERTY
0x2cf8a  ldloc.2
0x2cf8b  brtrue.s loc_2CF90
0x2cf8d  ldnull
0x2cf8e  br.s     loc_2CFA0
0x2cf90  ldloc.2
0x2cf91  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_TelemetryCorrelatedParents()
0x2cf96  ldstr    asc_82420// ";"
0x2cf9b  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2cfa0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cfa5  dup
0x2cfa6  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ANCESTORWORKLOADSPROPERTY
0x2cfab  ldloc.2
0x2cfac  brtrue.s loc_2CFB1
0x2cfae  ldnull
0x2cfaf  br.s     loc_2CFC1
0x2cfb1  ldloc.2
0x2cfb2  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_AncestorWorkloads()
0x2cfb7  ldstr    asc_82420// ";"
0x2cfbc  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::TryJoin(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x2cfc1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2cfc6  stloc.s  5
0x2cfc8  ldloc.s  5
0x2cfca  ldarg.0
0x2cfcb  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_AdditionalTelemetryProperties()
0x2cfd0  call     T0x2B000064
0x2cfd5  ldarg.0
0x2cfd6  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_TelemetryService()
0x2cfdb  dup
0x2cfdc  brtrue.s loc_2CFE2
0x2cfde  pop
0x2cfdf  ldnull
0x2cfe0  br.s     loc_2CFF0
0x2cfe2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x2cfe7  ldloc.s  5
0x2cfe9  ldc.i4.0
0x2cfea  ldc.i4.0
0x2cfeb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x2cff0  stloc.s  0xA
0x2cff2  ldarg.1
0x2cff3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2cff8  brtrue.s loc_2D020
0x2cffa  ldarg.1
0x2cffb  callvirt instance string InstallData::get_LocalPath()
0x2d000  brtrue.s loc_2D020
0x2d002  ldloc.s  0xA
0x2d004  brfalse.s loc_2D012
0x2d006  ldloc.s  0xA
0x2d008  ldsfld   string Microsoft.VisualStudio.Setup.Services.TelemetryOperationBase::NULLPATHSTRING
0x2d00d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2d012  ldc.i4.4
0x2d013  ldc.i4.0
0x2d014  ldnull
0x2d015  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2d01a  stloc.0
0x2d01b  br       loc_2D0CA
0x2d020  ldarg.0
0x2d021  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2d026  ldstr    aUninstalling0// "Uninstalling {0}"
0x2d02b  ldc.i4.1
0x2d02c  newarr   [mscorlib]System.Object
0x2d031  dup
0x2d032  ldc.i4.0
0x2d033  ldarg.0
0x2d034  ldarg.1
0x2d035  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage InstallData::get_Pkg()
0x2d03a  ldarg.1
0x2d03b  callvirt instance string InstallData::get_LocalPath()
0x2d040  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetPackageNameForLogging(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, string localPath)
0x2d045  stelem.ref
0x2d046  newobj   instance void Microsoft.VisualStudio.Setup.LogActionWrapper::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger log, string actionName, object[] args)
0x2d04b  stloc.s  0xB
0x2d04d  ldarg.1
0x2d04e  callvirt instance string InstallData::get_InstallDir()
0x2d053  stloc.s  0xC
0x2d055  ldarg.0
0x2d056  ldloc.s  0xC
0x2d058  ldloc.2
0x2d059  ldarg.1
0x2d05a  callvirt instance string InstallData::get_LocalPath()
0x2d05f  ldloc.s  4
0x2d061  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.InstallerBase::UninstallCore(string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [opt] string localPath, [opt] bool isManifestCached)
0x2d066  stloc.0
0x2d067  ldloc.0
0x2d068  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::INSTALLRESULTPROPERTY
0x2d06d  ldloc.s  0xA
0x2d06f  brtrue.s loc_2D074
0x2d071  ldnull
0x2d072  br.s     loc_2D07B
0x2d074  ldloc.s  0xA
0x2d076  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x2d07b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x2d080  ldloc.0
0x2d081  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult)
0x2d086  brfalse.s loc_2D09B
0x2d088  ldloc.s  0xA
0x2d08a  brfalse.s loc_2D0BC
0x2d08c  ldloc.s  0xA
0x2d08e  ldloc.0
0x2d08f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2d094  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x2d099  br.s     loc_2D0BC
0x2d09b  ldloc.s  0xA
0x2d09d  brfalse.s loc_2D0BC
0x2d09f  ldloc.s  0xA
0x2d0a1  ldstr    a01_0// "{0} - {1}"
0x2d0a6  ldc.i4.2
0x2d0a7  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x2d0ac  ldloc.0
0x2d0ad  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x2d0b2  call     string [mscorlib]System.String::Format(string, object, object)
0x2d0b7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x2d0bc  leave.s  loc_2D0CA
0x2d0be  ldloc.s  0xB
0x2d0c0  brfalse.s loc_2D0C9
0x2d0c2  ldloc.s  0xB
0x2d0c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d0c9  endfinally
0x2d0ca  leave    loc_2D175
0x2d0cf  pop
0x2d0d0  ldstr    aUserCanceledDu_3// "User canceled during package uninstall."
0x2d0d5  stloc.s  0xD
0x2d0d7  ldloc.s  0xA
0x2d0d9  brfalse.s loc_2D0E4
0x2d0db  ldloc.s  0xA
0x2d0dd  ldloc.s  0xD
0x2d0df  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x2d0e4  ldarg.0
0x2d0e5  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2d0ea  ldloc.s  0xD
0x2d0ec  call     T0x2B000003
0x2d0f1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2d0f6  ldc.i4.7
0x2d0f7  ldc.i4.0
0x2d0f8  ldnull
0x2d0f9  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2d0fe  stloc.s  6
0x2d100  leave    loc_2D1A7
0x2d105  stloc.s  0xE
0x2d107  ldloc.s  0xA
0x2d109  brfalse.s loc_2D11F
  ... truncated ...
```
