# Microsoft.Internal.GDIExporter.TrueTypeFont::writeString

- ea: `0x23410`
- end: `0x23434`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::writeString`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23050`
- `0x23200`
- `0x23220`

## callees

- `0x23410`

## pseudocode

```c

```

## disassembly

```asm
0x23410  ldarg.s  4
0x23412  callvirt instance bool [mscorlib]System.Text.Encoding::get_IsSingleByte()
0x23417  brfalse.s loc_2341D
0x23419  ldarg.2
0x2341a  stloc.0
0x2341b  br.s     loc_23421
0x2341d  ldarg.2
0x2341e  ldc.i4.1
0x2341f  shr.un
0x23420  stloc.0
0x23421  ldarg.s  4
0x23423  ldarg.3
0x23424  ldc.i4.0
0x23425  ldloc.0
0x23426  ldarg.0
0x23427  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.TrueTypeFont::m_fontdata
0x2342c  ldarg.1
0x2342d  callvirt instance int32 [mscorlib]System.Text.Encoding::GetBytes(char[], int32, int32, unsigned int8[], int32)
0x23432  pop
0x23433  ret
```
