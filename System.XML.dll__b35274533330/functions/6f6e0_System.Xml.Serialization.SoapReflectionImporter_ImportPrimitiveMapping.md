# System.Xml.Serialization.SoapReflectionImporter::ImportPrimitiveMapping

- ea: `0x6f6e0`
- end: `0x6f791`
- name: `System.Xml.Serialization.SoapReflectionImporter::ImportPrimitiveMapping`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6ebb0`

## callees

- `0x622f0`
- `0x68b90`
- `0x68c20`
- `0x68c40`
- `0x68c50`
- `0x68c60`
- `0x68d50`
- `0x6a820`
- `0x6f6e0`
- `0x72b50`
- `0x72be0`
- `0x73d30`
- `0xd6af0`

## string_xrefs

- `0x6f6fe`: `http://www.w3.org/2001/XMLSchema`
- `0x6f785`: `http://www.w3.org/2001/XMLSchema`
- `0x6f71d`: `http://microsoft.com/wsdl/types/`
- `0x6f77e`: `http://microsoft.com/wsdl/types/`
- `0x6f734`: `XmlUdeclaredXsdType`

## pseudocode

```c

```

## disassembly

```asm
0x6f6e0  newobj   instance void System.Xml.Serialization.PrimitiveMapping::.ctor()
0x6f6e5  stloc.0
0x6f6e6  ldloc.0
0x6f6e7  ldc.i4.1
0x6f6e8  callvirt instance void System.Xml.Serialization.Mapping::set_IsSoap(bool value)
0x6f6ed  ldarg.2
0x6f6ee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6f6f3  ldc.i4.0
0x6f6f4  ble.s    loc_6F74E
0x6f6f6  ldloc.0
0x6f6f7  ldarg.0
0x6f6f8  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.SoapReflectionImporter::typeScope
0x6f6fd  ldarg.2
0x6f6fe  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6f703  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x6f708  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x6f70d  ldloc.0
0x6f70e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f713  brtrue.s loc_6F75A
0x6f715  ldloc.0
0x6f716  ldarg.0
0x6f717  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.SoapReflectionImporter::typeScope
0x6f71c  ldarg.2
0x6f71d  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x6f722  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x6f727  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x6f72c  ldloc.0
0x6f72d  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f732  brtrue.s loc_6F75A
0x6f734  ldstr    aXmludeclaredxs// "XmlUdeclaredXsdType"
0x6f739  ldc.i4.1
0x6f73a  newarr   [mscorlib]System.Object
0x6f73f  dup
0x6f740  ldc.i4.0
0x6f741  ldarg.2
0x6f742  stelem.ref
0x6f743  call     string System.Xml.Res::GetString(string name, object[] args)
0x6f748  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6f74d  throw
0x6f74e  ldloc.0
0x6f74f  ldarg.1
0x6f750  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6f755  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x6f75a  ldloc.0
0x6f75b  ldloc.0
0x6f75c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f761  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x6f766  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x6f76b  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x6f770  ldloc.0
0x6f771  ldloc.0
0x6f772  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f777  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsXsdType()
0x6f77c  brtrue.s loc_6F785
0x6f77e  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x6f783  br.s     loc_6F78A
0x6f785  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6f78a  callvirt instance void System.Xml.Serialization.TypeMapping::set_Namespace(string value)
0x6f78f  ldloc.0
0x6f790  ret
```
