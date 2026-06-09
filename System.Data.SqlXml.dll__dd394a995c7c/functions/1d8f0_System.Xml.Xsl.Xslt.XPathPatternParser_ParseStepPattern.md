# System.Xml.Xsl.Xslt.XPathPatternParser::ParseStepPattern

- ea: `0x1d8f0`
- end: `0x1da5a`
- name: `System.Xml.Xsl.Xslt.XPathPatternParser::ParseStepPattern`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1d820`

## callees

- `0x1d0b0`
- `0x1d8f0`
- `0x1da60`
- `0x29ea0`
- `0x29f60`
- `0x29fc0`
- `0x2a000`
- `0x2a890`

## string_xrefs

- `0x1d937`: `XPath_InvalidAxisInPattern`
- `0x1d971`: `XPath_InvalidAxisInPattern`
- `0x1d9a4`: `XPath_UnexpectedToken`

## pseudocode

```c

```

## disassembly

```asm
0x1d8f0  ldarg.0
0x1d8f1  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d8f6  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x1d8fb  stloc.s  6
0x1d8fd  ldloc.s  6
0x1d8ff  ldc.i4.s 0x15
0x1d901  bgt.s    loc_1D91D
0x1d903  ldloc.s  6
0x1d905  ldc.i4.s 0x10
0x1d907  beq.s    loc_1D931
0x1d909  ldloc.s  6
0x1d90b  ldc.i4.s 0x14
0x1d90d  beq.s    loc_1D957
0x1d90f  ldloc.s  6
0x1d911  ldc.i4.s 0x15
0x1d913  beq      loc_1D99A
0x1d918  br       loc_1D99E
0x1d91d  ldloc.s  6
0x1d91f  ldc.i4.s 0x2A
0x1d921  beq.s    loc_1D99A
0x1d923  ldloc.s  6
0x1d925  ldc.i4.s 0x2E
0x1d927  beq.s    loc_1D931
0x1d929  ldloc.s  6
0x1d92b  ldc.i4.s 0x40
0x1d92d  beq.s    loc_1D948
0x1d92f  br.s     loc_1D99E
0x1d931  ldarg.0
0x1d932  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d937  ldstr    aXpathInvalidax// "XPath_InvalidAxisInPattern"
0x1d93c  ldc.i4.0
0x1d93d  newarr   [mscorlib]System.String
0x1d942  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x1d947  throw
0x1d948  ldc.i4.3
0x1d949  stloc.1
0x1d94a  ldarg.0
0x1d94b  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d950  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x1d955  br.s     loc_1D9C3
0x1d957  ldarg.0
0x1d958  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d95d  callvirt instance valuetype System.Xml.Xsl.XPath.XPathAxis System.Xml.Xsl.XPath.XPathScanner::get_Axis()
0x1d962  stloc.1
0x1d963  ldloc.1
0x1d964  ldc.i4.4
0x1d965  beq.s    loc_1D982
0x1d967  ldloc.1
0x1d968  ldc.i4.3
0x1d969  beq.s    loc_1D982
0x1d96b  ldarg.0
0x1d96c  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d971  ldstr    aXpathInvalidax// "XPath_InvalidAxisInPattern"
0x1d976  ldc.i4.0
0x1d977  newarr   [mscorlib]System.String
0x1d97c  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x1d981  throw
0x1d982  ldarg.0
0x1d983  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d988  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x1d98d  ldarg.0
0x1d98e  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d993  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x1d998  br.s     loc_1D9C3
0x1d99a  ldc.i4.4
0x1d99b  stloc.1
0x1d99c  br.s     loc_1D9C3
0x1d99e  ldarg.0
0x1d99f  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d9a4  ldstr    aXpathUnexpecte// "XPath_UnexpectedToken"
0x1d9a9  ldc.i4.1
0x1d9aa  newarr   [mscorlib]System.String
0x1d9af  dup
0x1d9b0  ldc.i4.0
0x1d9b1  ldarg.0
0x1d9b2  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d9b7  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_RawValue()
0x1d9bc  stelem.ref
0x1d9bd  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x1d9c2  throw
0x1d9c3  ldarg.0
0x1d9c4  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d9c9  ldloc.1
0x1d9ca  ldloca.s 2
0x1d9cc  ldloca.s 3
0x1d9ce  ldloca.s 4
0x1d9d0  call     void class System.Xml.Xsl.XPath.XPathParser`1<class System.Xml.Xsl.Qil.QilNode>::InternalParseNodeTest(class System.Xml.Xsl.XPath.XPathScanner, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType&, string&, string&)
0x1d9d5  ldarg.0
0x1d9d6  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d9db  ldloc.1
0x1d9dc  ldloc.2
0x1d9dd  ldloc.3
0x1d9de  ldloc.s  4
0x1d9e0  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::Axis(!!T0, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, string)
0x1d9e5  stloc.0
0x1d9e6  ldarg.0
0x1d9e7  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d9ec  isinst   System.Xml.Xsl.Xslt.XPathPatternBuilder
0x1d9f1  stloc.s  5
0x1d9f3  ldloc.s  5
0x1d9f5  brfalse.s loc_1DA49
0x1d9f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::.ctor()
0x1d9fc  stloc.s  7
0x1d9fe  br.s     loc_1DA0E
0x1da00  ldloc.s  7
0x1da02  ldarg.0
0x1da03  ldloc.0
0x1da04  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternParser::ParsePredicate(class System.Xml.Xsl.Qil.QilNode context)
0x1da09  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::Add(var<u1>)
0x1da0e  ldarg.0
0x1da0f  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1da14  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x1da19  ldc.i4.s 0x5B
0x1da1b  beq.s    loc_1DA00
0x1da1d  ldloc.s  7
0x1da1f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1da24  ldc.i4.0
0x1da25  ble.s    loc_1DA58
0x1da27  ldloc.s  5
0x1da29  ldloc.0
0x1da2a  ldloc.s  7
0x1da2c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternBuilder::BuildPredicates(class System.Xml.Xsl.Qil.QilNode nodeset, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode> predicates)
0x1da31  stloc.0
0x1da32  br.s     loc_1DA58
0x1da34  ldarg.0
0x1da35  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1da3a  ldloc.0
0x1da3b  ldarg.0
0x1da3c  ldloc.0
0x1da3d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternParser::ParsePredicate(class System.Xml.Xsl.Qil.QilNode context)
0x1da42  ldc.i4.0
0x1da43  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::Predicate(!!T0, var<u1>, !!T0)
0x1da48  stloc.0
0x1da49  ldarg.0
0x1da4a  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1da4f  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x1da54  ldc.i4.s 0x5B
0x1da56  beq.s    loc_1DA34
0x1da58  ldloc.0
0x1da59  ret
```
