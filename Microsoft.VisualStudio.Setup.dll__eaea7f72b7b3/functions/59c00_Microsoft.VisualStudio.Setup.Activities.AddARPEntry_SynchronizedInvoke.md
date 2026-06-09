# Microsoft.VisualStudio.Setup.Activities.AddARPEntry::SynchronizedInvoke

- ea: `0x59c00`
- end: `0x59fa4`
- name: `Microsoft.VisualStudio.Setup.Activities.AddARPEntry::SynchronizedInvoke`
- size: `932`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x103b0`
- `0x292b0`
- `0x596f0`
- `0x59c00`
- `0x59fb0`
- `0x5a080`
- `0x5a0c0`
- `0x5a110`

## string_xrefs

- `0x59ccb`: `InstallDate`
- `0x59db9`: `InstallDate`
- `0x59d24`: `Updated existing properties for Add/Remove Programs key: `
- `0x59d68`: `Unable to create the subkey for path: `
- `0x59ddc`: `InstallLocation`
- `0x59ec5`: `UninstallString`
- `0x59ecc`: ` uninstall --installPath "`
- `0x59ef1`: `ModifyPath`
- `0x59ef8`: ` modify --installPath "`
- `0x59f1d`: `RepairPath`
- `0x59f24`: ` repair --installPath "`
- `0x59f4b`: `Created new Add/Remove Program key: `
- `0x59f87`: `Unable to write Add/Remove Program entry for this instance: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x59c00  ldarg.0
0x59c01  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x59c06  ldc.i4.0
0x59c07  call     T0x2B00005B
0x59c0c  stloc.0
0x59c0d  ldarg.0
0x59c0e  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x59c13  ldc.i4.0
0x59c14  call     T0x2B000001
0x59c19  stloc.1
0x59c1a  ldarg.0
0x59c1b  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x59c20  ldc.i4.0
0x59c21  call     T0x2B0000A0
0x59c26  stloc.2
0x59c27  ldarg.0
0x59c28  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x59c2d  ldc.i4.0
0x59c2e  call     T0x2B00000C
0x59c33  dup
0x59c34  brtrue.s loc_59C3C
0x59c36  pop
0x59c37  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x59c3c  stloc.3
0x59c3d  ldloc.0
0x59c3e  brfalse.s loc_59C43
0x59c40  ldloc.2
0x59c41  brtrue.s loc_59C44
0x59c43  ret
0x59c44  ldarg.0
0x59c45  call     instance string Microsoft.VisualStudio.Setup.Activities.ARPEntryBase::GetARPInstanceKey()
0x59c4a  stloc.s  4
0x59c4c  ldloc.2
0x59c4d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x59c52  stloc.s  5
0x59c54  ldloc.s  5
0x59c56  brfalse.s loc_59C70
0x59c58  ldloc.s  5
0x59c5a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallDate()
0x59c5f  ldloca.s 7
0x59c61  initobj  [mscorlib]System.DateTime
0x59c67  ldloc.s  7
0x59c69  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x59c6e  brtrue.s loc_59C77
0x59c70  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x59c75  br.s     loc_59C7E
0x59c77  ldloc.s  5
0x59c79  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallDate()
0x59c7e  stloc.s  6
0x59c80  ldarg.0
0x59c81  call     instance void Microsoft.VisualStudio.Setup.Activities.ARPEntryBase::RemoveDuplicateRegKey()
0x59c86  ldloc.0
0x59c87  brtrue.s loc_59C8C
0x59c89  ldnull
0x59c8a  br.s     loc_59C94
0x59c8c  ldloc.0
0x59c8d  ldc.i4.2
0x59c8e  ldc.i4.1
0x59c8f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x59c94  stloc.s  8
0x59c96  ldarg.0
0x59c97  ldloc.s  5
0x59c99  call     instance string Microsoft.VisualStudio.Setup.Activities.AddARPEntry::GetArpVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance instance)
0x59c9e  stloc.s  9
0x59ca0  ldloc.s  8
0x59ca2  brtrue.s loc_59CA7
0x59ca4  ldnull
0x59ca5  br.s     loc_59CB1
0x59ca7  ldloc.s  8
0x59ca9  ldloc.s  4
0x59cab  ldc.i4.1
0x59cac  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x59cb1  stloc.s  0xA
0x59cb3  ldloc.s  0xA
0x59cb5  brfalse  loc_59D3F
0x59cba  ldloc.s  0xA
0x59cbc  ldstr    aDisplayversion// "DisplayVersion"
0x59cc1  ldloc.s  9
0x59cc3  ldc.i4.0
0x59cc4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59cc9  ldloc.s  0xA
0x59ccb  ldstr    aInstalldate// "InstallDate"
0x59cd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59cd5  ldstr    a0Yyyymmdd// "{0:yyyyMMdd}"
0x59cda  ldloc.s  6
0x59cdc  box      [mscorlib]System.DateTime
0x59ce1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x59ce6  ldc.i4.0
0x59ce7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59cec  ldloc.s  5
0x59cee  brtrue.s loc_59CF3
0x59cf0  ldnull
0x59cf1  br.s     loc_59CFB
0x59cf3  ldloc.s  5
0x59cf5  ldnull
0x59cf6  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::GetDisplayName(class [mscorlib]System.Globalization.CultureInfo)
0x59cfb  stloc.s  0xB
0x59cfd  ldloc.s  0xB
0x59cff  ldarg.0
0x59d00  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Activities.AddARPEntry::properties
0x59d05  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x59d0a  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::FormatDisplayName(string displayName, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> propertyBag)
0x59d0f  stloc.s  0xB
0x59d11  ldloc.s  0xA
0x59d13  ldstr    aDisplayname// "DisplayName"
0x59d18  ldloc.s  0xB
0x59d1a  ldc.i4.0
0x59d1b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59d20  ldloc.1
0x59d21  brfalse.s loc_59D3A
0x59d23  ldloc.1
0x59d24  ldstr    aUpdatedExistin// "Updated existing properties for Add/Rem"...
0x59d29  ldloc.s  4
0x59d2b  call     string [mscorlib]System.String::Concat(string, string)
0x59d30  call     T0x2B000003
0x59d35  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x59d3a  leave    loc_59FA3
0x59d3f  leave.s  loc_59D4D
0x59d41  ldloc.s  0xA
0x59d43  brfalse.s loc_59D4C
0x59d45  ldloc.s  0xA
0x59d47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59d4c  endfinally
0x59d4d  ldloc.s  8
0x59d4f  brtrue.s loc_59D54
0x59d51  ldnull
0x59d52  br.s     loc_59D5E
0x59d54  ldloc.s  8
0x59d56  ldloc.s  4
0x59d58  ldc.i4.0
0x59d59  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x59d5e  stloc.s  0xC
0x59d60  ldloc.s  0xC
0x59d62  brtrue.s loc_59D83
0x59d64  ldloc.1
0x59d65  brfalse.s loc_59D7E
0x59d67  ldloc.1
0x59d68  ldstr    aUnableToCreate_3// "Unable to create the subkey for path: "
0x59d6d  ldloc.s  4
0x59d6f  call     string [mscorlib]System.String::Concat(string, string)
0x59d74  call     T0x2B000003
0x59d79  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x59d7e  leave    loc_59FA3
0x59d83  ldloc.s  5
0x59d85  brtrue.s loc_59D8A
0x59d87  ldnull
0x59d88  br.s     loc_59D92
0x59d8a  ldloc.s  5
0x59d8c  ldnull
0x59d8d  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::GetDisplayName(class [mscorlib]System.Globalization.CultureInfo)
0x59d92  stloc.s  0xD
0x59d94  ldloc.s  0xD
0x59d96  ldarg.0
0x59d97  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Activities.AddARPEntry::properties
0x59d9c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x59da1  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::FormatDisplayName(string displayName, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> propertyBag)
0x59da6  stloc.s  0xD
0x59da8  ldloc.s  0xC
0x59daa  ldstr    aDisplayname// "DisplayName"
0x59daf  ldloc.s  0xD
0x59db1  ldc.i4.0
0x59db2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59db7  ldloc.s  0xC
0x59db9  ldstr    aInstalldate// "InstallDate"
0x59dbe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59dc3  ldstr    a0Yyyymmdd// "{0:yyyyMMdd}"
0x59dc8  ldloc.s  6
0x59dca  box      [mscorlib]System.DateTime
0x59dcf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x59dd4  ldc.i4.0
0x59dd5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59dda  ldloc.s  0xC
0x59ddc  ldstr    aInstalllocatio// "InstallLocation"
0x59de1  ldloc.s  5
0x59de3  brtrue.s loc_59DE8
0x59de5  ldnull
0x59de6  br.s     loc_59DEF
0x59de8  ldloc.s  5
0x59dea  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59def  ldc.i4.0
0x59df0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59df5  ldloc.s  0xC
0x59df7  ldstr    aDisplayversion// "DisplayVersion"
0x59dfc  ldloc.s  9
0x59dfe  ldc.i4.0
0x59dff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59e04  ldloc.s  0xC
0x59e06  ldstr    aPublisher// "Publisher"
0x59e0b  ldstr    aMicrosoftCorpo// "Microsoft Corporation"
0x59e10  ldc.i4.0
0x59e11  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59e16  ldloc.3
0x59e17  call     string Microsoft.VisualStudio.Setup.Extensions::GetInstallerPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x59e1c  stloc.s  0xE
0x59e1e  ldstr    asc_8B518// "\""
0x59e23  ldloc.s  0xE
0x59e25  ldstr    asc_8B518// "\""
0x59e2a  call     string [mscorlib]System.String::Concat(string, string, string)
0x59e2f  stloc.s  0xF
0x59e31  ldarg.0
0x59e32  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product Microsoft.VisualStudio.Setup.Activities.ARPEntryBase::get_Product()
0x59e37  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product::get_LaunchParams()
0x59e3c  dup
0x59e3d  brtrue.s loc_59E43
0x59e3f  pop
0x59e40  ldnull
0x59e41  br.s     loc_59E48
0x59e43  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_FileName()
0x59e48  stloc.s  0x10
0x59e4a  ldarg.0
0x59e4b  ldfld    string Microsoft.VisualStudio.Setup.Activities.AddARPEntry::authoredIconPath
0x59e50  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59e55  brtrue.s loc_59E83
0x59e57  ldloc.s  5
0x59e59  brtrue.s loc_59E5E
0x59e5b  ldnull
0x59e5c  br.s     loc_59E65
0x59e5e  ldloc.s  5
0x59e60  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59e65  ldarg.0
0x59e66  ldfld    string Microsoft.VisualStudio.Setup.Activities.AddARPEntry::authoredIconPath
0x59e6b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x59e70  stloc.s  0x11
0x59e72  ldloc.s  0xC
0x59e74  ldstr    aDisplayicon// "DisplayIcon"
0x59e79  ldloc.s  0x11
0x59e7b  ldc.i4.0
0x59e7c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59e81  br.s     loc_59EC3
0x59e83  ldloc.s  0x10
0x59e85  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59e8a  brtrue.s loc_59EB4
0x59e8c  ldloc.s  5
0x59e8e  brtrue.s loc_59E93
0x59e90  ldnull
0x59e91  br.s     loc_59E9A
0x59e93  ldloc.s  5
0x59e95  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59e9a  ldloc.s  0x10
0x59e9c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x59ea1  stloc.s  0x12
0x59ea3  ldloc.s  0xC
0x59ea5  ldstr    aDisplayicon// "DisplayIcon"
0x59eaa  ldloc.s  0x12
0x59eac  ldc.i4.0
0x59ead  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59eb2  br.s     loc_59EC3
0x59eb4  ldloc.s  0xC
0x59eb6  ldstr    aDisplayicon// "DisplayIcon"
0x59ebb  ldloc.s  0xF
0x59ebd  ldc.i4.0
0x59ebe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59ec3  ldloc.s  0xC
0x59ec5  ldstr    aUninstallstrin// "UninstallString"
0x59eca  ldloc.s  0xF
0x59ecc  ldstr    aUninstallInsta// " uninstall --installPath \""
0x59ed1  ldloc.s  5
0x59ed3  brtrue.s loc_59ED8
0x59ed5  ldnull
0x59ed6  br.s     loc_59EDF
0x59ed8  ldloc.s  5
0x59eda  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59edf  ldstr    asc_8B518// "\""
0x59ee4  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x59ee9  ldc.i4.0
0x59eea  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59eef  ldloc.s  0xC
0x59ef1  ldstr    aModifypath// "ModifyPath"
0x59ef6  ldloc.s  0xF
0x59ef8  ldstr    aModifyInstallp// " modify --installPath \""
0x59efd  ldloc.s  5
0x59eff  brtrue.s loc_59F04
0x59f01  ldnull
0x59f02  br.s     loc_59F0B
0x59f04  ldloc.s  5
0x59f06  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59f0b  ldstr    asc_8B518// "\""
0x59f10  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x59f15  ldc.i4.0
0x59f16  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59f1b  ldloc.s  0xC
0x59f1d  ldstr    aRepairpath// "RepairPath"
0x59f22  ldloc.s  0xF
0x59f24  ldstr    aRepairInstallp// " repair --installPath \""
0x59f29  ldloc.s  5
0x59f2b  brtrue.s loc_59F30
0x59f2d  ldnull
0x59f2e  br.s     loc_59F37
0x59f30  ldloc.s  5
0x59f32  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstallationPath()
0x59f37  ldstr    asc_8B518// "\""
0x59f3c  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x59f41  ldc.i4.0
0x59f42  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x59f47  ldloc.1
0x59f48  brfalse.s loc_59F61
0x59f4a  ldloc.1
0x59f4b  ldstr    aCreatedNewAddR// "Created new Add/Remove Program key: "
0x59f50  ldloc.s  4
0x59f52  call     string [mscorlib]System.String::Concat(string, string)
  ... truncated ...
```
