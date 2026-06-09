# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningSchemas

- ea: `0xbb180`
- end: `0xbb1a2`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::SetupMicroVersioningSchemas`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xba850`

## string_xrefs

- `0xbb187`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0xbb192`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition/defaultfontfamily`

## pseudocode

```c

```

## disassembly

```asm
0xbb180  ldarg.0
0xbb181  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xbb186  dup
0xbb187  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbb18c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb191  dup
0xbb192  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/sqlserver/"...
0xbb197  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb19c  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_serverSupportedSchemas
0xbb1a1  ret
```
