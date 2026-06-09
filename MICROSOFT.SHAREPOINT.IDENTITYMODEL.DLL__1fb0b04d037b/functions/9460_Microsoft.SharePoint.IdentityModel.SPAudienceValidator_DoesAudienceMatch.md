# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch

- ea: `0x9460`
- end: `0x9502`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8f60`

## callees

- `0x9460`
- `0x9510`

## string_xrefs

- `0x947c`: `The incoming token audience matches the ContextUri.`
- `0x949c`: `Could not match the token audience against the ContextUri and we do not execute fallback logic in SPO.`
- `0x94df`: `Failed to match audience URI with the internal URI.  Trying the external URI.`

## pseudocode

```c

```

## disassembly

```asm
0x9460  ldarg.0
0x9461  ldarg.1
0x9462  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x9467  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(class [System]System.Uri audienceUri, class [System]System.Uri requestUri)
0x946c  stloc.0
0x946d  ldloc.0
0x946e  brfalse.s loc_9488
0x9470  ldc.i4   0x1008001
0x9475  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x947a  ldc.i4.s 0x64
0x947c  ldstr    aTheIncomingTok// "The incoming token audience matches the"...
0x9481  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9486  br.s     loc_9500
0x9488  ldc.i4.1
0x9489  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::GetIsSPO(bool)
0x948e  brfalse.s loc_94A8
0x9490  ldc.i4   0x1008002
0x9495  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x949a  ldc.i4.s 0x64
0x949c  ldstr    aCouldNotMatchT// "Could not match the token audience agai"...
0x94a1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x94a6  br.s     loc_9500
0x94a8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x94ad  brtrue.s loc_94D3
0x94af  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x94b4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x94b9  brtrue.s loc_94D3
0x94bb  ldc.i4   0x1008003
0x94c0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x94c5  ldc.i4.s 0x64
0x94c7  ldstr    aCurrentRequest// "Current request is missing from the Htt"...
0x94cc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x94d1  br.s     loc_9500
0x94d3  ldc.i4   0x1008004
0x94d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x94dd  ldc.i4.s 0x64
0x94df  ldstr    aFailedToMatchA// "Failed to match audience URI with the i"...
0x94e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x94e9  ldarg.0
0x94ea  ldarg.1
0x94eb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x94f0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x94f5  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::GetOriginalUriFromRequest(class [System.Web]System.Web.HttpRequest)
0x94fa  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(class [System]System.Uri audienceUri, class [System]System.Uri requestUri)
0x94ff  stloc.0
0x9500  ldloc.0
0x9501  ret
```
