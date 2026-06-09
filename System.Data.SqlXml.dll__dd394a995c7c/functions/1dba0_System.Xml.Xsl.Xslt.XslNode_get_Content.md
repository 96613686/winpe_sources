# System.Xml.Xsl.Xslt.XslNode::get_Content

- ea: `0x1dba0`
- end: `0x1dbb2`
- name: `System.Xml.Xsl.Xslt.XslNode::get_Content`
- size: `18`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x16b70`
- `0x17130`
- `0x17550`
- `0x175d0`
- `0x17740`
- `0x17890`
- `0x17c70`
- `0x17cc0`
- `0x17d50`
- `0x17df0`
- `0x17f90`
- `0x18110`
- `0x181b0`
- `0x18430`
- `0x18470`
- `0x18510`
- `0x18600`
- `0x1a160`
- `0x1dcf0`
- `0x1e320`
- `0x1e850`
- `0x1e900`
- `0x1ea20`
- `0x1ec70`
- `0x1efb0`
- `0x1f4b0`
- `0x1f5b0`
- `0x22450`
- `0x224c0`
- `0x26d10`

## callees

- `0x1dba0`

## pseudocode

```c

```

## disassembly

```asm
0x1dba0  ldarg.0
0x1dba1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::content
0x1dba6  stloc.0
0x1dba7  ldloc.0
0x1dba8  dup
0x1dba9  brtrue.s loc_1DBB1
0x1dbab  pop
0x1dbac  ldsfld   class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::EmptyList
0x1dbb1  ret
```
