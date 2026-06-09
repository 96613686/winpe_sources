# System.Xml.Xsl.Xslt.QilGenerator::CompileSort

- ea: `0x18c10`
- end: `0x18dd0`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileSort`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18700`

## callees

- `0x167e0`
- `0x16810`
- `0x18750`
- `0x18860`
- `0x18ac0`
- `0x18c10`
- `0x19d10`
- `0x1bf20`
- `0x1bfa0`
- `0x1bfb0`
- `0x1bfc0`
- `0x1c000`
- `0x1db80`
- `0x1db90`
- `0x297d0`
- `0x37720`
- `0x377c0`
- `0x37a00`
- `0x38190`

## string_xrefs

- `0x18cf0`: `http://collations.microsoft.com`

## pseudocode

```c

```

## disassembly

```asm
0x18c10  ldarg.0
0x18c11  ldarg.1
0x18c12  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x18c17  pop
0x18c18  ldarg.1
0x18c19  callvirt instance bool System.Xml.Xsl.Xslt.XslNode::get_ForwardsCompatible()
0x18c1e  stloc.s  5
0x18c20  ldarg.0
0x18c21  ldarg.1
0x18c22  callvirt instance string System.Xml.Xsl.Xslt.XslNode::get_Select()
0x18c27  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileXPathExpression(string expr)
0x18c2c  stloc.0
0x18c2d  ldarg.1
0x18c2e  ldfld    string System.Xml.Xsl.Xslt.Sort::Lang
0x18c33  brtrue.s loc_18C4D
0x18c35  ldarg.1
0x18c36  ldfld    string System.Xml.Xsl.Xslt.Sort::DataType
0x18c3b  brtrue.s loc_18C4D
0x18c3d  ldarg.1
0x18c3e  ldfld    string System.Xml.Xsl.Xslt.Sort::Order
0x18c43  brtrue.s loc_18C4D
0x18c45  ldarg.1
0x18c46  ldfld    string System.Xml.Xsl.Xslt.Sort::CaseOrder
0x18c4b  brfalse.s loc_18CC9
0x18c4d  ldarg.0
0x18c4e  ldfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x18c53  stloc.s  9
0x18c55  ldarg.0
0x18c56  ldarg.3
0x18c57  ldobj    System.Xml.Xsl.Xslt.LoopFocus
0x18c5c  stfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x18c61  ldarg.0
0x18c62  ldarg.1
0x18c63  ldfld    string System.Xml.Xsl.Xslt.Sort::Lang
0x18c68  ldloc.s  5
0x18c6a  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileLangAttribute(string attValue, bool fwdCompat)
0x18c6f  stloc.2
0x18c70  ldarg.0
0x18c71  ldarg.1
0x18c72  ldfld    string System.Xml.Xsl.Xslt.Sort::DataType
0x18c77  ldloc.s  5
0x18c79  ldloca.s 0
0x18c7b  ldloca.s 1
0x18c7d  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileDataTypeAttribute(string attValue, bool fwdCompat, class System.Xml.Xsl.Qil.QilNode& select, [out] class System.Xml.Xsl.Qil.QilNode& select2)
0x18c82  ldarg.0
0x18c83  ldstr    aOrder// "order"
0x18c88  ldarg.1
0x18c89  ldfld    string System.Xml.Xsl.Xslt.Sort::Order
0x18c8e  ldstr    aAscending// "ascending"
0x18c93  ldstr    aDescending// "descending"
0x18c98  ldloc.s  5
0x18c9a  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileOrderAttribute(string attName, string attValue, string value0, string value1, bool fwdCompat)
0x18c9f  stloc.3
0x18ca0  ldarg.0
0x18ca1  ldstr    aCaseOrder// "case-order"
0x18ca6  ldarg.1
0x18ca7  ldfld    string System.Xml.Xsl.Xslt.Sort::CaseOrder
0x18cac  ldstr    aLowerFirst// "lower-first"
0x18cb1  ldstr    aUpperFirst// "upper-first"
0x18cb6  ldloc.s  5
0x18cb8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileOrderAttribute(string attName, string attValue, string value0, string value1, bool fwdCompat)
0x18cbd  stloc.s  4
0x18cbf  ldarg.0
0x18cc0  ldloc.s  9
0x18cc2  stfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x18cc7  br.s     loc_18CDF
0x18cc9  ldarg.0
0x18cca  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18ccf  ldloc.0
0x18cd0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x18cd5  stloc.0
0x18cd6  ldnull
0x18cd7  dup
0x18cd8  stloc.s  4
0x18cda  dup
0x18cdb  stloc.3
0x18cdc  dup
0x18cdd  stloc.2
0x18cde  stloc.1
0x18cdf  ldarg.0
0x18ce0  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18ce5  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Reset()
0x18cea  ldarg.0
0x18ceb  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18cf0  ldstr    aHttpCollations// "http://collations.microsoft.com"
0x18cf5  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(string value)
0x18cfa  ldarg.0
0x18cfb  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d00  ldc.i4.s 0x2F
0x18d02  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(char value)
0x18d07  ldarg.0
0x18d08  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d0d  ldloc.2
0x18d0e  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(class System.Xml.Xsl.Qil.QilNode value)
0x18d13  ldc.i4.s 0x3F
0x18d15  stloc.s  6
0x18d17  ldloc.3
0x18d18  brfalse.s loc_18D47
0x18d1a  ldarg.0
0x18d1b  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d20  ldloc.s  6
0x18d22  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(char value)
0x18d27  ldarg.0
0x18d28  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d2d  ldstr    aDescendingorde// "descendingOrder="
0x18d32  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(string value)
0x18d37  ldarg.0
0x18d38  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d3d  ldloc.3
0x18d3e  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(class System.Xml.Xsl.Qil.QilNode value)
0x18d43  ldc.i4.s 0x26
0x18d45  stloc.s  6
0x18d47  ldloc.s  4
0x18d49  brfalse.s loc_18D79
0x18d4b  ldarg.0
0x18d4c  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d51  ldloc.s  6
0x18d53  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(char value)
0x18d58  ldarg.0
0x18d59  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d5e  ldstr    aUpperfirst// "upperFirst="
0x18d63  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(string value)
0x18d68  ldarg.0
0x18d69  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d6e  ldloc.s  4
0x18d70  callvirt instance void System.Xml.Xsl.Xslt.QilStrConcatenator::Append(class System.Xml.Xsl.Qil.QilNode value)
0x18d75  ldc.i4.s 0x26
0x18d77  stloc.s  6
0x18d79  ldarg.0
0x18d7a  ldfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x18d7f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilStrConcatenator::ToQil()
0x18d84  stloc.s  7
0x18d86  ldarg.0
0x18d87  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18d8c  ldloc.0
0x18d8d  ldloc.s  7
0x18d8f  callvirt instance class System.Xml.Xsl.Qil.QilSortKey System.Xml.Xsl.Qil.QilPatternFactory::SortKey(class System.Xml.Xsl.Qil.QilNode key, class System.Xml.Xsl.Qil.QilNode collation)
0x18d94  stloc.s  8
0x18d96  ldarg.2
0x18d97  ldloc.s  8
0x18d99  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x18d9e  ldloc.1
0x18d9f  brfalse.s loc_18DC9
0x18da1  ldarg.0
0x18da2  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18da7  ldloc.1
0x18da8  ldloc.s  7
0x18daa  ldarg.0
0x18dab  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18db0  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x18db5  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::DeepClone(class System.Xml.Xsl.Qil.QilFactory f)
0x18dba  callvirt instance class System.Xml.Xsl.Qil.QilSortKey System.Xml.Xsl.Qil.QilPatternFactory::SortKey(class System.Xml.Xsl.Qil.QilNode key, class System.Xml.Xsl.Qil.QilNode collation)
0x18dbf  stloc.s  8
0x18dc1  ldarg.2
0x18dc2  ldloc.s  8
0x18dc4  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x18dc9  ldarg.0
0x18dca  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x18dcf  ret
```
