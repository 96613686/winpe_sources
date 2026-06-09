# System.Deployment.Application.ShellExposure::UpdateShortcuts

- ea: `0x1d970`
- end: `0x1db9e`
- name: `System.Deployment.Application.ShellExposure::UpdateShortcuts`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update`

## callers

- `0x1d5b0`

## callees

- `0x17d40`
- `0x1d840`
- `0x1d880`
- `0x1d970`
- `0x1dba0`
- `0x1dc60`
- `0x1dd40`
- `0x1df50`
- `0x1ece0`
- `0x1ede0`
- `0x1efa0`
- `0x23160`
- `0x23cc0`
- `0x23cd0`
- `0x23ce0`
- `0x2c3a0`
- `0x2c500`
- `0x2c510`
- `0x2c520`
- `0x2c530`
- `0x2c540`
- `0x2c590`
- `0x2c5a0`
- `0x2c5b0`
- `0x2c5d0`
- `0x2c5e0`

## string_xrefs

- `0x1da1e`: `Shortcut folder and files are not updated and application shortcut file already exists: `
- `0x1da71`: `Shortcut files deleted:`
- `0x1dab2`: `Attempt deleting shortcut folder:`
- `0x1dad7`: `Attempt deleting shortcut root folder:`
- `0x1db5e`: `Create the shortcut directory : `

## pseudocode

```c

