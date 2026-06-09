# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidatePostAugmentation

- ea: `0x1ef60`
- end: `0x1f167`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidatePostAugmentation`
- size: `519`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e400`
- `0x1e700`

## callees

- `0x199c0`
- `0x199e0`
- `0x19cc0`
- `0x1ef60`
- `0x1f170`
- `0x2c520`

## string_xrefs

- `0x1f140`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x1ef86`: `Validating the requestor based on the token after augmentation.`
- `0x1efb1`: `No token AVF in output claims identity.`
- `0x1efe9`: `Forms user token rebuild. Comparing new token AVF with incoming cookie AVF. Token AVF: '{0}' Cookie AVF: '{1}'.`
- `0x1f0a0`: `Comparing new token AVF with incoming token valid from value. Token AVF: '{0}' IncomingTokenTime: '{1}' Operation: '{2}'.`
- `0x1f15c`: `Post augmentation validation success! Proceeding with token generation.`

## pseudocode

```c

```

## disassembly

```asm
0x1ef60  ldc.i4   0x7A0510
0x1ef65  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1ef6a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ef6f  ldstr    aRequestinfo// "requestInfo"
0x1ef74  ldarg.1
0x1ef75  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1ef7a  ldc.i4   0x1451754
0x1ef7f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ef84  ldc.i4.s 0x32
0x1ef86  ldstr    aValidatingTheR// "Validating the requestor based on the t"...
0x1ef8b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1ef90  ldc.i4.0
0x1ef91  stloc.0
0x1ef92  ldloca.s 1
0x1ef94  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1ef9a  ldarg.0
0x1ef9b  ldarg.2
0x1ef9c  ldloca.s 1
0x1ef9e  call     instance bool Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::TryGetTokenAvfFromOutputClaims(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity, [out] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>& tokenAvfUtc)
0x1efa3  brtrue.s loc_1EFC0
0x1efa5  ldc.i4   0x7A0511
0x1efaa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1efaf  ldc.i4.s 0x32
0x1efb1  ldstr    aNoTokenAvfInOu// "No token AVF in output claims identity."
0x1efb6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1efbb  br       loc_1F13D
0x1efc0  ldarg.1
0x1efc1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_OperationType()
0x1efc6  stloc.3
0x1efc7  ldloca.s 3
0x1efc9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::GetValueOrDefault()
0x1efce  ldc.i4.1
0x1efcf  bne.un.s loc_1EFDA
0x1efd1  ldloca.s 3
0x1efd3  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::get_HasValue()
0x1efd8  br.s     loc_1EFDB
0x1efda  ldc.i4.0
0x1efdb  brfalse.s loc_1F04F
0x1efdd  ldc.i4   0x5DF353
0x1efe2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1efe7  ldc.i4.s 0x32
0x1efe9  ldstr    aFormsUserToken// "Forms user token rebuild. Comparing new"...
0x1efee  ldc.i4.2
0x1efef  newarr   [mscorlib]System.Object
0x1eff4  stloc.s  4
0x1eff6  ldloc.s  4
0x1eff8  ldc.i4.0
0x1eff9  ldloc.1
0x1effa  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1efff  stelem.ref
0x1f000  ldloc.s  4
0x1f002  ldc.i4.1
0x1f003  ldarg.1
0x1f004  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_AuthenticationValidFromTimeUtc()
0x1f009  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1f00e  stelem.ref
0x1f00f  ldloc.s  4
0x1f011  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f016  ldarg.1
0x1f017  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_AuthenticationValidFromTimeUtc()
0x1f01c  stloc.s  5
0x1f01e  ldloca.s 5
0x1f020  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1f025  brfalse.s loc_1F048
0x1f027  ldarg.1
0x1f028  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_AuthenticationValidFromTimeUtc()
0x1f02d  stloc.s  6
0x1f02f  ldloca.s 6
0x1f031  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1f036  ldloca.s 1
0x1f038  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1f03d  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1f042  stloc.0
0x1f043  br       loc_1F13D
0x1f048  ldc.i4.1
0x1f049  stloc.0
0x1f04a  br       loc_1F13D
0x1f04f  ldarg.1
0x1f050  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_OperationType()
0x1f055  stloc.s  7
0x1f057  ldloca.s 7
0x1f059  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::GetValueOrDefault()
0x1f05e  brtrue.s loc_1F069
0x1f060  ldloca.s 7
0x1f062  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::get_HasValue()
0x1f067  br.s     loc_1F06A
0x1f069  ldc.i4.0
0x1f06a  brtrue.s loc_1F08D
0x1f06c  ldarg.1
0x1f06d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_OperationType()
0x1f072  stloc.s  8
0x1f074  ldloca.s 8
0x1f076  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::GetValueOrDefault()
0x1f07b  ldc.i4.2
0x1f07c  bne.un.s loc_1F087
0x1f07e  ldloca.s 8
0x1f080  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>::get_HasValue()
0x1f085  br.s     loc_1F088
0x1f087  ldc.i4.0
0x1f088  brfalse  loc_1F10E
0x1f08d  ldarg.1
0x1f08e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionRevocationTokenValidFromTime()
0x1f093  stloc.2
0x1f094  ldc.i4   0x1405348
0x1f099  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f09e  ldc.i4.s 0x32
0x1f0a0  ldstr    aComparingNewTo// "Comparing new token AVF with incoming t"...
0x1f0a5  ldc.i4.3
0x1f0a6  newarr   [mscorlib]System.Object
0x1f0ab  stloc.s  9
0x1f0ad  ldloc.s  9
0x1f0af  ldc.i4.0
0x1f0b0  ldloc.1
0x1f0b1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x1f0b6  stelem.ref
0x1f0b7  ldloc.s  9
0x1f0b9  ldc.i4.1
0x1f0ba  ldloc.2
0x1f0bb  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetDateTimeString(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x1f0c0  stelem.ref
0x1f0c1  ldloc.s  9
0x1f0c3  ldc.i4.2
0x1f0c4  ldarg.1
0x1f0c5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_OperationType()
0x1f0ca  box      valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>
0x1f0cf  stelem.ref
0x1f0d0  ldloc.s  9
0x1f0d2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f0d7  ldarg.1
0x1f0d8  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SessionRevocationTokenValidFromTime()
0x1f0dd  stloc.s  0xA
0x1f0df  ldloca.s 0xA
0x1f0e1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1f0e6  brfalse.s loc_1F0FE
0x1f0e8  ldloca.s 2
0x1f0ea  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1f0ef  ldloca.s 1
0x1f0f1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1f0f6  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1f0fb  stloc.0
0x1f0fc  br.s     loc_1F13D
0x1f0fe  ldc.i4   0x29ED
0x1f103  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1f108  brfalse.s loc_1F13D
0x1f10a  ldc.i4.1
0x1f10b  stloc.0
0x1f10c  br.s     loc_1F13D
0x1f10e  ldc.i4   0x7588C8
0x1f113  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f118  ldc.i4.s 0x32
0x1f11a  ldstr    aOperationDoesN// "Operation does not require a check for "...
0x1f11f  ldc.i4.1
0x1f120  newarr   [mscorlib]System.Object
0x1f125  stloc.s  0xB
0x1f127  ldloc.s  0xB
0x1f129  ldc.i4.0
0x1f12a  ldarg.1
0x1f12b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType> Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_OperationType()
0x1f130  box      valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceOperationType>
0x1f135  stelem.ref
0x1f136  ldloc.s  0xB
0x1f138  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f13d  ldloc.0
0x1f13e  brfalse.s loc_1F150
0x1f140  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x1f145  ldstr    aSessionrevoked// "SessionRevokedByIdentityProvider"
0x1f14a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::ThrowTokenIssuanceFailureException(string, string)
0x1f14f  ret
0x1f150  ldc.i4   0x5DF354
0x1f155  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f15a  ldc.i4.s 0x32
0x1f15c  ldstr    aPostAugmentati// "Post augmentation validation success! P"...
0x1f161  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f166  ret
```
