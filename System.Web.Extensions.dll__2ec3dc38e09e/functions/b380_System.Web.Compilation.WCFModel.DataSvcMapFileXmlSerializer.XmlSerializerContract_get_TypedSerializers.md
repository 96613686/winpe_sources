# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_TypedSerializers

- ea: `0xb380`
- end: `0xb3b4`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_TypedSerializers`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb2c0`
- `0xb380`

## string_xrefs

- `0xb38f`: `System.Web.Compilation.WCFModel.DataSvcMapFileImpl:urn:schemas-microsoft-com:xml-dataservicemap:ReferenceGroup:True:`

## pseudocode

```c

```

## disassembly

```asm
0xb380  ldarg.0
0xb381  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0xb386  brtrue.s loc_B3AD
0xb388  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xb38d  stloc.0
0xb38e  ldloc.0
0xb38f  ldstr    aSystemWebCompi_3// "System.Web.Compilation.WCFModel.DataSvc"...
0xb394  newobj   instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.DataSvcMapFileImplSerializer::.ctor()
0xb399  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb39e  ldarg.0
0xb39f  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0xb3a4  brtrue.s loc_B3AD
0xb3a6  ldarg.0
0xb3a7  ldloc.0
0xb3a8  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0xb3ad  ldarg.0
0xb3ae  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0xb3b3  ret
```
