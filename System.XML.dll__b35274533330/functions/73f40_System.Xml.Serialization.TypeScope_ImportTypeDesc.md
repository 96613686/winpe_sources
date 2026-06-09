# System.Xml.Serialization.TypeScope::ImportTypeDesc

- ea: `0x73f40`
- end: `0x744e9`
- name: `System.Xml.Serialization.TypeScope::ImportTypeDesc`
- size: `1449`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x73dc0`
- `0x73e30`

## callees

- `0x622f0`
- `0x654e0`
- `0x72b10`
- `0x72d10`
- `0x72da0`
- `0x72df0`
- `0x72e00`
- `0x72e20`
- `0x72e80`
- `0x72f60`
- `0x72fe0`
- `0x730c0`
- `0x73db0`
- `0x73dc0`
- `0x73f40`
- `0x744f0`
- `0x74510`
- `0x74540`
- `0x74a90`
- `0x74b00`
- `0x74e60`
- `0xa2e70`

## string_xrefs

- `0x7402d`: `XmlSerializerUnsupportedType`
- `0x74180`: `XmlSerializerUnsupportedType`
- `0x74358`: `XmlSerializerUnsupportedType`
- `0x73f66`: `XmlTypeInaccessible`
- `0x73fa5`: `XmlTypeStatic`
- `0x740ba`: `XmlUnsupportedRank`
- `0x742e6`: `XmlUnsupportedInterface`
- `0x74308`: `XmlUnsupportedInterfaceDetails`

## pseudocode

```c

