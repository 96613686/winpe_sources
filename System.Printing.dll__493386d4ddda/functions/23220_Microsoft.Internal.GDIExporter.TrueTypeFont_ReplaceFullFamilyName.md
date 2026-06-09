# Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFullFamilyName

- ea: `0x23220`
- end: `0x2325a`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFullFamilyName`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x23050`

## callees

- `0x23220`
- `0x232e0`
- `0x23410`
- `0x23470`

## pseudocode

```c

```

## disassembly

```asm
0x23220  ldnull
0x23221  stloc.1
0x23222  ldarg.0
0x23223  ldarg.1
0x23224  ldarg.2
0x23225  ldloca.s 1
0x23227  ldarg.s  5
0x23229  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::readString(unsigned int32 offset, unsigned int32 byteLength, char[]& value, class [mscorlib]System.Text.Encoding encoding)
0x2322e  ldarg.s  4
0x23230  ldlen
0x23231  stloc.0
0x23232  ldloc.0
0x23233  ldarg.3
0x23234  ldlen
0x23235  bgt.s    loc_23258
0x23237  ldarg.0
0x23238  ldarg.3
0x23239  ldloc.1
0x2323a  ldloc.0
0x2323b  call     instance bool Microsoft.Internal.GDIExporter.TrueTypeFont::AreCharsEqual([hasfieldmarshal] char[] value, char[] a, unsigned int32 b)
0x23240  brfalse.s loc_23258
0x23242  ldarg.0
0x23243  ldarg.1
0x23244  ldarg.s  5
0x23246  ldarg.s  4
0x23248  callvirt instance int32 [mscorlib]System.Text.Encoding::GetByteCount(char[])
0x2324d  ldarg.s  4
0x2324f  ldarg.s  5
0x23251  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::writeString(unsigned int32 offset, unsigned int32 byteLength, char[] value, class [mscorlib]System.Text.Encoding encoding)
0x23256  ldc.i4.1
0x23257  ret
0x23258  ldc.i4.0
0x23259  ret
```
