# System.Xml.Serialization.TypeScope::GetDefaultIndexer

- ea: `0x74cd0`
- end: `0x74e56`
- name: `System.Xml.Serialization.TypeScope::GetDefaultIndexer`
- size: `390`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x74e60`
- `0xa39d0`

## callees

- `0x622f0`
- `0x74cd0`

## string_xrefs

- `0x74e24`: `XmlNoAddMethod`
- `0x74ce5`: `XmlUnsupportedIDictionary`
- `0x74d04`: `XmlUnsupportedIDictionaryDetails`
- `0x74de1`: `XmlNoDefaultAccessors`

## pseudocode

```c

```

## disassembly

```asm
0x74cd0  ldtoken  [mscorlib]System.Collections.IDictionary
0x74cd5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74cda  ldarg.0
0x74cdb  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x74ce0  brfalse.s loc_74D27
0x74ce2  ldarg.1
0x74ce3  brtrue.s loc_74D04
0x74ce5  ldstr    aXmlunsupported_6// "XmlUnsupportedIDictionary"
0x74cea  ldc.i4.1
0x74ceb  newarr   [mscorlib]System.Object
0x74cf0  dup
0x74cf1  ldc.i4.0
0x74cf2  ldarg.0
0x74cf3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74cf8  stelem.ref
0x74cf9  call     string System.Xml.Res::GetString(string name, object[] args)
0x74cfe  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x74d03  throw
0x74d04  ldstr    aXmlunsupported_7// "XmlUnsupportedIDictionaryDetails"
0x74d09  ldc.i4.2
0x74d0a  newarr   [mscorlib]System.Object
0x74d0f  dup
0x74d10  ldc.i4.0
0x74d11  ldarg.1
0x74d12  stelem.ref
0x74d13  dup
0x74d14  ldc.i4.1
0x74d15  ldarg.0
0x74d16  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74d1b  stelem.ref
0x74d1c  call     string System.Xml.Res::GetString(string name, object[] args)
0x74d21  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x74d26  throw
0x74d27  ldarg.0
0x74d28  callvirt instance class [mscorlib]System.Reflection.MemberInfo[] [mscorlib]System.Type::GetDefaultMembers()
0x74d2d  stloc.0
0x74d2e  ldnull
0x74d2f  stloc.1
0x74d30  ldloc.0
0x74d31  brfalse  loc_74DD8
0x74d36  ldloc.0
0x74d37  ldlen
0x74d38  brfalse  loc_74DD8
0x74d3d  ldarg.0
0x74d3e  stloc.3
0x74d3f  br       loc_74DCC
0x74d44  ldc.i4.0
0x74d45  stloc.s  4
0x74d47  br.s     loc_74DB5
0x74d49  ldloc.0
0x74d4a  ldloc.s  4
0x74d4c  ldelem.ref
0x74d4d  isinst   [mscorlib]System.Reflection.PropertyInfo
0x74d52  brfalse.s loc_74DAF
0x74d54  ldloc.0
0x74d55  ldloc.s  4
0x74d57  ldelem.ref
0x74d58  castclass [mscorlib]System.Reflection.PropertyInfo
0x74d5d  stloc.s  5
0x74d5f  ldloc.s  5
0x74d61  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x74d66  ldloc.3
0x74d67  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74d6c  brtrue.s loc_74DAF
0x74d6e  ldloc.s  5
0x74d70  callvirt instance bool [mscorlib]System.Reflection.PropertyInfo::get_CanRead()
0x74d75  brfalse.s loc_74DAF
0x74d77  ldloc.s  5
0x74d79  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.PropertyInfo::GetGetMethod()
0x74d7e  stloc.s  6
0x74d80  ldloc.s  6
0x74d82  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x74d87  stloc.s  7
0x74d89  ldloc.s  7
0x74d8b  ldlen
0x74d8c  conv.i4
0x74d8d  ldc.i4.1
0x74d8e  bne.un.s loc_74DAF
0x74d90  ldloc.s  7
0x74d92  ldc.i4.0
0x74d93  ldelem.ref
0x74d94  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x74d99  ldtoken  [mscorlib]System.Int32
0x74d9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74da3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74da8  brfalse.s loc_74DAF
0x74daa  ldloc.s  5
0x74dac  stloc.1
0x74dad  br.s     loc_74DBC
0x74daf  ldloc.s  4
0x74db1  ldc.i4.1
0x74db2  add
0x74db3  stloc.s  4
0x74db5  ldloc.s  4
0x74db7  ldloc.0
0x74db8  ldlen
0x74db9  conv.i4
0x74dba  blt.s    loc_74D49
0x74dbc  ldloc.1
0x74dbd  ldnull
0x74dbe  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x74dc3  brtrue.s loc_74DD8
0x74dc5  ldloc.3
0x74dc6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x74dcb  stloc.3
0x74dcc  ldloc.3
0x74dcd  ldnull
0x74dce  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74dd3  brtrue   loc_74D44
0x74dd8  ldloc.1
0x74dd9  ldnull
0x74dda  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x74ddf  brfalse.s loc_74E00
0x74de1  ldstr    aXmlnodefaultac// "XmlNoDefaultAccessors"
0x74de6  ldc.i4.1
0x74de7  newarr   [mscorlib]System.Object
0x74dec  dup
0x74ded  ldc.i4.0
0x74dee  ldarg.0
0x74def  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74df4  stelem.ref
0x74df5  call     string System.Xml.Res::GetString(string name, object[] args)
0x74dfa  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x74dff  throw
0x74e00  ldarg.0
0x74e01  ldstr    aAdd// "Add"
0x74e06  ldc.i4.1
0x74e07  newarr   [mscorlib]System.Type
0x74e0c  dup
0x74e0d  ldc.i4.0
0x74e0e  ldloc.1
0x74e0f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x74e14  stelem.ref
0x74e15  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x74e1a  stloc.2
0x74e1b  ldloc.2
0x74e1c  ldnull
0x74e1d  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x74e22  brfalse.s loc_74E54
0x74e24  ldstr    aXmlnoaddmethod// "XmlNoAddMethod"
0x74e29  ldc.i4.3
0x74e2a  newarr   [mscorlib]System.Object
0x74e2f  dup
0x74e30  ldc.i4.0
0x74e31  ldarg.0
0x74e32  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74e37  stelem.ref
0x74e38  dup
0x74e39  ldc.i4.1
0x74e3a  ldloc.1
0x74e3b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x74e40  stelem.ref
0x74e41  dup
0x74e42  ldc.i4.2
0x74e43  ldstr    aIcollection// "ICollection"
0x74e48  stelem.ref
0x74e49  call     string System.Xml.Res::GetString(string name, object[] args)
0x74e4e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x74e53  throw
0x74e54  ldloc.1
0x74e55  ret
```
