# System.Xml.Xsl.Xslt.Scripts::CompileAssembly

- ea: `0x1c3d0`
- end: `0x1c8ee`
- name: `System.Xml.Xsl.Xslt.Scripts::CompileAssembly`
- size: `1310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1c290`

## callees

- `0x137b0`
- `0x13ba0`
- `0x1c120`
- `0x1c3d0`
- `0x1c8f0`
- `0x1c950`

## string_xrefs

- `0x1c4cc`: `System.Xml.Xsl.CompiledQuery`
- `0x1c421`: `Xslt_ScriptCompileException`
- `0x1c7f7`: `Xslt_ScriptCompileException`
- `0x1c496`: `System.dll`
- `0x1c4ac`: `Microsoft.VisualBasic.dll`
- `0x1c5d9`: `System.Security.SecurityTransparentAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x1c3d0  ldarg.0
0x1c3d1  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c3d6  ldfld    class [System]System.CodeDom.Compiler.CompilerResults System.Xml.Xsl.Xslt.Compiler::CompilerResults
0x1c3db  callvirt instance class [System]System.CodeDom.Compiler.TempFileCollection [System]System.CodeDom.Compiler.CompilerResults::get_TempFiles()
0x1c3e0  stloc.0
0x1c3e1  ldarg.0
0x1c3e2  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c3e7  ldfld    class [System]System.CodeDom.Compiler.CompilerResults System.Xml.Xsl.Xslt.Compiler::CompilerResults
0x1c3ec  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x1c3f1  stloc.1
0x1c3f2  ldarg.1
0x1c3f3  ldarg.1
0x1c3f4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c3f9  ldc.i4.1
0x1c3fa  sub
0x1c3fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c400  stloc.2
0x1c401  ldc.i4.0
0x1c402  stloc.s  4
0x1c404  ldloc.2
0x1c405  ldfld    class [System]System.CodeDom.Compiler.CompilerInfo System.Xml.Xsl.Xslt.ScriptClass::compilerInfo
0x1c40a  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider [System]System.CodeDom.Compiler.CompilerInfo::CreateProvider()
0x1c40f  stloc.3
0x1c410  leave.s  loc_1C449
0x1c412  stloc.s  0xD
0x1c414  ldloc.1
0x1c415  ldarg.0
0x1c416  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c41b  ldloc.2
0x1c41c  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.ScriptClass::get_EndLineInfo()
0x1c421  ldstr    aXsltScriptcomp_0// "Xslt_ScriptCompileException"
0x1c426  ldc.i4.1
0x1c427  newarr   [mscorlib]System.String
0x1c42c  dup
0x1c42d  ldc.i4.0
0x1c42e  ldloc.s  0xD
0x1c430  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c435  stelem.ref
0x1c436  callvirt instance class [System]System.CodeDom.Compiler.CompilerError System.Xml.Xsl.Xslt.Compiler::CreateError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x1c43b  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerErrorCollection::Add(class [System]System.CodeDom.Compiler.CompilerError)
0x1c440  pop
0x1c441  ldnull
0x1c442  stloc.s  0xE
0x1c444  leave    loc_1C8EB
0x1c449  ldloc.3
0x1c44a  isinst   [System]Microsoft.VisualBasic.VBCodeProvider
0x1c44f  ldnull
0x1c450  cgt.un
0x1c452  stloc.s  4
0x1c454  ldarg.1
0x1c455  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c45a  newarr   [System]System.CodeDom.CodeCompileUnit
0x1c45f  stloc.s  5
0x1c461  ldloc.2
0x1c462  ldfld    class [System]System.CodeDom.Compiler.CompilerInfo System.Xml.Xsl.Xslt.ScriptClass::compilerInfo
0x1c467  callvirt instance class [System]System.CodeDom.Compiler.CompilerParameters [System]System.CodeDom.Compiler.CompilerInfo::CreateDefaultCompilerParameters()
0x1c46c  stloc.s  6
0x1c46e  ldloc.s  6
0x1c470  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x1c475  ldtoken  [System.Xml]System.Xml.Res
0x1c47a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c47f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1c484  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1c489  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1c48e  pop
0x1c48f  ldloc.s  6
0x1c491  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x1c496  ldstr    aSystemDll_0// "System.dll"
0x1c49b  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1c4a0  pop
0x1c4a1  ldloc.s  4
0x1c4a3  brfalse.s loc_1C4B7
0x1c4a5  ldloc.s  6
0x1c4a7  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x1c4ac  ldstr    aMicrosoftVisua_1// "Microsoft.VisualBasic.dll"
0x1c4b1  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1c4b6  pop
0x1c4b7  ldc.i4.0
0x1c4b8  stloc.s  7
0x1c4ba  ldc.i4.0
0x1c4bb  stloc.s  0xF
0x1c4bd  br       loc_1C692
0x1c4c2  ldarg.1
0x1c4c3  ldloc.s  0xF
0x1c4c5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c4ca  stloc.s  0x10
0x1c4cc  ldstr    aSystemXmlXslCo// "System.Xml.Xsl.CompiledQuery"
0x1c4d1  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor(string)
0x1c4d6  stloc.s  0x11
0x1c4d8  ldsfld   string[] System.Xml.Xsl.Xslt.Scripts::defaultNamespaces
0x1c4dd  stloc.s  0x13
0x1c4df  ldc.i4.0
0x1c4e0  stloc.s  0x14
0x1c4e2  br.s     loc_1C504
0x1c4e4  ldloc.s  0x13
0x1c4e6  ldloc.s  0x14
0x1c4e8  ldelem.ref
0x1c4e9  stloc.s  0x15
0x1c4eb  ldloc.s  0x11
0x1c4ed  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x1c4f2  ldloc.s  0x15
0x1c4f4  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x1c4f9  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x1c4fe  ldloc.s  0x14
0x1c500  ldc.i4.1
0x1c501  add
0x1c502  stloc.s  0x14
0x1c504  ldloc.s  0x14
0x1c506  ldloc.s  0x13
0x1c508  ldlen
0x1c509  conv.i4
0x1c50a  blt.s    loc_1C4E4
0x1c50c  ldloc.s  4
0x1c50e  brfalse.s loc_1C526
0x1c510  ldloc.s  0x11
0x1c512  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x1c517  ldstr    aMicrosoftVisua// "Microsoft.VisualBasic"
0x1c51c  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x1c521  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x1c526  ldloc.s  0x10
0x1c528  ldfld    class [System]System.Collections.Specialized.StringCollection System.Xml.Xsl.Xslt.ScriptClass::nsImports
0x1c52d  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x1c532  stloc.s  0x16
0x1c534  br.s     loc_1C552
0x1c536  ldloc.s  0x16
0x1c538  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x1c53d  stloc.s  0x17
0x1c53f  ldloc.s  0x11
0x1c541  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x1c546  ldloc.s  0x17
0x1c548  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x1c54d  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x1c552  ldloc.s  0x16
0x1c554  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x1c559  brtrue.s loc_1C536
0x1c55b  leave.s  loc_1C572
0x1c55d  ldloc.s  0x16
0x1c55f  isinst   [mscorlib]System.IDisposable
0x1c564  stloc.s  0x18
0x1c566  ldloc.s  0x18
0x1c568  brfalse.s loc_1C571
0x1c56a  ldloc.s  0x18
0x1c56c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c571  endfinally
0x1c572  ldloc.s  0x11
0x1c574  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x1c579  ldloc.s  0x10
0x1c57b  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.Xml.Xsl.Xslt.ScriptClass::typeDecl
0x1c580  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x1c585  pop
0x1c586  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x1c58b  stloc.s  0x12
0x1c58d  ldloc.s  0x12
0x1c58f  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x1c594  ldloc.s  0x11
0x1c596  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x1c59b  pop
0x1c59c  ldloc.s  4
0x1c59e  brfalse.s loc_1C5CE
0x1c5a0  ldloc.s  0x12
0x1c5a2  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x1c5a7  ldstr    aAllowlatebound// "AllowLateBound"
0x1c5ac  ldc.i4.1
0x1c5ad  box      [mscorlib]System.Boolean
0x1c5b2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1c5b7  ldloc.s  0x12
0x1c5b9  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x1c5be  ldstr    aRequirevariabl// "RequireVariableDeclaration"
0x1c5c3  ldc.i4.0
0x1c5c4  box      [mscorlib]System.Boolean
0x1c5c9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1c5ce  ldloc.s  0xF
0x1c5d0  brtrue.s loc_1C631
0x1c5d2  ldloc.s  0x12
0x1c5d4  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x1c5d9  ldstr    aSystemSecurity// "System.Security.SecurityTransparentAttr"...
0x1c5de  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(string)
0x1c5e3  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x1c5e8  pop
0x1c5e9  ldloc.s  0x12
0x1c5eb  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x1c5f0  ldtoken  [mscorlib]System.Security.SecurityRulesAttribute
0x1c5f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c5fa  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x1c5ff  ldc.i4.1
0x1c600  newarr   [System]System.CodeDom.CodeAttributeArgument
0x1c605  dup
0x1c606  ldc.i4.0
0x1c607  ldtoken  [mscorlib]System.Security.SecurityRuleSet
0x1c60c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c611  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x1c616  ldstr    aLevel1// "Level1"
0x1c61b  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x1c620  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x1c625  stelem.ref
0x1c626  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeAttributeArgument[])
0x1c62b  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x1c630  pop
0x1c631  ldloc.s  5
0x1c633  ldloc.s  0xF
0x1c635  ldloc.s  0x12
0x1c637  stelem.ref
0x1c638  ldloc.s  0x10
0x1c63a  ldfld    class [System]System.Collections.Specialized.StringCollection System.Xml.Xsl.Xslt.ScriptClass::refAssemblies
0x1c63f  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x1c644  stloc.s  0x19
0x1c646  br.s     loc_1C660
0x1c648  ldloc.s  0x19
0x1c64a  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x1c64f  stloc.s  0x1A
0x1c651  ldloc.s  6
0x1c653  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x1c658  ldloc.s  0x1A
0x1c65a  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1c65f  pop
0x1c660  ldloc.s  0x19
0x1c662  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x1c667  brtrue.s loc_1C648
0x1c669  leave.s  loc_1C680
0x1c66b  ldloc.s  0x19
0x1c66d  isinst   [mscorlib]System.IDisposable
0x1c672  stloc.s  0x18
0x1c674  ldloc.s  0x18
0x1c676  brfalse.s loc_1C67F
0x1c678  ldloc.s  0x18
0x1c67a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c67f  endfinally
0x1c680  ldloc.s  7
0x1c682  ldloc.s  0x10
0x1c684  ldfld    bool System.Xml.Xsl.Xslt.ScriptClass::refAssembliesByHref
0x1c689  or
0x1c68a  stloc.s  7
0x1c68c  ldloc.s  0xF
0x1c68e  ldc.i4.1
0x1c68f  add
0x1c690  stloc.s  0xF
0x1c692  ldloc.s  0xF
0x1c694  ldarg.1
0x1c695  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c69a  blt      loc_1C4C2
0x1c69f  ldarg.0
0x1c6a0  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c6a5  ldfld    class [System.Xml]System.Xml.Xsl.XsltSettings System.Xml.Xsl.Xslt.Compiler::Settings
0x1c6aa  stloc.s  8
0x1c6ac  ldloc.s  6
0x1c6ae  ldloc.s  8
0x1c6b0  callvirt instance int32 [System.Xml]System.Xml.Xsl.XsltSettings::get_WarningLevel()
0x1c6b5  ldc.i4.0
0x1c6b6  bge.s    loc_1C6C1
0x1c6b8  ldloc.s  6
0x1c6ba  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerParameters::get_WarningLevel()
0x1c6bf  br.s     loc_1C6C8
0x1c6c1  ldloc.s  8
0x1c6c3  callvirt instance int32 [System.Xml]System.Xml.Xsl.XsltSettings::get_WarningLevel()
0x1c6c8  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_WarningLevel(int32)
0x1c6cd  ldloc.s  6
0x1c6cf  ldloc.s  8
0x1c6d1  callvirt instance bool [System.Xml]System.Xml.Xsl.XsltSettings::get_TreatWarningsAsErrors()
0x1c6d6  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_TreatWarningsAsErrors(bool)
0x1c6db  ldloc.s  6
0x1c6dd  ldarg.0
0x1c6de  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c6e3  ldfld    bool System.Xml.Xsl.Xslt.Compiler::IsDebug
0x1c6e8  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_IncludeDebugInformation(bool)
0x1c6ed  ldarg.0
0x1c6ee  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.Scripts::compiler
0x1c6f3  ldfld    string System.Xml.Xsl.Xslt.Compiler::ScriptAssemblyPath
0x1c6f8  stloc.s  9
0x1c6fa  ldloc.s  9
0x1c6fc  brfalse.s loc_1C737
0x1c6fe  ldarg.1
0x1c6ff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c704  ldarg.0
0x1c705  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c70a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c70f  bge.s    loc_1C737
0x1c711  ldloc.s  9
0x1c713  ldstr    asc_5909A// "."
0x1c718  ldarg.0
0x1c719  ldloc.2
0x1c71a  ldfld    class [System]System.CodeDom.Compiler.CompilerInfo System.Xml.Xsl.Xslt.ScriptClass::compilerInfo
0x1c71f  call     instance string System.Xml.Xsl.Xslt.Scripts::GetLanguageName(class [System]System.CodeDom.Compiler.CompilerInfo compilerInfo)
0x1c724  ldloc.s  9
0x1c726  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x1c72b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c730  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x1c735  stloc.s  9
0x1c737  ldloc.s  6
0x1c739  ldloc.s  9
0x1c73b  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_OutputAssembly(string)
0x1c740  ldloc.s  8
0x1c742  callvirt instance class [System]System.CodeDom.Compiler.TempFileCollection [System.Xml]System.Xml.Xsl.XsltSettings::get_TempFiles()
0x1c747  brtrue.s loc_1C74C
0x1c749  ldnull
0x1c74a  br.s     loc_1C758
0x1c74c  ldloc.s  8
0x1c74e  callvirt instance class [System]System.CodeDom.Compiler.TempFileCollection [System.Xml]System.Xml.Xsl.XsltSettings::get_TempFiles()
0x1c753  callvirt instance string [System]System.CodeDom.Compiler.TempFileCollection::get_TempDir()
0x1c758  stloc.s  0xA
0x1c75a  ldloc.s  6
  ... truncated ...
```
