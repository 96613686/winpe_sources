# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_ReadMethods

- ea: `0xb300`
- end: `0xb334`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::get_ReadMethods`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb300`

## string_xrefs

- `0xb30f`: `System.Web.Compilation.WCFModel.DataSvcMapFileImpl:urn:schemas-microsoft-com:xml-dataservicemap:ReferenceGroup:True:`
- `0xb314`: `Read9_ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0xb300  ldarg.0
0xb301  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0xb306  brtrue.s loc_B32D
0xb308  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xb30d  stloc.0
0xb30e  ldloc.0
0xb30f  ldstr    aSystemWebCompi_3// "System.Web.Compilation.WCFModel.DataSvc"...
0xb314  ldstr    aRead9Reference// "Read9_ReferenceGroup"
0xb319  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xb31e  ldarg.0
0xb31f  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0xb324  brtrue.s loc_B32D
0xb326  ldarg.0
0xb327  ldloc.0
0xb328  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0xb32d  ldarg.0
0xb32e  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0xb333  ret
```
