# Microsoft.Internal.GDIExporter.TrueTypeFont::readString

- ea: `0x23470`
- end: `0x234a8`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::readString`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x22f10`
- `0x23050`
- `0x23220`

## callees

- `0x23470`

## pseudocode

```c

```

## disassembly

```asm
0x23470  ldarg.s  4
0x23472  callvirt instance bool [mscorlib]System.Text.Encoding::get_IsSingleByte()
0x23477  brfalse.s loc_2347D
0x23479  ldarg.2
0x2347a  stloc.0
0x2347b  br.s     loc_23481
0x2347d  ldarg.2
0x2347e  ldc.i4.1
0x2347f  shr.un
0x23480  stloc.0
0x23481  ldarg.3
0x23482  ldind.ref
0x23483  stloc.1
0x23484  ldloc.1
0x23485  brfalse.s loc_2348C
0x23487  ldloc.1
0x23488  ldlen
0x23489  ldloc.0
0x2348a  beq.s    loc_23494
0x2348c  ldarg.3
0x2348d  ldloc.0
0x2348e  newarr   [mscorlib]System.Char
0x23493  stind.ref
0x23494  ldarg.s  4
0x23496  ldarg.0
0x23497  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.TrueTypeFont::m_fontdata
0x2349c  ldarg.1
0x2349d  ldarg.2
0x2349e  ldarg.3
0x2349f  ldind.ref
0x234a0  ldc.i4.0
0x234a1  callvirt instance int32 [mscorlib]System.Text.Encoding::GetChars(unsigned int8[], int32, int32, char[], int32)
0x234a6  pop
0x234a7  ret
```
