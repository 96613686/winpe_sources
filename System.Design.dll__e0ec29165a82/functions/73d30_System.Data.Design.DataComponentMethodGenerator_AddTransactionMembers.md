# System.Data.Design.DataComponentMethodGenerator::AddTransactionMembers

- ea: `0x73d30`
- end: `0x73fdc`
- name: `System.Data.Design.DataComponentMethodGenerator::AddTransactionMembers`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x73230`

## callees

- `0x71e90`
- `0x71ed0`
- `0x71f20`
- `0x71fd0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72070`
- `0x72120`
- `0x721b0`
- `0x721c0`
- `0x72240`
- `0x72260`
- `0x72280`
- `0x722a0`
- `0x72390`
- `0x723b0`
- `0x724a0`
- `0x72500`
- `0x72510`
- `0x73d30`
- `0x73fe0`
- `0x74800`
- `0x74830`
- `0x74870`
- `0x74880`
- `0x7e6e0`
- `0x10d770`

## string_xrefs

- `0x73ec8`: `DeleteCommand`
- `0x73f20`: `InsertCommand`
- `0x73f78`: `UpdateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x73d30  ldarg.0
0x73d31  ldfld    class System.Data.Design.DesignTable System.Data.Design.DataComponentMethodGenerator::designTable
0x73d36  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x73d3b  callvirt instance class [mscorlib]System.Type CodeGenPropertyCache::get_TransactionType()
0x73d40  stloc.0
0x73d41  ldloc.0
0x73d42  ldnull
0x73d43  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x73d48  brfalse.s loc_73D4B
0x73d4a  ret
0x73d4b  ldloc.0
0x73d4c  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x73d51  stloc.1
0x73d52  ldarg.1
0x73d53  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x73d58  ldloc.1
0x73d59  call     string System.Data.Design.DataComponentNameHandler::get_TransactionVariableName()
0x73d5e  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x73d63  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x73d68  pop
0x73d69  ldloc.1
0x73d6a  call     string System.Data.Design.DataComponentNameHandler::get_TransactionPropertyName()
0x73d6f  ldc.i4   0x1002
0x73d74  call     class [System]System.CodeDom.CodeMemberProperty System.Data.Design.CodeGenHelper::PropertyDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x73d79  stloc.2
0x73d7a  ldloc.2
0x73d7b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x73d80  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73d85  call     string System.Data.Design.DataComponentNameHandler::get_TransactionVariableName()
0x73d8a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x73d8f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x73d94  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73d99  pop
0x73d9a  ldloc.2
0x73d9b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73da0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73da5  call     string System.Data.Design.DataComponentNameHandler::get_TransactionVariableName()
0x73daa  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x73daf  ldstr    aValue// "value"
0x73db4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x73db9  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73dbe  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73dc3  pop
0x73dc4  ldtoken  [mscorlib]System.Int32
0x73dc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73dce  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(class [mscorlib]System.Type type)
0x73dd3  ldstr    aI// "i"
0x73dd8  ldc.i4.0
0x73dd9  box      [mscorlib]System.Int32
0x73dde  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73de3  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x73de8  stloc.3
0x73de9  ldstr    aI// "i"
0x73dee  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73df3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73df8  call     string System.Data.Design.DataComponentNameHandler::get_SelectCmdCollectionPropertyName()
0x73dfd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73e02  ldstr    aLength// "Length"
0x73e07  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73e0c  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73e11  stloc.s  4
0x73e13  ldstr    aI// "i"
0x73e18  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73e1d  ldstr    aI// "i"
0x73e22  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73e27  ldc.i4.0
0x73e28  ldc.i4.1
0x73e29  box      [mscorlib]System.Int32
0x73e2e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73e33  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::BinOperator(class [System]System.CodeDom.CodeExpression left, valuetype [System]System.CodeDom.CodeBinaryOperatorType op, class [System]System.CodeDom.CodeExpression right)
0x73e38  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73e3d  stloc.s  5
0x73e3f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73e44  call     string System.Data.Design.DataComponentNameHandler::get_SelectCmdCollectionPropertyName()
0x73e49  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73e4e  ldstr    aI// "i"
0x73e53  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73e58  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x73e5d  ldstr    aTransaction// "Transaction"
0x73e62  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73e67  stloc.s  6
0x73e69  ldstr    aOldtransaction// "oldTransaction"
0x73e6e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x73e73  stloc.s  7
0x73e75  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73e7a  call     string System.Data.Design.DataComponentNameHandler::get_TransactionVariableName()
0x73e7f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x73e84  stloc.s  8
0x73e86  ldarg.0
0x73e87  ldloc.s  6
0x73e89  ldloc.s  7
0x73e8b  ldloc.s  8
0x73e8d  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.DataComponentMethodGenerator::GenerateSetTransactionStmt(class [System]System.CodeDom.CodeExpression transaction, class [System]System.CodeDom.CodeExpression oldTransaction, class [System]System.CodeDom.CodeExpression newTransaction)
0x73e92  stloc.s  9
0x73e94  ldloc.2
0x73e95  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73e9a  ldloc.3
0x73e9b  ldloc.s  4
0x73e9d  ldloc.s  5
0x73e9f  ldc.i4.1
0x73ea0  newarr   [System]System.CodeDom.CodeStatement
0x73ea5  dup
0x73ea6  ldc.i4.0
0x73ea7  ldloc.s  9
0x73ea9  stelem.ref
0x73eaa  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::ForLoop(class [System]System.CodeDom.CodeStatement initStmt, class [System]System.CodeDom.CodeExpression testExpression, class [System]System.CodeDom.CodeStatement incrementStmt, class [System]System.CodeDom.CodeStatement[] statements)
0x73eaf  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73eb4  pop
0x73eb5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x73eba  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x73ebf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73ec4  stloc.s  0xA
0x73ec6  ldloc.s  0xA
0x73ec8  ldstr    aDeletecommand// "DeleteCommand"
0x73ecd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73ed2  stloc.s  0xB
0x73ed4  ldloc.s  0xB
0x73ed6  ldstr    aTransaction// "Transaction"
0x73edb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73ee0  stloc.s  6
0x73ee2  ldloc.2
0x73ee3  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73ee8  ldloc.s  0xA
0x73eea  ldnull
0x73eeb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73ef0  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73ef5  ldloc.s  0xB
0x73ef7  ldnull
0x73ef8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73efd  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73f02  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73f07  ldarg.0
0x73f08  ldloc.s  6
0x73f0a  ldloc.s  7
0x73f0c  ldloc.s  8
0x73f0e  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.DataComponentMethodGenerator::GenerateSetTransactionStmt(class [System]System.CodeDom.CodeExpression transaction, class [System]System.CodeDom.CodeExpression oldTransaction, class [System]System.CodeDom.CodeExpression newTransaction)
0x73f13  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73f18  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73f1d  pop
0x73f1e  ldloc.s  0xA
0x73f20  ldstr    aInsertcommand// "InsertCommand"
0x73f25  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73f2a  stloc.s  0xB
0x73f2c  ldloc.s  0xB
0x73f2e  ldstr    aTransaction// "Transaction"
0x73f33  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73f38  stloc.s  6
0x73f3a  ldloc.2
0x73f3b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73f40  ldloc.s  0xA
0x73f42  ldnull
0x73f43  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73f48  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73f4d  ldloc.s  0xB
0x73f4f  ldnull
0x73f50  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73f55  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73f5a  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73f5f  ldarg.0
0x73f60  ldloc.s  6
0x73f62  ldloc.s  7
0x73f64  ldloc.s  8
0x73f66  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.DataComponentMethodGenerator::GenerateSetTransactionStmt(class [System]System.CodeDom.CodeExpression transaction, class [System]System.CodeDom.CodeExpression oldTransaction, class [System]System.CodeDom.CodeExpression newTransaction)
0x73f6b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73f70  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73f75  pop
0x73f76  ldloc.s  0xA
0x73f78  ldstr    aUpdatecommand// "UpdateCommand"
0x73f7d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73f82  stloc.s  0xB
0x73f84  ldloc.s  0xB
0x73f86  ldstr    aTransaction// "Transaction"
0x73f8b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x73f90  stloc.s  6
0x73f92  ldloc.2
0x73f93  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x73f98  ldloc.s  0xA
0x73f9a  ldnull
0x73f9b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73fa0  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73fa5  ldloc.s  0xB
0x73fa7  ldnull
0x73fa8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73fad  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73fb2  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x73fb7  ldarg.0
0x73fb8  ldloc.s  6
0x73fba  ldloc.s  7
0x73fbc  ldloc.s  8
0x73fbe  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.DataComponentMethodGenerator::GenerateSetTransactionStmt(class [System]System.CodeDom.CodeExpression transaction, class [System]System.CodeDom.CodeExpression oldTransaction, class [System]System.CodeDom.CodeExpression newTransaction)
0x73fc3  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x73fc8  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x73fcd  pop
0x73fce  ldarg.1
0x73fcf  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x73fd4  ldloc.2
0x73fd5  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x73fda  pop
0x73fdb  ret
```
