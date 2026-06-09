# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapLineTemplateStart

- ea: `0x151570`
- end: `0x151581`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapLineTemplateStart`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe9ae0`

## callees

- `0x152580`

## string_xrefs

- `0x151571`: `MapLineTemplate`
- `0x151576`: `MapLineTemplateExprHost`

## pseudocode

```c

```

## disassembly

```asm
0x151570  ldarg.0
0x151571  ldstr    aMaplinetemplat// "MapLineTemplate"
0x151576  ldstr    aMaplinetemplat_0// "MapLineTemplateExprHost"
0x15157b  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::TypeStart(string typeName, string baseType)
0x151580  ret
```
