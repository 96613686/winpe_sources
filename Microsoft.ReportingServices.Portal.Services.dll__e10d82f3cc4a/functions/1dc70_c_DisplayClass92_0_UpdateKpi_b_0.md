# <>c__DisplayClass92_0::<UpdateKpi>b__0

- ea: `0x1dc70`
- end: `0x1dd0b`
- name: `<>c__DisplayClass92_0::<UpdateKpi>b__0`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x3ed0`
- `0x4260`
- `0x12870`
- `0x1dc70`

## pseudocode

```c

```

## disassembly

```asm
0x1dc70  ldarg.0
0x1dc71  ldfld    bool <>c__DisplayClass92_0::updateProperties
0x1dc76  brfalse.s loc_1DCE0
0x1dc78  ldarg.0
0x1dc79  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass92_0::rsService
0x1dc7e  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateKpiAction()
0x1dc83  dup
0x1dc84  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters>::get_ActionParameters()
0x1dc89  dup
0x1dc8a  ldarg.0
0x1dc8b  ldfld    string <>c__DisplayClass92_0::oldName
0x1dc90  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x1dc95  dup
0x1dc96  ldarg.0
0x1dc97  ldfld    string <>c__DisplayClass92_0::parentPath
0x1dc9c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x1dca1  dup
0x1dca2  ldc.i4.1
0x1dca3  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x1dca8  ldarg.0
0x1dca9  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass92_0::<>4__this
0x1dcae  ldarg.0
0x1dcaf  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass92_0::item
0x1dcb4  ldarg.0
0x1dcb5  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass92_0::<>4__this
0x1dcba  ldftn    instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCatalogItem(valuetype [mscorlib]System.Guid id, string path, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType, bool throwIfNotExists, [out] valuetype [mscorlib]System.Guid& actualId, [out] string& actualPath)
0x1dcc0  newobj   instance void Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem::.ctor(object object, native int method)
0x1dcc5  ldloca.s 0
0x1dcc7  ldloca.s 1
0x1dcc9  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi item, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, [out] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[]& soapProperties, [out] class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection& sharedDataSets)
0x1dcce  dup
0x1dccf  ldloc.0
0x1dcd0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x1dcd5  ldloc.1
0x1dcd6  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters::set_SharedDataSets(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection)
0x1dcdb  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters>::PerformActionNow()
0x1dce0  ldarg.0
0x1dce1  ldfld    bool <>c__DisplayClass92_0::renameOrMove
0x1dce6  brfalse.s loc_1DD0A
0x1dce8  ldarg.0
0x1dce9  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass92_0::<>4__this
0x1dcee  ldarg.0
0x1dcef  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass92_0::rsService
0x1dcf4  ldarg.0
0x1dcf5  ldfld    string <>c__DisplayClass92_0::origItemPath
0x1dcfa  ldarg.0
0x1dcfb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass92_0::item
0x1dd00  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1dd05  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string sourcePath, string destPath)
0x1dd0a  ret
```
