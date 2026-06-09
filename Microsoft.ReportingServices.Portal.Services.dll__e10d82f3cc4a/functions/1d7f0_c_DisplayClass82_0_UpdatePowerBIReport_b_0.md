# <>c__DisplayClass82_0::<UpdatePowerBIReport>b__0

- ea: `0x1d7f0`
- end: `0x1d9ca`
- name: `<>c__DisplayClass82_0::<UpdatePowerBIReport>b__0`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x3b60`
- `0x3be0`
- `0x3ed0`
- `0x3f30`
- `0x6940`
- `0x6f30`
- `0x108c0`
- `0x1d7f0`

## pseudocode

```c

```

## disassembly

```asm
0x1d7f0  ldarg.0
0x1d7f1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d7f6  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0x1d7fb  brfalse  loc_1D8EF
0x1d800  ldc.i4.2
0x1d801  newarr   [mscorlib]System.String
0x1d806  dup
0x1d807  ldc.i4.0
0x1d808  ldstr    aSql// "SQL"
0x1d80d  stelem.ref
0x1d80e  dup
0x1d80f  ldc.i4.1
0x1d810  ldstr    aStorecontent// "StoreContent"
0x1d815  stelem.ref
0x1d816  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x1d81b  stloc.2
0x1d81c  ldarg.0
0x1d81d  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass82_0::rsService
0x1d822  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPowerBIReportContentsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetPowerBIReportContentsAction()
0x1d827  dup
0x1d828  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters>::get_ActionParameters()
0x1d82d  ldarg.0
0x1d82e  ldfld    string <>c__DisplayClass82_0::origItemPath
0x1d833  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemActionParameters::set_ItemPath(string)
0x1d838  dup
0x1d839  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters>::get_ActionParameters()
0x1d83e  ldarg.0
0x1d83f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d844  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent Microsoft.ReportingServices.Portal.Services.Extensions.CatalogItemExtensions::ToCatalogItemStreamContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x1d849  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemContentActionParameters::set_CatalogItemContent(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent)
0x1d84e  dup
0x1d84f  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters>::get_ActionParameters()
0x1d854  dup
0x1d855  ldarg.0
0x1d856  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d85b  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetOriginalPbiStream()
0x1d860  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters::set_Original(class [mscorlib]System.IO.Stream)
0x1d865  dup
0x1d866  ldarg.0
0x1d867  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d86c  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetPbixStream()
0x1d871  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters::set_Pbix(class [mscorlib]System.IO.Stream)
0x1d876  dup
0x1d877  ldarg.0
0x1d878  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d87d  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetModelStream()
0x1d882  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters::set_Model(class [mscorlib]System.IO.Stream)
0x1d887  ldarg.0
0x1d888  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d88d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelParameters()
0x1d892  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x1d897  stloc.3
0x1d898  ldloc.3
0x1d899  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters::set_DataModelParameters(string)
0x1d89e  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdatePowerBIReportActionParameters>::PerformActionNow()
0x1d8a3  leave.s  loc_1D8AF
0x1d8a5  ldloc.2
0x1d8a6  brfalse.s loc_1D8AE
0x1d8a8  ldloc.2
0x1d8a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d8ae  endfinally
0x1d8af  ldarg.0
0x1d8b0  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d8b5  ldarg.0
0x1d8b6  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass82_0::userPrincipal
0x1d8bb  ldarg.0
0x1d8bc  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass82_0::origItemId
0x1d8c1  ldarg.0
0x1d8c2  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d8c7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataSources()
0x1d8cc  ldc.i4.1
0x1d8cd  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelDataSourcesTrusted(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid itemId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources, bool isOverwrite)
0x1d8d2  ldarg.0
0x1d8d3  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d8d8  ldarg.0
0x1d8d9  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass82_0::origItemId
0x1d8de  ldarg.0
0x1d8df  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d8e4  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelRoles()
0x1d8e9  ldc.i4.1
0x1d8ea  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelRolesTrusted(valuetype [mscorlib]System.Guid itemId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> dataModelRoles, bool isOverwrite)
0x1d8ef  ldarg.0
0x1d8f0  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d8f5  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x1d8fa  ldarg.0
0x1d8fb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass82_0::origItemId
0x1d900  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x1d905  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_Result()
0x1d90a  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__82_1
0x1d90f  dup
0x1d910  brtrue.s loc_1D929
0x1d912  pop
0x1d913  ldsfld   class <>c <>c::<>9
0x1d918  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<UpdatePowerBIReport>b__82_1(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity x)
0x1d91e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0x1d923  dup
0x1d924  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__82_1
0x1d929  call     T0x2B000001
0x1d92e  stloc.0
0x1d92f  ldarg.0
0x1d930  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d935  ldloc.0
0x1d936  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsModelRefreshAllowed(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> updatedDataModelDatasources)
0x1d93b  stloc.1
0x1d93c  ldarg.0
0x1d93d  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d942  ldarg.0
0x1d943  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d948  ldloc.1
0x1d949  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateModelRefreshPropertyIfRequired(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item, bool modelRefreshAllowed)
0x1d94e  ldarg.0
0x1d94f  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d954  ldarg.0
0x1d955  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass82_0::rsService
0x1d95a  ldarg.0
0x1d95b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d960  ldarg.0
0x1d961  ldfld    string <>c__DisplayClass82_0::origItemPath
0x1d966  ldarg.0
0x1d967  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d96c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x1d971  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__82_2
0x1d976  dup
0x1d977  brtrue.s loc_1D990
0x1d979  pop
0x1d97a  ldsfld   class <>c <>c::<>9
0x1d97f  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<UpdatePowerBIReport>b__82_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property x)
0x1d985  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x1d98a  dup
0x1d98b  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__82_2
0x1d990  call     T0x2B000019
0x1d995  call     T0x2B00001A
0x1d99a  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateItemProperties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, string itemPath, [opt] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[] additionalProperties)
0x1d99f  ldarg.0
0x1d9a0  ldfld    bool <>c__DisplayClass82_0::renameOrMove
0x1d9a5  brfalse.s loc_1D9C9
0x1d9a7  ldarg.0
0x1d9a8  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass82_0::<>4__this
0x1d9ad  ldarg.0
0x1d9ae  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass82_0::rsService
0x1d9b3  ldarg.0
0x1d9b4  ldfld    string <>c__DisplayClass82_0::origItemPath
0x1d9b9  ldarg.0
0x1d9ba  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <>c__DisplayClass82_0::item
0x1d9bf  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1d9c4  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string sourcePath, string destPath)
0x1d9c9  ret
```
