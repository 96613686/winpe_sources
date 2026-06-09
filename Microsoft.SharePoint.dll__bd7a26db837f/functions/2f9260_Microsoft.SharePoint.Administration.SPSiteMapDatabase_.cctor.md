# Microsoft.SharePoint.Administration.SPSiteMapDatabase::.cctor

- ea: `0x2f9260`
- end: `0x2f9451`
- name: `Microsoft.SharePoint.Administration.SPSiteMapDatabase::.cctor`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x2f9367`: `proc_createNewAppSiteDomainIds`
- `0x2f93a6`: `proc_DeleteExtensionMap`
- `0x2f93af`: `proc_GetAllExtensionMap`
- `0x2f93dc`: `proc_GetDefaultExtensionDataHost`
- `0x2f92aa`: `proc_getDeletedSite`
- `0x2f929a`: `proc_getDeletedSitesByQuery`
- `0x2f92a2`: `proc_getDeletedSitesBySiteId`
- `0x2f9292`: `proc_getDeletedSitesByUrl`
- `0x2f93b8`: `proc_GetExtensionMap`
- `0x2f9400`: `proc_getSiteCountBySubscriptionIdAndPathPrefix`
- `0x2f9272`: `proc_putDeletedSiteMap`
- `0x2f93ca`: `proc_ResetExtensionMap`
- `0x2f9412`: `proc_ResetExtensionMapV2`
- `0x2f93d3`: `proc_RestoreExtensionMap`
- `0x2f93c1`: `proc_SetExtensionMap`
- `0x2f9409`: `proc_SetExtensionMapV2`

## pseudocode

```c

