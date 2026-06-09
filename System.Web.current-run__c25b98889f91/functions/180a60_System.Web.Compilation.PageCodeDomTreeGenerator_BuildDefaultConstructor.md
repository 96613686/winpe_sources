# System.Web.Compilation.PageCodeDomTreeGenerator::BuildDefaultConstructor

- ea: `0x180a60`
- end: `0x180f80`
- name: `System.Web.Compilation.PageCodeDomTreeGenerator::BuildDefaultConstructor`
- size: `1312`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x71030`
- `0x71040`
- `0x71070`
- `0x710a0`
- `0x710d0`
- `0x71100`
- `0x71130`
- `0x71160`
- `0x71190`
- `0x711c0`
- `0x711f0`
- `0x71220`
- `0x77d20`
- `0x77da0`
- `0x77db0`
- `0x80440`
- `0x16f9b0`
- `0x170000`
- `0x1807d0`
- `0x180a60`
- `0x1840e0`

## string_xrefs

- `0x180c61`: `outputCacheSettings`
- `0x180c96`: `outputCacheSettings`
- `0x180b23`: `AspCompatMode`
- `0x180be3`: `__outputCacheSettings`
- `0x180c27`: `__outputCacheSettings`
- `0x180f48`: `__outputCacheSettings`
- `0x180cc6`: `CacheProfile`

## pseudocode

```c

