# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::DoShortcutAction

- ea: `0x33e80`
- end: `0x33ff8`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::DoShortcutAction`
- size: `376`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x322d0`
- `0x328b0`
- `0x32cf0`

## callees

- `0x28b80`
- `0x28bb0`
- `0x28db0`
- `0x2b920`
- `0x33e80`

## string_xrefs

- `0x33f04`: `Failed to create shortcuts for `
- `0x33f48`: `Failed to create web shortcuts for `
- `0x33fa2`: `Failed to delete shortcuts for `
- `0x33fdd`: `Failed to delete web shortcuts for `

## pseudocode

```c

```

## disassembly

```asm
0x33e80  ldarg.1
0x33e81  brtrue.s loc_33E86
0x33e83  ldc.i4.0
0x33e84  br.s     loc_33E94
0x33e86  ldarg.1
0x33e87  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_Shortcuts()
0x33e8c  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut>::get_Count()
0x33e91  ldc.i4.0
0x33e92  cgt
0x33e94  stloc.0
0x33e95  ldarg.1
0x33e96  brtrue.s loc_33E9B
0x33e98  ldc.i4.0
0x33e99  br.s     loc_33EA9
0x33e9b  ldarg.1
0x33e9c  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.WebShortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_WebShortcuts()
0x33ea1  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.WebShortcut>::get_Count()
0x33ea6  ldc.i4.0
0x33ea7  cgt
0x33ea9  stloc.1
0x33eaa  ldloc.0
0x33eab  ldloc.1
0x33eac  or
0x33ead  brfalse  loc_33FF7
0x33eb2  ldarg.0
0x33eb3  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x33eb8  ldc.i4.0
0x33eb9  call     T0x2B000001
0x33ebe  stloc.2
0x33ebf  ldarg.3
0x33ec0  brfalse  loc_33F63
0x33ec5  ldloc.2
0x33ec6  brfalse.s loc_33EE3
0x33ec8  ldloc.2
0x33ec9  ldstr    aCreatingShortc// "Creating shortcuts for package: "
0x33ece  ldarg.1
0x33ecf  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33ed4  call     string [mscorlib]System.String::Concat(string, string)
0x33ed9  call     T0x2B000003
0x33ede  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x33ee3  ldloc.0
0x33ee4  brfalse.s loc_33F1E
0x33ee6  ldarg.1
0x33ee7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_Shortcuts()
0x33eec  ldarg.2
0x33eed  ldarg.0
0x33eee  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x33ef3  ldarg.0
0x33ef4  ldfld    class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory Microsoft.VisualStudio.Setup.Installer.VsixInstaller::shortcutFactory
0x33ef9  call     bool Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::CreateShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut> shortcuts, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variables, class [mscorlib]System.IServiceProvider container, class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory shortcutFactory)
0x33efe  brtrue.s loc_33F1E
0x33f00  ldloc.2
0x33f01  brfalse.s loc_33F1E
0x33f03  ldloc.2
0x33f04  ldstr    aFailedToCreate_4// "Failed to create shortcuts for "
0x33f09  ldarg.1
0x33f0a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33f0f  call     string [mscorlib]System.String::Concat(string, string)
0x33f14  call     T0x2B000003
0x33f19  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33f1e  ldloc.1
0x33f1f  brfalse  loc_33FF7
0x33f24  ldarg.1
0x33f25  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.WebShortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_WebShortcuts()
0x33f2a  ldarg.2
0x33f2b  ldarg.0
0x33f2c  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x33f31  ldarg.0
0x33f32  ldfld    class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory Microsoft.VisualStudio.Setup.Installer.VsixInstaller::shortcutFactory
0x33f37  call     bool Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::CreateWebShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.WebShortcut> webShortcuts, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variables, class [mscorlib]System.IServiceProvider container, class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory shortcutFactory)
0x33f3c  brtrue   loc_33FF7
0x33f41  ldloc.2
0x33f42  brfalse  loc_33FF7
0x33f47  ldloc.2
0x33f48  ldstr    aFailedToCreate_5// "Failed to create web shortcuts for "
0x33f4d  ldarg.1
0x33f4e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33f53  call     string [mscorlib]System.String::Concat(string, string)
0x33f58  call     T0x2B000003
0x33f5d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33f62  ret
0x33f63  ldloc.2
0x33f64  brfalse.s loc_33F81
0x33f66  ldloc.2
0x33f67  ldstr    aDeletingShortc// "Deleting shortcuts for package: "
0x33f6c  ldarg.1
0x33f6d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33f72  call     string [mscorlib]System.String::Concat(string, string)
0x33f77  call     T0x2B000003
0x33f7c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x33f81  ldloc.0
0x33f82  brfalse.s loc_33FBC
0x33f84  ldarg.1
0x33f85  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Shortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_Shortcuts()
0x33f8a  ldarg.2
0x33f8b  ldarg.0
0x33f8c  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x33f91  ldarg.0
0x33f92  ldfld    class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory Microsoft.VisualStudio.Setup.Installer.VsixInstaller::shortcutFactory
0x33f97  call     bool Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::DeleteShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation> shortcuts, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variables, class [mscorlib]System.IServiceProvider container, class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory shortcutFactory)
0x33f9c  brtrue.s loc_33FBC
0x33f9e  ldloc.2
0x33f9f  brfalse.s loc_33FBC
0x33fa1  ldloc.2
0x33fa2  ldstr    aFailedToDelete_6// "Failed to delete shortcuts for "
0x33fa7  ldarg.1
0x33fa8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33fad  call     string [mscorlib]System.String::Concat(string, string)
0x33fb2  call     T0x2B000003
0x33fb7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33fbc  ldloc.1
0x33fbd  brfalse.s loc_33FF7
0x33fbf  ldarg.1
0x33fc0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.WebShortcut> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_WebShortcuts()
0x33fc5  ldarg.2
0x33fc6  ldarg.0
0x33fc7  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x33fcc  ldarg.0
0x33fcd  ldfld    class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory Microsoft.VisualStudio.Setup.Installer.VsixInstaller::shortcutFactory
0x33fd2  call     bool Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::DeleteShortcuts(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation> shortcuts, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variables, class [mscorlib]System.IServiceProvider container, class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory shortcutFactory)
0x33fd7  brtrue.s loc_33FF7
0x33fd9  ldloc.2
0x33fda  brfalse.s loc_33FF7
0x33fdc  ldloc.2
0x33fdd  ldstr    aFailedToDelete_7// "Failed to delete web shortcuts for "
0x33fe2  ldarg.1
0x33fe3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x33fe8  call     string [mscorlib]System.String::Concat(string, string)
0x33fed  call     T0x2B000003
0x33ff2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33ff7  ret
```
