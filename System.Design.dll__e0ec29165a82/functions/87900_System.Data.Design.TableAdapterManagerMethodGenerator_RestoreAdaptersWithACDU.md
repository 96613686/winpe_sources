# System.Data.Design.TableAdapterManagerMethodGenerator::RestoreAdaptersWithACDU

- ea: `0x87900`
- end: `0x87a14`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::RestoreAdaptersWithACDU`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x863b0`

## callees

- `0x71f20`
- `0x71f30`
- `0x71ff0`
- `0x72020`
- `0x72070`
- `0x720d0`
- `0x72120`
- `0x72260`
- `0x72270`
- `0x722a0`
- `0x72380`
- `0x72500`
- `0x87b40`
- `0x87bb0`

## string_xrefs

- `0x87948`: `AcceptChangesDuringUpdate`
- `0x879d4`: `CopyTo`

## pseudocode

```c

```

## disassembly

```asm
0x87900  ldc.i4.2
0x87901  newarr   [System]System.CodeDom.CodeStatement
0x87906  stloc.0
0x87907  ldloc.0
0x87908  ldc.i4.0
0x87909  ldtoken  [System.Data]System.Data.Common.DataAdapter
0x8790e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87913  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x87918  ldstr    aAdapter_1// "adapter"
0x8791d  ldstr    aAdapters// "adapters"
0x87922  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87927  ldstr    aI// "i"
0x8792c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87931  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Indexer(class [System]System.CodeDom.CodeExpression targetObject, class [System]System.CodeDom.CodeExpression indices)
0x87936  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8793b  stelem.ref
0x8793c  ldloc.0
0x8793d  ldc.i4.1
0x8793e  ldstr    aAdapter_1// "adapter"
0x87943  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87948  ldstr    aAcceptchangesd// "AcceptChangesDuringUpdate"
0x8794d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x87952  ldc.i4.1
0x87953  box      [mscorlib]System.Boolean
0x87958  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8795d  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87962  stelem.ref
0x87963  ldc.i4.0
0x87964  box      [mscorlib]System.Int32
0x87969  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8796e  ldarg.1
0x8796f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87974  ldstr    aCount// "Count"
0x87979  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x8797e  call     class [System]System.CodeDom.CodeBinaryOperatorExpression System.Data.Design.CodeGenHelper::Less(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x87983  ldc.i4.3
0x87984  newarr   [System]System.CodeDom.CodeStatement
0x87989  dup
0x8798a  ldc.i4.0
0x8798b  ldtoken  [System.Data]System.Data.Common.DataAdapter
0x87990  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87995  ldc.i4.1
0x87996  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x8799b  ldstr    aAdapters// "adapters"
0x879a0  ldarg.0
0x879a1  ldtoken  [System.Data]System.Data.Common.DataAdapter
0x879a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x879ab  ldc.i4.1
0x879ac  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x879b1  ldarg.1
0x879b2  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x879b7  ldstr    aCount// "Count"
0x879bc  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x879c1  call     instance class [System]System.CodeDom.CodeExpression System.Data.Design.TableAdapterManagerMethodGenerator::NewArray(class [System]System.CodeDom.CodeTypeReference type, class [System]System.CodeDom.CodeExpression size)
0x879c6  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x879cb  stelem.ref
0x879cc  dup
0x879cd  ldc.i4.1
0x879ce  ldarg.1
0x879cf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x879d4  ldstr    aCopyto// "CopyTo"
0x879d9  ldstr    aAdapters// "adapters"
0x879de  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x879e3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::MethodCall(class [System]System.CodeDom.CodeExpression targetObject, string methodName, class [System]System.CodeDom.CodeExpression par)
0x879e8  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Stm(class [System]System.CodeDom.CodeExpression expr)
0x879ed  stelem.ref
0x879ee  dup
0x879ef  ldc.i4.2
0x879f0  ldarg.0
0x879f1  ldstr    aAdapters// "adapters"
0x879f6  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x879fb  ldstr    aLength// "Length"
0x87a00  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Property(class [System]System.CodeDom.CodeExpression exp, string property)
0x87a05  ldloc.0
0x87a06  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.TableAdapterManagerMethodGenerator::GetForLoopItoCount(class [System]System.CodeDom.CodeExpression countExp, class [System]System.CodeDom.CodeStatement[] forStms)
0x87a0b  stelem.ref
0x87a0c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::If(class [System]System.CodeDom.CodeExpression cond, class [System]System.CodeDom.CodeStatement[] trueStms)
0x87a11  stloc.1
0x87a12  ldloc.1
0x87a13  ret
```
