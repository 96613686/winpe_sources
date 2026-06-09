# Microsoft.Internal.GDIExporter.FontInstallInfo::Install

- ea: `0x22b70`
- end: `0x22bd5`
- name: `Microsoft.Internal.GDIExporter.FontInstallInfo::Install`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22cb0`

## callees

- `0x1be20`
- `0x22870`
- `0x228a0`
- `0x22980`
- `0x22b70`
- `0x22c40`
- `0x22dd0`
- `0x22df0`

## pseudocode

```c

```

## disassembly

```asm
0x22b70  ldarg.0
0x22b71  ldarg.1
0x22b72  call     instance void Microsoft.Internal.GDIExporter.FontInstallInfo::UpdateFromContext(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext context)
0x22b77  ldnull
0x22b78  stloc.2
0x22b79  ldloc.2
0x22b7a  brtrue.s loc_22BD3
0x22b7c  ldarg.1
0x22b7d  call     instance void Microsoft.Internal.GDIExporter.FontStreamContext::UpdateStreamLength()
0x22b82  ldarg.1
0x22b83  call     instance int32 Microsoft.Internal.GDIExporter.FontStreamContext::get_StreamLength()
0x22b88  stloc.0
0x22b89  ldloc.0
0x22b8a  ldc.i4.0
0x22b8b  ble.s    loc_22BD3
0x22b8d  ldloc.0
0x22b8e  ldsfld   modopt([mscorlib]System.Runtime.CompilerServices.IsConst) int32 Microsoft.Internal.GDIExporter.FontStreamContext::MaximumStreamLength
0x22b93  bge.s    loc_22BD3
0x22b95  ldarg.1
0x22b96  call     instance class [mscorlib]System.IO.Stream Microsoft.Internal.GDIExporter.FontStreamContext::GetStream()
0x22b9b  stloc.3
0x22b9c  ldloc.3
0x22b9d  brfalse.s loc_22BD3
0x22b9f  ldloc.0
0x22ba0  newarr   [mscorlib]System.Byte
0x22ba5  stloc.1
0x22ba6  ldloc.3
0x22ba7  ldloc.1
0x22ba8  ldc.i4.0
0x22ba9  ldloc.0
0x22baa  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x22baf  ldloc.0
0x22bb0  bne.un.s loc_22BD3
0x22bb2  ldloca.s 5
0x22bb4  ldloc.1
0x22bb5  ldarg.3
0x22bb6  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::.ctor(unsigned int8[] fontdata, unsigned int32 faceIndex)
0x22bbb  ldarg.2
0x22bbc  ldloca.s 5
0x22bbe  call     instance string Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFontName()
0x22bc3  stind.ref
0x22bc4  ldc.i4.0
0x22bc5  stloc.s  4
0x22bc7  ldloc.1
0x22bc8  ldloc.0
0x22bc9  ldc.i4.0
0x22bca  conv.i8
0x22bcb  ldloca.s 4
0x22bcd  call     class Microsoft.Internal.GDIExporter.GdiFontResourceSafeHandle Microsoft.Internal.GDIExporter.CNativeMethods::AddFontMemResourceEx([hasfieldmarshal] unsigned int8[] font, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 cbFont, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int8* pdv, [out] modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32* pcFonts)
0x22bd2  stloc.2
0x22bd3  ldloc.2
0x22bd4  ret
```
