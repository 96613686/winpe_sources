# Microsoft.SharePoint.IdentityModel.SPClaimsUtility::VerifyProofTokenEndPointUrl_0

- ea: `0x28530`
- end: `0x288de`
- name: `Microsoft.SharePoint.IdentityModel.SPClaimsUtility::VerifyProofTokenEndPointUrl_0`
- size: `942`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x16a10`
- `0x284f0`

## callees

- `0x10220`
- `0x283e0`
- `0x28530`
- `0x288e0`
- `0x28920`

## string_xrefs

- `0x28647`: `InvalidAccessTokenOnEndPoint`
- `0x288ac`: `InvalidAccessTokenOnEndPoint`
- `0x2866e`: `[SPClaimsUtility] Failed to parse site id claim in the hashed proof token. Value: '{0}'.`
- `0x286ff`: `VerifyProofTokenEndPointUrl: Its a vroom shares request. Will verify endpoint url against the shares id.`
- `0x287d3`: `Allow partial URL validation for proof token.`
- `0x28879`: `SPApplicationAuthenticationModule: Request URL '{0}' does not match with issued token url '{1}'.`
- `0x288d3`: `SPApplicationAuthenticationModule: Endpoint URL claim is null in Identity Token.`

## pseudocode

```c

```

## disassembly

```asm
0x28530  ldarg.0
0x28531  ldstr    aEndpointurl// "endpointurl"
0x28536  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x2853b  stloc.0
0x2853c  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x28541  brtrue   loc_286AE
0x28546  ldarg.0
0x28547  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::SiteIdClaimType
0x2854c  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x28551  stloc.2
0x28552  ldloc.2
0x28553  brfalse  loc_2868C
0x28558  ldloc.2
0x28559  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x2855e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x28563  brtrue   loc_2868C
0x28568  ldloc.2
0x28569  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x2856e  ldloca.s 1
0x28570  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x28575  stloc.3
0x28576  ldloc.3
0x28577  brtrue.s loc_28590
0x28579  ldloc.2
0x2857a  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x2857f  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::Base64UrlDecode(string)
0x28584  stloc.s  4
0x28586  ldloc.s  4
0x28588  ldloca.s 1
0x2858a  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2858f  stloc.3
0x28590  ldloc.3
0x28591  brfalse  loc_28662
0x28596  ldloc.1
0x28597  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2859c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x285a1  brfalse  loc_28662
0x285a6  ldnull
0x285a7  stloc.s  5
0x285a9  ldnull
0x285aa  stloc.s  6
0x285ac  ldnull
0x285ad  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x285b2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x285b7  brfalse.s loc_285C5
0x285b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x285be  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_SiteSubscriptionId()
0x285c3  stloc.s  6
0x285c5  ldnull
0x285c6  ldloc.s  6
0x285c8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier)
0x285cd  brfalse.s loc_285DC
0x285cf  ldloc.1
0x285d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x285d5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteLookupInfo [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteCache::LookupById(valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm)
0x285da  stloc.s  5
0x285dc  ldloc.s  6
0x285de  ldnull
0x285df  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier)
0x285e4  brfalse  loc_2868C
0x285e9  ldloc.s  5
0x285eb  brfalse  loc_2868C
0x285f0  ldloc.s  5
0x285f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ISPSiteLookupInfo::get_SiteSubscriptionId()
0x285f7  ldloc.s  6
0x285f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier::get_Id()
0x285fe  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28603  brfalse  loc_2868C
0x28608  ldc.i4   0x2021D1DF
0x2860d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28612  ldc.i4.s 0xA
0x28614  ldstr    aSpclaimsutilit// "[SPClaimsUtility] Site id does not matc"...
0x28619  ldc.i4.2
0x2861a  newarr   [mscorlib]System.Object
0x2861f  stloc.s  0x10
0x28621  ldloc.s  0x10
0x28623  ldc.i4.0
0x28624  ldloc.1
0x28625  box      [mscorlib]System.Guid
0x2862a  stelem.ref
0x2862b  ldloc.s  0x10
0x2862d  ldc.i4.1
0x2862e  ldloc.s  6
0x28630  stelem.ref
0x28631  ldloc.s  0x10
0x28633  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28638  ldstr    aInvalidRequest// "invalid_request"
0x2863d  ldc.i4   0x2DC6C1
0x28642  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x28647  ldstr    aInvalidaccesst// "InvalidAccessTokenOnEndPoint"
0x2864c  ldc.i4.0
0x2864d  newarr   [mscorlib]System.Object
0x28652  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x28657  ldc.i4   0x191
0x2865c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x28661  throw
0x28662  ldc.i4   0x2021D1E0
0x28667  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x2866c  ldc.i4.s 0xA
0x2866e  ldstr    aSpclaimsutilit_0// "[SPClaimsUtility] Failed to parse site "...
0x28673  ldc.i4.1
0x28674  newarr   [mscorlib]System.Object
0x28679  stloc.s  0x11
0x2867b  ldloc.s  0x11
0x2867d  ldc.i4.0
0x2867e  ldloc.2
0x2867f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x28684  stelem.ref
0x28685  ldloc.s  0x11
0x28687  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2868c  leave.s  loc_286AE
0x2868e  stloc.s  7
0x28690  ldc.i4   0x2021D1E1
0x28695  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2869a  ldloc.s  7
0x2869c  ldstr    aSpclaimsutilit_1// "[SPClaimsUtility] Failed to validate si"...
0x286a1  ldc.i4.0
0x286a2  newarr   [mscorlib]System.Object
0x286a7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x286ac  rethrow
0x286ae  ldloc.0
0x286af  brfalse  loc_288C7
0x286b4  ldnull
0x286b5  stloc.s  8
0x286b7  ldnull
0x286b8  stloc.s  9
0x286ba  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x286bf  brfalse.s loc_2870E
0x286c1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x286c6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x286cb  brfalse.s loc_2870E
0x286cd  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x286d2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x286d7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.FileServiceHelper::IsCurrentRequestVroomCall(class [System.Web]System.Web.HttpRequest)
0x286dc  brfalse.s loc_2870E
0x286de  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x286e3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x286e8  ldloca.s 8
0x286ea  ldloca.s 9
0x286ec  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.FileServiceHelper::TryGetTokenFromVroomSharesId(class [System.Web]System.Web.HttpRequest, string&, string&)
0x286f1  brfalse.s loc_2870E
0x286f3  ldc.i4   0x1758704
0x286f8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x286fd  ldc.i4.s 0x32
0x286ff  ldstr    aVerifyprooftok// "VerifyProofTokenEndPointUrl: Its a vroo"...
0x28704  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x28709  br       loc_287C0
0x2870e  ldstr    asc_336C0// ""
0x28713  stloc.s  0xA
0x28715  ldnull
0x28716  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x2871b  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x28720  brfalse.s loc_2872E
0x28722  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x28727  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x2872c  stloc.s  0xA
0x2872e  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x28733  brtrue.s loc_28768
0x28735  ldloc.s  0xA
0x28737  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2873c  brfalse.s loc_28768
0x2873e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x28743  brfalse.s loc_28768
0x28745  ldnull
0x28746  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x2874b  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Uri()
0x28750  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x28755  brfalse.s loc_28768
0x28757  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x2875c  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Uri()
0x28761  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x28766  stloc.s  0xA
0x28768  ldloc.s  0xA
0x2876a  call     string Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetEndpointUrl(string url)
0x2876f  stloc.s  0xB
0x28771  ldloc.s  0xB
0x28773  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28778  brfalse.s loc_28785
0x2877a  ldstr    aEndpointurl_1// "endPointurl"
0x2877f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28784  throw
0x28785  ldloc.s  0xB
0x28787  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x2878c  stloc.s  9
0x2878e  ldc.i4   0x114701E
0x28793  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28798  ldc.i4.s 0x32
0x2879a  ldstr    aSpapplicationa_112// "SPApplicationAuthenticationModule: Requ"...
0x2879f  ldc.i4.3
0x287a0  newarr   [mscorlib]System.Object
0x287a5  stloc.s  0x12
0x287a7  ldloc.s  0x12
0x287a9  ldc.i4.0
0x287aa  ldloc.s  0xA
0x287ac  stelem.ref
0x287ad  ldloc.s  0x12
0x287af  ldc.i4.1
0x287b0  ldloc.s  0xB
0x287b2  stelem.ref
0x287b3  ldloc.s  0x12
0x287b5  ldc.i4.2
0x287b6  ldloc.s  9
0x287b8  stelem.ref
0x287b9  ldloc.s  0x12
0x287bb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x287c0  ldloca.s 0xC
0x287c2  ldstr    a8ad6367e5fd944// "8ad6367e-5fd9-4423-b43b-8dac85f2f3b5"
0x287c7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x287cc  ldloc.s  0xC
0x287ce  ldstr    a4132016// "4/13/2016"
0x287d3  ldstr    aAllowPartialUr// "Allow partial URL validation for proof "...
0x287d8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x287dd  brtrue.s loc_28854
0x287df  ldarg.0
0x287e0  ldstr    aEndpointurllen// "endpointurlLength"
0x287e5  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x287ea  stloc.s  0xD
0x287ec  ldloc.s  0xD
0x287ee  brtrue.s loc_28808
0x287f0  ldc.i4   0x11C779E
0x287f5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x287fa  ldc.i4.s 0xA
0x287fc  ldstr    aSpapplicationa_113// "SPApplicationAuthenticationModule: endp"...
0x28801  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x28806  br.s     loc_28854
0x28808  ldloc.s  0xD
0x2880a  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x2880f  call     int32 [mscorlib]System.Int32::Parse(string)
0x28814  stloc.s  0xE
0x28816  ldloc.s  0xE
0x28818  ldc.i4.0
0x28819  bgt.s    loc_28848
0x2881b  ldc.i4   0x11C779F
0x28820  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28825  ldc.i4.s 0xA
0x28827  ldstr    aSpapplicationa_114// "SPApplicationAuthenticationModule: URL "...
0x2882c  ldc.i4.1
0x2882d  newarr   [mscorlib]System.Object
0x28832  stloc.s  0x13
0x28834  ldloc.s  0x13
0x28836  ldc.i4.0
0x28837  ldloc.s  0xE
0x28839  box      [mscorlib]System.Int32
0x2883e  stelem.ref
0x2883f  ldloc.s  0x13
0x28841  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28846  br.s     loc_28854
0x28848  ldloc.s  9
0x2884a  ldc.i4.0
0x2884b  ldloc.s  0xE
0x2884d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x28852  stloc.s  9
0x28854  ldloc.s  9
0x28856  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetHashValue(string endpointUrl)
0x2885b  stloc.s  0xF
0x2885d  ldloc.s  0xF
0x2885f  ldloc.0
0x28860  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x28865  ldc.i4.5
0x28866  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2886b  brtrue.s loc_288DD
0x2886d  ldc.i4   0x10D93CE
0x28872  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28877  ldc.i4.s 0xA
0x28879  ldstr    aSpapplicationa_115// "SPApplicationAuthenticationModule: Requ"...
0x2887e  ldc.i4.2
0x2887f  newarr   [mscorlib]System.Object
0x28884  stloc.s  0x14
0x28886  ldloc.s  0x14
0x28888  ldc.i4.0
0x28889  ldloc.s  0xF
0x2888b  stelem.ref
0x2888c  ldloc.s  0x14
0x2888e  ldc.i4.1
0x2888f  ldloc.0
0x28890  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x28895  stelem.ref
0x28896  ldloc.s  0x14
0x28898  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2889d  ldstr    aInvalidRequest// "invalid_request"
0x288a2  ldc.i4   0x2DC6C1
0x288a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x288ac  ldstr    aInvalidaccesst// "InvalidAccessTokenOnEndPoint"
0x288b1  ldc.i4.0
0x288b2  newarr   [mscorlib]System.Object
0x288b7  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x288bc  ldc.i4   0x191
0x288c1  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x288c6  throw
0x288c7  ldc.i4   0x10D93CF
0x288cc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x288d1  ldc.i4.s 0xA
0x288d3  ldstr    aSpapplicationa_116// "SPApplicationAuthenticationModule: Endp"...
0x288d8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x288dd  ret
```
