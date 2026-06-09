# Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::EnsureCatalogItemCanBeEdited

- ea: `0x12b40`
- end: `0x12c27`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::EnsureCatalogItemCanBeEdited`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1db90`

## callees

- `0x12b40`

## string_xrefs

- `0x12b78`: `ItemPath`
- `0x12bcd`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x12b40  ldarg.0
0x12b41  ldarg.1
0x12b42  ldstr    aParent// "parent"
0x12b47  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12b4c  stloc.0
0x12b4d  ldarg.0
0x12b4e  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x12b53  ldloc.0
0x12b54  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext)
0x12b59  pop
0x12b5a  ldloc.0
0x12b5b  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12b60  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x12b65  ldarg.2
0x12b66  ldstr    aName_0// "name"
0x12b6b  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string, string)
0x12b70  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0x12b75  stloc.1
0x12b76  ldarg.0
0x12b77  ldloc.1
0x12b78  ldstr    aItempath// "ItemPath"
0x12b7d  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12b82  stloc.2
0x12b83  ldarg.0
0x12b84  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x12b89  ldloc.2
0x12b8a  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext)
0x12b8f  stloc.3
0x12b90  ldarg.0
0x12b91  ldarg.s  4
0x12b93  ldstr    aParent// "parent"
0x12b98  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12b9d  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12ba2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x12ba7  ldarg.s  5
0x12ba9  ldstr    aName_0// "name"
0x12bae  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string, string)
0x12bb3  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0x12bb8  stloc.s  4
0x12bba  ldloc.3
0x12bbb  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ThisItemType()
0x12bc0  ldarg.3
0x12bc1  beq.s    loc_12BCA
0x12bc3  ldloc.1
0x12bc4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException::.ctor(string)
0x12bc9  throw
0x12bca  ldarg.0
0x12bcb  ldloc.s  4
0x12bcd  ldstr    aItempath// "ItemPath"
0x12bd2  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12bd7  stloc.s  6
0x12bd9  ldarg.0
0x12bda  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x12bdf  ldloc.s  6
0x12be1  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12be6  ldloca.s 5
0x12be8  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType&)
0x12bed  stloc.s  7
0x12bef  ldloc.1
0x12bf0  ldloc.s  4
0x12bf2  ldc.i4.5
0x12bf3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x12bf8  ldc.i4.0
0x12bf9  cgt.un
0x12bfb  ldloc.s  7
0x12bfd  and
0x12bfe  brfalse.s loc_12C08
0x12c00  ldloc.s  4
0x12c02  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException::.ctor(string)
0x12c07  throw
0x12c08  ldarg.0
0x12c09  ldarg.3
0x12c0a  ldloc.3
0x12c0b  callvirt instance unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_SecurityDescriptor()
0x12c10  ldloc.3
0x12c11  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x12c16  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12c1b  ldloc.2
0x12c1c  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x12c21  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::EnsureAllowedToEditItem(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, unsigned int8[], class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, string)
0x12c26  ret
```
