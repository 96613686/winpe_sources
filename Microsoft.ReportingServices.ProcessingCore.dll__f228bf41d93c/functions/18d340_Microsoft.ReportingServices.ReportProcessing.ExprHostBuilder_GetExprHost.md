# Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::GetExprHost

- ea: `0x18d340`
- end: `0x18d50b`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::GetExprHost`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18ce30`

## callees

- `0x18d300`
- `0x18d340`

## string_xrefs

- `0x18d3b6`: `System.Security.Permissions.SecurityPermission`
- `0x18d40b`: `System.Security.Permissions.SecurityPermission`
- `0x18d4c7`: `Microsoft.ReportingServices.ReportProcessing.ReportObjectModel`
- `0x18d4dc`: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x18d340  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x18d345  ldarg.0
0x18d346  ldfld    class RootTypeDecl Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::m_rootTypeDecl
0x18d34b  brfalse.s loc_18D35D
0x18d34d  ldarg.0
0x18d34e  ldfld    class TypeDecl Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::m_currentTypeDecl
0x18d353  ldfld    class TypeDecl TypeDecl::Parent
0x18d358  ldnull
0x18d359  ceq
0x18d35b  br.s     loc_18D35E
0x18d35d  ldc.i4.0
0x18d35e  ldstr    aMRoottypedeclN// "(m_rootTypeDecl != null && m_currentTyp"...
0x18d363  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x18d368  ldnull
0x18d369  stloc.0
0x18d36a  ldarg.0
0x18d36b  call     instance bool Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::get_HasExpressions()
0x18d370  brfalse  loc_18D502
0x18d375  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x18d37a  stloc.0
0x18d37b  ldloc.0
0x18d37c  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x18d381  ldstr    aSystemReflecti// "System.Reflection.AssemblyVersion"
0x18d386  ldc.i4.1
0x18d387  newarr   [System]System.CodeDom.CodeAttributeArgument
0x18d38c  dup
0x18d38d  ldc.i4.0
0x18d38e  ldarg.1
0x18d38f  callvirt instance string [mscorlib]System.Object::ToString()
0x18d394  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x18d399  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x18d39e  stelem.ref
0x18d39f  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x18d3a4  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x18d3a9  pop
0x18d3aa  ldarg.2
0x18d3ab  brfalse  loc_18D45A
0x18d3b0  ldloc.0
0x18d3b1  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x18d3b6  ldstr    aSystemSecurity// "System.Security.Permissions.SecurityPer"...
0x18d3bb  ldc.i4.2
0x18d3bc  newarr   [System]System.CodeDom.CodeAttributeArgument
0x18d3c1  dup
0x18d3c2  ldc.i4.0
0x18d3c3  ldtoken  [mscorlib]System.Security.Permissions.SecurityAction
0x18d3c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18d3cd  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x18d3d2  ldstr    aRequestminimum// "RequestMinimum"
0x18d3d7  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x18d3dc  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x18d3e1  stelem.ref
0x18d3e2  dup
0x18d3e3  ldc.i4.1
0x18d3e4  ldstr    aExecution// "Execution"
0x18d3e9  ldc.i4.1
0x18d3ea  box      [mscorlib]System.Boolean
0x18d3ef  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x18d3f4  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x18d3f9  stelem.ref
0x18d3fa  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x18d3ff  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x18d404  pop
0x18d405  ldloc.0
0x18d406  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x18d40b  ldstr    aSystemSecurity// "System.Security.Permissions.SecurityPer"...
0x18d410  ldc.i4.2
0x18d411  newarr   [System]System.CodeDom.CodeAttributeArgument
0x18d416  dup
0x18d417  ldc.i4.0
0x18d418  ldtoken  [mscorlib]System.Security.Permissions.SecurityAction
0x18d41d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18d422  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x18d427  ldstr    aRequestoptiona// "RequestOptional"
0x18d42c  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x18d431  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x18d436  stelem.ref
0x18d437  dup
0x18d438  ldc.i4.1
0x18d439  ldstr    aExecution// "Execution"
0x18d43e  ldc.i4.1
0x18d43f  box      [mscorlib]System.Boolean
0x18d444  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x18d449  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x18d44e  stelem.ref
0x18d44f  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x18d454  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x18d459  pop
0x18d45a  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor()
0x18d45f  stloc.1
0x18d460  ldloc.0
0x18d461  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x18d466  ldloc.1
0x18d467  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x18d46c  pop
0x18d46d  ldloc.1
0x18d46e  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d473  ldstr    aSystem// "System"
0x18d478  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d47d  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d482  ldloc.1
0x18d483  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d488  ldstr    aSystemConvert// "System.Convert"
0x18d48d  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d492  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d497  ldloc.1
0x18d498  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d49d  ldstr    aSystemMath// "System.Math"
0x18d4a2  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d4a7  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d4ac  ldloc.1
0x18d4ad  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d4b2  ldstr    aMicrosoftVisua// "Microsoft.VisualBasic"
0x18d4b7  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d4bc  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d4c1  ldloc.1
0x18d4c2  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d4c7  ldstr    aMicrosoftRepor_12// "Microsoft.ReportingServices.ReportProce"...
0x18d4cc  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d4d1  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d4d6  ldloc.1
0x18d4d7  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x18d4dc  ldstr    aMicrosoftRepor_16// "Microsoft.ReportingServices.ReportProce"...
0x18d4e1  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x18d4e6  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x18d4eb  ldloc.1
0x18d4ec  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x18d4f1  ldarg.0
0x18d4f2  ldfld    class RootTypeDecl Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::m_rootTypeDecl
0x18d4f7  ldfld    class [System]System.CodeDom.CodeTypeDeclaration TypeDecl::Type
0x18d4fc  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x18d501  pop
0x18d502  ldarg.0
0x18d503  ldnull
0x18d504  stfld    class RootTypeDecl Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::m_rootTypeDecl
0x18d509  ldloc.0
0x18d50a  ret
```
