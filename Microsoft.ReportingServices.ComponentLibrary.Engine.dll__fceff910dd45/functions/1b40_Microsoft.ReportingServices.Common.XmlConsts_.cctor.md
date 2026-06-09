# Microsoft.ReportingServices.Common.XmlConsts::.cctor

- ea: `0x1b40`
- end: `0x1b4b`
- name: `Microsoft.ReportingServices.Common.XmlConsts::.cctor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1b40`: `http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x1b45  stsfld   string Microsoft.ReportingServices.Common.XmlConsts::DefaultNamespace
0x1b4a  ret
```
