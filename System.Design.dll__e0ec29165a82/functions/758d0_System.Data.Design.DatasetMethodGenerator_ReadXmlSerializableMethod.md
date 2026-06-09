# System.Data.Design.DatasetMethodGenerator::ReadXmlSerializableMethod

- ea: `0x758d0`
- end: `0x75ce3`
- name: `System.Data.Design.DatasetMethodGenerator::ReadXmlSerializableMethod`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x74b50`

## callees

- `0x71e90`
- `0x71ea0`
- `0x71ec0`
- `0x71f20`
- `0x71f60`
- `0x71fd0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72080`
- `0x72090`
- `0x720b0`
- `0x720d0`
- `0x72120`
- `0x721c0`
- `0x72200`
- `0x72270`
- `0x722a0`
- `0x72350`
- `0x72390`
- `0x72450`
- `0x72500`
- `0x72560`
- `0x758d0`
- `0x7cf00`
- `0x7e480`
- `0x8bfe0`
- `0x8d080`

## string_xrefs

- `0x758df`: `ReadXmlSerializable`
- `0x75904`: `reader`
- `0x75993`: `reader`
- `0x75c30`: `reader`
- `0x75c7e`: `reader`
- `0x75986`: `ReadXml`
- `0x75c23`: `ReadXml`

## pseudocode

```c

