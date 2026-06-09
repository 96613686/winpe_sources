# Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement_0

- ea: `0x5d50`
- end: `0x5e07`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElement_0`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5a00`
- `0x5bd0`
- `0x5d40`

## callees

- `0x4fb0`
- `0x5010`
- `0x5070`
- `0x5090`
- `0x5d50`
- `0x5e10`
- `0x6440`
- `0x6450`

## string_xrefs

- `0x5deb`: `Configuration`

## pseudocode

```c

```

## disassembly

```asm
0x5d50  ldarg.1
0x5d51  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5d56  ldarg.3
0x5d57  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5d5c  brfalse.s loc_5D69
0x5d5e  ldarg.1
0x5d5f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x5d64  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string element)
0x5d69  ldnull
0x5d6a  stloc.0
0x5d6b  ldarg.1
0x5d6c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5d71  ldstr    aName_0// "Name"
0x5d76  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5d7b  stloc.0
0x5d7c  ldloc.0
0x5d7d  brtrue.s loc_5D89
0x5d7f  ldstr    aName_0// "Name"
0x5d84  call     void Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowElementMissing(string element)
0x5d89  ldarg.2
0x5d8a  ldind.ref
0x5d8b  ldloc.0
0x5d8c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5d91  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Name(string value)
0x5d96  ldarg.0
0x5d97  ldarg.1
0x5d98  ldarg.2
0x5d99  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::ParseExtensionElementType(class [System.Xml]System.Xml.XmlNode child, class Microsoft.ReportingServices.Diagnostics.Extension& extension)
0x5d9e  ldarg.1
0x5d9f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5da4  ldstr    aVisible// "Visible"
0x5da9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5dae  stloc.0
0x5daf  ldloc.0
0x5db0  brfalse.s loc_5DC4
0x5db2  ldarg.2
0x5db3  ldind.ref
0x5db4  ldloc.0
0x5db5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5dba  call     bool [mscorlib]System.Boolean::Parse(string)
0x5dbf  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Visible(bool value)
0x5dc4  ldarg.1
0x5dc5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5dca  ldstr    aLogallexecutio// "LogAllExecutionRequests"
0x5dcf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5dd4  stloc.0
0x5dd5  ldloc.0
0x5dd6  brfalse.s loc_5DEA
0x5dd8  ldarg.2
0x5dd9  ldind.ref
0x5dda  ldloc.0
0x5ddb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5de0  call     bool [mscorlib]System.Boolean::Parse(string)
0x5de5  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_LogAllExecutionRequests(bool value)
0x5dea  ldarg.1
0x5deb  ldstr    aConfiguration// "Configuration"
0x5df0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5df5  stloc.1
0x5df6  ldloc.1
0x5df7  brfalse.s loc_5E06
0x5df9  ldarg.2
0x5dfa  ldind.ref
0x5dfb  ldloc.1
0x5dfc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5e01  callvirt instance void Microsoft.ReportingServices.Diagnostics.Extension::set_Configuration(string value)
0x5e06  ret
```
