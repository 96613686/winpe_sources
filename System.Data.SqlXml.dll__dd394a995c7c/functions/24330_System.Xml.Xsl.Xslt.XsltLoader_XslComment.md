# System.Xml.Xsl.Xslt.XsltLoader::XslComment

- ea: `0x24330`
- end: `0x24373`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslComment`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x23380`

## callees

- `0x1e160`
- `0x20800`
- `0x24330`
- `0x24380`
- `0x25170`
- `0x254e0`
- `0x255c0`

## string_xrefs

- `0x24353`: `xsl:comment/@select`

## pseudocode

```c

```

## disassembly

```asm
0x24330  ldarg.0
0x24331  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24336  ldarg.0
0x24337  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::commentAttributes
0x2433c  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x24341  stloc.0
0x24342  ldarg.0
0x24343  ldc.i4.0
0x24344  ldstr    aSelect// "select"
0x24349  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x2434e  stloc.1
0x2434f  ldloc.1
0x24350  brfalse.s loc_2435D
0x24352  ldarg.0
0x24353  ldstr    aXslCommentSele// "xsl:comment/@select"
0x24358  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x2435d  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::Comment()
0x24362  ldarg.0
0x24363  ldloc.1
0x24364  ldnull
0x24365  cgt.un
0x24367  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadContent(bool hasSelect)
0x2436c  ldloc.0
0x2436d  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x24372  ret
```
