# Microsoft.Internal.GDIExporter.TrueTypeFont::read16

- ea: `0x23340`
- end: `0x23354`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::read16`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22df0`
- `0x22f10`
- `0x23050`

## pseudocode

```c

```

## disassembly

```asm
0x23340  ldarg.0
0x23341  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.TrueTypeFont::m_fontdata
0x23346  stloc.0
0x23347  ldloc.0
0x23348  ldarg.1
0x23349  ldc.i4.1
0x2334a  add
0x2334b  ldelem.u1
0x2334c  ldloc.0
0x2334d  ldarg.1
0x2334e  ldelem.u1
0x2334f  ldc.i4.8
0x23350  shl
0x23351  or
0x23352  conv.u2
0x23353  ret
```
