# System.Data.Design.DatasetMethodGenerator::GetSchemaIsInCollection

- ea: `0x76af0`
- end: `0x76fa6`
- name: `System.Data.Design.DatasetMethodGenerator::GetSchemaIsInCollection`
- size: `1206`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x76fb0`
- `0x89cc0`

## callees

- `0x71f20`
- `0x71fb0`
- `0x71ff0`
- `0x72010`
- `0x72020`
- `0x72040`
- `0x72070`
- `0x72090`
- `0x721c0`
- `0x72200`
- `0x72240`
- `0x72270`
- `0x72280`
- `0x722a0`
- `0x72380`
- `0x72500`
- `0x72510`
- `0x72630`

## string_xrefs

- `0x76b8c`: `ReadByte`
- `0x76ba6`: `ReadByte`
- `0x76cb7`: `Write`
- `0x76d45`: `Write`
- `0x76dca`: `MoveNext`

## pseudocode

```c

```

## disassembly

```asm
0x76af0  ldc.i4.4
0x76af1  newarr   [System]System.CodeDom.CodeStatement
0x76af6  dup
0x76af7  ldc.i4.0
0x76af8  ldstr    aS1// "s1"
0x76afd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76b02  ldstr    aPosition// "Position"
0x76b07  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76b0c  ldc.i4.0
0x76b0d  box      [mscorlib]System.Int32
0x76b12  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76b17  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76b1c  stelem.ref
0x76b1d  dup
0x76b1e  ldc.i4.1
0x76b1f  ldstr    aS2// "s2"
0x76b24  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76b29  ldstr    aPosition// "Position"
0x76b2e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76b33  ldc.i4.0
0x76b34  box      [mscorlib]System.Int32
0x76b39  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76b3e  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76b43  stelem.ref
0x76b44  dup
0x76b45  ldc.i4.2
0x76b46  ldstr    asc_12DF92// ""
0x76b4b  newobj   instance void [System]System.CodeDom.CodeSnippetExpression::.ctor(string)
0x76b50  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76b55  ldstr    aS1// "s1"
0x76b5a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76b5f  ldstr    aPosition// "Position"
0x76b64  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76b69  ldstr    aS1// "s1"
0x76b6e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76b73  ldstr    aLength// "Length"
0x76b78  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76b7d  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76b82  ldstr    aS1// "s1"
0x76b87  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76b8c  ldstr    aReadbyte// "ReadByte"
0x76b91  ldc.i4.0
0x76b92  newarr   [System]System.CodeDom.CodeExpression
0x76b97  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76b9c  ldstr    aS2// "s2"
0x76ba1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76ba6  ldstr    aReadbyte// "ReadByte"
0x76bab  ldc.i4.0
0x76bac  newarr   [System]System.CodeDom.CodeExpression
0x76bb1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76bb6  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76bbb  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::And(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76bc0  ldstr    asc_12DF92// ""
0x76bc5  newobj   instance void [System]System.CodeDom.CodeSnippetExpression::.ctor(string)
0x76bca  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76bcf  ldc.i4.1
0x76bd0  newarr   [System]System.CodeDom.CodeStatement
0x76bd5  dup
0x76bd6  ldc.i4.0
0x76bd7  ldstr    asc_12DF92// ""
0x76bdc  newobj   instance void [System]System.CodeDom.CodeSnippetExpression::.ctor(string)
0x76be1  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76be6  stelem.ref
0x76be7  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::ForLoop(class [System]System.CodeDom.CodeStatement initStmt, class [System]System.CodeDom.CodeExpression testExpression, class [System]System.CodeDom.CodeStatement incrementStmt, class [System]System.CodeDom.CodeStatement[] statements)
0x76bec  stelem.ref
0x76bed  dup
0x76bee  ldc.i4.3
0x76bef  ldstr    aS1// "s1"
0x76bf4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76bf9  ldstr    aPosition// "Position"
0x76bfe  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76c03  ldstr    aS1// "s1"
0x76c08  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76c0d  ldstr    aLength// "Length"
0x76c12  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76c17  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76c1c  ldc.i4.1
0x76c1d  newarr   [System]System.CodeDom.CodeStatement
0x76c22  dup
0x76c23  ldc.i4.0
0x76c24  ldstr    aType// "type"
0x76c29  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76c2e  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x76c33  stelem.ref
0x76c34  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x76c39  stelem.ref
0x76c3a  stloc.0
0x76c3b  ldc.i4.4
0x76c3c  newarr   [System]System.CodeDom.CodeStatement
0x76c41  dup
0x76c42  ldc.i4.0
0x76c43  ldstr    aSchema// "schema"
0x76c48  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76c4d  ldtoken  [System.Xml]System.Xml.Schema.XmlSchema
0x76c52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76c57  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76c5c  ldstr    aSchemas// "schemas"
0x76c61  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76c66  ldstr    aCurrent// "Current"
0x76c6b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76c70  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Cast(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression expr)
0x76c75  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76c7a  stelem.ref
0x76c7b  dup
0x76c7c  ldc.i4.1
0x76c7d  ldstr    aS2// "s2"
0x76c82  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76c87  ldstr    aSetlength// "SetLength"
0x76c8c  ldc.i4.1
0x76c8d  newarr   [System]System.CodeDom.CodeExpression
0x76c92  dup
0x76c93  ldc.i4.0
0x76c94  ldc.i4.0
0x76c95  box      [mscorlib]System.Int32
0x76c9a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76c9f  stelem.ref
0x76ca0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76ca5  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76caa  stelem.ref
0x76cab  dup
0x76cac  ldc.i4.2
0x76cad  ldstr    aSchema// "schema"
0x76cb2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76cb7  ldstr    aWrite// "Write"
0x76cbc  ldc.i4.1
0x76cbd  newarr   [System]System.CodeDom.CodeExpression
0x76cc2  dup
0x76cc3  ldc.i4.0
0x76cc4  ldstr    aS2// "s2"
0x76cc9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76cce  stelem.ref
0x76ccf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76cd4  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76cd9  stelem.ref
0x76cda  dup
0x76cdb  ldc.i4.3
0x76cdc  ldstr    aS1// "s1"
0x76ce1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76ce6  ldstr    aLength// "Length"
0x76ceb  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76cf0  ldstr    aS2// "s2"
0x76cf5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76cfa  ldstr    aLength// "Length"
0x76cff  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76d04  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::EQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76d09  ldloc.0
0x76d0a  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x76d0f  stelem.ref
0x76d10  stloc.1
0x76d11  ldc.i4.3
0x76d12  newarr   [System]System.CodeDom.CodeStatement
0x76d17  dup
0x76d18  ldc.i4.0
0x76d19  ldtoken  [System.Xml]System.Xml.Schema.XmlSchema
0x76d1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76d23  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76d28  ldstr    aSchema// "schema"
0x76d2d  ldnull
0x76d2e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76d33  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x76d38  stelem.ref
0x76d39  dup
0x76d3a  ldc.i4.1
0x76d3b  ldstr    aDsschema// "dsSchema"
0x76d40  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76d45  ldstr    aWrite// "Write"
0x76d4a  ldc.i4.1
0x76d4b  newarr   [System]System.CodeDom.CodeExpression
0x76d50  dup
0x76d51  ldc.i4.0
0x76d52  ldstr    aS1// "s1"
0x76d57  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76d5c  stelem.ref
0x76d5d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76d62  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76d67  stelem.ref
0x76d68  dup
0x76d69  ldc.i4.2
0x76d6a  ldtoken  [mscorlib]System.Collections.IEnumerator
0x76d6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76d74  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76d79  ldstr    aSchemas// "schemas"
0x76d7e  ldarg.2
0x76d7f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76d84  ldstr    aSchemas_0// "Schemas"
0x76d89  ldc.i4.1
0x76d8a  newarr   [System]System.CodeDom.CodeExpression
0x76d8f  dup
0x76d90  ldc.i4.0
0x76d91  ldstr    aDsschema// "dsSchema"
0x76d96  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76d9b  ldstr    aTargetnamespac// "TargetNamespace"
0x76da0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x76da5  stelem.ref
0x76da6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76dab  ldstr    aGetenumerator// "GetEnumerator"
0x76db0  ldc.i4.0
0x76db1  newarr   [System]System.CodeDom.CodeExpression
0x76db6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76dbb  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x76dc0  ldstr    aSchemas// "schemas"
0x76dc5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76dca  ldstr    aMovenext// "MoveNext"
0x76dcf  ldc.i4.0
0x76dd0  newarr   [System]System.CodeDom.CodeExpression
0x76dd5  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76dda  ldstr    asc_12DF92// ""
0x76ddf  newobj   instance void [System]System.CodeDom.CodeSnippetExpression::.ctor(string)
0x76de4  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76de9  ldloc.1
0x76dea  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::ForLoop(class [System]System.CodeDom.CodeStatement initStmt, class [System]System.CodeDom.CodeExpression testExpression, class [System]System.CodeDom.CodeStatement incrementStmt, class [System]System.CodeDom.CodeStatement[] statements)
0x76def  stelem.ref
0x76df0  stloc.2
0x76df1  ldc.i4.2
0x76df2  newarr   [System]System.CodeDom.CodeStatement
0x76df7  dup
0x76df8  ldc.i4.0
0x76df9  ldstr    aS1// "s1"
0x76dfe  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76e03  ldnull
0x76e04  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76e09  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76e0e  ldc.i4.1
0x76e0f  newarr   [System]System.CodeDom.CodeStatement
0x76e14  dup
0x76e15  ldc.i4.0
0x76e16  ldstr    aS1// "s1"
0x76e1b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76e20  ldstr    aClose// "Close"
0x76e25  ldc.i4.0
0x76e26  newarr   [System]System.CodeDom.CodeExpression
0x76e2b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76e30  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76e35  stelem.ref
0x76e36  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x76e3b  stelem.ref
0x76e3c  dup
0x76e3d  ldc.i4.1
0x76e3e  ldstr    aS2// "s2"
0x76e43  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76e48  ldnull
0x76e49  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x76e4e  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::IdNotEQ(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x76e53  ldc.i4.1
0x76e54  newarr   [System]System.CodeDom.CodeStatement
0x76e59  dup
0x76e5a  ldc.i4.0
0x76e5b  ldstr    aS2// "s2"
0x76e60  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x76e65  ldstr    aClose// "Close"
0x76e6a  ldc.i4.0
0x76e6b  newarr   [System]System.CodeDom.CodeExpression
0x76e70  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression[] parameters)
0x76e75  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x76e7a  stelem.ref
0x76e7b  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x76e80  stelem.ref
0x76e81  stloc.3
0x76e82  ldc.i4.3
0x76e83  newarr   [System]System.CodeDom.CodeStatement
0x76e88  dup
0x76e89  ldc.i4.0
0x76e8a  ldtoken  [mscorlib]System.IO.MemoryStream
0x76e8f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76e94  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76e99  ldstr    aS1// "s1"
0x76e9e  ldtoken  [mscorlib]System.IO.MemoryStream
0x76ea3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76ea8  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76ead  ldc.i4.0
0x76eae  newarr   [System]System.CodeDom.CodeExpression
0x76eb3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x76eb8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x76ebd  stelem.ref
0x76ebe  dup
0x76ebf  ldc.i4.1
0x76ec0  ldtoken  [mscorlib]System.IO.MemoryStream
0x76ec5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76eca  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76ecf  ldstr    aS2// "s2"
0x76ed4  ldtoken  [mscorlib]System.IO.MemoryStream
0x76ed9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x76ede  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x76ee3  ldc.i4.0
0x76ee4  newarr   [System]System.CodeDom.CodeExpression
0x76ee9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::New(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression[] parameters)
0x76eee  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x76ef3  stelem.ref
0x76ef4  dup
0x76ef5  ldc.i4.2
0x76ef6  ldloc.2
0x76ef7  ldc.i4.0
0x76ef8  newarr   [System]System.CodeDom.CodeCatchClause
0x76efd  ldloc.3
0x76efe  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Try(class [System]System.CodeDom.CodeStatement[] tryStmnts, class [System]System.CodeDom.CodeCatchClause[] catchClauses, class [System]System.CodeDom.CodeStatement[] finallyStmnts)
0x76f03  stelem.ref
0x76f04  stloc.s  4
0x76f06  ldarg.0
0x76f07  ldtoken  [System.Xml]System.Xml.Schema.XmlSchema
0x76f0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
  ... truncated ...
```
