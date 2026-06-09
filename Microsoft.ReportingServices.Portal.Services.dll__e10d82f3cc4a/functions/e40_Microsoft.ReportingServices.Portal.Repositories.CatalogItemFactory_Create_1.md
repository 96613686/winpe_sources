# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create_1

- ea: `0xe40`
- end: `0xf0d`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create_1`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`
- `0xe20`

## callees

- `0xe40`
- `0x14e0`
- `0x1550`
- `0x1570`
- `0x15c0`
- `0x15f0`
- `0x1610`
- `0x1650`
- `0x1680`
- `0x16a0`
- `0x16c0`
- `0x16e0`
- `0x1710`
- `0xa900`
- `0x10330`

## string_xrefs

- `0xe43`: `itemDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarg.1
0xe41  brtrue.s loc_E4E
0xe43  ldstr    aItemdescriptor// "itemDescriptor"
0xe48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe4d  throw
0xe4e  ldarg.0
0xe4f  ldfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_userPrincipal
0xe54  brtrue.s loc_E61
0xe56  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_UserPrincipalIsNotSet()
0xe5b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe60  throw
0xe61  ldarg.1
0xe62  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0xe67  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType Microsoft.ReportingServices.Portal.Services.ODataExtensions.CatalogItemTypeExtensions::ToCatalogItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0xe6c  stloc.0
0xe6d  ldloc.0
0xe6e  ldc.i4.1
0xe6f  sub
0xe70  switch   loc_EB5, loc_EBD, loc_EDD, loc_EE5, loc_ED5, loc_ECD, loc_EA7, loc_F05, loc_EC5, loc_EED, loc_EF5, loc_EFD
0xea5  br.s     loc_F05
0xea7  ldarg.0
0xea8  ldarg.0
0xea9  ldfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_userPrincipal
0xeae  ldarg.1
0xeaf  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xeb4  ret
0xeb5  ldarg.0
0xeb6  ldarg.1
0xeb7  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateFolderCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xebc  ret
0xebd  ldarg.0
0xebe  ldarg.1
0xebf  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateReportCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xec4  ret
0xec5  ldarg.0
0xec6  ldarg.1
0xec7  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateLinkedReportCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xecc  ret
0xecd  ldarg.0
0xece  ldarg.1
0xecf  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Resource Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateResourceCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xed4  ret
0xed5  ldarg.0
0xed6  ldarg.1
0xed7  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateComponentCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xedc  ret
0xedd  ldarg.0
0xede  ldarg.1
0xedf  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateDataSourceCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xee4  ret
0xee5  ldarg.0
0xee6  ldarg.1
0xee7  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateDataSetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xeec  ret
0xeed  ldarg.0
0xeee  ldarg.1
0xeef  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateModelCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xef4  ret
0xef5  ldarg.0
0xef6  ldarg.1
0xef7  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreatePowerBIReportCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xefc  ret
0xefd  ldarg.0
0xefe  ldarg.1
0xeff  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateExcelCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xf04  ret
0xf05  ldarg.0
0xf06  ldarg.1
0xf07  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateUnknownCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xf0c  ret
```
