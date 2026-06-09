# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallVsixManifest

- ea: `0x33230`
- end: `0x33295`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallVsixManifest`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x328b0`

## callees

- `0x33230`
- `0x335f0`
- `0x33840`
- `0x33b10`
- `0x33d70`

## string_xrefs

- `0x33235`: `Cannot deserialize into VSIX package.`
- `0x33278`: `Cannot process VSIX manifest for uninstall `

## pseudocode

```c

```

## disassembly

```asm
0x33230  ldarg.1
0x33231  brtrue.s loc_33246
0x33233  ldarg.s  4
0x33235  ldstr    aCannotDeserial// "Cannot deserialize into VSIX package."
0x3323a  call     T0x2B000003
0x3323f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33244  br.s     loc_33272
0x33246  ldarg.0
0x33247  ldarg.1
0x33248  ldarg.3
0x33249  ldarg.2
0x3324a  ldarg.s  4
0x3324c  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallProgIds(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x33251  ldarg.0
0x33252  ldarg.1
0x33253  ldarg.3
0x33254  ldarg.2
0x33255  ldarg.s  4
0x33257  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallFileAssociations(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x3325c  ldarg.0
0x3325d  ldarg.1
0x3325e  ldarg.3
0x3325f  ldarg.2
0x33260  ldarg.s  4
0x33262  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallUrlAssociations(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x33267  ldarg.0
0x33268  ldarg.1
0x33269  ldarg.3
0x3326a  ldarg.2
0x3326b  ldarg.s  4
0x3326d  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallDefaultProgram(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x33272  leave.s  loc_33294
0x33274  stloc.0
0x33275  ldarg.s  4
0x33277  ldloc.0
0x33278  ldstr    aCannotProcessV_0// "Cannot process VSIX manifest for uninst"...
0x3327d  ldloc.0
0x3327e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x33283  call     string [mscorlib]System.String::Concat(string, string)
0x33288  call     T0x2B000003
0x3328d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x33292  leave.s  loc_33294
0x33294  ret
```