```

## disassembly

```asm
0x180a60  ldarg.0
0x180a61  call     instance void System.Web.Compilation.TemplateControlCodeDomTreeGenerator::BuildDefaultConstructor()
0x180a66  ldarg.0
0x180a67  call     instance class [System]System.CodeDom.Compiler.CompilerParameters System.Web.Compilation.BaseCodeDomTreeGenerator::get_CompilParams()
0x180a6c  callvirt instance bool [System]System.CodeDom.Compiler.CompilerParameters::get_IncludeDebugInformation()
0x180a71  brfalse.s loc_180ABF
0x180a73  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor()
0x180a78  stloc.0
0x180a79  ldloc.0
0x180a7a  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x180a7f  ldstr    aServer// "Server"
0x180a84  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180a89  ldstr    aScripttimeout// "ScriptTimeout"
0x180a8e  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180a93  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Left(class [System]System.CodeDom.CodeExpression)
0x180a98  ldloc.0
0x180a99  ldc.i4   0x1C9C380
0x180a9e  box      [mscorlib]System.Int32
0x180aa3  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180aa8  callvirt instance void [System]System.CodeDom.CodeAssignStatement::set_Right(class [System]System.CodeDom.CodeExpression)
0x180aad  ldarg.0
0x180aae  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseCodeDomTreeGenerator::get_InitMethod()
0x180ab3  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x180ab8  ldloc.0
0x180ab9  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180abe  pop
0x180abf  ldarg.0
0x180ac0  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180ac5  callvirt instance int32 System.Web.UI.PageParser::get_TransactionMode()
0x180aca  brfalse.s loc_180B06
0x180acc  ldarg.0
0x180acd  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseCodeDomTreeGenerator::get_InitMethod()
0x180ad2  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x180ad7  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x180adc  ldstr    aTransactionmod// "TransactionMode"
0x180ae1  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180ae6  ldarg.0
0x180ae7  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180aec  callvirt instance int32 System.Web.UI.PageParser::get_TransactionMode()
0x180af1  box      [mscorlib]System.Int32
0x180af6  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180afb  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180b00  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180b05  pop
0x180b06  ldarg.0
0x180b07  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180b0c  callvirt instance bool System.Web.UI.PageParser::get_AspCompatMode()
0x180b11  brfalse.s loc_180B4D
0x180b13  ldarg.0
0x180b14  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseCodeDomTreeGenerator::get_InitMethod()
0x180b19  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x180b1e  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x180b23  ldstr    aAspcompatmode// "AspCompatMode"
0x180b28  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180b2d  ldarg.0
0x180b2e  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180b33  callvirt instance bool System.Web.UI.PageParser::get_AspCompatMode()
0x180b38  box      [mscorlib]System.Boolean
0x180b3d  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180b42  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180b47  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180b4c  pop
0x180b4d  ldarg.0
0x180b4e  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180b53  callvirt instance bool System.Web.UI.PageParser::get_AsyncMode()
0x180b58  brfalse.s loc_180B94
0x180b5a  ldarg.0
0x180b5b  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseCodeDomTreeGenerator::get_InitMethod()
0x180b60  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x180b65  newobj   instance void [System]System.CodeDom.CodeThisReferenceExpression::.ctor()
0x180b6a  ldstr    aAsyncmode// "AsyncMode"
0x180b6f  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180b74  ldarg.0
0x180b75  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180b7a  callvirt instance bool System.Web.UI.PageParser::get_AsyncMode()
0x180b7f  box      [mscorlib]System.Boolean
0x180b84  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180b89  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180b8e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180b93  pop
0x180b94  ldarg.0
0x180b95  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180b9a  callvirt instance class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::get_OutputCacheParameters()
0x180b9f  brfalse  loc_180F7F
0x180ba4  ldarg.0
0x180ba5  call     instance class System.Web.UI.PageParser System.Web.Compilation.PageCodeDomTreeGenerator::get_Parser()
0x180baa  callvirt instance class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::get_OutputCacheParameters()
0x180baf  stloc.1
0x180bb0  ldloc.1
0x180bb1  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x180bb6  brfalse.s loc_180BC5
0x180bb8  ldloc.1
0x180bb9  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x180bbe  callvirt instance int32 [mscorlib]System.String::get_Length()
0x180bc3  brtrue.s loc_180BD9
0x180bc5  ldloc.1
0x180bc6  callvirt instance int32 System.Web.UI.OutputCacheParameters::get_Duration()
0x180bcb  brtrue.s loc_180BD9
0x180bcd  ldloc.1
0x180bce  callvirt instance valuetype System.Web.UI.OutputCacheLocation System.Web.UI.OutputCacheParameters::get_Location()
0x180bd3  ldc.i4.4
0x180bd4  bne.un   loc_180F7F
0x180bd9  ldtoken  System.Web.UI.OutputCacheParameters
0x180bde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180be3  ldstr    aOutputcacheset_0// "__outputCacheSettings"
0x180be8  newobj   instance void [System]System.CodeDom.CodeMemberField::.ctor(class [mscorlib]System.Type, string)
0x180bed  stloc.2
0x180bee  ldloc.2
0x180bef  dup
0x180bf0  callvirt instance valuetype [System]System.CodeDom.MemberAttributes [System]System.CodeDom.CodeTypeMember::get_Attributes()
0x180bf5  ldc.i4.3
0x180bf6  or
0x180bf7  callvirt instance void [System]System.CodeDom.CodeTypeMember::set_Attributes(valuetype [System]System.CodeDom.MemberAttributes)
0x180bfc  ldloc.2
0x180bfd  ldnull
0x180bfe  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180c03  callvirt instance void [System]System.CodeDom.CodeMemberField::set_InitExpression(class [System]System.CodeDom.CodeExpression)
0x180c08  ldarg.0
0x180c09  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.Web.Compilation.BaseCodeDomTreeGenerator::_sourceDataClass
0x180c0e  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x180c13  ldloc.2
0x180c14  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x180c19  pop
0x180c1a  newobj   instance void [System]System.CodeDom.CodeConditionStatement::.ctor()
0x180c1f  stloc.3
0x180c20  ldloc.3
0x180c21  ldarg.0
0x180c22  ldfld    class [System]System.CodeDom.CodeTypeReferenceExpression System.Web.Compilation.BaseCodeDomTreeGenerator::_classTypeExpr
0x180c27  ldstr    aOutputcacheset_0// "__outputCacheSettings"
0x180c2c  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180c31  ldc.i4.7
0x180c32  ldnull
0x180c33  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180c38  newobj   instance void [System]System.CodeDom.CodeBinaryOperatorExpression::.ctor(class [System]System.CodeDom.CodeExpression, valuetype [System]System.CodeDom.CodeBinaryOperatorType, class [System]System.CodeDom.CodeExpression)
0x180c3d  callvirt instance void [System]System.CodeDom.CodeConditionStatement::set_Condition(class [System]System.CodeDom.CodeExpression)
0x180c42  newobj   instance void [System]System.CodeDom.CodeVariableDeclarationStatement::.ctor()
0x180c47  stloc.s  4
0x180c49  ldloc.s  4
0x180c4b  ldtoken  System.Web.UI.OutputCacheParameters
0x180c50  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180c55  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x180c5a  callvirt instance void [System]System.CodeDom.CodeVariableDeclarationStatement::set_Type(class [System]System.CodeDom.CodeTypeReference)
0x180c5f  ldloc.s  4
0x180c61  ldstr    aOutputcacheset// "outputCacheSettings"
0x180c66  callvirt instance void [System]System.CodeDom.CodeVariableDeclarationStatement::set_Name(string)
0x180c6b  ldloc.3
0x180c6c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180c71  ldc.i4.0
0x180c72  ldloc.s  4
0x180c74  callvirt instance void [System]System.CodeDom.CodeStatementCollection::Insert(int32, class [System]System.CodeDom.CodeStatement)
0x180c79  newobj   instance void [System]System.CodeDom.CodeObjectCreateExpression::.ctor()
0x180c7e  stloc.s  5
0x180c80  ldloc.s  5
0x180c82  ldtoken  System.Web.UI.OutputCacheParameters
0x180c87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180c8c  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x180c91  callvirt instance void [System]System.CodeDom.CodeObjectCreateExpression::set_CreateType(class [System]System.CodeDom.CodeTypeReference)
0x180c96  ldstr    aOutputcacheset// "outputCacheSettings"
0x180c9b  newobj   instance void [System]System.CodeDom.CodeVariableReferenceExpression::.ctor(string)
0x180ca0  stloc.s  6
0x180ca2  ldloc.s  6
0x180ca4  ldloc.s  5
0x180ca6  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180cab  stloc.s  7
0x180cad  ldloc.3
0x180cae  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180cb3  ldloc.s  7
0x180cb5  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180cba  pop
0x180cbb  ldloc.1
0x180cbc  ldc.i4.1
0x180cbd  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180cc2  brfalse.s loc_180CF0
0x180cc4  ldloc.s  6
0x180cc6  ldstr    aCacheprofile_0// "CacheProfile"
0x180ccb  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180cd0  ldloc.1
0x180cd1  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x180cd6  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180cdb  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180ce0  stloc.s  0xA
0x180ce2  ldloc.3
0x180ce3  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180ce8  ldloc.s  0xA
0x180cea  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180cef  pop
0x180cf0  ldloc.1
0x180cf1  ldc.i4.2
0x180cf2  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180cf7  brfalse.s loc_180D2A
0x180cf9  ldloc.s  6
0x180cfb  ldstr    aDuration// "Duration"
0x180d00  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180d05  ldloc.1
0x180d06  callvirt instance int32 System.Web.UI.OutputCacheParameters::get_Duration()
0x180d0b  box      [mscorlib]System.Int32
0x180d10  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180d15  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180d1a  stloc.s  0xB
0x180d1c  ldloc.3
0x180d1d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180d22  ldloc.s  0xB
0x180d24  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180d29  pop
0x180d2a  ldloc.1
0x180d2b  ldc.i4.4
0x180d2c  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180d31  brfalse.s loc_180D64
0x180d33  ldloc.s  6
0x180d35  ldstr    aEnabled// "Enabled"
0x180d3a  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180d3f  ldloc.1
0x180d40  callvirt instance bool System.Web.UI.OutputCacheParameters::get_Enabled()
0x180d45  box      [mscorlib]System.Boolean
0x180d4a  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180d4f  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180d54  stloc.s  0xC
0x180d56  ldloc.3
0x180d57  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180d5c  ldloc.s  0xC
0x180d5e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180d63  pop
0x180d64  ldloc.1
0x180d65  ldc.i4.8
0x180d66  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180d6b  brfalse.s loc_180DB7
0x180d6d  ldloc.s  6
0x180d6f  ldstr    aLocation// "Location"
0x180d74  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180d79  ldtoken  System.Web.UI.OutputCacheLocation
0x180d7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180d83  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x180d88  ldloc.1
0x180d89  callvirt instance valuetype System.Web.UI.OutputCacheLocation System.Web.UI.OutputCacheParameters::get_Location()
0x180d8e  stloc.s  0xE
0x180d90  ldloca.s 0xE
0x180d92  constrained. System.Web.UI.OutputCacheLocation
0x180d98  callvirt instance string [mscorlib]System.Object::ToString()
0x180d9d  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180da2  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180da7  stloc.s  0xD
0x180da9  ldloc.3
0x180daa  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180daf  ldloc.s  0xD
0x180db1  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180db6  pop
0x180db7  ldloc.1
0x180db8  ldc.i4.s 0x10
0x180dba  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180dbf  brfalse.s loc_180DF2
0x180dc1  ldloc.s  6
0x180dc3  ldstr    aNostore_1// "NoStore"
0x180dc8  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180dcd  ldloc.1
0x180dce  callvirt instance bool System.Web.UI.OutputCacheParameters::get_NoStore()
0x180dd3  box      [mscorlib]System.Boolean
0x180dd8  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180ddd  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180de2  stloc.s  0xF
0x180de4  ldloc.3
0x180de5  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180dea  ldloc.s  0xF
0x180dec  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180df1  pop
0x180df2  ldloc.1
0x180df3  ldc.i4.s 0x20
0x180df5  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180dfa  brfalse.s loc_180E28
0x180dfc  ldloc.s  6
0x180dfe  ldstr    aSqldependency_1// "SqlDependency"
0x180e03  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180e08  ldloc.1
0x180e09  callvirt instance string System.Web.UI.OutputCacheParameters::get_SqlDependency()
0x180e0e  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180e13  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180e18  stloc.s  0x10
0x180e1a  ldloc.3
0x180e1b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180e20  ldloc.s  0x10
0x180e22  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180e27  pop
0x180e28  ldloc.1
0x180e29  ldc.i4.s 0x40
0x180e2b  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x180e30  brfalse.s loc_180E5E
0x180e32  ldloc.s  6
0x180e34  ldstr    aVarybycontrol_1// "VaryByControl"
0x180e39  newobj   instance void [System]System.CodeDom.CodePropertyReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x180e3e  ldloc.1
0x180e3f  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByControl()
0x180e44  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x180e49  newobj   instance void [System]System.CodeDom.CodeAssignStatement::.ctor(class [System]System.CodeDom.CodeExpression, class [System]System.CodeDom.CodeExpression)
0x180e4e  stloc.s  0x11
0x180e50  ldloc.3
0x180e51  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeConditionStatement::get_TrueStatements()
0x180e56  ldloc.s  0x11
0x180e58  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x180e5d  pop
0x180e5e  ldloc.1
0x180e5f  ldc.i4   0x80
  ... truncated ...
```
