# Microsoft.ReportingServices.Library.Soap.ExtensionSettings::WriteToXml

- ea: `0x73380`
- end: `0x733b3`
- name: `Microsoft.ReportingServices.Library.Soap.ExtensionSettings::WriteToXml`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x73350`

## callees

- `0x70f10`
- `0x73380`

## string_xrefs

- `0x73385`: `ExtensionSettings`
- `0x73390`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x73380  ldarg.0
0x73381  brtrue.s loc_73384
0x73383  ret
0x73384  ldarg.1
0x73385  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x7338a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7338f  ldarg.1
0x73390  ldstr    aExtension_0// "Extension"
0x73395  ldarg.0
0x73396  ldfld    string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::Extension
0x7339b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x733a0  ldarg.0
0x733a1  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x733a6  ldarg.1
0x733a7  call     void Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::WriteThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, class [System.Xml]System.Xml.XmlTextWriter xml)
0x733ac  ldarg.1
0x733ad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x733b2  ret
```
