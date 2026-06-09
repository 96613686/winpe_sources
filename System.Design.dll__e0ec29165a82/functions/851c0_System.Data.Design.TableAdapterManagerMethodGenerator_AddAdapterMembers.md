# System.Data.Design.TableAdapterManagerMethodGenerator::AddAdapterMembers

- ea: `0x851c0`
- end: `0x8530d`
- name: `System.Data.Design.TableAdapterManagerMethodGenerator::AddAdapterMembers`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x85090`

## callees

- `0x71ec0`
- `0x71fe0`
- `0x72010`
- `0x72080`
- `0x72280`
- `0x722a0`
- `0x723b0`
- `0x724a0`
- `0x725a0`
- `0x7b3d0`
- `0x7e690`
- `0x7e6e0`
- `0x851c0`
- `0x878b0`
- `0x87ce0`
- `0x87cf0`
- `0x10d850`
- `0x10d860`
- `0x10d870`
- `0x10d880`

## string_xrefs

- `0x8527f`: `System.ComponentModel.EditorAttribute`
- `0x85284`: `Microsoft.VSDesigner.DataSource.Design.TableAdapterManagerPropertyEditor, Microsoft.VSDesigner, Version=10.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## pseudocode

```c

```

## disassembly

```asm
0x851c0  ldarg.0
0x851c1  ldfld    class System.Data.Design.DesignDataSource System.Data.Design.TableAdapterManagerMethodGenerator::dataSource
0x851c6  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x851cb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x851d0  stloc.0
0x851d1  br       loc_852EB
0x851d6  ldloc.0
0x851d7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x851dc  castclass System.Data.Design.DesignTable
0x851e1  stloc.1
0x851e2  ldarg.0
0x851e3  ldloc.1
0x851e4  call     instance bool System.Data.Design.TableAdapterManagerMethodGenerator::CanAddTableAdapter(class System.Data.Design.DesignTable table)
0x851e9  brfalse  loc_852EB
0x851ee  ldloc.1
0x851ef  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x851f4  ldarg.0
0x851f5  ldfld    class System.Data.Design.TableAdapterManagerNameHandler System.Data.Design.TableAdapterManagerMethodGenerator::nameHandler
0x851fa  ldloc.1
0x851fb  callvirt instance string System.Data.Design.DesignTable::get_GeneratorDataComponentClassName()
0x85200  callvirt instance string System.Data.Design.TableAdapterManagerNameHandler::GetTableAdapterPropName(string className)
0x85205  callvirt instance void CodeGenPropertyCache::set_TAMAdapterPropName(string value)
0x8520a  ldloc.1
0x8520b  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x85210  ldarg.0
0x85211  ldfld    class System.Data.Design.TableAdapterManagerNameHandler System.Data.Design.TableAdapterManagerMethodGenerator::nameHandler
0x85216  ldloc.1
0x85217  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x8521c  callvirt instance string CodeGenPropertyCache::get_TAMAdapterPropName()
0x85221  callvirt instance string System.Data.Design.TableAdapterManagerNameHandler::GetTableAdapterVarName(string propName)
0x85226  callvirt instance void CodeGenPropertyCache::set_TAMAdapterVarName(string value)
0x8522b  ldloc.1
0x8522c  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x85231  callvirt instance string CodeGenPropertyCache::get_TAMAdapterVarName()
0x85236  stloc.2
0x85237  ldloc.1
0x85238  callvirt instance string System.Data.Design.DesignTable::get_GeneratorDataComponentClassName()
0x8523d  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x85242  ldloc.2
0x85243  call     class [System]System.CodeDom.CodeMemberField System.Data.Design.CodeGenHelper::FieldDecl(class [System]System.CodeDom.CodeTypeReference type, string name)
0x85248  stloc.3
0x85249  ldarg.1
0x8524a  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x8524f  ldloc.3
0x85250  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x85255  pop
0x85256  ldloc.1
0x85257  callvirt instance string System.Data.Design.DesignTable::get_GeneratorDataComponentClassName()
0x8525c  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::Type(string type)
0x85261  ldloc.1
0x85262  callvirt instance class CodeGenPropertyCache System.Data.Design.DesignTable::get_PropertyCache()
0x85267  callvirt instance string CodeGenPropertyCache::get_TAMAdapterPropName()
0x8526c  ldc.i4   0x6002
0x85271  call     class [System]System.CodeDom.CodeMemberProperty System.Data.Design.CodeGenHelper::PropertyDecl(class [System]System.CodeDom.CodeTypeReference type, string name, valuetype [System]System.CodeDom.MemberAttributes attributes)
0x85276  stloc.s  4
0x85278  ldloc.s  4
0x8527a  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8527f  ldstr    aSystemComponen_8// "System.ComponentModel.EditorAttribute"
0x85284  ldstr    aMicrosoftVsdes_2// "Microsoft.VSDesigner.DataSource.Design."...
0x85289  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x8528e  ldstr    aSystemDrawingD// "System.Drawing.Design.UITypeEditor"
0x85293  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x85298  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value1, class [System]System.CodeDom.CodeExpression value2)
0x8529d  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x852a2  pop
0x852a3  ldloc.s  4
0x852a5  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_GetStatements()
0x852aa  ldloc.2
0x852ab  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x852b0  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Return(class [System]System.CodeDom.CodeExpression expr)
0x852b5  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x852ba  pop
0x852bb  ldloc.s  4
0x852bd  callvirt instance class [System]System.CodeDom.CodeStatementCollection [System]System.CodeDom.CodeMemberProperty::get_SetStatements()
0x852c2  ldloc.2
0x852c3  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::ThisField(string field)
0x852c8  ldstr    aValue// "value"
0x852cd  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Argument(string argument)
0x852d2  call     class [System]System.CodeDom.CodeStatement System.Data.Design.CodeGenHelper::Assign(class [System]System.CodeDom.CodeExpression left, class [System]System.CodeDom.CodeExpression right)
0x852d7  callvirt instance int32 [System]System.CodeDom.CodeStatementCollection::Add(class [System]System.CodeDom.CodeStatement)
0x852dc  pop
0x852dd  ldarg.1
0x852de  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x852e3  ldloc.s  4
0x852e5  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x852ea  pop
0x852eb  ldloc.0
0x852ec  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x852f1  brtrue   loc_851D6
0x852f6  leave.s  loc_8530C
0x852f8  ldloc.0
0x852f9  isinst   [mscorlib]System.IDisposable
0x852fe  stloc.s  5
0x85300  ldloc.s  5
0x85302  brfalse.s loc_8530B
0x85304  ldloc.s  5
0x85306  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8530b  endfinally
0x8530c  ret
```
