# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_WriteMethods

- ea: `0xb340`
- end: `0xb374`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_WriteMethods`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb340`

## string_xrefs

- `0xb34f`: `System.Web.Compilation.WCFModel.DataSvcMapFileImpl:urn:schemas-microsoft-com:xml-dataservicemap:ReferenceGroup:True:`
- `0xb354`: `Write9_ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0xb340  ldarg.0
0xb341  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0xb346  brtrue.s loc_B36D
0xb348  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xb34d  stloc.0
0xb34e  ldloc.0
0xb34f  ldstr    aSystemWebCompi_3// "System.Web.Compilation.WCFModel.DataSvc"...
0xb354  ldstr    aWrite9Referenc// "Write9_ReferenceGroup"
0xb359  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xb35e  ldarg.0
0xb35f  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0xb364  brtrue.s loc_B36D
0xb366  ldarg.0
0xb367  ldloc.0
0xb368  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0xb36d  ldarg.0
0xb36e  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0xb373  ret
```
