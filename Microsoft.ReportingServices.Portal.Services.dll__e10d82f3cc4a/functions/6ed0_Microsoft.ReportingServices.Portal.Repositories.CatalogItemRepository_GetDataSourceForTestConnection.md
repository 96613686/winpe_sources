# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSourceForTestConnection

- ea: `0x6ed0`
- end: `0x6f22`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSourceForTestConnection`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a00`
- `0x5ff0`
- `0x9e80`
- `0xdd60`
- `0x1ecf0`

## pseudocode

```c

```

## disassembly

```asm
0x6ed0  newobj   instance void <>c__DisplayClass191_0::.ctor()
0x6ed5  stloc.0
0x6ed6  ldloc.0
0x6ed7  ldarg.3
0x6ed8  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass191_0::dataSourceId
0x6edd  ldarg.1
0x6ede  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x6ee3  stloc.1
0x6ee4  ldloc.1
0x6ee5  ldarg.2
0x6ee6  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x6eeb  stloc.2
0x6eec  ldarg.0
0x6eed  ldloc.1
0x6eee  ldloc.2
0x6eef  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x6ef4  ldc.i4.5
0x6ef5  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x6efa  ldarg.0
0x6efb  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x6f00  ldarg.2
0x6f01  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x6f06  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_Result()
0x6f0b  ldloc.0
0x6f0c  ldftn    instance bool <>c__DisplayClass191_0::<GetDataSourceForTestConnection>b__0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity 'ds')
0x6f12  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, bool>::.ctor(object, native int)
0x6f17  call     T0x2B00005B
0x6f1c  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithDecryptedSecret(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity dataSourceEntity)
0x6f21  ret
```
