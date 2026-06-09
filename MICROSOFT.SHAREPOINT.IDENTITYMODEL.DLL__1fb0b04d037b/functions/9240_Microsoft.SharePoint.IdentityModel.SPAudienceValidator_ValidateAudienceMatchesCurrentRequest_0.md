# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest_0

- ea: `0x9240`
- end: `0x9375`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest_0`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a40`
- `0x15ed0`

## callees

- `0x69b0`
- `0x9240`
- `0x9380`
- `0x9560`

## string_xrefs

- `0x925e`: `audienceUri`
- `0x92d9`: `There is no service context to validate the tenant id with.`
- `0x9254`: `The audienceUri is null or empty.`
- `0x9306`: `Matching audience uri against cached realm. CachedRealm: '{0}'.`
- `0x934c`: `Matching audience uri against freshly-fetched realm. Realm: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x9240  ldarg.1
0x9241  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9246  brfalse.s loc_9269
0x9248  ldc.i4   0x7CC187
0x924d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9252  ldc.i4.s 0xA
0x9254  ldstr    aTheAudienceuri_1// "The audienceUri is null or empty."
0x9259  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x925e  ldstr    aAudienceuri// "audienceUri"
0x9263  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9268  throw
0x9269  ldnull
0x926a  stloc.0
0x926b  ldc.i4.1
0x926c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::GetIsSPO(bool)
0x9271  stloc.1
0x9272  ldloc.1
0x9273  brtrue.s loc_9297
0x9275  ldarg.0
0x9276  ldloca.s 0
0x9278  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateApplicationEndpointWithFallback([out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x927d  brtrue.s loc_9297
0x927f  ldc.i4   0x10078DF
0x9284  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9289  ldc.i4.s 0x64
0x928b  ldstr    aThereIsNoAppli// "There is no application identity at the"...
0x9290  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9295  ldc.i4.0
0x9296  ret
0x9297  ldloc.1
0x9298  brfalse.s loc_92C0
0x929a  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x929f  ldloca.s 0
0x92a1  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x92a6  brtrue.s loc_92C0
0x92a8  ldc.i4   0x15D5CE
0x92ad  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x92b2  ldc.i4.s 0x32
0x92b4  ldstr    aThereIsNoAppli// "There is no application identity at the"...
0x92b9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x92be  ldc.i4.0
0x92bf  ret
0x92c0  ldnull
0x92c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x92c6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x92cb  brfalse.s loc_92E5
0x92cd  ldc.i4   0x1211409
0x92d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x92d7  ldc.i4.s 0x32
0x92d9  ldstr    aThereIsNoServi// "There is no service context to validate"...
0x92de  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x92e3  ldc.i4.0
0x92e4  ret
0x92e5  ldc.i4.0
0x92e6  stloc.2
0x92e7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x92ec  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x92f1  ldloca.s 3
0x92f3  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::TryGetAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, string&)
0x92f8  brfalse.s loc_932D
0x92fa  ldc.i4   0x35F7C0
0x92ff  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9304  ldc.i4.s 0x64
0x9306  ldstr    aMatchingAudien_3// "Matching audience uri against cached re"...
0x930b  ldc.i4.1
0x930c  newarr   [mscorlib]System.Object
0x9311  stloc.s  4
0x9313  ldloc.s  4
0x9315  ldc.i4.0
0x9316  ldloc.3
0x9317  stelem.ref
0x9318  ldloc.s  4
0x931a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x931f  ldarg.1
0x9320  ldloc.0
0x9321  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::get_ApplicationId()
0x9326  ldloc.3
0x9327  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(string audienceUri, string applicationId, string realm)
0x932c  stloc.2
0x932d  ldloc.2
0x932e  brtrue.s loc_9373
0x9330  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x9335  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x933a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::RefreshAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x933f  stloc.3
0x9340  ldc.i4   0x35F7C1
0x9345  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x934a  ldc.i4.s 0x32
0x934c  ldstr    aMatchingAudien_4// "Matching audience uri against freshly-f"...
0x9351  ldc.i4.1
0x9352  newarr   [mscorlib]System.Object
0x9357  stloc.s  5
0x9359  ldloc.s  5
0x935b  ldc.i4.0
0x935c  ldloc.3
0x935d  stelem.ref
0x935e  ldloc.s  5
0x9360  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9365  ldarg.1
0x9366  ldloc.0
0x9367  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint::get_ApplicationId()
0x936c  ldloc.3
0x936d  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(string audienceUri, string applicationId, string realm)
0x9372  stloc.2
0x9373  ldloc.2
0x9374  ret
```
