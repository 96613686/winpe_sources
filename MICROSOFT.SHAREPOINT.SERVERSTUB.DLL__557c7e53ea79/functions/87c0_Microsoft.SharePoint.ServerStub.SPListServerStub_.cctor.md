# Microsoft.SharePoint.ServerStub.SPListServerStub::.cctor

- ea: `0x87c0`
- end: `0x8bdb`
- name: `Microsoft.SharePoint.ServerStub.SPListServerStub::.cctor`
- size: `1051`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x87da`: `BaseTemplate`
- `0x8802`: `Created`
- `0x880a`: `CurrentChangeToken`
- `0x8840`: `DefaultItemOpenUseListSetting`
- `0x8852`: `DefaultViewPath`
- `0x8b25`: `DefaultViewPath`
- `0x8876`: `DocumentTemplateUrl`
- `0x8918`: `ImagePath`
- `0x8984`: `LastItemDeletedDate`
- `0x89e7`: `ParentWebPath`
- `0x8a02`: `ReadSecurity`
- `0x8b86`: `ReadSecurity`
- `0x8a0b`: `SchemaXml`
- `0x8b8f`: `SchemaXml`
- `0x8a14`: `ServerTemplateCanCreateFolders`
- `0x8a1d`: `TemplateFeatureId`
- `0x8a41`: `WriteSecurity`
- `0x8baa`: `WriteSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x87c0  ldc.i4.s 0x48
0x87c2  newarr   [mscorlib]System.String
0x87c7  stloc.0
0x87c8  ldloc.0
0x87c9  ldc.i4.0
0x87ca  ldstr    aAllowcontentty// "AllowContentTypes"
0x87cf  stelem.ref
0x87d0  ldloc.0
0x87d1  ldc.i4.1
0x87d2  ldstr    aAllowdeletion// "AllowDeletion"
0x87d7  stelem.ref
0x87d8  ldloc.0
0x87d9  ldc.i4.2
0x87da  ldstr    aBasetemplate// "BaseTemplate"
0x87df  stelem.ref
0x87e0  ldloc.0
0x87e1  ldc.i4.3
0x87e2  ldstr    aBasetype// "BaseType"
0x87e7  stelem.ref
0x87e8  ldloc.0
0x87e9  ldc.i4.4
0x87ea  ldstr    aBrowserfilehan// "BrowserFileHandling"
0x87ef  stelem.ref
0x87f0  ldloc.0
0x87f1  ldc.i4.5
0x87f2  ldstr    aContenttypesen// "ContentTypesEnabled"
0x87f7  stelem.ref
0x87f8  ldloc.0
0x87f9  ldc.i4.6
0x87fa  ldstr    aCrawlnondefaul// "CrawlNonDefaultViews"
0x87ff  stelem.ref
0x8800  ldloc.0
0x8801  ldc.i4.7
0x8802  ldstr    aCreated// "Created"
0x8807  stelem.ref
0x8808  ldloc.0
0x8809  ldc.i4.8
0x880a  ldstr    aCurrentchanget// "CurrentChangeToken"
0x880f  stelem.ref
0x8810  ldloc.0
0x8811  ldc.i4.s 9
0x8813  ldstr    aCustomactionel// "CustomActionElements"
0x8818  stelem.ref
0x8819  ldloc.0
0x881a  ldc.i4.s 0xA
0x881c  ldstr    aDatasource// "DataSource"
0x8821  stelem.ref
0x8822  ldloc.0
0x8823  ldc.i4.s 0xB
0x8825  ldstr    aDefaultcontent// "DefaultContentApprovalWorkflowId"
0x882a  stelem.ref
0x882b  ldloc.0
0x882c  ldc.i4.s 0xC
0x882e  ldstr    aDefaultdisplay// "DefaultDisplayFormUrl"
0x8833  stelem.ref
0x8834  ldloc.0
0x8835  ldc.i4.s 0xD
0x8837  ldstr    aDefaulteditfor// "DefaultEditFormUrl"
0x883c  stelem.ref
0x883d  ldloc.0
0x883e  ldc.i4.s 0xE
0x8840  ldstr    aDefaultitemope// "DefaultItemOpenUseListSetting"
0x8845  stelem.ref
0x8846  ldloc.0
0x8847  ldc.i4.s 0xF
0x8849  ldstr    aDefaultnewform// "DefaultNewFormUrl"
0x884e  stelem.ref
0x884f  ldloc.0
0x8850  ldc.i4.s 0x10
0x8852  ldstr    aDefaultviewpat// "DefaultViewPath"
0x8857  stelem.ref
0x8858  ldloc.0
0x8859  ldc.i4.s 0x11
0x885b  ldstr    aDefaultviewurl// "DefaultViewUrl"
0x8860  stelem.ref
0x8861  ldloc.0
0x8862  ldc.i4.s 0x12
0x8864  ldstr    aDescription// "Description"
0x8869  stelem.ref
0x886a  ldloc.0
0x886b  ldc.i4.s 0x13
0x886d  ldstr    aDirection// "Direction"
0x8872  stelem.ref
0x8873  ldloc.0
0x8874  ldc.i4.s 0x14
0x8876  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x887b  stelem.ref
0x887c  ldloc.0
0x887d  ldc.i4.s 0x15
0x887f  ldstr    aDraftversionvi// "DraftVersionVisibility"
0x8884  stelem.ref
0x8885  ldloc.0
0x8886  ldc.i4.s 0x16
0x8888  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x888d  stelem.ref
0x888e  ldloc.0
0x888f  ldc.i4.s 0x17
0x8891  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0x8896  stelem.ref
0x8897  ldloc.0
0x8898  ldc.i4.s 0x18
0x889a  ldstr    aEnableassignto// "EnableAssignToEmail"
0x889f  stelem.ref
0x88a0  ldloc.0
0x88a1  ldc.i4.s 0x19
0x88a3  ldstr    aEnableattachme// "EnableAttachments"
0x88a8  stelem.ref
0x88a9  ldloc.0
0x88aa  ldc.i4.s 0x1A
0x88ac  ldstr    aEnablefoldercr// "EnableFolderCreation"
0x88b1  stelem.ref
0x88b2  ldloc.0
0x88b3  ldc.i4.s 0x1B
0x88b5  ldstr    aEnableminorver// "EnableMinorVersions"
0x88ba  stelem.ref
0x88bb  ldloc.0
0x88bc  ldc.i4.s 0x1C
0x88be  ldstr    aEnablemoderati// "EnableModeration"
0x88c3  stelem.ref
0x88c4  ldloc.0
0x88c5  ldc.i4.s 0x1D
0x88c7  ldstr    aEnableversioni// "EnableVersioning"
0x88cc  stelem.ref
0x88cd  ldloc.0
0x88ce  ldc.i4.s 0x1E
0x88d0  ldstr    aEntitytypename// "EntityTypeName"
0x88d5  stelem.ref
0x88d6  ldloc.0
0x88d7  ldc.i4.s 0x1F
0x88d9  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x88de  stelem.ref
0x88df  ldloc.0
0x88e0  ldc.i4.s 0x20
0x88e2  ldstr    aExemptfrombloc// "ExemptFromBlockDownloadOfNonViewableFil"...
0x88e7  stelem.ref
0x88e8  ldloc.0
0x88e9  ldc.i4.s 0x21
0x88eb  ldstr    aFilesavepostpr// "FileSavePostProcessingEnabled"
0x88f0  stelem.ref
0x88f1  ldloc.0
0x88f2  ldc.i4.s 0x22
0x88f4  ldstr    aForcecheckout// "ForceCheckout"
0x88f9  stelem.ref
0x88fa  ldloc.0
0x88fb  ldc.i4.s 0x23
0x88fd  ldstr    aHasexternaldat// "HasExternalDataSource"
0x8902  stelem.ref
0x8903  ldloc.0
0x8904  ldc.i4.s 0x24
0x8906  ldstr    aHidden// "Hidden"
0x890b  stelem.ref
0x890c  ldloc.0
0x890d  ldc.i4.s 0x25
0x890f  ldstr    aId_0// "Id"
0x8914  stelem.ref
0x8915  ldloc.0
0x8916  ldc.i4.s 0x26
0x8918  ldstr    aImagepath// "ImagePath"
0x891d  stelem.ref
0x891e  ldloc.0
0x891f  ldc.i4.s 0x27
0x8921  ldstr    aImageurl// "ImageUrl"
0x8926  stelem.ref
0x8927  ldloc.0
0x8928  ldc.i4.s 0x28
0x892a  ldstr    aIrmenabled// "IrmEnabled"
0x892f  stelem.ref
0x8930  ldloc.0
0x8931  ldc.i4.s 0x29
0x8933  ldstr    aIrmexpire// "IrmExpire"
0x8938  stelem.ref
0x8939  ldloc.0
0x893a  ldc.i4.s 0x2A
0x893c  ldstr    aIrmreject// "IrmReject"
0x8941  stelem.ref
0x8942  ldloc.0
0x8943  ldc.i4.s 0x2B
0x8945  ldstr    aIsapplicationl// "IsApplicationList"
0x894a  stelem.ref
0x894b  ldloc.0
0x894c  ldc.i4.s 0x2C
0x894e  ldstr    aIscatalog// "IsCatalog"
0x8953  stelem.ref
0x8954  ldloc.0
0x8955  ldc.i4.s 0x2D
0x8957  ldstr    aIsenterprisega// "IsEnterpriseGalleryLibrary"
0x895c  stelem.ref
0x895d  ldloc.0
0x895e  ldc.i4.s 0x2E
0x8960  ldstr    aIsprivate// "IsPrivate"
0x8965  stelem.ref
0x8966  ldloc.0
0x8967  ldc.i4.s 0x2F
0x8969  ldstr    aIssiteassetsli// "IsSiteAssetsLibrary"
0x896e  stelem.ref
0x896f  ldloc.0
0x8970  ldc.i4.s 0x30
0x8972  ldstr    aIssystemlist// "IsSystemList"
0x8977  stelem.ref
0x8978  ldloc.0
0x8979  ldc.i4.s 0x31
0x897b  ldstr    aItemcount// "ItemCount"
0x8980  stelem.ref
0x8981  ldloc.0
0x8982  ldc.i4.s 0x32
0x8984  ldstr    aLastitemdelete// "LastItemDeletedDate"
0x8989  stelem.ref
0x898a  ldloc.0
0x898b  ldc.i4.s 0x33
0x898d  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x8992  stelem.ref
0x8993  ldloc.0
0x8994  ldc.i4.s 0x34
0x8996  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x899b  stelem.ref
0x899c  ldloc.0
0x899d  ldc.i4.s 0x35
0x899f  ldstr    aListexperience// "ListExperienceOptions"
0x89a4  stelem.ref
0x89a5  ldloc.0
0x89a6  ldc.i4.s 0x36
0x89a8  ldstr    aListitementity// "ListItemEntityTypeFullName"
0x89ad  stelem.ref
0x89ae  ldloc.0
0x89af  ldc.i4.s 0x37
0x89b1  ldstr    aMajorversionli// "MajorVersionLimit"
0x89b6  stelem.ref
0x89b7  ldloc.0
0x89b8  ldc.i4.s 0x38
0x89ba  ldstr    aMajorwithminor// "MajorWithMinorVersionsLimit"
0x89bf  stelem.ref
0x89c0  ldloc.0
0x89c1  ldc.i4.s 0x39
0x89c3  ldstr    aMultipledatali// "MultipleDataList"
0x89c8  stelem.ref
0x89c9  ldloc.0
0x89ca  ldc.i4.s 0x3A
0x89cc  ldstr    aNocrawl// "NoCrawl"
0x89d1  stelem.ref
0x89d2  ldloc.0
0x89d3  ldc.i4.s 0x3B
0x89d5  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x89da  stelem.ref
0x89db  ldloc.0
0x89dc  ldc.i4.s 0x3C
0x89de  ldstr    aPagerendertype// "PageRenderType"
0x89e3  stelem.ref
0x89e4  ldloc.0
0x89e5  ldc.i4.s 0x3D
0x89e7  ldstr    aParentwebpath// "ParentWebPath"
0x89ec  stelem.ref
0x89ed  ldloc.0
0x89ee  ldc.i4.s 0x3E
0x89f0  ldstr    aParentweburl// "ParentWebUrl"
0x89f5  stelem.ref
0x89f6  ldloc.0
0x89f7  ldc.i4.s 0x3F
0x89f9  ldstr    aParserdisabled// "ParserDisabled"
0x89fe  stelem.ref
0x89ff  ldloc.0
0x8a00  ldc.i4.s 0x40
0x8a02  ldstr    aReadsecurity// "ReadSecurity"
0x8a07  stelem.ref
0x8a08  ldloc.0
0x8a09  ldc.i4.s 0x41
0x8a0b  ldstr    aSchemaxml// "SchemaXml"
0x8a10  stelem.ref
0x8a11  ldloc.0
0x8a12  ldc.i4.s 0x42
0x8a14  ldstr    aServertemplate// "ServerTemplateCanCreateFolders"
0x8a19  stelem.ref
0x8a1a  ldloc.0
0x8a1b  ldc.i4.s 0x43
0x8a1d  ldstr    aTemplatefeatur// "TemplateFeatureId"
0x8a22  stelem.ref
0x8a23  ldloc.0
0x8a24  ldc.i4.s 0x44
0x8a26  ldstr    aTitle// "Title"
0x8a2b  stelem.ref
0x8a2c  ldloc.0
0x8a2d  ldc.i4.s 0x45
0x8a2f  ldstr    aValidationform// "ValidationFormula"
0x8a34  stelem.ref
0x8a35  ldloc.0
0x8a36  ldc.i4.s 0x46
0x8a38  ldstr    aValidationmess// "ValidationMessage"
0x8a3d  stelem.ref
0x8a3e  ldloc.0
0x8a3f  ldc.i4.s 0x47
0x8a41  ldstr    aWritesecurity// "WriteSecurity"
0x8a46  stelem.ref
0x8a47  ldloc.0
0x8a48  stsfld   string[] Microsoft.SharePoint.ServerStub.SPListServerStub::s_valueProperties
0x8a4d  ldc.i4.s 0x11
0x8a4f  newarr   [mscorlib]System.String
0x8a54  stloc.1
0x8a55  ldloc.1
0x8a56  ldc.i4.0
0x8a57  ldstr    aActivities// "Activities"
0x8a5c  stelem.ref
  ... truncated ...
```
