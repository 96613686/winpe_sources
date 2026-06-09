# System.Data.Design.TypedDataSourceCodeGenerator::CreateDataSourceDeclaration

- ea: `0x8c3a0`
- end: `0x8c582`
- name: `System.Data.Design.TypedDataSourceCodeGenerator::CreateDataSourceDeclaration`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x8c060`

## callees

- `0x71f20`
- `0x72070`
- `0x72080`
- `0x72320`
- `0x723e0`
- `0x72570`
- `0x72580`
- `0x74b20`
- `0x74b50`
- `0x778a0`
- `0x7b3b0`
- `0x7b3d0`
- `0x7b440`
- `0x7b460`
- `0x7b510`
- `0x80420`
- `0x80440`
- `0x84170`
- `0x841a0`
- `0x8c3a0`
- `0x8cc20`
- `0x8ccf0`
- `0x8cd00`
- `0x8cd10`
- `0x8d050`
- `0x8d0b0`
- `0x8d120`
- `0x8d210`

## string_xrefs

- `0x8c416`: `System.ComponentModel.DesignerCategoryAttribute`
- `0x8c436`: `System.ComponentModel.ToolboxItem`
- `0x8c4d6`: `Represents a strongly typed in-memory cache of data.`

## pseudocode

```c

```

## disassembly

```asm
0x8c3a0  ldarg.1
0x8c3a1  callvirt instance string System.Data.Design.DesignDataSource::get_Name()
0x8c3a6  brtrue.s loc_8C3B3
0x8c3a8  ldstr    aDatasourceName// "DataSource name cannot be null."
0x8c3ad  newobj   instance void System.Data.Design.DataSourceGeneratorException::.ctor(string message)
0x8c3b2  throw
0x8c3b3  ldarg.0
0x8c3b4  ldfld    class [System]System.CodeDom.Compiler.CodeDomProvider System.Data.Design.TypedDataSourceCodeGenerator::codeProvider
0x8c3b9  newobj   instance void System.Data.Design.NameHandler::.ctor(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider)
0x8c3be  stloc.0
0x8c3bf  ldloc.0
0x8c3c0  ldarg.1
0x8c3c1  ldarg.0
0x8c3c2  ldfld    class [mscorlib]System.Collections.ArrayList System.Data.Design.TypedDataSourceCodeGenerator::problemList
0x8c3c7  callvirt instance void System.Data.Design.NameHandler::GenerateMemberNames(class System.Data.Design.DesignDataSource dataSource, class [mscorlib]System.Collections.ArrayList problemList)
0x8c3cc  ldarg.1
0x8c3cd  callvirt instance string System.Data.Design.DesignDataSource::get_GeneratorDataSetName()
0x8c3d2  ldc.i4.1
0x8c3d3  ldarg.1
0x8c3d4  callvirt instance valuetype [mscorlib]System.Reflection.TypeAttributes System.Data.Design.DesignDataSource::get_Modifier()
0x8c3d9  call     class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.CodeGenHelper::Class(string name, bool isPartial, valuetype [mscorlib]System.Reflection.TypeAttributes typeAttributes)
0x8c3de  stloc.1
0x8c3df  ldloc.1
0x8c3e0  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x8c3e5  ldtoken  [System.Data]System.Data.DataSet
0x8c3ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c3ef  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x8c3f4  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x8c3f9  pop
0x8c3fa  ldloc.1
0x8c3fb  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c400  ldstr    aSystemSerializ// "System.Serializable"
0x8c405  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name)
0x8c40a  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c40f  pop
0x8c410  ldloc.1
0x8c411  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c416  ldstr    aSystemComponen_2// "System.ComponentModel.DesignerCategoryA"...
0x8c41b  ldstr    aCode// "code"
0x8c420  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x8c425  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8c42a  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c42f  pop
0x8c430  ldloc.1
0x8c431  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c436  ldstr    aSystemComponen_3// "System.ComponentModel.ToolboxItem"
0x8c43b  ldc.i4.1
0x8c43c  box      [mscorlib]System.Boolean
0x8c441  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8c446  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8c44b  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c450  pop
0x8c451  ldloc.1
0x8c452  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c457  ldtoken  [System.Xml]System.Xml.Serialization.XmlSchemaProviderAttribute
0x8c45c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c461  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8c466  ldstr    aGettypeddatase// "GetTypedDataSetSchema"
0x8c46b  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8c470  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8c475  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c47a  pop
0x8c47b  ldloc.1
0x8c47c  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c481  ldtoken  [System.Xml]System.Xml.Serialization.XmlRootAttribute
0x8c486  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c48b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8c490  ldarg.1
0x8c491  callvirt instance string System.Data.Design.DesignDataSource::get_GeneratorDataSetName()
0x8c496  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x8c49b  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8c4a0  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c4a5  pop
0x8c4a6  ldloc.1
0x8c4a7  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x8c4ac  ldtoken  [System]System.ComponentModel.Design.HelpKeywordAttribute
0x8c4b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c4b6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8c4bb  ldstr    aVsDataDataset// "vs.data.DataSet"
0x8c4c0  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x8c4c5  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x8c4ca  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x8c4cf  pop
0x8c4d0  ldloc.1
0x8c4d1  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x8c4d6  ldstr    aRepresentsAStr// "Represents a strongly typed in-memory c"...
0x8c4db  ldc.i4.1
0x8c4dc  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x8c4e1  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x8c4e6  pop
0x8c4e7  ldarg.0
0x8c4e8  ldarg.0
0x8c4e9  ldarg.1
0x8c4ea  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x8c4ef  newobj   instance void System.Data.Design.TypedTableHandler::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignTableCollection tables)
0x8c4f4  stfld    class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::tableHandler
0x8c4f9  ldarg.0
0x8c4fa  ldarg.0
0x8c4fb  ldarg.1
0x8c4fc  callvirt instance class System.Data.Design.DesignRelationCollection System.Data.Design.DesignDataSource::get_DesignRelations()
0x8c501  newobj   instance void System.Data.Design.RelationHandler::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignRelationCollection relations)
0x8c506  stfld    class System.Data.Design.RelationHandler System.Data.Design.TypedDataSourceCodeGenerator::relationHandler
0x8c50b  ldarg.0
0x8c50c  ldarg.0
0x8c50d  ldarg.1
0x8c50e  callvirt instance class System.Data.Design.DesignTableCollection System.Data.Design.DesignDataSource::get_DesignTables()
0x8c513  newobj   instance void System.Data.Design.TypedRowHandler::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignTableCollection tables)
0x8c518  stfld    class System.Data.Design.TypedRowHandler System.Data.Design.TypedDataSourceCodeGenerator::rowHandler
0x8c51d  ldarg.0
0x8c51e  ldarg.1
0x8c51f  newobj   instance void System.Data.Design.DatasetMethodGenerator::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignDataSource dataSource)
0x8c524  stloc.2
0x8c525  ldarg.0
0x8c526  ldfld    class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::tableHandler
0x8c52b  ldloc.1
0x8c52c  callvirt instance void System.Data.Design.TypedTableHandler::AddPrivateVars(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c531  ldarg.0
0x8c532  ldfld    class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::tableHandler
0x8c537  ldloc.1
0x8c538  callvirt instance void System.Data.Design.TypedTableHandler::AddTableProperties(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c53d  ldarg.0
0x8c53e  ldfld    class System.Data.Design.RelationHandler System.Data.Design.TypedDataSourceCodeGenerator::relationHandler
0x8c543  ldloc.1
0x8c544  callvirt instance void System.Data.Design.RelationHandler::AddPrivateVars(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c549  ldloc.2
0x8c54a  ldloc.1
0x8c54b  callvirt instance void System.Data.Design.DatasetMethodGenerator::AddMethods(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c550  ldarg.0
0x8c551  ldfld    class System.Data.Design.TypedRowHandler System.Data.Design.TypedDataSourceCodeGenerator::rowHandler
0x8c556  ldloc.1
0x8c557  callvirt instance void System.Data.Design.TypedRowHandler::AddTypedRowEventHandlers(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c55c  ldarg.0
0x8c55d  ldfld    class System.Data.Design.TypedTableHandler System.Data.Design.TypedDataSourceCodeGenerator::tableHandler
0x8c562  ldloc.1
0x8c563  callvirt instance void System.Data.Design.TypedTableHandler::AddTableClasses(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c568  ldarg.0
0x8c569  ldfld    class System.Data.Design.TypedRowHandler System.Data.Design.TypedDataSourceCodeGenerator::rowHandler
0x8c56e  ldloc.1
0x8c56f  callvirt instance void System.Data.Design.TypedRowHandler::AddTypedRows(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c574  ldarg.0
0x8c575  ldfld    class System.Data.Design.TypedRowHandler System.Data.Design.TypedDataSourceCodeGenerator::rowHandler
0x8c57a  ldloc.1
0x8c57b  callvirt instance void System.Data.Design.TypedRowHandler::AddTypedRowEventArgs(class [System]System.CodeDom.CodeTypeDeclaration dataSourceClass)
0x8c580  ldloc.1
0x8c581  ret
```
