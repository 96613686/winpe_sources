# System.Xml.Xsl.IlGen.GenerateHelper::Call

- ea: `0x3f3e0`
- end: `0x3f41e`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::Call`
- size: `62`
- prototype: ``
- caller_count: `93`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xd50`
- `0xdb0`
- `0xed0`
- `0xf50`
- `0x3ef70`
- `0x3f020`
- `0x3f150`
- `0x3f190`
- `0x3f1b0`
- `0x3f3b0`
- `0x3f420`
- `0x3f4b0`
- `0x3f620`
- `0x3f710`
- `0x3f750`
- `0x3f780`
- `0x3f7c0`
- `0x3f7f0`
- `0x3f820`
- `0x3f850`
- `0x3f880`
- `0x3f8a0`
- `0x3f8c0`
- `0x3f8e0`
- `0x3f900`
- `0x3f930`
- `0x3f950`
- `0x3f9a0`
- `0x3f9d0`
- `0x3f9f0`
- `0x3fa10`
- `0x3fa30`
- `0x3fa50`
- `0x3fad0`
- `0x3fb00`
- `0x3fb20`
- `0x3fba0`
- `0x3fbd0`
- `0x3fbf0`
- `0x3fc30`
- `0x3fc40`
- `0x3fc60`
- `0x3fc80`
- `0x3fca0`
- `0x3fcc0`
- `0x3fce0`
- `0x3fd40`
- `0x405c0`
- `0x40670`
- `0x40820`

## callees

- `0x3f3e0`
- `0x3fe80`

## pseudocode

```c

```

## disassembly

```asm
0x3f3e0  ldarg.1
0x3f3e1  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsVirtual()
0x3f3e6  brtrue.s loc_3F3F7
0x3f3e8  ldarg.1
0x3f3e9  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsAbstract()
0x3f3ee  brtrue.s loc_3F3F7
0x3f3f0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Call
0x3f3f5  br.s     loc_3F3FC
0x3f3f7  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Callvirt
0x3f3fc  stloc.0
0x3f3fd  ldarg.0
0x3f3fe  ldfld    class [mscorlib]System.Reflection.Emit.ILGenerator System.Xml.Xsl.IlGen.GenerateHelper::ilgen
0x3f403  ldloc.0
0x3f404  ldarg.1
0x3f405  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo)
0x3f40a  ldarg.0
0x3f40b  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.IlGen.GenerateHelper::lastSourceInfo
0x3f410  brfalse.s loc_3F41D
0x3f412  ldarg.0
0x3f413  ldsfld   class System.Xml.Xsl.SourceLineInfo System.Xml.Xsl.SourceLineInfo::NoSource
0x3f418  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkSequencePoint(class System.Xml.Xsl.ISourceLineInfo sourceInfo)
0x3f41d  ret
```
