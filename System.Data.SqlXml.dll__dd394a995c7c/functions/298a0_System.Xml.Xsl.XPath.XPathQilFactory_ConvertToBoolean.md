# System.Xml.Xsl.XPath.XPathQilFactory::ConvertToBoolean

- ea: `0x298a0`
- end: `0x299b5`
- name: `System.Xml.Xsl.XPath.XPathQilFactory::ConvertToBoolean`
- size: `277`
- prototype: ``
- caller_count: `6`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18430`
- `0x1aee0`
- `0x271a0`
- `0x27ac0`
- `0x27c40`
- `0x29780`

## callees

- `0x1f80`
- `0x23d0`
- `0x298a0`
- `0x373b0`
- `0x373e0`
- `0x376a0`
- `0x376c0`
- `0x37a30`
- `0x37a40`
- `0x37c50`
- `0x37cb0`
- `0x37d30`
- `0x37d80`
- `0x37fe0`
- `0x38090`
- `0x380d0`
- `0x38120`
- `0x383c0`
- `0x384a0`

## pseudocode

```c

```

## disassembly

```asm
0x298a0  ldarg.1
0x298a1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x298a6  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x298ab  stloc.1
0x298ac  ldloc.1
0x298ad  ldc.i4.s 0xC
0x298af  sub
0x298b0  switch   loc_29954, loc_298CE, loc_2998D, loc_2998D, loc_298D0
0x298c9  br       loc_2998D
0x298ce  ldarg.1
0x298cf  ret
0x298d0  ldarg.1
0x298d1  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x298d6  ldc.i4.s 0x17
0x298d8  beq.s    loc_2991C
0x298da  ldarg.0
0x298db  ldarg.0
0x298dc  ldarg.1
0x298dd  call     instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x298e2  dup
0x298e3  stloc.0
0x298e4  ldarg.0
0x298e5  ldarg.0
0x298e6  ldloc.0
0x298e7  ldarg.0
0x298e8  ldc.r8   0.0
0x298f1  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::Double(float64 val)
0x298f6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Lt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x298fb  ldarg.0
0x298fc  ldarg.0
0x298fd  ldc.r8   0.0
0x29906  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::Double(float64 val)
0x2990b  ldloc.0
0x2990c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Lt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x29911  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Or(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x29916  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x2991b  ret
0x2991c  ldarg.0
0x2991d  ldarg.1
0x2991e  castclass System.Xml.Xsl.Qil.QilLiteral
0x29923  call     float64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x29928  conv.r8
0x29929  ldc.r8   0.0
0x29932  blt.s    loc_2994D
0x29934  ldc.r8   0.0
0x2993d  ldarg.1
0x2993e  castclass System.Xml.Xsl.Qil.QilLiteral
0x29943  call     float64 System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x29948  conv.r8
0x29949  clt
0x2994b  br.s     loc_2994E
0x2994d  ldc.i4.1
0x2994e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Boolean(bool b)
0x29953  ret
0x29954  ldarg.1
0x29955  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x2995a  ldc.i4.s 0x14
0x2995c  beq.s    loc_29973
0x2995e  ldarg.0
0x2995f  ldarg.0
0x29960  ldarg.1
0x29961  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::StrLength(class System.Xml.Xsl.Qil.QilNode str)
0x29966  ldarg.0
0x29967  ldc.i4.0
0x29968  call     instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::Int32(int32 val)
0x2996d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Ne(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x29972  ret
0x29973  ldarg.0
0x29974  ldarg.1
0x29975  castclass System.Xml.Xsl.Qil.QilLiteral
0x2997a  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x2997f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29984  ldc.i4.0
0x29985  cgt.un
0x29987  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Boolean(bool b)
0x2998c  ret
0x2998d  ldarg.1
0x2998e  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x29993  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsNode()
0x29998  brfalse.s loc_299A8
0x2999a  ldarg.0
0x2999b  ldarg.0
0x2999c  ldarg.1
0x2999d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode set)
0x299a2  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x299a7  ret
0x299a8  ldarg.0
0x299a9  ldarg.1
0x299aa  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::BooleanX
0x299af  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltConvert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x299b4  ret
```
