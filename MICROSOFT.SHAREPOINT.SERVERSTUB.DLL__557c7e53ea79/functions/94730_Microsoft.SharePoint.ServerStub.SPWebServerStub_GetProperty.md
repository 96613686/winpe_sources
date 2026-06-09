# Microsoft.SharePoint.ServerStub.SPWebServerStub::GetProperty

- ea: `0x94730`
- end: `0x95767`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::GetProperty`
- size: `4151`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10d0`
- `0x94730`

## string_xrefs

- `0x948dd`: `Created`
- `0x950eb`: `Created`
- `0x948ea`: `CurrentChangeToken`
- `0x95103`: `CurrentChangeToken`
- `0x94b5a`: `ServerRelativePath`
- `0x95501`: `ServerRelativePath`
- `0x94cb9`: `WelcomePage`
- `0x95725`: `WelcomePage`
- `0x94acb`: `ResourcePath`
- `0x9541c`: `ResourcePath`
- `0x948a9`: `CommentsOnSitePagesDisabled`
- `0x95090`: `CommentsOnSitePagesDisabled`
- `0x94c6b`: `UIVersionConfigurationEnabled`
- `0x956ae`: `UIVersionConfigurationEnabled`
- `0x94cac`: `WebTemplate`
- `0x95712`: `WebTemplate`
- `0x948b6`: `Configuration`
- `0x950a8`: `Configuration`
- `0x947b7`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x94eff`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x947db`: `AllowRevertFromTemplateForCurrentUser`
- `0x94f47`: `AllowRevertFromTemplateForCurrentUser`
- `0x947f3`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x94f77`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x94a49`: `ListTemplates`
- `0x95345`: `ListTemplates`
- `0x94ab1`: `OverwriteTranslationsOnChange`
- `0x953f1`: `OverwriteTranslationsOnChange`
- `0x94b26`: `RequestAccessEmail`
- `0x954b0`: `RequestAccessEmail`
- `0x94b4d`: `SaveSiteAsTemplateEnabled`
- `0x954e9`: `SaveSiteAsTemplateEnabled`
- `0x94cd3`: `WorkflowTemplates`
- `0x9574b`: `WorkflowTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x94730  ldarg.2
0x94731  brtrue.s loc_9473E
0x94733  ldstr    aPropname// "propName"
0x94738  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9473d  throw
0x9473e  ldarg.3
0x9473f  brtrue.s loc_9474C
0x94741  ldstr    aProxycontext// "proxyContext"
0x94746  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9474b  throw
0x9474c  ldarg.1
0x9474d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x94752  stloc.0
0x94753  ldloc.0
0x94754  brtrue.s loc_94761
0x94756  ldstr    aTarget// "target"
0x9475b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x94760  throw
0x94761  ldarg.0
0x94762  ldarg.2
0x94763  ldarg.3
0x94764  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x94769  starg.s  2
0x9476b  ldarg.2
0x9476c  dup
0x9476d  stloc.1
0x9476e  brfalse  loc_9575D
0x94773  volatile.
0x94775  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018a4-1
0x9477a  brtrue   loc_94CE6
0x9477f  ldc.i4.s 0x6A
0x94781  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x94786  dup
0x94787  ldstr    aActivities// "Activities"
0x9478c  ldc.i4.0
0x9478d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94792  dup
0x94793  ldstr    aActivitylogger// "ActivityLogger"
0x94798  ldc.i4.1
0x94799  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9479e  dup
0x9479f  ldstr    aAlerts// "Alerts"
0x947a4  ldc.i4.2
0x947a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947aa  dup
0x947ab  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x947b0  ldc.i4.3
0x947b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947b6  dup
0x947b7  ldstr    aAllowcreatedec_0// "AllowCreateDeclarativeWorkflowForCurren"...
0x947bc  ldc.i4.4
0x947bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947c2  dup
0x947c3  ldstr    aAllowdesignerf// "AllowDesignerForCurrentUser"
0x947c8  ldc.i4.5
0x947c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947ce  dup
0x947cf  ldstr    aAllowmasterpag_0// "AllowMasterPageEditingForCurrentUser"
0x947d4  ldc.i4.6
0x947d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947da  dup
0x947db  ldstr    aAllowrevertfro_0// "AllowRevertFromTemplateForCurrentUser"
0x947e0  ldc.i4.7
0x947e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947e6  dup
0x947e7  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x947ec  ldc.i4.8
0x947ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947f2  dup
0x947f3  ldstr    aAllowsavedecla_0// "AllowSaveDeclarativeWorkflowAsTemplateF"...
0x947f8  ldc.i4.s 9
0x947fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x947ff  dup
0x94800  ldstr    aAllowsavepubli_0// "AllowSavePublishDeclarativeWorkflowForC"...
0x94805  ldc.i4.s 0xA
0x94807  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9480c  dup
0x9480d  ldstr    aAllproperties// "AllProperties"
0x94812  ldc.i4.s 0xB
0x94814  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94819  dup
0x9481a  ldstr    aAlternatecssur// "AlternateCssUrl"
0x9481f  ldc.i4.s 0xC
0x94821  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94826  dup
0x94827  ldstr    aAppinstanceid_1// "AppInstanceId"
0x9482c  ldc.i4.s 0xD
0x9482e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94833  dup
0x94834  ldstr    aApptiles// "AppTiles"
0x94839  ldc.i4.s 0xE
0x9483b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94840  dup
0x94841  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x94846  ldc.i4.s 0xF
0x94848  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9484d  dup
0x9484e  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x94853  ldc.i4.s 0x10
0x94855  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9485a  dup
0x9485b  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x94860  ldc.i4.s 0x11
0x94862  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94867  dup
0x94868  ldstr    aAuthor_0// "Author"
0x9486d  ldc.i4.s 0x12
0x9486f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94874  dup
0x94875  ldstr    aAvailableconte// "AvailableContentTypes"
0x9487a  ldc.i4.s 0x13
0x9487c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94881  dup
0x94882  ldstr    aAvailablefield// "AvailableFields"
0x94887  ldc.i4.s 0x14
0x94889  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9488e  dup
0x9488f  ldstr    aBingmapsinform// "BingMapsInformation"
0x94894  ldc.i4.s 0x15
0x94896  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9489b  dup
0x9489c  ldstr    aClientwebparts// "ClientWebParts"
0x948a1  ldc.i4.s 0x16
0x948a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948a8  dup
0x948a9  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x948ae  ldc.i4.s 0x17
0x948b0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948b5  dup
0x948b6  ldstr    aConfiguration// "Configuration"
0x948bb  ldc.i4.s 0x18
0x948bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948c2  dup
0x948c3  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x948c8  ldc.i4.s 0x19
0x948ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948cf  dup
0x948d0  ldstr    aContenttypes// "ContentTypes"
0x948d5  ldc.i4.s 0x1A
0x948d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948dc  dup
0x948dd  ldstr    aCreated// "Created"
0x948e2  ldc.i4.s 0x1B
0x948e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948e9  dup
0x948ea  ldstr    aCurrentchanget// "CurrentChangeToken"
0x948ef  ldc.i4.s 0x1C
0x948f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x948f6  dup
0x948f7  ldstr    aCurrentuser// "CurrentUser"
0x948fc  ldc.i4.s 0x1D
0x948fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94903  dup
0x94904  ldstr    aCustommasterur// "CustomMasterUrl"
0x94909  ldc.i4.s 0x1E
0x9490b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94910  dup
0x94911  ldstr    aDataleakagepre// "DataLeakagePreventionStatusInfo"
0x94916  ldc.i4.s 0x1F
0x94918  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9491d  dup
0x9491e  ldstr    aDepartmentdata// "DepartmentData"
0x94923  ldc.i4.s 0x20
0x94925  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9492a  dup
0x9492b  ldstr    aDescription// "Description"
0x94930  ldc.i4.s 0x21
0x94932  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94937  dup
0x94938  ldstr    aDescriptionres// "DescriptionResource"
0x9493d  ldc.i4.s 0x22
0x9493f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94944  dup
0x94945  ldstr    aDesignerdownlo// "DesignerDownloadUrlForCurrentUser"
0x9494a  ldc.i4.s 0x23
0x9494c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94951  dup
0x94952  ldstr    aDesignpackagei// "DesignPackageId"
0x94957  ldc.i4.s 0x24
0x94959  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9495e  dup
0x9495f  ldstr    aDisableappview// "DisableAppViews"
0x94964  ldc.i4.s 0x25
0x94966  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9496b  dup
0x9496c  ldstr    aDisableflows// "DisableFlows"
0x94971  ldc.i4.s 0x26
0x94973  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94978  dup
0x94979  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x9497e  ldc.i4.s 0x27
0x94980  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94985  dup
0x94986  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x9498b  ldc.i4.s 0x28
0x9498d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94992  dup
0x94993  ldstr    aEnableminimald// "EnableMinimalDownload"
0x94998  ldc.i4.s 0x29
0x9499a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9499f  dup
0x949a0  ldstr    aEventreceivers// "EventReceivers"
0x949a5  ldc.i4.s 0x2A
0x949a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949ac  dup
0x949ad  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x949b2  ldc.i4.s 0x2B
0x949b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949b9  dup
0x949ba  ldstr    aFeatures// "Features"
0x949bf  ldc.i4.s 0x2C
0x949c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949c6  dup
0x949c7  ldstr    aFields// "Fields"
0x949cc  ldc.i4.s 0x2D
0x949ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949d3  dup
0x949d4  ldstr    aFolders// "Folders"
0x949d9  ldc.i4.s 0x2E
0x949db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949e0  dup
0x949e1  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x949e6  ldc.i4.s 0x2F
0x949e8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949ed  dup
0x949ee  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x949f3  ldc.i4.s 0x30
0x949f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x949fa  dup
0x949fb  ldstr    aId_0// "Id"
0x94a00  ldc.i4.s 0x31
0x94a02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a07  dup
0x94a08  ldstr    aIsmultilingual// "IsMultilingual"
0x94a0d  ldc.i4.s 0x32
0x94a0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a14  dup
0x94a15  ldstr    aLanguage// "Language"
0x94a1a  ldc.i4.s 0x33
0x94a1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a21  dup
0x94a22  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x94a27  ldc.i4.s 0x34
0x94a29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a2e  dup
0x94a2f  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x94a34  ldc.i4.s 0x35
0x94a36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a3b  dup
0x94a3c  ldstr    aLists// "Lists"
0x94a41  ldc.i4.s 0x36
0x94a43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a48  dup
0x94a49  ldstr    aListtemplates// "ListTemplates"
0x94a4e  ldc.i4.s 0x37
0x94a50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a55  dup
0x94a56  ldstr    aMasterurl// "MasterUrl"
0x94a5b  ldc.i4.s 0x38
0x94a5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a62  dup
0x94a63  ldstr    aMemberscanshar// "MembersCanShare"
0x94a68  ldc.i4.s 0x39
0x94a6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a6f  dup
0x94a70  ldstr    aNavigation// "Navigation"
0x94a75  ldc.i4.s 0x3A
0x94a77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a7c  dup
0x94a7d  ldstr    aNocrawl// "NoCrawl"
0x94a82  ldc.i4.s 0x3B
0x94a84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a89  dup
0x94a8a  ldstr    aNotificationsi// "NotificationsInOneDriveForBusinessEnabl"...
0x94a8f  ldc.i4.s 0x3C
0x94a91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94a96  dup
0x94a97  ldstr    aNotificationsi_0// "NotificationsInSharePointEnabled"
0x94a9c  ldc.i4.s 0x3D
0x94a9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94aa3  dup
0x94aa4  ldstr    aOnedriveshared// "OneDriveSharedItems"
0x94aa9  ldc.i4.s 0x3E
0x94aab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94ab0  dup
0x94ab1  ldstr    aOverwritetrans// "OverwriteTranslationsOnChange"
0x94ab6  ldc.i4.s 0x3F
0x94ab8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94abd  dup
0x94abe  ldstr    aParentweb// "ParentWeb"
0x94ac3  ldc.i4.s 0x40
0x94ac5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94aca  dup
0x94acb  ldstr    aResourcepath// "ResourcePath"
0x94ad0  ldc.i4.s 0x41
0x94ad2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x94ad7  dup
0x94ad8  ldstr    aPreviewfeature// "PreviewFeaturesEnabled"
0x94add  ldc.i4.s 0x42
0x94adf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
  ... truncated ...
```
