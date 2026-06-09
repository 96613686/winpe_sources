# System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel

- ea: `0x3ff10`
- end: `0x3ff3d`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel`
- size: `45`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xdb0`
- `0x3f2b0`
- `0x3f360`
- `0x403f0`
- `0x4aa60`
- `0x4ad40`
- `0x4b5c0`
- `0x4b620`
- `0x4b810`
- `0x4bae0`
- `0x4bdc0`
- `0x4c070`
- `0x4cc30`
- `0x4d740`
- `0x4e720`
- `0x4eb20`
- `0x4ece0`
- `0x4ee70`
- `0x4f110`
- `0x4f530`
- `0x4fa80`
- `0x4faf0`

## callees

- `0x2a0`
- `0x3fe20`
- `0x3ff10`

## pseudocode

```c

```

## disassembly

```asm
0x3ff10  ldarg.0
0x3ff11  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.IlGen.GenerateHelper::lastSourceInfo
0x3ff16  brfalse.s loc_3FF30
0x3ff18  ldarg.0
0x3ff19  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.IlGen.GenerateHelper::lastSourceInfo
0x3ff1e  callvirt instance bool System.Xml.Xsl.ISourceLineInfo::get_IsNoSource()
0x3ff23  brtrue.s loc_3FF30
0x3ff25  ldarg.0
0x3ff26  ldsfld   class System.Xml.Xsl.SourceLineInfo System.Xml.Xsl.SourceLineInfo::NoSource
0x3ff2b  call     instance void System.Xml.Xsl.IlGen.GenerateHelper::DebugSequencePoint(class System.Xml.Xsl.ISourceLineInfo sourceInfo)
0x3ff30  ldarg.0
0x3ff31  ldfld    class [mscorlib]System.Reflection.Emit.ILGenerator System.Xml.Xsl.IlGen.GenerateHelper::ilgen
0x3ff36  ldarg.1
0x3ff37  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label)
0x3ff3c  ret
```
