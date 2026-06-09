# System.Xml.Serialization.XmlReflectionImporter::InitializeStructMembers

- ea: `0x7af90`
- end: `0x7b4e1`
- name: `System.Xml.Serialization.XmlReflectionImporter::InitializeStructMembers`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `56`
- tags: `registry_config`

## callers

- `0x7adb0`

## callees

- `0x622f0`
- `0x68600`
- `0x68660`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68c90`
- `0x68fb0`
- `0x68fc0`
- `0x69050`
- `0x69070`
- `0x69090`
- `0x69110`
- `0x69140`
- `0x69150`
- `0x69160`
- `0x69180`
- `0x692f0`
- `0x69300`
- `0x69420`
- `0x69600`
- `0x69660`
- `0x696f0`
- `0x69730`
- `0x69a20`
- `0x69b20`
- `0x69bf0`
- `0x69c00`
- `0x6a6c0`
- `0x6a800`
- `0x6a820`
- `0x6a8d0`
- `0x6a940`
- `0x6b180`
- `0x72b90`
- `0x72c60`
- `0x730b0`
- `0x74f20`
- `0x75c10`
- `0x79a30`
- `0x79cf0`
- `0x7a250`
- `0x7acf0`
- `0x7adb0`
- `0x7af90`
- `0x7c1e0`
- `0x7e540`
- `0x7e5d0`
- `0x7e7a0`
- `0x7e7f0`

## string_xrefs

- `0x7b256`: `XmlIllegalTypedTextAttribute`
- `0x7afcc`: `XmlUnsupportedInheritance`
- `0x7b29c`: `XmlIllegalMultipleText`
- `0x7b2d9`: `XmlMultipleXmlns`
- `0x7b497`: `XmlMultipleXmlns`
- `0x7b3b6`: `XmlSequenceUnique`
- `0x7b40d`: `XmlSequenceInconsistent`

## pseudocode

```c

