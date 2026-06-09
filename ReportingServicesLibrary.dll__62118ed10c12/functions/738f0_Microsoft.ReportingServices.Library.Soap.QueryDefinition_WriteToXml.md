# Microsoft.ReportingServices.Library.Soap.QueryDefinition::WriteToXml

- ea: `0x738f0`
- end: `0x7394b`
- name: `Microsoft.ReportingServices.Library.Soap.QueryDefinition::WriteToXml`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x73500`

## callees

- `0x738f0`

## string_xrefs

- `0x73900`: `CommandType`
- `0x73911`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x738f0  ldarg.0
0x738f1  brtrue.s loc_738F4
0x738f3  ret
0x738f4  ldarg.1
0x738f5  ldstr    aQuery// "Query"
0x738fa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x738ff  ldarg.1
0x73900  ldstr    aCommandtype// "CommandType"
0x73905  ldarg.0
0x73906  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandType
0x7390b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x73910  ldarg.1
0x73911  ldstr    aCommandtext// "CommandText"
0x73916  ldarg.0
0x73917  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandText
0x7391c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x73921  ldarg.0
0x73922  ldfld    bool Microsoft.ReportingServices.Library.Soap.QueryDefinition::TimeoutSpecified
0x73927  brfalse.s loc_73944
0x73929  ldarg.1
0x7392a  ldstr    aTimeout_0// "Timeout"
0x7392f  ldarg.0
0x73930  ldflda   int32 Microsoft.ReportingServices.Library.Soap.QueryDefinition::Timeout
0x73935  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogCulture()
0x7393a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7393f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x73944  ldarg.1
0x73945  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7394a  ret
```
