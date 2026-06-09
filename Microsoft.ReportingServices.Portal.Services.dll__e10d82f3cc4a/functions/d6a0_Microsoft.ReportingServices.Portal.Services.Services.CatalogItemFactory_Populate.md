# Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::Populate

- ea: `0xd6a0`
- end: `0xd73a`
- name: `Microsoft.ReportingServices.Portal.Services.Services.CatalogItemFactory::Populate`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd640`
- `0xd650`
- `0xd670`
- `0xd680`
- `0xd690`

## callees

- `0xd6a0`
- `0x12c40`

## pseudocode

```c

```

## disassembly

```asm
0xd6a0  ldarg.2
0xd6a1  ldarg.1
0xd6a2  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ID()
0xd6a7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Id(string)
0xd6ac  ldarg.2
0xd6ad  ldarg.1
0xd6ae  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Name()
0xd6b3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Name(string)
0xd6b8  ldarg.2
0xd6b9  ldarg.1
0xd6ba  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Description()
0xd6bf  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Description(string)
0xd6c4  ldarg.2
0xd6c5  ldarg.1
0xd6c6  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreationDate()
0xd6cb  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_CreatedDate(valuetype [mscorlib]System.DateTime)
0xd6d0  ldarg.2
0xd6d1  ldarg.1
0xd6d2  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreatedBy()
0xd6d7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_CreatedBy(string)
0xd6dc  ldarg.2
0xd6dd  ldarg.1
0xd6de  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ModifiedDate()
0xd6e3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_ModifiedDate(valuetype [mscorlib]System.DateTime)
0xd6e8  ldarg.2
0xd6e9  ldarg.1
0xd6ea  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ModifiedBy()
0xd6ef  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_ModifiedBy(string)
0xd6f4  ldarg.2
0xd6f5  ldarg.1
0xd6f6  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Hidden()
0xd6fb  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Hidden(bool)
0xd700  ldarg.2
0xd701  ldarg.1
0xd702  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Path()
0xd707  brtrue.s loc_D70C
0xd709  ldnull
0xd70a  br.s     loc_D717
0xd70c  ldarg.1
0xd70d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Path()
0xd712  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xd717  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Path(string)
0xd71c  ldarg.2
0xd71d  ldarg.1
0xd71e  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0xd723  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.CatalogItemType Microsoft.ReportingServices.Portal.Services.Extensions.CatalogItemTypeExtensions::ToCatalogItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0xd728  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.CatalogItemType)
0xd72d  ldarg.2
0xd72e  ldarg.1
0xd72f  callvirt instance int32 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Size()
0xd734  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Models.ICatalogItem::set_Size(int32)
0xd739  ret
```
