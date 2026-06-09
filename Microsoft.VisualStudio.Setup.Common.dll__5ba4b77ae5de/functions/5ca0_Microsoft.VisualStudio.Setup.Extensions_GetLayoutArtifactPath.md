# Microsoft.VisualStudio.Setup.Extensions::GetLayoutArtifactPath

- ea: `0x5ca0`
- end: `0x5d06`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetLayoutArtifactPath`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x5ca0`
- `0x6170`
- `0x11900`
- `0x11b00`
- `0x11b30`

## string_xrefs

- `0x5cca`: ` found, using the originalArtifactUri instead.`
- `0x5ce6`: `Unable to check for layout artifact path with reason: `

## pseudocode

```c

```

## disassembly

```asm
0x5ca0  ldarg.0
0x5ca1  call     string Microsoft.VisualStudio.Setup.Extensions::GetParentLocalPath(class [System]System.Uri uri)
0x5ca6  ldarg.2
0x5ca7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5cac  stloc.0
0x5cad  ldarg.s  4
0x5caf  ldloc.0
0x5cb0  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0x5cb5  brfalse.s loc_5CC0
0x5cb7  ldloc.0
0x5cb8  newobj   instance void [System]System.Uri::.ctor(string)
0x5cbd  stloc.1
0x5cbe  leave.s  loc_5D04
0x5cc0  ldarg.3
0x5cc1  brfalse.s loc_5CDE
0x5cc3  ldarg.3
0x5cc4  ldstr    aNoLayoutArtifa// "No layout artifact "
0x5cc9  ldloc.0
0x5cca  ldstr    aFoundUsingTheO// " found, using the originalArtifactUri i"...
0x5ccf  call     string [mscorlib]System.String::Concat(string, string, string)
0x5cd4  call     T0x2B000016
0x5cd9  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x5cde  leave.s  loc_5D02
0x5ce0  stloc.2
0x5ce1  ldarg.3
0x5ce2  brfalse.s loc_5D00
0x5ce4  ldarg.3
0x5ce5  ldloc.2
0x5ce6  ldstr    aUnableToCheckF// "Unable to check for layout artifact pat"...
0x5ceb  ldloc.2
0x5cec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5cf1  call     string [mscorlib]System.String::Concat(string, string)
0x5cf6  call     T0x2B000016
0x5cfb  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0x5d00  leave.s  loc_5D02
0x5d02  ldarg.1
0x5d03  ret
0x5d04  ldloc.1
0x5d05  ret
```
