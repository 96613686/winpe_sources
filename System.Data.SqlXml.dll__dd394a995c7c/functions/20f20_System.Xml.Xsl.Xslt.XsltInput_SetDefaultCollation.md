# System.Xml.Xsl.Xslt.XsltInput::SetDefaultCollation

- ea: `0x20f20`
- end: `0x20f87`
- name: `System.Xml.Xsl.Xslt.XsltInput::SetDefaultCollation`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x20800`
- `0x20bc0`

## callees

- `0x1f920`
- `0x20570`
- `0x20f20`
- `0x21120`
- `0x21160`
- `0x2da30`

## string_xrefs

- `0x20f69`: `http://www.w3.org/2004/10/xpath-functions/collation/codepoint`

## pseudocode

```c

```

## disassembly

```asm
0x20f20  ldarg.0
0x20f21  ldarg.1
0x20f22  call     instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToLiteralAttribute(int32 attNum)
0x20f27  brfalse.s loc_20F86
0x20f29  ldarg.0
0x20f2a  call     instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x20f2f  call     string[] [System.Xml]System.Xml.XmlConvert::SplitString(string)
0x20f34  stloc.0
0x20f35  ldc.i4.0
0x20f36  stloc.1
0x20f37  br.s     loc_20F48
0x20f39  ldloc.0
0x20f3a  ldloc.1
0x20f3b  ldelem.ref
0x20f3c  ldc.i4.0
0x20f3d  call     class System.Xml.Xsl.Runtime.XmlCollation System.Xml.Xsl.Runtime.XmlCollation::Create(string collationLiteral, bool throwOnError)
0x20f42  brtrue.s loc_20F4E
0x20f44  ldloc.1
0x20f45  ldc.i4.1
0x20f46  add
0x20f47  stloc.1
0x20f48  ldloc.1
0x20f49  ldloc.0
0x20f4a  ldlen
0x20f4b  conv.i4
0x20f4c  blt.s    loc_20F39
0x20f4e  ldloc.1
0x20f4f  ldloc.0
0x20f50  ldlen
0x20f51  conv.i4
0x20f52  bne.un.s loc_20F66
0x20f54  ldarg.0
0x20f55  ldstr    aXsltCollations// "Xslt_CollationSyntax"
0x20f5a  ldc.i4.0
0x20f5b  newarr   [mscorlib]System.String
0x20f60  call     instance void System.Xml.Xsl.Xslt.XsltInput::ReportErrorFC(string res, string[] args)
0x20f65  ret
0x20f66  ldloc.0
0x20f67  ldloc.1
0x20f68  ldelem.ref
0x20f69  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2004/10/xpath-functio"...
0x20f6e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20f73  brfalse.s loc_20F86
0x20f75  ldarg.0
0x20f76  ldarg.0
0x20f77  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20f7c  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::DefaultCollation
0x20f81  call     instance void System.Xml.Xsl.Xslt.XsltInput::ReportNYI(string arg)
0x20f86  ret
```
