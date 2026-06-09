# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapMarkerTemplateStart

- ea: `0x1514a0`
- end: `0x1514b1`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapMarkerTemplateStart`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xeae60`

## callees

- `0x152580`

## string_xrefs

- `0x1514a1`: `MapMarkerTemplate`
- `0x1514a6`: `MapMarkerTemplateExprHost`

## pseudocode

```c

```

## disassembly

```asm
0x1514a0  ldarg.0
0x1514a1  ldstr    aMapmarkertempl// "MapMarkerTemplate"
0x1514a6  ldstr    aMapmarkertempl_0// "MapMarkerTemplateExprHost"
0x1514ab  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::TypeStart(string typeName, string baseType)
0x1514b0  ret
```
