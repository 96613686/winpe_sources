# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem

- ea: `0x5ff0`
- end: `0x6031`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem`
- size: `65`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a50`
- `0x5ac0`
- `0x5fc0`
- `0x65f0`
- `0x6ed0`
- `0x1e6d0`
- `0x1ed70`
- `0x1ee90`
- `0x1f010`

## callees

- `0x128e0`
- `0x1e5f0`

## pseudocode

```c

```

## disassembly

```asm
0x5ff0  newobj   instance void <>c__DisplayClass157_0::.ctor()
0x5ff5  stloc.0
0x5ff6  ldloc.0
0x5ff7  ldarg.1
0x5ff8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass157_0::rsService
0x5ffd  ldloc.0
0x5ffe  ldarg.2
0x5fff  stfld    string <>c__DisplayClass157_0::itemPath
0x6004  ldloc.0
0x6005  ldarg.0
0x6006  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass157_0::<>4__this
0x600b  ldloc.0
0x600c  ldnull
0x600d  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass157_0::catalogItem
0x6012  ldloc.0
0x6013  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass157_0::rsService
0x6018  ldloc.0
0x6019  ldftn    instance void <>c__DisplayClass157_0::<GetLibraryCatalogItem>b__0()
0x601f  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x6024  ldc.i4.1
0x6025  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType)
0x602a  ldloc.0
0x602b  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass157_0::catalogItem
0x6030  ret
```
