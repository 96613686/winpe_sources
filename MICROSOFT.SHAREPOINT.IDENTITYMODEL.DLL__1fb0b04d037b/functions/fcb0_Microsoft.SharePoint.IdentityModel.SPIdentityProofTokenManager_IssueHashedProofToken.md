# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueHashedProofToken

- ea: `0xfcb0`
- end: `0xff57`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueHashedProofToken`
- size: `679`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfcb0`
- `0xff60`
- `0x100c0`
- `0x10100`
- `0x102c0`
- `0x283e0`

## string_xrefs

- `0xfdfe`: `SPIdentityProofTokenManager: Incoming context is AppOnly, Issue AppOnly Proof token.`
- `0xfd79`: `SPIdentityProofTokenManager: Proof token with Hash. EndPoint Url: '{0}', Web Url: '{1}', Site Url: {2}`
- `0xfdb6`: `SPIdentityProofTokenManager: Web URL and endpoint does not match`
- `0xfe3e`: `SPIdentityProofTokenManager: ReadOnly proof token request.`
- `0xfe64`: `SPIdentityProofTokenManager: ReadOnly proof token request but appContext is not null.`
- `0xfe6e`: `ReadOnly proof token request but incoming context was not user only.`
- `0xfe95`: `SPIdentityProofTokenManager: Incoming context is App+user, Issue AppPlusOnly Proof token.`
- `0xfeb6`: `SPIdentityProofTokenManager: Issue Hashed Proof Token.`

## pseudocode

```c

```

## disassembly

