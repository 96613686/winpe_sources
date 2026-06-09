# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::GetExprHost

- ea: `0x14d070`
- end: `0x14d250`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::GetExprHost`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x152db0`

## callees

- `0x14d030`
- `0x14d070`

## string_xrefs

- `0x14d0e6`: `System.Security.Permissions.SecurityPermission`
- `0x14d13b`: `System.Security.Permissions.SecurityPermission`
- `0x14d20c`: `Microsoft.ReportingServices.ReportProcessing.ReportObjectModel`
- `0x14d221`: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x14d070  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x14d075  ldarg.0
0x14d076  ldfld    class RootTypeDecl Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::m_rootTypeDecl
0x14d07b  brfalse.s loc_14D08D
0x14d07d  ldarg.0
0x14d07e  ldfld    class TypeDecl Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::m_currentTypeDecl
0x14d083  ldfld    class TypeDecl TypeDecl::Parent
0x14d088  ldnull
0x14d089  ceq
0x14d08b  br.s     loc_14D08E
0x14d08d  ldc.i4.0
0x14d08e  ldstr    aMRoottypedeclN// "(m_rootTypeDecl != null && m_currentTyp"...
0x14d093  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x14d098  ldnull
0x14d099  stloc.0
0x14d09a  ldarg.0
0x14d09b  call     instance bool Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::get_HasExpressions()
0x14d0a0  brfalse  loc_14D247
0x14d0a5  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x14d0aa  stloc.0
0x14d0ab  ldloc.0
0x14d0ac  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x14d0b1  ldstr    aSystemReflecti// "System.Reflection.AssemblyVersion"
0x14d0b6  ldc.i4.1
0x14d0b7  newarr   [System]System.CodeDom.CodeAttributeArgument
0x14d0bc  dup
0x14d0bd  ldc.i4.0
0x14d0be  ldarg.1
0x14d0bf  callvirt instance string [mscorlib]System.Object::ToString()
0x14d0c4  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x14d0c9  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x14d0ce  stelem.ref
0x14d0cf  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x14d0d4  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x14d0d9  pop
0x14d0da  ldarg.2
0x14d0db  brfalse  loc_14D18A
0x14d0e0  ldloc.0
0x14d0e1  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x14d0e6  ldstr    aSystemSecurity// "System.Security.Permissions.SecurityPer"...
0x14d0eb  ldc.i4.2
0x14d0ec  newarr   [System]System.CodeDom.CodeAttributeArgument
0x14d0f1  dup
0x14d0f2  ldc.i4.0
0x14d0f3  ldtoken  [mscorlib]System.Security.Permissions.SecurityAction
0x14d0f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14d0fd  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x14d102  ldstr    aRequestminimum// "RequestMinimum"
0x14d107  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x14d10c  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x14d111  stelem.ref
0x14d112  dup
0x14d113  ldc.i4.1
0x14d114  ldstr    aExecution// "Execution"
0x14d119  ldc.i4.1
0x14d11a  box      [mscorlib]System.Boolean
0x14d11f  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x14d124  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x14d129  stelem.ref
0x14d12a  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x14d12f  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x14d134  pop
0x14d135  ldloc.0
0x14d136  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x14d13b  ldstr    aSystemSecurity// "System.Security.Permissions.SecurityPer"...
0x14d140  ldc.i4.2
0x14d141  newarr   [System]System.CodeDom.CodeAttributeArgument
0x14d146  dup
0x14d147  ldc.i4.0
0x14d148  ldtoken  [mscorlib]System.Security.Permissions.SecurityAction
0x14d14d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14d152  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x14d157  ldstr    aRequestoptiona// "RequestOptional"
0x14d15c  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x14d161  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x14d166  stelem.ref
0x14d167  dup
0x14d168  ldc.i4.1
0x14d169  ldstr    aExecution// "Execution"
0x14d16e  ldc.i4.1
0x14d16f  box      [mscorlib]System.Boolean
0x14d174  newobj   instance void [System]System.CodeDom.CodePrimitiveExpression::.ctor(object)
0x14d179  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(string, class [System]System.CodeDom.CodeExpression)
0x14d17e  stelem.ref
0x14d17f  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string, class [System]System.CodeDom.CodeAttributeArgument[])
0x14d184  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x14d189  pop
0x14d18a  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor()
0x14d18f  stloc.1
0x14d190  ldloc.0
0x14d191  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x14d196  ldloc.1
0x14d197  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x14d19c  pop
0x14d19d  ldloc.1
0x14d19e  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d1a3  ldstr    aSystem// "System"
0x14d1a8  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d1ad  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d1b2  ldloc.1
0x14d1b3  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d1b8  ldstr    aSystemConvert// "System.Convert"
0x14d1bd  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d1c2  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d1c7  ldloc.1
0x14d1c8  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d1cd  ldstr    aSystemMath// "System.Math"
0x14d1d2  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d1d7  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d1dc  ldloc.1
0x14d1dd  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d1e2  ldstr    aMicrosoftVisua// "Microsoft.VisualBasic"
0x14d1e7  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d1ec  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d1f1  ldloc.1
0x14d1f2  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d1f7  ldstr    aMicrosoftSqlse// "Microsoft.SqlServer.Types"
0x14d1fc  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d201  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d206  ldloc.1
0x14d207  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d20c  ldstr    aMicrosoftRepor_12// "Microsoft.ReportingServices.ReportProce"...
0x14d211  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d216  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d21b  ldloc.1
0x14d21c  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x14d221  ldstr    aMicrosoftRepor_13// "Microsoft.ReportingServices.RdlExpressi"...
0x14d226  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x14d22b  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x14d230  ldloc.1
0x14d231  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x14d236  ldarg.0
0x14d237  ldfld    class RootTypeDecl Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::m_rootTypeDecl
0x14d23c  ldfld    class [System]System.CodeDom.CodeTypeDeclaration TypeDecl::Type
0x14d241  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x14d246  pop
0x14d247  ldarg.0
0x14d248  ldnull
0x14d249  stfld    class RootTypeDecl Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::m_rootTypeDecl
0x14d24e  ldloc.0
0x14d24f  ret
```
