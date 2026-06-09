# System.Xml.Xsl.Xslt.XsltLoader::LoadTemplate

- ea: `0x22ce0`
- end: `0x22ed1`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadTemplate`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x21890`

## callees

- `0x34f0`
- `0x1cc60`
- `0x1e280`
- `0x1f920`
- `0x20590`
- `0x205e0`
- `0x206b0`
- `0x206d0`
- `0x206f0`
- `0x20800`
- `0x214e0`
- `0x22ce0`
- `0x23360`
- `0x24950`
- `0x24ac0`
- `0x24b90`
- `0x24e00`
- `0x25170`
- `0x254e0`
- `0x25510`
- `0x25580`
- `0x255a0`
- `0x255c0`
- `0x255f0`
- `0x37510`

## string_xrefs

- `0x22ea6`: `Xslt_DupTemplateName`
- `0x22e44`: `xsl:template/@as`

## pseudocode

```c

```

## disassembly

```asm
0x22ce0  ldarg.0
0x22ce1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22ce6  ldarg.0
0x22ce7  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::templateAttributes
0x22cec  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x22cf1  stloc.0
0x22cf2  ldloc.0
0x22cf3  ldloc.0
0x22cf4  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x22cf9  ldarg.1
0x22cfa  call     class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XsltLoader::MergeNamespaces(class System.Xml.Xsl.Xslt.NsDecl thisList, class System.Xml.Xsl.Xslt.NsDecl parentList)
0x22cff  stfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x22d04  ldarg.0
0x22d05  ldc.i4.0
0x22d06  ldstr    aMatch// "match"
0x22d0b  call     instance string System.Xml.Xsl.Xslt.XsltLoader::ParseStringAttribute(int32 attNum, string attName)
0x22d10  stloc.1
0x22d11  ldarg.0
0x22d12  ldc.i4.1
0x22d13  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::ParseQNameAttribute(int32 attNum)
0x22d18  stloc.2
0x22d19  ldc.r8   NaN
0x22d22  stloc.3
0x22d23  ldarg.0
0x22d24  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22d29  ldc.i4.2
0x22d2a  ldstr    aPriority// "priority"
0x22d2f  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x22d34  brfalse.s loc_22D83
0x22d36  ldarg.0
0x22d37  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22d3c  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22d41  call     float64 System.Xml.Xsl.XPathConvert::StringToDouble(string s)
0x22d46  stloc.3
0x22d47  ldloc.3
0x22d48  call     bool [mscorlib]System.Double::IsNaN(float64)
0x22d4d  brfalse.s loc_22D83
0x22d4f  ldarg.0
0x22d50  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22d55  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x22d5a  brtrue.s loc_22D83
0x22d5c  ldarg.0
0x22d5d  ldstr    aXsltInvalidatt_0// "Xslt_InvalidAttrValue"
0x22d62  ldc.i4.2
0x22d63  newarr   [mscorlib]System.String
0x22d68  dup
0x22d69  ldc.i4.0
0x22d6a  ldstr    aPriority// "priority"
0x22d6f  stelem.ref
0x22d70  dup
0x22d71  ldc.i4.1
0x22d72  ldarg.0
0x22d73  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22d78  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22d7d  stelem.ref
0x22d7e  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x22d83  ldarg.0
0x22d84  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x22d89  brtrue.s loc_22D94
0x22d8b  ldarg.0
0x22d8c  ldc.i4.3
0x22d8d  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::ParseModeListAttribute(int32 attNum)
0x22d92  br.s     loc_22D9B
0x22d94  ldarg.0
0x22d95  ldc.i4.3
0x22d96  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::ParseModeAttribute(int32 attNum)
0x22d9b  stloc.s  4
0x22d9d  ldloc.1
0x22d9e  brtrue   loc_22E30
0x22da3  ldarg.0
0x22da4  ldarg.0
0x22da5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22daa  ldc.i4.1
0x22dab  ldstr    aName// "name"
0x22db0  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::AttributeExists(int32 attNum, string attName)
0x22db5  ldc.i4.0
0x22db6  ceq
0x22db8  ldstr    aXsltBothmatchn// "Xslt_BothMatchNameAbsent"
0x22dbd  ldc.i4.0
0x22dbe  newarr   [mscorlib]System.String
0x22dc3  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x22dc8  ldarg.0
0x22dc9  ldarg.0
0x22dca  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22dcf  ldc.i4.3
0x22dd0  ldstr    aMode// "mode"
0x22dd5  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::AttributeExists(int32 attNum, string attName)
0x22dda  ldstr    aXsltModewithou// "Xslt_ModeWithoutMatch"
0x22ddf  ldc.i4.0
0x22de0  newarr   [mscorlib]System.String
0x22de5  call     instance void System.Xml.Xsl.Xslt.XsltLoader::CheckError(bool cond, string res, string[] args)
0x22dea  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x22def  stloc.s  4
0x22df1  ldarg.0
0x22df2  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22df7  ldc.i4.2
0x22df8  ldstr    aPriority// "priority"
0x22dfd  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::AttributeExists(int32 attNum, string attName)
0x22e02  brfalse.s loc_22E30
0x22e04  ldarg.0
0x22e05  call     instance bool System.Xml.Xsl.Xslt.XsltLoader::get_V1()
0x22e0a  brfalse.s loc_22E1F
0x22e0c  ldarg.0
0x22e0d  ldstr    aXsltPrioritywi// "Xslt_PriorityWithoutMatch"
0x22e12  ldc.i4.0
0x22e13  newarr   [mscorlib]System.String
0x22e18  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x22e1d  br.s     loc_22E30
0x22e1f  ldarg.0
0x22e20  ldstr    aXsltPrioritywi// "Xslt_PriorityWithoutMatch"
0x22e25  ldc.i4.0
0x22e26  newarr   [mscorlib]System.String
0x22e2b  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x22e30  ldarg.0
0x22e31  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22e36  ldc.i4.4
0x22e37  ldstr    aAs// "as"
0x22e3c  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x22e41  brfalse.s loc_22E4E
0x22e43  ldarg.0
0x22e44  ldstr    aXslTemplateAs// "xsl:template/@as"
0x22e49  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x22e4e  ldarg.0
0x22e4f  ldloc.2
0x22e50  ldloc.1
0x22e51  ldloc.s  4
0x22e53  ldloc.3
0x22e54  ldarg.0
0x22e55  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22e5a  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x22e5f  call     class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.AstFactory::Template(class System.Xml.Xsl.Qil.QilName name, string match, class System.Xml.Xsl.Qil.QilName mode, float64 priority, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x22e64  stfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x22e69  ldarg.0
0x22e6a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22e6f  ldloc.1
0x22e70  ldnull
0x22e71  cgt.un
0x22e73  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::set_CanHaveApplyImports(bool value)
0x22e78  ldarg.0
0x22e79  ldfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x22e7e  ldarg.0
0x22e7f  ldarg.0
0x22e80  ldc.i4.1
0x22e81  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions(valuetype InstructionFlags flags)
0x22e86  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadEndTag(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x22e8b  ldloc.0
0x22e8c  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x22e91  pop
0x22e92  ldarg.0
0x22e93  ldfld    class System.Xml.Xsl.Xslt.Stylesheet System.Xml.Xsl.Xslt.XsltLoader::curStylesheet
0x22e98  ldarg.0
0x22e99  ldfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x22e9e  callvirt instance bool System.Xml.Xsl.Xslt.Stylesheet::AddTemplate(class System.Xml.Xsl.Xslt.Template template)
0x22ea3  brtrue.s loc_22EC9
0x22ea5  ldarg.0
0x22ea6  ldstr    aXsltDuptemplat// "Xslt_DupTemplateName"
0x22eab  ldc.i4.1
0x22eac  newarr   [mscorlib]System.String
0x22eb1  dup
0x22eb2  ldc.i4.0
0x22eb3  ldarg.0
0x22eb4  ldfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x22eb9  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x22ebe  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x22ec3  stelem.ref
0x22ec4  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x22ec9  ldarg.0
0x22eca  ldnull
0x22ecb  stfld    class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.XsltLoader::curTemplate
0x22ed0  ret
```
