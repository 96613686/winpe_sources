# Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateAudience

- ea: `0x8740`
- end: `0x87fd`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateAudience`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x86d0`
- `0x10ad0`

## callees

- `0x86a0`
- `0x8740`
- `0x8830`
- `0x89f0`

## string_xrefs

- `0x874f`: `The identityProofToken is null.`
- `0x8759`: `identityProofToken`
- `0x879c`: `The identityProofToken is failing audience validation for the proof token.`
- `0x87e5`: `The identityProofToken is failing audience validation for the identity token.`

## pseudocode

```c

```

## disassembly

```asm
0x8740  ldarg.1
0x8741  brtrue.s loc_8764
0x8743  ldc.i4   0x7CC162
0x8748  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::get_Category()
0x874d  ldc.i4.s 0xA
0x874f  ldstr    aTheIdentitypro// "The identityProofToken is null."
0x8754  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8759  ldstr    aIdentityprooft// "identityProofToken"
0x875e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8763  throw
0x8764  ldc.i4.4
0x8765  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x876a  stloc.0
0x876b  ldarg.1
0x876c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_ProofToken()
0x8771  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x8776  stloc.1
0x8777  ldloc.1
0x8778  brfalse.s loc_87B2
0x877a  ldloc.1
0x877b  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x8780  ldc.i4.2
0x8781  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x8786  stloc.2
0x8787  ldloc.0
0x8788  ldloc.2
0x8789  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudience(class [System]System.Uri audienceUri)
0x878e  brtrue.s loc_87B2
0x8790  ldc.i4   0x7CC163
0x8795  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::get_Category()
0x879a  ldc.i4.s 0x32
0x879c  ldstr    aTheIdentitypro_0// "The identityProofToken is failing audie"...
0x87a1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x87a6  ldloc.2
0x87a7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor()
0x87ac  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x87b1  throw
0x87b2  ldarg.1
0x87b3  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::get_IdentityToken()
0x87b8  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x87bd  stloc.3
0x87be  ldloc.3
0x87bf  brfalse.s loc_87FC
0x87c1  ldloc.3
0x87c2  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x87c7  ldc.i4.2
0x87c8  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x87cd  stloc.s  4
0x87cf  ldloc.0
0x87d0  ldloc.s  4
0x87d2  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudience(class [System]System.Uri audienceUri)
0x87d7  brtrue.s loc_87FC
0x87d9  ldc.i4   0x7CC180
0x87de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::get_Category()
0x87e3  ldc.i4.s 0x32
0x87e5  ldstr    aTheIdentitypro_1// "The identityProofToken is failing audie"...
0x87ea  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x87ef  ldloc.s  4
0x87f1  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor()
0x87f6  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x87fb  throw
0x87fc  ret
```
