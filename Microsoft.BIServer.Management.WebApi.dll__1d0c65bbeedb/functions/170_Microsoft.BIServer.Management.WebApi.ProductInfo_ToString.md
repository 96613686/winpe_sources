# Microsoft.BIServer.Management.WebApi.ProductInfo::ToString

- ea: `0x170`
- end: `0x192`
- name: `Microsoft.BIServer.Management.WebApi.ProductInfo::ToString`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x40`
- `0x60`
- `0x80`

## pseudocode

```c

```

## disassembly

```asm
0x170  ldstr    aSku0Buildnumbe// "Sku: {0}, BuildNumber: {1}, DbSchemaHas"...
0x175  ldarg.0
0x176  call     instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x17b  box      [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType
0x180  ldarg.0
0x181  call     instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_BuildNumber()
0x186  ldarg.0
0x187  call     instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_DbSchemaHash()
0x18c  call     string [mscorlib]System.String::Format(string, object, object, object)
0x191  ret
```
