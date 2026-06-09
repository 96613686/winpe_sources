# Microsoft.ReportingServices.Portal.Repositories.SystemService::GetDefaultServerProductName

- ea: `0x87f0`
- end: `0x8804`
- name: `Microsoft.ReportingServices.Portal.Repositories.SystemService::GetDefaultServerProductName`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x87d0`
- `0x87f0`

## string_xrefs

- `0x87f8`: `SQL Server Reporting Services`

## pseudocode

```c

```

## disassembly

```asm
0x87f0  ldarg.0
0x87f1  call     instance bool Microsoft.ReportingServices.Portal.Repositories.SystemService::IsBiServer()
0x87f6  brtrue.s loc_87FE
0x87f8  ldstr    aSqlServerRepor// "SQL Server Reporting Services"
0x87fd  ret
0x87fe  ldstr    aPowerBiReportS// "Power BI Report Server"
0x8803  ret
```
