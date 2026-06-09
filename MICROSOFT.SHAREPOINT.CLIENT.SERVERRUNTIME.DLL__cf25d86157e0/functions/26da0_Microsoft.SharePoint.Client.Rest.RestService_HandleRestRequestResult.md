# Microsoft.SharePoint.Client.Rest.RestService::HandleRestRequestResult

- ea: `0x26da0`
- end: `0x271e4`
- name: `Microsoft.SharePoint.Client.Rest.RestService::HandleRestRequestResult`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x267f0`

## callees

- `0x5120`
- `0xe230`
- `0x21c40`
- `0x21c50`
- `0x21c70`
- `0x21c90`
- `0x21cb0`
- `0x21cd0`
- `0x21d10`
- `0x21d20`
- `0x21d30`
- `0x21d50`
- `0x21d60`
- `0x21d80`
- `0x26da0`
- `0x27750`
- `0x29560`
- `0x29580`
- `0x295a0`
- `0x295c0`
- `0x295e0`
- `0x29600`
- `0x29620`
- `0x29660`
- `0x29680`
- `0x296a0`
- `0x296c0`

## string_xrefs

- `0x2715e`: `DATASERVICEVERSION`
- `0x26faa`: `CARD-UPDATE-IN-BODY`

## pseudocode

```c

