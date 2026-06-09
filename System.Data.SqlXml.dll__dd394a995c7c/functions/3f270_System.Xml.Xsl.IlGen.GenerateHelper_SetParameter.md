# System.Xml.Xsl.IlGen.GenerateHelper::SetParameter

- ea: `0x3f270`
- end: `0x3f2ad`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::SetParameter`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x4ad40`

## callees

- `0x3770`
- `0x3f270`
- `0x3ff50`
- `0x3ffb0`

## string_xrefs

- `0x3f2a2`: `XmlIl_TooManyParameters`

## pseudocode

```c

```

## disassembly

```asm
0x3f270  ldarg.1
0x3f271  unbox.any [mscorlib]System.Int32
0x3f276  stloc.0
0x3f277  ldloc.0
0x3f278  ldc.i4   0xFF
0x3f27d  bgt.s    loc_3F28D
0x3f27f  ldarg.0
0x3f280  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Starg_S
0x3f285  ldloc.0
0x3f286  conv.u1
0x3f287  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, unsigned int8 byteVal)
0x3f28c  ret
0x3f28d  ldloc.0
0x3f28e  ldc.i4   0xFFFF
0x3f293  bgt.s    loc_3F2A2
0x3f295  ldarg.0
0x3f296  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Starg
0x3f29b  ldloc.0
0x3f29c  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, int32 intVal)
0x3f2a1  ret
0x3f2a2  ldstr    aXmlilToomanypa// "XmlIl_TooManyParameters"
0x3f2a7  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string message)
0x3f2ac  throw
```
