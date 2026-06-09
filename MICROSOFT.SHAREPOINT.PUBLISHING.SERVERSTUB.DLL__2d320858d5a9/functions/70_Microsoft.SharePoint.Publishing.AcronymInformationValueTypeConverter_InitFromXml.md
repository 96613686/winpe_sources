# Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter::InitFromXml

- ea: `0x70`
- end: `0x15f`
- name: `Microsoft.SharePoint.Publishing.AcronymInformationValueTypeConverter::InitFromXml`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x70`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.0
0x71  ldarg.1
0x72  ldarg.2
0x73  ldarg.3
0x74  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x79  starg.s  1
0x7b  ldarg.1
0x7c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation
0x81  stloc.0
0x82  ldloc.0
0x83  brfalse  loc_15D
0x88  ldarg.2
0x89  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x8e  stloc.s  4
0x90  br       loc_13A
0x95  ldloc.s  4
0x97  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9c  castclass [System.Xml]System.Xml.XmlNode
0xa1  stloc.1
0xa2  ldloc.1
0xa3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa8  ldstr    aName// "Name"
0xad  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb2  stloc.2
0xb3  ldloc.2
0xb4  brfalse  loc_13A
0xb9  ldloc.2
0xba  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xbf  stloc.3
0xc0  ldloc.3
0xc1  dup
0xc2  stloc.s  5
0xc4  brfalse.s loc_13A
0xc6  ldloc.s  5
0xc8  ldstr    aAcronym// "Acronym"
0xcd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd2  brtrue.s loc_100
0xd4  ldloc.s  5
0xd6  ldstr    aColor// "Color"
0xdb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe0  brtrue.s loc_10F
0xe2  ldloc.s  5
0xe4  ldstr    aLcid// "Lcid"
0xe9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xee  brtrue.s loc_11E
0xf0  ldloc.s  5
0xf2  ldstr    aText// "Text"
0xf7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xfc  brtrue.s loc_12D
0xfe  br.s     loc_13A
0x100  ldloc.0
0x101  ldloc.1
0x102  ldarg.3
0x103  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x108  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::set_Acronym(string)
0x10d  br.s     loc_13A
0x10f  ldloc.0
0x110  ldloc.1
0x111  ldarg.3
0x112  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x117  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::set_Color(string)
0x11c  br.s     loc_13A
0x11e  ldloc.0
0x11f  ldloc.1
0x120  ldarg.3
0x121  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x126  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::set_Lcid(int32)
0x12b  br.s     loc_13A
0x12d  ldloc.0
0x12e  ldloc.1
0x12f  ldarg.3
0x130  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x135  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation::set_Text(string)
0x13a  ldloc.s  4
0x13c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x141  brtrue   loc_95
0x146  leave.s  loc_15D
0x148  ldloc.s  4
0x14a  isinst   [mscorlib]System.IDisposable
0x14f  stloc.s  6
0x151  ldloc.s  6
0x153  brfalse.s loc_15C
0x155  ldloc.s  6
0x157  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15c  endfinally
0x15d  ldloc.0
0x15e  ret
```
