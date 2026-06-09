# System.Xml.Xsl.Xslt.XsltLoader::LoadFallbacks

- ea: `0x24a10`
- end: `0x24ab9`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadFallbacks`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x24780`
- `0x24990`

## callees

- `0x3bf0`
- `0x1e1a0`
- `0x1e1e0`
- `0x20190`
- `0x201b0`
- `0x201e0`
- `0x20540`
- `0x20680`
- `0x207f0`
- `0x20ff0`
- `0x23350`
- `0x24a10`
- `0x254e0`

## string_xrefs

- `0x24a99`: `Xslt_UnknownExtensionElement`

## pseudocode

```c

```

## disassembly

```asm
0x24a10  ldarg.0
0x24a11  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a16  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::MoveToElement()
0x24a1b  ldarg.0
0x24a1c  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a21  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XsltInput::BuildNameLineInfo()
0x24a26  stloc.0
0x24a27  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::.ctor()
0x24a2c  stloc.1
0x24a2d  ldarg.0
0x24a2e  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a33  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToFirstChild()
0x24a38  brfalse.s loc_24A8F
0x24a3a  ldarg.0
0x24a3b  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a40  ldarg.0
0x24a41  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x24a46  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Fallback
0x24a4b  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltKeyword(string kwd)
0x24a50  brfalse.s loc_24A77
0x24a52  ldarg.0
0x24a53  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a58  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes()
0x24a5d  stloc.2
0x24a5e  ldloc.1
0x24a5f  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::List()
0x24a64  ldarg.0
0x24a65  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions()
0x24a6a  ldloc.2
0x24a6b  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x24a70  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::Add(var<u1>)
0x24a75  br.s     loc_24A82
0x24a77  ldarg.0
0x24a78  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a7d  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x24a82  ldarg.0
0x24a83  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24a88  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToNextSibling()
0x24a8d  brtrue.s loc_24A3A
0x24a8f  ldloc.1
0x24a90  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x24a95  brtrue.s loc_24AB7
0x24a97  ldloc.1
0x24a98  ldloc.0
0x24a99  ldstr    aXsltUnknownext// "Xslt_UnknownExtensionElement"
0x24a9e  ldc.i4.1
0x24a9f  newarr   [mscorlib]System.String
0x24aa4  dup
0x24aa5  ldc.i4.0
0x24aa6  ldarg.1
0x24aa7  stelem.ref
0x24aa8  call     string System.Xml.Xsl.XslLoadException::CreateMessage(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x24aad  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::Error(string message)
0x24ab2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::Add(var<u1>)
0x24ab7  ldloc.1
0x24ab8  ret
```