```

## disassembly

```asm
0x2f9260  ldc.i4.s 0x31
0x2f9262  newarr   [mscorlib]System.String
0x2f9267  stloc.0
0x2f9268  ldloc.0
0x2f9269  ldc.i4.0
0x2f926a  ldstr    aProcDropsitema// "proc_dropSiteMap"
0x2f926f  stelem.ref
0x2f9270  ldloc.0
0x2f9271  ldc.i4.1
0x2f9272  ldstr    aProcPutdeleted// "proc_putDeletedSiteMap"
0x2f9277  stelem.ref
0x2f9278  ldloc.0
0x2f9279  ldc.i4.2
0x2f927a  ldstr    aProcDropsitema_0// "proc_dropSiteMap2"
0x2f927f  stelem.ref
0x2f9280  ldloc.0
0x2f9281  ldc.i4.3
0x2f9282  ldstr    aProcHidesitema// "proc_hideSiteMap"
0x2f9287  stelem.ref
0x2f9288  ldloc.0
0x2f9289  ldc.i4.4
0x2f928a  ldstr    aProcUnhidesite// "proc_unhideSiteMap"
0x2f928f  stelem.ref
0x2f9290  ldloc.0
0x2f9291  ldc.i4.5
0x2f9292  ldstr    aProcGetdeleted_3// "proc_getDeletedSitesByUrl"
0x2f9297  stelem.ref
0x2f9298  ldloc.0
0x2f9299  ldc.i4.6
0x2f929a  ldstr    aProcGetdeleted_1// "proc_getDeletedSitesByQuery"
0x2f929f  stelem.ref
0x2f92a0  ldloc.0
0x2f92a1  ldc.i4.7
0x2f92a2  ldstr    aProcGetdeleted_2// "proc_getDeletedSitesBySiteId"
0x2f92a7  stelem.ref
0x2f92a8  ldloc.0
0x2f92a9  ldc.i4.8
0x2f92aa  ldstr    aProcGetdeleted_0// "proc_getDeletedSite"
0x2f92af  stelem.ref
0x2f92b0  ldloc.0
0x2f92b1  ldc.i4.s 9
0x2f92b3  ldstr    aProcGetsitecou// "proc_getSiteCount"
0x2f92b8  stelem.ref
0x2f92b9  ldloc.0
0x2f92ba  ldc.i4.s 0xA
0x2f92bc  ldstr    aProcGetsiteinf_0// "proc_GetSiteInfoFromAppSiteDomainPrefix"
0x2f92c1  stelem.ref
0x2f92c2  ldloc.0
0x2f92c3  ldc.i4.s 0xB
0x2f92c5  ldstr    aProcGetsiteinf_1// "proc_getSiteInfoOfHostHeaderSite"
0x2f92ca  stelem.ref
0x2f92cb  ldloc.0
0x2f92cc  ldc.i4.s 0xC
0x2f92ce  ldstr    aProcGetsiteids// "proc_getSiteIds"
0x2f92d3  stelem.ref
0x2f92d4  ldloc.0
0x2f92d5  ldc.i4.s 0xD
0x2f92d7  ldstr    aProcGetsiteida// "proc_getSiteIdAndZoneOfHostHeaderSite"
0x2f92dc  stelem.ref
0x2f92dd  ldloc.0
0x2f92de  ldc.i4.s 0xE
0x2f92e0  ldstr    aProcGetsitemap// "proc_getSiteMap"
0x2f92e5  stelem.ref
0x2f92e6  ldloc.0
0x2f92e7  ldc.i4.s 0xF
0x2f92e9  ldstr    aProcGetsitemap_0// "proc_getSiteMapById"
0x2f92ee  stelem.ref
0x2f92ef  ldloc.0
0x2f92f0  ldc.i4.s 0x10
0x2f92f2  ldstr    aProcGetsitenam// "proc_getSiteNames"
0x2f92f7  stelem.ref
0x2f92f8  ldloc.0
0x2f92f9  ldc.i4.s 0x11
0x2f92fb  ldstr    aProcGetsubscri// "proc_getSubscriptionIds"
0x2f9300  stelem.ref
0x2f9301  ldloc.0
0x2f9302  ldc.i4.s 0x12
0x2f9304  ldstr    aProcPutsitemap// "proc_putSiteMap"
0x2f9309  stelem.ref
0x2f930a  ldloc.0
0x2f930b  ldc.i4.s 0x13
0x2f930d  ldstr    aProcSetsubscri// "proc_setSubscription"
0x2f9312  stelem.ref
0x2f9313  ldloc.0
0x2f9314  ldc.i4.s 0x14
0x2f9316  ldstr    aProcSetsources// "proc_setSourceSiteId"
0x2f931b  stelem.ref
0x2f931c  ldloc.0
0x2f931d  ldc.i4.s 0x15
0x2f931f  ldstr    aProcGetevalsit// "proc_getEvalSites"
0x2f9324  stelem.ref
0x2f9325  ldloc.0
0x2f9326  ldc.i4.s 0x16
0x2f9328  ldstr    aProcSetappsite// "proc_SetAppSiteDomainPrefix"
0x2f932d  stelem.ref
0x2f932e  ldloc.0
0x2f932f  ldc.i4.s 0x17
0x2f9331  ldstr    aProcAddurltosi// "proc_addUrlToSite"
0x2f9336  stelem.ref
0x2f9337  ldloc.0
0x2f9338  ldc.i4.s 0x18
0x2f933a  ldstr    aProcSetzonefor// "proc_setZoneForUrl"
0x2f933f  stelem.ref
0x2f9340  ldloc.0
0x2f9341  ldc.i4.s 0x19
0x2f9343  ldstr    aProcGeturlsfor// "proc_getUrlsForSite"
0x2f9348  stelem.ref
0x2f9349  ldloc.0
0x2f934a  ldc.i4.s 0x1A
0x2f934c  ldstr    aProcSetsubscri_0// "proc_setSubscriptionName"
0x2f9351  stelem.ref
0x2f9352  ldloc.0
0x2f9353  ldc.i4.s 0x1B
0x2f9355  ldstr    aProcGetcontent_0// "proc_getContentDatabaseIdsWithSubscript"...
0x2f935a  stelem.ref
0x2f935b  ldloc.0
0x2f935c  ldc.i4.s 0x1C
0x2f935e  ldstr    aProcGetcontent// "proc_getContentDatabaseIds"
0x2f9363  stelem.ref
0x2f9364  ldloc.0
0x2f9365  ldc.i4.s 0x1D
0x2f9367  ldstr    aProcCreatenewa_0// "proc_createNewAppSiteDomainIds"
0x2f936c  stelem.ref
0x2f936d  ldloc.0
0x2f936e  ldc.i4.s 0x1E
0x2f9370  ldstr    aProcGetsitesub_0// "proc_getSiteSubscriptionsInWebApplicati"...
0x2f9375  stelem.ref
0x2f9376  ldloc.0
0x2f9377  ldc.i4.s 0x1F
0x2f9379  ldstr    aProcGetsiteinf// "proc_getSiteInfoDatabases"
0x2f937e  stelem.ref
0x2f937f  ldloc.0
0x2f9380  ldc.i4.s 0x20
0x2f9382  ldstr    aProcGetdiskuse// "proc_getDiskUsedDatabases"
0x2f9387  stelem.ref
0x2f9388  ldloc.0
0x2f9389  ldc.i4.s 0x21
0x2f938b  ldstr    aProcSetdatabas_0// "proc_setDatabaseRegistration"
0x2f9390  stelem.ref
0x2f9391  ldloc.0
0x2f9392  ldc.i4.s 0x22
0x2f9394  ldstr    aProcDropdataba// "proc_dropDatabaseRegistration"
0x2f9399  stelem.ref
0x2f939a  ldloc.0
0x2f939b  ldc.i4.s 0x23
0x2f939d  ldstr    aProcGetsitesub// "proc_getSiteSubscriptionsInContentDB"
0x2f93a2  stelem.ref
0x2f93a3  ldloc.0
0x2f93a4  ldc.i4.s 0x24
0x2f93a6  ldstr    aProcDeleteexte// "proc_DeleteExtensionMap"
0x2f93ab  stelem.ref
0x2f93ac  ldloc.0
0x2f93ad  ldc.i4.s 0x25
0x2f93af  ldstr    aProcGetallexte// "proc_GetAllExtensionMap"
0x2f93b4  stelem.ref
0x2f93b5  ldloc.0
0x2f93b6  ldc.i4.s 0x26
0x2f93b8  ldstr    aProcGetextensi// "proc_GetExtensionMap"
0x2f93bd  stelem.ref
0x2f93be  ldloc.0
0x2f93bf  ldc.i4.s 0x27
0x2f93c1  ldstr    aProcSetextensi// "proc_SetExtensionMap"
0x2f93c6  stelem.ref
0x2f93c7  ldloc.0
0x2f93c8  ldc.i4.s 0x28
0x2f93ca  ldstr    aProcResetexten// "proc_ResetExtensionMap"
0x2f93cf  stelem.ref
0x2f93d0  ldloc.0
0x2f93d1  ldc.i4.s 0x29
0x2f93d3  ldstr    aProcRestoreext// "proc_RestoreExtensionMap"
0x2f93d8  stelem.ref
0x2f93d9  ldloc.0
0x2f93da  ldc.i4.s 0x2A
0x2f93dc  ldstr    aProcGetdefault// "proc_GetDefaultExtensionDataHost"
0x2f93e1  stelem.ref
0x2f93e2  ldloc.0
0x2f93e3  ldc.i4.s 0x2B
0x2f93e5  ldstr    aProcChecksubsc_0// "proc_checkSubscriptionIdExistsInFarm"
0x2f93ea  stelem.ref
0x2f93eb  ldloc.0
0x2f93ec  ldc.i4.s 0x2C
0x2f93ee  ldstr    aProcChecksubsc_1// "proc_checkSubscriptionIdExistsInWebAppl"...
0x2f93f3  stelem.ref
0x2f93f4  ldloc.0
0x2f93f5  ldc.i4.s 0x2D
0x2f93f7  ldstr    aProcChecksubsc// "proc_checkSubscriptionIdExistsInContent"...
0x2f93fc  stelem.ref
0x2f93fd  ldloc.0
0x2f93fe  ldc.i4.s 0x2E
0x2f9400  ldstr    aProcGetsitecou_0// "proc_getSiteCountBySubscriptionIdAndPat"...
0x2f9405  stelem.ref
0x2f9406  ldloc.0
0x2f9407  ldc.i4.s 0x2F
0x2f9409  ldstr    aProcSetextensi_0// "proc_SetExtensionMapV2"
0x2f940e  stelem.ref
0x2f940f  ldloc.0
0x2f9410  ldc.i4.s 0x30
0x2f9412  ldstr    aProcResetexten_0// "proc_ResetExtensionMapV2"
0x2f9417  stelem.ref
0x2f9418  ldloc.0
0x2f9419  stsfld   string[] Microsoft.SharePoint.Administration.SPSiteMapDatabase::s_AdminSprocsUsedByContentApplications
0x2f941e  ldc.i4.1
0x2f941f  newarr   [mscorlib]System.String
0x2f9424  stloc.1
0x2f9425  ldloc.1
0x2f9426  ldc.i4.0
0x2f9427  ldstr    aDboVersions// "[dbo].[Versions]"
0x2f942c  stelem.ref
0x2f942d  ldloc.1
0x2f942e  stsfld   string[] Microsoft.SharePoint.Administration.SPSiteMapDatabase::s_AdminTablesUsedByContentApplications
0x2f9433  ldc.i4.2
0x2f9434  newarr   [mscorlib]System.String
0x2f9439  stloc.2
0x2f943a  ldloc.2
0x2f943b  ldc.i4.0
0x2f943c  ldstr    aTvpsiteurls2// "tvpSiteUrls2"
0x2f9441  stelem.ref
0x2f9442  ldloc.2
0x2f9443  ldc.i4.1
0x2f9444  ldstr    aTvparrayofguid// "tvpArrayOfGuids"
0x2f9449  stelem.ref
0x2f944a  ldloc.2
0x2f944b  stsfld   string[] Microsoft.SharePoint.Administration.SPSiteMapDatabase::s_AdminTvpsUsedByContentApplications
0x2f9450  ret
```
