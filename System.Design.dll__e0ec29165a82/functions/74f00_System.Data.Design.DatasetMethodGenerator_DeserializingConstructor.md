# System.Data.Design.DatasetMethodGenerator::DeserializingConstructor

- ea: `0x74f00`
- end: `0x756bf`
- name: `System.Data.Design.DatasetMethodGenerator::DeserializingConstructor`
- size: `1983`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config`

## callers

- `0x74b50`

## callees

- `0x71e90`
- `0x71ea0`
- `0x71ec0`
- `0x71f20`
- `0x71f60`
- `0x71fb0`
- `0x71fc0`
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
- `0x72290`
- `0x722a0`
- `0x72350`
- `0x72380`
- `0x72390`
- `0x72410`
- `0x72500`
- `0x72560`
- `0x74f00`
- `0x7cf00`
- `0x7e480`
- `0x8bfe0`
- `0x8d080`

## string_xrefs

- `0x75167`: `XmlSchema`
- `0x751ef`: `ReadXmlSchema`
- `0x754ca`: `ReadXmlSchema`

## pseudocode

```c

```

## disassembly

```asm
0x74f00  ldc.i4   0x3000
0x74f05  call     class [System]System.CodeDom.CodeConstructor System.Data.Design.CodeGenHelper::Constructor(valuetype [System]System.CodeDom.MemberAttributes attributes)
0x74f0a  stloc.0
0x74f0b  ldloc.0
0x74f0c  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x74f11  ldtoken  [mscorlib]System.Runtime.Serialization.SerializationInfo
0x74f16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74f1b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x74f20  ldstr    aInfo// "info"
0x74f25  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x74f2a  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x74f2f  pop
0x74f30  ldloc.0
0x74f31  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x74f36  ldtoken  [mscorlib]System.Runtime.Serialization.StreamingContext
0x74f3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74f40  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x74f45  ldstr    aContext// "context"
0x74f4a  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x74f4f  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x74f54  pop
0x74f55  ldloc.0
0x74f56  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeConstructor::get_BaseConstructorArgs()
0x74f5b  ldc.i4.3
0x74f5c  newarr   [System]System.CodeDom.CodeExpression
0x74f61  dup
0x74f62  ldc.i4.0
0x74f63  ldstr    aInfo// "info"
0x74f68  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x74f6d  stelem.ref
0x74f6e  dup
0x74f6f  ldc.i4.1
0x74f70  ldstr    aContext// "context"
0x74f75  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x74f7a  stelem.ref
0x74f7b  dup
0x74f7c  ldc.i4.2
0x74f7d  ldc.i4.0
0x74f7e  box      [mscorlib]System.Boolean
0x74f83  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x74f88  stelem.ref
0x74f89  callvirt instance void [System]System.CodeDom.CodeExpressionCollection::AddRange(class [System]System.CodeDom.CodeExpression[])
0x74f8e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::.ctor()
0x74f93  stloc.1
0x74f94  ldloc.1
0x74f95  ldc.i4.4
0x74f96  newarr   [System]System.CodeDom.CodeStatement
0x74f9b  dup
0x74f9c  ldc.i4.0
0x74f9d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x74fa2  ldstr    aInitvars// "InitVars"
0x74fa7  ldc.i4.0
0x74fa8  box      [mscorlib]System.Boolean
0x74fad  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x74fb2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x74fb7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x74fbc  stelem.ref
0x74fbd  dup
0x74fbe  ldc.i4.1
0x74fbf  ldtoken  [System]System.ComponentModel.CollectionChangeEventHandler
0x74fc4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74fc9  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x74fce  ldstr    aSchemachangedh_0// "schemaChangedHandler1"
0x74fd3  ldtoken  [System]System.ComponentModel.CollectionChangeEventHandler
0x74fd8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74fdd  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x74fe2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x74fe7  ldstr    aSchemachanged// "SchemaChanged"
0x74fec  newobj   instance void [System]System.CodeDom.CodeDelegateCreateExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression, string)
0x74ff1  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x74ff6  stelem.ref
0x74ff7  dup
0x74ff8  ldc.i4.2
0x74ff9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x74ffe  ldstr    aTables// "Tables"
0x75003  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75008  ldstr    aCollectionchan// "CollectionChanged"
0x7500d  newobj   instance void [System]System.CodeDom.CodeEventReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x75012  ldstr    aSchemachangedh_0// "schemaChangedHandler1"
0x75017  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x7501c  newobj   instance void [System]System.CodeDom.CodeAttachEventStatement::.ctor(class [System]System.CodeDom.CodeEventReferenceExpression, class [System]System.CodeDom.CodeExpression)
0x75021  stelem.ref
0x75022  dup
0x75023  ldc.i4.3
0x75024  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75029  ldstr    aRelations// "Relations"
0x7502e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75033  ldstr    aCollectionchan// "CollectionChanged"
0x75038  newobj   instance void [System]System.CodeDom.CodeEventReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x7503d  ldstr    aSchemachangedh_0// "schemaChangedHandler1"
0x75042  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75047  newobj   instance void [System]System.CodeDom.CodeAttachEventStatement::.ctor(class [System]System.CodeDom.CodeEventReferenceExpression, class [System]System.CodeDom.CodeExpression)
0x7504c  stelem.ref
0x7504d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x75052  ldarg.0
0x75053  ldfld    class [System]System.CodeDom.CodeMemberMethod System.Data.Design.DatasetMethodGenerator::initExpressionsMethod
0x75058  brfalse.s loc_750C6
0x7505a  ldloc.1
0x7505b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x75060  ldstr    aDetermineschem// "DetermineSchemaSerializationMode"
0x75065  ldc.i4.2
0x75066  newarr   [System]System.CodeDom.CodeExpression
0x7506b  dup
0x7506c  ldc.i4.0
0x7506d  ldstr    aInfo// "info"
0x75072  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x75077  stelem.ref
0x75078  dup
0x75079  ldc.i4.1
0x7507a  ldstr    aContext// "context"
0x7507f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x75084  stelem.ref
0x75085  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x7508a  ldtoken  [System.Data]System.Data.SchemaSerializationMode
0x7508f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75094  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x75099  ldstr    aExcludeschema// "ExcludeSchema"
0x7509e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x750a3  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x750a8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x750ad  ldstr    aInitexpression// "InitExpressions"
0x750b2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName)
0x750b7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x750bc  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x750c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x750c6  ldloc.1
0x750c7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return()
0x750cc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::Add(var<u1>)
0x750d1  ldloc.0
0x750d2  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x750d7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x750dc  ldstr    aIsbinaryserial// "IsBinarySerialized"
0x750e1  ldc.i4.2
0x750e2  newarr   [System]System.CodeDom.CodeExpression
0x750e7  dup
0x750e8  ldc.i4.0
0x750e9  ldstr    aInfo// "info"
0x750ee  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x750f3  stelem.ref
0x750f4  dup
0x750f5  ldc.i4.1
0x750f6  ldstr    aContext// "context"
0x750fb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x75100  stelem.ref
0x75101  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75106  ldc.i4.1
0x75107  box      [mscorlib]System.Boolean
0x7510c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x75111  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x75116  ldloc.1
0x75117  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [System]System.CodeDom.CodeStatement>::ToArray()
0x7511c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x75121  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x75126  pop
0x75127  ldloc.0
0x75128  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x7512d  ldtoken  [mscorlib]System.String
0x75132  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75137  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x7513c  ldstr    aStrschema// "strSchema"
0x75141  ldtoken  [mscorlib]System.String
0x75146  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7514b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75150  ldstr    aInfo// "info"
0x75155  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x7515a  ldstr    aGetvalue// "GetValue"
0x7515f  ldc.i4.2
0x75160  newarr   [System]System.CodeDom.CodeExpression
0x75165  dup
0x75166  ldc.i4.0
0x75167  ldstr    aXmlschema// "XmlSchema"
0x7516c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x75171  stelem.ref
0x75172  dup
0x75173  ldc.i4.1
0x75174  ldtoken  [mscorlib]System.String
0x75179  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7517e  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75183  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::TypeOf(class [System]System.CodeDom.CodeTypeReference type)
0x75188  stelem.ref
0x75189  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x7518e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Cast(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression expr)
0x75193  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x75198  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x7519d  pop
0x7519e  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x751a3  stloc.2
0x751a4  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x751a9  stloc.3
0x751aa  ldloc.2
0x751ab  ldtoken  [System.Data]System.Data.DataSet
0x751b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x751b5  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x751ba  ldstr    aDs// "ds"
0x751bf  ldtoken  [System.Data]System.Data.DataSet
0x751c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x751c9  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x751ce  ldc.i4.0
0x751cf  newarr   [System]System.CodeDom.CodeExpression
0x751d4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x751d9  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x751de  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x751e3  pop
0x751e4  ldloc.2
0x751e5  ldstr    aDs// "ds"
0x751ea  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x751ef  ldstr    aReadxmlschema// "ReadXmlSchema"
0x751f4  ldc.i4.1
0x751f5  newarr   [System]System.CodeDom.CodeExpression
0x751fa  dup
0x751fb  ldc.i4.0
0x751fc  ldtoken  [System.Xml]System.Xml.XmlTextReader
0x75201  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75206  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x7520b  ldc.i4.1
0x7520c  newarr   [System]System.CodeDom.CodeExpression
0x75211  dup
0x75212  ldc.i4.0
0x75213  ldtoken  [mscorlib]System.IO.StringReader
0x75218  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7521d  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x75222  ldc.i4.1
0x75223  newarr   [System]System.CodeDom.CodeExpression
0x75228  dup
0x75229  ldc.i4.0
0x7522a  ldstr    aStrschema// "strSchema"
0x7522f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75234  stelem.ref
0x75235  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x7523a  stelem.ref
0x7523b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x75240  stelem.ref
0x75241  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x75246  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x7524b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75250  pop
0x75251  ldarg.0
0x75252  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DatasetMethodGenerator::codeGenerator
0x75257  callvirt instance class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::get_TableHandler()
0x7525c  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::get_Tables()
0x75261  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x75266  stloc.s  4
0x75268  br       loc_75314
0x7526d  ldloc.s  4
0x7526f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x75274  castclass System.Data.Design.DesignTable
0x75279  stloc.s  5
0x7527b  ldloc.2
0x7527c  ldstr    aDs// "ds"
0x75281  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x75286  ldstr    aTables// "Tables"
0x7528b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x75290  ldloc.s  5
0x75292  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x75297  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x7529c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x752a1  ldnull
0x752a2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x752a7  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x752ac  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Base()
0x752b1  ldstr    aTables// "Tables"
0x752b6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x752bb  ldstr    aAdd// "Add"
0x752c0  ldloc.s  5
0x752c2  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x752c7  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x752cc  ldc.i4.1
0x752cd  newarr   [System]System.CodeDom.CodeExpression
0x752d2  dup
0x752d3  ldc.i4.0
0x752d4  ldstr    aDs// "ds"
0x752d9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x752de  ldstr    aTables// "Tables"
0x752e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x752e8  ldloc.s  5
0x752ea  callvirt instance string System.Data.Design.DesignTable::get_Name()
0x752ef  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x752f4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x752f9  stelem.ref
0x752fa  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x752ff  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x75304  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x75309  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement trueStm)
0x7530e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75313  pop
0x75314  ldloc.s  4
0x75316  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7531b  brtrue   loc_7526D
0x75320  leave.s  loc_75337
0x75322  ldloc.s  4
0x75324  isinst   [mscorlib]System.IDisposable
0x75329  stloc.s  6
0x7532b  ldloc.s  6
0x7532d  brfalse.s loc_75336
0x7532f  ldloc.s  6
0x75331  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75336  endfinally
0x75337  ldloc.2
0x75338  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x7533d  ldstr    aDatasetname// "DataSetName"
  ... truncated ...
```
