# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::get_Catalog

- ea: `0x9d0`
- end: `0x9ea`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::get_Catalog`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9d0`
- `0xa00`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  ldarg.0
0x9d1  ldfld    class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::_catalog
0x9d6  dup
0x9d7  brtrue.s loc_9E9
0x9d9  pop
0x9da  ldarg.0
0x9db  ldarg.0
0x9dc  call     instance class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::CreateCatalog()
0x9e1  dup
0x9e2  stloc.0
0x9e3  stfld    class [System.ComponentModel.Composition]System.ComponentModel.Composition.Primitives.ComposablePartCatalog Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::_catalog
0x9e8  ldloc.0
0x9e9  ret
```
