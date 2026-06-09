# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteXmlType

- ea: `0xadf0`
- end: `0xaf4d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::WriteXmlType`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaa90`
- `0xac50`

## callees

- `0xa4f0`
- `0xadf0`

## pseudocode

```c

```

## disassembly

```asm
0xadf0  ldarg.1
0xadf1  ldc.i4.3
0xadf2  sub
0xadf3  switch   loc_AEB4, loc_AF2B, loc_AED6, loc_AEC5, loc_AEA3, loc_AEF8, loc_AE5F, loc_AF09, loc_AEE7, loc_AF1A, loc_AE92, loc_AE81, loc_AE4E, loc_AE70, loc_AF3C, loc_AE3D
0xae38  br       loc_AF3C
0xae3d  ldarg.0
0xae3e  ldstr    aType_0// "type"
0xae43  ldstr    aXsdString// "xsd:string"
0xae48  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xae4d  ret
0xae4e  ldarg.0
0xae4f  ldstr    aType_0// "type"
0xae54  ldstr    aXsdDecimal// "xsd:decimal"
0xae59  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xae5e  ret
0xae5f  ldarg.0
0xae60  ldstr    aType_0// "type"
0xae65  ldstr    aXsdInteger// "xsd:integer"
0xae6a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xae6f  ret
0xae70  ldarg.0
0xae71  ldstr    aType_0// "type"
0xae76  ldstr    aXsdDatetime// "xsd:dateTime"
0xae7b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xae80  ret
0xae81  ldarg.0
0xae82  ldstr    aType_0// "type"
0xae87  ldstr    aXsdDouble// "xsd:double"
0xae8c  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xae91  ret
0xae92  ldarg.0
0xae93  ldstr    aType_0// "type"
0xae98  ldstr    aXsdFloat// "xsd:float"
0xae9d  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaea2  ret
0xaea3  ldarg.0
0xaea4  ldstr    aType_0// "type"
0xaea9  ldstr    aXsdInteger// "xsd:integer"
0xaeae  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaeb3  ret
0xaeb4  ldarg.0
0xaeb5  ldstr    aType_0// "type"
0xaeba  ldstr    aXsdBoolean// "xsd:boolean"
0xaebf  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaec4  ret
0xaec5  ldarg.0
0xaec6  ldstr    aType_0// "type"
0xaecb  ldstr    aXsdInteger// "xsd:integer"
0xaed0  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaed5  ret
0xaed6  ldarg.0
0xaed7  ldstr    aType_0// "type"
0xaedc  ldstr    aXsdInteger// "xsd:integer"
0xaee1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaee6  ret
0xaee7  ldarg.0
0xaee8  ldstr    aType_0// "type"
0xaeed  ldstr    aXsdInteger// "xsd:integer"
0xaef2  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaef7  ret
0xaef8  ldarg.0
0xaef9  ldstr    aType_0// "type"
0xaefe  ldstr    aXsdInteger// "xsd:integer"
0xaf03  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaf08  ret
0xaf09  ldarg.0
0xaf0a  ldstr    aType_0// "type"
0xaf0f  ldstr    aXsdInteger// "xsd:integer"
0xaf14  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaf19  ret
0xaf1a  ldarg.0
0xaf1b  ldstr    aType_0// "type"
0xaf20  ldstr    aXsdInteger// "xsd:integer"
0xaf25  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaf2a  ret
0xaf2b  ldarg.0
0xaf2c  ldstr    aType_0// "type"
0xaf31  ldstr    aXsdString// "xsd:string"
0xaf36  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaf3b  ret
0xaf3c  ldarg.0
0xaf3d  ldstr    aType_0// "type"
0xaf42  ldstr    aXsdString// "xsd:string"
0xaf47  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xaf4c  ret
```
