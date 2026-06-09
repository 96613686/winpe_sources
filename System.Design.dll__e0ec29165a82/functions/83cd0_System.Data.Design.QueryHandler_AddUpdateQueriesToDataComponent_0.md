# System.Data.Design.QueryHandler::AddUpdateQueriesToDataComponent_0

- ea: `0x83cd0`
- end: `0x84065`
- name: `System.Data.Design.QueryHandler::AddUpdateQueriesToDataComponent_0`
- size: `917`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x801d0`
- `0x83cb0`

## callees

- `0x71f20`
- `0x71f30`
- `0x72810`
- `0x747c0`
- `0x747d0`
- `0x747e0`
- `0x79c90`
- `0x79ce0`
- `0x79d30`
- `0x79f10`
- `0x7ac50`
- `0x7cb70`
- `0x7cd30`
- `0x7ce00`
- `0x7e480`
- `0x7f8f0`
- `0x80fd0`
- `0x81ec0`
- `0x81ed0`
- `0x81ee0`
- `0x81ef0`
- `0x81f00`
- `0x81f20`
- `0x81f40`
- `0x81fe0`
- `0x82040`
- `0x82060`
- `0x82080`
- `0x82090`
- `0x820a0`
- `0x820c0`
- `0x820e0`
- `0x82100`
- `0x821b0`
- `0x83cd0`
- `0x84c30`
- `0x8bf80`
- `0x8c050`
- `0x8d2b0`
- `0x8d2c0`

## string_xrefs

- `0x83f57`: `DeleteCommand`
- `0x83faf`: `InsertCommand`
- `0x84007`: `UpdateCommand`
- `0x83d79`: `DesignTable.Connection should not be null to generate update query statements.`

## pseudocode

```c

