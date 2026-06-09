# Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectElements

- ea: `0xac90`
- end: `0xae38`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObjectElements`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab20`
- `0xac90`

## callees

- `0x8e0`
- `0x97d0`
- `0xac90`
- `0xaf00`

## string_xrefs

- `0xade4`: `LoadXmlElement left the reader at an invalid position.\n`

## pseudocode

```c

```

## disassembly

```asm
0xac90  ldc.i4.0
0xac91  stloc.0
0xac92  ldarg.0
0xac93  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xac98  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xac9d  pop
0xac9e  ldarg.0
0xac9f  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xaca4  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xaca9  ldarg.2
0xacaa  bne.un.s loc_ACF6
0xacac  ldarg.0
0xacad  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xacb2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xacb7  ldc.i4.s 0xF
0xacb9  bne.un.s loc_ACEF
0xacbb  ldarg.0
0xacbc  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xacc1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xacc6  ldarg.3
0xacc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaccc  brfalse.s loc_ACEF
0xacce  ldarg.0
0xaccf  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xacd4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xacd9  ldarg.s  4
0xacdb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xace0  brfalse.s loc_ACEF
0xace2  ldarg.0
0xace3  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xace8  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xaced  pop
0xacee  ret
0xacef  ldc.i4.1
0xacf0  stloc.0
0xacf1  br       loc_ADDE
0xacf6  ldarg.0
0xacf7  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xacfc  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xad01  ldarg.2
0xad02  ldc.i4.1
0xad03  add
0xad04  bne.un   loc_ADDC
0xad09  ldarg.0
0xad0a  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad0f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xad14  ldc.i4.1
0xad15  bne.un   loc_ADAE
0xad1a  ldarg.0
0xad1b  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad20  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xad25  stloc.1
0xad26  ldarg.0
0xad27  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad2c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xad31  stloc.2
0xad32  ldarg.1
0xad33  ldarg.0
0xad34  callvirt instance bool Microsoft.ReportingServices.Modeling.IXmlLoadable::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0xad39  brtrue.s loc_AD5B
0xad3b  ldstr    aUnhandledEleme// "Unhandled element '"
0xad40  ldarg.0
0xad41  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad46  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xad4b  ldstr    aInLoadobjectel// "' in LoadObjectElements"
0xad50  call     string [mscorlib]System.String::Concat(string, string, string)
0xad55  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xad5a  throw
0xad5b  ldarg.0
0xad5c  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad61  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xad66  ldarg.2
0xad67  ldc.i4.1
0xad68  add
0xad69  bne.un.s loc_ADDE
0xad6b  ldarg.0
0xad6c  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad71  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xad76  ldc.i4.s 0xF
0xad78  bne.un.s loc_ADDE
0xad7a  ldarg.0
0xad7b  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad80  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xad85  ldloc.1
0xad86  call     bool [mscorlib]System.String::op_Equality(string, string)
0xad8b  brfalse.s loc_ADDE
0xad8d  ldarg.0
0xad8e  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xad93  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xad98  ldloc.2
0xad99  call     bool [mscorlib]System.String::op_Equality(string, string)
0xad9e  brfalse.s loc_ADDE
0xada0  ldarg.0
0xada1  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xada6  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xadab  pop
0xadac  br.s     loc_ADDE
0xadae  ldstr    aUnhandled// "Unhandled "
0xadb3  ldarg.0
0xadb4  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xadb9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xadbe  stloc.3
0xadbf  ldloca.s 3
0xadc1  constrained. [System.Xml]System.Xml.XmlNodeType
0xadc7  callvirt instance string [mscorlib]System.Object::ToString()
0xadcc  ldstr    aNodeInLoadobje// " node in LoadObjectElements"
0xadd1  call     string [mscorlib]System.String::Concat(string, string, string)
0xadd6  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xaddb  throw
0xaddc  ldc.i4.1
0xaddd  stloc.0
0xadde  ldloc.0
0xaddf  brfalse  Microsoft.ReportingServices.Modeling.ModelingXmlReader__LoadObjectElements
0xade4  ldstr    aLoadxmlelement// "LoadXmlElement left the reader at an in"...
0xade9  ldstr    aCurrentNode01D// "Current node: {0} '{1}', depth {2}"
0xadee  ldc.i4.3
0xadef  newarr   [mscorlib]System.Object
0xadf4  dup
0xadf5  ldc.i4.0
0xadf6  ldarg.0
0xadf7  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xadfc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xae01  box      [System.Xml]System.Xml.XmlNodeType
0xae06  stelem.ref
0xae07  dup
0xae08  ldc.i4.1
0xae09  ldarg.0
0xae0a  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xae0f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xae14  stelem.ref
0xae15  dup
0xae16  ldc.i4.2
0xae17  ldarg.0
0xae18  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xae1d  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xae22  box      [mscorlib]System.Int32
0xae27  stelem.ref
0xae28  call     string Microsoft.ReportingServices.Common.StringUtil::FormatInvariant(string format, object[] args)
0xae2d  call     string [mscorlib]System.String::Concat(string, string)
0xae32  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xae37  throw
```
