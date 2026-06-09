# Microsoft.BIServer.Management.WebApi.ProductInfo::ToProductInfoEntity

- ea: `0x120`
- end: `0x158`
- name: `Microsoft.BIServer.Management.WebApi.ProductInfo::ToProductInfoEntity`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x40`
- `0x60`
- `0x80`

## pseudocode

```c

```

## disassembly

```asm
0x120  newobj   instance void [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::.ctor()
0x125  dup
0x126  ldarg.0
0x127  call     instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x12c  stloc.0
0x12d  ldloca.s 0
0x12f  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType
0x135  callvirt instance string [mscorlib]System.Object::ToString()
0x13a  callvirt instance void [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::set_Sku(string)
0x13f  dup
0x140  ldarg.0
0x141  call     instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_DbSchemaHash()
0x146  callvirt instance void [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::set_DbSchemaHash(string)
0x14b  dup
0x14c  ldarg.0
0x14d  call     instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_BuildNumber()
0x152  callvirt instance void [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::set_BuildNumber(string)
0x157  ret
```
