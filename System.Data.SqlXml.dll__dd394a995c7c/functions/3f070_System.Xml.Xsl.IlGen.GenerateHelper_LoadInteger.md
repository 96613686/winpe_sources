# System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger

- ea: `0x3f070`
- end: `0x3f12b`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger`
- size: `187`
- prototype: ``
- caller_count: `27`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xf50`
- `0x3f2d0`
- `0x3f560`
- `0x3f850`
- `0x3f880`
- `0x3f8a0`
- `0x3f8c0`
- `0x3f900`
- `0x3f950`
- `0x3f9d0`
- `0x403f0`
- `0x40820`
- `0x4aa60`
- `0x4ad40`
- `0x4b3c0`
- `0x4bbe0`
- `0x4bdc0`
- `0x4c800`
- `0x4cab0`
- `0x4cc30`
- `0x4d270`
- `0x4e7a0`
- `0x4e900`
- `0x4efa0`
- `0x4f110`
- `0x4faf0`
- `0x4fe10`

## callees

- `0x3f070`
- `0x3ff40`
- `0x3ffb0`
- `0x40010`

## pseudocode

```c

```

## disassembly

```asm
0x3f070  ldarg.1
0x3f071  ldc.i4.m1
0x3f072  blt      loc_3F106
0x3f077  ldarg.1
0x3f078  ldc.i4.s 9
0x3f07a  bge      loc_3F106
0x3f07f  ldarg.1
0x3f080  ldc.i4.m1
0x3f081  sub
0x3f082  switch   loc_3F0B0, loc_3F0B8, loc_3F0C0, loc_3F0C8, loc_3F0D0, loc_3F0D8, loc_3F0E0, loc_3F0E8, loc_3F0F0, loc_3F0F8
0x3f0af  ret
0x3f0b0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_M1
0x3f0b5  stloc.0
0x3f0b6  br.s     loc_3F0FE
0x3f0b8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_0
0x3f0bd  stloc.0
0x3f0be  br.s     loc_3F0FE
0x3f0c0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_1
0x3f0c5  stloc.0
0x3f0c6  br.s     loc_3F0FE
0x3f0c8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_2
0x3f0cd  stloc.0
0x3f0ce  br.s     loc_3F0FE
0x3f0d0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_3
0x3f0d5  stloc.0
0x3f0d6  br.s     loc_3F0FE
0x3f0d8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_4
0x3f0dd  stloc.0
0x3f0de  br.s     loc_3F0FE
0x3f0e0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_5
0x3f0e5  stloc.0
0x3f0e6  br.s     loc_3F0FE
0x3f0e8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_6
0x3f0ed  stloc.0
0x3f0ee  br.s     loc_3F0FE
0x3f0f0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_7
0x3f0f5  stloc.0
0x3f0f6  br.s     loc_3F0FE
0x3f0f8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_8
0x3f0fd  stloc.0
0x3f0fe  ldarg.0
0x3f0ff  ldloc.0
0x3f100  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x3f105  ret
0x3f106  ldarg.1
0x3f107  ldc.i4.s 0x80
0x3f109  blt.s    loc_3F11E
0x3f10b  ldarg.1
0x3f10c  ldc.i4.s 0x7F
0x3f10e  bgt.s    loc_3F11E
0x3f110  ldarg.0
0x3f111  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_S
0x3f116  ldarg.1
0x3f117  conv.i1
0x3f118  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, int8 sbyteVal)
0x3f11d  ret
0x3f11e  ldarg.0
0x3f11f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4
0x3f124  ldarg.1
0x3f125  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, int32 intVal)
0x3f12a  ret
```
