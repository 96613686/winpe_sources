# Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::EnsureCatalogItemCanBeCreated

- ea: `0x12aa0`
- end: `0x12b40`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::EnsureCatalogItemCanBeCreated`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1db40`

## callees

- `0x12aa0`

## string_xrefs

- `0x12af3`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x12aa0  ldarg.0
0x12aa1  ldarg.1
0x12aa2  ldstr    aParent// "parent"
0x12aa7  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12aac  stloc.0
0x12aad  ldarg.0
0x12aae  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x12ab3  ldloc.0
0x12ab4  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext)
0x12ab9  stloc.1
0x12aba  ldloc.1
0x12abb  ldc.i4.7
0x12abc  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType
0x12ac1  dup
0x12ac2  ldtoken  valuetype __StaticArrayInitTypeSize=28 <PrivateImplementationDetails>::F0616F564989C7CCC1B6FBE49F3123BD118D7222
0x12ac7  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x12acc  dup
0x12acd  ldc.i4.0
0x12ace  ldarg.2
0x12acf  stelem.i4
0x12ad0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfWrongItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType[])
0x12ad5  ldloc.0
0x12ad6  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12adb  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x12ae0  ldarg.3
0x12ae1  ldstr    aName_0// "name"
0x12ae6  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string, string)
0x12aeb  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0x12af0  stloc.2
0x12af1  ldarg.0
0x12af2  ldloc.2
0x12af3  ldstr    aItempath// "ItemPath"
0x12af8  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x12afd  stloc.3
0x12afe  ldarg.0
0x12aff  ldloc.1
0x12b00  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ThisItemType()
0x12b05  ldarg.s  4
0x12b07  ldloc.1
0x12b08  callvirt instance unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_SecurityDescriptor()
0x12b0d  ldloc.1
0x12b0e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x12b13  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12b18  ldloc.3
0x12b19  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x12b1e  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::EnsureAllowedAsSubitem(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, unsigned int8[], class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, string)
0x12b23  ldarg.0
0x12b24  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x12b29  ldloc.3
0x12b2a  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x12b2f  ldloca.s 4
0x12b31  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType&)
0x12b36  brfalse.s loc_12B3F
0x12b38  ldloc.2
0x12b39  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException::.ctor(string)
0x12b3e  throw
0x12b3f  ret
```
