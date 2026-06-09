# Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::Create_0

- ea: `0xd5d0`
- end: `0xd63a`
- name: `Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::Create_0`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xd5c0`

## callees

- `0xd5d0`
- `0xd640`
- `0xd650`
- `0xd670`
- `0xd680`
- `0xd690`
- `0x12c40`

## string_xrefs

- `0xd5e1`: `itemDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0xd5d0  ldarg.1
0xd5d1  brtrue.s loc_D5DE
0xd5d3  ldstr    aUserprincipal// "userPrincipal"
0xd5d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd5dd  throw
0xd5de  ldarg.2
0xd5df  brtrue.s loc_D5EC
0xd5e1  ldstr    aItemdescriptor// "itemDescriptor"
0xd5e6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd5eb  throw
0xd5ec  ldarg.2
0xd5ed  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0xd5f2  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.CatalogItemType Microsoft.ReportingServices.Portal.Services.Extensions.CatalogItemTypeExtensions::ToCatalogItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0xd5f7  stloc.0
0xd5f8  ldloc.0
0xd5f9  ldc.i4.6
0xd5fa  bgt.s    loc_D606
0xd5fc  ldloc.0
0xd5fd  ldc.i4.1
0xd5fe  beq.s    loc_D612
0xd600  ldloc.0
0xd601  ldc.i4.6
0xd602  beq.s    loc_D61A
0xd604  br.s     loc_D632
0xd606  ldloc.0
0xd607  ldc.i4.s 0xA
0xd609  beq.s    loc_D622
0xd60b  ldloc.0
0xd60c  ldc.i4.s 0xB
0xd60e  beq.s    loc_D62A
0xd610  br.s     loc_D632
0xd612  ldarg.0
0xd613  ldarg.2
0xd614  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.IFolderCatalogItem Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::CreateFolderCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xd619  ret
0xd61a  ldarg.0
0xd61b  ldarg.2
0xd61c  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.IResourceCatalogItem Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::CreateResourceCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xd621  ret
0xd622  ldarg.0
0xd623  ldarg.2
0xd624  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.IPowerBIReportCatalogItem Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::CreatePowerBIReportCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xd629  ret
0xd62a  ldarg.0
0xd62b  ldarg.2
0xd62c  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.IExcelWorkbookCatalogItem Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::CreateExcelWorkbookCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xd631  ret
0xd632  ldarg.0
0xd633  ldarg.2
0xd634  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::CreateUnknownCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor)
0xd639  ret
```
