# Microsoft.SharePoint.SPList::RenderListContextInfo_0

- ea: `0x34bc70`
- end: `0x34cc52`
- name: `Microsoft.SharePoint.SPList::RenderListContextInfo_0`
- size: `4066`
- prototype: ``
- caller_count: `1`
- callee_count: `139`
- tags: `broker_com_uri`

## callers

- `0x34bb80`

## callees

- `0x191de0`
- `0x1935e0`
- `0x26cdd0`
- `0x26f650`
- `0x31fc30`
- `0x31fe80`
- `0x325240`
- `0x342e60`
- `0x342fe0`
- `0x3431e0`
- `0x343230`
- `0x3438a0`
- `0x3438f0`
- `0x343aa0`
- `0x343e80`
- `0x344680`
- `0x344c90`
- `0x345950`
- `0x345a20`
- `0x345c30`
- `0x345d00`
- `0x345dc0`
- `0x345f90`
- `0x346530`
- `0x3467e0`
- `0x346ef0`
- `0x347300`
- `0x347690`
- `0x3478e0`
- `0x34aec0`
- `0x34aed0`
- `0x34aef0`
- `0x34af20`
- `0x34af60`
- `0x34b780`
- `0x34b7f0`
- `0x34b840`
- `0x34ba10`
- `0x34bba0`
- `0x34bc70`
- `0x34cc60`
- `0x34f600`
- `0x350330`
- `0x3526f0`
- `0x352d40`
- `0x354cc0`
- `0x355ae0`
- `0x355b30`
- `0x356750`
- `0x3cd1a0`

## string_xrefs

- `0x34ca91`: `SiteTemplateId`
- `0x34c5f1`: `WriteSecurity`
- `0x34c2ab`: `ListTemplateType`
- `0x34bc90`: `Templates`
- `0x34bebe`: `Port template URL normalization behavior from SPToolBar.AddNewDocumentMenuItem`
- `0x34bf8a`: `templateUrl`
- `0x34c304`: `overrideSelectCommand`
- `0x34c428`: `listTemplate`
- `0x34c49a`: `HttpPath`
- `0x34c520`: `imagesPath`
- `0x34c946`: `canUserCreateMicrosoftForm`
- `0x34c95d`: `AllowCreateFolder`
- `0x34c96f`: `CanShareLinkForNewDocument`
- `0x34cb0b`: `Support 3rd level of quick launch links in modern`

## pseudocode

```c

```

## disassembly

