# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_TypedSerializers

- ea: `0x9840`
- end: `0x9874`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::get_TypedSerializers`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9780`
- `0x9840`

## string_xrefs

- `0x984f`: `System.Web.Compilation.WCFModel.SvcMapFileImpl:urn:schemas-microsoft-com:xml-wcfservicemap:ReferenceGroup:True:`

## pseudocode

```c

```

## disassembly

```asm
0x9840  ldarg.0
0x9841  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0x9846  brtrue.s loc_986D
0x9848  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x984d  stloc.0
0x984e  ldloc.0
0x984f  ldstr    aSystemWebCompi_2// "System.Web.Compilation.WCFModel.SvcMapF"...
0x9854  newobj   instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.SvcMapFileImplSerializer::.ctor()
0x9859  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x985e  ldarg.0
0x985f  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0x9864  brtrue.s loc_986D
0x9866  ldarg.0
0x9867  ldloc.0
0x9868  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0x986d  ldarg.0
0x986e  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializerContract::typedSerializers
0x9873  ret
```
