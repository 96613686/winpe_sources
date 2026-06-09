# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonTemplateStart

- ea: `0x1514e0`
- end: `0x1514f1`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonTemplateStart`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe9e80`

## callees

- `0x152580`

## string_xrefs

- `0x1514e1`: `MapPolygonTemplate`
- `0x1514e6`: `MapPolygonTemplateExprHost`

## pseudocode

```c

```

## disassembly

```asm
0x1514e0  ldarg.0
0x1514e1  ldstr    aMappolygontemp// "MapPolygonTemplate"
0x1514e6  ldstr    aMappolygontemp_0// "MapPolygonTemplateExprHost"
0x1514eb  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::TypeStart(string typeName, string baseType)
0x1514f0  ret
```
