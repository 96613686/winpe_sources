# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetIsFavorite

- ea: `0x6170`
- end: `0x61aa`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetIsFavorite`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e4a0`
- `0x1e500`

## callees

- `0x6170`
- `0x128c0`
- `0x1e670`

## pseudocode

```c

```

## disassembly

```asm
0x6170  newobj   instance void <>c__DisplayClass163_0::.ctor()
0x6175  stloc.0
0x6176  ldloc.0
0x6177  ldarg.2
0x6178  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass163_0::catalogItem
0x617d  ldloc.0
0x617e  ldarg.1
0x617f  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass163_0::rsService
0x6184  ldloc.0
0x6185  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass163_0::catalogItem
0x618a  brfalse.s loc_61A3
0x618c  ldloc.0
0x618d  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass163_0::rsService
0x6192  ldloc.0
0x6193  ldftn    instance void <>c__DisplayClass163_0::<SetIsFavorite>b__0()
0x6199  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x619e  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x61a3  ldloc.0
0x61a4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass163_0::catalogItem
0x61a9  ret
```
