# System.Data.Design.TableAdapterManagerGenerator::GenerateAdapterManager

- ea: `0x84cc0`
- end: `0x84dfc`
- name: `System.Data.Design.TableAdapterManagerGenerator::GenerateAdapterManager`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8c060`

## callees

- `0x71f20`
- `0x72070`
- `0x72080`
- `0x72320`
- `0x723e0`
- `0x72580`
- `0x7b3d0`
- `0x7cee0`
- `0x84cc0`
- `0x85060`
- `0x85090`

## string_xrefs

- `0x84d54`: `System.ComponentModel.DesignerCategoryAttribute`
- `0x84d74`: `System.ComponentModel.ToolboxItem`
- `0x84d95`: `System.ComponentModel.DesignerAttribute`
- `0x84d22`: `TableAdapterManager is used to coordinate TableAdapters in the dataset to enable Hierarchical Update scenarios`
- `0x84d9a`: `Microsoft.VSDesigner.DataSource.Design.TableAdapterManagerDesigner, Microsoft.VSDesigner, Version=10.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## pseudocode

```c

```

## disassembly

```asm
0x84cc0  ldc.i4.1
0x84cc1  stloc.0
0x84cc2  ldarg.1
0x84cc3  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x84cc8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x84ccd  stloc.3
0x84cce  br.s     loc_84CF1
0x84cd0  ldloc.3
0x84cd1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84cd6  castclass System.Data.Design.DesignTable
0x84cdb  stloc.s  4
0x84cdd  ldloc.s  4
0x84cdf  callvirt instance valuetype [mscorlib]System.Reflection.TypeAttributes System.Data.Design.DesignTable::get_DataAccessorModifier()
0x84ce4  ldc.i4.1
0x84ce5  and
0x84ce6  ldc.i4.1
0x84ce7  beq.s    loc_84CF1
0x84ce9  ldloc.s  4
0x84ceb  callvirt instance valuetype [mscorlib]System.Reflection.TypeAttributes System.Data.Design.DesignTable::get_DataAccessorModifier()
0x84cf0  stloc.0
0x84cf1  ldloc.3
0x84cf2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x84cf7  brtrue.s loc_84CD0
0x84cf9  leave.s  loc_84D0F
0x84cfb  ldloc.3
0x84cfc  isinst   [mscorlib]System.IDisposable
0x84d01  stloc.s  5
0x84d03  ldloc.s  5
0x84d05  brfalse.s loc_84D0E
0x84d07  ldloc.s  5
0x84d09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84d0e  endfinally
0x84d0f  ldstr    aTableadapterma// "TableAdapterManager"
0x84d14  ldc.i4.1
0x84d15  ldloc.0
0x84d16  call     class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.CodeGenHelper::Class(string name, bool isPartial, valuetype [mscorlib]System.Reflection.TypeAttributes typeAttributes)
0x84d1b  stloc.1
0x84d1c  ldloc.1
0x84d1d  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x84d22  ldstr    aTableadapterma_0// "TableAdapterManager is used to coordina"...
0x84d27  ldc.i4.1
0x84d28  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x84d2d  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x84d32  pop
0x84d33  ldloc.1
0x84d34  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x84d39  ldtoken  [System]System.ComponentModel.Component
0x84d3e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x84d43  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x84d48  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x84d4d  pop
0x84d4e  ldloc.1
0x84d4f  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x84d54  ldstr    aSystemComponen_2// "System.ComponentModel.DesignerCategoryA"...
0x84d59  ldstr    aCode// "code"
0x84d5e  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x84d63  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x84d68  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x84d6d  pop
0x84d6e  ldloc.1
0x84d6f  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x84d74  ldstr    aSystemComponen_3// "System.ComponentModel.ToolboxItem"
0x84d79  ldc.i4.1
0x84d7a  box      [mscorlib]System.Boolean
0x84d7f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x84d84  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x84d89  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x84d8e  pop
0x84d8f  ldloc.1
0x84d90  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x84d95  ldstr    aSystemComponen_5// "System.ComponentModel.DesignerAttribute"
0x84d9a  ldstr    aMicrosoftVsdes_1// "Microsoft.VSDesigner.DataSource.Design."...
0x84d9f  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x84da4  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x84da9  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x84dae  pop
0x84daf  ldloc.1
0x84db0  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x84db5  ldtoken  [System]System.ComponentModel.Design.HelpKeywordAttribute
0x84dba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x84dbf  callvirt instance string [mscorlib]System.Type::get_FullName()
0x84dc4  ldstr    aVsDataTableada_0// "vs.data.TableAdapterManager"
0x84dc9  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x84dce  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x84dd3  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x84dd8  pop
0x84dd9  ldarg.0
0x84dda  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.TableAdapterManagerGenerator::dataSourceGenerator
0x84ddf  ldarg.1
0x84de0  ldarg.2
0x84de1  newobj   instance void System.Data.Design.TableAdapterManagerMethodGenerator::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignDataSource dataSource, class [System]System.CodeDom.CodeTypeDeclaration dataSourceType)
0x84de6  stloc.2
0x84de7  ldloc.2
0x84de8  ldloc.1
0x84de9  callvirt instance void System.Data.Design.TableAdapterManagerMethodGenerator::AddEverything(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass)
0x84dee  ldloc.1
0x84def  call     void [System]System.CodeDom.Compiler.CodeGenerator::ValidateIdentifiers(class [System]System.CodeDom.CodeObject)
0x84df4  leave.s  loc_84DFA
0x84df6  stloc.s  6
0x84df8  leave.s  loc_84DFA
0x84dfa  ldloc.1
0x84dfb  ret
```
