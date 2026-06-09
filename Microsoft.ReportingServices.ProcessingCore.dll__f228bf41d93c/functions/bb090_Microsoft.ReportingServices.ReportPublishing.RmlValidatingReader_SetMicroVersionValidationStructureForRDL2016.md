# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetMicroVersionValidationStructureForRDL2016

- ea: `0xbb090`
- end: `0xbb0b5`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetMicroVersionValidationStructureForRDL2016`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xba9b0`

## callees

- `0xbb1b0`

## string_xrefs

- `0xbb0a5`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0xbb096`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition/defaultfontfamily`

## pseudocode

```c

```

## disassembly

```asm
0xbb090  ldarg.0
0xbb091  ldstr    aDefaultfontfam// "DefaultFontFamily"
0xbb096  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/sqlserver/"...
0xbb09b  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb0a0  ldstr    aReport// "Report"
0xbb0a5  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbb0aa  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb0af  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb0b4  ret
```
