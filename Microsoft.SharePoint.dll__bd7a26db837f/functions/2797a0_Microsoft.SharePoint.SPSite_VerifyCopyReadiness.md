# Microsoft.SharePoint.SPSite::VerifyCopyReadiness

- ea: `0x2797a0`
- end: `0x27a81e`
- name: `Microsoft.SharePoint.SPSite::VerifyCopyReadiness`
- size: `4222`
- prototype: ``
- caller_count: `0`
- callee_count: `76`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1b57a0`
- `0x1b7df0`
- `0x25e260`
- `0x269aa0`
- `0x26b700`
- `0x26b840`
- `0x26bde0`
- `0x26e030`
- `0x26e660`
- `0x26f6c0`
- `0x2700f0`
- `0x2797a0`
- `0x29d0f0`
- `0x29d160`
- `0x342f00`
- `0x344790`
- `0x344830`
- `0x345a20`
- `0x345d00`
- `0x347300`
- `0x46a260`
- `0x46b420`
- `0x46bf40`
- `0x46c520`
- `0x46c940`
- `0x4e7720`
- `0x507700`
- `0x50c650`
- `0x50d3e0`
- `0x50d5b0`
- `0x50d810`
- `0x50d830`
- `0x510900`
- `0x510910`
- `0x5110f0`
- `0x521760`
- `0x521950`
- `0x5226a0`
- `0x5226c0`
- `0x526cc0`
- `0x53be00`
- `0x53e830`
- `0x53e8c0`
- `0x5729d0`
- `0x577060`
- `0x57db20`
- `0x58f8b0`
- `0x58f8c0`
- `0x58f8e0`
- `0x58f900`

## string_xrefs

- `0x2797c5`: `CreateCopyJobs is not enabled in this environment: [id={0}] [url={1}]`
- `0x279808`: `UseResourcePathInCopyJob`
- `0x279bf5`: `UseResourcePathInCopyJob`
- `0x279d6a`: `UseResourcePathInCopyJob`
- `0x279ddd`: `UseResourcePathInCopyJob`
- `0x279fa9`: `UseResourcePathInCopyJob`
- `0x27a0f1`: `UseResourcePathInCopyJob`
- `0x27a530`: `UseResourcePathInCopyJob`
- `0x27a66b`: `UseResourcePathInCopyJob`
- `0x279843`: `CopyMoveNotSupportedOnIRMLibrary`
- `0x279893`: `CreateCopyJobs in move mode is not enabled on for target site: [id={0}] [url={1}]`
- `0x279a6f`: `Cross-Geo Move : Get web relative URL for later use to get list schema.`
- `0x279adc`: `Cross-Geo Move : Get web relative URL {0} from REST request.`
- `0x279b22`: `Cross-Geo Move: Failed to get target web due to error {0}`
- `0x279bae`: `CopyMoveObjectsNotFromSameLevel`
- `0x279e5d`: `Cross-Geo Move: Sent information to target site to verify if root objects {0} exist`
- `0x279f84`: `MoreLoggingForMove`
- `0x27a04e`: `Copy/move destination requires checkout`
- `0x27a06d`: `Copy/move destination requires content approval`
- `0x27a15d`: `Cross-Geo Move : Get target list [{0}] schema.`
- `0x27a39c`: `MoveMismatchSchema`
- `0x27a45d`: `MoveMismatchSchema`
- `0x27a5e9`: `Failed to create dummy file at destination due to error {0}`
- `0x27a6a8`: `DeleteByRetentionDummyFile`
- `0x27a71f`: `Cross-Geo Move: Sent information to target site to verify if user has permission to add file`
- `0x27a758`: `Cross-Geo Failed to create dummy file at destination: {0}. Error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2797a0  ldarg.s  5
0x2797a2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.SPListItem, int32>::.ctor()
0x2797a7  stind.ref
0x2797a8  ldarg.s  6
0x2797aa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.SharePoint.SPListItem>::.ctor()
0x2797af  stind.ref
0x2797b0  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x2797b5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Administration.SPFarm::get_IsCNHosted()
0x2797ba  stloc.s  0x48
0x2797bc  ldloca.s 0x48
0x2797be  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x2797c3  brfalse.s loc_2797F9
0x2797c5  ldstr    aCreatecopyjobs// "CreateCopyJobs is not enabled in this e"...
0x2797ca  ldarg.0
0x2797cb  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x2797d0  box      [mscorlib]System.Guid
0x2797d5  ldarg.0
0x2797d6  call     instance string Microsoft.SharePoint.SPSite::get_Url()
0x2797db  call     string [mscorlib]System.String::Format(string, object, object)
0x2797e0  stloc.0
0x2797e1  ldc.i4   0x164F3D2
0x2797e6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x2797eb  ldc.i4.s 0x32
0x2797ed  ldloc.0
0x2797ee  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2797f3  newobj   instance void Microsoft.SharePoint.SPExperimentalFeatureException::.ctor()
0x2797f8  throw
0x2797f9  ldstr    a63d73645Cea746// "63d73645-cea7-46b6-9fbd-13879e399209"
0x2797fe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x279803  ldstr    a04202018// "04/20/2018"
0x279808  ldstr    aUseresourcepat// "UseResourcePathInCopyJob"
0x27980d  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x279812  brtrue.s loc_279826
0x279814  ldarg.s  4
0x279816  ldarg.1
0x279817  ldc.i4.0
0x279818  ldelem.ref
0x279819  call     class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.SPResourcePath::FromUri(class [System]System.Uri uri)
0x27981e  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPWeb::GetList(class Microsoft.SharePoint.SPResourcePath path)
0x279823  stloc.1
0x279824  br.s     loc_27983B
0x279826  ldarg.s  4
0x279828  ldarg.1
0x279829  ldc.i4.0
0x27982a  ldelem.ref
0x27982b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x279830  call     string [System]System.Uri::UnescapeDataString(string)
0x279835  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPWeb::GetList(string strUrl)
0x27983a  stloc.1
0x27983b  ldloc.1
0x27983c  callvirt instance bool Microsoft.SharePoint.SPList::get_IrmEnabled()
0x279841  brfalse.s loc_279872
0x279843  ldstr    aCopymovenotsup// "CopyMoveNotSupportedOnIRMLibrary"
0x279848  ldc.i4.0
0x279849  newarr   [mscorlib]System.Object
0x27984e  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x279853  stloc.2
0x279854  ldc.i4   0x184D81A
0x279859  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x27985e  ldc.i4.s 0xA
0x279860  ldloc.2
0x279861  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x279866  ldloc.2
0x279867  ldc.i4   0x80042011
0x27986c  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x279871  throw
0x279872  ldarg.3
0x279873  callvirt instance bool Microsoft.SharePoint.SPCopyMigrationOptions::get_IsMoveMode()
0x279878  brfalse.s loc_2798CE
0x27987a  ldc.i4   0x47E2
0x27987f  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x279884  brfalse.s loc_279893
0x279886  ldarg.0
0x279887  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x27988c  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsExportListItemETagVersion()
0x279891  brtrue.s loc_2798C7
0x279893  ldstr    aCreatecopyjobs_0// "CreateCopyJobs in move mode is not enab"...
0x279898  ldarg.0
0x279899  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x27989e  box      [mscorlib]System.Guid
0x2798a3  ldarg.0
0x2798a4  call     instance string Microsoft.SharePoint.SPSite::get_Url()
0x2798a9  call     string [mscorlib]System.String::Format(string, object, object)
0x2798ae  stloc.3
0x2798af  ldc.i4   0x178E24C
0x2798b4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x2798b9  ldc.i4.s 0x32
0x2798bb  ldloc.3
0x2798bc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2798c1  newobj   instance void Microsoft.SharePoint.SPExperimentalFeatureException::.ctor()
0x2798c6  throw
0x2798c7  ldarg.3
0x2798c8  ldc.i4.0
0x2798c9  callvirt instance void Microsoft.SharePoint.SPCopyMigrationOptions::set_IgnoreVersionHistory(bool value)
0x2798ce  ldc.i4.0
0x2798cf  stloc.s  4
0x2798d1  ldarg.2
0x2798d2  ldc.i4.1
0x2798d3  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x2798d8  call     bool Microsoft.SharePoint.SPSite::Exists(string url)
0x2798dd  brtrue.s loc_27995D
0x2798df  ldc.i4   0x47E6
0x2798e4  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x2798e9  brtrue.s loc_27990E
0x2798eb  ldstr    aMultiGeoScenar// "Multi-Geo scenario not enabled. [Source"...
0x2798f0  ldarg.1
0x2798f1  ldc.i4.0
0x2798f2  ldelem.ref
0x2798f3  callvirt instance string [mscorlib]System.Object::ToString()
0x2798f8  ldarg.2
0x2798f9  callvirt instance string [mscorlib]System.Object::ToString()
0x2798fe  call     string [mscorlib]System.String::Format(string, object, object)
0x279903  ldc.i4   0x8004201F
0x279908  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x27990d  throw
0x27990e  ldarg.2
0x27990f  ldarg.1
0x279910  ldc.i4.0
0x279911  ldelem.ref
0x279912  ldnull
0x279913  ldnull
0x279914  newobj   instance void Microsoft.SharePoint.Deployment.MultiGeoCopyRestApiClient::.ctor(class [System]System.Uri host, class [System]System.Uri local, [opt] class Microsoft.SharePoint.SPUserToken userToken, [opt] class Microsoft.SharePoint.IdentityModel.SPIdentityContext context)
0x279919  stloc.s  5
0x27991b  ldloc.s  5
0x27991d  callvirt instance class [System]System.Net.HttpWebResponse Microsoft.SharePoint.Deployment.MultiGeoCopyRestApiClient::SendRESTResquestGetSite()
0x279922  pop
0x279923  leave.s  loc_27995A
0x279925  stloc.s  6
0x279927  ldc.i4   0x185565E
0x27992c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x279931  ldc.i4.s 0x32
0x279933  ldloc.s  6
0x279935  callvirt instance string [mscorlib]System.Exception::get_Message()
0x27993a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x27993f  ldstr    aTargetsiteurle// "TargetSiteUrlError"
0x279944  ldc.i4.0
0x279945  newarr   [mscorlib]System.Object
0x27994a  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x27994f  ldc.i4   0x80042020
0x279954  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x279959  throw
0x27995a  ldc.i4.1
0x27995b  stloc.s  4
0x27995d  ldarg.1
0x27995e  ldc.i4.0
0x27995f  ldelem.ref
0x279960  callvirt instance string [mscorlib]System.Object::ToString()
0x279965  newobj   instance void Microsoft.SharePoint.SPRemoteWeb::.ctor(string requestUrl)
0x27996a  pop
0x27996b  leave.s  loc_279999
0x27996d  stloc.s  7
0x27996f  ldc.i4   0x180B15C
0x279974  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x279979  ldc.i4.s 0xA
0x27997b  ldloc.s  7
0x27997d  callvirt instance string [mscorlib]System.Object::ToString()
0x279982  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x279987  ldloc.s  7
0x279989  callvirt instance string [mscorlib]System.Exception::get_Message()
0x27998e  ldc.i4   0x8004201C
0x279993  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x279998  throw
0x279999  ldloc.s  4
0x27999b  brtrue.s loc_2799D7
0x27999d  ldarg.2
0x27999e  callvirt instance string [mscorlib]System.Object::ToString()
0x2799a3  newobj   instance void Microsoft.SharePoint.SPRemoteWeb::.ctor(string requestUrl)
0x2799a8  pop
0x2799a9  leave.s  loc_2799D7
0x2799ab  stloc.s  8
0x2799ad  ldc.i4   0x180B15D
0x2799b2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x2799b7  ldc.i4.s 0xA
0x2799b9  ldloc.s  8
0x2799bb  callvirt instance string [mscorlib]System.Object::ToString()
0x2799c0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2799c5  ldloc.s  8
0x2799c7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2799cc  ldc.i4   0x8004201D
0x2799d1  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x2799d6  throw
0x2799d7  ldnull
0x2799d8  stloc.s  9
0x2799da  ldarg.2
0x2799db  ldarg.1
0x2799dc  ldc.i4.0
0x2799dd  ldelem.ref
0x2799de  ldarg.0
0x2799df  call     instance class Microsoft.SharePoint.SPUserToken Microsoft.SharePoint.SPSite::get_UserToken()
0x2799e4  ldnull
0x2799e5  newobj   instance void Microsoft.SharePoint.Deployment.MultiGeoCopyRestApiClient::.ctor(class [System]System.Uri host, class [System]System.Uri local, [opt] class Microsoft.SharePoint.SPUserToken userToken, [opt] class Microsoft.SharePoint.IdentityModel.SPIdentityContext context)
0x2799ea  stloc.s  0xA
0x2799ec  ldc.i4.0
0x2799ed  stloc.s  0xB
0x2799ef  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2799f4  stloc.s  0xC
0x2799f6  ldstr    a0Verifyperm1// "{0}/VerifyPerm({1})"
0x2799fb  ldarg.2
0x2799fc  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x279a01  ldloc.s  0xC
0x279a03  box      [mscorlib]System.Guid
0x279a08  call     string [mscorlib]System.String::Format(string, object, object)
0x279a0d  newobj   instance void [System]System.Uri::.ctor(string)
0x279a12  stloc.s  0xD
0x279a14  ldsfld   string [mscorlib]System.String::Empty
0x279a19  stloc.s  0xE
0x279a1b  ldarg.3
0x279a1c  callvirt instance bool Microsoft.SharePoint.SPCopyMigrationOptions::get_IsMoveMode()
0x279a21  brtrue.s loc_279A32
0x279a23  ldc.i4   0x3B6A
0x279a28  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x279a2d  brfalse  loc_279B3E
0x279a32  ldloc.s  4
0x279a34  brtrue.s loc_279A63
0x279a36  ldarg.2
0x279a37  callvirt instance string [mscorlib]System.Object::ToString()
0x279a3c  ldarg.0
0x279a3d  call     instance class Microsoft.SharePoint.SPUserToken Microsoft.SharePoint.SPSite::get_UserToken()
0x279a42  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(string requestUrl, class Microsoft.SharePoint.SPUserToken userToken)
0x279a47  stloc.s  0xF
0x279a49  ldloc.s  0xF
0x279a4b  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSite::OpenWeb()
0x279a50  stloc.s  9
0x279a52  leave    loc_279B3E
0x279a57  ldloc.s  0xF
0x279a59  brfalse.s loc_279A62
0x279a5b  ldloc.s  0xF
0x279a5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x279a62  endfinally
0x279a63  ldc.i4   0x18D0804
0x279a68  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x279a6d  ldc.i4.s 0x32
0x279a6f  ldstr    aCrossGeoMoveGe// "Cross-Geo Move : Get web relative URL f"...
0x279a74  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x279a79  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x279a7e  stloc.s  0x10
0x279a80  ldloc.s  0xA
0x279a82  ldarg.2
0x279a83  callvirt instance class [System]System.Net.HttpWebResponse Microsoft.SharePoint.Deployment.MultiGeoCopyRestApiClient::SendRESTResquestGetWebRelativeURL(class [System]System.Uri destinationUri)
0x279a88  stloc.s  0x11
0x279a8a  ldloc.s  0x11
0x279a8c  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x279a91  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x279a96  stloc.s  0x12
0x279a98  ldloc.s  0x12
0x279a9a  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x279a9f  stloc.s  0x13
0x279aa1  ldloc.s  0x10
0x279aa3  ldloc.s  0x13
0x279aa5  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x279aaa  ldloc.s  0x10
0x279aac  ldstr    aDUrl// "d:Url"
0x279ab1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x279ab6  ldc.i4.0
0x279ab7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x279abc  stloc.s  0x14
0x279abe  ldloc.s  0x14
0x279ac0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x279ac5  stloc.s  0xE
0x279ac7  ldloc.s  0xA
0x279ac9  ldloc.s  0xE
0x279acb  callvirt instance void Microsoft.SharePoint.Deployment.MultiGeoCopyRestApiClient::set_targetWebUrl(string value)
0x279ad0  ldc.i4   0x18DD095
0x279ad5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x279ada  ldc.i4.s 0x32
0x279adc  ldstr    aCrossGeoMoveGe_0// "Cross-Geo Move : Get web relative URL {"...
0x279ae1  ldc.i4.1
0x279ae2  newarr   [mscorlib]System.Object
0x279ae7  stloc.s  0x49
0x279ae9  ldloc.s  0x49
0x279aeb  ldc.i4.0
0x279aec  ldloc.s  0xE
0x279aee  stelem.ref
0x279aef  ldloc.s  0x49
0x279af1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x279af6  leave.s  loc_279B04
0x279af8  ldloc.s  0x12
0x279afa  brfalse.s loc_279B03
0x279afc  ldloc.s  0x12
0x279afe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x279b03  endfinally
0x279b04  leave.s  loc_279B12
0x279b06  ldloc.s  0x11
0x279b08  brfalse.s loc_279B11
0x279b0a  ldloc.s  0x11
0x279b0c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x279b11  endfinally
0x279b12  leave.s  loc_279B3E
0x279b14  stloc.s  0x15
0x279b16  ldc.i4   0x18D0805
0x279b1b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Migration()
0x279b20  ldc.i4.s 0xA
0x279b22  ldstr    aCrossGeoMoveFa// "Cross-Geo Move: Failed to get target we"...
0x279b27  ldc.i4.1
0x279b28  newarr   [mscorlib]System.Object
0x279b2d  stloc.s  0x49
0x279b2f  ldloc.s  0x49
0x279b31  ldc.i4.0
0x279b32  ldloc.s  0x15
0x279b34  stelem.ref
  ... truncated ...
```
