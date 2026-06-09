# Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject_0

- ea: `0xab20`
- end: `0xab7f`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject_0`
- size: `95`
- prototype: ``
- caller_count: `20`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8ef0`
- `0xab10`
- `0x11d10`
- `0x122e0`
- `0x149b0`
- `0x14eb0`
- `0x15620`
- `0x17fc0`
- `0x18040`
- `0x18d00`
- `0x199d0`
- `0x1a110`
- `0x1d330`
- `0x1e180`
- `0x21dc0`
- `0x22380`
- `0x26f30`
- `0x37b00`
- `0x37d30`
- `0x39970`

## callees

- `0x97d0`
- `0xab20`
- `0xab80`
- `0xac90`

## pseudocode

```c

```

## disassembly

```asm
0xab20  ldarg.1
0xab21  brtrue.s loc_AB2E
0xab23  ldstr    aObjIsNull// "obj is null"
0xab28  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xab2d  throw
0xab2e  ldarg.0
0xab2f  ldarg.1
0xab30  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectAttributes(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0xab35  ldarg.0
0xab36  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab3b  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xab40  stloc.0
0xab41  ldarg.0
0xab42  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab47  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xab4c  stloc.1
0xab4d  ldarg.0
0xab4e  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab53  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xab58  stloc.2
0xab59  ldarg.0
0xab5a  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab5f  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xab64  ldarg.0
0xab65  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab6a  ldloc.1
0xab6b  ldloc.2
0xab6c  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement(string, string)
0xab71  brfalse.s loc_AB74
0xab73  ret
0xab74  ldarg.0
0xab75  ldarg.1
0xab76  ldloc.0
0xab77  ldloc.1
0xab78  ldloc.2
0xab79  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectElements(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj, int32 baseDepth, string baseLocalName, string baseNamespaceUri)
0xab7e  ret
```
