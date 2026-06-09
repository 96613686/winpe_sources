# Microsoft.VisualStudio.Setup.Extensions::GetEmbeddedVsixPackageFromPayload

- ea: `0x6570`
- end: `0x660a`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetEmbeddedVsixPackageFromPayload`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x6570`
- `0x10480`
- `0x11750`
- `0x11790`
- `0x11b00`
- `0x11b20`

## string_xrefs

- `0x6574`: `Using package payload to get the embedded manifest`
- `0x65e9`: `Couldn't use the package payload to get the embedded manifest: `

## pseudocode

```c

```

## disassembly

```asm
0x6570  ldarg.1
0x6571  brfalse.s loc_6583
0x6573  ldarg.1
0x6574  ldstr    aUsingPackagePa// "Using package payload to get the embedd"...
0x6579  call     T0x2B000016
0x657e  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x6583  nop
0x6584  ldarg.0
0x6585  ldsfld   string Microsoft.VisualStudio.Setup.Extensions::VsixManifestName
0x658a  ldc.i4.2
0x658b  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x6590  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x6595  callvirt instance class Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart Microsoft.VisualStudio.Setup.Services.ICompressedPackage::GetPart(class [System]System.Uri uri)
0x659a  stloc.0
0x659b  ldloc.0
0x659c  brfalse.s loc_65E1
0x659e  ldloc.0
0x659f  ldc.i4.3
0x65a0  ldc.i4.1
0x65a1  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Services.ICompressedPackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode fileMode, valuetype [mscorlib]System.IO.FileAccess fileAccess)
0x65a6  stloc.1
0x65a7  ldloc.1
0x65a8  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x65ad  stloc.2
0x65ae  ldnull
0x65af  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.PackageSerializer::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x65b4  dup
0x65b5  ldsfld   string Microsoft.VisualStudio.Setup.Extensions::VsixManifestName
0x65ba  callvirt instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.IPackage>::set_Location(string)
0x65bf  ldloc.2
0x65c0  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.IPackage>::Deserialize(!!T0)
0x65c5  isinst   Microsoft.VisualStudio.Setup.VsixPackage
0x65ca  stloc.3
0x65cb  leave.s  loc_6608
0x65cd  ldloc.2
0x65ce  brfalse.s loc_65D6
0x65d0  ldloc.2
0x65d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65d6  endfinally
0x65d7  ldloc.1
0x65d8  brfalse.s loc_65E0
0x65da  ldloc.1
0x65db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65e0  endfinally
0x65e1  leave.s  loc_6606
0x65e3  stloc.s  4
0x65e5  ldarg.1
0x65e6  brfalse.s loc_6604
0x65e8  ldarg.1
0x65e9  ldstr    aCouldnTUseTheP// "Couldn't use the package payload to get"...
0x65ee  ldloc.s  4
0x65f0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65f5  call     string [mscorlib]System.String::Concat(string, string)
0x65fa  call     T0x2B000016
0x65ff  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string format, object[] args)
0x6604  rethrow
0x6606  ldnull
0x6607  ret
0x6608  ldloc.3
0x6609  ret
```