```

## disassembly

```asm
0x83cd0  ldarg.0
0x83cd1  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83cd6  brtrue.s loc_83CE3
0x83cd8  ldstr    aDesignTableSho// "Design Table should not be null."
0x83cdd  newobj   instance void System.Data.Design.InternalException::.ctor(string internalMessage)
0x83ce2  throw
0x83ce3  ldarg.2
0x83ce4  call     bool System.Data.Design.StringUtil::EmptyOrSpace(string str)
0x83ce9  brfalse.s loc_83CF6
0x83ceb  ldstr    aDataSourceClas// "Data source class name should not be em"...
0x83cf0  newobj   instance void System.Data.Design.InternalException::.ctor(string internalMessage)
0x83cf5  throw
0x83cf6  ldarg.0
0x83cf7  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83cfc  callvirt instance bool System.Data.Design.DesignTable::get_HasAnyUpdateCommand()
0x83d01  brfalse  loc_84064
0x83d06  ldarg.0
0x83d07  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83d0c  newobj   instance void System.Data.Design.UpdateCommandGenerator::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator)
0x83d11  stloc.0
0x83d12  ldloc.0
0x83d13  ldarg.3
0x83d14  callvirt instance void System.Data.Design.QueryGeneratorBase::set_CodeProvider(class [System]System.CodeDom.Compiler.CodeDomProvider value)
0x83d19  ldloc.0
0x83d1a  ldarg.0
0x83d1b  ldfld    bool System.Data.Design.QueryHandler::declarationsOnly
0x83d20  callvirt instance void System.Data.Design.QueryGeneratorBase::set_DeclarationOnly(bool value)
0x83d25  ldloc.0
0x83d26  ldarg.0
0x83d27  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83d2c  callvirt instance class System.Data.Design.Source System.Data.Design.DesignTable::get_MainSource()
0x83d31  isinst   System.Data.Design.DbSource
0x83d36  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodSource(class System.Data.Design.DbSource value)
0x83d3b  ldloc.0
0x83d3c  ldarg.0
0x83d3d  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83d42  callvirt instance void System.Data.Design.QueryGeneratorBase::set_DesignTable(class System.Data.Design.DesignTable value)
0x83d47  ldarg.0
0x83d48  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83d4d  callvirt instance class System.Data.Design.IDesignConnection System.Data.Design.DesignTable::get_Connection()
0x83d52  brfalse.s loc_83D71
0x83d54  ldloc.0
0x83d55  ldarg.0
0x83d56  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83d5b  callvirt instance class System.Data.Design.IDesignConnection System.Data.Design.DesignTable::get_Connection()
0x83d60  callvirt instance string System.Data.Design.IDesignConnection::get_Provider()
0x83d65  call     class [System.Data]System.Data.Common.DbProviderFactory System.Data.Design.ProviderManager::GetFactory(string invariantName)
0x83d6a  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ProviderFactory(class [System.Data]System.Data.Common.DbProviderFactory value)
0x83d6f  br.s     loc_83D84
0x83d71  ldarg.0
0x83d72  ldfld    bool System.Data.Design.QueryHandler::declarationsOnly
0x83d77  brtrue.s loc_83D84
0x83d79  ldstr    aDesigntableCon// "DesignTable.Connection should not be nu"...
0x83d7e  newobj   instance void System.Data.Design.InternalException::.ctor(string internalMessage)
0x83d83  throw
0x83d84  ldnull
0x83d85  stloc.1
0x83d86  ldloc.0
0x83d87  call     string System.Data.Design.DataComponentNameHandler::get_UpdateMethodName()
0x83d8c  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodName(string value)
0x83d91  ldloc.0
0x83d92  ldloc.0
0x83d93  callvirt instance class System.Data.Design.DbSource System.Data.Design.QueryGeneratorBase::get_MethodSource()
0x83d98  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_UpdateCommand()
0x83d9d  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ActiveCommand(class System.Data.Design.DbSourceCommand value)
0x83da2  ldloc.0
0x83da3  ldc.i4.1
0x83da4  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodType(valuetype System.Data.Design.MethodTypeEnum value)
0x83da9  ldloc.0
0x83daa  ldtoken  [System.Data]System.Data.DataTable
0x83daf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x83db4  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x83db9  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeReference(class [System]System.CodeDom.CodeTypeReference value)
0x83dbe  ldloc.0
0x83dbf  ldstr    aDatatable// "dataTable"
0x83dc4  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterName(string value)
0x83dc9  ldloc.0
0x83dca  ldarg.3
0x83dcb  ldarg.2
0x83dcc  ldarg.0
0x83dcd  ldfld    class System.Data.Design.DesignTable System.Data.Design.QueryHandler::designTable
0x83dd2  callvirt instance string System.Data.Design.DesignTable::get_GeneratorTableClassName()
0x83dd7  call     string System.Data.Design.CodeGenHelper::GetTypeName(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, string string1, string string2)
0x83ddc  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83de1  ldarg.0
0x83de2  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83de7  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x83dec  brfalse.s loc_83E15
0x83dee  ldloc.0
0x83def  ldarg.0
0x83df0  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83df5  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider System.Data.Design.TypedDataSourceCodeGenerator::get_CodeProvider()
0x83dfa  ldarg.0
0x83dfb  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83e00  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x83e05  ldloc.0
0x83e06  callvirt instance string System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeName()
0x83e0b  call     string System.Data.Design.CodeGenHelper::GetTypeName(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, string string1, string string2)
0x83e10  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83e15  ldloc.0
0x83e16  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83e1b  stloc.1
0x83e1c  ldloc.1
0x83e1d  brfalse.s loc_83E2C
0x83e1f  ldarg.1
0x83e20  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83e25  ldloc.1
0x83e26  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83e2b  pop
0x83e2c  ldloc.0
0x83e2d  ldtoken  [System.Data]System.Data.DataSet
0x83e32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x83e37  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x83e3c  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeReference(class [System]System.CodeDom.CodeTypeReference value)
0x83e41  ldloc.0
0x83e42  ldstr    aDataset// "dataSet"
0x83e47  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterName(string value)
0x83e4c  ldloc.0
0x83e4d  ldarg.2
0x83e4e  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83e53  ldarg.0
0x83e54  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83e59  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x83e5e  brfalse.s loc_83E87
0x83e60  ldloc.0
0x83e61  ldarg.0
0x83e62  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83e67  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider System.Data.Design.TypedDataSourceCodeGenerator::get_CodeProvider()
0x83e6c  ldarg.0
0x83e6d  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.QueryHandler::codeGenerator
0x83e72  callvirt instance string System.Data.Design.TypedDataSourceCodeGenerator::get_DataSetNamespace()
0x83e77  ldloc.0
0x83e78  callvirt instance string System.Data.Design.QueryGeneratorBase::get_UpdateParameterTypeName()
0x83e7d  call     string System.Data.Design.CodeGenHelper::GetTypeName(class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, string string1, string string2)
0x83e82  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83e87  ldloc.0
0x83e88  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83e8d  stloc.1
0x83e8e  ldloc.1
0x83e8f  brfalse.s loc_83E9E
0x83e91  ldarg.1
0x83e92  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83e97  ldloc.1
0x83e98  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83e9d  pop
0x83e9e  ldloc.0
0x83e9f  ldtoken  [System.Data]System.Data.DataRow
0x83ea4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x83ea9  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type)
0x83eae  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeReference(class [System]System.CodeDom.CodeTypeReference value)
0x83eb3  ldloc.0
0x83eb4  ldstr    aDatarow// "dataRow"
0x83eb9  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterName(string value)
0x83ebe  ldloc.0
0x83ebf  ldnull
0x83ec0  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83ec5  ldloc.0
0x83ec6  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83ecb  stloc.1
0x83ecc  ldloc.1
0x83ecd  brfalse.s loc_83EDC
0x83ecf  ldarg.1
0x83ed0  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83ed5  ldloc.1
0x83ed6  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83edb  pop
0x83edc  ldloc.0
0x83edd  ldtoken  [System.Data]System.Data.DataRow
0x83ee2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x83ee7  ldc.i4.1
0x83ee8  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(class [mscorlib]System.Type type, int32 rank)
0x83eed  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeReference(class [System]System.CodeDom.CodeTypeReference value)
0x83ef2  ldloc.0
0x83ef3  ldstr    aDatarows// "dataRows"
0x83ef8  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterName(string value)
0x83efd  ldloc.0
0x83efe  ldnull
0x83eff  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateParameterTypeName(string value)
0x83f04  ldloc.0
0x83f05  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83f0a  stloc.1
0x83f0b  ldloc.1
0x83f0c  brfalse.s loc_83F1B
0x83f0e  ldarg.1
0x83f0f  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83f14  ldloc.1
0x83f15  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83f1a  pop
0x83f1b  ldloc.0
0x83f1c  callvirt instance class System.Data.Design.DbSource System.Data.Design.QueryGeneratorBase::get_MethodSource()
0x83f21  callvirt instance bool System.Data.Design.DbSource::get_GenerateShortCommands()
0x83f26  brfalse  loc_84064
0x83f2b  ldloc.0
0x83f2c  ldc.i4.0
0x83f2d  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodType(valuetype System.Data.Design.MethodTypeEnum value)
0x83f32  ldloc.0
0x83f33  ldloc.0
0x83f34  callvirt instance class System.Data.Design.DbSource System.Data.Design.QueryGeneratorBase::get_MethodSource()
0x83f39  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_DeleteCommand()
0x83f3e  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ActiveCommand(class System.Data.Design.DbSourceCommand value)
0x83f43  ldloc.0
0x83f44  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.QueryGeneratorBase::get_ActiveCommand()
0x83f49  brfalse.s loc_83F8A
0x83f4b  ldloc.0
0x83f4c  call     string System.Data.Design.DataComponentNameHandler::get_DeleteMethodName()
0x83f51  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodName(string value)
0x83f56  ldloc.0
0x83f57  ldstr    aDeletecommand// "DeleteCommand"
0x83f5c  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateCommandName(string value)
0x83f61  ldloc.0
0x83f62  ldarg.0
0x83f63  ldfld    bool System.Data.Design.QueryHandler::languageSupportsNullables
0x83f68  brtrue.s loc_83F6D
0x83f6a  ldc.i4.2
0x83f6b  br.s     loc_83F6E
0x83f6d  ldc.i4.0
0x83f6e  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ParameterOption(valuetype System.Data.Design.ParameterGenerationOption value)
0x83f73  ldloc.0
0x83f74  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83f79  stloc.1
0x83f7a  ldloc.1
0x83f7b  brfalse.s loc_83F8A
0x83f7d  ldarg.1
0x83f7e  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83f83  ldloc.1
0x83f84  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83f89  pop
0x83f8a  ldloc.0
0x83f8b  ldloc.0
0x83f8c  callvirt instance class System.Data.Design.DbSource System.Data.Design.QueryGeneratorBase::get_MethodSource()
0x83f91  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_InsertCommand()
0x83f96  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ActiveCommand(class System.Data.Design.DbSourceCommand value)
0x83f9b  ldloc.0
0x83f9c  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.QueryGeneratorBase::get_ActiveCommand()
0x83fa1  brfalse.s loc_83FE2
0x83fa3  ldloc.0
0x83fa4  call     string System.Data.Design.DataComponentNameHandler::get_InsertMethodName()
0x83fa9  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodName(string value)
0x83fae  ldloc.0
0x83faf  ldstr    aInsertcommand// "InsertCommand"
0x83fb4  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateCommandName(string value)
0x83fb9  ldloc.0
0x83fba  ldarg.0
0x83fbb  ldfld    bool System.Data.Design.QueryHandler::languageSupportsNullables
0x83fc0  brtrue.s loc_83FC5
0x83fc2  ldc.i4.2
0x83fc3  br.s     loc_83FC6
0x83fc5  ldc.i4.0
0x83fc6  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ParameterOption(valuetype System.Data.Design.ParameterGenerationOption value)
0x83fcb  ldloc.0
0x83fcc  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x83fd1  stloc.1
0x83fd2  ldloc.1
0x83fd3  brfalse.s loc_83FE2
0x83fd5  ldarg.1
0x83fd6  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x83fdb  ldloc.1
0x83fdc  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x83fe1  pop
0x83fe2  ldloc.0
0x83fe3  ldloc.0
0x83fe4  callvirt instance class System.Data.Design.DbSource System.Data.Design.QueryGeneratorBase::get_MethodSource()
0x83fe9  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.DbSource::get_UpdateCommand()
0x83fee  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ActiveCommand(class System.Data.Design.DbSourceCommand value)
0x83ff3  ldloc.0
0x83ff4  callvirt instance class System.Data.Design.DbSourceCommand System.Data.Design.QueryGeneratorBase::get_ActiveCommand()
0x83ff9  brfalse.s loc_84064
0x83ffb  ldloc.0
0x83ffc  call     string System.Data.Design.DataComponentNameHandler::get_UpdateMethodName()
0x84001  callvirt instance void System.Data.Design.QueryGeneratorBase::set_MethodName(string value)
0x84006  ldloc.0
0x84007  ldstr    aUpdatecommand// "UpdateCommand"
0x8400c  callvirt instance void System.Data.Design.QueryGeneratorBase::set_UpdateCommandName(string value)
0x84011  ldloc.0
0x84012  ldarg.0
0x84013  ldfld    bool System.Data.Design.QueryHandler::languageSupportsNullables
0x84018  brtrue.s loc_8401D
0x8401a  ldc.i4.2
0x8401b  br.s     loc_8401E
0x8401d  ldc.i4.0
0x8401e  callvirt instance void System.Data.Design.QueryGeneratorBase::set_ParameterOption(valuetype System.Data.Design.ParameterGenerationOption value)
0x84023  ldloc.0
0x84024  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x84029  stloc.1
0x8402a  ldloc.1
0x8402b  brfalse.s loc_84064
0x8402d  ldarg.1
0x8402e  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x84033  ldloc.1
0x84034  callvirt instance int32 [System]System.CodeDom.CodeTypeMemberCollection::Add(class [System]System.CodeDom.CodeTypeMember)
0x84039  pop
0x8403a  ldnull
0x8403b  stloc.1
0x8403c  ldloc.0
0x8403d  ldc.i4.1
0x8403e  callvirt instance void System.Data.Design.UpdateCommandGenerator::set_GenerateOverloadWithoutCurrentPKParameters(bool value)
0x84043  ldloc.0
0x84044  callvirt instance class [System]System.CodeDom.CodeMemberMethod System.Data.Design.QueryGeneratorBase::Generate()
0x84049  stloc.1
0x8404a  leave.s  loc_84054
  ... truncated ...
```
