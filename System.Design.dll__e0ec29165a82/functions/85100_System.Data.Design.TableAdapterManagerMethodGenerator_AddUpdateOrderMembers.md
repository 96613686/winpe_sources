# System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateOrderMembers

- ea: `0x85100`
- end: `0x851be`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddUpdateOrderMembers`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x85090`

## callees

- `0x71ec0`
- `0x71ed0`
- `0x72070`
- `0x72320`
- `0x723c0`
- `0x723e0`
- `0x87840`

## string_xrefs

- `0x85100`: `UpdateOrderOption`
- `0x851a3`: `UpdateOrderOption`
- `0x8511a`: `Update Order Option`
- `0x8513a`: `InsertUpdateDelete`
- `0x8516c`: `UpdateInsertDelete`
- `0x851ad`: `UpdateOrder`
- `0x851b2`: `_updateOrder`

## pseudocode

```c

```

## disassembly

```asm
0x85100  ldstr    aUpdateorderopt// "UpdateOrderOption"
0x85105  ldc.i4.0
0x85106  ldc.i4.2
0x85107  call     class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.CodeGenHelper::Class(string name, bool isPartial, valuetype [mscorlib]System.Reflection.TypeAttributes typeAttributes)
0x8510c  stloc.0
0x8510d  ldloc.0
0x8510e  ldc.i4.1
0x8510f  callvirt instance void [System]System.CodeDom.CodeTypeDeclaration::set_IsEnum(bool)
0x85114  ldloc.0
0x85115  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x8511a  ldstr    aUpdateOrderOpt// "Update Order Option"
0x8511f  ldc.i4.1
0x85120  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x85125  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x8512a  pop
0x8512b  ldtoken  [mscorlib]System.Int32
0x85130  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85135  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(class [mscorlib]System.Type type)
0x8513a  ldstr    aInsertupdatede// "InsertUpdateDelete"
0x8513f  ldc.i4.0
0x85140  box      [mscorlib]System.Int32
0x85145  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8514a  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x8514f  stloc.1
0x85150  ldloc.0
0x85151  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85156  ldloc.1
0x85157  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8515c  pop
0x8515d  ldtoken  [mscorlib]System.Int32
0x85162  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x85167  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(class [mscorlib]System.Type type)
0x8516c  ldstr    aUpdateinsertde// "UpdateInsertDelete"
0x85171  ldc.i4.1
0x85172  box      [mscorlib]System.Int32
0x85177  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8517c  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name, class [System]System.CodeDom.CodeExpression initExpr)
0x85181  stloc.2
0x85182  ldloc.0
0x85183  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85188  ldloc.2
0x85189  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8518e  pop
0x8518f  ldarg.1
0x85190  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x85195  ldloc.0
0x85196  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8519b  pop
0x8519c  ldarg.0
0x8519d  ldarg.1
0x8519e  ldc.i4   0x6002
0x851a3  ldstr    aUpdateorderopt// "UpdateOrderOption"
0x851a8  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x851ad  ldstr    aUpdateorder// "UpdateOrder"
0x851b2  ldstr    aUpdateorder_0// "_updateOrder"
0x851b7  ldc.i4.0
0x851b8  call     instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddVariableAndProperty(class [System]System.CodeDom.CodeTypeDeclaration codeType, valuetype [System]System.CodeDom.MemberAttributes memberAttributes, class [System]System.CodeDom.CodeTypeReference propertyType, string propertyName, string variableName, bool getOnly)
0x851bd  ret
```
