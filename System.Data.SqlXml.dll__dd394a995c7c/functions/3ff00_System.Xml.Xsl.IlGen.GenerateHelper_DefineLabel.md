# System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel

- ea: `0x3ff00`
- end: `0x3ff0e`
- name: `System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel`
- size: `14`
- prototype: ``
- caller_count: `32`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0xdb0`
- `0x3f360`
- `0x403f0`
- `0x4aa60`
- `0x4ad40`
- `0x4b570`
- `0x4b620`
- `0x4b750`
- `0x4b810`
- `0x4bae0`
- `0x4bbe0`
- `0x4bdc0`
- `0x4c070`
- `0x4c350`
- `0x4c770`
- `0x4cc30`
- `0x4d520`
- `0x4d740`
- `0x4d910`
- `0x4e720`
- `0x4eb20`
- `0x4ece0`
- `0x4ee70`
- `0x4f110`
- `0x4f530`
- `0x4f9c0`
- `0x4fa80`
- `0x4faf0`
- `0x4fee0`
- `0x50130`
- `0x50210`
- `0x50780`

## pseudocode

```c

```

## disassembly

```asm
0x3ff00  ldarg.0
0x3ff01  ldfld    class [mscorlib]System.Reflection.Emit.ILGenerator System.Xml.Xsl.IlGen.GenerateHelper::ilgen
0x3ff06  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label [mscorlib]System.Reflection.Emit.ILGenerator::DefineLabel()
0x3ff0b  stloc.0
0x3ff0c  ldloc.0
0x3ff0d  ret
```
