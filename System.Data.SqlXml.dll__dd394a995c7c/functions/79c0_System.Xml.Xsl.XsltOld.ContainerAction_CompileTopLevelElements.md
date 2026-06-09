# System.Xml.Xsl.XsltOld.ContainerAction::CompileTopLevelElements

- ea: `0x79c0`
- end: `0x7cb1`
- name: `System.Xml.Xsl.XsltOld.ContainerAction::CompileTopLevelElements`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7220`

## callees

- `0x5990`
- `0x5af0`
- `0x5b00`
- `0x5b10`
- `0x5b20`
- `0x5b30`
- `0x5ca0`
- `0x5e50`
- `0x5eb0`
- `0x6130`
- `0x6250`
- `0x6260`
- `0x6460`
- `0x6470`
- `0x6d20`
- `0x6e20`
- `0x6e70`
- `0x6ec0`
- `0x73a0`
- `0x7430`
- `0x7530`
- `0x7660`
- `0x78e0`
- `0x79c0`
- `0x8110`
- `0x8130`
- `0x81c0`
- `0xa8a0`
- `0xa930`
- `0xa940`
- `0xa950`
- `0xa960`
- `0x10920`

## pseudocode

```c

```

## disassembly

```asm
0x79c0  ldarg.1
0x79c1  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x79c6  brtrue.s loc_79C9
0x79c8  ret
0x79c9  ldarg.1
0x79ca  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x79cf  stloc.0
0x79d0  ldc.i4.0
0x79d1  stloc.1
0x79d2  ldloc.0
0x79d3  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0x79d8  stloc.s  4
0x79da  ldloc.s  4
0x79dc  ldc.i4.1
0x79dd  beq.s    loc_79EE
0x79df  ldloc.s  4
0x79e1  ldc.i4.5
0x79e2  sub
0x79e3  ldc.i4.3
0x79e4  ble.un   loc_7C9E
0x79e9  br       loc_7C85
0x79ee  ldloc.0
0x79ef  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x79f4  stloc.2
0x79f5  ldloc.0
0x79f6  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_NamespaceURI()
0x79fb  stloc.3
0x79fc  ldloc.3
0x79fd  ldloc.0
0x79fe  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7a03  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UriXsl
0x7a08  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7a0d  brfalse  loc_7C34
0x7a12  ldloc.2
0x7a13  ldloc.0
0x7a14  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7a19  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Import
0x7a1e  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7a23  brfalse.s loc_7A9F
0x7a25  ldloc.1
0x7a26  brfalse.s loc_7A39
0x7a28  ldstr    aXsltNotfirstim// "Xslt_NotFirstImport"
0x7a2d  ldc.i4.0
0x7a2e  newarr   [mscorlib]System.String
0x7a33  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x7a38  throw
0x7a39  ldarg.1
0x7a3a  ldarg.1
0x7a3b  ldarg.1
0x7a3c  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x7a41  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7a46  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Href
0x7a4b  callvirt instance string System.Xml.Xsl.XsltOld.Compiler::GetSingleAttribute(string attributeAtom)
0x7a50  callvirt instance class [System]System.Uri System.Xml.Xsl.XsltOld.Compiler::ResolveUri(string relativeUri)
0x7a55  stloc.s  5
0x7a57  ldloc.s  5
0x7a59  callvirt instance string [mscorlib]System.Object::ToString()
0x7a5e  stloc.s  6
0x7a60  ldarg.1
0x7a61  ldloc.s  6
0x7a63  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::IsCircularReference(string href)
0x7a68  brfalse.s loc_7A80
0x7a6a  ldstr    aXsltCircularin// "Xslt_CircularInclude"
0x7a6f  ldc.i4.1
0x7a70  newarr   [mscorlib]System.String
0x7a75  dup
0x7a76  ldc.i4.0
0x7a77  ldloc.s  6
0x7a79  stelem.ref
0x7a7a  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x7a7f  throw
0x7a80  ldarg.1
0x7a81  callvirt instance class System.Xml.Xsl.XsltOld.Stylesheet System.Xml.Xsl.XsltOld.Compiler::get_CompiledStylesheet()
0x7a86  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.Stylesheet::get_Imports()
0x7a8b  ldloc.s  5
0x7a8d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7a92  pop
0x7a93  ldarg.0
0x7a94  ldarg.1
0x7a95  call     instance void System.Xml.Xsl.XsltOld.CompiledAction::CheckEmpty(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7a9a  br       loc_7C9E
0x7a9f  ldloc.2
0x7aa0  ldloc.0
0x7aa1  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7aa6  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Include
0x7aab  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7ab0  brfalse.s loc_7AC0
0x7ab2  ldc.i4.1
0x7ab3  stloc.1
0x7ab4  ldarg.0
0x7ab5  ldarg.1
0x7ab6  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileInclude(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7abb  br       loc_7C9E
0x7ac0  ldc.i4.1
0x7ac1  stloc.1
0x7ac2  ldarg.1
0x7ac3  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PushNamespaceScope()
0x7ac8  ldloc.2
0x7ac9  ldloc.0
0x7aca  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7acf  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::StripSpace
0x7ad4  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7ad9  brfalse.s loc_7AE8
0x7adb  ldarg.0
0x7adc  ldarg.1
0x7add  ldc.i4.0
0x7ade  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileSpace(class System.Xml.Xsl.XsltOld.Compiler compiler, bool preserve)
0x7ae3  br       loc_7C2C
0x7ae8  ldloc.2
0x7ae9  ldloc.0
0x7aea  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7aef  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::PreserveSpace
0x7af4  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7af9  brfalse.s loc_7B08
0x7afb  ldarg.0
0x7afc  ldarg.1
0x7afd  ldc.i4.1
0x7afe  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileSpace(class System.Xml.Xsl.XsltOld.Compiler compiler, bool preserve)
0x7b03  br       loc_7C2C
0x7b08  ldloc.2
0x7b09  ldloc.0
0x7b0a  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7b0f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Output
0x7b14  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7b19  brfalse.s loc_7B27
0x7b1b  ldarg.0
0x7b1c  ldarg.1
0x7b1d  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileOutput(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7b22  br       loc_7C2C
0x7b27  ldloc.2
0x7b28  ldloc.0
0x7b29  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7b2e  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Key
0x7b33  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7b38  brfalse.s loc_7B46
0x7b3a  ldarg.0
0x7b3b  ldarg.1
0x7b3c  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileKey(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7b41  br       loc_7C2C
0x7b46  ldloc.2
0x7b47  ldloc.0
0x7b48  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7b4d  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::DecimalFormat
0x7b52  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7b57  brfalse.s loc_7B65
0x7b59  ldarg.0
0x7b5a  ldarg.1
0x7b5b  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileDecimalFormat(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7b60  br       loc_7C2C
0x7b65  ldloc.2
0x7b66  ldloc.0
0x7b67  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7b6c  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::NamespaceAlias
0x7b71  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7b76  brfalse.s loc_7B84
0x7b78  ldarg.0
0x7b79  ldarg.1
0x7b7a  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CompileNamespaceAlias(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7b7f  br       loc_7C2C
0x7b84  ldloc.2
0x7b85  ldloc.0
0x7b86  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7b8b  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::AttributeSet
0x7b90  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7b95  brfalse.s loc_7BA8
0x7b97  ldarg.1
0x7b98  ldarg.1
0x7b99  callvirt instance class System.Xml.Xsl.XsltOld.AttributeSetAction System.Xml.Xsl.XsltOld.Compiler::CreateAttributeSetAction()
0x7b9e  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::AddAttributeSet(class System.Xml.Xsl.XsltOld.AttributeSetAction attributeSet)
0x7ba3  br       loc_7C2C
0x7ba8  ldloc.2
0x7ba9  ldloc.0
0x7baa  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7baf  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Variable
0x7bb4  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7bb9  brfalse.s loc_7BD2
0x7bbb  ldarg.1
0x7bbc  ldc.i4.0
0x7bbd  callvirt instance class System.Xml.Xsl.XsltOld.VariableAction System.Xml.Xsl.XsltOld.Compiler::CreateVariableAction(valuetype System.Xml.Xsl.XsltOld.VariableType type)
0x7bc2  stloc.s  7
0x7bc4  ldloc.s  7
0x7bc6  brfalse.s loc_7C2C
0x7bc8  ldarg.0
0x7bc9  ldloc.s  7
0x7bcb  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x7bd0  br.s     loc_7C2C
0x7bd2  ldloc.2
0x7bd3  ldloc.0
0x7bd4  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7bd9  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Param
0x7bde  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7be3  brfalse.s loc_7BFC
0x7be5  ldarg.1
0x7be6  ldc.i4.1
0x7be7  callvirt instance class System.Xml.Xsl.XsltOld.VariableAction System.Xml.Xsl.XsltOld.Compiler::CreateVariableAction(valuetype System.Xml.Xsl.XsltOld.VariableType type)
0x7bec  stloc.s  8
0x7bee  ldloc.s  8
0x7bf0  brfalse.s loc_7C2C
0x7bf2  ldarg.0
0x7bf3  ldloc.s  8
0x7bf5  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x7bfa  br.s     loc_7C2C
0x7bfc  ldloc.2
0x7bfd  ldloc.0
0x7bfe  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7c03  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Template
0x7c08  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7c0d  brfalse.s loc_7C1D
0x7c0f  ldarg.1
0x7c10  ldarg.1
0x7c11  callvirt instance class System.Xml.Xsl.XsltOld.TemplateAction System.Xml.Xsl.XsltOld.Compiler::CreateTemplateAction()
0x7c16  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::AddTemplate(class System.Xml.Xsl.XsltOld.TemplateAction template)
0x7c1b  br.s     loc_7C2C
0x7c1d  ldarg.1
0x7c1e  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::get_ForwardCompatibility()
0x7c23  brtrue.s loc_7C2C
0x7c25  ldarg.1
0x7c26  callvirt instance class [System.Xml]System.Xml.Xsl.XsltException System.Xml.Xsl.XsltOld.Compiler::UnexpectedKeyword()
0x7c2b  throw
0x7c2c  ldarg.1
0x7c2d  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PopScope()
0x7c32  br.s     loc_7C9E
0x7c34  ldloc.3
0x7c35  ldloc.0
0x7c36  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7c3b  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UrnMsxsl
0x7c40  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7c45  brfalse.s loc_7C63
0x7c47  ldloc.2
0x7c48  ldloc.0
0x7c49  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7c4e  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Script
0x7c53  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7c58  brfalse.s loc_7C63
0x7c5a  ldarg.0
0x7c5b  ldarg.1
0x7c5c  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddScript(class System.Xml.Xsl.XsltOld.Compiler compiler)
0x7c61  br.s     loc_7C9E
0x7c63  ldloc.3
0x7c64  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7c69  brtrue.s loc_7C9E
0x7c6b  ldstr    aXsltNullnsatto// "Xslt_NullNsAtTopLevel"
0x7c70  ldc.i4.1
0x7c71  newarr   [mscorlib]System.String
0x7c76  dup
0x7c77  ldc.i4.0
0x7c78  ldloc.0
0x7c79  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Name()
0x7c7e  stelem.ref
0x7c7f  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x7c84  throw
0x7c85  ldstr    aXsltInvalidcon// "Xslt_InvalidContents"
0x7c8a  ldc.i4.1
0x7c8b  newarr   [mscorlib]System.String
0x7c90  dup
0x7c91  ldc.i4.0
0x7c92  ldstr    aStylesheet// "stylesheet"
0x7c97  stelem.ref
0x7c98  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x7c9d  throw
0x7c9e  ldarg.1
0x7c9f  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Advance()
0x7ca4  brtrue   loc_79D2
0x7ca9  ldarg.1
0x7caa  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x7caf  pop
0x7cb0  ret
```
