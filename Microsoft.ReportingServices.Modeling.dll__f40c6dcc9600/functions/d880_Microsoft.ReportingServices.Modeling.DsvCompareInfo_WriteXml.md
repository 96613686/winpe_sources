# Microsoft.ReportingServices.Modeling.DsvCompareInfo::WriteXml

- ea: `0xd880`
- end: `0xd8f4`
- name: `Microsoft.ReportingServices.Modeling.DsvCompareInfo::WriteXml`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd880`

## string_xrefs

- `0xd881`: `CompareInfo`

## pseudocode

```c

```

## disassembly

```asm
0xd880  ldarg.1
0xd881  ldstr    aCompareinfo// "CompareInfo"
0xd886  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xd88b  ldarg.0
0xd88c  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_culture
0xd891  brfalse.s loc_D8A9
0xd893  ldarg.1
0xd894  ldstr    aCulture_0// "Culture"
0xd899  ldarg.0
0xd89a  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_culture
0xd89f  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.XmlConvertEx::ToString(class [mscorlib]System.Globalization.CultureInfo)
0xd8a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xd8a9  ldarg.1
0xd8aa  ldstr    aIgnorecase// "IgnoreCase"
0xd8af  ldarg.0
0xd8b0  ldfld    bool Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_ignoreCase
0xd8b5  call     T0x2B000034
0xd8ba  ldarg.1
0xd8bb  ldstr    aIgnorekanatype// "IgnoreKanaType"
0xd8c0  ldarg.0
0xd8c1  ldfld    bool Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_ignoreKanaType
0xd8c6  call     T0x2B000034
0xd8cb  ldarg.1
0xd8cc  ldstr    aIgnorenonspace// "IgnoreNonSpace"
0xd8d1  ldarg.0
0xd8d2  ldfld    bool Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_ignoreNonSpace
0xd8d7  call     T0x2B000034
0xd8dc  ldarg.1
0xd8dd  ldstr    aIgnorewidth// "IgnoreWidth"
0xd8e2  ldarg.0
0xd8e3  ldfld    bool Microsoft.ReportingServices.Modeling.DsvCompareInfo::m_ignoreWidth
0xd8e8  call     T0x2B000034
0xd8ed  ldarg.1
0xd8ee  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xd8f3  ret
```
