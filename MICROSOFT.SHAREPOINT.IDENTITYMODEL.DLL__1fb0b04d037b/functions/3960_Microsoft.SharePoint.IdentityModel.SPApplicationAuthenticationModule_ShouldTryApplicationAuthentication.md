# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldTryApplicationAuthentication

- ea: `0x3960`
- end: `0x3b8f`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ShouldTryApplicationAuthentication`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x3110`

## callees

- `0x3960`
- `0x3b90`
- `0x6970`
- `0x69b0`
- `0x7030`
- `0x7070`
- `0x7120`
- `0x7180`
- `0x2caa0`

## string_xrefs

- `0x3a00`: `Read token from body for doc.aspx`
- `0x3a32`: `SPApplicationAuthenticationModule: Attempting to parse the accesstoken from the post body of wopiembedframe.aspx`
- `0x3ac9`: `SPApplicationAuthenticationModule: Found access token in the post body of wopiembedframe.aspx`
- `0x3b17`: `SPApplicationAuthenticationModule: Found proof token in query string.`

## pseudocode

```c

```

## disassembly

```asm
0x3960  ldarg.1
0x3961  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsClaimsMode(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.WSFederationAuthenticationModule fam)
0x3966  brtrue.s loc_3980
0x3968  ldc.i4   0x244655
0x396d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3972  ldc.i4.s 0x64
0x3974  ldstr    aSpapplicationa_8// "SPApplicationAuthenticationModule: This"...
0x3979  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x397e  ldc.i4.0
0x397f  ret
0x3980  ldarg.0
0x3981  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3986  call     string Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::GetAuthorizationHeader(class [System.Web]System.Web.HttpRequest request)
0x398b  stloc.0
0x398c  ldnull
0x398d  stloc.1
0x398e  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x3993  brfalse  loc_3A4A
0x3998  ldnull
0x3999  stloc.3
0x399a  newobj   instance void <>c__DisplayClass2::.ctor()
0x399f  stloc.s  4
0x39a1  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x39a6  ldloc.s  4
0x39a8  ldflda   class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint <>c__DisplayClass2::ep
0x39ad  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationPreAuthEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x39b2  brfalse  loc_3A4A
0x39b7  ldc.i4.3
0x39b8  newarr   [mscorlib]System.String
0x39bd  stloc.s  8
0x39bf  ldloc.s  8
0x39c1  ldc.i4.0
0x39c2  ldstr    aWopiembedframe// "wopiembedframe.aspx"
0x39c7  stelem.ref
0x39c8  ldloc.s  8
0x39ca  ldc.i4.1
0x39cb  ldstr    aDocAspx// "doc.aspx"
0x39d0  stelem.ref
0x39d1  ldloc.s  8
0x39d3  ldc.i4.2
0x39d4  ldstr    aWopiframeAspx// "WopiFrame.aspx"
0x39d9  stelem.ref
0x39da  ldloc.s  8
0x39dc  stloc.2
0x39dd  ldloc.s  4
0x39df  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint <>c__DisplayClass2::ep
0x39e4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::get_RelativeEndPoint()
0x39e9  ldstr    aWopiembedframe// "wopiembedframe.aspx"
0x39ee  ldc.i4.5
0x39ef  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x39f4  brtrue.s loc_3A26
0x39f6  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ReadTokenFromBodyForDocAspx
0x39fb  ldstr    a03212018// "03/21/2018"
0x3a00  ldstr    aReadTokenFromB// "Read token from body for doc.aspx"
0x3a05  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x3a0a  brtrue.s loc_3A4A
0x3a0c  ldloc.2
0x3a0d  ldloc.3
0x3a0e  brtrue.s loc_3A1E
0x3a10  ldloc.s  4
0x3a12  ldftn    instance bool <>c__DisplayClass2::<ShouldTryApplicationAuthentication>b__0(string x)
0x3a18  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x3a1d  stloc.3
0x3a1e  ldloc.3
0x3a1f  call     T0x2B00000A
0x3a24  brfalse.s loc_3A4A
0x3a26  ldc.i4   0x1001823
0x3a2b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3a30  ldc.i4.s 0x32
0x3a32  ldstr    aSpapplicationa_9// "SPApplicationAuthenticationModule: Atte"...
0x3a37  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3a3c  ldarg.0
0x3a3d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3a42  ldloca.s 1
0x3a44  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseOAuthTokenFromEncodedBody(class [System.Web]System.Web.HttpRequest request, [out] string& accessToken)
0x3a49  pop
0x3a4a  ldloc.0
0x3a4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a50  brtrue.s loc_3AAE
0x3a52  ldloc.1
0x3a53  brtrue.s loc_3AAE
0x3a55  ldc.i4.0
0x3a56  stloc.s  5
0x3a58  ldloc.s  5
0x3a5a  brfalse.s loc_3A8B
0x3a5c  ldc.i4   0x3777
0x3a61  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3a66  brfalse.s loc_3A8B
0x3a68  ldloc.0
0x3a69  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IsBadgerHeader(string)
0x3a6e  brfalse.s loc_3A8B
0x3a70  ldc.i4   0x215150E
0x3a75  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3a7a  ldc.i4.s 0x64
0x3a7c  ldstr    aSpapplicationa_10// "SPApplicationAuthenticationModule: Auth"...
0x3a81  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3a86  br       loc_3B3B
0x3a8b  ldloc.0
0x3a8c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IsOAuthHeader(string)
0x3a91  brtrue   loc_3B3B
0x3a96  ldc.i4   0x244657
0x3a9b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3aa0  ldc.i4.s 0x64
0x3aa2  ldstr    aSpapplicationa_11// "SPApplicationAuthenticationModule: Auth"...
0x3aa7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3aac  ldc.i4.0
0x3aad  ret
0x3aae  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x3ab3  brfalse.s loc_3AD5
0x3ab5  ldloc.1
0x3ab6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3abb  brtrue.s loc_3AD5
0x3abd  ldc.i4   0x1001840
0x3ac2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3ac7  ldc.i4.s 0x32
0x3ac9  ldstr    aSpapplicationa_12// "SPApplicationAuthenticationModule: Foun"...
0x3ace  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3ad3  br.s     loc_3B3B
0x3ad5  ldc.i4   0x2B3E
0x3ada  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3adf  brfalse.s loc_3AF0
0x3ae1  ldarg.0
0x3ae2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3ae7  ldloca.s 1
0x3ae9  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseOAuthTokenFromQueryParam(class [System.Web]System.Web.HttpRequest request, [out] string& accessToken)
0x3aee  brtrue.s loc_3B0B
0x3af0  ldc.i4   0x373
0x3af5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3afa  brfalse.s loc_3B23
0x3afc  ldarg.0
0x3afd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3b02  ldloca.s 1
0x3b04  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseHashedProofTokenFromQueryParam(class [System.Web]System.Web.HttpRequest request, [out] string& proofToken)
0x3b09  brfalse.s loc_3B23
0x3b0b  ldc.i4   0x10D93C2
0x3b10  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3b15  ldc.i4.s 0x64
0x3b17  ldstr    aSpapplicationa_13// "SPApplicationAuthenticationModule: Foun"...
0x3b1c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3b21  br.s     loc_3B3B
0x3b23  ldc.i4   0x244658
0x3b28  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3b2d  ldc.i4.s 0x64
0x3b2f  ldstr    aSpapplicationa_14// "SPApplicationAuthenticationModule: Ther"...
0x3b34  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3b39  ldc.i4.0
0x3b3a  ret
0x3b3b  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x3b40  ldloca.s 6
0x3b42  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x3b47  brtrue.s loc_3B8D
0x3b49  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x3b4e  ldnull
0x3b4f  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x3b54  brtrue.s loc_3B62
0x3b56  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x3b5b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x3b60  br.s     loc_3B63
0x3b62  ldnull
0x3b63  stloc.s  7
0x3b65  ldc.i4   0x10502CA
0x3b6a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3b6f  ldc.i4.s 0x32
0x3b71  ldstr    aSpapplicationa_15// "SPApplicationAuthenticationModule: Endp"...
0x3b76  ldc.i4.1
0x3b77  newarr   [mscorlib]System.Object
0x3b7c  stloc.s  9
0x3b7e  ldloc.s  9
0x3b80  ldc.i4.0
0x3b81  ldloc.s  7
0x3b83  stelem.ref
0x3b84  ldloc.s  9
0x3b86  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3b8b  ldc.i4.0
0x3b8c  ret
0x3b8d  ldc.i4.1
0x3b8e  ret
```
