# System.Xml.Xsl.XslCompiledTransform::Load_5

- ea: `0xecb50`
- end: `0xecca3`
- name: `System.Xml.Xsl.XslCompiledTransform::Load_5`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x622f0`
- `0xec800`
- `0xecb50`
- `0xeccb0`
- `0xf24f0`

## string_xrefs

- `0xecb5f`: `compiledStylesheet`
- `0xecbef`: `compiledStylesheet`
- `0xecc97`: `compiledStylesheet`
- `0xecbce`: `Xslt_IncompatibleCompiledStylesheetVersion`
- `0xecc7e`: `Xslt_NotCompiledStylesheet`

## pseudocode

```c

```

## disassembly

```asm
0xecb50  ldarg.0
0xecb51  call     instance void System.Xml.Xsl.XslCompiledTransform::Reset()
0xecb56  ldarg.1
0xecb57  ldnull
0xecb58  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xecb5d  brfalse.s loc_ECB6A
0xecb5f  ldstr    aCompiledstyles// "compiledStylesheet"
0xecb64  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xecb69  throw
0xecb6a  ldarg.1
0xecb6b  ldtoken  [System]System.CodeDom.Compiler.GeneratedCodeAttribute
0xecb70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xecb75  ldc.i4.0
0xecb76  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0xecb7b  stloc.0
0xecb7c  ldloc.0
0xecb7d  ldlen
0xecb7e  brtrue.s loc_ECB83
0xecb80  ldnull
0xecb81  br.s     loc_ECB8B
0xecb83  ldloc.0
0xecb84  ldc.i4.0
0xecb85  ldelem.ref
0xecb86  castclass [System]System.CodeDom.Compiler.GeneratedCodeAttribute
0xecb8b  stloc.1
0xecb8c  ldloc.1
0xecb8d  brfalse  loc_ECC76
0xecb92  ldloc.1
0xecb93  callvirt instance string [System]System.CodeDom.Compiler.GeneratedCodeAttribute::get_Tool()
0xecb98  ldtoken  System.Xml.Xsl.XslCompiledTransform
0xecb9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xecba2  callvirt instance string [mscorlib]System.Type::get_FullName()
0xecba7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xecbac  brfalse  loc_ECC76
0xecbb1  ldstr    a4000// "4.0.0.0"
0xecbb6  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xecbbb  ldloc.1
0xecbbc  callvirt instance string [System]System.CodeDom.Compiler.GeneratedCodeAttribute::get_Version()
0xecbc1  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xecbc6  call     instance int32 [mscorlib]System.Version::CompareTo(class [mscorlib]System.Version)
0xecbcb  ldc.i4.0
0xecbcc  bge.s    loc_ECBFA
0xecbce  ldstr    aXsltIncompatib// "Xslt_IncompatibleCompiledStylesheetVers"...
0xecbd3  ldc.i4.2
0xecbd4  newarr   [mscorlib]System.Object
0xecbd9  dup
0xecbda  ldc.i4.0
0xecbdb  ldloc.1
0xecbdc  callvirt instance string [System]System.CodeDom.Compiler.GeneratedCodeAttribute::get_Version()
0xecbe1  stelem.ref
0xecbe2  dup
0xecbe3  ldc.i4.1
0xecbe4  ldstr    a4000// "4.0.0.0"
0xecbe9  stelem.ref
0xecbea  call     string System.Xml.Res::GetString(string name, object[] args)
0xecbef  ldstr    aCompiledstyles// "compiledStylesheet"
0xecbf4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xecbf9  throw
0xecbfa  ldarg.1
0xecbfb  ldstr    aStaticdata// "staticData"
0xecc00  ldc.i4.s 0x28
0xecc02  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xecc07  stloc.2
0xecc08  ldarg.1
0xecc09  ldstr    aEbtypes// "ebTypes"
0xecc0e  ldc.i4.s 0x28
0xecc10  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xecc15  stloc.3
0xecc16  ldloc.2
0xecc17  ldnull
0xecc18  call     bool [mscorlib]System.Reflection.FieldInfo::op_Inequality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0xecc1d  brfalse.s loc_ECC76
0xecc1f  ldloc.3
0xecc20  ldnull
0xecc21  call     bool [mscorlib]System.Reflection.FieldInfo::op_Inequality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0xecc26  brfalse.s loc_ECC76
0xecc28  call     bool System.Xml.XmlConfiguration.XsltConfigSection::get_EnableMemberAccessForXslCompiledTransform()
0xecc2d  brfalse.s loc_ECC3A
0xecc2f  ldc.i4.2
0xecc30  newobj   instance void [mscorlib]System.Security.Permissions.ReflectionPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.ReflectionPermissionFlag)
0xecc35  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0xecc3a  ldloc.2
0xecc3b  ldnull
0xecc3c  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xecc41  isinst   unsigned int8[]
0xecc46  stloc.s  4
0xecc48  ldloc.s  4
0xecc4a  brfalse.s loc_ECC76
0xecc4c  ldarg.1
0xecc4d  ldstr    aExecute// "Execute"
0xecc52  ldc.i4.s 0x28
0xecc54  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xecc59  stloc.s  5
0xecc5b  ldloc.3
0xecc5c  ldnull
0xecc5d  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xecc62  castclass class [mscorlib]System.Type[]
0xecc67  stloc.s  6
0xecc69  ldarg.0
0xecc6a  ldloc.s  5
0xecc6c  ldloc.s  4
0xecc6e  ldloc.s  6
0xecc70  call     instance void System.Xml.Xsl.XslCompiledTransform::Load(class [mscorlib]System.Reflection.MethodInfo executeMethod, unsigned int8[] queryData, class [mscorlib]System.Type[] earlyBoundTypes)
0xecc75  ret
0xecc76  ldarg.0
0xecc77  ldfld    class [System.Data.SqlXml]System.Xml.Xsl.XmlILCommand System.Xml.Xsl.XslCompiledTransform::command
0xecc7c  brtrue.s loc_ECCA2
0xecc7e  ldstr    aXsltNotcompile// "Xslt_NotCompiledStylesheet"
0xecc83  ldc.i4.1
0xecc84  newarr   [mscorlib]System.Object
0xecc89  dup
0xecc8a  ldc.i4.0
0xecc8b  ldarg.1
0xecc8c  callvirt instance string [mscorlib]System.Type::get_FullName()
0xecc91  stelem.ref
0xecc92  call     string System.Xml.Res::GetString(string name, object[] args)
0xecc97  ldstr    aCompiledstyles// "compiledStylesheet"
0xecc9c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xecca1  throw
0xecca2  ret
```
