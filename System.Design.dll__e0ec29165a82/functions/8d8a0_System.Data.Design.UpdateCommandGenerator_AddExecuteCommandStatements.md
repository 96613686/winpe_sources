# System.Data.Design.UpdateCommandGenerator::AddExecuteCommandStatements

- ea: `0x8d8a0`
- end: `0x8dbb2`
- name: `System.Data.Design.UpdateCommandGenerator::AddExecuteCommandStatements`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8d5a0`

## callees

- `0x71e90`
- `0x71f20`
- `0x71f60`
- `0x71fd0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72060`
- `0x72080`
- `0x72090`
- `0x720b0`
- `0x721c0`
- `0x72200`
- `0x72230`
- `0x72270`
- `0x72280`
- `0x72390`
- `0x72500`
- `0x72630`
- `0x74800`
- `0x7cf00`
- `0x7f720`
- `0x7f750`
- `0x81fd0`
- `0x82050`
- `0x82070`
- `0x820b0`
- `0x820f0`
- `0x84c50`
- `0x8d8a0`

## string_xrefs

- `0x8dac6`: `Update`
- `0x8db39`: `Update`
- `0x8db87`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x8d8a0  ldarg.0
0x8d8a1  call     instance valuetype System.Data.Design.MethodTypeEnum System.Data.Design.QueryGeneratorBase::get_MethodType()
0x8d8a6  brtrue   loc_8DA88
0x8d8ab  ldc.i4.1
0x8d8ac  newarr   [System]System.CodeDom.CodeStatement
0x8d8b1  stloc.0
0x8d8b2  ldc.i4.1
0x8d8b3  newarr   [System]System.CodeDom.CodeStatement
0x8d8b8  stloc.1
0x8d8b9  ldarg.1
0x8d8ba  ldtoken  [System.Data]System.Data.ConnectionState
0x8d8bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d8c4  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8d8c9  ldarg.0
0x8d8ca  ldfld    class System.Data.Design.GenericNameHandler System.Data.Design.QueryGeneratorBase::nameHandler
0x8d8cf  ldstr    aPreviousconnec// "previousConnectionState"
0x8d8d4  callvirt instance string System.Data.Design.GenericNameHandler::AddNameToList(string originalName)
0x8d8d9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8d8de  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8d8e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d8e8  ldarg.0
0x8d8e9  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateCommandName()
0x8d8ee  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d8f3  ldstr    aConnection// "Connection"
0x8d8f8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d8fd  ldstr    aState// "State"
0x8d902  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d907  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8d90c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8d911  pop
0x8d912  ldarg.1
0x8d913  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8d918  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8d91d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d922  ldarg.0
0x8d923  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateCommandName()
0x8d928  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d92d  ldstr    aConnection// "Connection"
0x8d932  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d937  ldstr    aState// "State"
0x8d93c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d941  ldtoken  [System.Data]System.Data.ConnectionState
0x8d946  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d94b  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8d950  ldstr    aOpen// "Open"
0x8d955  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8d95a  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::BitwiseAnd(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8d95f  ldtoken  [System.Data]System.Data.ConnectionState
0x8d964  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d969  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8d96e  ldstr    aOpen// "Open"
0x8d973  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8d978  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8d97d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8d982  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8d987  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d98c  ldarg.0
0x8d98d  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateCommandName()
0x8d992  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d997  ldstr    aConnection// "Connection"
0x8d99c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d9a1  ldstr    aOpen// "Open"
0x8d9a6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x8d9ab  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x8d9b0  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x8d9b5  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8d9ba  pop
0x8d9bb  ldloc.0
0x8d9bc  ldc.i4.0
0x8d9bd  ldtoken  [mscorlib]System.Int32
0x8d9c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d9c7  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8d9cc  ldsfld   string System.Data.Design.QueryGeneratorBase::returnVariableName
0x8d9d1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8d9d6  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8d9db  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d9e0  ldarg.0
0x8d9e1  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateCommandName()
0x8d9e6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8d9eb  ldstr    aExecutenonquer// "ExecuteNonQuery"
0x8d9f0  ldc.i4.0
0x8d9f1  newarr   [System]System.CodeDom.CodeExpression
0x8d9f6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8d9fb  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8da00  stelem.ref
0x8da01  ldloc.1
0x8da02  ldc.i4.0
0x8da03  ldarg.0
0x8da04  ldfld    class System.Data.Design.GenericNameHandler System.Data.Design.QueryGeneratorBase::nameHandler
0x8da09  ldstr    aPreviousconnec// "previousConnectionState"
0x8da0e  callvirt instance string System.Data.Design.GenericNameHandler::GetNameFromList(string originalName)
0x8da13  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8da18  ldtoken  [System.Data]System.Data.ConnectionState
0x8da1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8da22  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8da27  ldstr    aClosed// "Closed"
0x8da2c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8da31  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8da36  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8da3b  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8da40  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8da45  ldarg.0
0x8da46  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateCommandName()
0x8da4b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8da50  ldstr    aConnection// "Connection"
0x8da55  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8da5a  ldstr    aClose// "Close"
0x8da5f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x8da64  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x8da69  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x8da6e  stelem.ref
0x8da6f  ldarg.1
0x8da70  ldloc.0
0x8da71  ldc.i4.0
0x8da72  newarr   [System]System.CodeDom.CodeCatchClause
0x8da77  ldloc.1
0x8da78  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Try(class [System]System.CodeDom.CodeStatement[] tryStmnts, class [System]System.CodeDom.CodeCatchClause[] catchClauses, class [System]System.CodeDom.CodeStatement[] finallyStmnts)
0x8da7d  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8da82  pop
0x8da83  br       loc_8DBB0
0x8da88  ldarg.0
0x8da89  call     instance class [System]System.CodeDom.CodeTypeReference System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeReference()
0x8da8e  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x8da93  ldtoken  [System.Data]System.Data.DataRow
0x8da98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8da9d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8daa2  call     bool System.Data.Design.StringUtil::EqualValue(string str1, string str2)
0x8daa7  brfalse.s loc_8DB08
0x8daa9  ldarg.0
0x8daaa  call     instance class [System]System.CodeDom.CodeTypeReference System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeReference()
0x8daaf  callvirt instance int32 [System]System.CodeDom.CodeTypeReference::get_ArrayRank()
0x8dab4  brtrue.s loc_8DB08
0x8dab6  ldarg.1
0x8dab7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8dabc  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8dac1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8dac6  ldstr    aUpdate// "Update"
0x8dacb  ldc.i4.1
0x8dacc  newarr   [System]System.CodeDom.CodeExpression
0x8dad1  dup
0x8dad2  ldc.i4.0
0x8dad3  ldarg.0
0x8dad4  call     instance class [System]System.CodeDom.CodeTypeReference System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeReference()
0x8dad9  ldc.i4.1
0x8dada  newarr   [System]System.CodeDom.CodeExpression
0x8dadf  dup
0x8dae0  ldc.i4.0
0x8dae1  ldarg.0
0x8dae2  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateParameterName()
0x8dae7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8daec  stelem.ref
0x8daed  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::NewArray(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] initializers)
0x8daf2  stelem.ref
0x8daf3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8daf8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8dafd  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8db02  pop
0x8db03  br       loc_8DBB0
0x8db08  ldarg.0
0x8db09  call     instance class [System]System.CodeDom.CodeTypeReference System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeReference()
0x8db0e  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x8db13  ldtoken  [System.Data]System.Data.DataSet
0x8db18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8db1d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8db22  call     bool System.Data.Design.StringUtil::EqualValue(string str1, string str2)
0x8db27  brfalse.s loc_8DB77
0x8db29  ldarg.1
0x8db2a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8db2f  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8db34  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8db39  ldstr    aUpdate// "Update"
0x8db3e  ldc.i4.2
0x8db3f  newarr   [System]System.CodeDom.CodeExpression
0x8db44  dup
0x8db45  ldc.i4.0
0x8db46  ldarg.0
0x8db47  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateParameterName()
0x8db4c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8db51  stelem.ref
0x8db52  dup
0x8db53  ldc.i4.1
0x8db54  ldarg.0
0x8db55  call     instance class System.Data.Design.DesignTable System.Data.Design.QueryGeneratorBase::get_DesignTable()
0x8db5a  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x8db5f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x8db64  stelem.ref
0x8db65  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8db6a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8db6f  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8db74  pop
0x8db75  br.s     loc_8DBB0
0x8db77  ldarg.1
0x8db78  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8db7d  call     string System.Data.Design.DataComponentNameHandler::get_AdapterPropertyName()
0x8db82  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8db87  ldstr    aUpdate// "Update"
0x8db8c  ldc.i4.1
0x8db8d  newarr   [System]System.CodeDom.CodeExpression
0x8db92  dup
0x8db93  ldc.i4.0
0x8db94  ldarg.0
0x8db95  call     instance string System.Data.Design.QueryGeneratorBase::get_UpdateParameterName()
0x8db9a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x8db9f  stelem.ref
0x8dba0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8dba5  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8dbaa  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8dbaf  pop
0x8dbb0  ldc.i4.1
0x8dbb1  ret
```
