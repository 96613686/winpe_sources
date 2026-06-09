# System.Data.Design.DatasetMethodGenerator::InitClassAndInitVarsMethods

- ea: `0x75e80`
- end: `0x7691d`
- name: `System.Data.Design.DatasetMethodGenerator::InitClassAndInitVarsMethods`
- size: `2717`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `installer_update`

## callers

- `0x74b50`

## callees

- `0x71e90`
- `0x71ea0`
- `0x71ec0`
- `0x71f20`
- `0x71f60`
- `0x71fb0`
- `0x71fd0`
- `0x71ff0`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72080`
- `0x720b0`
- `0x720d0`
- `0x72120`
- `0x721c0`
- `0x72200`
- `0x72270`
- `0x722a0`
- `0x72380`
- `0x72390`
- `0x72450`
- `0x724f0`
- `0x72560`
- `0x75e80`
- `0x773f0`
- `0x7a7c0`
- `0x7aa20`
- `0x7b4b0`
- `0x7c320`
- `0x7c370`
- `0x7c4b0`
- `0x7c5d0`
- `0x7c770`
- `0x7cca0`
- `0x7cd00`
- `0x7cf00`
- `0x7e440`
- `0x7e480`
- `0x7e7d0`
- `0x7eac0`
- `0x7ead0`
- `0x84190`
- `0x8bfe0`
- `0x8bff0`
- `0x8d080`

## string_xrefs

- `0x76574`: `DeleteRule`
- `0x765ae`: `UpdateRule`

## pseudocode

```c

