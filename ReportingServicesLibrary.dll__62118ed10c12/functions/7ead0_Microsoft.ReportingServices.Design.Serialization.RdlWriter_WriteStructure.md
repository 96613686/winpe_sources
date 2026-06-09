# Microsoft.ReportingServices.Design.Serialization.RdlWriter::WriteStructure

- ea: `0x7ead0`
- end: `0x7eb61`
- name: `Microsoft.ReportingServices.Design.Serialization.RdlWriter::WriteStructure`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7e430`
- `0x7e6c0`

## callees

- `0x7e840`
- `0x7ead0`

## string_xrefs

- `0x7eb05`: `xmlns`
- `0x7eb20`: `xmlns`
- `0x7eb2b`: `http://schemas.microsoft.com/SQLServer/reporting/reportdesigner`
- `0x7eae3`: `http://schemas.microsoft.com/sqlserver/reporting/2005/01/reportdefinition`
- `0x7eb10`: `http://schemas.microsoft.com/sqlserver/reporting/2005/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0x7ead0  ldarg.1
0x7ead1  brfalse  loc_7EB60
0x7ead6  ldarg.3
0x7ead7  ldstr    asc_90EAC// ""
0x7eadc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7eae1  brfalse.s loc_7EAEA
0x7eae3  ldstr    aHttpSchemasMic_9// "http://schemas.microsoft.com/sqlserver/"...
0x7eae8  starg.s  3
0x7eaea  ldarg.0
0x7eaeb  ldfld    bool Microsoft.ReportingServices.Design.Serialization.RdlWriter::isRootWritten
0x7eaf0  brtrue.s loc_7EB3E
0x7eaf2  ldarg.0
0x7eaf3  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Design.Serialization.RdlWriter::writer
0x7eaf8  ldarg.2
0x7eaf9  ldarg.3
0x7eafa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x7eaff  ldarg.0
0x7eb00  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Design.Serialization.RdlWriter::writer
0x7eb05  ldstr    aXmlns// "xmlns"
0x7eb0a  ldstr    asc_90EAC// ""
0x7eb0f  ldnull
0x7eb10  ldstr    aHttpSchemasMic_9// "http://schemas.microsoft.com/sqlserver/"...
0x7eb15  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x7eb1a  ldarg.0
0x7eb1b  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Design.Serialization.RdlWriter::writer
0x7eb20  ldstr    aXmlns// "xmlns"
0x7eb25  ldstr    aRd// "rd"
0x7eb2a  ldnull
0x7eb2b  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/SQLServer/"...
0x7eb30  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x7eb35  ldarg.0
0x7eb36  ldc.i4.1
0x7eb37  stfld    bool Microsoft.ReportingServices.Design.Serialization.RdlWriter::isRootWritten
0x7eb3c  br.s     loc_7EB4B
0x7eb3e  ldarg.0
0x7eb3f  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Design.Serialization.RdlWriter::writer
0x7eb44  ldarg.2
0x7eb45  ldarg.3
0x7eb46  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x7eb4b  ldarg.0
0x7eb4c  ldarg.1
0x7eb4d  ldarg.s  4
0x7eb4f  ldarg.3
0x7eb50  call     instance void Microsoft.ReportingServices.Design.Serialization.RdlWriter::WriteStructureContent(object obj, class Microsoft.ReportingServices.Design.Serialization.StructMapping mapping, string ns)
0x7eb55  ldarg.0
0x7eb56  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Design.Serialization.RdlWriter::writer
0x7eb5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7eb60  ret
```
