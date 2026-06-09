# System.Xml.Xsl.IlGen.GenerateHelper::LoadParameter

- ea: `0x3f1f0`
- end: `0x3f26e`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::LoadParameter`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x405c0`
- `0x4ad40`

## callees

- `0x3770`
- `0x3f1f0`
- `0x3ff40`
- `0x3ff50`
- `0x3ffb0`

## string_xrefs

- `0x3f263`: `XmlIl_TooManyParameters`

## pseudocode

```c

```

## disassembly

```asm
0x3f1f0  ldarg.1
0x3f1f1  switch   loc_3F208, loc_3F214, loc_3F220, loc_3F22C
0x3f206  br.s     loc_3F238
0x3f208  ldarg.0
0x3f209  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x3f20e  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x3f213  ret
0x3f214  ldarg.0
0x3f215  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x3f21a  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x3f21f  ret
0x3f220  ldarg.0
0x3f221  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_2
0x3f226  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x3f22b  ret
0x3f22c  ldarg.0
0x3f22d  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_3
0x3f232  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x3f237  ret
0x3f238  ldarg.1
0x3f239  ldc.i4   0xFF
0x3f23e  bgt.s    loc_3F24E
0x3f240  ldarg.0
0x3f241  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_S
0x3f246  ldarg.1
0x3f247  conv.u1
0x3f248  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, unsigned int8 byteVal)
0x3f24d  ret
0x3f24e  ldarg.1
0x3f24f  ldc.i4   0xFFFF
0x3f254  bgt.s    loc_3F263
0x3f256  ldarg.0
0x3f257  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg
0x3f25c  ldarg.1
0x3f25d  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, int32 intVal)
0x3f262  ret
0x3f263  ldstr    aXmlilToomanypa// "XmlIl_TooManyParameters"
0x3f268  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string message)
0x3f26d  throw
```
