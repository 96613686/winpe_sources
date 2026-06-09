# System.Data.Design.DataComponentMethodGenerator::AddConnectionMembers

- ea: `0x738f0`
- end: `0x73c5c`
- name: `System.Data.Design.DataComponentMethodGenerator::AddConnectionMembers`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x73230`

## callees

- `0x71e90`
- `0x71f20`
- `0x71fb0`
- `0x71fd0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72070`
- `0x72090`
- `0x72120`
- `0x721b0`
- `0x721c0`
- `0x721d0`
- `0x72260`
- `0x72270`
- `0x72280`
- `0x722a0`
- `0x72380`
- `0x72390`
- `0x723b0`
- `0x724a0`
- `0x72500`
- `0x72510`
- `0x74800`
- `0x74830`
- `0x74850`
- `0x74860`
- `0x74890`
- `0x7adf0`
- `0x7cb70`
- `0x7d0b0`

## string_xrefs

- `0x73a5b`: `DeleteCommand`
- `0x73a7f`: `DeleteCommand`
- `0x739f4`: `InsertCommand`
- `0x73a18`: `InsertCommand`
- `0x73ac2`: `UpdateCommand`
- `0x73ae6`: `UpdateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x738f0  ldarg.0
0x738f1  ldfld    class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.DataComponentMethodGenerator::providerFactory
0x738f6  callvirt instance class [System.Data]System.Data.Common.DbConnection [System.Data]System.Data.Common.DbProviderFactory::CreateConnection()
0x738fb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x73900  stloc.0
0x73901  ldarg.0
0x73902  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x73907  callvirt instance class System.Data.Design.IDesignConnection System.Data.Design.DesignTable::get_Connection()
0x7390c  castclass System.Data.Design.DesignConnection
0x73911  callvirt instance valuetype [System]System.CodeDom.MemberAttributes System.Data.Design.DesignConnection::get_Modifier()
0x73916  stloc.1
0x73917  ldarg.1
0x73918  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x7391d  ldloc.0
0x7391e  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x73923  call     string System.Data.Design.DataComponentNameHandler::get_DefaultConnectionVariableName()
0x73928  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x7392d  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x73932  pop
0x73933  ldloc.0
0x73934  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x73939  call     string System.Data.Design.DataComponentNameHandler::get_DefaultConnectionPropertyName()
0x7393e  ldloc.1
0x7393f  ldc.i4.2
0x73940  or
0x73941  call     class [System]System.CodeDom.CodeMemberProperty System.Data.Design.CodeGenHelper::PropertyDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x73946  stloc.2
0x73947  ldloc.2
0x73948  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x7394d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73952  call     string System.Data.Design.DataComponentNameHandler::get_DefaultConnectionVariableName()
0x73957  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x7395c  ldnull
0x7395d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73962  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73967  ldc.i4.1
0x73968  newarr   [System]System.CodeDom.CodeStatement
0x7396d  dup
0x7396e  ldc.i4.0
0x7396f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73974  call     string System.Data.Design.DataComponentNameHandler::get_InitConnection()
0x73979  ldc.i4.0
0x7397a  newarr   [System]System.CodeDom.CodeExpression
0x7397f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x73984  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x73989  stelem.ref
0x7398a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x7398f  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73994  pop
0x73995  ldloc.2
0x73996  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x7399b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x739a0  call     string System.Data.Design.DataComponentNameHandler::get_DefaultConnectionVariableName()
0x739a5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x739aa  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x739af  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x739b4  pop
0x739b5  ldloc.2
0x739b6  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x739bb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x739c0  call     string System.Data.Design.DataComponentNameHandler::get_DefaultConnectionVariableName()
0x739c5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x739ca  ldstr    aValue// "value"
0x739cf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x739d4  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x739d9  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x739de  pop
0x739df  ldloc.2
0x739e0  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x739e5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x739ea  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x739ef  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x739f4  ldstr    aInsertcommand// "InsertCommand"
0x739f9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x739fe  ldnull
0x739ff  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73a04  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73a09  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73a0e  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73a13  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a18  ldstr    aInsertcommand// "InsertCommand"
0x73a1d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a22  ldstr    aConnection// "Connection"
0x73a27  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a2c  ldstr    aValue// "value"
0x73a31  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x73a36  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73a3b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73a40  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73a45  pop
0x73a46  ldloc.2
0x73a47  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73a4c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73a51  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73a56  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a5b  ldstr    aDeletecommand// "DeleteCommand"
0x73a60  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a65  ldnull
0x73a66  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73a6b  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73a70  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73a75  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73a7a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a7f  ldstr    aDeletecommand// "DeleteCommand"
0x73a84  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a89  ldstr    aConnection// "Connection"
0x73a8e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73a93  ldstr    aValue// "value"
0x73a98  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x73a9d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73aa2  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73aa7  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73aac  pop
0x73aad  ldloc.2
0x73aae  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73ab3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73ab8  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73abd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73ac2  ldstr    aUpdatecommand// "UpdateCommand"
0x73ac7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73acc  ldnull
0x73acd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73ad2  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73ad7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73adc  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73ae1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73ae6  ldstr    aUpdatecommand// "UpdateCommand"
0x73aeb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73af0  ldstr    aConnection// "Connection"
0x73af5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73afa  ldstr    aValue// "value"
0x73aff  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x73b04  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73b09  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73b0e  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73b13  pop
0x73b14  ldarg.0
0x73b15  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x73b1a  callvirt instance class System.Data.Design.SourceCollection System.Data.Design.DesignTable::get_Sources()
0x73b1f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x73b24  ldc.i4.1
0x73b25  add
0x73b26  stloc.3
0x73b27  ldtoken  [mscorlib]System.Int32
0x73b2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73b31  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x73b36  ldstr    aI// "i"
0x73b3b  ldc.i4.0
0x73b3c  box      [mscorlib]System.Int32
0x73b41  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73b46  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x73b4b  stloc.s  4
0x73b4d  ldstr    aI// "i"
0x73b52  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73b57  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73b5c  call     string System.Data.Design.DataComponentNameHandler::get_SelectCmdCollectionPropertyName()
0x73b61  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73b66  ldstr    aLength// "Length"
0x73b6b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73b70  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73b75  stloc.s  5
0x73b77  ldstr    aI// "i"
0x73b7c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73b81  ldstr    aI// "i"
0x73b86  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73b8b  ldc.i4.0
0x73b8c  ldc.i4.1
0x73b8d  box      [mscorlib]System.Int32
0x73b92  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73b97  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::BinOperator(class [System]System.CodeDom.CodeExpression left, valuetype [System]System.CodeDom.CodeBinaryOperatorType op, class [System]System.CodeDom.CodeExpression right)
0x73b9c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73ba1  stloc.s  6
0x73ba3  ldarg.0
0x73ba4  ldfld    class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.DataComponentMethodGenerator::providerFactory
0x73ba9  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbProviderFactory::CreateCommand()
0x73bae  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x73bb3  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x73bb8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73bbd  call     string System.Data.Design.DataComponentNameHandler::get_SelectCmdCollectionPropertyName()
0x73bc2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73bc7  ldstr    aI// "i"
0x73bcc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73bd1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x73bd6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Cast(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression expr)
0x73bdb  ldstr    aConnection// "Connection"
0x73be0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73be5  stloc.s  7
0x73be7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73bec  call     string System.Data.Design.DataComponentNameHandler::get_SelectCmdCollectionPropertyName()
0x73bf1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73bf6  ldstr    aI// "i"
0x73bfb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73c00  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x73c05  stloc.s  8
0x73c07  ldloc.s  8
0x73c09  ldnull
0x73c0a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73c0f  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73c14  ldloc.s  7
0x73c16  ldstr    aValue// "value"
0x73c1b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x73c20  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73c25  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73c2a  stloc.s  9
0x73c2c  ldloc.2
0x73c2d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73c32  ldloc.s  4
0x73c34  ldloc.s  5
0x73c36  ldloc.s  6
0x73c38  ldc.i4.1
0x73c39  newarr   [System]System.CodeDom.CodeStatement
0x73c3e  dup
0x73c3f  ldc.i4.0
0x73c40  ldloc.s  9
0x73c42  stelem.ref
0x73c43  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::ForLoop(class [System]System.CodeDom.CodeStatement initStmt, class [System]System.CodeDom.CodeExpression testExpression, class [System]System.CodeDom.CodeStatement incrementStmt, class [System]System.CodeDom.CodeStatement[] statements)
0x73c48  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73c4d  pop
0x73c4e  ldarg.1
0x73c4f  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x73c54  ldloc.2
0x73c55  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x73c5a  pop
0x73c5b  ret
```
