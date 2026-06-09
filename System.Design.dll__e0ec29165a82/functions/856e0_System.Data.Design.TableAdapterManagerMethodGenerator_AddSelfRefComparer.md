# System.Data.Design.TableAdapterManagerMethodGenerator::AddSelfRefComparer

- ea: `0x856e0`
- end: `0x86231`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddSelfRefComparer`
- size: `2897`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x85090`

## callees

- `0x71e90`
- `0x71f20`
- `0x71f60`
- `0x71f80`
- `0x71fd0`
- `0x71fe0`
- `0x72010`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72090`
- `0x720b0`
- `0x720d0`
- `0x720f0`
- `0x72120`
- `0x72160`
- `0x721b0`
- `0x721e0`
- `0x721f0`
- `0x72200`
- `0x72240`
- `0x72260`
- `0x72280`
- `0x722a0`
- `0x72320`
- `0x72350`
- `0x72360`
- `0x72390`
- `0x723b0`
- `0x723e0`
- `0x72410`
- `0x72450`
- `0x72500`
- `0x72560`

## string_xrefs

- `0x856ec`: `SelfReferenceComparer`
- `0x856f9`: `System.Collections.Generic.IComparer`
- `0x85ea9`: `Compare`
- `0x860f1`: `CompareTo`

## pseudocode

```c

