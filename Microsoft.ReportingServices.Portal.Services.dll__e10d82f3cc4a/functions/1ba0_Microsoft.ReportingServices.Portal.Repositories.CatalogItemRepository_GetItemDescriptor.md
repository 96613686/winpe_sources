# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor

- ea: `0x1ba0`
- end: `0x1bda`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor`
- size: `58`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x2410`
- `0x4f70`
- `0x4fe0`

## callees

- `0x128e0`
- `0x1cd70`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x1ba5  stloc.0
0x1ba6  ldloc.0
0x1ba7  ldarg.2
0x1ba8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass22_0::rsService
0x1bad  ldloc.0
0x1bae  ldarg.3
0x1baf  stfld    string <>c__DisplayClass22_0::path
0x1bb4  ldloc.0
0x1bb5  ldnull
0x1bb6  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor <>c__DisplayClass22_0::itemDescriptor
0x1bbb  ldloc.0
0x1bbc  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass22_0::rsService
0x1bc1  ldloc.0
0x1bc2  ldftn    instance void <>c__DisplayClass22_0::<GetItemDescriptor>b__0()
0x1bc8  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1bcd  ldc.i4.1
0x1bce  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType)
0x1bd3  ldloc.0
0x1bd4  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor <>c__DisplayClass22_0::itemDescriptor
0x1bd9  ret
```
