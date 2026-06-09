# Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeMethod

- ea: `0x939e0`
- end: `0x94725`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeMethod`
- size: `3397`
- prototype: ``
- caller_count: `0`
- callee_count: `76`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1030`
- `0x92f90`
- `0x92fb0`
- `0x92fd0`
- `0x92fe0`
- `0x93010`
- `0x93050`
- `0x93080`
- `0x930a0`
- `0x930c0`
- `0x930e0`
- `0x93100`
- `0x93120`
- `0x93140`
- `0x93160`
- `0x93180`
- `0x931a0`
- `0x931c0`
- `0x93210`
- `0x93230`
- `0x93250`
- `0x93290`
- `0x932a0`
- `0x932d0`
- `0x932f0`
- `0x93350`
- `0x93370`
- `0x93390`
- `0x933b0`
- `0x933d0`
- `0x933f0`
- `0x93410`
- `0x93440`
- `0x93470`
- `0x93490`
- `0x934b0`
- `0x934d0`
- `0x934f0`
- `0x93520`
- `0x93550`
- `0x93570`
- `0x93590`
- `0x935b0`
- `0x935d0`
- `0x935f0`
- `0x93620`
- `0x93640`
- `0x93650`
- `0x93670`
- `0x936a0`

## string_xrefs

- `0x93cb9`: `Update`
- `0x944a9`: `Update`
- `0x93cac`: `DeleteObject`
- `0x9448d`: `DeleteObject`
- `0x93ced`: `GetFileByServerRelativePath`
- `0x94516`: `GetFileByServerRelativePath`
- `0x93b26`: `GetCustomListTemplates`
- `0x94162`: `GetCustomListTemplates`
- `0x93a5b`: `CreateDefaultAssociatedGroups`
- `0x93fa9`: `CreateDefaultAssociatedGroups`
- `0x93abe`: `GetClientSideComponentsById`
- `0x94088`: `GetClientSideComponentsById`
- `0x93acb`: `GetClientSideComponents`
- `0x940a3`: `GetClientSideComponents`
- `0x93ad8`: `GetClientSideWebParts`
- `0x940be`: `GetClientSideWebParts`
- `0x93aff`: `RemoveStorageEntity`
- `0x94110`: `RemoveStorageEntity`
- `0x93b0c`: `GetSharingLinkData`
- `0x9412c`: `GetSharingLinkData`
- `0x93b33`: `GetAvailableWebTemplates`
- `0x9417d`: `GetAvailableWebTemplates`
- `0x93b8e`: `GetFileByLinkingUrl`
- `0x9423a`: `GetFileByLinkingUrl`
- `0x93ba8`: `GetFileByGuestUrlEnsureAccess`
- `0x94270`: `GetFileByGuestUrlEnsureAccess`
- `0x93be9`: `GetFolderByServerRelativePath`
- `0x942f7`: `GetFolderByServerRelativePath`
- `0x93c1d`: `GetListUsingPath`
- `0x94363`: `GetListUsingPath`
- `0x93c37`: `GetListItemUsingPath`
- `0x94399`: `GetListItemUsingPath`
- `0x93c9f`: `ApplyWebTemplate`
- `0x94471`: `ApplyWebTemplate`
- `0x93cd3`: `GetViewFromPath`
- `0x944e0`: `GetViewFromPath`
- `0x93d48`: `LoadAndInstallAppInSpecifiedLocale`
- `0x945d4`: `LoadAndInstallAppInSpecifiedLocale`
- `0x93d62`: `LoadAndInstallApp`
- `0x9460a`: `LoadAndInstallApp`
- `0x93d7c`: `RemoveSupportedUILanguage`
- `0x94641`: `RemoveSupportedUILanguage`

## pseudocode

```c

```

## disassembly

