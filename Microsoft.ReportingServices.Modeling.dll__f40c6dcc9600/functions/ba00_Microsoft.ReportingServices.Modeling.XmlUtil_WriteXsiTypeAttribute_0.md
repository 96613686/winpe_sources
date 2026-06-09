# Microsoft.ReportingServices.Modeling.XmlUtil::WriteXsiTypeAttribute_0

- ea: `0xba00`
- end: `0xba29`
- name: `Microsoft.ReportingServices.Modeling.XmlUtil::WriteXsiTypeAttribute_0`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb9d0`

## string_xrefs

- `0xba06`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xba00  ldarg.0
0xba01  ldstr    aType// "type"
0xba06  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xba0b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string, string)
0xba10  ldarg.0
0xba11  ldarg.1
0xba12  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xba17  ldarg.1
0xba18  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xba1d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteQualifiedName(string, string)
0xba22  ldarg.0
0xba23  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0xba28  ret
```
