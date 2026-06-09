# Microsoft.SharePoint.ServerStub.SPListServerStub::GetProperty

- ea: `0x28d0`
- end: `0x36c6`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::GetProperty`
- size: `3574`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10d0`
- `0x28d0`

## string_xrefs

- `0x294b`: `BaseTemplate`
- `0x2f70`: `BaseTemplate`
- `0x29a0`: `Created`
- `0x300e`: `Created`
- `0x29ad`: `CurrentChangeToken`
- `0x3026`: `CurrentChangeToken`
- `0x29fb`: `DefaultItemOpenUseListSetting`
- `0x309d`: `DefaultItemOpenUseListSetting`
- `0x2a22`: `DefaultViewPath`
- `0x30db`: `DefaultViewPath`
- `0x2a63`: `DocumentTemplateUrl`
- `0x313a`: `DocumentTemplateUrl`
- `0x2b74`: `ImagePath`
- `0x330f`: `ImagePath`
- `0x2c2a`: `LastItemDeletedDate`
- `0x344b`: `LastItemDeletedDate`
- `0x2cc6`: `ParentWebPath`
- `0x3561`: `ParentWebPath`
- `0x2ced`: `ReadSecurity`
- `0x359f`: `ReadSecurity`
- `0x2d07`: `SchemaXml`
- `0x35ca`: `SchemaXml`
- `0x2d14`: `ServerTemplateCanCreateFolders`
- `0x35dd`: `ServerTemplateCanCreateFolders`
- `0x2d2e`: `TemplateFeatureId`
- `0x3608`: `TemplateFeatureId`
- `0x2d96`: `WriteSecurity`
- `0x36a5`: `WriteSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x28d0  ldarg.2
0x28d1  brtrue.s loc_28DE
0x28d3  ldstr    aPropname// "propName"
0x28d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28dd  throw
0x28de  ldarg.3
0x28df  brtrue.s loc_28EC
0x28e1  ldstr    aProxycontext// "proxyContext"
0x28e6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28eb  throw
0x28ec  ldarg.1
0x28ed  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x28f2  stloc.0
0x28f3  ldloc.0
0x28f4  brtrue.s loc_2901
0x28f6  ldstr    aTarget// "target"
0x28fb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2900  throw
0x2901  ldarg.0
0x2902  ldarg.2
0x2903  ldarg.3
0x2904  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2909  starg.s  2
0x290b  ldarg.2
0x290c  dup
0x290d  stloc.1
0x290e  brfalse  loc_36BC
0x2913  volatile.
0x2915  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000090-1
0x291a  brtrue   loc_2DA9
0x291f  ldc.i4.s 0x59
0x2921  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2926  dup
0x2927  ldstr    aActivities// "Activities"
0x292c  ldc.i4.0
0x292d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2932  dup
0x2933  ldstr    aAllowcontentty// "AllowContentTypes"
0x2938  ldc.i4.1
0x2939  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x293e  dup
0x293f  ldstr    aAllowdeletion// "AllowDeletion"
0x2944  ldc.i4.2
0x2945  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x294a  dup
0x294b  ldstr    aBasetemplate// "BaseTemplate"
0x2950  ldc.i4.3
0x2951  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2956  dup
0x2957  ldstr    aBasetype// "BaseType"
0x295c  ldc.i4.4
0x295d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2962  dup
0x2963  ldstr    aBrowserfilehan// "BrowserFileHandling"
0x2968  ldc.i4.5
0x2969  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x296e  dup
0x296f  ldstr    aContenttypes// "ContentTypes"
0x2974  ldc.i4.6
0x2975  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x297a  dup
0x297b  ldstr    aContenttypesen// "ContentTypesEnabled"
0x2980  ldc.i4.7
0x2981  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2986  dup
0x2987  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x298c  ldc.i4.8
0x298d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2992  dup
0x2993  ldstr    aCreatablesinfo// "CreatablesInfo"
0x2998  ldc.i4.s 9
0x299a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x299f  dup
0x29a0  ldstr    aCreated// "Created"
0x29a5  ldc.i4.s 0xA
0x29a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29ac  dup
0x29ad  ldstr    aCurrentchanget// "CurrentChangeToken"
0x29b2  ldc.i4.s 0xB
0x29b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29b9  dup
0x29ba  ldstr    aCustomactionel// "CustomActionElements"
0x29bf  ldc.i4.s 0xC
0x29c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29c6  dup
0x29c7  ldstr    aDatasource// "DataSource"
0x29cc  ldc.i4.s 0xD
0x29ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29d3  dup
0x29d4  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x29d9  ldc.i4.s 0xE
0x29db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29e0  dup
0x29e1  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x29e6  ldc.i4.s 0xF
0x29e8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29ed  dup
0x29ee  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x29f3  ldc.i4.s 0x10
0x29f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x29fa  dup
0x29fb  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x2a00  ldc.i4.s 0x11
0x2a02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a07  dup
0x2a08  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x2a0d  ldc.i4.s 0x12
0x2a0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a14  dup
0x2a15  ldstr    aDefaultview// "DefaultView"
0x2a1a  ldc.i4.s 0x13
0x2a1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a21  dup
0x2a22  ldstr    aDefaultviewpat// "DefaultViewPath"
0x2a27  ldc.i4.s 0x14
0x2a29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a2e  dup
0x2a2f  ldstr    aDefaultviewurl// "DefaultViewUrl"
0x2a34  ldc.i4.s 0x15
0x2a36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a3b  dup
0x2a3c  ldstr    aDescription// "Description"
0x2a41  ldc.i4.s 0x16
0x2a43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a48  dup
0x2a49  ldstr    aDescriptionres// "DescriptionResource"
0x2a4e  ldc.i4.s 0x17
0x2a50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a55  dup
0x2a56  ldstr    aDirection// "Direction"
0x2a5b  ldc.i4.s 0x18
0x2a5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a62  dup
0x2a63  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x2a68  ldc.i4.s 0x19
0x2a6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a6f  dup
0x2a70  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x2a75  ldc.i4.s 0x1A
0x2a77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a7c  dup
0x2a7d  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x2a82  ldc.i4.s 0x1B
0x2a84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a89  dup
0x2a8a  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0x2a8f  ldc.i4.s 0x1C
0x2a91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2a96  dup
0x2a97  ldstr    aEnableassignto// "EnableAssignToEmail"
0x2a9c  ldc.i4.s 0x1D
0x2a9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2aa3  dup
0x2aa4  ldstr    aEnableattachme// "EnableAttachments"
0x2aa9  ldc.i4.s 0x1E
0x2aab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2ab0  dup
0x2ab1  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x2ab6  ldc.i4.s 0x1F
0x2ab8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2abd  dup
0x2abe  ldstr    aEnableminorver// "EnableMinorVersions"
0x2ac3  ldc.i4.s 0x20
0x2ac5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2aca  dup
0x2acb  ldstr    aEnablemoderati// "EnableModeration"
0x2ad0  ldc.i4.s 0x21
0x2ad2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2ad7  dup
0x2ad8  ldstr    aEnableversioni// "EnableVersioning"
0x2add  ldc.i4.s 0x22
0x2adf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2ae4  dup
0x2ae5  ldstr    aEntitytypename// "EntityTypeName"
0x2aea  ldc.i4.s 0x23
0x2aec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2af1  dup
0x2af2  ldstr    aEventreceivers// "EventReceivers"
0x2af7  ldc.i4.s 0x24
0x2af9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2afe  dup
0x2aff  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x2b04  ldc.i4.s 0x25
0x2b06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b0b  dup
0x2b0c  ldstr    aExemptfrombloc// "ExemptFromBlockDownloadOfNonViewableFil"...
0x2b11  ldc.i4.s 0x26
0x2b13  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b18  dup
0x2b19  ldstr    aFields// "Fields"
0x2b1e  ldc.i4.s 0x27
0x2b20  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b25  dup
0x2b26  ldstr    aFilesavepostpr// "FileSavePostProcessingEnabled"
0x2b2b  ldc.i4.s 0x28
0x2b2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b32  dup
0x2b33  ldstr    aForcecheckout// "ForceCheckout"
0x2b38  ldc.i4.s 0x29
0x2b3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b3f  dup
0x2b40  ldstr    aForms// "Forms"
0x2b45  ldc.i4.s 0x2A
0x2b47  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b4c  dup
0x2b4d  ldstr    aHasexternaldat// "HasExternalDataSource"
0x2b52  ldc.i4.s 0x2B
0x2b54  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b59  dup
0x2b5a  ldstr    aHidden// "Hidden"
0x2b5f  ldc.i4.s 0x2C
0x2b61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b66  dup
0x2b67  ldstr    aId_0// "Id"
0x2b6c  ldc.i4.s 0x2D
0x2b6e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b73  dup
0x2b74  ldstr    aImagepath// "ImagePath"
0x2b79  ldc.i4.s 0x2E
0x2b7b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b80  dup
0x2b81  ldstr    aImageurl// "ImageUrl"
0x2b86  ldc.i4.s 0x2F
0x2b88  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8d  dup
0x2b8e  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x2b93  ldc.i4.s 0x30
0x2b95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b9a  dup
0x2b9b  ldstr    aIrmenabled// "IrmEnabled"
0x2ba0  ldc.i4.s 0x31
0x2ba2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2ba7  dup
0x2ba8  ldstr    aIrmexpire// "IrmExpire"
0x2bad  ldc.i4.s 0x32
0x2baf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2bb4  dup
0x2bb5  ldstr    aIrmreject// "IrmReject"
0x2bba  ldc.i4.s 0x33
0x2bbc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2bc1  dup
0x2bc2  ldstr    aIsapplicationl// "IsApplicationList"
0x2bc7  ldc.i4.s 0x34
0x2bc9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2bce  dup
0x2bcf  ldstr    aIscatalog// "IsCatalog"
0x2bd4  ldc.i4.s 0x35
0x2bd6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2bdb  dup
0x2bdc  ldstr    aIsenterprisega// "IsEnterpriseGalleryLibrary"
0x2be1  ldc.i4.s 0x36
0x2be3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2be8  dup
0x2be9  ldstr    aIsprivate// "IsPrivate"
0x2bee  ldc.i4.s 0x37
0x2bf0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2bf5  dup
0x2bf6  ldstr    aIssiteassetsli// "IsSiteAssetsLibrary"
0x2bfb  ldc.i4.s 0x38
0x2bfd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c02  dup
0x2c03  ldstr    aIssystemlist// "IsSystemList"
0x2c08  ldc.i4.s 0x39
0x2c0a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c0f  dup
0x2c10  ldstr    aItemcount// "ItemCount"
0x2c15  ldc.i4.s 0x3A
0x2c17  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c1c  dup
0x2c1d  ldstr    aItems// "Items"
0x2c22  ldc.i4.s 0x3B
0x2c24  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c29  dup
0x2c2a  ldstr    aLastitemdelete// "LastItemDeletedDate"
0x2c2f  ldc.i4.s 0x3C
0x2c31  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c36  dup
0x2c37  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x2c3c  ldc.i4.s 0x3D
0x2c3e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c43  dup
0x2c44  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x2c49  ldc.i4.s 0x3E
0x2c4b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c50  dup
0x2c51  ldstr    aListexperience// "ListExperienceOptions"
0x2c56  ldc.i4.s 0x3F
0x2c58  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c5d  dup
0x2c5e  ldstr    aListitementity// "ListItemEntityTypeFullName"
0x2c63  ldc.i4.s 0x40
0x2c65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c6a  dup
0x2c6b  ldstr    aMajorversionli// "MajorVersionLimit"
0x2c70  ldc.i4.s 0x41
0x2c72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2c77  dup
0x2c78  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x2c7d  ldc.i4.s 0x42
0x2c7f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
  ... truncated ...
```
