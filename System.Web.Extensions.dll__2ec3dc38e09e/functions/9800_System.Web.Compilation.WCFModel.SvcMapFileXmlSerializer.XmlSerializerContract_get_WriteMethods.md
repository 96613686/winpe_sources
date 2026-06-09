# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_WriteMethods

- ea: `0x9800`
- end: `0x9834`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_WriteMethods`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9800`

## string_xrefs

- `0x980f`: `System.Web.Compilation.WCFModel.SvcMapFileImpl:urn:schemas-microsoft-com:xml-wcfservicemap:ReferenceGroup:True:`
- `0x9814`: `Write16_ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9800  ldarg.0
0x9801  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0x9806  brtrue.s loc_982D
0x9808  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x980d  stloc.0
0x980e  ldloc.0
0x980f  ldstr    aSystemWebCompi_2// "System.Web.Compilation.WCFModel.SvcMapF"...
0x9814  ldstr    aWrite16Referen// "Write16_ReferenceGroup"
0x9819  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x981e  ldarg.0
0x981f  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0x9824  brtrue.s loc_982D
0x9826  ldarg.0
0x9827  ldloc.0
0x9828  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0x982d  ldarg.0
0x982e  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::writeMethods
0x9833  ret
```
