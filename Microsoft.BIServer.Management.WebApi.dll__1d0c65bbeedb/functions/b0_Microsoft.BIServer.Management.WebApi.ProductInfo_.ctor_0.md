# Microsoft.BIServer.Management.WebApi.ProductInfo::.ctor_0

- ea: `0xb0`
- end: `0x112`
- name: `Microsoft.BIServer.Management.WebApi.ProductInfo::.ctor_0`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x160`

## callees

- `0x50`
- `0x70`
- `0x90`
- `0xb0`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldarg.0
0xb1  call     instance void [mscorlib]System.Object::.ctor()
0xb6  ldarg.1
0xb7  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::get_Sku()
0xbc  ldloca.s 0
0xbe  call     T0x2B000001
0xc3  brtrue.s loc_E0
0xc5  ldc.i4.0
0xc6  stloc.0
0xc7  ldstr    aProductinfoent// "ProductInfoEntity: Sku value '{0}' gets"...
0xcc  ldc.i4.1
0xcd  newarr   [mscorlib]System.Object
0xd2  dup
0xd3  ldc.i4.0
0xd4  ldarg.1
0xd5  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::get_Sku()
0xda  stelem.ref
0xdb  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0xe0  ldarg.0
0xe1  ldloc.0
0xe2  call     instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_ServerSku(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType value)
0xe7  ldarg.0
0xe8  ldarg.1
0xe9  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::get_DbSchemaHash()
0xee  dup
0xef  brtrue.s loc_F7
0xf1  pop
0xf2  ldsfld   string [mscorlib]System.String::Empty
0xf7  call     instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_DbSchemaHash(string value)
0xfc  ldarg.0
0xfd  ldarg.1
0xfe  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ProductInfoEntity::get_BuildNumber()
0x103  dup
0x104  brtrue.s loc_10C
0x106  pop
0x107  ldsfld   string [mscorlib]System.String::Empty
0x10c  call     instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_BuildNumber(string value)
0x111  ret
```
