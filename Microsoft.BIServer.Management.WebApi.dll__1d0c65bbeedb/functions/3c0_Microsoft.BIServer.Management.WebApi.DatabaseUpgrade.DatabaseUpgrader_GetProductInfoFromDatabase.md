# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromDatabase

- ea: `0x3c0`
- end: `0x3d1`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromDatabase`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2f0`

## callees

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  ldarg.0
0x3c1  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity> [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor::GetCurrentProductInfoAsync()
0x3c6  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity>::get_Result()
0x3cb  call     class Microsoft.BIServer.Management.WebApi.ProductInfo Microsoft.BIServer.Management.WebApi.ProductInfo::FromProductInfoEntity(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity productInfoEntity)
0x3d0  ret
```
