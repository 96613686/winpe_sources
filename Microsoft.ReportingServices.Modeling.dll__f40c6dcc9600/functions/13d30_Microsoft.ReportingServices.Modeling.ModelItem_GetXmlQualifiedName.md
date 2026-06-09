# Microsoft.ReportingServices.Modeling.ModelItem::GetXmlQualifiedName

- ea: `0x13d30`
- end: `0x13d5e`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::GetXmlQualifiedName`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x299b0`

## callees

- `0xa0f0`
- `0xa120`
- `0xa130`
- `0x13d30`

## string_xrefs

- `0x13d40`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x13d30  ldarga.s 0
0x13d32  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Namespace()
0x13d37  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13d3c  brtrue.s loc_13D4A
0x13d3e  ldarga.s 0
0x13d40  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x13d45  call     instance void Microsoft.ReportingServices.Modeling.QName::set_Namespace(string value)
0x13d4a  ldarga.s 0
0x13d4c  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Name()
0x13d51  ldarga.s 0
0x13d53  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Namespace()
0x13d58  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x13d5d  ret
```