```asm
0x34bc70  ldnull
0x34bc71  stloc.0
0x34bc72  ldarg.1
0x34bc73  ldstr    asc_C85B6E// "{"
0x34bc78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bc7d  ldarg.1
0x34bc7e  ldstr    aWpq// "wpq"
0x34bc83  ldstr    asc_C00000// ""
0x34bc88  ldc.i4.0
0x34bc89  ldc.i4.0
0x34bc8a  call     void Microsoft.SharePoint.SPList::WriteJSONKeyValuePair(class [mscorlib]System.IO.TextWriter writer, string key, string value, [opt] bool omitQuotes, [opt] bool omitTrailingComma)
0x34bc8f  ldarg.1
0x34bc90  ldstr    aTemplates// "Templates"
0x34bc95  ldstr    asc_DED9C2// "{}"
0x34bc9a  ldc.i4.1
0x34bc9b  ldc.i4.0
0x34bc9c  call     void Microsoft.SharePoint.SPList::WriteJSONKeyValuePair(class [mscorlib]System.IO.TextWriter writer, string key, string value, [opt] bool omitQuotes, [opt] bool omitTrailingComma)
0x34bca1  ldarg.1
0x34bca2  ldstr    aListdata// "\"ListData\":"
0x34bca7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bcac  ldnull
0x34bcad  stloc.1
0x34bcae  ldarg.s  5
0x34bcb0  brfalse.s loc_34BCCE
0x34bcb2  ldarg.0
0x34bcb3  ldarg.3
0x34bcb4  callvirt instance string Microsoft.SharePoint.SPRenderListDataParameters::get_ViewXml()
0x34bcb9  ldarg.2
0x34bcba  ldc.i4.0
0x34bcbb  ldarg.3
0x34bcbc  ldarg.s  4
0x34bcbe  ldarg.1
0x34bcbf  ldloca.s 1
0x34bcc1  call     instance string Microsoft.SharePoint.SPList::RenderListData(string viewXml, class Microsoft.SharePoint.SPView view, bool ecbMode, class Microsoft.SharePoint.SPRenderListDataParameters parameters, class Microsoft.SharePoint.SPRenderListDataOverrideParameters overrideParameters, class [mscorlib]System.IO.TextWriter writer, [out] class Microsoft.SharePoint.WebPartPages.XsltListViewWebPart& xslWebPart)
0x34bcc6  pop
0x34bcc7  ldloc.0
0x34bcc8  brtrue.s loc_34BCD9
0x34bcca  ldloc.1
0x34bccb  stloc.0
0x34bccc  br.s     loc_34BCD9
0x34bcce  ldarg.1
0x34bccf  ldstr    aNull_2// "null"
0x34bcd4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bcd9  ldloc.0
0x34bcda  brtrue.s loc_34BCF3
0x34bcdc  ldarg.0
0x34bcdd  ldarg.2
0x34bcde  ldarg.0
0x34bcdf  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x34bce4  ldarg.3
0x34bce5  callvirt instance string Microsoft.SharePoint.SPRenderListDataParameters::get_ViewXml()
0x34bcea  ldc.i4.0
0x34bceb  ldc.i4.0
0x34bcec  ldc.i4.0
0x34bced  call     instance class Microsoft.SharePoint.WebPartPages.XsltListViewWebPart Microsoft.SharePoint.SPList::InstantiateViewWithProperty(class Microsoft.SharePoint.SPView view, class Microsoft.SharePoint.SPWeb web, string viewXml, [opt] bool bRequireFileRef, [opt] bool bReplaceGroup, [opt] bool bAddRequiredFields)
0x34bcf2  stloc.0
0x34bcf3  ldloc.0
0x34bcf4  ldc.i4.1
0x34bcf5  callvirt instance void Microsoft.SharePoint.WebPartPages.XsltListViewWebPart::set_RenderDataFromDataSource(bool value)
0x34bcfa  ldloc.0
0x34bcfb  callvirt instance void Microsoft.SharePoint.WebPartPages.DataFormWebPart::PrepareAndPerformTransform()
0x34bd00  ldarg.1
0x34bd01  ldstr    asc_C6AA4A// ","
0x34bd06  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bd0b  ldarg.1
0x34bd0c  ldstr    aListschema// "\"ListSchema\":"
0x34bd11  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bd16  ldarg.s  6
0x34bd18  brfalse.s loc_34BD25
0x34bd1a  ldarg.0
0x34bd1b  ldloc.0
0x34bd1c  ldarg.2
0x34bd1d  ldarg.1
0x34bd1e  call     instance void Microsoft.SharePoint.SPList::RenderListSchema(class Microsoft.SharePoint.WebPartPages.XsltListViewWebPart xslWebPart, class Microsoft.SharePoint.SPView view, class [mscorlib]System.IO.TextWriter output)
0x34bd23  br.s     loc_34BD30
0x34bd25  ldarg.1
0x34bd26  ldstr    aNull_2// "null"
0x34bd2b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bd30  ldarg.s  7
0x34bd32  brfalse  loc_34C1AE
0x34bd37  ldarg.3
0x34bd38  callvirt instance bool Microsoft.SharePoint.SPRenderListDataParameters::get_DeferredRender()
0x34bd3d  brtrue.s loc_34BD63
0x34bd3f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::ContentTypeFetchFolderKillSwitch
0x34bd44  ldstr    a03172017// "03/17/2017"
0x34bd49  ldstr    aFetchRealFolde// "Fetch real folder for contenttype order"
0x34bd4e  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x34bd53  brfalse.s loc_34BD63
0x34bd55  ldarg.0
0x34bd56  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.SPContentType> Microsoft.SharePoint.SPList::get_DefaultContentTypeOrder()
0x34bd5b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPContentType>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x34bd60  stloc.2
0x34bd61  br.s     loc_34BDA7
0x34bd63  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x34bd68  callvirt instance string Microsoft.SharePoint.SPContext::get_RootFolderUrl()
0x34bd6d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bd72  brtrue.s loc_34BD96
0x34bd74  ldarg.0
0x34bd75  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x34bd7a  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x34bd7f  callvirt instance class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.SPContext::get_RootFolderPath()
0x34bd84  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPWeb::GetFolder(class Microsoft.SharePoint.SPResourcePath path)
0x34bd89  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.SPContentType> Microsoft.SharePoint.SPFolder::get_ContentTypeOrder()
0x34bd8e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPContentType>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x34bd93  stloc.2
0x34bd94  br.s     loc_34BDA7
0x34bd96  ldarg.0
0x34bd97  call     instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x34bd9c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.SPContentType> Microsoft.SharePoint.SPFolder::get_ContentTypeOrder()
0x34bda1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPContentType>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x34bda6  stloc.2
0x34bda7  ldarg.1
0x34bda8  ldstr    aListcontentype// ", \"ListContenTypes\": ["
0x34bdad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bdb2  ldc.i4.1
0x34bdb3  stloc.3
0x34bdb4  ldarg.2
0x34bdb5  brfalse.s loc_34BDCE
0x34bdb7  ldarg.2
0x34bdb8  callvirt instance valuetype Microsoft.SharePoint.SPViewScope Microsoft.SharePoint.SPView::get_Scope()
0x34bdbd  ldc.i4.3
0x34bdbe  beq.s    loc_34BDCB
0x34bdc0  ldarg.2
0x34bdc1  callvirt instance valuetype Microsoft.SharePoint.SPViewScope Microsoft.SharePoint.SPView::get_Scope()
0x34bdc6  ldc.i4.1
0x34bdc7  ceq
0x34bdc9  br.s     loc_34BDCF
0x34bdcb  ldc.i4.1
0x34bdcc  br.s     loc_34BDCF
0x34bdce  ldc.i4.0
0x34bdcf  stloc.s  4
0x34bdd1  ldloc.2
0x34bdd2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.SPContentType>::GetEnumerator()
0x34bdd7  stloc.s  0x19
0x34bdd9  br       loc_34C189
0x34bdde  ldloc.s  0x19
0x34bde0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.SPContentType>::get_Current()
0x34bde5  stloc.s  5
0x34bde7  ldloc.s  5
0x34bde9  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34bdee  stloc.s  0x1A
0x34bdf0  ldloca.s 0x1A
0x34bdf2  call     instance bool Microsoft.SharePoint.SPContentTypeId::get_IsFolder()
0x34bdf7  brfalse.s loc_34BE17
0x34bdf9  ldloc.s  4
0x34bdfb  brfalse.s loc_34BE17
0x34bdfd  ldloc.s  5
0x34bdff  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34be04  stloc.s  0x1B
0x34be06  ldloca.s 0x1B
0x34be08  ldsfld   valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPBuiltInContentTypeId::DocumentSet
0x34be0d  call     instance bool Microsoft.SharePoint.SPContentTypeId::IsChildOf(valuetype Microsoft.SharePoint.SPContentTypeId id)
0x34be12  brfalse  loc_34C189
0x34be17  ldloc.s  5
0x34be19  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0x34be1e  ldstr    aHidden_0// "_Hidden"
0x34be23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34be28  brtrue   loc_34C189
0x34be2d  ldloc.s  5
0x34be2f  callvirt instance bool Microsoft.SharePoint.SPContentType::get_Hidden()
0x34be34  brtrue   loc_34C189
0x34be39  ldloc.s  5
0x34be3b  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34be40  stloc.s  0x1C
0x34be42  ldloca.s 0x1C
0x34be44  ldsfld   valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SitePagesFeatureReceiver::SitePageContentTypeId
0x34be49  call     instance bool Microsoft.SharePoint.SPContentTypeId::IsChildOf(valuetype Microsoft.SharePoint.SPContentTypeId id)
0x34be4e  brfalse.s loc_34BE6E
0x34be50  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x34be55  brfalse  loc_34C189
0x34be5a  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x34be5f  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPContext::get_SiteSubscription()
0x34be64  call     bool Microsoft.SharePoint.SitePagesHelper::IsSitePagesEnabledOnSiteSubscription(class Microsoft.SharePoint.SPSiteSubscription subscription)
0x34be69  brfalse  loc_34C189
0x34be6e  ldloc.3
0x34be6f  brfalse.s loc_34BE75
0x34be71  ldc.i4.0
0x34be72  stloc.3
0x34be73  br.s     loc_34BE80
0x34be75  ldarg.1
0x34be76  ldstr    asc_C6AA4A// ","
0x34be7b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34be80  ldloc.s  5
0x34be82  callvirt instance string Microsoft.SharePoint.SPContentType::get_DocumentTemplateUrl()
0x34be87  stloc.s  6
0x34be89  ldarg.0
0x34be8a  call     instance bool Microsoft.SharePoint.SPList::get_ContentTypesEnabled()
0x34be8f  brtrue.s loc_34BEE7
0x34be91  ldarg.0
0x34be92  isinst   Microsoft.SharePoint.SPDocumentLibrary
0x34be97  stloc.s  7
0x34be99  ldloc.s  7
0x34be9b  brfalse.s loc_34BEE7
0x34be9d  ldloc.s  7
0x34be9f  callvirt instance string Microsoft.SharePoint.SPDocumentLibrary::get_DocumentTemplateUrl()
0x34bea4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bea9  brtrue.s loc_34BEE7
0x34beab  ldloc.s  7
0x34bead  callvirt instance string Microsoft.SharePoint.SPDocumentLibrary::get_DocumentTemplateUrl()
0x34beb2  stloc.s  6
0x34beb4  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::s_guidNormalizeTemplateUrl
0x34beb9  ldstr    a03052018// "03/05/2018"
0x34bebe  ldstr    aPortTemplateUr// "Port template URL normalization behavio"...
0x34bec3  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x34bec8  brtrue.s loc_34BEE7
0x34beca  ldloc.s  6
0x34becc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bed1  brtrue.s loc_34BEE7
0x34bed3  ldarg.0
0x34bed4  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x34bed9  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x34bede  ldloc.s  6
0x34bee0  call     string Microsoft.SharePoint.Utilities.SPUrlUtility::CombineUrl(string baseUrlPath, string additionalNodes)
0x34bee5  stloc.s  6
0x34bee7  ldsfld   string [mscorlib]System.String::Empty
0x34beec  stloc.s  8
0x34beee  ldloc.s  6
0x34bef0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bef5  brfalse.s loc_34BF3B
0x34bef7  ldloc.s  5
0x34bef9  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34befe  stloc.s  0x1D
0x34bf00  ldloca.s 0x1D
0x34bf02  ldsfld   valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPBuiltInContentTypeId::DocumentSet
0x34bf07  call     instance bool Microsoft.SharePoint.SPContentTypeId::IsChildOf(valuetype Microsoft.SharePoint.SPContentTypeId id)
0x34bf0c  brfalse.s loc_34BF3B
0x34bf0e  ldarg.0
0x34bf0f  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x34bf14  call     string Microsoft.SharePoint.WebControls.NewMenu::NewFormUrl(class Microsoft.SharePoint.SPList list, class Microsoft.SharePoint.SPContext renderContext)
0x34bf19  ldstr    aContenttypeid_0// "&ContentTypeId="
0x34bf1e  ldloc.s  5
0x34bf20  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34bf25  stloc.s  0x1E
0x34bf27  ldloca.s 0x1E
0x34bf29  constrained. Microsoft.SharePoint.SPContentTypeId
0x34bf2f  callvirt instance string [mscorlib]System.Object::ToString()
0x34bf34  call     string [mscorlib]System.String::Concat(string, string, string)
0x34bf39  stloc.s  8
0x34bf3b  ldloc.s  5
0x34bf3d  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0x34bf42  stloc.s  0xA
0x34bf44  ldloc.s  5
0x34bf46  callvirt instance string Microsoft.SharePoint.SPContentType::get_Description()
0x34bf4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bf50  brfalse.s loc_34BF75
0x34bf52  ldstr    aToolbarmenubas// "ToolBarMenuBaseContentTypeDescription"
0x34bf57  ldc.i4.1
0x34bf58  newarr   [mscorlib]System.Object
0x34bf5d  stloc.s  0x1F
0x34bf5f  ldloc.s  0x1F
0x34bf61  ldc.i4.0
0x34bf62  ldloc.s  5
0x34bf64  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0x34bf69  stelem.ref
0x34bf6a  ldloc.s  0x1F
0x34bf6c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x34bf71  stloc.s  9
0x34bf73  br.s     loc_34BF7E
0x34bf75  ldloc.s  5
0x34bf77  callvirt instance string Microsoft.SharePoint.SPContentType::get_Description()
0x34bf7c  stloc.s  9
0x34bf7e  ldarg.1
0x34bf7f  ldstr    asc_C85B6E// "{"
0x34bf84  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x34bf89  ldarg.1
0x34bf8a  ldstr    aTemplateurl// "templateUrl"
0x34bf8f  ldarg.0
0x34bf90  ldloc.s  6
0x34bf92  ldloc.s  5
0x34bf94  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34bf99  stloc.s  0x20
0x34bf9b  ldloca.s 0x20
0x34bf9d  constrained. Microsoft.SharePoint.SPContentTypeId
0x34bfa3  callvirt instance string [mscorlib]System.Object::ToString()
0x34bfa8  ldloca.s 0xB
0x34bfaa  call     instance string Microsoft.SharePoint.SPList::ComputeTemplateUrl(string templateUrl, string contentTypeId, [out] string& strOpenApp)
0x34bfaf  ldc.i4.0
0x34bfb0  ldc.i4.0
0x34bfb1  call     void Microsoft.SharePoint.SPList::WriteJSONKeyValuePair(class [mscorlib]System.IO.TextWriter writer, string key, string value, [opt] bool omitQuotes, [opt] bool omitTrailingComma)
0x34bfb6  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::ReturnContentTypeIdKillSwitch
0x34bfbb  ldstr    a1102018// "1/10/2018"
0x34bfc0  ldstr    aReturnContentt// "Return contentTypeId"
0x34bfc5  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x34bfca  brtrue.s loc_34BFEF
0x34bfcc  ldarg.1
0x34bfcd  ldstr    aContenttypeid_1// "contentTypeId"
0x34bfd2  ldloc.s  5
0x34bfd4  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0x34bfd9  stloc.s  0x21
0x34bfdb  ldloca.s 0x21
0x34bfdd  constrained. Microsoft.SharePoint.SPContentTypeId
0x34bfe3  callvirt instance string [mscorlib]System.Object::ToString()
0x34bfe8  ldc.i4.0
0x34bfe9  ldc.i4.0
0x34bfea  call     void Microsoft.SharePoint.SPList::WriteJSONKeyValuePair(class [mscorlib]System.IO.TextWriter writer, string key, string value, [opt] bool omitQuotes, [opt] bool omitTrailingComma)
0x34bfef  ldloc.s  0xB
0x34bff1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34bff6  brtrue.s loc_34C007
0x34bff8  ldarg.1
0x34bff9  ldstr    aAppmap// "appMap"
  ... truncated ...
```
