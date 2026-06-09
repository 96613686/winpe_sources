# Microsoft.SharePoint.SPSharingEmailHelper::GetNotificationMessageComponents_0

- ea: `0x756b40`
- end: `0x7571cb`
- name: `Microsoft.SharePoint.SPSharingEmailHelper::GetNotificationMessageComponents_0`
- size: `1675`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x74fd30`
- `0x756b20`

## callees

- `0x187950`
- `0x1a2030`
- `0x1fa8a0`
- `0x1fa8c0`
- `0x1fa8e0`
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
- `0x50d860`
- `0x5263f0`
- `0x53be00`
- `0x53bf80`
- `0x53e830`
- `0x53e8c0`
- `0x53ed60`
- `0x542e10`
- `0x542e40`
- `0x5c24f0`
- `0x5c3b50`
- `0x5c3ce0`
- `0x5c3eb0`
- `0x678580`
- `0x732ff0`
- `0x756b40`
- `0x7574b0`
- `0x759290`
- `0x789b20`
- `0x78c690`
- `0x7bea40`
- `0x93dab0`
- `0x957470`
- `0xaefbc0`

## string_xrefs

- `0x756c48`: `SharingLinkDirect`
- `0x756d16`: `SharingLinkDirect`
- `0x756e6a`: `SharingLinkDirect`
- `0x75716e`: `SharingLinkDirect`
- `0x756c5c`: `SharingLinkFollowSiteContent`
- `0x756e90`: `SharingLinkAddToOneDrive`
- `0x756ee2`: `MountSiteId`
- `0x756f08`: `MountWebId`
- `0x756f29`: `MountItemUniqueId`
- `0x756f40`: `MountItemTitle`
- `0x756fdc`: `SharingLinkDocumentDirect`
- `0x756ffe`: `SharingLinkFollowDocContent`
- `0x756bed`: `DirectUrlEmailQS:TemplateVersion`
- `0x756bff`: `DirectUrlEmailQS:ResourceLink`

## pseudocode

```c

