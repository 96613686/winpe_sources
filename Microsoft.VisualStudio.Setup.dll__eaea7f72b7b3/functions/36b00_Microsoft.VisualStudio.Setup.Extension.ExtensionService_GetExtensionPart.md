# Microsoft.VisualStudio.Setup.Extension.ExtensionService::GetExtensionPart

- ea: `0x36b00`
- end: `0x36b9c`
- name: `Microsoft.VisualStudio.Setup.Extension.ExtensionService::GetExtensionPart`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x36490`
- `0x368a0`

## callees

- `0x36b00`
- `0x36ba0`
- `0x36c20`
- `0x36dd0`

## string_xrefs

- `0x36b80`: `Failed to extract extension contents from the stream`
- `0x36b4f`: `Vsix did not contain the part with path: `

## pseudocode

```c

```

## disassembly

```asm
0x36b00  ldarg.1
0x36b01  ldc.i4.0
0x36b02  conv.i8
0x36b03  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x36b08  ldarg.1
0x36b09  call     class [WindowsBase]System.IO.Packaging.Package [WindowsBase]System.IO.Packaging.Package::Open(class [mscorlib]System.IO.Stream)
0x36b0e  stloc.0
0x36b0f  ldarg.2
0x36b10  ldc.i4.2
0x36b11  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x36b16  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x36b1b  stloc.1
0x36b1c  ldloc.0
0x36b1d  ldloc.1
0x36b1e  callvirt instance bool [WindowsBase]System.IO.Packaging.Package::PartExists(class [System]System.Uri)
0x36b23  brfalse.s loc_36B4E
0x36b25  ldloc.0
0x36b26  ldloc.1
0x36b27  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x36b2c  stloc.2
0x36b2d  ldloc.2
0x36b2e  brfalse.s loc_36B69
0x36b30  ldarg.3
0x36b31  ldarg.0
0x36b32  ldloc.0
0x36b33  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionManifest Microsoft.VisualStudio.Setup.Extension.ExtensionService::GetExtensionManifest(class [WindowsBase]System.IO.Packaging.Package)
0x36b38  stind.ref
0x36b39  ldarg.s  4
0x36b3b  ldarg.0
0x36b3c  ldloc.0
0x36b3d  call     instance class Microsoft.VisualStudio.Setup.Extension.Serialization.ExtensionPackFile Microsoft.VisualStudio.Setup.Extension.ExtensionService::GetExtensionPackFile(class [WindowsBase]System.IO.Packaging.Package)
0x36b42  stind.ref
0x36b43  ldloc.2
0x36b44  ldc.i4.3
0x36b45  ldc.i4.1
0x36b46  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x36b4b  stloc.3
0x36b4c  leave.s  loc_36B9A
0x36b4e  ldarg.0
0x36b4f  ldstr    aVsixDidNotCont// "Vsix did not contain the part with path"...
0x36b54  ldarg.2
0x36b55  ldstr    asc_80DBA// "."
0x36b5a  call     string [mscorlib]System.String::Concat(string, string, string)
0x36b5f  call     T0x2B000003
0x36b64  call     instance void Microsoft.VisualStudio.Setup.Extension.ExtensionService::WriteWarning(string message, object[] args)
0x36b69  leave.s  loc_36B91
0x36b6b  stloc.s  4
0x36b6d  ldarg.0
0x36b6e  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger> Microsoft.VisualStudio.Setup.Extension.ExtensionService::lazyLogger
0x36b73  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger>::get_Value()
0x36b78  dup
0x36b79  brtrue.s loc_36B7E
0x36b7b  pop
0x36b7c  br.s     loc_36B8F
0x36b7e  ldloc.s  4
0x36b80  ldstr    aFailedToExtrac// "Failed to extract extension contents fr"...
0x36b85  call     T0x2B000003
0x36b8a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x36b8f  leave.s  loc_36B91
0x36b91  ldarg.3
0x36b92  ldnull
0x36b93  stind.ref
0x36b94  ldarg.s  4
0x36b96  ldnull
0x36b97  stind.ref
0x36b98  ldnull
0x36b99  ret
0x36b9a  ldloc.3
0x36b9b  ret
```