```asm
0xfcb0  ldnull
0xfcb1  ldarg.0
0xfcb2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xfcb7  brfalse.s loc_FCC4
0xfcb9  ldstr    aEndpoint// "endpoint"
0xfcbe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfcc3  throw
0xfcc4  ldarg.1
0xfcc5  brtrue.s loc_FCD2
0xfcc7  ldstr    aWeb// "web"
0xfccc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfcd1  throw
0xfcd2  ldarg.1
0xfcd3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0xfcd8  brtrue.s loc_FCE5
0xfcda  ldstr    aSite// "Site"
0xfcdf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfce4  throw
0xfce5  ldarg.1
0xfce6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0xfceb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfcf0  brfalse.s loc_FCFD
0xfcf2  ldstr    aWebUrl// "Web Url"
0xfcf7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfcfc  throw
0xfcfd  ldarg.2
0xfcfe  brtrue.s loc_FD0B
0xfd00  ldstr    aIdentitycontex// "identityContext"
0xfd05  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfd0a  throw
0xfd0b  ldarg.s  4
0xfd0d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfd12  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfd17  brfalse.s loc_FD24
0xfd19  ldstr    aExpiryParamete// "Expiry parameter is less than current d"...
0xfd1e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfd23  throw
0xfd24  ldarg.1
0xfd25  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0xfd2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteId()
0xfd2f  stloc.s  0xC
0xfd31  ldloca.s 0xC
0xfd33  constrained. [mscorlib]System.Guid
0xfd39  callvirt instance string [mscorlib]System.Object::ToString()
0xfd3e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::Base64UrlEncode(string)
0xfd43  stloc.0
0xfd44  ldarg.1
0xfd45  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Path()
0xfd4a  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath::ToUri()
0xfd4f  ldc.i4.2
0xfd50  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0xfd55  stloc.1
0xfd56  ldarg.1
0xfd57  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0xfd5c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Path()
0xfd61  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath::ToUri()
0xfd66  ldc.i4.2
0xfd67  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0xfd6c  stloc.2
0xfd6d  ldc.i4   0x148F8D1
0xfd72  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfd77  ldc.i4.s 0x32
0xfd79  ldstr    aSpidentityproo_8// "SPIdentityProofTokenManager: Proof toke"...
0xfd7e  ldc.i4.3
0xfd7f  newarr   [mscorlib]System.Object
0xfd84  stloc.s  0xD
0xfd86  ldloc.s  0xD
0xfd88  ldc.i4.0
0xfd89  ldarg.3
0xfd8a  stelem.ref
0xfd8b  ldloc.s  0xD
0xfd8d  ldc.i4.1
0xfd8e  ldloc.1
0xfd8f  stelem.ref
0xfd90  ldloc.s  0xD
0xfd92  ldc.i4.2
0xfd93  ldloc.2
0xfd94  stelem.ref
0xfd95  ldloc.s  0xD
0xfd97  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xfd9c  ldarg.s  5
0xfd9e  brtrue.s loc_FDCB
0xfda0  ldarg.3
0xfda1  ldloc.1
0xfda2  ldc.i4.3
0xfda3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xfda8  brtrue.s loc_FDCB
0xfdaa  ldc.i4   0x148F8D2
0xfdaf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfdb4  ldc.i4.s 0x32
0xfdb6  ldstr    aSpidentityproo_9// "SPIdentityProofTokenManager: Web URL an"...
0xfdbb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfdc0  ldstr    aWebUrlAndEndpo// "Web URL and endpoint does not match"
0xfdc5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfdca  throw
0xfdcb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_Current()
0xfdd0  stloc.3
0xfdd1  ldc.i4.0
0xfdd2  stloc.s  4
0xfdd4  ldsfld   string [mscorlib]System.String::Empty
0xfdd9  stloc.s  5
0xfddb  ldc.i4   0x2B3D
0xfde0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xfde5  brfalse.s loc_FE13
0xfde7  ldloc.3
0xfde8  brfalse.s loc_FE13
0xfdea  ldloc.3
0xfdeb  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_IsAppOnlyRequest()
0xfdf0  brfalse.s loc_FE13
0xfdf2  ldc.i4   0x164F38D
0xfdf7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfdfc  ldc.i4.s 0x32
0xfdfe  ldstr    aSpidentityproo_4// "SPIdentityProofTokenManager: Incoming c"...
0xfe03  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfe08  ldc.i4.1
0xfe09  stloc.s  4
0xfe0b  ldloc.3
0xfe0c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0xfe11  stloc.s  5
0xfe13  ldc.i4   0x374E
0xfe18  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xfe1d  brfalse  loc_FEAA
0xfe22  ldc.i4   0x3722
0xfe27  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xfe2c  brfalse.s loc_FE7E
0xfe2e  ldarg.s  6
0xfe30  brfalse.s loc_FE7E
0xfe32  ldc.i4   0x21C108B
0xfe37  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfe3c  ldc.i4.s 0x32
0xfe3e  ldstr    aSpidentityproo_10// "SPIdentityProofTokenManager: ReadOnly p"...
0xfe43  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfe48  ldloc.3
0xfe49  brfalse.s loc_FE79
0xfe4b  ldloc.3
0xfe4c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0xfe51  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IsAppAllowedForReadOnlyProofToken(string appid)
0xfe56  brtrue.s loc_FE79
0xfe58  ldc.i4   0x21C108C
0xfe5d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfe62  ldc.i4.s 0xA
0xfe64  ldstr    aSpidentityproo_11// "SPIdentityProofTokenManager: ReadOnly p"...
0xfe69  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfe6e  ldstr    aReadonlyProofT// "ReadOnly proof token request but incomi"...
0xfe73  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfe78  throw
0xfe79  ldc.i4.2
0xfe7a  stloc.s  4
0xfe7c  br.s     loc_FEAA
0xfe7e  ldloc.3
0xfe7f  brfalse.s loc_FEAA
0xfe81  ldloc.3
0xfe82  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_IsAppOnlyRequest()
0xfe87  brtrue.s loc_FEAA
0xfe89  ldc.i4   0x164F38E
0xfe8e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfe93  ldc.i4.s 0x32
0xfe95  ldstr    aSpidentityproo_12// "SPIdentityProofTokenManager: Incoming c"...
0xfe9a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfe9f  ldc.i4.2
0xfea0  stloc.s  4
0xfea2  ldloc.3
0xfea3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0xfea8  stloc.s  5
0xfeaa  ldc.i4   0x234A01D
0xfeaf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfeb4  ldc.i4.s 0x32
0xfeb6  ldstr    aSpidentityproo_13// "SPIdentityProofTokenManager: Issue Hash"...
0xfebb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfec0  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0xfec5  brtrue.s loc_FEED
0xfec7  ldarg.1
0xfec8  ldarg.0
0xfec9  callvirt instance string [mscorlib]System.Object::ToString()
0xfece  ldarg.2
0xfecf  ldarg.3
0xfed0  ldc.i4.3
0xfed1  ldloc.s  4
0xfed3  ldloc.0
0xfed4  ldarg.0
0xfed5  ldloc.s  5
0xfed7  ldarg.s  6
0xfed9  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOutboundClaimsForLoopback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string endPointUrl, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario scenario, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes proofTokenType, string encodedSiteId, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, string appId, [opt] bool readonlyProofToken)
0xfede  ldarg.s  4
0xfee0  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateSignedHashedProofToken(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web, string audience, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, valuetype [mscorlib]System.DateTime expiry)
0xfee5  stloc.s  6
0xfee7  ldloc.s  6
0xfee9  stloc.s  0xB
0xfeeb  leave.s  loc_FF54
0xfeed  ldarg.0
0xfeee  callvirt instance string [mscorlib]System.Object::ToString()
0xfef3  ldarg.2
0xfef4  ldarg.3
0xfef5  ldc.i4.3
0xfef6  ldloc.s  4
0xfef8  ldloc.0
0xfef9  ldarg.0
0xfefa  ldloc.s  5
0xfefc  ldarg.s  6
0xfefe  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOutboundClaimsForLoopback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string endPointUrl, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario scenario, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes proofTokenType, string encodedSiteId, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, string appId, [opt] bool readonlyProofToken)
0xff03  ldarg.s  4
0xff05  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateProofToken(string audience, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, valuetype [mscorlib]System.DateTime expiry)
0xff0a  stloc.s  7
0xff0c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xff11  ldloc.s  7
0xff13  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xff18  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xff1d  stloc.s  8
0xff1f  ldarg.1
0xff20  ldloc.s  8
0xff22  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::HashedProofTokenSeed
0xff27  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GenerateHash(unsigned int8[], valuetype [mscorlib]System.Guid)
0xff2c  stloc.s  9
0xff2e  ldloc.s  7
0xff30  ldloc.s  9
0xff32  call     string [mscorlib]System.String::Concat(string, string)
0xff37  stloc.s  7
0xff39  ldloc.s  7
0xff3b  stloc.s  0xB
0xff3d  leave.s  loc_FF54
0xff3f  stloc.s  0xA
0xff41  ldc.i4   0x234A01E
0xff46  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xff4b  ldloc.s  0xA
0xff4d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, class [mscorlib]System.Exception)
0xff52  rethrow
0xff54  ldloc.s  0xB
0xff56  ret
```
