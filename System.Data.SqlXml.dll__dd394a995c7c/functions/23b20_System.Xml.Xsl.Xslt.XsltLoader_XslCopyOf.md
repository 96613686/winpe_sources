# System.Xml.Xsl.Xslt.XsltLoader::XslCopyOf

- ea: `0x23b20`
- end: `0x23b8b`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslCopyOf`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x23380`

## callees

- `0x1e180`
- `0x206f0`
- `0x20800`
- `0x23b20`
- `0x25170`
- `0x25200`
- `0x25270`
- `0x252a0`
- `0x25410`
- `0x254e0`
- `0x255c0`

## string_xrefs

- `0x23b41`: `copy-namespaces`
- `0x23b53`: `xsl:copy-of[@copy-namespaces    = 'no']`

## pseudocode

```c

```

## disassembly

```asm
0x23b20  ldarg.0
0x23b21  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23b26  ldarg.0
0x23b27  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::copyOfAttributes
0x23b2c  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x23b31  stloc.0
0x23b32  ldarg.0
0x23b33  ldc.i4.0
0x23b34  ldstr    aSelect// "select"
0x23b39  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x23b3e  stloc.1
0x23b3f  ldarg.0
0x23b40  ldc.i4.1
0x23b41  ldstr    aCopyNamespaces// "copy-namespaces"
0x23b46  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x23b4b  ldc.i4.0
0x23b4c  cgt.un
0x23b4e  stloc.2
0x23b4f  ldloc.2
0x23b50  brtrue.s loc_23B5D
0x23b52  ldarg.0
0x23b53  ldstr    aXslCopyOfCopyN// "xsl:copy-of[@copy-namespaces    = 'no']"
0x23b58  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x23b5d  ldarg.0
0x23b5e  ldc.i4.2
0x23b5f  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseTypeAttribute(int32 attNum)
0x23b64  ldarg.0
0x23b65  ldc.i4.3
0x23b66  ldc.i4.0
0x23b67  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseValidationAttribute(int32 attNum, bool defVal)
0x23b6c  ldarg.0
0x23b6d  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckNoContent()
0x23b72  ldloc.1
0x23b73  ldarg.0
0x23b74  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23b79  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x23b7e  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::CopyOf(string select, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x23b83  ldnull
0x23b84  ldloc.0
0x23b85  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x23b8a  ret
```
