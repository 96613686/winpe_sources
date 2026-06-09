# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallVsixManifest

- ea: `0x331c0`
- end: `0x33225`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallVsixManifest`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x322d0`

## callees

- `0x331c0`
- `0x332a0`
- `0x33680`
- `0x339a0`
- `0x33c00`

## string_xrefs

- `0x331c5`: `Cannot deserialize into VSIX package.`
- `0x33208`: `Cannot process VSIX manifest for install `

## pseudocode

```c

```

## disassembly

```asm
0x331c0  ldarg.1
0x331c1  brtrue.s loc_331D6
0x331c3  ldarg.s  4
0x331c5  ldstr    aCannotDeserial// "Cannot deserialize into VSIX package."
0x331ca  call     T0x2B000003
0x331cf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x331d4  br.s     loc_33202
0x331d6  ldarg.0
0x331d7  ldarg.1
0x331d8  ldarg.3
0x331d9  ldarg.2
0x331da  ldarg.s  4
0x331dc  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallProgIds(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x331e1  ldarg.0
0x331e2  ldarg.1
0x331e3  ldarg.3
0x331e4  ldarg.2
0x331e5  ldarg.s  4
0x331e7  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallFileAssociations(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x331ec  ldarg.0
0x331ed  ldarg.1
0x331ee  ldarg.3
0x331ef  ldarg.2
0x331f0  ldarg.s  4
0x331f2  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallUrlAssociations(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x331f7  ldarg.0
0x331f8  ldarg.1
0x331f9  ldarg.3
0x331fa  ldarg.2
0x331fb  ldarg.s  4
0x331fd  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallDefaultProgram(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x33202  leave.s  loc_33224
0x33204  stloc.0
0x33205  ldarg.s  4
0x33207  ldloc.0
0x33208  ldstr    aCannotProcessV// "Cannot process VSIX manifest for instal"...
0x3320d  ldloc.0
0x3320e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x33213  call     string [mscorlib]System.String::Concat(string, string)
0x33218  call     T0x2B000003
0x3321d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x33222  leave.s  loc_33224
0x33224  ret
```
