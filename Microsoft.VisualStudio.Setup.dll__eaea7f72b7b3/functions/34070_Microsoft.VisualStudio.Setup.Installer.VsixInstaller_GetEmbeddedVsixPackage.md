# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetEmbeddedVsixPackage

- ea: `0x34070`
- end: `0x34134`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetEmbeddedVsixPackage`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x322d0`
- `0x328b0`

## callees

- `0x34070`

## string_xrefs

- `0x34094`: `Cannot retrieve embedded manifest.`
- `0x340b7`: `Using cached package manifest as the embedded manifest`
- `0x340f9`: `is not cached. Cannot retrieve embedded manifest.`
- `0x34113`: `Error processing vsix manifest: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x34070  ldnull
0x34071  stloc.0
0x34072  ldarg.3
0x34073  ldc.i4.3
0x34074  bne.un.s loc_3407D
0x34076  ldarg.3
0x34077  ldc.i4.3
0x34078  bne.un.s loc_3409F
0x3407a  ldarg.2
0x3407b  brfalse.s loc_3409F
0x3407d  ldarg.2
0x3407e  ldstr    aPackage// "package"
0x34083  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x34088  ldarg.2
0x34089  ldarg.s  4
0x3408b  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetEmbeddedVsixPackageFromPayload(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x34090  stloc.0
0x34091  ldloc.0
0x34092  brtrue.s loc_3410D
0x34094  ldstr    aCannotRetrieve// "Cannot retrieve embedded manifest."
0x34099  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3409e  throw
0x3409f  ldarg.1
0x340a0  ldstr    aVsix// "vsix"
0x340a5  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x340aa  ldarg.s  5
0x340ac  brfalse.s loc_340C8
0x340ae  ldarg.1
0x340af  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage
0x340b4  stloc.0
0x340b5  ldarg.s  4
0x340b7  ldstr    aUsingCachedPac// "Using cached package manifest as the em"...
0x340bc  call     T0x2B000003
0x340c1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x340c6  br.s     loc_3410D
0x340c8  ldarg.s  4
0x340ca  ldstr    aPackage_1// "Package "
0x340cf  ldarg.1
0x340d0  brtrue.s loc_340D5
0x340d2  ldnull
0x340d3  br.s     loc_340DB
0x340d5  ldarg.1
0x340d6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x340db  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x340e0  brfalse.s loc_340E9
0x340e2  ldsfld   string [mscorlib]System.String::Empty
0x340e7  br.s     loc_340F9
0x340e9  ldarg.1
0x340ea  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x340ef  ldstr    asc_853DA// " "
0x340f4  call     string [mscorlib]System.String::Concat(string, string)
0x340f9  ldstr    aIsNotCachedCan// "is not cached. Cannot retrieve embedded"...
0x340fe  call     string [mscorlib]System.String::Concat(string, string, string)
0x34103  call     T0x2B000003
0x34108  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x3410d  leave.s  loc_34130
0x3410f  stloc.1
0x34110  ldarg.s  4
0x34112  ldloc.1
0x34113  ldstr    aErrorProcessin// "Error processing vsix manifest: {0}"
0x34118  ldc.i4.1
0x34119  newarr   [mscorlib]System.Object
0x3411e  dup
0x3411f  ldc.i4.0
0x34120  ldloc.1
0x34121  callvirt instance string [mscorlib]System.Object::ToString()
0x34126  stelem.ref
0x34127  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x3412c  ldnull
0x3412d  stloc.2
0x3412e  leave.s  loc_34132
0x34130  ldloc.0
0x34131  ret
0x34132  ldloc.2
0x34133  ret
```
