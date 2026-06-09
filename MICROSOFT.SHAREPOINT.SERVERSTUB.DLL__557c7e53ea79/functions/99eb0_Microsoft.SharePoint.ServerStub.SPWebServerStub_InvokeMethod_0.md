# Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeMethod_0

- ea: `0x99eb0`
- end: `0x9abf5`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeMethod_0`
- size: `3397`
- prototype: ``
- caller_count: `0`
- callee_count: `76`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x13d0`
- `0x99460`
- `0x99480`
- `0x994a0`
- `0x994b0`
- `0x994e0`
- `0x99520`
- `0x99550`
- `0x99570`
- `0x99590`
- `0x995b0`
- `0x995d0`
- `0x995f0`
- `0x99610`
- `0x99630`
- `0x99650`
- `0x99670`
- `0x99690`
- `0x996e0`
- `0x99700`
- `0x99720`
- `0x99760`
- `0x99770`
- `0x997a0`
- `0x997c0`
- `0x99820`
- `0x99840`
- `0x99860`
- `0x99880`
- `0x998a0`
- `0x998c0`
- `0x998e0`
- `0x99910`
- `0x99940`
- `0x99960`
- `0x99980`
- `0x999a0`
- `0x999c0`
- `0x999f0`
- `0x99a20`
- `0x99a40`
- `0x99a60`
- `0x99a80`
- `0x99aa0`
- `0x99ac0`
- `0x99af0`
- `0x99b10`
- `0x99b20`
- `0x99b40`
- `0x99b70`

## string_xrefs

- `0x9a189`: `Update`
- `0x9a979`: `Update`
- `0x9a17c`: `DeleteObject`
- `0x9a95d`: `DeleteObject`
- `0x9a1bd`: `GetFileByServerRelativePath`
- `0x9a9e6`: `GetFileByServerRelativePath`
- `0x99ff6`: `GetCustomListTemplates`
- `0x9a632`: `GetCustomListTemplates`
- `0x99f2b`: `CreateDefaultAssociatedGroups`
- `0x9a479`: `CreateDefaultAssociatedGroups`
- `0x99f8e`: `GetClientSideComponentsById`
- `0x9a558`: `GetClientSideComponentsById`
- `0x99f9b`: `GetClientSideComponents`
- `0x9a573`: `GetClientSideComponents`
- `0x99fa8`: `GetClientSideWebParts`
- `0x9a58e`: `GetClientSideWebParts`
- `0x99fcf`: `RemoveStorageEntity`
- `0x9a5e0`: `RemoveStorageEntity`
- `0x99fdc`: `GetSharingLinkData`
- `0x9a5fc`: `GetSharingLinkData`
- `0x9a003`: `GetAvailableWebTemplates`
- `0x9a64d`: `GetAvailableWebTemplates`
- `0x9a05e`: `GetFileByLinkingUrl`
- `0x9a70a`: `GetFileByLinkingUrl`
- `0x9a078`: `GetFileByGuestUrlEnsureAccess`
- `0x9a740`: `GetFileByGuestUrlEnsureAccess`
- `0x9a0b9`: `GetFolderByServerRelativePath`
- `0x9a7c7`: `GetFolderByServerRelativePath`
- `0x9a0ed`: `GetListUsingPath`
- `0x9a833`: `GetListUsingPath`
- `0x9a107`: `GetListItemUsingPath`
- `0x9a869`: `GetListItemUsingPath`
- `0x9a16f`: `ApplyWebTemplate`
- `0x9a941`: `ApplyWebTemplate`
- `0x9a1a3`: `GetViewFromPath`
- `0x9a9b0`: `GetViewFromPath`
- `0x9a218`: `LoadAndInstallAppInSpecifiedLocale`
- `0x9aaa4`: `LoadAndInstallAppInSpecifiedLocale`
- `0x9a232`: `LoadAndInstallApp`
- `0x9aada`: `LoadAndInstallApp`
- `0x9a24c`: `RemoveSupportedUILanguage`
- `0x9ab11`: `RemoveSupportedUILanguage`

## pseudocode

```c

```

## disassembly

