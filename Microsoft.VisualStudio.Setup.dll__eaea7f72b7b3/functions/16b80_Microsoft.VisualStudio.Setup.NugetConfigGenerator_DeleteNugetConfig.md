# Microsoft.VisualStudio.Setup.NugetConfigGenerator::DeleteNugetConfig

- ea: `0x16b80`
- end: `0x16c83`
- name: `Microsoft.VisualStudio.Setup.NugetConfigGenerator::DeleteNugetConfig`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x31300`

## callees

- `0xfe50`
- `0x16b80`
- `0x19df0`
- `0x19e10`
- `0x19e50`
- `0x1a090`

## string_xrefs

- `0x16b94`: `Microsoft.VisualStudio.FallbackLocation.config`
- `0x16bf1`: `Microsoft.VisualStudio.FallbackLocation.config`
- `0x16c1d`: `Microsoft.VisualStudio.FallbackLocation.config`
- `0x16c4b`: `Microsoft.VisualStudio.FallbackLocation.config`

## pseudocode

```c

```

## disassembly

```asm
0x16b80  ldarg.0
0x16b81  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.NugetConfigGenerator::container
0x16b86  ldc.i4.1
0x16b87  call     T0x2B00000C
0x16b8c  stloc.0
0x16b8d  ldsfld   string [mscorlib]System.String::Empty
0x16b92  stloc.1
0x16b93  ldarg.1
0x16b94  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16b99  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16b9e  stloc.1
0x16b9f  ldarg.0
0x16ba0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16ba5  dup
0x16ba6  brtrue.s loc_16BAB
0x16ba8  pop
0x16ba9  br.s     loc_16BC3
0x16bab  ldstr    aDeleting0At1// "Deleting {0} at {1}."
0x16bb0  ldc.i4.2
0x16bb1  newarr   [mscorlib]System.Object
0x16bb6  dup
0x16bb7  ldc.i4.0
0x16bb8  ldloc.1
0x16bb9  stelem.ref
0x16bba  dup
0x16bbb  ldc.i4.1
0x16bbc  ldarg.1
0x16bbd  stelem.ref
0x16bbe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x16bc3  ldloc.0
0x16bc4  ldloc.1
0x16bc5  ldc.i4.2
0x16bc6  ldc.i4   0x1F4
0x16bcb  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x16bd0  pop
0x16bd1  leave    loc_16C82
0x16bd6  stloc.2
0x16bd7  ldarg.0
0x16bd8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16bdd  dup
0x16bde  brtrue.s loc_16BE3
0x16be0  pop
0x16be1  br.s     loc_16C00
0x16be3  ldloc.2
0x16be4  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToDelete_FileSystemOrPathIsNull_Args2()
0x16be9  ldc.i4.2
0x16bea  newarr   [mscorlib]System.Object
0x16bef  dup
0x16bf0  ldc.i4.0
0x16bf1  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16bf6  stelem.ref
0x16bf7  dup
0x16bf8  ldc.i4.1
0x16bf9  ldarg.1
0x16bfa  stelem.ref
0x16bfb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x16c00  rethrow
0x16c02  stloc.3
0x16c03  ldarg.0
0x16c04  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16c09  dup
0x16c0a  brtrue.s loc_16C0F
0x16c0c  pop
0x16c0d  br.s     loc_16C2C
0x16c0f  ldloc.3
0x16c10  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToDelete_FileInUse_Args2()
0x16c15  ldc.i4.2
0x16c16  newarr   [mscorlib]System.Object
0x16c1b  dup
0x16c1c  ldc.i4.0
0x16c1d  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16c22  stelem.ref
0x16c23  dup
0x16c24  ldc.i4.1
0x16c25  ldarg.1
0x16c26  stelem.ref
0x16c27  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x16c2c  rethrow
0x16c2e  stloc.s  4
0x16c30  ldarg.0
0x16c31  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16c36  dup
0x16c37  brtrue.s loc_16C3C
0x16c39  pop
0x16c3a  br.s     loc_16C5A
0x16c3c  ldloc.s  4
0x16c3e  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToDelete_FileIsReadOnly_Args2()
0x16c43  ldc.i4.2
0x16c44  newarr   [mscorlib]System.Object
0x16c49  dup
0x16c4a  ldc.i4.0
0x16c4b  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.FallbackLocation"...
0x16c50  stelem.ref
0x16c51  dup
0x16c52  ldc.i4.1
0x16c53  ldarg.1
0x16c54  stelem.ref
0x16c55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x16c5a  rethrow
0x16c5c  stloc.s  5
0x16c5e  ldarg.0
0x16c5f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.NugetConfigGenerator::logger
0x16c64  dup
0x16c65  brtrue.s loc_16C6A
0x16c67  pop
0x16c68  br.s     loc_16C80
0x16c6a  ldloc.s  5
0x16c6c  call     string Microsoft.VisualStudio.Setup.Resources::get_FileDeletionFailed_Args1()
0x16c71  ldc.i4.1
0x16c72  newarr   [mscorlib]System.Object
0x16c77  dup
0x16c78  ldc.i4.0
0x16c79  ldloc.1
0x16c7a  stelem.ref
0x16c7b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x16c80  rethrow
0x16c82  ret
```
