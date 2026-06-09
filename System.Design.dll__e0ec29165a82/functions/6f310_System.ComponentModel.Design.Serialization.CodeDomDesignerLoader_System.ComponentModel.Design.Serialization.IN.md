# System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::System.ComponentModel.Design.Serialization.INameCreationService.ValidateName

- ea: `0x6f310`
- end: `0x6f473`
- name: `System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::System.ComponentModel.Design.Serialization.INameCreationService.ValidateName`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x6cdf0`
- `0x6ce30`
- `0x6df30`
- `0x6f310`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x6f448`: `CodeDomDesignerLoaderDupComponentName`
- `0x6f465`: `CodeDomDesignerLoaderDupComponentName`

## pseudocode

```c

```

## disassembly

```asm
0x6f310  ldarg.1
0x6f311  brtrue.s loc_6F31E
0x6f313  ldstr    aName// "name"
0x6f318  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6f31d  throw
0x6f31e  ldarg.1
0x6f31f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6f324  brtrue.s loc_6F343
0x6f326  ldstr    aCodedomdesigne_8// "CodeDomDesignerLoaderInvalidBlankIdenti"...
0x6f32b  call     string System.Design.SR::GetString(string name)
0x6f330  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6f335  stloc.0
0x6f336  ldloc.0
0x6f337  ldstr    aCodedomdesigne_9// "CodeDomDesignerLoaderInvalidIdentifier"
0x6f33c  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6f341  ldloc.0
0x6f342  throw
0x6f343  ldarg.0
0x6f344  ldfld    class [System]System.CodeDom.Compiler.ICodeGenerator System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_codeGenerator
0x6f349  brtrue.s loc_6F361
0x6f34b  ldarg.0
0x6f34c  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::get_CodeDomProvider()
0x6f351  stloc.1
0x6f352  ldloc.1
0x6f353  brfalse.s loc_6F361
0x6f355  ldarg.0
0x6f356  ldloc.1
0x6f357  callvirt instance class [System]System.CodeDom.Compiler.ICodeGenerator [System]System.CodeDom.Compiler.CodeDomProvider::CreateGenerator()
0x6f35c  stfld    class [System]System.CodeDom.Compiler.ICodeGenerator System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_codeGenerator
0x6f361  ldarg.0
0x6f362  ldfld    class [System]System.CodeDom.Compiler.ICodeGenerator System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_codeGenerator
0x6f367  brfalse.s loc_6F3B5
0x6f369  ldarg.0
0x6f36a  ldfld    class [System]System.CodeDom.Compiler.ICodeGenerator System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_codeGenerator
0x6f36f  ldarg.1
0x6f370  callvirt instance void [System]System.CodeDom.Compiler.ICodeGenerator::ValidateIdentifier(string)
0x6f375  ldarg.0
0x6f376  ldfld    class [System]System.CodeDom.Compiler.ICodeGenerator System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_codeGenerator
0x6f37b  ldarg.1
0x6f37c  ldstr    asc_12C5B2// "_"
0x6f381  call     string [mscorlib]System.String::Concat(string, string)
0x6f386  callvirt instance void [System]System.CodeDom.Compiler.ICodeGenerator::ValidateIdentifier(string)
0x6f38b  leave.s  loc_6F3B5
0x6f38d  pop
0x6f38e  ldstr    aCodedomdesigne_9// "CodeDomDesignerLoaderInvalidIdentifier"
0x6f393  ldc.i4.1
0x6f394  newarr   [mscorlib]System.Object
0x6f399  dup
0x6f39a  ldc.i4.0
0x6f39b  ldarg.1
0x6f39c  stelem.ref
0x6f39d  call     string System.Design.SR::GetString(string name, object[] args)
0x6f3a2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6f3a7  stloc.2
0x6f3a8  ldloc.2
0x6f3a9  ldstr    aCodedomdesigne_9// "CodeDomDesignerLoaderInvalidIdentifier"
0x6f3ae  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6f3b3  ldloc.2
0x6f3b4  throw
0x6f3b5  ldarg.0
0x6f3b6  callvirt instance bool [System]System.ComponentModel.Design.Serialization.DesignerLoader::get_Loading()
0x6f3bb  brtrue   loc_6F472
0x6f3c0  ldc.i4.0
0x6f3c1  stloc.3
0x6f3c2  ldarg.0
0x6f3c3  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::_documentType
0x6f3c8  stloc.s  4
0x6f3ca  ldloc.s  4
0x6f3cc  brfalse.s loc_6F420
0x6f3ce  ldloc.s  4
0x6f3d0  callvirt instance class [System]System.CodeDom.CodeTypeMemberCollection [System]System.CodeDom.CodeTypeDeclaration::get_Members()
0x6f3d5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6f3da  stloc.s  5
0x6f3dc  br.s     loc_6F400
0x6f3de  ldloc.s  5
0x6f3e0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6f3e5  castclass [System]System.CodeDom.CodeTypeMember
0x6f3ea  stloc.s  6
0x6f3ec  ldloc.s  6
0x6f3ee  callvirt instance string [System]System.CodeDom.CodeTypeMember::get_Name()
0x6f3f3  ldarg.1
0x6f3f4  ldc.i4.5
0x6f3f5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x6f3fa  brfalse.s loc_6F400
0x6f3fc  ldc.i4.1
0x6f3fd  stloc.3
0x6f3fe  leave.s  loc_6F420
0x6f400  ldloc.s  5
0x6f402  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6f407  brtrue.s loc_6F3DE
0x6f409  leave.s  loc_6F420
0x6f40b  ldloc.s  5
0x6f40d  isinst   [mscorlib]System.IDisposable
0x6f412  stloc.s  7
0x6f414  ldloc.s  7
0x6f416  brfalse.s loc_6F41F
0x6f418  ldloc.s  7
0x6f41a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f41f  endfinally
0x6f420  ldloc.3
0x6f421  brtrue.s loc_6F445
0x6f423  ldarg.0
0x6f424  callvirt instance bool System.ComponentModel.Design.Serialization.BasicDesignerLoader::get_Modified()
0x6f429  brfalse.s loc_6F445
0x6f42b  ldarg.0
0x6f42c  call     instance class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::get_LoaderHost()
0x6f431  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.Design.IDesignerHost::get_Container()
0x6f436  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x6f43b  ldarg.1
0x6f43c  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.ComponentCollection::get_Item(string)
0x6f441  brfalse.s loc_6F445
0x6f443  ldc.i4.1
0x6f444  stloc.3
0x6f445  ldloc.3
0x6f446  brfalse.s loc_6F472
0x6f448  ldstr    aCodedomdesigne_10// "CodeDomDesignerLoaderDupComponentName"
0x6f44d  ldc.i4.1
0x6f44e  newarr   [mscorlib]System.Object
0x6f453  dup
0x6f454  ldc.i4.0
0x6f455  ldarg.1
0x6f456  stelem.ref
0x6f457  call     string System.Design.SR::GetString(string name, object[] args)
0x6f45c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6f461  stloc.s  8
0x6f463  ldloc.s  8
0x6f465  ldstr    aCodedomdesigne_10// "CodeDomDesignerLoaderDupComponentName"
0x6f46a  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6f46f  ldloc.s  8
0x6f471  throw
0x6f472  ret
```
