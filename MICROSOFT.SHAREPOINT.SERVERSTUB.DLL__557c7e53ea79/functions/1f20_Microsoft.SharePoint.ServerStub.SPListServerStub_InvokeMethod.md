# Microsoft.SharePoint.ServerStub.SPListServerStub::InvokeMethod

- ea: `0x1f20`
- end: `0x28c1`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::InvokeMethod`
- size: `2465`
- prototype: ``
- caller_count: `0`
- callee_count: `55`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1030`
- `0x1610`
- `0x1650`
- `0x1670`
- `0x1680`
- `0x16a0`
- `0x16b0`
- `0x16e0`
- `0x1700`
- `0x1730`
- `0x1780`
- `0x17b0`
- `0x17d0`
- `0x1800`
- `0x1830`
- `0x1860`
- `0x1880`
- `0x18a0`
- `0x18b0`
- `0x18d0`
- `0x18f0`
- `0x1940`
- `0x1970`
- `0x19b0`
- `0x1a00`
- `0x1a50`
- `0x1a90`
- `0x1ad0`
- `0x1b20`
- `0x1b30`
- `0x1b40`
- `0x1b60`
- `0x1bc0`
- `0x1bd0`
- `0x1be0`
- `0x1c00`
- `0x1c20`
- `0x1c50`
- `0x1cb0`
- `0x1cf0`
- `0x1d10`
- `0x1d40`
- `0x1d60`
- `0x1d80`
- `0x1da0`
- `0x1dc0`
- `0x1de0`
- `0x1e00`
- `0x1e20`
- `0x1e30`

## string_xrefs

