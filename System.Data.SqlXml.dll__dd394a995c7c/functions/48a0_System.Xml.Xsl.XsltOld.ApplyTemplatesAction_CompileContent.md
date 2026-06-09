# System.Xml.Xsl.XsltOld.ApplyTemplatesAction::CompileContent

- ea: `0x48a0`
- end: `0x4987`
- name: `System.Xml.Xsl.XsltOld.ApplyTemplatesAction::CompileContent`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4800`

## callees

- `0x48a0`
- `0x5af0`
- `0x5b00`
- `0x5b10`
- `0x5b20`
- `0x5e50`
- `0x5eb0`
- `0x6e10`
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

- `0x4968`: `apply-templates`

## pseudocode

```c

```

## disassembly

```asm
0x48a0  ldarg.1
0x48a1  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x48a6  stloc.0
0x48a7  ldarg.1
0x48a8  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Recurse()
0x48ad  brfalse  loc_4986
0x48b2  ldloc.0
0x48b3  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0x48b8  stloc.3
0x48b9  ldloc.3
0x48ba  ldc.i4.1
0x48bb  beq.s    loc_48CB
0x48bd  ldloc.3
0x48be  ldc.i4.5
0x48bf  sub
0x48c0  ldc.i4.3
0x48c1  ble.un   loc_4974
0x48c6  br       loc_495B
0x48cb  ldarg.1
0x48cc  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PushNamespaceScope()
0x48d1  ldloc.0
0x48d2  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_NamespaceURI()
0x48d7  stloc.1
0x48d8  ldloc.0
0x48d9  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x48de  stloc.2
0x48df  ldloc.1
0x48e0  ldloc.0
0x48e1  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x48e6  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UriXsl
0x48eb  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x48f0  brfalse.s loc_494C
0x48f2  ldloc.2
0x48f3  ldloc.0
0x48f4  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x48f9  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Sort
0x48fe  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x4903  brfalse.s loc_4913
0x4905  ldarg.0
0x4906  ldarg.1
0x4907  callvirt instance class System.Xml.Xsl.XsltOld.SortAction System.Xml.Xsl.XsltOld.Compiler::CreateSortAction()
0x490c  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x4911  br.s     loc_4953
0x4913  ldloc.2
0x4914  ldloc.0
0x4915  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x491a  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::WithParam
0x491f  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x4924  brfalse.s loc_4945
0x4926  ldarg.1
0x4927  callvirt instance class System.Xml.Xsl.XsltOld.WithParamAction System.Xml.Xsl.XsltOld.Compiler::CreateWithParamAction()
0x492c  stloc.s  4
0x492e  ldarg.0
0x492f  ldloc.s  4
0x4931  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.VariableAction::get_Name()
0x4936  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::CheckDuplicateParams(class [System.Xml]System.Xml.XmlQualifiedName name)
0x493b  ldarg.0
0x493c  ldloc.s  4
0x493e  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x4943  br.s     loc_4953
0x4945  ldarg.1
0x4946  callvirt instance class [System.Xml]System.Xml.Xsl.XsltException System.Xml.Xsl.XsltOld.Compiler::UnexpectedKeyword()
0x494b  throw
0x494c  ldarg.1
0x494d  callvirt instance class [System.Xml]System.Xml.Xsl.XsltException System.Xml.Xsl.XsltOld.Compiler::UnexpectedKeyword()
0x4952  throw
0x4953  ldarg.1
0x4954  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::PopScope()
0x4959  br.s     loc_4974
0x495b  ldstr    aXsltInvalidcon// "Xslt_InvalidContents"
0x4960  ldc.i4.1
0x4961  newarr   [mscorlib]System.String
0x4966  dup
0x4967  ldc.i4.0
0x4968  ldstr    aApplyTemplates// "apply-templates"
0x496d  stelem.ref
0x496e  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x4973  throw
0x4974  ldarg.1
0x4975  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::Advance()
0x497a  brtrue   loc_48B2
0x497f  ldarg.1
0x4980  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::ToParent()
0x4985  pop
0x4986  ret
```
