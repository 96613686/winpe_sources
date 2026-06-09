# Microsoft.SharePoint.SPSharingEmailHelper::GetNotificationMessageComponentsObsolete

- ea: `0x756680`
- end: `0x756b1d`
- name: `Microsoft.SharePoint.SPSharingEmailHelper::GetNotificationMessageComponentsObsolete`
- size: `1181`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x7539f0`
- `0x754160`

## callees

- `0x187950`
- `0x1a2030`
- `0x1fa8a0`
- `0x1fa8c0`
- `0x1fa8e0`
- `0x232050`
- `0x26b840`
- `0x26f0e0`
- `0x342e60`
- `0x343930`
- `0x344680`
- `0x344eb0`
- `0x3e99a0`
- `0x475150`
- `0x475190`
- `0x4cd8e0`
- `0x53be00`
- `0x53bf80`
- `0x53e8c0`
- `0x542e10`
- `0x5b2ef0`
- `0x5c24f0`
- `0x5c3b50`
- `0x5c3ce0`
- `0x5c3eb0`
- `0x678580`
- `0x756680`
- `0x7571d0`
- `0x7574b0`
- `0x789910`
- `0x78c690`
- `0x79c430`
- `0x7bea00`
- `0x93dab0`
- `0x93dae0`
- `0x957470`
- `0xaefbc0`

## string_xrefs

- `0x756980`: `SharingLinkRelatedDelveUser`
- `0x756716`: `SharingLinkDirect`
- `0x75678a`: `SharingLinkDirect`
- `0x756826`: `SharingLinkDirect`
- `0x756b16`: `SharingLinkDirect`
- `0x75672d`: `SharingLinkFollowSiteContent`
- `0x75684c`: `SharingLinkAddToOneDrive`
- `0x75689e`: `MountSiteId`
- `0x7568c3`: `MountWebId`
- `0x7568e3`: `MountItemUniqueId`
- `0x7568f9`: `MountItemTitle`
- `0x756912`: `SharingLinkDocumentDirect`
- `0x756a3c`: `SharingLinkFollowDocContent`

## pseudocode

```c

