# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOrIssueIdentityProofToken

- ea: `0x10430`
- end: `0x105b2`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOrIssueIdentityProofToken`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2250`

## callees

- `0xf500`
- `0xf680`
- `0xf6a0`
- `0xf760`
- `0xf780`
- `0xf7a0`
- `0x10430`

## string_xrefs

- `0x10455`: `SPIdentityProofTokenManager: Expire existing proof token.`
- `0x104a8`: `SPIdentityProofTokenManager: Proof Token is not expired. CurrentTime: {0} , Expiration Time: {1}.`
- `0x104fc`: `SPIdentityProofTokenManager: Self-Issued proof token doesn't exist or has expired.`
- `0x10525`: `SPIdentityProofTokenManager: Issued proof token '{0}'.`
- `0x1056b`: `SPIdentityProofTokenManager: Return existing Proof Token. CurrentTime: {0} , Expiration Time: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x10430  ldnull
0x10431  stloc.0
0x10432  call     class Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::get_Local()
0x10437  callvirt instance class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::GetSelfIssued()
0x1043c  stloc.0
0x1043d  ldloc.0
0x1043e  brfalse  loc_104ED
0x10443  ldarg.0
0x10444  brfalse  loc_104ED
0x10449  ldc.i4   0x114701C
0x1044e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10453  ldc.i4.s 0x32
0x10455  ldstr    aSpidentityproo_35// "SPIdentityProofTokenManager: Expire exi"...
0x1045a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1045f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10464  stloc.s  5
0x10466  ldloca.s 5
0x10468  ldc.r8   -1.0
0x10471  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x10476  stloc.1
0x10477  call     class Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::get_Local()
0x1047c  ldloc.0
0x1047d  callvirt instance string Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_ProofTokenString()
0x10482  ldloc.0
0x10483  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_SecurityKey()
0x10488  ldloc.1
0x10489  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::SetSelfIssued(string proofTokenString, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey securityKey, valuetype [mscorlib]System.DateTime expiry)
0x1048e  call     class Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::get_Local()
0x10493  callvirt instance class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::GetSelfIssued()
0x10498  stloc.0
0x10499  ldloc.0
0x1049a  brfalse.s loc_104ED
0x1049c  ldc.i4   0x114701D
0x104a1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x104a6  ldc.i4.s 0x32
0x104a8  ldstr    aSpidentityproo_36// "SPIdentityProofTokenManager: Proof Toke"...
0x104ad  ldc.i4.2
0x104ae  newarr   [mscorlib]System.Object
0x104b3  stloc.s  6
0x104b5  ldloc.s  6
0x104b7  ldc.i4.0
0x104b8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x104bd  stloc.s  7
0x104bf  ldloca.s 7
0x104c1  constrained. [mscorlib]System.DateTime
0x104c7  callvirt instance string [mscorlib]System.Object::ToString()
0x104cc  stelem.ref
0x104cd  ldloc.s  6
0x104cf  ldc.i4.1
0x104d0  ldloc.0
0x104d1  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_Expiry()
0x104d6  stloc.s  8
0x104d8  ldloca.s 8
0x104da  constrained. [mscorlib]System.DateTime
0x104e0  callvirt instance string [mscorlib]System.Object::ToString()
0x104e5  stelem.ref
0x104e6  ldloc.s  6
0x104e8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x104ed  leave.s  loc_1050A
0x104ef  pop
0x104f0  ldc.i4   0x35F7C9
0x104f5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x104fa  ldc.i4.s 0x32
0x104fc  ldstr    aSpidentityproo_37// "SPIdentityProofTokenManager: Self-Issue"...
0x10501  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10506  ldnull
0x10507  stloc.0
0x10508  leave.s  loc_1050A
0x1050a  ldloc.0
0x1050b  brtrue.s loc_1055F
0x1050d  ldnull
0x1050e  ldloca.s 2
0x10510  ldloca.s 3
0x10512  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOAuth2SecurityTokenManager::IssueProofTokenString(class [System]System.Uri, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey&, valuetype [mscorlib]System.DateTime&)
0x10517  stloc.s  4
0x10519  ldc.i4   0x35F7CA
0x1051e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10523  ldc.i4.s 0x32
0x10525  ldstr    aSpidentityproo_38// "SPIdentityProofTokenManager: Issued pro"...
0x1052a  ldc.i4.1
0x1052b  newarr   [mscorlib]System.Object
0x10530  stloc.s  9
0x10532  ldloc.s  9
0x10534  ldc.i4.0
0x10535  ldloc.s  4
0x10537  call     string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHelper::GetSafeForLoggingTokenString(string)
0x1053c  stelem.ref
0x1053d  ldloc.s  9
0x1053f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10544  call     class Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::get_Local()
0x10549  ldloc.s  4
0x1054b  ldloc.2
0x1054c  ldloc.3
0x1054d  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::SetSelfIssued(string proofTokenString, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey securityKey, valuetype [mscorlib]System.DateTime expiry)
0x10552  call     class Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::get_Local()
0x10557  callvirt instance class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenCache::GetSelfIssued()
0x1055c  stloc.0
0x1055d  br.s     loc_105B0
0x1055f  ldc.i4   0x12558A1
0x10564  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10569  ldc.i4.s 0x32
0x1056b  ldstr    aSpidentityproo_39// "SPIdentityProofTokenManager: Return exi"...
0x10570  ldc.i4.2
0x10571  newarr   [mscorlib]System.Object
0x10576  stloc.s  0xA
0x10578  ldloc.s  0xA
0x1057a  ldc.i4.0
0x1057b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10580  stloc.s  0xB
0x10582  ldloca.s 0xB
0x10584  constrained. [mscorlib]System.DateTime
0x1058a  callvirt instance string [mscorlib]System.Object::ToString()
0x1058f  stelem.ref
0x10590  ldloc.s  0xA
0x10592  ldc.i4.1
0x10593  ldloc.0
0x10594  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_Expiry()
0x10599  stloc.s  0xC
0x1059b  ldloca.s 0xC
0x1059d  constrained. [mscorlib]System.DateTime
0x105a3  callvirt instance string [mscorlib]System.Object::ToString()
0x105a8  stelem.ref
0x105a9  ldloc.s  0xA
0x105ab  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x105b0  ldloc.0
0x105b1  ret
```
