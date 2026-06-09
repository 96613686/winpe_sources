# Microsoft.VisualStudio.Setup.NugetConfigGenerator::AddNugetConfig

- ea: `0x16ae0`
- end: `0x16b7d`
- name: `Microsoft.VisualStudio.Setup.NugetConfigGenerator::AddNugetConfig`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x30c00`

## callees

- `0x16ae0`
- `0x16c90`

## string_xrefs

- `0x16aee`: `Microsoft.VisualStudio.FallbackLocation.config`
- `0x16b4b`: `Microsoft.VisualStudio.FallbackLocation.config`

## pseudocode

```c

```

## disassembly

```asm
0x16ae0  ldarg.0
0x16ae1  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.NugetConfigGenerator::container
0x16ae6  ldc.i4.1
0x16ae7  call     T0x2B00000C
0x16aec  stloc.0
0x16aed  ldarg.1
0x16aee  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16af3  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16af8  stloc.1
0x16af9  ldloc.0
0x16afa  ldloc.1
0x16afb  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x16b00  brtrue.s loc_16B7C
0x16b02  ldloc.0
0x16b03  ldarg.1
0x16b04  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x16b09  brtrue.s loc_16B32
0x16b0b  ldarg.0
0x16b0c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16b11  dup
0x16b12  brtrue.s loc_16B17
0x16b14  pop
0x16b15  br.s     loc_16B2B
0x16b17  ldstr    aCreating0// "Creating {0}."
0x16b1c  ldc.i4.1
0x16b1d  newarr   [mscorlib]System.Object
0x16b22  dup
0x16b23  ldc.i4.0
0x16b24  ldarg.1
0x16b25  stelem.ref
0x16b26  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x16b2b  ldloc.0
0x16b2c  ldarg.1
0x16b2d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x16b32  ldarg.0
0x16b33  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16b38  dup
0x16b39  brtrue.s loc_16B3E
0x16b3b  pop
0x16b3c  br.s     loc_16B5A
0x16b3e  ldstr    aAdding0To1// "Adding {0} to {1}."
0x16b43  ldc.i4.2
0x16b44  newarr   [mscorlib]System.Object
0x16b49  dup
0x16b4a  ldc.i4.0
0x16b4b  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16b50  stelem.ref
0x16b51  dup
0x16b52  ldc.i4.1
0x16b53  ldarg.1
0x16b54  stelem.ref
0x16b55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x16b5a  ldloc.0
0x16b5b  ldloc.1
0x16b5c  ldc.i4.0
0x16b5d  callvirt instance class [mscorlib]System.IO.TextWriter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateText(string, bool)
0x16b62  stloc.2
0x16b63  ldarg.0
0x16b64  ldarg.2
0x16b65  call     instance class [System.Xml.Linq]System.Xml.Linq.XDocument Microsoft.VisualStudio.Setup.NugetConfigGenerator::GenerateXDocument(string fallbackfolderPath)
0x16b6a  ldloc.2
0x16b6b  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XDocument::Save(class [mscorlib]System.IO.TextWriter)
0x16b70  leave.s  loc_16B7C
0x16b72  ldloc.2
0x16b73  brfalse.s loc_16B7B
0x16b75  ldloc.2
0x16b76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16b7b  endfinally
0x16b7c  ret
```