```

## disassembly

```asm
0x756b40  ldarg.s  0xD
0x756b42  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x756b47  ldc.i4.0
0x756b48  ceq
0x756b4a  stloc.0
0x756b4b  ldarg.s  0xE
0x756b4d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x756b52  ldc.i4.0
0x756b53  ceq
0x756b55  stloc.1
0x756b56  ldarg.3
0x756b57  ldsfld   string [mscorlib]System.String::Empty
0x756b5c  stind.ref
0x756b5d  ldarg.s  4
0x756b5f  ldsfld   string [mscorlib]System.String::Empty
0x756b64  stind.ref
0x756b65  ldarg.s  5
0x756b67  ldsfld   string [mscorlib]System.String::Empty
0x756b6c  stind.ref
0x756b6d  ldarg.s  6
0x756b6f  ldsfld   string [mscorlib]System.String::Empty
0x756b74  stind.ref
0x756b75  ldarg.s  7
0x756b77  ldsfld   string [mscorlib]System.String::Empty
0x756b7c  stind.ref
0x756b7d  ldarg.s  8
0x756b7f  ldsfld   string [mscorlib]System.String::Empty
0x756b84  stind.ref
0x756b85  ldarg.s  9
0x756b87  ldsfld   string [mscorlib]System.String::Empty
0x756b8c  stind.ref
0x756b8d  ldarg.s  0xA
0x756b8f  ldsfld   string [mscorlib]System.String::Empty
0x756b94  stind.ref
0x756b95  ldarg.s  0xB
0x756b97  ldc.i4.0
0x756b98  stind.i1
0x756b99  ldarg.s  0xC
0x756b9b  ldc.i4.0
0x756b9c  stind.i1
0x756b9d  ldarg.1
0x756b9e  brtrue.s loc_756BA4
0x756ba0  ldarg.0
0x756ba1  stloc.2
0x756ba2  br.s     loc_756BAB
0x756ba4  ldarg.1
0x756ba5  isinst   Microsoft.SharePoint.SPWeb
0x756baa  stloc.2
0x756bab  ldarg.1
0x756bac  isinst   Microsoft.SharePoint.SPList
0x756bb1  stloc.3
0x756bb2  ldarg.1
0x756bb3  isinst   Microsoft.SharePoint.SPListItem
0x756bb8  stloc.s  4
0x756bba  ldloc.1
0x756bbb  brtrue.s loc_756BD2
0x756bbd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x756bc2  stloc.s  0xC
0x756bc4  ldloca.s 0xC
0x756bc6  ldstr    aN// "N"
0x756bcb  call     instance string [mscorlib]System.Guid::ToString(string)
0x756bd0  br.s     loc_756BD4
0x756bd2  ldarg.s  0xE
0x756bd4  stloc.s  5
0x756bd6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x756bdb  stloc.s  6
0x756bdd  ldloc.s  6
0x756bdf  ldstr    aDirecturlemail// "DirectUrlEmailQS:Guid"
0x756be4  ldloc.s  5
0x756be6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756beb  ldloc.s  6
0x756bed  ldstr    aDirecturlemail_0// "DirectUrlEmailQS:TemplateVersion"
0x756bf2  ldarg.2
0x756bf3  box      Microsoft.SharePoint.SPSharingEmailTemplateVersion
0x756bf8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756bfd  ldloc.s  6
0x756bff  ldstr    aDirecturlemail_1// "DirectUrlEmailQS:ResourceLink"
0x756c04  ldloca.s 0
0x756c06  call     instance string [mscorlib]System.Boolean::ToString()
0x756c0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756c10  ldloc.2
0x756c11  brfalse  loc_756CE0
0x756c16  ldarg.3
0x756c17  ldloc.2
0x756c18  callvirt instance string Microsoft.SharePoint.SPWeb::get_Title()
0x756c1d  stind.ref
0x756c1e  ldarg.s  4
0x756c20  ldloc.2
0x756c21  callvirt instance string Microsoft.SharePoint.SPWeb::get_Title()
0x756c26  stind.ref
0x756c27  ldarg.s  5
0x756c29  ldloc.0
0x756c2a  brtrue.s loc_756C3B
0x756c2c  ldloc.2
0x756c2d  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x756c32  ldc.i4.1
0x756c33  ldc.i4.0
0x756c34  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlPathEncode(string urlToEncode, bool allowHashParameter, bool encodeUnicodeCharacters)
0x756c39  br.s     loc_756C3D
0x756c3b  ldarg.s  0xD
0x756c3d  stind.ref
0x756c3e  ldarg.s  8
0x756c40  ldstr    aSharingdefault_0// "SharingDefaultMessageSite"
0x756c45  stind.ref
0x756c46  ldarg.s  9
0x756c48  ldstr    aSharinglinkdir// "SharingLinkDirect"
0x756c4d  stind.ref
0x756c4e  ldarg.s  0xB
0x756c50  ldc.i4.1
0x756c51  stind.i1
0x756c52  ldloc.2
0x756c53  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsEmailFollowLinkEnabled(class Microsoft.SharePoint.SPWeb web)
0x756c58  brfalse.s loc_756C8A
0x756c5a  ldarg.s  0xA
0x756c5c  ldstr    aSharinglinkfol// "SharingLinkFollowSiteContent"
0x756c61  stind.ref
0x756c62  ldarg.s  6
0x756c64  ldarg.s  5
0x756c66  ldind.ref
0x756c67  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::FollowSiteQuery
0x756c6c  ldstr    a1// "1"
0x756c71  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756c76  stind.ref
0x756c77  ldarg.s  6
0x756c79  ldarg.s  6
0x756c7b  ldind.ref
0x756c7c  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::SiteNameQuery
0x756c81  ldarg.s  4
0x756c83  ldind.ref
0x756c84  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756c89  stind.ref
0x756c8a  ldarg.s  5
0x756c8c  ldarg.s  5
0x756c8e  ldind.ref
0x756c8f  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS
0x756c94  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS_Web
0x756c99  ldstr    asc_C76D2E// ":"
0x756c9e  ldloc.s  5
0x756ca0  call     string [mscorlib]System.String::Concat(string, string, string)
0x756ca5  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756caa  stind.ref
0x756cab  ldloc.s  6
0x756cad  ldstr    aDirecturlemail_2// "DirectUrlEmailQS:Web"
0x756cb2  ldloc.2
0x756cb3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x756cb8  box      [mscorlib]System.Guid
0x756cbd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756cc2  ldc.i4   0x110F849
0x756cc7  ldstr    aDirecturlemail_2// "DirectUrlEmailQS:Web"
0x756ccc  ldnull
0x756ccd  ldloca.s 0xD
0x756ccf  initobj  [mscorlib]System.Guid
0x756cd5  ldloc.s  0xD
0x756cd7  ldloc.s  6
0x756cd9  ldnull
0x756cda  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0x756cdf  ret
0x756ce0  ldloc.3
0x756ce1  brfalse  loc_756DE1
0x756ce6  ldnull
0x756ce7  stloc.s  7
0x756ce9  ldarg.0
0x756cea  ldloc.3
0x756ceb  ldarg.3
0x756cec  ldarg.s  4
0x756cee  ldloca.s 7
0x756cf0  call     void Microsoft.SharePoint.SPAccessRequestsUtility::GetListTitleAndUri(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPList listRequested, [out] string& itemTitle, [out] string& itemDirectLinkText, [out] class [System]System.Uri& directUrl)
0x756cf5  ldarg.s  5
0x756cf7  ldloc.s  7
0x756cf9  ldnull
0x756cfa  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x756cff  brtrue.s loc_756D04
0x756d01  ldnull
0x756d02  br.s     loc_756D0B
0x756d04  ldloc.s  7
0x756d06  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x756d0b  stind.ref
0x756d0c  ldloc.0
0x756d0d  brfalse.s loc_756D14
0x756d0f  ldarg.s  5
0x756d11  ldarg.s  0xD
0x756d13  stind.ref
0x756d14  ldarg.s  9
0x756d16  ldstr    aSharinglinkdir// "SharingLinkDirect"
0x756d1b  stind.ref
0x756d1c  ldloc.3
0x756d1d  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x756d22  ldc.i4.1
0x756d23  bne.un.s loc_756D83
0x756d25  ldarg.s  8
0x756d27  ldstr    aSharingdefault_1// "SharingDefaultMessageDocumentLibrary"
0x756d2c  stind.ref
0x756d2d  ldarg.s  5
0x756d2f  ldarg.s  5
0x756d31  ldind.ref
0x756d32  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS
0x756d37  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS_DocLib
0x756d3c  ldstr    asc_C76D2E// ":"
0x756d41  ldloc.s  5
0x756d43  call     string [mscorlib]System.String::Concat(string, string, string)
0x756d48  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756d4d  stind.ref
0x756d4e  ldloc.s  6
0x756d50  ldstr    aDirecturlemail_3// "DirectUrlEmailQS:DocLib"
0x756d55  ldloc.3
0x756d56  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0x756d5b  box      [mscorlib]System.Guid
0x756d60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756d65  ldc.i4   0x110F84A
0x756d6a  ldstr    aDirecturlemail_3// "DirectUrlEmailQS:DocLib"
0x756d6f  ldnull
0x756d70  ldloca.s 0xE
0x756d72  initobj  [mscorlib]System.Guid
0x756d78  ldloc.s  0xE
0x756d7a  ldloc.s  6
0x756d7c  ldnull
0x756d7d  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0x756d82  ret
0x756d83  ldarg.s  8
0x756d85  ldstr    aSharingdefault_2// "SharingDefaultMessageList"
0x756d8a  stind.ref
0x756d8b  ldarg.s  5
0x756d8d  ldarg.s  5
0x756d8f  ldind.ref
0x756d90  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS
0x756d95  ldsfld   string Microsoft.SharePoint.SPSharingEmailHelper::DirectUrlEmailQS_List
0x756d9a  ldstr    asc_C76D2E// ":"
0x756d9f  ldloc.s  5
0x756da1  call     string [mscorlib]System.String::Concat(string, string, string)
0x756da6  call     string Microsoft.SharePoint.Utilities.SPUtilityInternal::AppendQueryStringParameterToUrl(string strUrl, string key, string value)
0x756dab  stind.ref
0x756dac  ldloc.s  6
0x756dae  ldstr    aDirecturlemail_4// "DirectUrlEmailQS:List"
0x756db3  ldloc.3
0x756db4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0x756db9  box      [mscorlib]System.Guid
0x756dbe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x756dc3  ldc.i4   0x110F84B
0x756dc8  ldstr    aDirecturlemail_4// "DirectUrlEmailQS:List"
0x756dcd  ldnull
0x756dce  ldloca.s 0xF
0x756dd0  initobj  [mscorlib]System.Guid
0x756dd6  ldloc.s  0xF
0x756dd8  ldloc.s  6
0x756dda  ldnull
0x756ddb  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0x756de0  ret
0x756de1  ldloc.s  4
0x756de3  brfalse  loc_7571CA
0x756de8  ldloc.s  4
0x756dea  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x756def  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x756df4  ldc.i4.1
0x756df5  bne.un   loc_757103
0x756dfa  ldnull
0x756dfb  stloc.s  8
0x756dfd  ldnull
0x756dfe  stloc.s  9
0x756e00  ldarg.0
0x756e01  ldloc.s  4
0x756e03  ldarg.3
0x756e04  ldarg.s  4
0x756e06  ldloca.s 8
0x756e08  ldloca.s 9
0x756e0a  ldc.i4.0
0x756e0b  call     void Microsoft.SharePoint.SPAccessRequestsUtility::GetItemTitleAndUri(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPListItem itemRequested, [out] string& itemTitle, [out] string& itemDirectLinkText, [out] class [System]System.Uri& directUrl, [out] class [System]System.Uri& previewUrl, [opt] bool supportListFolders)
0x756e10  ldarg.s  5
0x756e12  ldloc.s  8
0x756e14  ldnull
0x756e15  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x756e1a  brtrue.s loc_756E1F
0x756e1c  ldnull
0x756e1d  br.s     loc_756E26
0x756e1f  ldloc.s  8
0x756e21  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x756e26  stind.ref
0x756e27  ldarg.s  5
0x756e29  ldarg.s  5
0x756e2b  ldind.ref
0x756e2c  ldloc.s  4
0x756e2e  ldc.i4.1
0x756e2f  call     string Microsoft.SharePoint.SPSharingEmailHelper::ConvertUrlFormatIfNecessary(string directUrl, class Microsoft.SharePoint.SPListItem itemRequested, bool encode)
0x756e34  stind.ref
0x756e35  ldarg.s  7
0x756e37  ldloc.s  9
0x756e39  ldnull
0x756e3a  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x756e3f  brtrue.s loc_756E44
0x756e41  ldnull
0x756e42  br.s     loc_756E4B
0x756e44  ldloc.s  9
0x756e46  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x756e4b  stind.ref
0x756e4c  ldloc.0
0x756e4d  brfalse.s loc_756E54
0x756e4f  ldarg.s  5
0x756e51  ldarg.s  0xD
0x756e53  stind.ref
0x756e54  ldloc.s  4
0x756e56  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPListItem::get_Folder()
  ... truncated ...
```