```

## disassembly

```asm
0x75e80  ldarg.1
0x75e81  ldtoken  [mscorlib]System.Void
0x75e86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75e8b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75e90  ldstr    aInitclass// "InitClass"
0x75e95  ldc.i4   0x5000
0x75e9a  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x75e9f  stind.ref
0x75ea0  ldarg.2
0x75ea1  ldtoken  [mscorlib]System.Void
0x75ea6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75eab  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75eb0  ldstr    aInitvars// "InitVars"
0x75eb5  ldc.i4   0x1002
0x75eba  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x75ebf  stind.ref
0x75ec0  ldarg.2
0x75ec1  ldind.ref
0x75ec2  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x75ec7  ldtoken  [mscorlib]System.Boolean
0x75ecc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75ed1  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75ed6  ldstr    aInittable// "initTable"
0x75edb  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x75ee0  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x75ee5  pop
0x75ee6  ldarg.1
0x75ee7  ldind.ref
0x75ee8  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x75eed  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75ef2  ldstr    aDatasetname// "DataSetName"
0x75ef7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75efc  ldarg.0
0x75efd  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75f02  callvirt instance string [System.Data]System.Data.DataSet::get_DataSetName()
0x75f07  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75f0c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75f11  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75f16  pop
0x75f17  ldarg.1
0x75f18  ldind.ref
0x75f19  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x75f1e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75f23  ldstr    aPrefix// "Prefix"
0x75f28  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75f2d  ldarg.0
0x75f2e  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75f33  callvirt instance string [System.Data]System.Data.DataSet::get_Prefix()
0x75f38  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75f3d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75f42  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75f47  pop
0x75f48  ldsfld   class [System]System.ComponentModel.PropertyDescriptor System.Data.Design.DatasetMethodGenerator::namespaceProperty
0x75f4d  ldarg.0
0x75f4e  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75f53  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::ShouldSerializeValue(object)
0x75f58  brfalse.s loc_75F8B
0x75f5a  ldarg.1
0x75f5b  ldind.ref
0x75f5c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x75f61  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75f66  ldstr    aNamespace// "Namespace"
0x75f6b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75f70  ldarg.0
0x75f71  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75f76  callvirt instance string [System.Data]System.Data.DataSet::get_Namespace()
0x75f7b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75f80  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75f85  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75f8a  pop
0x75f8b  ldsfld   class [System]System.ComponentModel.PropertyDescriptor System.Data.Design.DatasetMethodGenerator::localeProperty
0x75f90  ldarg.0
0x75f91  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75f96  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::ShouldSerializeValue(object)
0x75f9b  brfalse.s loc_75FF0
0x75f9d  ldarg.1
0x75f9e  ldind.ref
0x75f9f  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x75fa4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75fa9  ldstr    aLocale// "Locale"
0x75fae  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75fb3  ldtoken  [mscorlib]System.Globalization.CultureInfo
0x75fb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75fbd  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75fc2  ldc.i4.1
0x75fc3  newarr   [System]System.CodeDom.CodeExpression
0x75fc8  dup
0x75fc9  ldc.i4.0
0x75fca  ldarg.0
0x75fcb  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75fd0  callvirt instance class [mscorlib]System.Globalization.CultureInfo [System.Data]System.Data.DataSet::get_Locale()
0x75fd5  callvirt instance string [mscorlib]System.Object::ToString()
0x75fda  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75fdf  stelem.ref
0x75fe0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x75fe5  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75fea  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75fef  pop
0x75ff0  ldsfld   class [System]System.ComponentModel.PropertyDescriptor System.Data.Design.DatasetMethodGenerator::caseSensitiveProperty
0x75ff5  ldarg.0
0x75ff6  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x75ffb  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::ShouldSerializeValue(object)
0x76000  brfalse.s loc_76038
0x76002  ldarg.1
0x76003  ldind.ref
0x76004  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x76009  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x7600e  ldstr    aCasesensitive// "CaseSensitive"
0x76013  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76018  ldarg.0
0x76019  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x7601e  callvirt instance bool [System.Data]System.Data.DataSet::get_CaseSensitive()
0x76023  box      [mscorlib]System.Boolean
0x76028  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x7602d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76032  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x76037  pop
0x76038  ldarg.1
0x76039  ldind.ref
0x7603a  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x7603f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x76044  ldstr    aEnforceconstra// "EnforceConstraints"
0x76049  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x7604e  ldarg.0
0x7604f  ldfld    class [System.Data]System.Data.DataSet System.Data.Design.DatasetMethodGenerator::dataSet
0x76054  callvirt instance bool [System.Data]System.Data.DataSet::get_EnforceConstraints()
0x76059  box      [mscorlib]System.Boolean
0x7605e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76063  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76068  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x7606d  pop
0x7606e  ldarg.1
0x7606f  ldind.ref
0x76070  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x76075  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x7607a  ldstr    aSchemaserializ_0// "SchemaSerializationMode"
0x7607f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76084  ldtoken  [System.Data]System.Data.SchemaSerializationMode
0x76089  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7608e  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x76093  ldarg.0
0x76094  ldfld    class System.Data.Design.DesignDataSource System.Data.Design.DatasetMethodGenerator::dataSource
0x76099  callvirt instance valuetype [System.Data]System.Data.SchemaSerializationMode System.Data.Design.DesignDataSource::get_SchemaSerializationMode()
0x7609e  stloc.1
0x7609f  ldloca.s 1
0x760a1  constrained. [System.Data]System.Data.SchemaSerializationMode
0x760a7  callvirt instance string [mscorlib]System.Object::ToString()
0x760ac  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x760b1  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x760b6  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x760bb  pop
0x760bc  ldarg.0
0x760bd  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DatasetMethodGenerator::codeGenerator
0x760c2  callvirt instance class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::get_TableHandler()
0x760c7  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::get_Tables()
0x760cc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x760d1  stloc.2
0x760d2  br       loc_76225
0x760d7  ldloc.2
0x760d8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x760dd  castclass System.Data.Design.DesignTable
0x760e2  stloc.3
0x760e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x760e8  ldloc.3
0x760e9  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableVarName()
0x760ee  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x760f3  stloc.s  4
0x760f5  ldarg.0
0x760f6  ldloc.3
0x760f7  call     instance bool System.Data.Design.DatasetMethodGenerator::TableContainsExpressions(class System.Data.Design.DesignTable designTable)
0x760fc  brfalse.s loc_76138
0x760fe  ldarg.1
0x760ff  ldind.ref
0x76100  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x76105  ldloc.s  4
0x76107  ldloc.3
0x76108  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x7610d  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x76112  ldc.i4.1
0x76113  newarr   [System]System.CodeDom.CodeExpression
0x76118  dup
0x76119  ldc.i4.0
0x7611a  ldc.i4.0
0x7611b  box      [mscorlib]System.Boolean
0x76120  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76125  stelem.ref
0x76126  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x7612b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76130  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x76135  pop
0x76136  br.s     loc_76162
0x76138  ldarg.1
0x76139  ldind.ref
0x7613a  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x7613f  ldloc.s  4
0x76141  ldloc.3
0x76142  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x76147  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x7614c  ldc.i4.0
0x7614d  newarr   [System]System.CodeDom.CodeExpression
0x76152  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x76157  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x7615c  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x76161  pop
0x76162  ldarg.1
0x76163  ldind.ref
0x76164  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x76169  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Base()
0x7616e  ldstr    aTables// "Tables"
0x76173  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76178  ldstr    aAdd// "Add"
0x7617d  ldloc.s  4
0x7617f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x76184  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeExpression)
0x76189  pop
0x7618a  ldarg.2
0x7618b  ldind.ref
0x7618c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x76191  ldloc.s  4
0x76193  ldloc.3
0x76194  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x76199  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x7619e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Base()
0x761a3  ldstr    aTables// "Tables"
0x761a8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x761ad  ldloc.3
0x761ae  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x761b3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x761b8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x761bd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Cast(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression expr)
0x761c2  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x761c7  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x761cc  pop
0x761cd  ldarg.2
0x761ce  ldind.ref
0x761cf  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x761d4  ldstr    aInittable// "initTable"
0x761d9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x761de  ldc.i4.1
0x761df  box      [mscorlib]System.Boolean
0x761e4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x761e9  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x761ee  ldc.i4.1
0x761ef  newarr   [System]System.CodeDom.CodeStatement
0x761f4  dup
0x761f5  ldc.i4.0
0x761f6  ldloc.s  4
0x761f8  ldnull
0x761f9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x761fe  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76203  ldloc.s  4
0x76205  ldstr    aInitvars// "InitVars"
0x7620a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x7620f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76214  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x76219  stelem.ref
0x7621a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x7621f  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x76224  pop
0x76225  ldloc.2
0x76226  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7622b  brtrue   loc_760D7
0x76230  leave.s  loc_76246
0x76232  ldloc.2
0x76233  isinst   [mscorlib]System.IDisposable
0x76238  stloc.s  5
0x7623a  ldloc.s  5
0x7623c  brfalse.s loc_76245
0x7623e  ldloc.s  5
0x76240  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76245  endfinally
0x76246  ldnull
0x76247  stloc.0
0x76248  ldarg.0
0x76249  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DatasetMethodGenerator::codeGenerator
0x7624e  callvirt instance class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::get_TableHandler()
0x76253  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::get_Tables()
0x76258  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x7625d  stloc.s  6
0x7625f  br       loc_76603
0x76264  ldloc.s  6
0x76266  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7626b  castclass System.Data.Design.DesignTable
0x76270  stloc.s  7
0x76272  ldloc.s  7
0x76274  callvirt instance class [System.Data]System.Data.DataTable System.Data.Design.DesignTable::get_DataTable()
0x76279  stloc.s  8
0x7627b  ldloc.s  8
0x7627d  callvirt instance class [System.Data]System.Data.ConstraintCollection [System.Data]System.Data.DataTable::get_Constraints()
0x76282  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.InternalDataCollectionBase::GetEnumerator()
0x76287  stloc.s  9
0x76289  br       loc_765E0
0x7628e  ldloc.s  9
0x76290  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x76295  castclass [System.Data]System.Data.Constraint
0x7629a  stloc.s  0xA
0x7629c  ldloc.s  0xA
0x7629e  isinst   [System.Data]System.Data.ForeignKeyConstraint
0x762a3  brfalse  loc_765E0
0x762a8  ldloc.s  0xA
  ... truncated ...
```
