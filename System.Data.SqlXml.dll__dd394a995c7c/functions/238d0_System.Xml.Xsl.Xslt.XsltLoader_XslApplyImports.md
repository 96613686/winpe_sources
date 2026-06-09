# System.Xml.Xsl.Xslt.XsltLoader::XslApplyImports

- ea: `0x238d0`
- end: `0x239da`
- name: `System.Xml.Xsl.Xslt.XsltLoader::XslApplyImports`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x23380`

## callees

- `0x3bf0`
- `0x13be0`
- `0x1e0f0`
- `0x1e1a0`
- `0x201e0`
- `0x206a0`
- `0x206d0`
- `0x206f0`
- `0x207f0`
- `0x214e0`
- `0x237a0`
- `0x238d0`
- `0x254e0`
- `0x25580`
- `0x255c0`
- `0x56cc0`

## string_xrefs

- `0x2394c`: `Xslt_NotEmptyContents`
- `0x2396d`: `Xslt_NotEmptyContents`

## pseudocode

```c

```

## disassembly

```asm
0x238d0  ldarg.0
0x238d1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x238d6  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes()
0x238db  stloc.0
0x238dc  ldarg.0
0x238dd  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x238e2  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_CanHaveApplyImports()
0x238e7  brtrue.s loc_23907
0x238e9  ldarg.0
0x238ea  ldstr    aXsltInvalidapp// "Xslt_InvalidApplyImports"
0x238ef  ldc.i4.0
0x238f0  newarr   [mscorlib]System.String
0x238f5  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x238fa  ldarg.0
0x238fb  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23900  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x23905  ldnull
0x23906  ret
0x23907  ldarg.0
0x23908  ldc.i4.0
0x23909  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadWithParams(valuetype InstructionFlags flags)
0x2390e  stloc.1
0x2390f  ldloc.0
0x23910  ldarg.0
0x23911  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x23916  callvirt instance void ContextInfo::SaveExtendedLineInfo(class System.Xml.Xsl.Xslt.XsltInput input)
0x2391b  ldarg.0
0x2391c  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x23921  brfalse.s loc_2399C
0x23923  ldloc.1
0x23924  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x23929  brfalse.s loc_23998
0x2392b  ldloc.1
0x2392c  ldc.i4.0
0x2392d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x23932  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x23937  stloc.2
0x23938  ldarg.0
0x23939  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2393e  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x23943  brtrue.s loc_2396C
0x23945  ldarg.0
0x23946  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x2394b  ldloc.2
0x2394c  ldstr    aXsltNotemptyco// "Xslt_NotEmptyContents"
0x23951  ldc.i4.1
0x23952  newarr   [mscorlib]System.String
0x23957  dup
0x23958  ldc.i4.0
0x23959  ldarg.0
0x2395a  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2395f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyImports
0x23964  stelem.ref
0x23965  callvirt instance void System.Xml.Xsl.Xslt.Compiler::ReportError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x2396a  br.s     loc_23998
0x2396c  ldloc.2
0x2396d  ldstr    aXsltNotemptyco// "Xslt_NotEmptyContents"
0x23972  ldc.i4.1
0x23973  newarr   [mscorlib]System.String
0x23978  dup
0x23979  ldc.i4.0
0x2397a  ldarg.0
0x2397b  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x23980  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyImports
0x23985  stelem.ref
0x23986  call     string System.Xml.Xsl.XslLoadException::CreateMessage(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x2398b  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::Error(string message)
0x23990  ldnull
0x23991  ldloc.0
0x23992  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x23997  ret
0x23998  ldnull
0x23999  stloc.1
0x2399a  br.s     loc_239B1
0x2399c  ldloc.1
0x2399d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x239a2  brfalse.s loc_239AF
0x239a4  ldarg.0
0x239a5  ldstr    aXslApplyImport_0// "xsl:apply-imports/xsl:with-param"
0x239aa  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x239af  ldnull
0x239b0  stloc.1
0x239b1  ldarg.0
0x239b2  ldfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x239b7  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.Template::Mode
0x239bc  ldarg.0
0x239bd  ldfld    class System.Xml.Xsl.Xslt.Stylesheet System.Xml.Xsl.Xslt.XsltLoader::curStylesheet
0x239c2  ldarg.0
0x239c3  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x239c8  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x239cd  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::ApplyImports(class System.Xml.Xsl.Qil.QilName mode, class System.Xml.Xsl.Xslt.Stylesheet sheet, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x239d2  ldloc.1
0x239d3  ldloc.0
0x239d4  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x239d9  ret
```
