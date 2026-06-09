# Microsoft.Internal.GDIExporter.FontStreamContext::UpdateStreamLength

- ea: `0x22980`
- end: `0x229bb`
- name: `Microsoft.Internal.GDIExporter.FontStreamContext::UpdateStreamLength`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x229c0`
- `0x22b70`

## callees

- `0x228a0`
- `0x22980`

## pseudocode

```c

```

## disassembly

```asm
0x22980  ldarg.0
0x22981  ldfld    int32 Microsoft.Internal.GDIExporter.FontStreamContext::_streamLength
0x22986  brtrue.s loc_229BA
0x22988  ldarg.0
0x22989  call     instance class [mscorlib]System.IO.Stream Microsoft.Internal.GDIExporter.FontStreamContext::GetStream()
0x2298e  stloc.0
0x2298f  ldloc.0
0x22990  brfalse.s loc_229AF
0x22992  ldloc.0
0x22993  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x22998  ldsfld   modopt([mscorlib]System.Runtime.CompilerServices.IsConst) int32 Microsoft.Internal.GDIExporter.FontStreamContext::MaximumStreamLength
0x2299d  conv.i8
0x2299e  bge.s    loc_229AF
0x229a0  ldarg.0
0x229a1  ldloc.0
0x229a2  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x229a7  conv.i4
0x229a8  stfld    int32 Microsoft.Internal.GDIExporter.FontStreamContext::_streamLength
0x229ad  br.s     loc_229BA
0x229af  ldarg.0
0x229b0  ldsfld   modopt([mscorlib]System.Runtime.CompilerServices.IsConst) int32 Microsoft.Internal.GDIExporter.FontStreamContext::MaximumStreamLength
0x229b5  stfld    int32 Microsoft.Internal.GDIExporter.FontStreamContext::_streamLength
0x229ba  ret
```
