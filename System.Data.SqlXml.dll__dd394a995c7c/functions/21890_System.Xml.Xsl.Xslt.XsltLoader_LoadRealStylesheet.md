# System.Xml.Xsl.Xslt.XsltLoader::LoadRealStylesheet

- ea: `0x21890`
- end: `0x21c0f`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadRealStylesheet`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config`

## callers

- `0x21760`

## callees

- `0x1f8a0`
- `0x1f8c0`
- `0x1f960`
- `0x20190`
- `0x201b0`
- `0x201e0`
- `0x205f0`
- `0x20610`
- `0x20620`
- `0x20630`
- `0x20650`
- `0x206d0`
- `0x20800`
- `0x20d80`
- `0x21890`
- `0x21c10`
- `0x21ca0`
- `0x21d30`
- `0x21d90`
- `0x21df0`
- `0x22530`
- `0x22670`
- `0x229b0`
- `0x22b10`
- `0x22c90`
- `0x22ce0`
- `0x22ee0`
- `0x252a0`
- `0x25350`
- `0x25580`
- `0x56c00`

## pseudocode

```c

```

## disassembly

```asm
0x21890  ldarg.0
0x21891  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21896  ldarg.0
0x21897  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::stylesheetAttributes
0x2189c  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x218a1  stloc.0
0x218a2  ldarg.0
0x218a3  ldc.i4.2
0x218a4  ldc.i4.1
0x218a5  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseValidationAttribute(int32 attNum, bool defVal)
0x218aa  ldarg.0
0x218ab  ldc.i4.3
0x218ac  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ParseInputTypeAnnotationsAttribute(int32 attNum)
0x218b1  ldarg.0
0x218b2  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x218b7  callvirt instance valuetype DelayedQName System.Xml.Xsl.Xslt.XsltInput::get_ElementName()
0x218bc  stloc.1
0x218bd  ldarg.0
0x218be  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x218c3  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToFirstChild()
0x218c8  brfalse  loc_21C0E
0x218cd  ldc.i4.1
0x218ce  stloc.2
0x218cf  ldc.i4.0
0x218d0  stloc.3
0x218d1  ldarg.0
0x218d2  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x218d7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType System.Xml.Xsl.Xslt.XsltInput::get_NodeType()
0x218dc  stloc.s  4
0x218de  ldloc.s  4
0x218e0  ldc.i4.1
0x218e1  beq.s    loc_218F3
0x218e3  ldloc.s  4
0x218e5  ldc.i4.s 0xD
0x218e7  sub
0x218e8  ldc.i4.1
0x218e9  ble.un   loc_21BFE
0x218ee  br       loc_21BE4
0x218f3  ldarg.0
0x218f4  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x218f9  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x218fe  brfalse  loc_21B6B
0x21903  ldarg.0
0x21904  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21909  ldarg.0
0x2190a  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2190f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Import
0x21914  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21919  brfalse.s loc_21963
0x2191b  ldloc.2
0x2191c  brtrue.s loc_21956
0x2191e  ldarg.0
0x2191f  ldstr    aXsltNotattop// "Xslt_NotAtTop"
0x21924  ldc.i4.2
0x21925  newarr   [mscorlib]System.String
0x2192a  dup
0x2192b  ldc.i4.0
0x2192c  ldarg.0
0x2192d  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21932  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x21937  stelem.ref
0x21938  dup
0x21939  ldc.i4.1
0x2193a  ldloc.1
0x2193b  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x21940  stelem.ref
0x21941  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x21946  ldarg.0
0x21947  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2194c  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x21951  br       loc_21BE0
0x21956  ldc.i4.1
0x21957  stloc.3
0x21958  ldarg.0
0x21959  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadImport()
0x2195e  br       loc_21BE0
0x21963  ldarg.0
0x21964  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21969  ldarg.0
0x2196a  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x2196f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Include
0x21974  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21979  brfalse.s loc_21986
0x2197b  ldarg.0
0x2197c  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadInclude()
0x21981  br       loc_21BE0
0x21986  ldarg.0
0x21987  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2198c  ldarg.0
0x2198d  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21992  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::StripSpace
0x21997  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2199c  brfalse.s loc_219AF
0x2199e  ldarg.0
0x2199f  ldloc.0
0x219a0  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x219a5  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadStripSpace(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x219aa  br       loc_21BE0
0x219af  ldarg.0
0x219b0  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x219b5  ldarg.0
0x219b6  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x219bb  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::PreserveSpace
0x219c0  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x219c5  brfalse.s loc_219D8
0x219c7  ldarg.0
0x219c8  ldloc.0
0x219c9  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x219ce  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadPreserveSpace(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x219d3  br       loc_21BE0
0x219d8  ldarg.0
0x219d9  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x219de  ldarg.0
0x219df  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x219e4  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Output
0x219e9  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x219ee  brfalse.s loc_219FB
0x219f0  ldarg.0
0x219f1  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadOutput()
0x219f6  br       loc_21BE0
0x219fb  ldarg.0
0x219fc  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21a01  ldarg.0
0x21a02  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21a07  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Key
0x21a0c  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21a11  brfalse.s loc_21A24
0x21a13  ldarg.0
0x21a14  ldloc.0
0x21a15  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21a1a  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadKey(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21a1f  br       loc_21BE0
0x21a24  ldarg.0
0x21a25  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21a2a  ldarg.0
0x21a2b  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21a30  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::DecimalFormat
0x21a35  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21a3a  brfalse.s loc_21A4D
0x21a3c  ldarg.0
0x21a3d  ldloc.0
0x21a3e  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21a43  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadDecimalFormat(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21a48  br       loc_21BE0
0x21a4d  ldarg.0
0x21a4e  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21a53  ldarg.0
0x21a54  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21a59  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::NamespaceAlias
0x21a5e  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21a63  brfalse.s loc_21A76
0x21a65  ldarg.0
0x21a66  ldloc.0
0x21a67  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21a6c  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadNamespaceAlias(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21a71  br       loc_21BE0
0x21a76  ldarg.0
0x21a77  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21a7c  ldarg.0
0x21a7d  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21a82  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::AttributeSet
0x21a87  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21a8c  brfalse.s loc_21A9F
0x21a8e  ldarg.0
0x21a8f  ldloc.0
0x21a90  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21a95  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadAttributeSet(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21a9a  br       loc_21BE0
0x21a9f  ldarg.0
0x21aa0  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21aa5  ldarg.0
0x21aa6  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21aab  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Variable
0x21ab0  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21ab5  brfalse.s loc_21ACA
0x21ab7  ldarg.0
0x21ab8  ldloc.0
0x21ab9  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21abe  ldc.i4.s 0x1E
0x21ac0  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadGlobalVariableOrParameter(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList, valuetype System.Xml.Xsl.Xslt.XslNodeType nodeType)
0x21ac5  br       loc_21BE0
0x21aca  ldarg.0
0x21acb  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21ad0  ldarg.0
0x21ad1  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21ad6  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x21adb  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21ae0  brfalse.s loc_21AF5
0x21ae2  ldarg.0
0x21ae3  ldloc.0
0x21ae4  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21ae9  ldc.i4.s 0x16
0x21aeb  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadGlobalVariableOrParameter(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList, valuetype System.Xml.Xsl.Xslt.XslNodeType nodeType)
0x21af0  br       loc_21BE0
0x21af5  ldarg.0
0x21af6  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21afb  ldarg.0
0x21afc  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21b01  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Template
0x21b06  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21b0b  brfalse.s loc_21B1E
0x21b0d  ldarg.0
0x21b0e  ldloc.0
0x21b0f  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21b14  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadTemplate(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21b19  br       loc_21BE0
0x21b1e  ldarg.0
0x21b1f  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b24  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::GetVersionAttribute()
0x21b29  ldarg.0
0x21b2a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b2f  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x21b34  brtrue.s loc_21B5E
0x21b36  ldarg.0
0x21b37  ldstr    aXsltUnexpected_0// "Xslt_UnexpectedElement"
0x21b3c  ldc.i4.2
0x21b3d  newarr   [mscorlib]System.String
0x21b42  dup
0x21b43  ldc.i4.0
0x21b44  ldarg.0
0x21b45  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b4a  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x21b4f  stelem.ref
0x21b50  dup
0x21b51  ldc.i4.1
0x21b52  ldloc.1
0x21b53  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x21b58  stelem.ref
0x21b59  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x21b5e  ldarg.0
0x21b5f  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b64  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x21b69  br.s     loc_21BE0
0x21b6b  ldarg.0
0x21b6c  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b71  ldarg.0
0x21b72  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21b77  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UrnMsxsl
0x21b7c  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsNs(string ns)
0x21b81  brfalse.s loc_21BA9
0x21b83  ldarg.0
0x21b84  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21b89  ldarg.0
0x21b8a  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x21b8f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Script
0x21b94  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x21b99  brfalse.s loc_21BA9
0x21b9b  ldarg.0
0x21b9c  ldloc.0
0x21b9d  ldfld    class System.Xml.Xsl.Xslt.NsDecl ContextInfo::nsList
0x21ba2  call     instance void System.Xml.Xsl.Xslt.XsltLoader::LoadMsScript(class System.Xml.Xsl.Xslt.NsDecl stylesheetNsList)
0x21ba7  br.s     loc_21BE0
0x21ba9  ldarg.0
0x21baa  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21baf  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsNullNamespace()
0x21bb4  brfalse.s loc_21BD5
0x21bb6  ldarg.0
0x21bb7  ldstr    aXsltNullnsatto// "Xslt_NullNsAtTopLevel"
0x21bbc  ldc.i4.1
0x21bbd  newarr   [mscorlib]System.String
0x21bc2  dup
0x21bc3  ldc.i4.0
0x21bc4  ldarg.0
0x21bc5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21bca  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x21bcf  stelem.ref
0x21bd0  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x21bd5  ldarg.0
0x21bd6  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21bdb  callvirt instance void System.Xml.Xsl.Xslt.XsltInput::SkipNode()
0x21be0  ldloc.3
0x21be1  stloc.2
0x21be2  br.s     loc_21BFE
0x21be4  ldarg.0
0x21be5  ldstr    aXsltTextnodesn// "Xslt_TextNodesNotAllowed"
0x21bea  ldc.i4.1
0x21beb  newarr   [mscorlib]System.String
0x21bf0  dup
0x21bf1  ldc.i4.0
0x21bf2  ldloc.1
0x21bf3  call     string DelayedQName::op_Implicit(valuetype DelayedQName qn)
0x21bf8  stelem.ref
0x21bf9  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportError(string res, string[] args)
0x21bfe  ldarg.0
0x21bff  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21c04  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToNextSibling()
0x21c09  brtrue   loc_218CF
0x21c0e  ret
```
