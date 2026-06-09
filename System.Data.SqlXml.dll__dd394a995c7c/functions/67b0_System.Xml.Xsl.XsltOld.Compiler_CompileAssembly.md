# System.Xml.Xsl.XsltOld.Compiler::CompileAssembly

- ea: `0x67b0`
- end: `0x6a7c`
- name: `System.Xml.Xsl.XsltOld.Compiler::CompileAssembly`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x6770`

## callees

- `0x66e0`
- `0x6740`
- `0x67b0`
- `0x10f30`

## string_xrefs

- `0x67b0`: `Microsoft.Xslt.CompiledScripts.`
- `0x6928`: `system.dll`
- `0x693d`: `microsoft.visualbasic.dll`
- `0x69d9`: `Xslt_ScriptCompileErrors`

## pseudocode

```c

```

## disassembly

```asm
0x67b0  ldstr    aMicrosoftXsltC// "Microsoft.Xslt.CompiledScripts."
0x67b5  ldarg.3
0x67b6  call     string [mscorlib]System.String::Concat(string, string)
0x67bb  starg.s  3
0x67bd  ldarg.3
0x67be  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor(string)
0x67c3  stloc.0
0x67c4  ldsfld   string[] System.Xml.Xsl.XsltOld.Compiler::_defaultNamespaces
0x67c9  stloc.s  5
0x67cb  ldc.i4.0
0x67cc  stloc.s  6
0x67ce  br.s     loc_67EF
0x67d0  ldloc.s  5
0x67d2  ldloc.s  6
0x67d4  ldelem.ref
0x67d5  stloc.s  7
0x67d7  ldloc.0
0x67d8  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x67dd  ldloc.s  7
0x67df  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x67e4  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x67e9  ldloc.s  6
0x67eb  ldc.i4.1
0x67ec  add
0x67ed  stloc.s  6
0x67ef  ldloc.s  6
0x67f1  ldloc.s  5
0x67f3  ldlen
0x67f4  conv.i4
0x67f5  blt.s    loc_67D0
0x67f7  ldarg.1
0x67f8  ldc.i4.1
0x67f9  bne.un.s loc_6810
0x67fb  ldloc.0
0x67fc  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x6801  ldstr    aMicrosoftVisua// "Microsoft.VisualBasic"
0x6806  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x680b  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x6810  ldarg.2
0x6811  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x6816  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x681b  stloc.s  8
0x681d  br.s     loc_683B
0x681f  ldloc.s  8
0x6821  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6826  castclass [System]System.CodeDom.CodeTypeDeclaration
0x682b  stloc.s  9
0x682d  ldloc.0
0x682e  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x6833  ldloc.s  9
0x6835  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x683a  pop
0x683b  ldloc.s  8
0x683d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6842  brtrue.s loc_681F
0x6844  leave.s  loc_685B
0x6846  ldloc.s  8
0x6848  isinst   [mscorlib]System.IDisposable
0x684d  stloc.s  0xA
0x684f  ldloc.s  0xA
0x6851  brfalse.s loc_685A
0x6853  ldloc.s  0xA
0x6855  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x685a  endfinally
0x685b  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x6860  stloc.1
0x6861  ldloc.1
0x6862  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x6867  ldloc.0
0x6868  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x686d  pop
0x686e  ldloc.1
0x686f  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x6874  ldstr    aAllowlatebound// "AllowLateBound"
0x6879  ldc.i4.1
0x687a  box      [mscorlib]System.Boolean
0x687f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x6884  ldloc.1
0x6885  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x688a  ldstr    aRequirevariabl// "RequireVariableDeclaration"
0x688f  ldc.i4.0
0x6890  box      [mscorlib]System.Boolean
0x6895  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x689a  ldloc.1
0x689b  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeCompileUnit::get_AssemblyCustomAttributes()
0x68a0  ldtoken  [mscorlib]System.Security.SecurityRulesAttribute
0x68a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68aa  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x68af  ldc.i4.1
0x68b0  newarr   [System]System.CodeDom.CodeAttributeArgument
0x68b5  dup
0x68b6  ldc.i4.0
0x68b7  ldtoken  [mscorlib]System.Security.SecurityRuleSet
0x68bc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68c1  newobj   instance void [System]System.CodeDom.CodeTypeReferenceExpression::.ctor(class [mscorlib]System.Type)
0x68c6  ldstr    aLevel1// "Level1"
0x68cb  newobj   instance void [System]System.CodeDom.CodeFieldReferenceExpression::.ctor(class [System]System.CodeDom.CodeExpression, string)
0x68d0  newobj   instance void [System]System.CodeDom.CodeAttributeArgument::.ctor(class [System]System.CodeDom.CodeExpression)
0x68d5  stelem.ref
0x68d6  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeAttributeArgument[])
0x68db  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x68e0  pop
0x68e1  newobj   instance void [System]System.CodeDom.Compiler.CompilerParameters::.ctor()
0x68e6  stloc.2
0x68e7  ldc.i4.s 0x20
0x68e9  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x68ee  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x68f3  ldloc.2
0x68f4  ldc.i4.1
0x68f5  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateInMemory(bool)
0x68fa  ldloc.2
0x68fb  ldarg.s  4
0x68fd  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_Evidence(class [mscorlib]System.Security.Policy.Evidence)
0x6902  ldloc.2
0x6903  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x6908  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x690d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6912  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Type::get_Module()
0x6917  callvirt instance string [mscorlib]System.Reflection.Module::get_FullyQualifiedName()
0x691c  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6921  pop
0x6922  ldloc.2
0x6923  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x6928  ldstr    aSystemDll// "system.dll"
0x692d  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6932  pop
0x6933  ldarg.1
0x6934  ldc.i4.1
0x6935  bne.un.s loc_6948
0x6937  ldloc.2
0x6938  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x693d  ldstr    aMicrosoftVisua_0// "microsoft.visualbasic.dll"
0x6942  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6947  pop
0x6948  leave.s  loc_6950
0x694a  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x694f  endfinally
0x6950  leave.s  loc_6955
0x6952  pop
0x6953  rethrow
0x6955  ldarg.0
0x6956  ldarg.1
0x6957  call     instance class [System]System.CodeDom.Compiler.CodeDomProvider System.Xml.Xsl.XsltOld.Compiler::ChooseCodeDomProvider(valuetype System.Xml.Xsl.XsltOld.ScriptingLanguage lang)
0x695c  ldloc.2
0x695d  ldc.i4.1
0x695e  newarr   [System]System.CodeDom.CodeCompileUnit
0x6963  dup
0x6964  ldc.i4.0
0x6965  ldloc.1
0x6966  stelem.ref
0x6967  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults [System]System.CodeDom.Compiler.CodeDomProvider::CompileAssemblyFromDom(class [System]System.CodeDom.Compiler.CompilerParameters, class [System]System.CodeDom.CodeCompileUnit[])
0x696c  stloc.3
0x696d  ldloc.3
0x696e  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x6973  callvirt instance bool [System]System.CodeDom.Compiler.CompilerErrorCollection::get_HasErrors()
0x6978  brfalse.s loc_69F4
0x697a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x697f  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x6984  stloc.s  0xB
0x6986  ldloc.3
0x6987  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x698c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6991  stloc.s  0xC
0x6993  br.s     loc_69B9
0x6995  ldloc.s  0xC
0x6997  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x699c  castclass [System]System.CodeDom.Compiler.CompilerError
0x69a1  stloc.s  0xD
0x69a3  ldarg.0
0x69a4  ldloc.s  0xD
0x69a6  call     instance void System.Xml.Xsl.XsltOld.Compiler::FixCompilerError(class [System]System.CodeDom.Compiler.CompilerError e)
0x69ab  ldloc.s  0xB
0x69ad  ldloc.s  0xD
0x69af  callvirt instance string [mscorlib]System.Object::ToString()
0x69b4  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69b9  ldloc.s  0xC
0x69bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69c0  brtrue.s loc_6995
0x69c2  leave.s  loc_69D9
0x69c4  ldloc.s  0xC
0x69c6  isinst   [mscorlib]System.IDisposable
0x69cb  stloc.s  0xA
0x69cd  ldloc.s  0xA
0x69cf  brfalse.s loc_69D8
0x69d1  ldloc.s  0xA
0x69d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69d8  endfinally
0x69d9  ldstr    aXsltScriptcomp// "Xslt_ScriptCompileErrors"
0x69de  ldc.i4.1
0x69df  newarr   [mscorlib]System.String
0x69e4  dup
0x69e5  ldc.i4.0
0x69e6  ldloc.s  0xB
0x69e8  callvirt instance string [mscorlib]System.Object::ToString()
0x69ed  stelem.ref
0x69ee  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x69f3  throw
0x69f4  ldloc.3
0x69f5  callvirt instance class [mscorlib]System.Reflection.Assembly [System]System.CodeDom.Compiler.CompilerResults::get_CompiledAssembly()
0x69fa  stloc.s  4
0x69fc  ldarg.2
0x69fd  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0x6a02  stloc.s  0xE
0x6a04  br.s     loc_6A5B
0x6a06  ldloc.s  0xE
0x6a08  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6a0d  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x6a12  stloc.s  0xF
0x6a14  ldloca.s 0xF
0x6a16  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x6a1b  castclass [mscorlib]System.String
0x6a20  stloc.s  0x10
0x6a22  ldloca.s 0xF
0x6a24  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x6a29  castclass [System]System.CodeDom.CodeTypeDeclaration
0x6a2e  stloc.s  0x11
0x6a30  ldarg.0
0x6a31  ldfld    class System.Xml.Xsl.XsltOld.Stylesheet System.Xml.Xsl.XsltOld.Compiler::stylesheet
0x6a36  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.Stylesheet::get_ScriptObjectTypes()
0x6a3b  ldloc.s  0x10
0x6a3d  ldloc.s  4
0x6a3f  ldarg.3
0x6a40  ldstr    asc_5909A// "."
0x6a45  ldloc.s  0x11
0x6a47  callvirt instance string [System]System.CodeDom.CodeTypeMember::get_Name()
0x6a4c  call     string [mscorlib]System.String::Concat(string, string, string)
0x6a51  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x6a56  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x6a5b  ldloc.s  0xE
0x6a5d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a62  brtrue.s loc_6A06
0x6a64  leave.s  loc_6A7B
0x6a66  ldloc.s  0xE
0x6a68  isinst   [mscorlib]System.IDisposable
0x6a6d  stloc.s  0xA
0x6a6f  ldloc.s  0xA
0x6a71  brfalse.s loc_6A7A
0x6a73  ldloc.s  0xA
0x6a75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a7a  endfinally
0x6a7b  ret
```
