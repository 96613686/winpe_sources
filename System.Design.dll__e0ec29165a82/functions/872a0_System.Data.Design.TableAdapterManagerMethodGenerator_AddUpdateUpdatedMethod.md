# System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateUpdatedMethod

- ea: `0x872a0`
- end: `0x873c2`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateUpdatedMethod`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x863b0`

## callees

- `0x71ed0`
- `0x71f20`
- `0x71f80`
- `0x72020`
- `0x72070`
- `0x72280`
- `0x72320`
- `0x72450`
- `0x72500`
- `0x72560`
- `0x7b3d0`
- `0x7e7e0`
- `0x872a0`
- `0x875f0`
- `0x878b0`

## string_xrefs

- `0x872af`: `UpdateUpdatedRows`
- `0x87309`: `Update rows in top-down order.`

## pseudocode

```c

```

## disassembly

```asm
0x872a0  ldtoken  [mscorlib]System.Int32
0x872a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x872aa  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x872af  ldstr    aUpdateupdatedr// "UpdateUpdatedRows"
0x872b4  ldc.i4   0x5000
0x872b9  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x872be  stloc.0
0x872bf  ldstr    aSystemCollecti_2// "System.Collections.Generic.List"
0x872c4  ldtoken  [System.Data]System.Data.DataRow
0x872c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x872ce  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalGenericType(string fullTypeName, class [mscorlib]System.Type itemType)
0x872d3  stloc.1
0x872d4  ldloc.1
0x872d5  ldarg.s  7
0x872d7  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x872dc  stloc.2
0x872dd  ldloc.1
0x872de  ldarg.s  8
0x872e0  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x872e5  stloc.3
0x872e6  ldloc.0
0x872e7  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x872ec  ldc.i4.3
0x872ed  newarr   [System]System.CodeDom.CodeParameterDeclarationExpression
0x872f2  dup
0x872f3  ldc.i4.0
0x872f4  ldarg.3
0x872f5  stelem.ref
0x872f6  dup
0x872f7  ldc.i4.1
0x872f8  ldloc.2
0x872f9  stelem.ref
0x872fa  dup
0x872fb  ldc.i4.2
0x872fc  ldloc.3
0x872fd  stelem.ref
0x872fe  callvirt instance void [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::AddRange(class [System]System.CodeDom.CodeParameterDeclarationExpression[])
0x87303  ldloc.0
0x87304  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x87309  ldstr    aUpdateRowsInTo// "Update rows in top-down order."
0x8730e  ldc.i4.1
0x8730f  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x87314  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x87319  pop
0x8731a  ldloc.0
0x8731b  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x87320  ldtoken  [mscorlib]System.Int32
0x87325  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8732a  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(class [mscorlib]System.Type type)
0x8732f  ldarg.s  5
0x87331  ldc.i4.0
0x87332  box      [mscorlib]System.Int32
0x87337  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8733c  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x87341  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x87346  pop
0x87347  ldc.i4.0
0x87348  stloc.s  4
0x8734a  br.s     loc_87395
0x8734c  ldarg.0
0x8734d  ldfld    class System.Data.Design.DesignDataSource System.Data.Design.TableAdapterManagerMethodGenerator::dataSource
0x87352  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x87357  ldarg.2
0x87358  ldloc.s  4
0x8735a  ldelem.ref
0x8735b  callvirt instance class System.Data.Design.DesignTable System.Data.Design.DesignTableCollection::get_Item(class [System.Data]System.Data.DataTable dataTable)
0x87360  stloc.s  5
0x87362  ldarg.0
0x87363  ldloc.s  5
0x87365  call     instance bool System.Data.Design.TableAdapterManagerMethodGenerator::CanAddTableAdapter(class System.Data.Design.DesignTable table)
0x8736a  brfalse.s loc_8738F
0x8736c  ldloc.0
0x8736d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x87372  ldarg.0
0x87373  ldloc.s  5
0x87375  ldarg.s  4
0x87377  ldarg.s  5
0x87379  ldarg.s  6
0x8737b  ldarg.s  7
0x8737d  ldstr    aModifiedcurren// "ModifiedCurrent"
0x87382  ldarg.s  8
0x87384  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAllTAUpdate(class System.Data.Design.DesignTable table, string dataSetStr, string resultStr, string updateRowsStr, string allUpdateRowsStr, string rowState, string allAddedRowsStr)
0x87389  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8738e  pop
0x8738f  ldloc.s  4
0x87391  ldc.i4.1
0x87392  add
0x87393  stloc.s  4
0x87395  ldloc.s  4
0x87397  ldarg.2
0x87398  ldlen
0x87399  conv.i4
0x8739a  blt.s    loc_8734C
0x8739c  ldloc.0
0x8739d  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x873a2  ldarg.s  5
0x873a4  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x873a9  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x873ae  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x873b3  pop
0x873b4  ldarg.1
0x873b5  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x873ba  ldloc.0
0x873bb  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x873c0  pop
0x873c1  ret
```
