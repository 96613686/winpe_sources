# System.Data.Design.TableAdapterManagerMethodGenerator::AddRealUpdatedRowsMethod

- ea: `0x873d0`
- end: `0x875ef`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddRealUpdatedRowsMethod`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x863b0`

## callees

- `0x71f20`
- `0x71f30`
- `0x71f80`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x720b0`
- `0x720d0`
- `0x720f0`
- `0x72120`
- `0x721e0`
- `0x72200`
- `0x72250`
- `0x72260`
- `0x72280`
- `0x72320`
- `0x72390`
- `0x72450`
- `0x72500`
- `0x72560`
- `0x87b40`

## string_xrefs

- `0x873d0`: `realUpdatedRows`
- `0x873e6`: `GetRealUpdatedRows`
- `0x87435`: `Remove inserted rows that become updated rows after calling TableAdapter.Update(inserted rows) first`

## pseudocode

```c

```

## disassembly

```asm
0x873d0  ldstr    aRealupdatedrow// "realUpdatedRows"
0x873d5  stloc.0
0x873d6  ldtoken  [System.Data]System.Data.DataRow
0x873db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x873e0  ldc.i4.1
0x873e1  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x873e6  ldstr    aGetrealupdated// "GetRealUpdatedRows"
0x873eb  ldc.i4   0x5000
0x873f0  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x873f5  stloc.1
0x873f6  ldstr    aSystemCollecti_2// "System.Collections.Generic.List"
0x873fb  ldtoken  [System.Data]System.Data.DataRow
0x87400  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87405  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalGenericType(string fullTypeName, class [mscorlib]System.Type itemType)
0x8740a  stloc.2
0x8740b  ldloc.2
0x8740c  ldarg.3
0x8740d  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x87412  stloc.3
0x87413  ldtoken  [System.Data]System.Data.DataRow
0x87418  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8741d  ldc.i4.1
0x8741e  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x87423  stloc.s  4
0x87425  ldloc.s  4
0x87427  ldarg.2
0x87428  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x8742d  stloc.s  5
0x8742f  ldloc.1
0x87430  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x87435  ldstr    aRemoveInserted// "Remove inserted rows that become update"...
0x8743a  ldc.i4.1
0x8743b  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x87440  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x87445  pop
0x87446  ldloc.1
0x87447  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x8744c  ldc.i4.2
0x8744d  newarr   [System]System.CodeDom.CodeParameterDeclarationExpression
0x87452  dup
0x87453  ldc.i4.0
0x87454  ldloc.s  5
0x87456  stelem.ref
0x87457  dup
0x87458  ldc.i4.1
0x87459  ldloc.3
0x8745a  stelem.ref
0x8745b  callvirt instance void [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::AddRange(class [System]System.CodeDom.CodeParameterDeclarationExpression[])
0x87460  ldloc.1
0x87461  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x87466  ldarg.2
0x87467  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8746c  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNull(class [System]System.CodeDom.CodeExpression id)
0x87471  ldarg.2
0x87472  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x87477  ldstr    aLength// "Length"
0x8747c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x87481  ldc.i4.1
0x87482  box      [mscorlib]System.Int32
0x87487  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8748c  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87491  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Or(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87496  ldarg.2
0x87497  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8749c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x874a1  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x874a6  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x874ab  pop
0x874ac  ldloc.1
0x874ad  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x874b2  ldarg.3
0x874b3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x874b8  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdIsNull(class [System]System.CodeDom.CodeExpression id)
0x874bd  ldarg.3
0x874be  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x874c3  ldstr    aCount// "Count"
0x874c8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x874cd  ldc.i4.1
0x874ce  box      [mscorlib]System.Int32
0x874d3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x874d8  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x874dd  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Or(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x874e2  ldarg.2
0x874e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x874e8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x874ed  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x874f2  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x874f7  pop
0x874f8  ldloc.1
0x874f9  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x874fe  ldloc.2
0x874ff  ldloc.0
0x87500  ldloc.2
0x87501  ldc.i4.0
0x87502  newarr   [System]System.CodeDom.CodeExpression
0x87507  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x8750c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x87511  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x87516  pop
0x87517  ldstr    aRow_0// "row"
0x8751c  stloc.s  6
0x8751e  ldc.i4.2
0x8751f  newarr   [System]System.CodeDom.CodeStatement
0x87524  stloc.s  7
0x87526  ldloc.s  7
0x87528  ldc.i4.0
0x87529  ldtoken  [System.Data]System.Data.DataRow
0x8752e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87533  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x87538  ldloc.s  6
0x8753a  ldarg.2
0x8753b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87540  ldstr    aI// "i"
0x87545  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8754a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x8754f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x87554  stelem.ref
0x87555  ldloc.s  7
0x87557  ldc.i4.1
0x87558  ldarg.3
0x87559  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8755e  ldstr    aContains_0// "Contains"
0x87563  ldloc.s  6
0x87565  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8756a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x8756f  ldc.i4.0
0x87570  box      [mscorlib]System.Boolean
0x87575  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8757a  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8757f  ldloc.0
0x87580  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87585  ldstr    aAdd// "Add"
0x8758a  ldloc.s  6
0x8758c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87591  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::MethodCallStm(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x87596  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x8759b  stelem.ref
0x8759c  ldloc.1
0x8759d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x875a2  ldarg.0
0x875a3  ldarg.2
0x875a4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x875a9  ldstr    aLength// "Length"
0x875ae  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x875b3  ldloc.s  7
0x875b5  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.TableAdapterManagerMethodGenerator::GetForLoopItoCount(class [System]System.CodeDom.CodeExpression countExp, class [System]System.CodeDom.CodeStatement[] forStms)
0x875ba  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x875bf  pop
0x875c0  ldloc.1
0x875c1  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x875c6  ldloc.0
0x875c7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x875cc  ldstr    aToarray// "ToArray"
0x875d1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x875d6  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x875db  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x875e0  pop
0x875e1  ldarg.1
0x875e2  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x875e7  ldloc.1
0x875e8  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x875ed  pop
0x875ee  ret
```
