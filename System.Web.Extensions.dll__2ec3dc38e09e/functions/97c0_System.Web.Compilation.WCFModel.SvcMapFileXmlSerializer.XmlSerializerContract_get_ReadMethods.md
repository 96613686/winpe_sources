# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_ReadMethods

- ea: `0x97c0`
- end: `0x97f4`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_ReadMethods`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97c0`

## string_xrefs

- `0x97cf`: `System.Web.Compilation.WCFModel.SvcMapFileImpl:urn:schemas-microsoft-com:xml-wcfservicemap:ReferenceGroup:True:`
- `0x97d4`: `Read16_ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0x97c0  ldarg.0
0x97c1  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0x97c6  brtrue.s loc_97ED
0x97c8  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x97cd  stloc.0
0x97ce  ldloc.0
0x97cf  ldstr    aSystemWebCompi_2// "System.Web.Compilation.WCFModel.SvcMapF"...
0x97d4  ldstr    aRead16Referenc// "Read16_ReferenceGroup"
0x97d9  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x97de  ldarg.0
0x97df  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0x97e4  brtrue.s loc_97ED
0x97e6  ldarg.0
0x97e7  ldloc.0
0x97e8  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0x97ed  ldarg.0
0x97ee  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::readMethods
0x97f3  ret
```
