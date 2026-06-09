# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::IsPowerViewMicroVersionedNamespace

- ea: `0xbb7f0`
- end: `0xbb855`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::IsPowerViewMicroVersionedNamespace`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb1d0`

## callees

- `0xbb7f0`
- `0x18a470`

## string_xrefs

- `0xbb821`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportdefinition`
- `0xbb833`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xbb845`: `http://schemas.microsoft.com/sqlserver/reporting/2013/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xbb7f0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xbb7f5  ldarg.0
0xbb7f6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb7fb  ldarg.0
0xbb7fc  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::m_validationNamespaceList
0xbb801  call     bool Microsoft.ReportingServices.ReportProcessing.ListUtils::ContainsWithOrdinalComparer(string item, class [mscorlib]System.Collections.Generic.List`1<string> list)
0xbb806  ldstr    aNotRdlNamespac// "Not rdl namespace: "
0xbb80b  ldarg.0
0xbb80c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb811  call     string [mscorlib]System.String::Concat(string, string)
0xbb816  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xbb81b  ldarg.0
0xbb81c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb821  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0xbb826  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xbb82b  brfalse.s loc_BB853
0xbb82d  ldarg.0
0xbb82e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb833  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xbb838  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xbb83d  brfalse.s loc_BB853
0xbb83f  ldarg.0
0xbb840  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb845  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0xbb84a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xbb84f  ldc.i4.0
0xbb850  ceq
0xbb852  ret
0xbb853  ldc.i4.1
0xbb854  ret
```