```

## disassembly

```asm
0x73f40  ldnull
0x73f41  stloc.0
0x73f42  ldnull
0x73f43  stloc.2
0x73f44  ldnull
0x73f45  stloc.3
0x73f46  ldc.i4.0
0x73f47  stloc.s  4
0x73f49  ldnull
0x73f4a  stloc.s  5
0x73f4c  ldarg.1
0x73f4d  callvirt instance bool [mscorlib]System.Type::get_IsPublic()
0x73f52  brtrue.s loc_73F88
0x73f54  ldarg.1
0x73f55  callvirt instance bool [mscorlib]System.Type::get_IsNestedPublic()
0x73f5a  brtrue.s loc_73F88
0x73f5c  ldloc.s  4
0x73f5e  ldc.i4   0x100000
0x73f63  or
0x73f64  stloc.s  4
0x73f66  ldstr    aXmltypeinacces// "XmlTypeInaccessible"
0x73f6b  ldc.i4.1
0x73f6c  newarr   [mscorlib]System.Object
0x73f71  dup
0x73f72  ldc.i4.0
0x73f73  ldarg.1
0x73f74  callvirt instance string [mscorlib]System.Type::get_FullName()
0x73f79  stelem.ref
0x73f7a  call     string System.Xml.Res::GetString(string name, object[] args)
0x73f7f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x73f84  stloc.s  5
0x73f86  br.s     loc_73FC5
0x73f88  ldarg.3
0x73f89  brfalse.s loc_73FC5
0x73f8b  ldarg.1
0x73f8c  callvirt instance bool [mscorlib]System.Type::get_IsAbstract()
0x73f91  brfalse.s loc_73FC5
0x73f93  ldarg.1
0x73f94  callvirt instance bool [mscorlib]System.Type::get_IsSealed()
0x73f99  brfalse.s loc_73FC5
0x73f9b  ldloc.s  4
0x73f9d  ldc.i4   0x100000
0x73fa2  or
0x73fa3  stloc.s  4
0x73fa5  ldstr    aXmltypestatic// "XmlTypeStatic"
0x73faa  ldc.i4.1
0x73fab  newarr   [mscorlib]System.Object
0x73fb0  dup
0x73fb1  ldc.i4.0
0x73fb2  ldarg.1
0x73fb3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x73fb8  stelem.ref
0x73fb9  call     string System.Xml.Res::GetString(string name, object[] args)
0x73fbe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x73fc3  stloc.s  5
0x73fc5  ldarg.1
0x73fc6  call     bool System.Xml.Serialization.DynamicAssemblies::IsTypeDynamic(class [mscorlib]System.Type type)
0x73fcb  brfalse.s loc_73FD7
0x73fcd  ldloc.s  4
0x73fcf  ldc.i4   0x4000
0x73fd4  or
0x73fd5  stloc.s  4
0x73fd7  ldarg.1
0x73fd8  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x73fdd  brtrue.s loc_73FE5
0x73fdf  ldloc.s  4
0x73fe1  ldc.i4.2
0x73fe2  or
0x73fe3  stloc.s  4
0x73fe5  ldarg.1
0x73fe6  ldtoken  [mscorlib]System.Object
0x73feb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73ff0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x73ff5  brfalse.s loc_74008
0x73ff7  ldc.i4.0
0x73ff8  stloc.1
0x73ff9  ldloc.s  4
0x73ffb  ldc.i4   0x800
0x74000  or
0x74001  stloc.s  4
0x74003  br       loc_74378
0x74008  ldarg.1
0x74009  ldtoken  [mscorlib]System.ValueType
0x7400e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74013  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74018  brfalse.s loc_74052
0x7401a  ldc.i4.2
0x7401b  stloc.1
0x7401c  ldloc.s  4
0x7401e  ldc.i4   0x100000
0x74023  or
0x74024  stloc.s  4
0x74026  ldloc.s  5
0x74028  brtrue   loc_74378
0x7402d  ldstr    aXmlserializeru// "XmlSerializerUnsupportedType"
0x74032  ldc.i4.1
0x74033  newarr   [mscorlib]System.Object
0x74038  dup
0x74039  ldc.i4.0
0x7403a  ldarg.1
0x7403b  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74040  stelem.ref
0x74041  call     string System.Xml.Res::GetString(string name, object[] args)
0x74046  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7404b  stloc.s  5
0x7404d  br       loc_74378
0x74052  ldarg.1
0x74053  ldtoken  [mscorlib]System.Void
0x74058  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7405d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74062  brfalse.s loc_7406B
0x74064  ldc.i4.8
0x74065  stloc.1
0x74066  br       loc_74378
0x7406b  ldtoken  System.Xml.Serialization.IXmlSerializable
0x74070  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74075  ldarg.1
0x74076  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x7407b  brfalse.s loc_74099
0x7407d  ldc.i4.s 0xB
0x7407f  stloc.1
0x74080  ldloc.s  4
0x74082  ldc.i4.s 0x24
0x74084  or
0x74085  stloc.s  4
0x74087  ldloc.s  4
0x74089  ldarg.1
0x7408a  ldloca.s 5
0x7408c  call     valuetype System.Xml.Serialization.TypeFlags System.Xml.Serialization.TypeScope::GetConstructorFlags(class [mscorlib]System.Type type, class [mscorlib]System.Exception& exception)
0x74091  or
0x74092  stloc.s  4
0x74094  br       loc_74378
0x74099  ldarg.1
0x7409a  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x7409f  brfalse.s loc_740F0
0x740a1  ldc.i4.5
0x740a2  stloc.1
0x740a3  ldarg.1
0x740a4  callvirt instance int32 [mscorlib]System.Type::GetArrayRank()
0x740a9  ldc.i4.1
0x740aa  ble.s    loc_740DA
0x740ac  ldloc.s  4
0x740ae  ldc.i4   0x100000
0x740b3  or
0x740b4  stloc.s  4
0x740b6  ldloc.s  5
0x740b8  brtrue.s loc_740DA
0x740ba  ldstr    aXmlunsupported_3// "XmlUnsupportedRank"
0x740bf  ldc.i4.1
0x740c0  newarr   [mscorlib]System.Object
0x740c5  dup
0x740c6  ldc.i4.0
0x740c7  ldarg.1
0x740c8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x740cd  stelem.ref
0x740ce  call     string System.Xml.Res::GetString(string name, object[] args)
0x740d3  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x740d8  stloc.s  5
0x740da  ldarg.1
0x740db  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x740e0  stloc.2
0x740e1  ldloc.s  4
0x740e3  ldc.i4   0x800
0x740e8  or
0x740e9  stloc.s  4
0x740eb  br       loc_74378
0x740f0  ldtoken  [mscorlib]System.Collections.ICollection
0x740f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x740fa  ldarg.1
0x740fb  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x74100  brfalse.s loc_7414C
0x74102  ldarg.1
0x74103  call     bool System.Xml.Serialization.TypeScope::IsArraySegment(class [mscorlib]System.Type t)
0x74108  brtrue.s loc_7414C
0x7410a  ldc.i4.6
0x7410b  stloc.1
0x7410c  ldarg.1
0x7410d  ldarg.2
0x7410e  ldnull
0x7410f  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0x74114  brtrue.s loc_74133
0x74116  ldarg.2
0x74117  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x7411c  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74121  ldstr    asc_129CEE// "."
0x74126  ldarg.2
0x74127  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7412c  call     string [mscorlib]System.String::Concat(string, string, string)
0x74131  br.s     loc_74134
0x74133  ldnull
0x74134  call     class [mscorlib]System.Type System.Xml.Serialization.TypeScope::GetCollectionElementType(class [mscorlib]System.Type type, string memberInfo)
0x74139  stloc.2
0x7413a  ldloc.s  4
0x7413c  ldarg.1
0x7413d  ldloca.s 5
0x7413f  call     valuetype System.Xml.Serialization.TypeFlags System.Xml.Serialization.TypeScope::GetConstructorFlags(class [mscorlib]System.Type type, class [mscorlib]System.Exception& exception)
0x74144  or
0x74145  stloc.s  4
0x74147  br       loc_74378
0x7414c  ldarg.1
0x7414d  ldtoken  System.Xml.XmlQualifiedName
0x74152  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74157  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7415c  brfalse.s loc_74165
0x7415e  ldc.i4.1
0x7415f  stloc.1
0x74160  br       loc_74378
0x74165  ldarg.1
0x74166  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x7416b  brfalse.s loc_741A5
0x7416d  ldc.i4.1
0x7416e  stloc.1
0x7416f  ldloc.s  4
0x74171  ldc.i4   0x100000
0x74176  or
0x74177  stloc.s  4
0x74179  ldloc.s  5
0x7417b  brtrue   loc_74378
0x74180  ldstr    aXmlserializeru// "XmlSerializerUnsupportedType"
0x74185  ldc.i4.1
0x74186  newarr   [mscorlib]System.Object
0x7418b  dup
0x7418c  ldc.i4.0
0x7418d  ldarg.1
0x7418e  callvirt instance string [mscorlib]System.Type::get_FullName()
0x74193  stelem.ref
0x74194  call     string System.Xml.Res::GetString(string name, object[] args)
0x74199  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7419e  stloc.s  5
0x741a0  br       loc_74378
0x741a5  ldarg.1
0x741a6  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x741ab  brfalse.s loc_741B4
0x741ad  ldc.i4.2
0x741ae  stloc.1
0x741af  br       loc_74378
0x741b4  ldarg.1
0x741b5  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x741ba  brfalse.s loc_741F8
0x741bc  ldc.i4.3
0x741bd  stloc.1
0x741be  ldarg.1
0x741bf  call     bool System.Xml.Serialization.TypeScope::IsOptionalValue(class [mscorlib]System.Type type)
0x741c4  brfalse.s loc_741DB
0x741c6  ldarg.1
0x741c7  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetGenericArguments()
0x741cc  ldc.i4.0
0x741cd  ldelem.ref
0x741ce  stloc.3
0x741cf  ldloc.s  4
0x741d1  ldc.i4   0x10000
0x741d6  or
0x741d7  stloc.s  4
0x741d9  br.s     loc_741E2
0x741db  ldarg.1
0x741dc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x741e1  stloc.3
0x741e2  ldarg.1
0x741e3  callvirt instance bool [mscorlib]System.Type::get_IsAbstract()
0x741e8  brfalse  loc_74378
0x741ed  ldloc.s  4
0x741ef  ldc.i4.1
0x741f0  or
0x741f1  stloc.s  4
0x741f3  br       loc_74378
0x741f8  ldarg.1
0x741f9  callvirt instance bool [mscorlib]System.Type::get_IsClass()
0x741fe  brfalse  loc_742C2
0x74203  ldarg.1
0x74204  ldtoken  System.Xml.XmlAttribute
0x74209  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7420e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x74213  brfalse.s loc_74224
0x74215  ldc.i4.s 0xA
0x74217  stloc.1
0x74218  ldloc.s  4
0x7421a  ldc.i4.s 0xC
0x7421c  or
0x7421d  stloc.s  4
0x7421f  br       loc_74378
0x74224  ldtoken  System.Xml.XmlNode
0x74229  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7422e  ldarg.1
0x7422f  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x74234  brfalse.s loc_742A3
0x74236  ldc.i4.s 9
0x74238  stloc.1
0x74239  ldarg.1
0x7423a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x7423f  stloc.3
0x74240  ldloc.s  4
0x74242  ldc.i4.s 0x34
0x74244  or
0x74245  stloc.s  4
0x74247  ldtoken  System.Xml.XmlText
0x7424c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74251  ldarg.1
0x74252  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x74257  brfalse.s loc_74265
0x74259  ldloc.s  4
  ... truncated ...
```
