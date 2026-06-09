# Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Parse

- ea: `0x3060`
- end: `0x30da`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Parse`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b00`

## callees

- `0x2b90`
- `0x2ff0`
- `0x3020`
- `0x3060`

## pseudocode

```c

```

## disassembly

```asm
0x3060  newobj   instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::.ctor()
0x3065  stloc.0
0x3066  ldarg.0
0x3067  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x306c  ldstr    aNamespace// "Namespace"
0x3071  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3076  stloc.1
0x3077  ldloc.1
0x3078  brfalse.s loc_3087
0x307a  ldloc.1
0x307b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x3080  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3085  brfalse.s loc_3091
0x3087  ldstr    aNamespace// "Namespace"
0x308c  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowElementMissing(string)
0x3091  ldloc.0
0x3092  ldstr    aNamespace// "Namespace"
0x3097  ldloc.1
0x3098  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x309d  callvirt instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add(string propertyId, string value)
0x30a2  ldarg.0
0x30a3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x30a8  ldstr    aAllownew// "AllowNew"
0x30ad  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30b2  stloc.2
0x30b3  ldloc.2
0x30b4  brfalse.s loc_30C7
0x30b6  ldloc.0
0x30b7  ldstr    aAllownew// "AllowNew"
0x30bc  ldloc.2
0x30bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30c2  callvirt instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add(string propertyId, string value)
0x30c7  ldloc.0
0x30c8  ldstr    aName_0// "Name"
0x30cd  ldarg.0
0x30ce  call     string Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ReadNodeText(class [System.Xml]System.Xml.XmlNode node)
0x30d3  callvirt instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag::Add(string propertyId, string value)
0x30d8  ldloc.0
0x30d9  ret
```
