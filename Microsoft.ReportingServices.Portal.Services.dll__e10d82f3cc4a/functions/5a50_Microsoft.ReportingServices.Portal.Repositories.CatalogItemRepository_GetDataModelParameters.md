# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataModelParameters

- ea: `0x5a50`
- end: `0x5ab3`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataModelParameters`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a00`
- `0x56b0`
- `0x5ff0`
- `0x9e80`
- `0x1e3d0`

## pseudocode

```c

```

## disassembly

```asm
0x5a50  newobj   instance void <>c__DisplayClass139_0::.ctor()
0x5a55  stloc.0
0x5a56  ldloc.0
0x5a57  ldarg.2
0x5a58  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass139_0::id
0x5a5d  ldloc.0
0x5a5e  ldarg.1
0x5a5f  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5a64  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass139_0::rsService
0x5a69  ldloc.0
0x5a6a  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass139_0::rsService
0x5a6f  ldloc.0
0x5a70  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass139_0::id
0x5a75  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x5a7a  stloc.1
0x5a7b  ldarg.0
0x5a7c  ldloc.0
0x5a7d  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass139_0::rsService
0x5a82  ldloc.1
0x5a83  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x5a88  ldc.i4.5
0x5a89  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x5a8e  ldloc.0
0x5a8f  ldnull
0x5a90  stfld    string <>c__DisplayClass139_0::dataModelParameters
0x5a95  ldloc.0
0x5a96  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass139_0::rsService
0x5a9b  ldloc.0
0x5a9c  ldftn    instance void <>c__DisplayClass139_0::<GetDataModelParameters>b__0()
0x5aa2  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5aa7  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x5aac  ldloc.0
0x5aad  ldfld    string <>c__DisplayClass139_0::dataModelParameters
0x5ab2  ret
```
