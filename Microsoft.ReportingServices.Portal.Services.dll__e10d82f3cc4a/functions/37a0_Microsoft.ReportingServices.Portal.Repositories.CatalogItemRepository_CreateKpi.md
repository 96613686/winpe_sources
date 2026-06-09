# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateKpi

- ea: `0x37a0`
- end: `0x3806`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateKpi`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x4260`
- `0x12870`

## pseudocode

```c

```

## disassembly

```asm
0x37a0  ldarg.1
0x37a1  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateKpiAction()
0x37a6  dup
0x37a7  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters>::get_ActionParameters()
0x37ac  dup
0x37ad  ldarg.3
0x37ae  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x37b3  dup
0x37b4  ldarg.s  4
0x37b6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x37bb  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x37c0  ldarg.0
0x37c1  ldarg.s  4
0x37c3  ldarg.0
0x37c4  ldftn    instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCatalogItem(valuetype [mscorlib]System.Guid id, string path, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType, bool throwIfNotExists, [out] valuetype [mscorlib]System.Guid& actualId, [out] string& actualPath)
0x37ca  newobj   instance void Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem::.ctor(object object, native int method)
0x37cf  ldloca.s 0
0x37d1  ldloca.s 1
0x37d3  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi item, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, [out] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[]& soapProperties, [out] class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection& sharedDataSets)
0x37d8  dup
0x37d9  ldloc.0
0x37da  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x37df  ldloc.1
0x37e0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters::set_SharedDataSets(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection)
0x37e5  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateKpiActionParameters>::Execute()
0x37ea  ldarg.0
0x37eb  ldarg.1
0x37ec  ldarg.2
0x37ed  ldarg.0
0x37ee  ldarg.3
0x37ef  ldarg.s  4
0x37f1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x37f6  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x37fb  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x3800  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi
0x3805  ret
```
