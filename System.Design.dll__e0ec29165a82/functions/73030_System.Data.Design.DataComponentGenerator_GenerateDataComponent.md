# System.Data.Design.DataComponentGenerator::GenerateDataComponent

- ea: `0x73030`
- end: `0x731ce`
- name: `System.Data.Design.DataComponentGenerator::GenerateDataComponent`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x8c060`

## callees

- `0x71f40`
- `0x72070`
- `0x72080`
- `0x72320`
- `0x723e0`
- `0x72580`
- `0x73030`
- `0x731f0`
- `0x73230`
- `0x7cb40`
- `0x7cee0`
- `0x7d150`
- `0x7d170`
- `0x7d190`
- `0x7e690`
- `0x836a0`
- `0x83710`
- `0x83ae0`

## string_xrefs

- `0x73062`: `System.ComponentModel.DesignerCategoryAttribute`
- `0x73082`: `System.ComponentModel.ToolboxItem`
- `0x730a3`: `System.ComponentModel.DataObjectAttribute`
- `0x730c4`: `System.ComponentModel.DesignerAttribute`
- `0x730ce`: `, Microsoft.VSDesigner, Version=10.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`
- `0x7311a`: `System.Web.Services.WebService`
- `0x7317e`: `Represents the connection and commands used to retrieve and save data.`

## pseudocode

```c

