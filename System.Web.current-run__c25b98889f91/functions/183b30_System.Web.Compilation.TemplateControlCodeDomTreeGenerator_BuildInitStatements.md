# System.Web.Compilation.TemplateControlCodeDomTreeGenerator::BuildInitStatements

- ea: `0x183b30`
- end: `0x183c57`
- name: `System.Web.Compilation.TemplateControlCodeDomTreeGenerator::BuildInitStatements`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1808a0`

## callees

- `0x2e800`
- `0x30f70`
- `0x31090`
- `0x31470`
- `0x5b3f0`
- `0x80cb0`
- `0x81250`
- `0x170100`
- `0x170a30`
- `0x17d6c0`
- `0x183b10`
- `0x183b30`

## string_xrefs

- `0x183bb8`: `ReadStringResource`
- `0x183bee`: `AppRelativeVirtualPath`

## pseudocode

```c

```

## disassembly

```asm
0x183b30  ldarg.0
0x183b31  ldarg.1
0x183b32  ldarg.2
0x183b33  call     instance void System.Web.Compilation.BaseCodeDomTreeGenerator::BuildInitStatements(class [System]System.CodeDom.CodeStatementCollection trueStatements, class [System]System.CodeDom.CodeStatementCollection topLevelStatements)
0x183b38  ldarg.0
0x183b39  ldfld    class System.Web.StringResourceBuilder System.Web.Compilation.BaseCodeDomTreeGenerator::_stringResourceBuilder
0x183b3e  callvirt instance bool System.Web.StringResourceBuilder::get_HasStrings()
0x183b43  brfalse  loc_183BD2
0x183b48  ldtoken  [mscorlib]System.Object
0x183b4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x183b52  ldstr    aStringresource// "__stringResource"
0x183b57  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(class [mscorlib]System.Type, string)
0x183b5c  stloc.2
0x183b5d  ldloc.2
0x183b5e  dup
0x183b5f  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x183b64  ldc.i4.3
0x183b65  or
0x183b66  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x183b6b  ldarg.0
0x183b6c  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.Web.Compilation.BaseCodeDomTreeGenerator::_sourceDataClass
0x183b71  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x183b76  ldloc.2
0x183b77  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x183b7c  pop
0x183b7d  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor()
0x183b82  stloc.3
0x183b83  ldloc.3
0x183b84  ldarg.0
0x183b85  ldfld    class [System]System.CodeDom.CodeTypeReferenceExpression System.Web.Compilation.BaseCodeDomTreeGenerator::_classTypeExpr
0x183b8a  ldstr    aStringresource// "__stringResource"
0x183b8f  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x183b94  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Left(class [System]System.CodeDom.CodeExpression)
0x183b99  newobj   instance void [System]System.CodeDom.CodeMethodInvokeExpression::.ctor()
0x183b9e  stloc.s  4
0x183ba0  ldloc.s  4
0x183ba2  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x183ba7  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x183bac  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_TargetObject(class [System]System.CodeDom.CodeExpression)
0x183bb1  ldloc.s  4
0x183bb3  callvirt instance class [System]System.CodeDom.CodeMethodReferenceExpression [System]System.CodeDom.CodeMethodInvokeExpression::get_Method()
0x183bb8  ldstr    aReadstringreso// "ReadStringResource"
0x183bbd  callvirt instance void [System]System.CodeDom.CodeMethodReferenceExpression::set_MethodName(string)
0x183bc2  ldloc.3
0x183bc3  ldloc.s  4
0x183bc5  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x183bca  ldarg.1
0x183bcb  ldloc.3
0x183bcc  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x183bd1  pop
0x183bd2  ldarg.0
0x183bd3  call     instance class System.Web.UI.TemplateControlParser System.Web.Compilation.TemplateControlCodeDomTreeGenerator::get_Parser()
0x183bd8  callvirt instance class [mscorlib]System.Type System.Web.UI.TemplateParser::get_BaseType()
0x183bdd  call     class [System]System.CodeDom.CodeTypeReference System.Web.Compilation.CodeDomUtility::BuildGlobalCodeTypeReference(class [mscorlib]System.Type type)
0x183be2  stloc.0
0x183be3  ldloc.0
0x183be4  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x183be9  newobj   instance void [System]System.CodeDom.CodeCastExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression)
0x183bee  ldstr    aApprelativevir// "AppRelativeVirtualPath"
0x183bf3  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x183bf8  ldarg.0
0x183bf9  call     instance class System.Web.UI.TemplateControlParser System.Web.Compilation.TemplateControlCodeDomTreeGenerator::get_Parser()
0x183bfe  callvirt instance class System.Web.VirtualPath System.Web.UI.BaseParser::get_CurrentVirtualPath()
0x183c03  callvirt instance string System.Web.VirtualPath::get_AppRelativeVirtualPathString()
0x183c08  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x183c0d  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x183c12  stloc.1
0x183c13  ldarg.0
0x183c14  ldfld    bool System.Web.Compilation.BaseCodeDomTreeGenerator::_designerMode
0x183c19  brtrue.s loc_183C4E
0x183c1b  ldarg.0
0x183c1c  call     instance class System.Web.UI.TemplateControlParser System.Web.Compilation.TemplateControlCodeDomTreeGenerator::get_Parser()
0x183c21  callvirt instance class System.Web.VirtualPath System.Web.UI.TemplateParser::get_CodeFileVirtualPath()
0x183c26  ldnull
0x183c27  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x183c2c  brfalse.s loc_183C4E
0x183c2e  ldloc.1
0x183c2f  ldarg.0
0x183c30  call     instance class System.Web.UI.TemplateControlParser System.Web.Compilation.TemplateControlCodeDomTreeGenerator::get_Parser()
0x183c35  callvirt instance class System.Web.VirtualPath System.Web.UI.TemplateParser::get_CodeFileVirtualPath()
0x183c3a  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x183c3f  ldc.i4   System.Web.UI.WebControls.TargetConverter
0x183c44  call     class [System]System.CodeDom.CodeLinePragma System.Web.Compilation.BaseCodeDomTreeGenerator::CreateCodeLinePragmaHelper(string virtualPath, int32 lineNumber)
0x183c49  callvirt instance void [System]System.CodeDom.CodeStatement::set_LinePragma(class [System]System.CodeDom.CodeLinePragma)
0x183c4e  ldarg.2
0x183c4f  ldloc.1
0x183c50  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x183c55  pop
0x183c56  ret
```
