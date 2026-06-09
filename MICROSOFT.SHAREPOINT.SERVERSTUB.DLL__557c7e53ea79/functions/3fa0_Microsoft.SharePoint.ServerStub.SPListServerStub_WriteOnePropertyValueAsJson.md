# Microsoft.SharePoint.ServerStub.SPListServerStub::WriteOnePropertyValueAsJson

- ea: `0x3fa0`
- end: `0x6016`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::WriteOnePropertyValueAsJson`
- size: `8310`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11e0`
- `0x3fa0`

## string_xrefs

- `0x3ffc`: `BaseTemplate`
- `0x46eb`: `BaseTemplate`
- `0x4051`: `Created`
- `0x48ff`: `Created`
- `0x405e`: `CurrentChangeToken`
- `0x4949`: `CurrentChangeToken`
- `0x40ac`: `DefaultItemOpenUseListSetting`
- `0x4b05`: `DefaultItemOpenUseListSetting`
- `0x40d3`: `DefaultViewPath`
- `0x4bea`: `DefaultViewPath`
- `0x4114`: `DocumentTemplateUrl`
- `0x4d63`: `DocumentTemplateUrl`
- `0x4225`: `ImagePath`
- `0x538a`: `ImagePath`
- `0x42db`: `LastItemDeletedDate`
- `0x57a4`: `LastItemDeletedDate`
- `0x4377`: `ParentWebPath`
- `0x5b23`: `ParentWebPath`
- `0x439e`: `ReadSecurity`
- `0x5c01`: `ReadSecurity`
- `0x43b8`: `SchemaXml`
- `0x5c9c`: `SchemaXml`
- `0x43c5`: `ServerTemplateCanCreateFolders`
- `0x5ce6`: `ServerTemplateCanCreateFolders`
- `0x43df`: `TemplateFeatureId`
- `0x5d81`: `TemplateFeatureId`
- `0x4447`: `WriteSecurity`
- `0x5fea`: `WriteSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x3fa0  ldc.i4.0
0x3fa1  stloc.0
0x3fa2  ldarg.2
0x3fa3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x3fa8  stloc.1
0x3fa9  ldloc.1
0x3faa  brtrue.s loc_3FB7
0x3fac  ldstr    aTarget// "target"
0x3fb1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3fb6  throw
0x3fb7  ldarg.3
0x3fb8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x3fbd  dup
0x3fbe  stloc.2
0x3fbf  brfalse  loc_6008
0x3fc4  volatile.
0x3fc6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000096-1
0x3fcb  brtrue   loc_445A
0x3fd0  ldc.i4.s 0x59
0x3fd2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3fd7  dup
0x3fd8  ldstr    aActivities// "Activities"
0x3fdd  ldc.i4.0
0x3fde  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3fe3  dup
0x3fe4  ldstr    aAllowcontentty// "AllowContentTypes"
0x3fe9  ldc.i4.1
0x3fea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3fef  dup
0x3ff0  ldstr    aAllowdeletion// "AllowDeletion"
0x3ff5  ldc.i4.2
0x3ff6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ffb  dup
0x3ffc  ldstr    aBasetemplate// "BaseTemplate"
0x4001  ldc.i4.3
0x4002  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4007  dup
0x4008  ldstr    aBasetype// "BaseType"
0x400d  ldc.i4.4
0x400e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4013  dup
0x4014  ldstr    aBrowserfilehan// "BrowserFileHandling"
0x4019  ldc.i4.5
0x401a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x401f  dup
0x4020  ldstr    aContenttypes// "ContentTypes"
0x4025  ldc.i4.6
0x4026  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x402b  dup
0x402c  ldstr    aContenttypesen// "ContentTypesEnabled"
0x4031  ldc.i4.7
0x4032  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4037  dup
0x4038  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x403d  ldc.i4.8
0x403e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4043  dup
0x4044  ldstr    aCreatablesinfo// "CreatablesInfo"
0x4049  ldc.i4.s 9
0x404b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4050  dup
0x4051  ldstr    aCreated// "Created"
0x4056  ldc.i4.s 0xA
0x4058  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x405d  dup
0x405e  ldstr    aCurrentchanget// "CurrentChangeToken"
0x4063  ldc.i4.s 0xB
0x4065  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x406a  dup
0x406b  ldstr    aCustomactionel// "CustomActionElements"
0x4070  ldc.i4.s 0xC
0x4072  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4077  dup
0x4078  ldstr    aDatasource// "DataSource"
0x407d  ldc.i4.s 0xD
0x407f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4084  dup
0x4085  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x408a  ldc.i4.s 0xE
0x408c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4091  dup
0x4092  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x4097  ldc.i4.s 0xF
0x4099  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x409e  dup
0x409f  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x40a4  ldc.i4.s 0x10
0x40a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40ab  dup
0x40ac  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x40b1  ldc.i4.s 0x11
0x40b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40b8  dup
0x40b9  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x40be  ldc.i4.s 0x12
0x40c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40c5  dup
0x40c6  ldstr    aDefaultview// "DefaultView"
0x40cb  ldc.i4.s 0x13
0x40cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40d2  dup
0x40d3  ldstr    aDefaultviewpat// "DefaultViewPath"
0x40d8  ldc.i4.s 0x14
0x40da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40df  dup
0x40e0  ldstr    aDefaultviewurl// "DefaultViewUrl"
0x40e5  ldc.i4.s 0x15
0x40e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40ec  dup
0x40ed  ldstr    aDescription// "Description"
0x40f2  ldc.i4.s 0x16
0x40f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x40f9  dup
0x40fa  ldstr    aDescriptionres// "DescriptionResource"
0x40ff  ldc.i4.s 0x17
0x4101  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4106  dup
0x4107  ldstr    aDirection// "Direction"
0x410c  ldc.i4.s 0x18
0x410e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4113  dup
0x4114  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x4119  ldc.i4.s 0x19
0x411b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4120  dup
0x4121  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x4126  ldc.i4.s 0x1A
0x4128  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x412d  dup
0x412e  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x4133  ldc.i4.s 0x1B
0x4135  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x413a  dup
0x413b  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0x4140  ldc.i4.s 0x1C
0x4142  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4147  dup
0x4148  ldstr    aEnableassignto// "EnableAssignToEmail"
0x414d  ldc.i4.s 0x1D
0x414f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4154  dup
0x4155  ldstr    aEnableattachme// "EnableAttachments"
0x415a  ldc.i4.s 0x1E
0x415c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4161  dup
0x4162  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x4167  ldc.i4.s 0x1F
0x4169  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x416e  dup
0x416f  ldstr    aEnableminorver// "EnableMinorVersions"
0x4174  ldc.i4.s 0x20
0x4176  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x417b  dup
0x417c  ldstr    aEnablemoderati// "EnableModeration"
0x4181  ldc.i4.s 0x21
0x4183  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4188  dup
0x4189  ldstr    aEnableversioni// "EnableVersioning"
0x418e  ldc.i4.s 0x22
0x4190  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4195  dup
0x4196  ldstr    aEntitytypename// "EntityTypeName"
0x419b  ldc.i4.s 0x23
0x419d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41a2  dup
0x41a3  ldstr    aEventreceivers// "EventReceivers"
0x41a8  ldc.i4.s 0x24
0x41aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41af  dup
0x41b0  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x41b5  ldc.i4.s 0x25
0x41b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41bc  dup
0x41bd  ldstr    aExemptfrombloc// "ExemptFromBlockDownloadOfNonViewableFil"...
0x41c2  ldc.i4.s 0x26
0x41c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41c9  dup
0x41ca  ldstr    aFields// "Fields"
0x41cf  ldc.i4.s 0x27
0x41d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41d6  dup
0x41d7  ldstr    aFilesavepostpr// "FileSavePostProcessingEnabled"
0x41dc  ldc.i4.s 0x28
0x41de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41e3  dup
0x41e4  ldstr    aForcecheckout// "ForceCheckout"
0x41e9  ldc.i4.s 0x29
0x41eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41f0  dup
0x41f1  ldstr    aForms// "Forms"
0x41f6  ldc.i4.s 0x2A
0x41f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41fd  dup
0x41fe  ldstr    aHasexternaldat// "HasExternalDataSource"
0x4203  ldc.i4.s 0x2B
0x4205  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x420a  dup
0x420b  ldstr    aHidden// "Hidden"
0x4210  ldc.i4.s 0x2C
0x4212  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4217  dup
0x4218  ldstr    aId_0// "Id"
0x421d  ldc.i4.s 0x2D
0x421f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4224  dup
0x4225  ldstr    aImagepath// "ImagePath"
0x422a  ldc.i4.s 0x2E
0x422c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4231  dup
0x4232  ldstr    aImageurl// "ImageUrl"
0x4237  ldc.i4.s 0x2F
0x4239  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x423e  dup
0x423f  ldstr    aInformationrig// "InformationRightsManagementSettings"
0x4244  ldc.i4.s 0x30
0x4246  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x424b  dup
0x424c  ldstr    aIrmenabled// "IrmEnabled"
0x4251  ldc.i4.s 0x31
0x4253  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4258  dup
0x4259  ldstr    aIrmexpire// "IrmExpire"
0x425e  ldc.i4.s 0x32
0x4260  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4265  dup
0x4266  ldstr    aIrmreject// "IrmReject"
0x426b  ldc.i4.s 0x33
0x426d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4272  dup
0x4273  ldstr    aIsapplicationl// "IsApplicationList"
0x4278  ldc.i4.s 0x34
0x427a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x427f  dup
0x4280  ldstr    aIscatalog// "IsCatalog"
0x4285  ldc.i4.s 0x35
0x4287  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x428c  dup
0x428d  ldstr    aIsenterprisega// "IsEnterpriseGalleryLibrary"
0x4292  ldc.i4.s 0x36
0x4294  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4299  dup
0x429a  ldstr    aIsprivate// "IsPrivate"
0x429f  ldc.i4.s 0x37
0x42a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42a6  dup
0x42a7  ldstr    aIssiteassetsli// "IsSiteAssetsLibrary"
0x42ac  ldc.i4.s 0x38
0x42ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42b3  dup
0x42b4  ldstr    aIssystemlist// "IsSystemList"
0x42b9  ldc.i4.s 0x39
0x42bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c0  dup
0x42c1  ldstr    aItemcount// "ItemCount"
0x42c6  ldc.i4.s 0x3A
0x42c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42cd  dup
0x42ce  ldstr    aItems// "Items"
0x42d3  ldc.i4.s 0x3B
0x42d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42da  dup
0x42db  ldstr    aLastitemdelete// "LastItemDeletedDate"
0x42e0  ldc.i4.s 0x3C
0x42e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42e7  dup
0x42e8  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x42ed  ldc.i4.s 0x3D
0x42ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42f4  dup
0x42f5  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x42fa  ldc.i4.s 0x3E
0x42fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4301  dup
0x4302  ldstr    aListexperience// "ListExperienceOptions"
0x4307  ldc.i4.s 0x3F
0x4309  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430e  dup
0x430f  ldstr    aListitementity// "ListItemEntityTypeFullName"
0x4314  ldc.i4.s 0x40
0x4316  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x431b  dup
0x431c  ldstr    aMajorversionli// "MajorVersionLimit"
0x4321  ldc.i4.s 0x41
0x4323  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4328  dup
0x4329  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x432e  ldc.i4.s 0x42
0x4330  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4335  dup
0x4336  ldstr    aMultipledatali// "MultipleDataList"
0x433b  ldc.i4.s 0x43
0x433d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4342  dup
0x4343  ldstr    aNocrawl// "NoCrawl"
0x4348  ldc.i4.s 0x44
0x434a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434f  dup
0x4350  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x4355  ldc.i4.s 0x45
0x4357  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
  ... truncated ...
```
