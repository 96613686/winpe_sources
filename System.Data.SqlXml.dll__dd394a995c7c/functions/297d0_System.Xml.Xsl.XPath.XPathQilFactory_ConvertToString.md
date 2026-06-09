# System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString

- ea: `0x297d0`
- end: `0x2989e`
- name: `System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString`
- size: `206`
- prototype: ``
- caller_count: `14`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x17ae0`
- `0x18290`
- `0x183d0`
- `0x18400`
- `0x18860`
- `0x18c10`
- `0x198c0`
- `0x1a9a0`
- `0x1aee0`
- `0x1b310`
- `0x1b7d0`
- `0x27c40`
- `0x29780`
- `0x29b80`

## callees

- `0x1f80`
- `0x23d0`
- `0x3350`
- `0x295c0`
- `0x297d0`
- `0x373e0`
- `0x376a0`
- `0x376c0`
- `0x37a20`
- `0x37de0`
- `0x383d0`
- `0x384a0`

## pseudocode

```c

```

## disassembly

```asm
0x297d0  ldarg.1
0x297d1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x297d6  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x297db  stloc.0
0x297dc  ldloc.0
0x297dd  ldc.i4.s 0xC
0x297df  sub
0x297e0  switch   loc_29874, loc_297FB, loc_29876, loc_29876, loc_29845
0x297f9  br.s     loc_29876
0x297fb  ldarg.1
0x297fc  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x29801  ldc.i4.s 0x12
0x29803  beq.s    loc_29839
0x29805  ldarg.1
0x29806  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x2980b  ldc.i4.s 0x13
0x2980d  beq.s    loc_2982D
0x2980f  ldarg.0
0x29810  ldarg.1
0x29811  ldarg.0
0x29812  ldstr    aTrue// "true"
0x29817  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x2981c  ldarg.0
0x2981d  ldstr    aFalse// "false"
0x29822  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x29827  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x2982c  ret
0x2982d  ldarg.0
0x2982e  ldstr    aFalse// "false"
0x29833  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x29838  ret
0x29839  ldarg.0
0x2983a  ldstr    aTrue// "true"
0x2983f  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x29844  ret
0x29845  ldarg.1
0x29846  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x2984b  ldc.i4.s 0x17
0x2984d  beq.s    loc_2985C
0x2984f  ldarg.0
0x29850  ldarg.1
0x29851  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x29856  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x2985b  ret
0x2985c  ldarg.0
0x2985d  ldarg.1
0x2985e  castclass System.Xml.Xsl.Qil.QilLiteral
0x29863  call     float64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x29868  conv.r8
0x29869  call     string System.Xml.Xsl.XPathConvert::DoubleToString(float64 dbl)
0x2986e  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x29873  ret
0x29874  ldarg.1
0x29875  ret
0x29876  ldarg.1
0x29877  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x2987c  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsNode()
0x29881  brfalse.s loc_29891
0x29883  ldarg.0
0x29884  ldarg.0
0x29885  ldarg.1
0x29886  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::SafeDocOrderDistinct(class System.Xml.Xsl.Qil.QilNode n)
0x2988b  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x29890  ret
0x29891  ldarg.0
0x29892  ldarg.1
0x29893  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x29898  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x2989d  ret
```
