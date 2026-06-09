# System.Xml.Serialization.XmlReflectionImporter::ImportPrimitiveMapping

- ea: `0x7ba80`
- end: `0x7bb3f`
- name: `System.Xml.Serialization.XmlReflectionImporter::ImportPrimitiveMapping`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a2a0`

## callees

- `0x622f0`
- `0x68c20`
- `0x68c40`
- `0x68c50`
- `0x68c60`
- `0x68ca0`
- `0x68d50`
- `0x6a820`
- `0x72b50`
- `0x72be0`
- `0x73d30`
- `0x7ba20`
- `0x7ba80`
- `0xd6af0`

## string_xrefs

- `0x7ba97`: `http://www.w3.org/2001/XMLSchema`
- `0x7bb1e`: `http://www.w3.org/2001/XMLSchema`
- `0x7bab6`: `http://microsoft.com/wsdl/types/`
- `0x7bb17`: `http://microsoft.com/wsdl/types/`
- `0x7bacd`: `XmlUdeclaredXsdType`

## pseudocode

```c

```

## disassembly

```asm
0x7ba80  newobj   instance void System.Xml.Serialization.PrimitiveMapping::.ctor()
0x7ba85  stloc.0
0x7ba86  ldarg.3
0x7ba87  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7ba8c  ldc.i4.0
0x7ba8d  ble.s    loc_7BAE7
0x7ba8f  ldloc.0
0x7ba90  ldarg.0
0x7ba91  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7ba96  ldarg.3
0x7ba97  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7ba9c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x7baa1  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7baa6  ldloc.0
0x7baa7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7baac  brtrue.s loc_7BAF3
0x7baae  ldloc.0
0x7baaf  ldarg.0
0x7bab0  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7bab5  ldarg.3
0x7bab6  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7babb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x7bac0  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7bac5  ldloc.0
0x7bac6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7bacb  brtrue.s loc_7BAF3
0x7bacd  ldstr    aXmludeclaredxs// "XmlUdeclaredXsdType"
0x7bad2  ldc.i4.1
0x7bad3  newarr   [mscorlib]System.Object
0x7bad8  dup
0x7bad9  ldc.i4.0
0x7bada  ldarg.3
0x7badb  stelem.ref
0x7badc  call     string System.Xml.Res::GetString(string name, object[] args)
0x7bae1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7bae6  throw
0x7bae7  ldloc.0
0x7bae8  ldarg.1
0x7bae9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7baee  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7baf3  ldloc.0
0x7baf4  ldloc.0
0x7baf5  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7bafa  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7baff  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x7bb04  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x7bb09  ldloc.0
0x7bb0a  ldloc.0
0x7bb0b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7bb10  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsXsdType()
0x7bb15  brtrue.s loc_7BB1E
0x7bb17  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7bb1c  br.s     loc_7BB23
0x7bb1e  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7bb23  callvirt instance void System.Xml.Serialization.TypeMapping::set_Namespace(string value)
0x7bb28  ldloc.0
0x7bb29  ldarg.s  4
0x7bb2b  callvirt instance void System.Xml.Serialization.TypeMapping::set_IsList(bool value)
0x7bb30  ldarg.0
0x7bb31  ldloc.0
0x7bb32  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7bb37  ldarg.2
0x7bb38  call     instance void System.Xml.Serialization.XmlReflectionImporter::CheckContext(class System.Xml.Serialization.TypeDesc typeDesc, valuetype ImportContext context)
0x7bb3d  ldloc.0
0x7bb3e  ret
```