```

## disassembly

```asm
0x7af90  ldarg.1
0x7af91  callvirt instance bool System.Xml.Serialization.StructMapping::get_IsFullyInitialized()
0x7af96  brfalse.s loc_7AF9A
0x7af98  ldc.i4.1
0x7af99  ret
0x7af9a  ldarg.2
0x7af9b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7afa0  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x7afa5  brfalse  loc_7B167
0x7afaa  ldarg.0
0x7afab  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.XmlReflectionImporter::modelScope
0x7afb0  ldarg.2
0x7afb1  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7afb6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x7afbb  ldc.i4.0
0x7afbc  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type, bool directReference)
0x7afc1  stloc.s  4
0x7afc3  ldloc.s  4
0x7afc5  isinst   System.Xml.Serialization.StructModel
0x7afca  brtrue.s loc_7AFF5
0x7afcc  ldstr    aXmlunsupported_10// "XmlUnsupportedInheritance"
0x7afd1  ldc.i4.1
0x7afd2  newarr   [mscorlib]System.Object
0x7afd7  dup
0x7afd8  ldc.i4.0
0x7afd9  ldarg.2
0x7afda  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7afdf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x7afe4  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7afe9  stelem.ref
0x7afea  call     string System.Xml.Res::GetString(string name, object[] args)
0x7afef  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7aff4  throw
0x7aff5  ldarg.0
0x7aff6  ldloc.s  4
0x7aff8  castclass System.Xml.Serialization.StructModel
0x7affd  ldarg.1
0x7affe  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7b003  ldarg.3
0x7b004  ldnull
0x7b005  ldarg.s  5
0x7b007  call     instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.XmlReflectionImporter::ImportStructLikeMapping(class System.Xml.Serialization.StructModel model, string ns, bool openModel, class System.Xml.Serialization.XmlAttributes a, class System.Xml.Serialization.RecursionLimiter limiter)
0x7b00c  stloc.s  5
0x7b00e  ldarg.s  5
0x7b010  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b015  ldloc.s  5
0x7b017  callvirt instance int32 System.Xml.Serialization.WorkItems::IndexOf(class System.Xml.Serialization.StructMapping mapping)
0x7b01c  stloc.s  6
0x7b01e  ldloc.s  6
0x7b020  ldc.i4.0
0x7b021  bge      loc_7B0F1
0x7b026  ldarg.1
0x7b027  ldloc.s  5
0x7b029  callvirt instance void System.Xml.Serialization.StructMapping::set_BaseMapping(class System.Xml.Serialization.StructMapping value)
0x7b02e  ldarg.1
0x7b02f  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x7b034  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalAttributes()
0x7b039  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.NameTable::get_Values()
0x7b03e  stloc.s  7
0x7b040  ldloc.s  7
0x7b042  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7b047  stloc.s  8
0x7b049  br.s     loc_7B066
0x7b04b  ldloc.s  8
0x7b04d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7b052  castclass System.Xml.Serialization.AttributeAccessor
0x7b057  stloc.s  9
0x7b059  ldarg.1
0x7b05a  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalAttributes()
0x7b05f  ldloc.s  9
0x7b061  call     void System.Xml.Serialization.XmlReflectionImporter::AddUniqueAccessor(class System.Xml.Serialization.INameScope scope, class System.Xml.Serialization.Accessor accessor)
0x7b066  ldloc.s  8
0x7b068  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7b06d  brtrue.s loc_7B04B
0x7b06f  leave.s  loc_7B086
0x7b071  ldloc.s  8
0x7b073  isinst   [mscorlib]System.IDisposable
0x7b078  stloc.s  0xA
0x7b07a  ldloc.s  0xA
0x7b07c  brfalse.s loc_7B085
0x7b07e  ldloc.s  0xA
0x7b080  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b085  endfinally
0x7b086  ldarg.1
0x7b087  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x7b08c  callvirt instance bool System.Xml.Serialization.StructMapping::HasExplicitSequence()
0x7b091  brtrue   loc_7B167
0x7b096  ldarg.1
0x7b097  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x7b09c  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalElements()
0x7b0a1  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Serialization.NameTable::get_Values()
0x7b0a6  stloc.s  7
0x7b0a8  ldloc.s  7
0x7b0aa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7b0af  stloc.s  0xB
0x7b0b1  br.s     loc_7B0CE
0x7b0b3  ldloc.s  0xB
0x7b0b5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7b0ba  castclass System.Xml.Serialization.ElementAccessor
0x7b0bf  stloc.s  0xC
0x7b0c1  ldarg.1
0x7b0c2  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalElements()
0x7b0c7  ldloc.s  0xC
0x7b0c9  call     void System.Xml.Serialization.XmlReflectionImporter::AddUniqueAccessor(class System.Xml.Serialization.INameScope scope, class System.Xml.Serialization.Accessor accessor)
0x7b0ce  ldloc.s  0xB
0x7b0d0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7b0d5  brtrue.s loc_7B0B3
0x7b0d7  leave    loc_7B167
0x7b0dc  ldloc.s  0xB
0x7b0de  isinst   [mscorlib]System.IDisposable
0x7b0e3  stloc.s  0xA
0x7b0e5  ldloc.s  0xA
0x7b0e7  brfalse.s loc_7B0F0
0x7b0e9  ldloc.s  0xA
0x7b0eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b0f0  endfinally
0x7b0f1  ldarg.s  5
0x7b0f3  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b0f8  ldarg.1
0x7b0f9  callvirt instance bool System.Xml.Serialization.WorkItems::Contains(class System.Xml.Serialization.StructMapping mapping)
0x7b0fe  brtrue.s loc_7B113
0x7b100  ldarg.s  5
0x7b102  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b107  ldarg.2
0x7b108  ldarg.1
0x7b109  newobj   instance void System.Xml.Serialization.ImportStructWorkItem::.ctor(class System.Xml.Serialization.StructModel model, class System.Xml.Serialization.StructMapping mapping)
0x7b10e  callvirt instance void System.Xml.Serialization.WorkItems::Add(class System.Xml.Serialization.ImportStructWorkItem item)
0x7b113  ldarg.s  5
0x7b115  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b11a  callvirt instance int32 System.Xml.Serialization.WorkItems::get_Count()
0x7b11f  ldc.i4.1
0x7b120  sub
0x7b121  stloc.s  0xD
0x7b123  ldloc.s  6
0x7b125  ldloc.s  0xD
0x7b127  bge.s    loc_7B165
0x7b129  ldarg.s  5
0x7b12b  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b130  ldloc.s  6
0x7b132  callvirt instance class System.Xml.Serialization.ImportStructWorkItem System.Xml.Serialization.WorkItems::get_Item(int32 index)
0x7b137  stloc.s  0xE
0x7b139  ldarg.s  5
0x7b13b  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b140  ldloc.s  6
0x7b142  ldarg.s  5
0x7b144  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b149  ldloc.s  0xD
0x7b14b  callvirt instance class System.Xml.Serialization.ImportStructWorkItem System.Xml.Serialization.WorkItems::get_Item(int32 index)
0x7b150  callvirt instance void System.Xml.Serialization.WorkItems::set_Item(int32 index, class System.Xml.Serialization.ImportStructWorkItem value)
0x7b155  ldarg.s  5
0x7b157  callvirt instance class System.Xml.Serialization.WorkItems System.Xml.Serialization.RecursionLimiter::get_DeferredWorkItems()
0x7b15c  ldloc.s  0xD
0x7b15e  ldloc.s  0xE
0x7b160  callvirt instance void System.Xml.Serialization.WorkItems::set_Item(int32 index, class System.Xml.Serialization.ImportStructWorkItem value)
0x7b165  ldc.i4.0
0x7b166  ret
0x7b167  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x7b16c  stloc.0
0x7b16d  ldnull
0x7b16e  stloc.1
0x7b16f  ldc.i4.0
0x7b170  stloc.2
0x7b171  ldc.i4.0
0x7b172  stloc.3
0x7b173  ldarg.2
0x7b174  callvirt instance class [mscorlib]System.Reflection.MemberInfo[] System.Xml.Serialization.StructModel::GetMemberInfos()
0x7b179  stloc.s  0xF
0x7b17b  ldc.i4.0
0x7b17c  stloc.s  0x10
0x7b17e  br       loc_7B355
0x7b183  ldloc.s  0xF
0x7b185  ldloc.s  0x10
0x7b187  ldelem.ref
0x7b188  stloc.s  0x11
0x7b18a  ldloc.s  0x11
0x7b18c  callvirt instance valuetype [mscorlib]System.Reflection.MemberTypes [mscorlib]System.Reflection.MemberInfo::get_MemberType()
0x7b191  ldc.i4.s 0x14
0x7b193  and
0x7b194  brfalse  loc_7B34F
0x7b199  ldarg.0
0x7b19a  ldloc.s  0x11
0x7b19c  call     instance class System.Xml.Serialization.XmlAttributes System.Xml.Serialization.XmlReflectionImporter::GetAttributes(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0x7b1a1  stloc.s  0x12
0x7b1a3  ldloc.s  0x12
0x7b1a5  callvirt instance bool System.Xml.Serialization.XmlAttributes::get_XmlIgnore()
0x7b1aa  brtrue   loc_7B34F
0x7b1af  ldarg.2
0x7b1b0  ldloc.s  0x11
0x7b1b2  callvirt instance class System.Xml.Serialization.FieldModel System.Xml.Serialization.StructModel::GetFieldModel(class [mscorlib]System.Reflection.MemberInfo memberInfo)
0x7b1b7  stloc.s  0x13
0x7b1b9  ldloc.s  0x13
0x7b1bb  brfalse  loc_7B34F
0x7b1c0  nop
0x7b1c1  ldarg.0
0x7b1c2  ldarg.2
0x7b1c3  ldloc.s  0x13
0x7b1c5  ldloc.s  0x12
0x7b1c7  ldarg.1
0x7b1c8  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7b1cd  ldarg.s  5
0x7b1cf  call     instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.XmlReflectionImporter::ImportFieldMapping(class System.Xml.Serialization.StructModel parent, class System.Xml.Serialization.FieldModel model, class System.Xml.Serialization.XmlAttributes a, string ns, class System.Xml.Serialization.RecursionLimiter limiter)
0x7b1d4  stloc.s  0x14
0x7b1d6  ldloc.s  0x14
0x7b1d8  brtrue.s loc_7B1DF
0x7b1da  leave    loc_7B34F
0x7b1df  ldarg.1
0x7b1e0  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x7b1e5  brfalse.s loc_7B201
0x7b1e7  ldarg.1
0x7b1e8  callvirt instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.StructMapping::get_BaseMapping()
0x7b1ed  ldloc.s  0x14
0x7b1ef  ldarg.1
0x7b1f0  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x7b1f5  callvirt instance bool System.Xml.Serialization.StructMapping::Declares(class System.Xml.Serialization.MemberMapping member, string parent)
0x7b1fa  brfalse.s loc_7B201
0x7b1fc  leave    loc_7B34F
0x7b201  ldloc.3
0x7b202  ldloc.s  0x14
0x7b204  callvirt instance bool System.Xml.Serialization.MemberMapping::get_IsSequence()
0x7b209  or
0x7b20a  stloc.3
0x7b20b  ldloc.s  0x14
0x7b20d  ldarg.1
0x7b20e  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalElements()
0x7b213  ldarg.1
0x7b214  callvirt instance class System.Xml.Serialization.NameTable System.Xml.Serialization.StructMapping::get_LocalAttributes()
0x7b219  ldloc.3
0x7b21a  call     void System.Xml.Serialization.XmlReflectionImporter::AddUniqueAccessor(class System.Xml.Serialization.MemberMapping member, class System.Xml.Serialization.INameScope elements, class System.Xml.Serialization.INameScope attributes, bool isSequence)
0x7b21f  ldloc.s  0x14
0x7b221  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b226  brfalse  loc_7B2C8
0x7b22b  ldloc.s  0x14
0x7b22d  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b232  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7b237  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7b23c  callvirt instance bool System.Xml.Serialization.TypeDesc::get_CanBeTextValue()
0x7b241  brtrue.s loc_7B299
0x7b243  ldloc.s  0x14
0x7b245  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b24a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7b24f  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsList()
0x7b254  brfalse.s loc_7B299
0x7b256  ldstr    aXmlillegaltype// "XmlIllegalTypedTextAttribute"
0x7b25b  ldc.i4.3
0x7b25c  newarr   [mscorlib]System.Object
0x7b261  dup
0x7b262  ldc.i4.0
0x7b263  ldarg.s  4
0x7b265  stelem.ref
0x7b266  dup
0x7b267  ldc.i4.1
0x7b268  ldloc.s  0x14
0x7b26a  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b26f  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7b274  stelem.ref
0x7b275  dup
0x7b276  ldc.i4.2
0x7b277  ldloc.s  0x14
0x7b279  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b27e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7b283  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7b288  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7b28d  stelem.ref
0x7b28e  call     string System.Xml.Res::GetString(string name, object[] args)
0x7b293  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7b298  throw
0x7b299  ldloc.1
0x7b29a  brfalse.s loc_7B2C0
0x7b29c  ldstr    aXmlillegalmult// "XmlIllegalMultipleText"
0x7b2a1  ldc.i4.1
0x7b2a2  newarr   [mscorlib]System.Object
0x7b2a7  dup
0x7b2a8  ldc.i4.0
0x7b2a9  ldarg.2
0x7b2aa  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7b2af  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7b2b4  stelem.ref
0x7b2b5  call     string System.Xml.Res::GetString(string name, object[] args)
0x7b2ba  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7b2bf  throw
0x7b2c0  ldloc.s  0x14
0x7b2c2  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x7b2c7  stloc.1
0x7b2c8  ldloc.s  0x14
0x7b2ca  callvirt instance class System.Xml.Serialization.XmlnsAccessor System.Xml.Serialization.AccessorMapping::get_Xmlns()
0x7b2cf  brfalse.s loc_7B305
0x7b2d1  ldarg.1
0x7b2d2  callvirt instance class System.Xml.Serialization.MemberMapping System.Xml.Serialization.StructMapping::get_XmlnsMember()
0x7b2d7  brfalse.s loc_7B2FD
0x7b2d9  ldstr    aXmlmultiplexml// "XmlMultipleXmlns"
0x7b2de  ldc.i4.1
0x7b2df  newarr   [mscorlib]System.Object
0x7b2e4  dup
0x7b2e5  ldc.i4.0
0x7b2e6  ldarg.2
0x7b2e7  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7b2ec  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7b2f1  stelem.ref
0x7b2f2  call     string System.Xml.Res::GetString(string name, object[] args)
0x7b2f7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
  ... truncated ...
```
