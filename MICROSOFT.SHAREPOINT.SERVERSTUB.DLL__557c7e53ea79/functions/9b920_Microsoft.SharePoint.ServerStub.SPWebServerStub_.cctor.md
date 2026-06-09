# Microsoft.SharePoint.ServerStub.SPWebServerStub::.cctor

- ea: `0x9b920`
- end: `0x9be13`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::.cctor`
- size: `1267`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9b997`: `Created`
- `0x9b9a0`: `CurrentChangeToken`
- `0x9bab7`: `ServerRelativePath`
- `0x9bda3`: `ServerRelativePath`
- `0x9bb50`: `WelcomePage`
- `0x9ba81`: `ResourcePath`
- `0x9b97c`: `CommentsOnSitePagesDisabled`
- `0x9bd26`: `CommentsOnSitePagesDisabled`
- `0x9bb35`: `UIVersionConfigurationEnabled`
- `0x9bb47`: `WebTemplate`
- `0x9b985`: `Configuration`
- `0x9b932`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x9bcf6`: `AllowCreateDeclarativeWorkflowForCurrentUser`
- `0x9b94a`: `AllowRevertFromTemplateForCurrentUser`
- `0x9bd0e`: `AllowRevertFromTemplateForCurrentUser`
- `0x9b95a`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x9bd16`: `AllowSaveDeclarativeWorkflowAsTemplateForCurrentUser`
- `0x9bc24`: `ListTemplates`
- `0x9ba78`: `OverwriteTranslationsOnChange`
- `0x9baa5`: `RequestAccessEmail`
- `0x9bd91`: `RequestAccessEmail`
- `0x9baae`: `SaveSiteAsTemplateEnabled`
- `0x9bd9a`: `SaveSiteAsTemplateEnabled`
- `0x9bcd8`: `WorkflowTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x9b920  ldc.i4.s 0x3F
0x9b922  newarr   [mscorlib]System.String
0x9b927  stloc.0
0x9b928  ldloc.0
0x9b929  ldc.i4.0
0x9b92a  ldstr    aAllowautomatic// "AllowAutomaticASPXPageIndexing"
0x9b92f  stelem.ref
0x9b930  ldloc.0
0x9b931  ldc.i4.1
0x9b932  ldstr    aAllowcreatedec_0// "AllowCreateDeclarativeWorkflowForCurren"...
0x9b937  stelem.ref
0x9b938  ldloc.0
0x9b939  ldc.i4.2
0x9b93a  ldstr    aAllowdesignerf// "AllowDesignerForCurrentUser"
0x9b93f  stelem.ref
0x9b940  ldloc.0
0x9b941  ldc.i4.3
0x9b942  ldstr    aAllowmasterpag_0// "AllowMasterPageEditingForCurrentUser"
0x9b947  stelem.ref
0x9b948  ldloc.0
0x9b949  ldc.i4.4
0x9b94a  ldstr    aAllowrevertfro_0// "AllowRevertFromTemplateForCurrentUser"
0x9b94f  stelem.ref
0x9b950  ldloc.0
0x9b951  ldc.i4.5
0x9b952  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x9b957  stelem.ref
0x9b958  ldloc.0
0x9b959  ldc.i4.6
0x9b95a  ldstr    aAllowsavedecla_0// "AllowSaveDeclarativeWorkflowAsTemplateF"...
0x9b95f  stelem.ref
0x9b960  ldloc.0
0x9b961  ldc.i4.7
0x9b962  ldstr    aAllowsavepubli_0// "AllowSavePublishDeclarativeWorkflowForC"...
0x9b967  stelem.ref
0x9b968  ldloc.0
0x9b969  ldc.i4.8
0x9b96a  ldstr    aAlternatecssur// "AlternateCssUrl"
0x9b96f  stelem.ref
0x9b970  ldloc.0
0x9b971  ldc.i4.s 9
0x9b973  ldstr    aAppinstanceid_1// "AppInstanceId"
0x9b978  stelem.ref
0x9b979  ldloc.0
0x9b97a  ldc.i4.s 0xA
0x9b97c  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x9b981  stelem.ref
0x9b982  ldloc.0
0x9b983  ldc.i4.s 0xB
0x9b985  ldstr    aConfiguration// "Configuration"
0x9b98a  stelem.ref
0x9b98b  ldloc.0
0x9b98c  ldc.i4.s 0xC
0x9b98e  ldstr    aContainsconfid// "ContainsConfidentialInfo"
0x9b993  stelem.ref
0x9b994  ldloc.0
0x9b995  ldc.i4.s 0xD
0x9b997  ldstr    aCreated// "Created"
0x9b99c  stelem.ref
0x9b99d  ldloc.0
0x9b99e  ldc.i4.s 0xE
0x9b9a0  ldstr    aCurrentchanget// "CurrentChangeToken"
0x9b9a5  stelem.ref
0x9b9a6  ldloc.0
0x9b9a7  ldc.i4.s 0xF
0x9b9a9  ldstr    aCustommasterur// "CustomMasterUrl"
0x9b9ae  stelem.ref
0x9b9af  ldloc.0
0x9b9b0  ldc.i4.s 0x10
0x9b9b2  ldstr    aDepartmentdata// "DepartmentData"
0x9b9b7  stelem.ref
0x9b9b8  ldloc.0
0x9b9b9  ldc.i4.s 0x11
0x9b9bb  ldstr    aDescription// "Description"
0x9b9c0  stelem.ref
0x9b9c1  ldloc.0
0x9b9c2  ldc.i4.s 0x12
0x9b9c4  ldstr    aDesignerdownlo// "DesignerDownloadUrlForCurrentUser"
0x9b9c9  stelem.ref
0x9b9ca  ldloc.0
0x9b9cb  ldc.i4.s 0x13
0x9b9cd  ldstr    aDesignpackagei// "DesignPackageId"
0x9b9d2  stelem.ref
0x9b9d3  ldloc.0
0x9b9d4  ldc.i4.s 0x14
0x9b9d6  ldstr    aDisableappview// "DisableAppViews"
0x9b9db  stelem.ref
0x9b9dc  ldloc.0
0x9b9dd  ldc.i4.s 0x15
0x9b9df  ldstr    aDisableflows// "DisableFlows"
0x9b9e4  stelem.ref
0x9b9e5  ldloc.0
0x9b9e6  ldc.i4.s 0x16
0x9b9e8  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x9b9ed  stelem.ref
0x9b9ee  ldloc.0
0x9b9ef  ldc.i4.s 0x17
0x9b9f1  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0x9b9f6  stelem.ref
0x9b9f7  ldloc.0
0x9b9f8  ldc.i4.s 0x18
0x9b9fa  ldstr    aEnableminimald// "EnableMinimalDownload"
0x9b9ff  stelem.ref
0x9ba00  ldloc.0
0x9ba01  ldc.i4.s 0x19
0x9ba03  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x9ba08  stelem.ref
0x9ba09  ldloc.0
0x9ba0a  ldc.i4.s 0x1A
0x9ba0c  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x9ba11  stelem.ref
0x9ba12  ldloc.0
0x9ba13  ldc.i4.s 0x1B
0x9ba15  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x9ba1a  stelem.ref
0x9ba1b  ldloc.0
0x9ba1c  ldc.i4.s 0x1C
0x9ba1e  ldstr    aId_0// "Id"
0x9ba23  stelem.ref
0x9ba24  ldloc.0
0x9ba25  ldc.i4.s 0x1D
0x9ba27  ldstr    aIsmultilingual// "IsMultilingual"
0x9ba2c  stelem.ref
0x9ba2d  ldloc.0
0x9ba2e  ldc.i4.s 0x1E
0x9ba30  ldstr    aLanguage// "Language"
0x9ba35  stelem.ref
0x9ba36  ldloc.0
0x9ba37  ldc.i4.s 0x1F
0x9ba39  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x9ba3e  stelem.ref
0x9ba3f  ldloc.0
0x9ba40  ldc.i4.s 0x20
0x9ba42  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x9ba47  stelem.ref
0x9ba48  ldloc.0
0x9ba49  ldc.i4.s 0x21
0x9ba4b  ldstr    aMasterurl// "MasterUrl"
0x9ba50  stelem.ref
0x9ba51  ldloc.0
0x9ba52  ldc.i4.s 0x22
0x9ba54  ldstr    aMemberscanshar// "MembersCanShare"
0x9ba59  stelem.ref
0x9ba5a  ldloc.0
0x9ba5b  ldc.i4.s 0x23
0x9ba5d  ldstr    aNocrawl// "NoCrawl"
0x9ba62  stelem.ref
0x9ba63  ldloc.0
0x9ba64  ldc.i4.s 0x24
0x9ba66  ldstr    aNotificationsi// "NotificationsInOneDriveForBusinessEnabl"...
0x9ba6b  stelem.ref
0x9ba6c  ldloc.0
0x9ba6d  ldc.i4.s 0x25
0x9ba6f  ldstr    aNotificationsi_0// "NotificationsInSharePointEnabled"
0x9ba74  stelem.ref
0x9ba75  ldloc.0
0x9ba76  ldc.i4.s 0x26
0x9ba78  ldstr    aOverwritetrans// "OverwriteTranslationsOnChange"
0x9ba7d  stelem.ref
0x9ba7e  ldloc.0
0x9ba7f  ldc.i4.s 0x27
0x9ba81  ldstr    aResourcepath// "ResourcePath"
0x9ba86  stelem.ref
0x9ba87  ldloc.0
0x9ba88  ldc.i4.s 0x28
0x9ba8a  ldstr    aPreviewfeature// "PreviewFeaturesEnabled"
0x9ba8f  stelem.ref
0x9ba90  ldloc.0
0x9ba91  ldc.i4.s 0x29
0x9ba93  ldstr    aQuicklaunchena// "QuickLaunchEnabled"
0x9ba98  stelem.ref
0x9ba99  ldloc.0
0x9ba9a  ldc.i4.s 0x2A
0x9ba9c  ldstr    aRecyclebinenab// "RecycleBinEnabled"
0x9baa1  stelem.ref
0x9baa2  ldloc.0
0x9baa3  ldc.i4.s 0x2B
0x9baa5  ldstr    aRequestaccesse// "RequestAccessEmail"
0x9baaa  stelem.ref
0x9baab  ldloc.0
0x9baac  ldc.i4.s 0x2C
0x9baae  ldstr    aSavesiteastemp// "SaveSiteAsTemplateEnabled"
0x9bab3  stelem.ref
0x9bab4  ldloc.0
0x9bab5  ldc.i4.s 0x2D
0x9bab7  ldstr    aServerrelative_0// "ServerRelativePath"
0x9babc  stelem.ref
0x9babd  ldloc.0
0x9babe  ldc.i4.s 0x2E
0x9bac0  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x9bac5  stelem.ref
0x9bac6  ldloc.0
0x9bac7  ldc.i4.s 0x2F
0x9bac9  ldstr    aShowurlstructu_1// "ShowUrlStructureForCurrentUser"
0x9bace  stelem.ref
0x9bacf  ldloc.0
0x9bad0  ldc.i4.s 0x30
0x9bad2  ldstr    aSitelogodescri// "SiteLogoDescription"
0x9bad7  stelem.ref
0x9bad8  ldloc.0
0x9bad9  ldc.i4.s 0x31
0x9badb  ldstr    aSitelogourl// "SiteLogoUrl"
0x9bae0  stelem.ref
0x9bae1  ldloc.0
0x9bae2  ldc.i4.s 0x32
0x9bae4  ldstr    aSupporteduilan// "SupportedUILanguageIds"
0x9bae9  stelem.ref
0x9baea  ldloc.0
0x9baeb  ldc.i4.s 0x33
0x9baed  ldstr    aSyndicationena// "SyndicationEnabled"
0x9baf2  stelem.ref
0x9baf3  ldloc.0
0x9baf4  ldc.i4.s 0x34
0x9baf6  ldstr    aTenanttagpolic// "TenantTagPolicyEnabled"
0x9bafb  stelem.ref
0x9bafc  ldloc.0
0x9bafd  ldc.i4.s 0x35
0x9baff  ldstr    aThemedata// "ThemeData"
0x9bb04  stelem.ref
0x9bb05  ldloc.0
0x9bb06  ldc.i4.s 0x36
0x9bb08  ldstr    aThemedcssfolde// "ThemedCssFolderUrl"
0x9bb0d  stelem.ref
0x9bb0e  ldloc.0
0x9bb0f  ldc.i4.s 0x37
0x9bb11  ldstr    aThirdpartymdme// "ThirdPartyMdmEnabled"
0x9bb16  stelem.ref
0x9bb17  ldloc.0
0x9bb18  ldc.i4.s 0x38
0x9bb1a  ldstr    aTitle// "Title"
0x9bb1f  stelem.ref
0x9bb20  ldloc.0
0x9bb21  ldc.i4.s 0x39
0x9bb23  ldstr    aTreeviewenable// "TreeViewEnabled"
0x9bb28  stelem.ref
0x9bb29  ldloc.0
0x9bb2a  ldc.i4.s 0x3A
0x9bb2c  ldstr    aUiversion// "UIVersion"
0x9bb31  stelem.ref
0x9bb32  ldloc.0
0x9bb33  ldc.i4.s 0x3B
0x9bb35  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x9bb3a  stelem.ref
0x9bb3b  ldloc.0
0x9bb3c  ldc.i4.s 0x3C
0x9bb3e  ldstr    aUrl// "Url"
0x9bb43  stelem.ref
0x9bb44  ldloc.0
0x9bb45  ldc.i4.s 0x3D
0x9bb47  ldstr    aWebtemplate// "WebTemplate"
0x9bb4c  stelem.ref
0x9bb4d  ldloc.0
0x9bb4e  ldc.i4.s 0x3E
0x9bb50  ldstr    aWelcomepage// "WelcomePage"
0x9bb55  stelem.ref
0x9bb56  ldloc.0
0x9bb57  stsfld   string[] Microsoft.SharePoint.ServerStub.SPWebServerStub::s_valueProperties
0x9bb5c  ldc.i4.s 0x2B
0x9bb5e  newarr   [mscorlib]System.String
0x9bb63  stloc.1
0x9bb64  ldloc.1
0x9bb65  ldc.i4.0
0x9bb66  ldstr    aActivities// "Activities"
0x9bb6b  stelem.ref
0x9bb6c  ldloc.1
0x9bb6d  ldc.i4.1
0x9bb6e  ldstr    aActivitylogger// "ActivityLogger"
0x9bb73  stelem.ref
0x9bb74  ldloc.1
0x9bb75  ldc.i4.2
0x9bb76  ldstr    aAlerts// "Alerts"
0x9bb7b  stelem.ref
0x9bb7c  ldloc.1
0x9bb7d  ldc.i4.3
0x9bb7e  ldstr    aAllproperties// "AllProperties"
0x9bb83  stelem.ref
0x9bb84  ldloc.1
0x9bb85  ldc.i4.4
0x9bb86  ldstr    aApptiles// "AppTiles"
0x9bb8b  stelem.ref
0x9bb8c  ldloc.1
0x9bb8d  ldc.i4.5
0x9bb8e  ldstr    aAssociatedmemb// "AssociatedMemberGroup"
0x9bb93  stelem.ref
0x9bb94  ldloc.1
0x9bb95  ldc.i4.6
0x9bb96  ldstr    aAssociatedowne// "AssociatedOwnerGroup"
0x9bb9b  stelem.ref
0x9bb9c  ldloc.1
0x9bb9d  ldc.i4.7
0x9bb9e  ldstr    aAssociatedvisi// "AssociatedVisitorGroup"
0x9bba3  stelem.ref
0x9bba4  ldloc.1
0x9bba5  ldc.i4.8
0x9bba6  ldstr    aAuthor_0// "Author"
0x9bbab  stelem.ref
0x9bbac  ldloc.1
0x9bbad  ldc.i4.s 9
0x9bbaf  ldstr    aAvailableconte// "AvailableContentTypes"
0x9bbb4  stelem.ref
  ... truncated ...
```
