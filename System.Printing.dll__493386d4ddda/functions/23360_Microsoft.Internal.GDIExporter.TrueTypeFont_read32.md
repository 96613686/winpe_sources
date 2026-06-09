# Microsoft.Internal.GDIExporter.TrueTypeFont::read32

- ea: `0x23360`
- end: `0x23388`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::read32`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22df0`
- `0x22e70`
- `0x23310`

## pseudocode

```c

```

## disassembly

```asm
0x23360  ldarg.0
0x23361  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.TrueTypeFont::m_fontdata
0x23366  stloc.0
0x23367  ldloc.0
0x23368  ldarg.1
0x23369  ldc.i4.2
0x2336a  add
0x2336b  ldelem.u1
0x2336c  ldc.i4   0x100
0x23371  mul
0x23372  ldloc.0
0x23373  ldarg.1
0x23374  ldc.i4.3
0x23375  add
0x23376  ldelem.u1
0x23377  add
0x23378  ldloc.0
0x23379  ldarg.1
0x2337a  ldc.i4.1
0x2337b  add
0x2337c  ldelem.u1
0x2337d  ldloc.0
0x2337e  ldarg.1
0x2337f  ldelem.u1
0x23380  ldc.i4.8
0x23381  shl
0x23382  or
0x23383  ldc.i4.s 0x10
0x23385  shl
0x23386  or
0x23387  ret
```
