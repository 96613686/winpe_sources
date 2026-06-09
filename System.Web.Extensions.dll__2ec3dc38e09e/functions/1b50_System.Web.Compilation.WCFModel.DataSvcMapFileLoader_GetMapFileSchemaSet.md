# System.Web.Compilation.WCFModel.DataSvcMapFileLoader::GetMapFileSchemaSet

- ea: `0x1b50`
- end: `0x1bad`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileLoader::GetMapFileSchemaSet`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b50`

## string_xrefs

- `0x1b7c`: `Schema.DataServiceMapSchema.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x1b50  ldarg.0
0x1b51  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.DataSvcMapFileLoader::_mapFileSchemaSet
0x1b56  brtrue.s loc_1BA6
0x1b58  ldarg.0
0x1b59  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::.ctor()
0x1b5e  stfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.DataSvcMapFileLoader::_mapFileSchemaSet
0x1b63  ldtoken  System.Web.Compilation.WCFModel.DataSvcMapFileImpl
0x1b68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b6d  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1b72  ldtoken  System.Web.Compilation.WCFModel.DataSvcMapFileImpl
0x1b77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7c  ldstr    aSchemaDataserv// "Schema.DataServiceMapSchema.xsd"
0x1b81  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(class [mscorlib]System.Type, string)
0x1b86  stloc.0
0x1b87  ldarg.0
0x1b88  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.DataSvcMapFileLoader::_mapFileSchemaSet
0x1b8d  ldloc.0
0x1b8e  ldnull
0x1b8f  call     class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchema::Read(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.Schema.ValidationEventHandler)
0x1b94  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0x1b99  pop
0x1b9a  leave.s  loc_1BA6
0x1b9c  ldloc.0
0x1b9d  brfalse.s loc_1BA5
0x1b9f  ldloc.0
0x1ba0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ba5  endfinally
0x1ba6  ldarg.0
0x1ba7  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.DataSvcMapFileLoader::_mapFileSchemaSet
0x1bac  ret
```