```

## disassembly

```asm
0x1d970  ldstr    a01_0// "{0}#{1}"
0x1d975  ldarg.0
0x1d976  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1d97b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1d980  ldarg.0
0x1d981  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1d986  callvirt instance string [mscorlib]System.Object::ToString()
0x1d98b  call     string [mscorlib]System.String::Format(string, object, object)
0x1d990  stloc.0
0x1d991  ldarg.0
0x1d992  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0x1d997  stloc.1
0x1d998  ldarg.1
0x1d999  ldind.ref
0x1d99a  brfalse  loc_1DB43
0x1d99f  ldc.i4.1
0x1d9a0  stloc.2
0x1d9a1  ldc.i4.1
0x1d9a2  stloc.3
0x1d9a3  ldc.i4.1
0x1d9a4  stloc.s  4
0x1d9a6  ldc.i4.1
0x1d9a7  stloc.s  5
0x1d9a9  ldloc.1
0x1d9aa  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x1d9af  ldarg.1
0x1d9b0  ldind.ref
0x1d9b1  callvirt instance string ShellExposureInformation::get_AppVendor()
0x1d9b6  ldc.i4.4
0x1d9b7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1d9bc  brtrue.s loc_1DA02
0x1d9be  ldc.i4.0
0x1d9bf  stloc.2
0x1d9c0  ldloc.1
0x1d9c1  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredSuiteName()
0x1d9c6  ldarg.1
0x1d9c7  ldind.ref
0x1d9c8  callvirt instance string ShellExposureInformation::get_AppSuiteName()
0x1d9cd  ldc.i4.4
0x1d9ce  call     int32 System.Deployment.Application.Utilities::CompareWithNullEqEmpty(string s1, string s2, valuetype [mscorlib]System.StringComparison comparisonType)
0x1d9d3  brtrue.s loc_1DA02
0x1d9d5  ldc.i4.0
0x1d9d6  stloc.3
0x1d9d7  ldloc.1
0x1d9d8  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x1d9dd  ldarg.1
0x1d9de  ldind.ref
0x1d9df  callvirt instance string ShellExposureInformation::get_AppProduct()
0x1d9e4  ldc.i4.4
0x1d9e5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1d9ea  brtrue.s loc_1DA02
0x1d9ec  ldc.i4.0
0x1d9ed  stloc.s  4
0x1d9ef  ldloc.0
0x1d9f0  ldarg.1
0x1d9f1  ldind.ref
0x1d9f2  callvirt instance string ShellExposureInformation::get_ShortcutAppId()
0x1d9f7  ldc.i4.4
0x1d9f8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1d9fd  brtrue.s loc_1DA02
0x1d9ff  ldc.i4.0
0x1da00  stloc.s  5
0x1da02  ldloc.2
0x1da03  brtrue.s loc_1DA35
0x1da05  ldloc.3
0x1da06  brtrue.s loc_1DA35
0x1da08  ldloc.s  4
0x1da0a  brtrue.s loc_1DA35
0x1da0c  ldloc.s  5
0x1da0e  brtrue.s loc_1DA35
0x1da10  ldarg.1
0x1da11  ldind.ref
0x1da12  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1da17  call     bool [mscorlib]System.IO.File::Exists(string)
0x1da1c  brfalse.s loc_1DA35
0x1da1e  ldstr    aShortcutFolder// "Shortcut folder and files are not updat"...
0x1da23  ldarg.1
0x1da24  ldind.ref
0x1da25  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1da2a  call     string [mscorlib]System.String::Concat(string, string)
0x1da2f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1da34  ret
0x1da35  ldloc.s  4
0x1da37  brfalse.s loc_1DAAF
0x1da39  ldarg.1
0x1da3a  ldind.ref
0x1da3b  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1da40  call     void System.Deployment.Application.ShellExposure::UnpinShortcut(string shortcutPath)
0x1da45  ldarg.1
0x1da46  ldind.ref
0x1da47  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1da4c  call     void System.Deployment.Application.ShellExposure::MoveDeleteFile(string filePath)
0x1da51  ldarg.1
0x1da52  ldind.ref
0x1da53  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1da58  call     void System.Deployment.Application.ShellExposure::MoveDeleteFile(string filePath)
0x1da5d  ldarg.1
0x1da5e  ldind.ref
0x1da5f  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1da64  call     void System.Deployment.Application.ShellExposure::MoveDeleteFile(string filePath)
0x1da69  ldc.i4.6
0x1da6a  newarr   [mscorlib]System.String
0x1da6f  dup
0x1da70  ldc.i4.0
0x1da71  ldstr    aShortcutFilesD// "Shortcut files deleted:"
0x1da76  stelem.ref
0x1da77  dup
0x1da78  ldc.i4.1
0x1da79  ldarg.1
0x1da7a  ldind.ref
0x1da7b  callvirt instance string ShellExposureInformation::get_ApplicationShortcutPath()
0x1da80  stelem.ref
0x1da81  dup
0x1da82  ldc.i4.2
0x1da83  ldstr    asc_308B8// ","
0x1da88  stelem.ref
0x1da89  dup
0x1da8a  ldc.i4.3
0x1da8b  ldarg.1
0x1da8c  ldind.ref
0x1da8d  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1da92  stelem.ref
0x1da93  dup
0x1da94  ldc.i4.4
0x1da95  ldstr    asc_308B8// ","
0x1da9a  stelem.ref
0x1da9b  dup
0x1da9c  ldc.i4.5
0x1da9d  ldarg.1
0x1da9e  ldind.ref
0x1da9f  callvirt instance string ShellExposureInformation::get_DesktopShortcutPath()
0x1daa4  stelem.ref
0x1daa5  call     string [mscorlib]System.String::Concat(string[])
0x1daaa  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1daaf  ldloc.3
0x1dab0  brfalse.s loc_1DAD4
0x1dab2  ldstr    aAttemptDeletin// "Attempt deleting shortcut folder:"
0x1dab7  ldarg.1
0x1dab8  ldind.ref
0x1dab9  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1dabe  call     string [mscorlib]System.String::Concat(string, string)
0x1dac3  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1dac8  ldarg.1
0x1dac9  ldind.ref
0x1daca  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1dacf  call     void System.Deployment.Application.ShellExposure::MoveDeleteEmptyFolder(string folderPath)
0x1dad4  ldloc.2
0x1dad5  brfalse.s loc_1DAF9
0x1dad7  ldstr    aAttemptDeletin_0// "Attempt deleting shortcut root folder:"
0x1dadc  ldarg.1
0x1dadd  ldind.ref
0x1dade  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1dae3  call     string [mscorlib]System.String::Concat(string, string)
0x1dae8  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1daed  ldarg.1
0x1daee  ldind.ref
0x1daef  callvirt instance string ShellExposureInformation::get_ApplicationRootFolderPath()
0x1daf4  call     void System.Deployment.Application.ShellExposure::MoveDeleteEmptyFolder(string folderPath)
0x1daf9  ldloc.2
0x1dafa  ldloc.3
0x1dafb  or
0x1dafc  ldloc.s  4
0x1dafe  or
0x1daff  brfalse.s loc_1DB1D
0x1db01  ldarg.1
0x1db02  ldloc.1
0x1db03  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x1db08  ldloc.1
0x1db09  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredSuiteName()
0x1db0e  ldloc.1
0x1db0f  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x1db14  ldloc.0
0x1db15  call     class ShellExposureInformation ShellExposureInformation::CreateShellExposureInformation(string publisher, string suiteName, string product, string shortcutAppId)
0x1db1a  stind.ref
0x1db1b  br.s     loc_1DB5D
0x1db1d  ldstr    aShortcutAppIdH// "Shortcut app id has changed. Old value="
0x1db22  ldarg.1
0x1db23  ldind.ref
0x1db24  callvirt instance string ShellExposureInformation::get_ShortcutAppId()
0x1db29  ldstr    aNewValue// ",New value="
0x1db2e  ldloc.0
0x1db2f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1db34  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1db39  ldarg.1
0x1db3a  ldind.ref
0x1db3b  ldloc.0
0x1db3c  callvirt instance void ShellExposureInformation::set_ShortcutAppId(string value)
0x1db41  br.s     loc_1DB5D
0x1db43  ldarg.1
0x1db44  ldloc.1
0x1db45  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x1db4a  ldloc.1
0x1db4b  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredSuiteName()
0x1db50  ldloc.1
0x1db51  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x1db56  ldloc.0
0x1db57  call     class ShellExposureInformation ShellExposureInformation::CreateShellExposureInformation(string publisher, string suiteName, string product, string shortcutAppId)
0x1db5c  stind.ref
0x1db5d  nop
0x1db5e  ldstr    aCreateTheShort// "Create the shortcut directory : "
0x1db63  ldarg.1
0x1db64  ldind.ref
0x1db65  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1db6a  call     string [mscorlib]System.String::Concat(string, string)
0x1db6f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1db74  ldarg.1
0x1db75  ldind.ref
0x1db76  callvirt instance string ShellExposureInformation::get_ApplicationFolderPath()
0x1db7b  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x1db80  pop
0x1db81  ldarg.0
0x1db82  ldarg.1
0x1db83  ldind.ref
0x1db84  call     void System.Deployment.Application.ShellExposure::GenerateAppShortcut(class System.Deployment.Application.SubscriptionState subState, class ShellExposureInformation shellExposureInformation)
0x1db89  ldarg.0
0x1db8a  ldarg.1
0x1db8b  ldind.ref
0x1db8c  call     void System.Deployment.Application.ShellExposure::GenerateSupportShortcut(class System.Deployment.Application.SubscriptionState subState, class ShellExposureInformation shellExposureInformation)
0x1db91  leave.s  loc_1DB9D
0x1db93  pop
0x1db94  ldarg.1
0x1db95  ldind.ref
0x1db96  call     void System.Deployment.Application.ShellExposure::RemoveShortcuts(class ShellExposureInformation shellExposureInformation)
0x1db9b  rethrow
0x1db9d  ret
```
