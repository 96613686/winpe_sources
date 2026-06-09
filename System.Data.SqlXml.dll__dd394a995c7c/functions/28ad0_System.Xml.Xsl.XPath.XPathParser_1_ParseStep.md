# System.Xml.Xsl.XPath.XPathParser`1::ParseStep

- ea: `0x28ad0`
- end: `0x28c33`
- name: `System.Xml.Xsl.XPath.XPathParser`1::ParseStep`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x28ad0`
- `0x29ea0`
- `0x29f60`
- `0x29fc0`
- `0x2a000`
- `0x2a890`

## string_xrefs

- `0x28be0`: `XPath_UnexpectedToken`
- `0x28b14`: `XPath_PredicateAfterDot`
- `0x28b69`: `XPath_PredicateAfterDotDot`

## pseudocode

```c

```

## disassembly

```asm
0x28ad0  ldc.i4.s 0x2E
0x28ad2  ldarg.0
0x28ad3  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28ad8  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28add  bne.un.s loc_28B25
0x28adf  ldarg.0
0x28ae0  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28ae5  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28aea  ldarg.0
0x28aeb  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28af0  ldc.i4.s 0xD
0x28af2  ldc.i4.s 9
0x28af4  ldnull
0x28af5  ldnull
0x28af6  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Axis(!!T0, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, string)
0x28afb  stloc.0
0x28afc  ldc.i4.s 0x5B
0x28afe  ldarg.0
0x28aff  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b04  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28b09  bne.un   loc_28C31
0x28b0e  ldarg.0
0x28b0f  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b14  ldstr    aXpathPredicate// "XPath_PredicateAfterDot"
0x28b19  ldc.i4.0
0x28b1a  newarr   [mscorlib]System.String
0x28b1f  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28b24  throw
0x28b25  ldc.i4.s 0x10
0x28b27  ldarg.0
0x28b28  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b2d  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28b32  bne.un.s loc_28B7A
0x28b34  ldarg.0
0x28b35  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b3a  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28b3f  ldarg.0
0x28b40  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28b45  ldc.i4.s 0xA
0x28b47  ldc.i4.s 9
0x28b49  ldnull
0x28b4a  ldnull
0x28b4b  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Axis(!!T0, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, string)
0x28b50  stloc.0
0x28b51  ldc.i4.s 0x5B
0x28b53  ldarg.0
0x28b54  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b59  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28b5e  bne.un   loc_28C31
0x28b63  ldarg.0
0x28b64  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b69  ldstr    aXpathPredicate_0// "XPath_PredicateAfterDotDot"
0x28b6e  ldc.i4.0
0x28b6f  newarr   [mscorlib]System.String
0x28b74  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28b79  throw
0x28b7a  ldarg.0
0x28b7b  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28b80  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28b85  stloc.2
0x28b86  ldloc.2
0x28b87  ldc.i4.s 0x15
0x28b89  bgt.s    loc_28B97
0x28b8b  ldloc.2
0x28b8c  ldc.i4.s 0x14
0x28b8e  beq.s    loc_28BA3
0x28b90  ldloc.2
0x28b91  ldc.i4.s 0x15
0x28b93  beq.s    loc_28BD6
0x28b95  br.s     loc_28BDA
0x28b97  ldloc.2
0x28b98  ldc.i4.s 0x2A
0x28b9a  beq.s    loc_28BD6
0x28b9c  ldloc.2
0x28b9d  ldc.i4.s 0x40
0x28b9f  beq.s    loc_28BC7
0x28ba1  br.s     loc_28BDA
0x28ba3  ldarg.0
0x28ba4  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28ba9  callvirt instance valuetype System.Xml.Xsl.XPath.XPathAxis System.Xml.Xsl.XPath.XPathScanner::get_Axis()
0x28bae  stloc.1
0x28baf  ldarg.0
0x28bb0  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28bb5  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28bba  ldarg.0
0x28bbb  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28bc0  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28bc5  br.s     loc_28BFF
0x28bc7  ldc.i4.3
0x28bc8  stloc.1
0x28bc9  ldarg.0
0x28bca  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28bcf  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x28bd4  br.s     loc_28BFF
0x28bd6  ldc.i4.4
0x28bd7  stloc.1
0x28bd8  br.s     loc_28BFF
0x28bda  ldarg.0
0x28bdb  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28be0  ldstr    aXpathUnexpecte// "XPath_UnexpectedToken"
0x28be5  ldc.i4.1
0x28be6  newarr   [mscorlib]System.String
0x28beb  dup
0x28bec  ldc.i4.0
0x28bed  ldarg.0
0x28bee  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28bf3  callvirt instance string System.Xml.Xsl.XPath.XPathScanner::get_RawValue()
0x28bf8  stelem.ref
0x28bf9  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x28bfe  throw
0x28bff  ldarg.0
0x28c00  ldloc.1
0x28c01  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParseNodeTest(!!T0)
0x28c06  stloc.0
0x28c07  br.s     loc_28C22
0x28c09  ldarg.0
0x28c0a  ldfld    class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::builder
0x28c0f  ldloc.0
0x28c10  ldarg.0
0x28c11  call     instance var<u1> class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::ParsePredicate()
0x28c16  ldloc.1
0x28c17  call     bool class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::IsReverseAxis(valuetype System.Xml.Xsl.XPath.XPathAxis)
0x28c1c  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<var<u1>>::Predicate(!!T0, var<u1>, !!T0)
0x28c21  stloc.0
0x28c22  ldc.i4.s 0x5B
0x28c24  ldarg.0
0x28c25  ldfld    class System.Xml.Xsl.XPath.XPathScanner class System.Xml.Xsl.XPath.XPathParser`1<var<u1>>::scanner
0x28c2a  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x28c2f  beq.s    loc_28C09
0x28c31  ldloc.0
0x28c32  ret
```
