# Microsoft.ReportingServices.Modeling.SemanticQuery::LoadCore

- ea: `0x23480`
- end: `0x234bc`
- name: `Microsoft.ReportingServices.Modeling.SemanticQuery::LoadCore`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x38110`

## callees

- `0xa730`
- `0xa750`
- `0xab10`
- `0xbaa0`
- `0x23480`
- `0x25bb0`
- `0x25be0`

## string_xrefs

- `0x2348b`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x23480  ldarg.1
0x23481  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Reader()
0x23486  ldstr    aSemanticquery// "SemanticQuery"
0x2348b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x23490  call     void Microsoft.ReportingServices.Modeling.XmlUtil::CheckElement(class [System.Xml]System.Xml.XmlReader xr, string localName, string namespaceUri)
0x23495  ldarg.1
0x23496  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x2349b  ldarg.0
0x2349c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x234a1  ldarg.1
0x234a2  ldstr    aSemanticquery// "SemanticQuery"
0x234a7  ldarg.0
0x234a8  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(string elementName, class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x234ad  leave.s  loc_234BB
0x234af  ldarg.1
0x234b0  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Validation()
0x234b5  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x234ba  endfinally
0x234bb  ret
```
