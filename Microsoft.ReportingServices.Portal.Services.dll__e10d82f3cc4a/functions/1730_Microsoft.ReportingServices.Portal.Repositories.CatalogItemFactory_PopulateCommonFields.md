# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields

- ea: `0x1730`
- end: `0x1815`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields`
- size: `229`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

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
- `0x2410`
- `0x4f70`
- `0x4fe0`

## callees

- `0x1730`
- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1730  ldarg.0
0x1731  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ID()
0x1736  brfalse.s loc_1749
0x1738  ldarg.1
0x1739  ldarg.0
0x173a  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ID()
0x173f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1744  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0x1749  ldarg.1
0x174a  ldarg.0
0x174b  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Name()
0x1750  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x1755  ldarg.1
0x1756  ldarg.0
0x1757  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Description()
0x175c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Description(string)
0x1761  ldarg.1
0x1762  ldarg.0
0x1763  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_MimeType()
0x1768  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x176d  ldarg.1
0x176e  ldarg.0
0x176f  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreationDate()
0x1774  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::ToDateTimeOffset(valuetype [mscorlib]System.DateTime dateTime)
0x1779  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedDate(valuetype [mscorlib]System.DateTimeOffset)
0x177e  ldarg.1
0x177f  ldarg.0
0x1780  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_CreatedBy()
0x1785  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedBy(string)
0x178a  ldarg.1
0x178b  ldarg.0
0x178c  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ModifiedDate()
0x1791  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::ToDateTimeOffset(valuetype [mscorlib]System.DateTime dateTime)
0x1796  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedDate(valuetype [mscorlib]System.DateTimeOffset)
0x179b  ldarg.1
0x179c  ldarg.0
0x179d  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ModifiedBy()
0x17a2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedBy(string)
0x17a7  ldarg.1
0x17a8  ldarg.0
0x17a9  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Hidden()
0x17ae  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Hidden(bool)
0x17b3  ldarg.1
0x17b4  ldarg.0
0x17b5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Path()
0x17ba  brtrue.s loc_17BF
0x17bc  ldnull
0x17bd  br.s     loc_17CA
0x17bf  ldarg.0
0x17c0  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Path()
0x17c5  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x17ca  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x17cf  ldarg.1
0x17d0  ldarg.0
0x17d1  callvirt instance int32 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Size()
0x17d6  conv.i8
0x17d7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Size(int64)
0x17dc  ldarg.1
0x17dd  ldarg.0
0x17de  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemMetadata [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ItemMetadata()
0x17e3  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemMetadata::get_ParentID()
0x17e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17ed  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x17f2  brtrue.s loc_17FF
0x17f4  ldloca.s 0
0x17f6  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x17fc  ldloc.0
0x17fd  br.s     loc_180F
0x17ff  ldarg.0
0x1800  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemMetadata [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_ItemMetadata()
0x1805  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemMetadata::get_ParentID()
0x180a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x180f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ParentFolderId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1814  ret
```