```

## disassembly

```asm
0x758d0  ldtoken  [mscorlib]System.Void
0x758d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x758da  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x758df  ldstr    aReadxmlseriali// "ReadXmlSerializable"
0x758e4  ldc.i4   0x3004
0x758e9  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x758ee  stloc.0
0x758ef  ldloc.0
0x758f0  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x758f5  ldtoken  [System.Xml]System.Xml.XmlReader
0x758fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x758ff  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75904  ldstr    aReader// "reader"
0x75909  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x7590e  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x75913  pop
0x75914  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x75919  stloc.1
0x7591a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x7591f  stloc.2
0x75920  ldloc.1
0x75921  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75926  ldstr    aReset// "Reset"
0x7592b  ldc.i4.0
0x7592c  newarr   [System]System.CodeDom.CodeExpression
0x75931  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75936  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x7593b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75940  pop
0x75941  ldloc.1
0x75942  ldtoken  [System.Data]System.Data.DataSet
0x75947  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7594c  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75951  ldstr    aDs// "ds"
0x75956  ldtoken  [System.Data]System.Data.DataSet
0x7595b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75960  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75965  ldc.i4.0
0x75966  newarr   [System]System.CodeDom.CodeExpression
0x7596b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x75970  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x75975  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7597a  pop
0x7597b  ldloc.1
0x7597c  ldstr    aDs// "ds"
0x75981  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75986  ldstr    aReadxml// "ReadXml"
0x7598b  ldc.i4.1
0x7598c  newarr   [System]System.CodeDom.CodeExpression
0x75991  dup
0x75992  ldc.i4.0
0x75993  ldstr    aReader// "reader"
0x75998  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x7599d  stelem.ref
0x7599e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x759a3  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x759a8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x759ad  pop
0x759ae  ldarg.0
0x759af  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DatasetMethodGenerator::codeGenerator
0x759b4  callvirt instance class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::get_TableHandler()
0x759b9  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::get_Tables()
0x759be  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x759c3  stloc.3
0x759c4  br       loc_75A6F
0x759c9  ldloc.3
0x759ca  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x759cf  castclass System.Data.Design.DesignTable
0x759d4  stloc.s  4
0x759d6  ldloc.1
0x759d7  ldstr    aDs// "ds"
0x759dc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x759e1  ldstr    aTables// "Tables"
0x759e6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x759eb  ldloc.s  4
0x759ed  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x759f2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x759f7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x759fc  ldnull
0x759fd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x75a02  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75a07  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Base()
0x75a0c  ldstr    aTables// "Tables"
0x75a11  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75a16  ldstr    aAdd// "Add"
0x75a1b  ldloc.s  4
0x75a1d  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x75a22  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x75a27  ldc.i4.1
0x75a28  newarr   [System]System.CodeDom.CodeExpression
0x75a2d  dup
0x75a2e  ldc.i4.0
0x75a2f  ldstr    aDs// "ds"
0x75a34  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75a39  ldstr    aTables// "Tables"
0x75a3e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75a43  ldloc.s  4
0x75a45  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x75a4a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75a4f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x75a54  stelem.ref
0x75a55  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x75a5a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x75a5f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75a64  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x75a69  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75a6e  pop
0x75a6f  ldloc.3
0x75a70  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x75a75  brtrue   loc_759C9
0x75a7a  leave.s  loc_75A90
0x75a7c  ldloc.3
0x75a7d  isinst   [mscorlib]System.IDisposable
0x75a82  stloc.s  5
0x75a84  ldloc.s  5
0x75a86  brfalse.s loc_75A8F
0x75a88  ldloc.s  5
0x75a8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75a8f  endfinally
0x75a90  ldloc.1
0x75a91  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75a96  ldstr    aDatasetname// "DataSetName"
0x75a9b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75aa0  ldstr    aDs// "ds"
0x75aa5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75aaa  ldstr    aDatasetname// "DataSetName"
0x75aaf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75ab4  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75ab9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75abe  pop
0x75abf  ldloc.1
0x75ac0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75ac5  ldstr    aPrefix// "Prefix"
0x75aca  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75acf  ldstr    aDs// "ds"
0x75ad4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75ad9  ldstr    aPrefix// "Prefix"
0x75ade  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75ae3  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75ae8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75aed  pop
0x75aee  ldloc.1
0x75aef  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75af4  ldstr    aNamespace// "Namespace"
0x75af9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75afe  ldstr    aDs// "ds"
0x75b03  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75b08  ldstr    aNamespace// "Namespace"
0x75b0d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b12  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75b17  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75b1c  pop
0x75b1d  ldloc.1
0x75b1e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75b23  ldstr    aLocale// "Locale"
0x75b28  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b2d  ldstr    aDs// "ds"
0x75b32  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75b37  ldstr    aLocale// "Locale"
0x75b3c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b41  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75b46  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75b4b  pop
0x75b4c  ldloc.1
0x75b4d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75b52  ldstr    aCasesensitive// "CaseSensitive"
0x75b57  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b5c  ldstr    aDs// "ds"
0x75b61  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75b66  ldstr    aCasesensitive// "CaseSensitive"
0x75b6b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b70  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75b75  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75b7a  pop
0x75b7b  ldloc.1
0x75b7c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75b81  ldstr    aEnforceconstra// "EnforceConstraints"
0x75b86  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b8b  ldstr    aDs// "ds"
0x75b90  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75b95  ldstr    aEnforceconstra// "EnforceConstraints"
0x75b9a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75b9f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75ba4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75ba9  pop
0x75baa  ldloc.1
0x75bab  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75bb0  ldstr    aMerge// "Merge"
0x75bb5  ldc.i4.3
0x75bb6  newarr   [System]System.CodeDom.CodeExpression
0x75bbb  dup
0x75bbc  ldc.i4.0
0x75bbd  ldstr    aDs// "ds"
0x75bc2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75bc7  stelem.ref
0x75bc8  dup
0x75bc9  ldc.i4.1
0x75bca  ldc.i4.0
0x75bcb  box      [mscorlib]System.Boolean
0x75bd0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x75bd5  stelem.ref
0x75bd6  dup
0x75bd7  ldc.i4.2
0x75bd8  ldtoken  [System.Data]System.Data.MissingSchemaAction
0x75bdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75be2  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x75be7  ldstr    aAdd// "Add"
0x75bec  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x75bf1  stelem.ref
0x75bf2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75bf7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75bfc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75c01  pop
0x75c02  ldloc.1
0x75c03  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75c08  ldstr    aInitvars// "InitVars"
0x75c0d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x75c12  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75c17  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75c1c  pop
0x75c1d  ldloc.2
0x75c1e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75c23  ldstr    aReadxml// "ReadXml"
0x75c28  ldc.i4.1
0x75c29  newarr   [System]System.CodeDom.CodeExpression
0x75c2e  dup
0x75c2f  ldc.i4.0
0x75c30  ldstr    aReader// "reader"
0x75c35  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x75c3a  stelem.ref
0x75c3b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75c40  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75c45  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75c4a  pop
0x75c4b  ldloc.2
0x75c4c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75c51  ldstr    aInitvars// "InitVars"
0x75c56  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x75c5b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75c60  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75c65  pop
0x75c66  ldloc.0
0x75c67  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x75c6c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75c71  ldstr    aDetermineschem// "DetermineSchemaSerializationMode"
0x75c76  ldc.i4.1
0x75c77  newarr   [System]System.CodeDom.CodeExpression
0x75c7c  dup
0x75c7d  ldc.i4.0
0x75c7e  ldstr    aReader// "reader"
0x75c83  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x75c88  stelem.ref
0x75c89  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75c8e  ldtoken  [System.Data]System.Data.SchemaSerializationMode
0x75c93  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75c98  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x75c9d  ldstr    aIncludeschema// "IncludeSchema"
0x75ca2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x75ca7  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75cac  ldloc.1
0x75cad  ldtoken  [System]System.CodeDom.CodeStatement
0x75cb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75cb7  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x75cbc  castclass class [System]System.CodeDom.CodeStatement[]
0x75cc1  ldloc.2
0x75cc2  ldtoken  [System]System.CodeDom.CodeStatement
0x75cc7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75ccc  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x75cd1  castclass class [System]System.CodeDom.CodeStatement[]
0x75cd6  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms, class [System]System.CodeDom.CodeStatement[] falseStms)
0x75cdb  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75ce0  pop
0x75ce1  ldloc.0
0x75ce2  ret
```
