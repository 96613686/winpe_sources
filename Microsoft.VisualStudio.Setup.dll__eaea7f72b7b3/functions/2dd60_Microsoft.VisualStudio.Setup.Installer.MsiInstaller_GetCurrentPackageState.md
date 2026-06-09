# Microsoft.VisualStudio.Setup.Installer.MsiInstaller::GetCurrentPackageState

- ea: `0x2dd60`
- end: `0x2e2a7`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiInstaller::GetCurrentPackageState`
- size: `1351`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x27920`
- `0x2b940`
- `0x2bd80`
- `0x2be20`
- `0x2d380`
- `0x2dd60`
- `0x2ec40`
- `0x2ee80`
- `0x2feb0`

## string_xrefs

- `0x2de88`: `Windows Installer found the package '`
- `0x2de93`: `' superseded but corresponding compatible package information was not found. Attempts to repair will be skipped and that to uninstall may leave the cache behind.`
- `0x2e033`: `Related product associated with current upgrade table row did not pass the min version comparison test. Skipping to next related product if present on the system.`
- `0x2e099`: `Related product associated with current upgrade table row did not pass max version comparison test. Skipping to next related product if present on the system.`
- `0x2e0e9`: `Detected related package: {0}, but failed to read language: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2dd60  ldarg.0
0x2dd61  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::Initialize()
0x2dd66  ldarg.0
0x2dd67  ldarg.1
0x2dd68  call     T0x2B000174
0x2dd6d  stloc.0
0x2dd6e  ldarg.2
0x2dd6f  ldc.i4.1
0x2dd70  stind.i4
0x2dd71  ldc.i4.0
0x2dd72  stloc.1
0x2dd73  ldloc.0
0x2dd74  brfalse  loc_2E233
0x2dd79  ldloc.0
0x2dd7a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2dd7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dd84  brtrue   loc_2E233
0x2dd89  ldloc.0
0x2dd8a  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductVersion()
0x2dd8f  ldnull
0x2dd90  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2dd95  brfalse  loc_2E233
0x2dd9a  ldc.i4.0
0x2dd9b  stloc.2
0x2dd9c  ldloc.0
0x2dd9d  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductVersion()
0x2dda2  ldc.i4.1
0x2dda3  ldnull
0x2dda4  ldc.i4.0
0x2dda5  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::.ctor(class [mscorlib]System.Version, bool, class [mscorlib]System.Version, bool)
0x2ddaa  stloc.s  7
0x2ddac  ldloca.s 8
0x2ddae  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2ddb4  ldloc.0
0x2ddb5  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductLanguage()
0x2ddba  brfalse.s loc_2DDCB
0x2ddbc  ldloca.s 8
0x2ddbe  ldloc.0
0x2ddbf  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductLanguage()
0x2ddc4  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2ddc9  br.s     loc_2DDEF
0x2ddcb  ldloc.0
0x2ddcc  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2ddd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ddd6  brtrue.s loc_2DDEF
0x2ddd8  ldloca.s 8
0x2ddda  ldloc.0
0x2dddb  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Language()
0x2dde0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::GetCultureInfo(string)
0x2dde5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2ddea  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2ddef  ldarg.0
0x2ddf0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService Microsoft.VisualStudio.Setup.Installer.MsiInstaller::windowsInstallerService
0x2ddf5  ldloc.0
0x2ddf6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2ddfb  ldloc.0
0x2ddfc  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_UpgradeCode()
0x2de01  ldloc.s  7
0x2de03  ldloc.s  8
0x2de05  ldloca.s 0xA
0x2de07  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::GetPackageInstallState(string, string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange, valuetype [mscorlib]System.Nullable`1<int32>, class [mscorlib]System.Version&)
0x2de0c  stloc.s  9
0x2de0e  ldloc.s  9
0x2de10  brfalse.s loc_2DE19
0x2de12  ldarg.0
0x2de13  ldloc.0
0x2de14  call     instance void Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage package)
0x2de19  ldloc.s  9
0x2de1b  ldc.i4.2
0x2de1c  bne.un.s loc_2DE29
0x2de1e  ldarg.0
0x2de1f  ldloc.0
0x2de20  ldloc.s  0xA
0x2de22  ldloca.s 9
0x2de24  call     instance void Microsoft.VisualStudio.Setup.Installer.MsiInstaller::MarkSupersededAbsentIfApplicable(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage msi, class [mscorlib]System.Version installedVersion, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState& installState)
0x2de29  ldloc.s  9
0x2de2b  switch   loc_2DE6A, loc_2DE46, loc_2DE6F, loc_2DE63, loc_2DE4B
0x2de44  br.s     loc_2DEAC
0x2de46  ldarg.2
0x2de47  ldc.i4.1
0x2de48  stind.i4
0x2de49  br.s     loc_2DEAC
0x2de4b  ldc.i4.4
0x2de4c  ldc.i4   0x645
0x2de51  ldnull
0x2de52  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2de57  dup
0x2de58  ldstr    aSystemFailedTo// "System failed to get product info for g"...
0x2de5d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2de62  ret
0x2de63  ldc.i4.2
0x2de64  stloc.2
0x2de65  ldarg.2
0x2de66  ldc.i4.3
0x2de67  stind.i4
0x2de68  br.s     loc_2DEAC
0x2de6a  ldarg.2
0x2de6b  ldc.i4.0
0x2de6c  stind.i4
0x2de6d  br.s     loc_2DEAC
0x2de6f  ldloc.0
0x2de70  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_InstalledProductCode()
0x2de75  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2de7a  brfalse.s loc_2DEA7
0x2de7c  ldarg.0
0x2de7d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2de82  dup
0x2de83  brtrue.s loc_2DE88
0x2de85  pop
0x2de86  br.s     loc_2DEA7
0x2de88  ldstr    aWindowsInstall// "Windows Installer found the package '"
0x2de8d  ldloc.0
0x2de8e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2de93  ldstr    aSupersededButC// "' superseded but corresponding compatib"...
0x2de98  call     string [mscorlib]System.String::Concat(string, string, string)
0x2de9d  call     T0x2B000003
0x2dea2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2dea7  ldc.i4.1
0x2dea8  stloc.2
0x2dea9  ldarg.2
0x2deaa  ldc.i4.2
0x2deab  stind.i4
0x2deac  ldloc.0
0x2dead  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_RelatedPackages()
0x2deb2  brfalse  loc_2E231
0x2deb7  ldloc.0
0x2deb8  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_RelatedPackages()
0x2debd  call     T0x2B000175
0x2dec2  ldc.i4.0
0x2dec3  ble      loc_2E231
0x2dec8  ldarg.0
0x2dec9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2dece  ldstr    aScanningThroug// "Scanning through upgrade table now."
0x2ded3  call     T0x2B000003
0x2ded8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2dedd  ldc.i4.s 0x28
0x2dedf  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x2dee4  stloc.s  0xB
0x2dee6  ldloc.0
0x2dee7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_RelatedPackages()
0x2deec  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage>::GetEnumerator()
0x2def1  stloc.s  0xC
0x2def3  br       loc_2E217
0x2def8  ldloc.s  0xC
0x2defa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage>::get_Current()
0x2deff  stloc.s  0xD
0x2df01  ldnull
0x2df02  stloc.s  0xE
0x2df04  ldc.i4.0
0x2df05  stloc.s  0xF
0x2df07  ldloc.s  0xD
0x2df09  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Id()
0x2df0e  ldc.i4.0
0x2df0f  ldloc.s  0xF
0x2df11  ldloc.s  0xB
0x2df13  call     int32 Microsoft.VisualStudio.Setup.Installer.NativeMethods::MsiEnumRelatedProducts([hasfieldmarshal] string, int32 upgradeCode, [hasfieldmarshal] int32 dwReserved, [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder iProductIndex)
0x2df18  stloc.s  0x10
0x2df1a  ldloc.s  0x10
0x2df1c  ldc.i4   0x103
0x2df21  beq      loc_2E217
0x2df26  ldloc.s  0x10
0x2df28  brfalse.s loc_2DF45
0x2df2a  ldc.i4.4
0x2df2b  ldloc.s  0x10
0x2df2d  ldnull
0x2df2e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2df33  dup
0x2df34  ldstr    aSystemFailedTo_0// "System failed to query for the product "...
0x2df39  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2df3e  stloc.s  0x11
0x2df40  leave    loc_2E2A4
0x2df45  ldloc.0
0x2df46  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2df4b  ldloc.s  0xB
0x2df4d  callvirt instance string [mscorlib]System.Object::ToString()
0x2df52  ldc.i4.3
0x2df53  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2df58  brfalse.s loc_2DF74
0x2df5a  ldarg.0
0x2df5b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2df60  ldstr    aFoundSelfPacka// "Found self package. Skipping to next re"...
0x2df65  call     T0x2B000003
0x2df6a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2df6f  br       loc_2E20C
0x2df74  ldloc.s  0xB
0x2df76  callvirt instance string [mscorlib]System.Object::ToString()
0x2df7b  ldloca.s 0xE
0x2df7d  ldstr    aVersionstring// "VersionString"
0x2df82  call     int32 Microsoft.VisualStudio.Setup.Utility.WindowsInstallerUtil::GetProductInfo(string productCode, [out] string& propertyValue, [opt] string propertyName)
0x2df87  stloc.s  0x10
0x2df89  ldloc.s  0x10
0x2df8b  ldc.i4   0x645
0x2df90  beq.s    loc_2DFBA
0x2df92  ldloc.s  0x10
0x2df94  ldc.i4   0x648
0x2df99  beq.s    loc_2DFBA
0x2df9b  ldloc.s  0x10
0x2df9d  brfalse.s loc_2DFBA
0x2df9f  ldc.i4.4
0x2dfa0  ldloc.s  0x10
0x2dfa2  ldnull
0x2dfa3  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2dfa8  dup
0x2dfa9  ldstr    aSystemFailedTo_1// "System failed to retrieve version info "...
0x2dfae  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x2dfb3  stloc.s  0x11
0x2dfb5  leave    loc_2E2A4
0x2dfba  ldloc.s  0x10
0x2dfbc  brfalse.s loc_2DFD8
0x2dfbe  ldarg.0
0x2dfbf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2dfc4  ldstr    aSystemReturned// "System returned Unknown-Product\\Proper"...
0x2dfc9  call     T0x2B000003
0x2dfce  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2dfd3  br       loc_2E20C
0x2dfd8  ldloc.s  0xE
0x2dfda  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x2dfdf  stloc.s  5
0x2dfe1  ldloc.s  0xD
0x2dfe3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2dfe8  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Minimum()
0x2dfed  ldnull
0x2dfee  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2dff3  brfalse.s loc_2E047
0x2dff5  ldloc.s  0xD
0x2dff7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2dffc  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_IsMinimumInclusive()
0x2e001  brtrue.s loc_2E018
0x2e003  ldloc.s  5
0x2e005  ldloc.s  0xD
0x2e007  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e00c  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Minimum()
0x2e011  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2e016  br.s     loc_2E02B
0x2e018  ldloc.s  5
0x2e01a  ldloc.s  0xD
0x2e01c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e021  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Minimum()
0x2e026  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2e02b  brfalse.s loc_2E047
0x2e02d  ldarg.0
0x2e02e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e033  ldstr    aRelatedProduct// "Related product associated with current"...
0x2e038  call     T0x2B000003
0x2e03d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2e042  br       loc_2E20C
0x2e047  ldloc.s  0xD
0x2e049  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e04e  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Maximum()
0x2e053  ldnull
0x2e054  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2e059  brfalse.s loc_2E0AD
0x2e05b  ldloc.s  0xD
0x2e05d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e062  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_IsMaximumInclusive()
0x2e067  brtrue.s loc_2E07E
0x2e069  ldloc.s  5
0x2e06b  ldloc.s  0xD
0x2e06d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e072  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Maximum()
0x2e077  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2e07c  br.s     loc_2E091
0x2e07e  ldloc.s  5
0x2e080  ldloc.s  0xD
0x2e082  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_Version()
0x2e087  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange::get_Maximum()
0x2e08c  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2e091  brfalse.s loc_2E0AD
0x2e093  ldarg.0
0x2e094  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e099  ldstr    aRelatedProduct_0// "Related product associated with current"...
0x2e09e  call     T0x2B000003
0x2e0a3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2e0a8  br       loc_2E20C
0x2e0ad  ldnull
0x2e0ae  stloc.s  4
0x2e0b0  ldc.i4.0
0x2e0b1  stloc.s  6
0x2e0b3  ldloc.s  0xD
0x2e0b5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RelatedPackage::get_LanguageIds()
0x2e0ba  brfalse  loc_2E196
0x2e0bf  ldloc.s  0xB
0x2e0c1  callvirt instance string [mscorlib]System.Object::ToString()
0x2e0c6  ldloca.s 4
0x2e0c8  ldstr    aLanguage// "Language"
0x2e0cd  call     int32 Microsoft.VisualStudio.Setup.Utility.WindowsInstallerUtil::GetProductInfo(string productCode, [out] string& propertyValue, [opt] string propertyName)
0x2e0d2  stloc.s  0x10
0x2e0d4  ldloc.s  0x10
0x2e0d6  brtrue.s loc_2E0E3
0x2e0d8  ldloc.s  4
0x2e0da  ldloca.s 6
0x2e0dc  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x2e0e1  brtrue.s loc_2E10D
0x2e0e3  ldarg.0
0x2e0e4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2e0e9  ldstr    aDetectedRelate// "Detected related package: {0}, but fail"...
0x2e0ee  ldc.i4.2
0x2e0ef  newarr   [mscorlib]System.Object
0x2e0f4  dup
0x2e0f5  ldc.i4.0
  ... truncated ...
```
