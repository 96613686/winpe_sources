# Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectAttributes

- ea: `0xab80`
- end: `0xac90`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectAttributes`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab20`

## callees

- `0x8e0`
- `0x97d0`
- `0xab80`
- `0xaef0`

## string_xrefs

- `0xabae`: `http://www.w3.org/2000/xmlns/`
- `0xabdc`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xac1f`: `LoadXmlAttribute left the reader at an invalid position.\n`

## pseudocode

```c

```

## disassembly

```asm
0xab80  ldarg.0
0xab81  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab86  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToFirstAttribute()
0xab8b  brtrue.s loc_AB8E
0xab8d  ret
0xab8e  ldarg.0
0xab8f  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xab94  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xab99  stloc.0
0xab9a  ldarg.1
0xab9b  ldarg.0
0xab9c  callvirt instance bool Microsoft.ReportingServices.Modeling.IXmlLoadable::LoadXmlAttribute(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0xaba1  brtrue.s loc_ABFE
0xaba3  ldarg.0
0xaba4  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xaba9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xabae  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xabb3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xabb8  brfalse.s loc_ABFE
0xabba  ldarg.0
0xabbb  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xabc0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xabc5  ldstr    aType// "type"
0xabca  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xabcf  brtrue.s loc_ABE8
0xabd1  ldarg.0
0xabd2  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xabd7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xabdc  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xabe1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xabe6  brfalse.s loc_ABFE
0xabe8  ldstr    aUnhandledAttri// "Unhandled attribute '"
0xabed  ldloc.0
0xabee  ldstr    aInLoadobjectat// "' in LoadObjectAttributes"
0xabf3  call     string [mscorlib]System.String::Concat(string, string, string)
0xabf8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xabfd  throw
0xabfe  ldarg.0
0xabff  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac04  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xac09  ldc.i4.2
0xac0a  bne.un.s loc_AC1F
0xac0c  ldarg.0
0xac0d  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac12  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xac17  ldloc.0
0xac18  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xac1d  brfalse.s loc_AC73
0xac1f  ldstr    aLoadxmlattribu// "LoadXmlAttribute left the reader at an "...
0xac24  ldstr    aCurrentNode01D// "Current node: {0} '{1}', depth {2}"
0xac29  ldc.i4.3
0xac2a  newarr   [mscorlib]System.Object
0xac2f  dup
0xac30  ldc.i4.0
0xac31  ldarg.0
0xac32  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac37  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xac3c  box      [System.Xml]System.Xml.XmlNodeType
0xac41  stelem.ref
0xac42  dup
0xac43  ldc.i4.1
0xac44  ldarg.0
0xac45  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac4a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xac4f  stelem.ref
0xac50  dup
0xac51  ldc.i4.2
0xac52  ldarg.0
0xac53  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac58  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xac5d  box      [mscorlib]System.Int32
0xac62  stelem.ref
0xac63  call     string Microsoft.ReportingServices.Common.StringUtil::FormatInvariant(string format, object[] args)
0xac68  call     string [mscorlib]System.String::Concat(string, string)
0xac6d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xac72  throw
0xac73  ldarg.0
0xac74  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac79  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xac7e  brtrue   loc_AB8E
0xac83  ldarg.0
0xac84  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac89  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xac8e  pop
0xac8f  ret
```
