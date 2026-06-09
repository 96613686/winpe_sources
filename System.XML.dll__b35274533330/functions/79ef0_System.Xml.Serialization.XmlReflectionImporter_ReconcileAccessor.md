# System.Xml.Serialization.XmlReflectionImporter::ReconcileAccessor

- ea: `0x79ef0`
- end: `0x7a206`
- name: `System.Xml.Serialization.XmlReflectionImporter::ReconcileAccessor`
- size: `790`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x79be0`
- `0x79d20`
- `0x79ec0`
- `0x7c5e0`

## callees

- `0x622f0`
- `0x68600`
- `0x68620`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x68760`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68cd0`
- `0x68d70`
- `0x68e40`
- `0x68e50`
- `0x6b0a0`
- `0x6b100`
- `0x6b120`
- `0x79e80`
- `0x79ef0`

## string_xrefs

- `0x7a011`: `XmlCannotReconcileAccessorDefault`
- `0x7a05b`: `XmlMethodTypeNameConflict`
- `0x7a0a0`: `XmlCannotReconcileAccessor`
- `0x7a1c2`: `XmlCannotReconcileAccessor`
- `0x7a17e`: `XmlCannotReconcileAttributeAccessor`

## pseudocode

```c

```

## disassembly

```asm
0x79ef0  ldarg.1
0x79ef1  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x79ef6  brfalse.s loc_79F07
0x79ef8  ldarg.1
0x79ef9  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x79efe  callvirt instance int32 [mscorlib]System.String::get_Length()
0x79f03  brtrue.s loc_79F07
0x79f05  ldarg.1
0x79f06  ret
0x79f07  ldarg.2
0x79f08  ldarg.1
0x79f09  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x79f0e  ldarg.1
0x79f0f  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x79f14  callvirt instance object System.Xml.Serialization.NameTable::get_Item(string name, string ns)
0x79f19  castclass System.Xml.Serialization.Accessor
0x79f1e  stloc.0
0x79f1f  ldloc.0
0x79f20  brtrue.s loc_79F3E
0x79f22  ldarg.1
0x79f23  ldc.i4.1
0x79f24  callvirt instance void System.Xml.Serialization.Accessor::set_IsTopLevelInSchema(bool value)
0x79f29  ldarg.2
0x79f2a  ldarg.1
0x79f2b  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x79f30  ldarg.1
0x79f31  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x79f36  ldarg.1
0x79f37  callvirt instance void System.Xml.Serialization.NameTable::Add(string name, string ns, object value)
0x79f3c  ldarg.1
0x79f3d  ret
0x79f3e  ldloc.0
0x79f3f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f44  ldarg.1
0x79f45  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f4a  bne.un.s loc_79F4E
0x79f4c  ldloc.0
0x79f4d  ret
0x79f4e  ldarg.1
0x79f4f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f54  isinst   System.Xml.Serialization.MembersMapping
0x79f59  brtrue   loc_7A041
0x79f5e  ldloc.0
0x79f5f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f64  isinst   System.Xml.Serialization.MembersMapping
0x79f69  brtrue   loc_7A041
0x79f6e  ldarg.1
0x79f6f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f74  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79f79  ldloc.0
0x79f7a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f7f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79f84  beq.s    loc_79FE4
0x79f86  ldloc.0
0x79f87  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f8c  isinst   System.Xml.Serialization.NullableMapping
0x79f91  brfalse.s loc_79FB5
0x79f93  ldarg.1
0x79f94  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79f99  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79f9e  ldloc.0
0x79f9f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79fa4  castclass System.Xml.Serialization.NullableMapping
0x79fa9  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.NullableMapping::get_BaseMapping()
0x79fae  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79fb3  beq.s    loc_79FE4
0x79fb5  ldarg.1
0x79fb6  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79fbb  isinst   System.Xml.Serialization.NullableMapping
0x79fc0  brfalse.s loc_7A041
0x79fc2  ldarg.1
0x79fc3  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79fc8  castclass System.Xml.Serialization.NullableMapping
0x79fcd  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.NullableMapping::get_BaseMapping()
0x79fd2  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79fd7  ldloc.0
0x79fd8  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x79fdd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x79fe2  bne.un.s loc_7A041
0x79fe4  ldarg.1
0x79fe5  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x79fea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79fef  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x79ff4  stloc.1
0x79ff5  ldloc.0
0x79ff6  callvirt instance object System.Xml.Serialization.Accessor::get_Default()
0x79ffb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7a000  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x7a005  stloc.2
0x7a006  ldloc.1
0x7a007  ldloc.2
0x7a008  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a00d  brfalse.s loc_7A011
0x7a00f  ldloc.0
0x7a010  ret
0x7a011  ldstr    aXmlcannotrecon// "XmlCannotReconcileAccessorDefault"
0x7a016  ldc.i4.4
0x7a017  newarr   [mscorlib]System.Object
0x7a01c  dup
0x7a01d  ldc.i4.0
0x7a01e  ldarg.1
0x7a01f  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7a024  stelem.ref
0x7a025  dup
0x7a026  ldc.i4.1
0x7a027  ldarg.1
0x7a028  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7a02d  stelem.ref
0x7a02e  dup
0x7a02f  ldc.i4.2
0x7a030  ldloc.1
0x7a031  stelem.ref
0x7a032  dup
0x7a033  ldc.i4.3
0x7a034  ldloc.2
0x7a035  stelem.ref
0x7a036  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a03b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a040  throw
0x7a041  ldarg.1
0x7a042  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a047  isinst   System.Xml.Serialization.MembersMapping
0x7a04c  brtrue.s loc_7A05B
0x7a04e  ldloc.0
0x7a04f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a054  isinst   System.Xml.Serialization.MembersMapping
0x7a059  brfalse.s loc_7A083
0x7a05b  ldstr    aXmlmethodtypen// "XmlMethodTypeNameConflict"
0x7a060  ldc.i4.2
0x7a061  newarr   [mscorlib]System.Object
0x7a066  dup
0x7a067  ldc.i4.0
0x7a068  ldarg.1
0x7a069  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7a06e  stelem.ref
0x7a06f  dup
0x7a070  ldc.i4.1
0x7a071  ldarg.1
0x7a072  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7a077  stelem.ref
0x7a078  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a07d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a082  throw
0x7a083  ldarg.1
0x7a084  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a089  isinst   System.Xml.Serialization.ArrayMapping
0x7a08e  brfalse  loc_7A176
0x7a093  ldloc.0
0x7a094  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a099  isinst   System.Xml.Serialization.ArrayMapping
0x7a09e  brtrue.s loc_7A0E4
0x7a0a0  ldstr    aXmlcannotrecon_0// "XmlCannotReconcileAccessor"
0x7a0a5  ldc.i4.4
0x7a0a6  newarr   [mscorlib]System.Object
0x7a0ab  dup
0x7a0ac  ldc.i4.0
0x7a0ad  ldarg.1
0x7a0ae  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7a0b3  stelem.ref
0x7a0b4  dup
0x7a0b5  ldc.i4.1
0x7a0b6  ldarg.1
0x7a0b7  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7a0bc  stelem.ref
0x7a0bd  dup
0x7a0be  ldc.i4.2
0x7a0bf  ldloc.0
0x7a0c0  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a0c5  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a0ca  stelem.ref
0x7a0cb  dup
0x7a0cc  ldc.i4.3
0x7a0cd  ldarg.1
0x7a0ce  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a0d3  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a0d8  stelem.ref
0x7a0d9  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a0de  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a0e3  throw
0x7a0e4  ldarg.1
0x7a0e5  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a0ea  castclass System.Xml.Serialization.ArrayMapping
0x7a0ef  stloc.3
0x7a0f0  ldloc.3
0x7a0f1  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x7a0f6  brtrue.s loc_7A120
0x7a0f8  ldarg.0
0x7a0f9  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::types
0x7a0fe  ldloc.0
0x7a0ff  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a104  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x7a109  ldloc.0
0x7a10a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a10f  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7a114  callvirt instance object System.Xml.Serialization.NameTable::get_Item(string name, string ns)
0x7a119  castclass System.Xml.Serialization.ArrayMapping
0x7a11e  br.s     loc_7A121
0x7a120  ldnull
0x7a121  stloc.s  4
0x7a123  ldloc.s  4
0x7a125  stloc.s  5
0x7a127  br.s     loc_7A13E
0x7a129  ldloc.s  4
0x7a12b  ldarg.1
0x7a12c  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a131  bne.un.s loc_7A135
0x7a133  ldloc.0
0x7a134  ret
0x7a135  ldloc.s  4
0x7a137  callvirt instance class System.Xml.Serialization.ArrayMapping System.Xml.Serialization.ArrayMapping::get_Next()
0x7a13c  stloc.s  4
0x7a13e  ldloc.s  4
0x7a140  brtrue.s loc_7A129
0x7a142  ldloc.3
0x7a143  ldloc.s  5
0x7a145  callvirt instance void System.Xml.Serialization.ArrayMapping::set_Next(class System.Xml.Serialization.ArrayMapping value)
0x7a14a  ldloc.3
0x7a14b  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x7a150  brtrue.s loc_7A174
0x7a152  ldarg.0
0x7a153  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::types
0x7a158  ldloc.0
0x7a159  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a15e  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x7a163  ldloc.0
0x7a164  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a169  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7a16e  ldloc.3
0x7a16f  callvirt instance void System.Xml.Serialization.NameTable::set_Item(string name, string ns, object value)
0x7a174  ldloc.0
0x7a175  ret
0x7a176  ldarg.1
0x7a177  isinst   System.Xml.Serialization.AttributeAccessor
0x7a17c  brfalse.s loc_7A1C2
0x7a17e  ldstr    aXmlcannotrecon_1// "XmlCannotReconcileAttributeAccessor"
0x7a183  ldc.i4.4
0x7a184  newarr   [mscorlib]System.Object
0x7a189  dup
0x7a18a  ldc.i4.0
0x7a18b  ldarg.1
0x7a18c  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7a191  stelem.ref
0x7a192  dup
0x7a193  ldc.i4.1
0x7a194  ldarg.1
0x7a195  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7a19a  stelem.ref
0x7a19b  dup
0x7a19c  ldc.i4.2
0x7a19d  ldloc.0
0x7a19e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a1a3  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a1a8  stelem.ref
0x7a1a9  dup
0x7a1aa  ldc.i4.3
0x7a1ab  ldarg.1
0x7a1ac  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a1b1  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a1b6  stelem.ref
0x7a1b7  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a1bc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a1c1  throw
0x7a1c2  ldstr    aXmlcannotrecon_0// "XmlCannotReconcileAccessor"
0x7a1c7  ldc.i4.4
0x7a1c8  newarr   [mscorlib]System.Object
0x7a1cd  dup
0x7a1ce  ldc.i4.0
0x7a1cf  ldarg.1
0x7a1d0  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7a1d5  stelem.ref
0x7a1d6  dup
0x7a1d7  ldc.i4.1
0x7a1d8  ldarg.1
0x7a1d9  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7a1de  stelem.ref
0x7a1df  dup
0x7a1e0  ldc.i4.2
0x7a1e1  ldloc.0
0x7a1e2  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a1e7  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a1ec  stelem.ref
0x7a1ed  dup
0x7a1ee  ldc.i4.3
0x7a1ef  ldarg.1
0x7a1f0  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7a1f5  call     string System.Xml.Serialization.XmlReflectionImporter::GetMappingName(class System.Xml.Serialization.Mapping mapping)
0x7a1fa  stelem.ref
0x7a1fb  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a200  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a205  throw
```