```asm
0x99eb0  ldarg.s  4
0x99eb2  brtrue.s loc_99EBF
0x99eb4  ldstr    aProxycontext// "proxyContext"
0x99eb9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x99ebe  throw
0x99ebf  ldarg.1
0x99ec0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x99ec5  stloc.0
0x99ec6  ldloc.0
0x99ec7  brtrue.s loc_99ED4
0x99ec9  ldstr    aTarget// "target"
0x99ece  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x99ed3  throw
0x99ed4  ldarg.0
0x99ed5  ldarg.2
0x99ed6  ldarg.s  4
0x99ed8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x99edd  starg.s  2
0x99edf  ldarg.2
0x99ee0  dup
0x99ee1  stloc.1
0x99ee2  brfalse  loc_9ABE7
0x99ee7  volatile.
0x99ee9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600190b-1
0x99eee  brtrue   loc_9A2BA
0x99ef3  ldc.i4.s 0x4A
0x99ef5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x99efa  dup
0x99efb  ldstr    aDoesuserhavepe// "DoesUserHavePermissions"
0x99f00  ldc.i4.0
0x99f01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f06  dup
0x99f07  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x99f0c  ldc.i4.1
0x99f0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f12  dup
0x99f13  ldstr    aResetroleinher// "ResetRoleInheritance"
0x99f18  ldc.i4.2
0x99f19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f1e  dup
0x99f1f  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x99f24  ldc.i4.3
0x99f25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f2a  dup
0x99f2b  ldstr    aCreatedefaulta// "CreateDefaultAssociatedGroups"
0x99f30  ldc.i4.4
0x99f31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f36  dup
0x99f37  ldstr    aRegisterpushno// "RegisterPushNotificationSubscriber"
0x99f3c  ldc.i4.5
0x99f3d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f42  dup
0x99f43  ldstr    aUnregisterpush// "UnregisterPushNotificationSubscriber"
0x99f48  ldc.i4.6
0x99f49  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f4e  dup
0x99f4f  ldstr    aGetpushnotific// "GetPushNotificationSubscribersByArgs"
0x99f54  ldc.i4.7
0x99f55  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f5a  dup
0x99f5b  ldstr    aGetpushnotific_0// "GetPushNotificationSubscribersByUser"
0x99f60  ldc.i4.8
0x99f61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f66  dup
0x99f67  ldstr    aDoespushnotifi// "DoesPushNotificationSubscriberExist"
0x99f6c  ldc.i4.s 9
0x99f6e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f73  dup
0x99f74  ldstr    aGetpushnotific_1// "GetPushNotificationSubscriber"
0x99f79  ldc.i4.s 0xA
0x99f7b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f80  dup
0x99f81  ldstr    aGetuserbyid// "GetUserById"
0x99f86  ldc.i4.s 0xB
0x99f88  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f8d  dup
0x99f8e  ldstr    aGetclientsidec// "GetClientSideComponentsById"
0x99f93  ldc.i4.s 0xC
0x99f95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99f9a  dup
0x99f9b  ldstr    aGetclientsidec_0// "GetClientSideComponents"
0x99fa0  ldc.i4.s 0xD
0x99fa2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fa7  dup
0x99fa8  ldstr    aGetclientsidew// "GetClientSideWebParts"
0x99fad  ldc.i4.s 0xE
0x99faf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fb4  dup
0x99fb5  ldstr    aGetstorageenti// "GetStorageEntity"
0x99fba  ldc.i4.s 0xF
0x99fbc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fc1  dup
0x99fc2  ldstr    aSetstorageenti// "SetStorageEntity"
0x99fc7  ldc.i4.s 0x10
0x99fc9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fce  dup
0x99fcf  ldstr    aRemovestoragee// "RemoveStorageEntity"
0x99fd4  ldc.i4.s 0x11
0x99fd6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fdb  dup
0x99fdc  ldstr    aGetsharinglink// "GetSharingLinkData"
0x99fe1  ldc.i4.s 0x12
0x99fe3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99fe8  dup
0x99fe9  ldstr    aMaptoicon// "MapToIcon"
0x99fee  ldc.i4.s 0x13
0x99ff0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x99ff5  dup
0x99ff6  ldstr    aGetcustomlistt// "GetCustomListTemplates"
0x99ffb  ldc.i4.s 0x14
0x99ffd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a002  dup
0x9a003  ldstr    aGetavailablewe// "GetAvailableWebTemplates"
0x9a008  ldc.i4.s 0x15
0x9a00a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a00f  dup
0x9a010  ldstr    aGetcatalog// "GetCatalog"
0x9a015  ldc.i4.s 0x16
0x9a017  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a01c  dup
0x9a01d  ldstr    aGetrecyclebini// "GetRecycleBinItems"
0x9a022  ldc.i4.s 0x17
0x9a024  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a029  dup
0x9a02a  ldstr    aGetrecyclebini_1// "GetRecycleBinItemsByQueryInfo"
0x9a02f  ldc.i4.s 0x18
0x9a031  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a036  dup
0x9a037  ldstr    aGetchanges// "GetChanges"
0x9a03c  ldc.i4.s 0x19
0x9a03e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a043  dup
0x9a044  ldstr    aGetfilebyid// "GetFileById"
0x9a049  ldc.i4.s 0x1A
0x9a04b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a050  dup
0x9a051  ldstr    aGetfolderbyid// "GetFolderById"
0x9a056  ldc.i4.s 0x1B
0x9a058  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a05d  dup
0x9a05e  ldstr    aGetfilebylinki// "GetFileByLinkingUrl"
0x9a063  ldc.i4.s 0x1C
0x9a065  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a06a  dup
0x9a06b  ldstr    aGetfilebyguest// "GetFileByGuestUrl"
0x9a070  ldc.i4.s 0x1D
0x9a072  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a077  dup
0x9a078  ldstr    aGetfilebyguest_0// "GetFileByGuestUrlEnsureAccess"
0x9a07d  ldc.i4.s 0x1E
0x9a07f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a084  dup
0x9a085  ldstr    aGetfilebyguest_1// "GetFileByGuestUrlExtended"
0x9a08a  ldc.i4.s 0x1F
0x9a08c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a091  dup
0x9a092  ldstr    aGetfilebywopif// "GetFileByWOPIFrameUrl"
0x9a097  ldc.i4.s 0x20
0x9a099  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a09e  dup
0x9a09f  ldstr    aGetfilebyurl// "GetFileByUrl"
0x9a0a4  ldc.i4.s 0x21
0x9a0a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0ab  dup
0x9a0ac  ldstr    aGetfolderbyser// "GetFolderByServerRelativeUrl"
0x9a0b1  ldc.i4.s 0x22
0x9a0b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0b8  dup
0x9a0b9  ldstr    aGetfolderbyser_0// "GetFolderByServerRelativePath"
0x9a0be  ldc.i4.s 0x23
0x9a0c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0c5  dup
0x9a0c6  ldstr    aGetfolderbygue// "GetFolderByGuestUrl"
0x9a0cb  ldc.i4.s 0x24
0x9a0cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0d2  dup
0x9a0d3  ldstr    aGetfolderbygue_0// "GetFolderByGuestUrlExtended"
0x9a0d8  ldc.i4.s 0x25
0x9a0da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0df  dup
0x9a0e0  ldstr    aGetlist// "GetList"
0x9a0e5  ldc.i4.s 0x26
0x9a0e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0ec  dup
0x9a0ed  ldstr    aGetlistusingpa// "GetListUsingPath"
0x9a0f2  ldc.i4.s 0x27
0x9a0f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a0f9  dup
0x9a0fa  ldstr    aGetlistitem// "GetListItem"
0x9a0ff  ldc.i4.s 0x28
0x9a101  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a106  dup
0x9a107  ldstr    aGetlistitemusi// "GetListItemUsingPath"
0x9a10c  ldc.i4.s 0x29
0x9a10e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a113  dup
0x9a114  ldstr    aGetlistitembyr// "GetListItemByResourceId"
0x9a119  ldc.i4.s 0x2A
0x9a11b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a120  dup
0x9a121  ldstr    aGetentity// "GetEntity"
0x9a126  ldc.i4.s 0x2B
0x9a128  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a12d  dup
0x9a12e  ldstr    aGetappbdccatal// "GetAppBdcCatalogForAppInstance"
0x9a133  ldc.i4.s 0x2C
0x9a135  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a13a  dup
0x9a13b  ldstr    aGetappbdccatal_0// "GetAppBdcCatalog"
0x9a140  ldc.i4.s 0x2D
0x9a142  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a147  dup
0x9a148  ldstr    aGetsubwebsforc// "GetSubwebsForCurrentUser"
0x9a14d  ldc.i4.s 0x2E
0x9a14f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a154  dup
0x9a155  ldstr    aGetsubwebsfilt// "GetSubwebsFilteredForCurrentUser"
0x9a15a  ldc.i4.s 0x2F
0x9a15c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a161  dup
0x9a162  ldstr    aGetonepagecont// "GetOnePageContextAsStream"
0x9a167  ldc.i4.s 0x30
0x9a169  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a16e  dup
0x9a16f  ldstr    aApplywebtempla// "ApplyWebTemplate"
0x9a174  ldc.i4.s 0x31
0x9a176  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a17b  dup
0x9a17c  ldstr    aDeleteobject// "DeleteObject"
0x9a181  ldc.i4.s 0x32
0x9a183  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a188  dup
0x9a189  ldstr    aUpdate// "Update"
0x9a18e  ldc.i4.s 0x33
0x9a190  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a195  dup
0x9a196  ldstr    aGetviewfromurl// "GetViewFromUrl"
0x9a19b  ldc.i4.s 0x34
0x9a19d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1a2  dup
0x9a1a3  ldstr    aGetviewfrompat// "GetViewFromPath"
0x9a1a8  ldc.i4.s 0x35
0x9a1aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1af  dup
0x9a1b0  ldstr    aGetfilebyserve// "GetFileByServerRelativeUrl"
0x9a1b5  ldc.i4.s 0x36
0x9a1b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1bc  dup
0x9a1bd  ldstr    aGetfilebyserve_0// "GetFileByServerRelativePath"
0x9a1c2  ldc.i4.s 0x37
0x9a1c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1c9  dup
0x9a1ca  ldstr    aDefaultdocumen// "DefaultDocumentLibrary"
0x9a1cf  ldc.i4.s 0x38
0x9a1d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1d6  dup
0x9a1d7  ldstr    aGetregionaldat// "GetRegionalDateTimeSchema"
0x9a1dc  ldc.i4.s 0x39
0x9a1de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1e3  dup
0x9a1e4  ldstr    aParsedatetime// "ParseDateTime"
0x9a1e9  ldc.i4.s 0x3A
0x9a1eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1f0  dup
0x9a1f1  ldstr    aIncrementsitec// "IncrementSiteClientTag"
0x9a1f6  ldc.i4.s 0x3B
0x9a1f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a1fd  dup
0x9a1fe  ldstr    aGetappinstance_1// "GetAppInstanceById"
0x9a203  ldc.i4.s 0x3C
0x9a205  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a20a  dup
0x9a20b  ldstr    aGetappinstance_2// "GetAppInstancesByProductId"
0x9a210  ldc.i4.s 0x3D
0x9a212  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a217  dup
0x9a218  ldstr    aLoadandinstall// "LoadAndInstallAppInSpecifiedLocale"
0x9a21d  ldc.i4.s 0x3E
0x9a21f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a224  dup
0x9a225  ldstr    aLoadapp// "LoadApp"
0x9a22a  ldc.i4.s 0x3F
0x9a22c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a231  dup
0x9a232  ldstr    aLoadandinstall_0// "LoadAndInstallApp"
0x9a237  ldc.i4.s 0x40
0x9a239  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a23e  dup
0x9a23f  ldstr    aAddsupportedui// "AddSupportedUILanguage"
0x9a244  ldc.i4.s 0x41
0x9a246  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a24b  dup
0x9a24c  ldstr    aRemovesupporte// "RemoveSupportedUILanguage"
0x9a251  ldc.i4.s 0x42
0x9a253  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a258  dup
0x9a259  ldstr    aProcessexterna// "ProcessExternalNotification"
0x9a25e  ldc.i4.s 0x43
0x9a260  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9a265  dup
  ... truncated ...
```
