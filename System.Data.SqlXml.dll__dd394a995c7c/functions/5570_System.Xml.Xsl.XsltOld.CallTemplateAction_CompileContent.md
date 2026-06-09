# System.Xml.Xsl.XsltOld.CallTemplateAction::CompileContent

- ea: `0x5570`
- end: `0x562c`
- name: `System.Xml.Xsl.XsltOld.CallTemplateAction::CompileContent`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5500`

## callees

- `0x5570`
- `0x5af0`
- `0x5b00`
- `0x5b10`
- `0x5b20`
- `0x5e50`
- `0x5eb0`
- `0x6e90`
- `0x6ec0`
- `0x8130`
- `0x83c0`
- `0xa8a0`
- `0xa930`
- `0xa950`
- `0xa960`
- `0x11e20`

## string_xrefs

- `0x560d`: `call-template`

## pseudocode

```c

```

## disassembly

```asm
0x5570  ldarg.1
0x5571  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x5576  stloc.0
0x5577  ldarg.1
0x5578  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x557d  brfalse  loc_562B
0x5582  ldloc.0
0x5583  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0x5588  stloc.3
0x5589  ldloc.3
0x558a  ldc.i4.1
0x558b  beq.s    loc_5598
0x558d  ldloc.3
0x558e  ldc.i4.5
0x558f  sub
0x5590  ldc.i4.3
0x5591  ble.un   loc_5619
0x5596  br.s     loc_5600
0x5598  ldarg.1
0x5599  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PushNamespaceScope()
0x559e  ldloc.0
0x559f  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_NamespaceURI()
0x55a4  stloc.1
0x55a5  ldloc.0
0x55a6  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x55ab  stloc.2
0x55ac  ldloc.1
0x55ad  ldloc.0
0x55ae  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x55b3  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UriXsl
0x55b8  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x55bd  brfalse.s loc_55F1
0x55bf  ldloc.2
0x55c0  ldloc.0
0x55c1  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x55c6  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::WithParam
0x55cb  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x55d0  brfalse.s loc_55F1
0x55d2  ldarg.1
0x55d3  callvirt instance class System.Xml.Xsl.XsltOld.WithParamAction System.Xml.Xsl.XsltOld.Compiler::CreateWithParamAction()
0x55d8  stloc.s  4
0x55da  ldarg.0
0x55db  ldloc.s  4
0x55dd  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.VariableAction::get_Name()
0x55e2  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CheckDuplicateParams(class [System.Xml]System.Xml.XmlQualifiedName name)
0x55e7  ldarg.0
0x55e8  ldloc.s  4
0x55ea  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x55ef  br.s     loc_55F8
0x55f1  ldarg.1
0x55f2  callvirt instance class [System.Xml]System.Xml.Xsl.XsltException System.Xml.Xsl.XsltOld.Compiler::UnexpectedKeyword()
0x55f7  throw
0x55f8  ldarg.1
0x55f9  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PopScope()
0x55fe  br.s     loc_5619
0x5600  ldstr    aXsltInvalidcon// "Xslt_InvalidContents"
0x5605  ldc.i4.1
0x5606  newarr   [mscorlib]System.String
0x560b  dup
0x560c  ldc.i4.0
0x560d  ldstr    aCallTemplate// "call-template"
0x5612  stelem.ref
0x5613  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x5618  throw
0x5619  ldarg.1
0x561a  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Advance()
0x561f  brtrue   loc_5582
0x5624  ldarg.1
0x5625  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x562a  pop
0x562b  ret
```
