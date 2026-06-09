# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelParameters

- ea: `0x5ac0`
- end: `0x5b1d`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelParameters`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a00`
- `0x56b0`
- `0x5ff0`
- `0x9e80`
- `0x1e410`

## pseudocode

```c

```

## disassembly

```asm
0x5ac0  newobj   instance void <>c__DisplayClass140_0::.ctor()
0x5ac5  stloc.0
0x5ac6  ldloc.0
0x5ac7  ldarg.2
0x5ac8  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass140_0::id
0x5acd  ldloc.0
0x5ace  ldarg.3
0x5acf  stfld    string <>c__DisplayClass140_0::parameters
0x5ad4  ldloc.0
0x5ad5  ldarg.1
0x5ad6  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5adb  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass140_0::rsService
0x5ae0  ldloc.0
0x5ae1  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass140_0::rsService
0x5ae6  ldloc.0
0x5ae7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass140_0::id
0x5aec  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x5af1  stloc.1
0x5af2  ldarg.0
0x5af3  ldloc.0
0x5af4  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass140_0::rsService
0x5af9  ldloc.1
0x5afa  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x5aff  ldc.i4.4
0x5b00  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x5b05  ldloc.0
0x5b06  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass140_0::rsService
0x5b0b  ldloc.0
0x5b0c  ldftn    instance void <>c__DisplayClass140_0::<SetDataModelParameters>b__0()
0x5b12  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5b17  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x5b1c  ret
```
