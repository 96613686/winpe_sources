# System.Deployment.Application.ShellExposure::UpdateArpEntry

- ea: `0x1e580`
- end: `0x1e73b`
- name: `System.Deployment.Application.ShellExposure::UpdateArpEntry`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1d5b0`

## callees

- `0xda80`
- `0x17d40`
- `0x1e580`
- `0x1e7a0`
- `0x1e7d0`
- `0x1ece0`
- `0x1ede0`
- `0x1eee0`
- `0x1efa0`
- `0x23c50`
- `0x23cc0`
- `0x24970`
- `0x2c550`
- `0x2c590`
- `0x2c5a0`
- `0x2c5b0`
- `0x2c5c0`
- `0x2c5d0`

## string_xrefs

- `0x1e58c`: `rundll32.exe dfshim.dll,ShArpMaintain {0}`
- `0x1e5ab`: `dfshim.dll,2`
- `0x1e5d0`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1e63e`: `UninstallString`
- `0x1e64c`: `HelpLink`
- `0x1e660`: `UrlUpdateInfo`

## pseudocode

```c

```

## disassembly

```asm
0x1e580  ldarg.0
0x1e581  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1e586  stloc.0
0x1e587  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e58c  ldstr    aRundll32ExeDfs_0// "rundll32.exe dfshim.dll,ShArpMaintain {"...
0x1e591  ldc.i4.1
0x1e592  newarr   [mscorlib]System.Object
0x1e597  dup
0x1e598  ldc.i4.0
0x1e599  ldloc.0
0x1e59a  callvirt instance string [mscorlib]System.Object::ToString()
0x1e59f  stelem.ref
0x1e5a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e5a5  stloc.1
0x1e5a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e5ab  ldstr    aDfshimDll2// "dfshim.dll,2"
0x1e5b0  ldc.i4.0
0x1e5b1  newarr   [mscorlib]System.Object
0x1e5b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e5bb  stloc.2
0x1e5bc  ldarg.0
0x1e5bd  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x1e5c2  stloc.3
0x1e5c3  ldarg.0
0x1e5c4  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0x1e5c9  stloc.s  4
0x1e5cb  call     class [mscorlib]Microsoft.Win32.RegistryKey System.Deployment.Application.ShellExposure::get_UninstallRoot()
0x1e5d0  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1e5d5  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e5da  stloc.s  5
0x1e5dc  ldloc.s  5
0x1e5de  ldloc.0
0x1e5df  call     string System.Deployment.Application.ShellExposure::GenerateArpKeyName(class System.Deployment.Application.DefinitionIdentity subId)
0x1e5e4  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x1e5e9  stloc.s  6
0x1e5eb  ldc.i4.s 0x18
0x1e5ed  newarr   [mscorlib]System.String
0x1e5f2  dup
0x1e5f3  ldc.i4.0
0x1e5f4  ldstr    aDisplayname// "DisplayName"
0x1e5f9  stelem.ref
0x1e5fa  dup
0x1e5fb  ldc.i4.1
0x1e5fc  ldarg.1
0x1e5fd  callvirt instance string ShellExposureInformation::get_ARPDisplayName()
0x1e602  stelem.ref
0x1e603  dup
0x1e604  ldc.i4.2
0x1e605  ldstr    aDisplayicon// "DisplayIcon"
0x1e60a  stelem.ref
0x1e60b  dup
0x1e60c  ldc.i4.3
0x1e60d  ldloc.2
0x1e60e  stelem.ref
0x1e60f  dup
0x1e610  ldc.i4.4
0x1e611  ldstr    aDisplayversion// "DisplayVersion"
0x1e616  stelem.ref
0x1e617  dup
0x1e618  ldc.i4.5
0x1e619  ldloc.3
0x1e61a  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1e61f  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x1e624  callvirt instance string [mscorlib]System.Object::ToString()
0x1e629  stelem.ref
0x1e62a  dup
0x1e62b  ldc.i4.6
0x1e62c  ldstr    aPublisher// "Publisher"
0x1e631  stelem.ref
0x1e632  dup
0x1e633  ldc.i4.7
0x1e634  ldloc.s  4
0x1e636  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x1e63b  stelem.ref
0x1e63c  dup
0x1e63d  ldc.i4.8
0x1e63e  ldstr    aUninstallstrin// "UninstallString"
0x1e643  stelem.ref
0x1e644  dup
0x1e645  ldc.i4.s 9
0x1e647  ldloc.1
0x1e648  stelem.ref
0x1e649  dup
0x1e64a  ldc.i4.s 0xA
0x1e64c  ldstr    aHelplink// "HelpLink"
0x1e651  stelem.ref
0x1e652  dup
0x1e653  ldc.i4.s 0xB
0x1e655  ldloc.s  4
0x1e657  callvirt instance string System.Deployment.Application.Manifest.Description::get_SupportUrl()
0x1e65c  stelem.ref
0x1e65d  dup
0x1e65e  ldc.i4.s 0xC
0x1e660  ldstr    aUrlupdateinfo// "UrlUpdateInfo"
0x1e665  stelem.ref
0x1e666  dup
0x1e667  ldc.i4.s 0xD
0x1e669  ldarg.0
0x1e66a  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1e66f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1e674  stelem.ref
0x1e675  dup
0x1e676  ldc.i4.s 0xE
0x1e678  ldstr    aShortcutfolder// "ShortcutFolderName"
0x1e67d  stelem.ref
0x1e67e  dup
0x1e67f  ldc.i4.s 0xF
0x1e681  ldarg.1
0x1e682  callvirt instance string ShellExposureInformation::get_AppVendor()
0x1e687  stelem.ref
0x1e688  dup
0x1e689  ldc.i4.s 0x10
0x1e68b  ldstr    aShortcutfilena// "ShortcutFileName"
0x1e690  stelem.ref
0x1e691  dup
0x1e692  ldc.i4.s 0x11
0x1e694  ldarg.1
0x1e695  callvirt instance string ShellExposureInformation::get_AppProduct()
0x1e69a  stelem.ref
0x1e69b  dup
0x1e69c  ldc.i4.s 0x12
0x1e69e  ldstr    aShortcutsuiten// "ShortcutSuiteName"
0x1e6a3  stelem.ref
0x1e6a4  dup
0x1e6a5  ldc.i4.s 0x13
0x1e6a7  ldarg.1
0x1e6a8  callvirt instance string ShellExposureInformation::get_AppSuiteName()
0x1e6ad  stelem.ref
0x1e6ae  dup
0x1e6af  ldc.i4.s 0x14
0x1e6b1  ldstr    aSupportshortcu// "SupportShortcutFileName"
0x1e6b6  stelem.ref
0x1e6b7  dup
0x1e6b8  ldc.i4.s 0x15
0x1e6ba  ldarg.1
0x1e6bb  callvirt instance string ShellExposureInformation::get_AppSupportShortcut()
0x1e6c0  stelem.ref
0x1e6c1  dup
0x1e6c2  ldc.i4.s 0x16
0x1e6c4  ldstr    aShortcutappid// "ShortcutAppId"
0x1e6c9  stelem.ref
0x1e6ca  dup
0x1e6cb  ldc.i4.s 0x17
0x1e6cd  ldarg.1
0x1e6ce  callvirt instance string ShellExposureInformation::get_ShortcutAppId()
0x1e6d3  stelem.ref
0x1e6d4  stloc.s  7
0x1e6d6  ldstr    aUpdatingArpEnt// "Updating ARP entry."
0x1e6db  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e6e0  ldloc.s  7
0x1e6e2  ldlen
0x1e6e3  conv.i4
0x1e6e4  ldc.i4.2
0x1e6e5  sub
0x1e6e6  stloc.s  8
0x1e6e8  br.s     loc_1E71B
0x1e6ea  ldloc.s  7
0x1e6ec  ldloc.s  8
0x1e6ee  ldelem.ref
0x1e6ef  stloc.s  9
0x1e6f1  ldloc.s  7
0x1e6f3  ldloc.s  8
0x1e6f5  ldc.i4.1
0x1e6f6  add
0x1e6f7  ldelem.ref
0x1e6f8  stloc.s  0xA
0x1e6fa  ldloc.s  0xA
0x1e6fc  brfalse.s loc_1E70B
0x1e6fe  ldloc.s  6
0x1e700  ldloc.s  9
0x1e702  ldloc.s  0xA
0x1e704  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1e709  br.s     loc_1E715
0x1e70b  ldloc.s  6
0x1e70d  ldloc.s  9
0x1e70f  ldc.i4.0
0x1e710  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x1e715  ldloc.s  8
0x1e717  ldc.i4.2
0x1e718  sub
0x1e719  stloc.s  8
0x1e71b  ldloc.s  8
0x1e71d  ldc.i4.0
0x1e71e  bge.s    loc_1E6EA
0x1e720  leave.s  loc_1E73A
0x1e722  ldloc.s  6
0x1e724  brfalse.s loc_1E72D
0x1e726  ldloc.s  6
0x1e728  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e72d  endfinally
0x1e72e  ldloc.s  5
0x1e730  brfalse.s loc_1E739
0x1e732  ldloc.s  5
0x1e734  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e739  endfinally
0x1e73a  ret
```