```

## disassembly

```asm
0x856e0  ldstr    aRelation_1// "_relation"
0x856e5  stloc.0
0x856e6  ldstr    aChildfirst_0// "_childFirst"
0x856eb  stloc.1
0x856ec  ldstr    aSelfreferencec// "SelfReferenceComparer"
0x856f1  ldc.i4.0
0x856f2  ldc.i4.3
0x856f3  call     class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.CodeGenHelper::Class(string name, bool isPartial, valuetype [mscorlib]System.Reflection.TypeAttributes typeAttributes)
0x856f8  stloc.2
0x856f9  ldstr    aSystemCollecti// "System.Collections.Generic.IComparer"
0x856fe  ldtoken  [System.Data]System.Data.DataRow
0x85703  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85708  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalGenericType(string fullTypeName, class [mscorlib]System.Type itemType)
0x8570d  stloc.3
0x8570e  ldloc.2
0x8570f  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x85714  ldtoken  [mscorlib]System.Object
0x85719  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8571e  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x85723  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x85728  pop
0x85729  ldloc.2
0x8572a  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x8572f  ldloc.3
0x85730  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x85735  pop
0x85736  ldloc.2
0x85737  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x8573c  ldstr    aUsedToSortSelf// "Used to sort self-referenced table's ro"...
0x85741  ldc.i4.1
0x85742  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x85747  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x8574c  pop
0x8574d  ldarg.1
0x8574e  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85753  ldloc.2
0x85754  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x85759  pop
0x8575a  ldloc.2
0x8575b  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85760  ldtoken  [System.Data]System.Data.DataRelation
0x85765  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8576a  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8576f  ldloc.0
0x85770  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x85775  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8577a  pop
0x8577b  ldloc.2
0x8577c  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85781  ldtoken  [mscorlib]System.Int32
0x85786  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8578b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x85790  ldloc.1
0x85791  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x85796  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8579b  pop
0x8579c  ldc.i4   0x1000
0x857a1  call     class [System]System.CodeDom.CodeConstructor System.Data.Design.CodeGenHelper::Constructor(valuetype [System]System.CodeDom.MemberAttributes attributes)
0x857a6  stloc.s  4
0x857a8  ldloc.s  4
0x857aa  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x857af  ldtoken  [System.Data]System.Data.DataRelation
0x857b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x857b9  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x857be  ldstr    aRelation// "relation"
0x857c3  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x857c8  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x857cd  pop
0x857ce  ldloc.s  4
0x857d0  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x857d5  ldtoken  [mscorlib]System.Boolean
0x857da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x857df  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x857e4  ldstr    aChildfirst// "childFirst"
0x857e9  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x857ee  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x857f3  pop
0x857f4  ldloc.s  4
0x857f6  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x857fb  ldloc.0
0x857fc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x85801  ldstr    aRelation// "relation"
0x85806  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8580b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x85810  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85815  pop
0x85816  ldloc.s  4
0x85818  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8581d  ldstr    aChildfirst// "childFirst"
0x85822  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85827  ldloc.1
0x85828  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x8582d  ldc.i4.m1
0x8582e  box      [mscorlib]System.Int32
0x85833  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x85838  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8583d  ldloc.1
0x8583e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x85843  ldc.i4.1
0x85844  box      [mscorlib]System.Int32
0x85849  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8584e  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x85853  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm, class [System]System.CodeDom.CodeStatement falseStm)
0x85858  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8585d  pop
0x8585e  ldloc.2
0x8585f  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85864  ldloc.s  4
0x85866  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8586b  pop
0x8586c  ldstr    aRow_0// "row"
0x85871  stloc.s  5
0x85873  ldstr    aDistance// "distance"
0x85878  stloc.s  6
0x8587a  ldstr    aRoot// "root"
0x8587f  stloc.s  7
0x85881  ldstr    aParent_0// "parent"
0x85886  stloc.s  8
0x85888  ldstr    aGetroot// "GetRoot"
0x8588d  stloc.s  9
0x8588f  ldstr    aTraversedrows// "traversedRows"
0x85894  stloc.s  0xA
0x85896  ldtoken  [System.Data]System.Data.DataRow
0x8589b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x858a0  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x858a5  ldloc.s  9
0x858a7  ldc.i4   0x5000
0x858ac  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x858b1  stloc.s  0xB
0x858b3  ldloc.s  0xB
0x858b5  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x858ba  ldtoken  [System.Data]System.Data.DataRow
0x858bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x858c4  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x858c9  ldloc.s  5
0x858cb  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x858d0  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x858d5  pop
0x858d6  ldtoken  [mscorlib]System.Int32
0x858db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x858e0  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x858e5  ldloc.s  6
0x858e7  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x858ec  stloc.s  0xC
0x858ee  ldloc.s  0xC
0x858f0  ldc.i4.1
0x858f1  callvirt instance void [System]System.CodeDom.CodeParameterDeclarationExpression::set_Direction(valuetype [System]System.CodeDom.FieldDirection)
0x858f6  ldloc.s  0xB
0x858f8  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x858fd  ldloc.s  0xC
0x858ff  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x85904  pop
0x85905  ldloc.s  0xB
0x85907  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8590c  ldtoken  [System]System.Diagnostics.Debug
0x85911  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85916  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8591b  ldstr    aAssert// "Assert"
0x85920  ldloc.s  5
0x85922  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85927  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNotNull(class [System]System.CodeDom.CodeExpression id)
0x8592c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::MethodCallStm(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x85931  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85936  pop
0x85937  ldloc.s  0xB
0x85939  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8593e  ldtoken  [System.Data]System.Data.DataRow
0x85943  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85948  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8594d  ldloc.s  7
0x8594f  ldloc.s  5
0x85951  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85956  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8595b  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85960  pop
0x85961  ldloc.s  0xB
0x85963  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x85968  ldloc.s  6
0x8596a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8596f  ldc.i4.0
0x85970  box      [mscorlib]System.Int32
0x85975  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8597a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8597f  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85984  pop
0x85985  ldloc.s  0xB
0x85987  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8598c  newobj   instance void [System]System.CodeDom.CodeSnippetStatement::.ctor()
0x85991  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85996  pop
0x85997  ldstr    aSystemCollecti_0// "System.Collections.Generic.IDictionary"
0x8599c  ldc.i4.2
0x8599d  newarr   [System]System.CodeDom.CodeTypeReference
0x859a2  dup
0x859a3  ldc.i4.0
0x859a4  ldtoken  [System.Data]System.Data.DataRow
0x859a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x859ae  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x859b3  stelem.ref
0x859b4  dup
0x859b5  ldc.i4.1
0x859b6  ldtoken  [System.Data]System.Data.DataRow
0x859bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x859c0  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x859c5  stelem.ref
0x859c6  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string, class [System]System.CodeDom.CodeTypeReference[])
0x859cb  stloc.s  0xD
0x859cd  ldloc.s  0xD
0x859cf  ldc.i4.1
0x859d0  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0x859d5  ldstr    aSystemCollecti_1// "System.Collections.Generic.Dictionary"
0x859da  ldc.i4.2
0x859db  newarr   [System]System.CodeDom.CodeTypeReference
0x859e0  dup
0x859e1  ldc.i4.0
0x859e2  ldtoken  [System.Data]System.Data.DataRow
0x859e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x859ec  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x859f1  stelem.ref
0x859f2  dup
0x859f3  ldc.i4.1
0x859f4  ldtoken  [System.Data]System.Data.DataRow
0x859f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x859fe  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x85a03  stelem.ref
0x85a04  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(string, class [System]System.CodeDom.CodeTypeReference[])
0x85a09  stloc.s  0xE
0x85a0b  ldloc.s  0xE
0x85a0d  ldc.i4.1
0x85a0e  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0x85a13  ldloc.s  0xB
0x85a15  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x85a1a  ldloc.s  0xD
0x85a1c  ldloc.s  0xA
0x85a1e  ldloc.s  0xE
0x85a20  ldc.i4.0
0x85a21  newarr   [System]System.CodeDom.CodeExpression
0x85a26  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x85a2b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x85a30  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85a35  pop
0x85a36  ldloc.s  0xB
0x85a38  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x85a3d  ldloc.s  0xA
0x85a3f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x85a44  ldloc.s  5
0x85a46  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85a4b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x85a50  ldloc.s  5
0x85a52  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85a57  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x85a5c  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85a61  pop
0x85a62  ldloc.s  0xB
0x85a64  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x85a69  newobj   instance void [System]System.CodeDom.CodeSnippetStatement::.ctor()
0x85a6e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85a73  pop
0x85a74  ldloc.s  0xB
0x85a76  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x85a7b  ldtoken  [System.Data]System.Data.DataRow
0x85a80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85a85  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x85a8a  ldloc.s  8
0x85a8c  ldloc.s  5
0x85a8e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x85a93  ldstr    aGetparentrow// "GetParentRow"
0x85a98  ldc.i4.2
0x85a99  newarr   [System]System.CodeDom.CodeExpression
0x85a9e  dup
0x85a9f  ldc.i4.0
0x85aa0  ldloc.0
0x85aa1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x85aa6  stelem.ref
0x85aa7  dup
0x85aa8  ldc.i4.1
0x85aa9  ldtoken  [System.Data]System.Data.DataRowVersion
0x85aae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85ab3  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x85ab8  ldstr    aDefault_0// "Default"
0x85abd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x85ac2  stelem.ref
0x85ac3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x85ac8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x85acd  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x85ad2  pop
0x85ad3  newobj   instance void [System]System.CodeDom.CodeIterationStatement::.ctor()
0x85ad8  stloc.s  0xF
0x85ada  ldloc.s  0xF
0x85adc  ldloc.s  8
0x85ade  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x85ae3  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNotNull(class [System]System.CodeDom.CodeExpression id)
0x85ae8  ldloc.s  0xA
0x85aea  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x85aef  ldstr    aContainskey// "ContainsKey"
0x85af4  ldloc.s  8
0x85af6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x85afb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x85b00  ldc.i4.0
0x85b01  box      [mscorlib]System.Boolean
  ... truncated ...
```
