# Microsoft.ReportingServices.Library.CreateItemAction`2::PerformActionNow

- ea: `0x1f340`
- end: `0x1f5fb`
- name: `Microsoft.ReportingServices.Library.CreateItemAction`2::PerformActionNow`
- size: `699`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0xd150`
- `0x1d6f0`
- `0x1e210`
- `0x1e270`
- `0x1e2e0`
- `0x1e510`
- `0x1f190`
- `0x1f1a0`
- `0x1f1b0`
- `0x1f230`
- `0x1f340`
- `0x227e0`
- `0x22e40`
- `0x233a0`
- `0x23590`
- `0x4a680`

## string_xrefs

- `0x1f3e8`: `ItemPath`
- `0x1f4d3`: `ItemPath`
- `0x1f50b`: `item is not TCreatedType`

## pseudocode

```c

```

## disassembly

```asm
0x1f340  ldarg.0
0x1f341  callvirt instance void class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::InitAndCheckParams()
0x1f346  ldarg.0
0x1f347  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f34c  box      var<u1>
0x1f351  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ParentPath()
0x1f356  stloc.0
0x1f357  ldc.i4.0
0x1f358  stloc.1
0x1f359  ldc.i4.0
0x1f35a  stloc.2
0x1f35b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f360  stloc.s  4
0x1f362  ldnull
0x1f363  stloc.s  5
0x1f365  ldarg.0
0x1f366  callvirt instance bool class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::get_AllowVirtualItems()
0x1f36b  brfalse  loc_1F446
0x1f370  ldloc.0
0x1f371  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f376  brfalse.s loc_1F39A
0x1f378  ldarg.0
0x1f379  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f37e  ldstr    asc_96832// "/"
0x1f383  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath::.ctor(string)
0x1f388  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath source)
0x1f38d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1f392  stloc.0
0x1f393  ldc.i4.1
0x1f394  stloc.1
0x1f395  br       loc_1F446
0x1f39a  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsViaPortal()
0x1f39f  brfalse  loc_1F446
0x1f3a4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f3a9  stloc.s  0xA
0x1f3ab  ldnull
0x1f3ac  stloc.s  0xB
0x1f3ae  ldarg.0
0x1f3af  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f3b4  ldloc.0
0x1f3b5  ldstr    aParent_1// "parent"
0x1f3ba  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x1f3bf  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x1f3c4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1f3c9  ldarg.0
0x1f3ca  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f3cf  box      var<u1>
0x1f3d4  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemName()
0x1f3d9  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0x1f3de  stloc.s  0xC
0x1f3e0  ldarg.0
0x1f3e1  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f3e6  ldloc.s  0xC
0x1f3e8  ldstr    aItempath// "ItemPath"
0x1f3ed  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x1f3f2  stloc.s  0xD
0x1f3f4  ldarg.0
0x1f3f5  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f3fa  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1f3ff  ldloc.s  0xD
0x1f401  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x1f406  ldloca.s 2
0x1f408  ldloca.s 0xA
0x1f40a  ldloca.s 0xB
0x1f40c  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] unsigned int8[]& secDesc)
0x1f411  brfalse.s loc_1F436
0x1f413  ldloc.2
0x1f414  ldc.i4.8
0x1f415  bne.un.s loc_1F436
0x1f417  ldarg.0
0x1f418  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f41d  box      var<u1>
0x1f422  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ParentPath()
0x1f427  stloc.0
0x1f428  ldloc.2
0x1f429  stloc.3
0x1f42a  ldloc.s  0xA
0x1f42c  stloc.s  4
0x1f42e  ldloc.s  0xB
0x1f430  stloc.s  5
0x1f432  ldc.i4.1
0x1f433  stloc.1
0x1f434  br.s     loc_1F446
0x1f436  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1f43b  ldc.i4.2
0x1f43c  ldstr    aTheApiCallToEd// "The api call to EditSession did not cam"...
0x1f441  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1f446  ldarg.0
0x1f447  ldloc.2
0x1f448  call     instance void class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::set_ResolvedItemType(valuetype Microsoft.ReportingServices.Library.ItemType)
0x1f44d  ldarg.0
0x1f44e  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f453  ldloc.0
0x1f454  ldstr    aParent_1// "parent"
0x1f459  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x1f45e  stloc.s  6
0x1f460  ldarg.0
0x1f461  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f466  box      var<u1>
0x1f46b  ldarg.0
0x1f46c  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f471  box      var<u1>
0x1f476  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemName()
0x1f47b  ldstr    aName_1// "name"
0x1f480  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string, string)
0x1f485  callvirt instance void Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string value)
0x1f48a  ldloc.s  6
0x1f48c  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x1f491  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1f496  ldarg.0
0x1f497  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f49c  box      var<u1>
0x1f4a1  callvirt instance string Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemName()
0x1f4a6  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath(string, string)
0x1f4ab  stloc.s  7
0x1f4ad  ldloc.1
0x1f4ae  brfalse.s loc_1F4CB
0x1f4b0  ldarg.0
0x1f4b1  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f4b6  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator)
0x1f4bb  stloc.s  8
0x1f4bd  ldloc.s  8
0x1f4bf  ldloc.s  7
0x1f4c1  ldc.i4.s 0x10
0x1f4c3  callvirt instance bool class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::SetPath(string, valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathOptions)
0x1f4c8  pop
0x1f4c9  br.s     loc_1F4DF
0x1f4cb  ldarg.0
0x1f4cc  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f4d1  ldloc.s  7
0x1f4d3  ldstr    aItempath// "ItemPath"
0x1f4d8  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x1f4dd  stloc.s  8
0x1f4df  ldarg.0
0x1f4e0  call     instance valuetype Microsoft.ReportingServices.Library.ItemType class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::get_ItemType()
0x1f4e5  ldarg.0
0x1f4e6  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f4eb  call     class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::CreateCatalogItem(valuetype Microsoft.ReportingServices.Library.ItemType itemType, class Microsoft.ReportingServices.Library.RSService service)
0x1f4f0  isinst   var<u1>
0x1f4f5  unbox.any var<u1>
0x1f4fa  stloc.s  9
0x1f4fc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1f501  ldloc.s  9
0x1f503  box      var<u1>
0x1f508  ldnull
0x1f509  cgt.un
0x1f50b  ldstr    aItemIsNotTcrea// "item is not TCreatedType"
0x1f510  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1f515  ldloc.1
0x1f516  brtrue   loc_1F5DB
0x1f51b  ldarg.0
0x1f51c  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f521  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1f526  ldloc.s  8
0x1f528  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x1f52d  ldloca.s 3
0x1f52f  ldloca.s 4
0x1f531  ldloca.s 5
0x1f533  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] unsigned int8[]& secDesc)
0x1f538  brfalse  loc_1F5DB
0x1f53d  ldarg.0
0x1f53e  callvirt instance bool class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::get_IsUpdateSupported()
0x1f543  brfalse  loc_1F5D3
0x1f548  ldloc.s  9
0x1f54a  box      var<u1>
0x1f54f  isinst   Microsoft.ReportingServices.Library.IEditSessionAware
0x1f554  brfalse.s loc_1F5B1
0x1f556  ldarg.0
0x1f557  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f55c  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemFactory Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x1f561  ldloc.s  6
0x1f563  callvirt instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext)
0x1f568  stloc.s  0xE
0x1f56a  ldarg.0
0x1f56b  call     instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_ActionParameters()
0x1f570  box      var<u1>
0x1f575  callvirt instance bool Microsoft.ReportingServices.Library.CreateItemActionParameters::get_SkipSecurityCheck()
0x1f57a  brtrue.s loc_1F5B1
0x1f57c  ldarg.0
0x1f57d  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f582  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x1f587  ldc.i4.1
0x1f588  ldloc.s  0xE
0x1f58a  callvirt instance unsigned int8[] Microsoft.ReportingServices.Library.CatalogItem::get_SecurityDescriptor()
0x1f58f  ldc.i4.4
0x1f590  ldloc.s  6
0x1f592  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x1f597  callvirt instance bool Microsoft.ReportingServices.Library.Security::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType catItemType, unsigned int8[] secDesc, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation fldOper, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath folderPath)
0x1f59c  brtrue.s loc_1F5B1
0x1f59e  ldarg.0
0x1f59f  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<var<u1>>::get_Service()
0x1f5a4  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x1f5a9  ldc.i4.s 0x59
0x1f5ab  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x1f5b0  throw
0x1f5b1  ldloc.s  9
0x1f5b3  box      var<u1>
0x1f5b8  ldloc.s  8
0x1f5ba  ldloc.s  4
0x1f5bc  ldloc.s  5
0x1f5be  callvirt instance void Microsoft.ReportingServices.Library.CatalogItem::Initialize(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, valuetype [mscorlib]System.Guid itemID, unsigned int8[] securityDescriptor)
0x1f5c3  ldarg.0
0x1f5c4  ldloc.s  8
0x1f5c6  ldloc.s  9
0x1f5c8  ldloc.3
0x1f5c9  ldloc.s  4
0x1f5cb  ldloc.s  5
0x1f5cd  call     instance void class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::PerformUpdateActions(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, var<u1>, void, valuetype Microsoft.ReportingServices.Library.ItemType, valuetype [mscorlib]System.Guid)
0x1f5d2  ret
0x1f5d3  ldloc.s  7
0x1f5d5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException::.ctor(string)
0x1f5da  throw
0x1f5db  ldloc.s  9
0x1f5dd  box      var<u1>
0x1f5e2  ldloc.s  8
0x1f5e4  ldloc.s  4
0x1f5e6  ldloc.s  5
0x1f5e8  callvirt instance void Microsoft.ReportingServices.Library.CatalogItem::Initialize(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, valuetype [mscorlib]System.Guid itemID, unsigned int8[] securityDescriptor)
0x1f5ed  ldarg.0
0x1f5ee  ldloc.s  6
0x1f5f0  ldloc.s  8
0x1f5f2  ldloc.s  9
0x1f5f4  ldloc.1
0x1f5f5  call     instance void class Microsoft.ReportingServices.Library.CreateItemAction`2<var<u1>, !!T0>::PerformCreateActions(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, var<u1>, void)
0x1f5fa  ret
```
