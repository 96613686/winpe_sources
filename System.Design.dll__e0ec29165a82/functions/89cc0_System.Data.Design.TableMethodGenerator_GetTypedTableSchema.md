# System.Data.Design.TableMethodGenerator::GetTypedTableSchema

- ea: `0x89cc0`
- end: `0x8a2a6`
- name: `System.Data.Design.TableMethodGenerator::GetTypedTableSchema`
- size: `1510`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x87d60`

## callees

- `0x71ec0`
- `0x71f20`
- `0x71f60`
- `0x71fd0`
- `0x71ff0`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72080`
- `0x72090`
- `0x72270`
- `0x72280`
- `0x722a0`
- `0x72450`
- `0x72500`
- `0x72560`
- `0x76af0`
- `0x7e480`
- `0x8bfc0`

## string_xrefs

- `0x89e1c`: `http://www.w3.org/2001/XMLSchema`
- `0x89f95`: `urn:schemas-microsoft-com:xml-diffgram-v1`

## pseudocode

```c

```

## disassembly

```asm
0x89cc0  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x89cc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89cca  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89ccf  ldstr    aGettypedtables// "GetTypedTableSchema"
0x89cd4  ldc.i4   0x6003
0x89cd9  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x89cde  stloc.0
0x89cdf  ldloc.0
0x89ce0  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x89ce5  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaSet
0x89cea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89cef  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89cf4  ldstr    aXs// "xs"
0x89cf9  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x89cfe  callvirt instance int32 [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::Add(class [System]System.CodeDom.CodeParameterDeclarationExpression)
0x89d03  pop
0x89d04  ldloc.0
0x89d05  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89d0a  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x89d0f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89d14  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89d19  ldstr    aType// "type"
0x89d1e  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x89d23  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89d28  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89d2d  ldc.i4.0
0x89d2e  newarr   [System]System.CodeDom.CodeExpression
0x89d33  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89d38  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x89d3d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89d42  pop
0x89d43  ldloc.0
0x89d44  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89d49  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x89d4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89d53  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89d58  ldstr    aSequence// "sequence"
0x89d5d  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x89d62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89d67  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89d6c  ldc.i4.0
0x89d6d  newarr   [System]System.CodeDom.CodeExpression
0x89d72  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89d77  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x89d7c  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89d81  pop
0x89d82  ldloc.0
0x89d83  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89d88  ldarg.0
0x89d89  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableMethodGenerator::codeGenerator
0x89d8e  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSourceName()
0x89d93  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x89d98  ldstr    aDs// "ds"
0x89d9d  ldarg.0
0x89d9e  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableMethodGenerator::codeGenerator
0x89da3  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSourceName()
0x89da8  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x89dad  ldc.i4.0
0x89dae  newarr   [System]System.CodeDom.CodeExpression
0x89db3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89db8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x89dbd  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89dc2  pop
0x89dc3  ldloc.0
0x89dc4  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89dc9  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAny
0x89dce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89dd3  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89dd8  ldstr    aAny1// "any1"
0x89ddd  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAny
0x89de2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89de7  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89dec  ldc.i4.0
0x89ded  newarr   [System]System.CodeDom.CodeExpression
0x89df2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89df7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x89dfc  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89e01  pop
0x89e02  ldloc.0
0x89e03  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89e08  ldstr    aAny1// "any1"
0x89e0d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89e12  ldstr    aNamespace// "Namespace"
0x89e17  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89e1c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x89e21  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x89e26  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89e2b  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89e30  pop
0x89e31  ldloc.0
0x89e32  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89e37  ldstr    aAny1// "any1"
0x89e3c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89e41  ldstr    aMinoccurs// "MinOccurs"
0x89e46  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89e4b  ldtoken  [mscorlib]System.Decimal
0x89e50  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89e55  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89e5a  ldc.i4.1
0x89e5b  newarr   [System]System.CodeDom.CodeExpression
0x89e60  dup
0x89e61  ldc.i4.0
0x89e62  ldc.i4.0
0x89e63  box      [mscorlib]System.Int32
0x89e68  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x89e6d  stelem.ref
0x89e6e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89e73  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89e78  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89e7d  pop
0x89e7e  ldloc.0
0x89e7f  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89e84  ldstr    aAny1// "any1"
0x89e89  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89e8e  ldstr    aMaxoccurs// "MaxOccurs"
0x89e93  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89e98  ldtoken  [mscorlib]System.Decimal
0x89e9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89ea2  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x89ea7  ldstr    aMaxvalue// "MaxValue"
0x89eac  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x89eb1  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89eb6  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89ebb  pop
0x89ebc  ldloc.0
0x89ebd  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89ec2  ldstr    aAny1// "any1"
0x89ec7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89ecc  ldstr    aProcesscontent// "ProcessContents"
0x89ed1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89ed6  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaContentProcessing
0x89edb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89ee0  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x89ee5  ldstr    aLax// "Lax"
0x89eea  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x89eef  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89ef4  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89ef9  pop
0x89efa  ldloc.0
0x89efb  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89f00  ldstr    aSequence// "sequence"
0x89f05  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89f0a  ldstr    aItems// "Items"
0x89f0f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89f14  ldstr    aAdd// "Add"
0x89f19  ldc.i4.1
0x89f1a  newarr   [System]System.CodeDom.CodeExpression
0x89f1f  dup
0x89f20  ldc.i4.0
0x89f21  ldstr    aAny1// "any1"
0x89f26  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89f2b  stelem.ref
0x89f2c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x89f31  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x89f36  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89f3b  pop
0x89f3c  ldloc.0
0x89f3d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89f42  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAny
0x89f47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89f4c  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89f51  ldstr    aAny2// "any2"
0x89f56  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAny
0x89f5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89f60  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89f65  ldc.i4.0
0x89f66  newarr   [System]System.CodeDom.CodeExpression
0x89f6b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89f70  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x89f75  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89f7a  pop
0x89f7b  ldloc.0
0x89f7c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89f81  ldstr    aAny2// "any2"
0x89f86  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89f8b  ldstr    aNamespace// "Namespace"
0x89f90  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89f95  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xml-diffgram-"...
0x89f9a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x89f9f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89fa4  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89fa9  pop
0x89faa  ldloc.0
0x89fab  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89fb0  ldstr    aAny2// "any2"
0x89fb5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x89fba  ldstr    aMinoccurs// "MinOccurs"
0x89fbf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x89fc4  ldtoken  [mscorlib]System.Decimal
0x89fc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89fce  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x89fd3  ldc.i4.1
0x89fd4  newarr   [System]System.CodeDom.CodeExpression
0x89fd9  dup
0x89fda  ldc.i4.0
0x89fdb  ldc.i4.1
0x89fdc  box      [mscorlib]System.Int32
0x89fe1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x89fe6  stelem.ref
0x89fe7  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x89fec  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x89ff1  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x89ff6  pop
0x89ff7  ldloc.0
0x89ff8  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x89ffd  ldstr    aAny2// "any2"
0x8a002  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a007  ldstr    aProcesscontent// "ProcessContents"
0x8a00c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a011  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaContentProcessing
0x8a016  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a01b  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8a020  ldstr    aLax// "Lax"
0x8a025  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8a02a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8a02f  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a034  pop
0x8a035  ldloc.0
0x8a036  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a03b  ldstr    aSequence// "sequence"
0x8a040  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a045  ldstr    aItems// "Items"
0x8a04a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a04f  ldstr    aAdd// "Add"
0x8a054  ldc.i4.1
0x8a055  newarr   [System]System.CodeDom.CodeExpression
0x8a05a  dup
0x8a05b  ldc.i4.0
0x8a05c  ldstr    aAny2// "any2"
0x8a061  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a066  stelem.ref
0x8a067  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8a06c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x8a071  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a076  pop
0x8a077  ldloc.0
0x8a078  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a07d  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x8a082  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a087  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8a08c  ldstr    aAttribute1// "attribute1"
0x8a091  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x8a096  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a09b  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8a0a0  ldc.i4.0
0x8a0a1  newarr   [System]System.CodeDom.CodeExpression
0x8a0a6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x8a0ab  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8a0b0  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a0b5  pop
0x8a0b6  ldloc.0
0x8a0b7  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a0bc  ldstr    aAttribute1// "attribute1"
0x8a0c1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a0c6  ldstr    aName_1// "Name"
0x8a0cb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a0d0  ldstr    aNamespace_0// "namespace"
0x8a0d5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8a0da  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8a0df  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a0e4  pop
0x8a0e5  ldloc.0
0x8a0e6  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a0eb  ldstr    aAttribute1// "attribute1"
0x8a0f0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a0f5  ldstr    aFixedvalue// "FixedValue"
0x8a0fa  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a0ff  ldstr    aDs// "ds"
0x8a104  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a109  ldstr    aNamespace// "Namespace"
0x8a10e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a113  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x8a118  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a11d  pop
0x8a11e  ldloc.0
0x8a11f  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a124  ldstr    aType// "type"
0x8a129  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a12e  ldstr    aAttributes_0// "Attributes"
0x8a133  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8a138  ldstr    aAdd// "Add"
0x8a13d  ldc.i4.1
0x8a13e  newarr   [System]System.CodeDom.CodeExpression
0x8a143  dup
0x8a144  ldc.i4.0
0x8a145  ldstr    aAttribute1// "attribute1"
0x8a14a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x8a14f  stelem.ref
0x8a150  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x8a155  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x8a15a  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8a15f  pop
0x8a160  ldloc.0
0x8a161  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x8a166  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x8a16b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a170  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8a175  ldstr    aAttribute2// "attribute2"
0x8a17a  ldtoken  [System.Xml]System.Xml.Schema.XmlSchemaAttribute
0x8a17f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
  ... truncated ...
```
