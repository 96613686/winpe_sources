# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeCreated

- ea: `0x3e40`
- end: `0x3e73`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeCreated`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`
- `0x2a20`
- `0x5b60`

## callees

- `0x128c0`
- `0x1db30`

## pseudocode

```c

```

## disassembly

```asm
0x3e40  newobj   instance void <>c__DisplayClass87_0::.ctor()
0x3e45  stloc.0
0x3e46  ldloc.0
0x3e47  ldarg.1
0x3e48  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass87_0::rsService
0x3e4d  ldloc.0
0x3e4e  ldarg.2
0x3e4f  stfld    string <>c__DisplayClass87_0::parentPath
0x3e54  ldloc.0
0x3e55  ldarg.3
0x3e56  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass87_0::item
0x3e5b  ldloc.0
0x3e5c  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass87_0::rsService
0x3e61  ldloc.0
0x3e62  ldftn    instance void <>c__DisplayClass87_0::<EnsureCatalogItemCanBeCreated>b__0()
0x3e68  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3e6d  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x3e72  ret
```