- `0x20ce`: `Update`
- `0x260d`: `Update`
- `0x20f5`: `DeleteObject`
- `0x265f`: `DeleteObject`
- `0x1fd7`: `CreateMappedView`
- `0x2406`: `CreateMappedView`
- `0x2025`: `SyncFlowTemplates`
- `0x24a8`: `SyncFlowTemplates`
- `0x2059`: `CreateDocumentAndGetEditLink`
- `0x2514`: `CreateDocumentAndGetEditLink`
- `0x2066`: `CreateDocumentWithDefaultName`
- `0x252f`: `CreateDocumentWithDefaultName`
- `0x2073`: `CreateDocument`
- `0x254a`: `CreateDocument`
- `0x2080`: `CreateDocumentFromTemplateStream`
- `0x2565`: `CreateDocumentFromTemplateStream`
- `0x208d`: `CreateDocumentFromTemplateBytes`
- `0x2580`: `CreateDocumentFromTemplateBytes`
- `0x209a`: `CreateDocumentFromTemplate`
- `0x259b`: `CreateDocumentFromTemplate`
- `0x20a7`: `CreateDocumentFromTemplateUsingPath`
- `0x25b6`: `CreateDocumentFromTemplateUsingPath`
- `0x20b4`: `SaveAsTemplate`
- `0x25d1`: `SaveAsTemplate`
- `0x20e8`: `BulkValidateUpdateListItems`
- `0x2644`: `BulkValidateUpdateListItems`
- `0x211c`: `GetListItemChangesSinceToken`
- `0x26b6`: `GetListItemChangesSinceToken`
- `0x21ec`: `AddItemUsingPath`
- `0x2867`: `AddItemUsingPath`
- `0x21f9`: `AddValidateUpdateItem`
- `0x2882`: `AddValidateUpdateItem`
- `0x2206`: `AddValidateUpdateItemUsingPath`
- `0x289d`: `AddValidateUpdateItemUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x1f20  ldarg.s  4
0x1f22  brtrue.s loc_1F2F
0x1f24  ldstr    aProxycontext// "proxyContext"
0x1f29  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f2e  throw
0x1f2f  ldarg.1
0x1f30  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x1f35  stloc.0
0x1f36  ldloc.0
0x1f37  brtrue.s loc_1F44
0x1f39  ldstr    aTarget// "target"
0x1f3e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f43  throw
0x1f44  ldarg.0
0x1f45  ldarg.2
0x1f46  ldarg.s  4
0x1f48  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1f4d  starg.s  2
0x1f4f  ldarg.2
0x1f50  dup
0x1f51  stloc.1
0x1f52  brfalse  loc_28B3
0x1f57  volatile.
0x1f59  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600008f-1
0x1f5e  brtrue   loc_2219
0x1f63  ldc.i4.s 0x35
0x1f65  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x1f6a  dup
0x1f6b  ldstr    aGetspecialfold// "GetSpecialFolderUrl"
0x1f70  ldc.i4.0
0x1f71  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1f76  dup
0x1f77  ldstr    aGetwebdavurl// "GetWebDavUrl"
0x1f7c  ldc.i4.1
0x1f7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1f82  dup
0x1f83  ldstr    aGetcheckedoutf// "GetCheckedOutFiles"
0x1f88  ldc.i4.2
0x1f89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1f8e  dup
0x1f8f  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x1f94  ldc.i4.3
0x1f95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1f9a  dup
0x1f9b  ldstr    aResetroleinher// "ResetRoleInheritance"
0x1fa0  ldc.i4.4
0x1fa1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fa6  dup
0x1fa7  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x1fac  ldc.i4.5
0x1fad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fb2  dup
0x1fb3  ldstr    aGetbloomfilter// "GetBloomFilter"
0x1fb8  ldc.i4.6
0x1fb9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fbe  dup
0x1fbf  ldstr    aGetbloomfilter_0// "GetBloomFilterWithCustomFields"
0x1fc4  ldc.i4.7
0x1fc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fca  dup
0x1fcb  ldstr    aSaveasnewview// "SaveAsNewView"
0x1fd0  ldc.i4.8
0x1fd1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fd6  dup
0x1fd7  ldstr    aCreatemappedvi// "CreateMappedView"
0x1fdc  ldc.i4.s 9
0x1fde  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1fe3  dup
0x1fe4  ldstr    aValidateappnam// "ValidateAppName"
0x1fe9  ldc.i4.s 0xA
0x1feb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1ff0  dup
0x1ff1  ldstr    aPublishmappedv// "PublishMappedView"
0x1ff6  ldc.i4.s 0xB
0x1ff8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1ffd  dup
0x1ffe  ldstr    aUnpublishmappe// "UnpublishMappedView"
0x2003  ldc.i4.s 0xC
0x2005  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x200a  dup
0x200b  ldstr    aGetmappedapp// "GetMappedApp"
0x2010  ldc.i4.s 0xD
0x2012  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2017  dup
0x2018  ldstr    aGetmappedapps// "GetMappedApps"
0x201d  ldc.i4.s 0xE
0x201f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2024  dup
0x2025  ldstr    aSyncflowtempla// "SyncFlowTemplates"
0x202a  ldc.i4.s 0xF
0x202c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2031  dup
0x2032  ldstr    aSyncflowinstan// "SyncFlowInstances"
0x2037  ldc.i4.s 0x10
0x2039  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x203e  dup
0x203f  ldstr    aSyncflowinstan_0// "SyncFlowInstance"
0x2044  ldc.i4.s 0x11
0x2046  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x204b  dup
0x204c  ldstr    aSyncflowcallba// "SyncFlowCallbackUrl"
0x2051  ldc.i4.s 0x12
0x2053  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2058  dup
0x2059  ldstr    aCreatedocument// "CreateDocumentAndGetEditLink"
0x205e  ldc.i4.s 0x13
0x2060  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2065  dup
0x2066  ldstr    aCreatedocument_0// "CreateDocumentWithDefaultName"
0x206b  ldc.i4.s 0x14
0x206d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2072  dup
0x2073  ldstr    aCreatedocument_1// "CreateDocument"
0x2078  ldc.i4.s 0x15
0x207a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x207f  dup
0x2080  ldstr    aCreatedocument_2// "CreateDocumentFromTemplateStream"
0x2085  ldc.i4.s 0x16
0x2087  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x208c  dup
0x208d  ldstr    aCreatedocument_3// "CreateDocumentFromTemplateBytes"
0x2092  ldc.i4.s 0x17
0x2094  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2099  dup
0x209a  ldstr    aCreatedocument_4// "CreateDocumentFromTemplate"
0x209f  ldc.i4.s 0x18
0x20a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20a6  dup
0x20a7  ldstr    aCreatedocument_5// "CreateDocumentFromTemplateUsingPath"
0x20ac  ldc.i4.s 0x19
0x20ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20b3  dup
0x20b4  ldstr    aSaveastemplate// "SaveAsTemplate"
0x20b9  ldc.i4.s 0x1A
0x20bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20c0  dup
0x20c1  ldstr    aReservelistite// "ReserveListItemId"
0x20c6  ldc.i4.s 0x1B
0x20c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20cd  dup
0x20ce  ldstr    aUpdate// "Update"
0x20d3  ldc.i4.s 0x1C
0x20d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20da  dup
0x20db  ldstr    aGetview// "GetView"
0x20e0  ldc.i4.s 0x1D
0x20e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20e7  dup
0x20e8  ldstr    aBulkvalidateup// "BulkValidateUpdateListItems"
0x20ed  ldc.i4.s 0x1E
0x20ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20f4  dup
0x20f5  ldstr    aDeleteobject// "DeleteObject"
0x20fa  ldc.i4.s 0x1F
0x20fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2101  dup
0x2102  ldstr    aRecycle// "Recycle"
0x2107  ldc.i4.s 0x20
0x2109  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x210e  dup
0x210f  ldstr    aGetchanges// "GetChanges"
0x2114  ldc.i4.s 0x21
0x2116  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x211b  dup
0x211c  ldstr    aGetlistitemcha// "GetListItemChangesSinceToken"
0x2121  ldc.i4.s 0x22
0x2123  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2128  dup
0x2129  ldstr    aGetfileextende// "getFileExtendedActivities"
0x212e  ldc.i4.s 0x23
0x2130  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2135  dup
0x2136  ldstr    aRenderextended// "RenderExtendedListFormData"
0x213b  ldc.i4.s 0x24
0x213d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2142  dup
0x2143  ldstr    aRenderlistform// "RenderListFormData"
0x2148  ldc.i4.s 0x25
0x214a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x214f  dup
0x2150  ldstr    aRenderlistdata// "RenderListData"
0x2155  ldc.i4.s 0x26
0x2157  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x215c  dup
0x215d  ldstr    aRenderlistdata_0// "RenderListDataAsStream"
0x2162  ldc.i4.s 0x27
0x2164  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2169  dup
0x216a  ldstr    aRenderlistfilt// "RenderListFilterData"
0x216f  ldc.i4.s 0x28
0x2171  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2176  dup
0x2177  ldstr    aRenderlistcont// "RenderListContextMenuData"
0x217c  ldc.i4.s 0x29
0x217e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2183  dup
0x2184  ldstr    aGetitems// "GetItems"
0x2189  ldc.i4.s 0x2A
0x218b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2190  dup
0x2191  ldstr    aGetitembyid// "GetItemById"
0x2196  ldc.i4.s 0x2B
0x2198  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x219d  dup
0x219e  ldstr    aGetitembystrin// "GetItemByStringId"
0x21a3  ldc.i4.s 0x2C
0x21a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21aa  dup
0x21ab  ldstr    aSetexemptfromb// "SetExemptFromBlockDownloadOfNonViewable"...
0x21b0  ldc.i4.s 0x2D
0x21b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21b7  dup
0x21b8  ldstr    aGetitembyuniqu// "GetItemByUniqueId"
0x21bd  ldc.i4.s 0x2E
0x21bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21c4  dup
0x21c5  ldstr    aGetrelatedfiel// "GetRelatedFields"
0x21ca  ldc.i4.s 0x2F
0x21cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21d1  dup
0x21d2  ldstr    aGetrelatedfiel_0// "GetRelatedFieldsExtendedData"
0x21d7  ldc.i4.s 0x30
0x21d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21de  dup
0x21df  ldstr    aAdditem// "AddItem"
0x21e4  ldc.i4.s 0x31
0x21e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21eb  dup
0x21ec  ldstr    aAdditemusingpa// "AddItemUsingPath"
0x21f1  ldc.i4.s 0x32
0x21f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x21f8  dup
0x21f9  ldstr    aAddvalidateupd// "AddValidateUpdateItem"
0x21fe  ldc.i4.s 0x33
0x2200  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2205  dup
0x2206  ldstr    aAddvalidateupd_0// "AddValidateUpdateItemUsingPath"
0x220b  ldc.i4.s 0x34
0x220d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2212  volatile.
0x2214  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600008f-1
0x2219  volatile.
0x221b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600008f-1
0x2220  ldloc.1
0x2221  ldloca.s 2
0x2223  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x2228  brfalse  loc_28B3
0x222d  ldloc.2
0x222e  switch   loc_230C, loc_2327, loc_2342, loc_235D, loc_2378, loc_2394, loc_23B0, loc_23CB, loc_23E6, loc_2401, loc_241C, loc_2437, loc_2452, loc_246D, loc_2488, loc_24A3, loc_24BE, loc_24D9, loc_24F4, loc_250F, loc_252A, loc_2545, loc_2560, loc_257B, loc_2596, loc_25B1, loc_25CC, loc_25E8, loc_2608, loc_2624, loc_263F, loc_265A, loc_2676, loc_2696, loc_26B1, loc_26CC, loc_26E7, loc_2702, loc_271D, loc_2738, loc_2753, loc_276E, loc_2789, loc_27A4, loc_27BF, loc_27DA, loc_27F6, loc_2811, loc_282C, loc_2847, loc_2862, loc_287D, loc_2898
0x2307  br       loc_28B3
0x230c  ldarg.s  5
0x230e  ldc.i4.0
0x230f  stind.i1
0x2310  ldarg.0
0x2311  ldstr    aGetspecialfold// "GetSpecialFolderUrl"
0x2316  ldarg.s  4
0x2318  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x231d  ldloc.0
0x231e  ldarg.3
0x231f  ldarg.s  4
0x2321  call     string Microsoft.SharePoint.ServerStub.SPListServerStub::GetSpecialFolderUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2326  ret
0x2327  ldarg.s  5
0x2329  ldc.i4.0
0x232a  stind.i1
0x232b  ldarg.0
0x232c  ldstr    aGetwebdavurl// "GetWebDavUrl"
0x2331  ldarg.s  4
0x2333  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2338  ldloc.0
0x2339  ldarg.3
0x233a  ldarg.s  4
0x233c  call     string Microsoft.SharePoint.ServerStub.SPListServerStub::GetWebDavUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2341  ret
0x2342  ldarg.s  5
0x2344  ldc.i4.0
0x2345  stind.i1
0x2346  ldarg.0
0x2347  ldstr    aGetcheckedoutf// "GetCheckedOutFiles"
0x234c  ldarg.s  4
0x234e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2353  ldloc.0
0x2354  ldarg.3
0x2355  ldarg.s  4
0x2357  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPCheckedOutFileCollection Microsoft.SharePoint.ServerStub.SPListServerStub::GetCheckedOutFiles_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x235c  ret
0x235d  ldarg.s  5
0x235f  ldc.i4.0
0x2360  stind.i1
0x2361  ldarg.0
0x2362  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x2367  ldarg.s  4
0x2369  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x236e  ldloc.0
0x236f  ldarg.3
0x2370  ldarg.s  4
0x2372  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client Microsoft.SharePoint.ServerStub.SPListServerStub::GetUserEffectivePermissions_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2377  ret
0x2378  ldarg.s  5
0x237a  ldc.i4.1
  ... truncated ...
```
