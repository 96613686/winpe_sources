# Microsoft.ReportingServices.Library.CreateSystemResourceActionBase`2::PerformActionNow

- ea: `0xea90`
- end: `0xebe1`
- name: `Microsoft.ReportingServices.Library.CreateSystemResourceActionBase`2::PerformActionNow`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0xd120`
- `0xea90`
- `0x1e210`
- `0x1e270`
- `0x1e2e0`
- `0x1e510`
- `0x1f190`
- `0x1f1a0`
- `0x1f1b0`
- `0x22ff0`
- `0x233a0`
- `0x23590`
- `0x4a4f0`
- `0x4afb0`
- `0x56f00`

## string_xrefs

- `0xeb1f`: `ItemPath`
- `0xebcc`: `item is not TCreatedType`

## pseudocode

```c

```

## disassembly

```asm
0xea90  ldarg.0
0xea91  callvirt instance void class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::InitAndCheckParams()
0xea96  ldarg.0
0xea97  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0xea9c  box      var<u1>
0xeaa1  ldarg.0
0xeaa2  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0xeaa7  box      var<u1>
0xeaac  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemName()
0xeab1  ldstr    aName_1// "name"
0xeab6  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string, string)
0xeabb  callvirt instance void Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string value)
0xeac0  ldarg.0
0xeac1  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0xeac6  box      var<u1>
0xeacb  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ParentPath()
0xead0  stloc.0
0xead1  ldarg.0
0xead2  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xead7  ldloc.0
0xead8  ldstr    aParent_1// "parent"
0xeadd  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0xeae2  stloc.1
0xeae3  ldloc.1
0xeae4  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPathAsString()
0xeae9  call     bool Microsoft.ReportingServices.Library.SystemResourceManager::IsSystemResourcePath(string path)
0xeaee  brtrue.s loc_EAF7
0xeaf0  ldloc.0
0xeaf1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string)
0xeaf6  throw
0xeaf7  ldloc.1
0xeaf8  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0xeafd  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0xeb02  ldarg.0
0xeb03  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0xeb08  box      var<u1>
0xeb0d  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemName()
0xeb12  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0xeb17  stloc.2
0xeb18  ldarg.0
0xeb19  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb1e  ldloc.2
0xeb1f  ldstr    aItempath// "ItemPath"
0xeb24  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0xeb29  stloc.3
0xeb2a  ldarg.0
0xeb2b  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb30  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0xeb35  ldloc.3
0xeb36  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0xeb3b  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName)
0xeb40  brfalse.s loc_EB49
0xeb42  ldloc.2
0xeb43  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException::.ctor(string)
0xeb48  throw
0xeb49  ldarg.0
0xeb4a  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb4f  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemFactory Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0xeb54  ldloc.1
0xeb55  callvirt instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext)
0xeb5a  ldc.i4.1
0xeb5b  newarr   Microsoft.ReportingServices.Library.ItemType
0xeb60  dup
0xeb61  ldc.i4.0
0xeb62  ldc.i4.1
0xeb63  stelem.i4
0xeb64  callvirt instance void Microsoft.ReportingServices.Library.CatalogItem::ThrowIfWrongItemType(valuetype Microsoft.ReportingServices.Library.ItemType[] expectedItemTypes)
0xeb69  ldarg.0
0xeb6a  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb6f  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0xeb74  ldarg.0
0xeb75  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb7a  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0xeb7f  callvirt instance unsigned int8[] Microsoft.ReportingServices.Library.Security::get_SystemSecDesc()
0xeb84  ldc.i4.5
0xeb85  ldnull
0xeb86  callvirt instance bool Microsoft.ReportingServices.Library.Security::CheckAccess(unsigned int8[] secDesc, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation catOper, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0xeb8b  brtrue.s loc_EBA0
0xeb8d  ldarg.0
0xeb8e  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xeb93  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0xeb98  ldc.i4.s 0x59
0xeb9a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0xeb9f  throw
0xeba0  ldarg.0
0xeba1  call     instance valuetype Microsoft.ReportingServices.Library.ItemType class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::get_ItemType()
0xeba6  ldarg.0
0xeba7  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0xebac  call     class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::CreateCatalogItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType, class Microsoft.ReportingServices.Library.RSService service)
0xebb1  isinst   var<u1>
0xebb6  unbox.any var<u1>
0xebbb  stloc.s  4
0xebbd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xebc2  ldloc.s  4
0xebc4  box      var<u1>
0xebc9  ldnull
0xebca  cgt.un
0xebcc  ldstr    aItemIsNotTcrea// "item is not TCreatedType"
0xebd1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xebd6  ldarg.0
0xebd7  ldloc.1
0xebd8  ldloc.3
0xebd9  ldloc.s  4
0xebdb  call     instance void class Microsoft.ReportingServices.Library.CreateSystemResourceActionBase`2<var<u1>, !!T0>::PerformCreateActions(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, var<u1>)
0xebe0  ret
```
