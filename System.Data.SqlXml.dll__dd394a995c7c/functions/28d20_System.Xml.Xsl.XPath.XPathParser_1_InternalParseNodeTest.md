# System.Xml.Xsl.XPath.XPathParser`1::InternalParseNodeTest

- ea: `0x28d20`
- end: `0x28e42`
- name: `System.Xml.Xsl.XPath.XPathParser`1::InternalParseNodeTest`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28d20`
- `0x29ea0`
- `0x29f40`
- `0x29f50`
- `0x29f60`
- `0x29fa0`
- `0x29fb0`
- `0x2a000`
- `0x2a7f0`
- `0x2a800`
- `0x2a890`

## string_xrefs

- `0x28d5e`: `comment`
- `0x28e27`: `XPath_NodeTestExpected`

## pseudocode

```c

```

## disassembly

```asm
0x28d20  ldarg.0
0x28d21  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28d26  stloc.0
0x28d27  ldloc.0
0x28d28  ldc.i4.s 0x15
0x28d2a  beq.s    loc_28D39
0x28d2c  ldloc.0
0x28d2d  ldc.i4.s 0x2A
0x28d2f  beq      loc_28E10
0x28d34  br       loc_28E26
0x28d39  ldarg.0
0x28d3a  callvirt instance bool System.Xml.Xsl.XPath.XPathScanner::get_CanBeFunction()
0x28d3f  brfalse  loc_28DDD
0x28d44  ldarg.0
0x28d45  call     bool class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::IsNodeType(class System.Xml.Xsl.XPath.XPathScanner)
0x28d4a  brfalse  loc_28DDD
0x28d4f  ldarg.3
0x28d50  ldnull
0x28d51  stind.ref
0x28d52  ldarg.s  4
0x28d54  ldnull
0x28d55  stind.ref
0x28d56  ldarg.0
0x28d57  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28d5c  stloc.1
0x28d5d  ldloc.1
0x28d5e  ldstr    aComment// "comment"
0x28d63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28d68  brtrue.s loc_28D86
0x28d6a  ldloc.1
0x28d6b  ldstr    aText// "text"
0x28d70  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28d75  brtrue.s loc_28D8B
0x28d77  ldloc.1
0x28d78  ldstr    aNode// "node"
0x28d7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28d82  brtrue.s loc_28D90
0x28d84  br.s     loc_28D96
0x28d86  ldarg.2
0x28d87  ldc.i4.8
0x28d88  stind.i4
0x28d89  br.s     loc_28D99
0x28d8b  ldarg.2
0x28d8c  ldc.i4.4
0x28d8d  stind.i4
0x28d8e  br.s     loc_28D99
0x28d90  ldarg.2
0x28d91  ldc.i4.s 9
0x28d93  stind.i4
0x28d94  br.s     loc_28D99
0x28d96  ldarg.2
0x28d97  ldc.i4.7
0x28d98  stind.i4
0x28d99  ldarg.0
0x28d9a  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28d9f  ldarg.0
0x28da0  ldc.i4.s 0x28
0x28da2  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::PassToken(valuetype System.Xml.Xsl.XPath.LexKind t)
0x28da7  ldarg.2
0x28da8  ldind.i4
0x28da9  ldc.i4.7
0x28daa  bne.un.s loc_28DD4
0x28dac  ldarg.0
0x28dad  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28db2  ldc.i4.s 0x29
0x28db4  beq.s    loc_28DD4
0x28db6  ldarg.0
0x28db7  ldc.i4.s 0x16
0x28db9  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::CheckToken(valuetype System.Xml.Xsl.XPath.LexKind t)
0x28dbe  ldarg.3
0x28dbf  ldsfld   string [mscorlib]System.String::Empty
0x28dc4  stind.ref
0x28dc5  ldarg.s  4
0x28dc7  ldarg.0
0x28dc8  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_StringValue()
0x28dcd  stind.ref
0x28dce  ldarg.0
0x28dcf  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28dd4  ldarg.0
0x28dd5  ldc.i4.s 0x29
0x28dd7  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::PassToken(valuetype System.Xml.Xsl.XPath.LexKind t)
0x28ddc  ret
0x28ddd  ldarg.3
0x28dde  ldarg.0
0x28ddf  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Prefix()
0x28de4  stind.ref
0x28de5  ldarg.s  4
0x28de7  ldarg.0
0x28de8  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_Name()
0x28ded  stind.ref
0x28dee  ldarg.2
0x28def  ldarg.1
0x28df0  call     valuetype [System.Xml]System.Xml.XPath.XPathNodeType class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::PrincipalNodeType(valuetype System.Xml.Xsl.XPath.XPathAxis)
0x28df5  stind.i4
0x28df6  ldarg.0
0x28df7  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28dfc  ldarg.s  4
0x28dfe  ldind.ref
0x28dff  ldstr    asc_580B6// "*"
0x28e04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28e09  brfalse.s loc_28E41
0x28e0b  ldarg.s  4
0x28e0d  ldnull
0x28e0e  stind.ref
0x28e0f  ret
0x28e10  ldarg.3
0x28e11  ldnull
0x28e12  stind.ref
0x28e13  ldarg.s  4
0x28e15  ldnull
0x28e16  stind.ref
0x28e17  ldarg.2
0x28e18  ldarg.1
0x28e19  call     valuetype [System.Xml]System.Xml.XPath.XPathNodeType class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::PrincipalNodeType(valuetype System.Xml.Xsl.XPath.XPathAxis)
0x28e1e  stind.i4
0x28e1f  ldarg.0
0x28e20  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28e25  ret
0x28e26  ldarg.0
0x28e27  ldstr    aXpathNodeteste// "XPath_NodeTestExpected"
0x28e2c  ldc.i4.1
0x28e2d  newarr   [mscorlib]System.String
0x28e32  dup
0x28e33  ldc.i4.0
0x28e34  ldarg.0
0x28e35  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_RawValue()
0x28e3a  stelem.ref
0x28e3b  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28e40  throw
0x28e41  ret
```
