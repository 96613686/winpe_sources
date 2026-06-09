# Microsoft.SharePoint.ServerStub.SPWebServerStub::WriteOnePropertyValueAsJson

- ea: `0x964b0`
- end: `0x98be7`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::WriteOnePropertyValueAsJson`
- size: `10039`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11e0`
- `0x964b0`

## string_xrefs

- `0x9663e`: `Created`
- `0x97467`: `Created`
- `0x9664b`: `CurrentChangeToken`
- `0x974b1`: `CurrentChangeToken`
- `0x968bb`: `ServerRelativePath`
- `0x98308`: `ServerRelativePath`
- `0x96a1a`: `WelcomePage`
- `0x98b1c`: `WelcomePage`
- `0x9682c`: `ResourcePath`
- `0x97fb7`: `ResourcePath`
- `0x9660a`: `CommentsOnSitePagesDisabled`
- `0x97338`: `CommentsOnSitePagesDisabled`
- `0x969cc`: `UIVersionConfigurationEnabled`
- `0x9894b`: `UIVersionConfigurationEnabled`
- `0x96a0d`: `WebTemplate`
- `0x98ad2`: `WebTemplate`
- `0x96617`: `Configuration`
- `0x97382`: `Configuration`
- `0x96518`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x96d74`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x9653c`: `AllowRevertFromTemplateForCurrentUser`
- `0x96e52`: `AllowRevertFromTemplateForCurrentUser`
- `0x96554`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x96ee6`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x967aa`: `ListTemplates`
- `0x97cb7`: `ListTemplates`
- `0x96812`: `OverwriteTranslationsOnChange`
- `0x97f1c`: `OverwriteTranslationsOnChange`
- `0x96887`: `RequestAccessEmail`
- `0x981d2`: `RequestAccessEmail`
- `0x968ae`: `SaveSiteAsTemplateEnabled`
- `0x982be`: `SaveSiteAsTemplateEnabled`
- `0x96a34`: `WorkflowTemplates`
- `0x98bb4`: `WorkflowTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x964b0  ldc.i4.0
0x964b1  stloc.0
0x964b2  ldarg.2
0x964b3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x964b8  stloc.1
0x964b9  ldloc.1
0x964ba  brtrue.s loc_964C7
0x964bc  ldstr    aTarget// "target"
0x964c1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x964c6  throw
0x964c7  ldarg.3
0x964c8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x964cd  dup
0x964ce  stloc.2
0x964cf  brfalse  loc_98BD9
0x964d4  volatile.
0x964d6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018ba-1
0x964db  brtrue   loc_96A47
0x964e0  ldc.i4.s 0x6A
0x964e2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x964e7  dup
0x964e8  ldstr    aActivities// "Activities"
0x964ed  ldc.i4.0
0x964ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x964f3  dup
0x964f4  ldstr    aActivitylogger// "ActivityLogger"
0x964f9  ldc.i4.1
0x964fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x964ff  dup
0x96500  ldstr    aAlerts// "Alerts"
0x96505  ldc.i4.2
0x96506  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9650b  dup
0x9650c  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x96511  ldc.i4.3
0x96512  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96517  dup
0x96518  ldstr    aAllowcreatedec_0// "AllowCreateDeclarativeWorkflowForCurren"...
0x9651d  ldc.i4.4
0x9651e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96523  dup
0x96524  ldstr    aAllowdesignerf// "AllowDesignerForCurrentUser"
0x96529  ldc.i4.5
0x9652a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9652f  dup
0x96530  ldstr    aAllowmasterpag_0// "AllowMasterPageEditingForCurrentUser"
0x96535  ldc.i4.6
0x96536  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9653b  dup
0x9653c  ldstr    aAllowrevertfro_0// "AllowRevertFromTemplateForCurrentUser"
0x96541  ldc.i4.7
0x96542  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96547  dup
0x96548  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x9654d  ldc.i4.8
0x9654e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96553  dup
0x96554  ldstr    aAllowsavedecla_0// "AllowSaveDeclarativeWorkflowAsTemplateF"...
0x96559  ldc.i4.s 9
0x9655b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96560  dup
0x96561  ldstr    aAllowsavepubli_0// "AllowSavePublishDeclarativeWorkflowForC"...
0x96566  ldc.i4.s 0xA
0x96568  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9656d  dup
0x9656e  ldstr    aAllproperties// "AllProperties"
0x96573  ldc.i4.s 0xB
0x96575  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9657a  dup
0x9657b  ldstr    aAlternatecssur// "AlternateCssUrl"
0x96580  ldc.i4.s 0xC
0x96582  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96587  dup
0x96588  ldstr    aAppinstanceid_1// "AppInstanceId"
0x9658d  ldc.i4.s 0xD
0x9658f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96594  dup
0x96595  ldstr    aApptiles// "AppTiles"
0x9659a  ldc.i4.s 0xE
0x9659c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965a1  dup
0x965a2  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x965a7  ldc.i4.s 0xF
0x965a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965ae  dup
0x965af  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x965b4  ldc.i4.s 0x10
0x965b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965bb  dup
0x965bc  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x965c1  ldc.i4.s 0x11
0x965c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965c8  dup
0x965c9  ldstr    aAuthor_0// "Author"
0x965ce  ldc.i4.s 0x12
0x965d0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965d5  dup
0x965d6  ldstr    aAvailableconte// "AvailableContentTypes"
0x965db  ldc.i4.s 0x13
0x965dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965e2  dup
0x965e3  ldstr    aAvailablefield// "AvailableFields"
0x965e8  ldc.i4.s 0x14
0x965ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965ef  dup
0x965f0  ldstr    aBingmapsinform// "BingMapsInformation"
0x965f5  ldc.i4.s 0x15
0x965f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x965fc  dup
0x965fd  ldstr    aClientwebparts// "ClientWebParts"
0x96602  ldc.i4.s 0x16
0x96604  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96609  dup
0x9660a  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x9660f  ldc.i4.s 0x17
0x96611  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96616  dup
0x96617  ldstr    aConfiguration// "Configuration"
0x9661c  ldc.i4.s 0x18
0x9661e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96623  dup
0x96624  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x96629  ldc.i4.s 0x19
0x9662b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96630  dup
0x96631  ldstr    aContenttypes// "ContentTypes"
0x96636  ldc.i4.s 0x1A
0x96638  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9663d  dup
0x9663e  ldstr    aCreated// "Created"
0x96643  ldc.i4.s 0x1B
0x96645  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9664a  dup
0x9664b  ldstr    aCurrentchanget// "CurrentChangeToken"
0x96650  ldc.i4.s 0x1C
0x96652  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96657  dup
0x96658  ldstr    aCurrentuser// "CurrentUser"
0x9665d  ldc.i4.s 0x1D
0x9665f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96664  dup
0x96665  ldstr    aCustommasterur// "CustomMasterUrl"
0x9666a  ldc.i4.s 0x1E
0x9666c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96671  dup
0x96672  ldstr    aDataleakagepre// "DataLeakagePreventionStatusInfo"
0x96677  ldc.i4.s 0x1F
0x96679  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9667e  dup
0x9667f  ldstr    aDepartmentdata// "DepartmentData"
0x96684  ldc.i4.s 0x20
0x96686  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9668b  dup
0x9668c  ldstr    aDescription// "Description"
0x96691  ldc.i4.s 0x21
0x96693  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96698  dup
0x96699  ldstr    aDescriptionres// "DescriptionResource"
0x9669e  ldc.i4.s 0x22
0x966a0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966a5  dup
0x966a6  ldstr    aDesignerdownlo// "DesignerDownloadUrlForCurrentUser"
0x966ab  ldc.i4.s 0x23
0x966ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966b2  dup
0x966b3  ldstr    aDesignpackagei// "DesignPackageId"
0x966b8  ldc.i4.s 0x24
0x966ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966bf  dup
0x966c0  ldstr    aDisableappview// "DisableAppViews"
0x966c5  ldc.i4.s 0x25
0x966c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966cc  dup
0x966cd  ldstr    aDisableflows// "DisableFlows"
0x966d2  ldc.i4.s 0x26
0x966d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966d9  dup
0x966da  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x966df  ldc.i4.s 0x27
0x966e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966e6  dup
0x966e7  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x966ec  ldc.i4.s 0x28
0x966ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x966f3  dup
0x966f4  ldstr    aEnableminimald// "EnableMinimalDownload"
0x966f9  ldc.i4.s 0x29
0x966fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96700  dup
0x96701  ldstr    aEventreceivers// "EventReceivers"
0x96706  ldc.i4.s 0x2A
0x96708  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9670d  dup
0x9670e  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x96713  ldc.i4.s 0x2B
0x96715  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9671a  dup
0x9671b  ldstr    aFeatures// "Features"
0x96720  ldc.i4.s 0x2C
0x96722  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96727  dup
0x96728  ldstr    aFields// "Fields"
0x9672d  ldc.i4.s 0x2D
0x9672f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96734  dup
0x96735  ldstr    aFolders// "Folders"
0x9673a  ldc.i4.s 0x2E
0x9673c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96741  dup
0x96742  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x96747  ldc.i4.s 0x2F
0x96749  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9674e  dup
0x9674f  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x96754  ldc.i4.s 0x30
0x96756  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9675b  dup
0x9675c  ldstr    aId_0// "Id"
0x96761  ldc.i4.s 0x31
0x96763  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96768  dup
0x96769  ldstr    aIsmultilingual// "IsMultilingual"
0x9676e  ldc.i4.s 0x32
0x96770  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96775  dup
0x96776  ldstr    aLanguage// "Language"
0x9677b  ldc.i4.s 0x33
0x9677d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96782  dup
0x96783  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x96788  ldc.i4.s 0x34
0x9678a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9678f  dup
0x96790  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x96795  ldc.i4.s 0x35
0x96797  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9679c  dup
0x9679d  ldstr    aLists// "Lists"
0x967a2  ldc.i4.s 0x36
0x967a4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967a9  dup
0x967aa  ldstr    aListtemplates// "ListTemplates"
0x967af  ldc.i4.s 0x37
0x967b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967b6  dup
0x967b7  ldstr    aMasterurl// "MasterUrl"
0x967bc  ldc.i4.s 0x38
0x967be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967c3  dup
0x967c4  ldstr    aMemberscanshar// "MembersCanShare"
0x967c9  ldc.i4.s 0x39
0x967cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967d0  dup
0x967d1  ldstr    aNavigation// "Navigation"
0x967d6  ldc.i4.s 0x3A
0x967d8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967dd  dup
0x967de  ldstr    aNocrawl// "NoCrawl"
0x967e3  ldc.i4.s 0x3B
0x967e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967ea  dup
0x967eb  ldstr    aNotificationsi// "NotificationsInOneDriveForBusinessEnabl"...
0x967f0  ldc.i4.s 0x3C
0x967f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x967f7  dup
0x967f8  ldstr    aNotificationsi_0// "NotificationsInSharePointEnabled"
0x967fd  ldc.i4.s 0x3D
0x967ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96804  dup
0x96805  ldstr    aOnedriveshared// "OneDriveSharedItems"
0x9680a  ldc.i4.s 0x3E
0x9680c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96811  dup
0x96812  ldstr    aOverwritetrans// "OverwriteTranslationsOnChange"
0x96817  ldc.i4.s 0x3F
0x96819  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9681e  dup
0x9681f  ldstr    aParentweb// "ParentWeb"
0x96824  ldc.i4.s 0x40
0x96826  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9682b  dup
0x9682c  ldstr    aResourcepath// "ResourcePath"
0x96831  ldc.i4.s 0x41
0x96833  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96838  dup
0x96839  ldstr    aPreviewfeature// "PreviewFeaturesEnabled"
0x9683e  ldc.i4.s 0x42
0x96840  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96845  dup
0x96846  ldstr    aPushnotificati// "PushNotificationSubscribers"
0x9684b  ldc.i4.s 0x43
0x9684d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96852  dup
0x96853  ldstr    aQuicklaunchena// "QuickLaunchEnabled"
0x96858  ldc.i4.s 0x44
0x9685a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9685f  dup
0x96860  ldstr    aRecyclebin// "RecycleBin"
0x96865  ldc.i4.s 0x45
0x96867  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
  ... truncated ...
```
