# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningValidationStructureForAttributes

- ea: `0xbb0c0`
- end: `0xbb17f`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningValidationStructureForAttributes`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xba850`

## callees

- `0xbb1b0`

## string_xrefs

- `0xbb103`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0xbb0d0`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0xbb0f4`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0xbb118`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb127`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb13c`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb14b`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb160`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb16f`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb0df`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xbb0c0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0xbb0c5  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xbb0ca  dup
0xbb0cb  ldstr    aName_1// "Name"
0xbb0d0  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0xbb0d5  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb0da  ldstr    aReportsection// "ReportSection"
0xbb0df  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbb0e4  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb0e9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb0ee  dup
0xbb0ef  ldstr    aName_1// "Name"
0xbb0f4  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0xbb0f9  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb0fe  ldstr    aReportsection// "ReportSection"
0xbb103  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0xbb108  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb10d  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb112  dup
0xbb113  ldstr    aValuetype// "ValueType"
0xbb118  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb11d  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb122  ldstr    aFontfamily// "FontFamily"
0xbb127  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb12c  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb131  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb136  dup
0xbb137  ldstr    aValuetype// "ValueType"
0xbb13c  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb141  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb146  ldstr    aColor// "Color"
0xbb14b  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb150  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb155  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb15a  dup
0xbb15b  ldstr    aValuetype// "ValueType"
0xbb160  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb165  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb16a  ldstr    aBackgroundcolo// "BackgroundColor"
0xbb16f  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb174  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb179  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbb17e  ret
```
