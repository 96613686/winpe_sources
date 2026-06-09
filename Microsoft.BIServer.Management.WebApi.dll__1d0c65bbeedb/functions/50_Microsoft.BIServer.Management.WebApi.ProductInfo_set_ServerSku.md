# Microsoft.BIServer.Management.WebApi.ProductInfo::set_ServerSku

- ea: `0x50`
- end: `0x58`
- name: `Microsoft.BIServer.Management.WebApi.ProductInfo::set_ServerSku`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb0`
- `0x3e0`

## pseudocode

```c

```

## disassembly

```asm
0x50  ldarg.0
0x51  ldarg.1
0x52  stfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::<ServerSku>k__BackingField
0x57  ret
```
