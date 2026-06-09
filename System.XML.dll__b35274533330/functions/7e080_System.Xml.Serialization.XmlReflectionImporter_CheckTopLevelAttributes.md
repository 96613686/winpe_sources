# System.Xml.Serialization.XmlReflectionImporter::CheckTopLevelAttributes

- ea: `0x7e080`
- end: `0x7e19f`
- name: `System.Xml.Serialization.XmlReflectionImporter::CheckTopLevelAttributes`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x7c5e0`

## callees

- `0x622f0`
- `0x62370`
- `0x75250`
- `0x75770`
- `0x75b50`
- `0x75bc0`
- `0x79260`
- `0x792b0`
- `0x79350`
- `0x7e080`

## string_xrefs

- `0x7e090`: `XmlRpcLitAttributeAttributes`
- `0x7e0a9`: `XmlRpcLitAttributes`
- `0x7e0e3`: `XmlRpcLitElements`
- `0x7e108`: `XmlRpcLitElementNamespace`
- `0x7e172`: `XmlRpcLitElementNamespace`
- `0x7e137`: `XmlRpcLitElementNullable`

## pseudocode

```c

```

## disassembly

```asm
0x7e080  ldarg.1
0x7e081  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7e086  stloc.0
0x7e087  ldloc.0
0x7e088  ldc.i4   0x220
0x7e08d  and
0x7e08e  brfalse.s loc_7E0A0
0x7e090  ldstr    aXmlrpclitattri// "XmlRpcLitAttributeAttributes"
0x7e095  call     string System.Xml.Res::GetString(string name)
0x7e09a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e09f  throw
0x7e0a0  ldloc.0
0x7e0a1  ldc.i4   0x504
0x7e0a6  and
0x7e0a7  brfalse.s loc_7E0B9
0x7e0a9  ldstr    aXmlrpclitattri_0// "XmlRpcLitAttributes"
0x7e0ae  call     string System.Xml.Res::GetString(string name)
0x7e0b3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e0b8  throw
0x7e0b9  ldarg.1
0x7e0ba  callvirt instance class System.Xml.Serialization.XmlElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlElements()
0x7e0bf  brfalse  loc_7E15D
0x7e0c4  ldarg.1
0x7e0c5  callvirt instance class System.Xml.Serialization.XmlElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlElements()
0x7e0ca  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e0cf  ldc.i4.0
0x7e0d0  ble      loc_7E15D
0x7e0d5  ldarg.1
0x7e0d6  callvirt instance class System.Xml.Serialization.XmlElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlElements()
0x7e0db  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e0e0  ldc.i4.1
0x7e0e1  ble.s    loc_7E0F3
0x7e0e3  ldstr    aXmlrpcliteleme// "XmlRpcLitElements"
0x7e0e8  call     string System.Xml.Res::GetString(string name)
0x7e0ed  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e0f2  throw
0x7e0f3  ldarg.1
0x7e0f4  callvirt instance class System.Xml.Serialization.XmlElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlElements()
0x7e0f9  ldc.i4.0
0x7e0fa  callvirt instance class System.Xml.Serialization.XmlElementAttribute System.Xml.Serialization.XmlElementAttributes::get_Item(int32 index)
0x7e0ff  stloc.1
0x7e100  ldloc.1
0x7e101  callvirt instance string System.Xml.Serialization.XmlElementAttribute::get_Namespace()
0x7e106  brfalse.s loc_7E12F
0x7e108  ldstr    aXmlrpcliteleme_0// "XmlRpcLitElementNamespace"
0x7e10d  ldc.i4.2
0x7e10e  newarr   [mscorlib]System.Object
0x7e113  dup
0x7e114  ldc.i4.0
0x7e115  ldstr    aNamespace_0// "Namespace"
0x7e11a  stelem.ref
0x7e11b  dup
0x7e11c  ldc.i4.1
0x7e11d  ldloc.1
0x7e11e  callvirt instance string System.Xml.Serialization.XmlElementAttribute::get_Namespace()
0x7e123  stelem.ref
0x7e124  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e129  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e12e  throw
0x7e12f  ldloc.1
0x7e130  callvirt instance bool System.Xml.Serialization.XmlElementAttribute::get_IsNullable()
0x7e135  brfalse.s loc_7E15D
0x7e137  ldstr    aXmlrpcliteleme_1// "XmlRpcLitElementNullable"
0x7e13c  ldc.i4.2
0x7e13d  newarr   [mscorlib]System.Object
0x7e142  dup
0x7e143  ldc.i4.0
0x7e144  ldstr    aIsnullable// "IsNullable"
0x7e149  stelem.ref
0x7e14a  dup
0x7e14b  ldc.i4.1
0x7e14c  ldstr    aTrue// "true"
0x7e151  stelem.ref
0x7e152  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e157  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e15c  throw
0x7e15d  ldarg.1
0x7e15e  callvirt instance class System.Xml.Serialization.XmlArrayAttribute System.Xml.Serialization.XmlAttributes::get_XmlArray()
0x7e163  brfalse.s loc_7E19E
0x7e165  ldarg.1
0x7e166  callvirt instance class System.Xml.Serialization.XmlArrayAttribute System.Xml.Serialization.XmlAttributes::get_XmlArray()
0x7e16b  callvirt instance string System.Xml.Serialization.XmlArrayAttribute::get_Namespace()
0x7e170  brfalse.s loc_7E19E
0x7e172  ldstr    aXmlrpcliteleme_0// "XmlRpcLitElementNamespace"
0x7e177  ldc.i4.2
0x7e178  newarr   [mscorlib]System.Object
0x7e17d  dup
0x7e17e  ldc.i4.0
0x7e17f  ldstr    aNamespace_0// "Namespace"
0x7e184  stelem.ref
0x7e185  dup
0x7e186  ldc.i4.1
0x7e187  ldarg.1
0x7e188  callvirt instance class System.Xml.Serialization.XmlArrayAttribute System.Xml.Serialization.XmlAttributes::get_XmlArray()
0x7e18d  callvirt instance string System.Xml.Serialization.XmlArrayAttribute::get_Namespace()
0x7e192  stelem.ref
0x7e193  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e198  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e19d  throw
0x7e19e  ret
```
