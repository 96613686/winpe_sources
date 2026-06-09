# System.Data.Design.TypedTableHandler::AddTableProperties

- ea: `0x8d120`
- end: `0x8d20f`
- name: `System.Data.Design.TypedTableHandler::AddTableProperties`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8c3a0`

## callees

- `0x71e90`
- `0x71ec0`
- `0x71f60`
- `0x71fd0`
- `0x72070`
- `0x72280`
- `0x724a0`
- `0x72580`
- `0x7e400`
- `0x7e440`
- `0x7e480`
- `0x8d120`

## string_xrefs

- `0x8d176`: `System.ComponentModel.Browsable`
- `0x8d198`: `System.ComponentModel.DesignerSerializationVisibility`

## pseudocode

```c

```

## disassembly

```asm
0x8d120  ldarg.0
0x8d121  ldfld    class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::tables
0x8d126  brtrue.s loc_8D129
0x8d128  ret
0x8d129  ldarg.0
0x8d12a  ldfld    class System.Data.Design.DesignTableCollection System.Data.Design.TypedTableHandler::tables
0x8d12f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8d134  stloc.0
0x8d135  br       loc_8D1ED
0x8d13a  ldloc.0
0x8d13b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8d140  castclass System.Data.Design.DesignTable
0x8d145  stloc.1
0x8d146  ldloc.1
0x8d147  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x8d14c  stloc.2
0x8d14d  ldloc.1
0x8d14e  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTablePropName()
0x8d153  stloc.3
0x8d154  ldloc.1
0x8d155  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableVarName()
0x8d15a  stloc.s  4
0x8d15c  ldloc.2
0x8d15d  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x8d162  ldloc.3
0x8d163  ldc.i4   0x6002
0x8d168  call     class [System]System.CodeDom.CodeMemberProperty System.Data.Design.CodeGenHelper::PropertyDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x8d16d  stloc.s  5
0x8d16f  ldloc.s  5
0x8d171  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8d176  ldstr    aSystemComponen_9// "System.ComponentModel.Browsable"
0x8d17b  ldc.i4.0
0x8d17c  box      [mscorlib]System.Boolean
0x8d181  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8d186  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8d18b  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8d190  pop
0x8d191  ldloc.s  5
0x8d193  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8d198  ldstr    aSystemComponen_10// "System.ComponentModel.DesignerSerializa"...
0x8d19d  ldtoken  [System]System.ComponentModel.DesignerSerializationVisibility
0x8d1a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d1a7  call     class [System]System.CodeDom.CodeTypeReferenceExpression System.Data.Design.CodeGenHelper::GlobalTypeExpr(class [mscorlib]System.Type type)
0x8d1ac  ldstr    aContent// "Content"
0x8d1b1  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8d1b6  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8d1bb  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8d1c0  pop
0x8d1c1  ldloc.s  5
0x8d1c3  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x8d1c8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::This()
0x8d1cd  ldloc.s  4
0x8d1cf  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Field(class [System]System.CodeDom.CodeExpression exp, string field)
0x8d1d4  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x8d1d9  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x8d1de  pop
0x8d1df  ldarg.1
0x8d1e0  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x8d1e5  ldloc.s  5
0x8d1e7  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x8d1ec  pop
0x8d1ed  ldloc.0
0x8d1ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8d1f3  brtrue   loc_8D13A
0x8d1f8  leave.s  loc_8D20E
0x8d1fa  ldloc.0
0x8d1fb  isinst   [mscorlib]System.IDisposable
0x8d200  stloc.s  6
0x8d202  ldloc.s  6
0x8d204  brfalse.s loc_8D20D
0x8d206  ldloc.s  6
0x8d208  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d20d  endfinally
0x8d20e  ret
```
