# Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage

- ea: `0x2ec40`
- end: `0x2edb4`
- name: `Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage`
- size: `372`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2dd60`
- `0x2e370`
- `0x2e4f0`

## callees

- `0x2b920`
- `0x2b940`
- `0x2ec40`
- `0x2edc0`

## string_xrefs

- `0x2ec46`: `Services`
- `0x2ecb2`: `Compatible ProductCode '`
- `0x2ed4d`: `Compatible package version is less than or equal to the package version. Code '`
- `0x2ed53`: `' will not be used for repair/uninstall attempts.`
- `0x2ed79`: `' will not be used for repair/uninstall attempts.`
- `0x2ed9f`: `' will not be used for repair/uninstall attempts.`
- `0x2ed73`: `Compatible package version information could not be found. Code '`
- `0x2ed99`: `Compatible package is not installed. Code '`

## pseudocode

```c

```

## disassembly

```asm
0x2ec40  ldarg.0
0x2ec41  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2ec46  ldstr    aServices_0// "Services"
0x2ec4b  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x2ec50  ldarg.0
0x2ec51  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2ec56  ldc.i4.1
0x2ec57  call     T0x2B00004C
0x2ec5c  stloc.0
0x2ec5d  ldloc.0
0x2ec5e  ldarg.1
0x2ec5f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductCode()
0x2ec64  ldloca.s 2
0x2ec66  ldstr    aVersionstring// "VersionString"
0x2ec6b  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::GetProductInfo(string, string&, string)
0x2ec70  stloc.1
0x2ec71  ldloc.1
0x2ec72  ldc.i4   0x645
0x2ec77  beq.s    loc_2EC84
0x2ec79  ldloc.1
0x2ec7a  ldc.i4   0x648
0x2ec7f  bne.un   loc_2EDB3
0x2ec84  ldarg.0
0x2ec85  ldarg.1
0x2ec86  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_ProviderKey()
0x2ec8b  ldloca.s 4
0x2ec8d  call     instance string Microsoft.VisualStudio.Setup.Installer.MsiInstaller::DetectCompatiblePackage(string providerKeyStr, [out] string& packageId)
0x2ec92  stloc.3
0x2ec93  ldloc.3
0x2ec94  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ec99  brtrue   loc_2EDB3
0x2ec9e  ldarg.0
0x2ec9f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2eca4  dup
0x2eca5  brtrue.s loc_2ECAA
0x2eca7  pop
0x2eca8  br.s     loc_2ECE4
0x2ecaa  ldc.i4.5
0x2ecab  newarr   [mscorlib]System.String
0x2ecb0  dup
0x2ecb1  ldc.i4.0
0x2ecb2  ldstr    aCompatibleProd// "Compatible ProductCode '"
0x2ecb7  stelem.ref
0x2ecb8  dup
0x2ecb9  ldc.i4.1
0x2ecba  ldloc.3
0x2ecbb  stelem.ref
0x2ecbc  dup
0x2ecbd  ldc.i4.2
0x2ecbe  ldstr    aFoundForPackag// "' found for package '"
0x2ecc3  stelem.ref
0x2ecc4  dup
0x2ecc5  ldc.i4.3
0x2ecc6  ldarg.1
0x2ecc7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2eccc  stelem.ref
0x2eccd  dup
0x2ecce  ldc.i4.4
0x2eccf  ldstr    asc_7FEB6// "'"
0x2ecd4  stelem.ref
0x2ecd5  call     string [mscorlib]System.String::Concat(string[])
0x2ecda  call     T0x2B000003
0x2ecdf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2ece4  ldloc.0
0x2ece5  ldloc.3
0x2ece6  ldloca.s 5
0x2ece8  ldstr    aVersionstring// "VersionString"
0x2eced  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IWindowsInstallerService::GetProductInfo(string, string&, string)
0x2ecf2  stloc.1
0x2ecf3  ldloc.1
0x2ecf4  brtrue   loc_2ED8E
0x2ecf9  ldloc.s  5
0x2ecfb  ldloca.s 6
0x2ecfd  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x2ed02  brfalse.s loc_2ED68
0x2ed04  ldarg.1
0x2ed05  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::get_ProductVersion()
0x2ed0a  ldloc.s  6
0x2ed0c  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2ed11  brfalse.s loc_2ED42
0x2ed13  ldarg.1
0x2ed14  ldloc.3
0x2ed15  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::set_InstalledProductCode(string)
0x2ed1a  ldarg.1
0x2ed1b  ldloc.s  6
0x2ed1d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::set_InstalledVersion(class [mscorlib]System.Version)
0x2ed22  ldloc.s  4
0x2ed24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ed29  brtrue   loc_2EDB3
0x2ed2e  ldloc.s  4
0x2ed30  ldloca.s 7
0x2ed32  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentity::TryParse(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity&)
0x2ed37  brfalse.s loc_2EDB3
0x2ed39  ldarg.1
0x2ed3a  ldloc.s  7
0x2ed3c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.MsiPackage::set_InstalledPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity)
0x2ed41  ret
0x2ed42  ldarg.0
0x2ed43  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2ed48  dup
0x2ed49  brtrue.s loc_2ED4D
0x2ed4b  pop
0x2ed4c  ret
0x2ed4d  ldstr    aCompatiblePack// "Compatible package version is less than"...
0x2ed52  ldloc.3
0x2ed53  ldstr    aWillNotBeUsedF// "' will not be used for repair/uninstall"...
0x2ed58  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ed5d  call     T0x2B000003
0x2ed62  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2ed67  ret
0x2ed68  ldarg.0
0x2ed69  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2ed6e  dup
0x2ed6f  brtrue.s loc_2ED73
0x2ed71  pop
0x2ed72  ret
0x2ed73  ldstr    aCompatiblePack_0// "Compatible package version information "...
0x2ed78  ldloc.3
0x2ed79  ldstr    aWillNotBeUsedF// "' will not be used for repair/uninstall"...
0x2ed7e  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ed83  call     T0x2B000003
0x2ed88  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2ed8d  ret
0x2ed8e  ldarg.0
0x2ed8f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2ed94  dup
0x2ed95  brtrue.s loc_2ED99
0x2ed97  pop
0x2ed98  ret
0x2ed99  ldstr    aCompatiblePack_1// "Compatible package is not installed. Co"...
0x2ed9e  ldloc.3
0x2ed9f  ldstr    aWillNotBeUsedF// "' will not be used for repair/uninstall"...
0x2eda4  call     string [mscorlib]System.String::Concat(string, string, string)
0x2eda9  call     T0x2B000003
0x2edae  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2edb3  ret
```
