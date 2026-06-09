# System.Xml.Xsl.XPath.XPathParser`1::ParseSubExpr

- ea: `0x28e90`
- end: `0x28f71`
- name: `System.Xml.Xsl.XPath.XPathParser`1::ParseSubExpr`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x28e90`
- `0x29ea0`
- `0x2a000`
- `0x2a890`

## string_xrefs

- `0x28eb5`: `Xslt_InputTooComplex`

## pseudocode

```c

```

## disassembly

```asm
0x28e90  ldarg.0
0x28e91  ldarg.0
0x28e92  ldfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseSubExprDepth
0x28e97  ldc.i4.1
0x28e98  add
0x28e99  stloc.2
0x28e9a  ldloc.2
0x28e9b  stfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseSubExprDepth
0x28ea0  ldloc.2
0x28ea1  ldc.i4   0x400
0x28ea6  ble.s    loc_28EC6
0x28ea8  call     bool [System.Xml]System.Xml.XmlConfiguration.XsltConfigSection::get_LimitXPathComplexity()
0x28ead  brfalse.s loc_28EC6
0x28eaf  ldarg.0
0x28eb0  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28eb5  ldstr    aXsltInputtooco// "Xslt_InputTooComplex"
0x28eba  ldc.i4.0
0x28ebb  newarr   [mscorlib]System.String
0x28ec0  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28ec5  throw
0x28ec6  ldarg.0
0x28ec7  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28ecc  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28ed1  ldc.i4.s 0xA
0x28ed3  bne.un.s loc_28F0B
0x28ed5  ldc.i4.s 0xE
0x28ed7  stloc.0
0x28ed8  ldsfld   int32[] class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::XPathOperatorPrecedence
0x28edd  ldloc.0
0x28ede  ldelem.i4
0x28edf  stloc.3
0x28ee0  ldarg.0
0x28ee1  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28ee6  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28eeb  ldarg.0
0x28eec  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28ef1  ldloc.0
0x28ef2  ldarg.0
0x28ef3  ldloc.3
0x28ef4  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseSubExpr(!!T0)
0x28ef9  ldloca.s 4
0x28efb  initobj  var<u1>
0x28f01  ldloc.s  4
0x28f03  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Operator(!!T0, valuetype System.Xml.Xsl.XPath.XPathOperator, var<u1>)
0x28f08  stloc.1
0x28f09  br.s     loc_28F12
0x28f0b  ldarg.0
0x28f0c  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseUnionExpr()
0x28f11  stloc.1
0x28f12  ldarg.0
0x28f13  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28f18  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28f1d  ldc.i4.s 0xF
0x28f1f  ble.s    loc_28F24
0x28f21  ldc.i4.0
0x28f22  br.s     loc_28F2F
0x28f24  ldarg.0
0x28f25  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28f2a  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28f2f  stloc.0
0x28f30  ldsfld   int32[] class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::XPathOperatorPrecedence
0x28f35  ldloc.0
0x28f36  ldelem.i4
0x28f37  stloc.s  5
0x28f39  ldloc.s  5
0x28f3b  ldarg.1
0x28f3c  ble.s    loc_28F61
0x28f3e  ldarg.0
0x28f3f  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28f44  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28f49  ldarg.0
0x28f4a  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28f4f  ldloc.0
0x28f50  ldloc.1
0x28f51  ldarg.0
0x28f52  ldloc.s  5
0x28f54  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseSubExpr(!!T0)
0x28f59  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Operator(!!T0, valuetype System.Xml.Xsl.XPath.XPathOperator, var<u1>)
0x28f5e  stloc.1
0x28f5f  br.s     loc_28F12
0x28f61  ldarg.0
0x28f62  ldarg.0
0x28f63  ldfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseSubExprDepth
0x28f68  ldc.i4.1
0x28f69  sub
0x28f6a  stfld    int32 class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::parseSubExprDepth
0x28f6f  ldloc.1
0x28f70  ret
```
