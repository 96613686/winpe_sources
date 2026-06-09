# System.Xml.Xsl.Xslt.XPathPatternParser::ParseRelativePathPattern

- ea: `0x1d820`
- end: `0x1d8e4`
- name: `System.Xml.Xsl.Xslt.XPathPatternParser::ParseRelativePathPattern`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d550`
- `0x1d820`

## callees

- `0x1d820`
- `0x1d8f0`
- `0x29ea0`
- `0x2a000`
- `0x2a890`

## string_xrefs

- `0x1d845`: `Xslt_InputTooComplex`

## pseudocode

```c

```

## disassembly

```asm
0x1d820  ldarg.0
0x1d821  ldarg.0
0x1d822  ldfld    int32 System.Xml.Xsl.Xslt.XPathPatternParser::parseRelativePath
0x1d827  ldc.i4.1
0x1d828  add
0x1d829  stloc.1
0x1d82a  ldloc.1
0x1d82b  stfld    int32 System.Xml.Xsl.Xslt.XPathPatternParser::parseRelativePath
0x1d830  ldloc.1
0x1d831  ldc.i4   0x400
0x1d836  ble.s    loc_1D856
0x1d838  call     bool [System.Xml]System.Xml.XmlConfiguration.XsltConfigSection::get_LimitXPathComplexity()
0x1d83d  brfalse.s loc_1D856
0x1d83f  ldarg.0
0x1d840  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d845  ldstr    aXsltInputtooco// "Xslt_InputTooComplex"
0x1d84a  ldc.i4.0
0x1d84b  newarr   [mscorlib]System.String
0x1d850  callvirt instance class System.Xml.Xsl.XPath.XPathCompileException System.Xml.Xsl.XPath.XPathScanner::CreateException(string resId, string[] args)
0x1d855  throw
0x1d856  ldarg.0
0x1d857  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternParser::ParseStepPattern()
0x1d85c  stloc.0
0x1d85d  ldarg.0
0x1d85e  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d863  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x1d868  ldc.i4.s 0x2F
0x1d86a  bne.un.s loc_1D88C
0x1d86c  ldarg.0
0x1d86d  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d872  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x1d877  ldarg.0
0x1d878  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d87d  ldloc.0
0x1d87e  ldarg.0
0x1d87f  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternParser::ParseRelativePathPattern()
0x1d884  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::JoinStep(!!T0, var<u1>)
0x1d889  stloc.0
0x1d88a  br.s     loc_1D8D4
0x1d88c  ldarg.0
0x1d88d  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d892  callvirt instance valuetype System.Xml.Xsl.XPath.LexKind System.Xml.Xsl.XPath.XPathScanner::get_Kind()
0x1d897  ldc.i4.s 0x12
0x1d899  bne.un.s loc_1D8D4
0x1d89b  ldarg.0
0x1d89c  ldfld    class System.Xml.Xsl.XPath.XPathScanner System.Xml.Xsl.Xslt.XPathPatternParser::scanner
0x1d8a1  callvirt instance void System.Xml.Xsl.XPath.XPathScanner::NextLex()
0x1d8a6  ldarg.0
0x1d8a7  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d8ac  ldloc.0
0x1d8ad  ldarg.0
0x1d8ae  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d8b3  ldarg.0
0x1d8b4  ldfld    class IPatternBuilder System.Xml.Xsl.Xslt.XPathPatternParser::ptrnBuilder
0x1d8b9  ldc.i4.6
0x1d8ba  ldc.i4.s 9
0x1d8bc  ldnull
0x1d8bd  ldnull
0x1d8be  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::Axis(!!T0, valuetype System.Xml.Xsl.XPath.XPathAxis, valuetype [System.Xml]System.Xml.XPath.XPathNodeType, string)
0x1d8c3  ldarg.0
0x1d8c4  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XPathPatternParser::ParseRelativePathPattern()
0x1d8c9  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::JoinStep(!!T0, var<u1>)
0x1d8ce  callvirt instance var<u1> class System.Xml.Xsl.XPath.IXPathBuilder`1<class System.Xml.Xsl.Qil.QilNode>::JoinStep(!!T0, var<u1>)
0x1d8d3  stloc.0
0x1d8d4  ldarg.0
0x1d8d5  ldarg.0
0x1d8d6  ldfld    int32 System.Xml.Xsl.Xslt.XPathPatternParser::parseRelativePath
0x1d8db  ldc.i4.1
0x1d8dc  sub
0x1d8dd  stfld    int32 System.Xml.Xsl.Xslt.XPathPatternParser::parseRelativePath
0x1d8e2  ldloc.0
0x1d8e3  ret
```