```

## disassembly

```asm
0x73030  ldarg.1
0x73031  callvirt instance string System.Data.Design.DesignTable::get_GeneratorDataComponentClassName()
0x73036  stloc.0
0x73037  ldloc.0
0x73038  ldc.i4.1
0x73039  ldarg.1
0x7303a  callvirt instance valuetype [mscorlib]System.Reflection.TypeAttributes System.Data.Design.DesignTable::get_DataAccessorModifier()
0x7303f  call     class [System]System.CodeDom.CodeTypeDeclaration System.Data.Design.CodeGenHelper::Class(string name, bool isPartial, valuetype [mscorlib]System.Reflection.TypeAttributes typeAttributes)
0x73044  stloc.1
0x73045  ldloc.1
0x73046  callvirt instance class [System]System.CodeDom.CodeTypeReferenceCollection [System]System.CodeDom.CodeTypeDeclaration::get_BaseTypes()
0x7304b  ldarg.1
0x7304c  callvirt instance string System.Data.Design.DesignTable::get_BaseClass()
0x73051  call     class [System]System.CodeDom.CodeTypeReference System.Data.Design.CodeGenHelper::GlobalType(string type)
0x73056  callvirt instance int32 [System]System.CodeDom.CodeTypeReferenceCollection::Add(class [System]System.CodeDom.CodeTypeReference)
0x7305b  pop
0x7305c  ldloc.1
0x7305d  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x73062  ldstr    aSystemComponen_2// "System.ComponentModel.DesignerCategoryA"...
0x73067  ldstr    aCode// "code"
0x7306c  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x73071  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x73076  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x7307b  pop
0x7307c  ldloc.1
0x7307d  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x73082  ldstr    aSystemComponen_3// "System.ComponentModel.ToolboxItem"
0x73087  ldc.i4.1
0x73088  box      [mscorlib]System.Boolean
0x7308d  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x73092  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x73097  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x7309c  pop
0x7309d  ldloc.1
0x7309e  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x730a3  ldstr    aSystemComponen_4// "System.ComponentModel.DataObjectAttribu"...
0x730a8  ldc.i4.1
0x730a9  box      [mscorlib]System.Boolean
0x730ae  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Primitive(object primitive)
0x730b3  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x730b8  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x730bd  pop
0x730be  ldloc.1
0x730bf  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x730c4  ldstr    aSystemComponen_5// "System.ComponentModel.DesignerAttribute"
0x730c9  ldsfld   string System.Data.Design.DataComponentGenerator::adapterDesigner
0x730ce  ldstr    aMicrosoftVsdes// ", Microsoft.VSDesigner, Version=10.0.0."...
0x730d3  call     string [mscorlib]System.String::Concat(string, string)
0x730d8  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x730dd  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x730e2  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x730e7  pop
0x730e8  ldloc.1
0x730e9  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x730ee  ldtoken  [System]System.ComponentModel.Design.HelpKeywordAttribute
0x730f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x730f8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x730fd  ldstr    aVsDataTableada// "vs.data.TableAdapter"
0x73102  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x73107  call     class [System]System.CodeDom.CodeAttributeDeclaration System.Data.Design.CodeGenHelper::AttributeDecl(string name, class [System]System.CodeDom.CodeExpression value)
0x7310c  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x73111  pop
0x73112  ldarg.1
0x73113  callvirt instance bool System.Data.Design.DesignTable::get_WebServiceAttribute()
0x73118  brfalse.s loc_73178
0x7311a  ldstr    aSystemWebServi// "System.Web.Services.WebService"
0x7311f  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string)
0x73124  stloc.s  4
0x73126  ldloc.s  4
0x73128  callvirt instance class [System]System.CodeDom.CodeAttributeArgumentCollection [System]System.CodeDom.CodeAttributeDeclaration::get_Arguments()
0x7312d  ldstr    aNamespace// "Namespace"
0x73132  ldarg.1
0x73133  callvirt instance string System.Data.Design.DesignTable::get_WebServiceNamespace()
0x73138  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x7313d  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x73142  callvirt instance int32 [System]System.CodeDom.CodeAttributeArgumentCollection::Add(class [System]System.CodeDom.CodeAttributeArgument)
0x73147  pop
0x73148  ldloc.s  4
0x7314a  callvirt instance class [System]System.CodeDom.CodeAttributeArgumentCollection [System]System.CodeDom.CodeAttributeDeclaration::get_Arguments()
0x7314f  ldstr    aDescription_0// "Description"
0x73154  ldarg.1
0x73155  callvirt instance string System.Data.Design.DesignTable::get_WebServiceDescription()
0x7315a  call     class [System]System.CodeDom.CodeExpression System.Data.Design.CodeGenHelper::Str(string str)
0x7315f  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x73164  callvirt instance int32 [System]System.CodeDom.CodeAttributeArgumentCollection::Add(class [System]System.CodeDom.CodeAttributeArgument)
0x73169  pop
0x7316a  ldloc.1
0x7316b  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x73170  ldloc.s  4
0x73172  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x73177  pop
0x73178  ldloc.1
0x73179  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x7317e  ldstr    aRepresentsTheC// "Represents the connection and commands "...
0x73183  ldc.i4.1
0x73184  call     class [System]System.CodeDom.CodeCommentStatement System.Data.Design.CodeGenHelper::Comment(string comment, bool docSummary)
0x73189  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x7318e  pop
0x7318f  ldarg.0
0x73190  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DataComponentGenerator::dataSourceGenerator
0x73195  ldarg.1
0x73196  ldarg.3
0x73197  newobj   instance void System.Data.Design.DataComponentMethodGenerator::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignTable designTable, bool generateHierarchicalUpdate)
0x7319c  stloc.2
0x7319d  ldloc.2
0x7319e  ldloc.1
0x7319f  ldarg.2
0x731a0  callvirt instance void System.Data.Design.DataComponentMethodGenerator::AddMethods(class [System]System.CodeDom.CodeTypeDeclaration dataComponentClass, bool isFunctionsDataComponent)
0x731a5  ldloc.1
0x731a6  call     void [System]System.CodeDom.Compiler.CodeGenerator::ValidateIdentifiers(class [System]System.CodeDom.CodeObject)
0x731ab  ldarg.0
0x731ac  ldfld    class System.Data.Design.TypedDataSourceCodeGenerator System.Data.Design.DataComponentGenerator::dataSourceGenerator
0x731b1  ldarg.1
0x731b2  newobj   instance void System.Data.Design.QueryHandler::.ctor(class System.Data.Design.TypedDataSourceCodeGenerator codeGenerator, class System.Data.Design.DesignTable designTable)
0x731b7  stloc.3
0x731b8  ldarg.2
0x731b9  brfalse.s loc_731C5
0x731bb  ldloc.3
0x731bc  ldloc.1
0x731bd  ldc.i4.1
0x731be  callvirt instance void System.Data.Design.QueryHandler::AddFunctionsToDataComponent(class [System]System.CodeDom.CodeTypeDeclaration classDeclaration, bool isFunctionsDataComponent)
0x731c3  br.s     loc_731CC
0x731c5  ldloc.3
0x731c6  ldloc.1
0x731c7  callvirt instance void System.Data.Design.QueryHandler::AddQueriesToDataComponent(class [System]System.CodeDom.CodeTypeDeclaration classDeclaration)
0x731cc  ldloc.1
0x731cd  ret
```
