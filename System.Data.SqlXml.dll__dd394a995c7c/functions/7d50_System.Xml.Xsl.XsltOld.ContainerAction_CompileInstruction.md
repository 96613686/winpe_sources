# System.Xml.Xsl.XsltOld.ContainerAction::CompileInstruction

- ea: `0x7d50`
- end: `0x7f99`
- name: `System.Xml.Xsl.XsltOld.ContainerAction::CompileInstruction`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7cd0`

## callees

- `0x5af0`
- `0x5ca0`
- `0x6cf0`
- `0x6d00`
- `0x6d10`
- `0x6d30`
- `0x6d40`
- `0x6d50`
- `0x6d60`
- `0x6d70`
- `0x6d80`
- `0x6d90`
- `0x6da0`
- `0x6db0`
- `0x6dc0`
- `0x6dd0`
- `0x6de0`
- `0x6e40`
- `0x6e60`
- `0x6e70`
- `0x6ec0`
- `0x7d50`
- `0x8130`
- `0xa8a0`
- `0xa950`

## pseudocode

```c

```

## disassembly

```asm
0x7d50  ldarg.1
0x7d51  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x7d56  stloc.0
0x7d57  ldnull
0x7d58  stloc.1
0x7d59  ldloc.0
0x7d5a  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x7d5f  stloc.2
0x7d60  ldloc.2
0x7d61  ldloc.0
0x7d62  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7d67  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyImports
0x7d6c  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7d71  brfalse.s loc_7D7F
0x7d73  ldarg.1
0x7d74  callvirt instance class System.Xml.Xsl.XsltOld.ApplyImportsAction System.Xml.Xsl.XsltOld.Compiler::CreateApplyImportsAction()
0x7d79  stloc.1
0x7d7a  br       loc_7F91
0x7d7f  ldloc.2
0x7d80  ldloc.0
0x7d81  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7d86  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ApplyTemplates
0x7d8b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7d90  brfalse.s loc_7D9E
0x7d92  ldarg.1
0x7d93  callvirt instance class System.Xml.Xsl.XsltOld.ApplyTemplatesAction System.Xml.Xsl.XsltOld.Compiler::CreateApplyTemplatesAction()
0x7d98  stloc.1
0x7d99  br       loc_7F91
0x7d9e  ldloc.2
0x7d9f  ldloc.0
0x7da0  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7da5  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Attribute
0x7daa  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7daf  brfalse.s loc_7DBD
0x7db1  ldarg.1
0x7db2  callvirt instance class System.Xml.Xsl.XsltOld.AttributeAction System.Xml.Xsl.XsltOld.Compiler::CreateAttributeAction()
0x7db7  stloc.1
0x7db8  br       loc_7F91
0x7dbd  ldloc.2
0x7dbe  ldloc.0
0x7dbf  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7dc4  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::CallTemplate
0x7dc9  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7dce  brfalse.s loc_7DDC
0x7dd0  ldarg.1
0x7dd1  callvirt instance class System.Xml.Xsl.XsltOld.CallTemplateAction System.Xml.Xsl.XsltOld.Compiler::CreateCallTemplateAction()
0x7dd6  stloc.1
0x7dd7  br       loc_7F91
0x7ddc  ldloc.2
0x7ddd  ldloc.0
0x7dde  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7de3  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Choose
0x7de8  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7ded  brfalse.s loc_7DFB
0x7def  ldarg.1
0x7df0  callvirt instance class System.Xml.Xsl.XsltOld.ChooseAction System.Xml.Xsl.XsltOld.Compiler::CreateChooseAction()
0x7df5  stloc.1
0x7df6  br       loc_7F91
0x7dfb  ldloc.2
0x7dfc  ldloc.0
0x7dfd  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e02  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Comment
0x7e07  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e0c  brfalse.s loc_7E1A
0x7e0e  ldarg.1
0x7e0f  callvirt instance class System.Xml.Xsl.XsltOld.CommentAction System.Xml.Xsl.XsltOld.Compiler::CreateCommentAction()
0x7e14  stloc.1
0x7e15  br       loc_7F91
0x7e1a  ldloc.2
0x7e1b  ldloc.0
0x7e1c  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e21  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Copy
0x7e26  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e2b  brfalse.s loc_7E39
0x7e2d  ldarg.1
0x7e2e  callvirt instance class System.Xml.Xsl.XsltOld.CopyAction System.Xml.Xsl.XsltOld.Compiler::CreateCopyAction()
0x7e33  stloc.1
0x7e34  br       loc_7F91
0x7e39  ldloc.2
0x7e3a  ldloc.0
0x7e3b  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e40  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::CopyOf
0x7e45  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e4a  brfalse.s loc_7E58
0x7e4c  ldarg.1
0x7e4d  callvirt instance class System.Xml.Xsl.XsltOld.CopyOfAction System.Xml.Xsl.XsltOld.Compiler::CreateCopyOfAction()
0x7e52  stloc.1
0x7e53  br       loc_7F91
0x7e58  ldloc.2
0x7e59  ldloc.0
0x7e5a  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e5f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Element
0x7e64  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e69  brfalse.s loc_7E77
0x7e6b  ldarg.1
0x7e6c  callvirt instance class System.Xml.Xsl.XsltOld.ElementAction System.Xml.Xsl.XsltOld.Compiler::CreateElementAction()
0x7e71  stloc.1
0x7e72  br       loc_7F91
0x7e77  ldloc.2
0x7e78  ldloc.0
0x7e79  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e7e  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Fallback
0x7e83  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e88  brfalse.s loc_7E8B
0x7e8a  ret
0x7e8b  ldloc.2
0x7e8c  ldloc.0
0x7e8d  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7e92  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ForEach
0x7e97  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7e9c  brfalse.s loc_7EAA
0x7e9e  ldarg.1
0x7e9f  callvirt instance class System.Xml.Xsl.XsltOld.ForEachAction System.Xml.Xsl.XsltOld.Compiler::CreateForEachAction()
0x7ea4  stloc.1
0x7ea5  br       loc_7F91
0x7eaa  ldloc.2
0x7eab  ldloc.0
0x7eac  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7eb1  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::If
0x7eb6  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7ebb  brfalse.s loc_7ECA
0x7ebd  ldarg.1
0x7ebe  ldc.i4.0
0x7ebf  callvirt instance class System.Xml.Xsl.XsltOld.IfAction System.Xml.Xsl.XsltOld.Compiler::CreateIfAction(valuetype ConditionType type)
0x7ec4  stloc.1
0x7ec5  br       loc_7F91
0x7eca  ldloc.2
0x7ecb  ldloc.0
0x7ecc  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7ed1  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Message
0x7ed6  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7edb  brfalse.s loc_7EE9
0x7edd  ldarg.1
0x7ede  callvirt instance class System.Xml.Xsl.XsltOld.MessageAction System.Xml.Xsl.XsltOld.Compiler::CreateMessageAction()
0x7ee3  stloc.1
0x7ee4  br       loc_7F91
0x7ee9  ldloc.2
0x7eea  ldloc.0
0x7eeb  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7ef0  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Number
0x7ef5  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7efa  brfalse.s loc_7F08
0x7efc  ldarg.1
0x7efd  callvirt instance class System.Xml.Xsl.XsltOld.NumberAction System.Xml.Xsl.XsltOld.Compiler::CreateNumberAction()
0x7f02  stloc.1
0x7f03  br       loc_7F91
0x7f08  ldloc.2
0x7f09  ldloc.0
0x7f0a  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7f0f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ProcessingInstruction
0x7f14  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7f19  brfalse.s loc_7F24
0x7f1b  ldarg.1
0x7f1c  callvirt instance class System.Xml.Xsl.XsltOld.ProcessingInstructionAction System.Xml.Xsl.XsltOld.Compiler::CreateProcessingInstructionAction()
0x7f21  stloc.1
0x7f22  br.s     loc_7F91
0x7f24  ldloc.2
0x7f25  ldloc.0
0x7f26  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7f2b  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Text
0x7f30  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7f35  brfalse.s loc_7F40
0x7f37  ldarg.1
0x7f38  callvirt instance class System.Xml.Xsl.XsltOld.TextAction System.Xml.Xsl.XsltOld.Compiler::CreateTextAction()
0x7f3d  stloc.1
0x7f3e  br.s     loc_7F91
0x7f40  ldloc.2
0x7f41  ldloc.0
0x7f42  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7f47  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ValueOf
0x7f4c  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7f51  brfalse.s loc_7F5C
0x7f53  ldarg.1
0x7f54  callvirt instance class System.Xml.Xsl.XsltOld.ValueOfAction System.Xml.Xsl.XsltOld.Compiler::CreateValueOfAction()
0x7f59  stloc.1
0x7f5a  br.s     loc_7F91
0x7f5c  ldloc.2
0x7f5d  ldloc.0
0x7f5e  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x7f63  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Variable
0x7f68  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x7f6d  brfalse.s loc_7F79
0x7f6f  ldarg.1
0x7f70  ldc.i4.2
0x7f71  callvirt instance class System.Xml.Xsl.XsltOld.VariableAction System.Xml.Xsl.XsltOld.Compiler::CreateVariableAction(valuetype System.Xml.Xsl.XsltOld.VariableType type)
0x7f76  stloc.1
0x7f77  br.s     loc_7F91
0x7f79  ldarg.1
0x7f7a  callvirt instance bool System.Xml.Xsl.XsltOld.Compiler::get_ForwardCompatibility()
0x7f7f  brfalse.s loc_7F8A
0x7f81  ldarg.1
0x7f82  callvirt instance class System.Xml.Xsl.XsltOld.NewInstructionAction System.Xml.Xsl.XsltOld.Compiler::CreateNewInstructionAction()
0x7f87  stloc.1
0x7f88  br.s     loc_7F91
0x7f8a  ldarg.1
0x7f8b  callvirt instance class [System.Xml]System.Xml.Xsl.XsltException System.Xml.Xsl.XsltOld.Compiler::UnexpectedKeyword()
0x7f90  throw
0x7f91  ldarg.0
0x7f92  ldloc.1
0x7f93  call     instance void System.Xml.Xsl.XsltOld.ContainerAction::AddAction(class System.Xml.Xsl.XsltOld.Action action)
0x7f98  ret
```
