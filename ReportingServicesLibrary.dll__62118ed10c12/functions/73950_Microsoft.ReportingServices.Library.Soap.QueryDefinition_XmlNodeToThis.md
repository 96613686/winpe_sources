# Microsoft.ReportingServices.Library.Soap.QueryDefinition::XmlNodeToThis

- ea: `0x73950`
- end: `0x739bf`
- name: `Microsoft.ReportingServices.Library.Soap.QueryDefinition::XmlNodeToThis`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x735f0`

## callees

- `0x738c0`
- `0x73950`

## string_xrefs

- `0x7395c`: `CommandType`
- `0x73977`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x73950  ldarg.0
0x73951  brtrue.s loc_73955
0x73953  ldnull
0x73954  ret
0x73955  newobj   instance void Microsoft.ReportingServices.Library.Soap.QueryDefinition::.ctor()
0x7395a  stloc.0
0x7395b  ldarg.0
0x7395c  ldstr    aCommandtype// "CommandType"
0x73961  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x73966  stloc.1
0x73967  ldloc.1
0x73968  brfalse.s loc_73976
0x7396a  ldloc.0
0x7396b  ldloc.1
0x7396c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x73971  stfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandType
0x73976  ldarg.0
0x73977  ldstr    aCommandtext// "CommandText"
0x7397c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x73981  stloc.2
0x73982  ldloc.2
0x73983  brfalse.s loc_73991
0x73985  ldloc.0
0x73986  ldloc.2
0x73987  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7398c  stfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandText
0x73991  ldarg.0
0x73992  ldstr    aTimeout_0// "Timeout"
0x73997  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7399c  stloc.3
0x7399d  ldloc.3
0x7399e  brfalse.s loc_739BD
0x739a0  ldloc.0
0x739a1  ldloc.3
0x739a2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x739a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x739ac  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x739b1  stfld    int32 Microsoft.ReportingServices.Library.Soap.QueryDefinition::Timeout
0x739b6  ldloc.0
0x739b7  ldc.i4.1
0x739b8  stfld    bool Microsoft.ReportingServices.Library.Soap.QueryDefinition::TimeoutSpecified
0x739bd  ldloc.0
0x739be  ret
```
