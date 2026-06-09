# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSource

- ea: `0x2850`
- end: `0x294b`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSource`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x2850`
- `0x10c80`
- `0x116c0`

## pseudocode

```c

```

## disassembly

```asm
0x2850  ldarg.0
0x2851  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x2856  ldarg.2
0x2857  ldc.i4.3
0x2858  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ListExtensions(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionType)
0x285d  stloc.0
0x285e  ldarg.s  4
0x2860  call     void Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::LoadFromContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x2865  ldarg.s  4
0x2867  ldloc.0
0x2868  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::Validate(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>)
0x286d  ldarg.s  4
0x286f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2874  ldc.i4.5
0x2875  ldstr    aName// "Name"
0x287a  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::CheckItemName(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, string)
0x287f  ldarg.1
0x2880  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateDataSourceAction()
0x2885  stloc.1
0x2886  ldloc.1
0x2887  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::get_ActionParameters()
0x288c  ldarg.s  4
0x288e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2893  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x2898  ldloc.1
0x2899  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::get_ActionParameters()
0x289e  ldarg.3
0x289f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x28a4  ldloc.1
0x28a5  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::get_ActionParameters()
0x28aa  ldc.i4.0
0x28ab  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x28b0  ldloc.1
0x28b1  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::get_ActionParameters()
0x28b6  ldarg.s  4
0x28b8  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x28bd  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters::set_DataSourceDefinition(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition)
0x28c2  ldloc.1
0x28c3  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::get_ActionParameters()
0x28c8  ldc.i4.2
0x28c9  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x28ce  dup
0x28cf  ldc.i4.0
0x28d0  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x28d5  dup
0x28d6  ldstr    aHidden// "Hidden"
0x28db  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x28e0  dup
0x28e1  ldarg.s  4
0x28e3  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x28e8  brtrue.s loc_28F5
0x28ea  ldc.i4.0
0x28eb  stloc.2
0x28ec  ldloca.s 2
0x28ee  call     instance string [mscorlib]System.Boolean::ToString()
0x28f3  br.s     loc_28FE
0x28f5  ldc.i4.1
0x28f6  stloc.2
0x28f7  ldloca.s 2
0x28f9  call     instance string [mscorlib]System.Boolean::ToString()
0x28fe  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x2903  stelem.ref
0x2904  dup
0x2905  ldc.i4.1
0x2906  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x290b  dup
0x290c  ldstr    aDescription// "Description"
0x2911  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x2916  dup
0x2917  ldarg.s  4
0x2919  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x291e  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x2923  stelem.ref
0x2924  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x2929  ldloc.1
0x292a  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSourceActionParameters>::Execute()
0x292f  ldarg.0
0x2930  ldarg.1
0x2931  ldarg.2
0x2932  ldarg.0
0x2933  ldarg.3
0x2934  ldarg.s  4
0x2936  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x293b  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x2940  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x2945  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0x294a  ret
```
