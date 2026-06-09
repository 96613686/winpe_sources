# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningValidationStructureForElements

- ea: `0xba980`
- end: `0xba9a1`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningValidationStructureForElements`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xba850`

## callees

- `0xba9b0`

## string_xrefs

- `0xba98b`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0xba996`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xba980  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0xba985  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xba98a  dup
0xba98b  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0xba990  call     void Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetMicroVersionValidationStructure(class [System]System.Collections.Specialized.NameValueCollection validationStructure, string expandToThisNamespace)
0xba995  dup
0xba996  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xba99b  call     void Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetMicroVersionValidationStructure(class [System]System.Collections.Specialized.NameValueCollection validationStructure, string expandToThisNamespace)
0xba9a0  ret
```
