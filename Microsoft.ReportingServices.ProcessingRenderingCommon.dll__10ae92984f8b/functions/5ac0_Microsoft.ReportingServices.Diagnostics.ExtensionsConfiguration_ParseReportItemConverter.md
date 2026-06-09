# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemConverter

- ea: `0x5ac0`
- end: `0x5b59`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseReportItemConverter`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5a70`

## callees

- `0x5030`
- `0x5ac0`
- `0x5e10`
- `0x63d0`
- `0x63f0`
- `0x6400`
- `0x6440`
- `0x6450`

## pseudocode

```c

```

## disassembly

```asm
0x5ac0  ldarg.1
0x5ac1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5ac6  ldstr    aConverter// "Converter"
0x5acb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5ad0  brfalse.s loc_5ADD
0x5ad2  ldarg.1
0x5ad3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5ad8  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string element)
0x5add  newobj   instance void Microsoft.ReportingServices.Diagnostics.ReportItemConverterExtension::.ctor()
0x5ae2  stloc.0
0x5ae3  ldloc.0
0x5ae4  ldarg.1
0x5ae5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5aea  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Type(string value)
0x5aef  ldnull
0x5af0  stloc.1
0x5af1  ldarg.1
0x5af2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5af7  ldstr    aSource// "Source"
0x5afc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5b01  stloc.1
0x5b02  ldloc.1
0x5b03  brtrue.s loc_5B0F
0x5b05  ldstr    aSource// "Source"
0x5b0a  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowElementMissing(string element)
0x5b0f  ldloc.0
0x5b10  ldloc.1
0x5b11  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5b16  callvirt instance void Microsoft.ReportingServices.Diagnostics.ReportItemConverterExtension::set_Source(string value)
0x5b1b  ldarg.1
0x5b1c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5b21  ldstr    aTarget// "Target"
0x5b26  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5b2b  stloc.1
0x5b2c  ldloc.1
0x5b2d  brtrue.s loc_5B39
0x5b2f  ldstr    aTarget// "Target"
0x5b34  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowElementMissing(string element)
0x5b39  ldloc.0
0x5b3a  ldloc.1
0x5b3b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5b40  callvirt instance void Microsoft.ReportingServices.Diagnostics.ReportItemConverterExtension::set_Target(string value)
0x5b45  ldloc.0
0x5b46  stloc.2
0x5b47  ldarg.0
0x5b48  ldarg.1
0x5b49  ldloca.s 2
0x5b4b  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElementType(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x5b50  ldarg.2
0x5b51  ldloc.0
0x5b52  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5b57  pop
0x5b58  ret
```
