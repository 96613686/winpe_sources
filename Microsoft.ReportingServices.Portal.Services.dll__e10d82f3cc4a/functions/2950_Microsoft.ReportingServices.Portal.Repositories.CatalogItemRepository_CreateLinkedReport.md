# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateLinkedReport

- ea: `0x2950`
- end: `0x2a15`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateLinkedReport`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x2950`

## pseudocode

```c

```

## disassembly

```asm
0x2950  ldarg.1
0x2951  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateLinkedReportAction()
0x2956  stloc.0
0x2957  ldloc.0
0x2958  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::get_ActionParameters()
0x295d  ldarg.3
0x295e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2963  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x2968  ldloc.0
0x2969  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::get_ActionParameters()
0x296e  ldarg.3
0x296f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x2974  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x2979  ldloc.0
0x297a  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::get_ActionParameters()
0x297f  ldarg.3
0x2980  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport::get_Link()
0x2985  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters::set_LinkPath(string)
0x298a  ldloc.0
0x298b  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::get_ActionParameters()
0x2990  ldc.i4.2
0x2991  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x2996  dup
0x2997  ldc.i4.0
0x2998  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x299d  dup
0x299e  ldstr    aHidden// "Hidden"
0x29a3  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x29a8  dup
0x29a9  ldarg.3
0x29aa  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x29af  brtrue.s loc_29BC
0x29b1  ldc.i4.0
0x29b2  stloc.1
0x29b3  ldloca.s 1
0x29b5  call     instance string [mscorlib]System.Boolean::ToString()
0x29ba  br.s     loc_29C5
0x29bc  ldc.i4.1
0x29bd  stloc.1
0x29be  ldloca.s 1
0x29c0  call     instance string [mscorlib]System.Boolean::ToString()
0x29c5  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x29ca  stelem.ref
0x29cb  dup
0x29cc  ldc.i4.1
0x29cd  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x29d2  dup
0x29d3  ldstr    aDescription// "Description"
0x29d8  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x29dd  dup
0x29de  ldarg.3
0x29df  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x29e4  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x29e9  stelem.ref
0x29ea  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x29ef  ldloc.0
0x29f0  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateLinkedReportActionParameters>::Execute()
0x29f5  ldarg.0
0x29f6  ldarg.1
0x29f7  ldarg.2
0x29f8  ldarg.0
0x29f9  ldarg.3
0x29fa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x29ff  ldarg.3
0x2a00  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2a05  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x2a0a  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x2a0f  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport
0x2a14  ret
```
