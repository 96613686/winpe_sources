# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::SaveProductInfoToDatabase

- ea: `0x3a0`
- end: `0x3b2`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::SaveProductInfoToDatabase`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2f0`

## callees

- `0x120`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.0
0x3a1  ldarg.1
0x3a2  callvirt instance class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity Microsoft.BIServer.Management.WebApi.ProductInfo::ToProductInfoEntity()
0x3a7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor::AddProductInfoAsync(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity)
0x3ac  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x3b1  ret
```
