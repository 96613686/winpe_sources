# Microsoft.BIServer.Management.WebApi.ProductInfo::FromProductInfoEntity

- ea: `0x160`
- end: `0x16c`
- name: `Microsoft.BIServer.Management.WebApi.ProductInfo::FromProductInfoEntity`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3c0`

## callees

- `0xb0`
- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  brtrue.s loc_165
0x163  ldnull
0x164  ret
0x165  ldarg.0
0x166  newobj   instance void Microsoft.BIServer.Management.WebApi.ProductInfo::.ctor(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity productInfoEntity)
0x16b  ret
```
