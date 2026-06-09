# ::Microsoft.Internal.GDIExporter.CopyTo

- ea: `0x1620`
- end: `0x1652`
- name: `::Microsoft.Internal.GDIExporter.CopyTo`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ffe0`

## callees

- `0x1620`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldarg.1
0x1621  ldarg.2
0x1622  call     instance int32 [mscorlib]System.String::get_Length()
0x1627  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x162c  starg.s  1
0x162e  ldarg.1
0x162f  ldc.i4.0
0x1630  ble.s    loc_1651
0x1632  ldarg.1
0x1633  conv.i8
0x1634  ldc.i4.2
0x1635  conv.i8
0x1636  mul
0x1637  stloc.0
0x1638  ldarg.1
0x1639  ldc.i4.m1
0x163a  add
0x163b  starg.s  1
0x163d  ldloc.0
0x163e  ldc.i4.2
0x163f  conv.i8
0x1640  sub
0x1641  stloc.0
0x1642  ldloc.0
0x1643  ldarg.0
0x1644  add
0x1645  ldarg.2
0x1646  ldarg.1
0x1647  call     instance char [mscorlib]System.String::get_Chars(int32)
0x164c  stind.i2
0x164d  ldarg.1
0x164e  ldc.i4.0
0x164f  bgt.s    loc_1638
0x1651  ret
```
