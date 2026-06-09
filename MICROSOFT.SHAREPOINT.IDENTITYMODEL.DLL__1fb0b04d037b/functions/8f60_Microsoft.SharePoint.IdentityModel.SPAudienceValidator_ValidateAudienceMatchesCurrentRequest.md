# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest

- ea: `0x8f60`
- end: `0x9177`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest`
- size: `535`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a40`
- `0x160b0`

## callees

- `0x69b0`
- `0x8f60`
- `0x9380`
- `0x9460`
- `0x19390`

## string_xrefs

- `0x8f75`: `The audienceUri is null.`
- `0x8f7f`: `audienceUri`
- `0x8fdf`: `AudienceValidator is occuring for an OAuth token on an unallowed endpoint.`
- `0x901c`: `There is no service context to validate the tenant id with.`
- `0x9041`: `SPAudienceValidator: Audience Uri doesn't match Current Request Uri Authority. Token Audience: '{0}'`
- `0x907e`: `Matching audience tenant identifier against cached realm. Realm: '{0}', InputRealm: '{1}'.`
- `0x9149`: `The audience uri matched and so did the tenant. AudienceUri: '{0}', SudienceTenantId: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x8f60  ldnull
0x8f61  ldarg.1
0x8f62  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x8f67  brfalse.s loc_8F8A
0x8f69  ldc.i4   0x7CC185
0x8f6e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8f73  ldc.i4.s 0xA
0x8f75  ldstr    aTheAudienceuri_0// "The audienceUri is null."
0x8f7a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8f7f  ldstr    aAudienceuri// "audienceUri"
0x8f84  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8f89  throw
0x8f8a  ldc.i4.1
0x8f8b  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPGlobal::GetIsSPO(bool)
0x8f90  stloc.1
0x8f91  ldloc.1
0x8f92  brtrue.s loc_8FB6
0x8f94  ldarg.0
0x8f95  ldloca.s 0
0x8f97  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateApplicationEndpointWithFallback([out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x8f9c  brtrue.s loc_8FB6
0x8f9e  ldc.i4   0x10078DE
0x8fa3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8fa8  ldc.i4.s 0x64
0x8faa  ldstr    aThereIsNoAppli// "There is no application identity at the"...
0x8faf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8fb4  ldc.i4.0
0x8fb5  ret
0x8fb6  ldloc.1
0x8fb7  brfalse.s loc_9003
0x8fb9  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x8fbe  ldloca.s 0
0x8fc0  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x8fc5  brtrue.s loc_9003
0x8fc7  ldc.i4   0x373A
0x8fcc  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x8fd1  brfalse.s loc_8FEB
0x8fd3  ldc.i4   0x128B05E
0x8fd8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8fdd  ldc.i4.s 0x32
0x8fdf  ldstr    aAudiencevalida// "AudienceValidator is occuring for an OA"...
0x8fe4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8fe9  br.s     loc_9028
0x8feb  ldc.i4   0x4454D3
0x8ff0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8ff5  ldc.i4.s 0x64
0x8ff7  ldstr    aThereIsNoAppli_0// "There is no application identity at the"...
0x8ffc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9001  ldc.i4.0
0x9002  ret
0x9003  ldnull
0x9004  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x9009  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x900e  brfalse.s loc_9028
0x9010  ldc.i4   0x1211408
0x9015  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x901a  ldc.i4.s 0x32
0x901c  ldstr    aThereIsNoServi// "There is no service context to validate"...
0x9021  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9026  ldc.i4.0
0x9027  ret
0x9028  ldarg.0
0x9029  ldarg.1
0x902a  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatch(class [System]System.Uri audienceUri)
0x902f  stloc.2
0x9030  ldc.i4.0
0x9031  stloc.3
0x9032  ldloc.2
0x9033  brtrue.s loc_905F
0x9035  ldc.i4   0x4454D4
0x903a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x903f  ldc.i4.s 0x32
0x9041  ldstr    aSpaudiencevali// "SPAudienceValidator: Audience Uri doesn"...
0x9046  ldc.i4.1
0x9047  newarr   [mscorlib]System.Object
0x904c  stloc.s  5
0x904e  ldloc.s  5
0x9050  ldc.i4.0
0x9051  ldarg.1
0x9052  stelem.ref
0x9053  ldloc.s  5
0x9055  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x905a  br       loc_9137
0x905f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x9064  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x9069  ldloca.s 4
0x906b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::TryGetAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, string&)
0x9070  brfalse.s loc_90AF
0x9072  ldc.i4   0x4454D5
0x9077  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x907c  ldc.i4.s 0x64
0x907e  ldstr    aMatchingAudien// "Matching audience tenant identifier aga"...
0x9083  ldc.i4.2
0x9084  newarr   [mscorlib]System.Object
0x9089  stloc.s  6
0x908b  ldloc.s  6
0x908d  ldc.i4.0
0x908e  ldloc.s  4
0x9090  stelem.ref
0x9091  ldloc.s  6
0x9093  ldc.i4.1
0x9094  ldarg.2
0x9095  dup
0x9096  brtrue.s loc_909E
0x9098  pop
0x9099  ldsfld   string [mscorlib]System.String::Empty
0x909e  stelem.ref
0x909f  ldloc.s  6
0x90a1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x90a6  ldloc.s  4
0x90a8  ldarg.2
0x90a9  call     bool Microsoft.SharePoint.IdentityModel.SPRealmComparer::Compare(string realm1, string realm2)
0x90ae  stloc.3
0x90af  ldloc.3
0x90b0  brtrue.s loc_9100
0x90b2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x90b7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x90bc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::RefreshAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x90c1  stloc.s  4
0x90c3  ldc.i4   0x4454D6
0x90c8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x90cd  ldc.i4.s 0x32
0x90cf  ldstr    aMatchingAudien_0// "Matching audience tenant identifier aga"...
0x90d4  ldc.i4.2
0x90d5  newarr   [mscorlib]System.Object
0x90da  stloc.s  7
0x90dc  ldloc.s  7
0x90de  ldc.i4.0
0x90df  ldloc.s  4
0x90e1  stelem.ref
0x90e2  ldloc.s  7
0x90e4  ldc.i4.1
0x90e5  ldarg.2
0x90e6  dup
0x90e7  brtrue.s loc_90EF
0x90e9  pop
0x90ea  ldsfld   string [mscorlib]System.String::Empty
0x90ef  stelem.ref
0x90f0  ldloc.s  7
0x90f2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x90f7  ldloc.s  4
0x90f9  ldarg.2
0x90fa  call     bool Microsoft.SharePoint.IdentityModel.SPRealmComparer::Compare(string realm1, string realm2)
0x90ff  stloc.3
0x9100  ldloc.3
0x9101  brtrue.s loc_9137
0x9103  ldc.i4   0x1182257
0x9108  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x910d  ldc.i4.s 0x14
0x910f  ldstr    aTheTenantIdent// "The tenant identifier dit not match. Re"...
0x9114  ldc.i4.2
0x9115  newarr   [mscorlib]System.Object
0x911a  stloc.s  8
0x911c  ldloc.s  8
0x911e  ldc.i4.0
0x911f  ldloc.s  4
0x9121  stelem.ref
0x9122  ldloc.s  8
0x9124  ldc.i4.1
0x9125  ldarg.2
0x9126  dup
0x9127  brtrue.s loc_912F
0x9129  pop
0x912a  ldsfld   string [mscorlib]System.String::Empty
0x912f  stelem.ref
0x9130  ldloc.s  8
0x9132  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9137  ldloc.2
0x9138  brfalse.s loc_9170
0x913a  ldloc.3
0x913b  brfalse.s loc_9170
0x913d  ldc.i4   0x8C5644
0x9142  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9147  ldc.i4.s 0x32
0x9149  ldstr    aTheAudienceUri_3// "The audience uri matched and so did the"...
0x914e  ldc.i4.2
0x914f  newarr   [mscorlib]System.Object
0x9154  stloc.s  9
0x9156  ldloc.s  9
0x9158  ldc.i4.0
0x9159  ldarg.1
0x915a  stelem.ref
0x915b  ldloc.s  9
0x915d  ldc.i4.1
0x915e  ldarg.2
0x915f  dup
0x9160  brtrue.s loc_9168
0x9162  pop
0x9163  ldsfld   string [mscorlib]System.String::Empty
0x9168  stelem.ref
0x9169  ldloc.s  9
0x916b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9170  ldloc.2
0x9171  brfalse.s loc_9175
0x9173  ldloc.3
0x9174  ret
0x9175  ldc.i4.0
0x9176  ret
```
