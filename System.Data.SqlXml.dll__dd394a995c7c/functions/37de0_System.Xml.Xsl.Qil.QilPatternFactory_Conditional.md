# System.Xml.Xsl.Qil.QilPatternFactory::Conditional

- ea: `0x37de0`
- end: `0x37e27`
- name: `System.Xml.Xsl.Qil.QilPatternFactory::Conditional`
- size: `71`
- prototype: ``
- caller_count: `23`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x159f0`
- `0x15a60`
- `0x15aa0`
- `0x15bb0`
- `0x18290`
- `0x18430`
- `0x18750`
- `0x18860`
- `0x18ac0`
- `0x19200`
- `0x193a0`
- `0x194f0`
- `0x195f0`
- `0x1a360`
- `0x1b310`
- `0x1b6a0`
- `0x1b7d0`
- `0x27ac0`
- `0x280d0`
- `0x295c0`
- `0x297d0`
- `0x299c0`
- `0x37de0`

## callees

- `0x36450`
- `0x376a0`
- `0x37de0`
- `0x3a530`

## pseudocode

```c

```

## disassembly

```asm
0x37de0  ldarg.0
0x37de1  ldfld    bool System.Xml.Xsl.Qil.QilPatternFactory::debug
0x37de6  brtrue.s loc_37E18
0x37de8  ldarg.1
0x37de9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x37dee  stloc.0
0x37def  ldloc.0
0x37df0  ldc.i4.s 0x12
0x37df2  beq.s    loc_37E00
0x37df4  ldloc.0
0x37df5  ldc.i4.s 0x13
0x37df7  beq.s    loc_37E02
0x37df9  ldloc.0
0x37dfa  ldc.i4.s 0x1E
0x37dfc  beq.s    loc_37E04
0x37dfe  br.s     loc_37E18
0x37e00  ldarg.2
0x37e01  ret
0x37e02  ldarg.3
0x37e03  ret
0x37e04  ldarg.0
0x37e05  ldarg.1
0x37e06  castclass System.Xml.Xsl.Qil.QilUnary
0x37e0b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x37e10  ldarg.3
0x37e11  ldarg.2
0x37e12  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x37e17  ret
0x37e18  ldarg.0
0x37e19  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x37e1e  ldarg.1
0x37e1f  ldarg.2
0x37e20  ldarg.3
0x37e21  callvirt instance class System.Xml.Xsl.Qil.QilTernary System.Xml.Xsl.Qil.QilFactory::Conditional(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode center, class System.Xml.Xsl.Qil.QilNode right)
0x37e26  ret
```
