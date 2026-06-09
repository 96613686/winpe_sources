# ShellExposureInformation::CreateShellExposureInformation

- ea: `0x2c1e0`
- end: `0x2c394`
- name: `ShellExposureInformation::CreateShellExposureInformation`
- size: `436`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d5b0`
- `0x1d5f0`
- `0x1de90`
- `0x1f1c0`

## callees

- `0x1e7a0`
- `0x1e7d0`
- `0x2c1e0`
- `0x2c5f0`

## string_xrefs

- `0x2c1f7`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c

```

## disassembly

```asm
0x2c1e0  ldnull
0x2c1e1  stloc.0
0x2c1e2  ldnull
0x2c1e3  stloc.1
0x2c1e4  ldnull
0x2c1e5  stloc.2
0x2c1e6  ldnull
0x2c1e7  stloc.3
0x2c1e8  ldnull
0x2c1e9  stloc.s  4
0x2c1eb  ldstr    asc_2F208// ""
0x2c1f0  stloc.s  5
0x2c1f2  call     class [mscorlib]Microsoft.Win32.RegistryKey System.Deployment.Application.ShellExposure::get_UninstallRoot()
0x2c1f7  ldstr    aSoftwareMicros_5// "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x2c1fc  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x2c201  stloc.s  6
0x2c203  ldloc.s  6
0x2c205  brfalse  loc_2C2B7
0x2c20a  ldloc.s  6
0x2c20c  ldarg.0
0x2c20d  call     string System.Deployment.Application.ShellExposure::GenerateArpKeyName(class System.Deployment.Application.DefinitionIdentity subId)
0x2c212  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x2c217  stloc.s  7
0x2c219  ldloc.s  7
0x2c21b  brfalse  loc_2C2A9
0x2c220  ldloc.s  7
0x2c222  ldstr    aShortcutfolder// "ShortcutFolderName"
0x2c227  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c22c  isinst   [mscorlib]System.String
0x2c231  stloc.1
0x2c232  ldloc.s  7
0x2c234  ldstr    aShortcutfilena// "ShortcutFileName"
0x2c239  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c23e  isinst   [mscorlib]System.String
0x2c243  stloc.2
0x2c244  ldloc.s  7
0x2c246  ldstr    aShortcutsuiten// "ShortcutSuiteName"
0x2c24b  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c250  brfalse.s loc_2C266
0x2c252  ldloc.s  7
0x2c254  ldstr    aShortcutsuiten// "ShortcutSuiteName"
0x2c259  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c25e  isinst   [mscorlib]System.String
0x2c263  stloc.3
0x2c264  br.s     loc_2C26C
0x2c266  ldstr    asc_2F208// ""
0x2c26b  stloc.3
0x2c26c  ldloc.s  7
0x2c26e  ldstr    aSupportshortcu// "SupportShortcutFileName"
0x2c273  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c278  isinst   [mscorlib]System.String
0x2c27d  stloc.s  4
0x2c27f  ldloc.s  7
0x2c281  ldstr    aShortcutappid// "ShortcutAppId"
0x2c286  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c28b  brfalse.s loc_2C2A2
0x2c28d  ldloc.s  7
0x2c28f  ldstr    aShortcutappid// "ShortcutAppId"
0x2c294  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2c299  isinst   [mscorlib]System.String
0x2c29e  stloc.s  5
0x2c2a0  leave.s  loc_2C2C5
0x2c2a2  ldstr    asc_2F208// ""
0x2c2a7  stloc.s  5
0x2c2a9  leave.s  loc_2C2C5
0x2c2ab  ldloc.s  7
0x2c2ad  brfalse.s loc_2C2B6
0x2c2af  ldloc.s  7
0x2c2b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c2b6  endfinally
0x2c2b7  leave.s  loc_2C2C5
0x2c2b9  ldloc.s  6
0x2c2bb  brfalse.s loc_2C2C4
0x2c2bd  ldloc.s  6
0x2c2bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c2c4  endfinally
0x2c2c5  ldloc.1
0x2c2c6  brfalse  loc_2C392
0x2c2cb  ldloc.2
0x2c2cc  brfalse  loc_2C392
0x2c2d1  ldloc.s  4
0x2c2d3  brfalse  loc_2C392
0x2c2d8  newobj   instance void ShellExposureInformation::.ctor()
0x2c2dd  stloc.0
0x2c2de  ldloc.0
0x2c2df  ldc.i4.2
0x2c2e0  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x2c2e5  ldloc.1
0x2c2e6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2c2eb  stfld    string ShellExposureInformation::_applicationRootFolderPath
0x2c2f0  ldloc.3
0x2c2f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c2f6  brfalse.s loc_2C306
0x2c2f8  ldloc.0
0x2c2f9  ldloc.0
0x2c2fa  ldfld    string ShellExposureInformation::_applicationRootFolderPath
0x2c2ff  stfld    string ShellExposureInformation::_applicationFolderPath
0x2c304  br.s     loc_2C318
0x2c306  ldloc.0
0x2c307  ldloc.0
0x2c308  ldfld    string ShellExposureInformation::_applicationRootFolderPath
0x2c30d  ldloc.3
0x2c30e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2c313  stfld    string ShellExposureInformation::_applicationFolderPath
0x2c318  ldloc.0
0x2c319  ldloc.0
0x2c31a  ldfld    string ShellExposureInformation::_applicationFolderPath
0x2c31f  ldloc.2
0x2c320  ldstr    aApprefMs// ".appref-ms"
0x2c325  call     string [mscorlib]System.String::Concat(string, string)
0x2c32a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2c32f  stfld    string ShellExposureInformation::_applicationShortcutPath
0x2c334  ldloc.0
0x2c335  ldloc.0
0x2c336  ldfld    string ShellExposureInformation::_applicationFolderPath
0x2c33b  ldloc.s  4
0x2c33d  ldstr    aUrl_1// ".url"
0x2c342  call     string [mscorlib]System.String::Concat(string, string)
0x2c347  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2c34c  stfld    string ShellExposureInformation::_supportShortcutPath
0x2c351  ldloc.0
0x2c352  ldc.i4.0
0x2c353  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x2c358  ldloc.2
0x2c359  ldstr    aApprefMs// ".appref-ms"
0x2c35e  call     string [mscorlib]System.String::Concat(string, string)
0x2c363  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2c368  stfld    string ShellExposureInformation::_desktopShortcutPath
0x2c36d  ldloc.0
0x2c36e  ldloc.1
0x2c36f  stfld    string ShellExposureInformation::_appVendor
0x2c374  ldloc.0
0x2c375  ldloc.2
0x2c376  stfld    string ShellExposureInformation::_appProduct
0x2c37b  ldloc.0
0x2c37c  ldloc.s  4
0x2c37e  stfld    string ShellExposureInformation::_appSupportShortcut
0x2c383  ldloc.0
0x2c384  ldloc.s  5
0x2c386  stfld    string ShellExposureInformation::_shortcutAppId
0x2c38b  ldloc.0
0x2c38c  ldloc.3
0x2c38d  stfld    string ShellExposureInformation::_appSuiteName
0x2c392  ldloc.0
0x2c393  ret
```
