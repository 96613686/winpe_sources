# Microsoft.ReportingServices.WebServer.Global::IsReportServerAsmx

- ea: `0x2c9d0`
- end: `0x2ca05`
- name: `Microsoft.ReportingServices.WebServer.Global::IsReportServerAsmx`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c950`
- `0x2d120`

## callees

- `0x2c9d0`
- `0x2cdb0`

## string_xrefs

- `0x2c9d1`: `/ReportService2005.asmx`
- `0x2c9de`: `/ReportService2006.asmx`
- `0x2c9eb`: `/ReportService2010.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x2c9d0  ldarg.0
0x2c9d1  ldstr    aReportservice2// "/ReportService2005.asmx"
0x2c9d6  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsServiceObjectRequest(string objectName)
0x2c9db  brtrue.s loc_2CA03
0x2c9dd  ldarg.0
0x2c9de  ldstr    aReportservice2_0// "/ReportService2006.asmx"
0x2c9e3  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsServiceObjectRequest(string objectName)
0x2c9e8  brtrue.s loc_2CA03
0x2c9ea  ldarg.0
0x2c9eb  ldstr    aReportservice2_3// "/ReportService2010.asmx"
0x2c9f0  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsServiceObjectRequest(string objectName)
0x2c9f5  brtrue.s loc_2CA03
0x2c9f7  ldarg.0
0x2c9f8  ldstr    aReportexecutio// "/ReportExecution2005.asmx"
0x2c9fd  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsServiceObjectRequest(string objectName)
0x2ca02  ret
0x2ca03  ldc.i4.1
0x2ca04  ret
```
