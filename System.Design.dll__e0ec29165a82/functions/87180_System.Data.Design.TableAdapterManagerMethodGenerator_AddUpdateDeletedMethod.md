# System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateDeletedMethod

- ea: `0x87180`
- end: `0x87291`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateDeletedMethod`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

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
- `0x87180`
- `0x875f0`
- `0x878b0`

## string_xrefs

- `0x87252`: `Deleted`
- `0x8718f`: `UpdateDeletedRows`
- `0x871dc`: `Delete rows in bottom-up order.`

## pseudocode

```c

```

## disassembly

```asm
0x87180  ldtoken  [mscorlib]System.Int32
0x87185  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8718a  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8718f  ldstr    aUpdatedeletedr// "UpdateDeletedRows"
0x87194  ldc.i4   0x5000
0x87199  call     class [System]System.CodeDom.CodeMemberMethod System.Data.Design.CodeGenHelper::MethodDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x8719e  stloc.0
0x8719f  ldstr    aSystemCollecti_2// "System.Collections.Generic.List"
0x871a4  ldtoken  [System.Data]System.Data.DataRow
0x871a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x871ae  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalGenericType(string fullTypeName, class [mscorlib]System.Type itemType)
0x871b3  stloc.1
0x871b4  ldloc.1
0x871b5  ldarg.s  7
0x871b7  call     class [System]System.CodeDom.CodeParameterDeclarationExpression System.Data.Design.CodeGenHelper::ParameterDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x871bc  stloc.2
0x871bd  ldloc.0
0x871be  callvirt instance class [System]System.CodeDom.CodeParameterDeclarationExpressionCollection [System]System.CodeDom.CodeMemberMethod::get_Parameters()
0x871c3  ldc.i4.2
0x871c4  newarr   [System]System.CodeDom.CodeParameterDeclarationExpression
0x871c9  dup
0x871ca  ldc.i4.0
0x871cb  ldarg.3
0x871cc  stelem.ref
0x871cd  dup
0x871ce  ldc.i4.1
0x871cf  ldloc.2
0x871d0  stelem.ref
0x871d1  callvirt instance void [System]System.CodeDom.CodeParameterDeclarationExpressionCollection::AddRange(class [System]System.CodeDom.CodeParameterDeclarationExpression[])
0x871d6  ldloc.0
0x871d7  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x871dc  ldstr    aDeleteRowsInBo// "Delete rows in bottom-up order."
0x871e1  ldc.i4.1
0x871e2  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x871e7  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x871ec  pop
0x871ed  ldloc.0
0x871ee  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x871f3  ldtoken  [mscorlib]System.Int32
0x871f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x871fd  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(class [mscorlib]System.Type type)
0x87202  ldarg.s  5
0x87204  ldc.i4.0
0x87205  box      [mscorlib]System.Int32
0x8720a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8720f  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::VariableDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x87214  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x87219  pop
0x8721a  ldarg.2
0x8721b  ldlen
0x8721c  conv.i4
0x8721d  ldc.i4.1
0x8721e  sub
0x8721f  stloc.3
0x87220  br.s     loc_87267
0x87222  ldarg.0
0x87223  ldfld    class System.Data.Design.DesignDataSource System.Data.Design.TableAdapterManagerMethodGenerator::dataSource
0x87228  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x8722d  ldarg.2
0x8722e  ldloc.3
0x8722f  ldelem.ref
0x87230  callvirt instance class System.Data.Design.DesignTable System.Data.Design.DesignTableCollection::get_Item(class [System.Data]System.Data.DataTable dataTable)
0x87235  stloc.s  4
0x87237  ldarg.0
0x87238  ldloc.s  4
0x8723a  call     instance bool System.Data.Design.TableAdapterManagerMethodGenerator::CanAddTableAdapter(class System.Data.Design.DesignTable table)
0x8723f  brfalse.s loc_87263
0x87241  ldloc.0
0x87242  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x87247  ldarg.0
0x87248  ldloc.s  4
0x8724a  ldarg.s  4
0x8724c  ldarg.s  5
0x8724e  ldarg.s  6
0x87250  ldarg.s  7
0x87252  ldstr    aDeleted// "Deleted"
0x87257  ldnull
0x87258  call     instance class [System]System.CodeDom.CodeStatement System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateAllTAUpdate(class System.Data.Design.DesignTable table, string dataSetStr, string resultStr, string updateRowsStr, string allUpdateRowsStr, string rowState, string allAddedRowsStr)
0x8725d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x87262  pop
0x87263  ldloc.3
0x87264  ldc.i4.1
0x87265  sub
0x87266  stloc.3
0x87267  ldloc.3
0x87268  ldc.i4.0
0x87269  bge.s    loc_87222
0x8726b  ldloc.0
0x8726c  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberMethod::get_Statements()
0x87271  ldarg.s  5
0x87273  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Variable(string variable)
0x87278  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8727d  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x87282  pop
0x87283  ldarg.1
0x87284  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x87289  ldloc.0
0x8728a  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8728f  pop
0x87290  ret
```
