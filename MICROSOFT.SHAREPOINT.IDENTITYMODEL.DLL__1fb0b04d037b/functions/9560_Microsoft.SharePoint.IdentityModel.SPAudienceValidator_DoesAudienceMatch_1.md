# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch_1

- ea: `0x9560`
- end: `0x965e`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch_1`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9240`

## callees

- `0x9560`
- `0x9660`

## string_xrefs

- `0x95d7`: `The incoming token audience matches the ContextUri.`
- `0x95f7`: `Could not match the token audience against the ContextUri and we do not execute fallback logic in SPO.`
- `0x959f`: `DoesAudienceMatch: This is a shares request with tempauth token. Audience validation will be done against the url in the shares id.`
- `0x963a`: `Failed to match audience URI with the internal URI.  Tring the external URI.`

## pseudocode

```c

```

## disassembly

```asm
0x9560  ldc.i4.0
0x9561  stloc.0
0x9562  ldnull
0x9563  stloc.1
0x9564  ldnull
0x9565  stloc.2
0x9566  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x956b  brfalse.s loc_95BA
0x956d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x9572  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9577  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.FileServiceHelper::IsCurrentRequestVroomCall(class [System.Web]System.Web.HttpRequest)
0x957c  brfalse.s loc_95BA
0x957e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x9583  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9588  ldloca.s 2
0x958a  ldloca.s 1
0x958c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.FileServiceHelper::TryGetTokenFromVroomSharesId(class [System.Web]System.Web.HttpRequest, string&, string&)
0x9591  brfalse.s loc_95BA
0x9593  ldc.i4   0x1758703
0x9598  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x959d  ldc.i4.s 0x32
0x959f  ldstr    aDoesaudiencema// "DoesAudienceMatch: This is a shares req"...
0x95a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x95a9  ldarg.0
0x95aa  ldarg.1
0x95ab  ldarg.2
0x95ac  ldloc.1
0x95ad  newobj   instance void [System]System.Uri::.ctor(string)
0x95b2  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(string audienceUri, string applicationId, string realm, class [System]System.Uri requestUri)
0x95b7  stloc.0
0x95b8  br.s     loc_95C8
0x95ba  ldarg.0
0x95bb  ldarg.1
0x95bc  ldarg.2
0x95bd  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x95c2  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(string audienceUri, string applicationId, string realm, class [System]System.Uri requestUri)
0x95c7  stloc.0
0x95c8  ldloc.0
0x95c9  brfalse.s loc_95E3
0x95cb  ldc.i4   0x1008005
0x95d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x95d5  ldc.i4.s 0x64
0x95d7  ldstr    aTheIncomingTok// "The incoming token audience matches the"...
0x95dc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x95e1  br.s     loc_965C
0x95e3  ldc.i4.1
0x95e4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::GetIsSPO(bool)
0x95e9  brfalse.s loc_9603
0x95eb  ldc.i4   0x1008006
0x95f0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x95f5  ldc.i4.s 0x64
0x95f7  ldstr    aCouldNotMatchT// "Could not match the token audience agai"...
0x95fc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9601  br.s     loc_965C
0x9603  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x9608  brtrue.s loc_962E
0x960a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x960f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9614  brtrue.s loc_962E
0x9616  ldc.i4   0x1008007
0x961b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9620  ldc.i4.s 0x64
0x9622  ldstr    aCurrentRequest// "Current request is missing from the Htt"...
0x9627  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x962c  br.s     loc_965C
0x962e  ldc.i4   0x1008008
0x9633  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9638  ldc.i4.s 0x64
0x963a  ldstr    aFailedToMatchA_0// "Failed to match audience URI with the i"...
0x963f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9644  ldarg.0
0x9645  ldarg.1
0x9646  ldarg.2
0x9647  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x964c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9651  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::GetOriginalUriFromRequest(class [System.Web]System.Web.HttpRequest)
0x9656  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(string audienceUri, string applicationId, string realm, class [System]System.Uri requestUri)
0x965b  stloc.0
0x965c  ldloc.0
0x965d  ret
```
