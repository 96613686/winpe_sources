# System.Resources.Tools.StronglyTypedResourceBuilder::InternalCreate

- ea: `0x470`
- end: `0x778`
- name: `System.Resources.Tools.StronglyTypedResourceBuilder::InternalCreate`
- size: `776`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x330`
- `0x790`

## callees

- `0x300`
- `0x470`
- `0x860`
- `0x8e0`
- `0xe50`
- `0x10d0`
- `0x10e0`
- `0x1170`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x514`: `System.dll`
- `0x5ca`: `ClassDocComment`

## pseudocode

```c

```

## disassembly

```asm
0x470  ldarg.1
0x471  brtrue.s loc_47E
0x473  ldstr    aBasename// "baseName"
0x478  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x47d  throw
0x47e  ldarg.s  4
0x480  brtrue.s loc_48D
0x482  ldstr    aCodeprovider// "codeProvider"
0x487  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x48c  throw
0x48d  ldc.i4.0
0x48e  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x493  stloc.0
0x494  ldarg.0
0x495  ldarg.s  4
0x497  ldloc.0
0x498  ldloca.s 2
0x49a  call     class [mscorlib]System.Collections.SortedList System.Resources.Tools.StronglyTypedResourceBuilder::VerifyResourceNames(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ResourceData> resourceList, class [System]System.CodeDom.Compiler.CodeDomProvider codeProvider, class [mscorlib]System.Collections.ArrayList errors, [out] class [mscorlib]System.Collections.Hashtable& reverseFixupTable)
0x49f  stloc.1
0x4a0  ldarg.1
0x4a1  stloc.3
0x4a2  ldarg.s  4
0x4a4  ldloc.3
0x4a5  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::IsValidIdentifier(string)
0x4aa  brtrue.s loc_4BD
0x4ac  ldloc.3
0x4ad  ldarg.s  4
0x4af  call     string System.Resources.Tools.StronglyTypedResourceBuilder::VerifyResourceName(string key, class [System]System.CodeDom.Compiler.CodeDomProvider provider)
0x4b4  stloc.s  0xE
0x4b6  ldloc.s  0xE
0x4b8  brfalse.s loc_4BD
0x4ba  ldloc.s  0xE
0x4bc  stloc.3
0x4bd  ldarg.s  4
0x4bf  ldloc.3
0x4c0  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::IsValidIdentifier(string)
0x4c5  brtrue.s loc_4E1
0x4c7  ldstr    aInvalididentif// "InvalidIdentifier"
0x4cc  ldc.i4.1
0x4cd  newarr   [mscorlib]System.Object
0x4d2  dup
0x4d3  ldc.i4.0
0x4d4  ldloc.3
0x4d5  stelem.ref
0x4d6  call     string System.Design.SR::GetString(string name, object[] args)
0x4db  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4e0  throw
0x4e1  ldarg.2
0x4e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e7  brtrue.s loc_506
0x4e9  ldarg.s  4
0x4eb  ldarg.2
0x4ec  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::IsValidIdentifier(string)
0x4f1  brtrue.s loc_506
0x4f3  ldarg.2
0x4f4  ldarg.s  4
0x4f6  ldc.i4.1
0x4f7  call     string System.Resources.Tools.StronglyTypedResourceBuilder::VerifyResourceName(string key, class [System]System.CodeDom.Compiler.CodeDomProvider provider, bool isNameSpace)
0x4fc  stloc.s  0xF
0x4fe  ldloc.s  0xF
0x500  brfalse.s loc_506
0x502  ldloc.s  0xF
0x504  starg.s  2
0x506  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x50b  stloc.s  4
0x50d  ldloc.s  4
0x50f  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0x514  ldstr    aSystemDll// "System.dll"
0x519  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x51e  pop
0x51f  ldloc.s  4
0x521  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x526  ldstr    aAllowlatebound// "AllowLateBound"
0x52b  ldc.i4.0
0x52c  box      [mscorlib]System.Boolean
0x531  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x536  ldloc.s  4
0x538  callvirt instance class [mscorlib]System.Collections.IDictionary [System]System.CodeDom.CodeObject::get_UserData()
0x53d  ldstr    aRequirevariabl// "RequireVariableDeclaration"
0x542  ldc.i4.1
0x543  box      [mscorlib]System.Boolean
0x548  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x54d  ldarg.2
0x54e  newobj   instance void [System]System.CodeDom.CodeNamespace::.ctor(string)
0x553  stloc.s  5
0x555  ldloc.s  5
0x557  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x55c  ldstr    aSystem// "System"
0x561  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x566  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x56b  ldloc.s  4
0x56d  callvirt instance class [System]System.CodeDom.CodeNamespaceCollection [System]System.CodeDom.CodeCompileUnit::get_Namespaces()
0x572  ldloc.s  5
0x574  callvirt instance int32 [System]System.CodeDom.CodeNamespaceCollection::Add(class [System]System.CodeDom.CodeNamespace)
0x579  pop
0x57a  ldloc.3
0x57b  newobj   instance void [System]System.CodeDom.CodeTypeDeclaration::.ctor(string)
0x580  stloc.s  6
0x582  ldloc.s  5
0x584  callvirt instance class [System]System.CodeDom.CodeTypeDeclarationCollection [System]System.CodeDom.CodeNamespace::get_Types()
0x589  ldloc.s  6
0x58b  callvirt instance int32 [System]System.CodeDom.CodeTypeDeclarationCollection::Add(class [System]System.CodeDom.CodeTypeDeclaration)
0x590  pop
0x591  ldloc.s  6
0x593  call     void System.Resources.Tools.StronglyTypedResourceBuilder::AddGeneratedCodeAttributeforMember(class [System]System.CodeDom.CodeTypeMember typeMember)
0x598  ldarg.s  5
0x59a  brtrue.s loc_59F
0x59c  ldc.i4.1
0x59d  br.s     loc_5A0
0x59f  ldc.i4.0
0x5a0  stloc.s  7
0x5a2  ldloc.s  6
0x5a4  ldloc.s  7
0x5a6  callvirt instance void [System]System.CodeDom.CodeTypeDeclaration::set_TypeAttributes(valuetype [mscorlib]System.Reflection.TypeAttributes)
0x5ab  ldloc.s  6
0x5ad  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x5b2  ldstr    aSummary// "<summary>"
0x5b7  ldc.i4.1
0x5b8  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x5bd  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x5c2  pop
0x5c3  ldloc.s  6
0x5c5  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x5ca  ldstr    aClassdoccommen// "ClassDocComment"
0x5cf  call     string System.Design.SR::GetString(string name)
0x5d4  ldc.i4.1
0x5d5  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x5da  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x5df  pop
0x5e0  ldloc.s  6
0x5e2  callvirt instance class [System]System.CodeDom.CodeCommentStatementCollection [System]System.CodeDom.CodeTypeMember::get_Comments()
0x5e7  ldstr    aSummary_0// "</summary>"
0x5ec  ldc.i4.1
0x5ed  newobj   instance void [System]System.CodeDom.CodeCommentStatement::.ctor(string, bool)
0x5f2  callvirt instance int32 [System]System.CodeDom.CodeCommentStatementCollection::Add(class [System]System.CodeDom.CodeCommentStatement)
0x5f7  pop
0x5f8  ldtoken  [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute
0x5fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x602  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x607  stloc.s  8
0x609  ldloc.s  8
0x60b  ldc.i4.1
0x60c  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0x611  ldloc.s  6
0x613  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x618  ldloc.s  8
0x61a  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(class [System]System.CodeDom.CodeTypeReference)
0x61f  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x624  pop
0x625  ldtoken  [mscorlib]System.Runtime.CompilerServices.CompilerGeneratedAttribute
0x62a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x62f  newobj   instance void [System]System.CodeDom.CodeTypeReference::.ctor(class [mscorlib]System.Type)
0x634  stloc.s  9
0x636  ldloc.s  9
0x638  ldc.i4.1
0x639  callvirt instance void [System]System.CodeDom.CodeTypeReference::set_Options(valuetype [System]System.CodeDom.CodeTypeReferenceOptions)
0x63e  ldloc.s  6
0x640  callvirt instance class [System]System.CodeDom.CodeAttributeDeclarationCollection [System]System.CodeDom.CodeTypeMember::get_CustomAttributes()
0x645  ldloc.s  9
0x647  newobj   instance void [System]System.CodeDom.CodeAttributeDeclaration::.ctor(class [System]System.CodeDom.CodeTypeReference)
0x64c  callvirt instance int32 [System]System.CodeDom.CodeAttributeDeclarationCollection::Add(class [System]System.CodeDom.CodeAttributeDeclaration)
0x651  pop
0x652  ldarg.s  5
0x654  brtrue.s loc_664
0x656  ldarg.s  4
0x658  ldc.i4   0x40000
0x65d  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::Supports(valuetype [System]System.CodeDom.Compiler.GeneratorSupport)
0x662  br.s     loc_665
0x664  ldc.i4.1
0x665  stloc.s  0xA
0x667  ldarg.s  4
0x669  ldc.i4.s 0x20
0x66b  callvirt instance bool [System]System.CodeDom.Compiler.CodeDomProvider::Supports(valuetype [System]System.CodeDom.Compiler.GeneratorSupport)
0x670  stloc.s  0xB
0x672  ldarg.s  4
0x674  isinst   System.Resources.Tools.ITargetAwareCodeDomProvider
0x679  stloc.s  0xC
0x67b  ldloc.s  0xC
0x67d  brfalse.s loc_69B
0x67f  ldloc.s  0xC
0x681  ldtoken  [mscorlib]System.Type
0x686  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68b  ldstr    aAssembly// "Assembly"
0x690  ldc.i4.0
0x691  callvirt instance bool System.Resources.Tools.ITargetAwareCodeDomProvider::SupportsProperty(class [mscorlib]System.Type type, string propertyName, bool isWritable)
0x696  ldc.i4.0
0x697  ceq
0x699  br.s     loc_69C
0x69b  ldc.i4.0
0x69c  stloc.s  0xD
0x69e  ldloc.s  0xD
0x6a0  brfalse.s loc_6B8
0x6a2  ldloc.s  5
0x6a4  callvirt instance class [System]System.CodeDom.CodeNamespaceImportCollection [System]System.CodeDom.CodeNamespace::get_Imports()
0x6a9  ldstr    aSystemReflecti// "System.Reflection"
0x6ae  newobj   instance void [System]System.CodeDom.CodeNamespaceImport::.ctor(string)
0x6b3  callvirt instance void [System]System.CodeDom.CodeNamespaceImportCollection::Add(class [System]System.CodeDom.CodeNamespaceImport)
0x6b8  ldloc.s  6
0x6ba  ldarg.2
0x6bb  ldarg.1
0x6bc  ldarg.3
0x6bd  ldarg.s  5
0x6bf  ldloc.s  0xA
0x6c1  ldloc.s  0xB
0x6c3  ldloc.s  0xD
0x6c5  call     void System.Resources.Tools.StronglyTypedResourceBuilder::EmitBasicClassMembers(class [System]System.CodeDom.CodeTypeDeclaration srClass, string nameSpace, string baseName, string resourcesNamespace, bool internalClass, bool useStatic, bool supportsTryCatch, bool useTypeInfo)
0x6ca  ldloc.1
0x6cb  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.SortedList::GetEnumerator()
0x6d0  stloc.s  0x10
0x6d2  br.s     loc_736
0x6d4  ldloc.s  0x10
0x6d6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6db  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x6e0  stloc.s  0x11
0x6e2  ldloca.s 0x11
0x6e4  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x6e9  castclass [mscorlib]System.String
0x6ee  stloc.s  0x12
0x6f0  ldloc.2
0x6f1  ldloc.s  0x12
0x6f3  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x6f8  castclass [mscorlib]System.String
0x6fd  stloc.s  0x13
0x6ff  ldloc.s  0x13
0x701  brtrue.s loc_707
0x703  ldloc.s  0x12
0x705  stloc.s  0x13
0x707  ldloc.s  0x12
0x709  ldloc.s  0x13
0x70b  ldloca.s 0x11
0x70d  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x712  castclass ResourceData
0x717  ldloc.s  6
0x719  ldarg.s  5
0x71b  ldloc.s  0xA
0x71d  call     bool System.Resources.Tools.StronglyTypedResourceBuilder::DefineResourceFetchingProperty(string propertyName, string resourceName, class ResourceData data, class [System]System.CodeDom.CodeTypeDeclaration srClass, bool internalClass, bool useStatic)
0x722  stloc.s  0x14
0x724  ldloc.s  0x14
0x726  brtrue.s loc_736
0x728  ldloc.0
0x729  ldloca.s 0x11
0x72b  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x730  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x735  pop
0x736  ldloc.s  0x10
0x738  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x73d  brtrue.s loc_6D4
0x73f  leave.s  loc_756
0x741  ldloc.s  0x10
0x743  isinst   [mscorlib]System.IDisposable
0x748  stloc.s  0x15
0x74a  ldloc.s  0x15
0x74c  brfalse.s loc_755
0x74e  ldloc.s  0x15
0x750  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x755  endfinally
0x756  ldarg.s  6
0x758  ldloc.0
0x759  ldtoken  [mscorlib]System.String
0x75e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x763  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x768  castclass string[]
0x76d  stind.ref
0x76e  ldloc.s  4
0x770  call     void [System]System.CodeDom.Compiler.CodeGenerator::ValidateIdentifiers(class [System]System.CodeDom.CodeObject)
0x775  ldloc.s  4
0x777  ret
```
