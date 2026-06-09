# Microsoft.SharePoint.ServerStub.SPListServerStub::InvokeMethod_0

- ea: `0x7580`
- end: `0x7f21`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::InvokeMethod_0`
- size: `2465`
- prototype: ``
- caller_count: `0`
- callee_count: `55`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13d0`
- `0x6c70`
- `0x6cb0`
- `0x6cd0`
- `0x6ce0`
- `0x6d00`
- `0x6d10`
- `0x6d40`
- `0x6d60`
- `0x6d90`
- `0x6de0`
- `0x6e10`
- `0x6e30`
- `0x6e60`
- `0x6e90`
- `0x6ec0`
- `0x6ee0`
- `0x6f00`
- `0x6f10`
- `0x6f30`
- `0x6f50`
- `0x6fa0`
- `0x6fd0`
- `0x7010`
- `0x7060`
- `0x70b0`
- `0x70f0`
- `0x7130`
- `0x7180`
- `0x7190`
- `0x71a0`
- `0x71c0`
- `0x7220`
- `0x7230`
- `0x7240`
- `0x7260`
- `0x7280`
- `0x72b0`
- `0x7310`
- `0x7350`
- `0x7370`
- `0x73a0`
- `0x73c0`
- `0x73e0`
- `0x7400`
- `0x7420`
- `0x7440`
- `0x7460`
- `0x7480`
- `0x7490`

## string_xrefs

