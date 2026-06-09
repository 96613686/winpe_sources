# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequestWithWildCard

- ea: `0x9180`
- end: `0x9232`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequestWithWildCard`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8a40`
- `0x161d0`

## callees

- `0x9180`
- `0x96b0`

## string_xrefs

- `0x919e`: `audienceUri`
- `0x9194`: `The audienceUri is null or empty.`
- `0x91d0`: `Matching audience uri, with wildcard, against cached realm. CachedRealm: '{0}'.`
- `0x920e`: `Matching audience uri, with wildcard, against freshly-fetched realm. Realm: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x9180  ldarg.1
0x9181  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9186  brfalse.s loc_91A9
0x9188  ldc.i4   0x7CC186
0x918d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x9192  ldc.i4.s 0xA
0x9194  ldstr    aTheAudienceuri_1// "The audienceUri is null or empty."
0x9199  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x919e  ldstr    aAudienceuri// "audienceUri"
0x91a3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x91a8  throw
0x91a9  ldc.i4.0
0x91aa  stloc.0
0x91ab  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x91b0  stloc.1
0x91b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x91b6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x91bb  ldloca.s 2
0x91bd  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::TryGetAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext, string&)
0x91c2  brfalse.s loc_91EF
0x91c4  ldc.i4   0x2563E2
0x91c9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x91ce  ldc.i4.s 0x64
0x91d0  ldstr    aMatchingAudien_1// "Matching audience uri, with wildcard, a"...
0x91d5  ldc.i4.1
0x91d6  newarr   [mscorlib]System.Object
0x91db  stloc.3
0x91dc  ldloc.3
0x91dd  ldc.i4.0
0x91de  ldloc.2
0x91df  stelem.ref
0x91e0  ldloc.3
0x91e1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x91e6  ldarg.1
0x91e7  ldloc.1
0x91e8  ldloc.2
0x91e9  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatchWithWildCard(string audienceUri, string applicationId, string realm)
0x91ee  stloc.0
0x91ef  ldloc.0
0x91f0  brtrue.s loc_9230
0x91f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::get_Current()
0x91f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_Current()
0x91fc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAuthenticationRealmCache::RefreshAuthenticationRealm(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext)
0x9201  stloc.2
0x9202  ldc.i4   0x2563E3
0x9207  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x920c  ldc.i4.s 0x32
0x920e  ldstr    aMatchingAudien_2// "Matching audience uri, with wildcard, a"...
0x9213  ldc.i4.1
0x9214  newarr   [mscorlib]System.Object
0x9219  stloc.s  4
0x921b  ldloc.s  4
0x921d  ldc.i4.0
0x921e  ldloc.2
0x921f  stelem.ref
0x9220  ldloc.s  4
0x9222  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x9227  ldarg.1
0x9228  ldloc.1
0x9229  ldloc.2
0x922a  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::DoesAudienceMatchWithWildCard(string audienceUri, string applicationId, string realm)
0x922f  stloc.0
0x9230  ldloc.0
0x9231  ret
```
