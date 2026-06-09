# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallWithoutCachedManifestAndPayload

- ea: `0x32cf0`
- end: `0x32d64`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallWithoutCachedManifestAndPayload`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x328b0`

## callees

- `0x2b940`
- `0x31e90`
- `0x32cf0`
- `0x32d70`
- `0x33e80`
- `0x3ceb0`

## string_xrefs

- `0x32cf8`: `'s cached manifest as well as payload could not be found, using provider package information.`
- `0x32d1e`: `'s cached manifest as well as payload could not be found, setup engine will try best-effort uninstall. Manual cleanup may be required.`

## pseudocode

```c

```

## disassembly

```asm
0x32cf0  ldarg.s  5
0x32cf2  ldarg.1
0x32cf3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x32cf8  ldstr    aSCachedManifes// "'s cached manifest as well as payload c"...
0x32cfd  call     string [mscorlib]System.String::Concat(string, string)
0x32d02  call     T0x2B000003
0x32d07  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteWarning(string format, object[] args)
0x32d0c  ldarg.0
0x32d0d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x32d12  dup
0x32d13  brtrue.s loc_32D18
0x32d15  pop
0x32d16  br.s     loc_32D32
0x32d18  ldarg.1
0x32d19  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x32d1e  ldstr    aSCachedManifes_0// "'s cached manifest as well as payload c"...
0x32d23  call     string [mscorlib]System.String::Concat(string, string)
0x32d28  call     T0x2B000003
0x32d2d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x32d32  ldarg.0
0x32d33  ldarg.1
0x32d34  ldarg.2
0x32d35  ldc.i4.0
0x32d36  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::DoShortcutAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variableMapping, bool create)
0x32d3b  ldarg.0
0x32d3c  ldnull
0x32d3d  ldarg.1
0x32d3e  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetVsixType(string vsixPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage)
0x32d43  stloc.0
0x32d44  ldarg.0
0x32d45  ldarg.2
0x32d46  ldarg.1
0x32d47  brtrue.s loc_32D4C
0x32d49  ldnull
0x32d4a  br.s     loc_32D52
0x32d4c  ldarg.1
0x32d4d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_FolderMappings()
0x32d52  ldarg.3
0x32d53  ldloc.0
0x32d54  ldarg.s  5
0x32d56  ldarg.s  4
0x32d58  ldarg.1
0x32d59  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile>::get_Files()
0x32d5e  call     instance class [mscorlib]System.Tuple`2<bool, string> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ProcessVsixForUninstall(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> folderMappings, string layoutDir, valuetype Microsoft.VisualStudio.Setup.Installer.VsixType vsixType, class Microsoft.VisualStudio.Setup.Services.FileLogger logger, class [System]System.Collections.Generic.SortedSet`1<string> dirsDeleteCandidates, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile> files)
0x32d63  ret
```