- `0x772e`: `Update`
- `0x7c6d`: `Update`
- `0x7755`: `DeleteObject`
- `0x7cbf`: `DeleteObject`
- `0x7637`: `CreateMappedView`
- `0x7a66`: `CreateMappedView`
- `0x7685`: `SyncFlowTemplates`
- `0x7b08`: `SyncFlowTemplates`
- `0x76b9`: `CreateDocumentAndGetEditLink`
- `0x7b74`: `CreateDocumentAndGetEditLink`
- `0x76c6`: `CreateDocumentWithDefaultName`
- `0x7b8f`: `CreateDocumentWithDefaultName`
- `0x76d3`: `CreateDocument`
- `0x7baa`: `CreateDocument`
- `0x76e0`: `CreateDocumentFromTemplateStream`
- `0x7bc5`: `CreateDocumentFromTemplateStream`
- `0x76ed`: `CreateDocumentFromTemplateBytes`
- `0x7be0`: `CreateDocumentFromTemplateBytes`
- `0x76fa`: `CreateDocumentFromTemplate`
- `0x7bfb`: `CreateDocumentFromTemplate`
- `0x7707`: `CreateDocumentFromTemplateUsingPath`
- `0x7c16`: `CreateDocumentFromTemplateUsingPath`
- `0x7714`: `SaveAsTemplate`
- `0x7c31`: `SaveAsTemplate`
- `0x7748`: `BulkValidateUpdateListItems`
- `0x7ca4`: `BulkValidateUpdateListItems`
- `0x777c`: `GetListItemChangesSinceToken`
- `0x7d16`: `GetListItemChangesSinceToken`
- `0x784c`: `AddItemUsingPath`
- `0x7ec7`: `AddItemUsingPath`
- `0x7859`: `AddValidateUpdateItem`
- `0x7ee2`: `AddValidateUpdateItem`
- `0x7866`: `AddValidateUpdateItemUsingPath`
- `0x7efd`: `AddValidateUpdateItemUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x7580  ldarg.s  4
0x7582  brtrue.s loc_758F
0x7584  ldstr    aProxycontext// "proxyContext"
0x7589  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x758e  throw
0x758f  ldarg.1
0x7590  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x7595  stloc.0
0x7596  ldloc.0
0x7597  brtrue.s loc_75A4
0x7599  ldstr    aTarget// "target"
0x759e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x75a3  throw
0x75a4  ldarg.0
0x75a5  ldarg.2
0x75a6  ldarg.s  4
0x75a8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x75ad  starg.s  2
0x75af  ldarg.2
0x75b0  dup
0x75b1  stloc.1
0x75b2  brfalse  loc_7F13
0x75b7  volatile.
0x75b9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d4-1
0x75be  brtrue   loc_7879
0x75c3  ldc.i4.s 0x35
0x75c5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x75ca  dup
0x75cb  ldstr    aGetspecialfold// "GetSpecialFolderUrl"
0x75d0  ldc.i4.0
0x75d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x75d6  dup
0x75d7  ldstr    aGetwebdavurl// "GetWebDavUrl"
0x75dc  ldc.i4.1
0x75dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x75e2  dup
0x75e3  ldstr    aGetcheckedoutf// "GetCheckedOutFiles"
0x75e8  ldc.i4.2
0x75e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x75ee  dup
0x75ef  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x75f4  ldc.i4.3
0x75f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x75fa  dup
0x75fb  ldstr    aResetroleinher// "ResetRoleInheritance"
0x7600  ldc.i4.4
0x7601  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7606  dup
0x7607  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x760c  ldc.i4.5
0x760d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7612  dup
0x7613  ldstr    aGetbloomfilter// "GetBloomFilter"
0x7618  ldc.i4.6
0x7619  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x761e  dup
0x761f  ldstr    aGetbloomfilter_0// "GetBloomFilterWithCustomFields"
0x7624  ldc.i4.7
0x7625  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x762a  dup
0x762b  ldstr    aSaveasnewview// "SaveAsNewView"
0x7630  ldc.i4.8
0x7631  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7636  dup
0x7637  ldstr    aCreatemappedvi// "CreateMappedView"
0x763c  ldc.i4.s 9
0x763e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7643  dup
0x7644  ldstr    aValidateappnam// "ValidateAppName"
0x7649  ldc.i4.s 0xA
0x764b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7650  dup
0x7651  ldstr    aPublishmappedv// "PublishMappedView"
0x7656  ldc.i4.s 0xB
0x7658  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x765d  dup
0x765e  ldstr    aUnpublishmappe// "UnpublishMappedView"
0x7663  ldc.i4.s 0xC
0x7665  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x766a  dup
0x766b  ldstr    aGetmappedapp// "GetMappedApp"
0x7670  ldc.i4.s 0xD
0x7672  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7677  dup
0x7678  ldstr    aGetmappedapps// "GetMappedApps"
0x767d  ldc.i4.s 0xE
0x767f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7684  dup
0x7685  ldstr    aSyncflowtempla// "SyncFlowTemplates"
0x768a  ldc.i4.s 0xF
0x768c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7691  dup
0x7692  ldstr    aSyncflowinstan// "SyncFlowInstances"
0x7697  ldc.i4.s 0x10
0x7699  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x769e  dup
0x769f  ldstr    aSyncflowinstan_0// "SyncFlowInstance"
0x76a4  ldc.i4.s 0x11
0x76a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76ab  dup
0x76ac  ldstr    aSyncflowcallba// "SyncFlowCallbackUrl"
0x76b1  ldc.i4.s 0x12
0x76b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76b8  dup
0x76b9  ldstr    aCreatedocument// "CreateDocumentAndGetEditLink"
0x76be  ldc.i4.s 0x13
0x76c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76c5  dup
0x76c6  ldstr    aCreatedocument_0// "CreateDocumentWithDefaultName"
0x76cb  ldc.i4.s 0x14
0x76cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76d2  dup
0x76d3  ldstr    aCreatedocument_1// "CreateDocument"
0x76d8  ldc.i4.s 0x15
0x76da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76df  dup
0x76e0  ldstr    aCreatedocument_2// "CreateDocumentFromTemplateStream"
0x76e5  ldc.i4.s 0x16
0x76e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76ec  dup
0x76ed  ldstr    aCreatedocument_3// "CreateDocumentFromTemplateBytes"
0x76f2  ldc.i4.s 0x17
0x76f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x76f9  dup
0x76fa  ldstr    aCreatedocument_4// "CreateDocumentFromTemplate"
0x76ff  ldc.i4.s 0x18
0x7701  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7706  dup
0x7707  ldstr    aCreatedocument_5// "CreateDocumentFromTemplateUsingPath"
0x770c  ldc.i4.s 0x19
0x770e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7713  dup
0x7714  ldstr    aSaveastemplate// "SaveAsTemplate"
0x7719  ldc.i4.s 0x1A
0x771b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7720  dup
0x7721  ldstr    aReservelistite// "ReserveListItemId"
0x7726  ldc.i4.s 0x1B
0x7728  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x772d  dup
0x772e  ldstr    aUpdate// "Update"
0x7733  ldc.i4.s 0x1C
0x7735  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x773a  dup
0x773b  ldstr    aGetview// "GetView"
0x7740  ldc.i4.s 0x1D
0x7742  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7747  dup
0x7748  ldstr    aBulkvalidateup// "BulkValidateUpdateListItems"
0x774d  ldc.i4.s 0x1E
0x774f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7754  dup
0x7755  ldstr    aDeleteobject// "DeleteObject"
0x775a  ldc.i4.s 0x1F
0x775c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7761  dup
0x7762  ldstr    aRecycle// "Recycle"
0x7767  ldc.i4.s 0x20
0x7769  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x776e  dup
0x776f  ldstr    aGetchanges// "GetChanges"
0x7774  ldc.i4.s 0x21
0x7776  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x777b  dup
0x777c  ldstr    aGetlistitemcha// "GetListItemChangesSinceToken"
0x7781  ldc.i4.s 0x22
0x7783  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7788  dup
0x7789  ldstr    aGetfileextende// "getFileExtendedActivities"
0x778e  ldc.i4.s 0x23
0x7790  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7795  dup
0x7796  ldstr    aRenderextended// "RenderExtendedListFormData"
0x779b  ldc.i4.s 0x24
0x779d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77a2  dup
0x77a3  ldstr    aRenderlistform// "RenderListFormData"
0x77a8  ldc.i4.s 0x25
0x77aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77af  dup
0x77b0  ldstr    aRenderlistdata// "RenderListData"
0x77b5  ldc.i4.s 0x26
0x77b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77bc  dup
0x77bd  ldstr    aRenderlistdata_0// "RenderListDataAsStream"
0x77c2  ldc.i4.s 0x27
0x77c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77c9  dup
0x77ca  ldstr    aRenderlistfilt// "RenderListFilterData"
0x77cf  ldc.i4.s 0x28
0x77d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77d6  dup
0x77d7  ldstr    aRenderlistcont// "RenderListContextMenuData"
0x77dc  ldc.i4.s 0x29
0x77de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77e3  dup
0x77e4  ldstr    aGetitems// "GetItems"
0x77e9  ldc.i4.s 0x2A
0x77eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77f0  dup
0x77f1  ldstr    aGetitembyid// "GetItemById"
0x77f6  ldc.i4.s 0x2B
0x77f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x77fd  dup
0x77fe  ldstr    aGetitembystrin// "GetItemByStringId"
0x7803  ldc.i4.s 0x2C
0x7805  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x780a  dup
0x780b  ldstr    aSetexemptfromb// "SetExemptFromBlockDownloadOfNonViewable"...
0x7810  ldc.i4.s 0x2D
0x7812  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7817  dup
0x7818  ldstr    aGetitembyuniqu// "GetItemByUniqueId"
0x781d  ldc.i4.s 0x2E
0x781f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7824  dup
0x7825  ldstr    aGetrelatedfiel// "GetRelatedFields"
0x782a  ldc.i4.s 0x2F
0x782c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7831  dup
0x7832  ldstr    aGetrelatedfiel_0// "GetRelatedFieldsExtendedData"
0x7837  ldc.i4.s 0x30
0x7839  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x783e  dup
0x783f  ldstr    aAdditem// "AddItem"
0x7844  ldc.i4.s 0x31
0x7846  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x784b  dup
0x784c  ldstr    aAdditemusingpa// "AddItemUsingPath"
0x7851  ldc.i4.s 0x32
0x7853  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7858  dup
0x7859  ldstr    aAddvalidateupd// "AddValidateUpdateItem"
0x785e  ldc.i4.s 0x33
0x7860  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7865  dup
0x7866  ldstr    aAddvalidateupd_0// "AddValidateUpdateItemUsingPath"
0x786b  ldc.i4.s 0x34
0x786d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7872  volatile.
0x7874  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d4-1
0x7879  volatile.
0x787b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60000d4-1
0x7880  ldloc.1
0x7881  ldloca.s 2
0x7883  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x7888  brfalse  loc_7F13
0x788d  ldloc.2
0x788e  switch   loc_796C, loc_7987, loc_79A2, loc_79BD, loc_79D8, loc_79F4, loc_7A10, loc_7A2B, loc_7A46, loc_7A61, loc_7A7C, loc_7A97, loc_7AB2, loc_7ACD, loc_7AE8, loc_7B03, loc_7B1E, loc_7B39, loc_7B54, loc_7B6F, loc_7B8A, loc_7BA5, loc_7BC0, loc_7BDB, loc_7BF6, loc_7C11, loc_7C2C, loc_7C48, loc_7C68, loc_7C84, loc_7C9F, loc_7CBA, loc_7CD6, loc_7CF6, loc_7D11, loc_7D2C, loc_7D47, loc_7D62, loc_7D7D, loc_7D98, loc_7DB3, loc_7DCE, loc_7DE9, loc_7E04, loc_7E1F, loc_7E3A, loc_7E56, loc_7E71, loc_7E8C, loc_7EA7, loc_7EC2, loc_7EDD, loc_7EF8
0x7967  br       loc_7F13
0x796c  ldarg.s  5
0x796e  ldc.i4.0
0x796f  stind.i1
0x7970  ldarg.0
0x7971  ldstr    aGetspecialfold// "GetSpecialFolderUrl"
0x7976  ldarg.s  4
0x7978  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x797d  ldloc.0
0x797e  ldarg.3
0x797f  ldarg.s  4
0x7981  call     string Microsoft.SharePoint.ServerStub.SPListServerStub::GetSpecialFolderUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7986  ret
0x7987  ldarg.s  5
0x7989  ldc.i4.0
0x798a  stind.i1
0x798b  ldarg.0
0x798c  ldstr    aGetwebdavurl// "GetWebDavUrl"
0x7991  ldarg.s  4
0x7993  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7998  ldloc.0
0x7999  ldarg.3
0x799a  ldarg.s  4
0x799c  call     string Microsoft.SharePoint.ServerStub.SPListServerStub::GetWebDavUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x79a1  ret
0x79a2  ldarg.s  5
0x79a4  ldc.i4.0
0x79a5  stind.i1
0x79a6  ldarg.0
0x79a7  ldstr    aGetcheckedoutf// "GetCheckedOutFiles"
0x79ac  ldarg.s  4
0x79ae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x79b3  ldloc.0
0x79b4  ldarg.3
0x79b5  ldarg.s  4
0x79b7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPCheckedOutFileCollection Microsoft.SharePoint.ServerStub.SPListServerStub::GetCheckedOutFiles_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x79bc  ret
0x79bd  ldarg.s  5
0x79bf  ldc.i4.0
0x79c0  stind.i1
0x79c1  ldarg.0
0x79c2  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x79c7  ldarg.s  4
0x79c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x79ce  ldloc.0
0x79cf  ldarg.3
0x79d0  ldarg.s  4
0x79d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client Microsoft.SharePoint.ServerStub.SPListServerStub::GetUserEffectivePermissions_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x79d7  ret
0x79d8  ldarg.s  5
0x79da  ldc.i4.1
  ... truncated ...
```