```asm
0x939e0  ldarg.s  4
0x939e2  brtrue.s loc_939EF
0x939e4  ldstr    aProxycontext// "proxyContext"
0x939e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x939ee  throw
0x939ef  ldarg.1
0x939f0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x939f5  stloc.0
0x939f6  ldloc.0
0x939f7  brtrue.s loc_93A04
0x939f9  ldstr    aTarget// "target"
0x939fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x93a03  throw
0x93a04  ldarg.0
0x93a05  ldarg.2
0x93a06  ldarg.s  4
0x93a08  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x93a0d  starg.s  2
0x93a0f  ldarg.2
0x93a10  dup
0x93a11  stloc.1
0x93a12  brfalse  loc_94717
0x93a17  volatile.
0x93a19  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018a3-1
0x93a1e  brtrue   loc_93DEA
0x93a23  ldc.i4.s 0x4A
0x93a25  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x93a2a  dup
0x93a2b  ldstr    aDoesuserhavepe// "DoesUserHavePermissions"
0x93a30  ldc.i4.0
0x93a31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a36  dup
0x93a37  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x93a3c  ldc.i4.1
0x93a3d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a42  dup
0x93a43  ldstr    aResetroleinher// "ResetRoleInheritance"
0x93a48  ldc.i4.2
0x93a49  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a4e  dup
0x93a4f  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x93a54  ldc.i4.3
0x93a55  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a5a  dup
0x93a5b  ldstr    aCreatedefaulta// "CreateDefaultAssociatedGroups"
0x93a60  ldc.i4.4
0x93a61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a66  dup
0x93a67  ldstr    aRegisterpushno// "RegisterPushNotificationSubscriber"
0x93a6c  ldc.i4.5
0x93a6d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a72  dup
0x93a73  ldstr    aUnregisterpush// "UnregisterPushNotificationSubscriber"
0x93a78  ldc.i4.6
0x93a79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a7e  dup
0x93a7f  ldstr    aGetpushnotific// "GetPushNotificationSubscribersByArgs"
0x93a84  ldc.i4.7
0x93a85  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a8a  dup
0x93a8b  ldstr    aGetpushnotific_0// "GetPushNotificationSubscribersByUser"
0x93a90  ldc.i4.8
0x93a91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93a96  dup
0x93a97  ldstr    aDoespushnotifi// "DoesPushNotificationSubscriberExist"
0x93a9c  ldc.i4.s 9
0x93a9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93aa3  dup
0x93aa4  ldstr    aGetpushnotific_1// "GetPushNotificationSubscriber"
0x93aa9  ldc.i4.s 0xA
0x93aab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93ab0  dup
0x93ab1  ldstr    aGetuserbyid// "GetUserById"
0x93ab6  ldc.i4.s 0xB
0x93ab8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93abd  dup
0x93abe  ldstr    aGetclientsidec// "GetClientSideComponentsById"
0x93ac3  ldc.i4.s 0xC
0x93ac5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93aca  dup
0x93acb  ldstr    aGetclientsidec_0// "GetClientSideComponents"
0x93ad0  ldc.i4.s 0xD
0x93ad2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93ad7  dup
0x93ad8  ldstr    aGetclientsidew// "GetClientSideWebParts"
0x93add  ldc.i4.s 0xE
0x93adf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93ae4  dup
0x93ae5  ldstr    aGetstorageenti// "GetStorageEntity"
0x93aea  ldc.i4.s 0xF
0x93aec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93af1  dup
0x93af2  ldstr    aSetstorageenti// "SetStorageEntity"
0x93af7  ldc.i4.s 0x10
0x93af9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93afe  dup
0x93aff  ldstr    aRemovestoragee// "RemoveStorageEntity"
0x93b04  ldc.i4.s 0x11
0x93b06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b0b  dup
0x93b0c  ldstr    aGetsharinglink// "GetSharingLinkData"
0x93b11  ldc.i4.s 0x12
0x93b13  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b18  dup
0x93b19  ldstr    aMaptoicon// "MapToIcon"
0x93b1e  ldc.i4.s 0x13
0x93b20  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b25  dup
0x93b26  ldstr    aGetcustomlistt// "GetCustomListTemplates"
0x93b2b  ldc.i4.s 0x14
0x93b2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b32  dup
0x93b33  ldstr    aGetavailablewe// "GetAvailableWebTemplates"
0x93b38  ldc.i4.s 0x15
0x93b3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b3f  dup
0x93b40  ldstr    aGetcatalog// "GetCatalog"
0x93b45  ldc.i4.s 0x16
0x93b47  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b4c  dup
0x93b4d  ldstr    aGetrecyclebini// "GetRecycleBinItems"
0x93b52  ldc.i4.s 0x17
0x93b54  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b59  dup
0x93b5a  ldstr    aGetrecyclebini_1// "GetRecycleBinItemsByQueryInfo"
0x93b5f  ldc.i4.s 0x18
0x93b61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b66  dup
0x93b67  ldstr    aGetchanges// "GetChanges"
0x93b6c  ldc.i4.s 0x19
0x93b6e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b73  dup
0x93b74  ldstr    aGetfilebyid// "GetFileById"
0x93b79  ldc.i4.s 0x1A
0x93b7b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b80  dup
0x93b81  ldstr    aGetfolderbyid// "GetFolderById"
0x93b86  ldc.i4.s 0x1B
0x93b88  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b8d  dup
0x93b8e  ldstr    aGetfilebylinki// "GetFileByLinkingUrl"
0x93b93  ldc.i4.s 0x1C
0x93b95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93b9a  dup
0x93b9b  ldstr    aGetfilebyguest// "GetFileByGuestUrl"
0x93ba0  ldc.i4.s 0x1D
0x93ba2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93ba7  dup
0x93ba8  ldstr    aGetfilebyguest_0// "GetFileByGuestUrlEnsureAccess"
0x93bad  ldc.i4.s 0x1E
0x93baf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93bb4  dup
0x93bb5  ldstr    aGetfilebyguest_1// "GetFileByGuestUrlExtended"
0x93bba  ldc.i4.s 0x1F
0x93bbc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93bc1  dup
0x93bc2  ldstr    aGetfilebywopif// "GetFileByWOPIFrameUrl"
0x93bc7  ldc.i4.s 0x20
0x93bc9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93bce  dup
0x93bcf  ldstr    aGetfilebyurl// "GetFileByUrl"
0x93bd4  ldc.i4.s 0x21
0x93bd6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93bdb  dup
0x93bdc  ldstr    aGetfolderbyser// "GetFolderByServerRelativeUrl"
0x93be1  ldc.i4.s 0x22
0x93be3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93be8  dup
0x93be9  ldstr    aGetfolderbyser_0// "GetFolderByServerRelativePath"
0x93bee  ldc.i4.s 0x23
0x93bf0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93bf5  dup
0x93bf6  ldstr    aGetfolderbygue// "GetFolderByGuestUrl"
0x93bfb  ldc.i4.s 0x24
0x93bfd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c02  dup
0x93c03  ldstr    aGetfolderbygue_0// "GetFolderByGuestUrlExtended"
0x93c08  ldc.i4.s 0x25
0x93c0a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c0f  dup
0x93c10  ldstr    aGetlist// "GetList"
0x93c15  ldc.i4.s 0x26
0x93c17  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c1c  dup
0x93c1d  ldstr    aGetlistusingpa// "GetListUsingPath"
0x93c22  ldc.i4.s 0x27
0x93c24  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c29  dup
0x93c2a  ldstr    aGetlistitem// "GetListItem"
0x93c2f  ldc.i4.s 0x28
0x93c31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c36  dup
0x93c37  ldstr    aGetlistitemusi// "GetListItemUsingPath"
0x93c3c  ldc.i4.s 0x29
0x93c3e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c43  dup
0x93c44  ldstr    aGetlistitembyr// "GetListItemByResourceId"
0x93c49  ldc.i4.s 0x2A
0x93c4b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c50  dup
0x93c51  ldstr    aGetentity// "GetEntity"
0x93c56  ldc.i4.s 0x2B
0x93c58  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c5d  dup
0x93c5e  ldstr    aGetappbdccatal// "GetAppBdcCatalogForAppInstance"
0x93c63  ldc.i4.s 0x2C
0x93c65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c6a  dup
0x93c6b  ldstr    aGetappbdccatal_0// "GetAppBdcCatalog"
0x93c70  ldc.i4.s 0x2D
0x93c72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c77  dup
0x93c78  ldstr    aGetsubwebsforc// "GetSubwebsForCurrentUser"
0x93c7d  ldc.i4.s 0x2E
0x93c7f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c84  dup
0x93c85  ldstr    aGetsubwebsfilt// "GetSubwebsFilteredForCurrentUser"
0x93c8a  ldc.i4.s 0x2F
0x93c8c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c91  dup
0x93c92  ldstr    aGetonepagecont// "GetOnePageContextAsStream"
0x93c97  ldc.i4.s 0x30
0x93c99  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93c9e  dup
0x93c9f  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x93ca4  ldc.i4.s 0x31
0x93ca6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cab  dup
0x93cac  ldstr    aDeleteobject// "DeleteObject"
0x93cb1  ldc.i4.s 0x32
0x93cb3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cb8  dup
0x93cb9  ldstr    aUpdate// "Update"
0x93cbe  ldc.i4.s 0x33
0x93cc0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cc5  dup
0x93cc6  ldstr    aGetviewfromurl// "GetViewFromUrl"
0x93ccb  ldc.i4.s 0x34
0x93ccd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cd2  dup
0x93cd3  ldstr    aGetviewfrompat// "GetViewFromPath"
0x93cd8  ldc.i4.s 0x35
0x93cda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cdf  dup
0x93ce0  ldstr    aGetfilebyserve// "GetFileByServerRelativeUrl"
0x93ce5  ldc.i4.s 0x36
0x93ce7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cec  dup
0x93ced  ldstr    aGetfilebyserve_0// "GetFileByServerRelativePath"
0x93cf2  ldc.i4.s 0x37
0x93cf4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93cf9  dup
0x93cfa  ldstr    aDefaultdocumen// "DefaultDocumentLibrary"
0x93cff  ldc.i4.s 0x38
0x93d01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d06  dup
0x93d07  ldstr    aGetregionaldat// "GetRegionalDateTimeSchema"
0x93d0c  ldc.i4.s 0x39
0x93d0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d13  dup
0x93d14  ldstr    aParsedatetime// "ParseDateTime"
0x93d19  ldc.i4.s 0x3A
0x93d1b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d20  dup
0x93d21  ldstr    aIncrementsitec// "IncrementSiteClientTag"
0x93d26  ldc.i4.s 0x3B
0x93d28  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d2d  dup
0x93d2e  ldstr    aGetappinstance_1// "GetAppInstanceById"
0x93d33  ldc.i4.s 0x3C
0x93d35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d3a  dup
0x93d3b  ldstr    aGetappinstance_2// "GetAppInstancesByProductId"
0x93d40  ldc.i4.s 0x3D
0x93d42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d47  dup
0x93d48  ldstr    aLoadandinstall// "LoadAndInstallAppInSpecifiedLocale"
0x93d4d  ldc.i4.s 0x3E
0x93d4f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d54  dup
0x93d55  ldstr    aLoadapp// "LoadApp"
0x93d5a  ldc.i4.s 0x3F
0x93d5c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d61  dup
0x93d62  ldstr    aLoadandinstall_0// "LoadAndInstallApp"
0x93d67  ldc.i4.s 0x40
0x93d69  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d6e  dup
0x93d6f  ldstr    aAddsupportedui// "AddSupportedUILanguage"
0x93d74  ldc.i4.s 0x41
0x93d76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d7b  dup
0x93d7c  ldstr    aRemovesupporte// "RemoveSupportedUILanguage"
0x93d81  ldc.i4.s 0x42
0x93d83  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d88  dup
0x93d89  ldstr    aProcessexterna// "ProcessExternalNotification"
0x93d8e  ldc.i4.s 0x43
0x93d90  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x93d95  dup
  ... truncated ...
```