```

## disassembly

```asm
0x26da0  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26da5  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26daa  ldarg.2
0x26dab  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_ContentType()
0x26db0  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_ContentType(string)
0x26db5  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26dba  brfalse.s loc_26DF3
0x26dbc  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26dc1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.RESTfulOperationContext::get_StatusCode()
0x26dc6  stloc.1
0x26dc7  ldloca.s 1
0x26dc9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0x26dce  brfalse.s loc_26DF3
0x26dd0  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26dd5  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26dda  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26ddf  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.RESTfulOperationContext::get_StatusCode()
0x26de4  stloc.2
0x26de5  ldloca.s 2
0x26de7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_Value()
0x26dec  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x26df1  br.s     loc_26E21
0x26df3  ldarg.2
0x26df4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.RestRequestResult::get_StatusCode()
0x26df9  stloc.3
0x26dfa  ldloca.s 3
0x26dfc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0x26e01  brfalse.s loc_26E21
0x26e03  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26e08  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26e0d  ldarg.2
0x26e0e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.RestRequestResult::get_StatusCode()
0x26e13  stloc.s  4
0x26e15  ldloca.s 4
0x26e17  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_Value()
0x26e1c  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x26e21  ldarg.2
0x26e22  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_StatusDescriptionOverride()
0x26e27  brfalse.s loc_26E3E
0x26e29  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26e2e  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26e33  ldarg.2
0x26e34  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_StatusDescriptionOverride()
0x26e39  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_StatusDescription(string)
0x26e3e  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26e43  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26e48  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_StatusCode()
0x26e4d  stloc.s  5
0x26e4f  ldloc.s  5
0x26e51  ldc.i4   0xCC
0x26e56  beq.s    loc_26E6C
0x26e58  ldloc.s  5
0x26e5a  ldc.i4   0x130
0x26e5f  beq.s    loc_26E7A
0x26e61  ldloc.s  5
0x26e63  ldc.i4   0x191
0x26e68  beq.s    loc_26E88
0x26e6a  br.s     loc_26E8E
0x26e6c  ldarg.2
0x26e6d  ldc.i4.1
0x26e6e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x26e73  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_SuppressEntityBody(valuetype [mscorlib]System.Nullable`1<bool> value)
0x26e78  br.s     loc_26E8E
0x26e7a  ldarg.2
0x26e7b  ldc.i4.1
0x26e7c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x26e81  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_SuppressEntityBody(valuetype [mscorlib]System.Nullable`1<bool> value)
0x26e86  br.s     loc_26E8E
0x26e88  ldarg.1
0x26e89  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendAccessDeniedHeader()
0x26e8e  ldarg.2
0x26e8f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RestRequestResult::get_SuppressEntityBody()
0x26e94  stloc.s  6
0x26e96  ldloca.s 6
0x26e98  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x26e9d  brfalse.s loc_26EBD
0x26e9f  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26ea4  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26ea9  ldarg.2
0x26eaa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Client.RestRequestResult::get_SuppressEntityBody()
0x26eaf  stloc.s  7
0x26eb1  ldloca.s 7
0x26eb3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x26eb8  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_SuppressEntityBody(bool)
0x26ebd  ldarg.2
0x26ebe  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_ETag()
0x26ec3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26ec8  brtrue.s loc_26EE1
0x26eca  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26ecf  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26ed4  ldarg.2
0x26ed5  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_ETag()
0x26eda  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_ETag(string)
0x26edf  br.s     loc_26F0D
0x26ee1  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26ee6  brfalse.s loc_26F0D
0x26ee8  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26eed  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ETag()
0x26ef2  brfalse.s loc_26F0D
0x26ef4  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26ef9  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26efe  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f03  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ETag()
0x26f08  callvirt instance void [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::set_ETag(string)
0x26f0d  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f12  brfalse.s loc_26F48
0x26f14  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f19  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ContentTag()
0x26f1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26f23  brtrue.s loc_26F48
0x26f25  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26f2a  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26f2f  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x26f34  ldstr    aXSpContenttag// "X-SP-CONTENTTAG"
0x26f39  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f3e  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ContentTag()
0x26f43  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x26f48  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f4d  brfalse.s loc_26F83
0x26f4f  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f54  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_CardActionStatus()
0x26f59  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26f5e  brtrue.s loc_26F83
0x26f60  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26f65  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26f6a  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x26f6f  ldstr    aCardActionStat// "CARD-ACTION-STATUS"
0x26f74  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f79  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_CardActionStatus()
0x26f7e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x26f83  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f88  brfalse.s loc_26FBE
0x26f8a  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26f8f  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_CardUpdateInBody()
0x26f94  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26f99  brtrue.s loc_26FBE
0x26f9b  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26fa0  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26fa5  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x26faa  ldstr    aCardUpdateInBo// "CARD-UPDATE-IN-BODY"
0x26faf  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26fb4  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_CardUpdateInBody()
0x26fb9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x26fbe  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26fc3  brfalse.s loc_27001
0x26fc5  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26fca  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulOperationContext::get_Location()
0x26fcf  ldnull
0x26fd0  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x26fd5  brfalse.s loc_27001
0x26fd7  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x26fdc  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x26fe1  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x26fe6  ldstr    aLocation// "LOCATION"
0x26feb  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x26ff0  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulOperationContext::get_Location()
0x26ff5  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x26ffa  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x26fff  br.s     loc_27033
0x27001  ldarg.2
0x27002  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RestRequestResult::get_Location()
0x27007  ldnull
0x27008  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2700d  brfalse.s loc_27033
0x2700f  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27014  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x27019  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2701e  ldstr    aLocation// "LOCATION"
0x27023  ldarg.2
0x27024  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RestRequestResult::get_Location()
0x27029  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x2702e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x27033  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27038  brfalse.s loc_2706B
0x2703a  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x2703f  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamAcceptRanges()
0x27044  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27049  brtrue.s loc_2706B
0x2704b  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27050  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x27055  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2705a  ldc.i4.s 0x14
0x2705c  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27061  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamAcceptRanges()
0x27066  callvirt instance void [System]System.Net.WebHeaderCollection::set_Item(valuetype [System]System.Net.HttpResponseHeader, string)
0x2706b  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27070  brfalse.s loc_270E6
0x27072  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27077  callvirt instance int64 Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamContentLength()
0x2707c  ldc.i4.0
0x2707d  conv.i8
0x2707e  ble.s    loc_270E6
0x27080  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27085  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x2708a  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2708f  ldc.i4.s 0xB
0x27091  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27096  callvirt instance int64 Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamContentLength()
0x2709b  stloc.s  8
0x2709d  ldloca.s 8
0x2709f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x270a4  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x270a9  callvirt instance void [System]System.Net.WebHeaderCollection::set_Item(valuetype [System]System.Net.HttpResponseHeader, string)
0x270ae  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x270b3  brfalse.s loc_270E6
0x270b5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x270ba  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x270bf  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x270c4  ldstr    aContentLength// "CONTENT-LENGTH"
0x270c9  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x270ce  callvirt instance int64 Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamContentLength()
0x270d3  stloc.s  9
0x270d5  ldloca.s 9
0x270d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x270dc  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x270e1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x270e6  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x270eb  brfalse.s loc_2711E
0x270ed  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x270f2  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamContentRange()
0x270f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x270fc  brtrue.s loc_2711E
0x270fe  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27103  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x27108  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2710d  ldc.i4.s 0x11
0x2710f  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27114  callvirt instance string Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseStreamContentRange()
0x27119  callvirt instance void [System]System.Net.WebHeaderCollection::set_Item(valuetype [System]System.Net.HttpResponseHeader, string)
0x2711e  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x27123  brfalse.s loc_2714F
0x27125  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x2712a  callvirt instance bool Microsoft.SharePoint.Client.RESTfulOperationContext::get_ResponseReturnOriginalStream()
0x2712f  brfalse.s loc_2714F
0x27131  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27136  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x2713b  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x27140  ldstr    aXSpReturnorigi// "X-SP-RETURNORIGINALSTREAM"
0x27145  ldstr    aTrue// "true"
0x2714a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x2714f  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27154  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x27159  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2715e  ldstr    aDataservicever// "DATASERVICEVERSION"
0x27163  ldstr    a30// "3.0"
0x27168  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x2716d  call     class [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.IKillSwitch [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.KillSwitch::get_Instance()
0x27172  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Client.Rest.RestService::AdditionalHeadersKillSwitchId
0x27177  ldstr    a1102018// "1/10/2018"
0x2717c  ldstr    aAdditionalhead// "AdditionalHeadersKillSwitchId"
0x27181  callvirt instance bool [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.IKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x27186  brtrue.s loc_271AA
0x27188  ldarg.2
0x27189  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.RestRequestResult::get_AdditionalHeaders()
0x2718e  brfalse.s loc_271AA
0x27190  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27195  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x2719a  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2719f  ldarg.2
0x271a0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.RestRequestResult::get_AdditionalHeaders()
0x271a5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(class [System]System.Collections.Specialized.NameValueCollection)
0x271aa  ldarg.2
0x271ab  callvirt instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.RestRequestResult::get_StreamBuilder()
0x271b0  brfalse.s loc_271C0
0x271b2  ldarg.2
0x271b3  callvirt instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.RestRequestResult::DetachStreamBuilder()
0x271b8  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.ChunkStreamBuilder::CreateReadonlyStream()
0x271bd  stloc.0
0x271be  br.s     loc_271C7
0x271c0  ldarg.2
0x271c1  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.RestRequestResult::DetachRawStream()
0x271c6  stloc.0
0x271c7  ldarg.0
0x271c8  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x271cd  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x271d2  callvirt instance string [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_ContentType()
0x271d7  ldarg.2
0x271d8  callvirt instance string Microsoft.SharePoint.Client.RestRequestResult::get_ContentDispositionFileNameQuotedString()
0x271dd  call     instance void Microsoft.SharePoint.Client.Rest.RestService::AddDownloadOptionsIfNecessary(string contentType, string contentDispositonFileNameQuotedString)
0x271e2  ldloc.0
0x271e3  ret
```
