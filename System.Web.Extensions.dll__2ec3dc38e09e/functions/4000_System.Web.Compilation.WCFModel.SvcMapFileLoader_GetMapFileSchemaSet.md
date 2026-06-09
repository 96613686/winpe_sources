# System.Web.Compilation.WCFModel.SvcMapFileLoader::GetMapFileSchemaSet

- ea: `0x4000`
- end: `0x405d`
- name: `System.Web.Compilation.WCFModel.SvcMapFileLoader::GetMapFileSchemaSet`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4000`

## string_xrefs

- `0x402c`: `Schema.ServiceMapSchema.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x4000  ldarg.0
0x4001  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.SvcMapFileLoader::_mapFileSchemaSet
0x4006  brtrue.s loc_4056
0x4008  ldarg.0
0x4009  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaSet::.ctor()
0x400e  stfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.SvcMapFileLoader::_mapFileSchemaSet
0x4013  ldtoken  System.Web.Compilation.WCFModel.SvcMapFileImpl
0x4018  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x401d  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4022  ldtoken  System.Web.Compilation.WCFModel.SvcMapFileImpl
0x4027  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x402c  ldstr    aSchemaServicem// "Schema.ServiceMapSchema.xsd"
0x4031  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(class [mscorlib]System.Type, string)
0x4036  stloc.0
0x4037  ldarg.0
0x4038  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.SvcMapFileLoader::_mapFileSchemaSet
0x403d  ldloc.0
0x403e  ldnull
0x403f  call     class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchema::Read(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.Schema.ValidationEventHandler)
0x4044  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(class [System.Xml]System.Xml.Schema.XmlSchema)
0x4049  pop
0x404a  leave.s  loc_4056
0x404c  ldloc.0
0x404d  brfalse.s loc_4055
0x404f  ldloc.0
0x4050  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4055  endfinally
0x4056  ldarg.0
0x4057  ldfld    class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Web.Compilation.WCFModel.SvcMapFileLoader::_mapFileSchemaSet
0x405c  ret
```