```

## disassembly

```asm
0x756680  ldarg.3
0x756681  ldsfld   string [mscorlib]System.String::Empty
0x756686  stind.ref
0x756687  ldarg.s  4
0x756689  ldsfld   string [mscorlib]System.String::Empty
0x75668e  stind.ref
0x75668f  ldarg.s  5
0x756691  ldsfld   string [mscorlib]System.String::Empty
0x756696  stind.ref
0x756697  ldarg.s  6
0x756699  ldsfld   string [mscorlib]System.String::Empty
0x75669e  stind.ref
0x75669f  ldarg.s  7
0x7566a1  ldsfld   string [mscorlib]System.String::Empty
0x7566a6  stind.ref
0x7566a7  ldarg.s  8
0x7566a9  ldsfld   string [mscorlib]System.String::Empty
0x7566ae  stind.ref
0x7566af  ldarg.s  9
0x7566b1  ldsfld   string [mscorlib]System.String::Empty
0x7566b6  stind.ref
0x7566b7  ldarg.s  0xA
0x7566b9  ldsfld   string [mscorlib]System.String::Empty
0x7566be  stind.ref
0x7566bf  ldarg.s  0xB
0x7566c1  ldsfld   string [mscorlib]System.String::Empty
0x7566c6  stind.ref
0x7566c7  ldarg.s  0xC
0x7566c9  ldsfld   string [mscorlib]System.String::Empty
0x7566ce  stind.ref
0x7566cf  ldarg.s  0xD
0x7566d1  ldc.i4.0
0x7566d2  stind.i1
0x7566d3  ldarg.1
0x7566d4  brtrue.s loc_7566DA
0x7566d6  ldarg.0
0x7566d7  stloc.0
0x7566d8  br.s     loc_7566E1
0x7566da  ldarg.1
0x7566db  isinst   Microsoft.SharePoint.SPWeb
0x7566e0  stloc.0
0x7566e1  ldarg.1
0x7566e2  isinst   Microsoft.SharePoint.SPList
0x7566e7  stloc.1
0x7566e8  ldarg.1
0x7566e9  isinst   Microsoft.SharePoint.SPListItem
0x7566ee  stloc.2
0x7566ef  ldloc.0
0x7566f0  brfalse.s loc_75675C
0x7566f2  ldarg.3
0x7566f3  ldloc.0
0x7566f4  callvirt instance string Microsoft.SharePoint.SPWeb::get_Title()
0x7566f9  stind.ref
0x7566fa  ldarg.s  4
0x7566fc  ldloc.0
0x7566fd  callvirt instance string Microsoft.SharePoint.SPWeb::get_Title()
0x756702  stind.ref
0x756703  ldarg.s  5
0x756705  ldloc.0
0x756706  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x75670b  stind.ref
0x75670c  ldarg.s  9
0x75670e  ldstr    aSharingdefault_0// "SharingDefaultMessageSite"
0x756713  stind.ref
0x756714  ldarg.s  0xA
0x756716  ldstr    aSharinglinkdir// "SharingLinkDirect"
0x75671b  stind.ref
0x75671c  ldarg.s  0xD
0x75671e  ldc.i4.1
0x75671f  stind.i1
0x756720  ldloc.0
0x756721  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsEmailFollowLinkEnabled(class Microsoft.SharePoint.SPWeb web)
0x756726  brfalse  loc_756B1C
0x75672b  ldarg.s  0xB
0x75672d  ldstr    aSharinglinkfol// "SharingLinkFollowSiteContent"
0x756732  stind.ref
0x756733  ldarg.s  6
0x756735  ldarg.s  5
0x756737  ldind.ref
0x756738  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::FollowSiteQuery
0x75673d  ldstr    a1// "1"
0x756742  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756747  stind.ref
0x756748  ldarg.s  6
0x75674a  ldarg.s  6
0x75674c  ldind.ref
0x75674d  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::SiteNameQuery
0x756752  ldarg.s  4
0x756754  ldind.ref
0x756755  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x75675a  stind.ref
0x75675b  ret
0x75675c  ldloc.1
0x75675d  brfalse.s loc_7567AB
0x75675f  ldnull
0x756760  stloc.3
0x756761  ldarg.0
0x756762  ldloc.1
0x756763  ldarg.3
0x756764  ldarg.s  4
0x756766  ldloca.s 3
0x756768  call     void Microsoft.SharePoint.SPAccessRequestsUtility::GetListTitleAndUri(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPList listRequested, [out] string& itemTitle, [out] string& itemDirectLinkText, [out] class [System]System.Uri& directUrl)
0x75676d  ldarg.s  5
0x75676f  ldloc.3
0x756770  ldnull
0x756771  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x756776  brtrue.s loc_75677B
0x756778  ldnull
0x756779  br.s     loc_756787
0x75677b  ldloc.3
0x75677c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x756781  ldc.i4.1
0x756782  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlPathDecode(string urlToDecode, bool allowHashParameter)
0x756787  stind.ref
0x756788  ldarg.s  0xA
0x75678a  ldstr    aSharinglinkdir// "SharingLinkDirect"
0x75678f  stind.ref
0x756790  ldloc.1
0x756791  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x756796  ldc.i4.1
0x756797  bne.un.s loc_7567A2
0x756799  ldarg.s  9
0x75679b  ldstr    aSharingdefault_1// "SharingDefaultMessageDocumentLibrary"
0x7567a0  stind.ref
0x7567a1  ret
0x7567a2  ldarg.s  9
0x7567a4  ldstr    aSharingdefault_2// "SharingDefaultMessageList"
0x7567a9  stind.ref
0x7567aa  ret
0x7567ab  ldloc.2
0x7567ac  brfalse  loc_756B1C
0x7567b1  ldloc.2
0x7567b2  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x7567b7  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x7567bc  ldc.i4.1
0x7567bd  bne.un   loc_756AD5
0x7567c2  ldnull
0x7567c3  stloc.s  4
0x7567c5  ldnull
0x7567c6  stloc.s  5
0x7567c8  ldarg.0
0x7567c9  ldloc.2
0x7567ca  ldarg.3
0x7567cb  ldarg.s  4
0x7567cd  ldloca.s 4
0x7567cf  ldloca.s 5
0x7567d1  ldc.i4.0
0x7567d2  call     void Microsoft.SharePoint.SPAccessRequestsUtility::GetItemTitleAndUri(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPListItem itemRequested, [out] string& itemTitle, [out] string& itemDirectLinkText, [out] class [System]System.Uri& directUrl, [out] class [System]System.Uri& previewUrl, [opt] bool supportListFolders)
0x7567d7  ldarg.s  5
0x7567d9  ldloc.s  4
0x7567db  ldnull
0x7567dc  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x7567e1  brtrue.s loc_7567E6
0x7567e3  ldnull
0x7567e4  br.s     loc_7567F3
0x7567e6  ldloc.s  4
0x7567e8  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x7567ed  ldc.i4.1
0x7567ee  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlPathDecode(string urlToDecode, bool allowHashParameter)
0x7567f3  stind.ref
0x7567f4  ldarg.s  8
0x7567f6  ldloc.s  5
0x7567f8  ldnull
0x7567f9  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x7567fe  brtrue.s loc_756803
0x756800  ldnull
0x756801  br.s     loc_756810
0x756803  ldloc.s  5
0x756805  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x75680a  ldc.i4.1
0x75680b  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlPathDecode(string urlToDecode, bool allowHashParameter)
0x756810  stind.ref
0x756811  ldloc.2
0x756812  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPListItem::get_Folder()
0x756817  brfalse  loc_756908
0x75681c  ldarg.s  9
0x75681e  ldstr    aSharingdefault_3// "SharingDefaultMessageFolder"
0x756823  stind.ref
0x756824  ldarg.s  0xA
0x756826  ldstr    aSharinglinkdir// "SharingLinkDirect"
0x75682b  stind.ref
0x75682c  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x756831  brfalse  loc_756B1C
0x756836  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x75683b  ldc.i4   0x86
0x756840  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x756845  brfalse  loc_756B1C
0x75684a  ldarg.s  0xB
0x75684c  ldstr    aSharinglinkadd// "SharingLinkAddToOneDrive"
0x756851  stind.ref
0x756852  call     string Microsoft.SharePoint.Utilities.MySiteUtility::GetMySiteHostUrl()
0x756857  stloc.s  6
0x756859  ldloc.s  6
0x75685b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x756860  brtrue   loc_756B1C
0x756865  ldarg.s  6
0x756867  ldloc.s  6
0x756869  call     string Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x75686e  call     string Microsoft.SharePoint.Utilities.SPUrlUtility::CombineUrl(string baseUrlPath, string additionalNodes)
0x756873  stind.ref
0x756874  ldarg.s  6
0x756876  ldarg.s  6
0x756878  ldind.ref
0x756879  ldstr    aMysiteAspx// "mysite.aspx"
0x75687e  call     string Microsoft.SharePoint.Utilities.SPUrlUtility::CombineUrl(string baseUrlPath, string additionalNodes)
0x756883  stind.ref
0x756884  ldarg.s  6
0x756886  ldarg.s  6
0x756888  ldind.ref
0x756889  ldstr    aMysiteredirect// "MySiteRedirect"
0x75688e  ldstr    aAlldocuments// "AllDocuments"
0x756893  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756898  stind.ref
0x756899  ldarg.s  6
0x75689b  ldarg.s  6
0x75689d  ldind.ref
0x75689e  ldstr    aMountsiteid// "MountSiteId"
0x7568a3  ldloc.2
0x7568a4  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x7568a9  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x7568ae  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7568b3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x7568b8  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, valuetype [mscorlib]System.Guid value)
0x7568bd  stind.ref
0x7568be  ldarg.s  6
0x7568c0  ldarg.s  6
0x7568c2  ldind.ref
0x7568c3  ldstr    aMountwebid// "MountWebId"
0x7568c8  ldloc.2
0x7568c9  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x7568ce  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x7568d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x7568d8  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, valuetype [mscorlib]System.Guid value)
0x7568dd  stind.ref
0x7568de  ldarg.s  6
0x7568e0  ldarg.s  6
0x7568e2  ldind.ref
0x7568e3  ldstr    aMountitemuniqu// "MountItemUniqueId"
0x7568e8  ldloc.2
0x7568e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPListItem::get_UniqueId()
0x7568ee  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, valuetype [mscorlib]System.Guid value)
0x7568f3  stind.ref
0x7568f4  ldarg.s  6
0x7568f6  ldarg.s  6
0x7568f8  ldind.ref
0x7568f9  ldstr    aMountitemtitle// "MountItemTitle"
0x7568fe  ldarg.s  4
0x756900  ldind.ref
0x756901  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756906  stind.ref
0x756907  ret
0x756908  ldarg.s  9
0x75690a  ldstr    aSharingdefault// "SharingDefaultMessageDocument"
0x75690f  stind.ref
0x756910  ldarg.s  0xA
0x756912  ldstr    aSharinglinkdoc// "SharingLinkDocumentDirect"
0x756917  stind.ref
0x756918  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x75691d  ldc.i4   0x1DD
0x756922  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x756927  brtrue.s loc_756933
0x756929  call     bool Microsoft.SharePoint.Utilities.OfficeGraphUtil::get_IsDocumentSharingEnabledWithDelveLink()
0x75692e  brfalse  loc_756A18
0x756933  ldstr    aSpsharingemail_73// "SPSharingEmailHelper-GenerateMyDelveUrl"...
0x756938  ldc.i4.s 0x32
0x75693a  ldc.i4.0
0x75693b  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x756940  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x756945  stloc.s  0xB
0x756947  call     string Microsoft.SharePoint.Utilities.MySiteUtility::GetMySiteHostUrl()
0x75694c  stloc.s  7
0x75694e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x756953  stloc.s  8
0x756955  ldloc.s  7
0x756957  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x75695c  brtrue.s loc_7569B9
0x75695e  ldloc.s  7
0x756960  call     string Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x756965  call     string Microsoft.SharePoint.Utilities.SPUrlUtility::CombineUrl(string baseUrlPath, string additionalNodes)
0x75696a  stloc.s  9
0x75696c  ldarg.s  7
0x75696e  ldloc.s  9
0x756970  ldarg.2
0x756971  callvirt instance string Microsoft.SharePoint.SPUser::get_SipAddress()
0x756976  ldloc.s  8
0x756978  call     string Microsoft.SharePoint.SPSharingEmailHelper::GenerateMyDelveUrlObsolete(string mySiteLayoutUrl, string email, valuetype [mscorlib]System.Guid sharingClickTrackingGuid)
0x75697d  stind.ref
0x75697e  ldarg.s  0xC
0x756980  ldstr    aSharinglinkrel// "SharingLinkRelatedDelveUser"
0x756985  stind.ref
0x756986  ldc.i4   0x85F0CB
0x75698b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x756990  ldc.i4.s 0x32
0x756992  ldstr    aSharingADocume_0// "Sharing a document with delve document "...
0x756997  ldc.i4.1
0x756998  newarr   [mscorlib]System.Object
0x75699d  stloc.s  0xC
0x75699f  ldloc.s  0xC
0x7569a1  ldc.i4.0
0x7569a2  ldloca.s 8
  ... truncated ...
```
