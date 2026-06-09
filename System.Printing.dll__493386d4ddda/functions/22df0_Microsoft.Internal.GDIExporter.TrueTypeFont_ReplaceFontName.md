# Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFontName

- ea: `0x22df0`
- end: `0x22e6a`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFontName`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22b70`

## callees

- `0x22df0`
- `0x22e70`
- `0x23340`
- `0x23360`

## pseudocode

```c

```

## disassembly

```asm
0x22df0  ldc.i4.0
0x22df1  stloc.1
0x22df2  ldarg.0
0x22df3  ldc.i4.0
0x22df4  call     instance unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::read32(unsigned int32 offset)
0x22df9  ldc.i4   0x74746366
0x22dfe  bne.un.s loc_22E26
0x22e00  ldarg.0
0x22e01  ldc.i4.8
0x22e02  call     instance unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::read32(unsigned int32 offset)
0x22e07  stloc.s  5
0x22e09  ldarg.0
0x22e0a  ldfld    unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::m_faceIndex
0x22e0f  stloc.s  4
0x22e11  ldloc.s  4
0x22e13  ldloc.s  5
0x22e15  blt.un.s loc_22E19
0x22e17  ldnull
0x22e18  ret
0x22e19  ldarg.0
0x22e1a  ldloc.s  4
0x22e1c  ldc.i4.3
0x22e1d  add
0x22e1e  ldc.i4.4
0x22e1f  mul
0x22e20  call     instance unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::read32(unsigned int32 offset)
0x22e25  stloc.1
0x22e26  ldarg.0
0x22e27  ldloc.1
0x22e28  call     instance unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::read32(unsigned int32 offset)
0x22e2d  pop
0x22e2e  ldarg.0
0x22e2f  ldloc.1
0x22e30  ldc.i4.4
0x22e31  add
0x22e32  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x22e37  stloc.3
0x22e38  ldc.i4.0
0x22e39  stloc.2
0x22e3a  ldc.i4.0
0x22e3b  ldloc.3
0x22e3c  bge.s    loc_22E68
0x22e3e  ldloc.1
0x22e3f  ldc.i4.s 0xC
0x22e41  add
0x22e42  stloc.0
0x22e43  ldarg.0
0x22e44  ldloc.0
0x22e45  call     instance unsigned int32 Microsoft.Internal.GDIExporter.TrueTypeFont::read32(unsigned int32 offset)
0x22e4a  ldc.i4   0x6E616D65
0x22e4f  beq.s    loc_22E60
0x22e51  ldloc.2
0x22e52  ldc.i4.1
0x22e53  add
0x22e54  stloc.2
0x22e55  ldloc.0
0x22e56  ldc.i4.s 0x10
0x22e58  add
0x22e59  stloc.0
0x22e5a  ldloc.2
0x22e5b  ldloc.3
0x22e5c  blt.s    loc_22E43
0x22e5e  br.s     loc_22E68
0x22e60  ldarg.0
0x22e61  ldloc.0
0x22e62  call     instance string Microsoft.Internal.GDIExporter.TrueTypeFont::ProcessNameTable(unsigned int32 pos)
0x22e67  ret
0x22e68  ldnull
0x22e69  ret
```
