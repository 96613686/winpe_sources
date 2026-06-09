# System.Xml.Xsl.Xslt.QilGenerator::CompileNodeSetExpression

- ea: `0x19d90`
- end: `0x19de9`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileNodeSetExpression`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17d50`
- `0x17df0`

## callees

- `0x19c90`
- `0x19d10`
- `0x19d90`
- `0x286c0`
- `0x29b00`
- `0x37a20`
- `0x37c20`

## string_xrefs

- `0x19dae`: `XPath_NodeSetExpected`

## pseudocode

```c

```

## disassembly

```asm
0x19d90  ldarg.0
0x19d91  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19d96  ldarg.0
0x19d97  ldarg.1
0x19d98  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileXPathExpression(string expr)
0x19d9d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::TryEnsureNodeSet(class System.Xml.Xsl.Qil.QilNode n)
0x19da2  stloc.0
0x19da3  ldloc.0
0x19da4  brtrue.s loc_19DE7
0x19da6  ldarg.1
0x19da7  ldc.i4.0
0x19da8  ldarg.1
0x19da9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19dae  ldstr    aXpathNodesetex// "XPath_NodeSetExpected"
0x19db3  ldnull
0x19db4  newobj   instance void System.Xml.Xsl.XPath.XPathCompileException::.ctor(string queryString, int32 startChar, int32 endChar, string resId, string[] args)
0x19db9  stloc.1
0x19dba  ldarg.0
0x19dbb  ldfld    valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.QilGenerator::xslVersion
0x19dc0  ldc.i4.1
0x19dc1  beq.s    loc_19DCA
0x19dc3  ldarg.0
0x19dc4  ldloc.1
0x19dc5  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ReportErrorInXPath(class System.Xml.Xsl.XslLoadException e)
0x19dca  ldarg.0
0x19dcb  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19dd0  ldarg.0
0x19dd1  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19dd6  ldloc.1
0x19dd7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19ddc  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x19de1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Error(class System.Xml.Xsl.Qil.QilNode text)
0x19de6  stloc.0
0x19de7  ldloc.0
0x19de8  ret
```
