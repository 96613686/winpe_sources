# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateSingleAudienceCondition

- ea: `0x8c40`
- end: `0x8e62`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateSingleAudienceCondition`
- size: `546`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8b70`
- `0x22130`

## callees

- `0x8c40`
- `0x8e70`

## string_xrefs

- `0x8c55`: `The audienceUri is null.`
- `0x8c5f`: `audienceUri`
- `0x8ca2`: `The audience uri loads a web application matches. AudienceUri: '{0}', InputWebApplicationId: '{1}', InputUrlZone: '{2}'.`
- `0x8d2a`: `The audience uri matches a trusted login provider default provider realm. AudienceUri: '{0}', InputWebApplicationId: '{1}', InputUrlZone: '{2}', LoginProviderName: '{3}'.`
- `0x8dae`: `The audience uri matches a trusted login provider provider realm. AudienceUri: '{0}', InputWebApplicationId: '{1}', InputUrlZone: '{2}', LoginProviderName: '{3}'.`
- `0x8e2c`: `The audience uri did not match a web application or trusted provider. AudienceUri: '{0}', InputWebApplicationId: '{1}', InputUrlZone: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x8c40  ldnull
0x8c41  ldarg.0
0x8c42  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x8c47  brfalse.s loc_8C6A
0x8c49  ldc.i4   0x7CC184
0x8c4e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8c53  ldc.i4.s 0xA
0x8c55  ldstr    aTheAudienceuri_0// "The audienceUri is null."
0x8c5a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8c5f  ldstr    aAudienceuri// "audienceUri"
0x8c64  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c69  throw
0x8c6a  ldc.i4.0
0x8c6b  stloc.0
0x8c6c  ldarg.0
0x8c6d  ldloca.s 1
0x8c6f  ldloca.s 2
0x8c71  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::RetrieveWebApplicationIdAndZoneFromUri(class [System]System.Uri context, [out] valuetype [mscorlib]System.Guid& webAppId, [out] valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone& zone)
0x8c76  stloc.3
0x8c77  ldloc.3
0x8c78  brfalse.s loc_8CDB
0x8c7a  ldloc.1
0x8c7b  ldarg.1
0x8c7c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8c81  brfalse.s loc_8CDB
0x8c83  ldloc.2
0x8c84  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8c89  ldarg.2
0x8c8a  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8c8f  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x8c94  brfalse.s loc_8CDB
0x8c96  ldc.i4   0x8C5621
0x8c9b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8ca0  ldc.i4.s 0x64
0x8ca2  ldstr    aTheAudienceUri// "The audience uri loads a web applicatio"...
0x8ca7  ldc.i4.3
0x8ca8  newarr   [mscorlib]System.Object
0x8cad  stloc.s  7
0x8caf  ldloc.s  7
0x8cb1  ldc.i4.0
0x8cb2  ldarg.0
0x8cb3  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8cb8  stelem.ref
0x8cb9  ldloc.s  7
0x8cbb  ldc.i4.1
0x8cbc  ldarg.1
0x8cbd  box      [mscorlib]System.Guid
0x8cc2  stelem.ref
0x8cc3  ldloc.s  7
0x8cc5  ldc.i4.2
0x8cc6  ldarg.2
0x8cc7  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8ccc  stelem.ref
0x8ccd  ldloc.s  7
0x8ccf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8cd4  ldc.i4.1
0x8cd5  stloc.0
0x8cd6  br       loc_8E60
0x8cdb  ldarg.3
0x8cdc  brfalse  loc_8E20
0x8ce1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x8ce6  stloc.s  4
0x8ce8  ldarg.3
0x8ce9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x8cee  stloc.s  8
0x8cf0  br       loc_8E06
0x8cf5  ldloc.s  8
0x8cf7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x8cfc  stloc.s  5
0x8cfe  ldloc.s  4
0x8d00  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProviderCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedLoginProviders()
0x8d05  ldloc.s  5
0x8d07  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider>::get_Item(!!T0)
0x8d0c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider::get_DefaultProviderRealm()
0x8d11  ldarg.0
0x8d12  callvirt instance string [mscorlib]System.Object::ToString()
0x8d17  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8d1c  brfalse.s loc_8D69
0x8d1e  ldc.i4   0x8C5622
0x8d23  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8d28  ldc.i4.s 0x32
0x8d2a  ldstr    aTheAudienceUri_0// "The audience uri matches a trusted logi"...
0x8d2f  ldc.i4.4
0x8d30  newarr   [mscorlib]System.Object
0x8d35  stloc.s  9
0x8d37  ldloc.s  9
0x8d39  ldc.i4.0
0x8d3a  ldarg.0
0x8d3b  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8d40  stelem.ref
0x8d41  ldloc.s  9
0x8d43  ldc.i4.1
0x8d44  ldarg.1
0x8d45  box      [mscorlib]System.Guid
0x8d4a  stelem.ref
0x8d4b  ldloc.s  9
0x8d4d  ldc.i4.2
0x8d4e  ldarg.2
0x8d4f  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8d54  stelem.ref
0x8d55  ldloc.s  9
0x8d57  ldc.i4.3
0x8d58  ldloc.s  5
0x8d5a  stelem.ref
0x8d5b  ldloc.s  9
0x8d5d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8d62  ldc.i4.1
0x8d63  stloc.0
0x8d64  br       loc_8E03
0x8d69  ldloc.s  4
0x8d6b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProviderCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedLoginProviders()
0x8d70  ldloc.s  5
0x8d72  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider>::get_Item(!!T0)
0x8d77  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, string> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider::get_ProviderRealms()
0x8d7c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, string>::get_Values()
0x8d81  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<class [System]System.Uri, string>::GetEnumerator()
0x8d86  stloc.s  0xA
0x8d88  br.s     loc_8DEA
0x8d8a  ldloca.s 0xA
0x8d8c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>::get_Current()
0x8d91  stloc.s  6
0x8d93  ldloc.s  6
0x8d95  ldarg.0
0x8d96  callvirt instance string [mscorlib]System.Object::ToString()
0x8d9b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8da0  brfalse.s loc_8DEA
0x8da2  ldc.i4   0x8C5623
0x8da7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8dac  ldc.i4.s 0x32
0x8dae  ldstr    aTheAudienceUri_1// "The audience uri matches a trusted logi"...
0x8db3  ldc.i4.4
0x8db4  newarr   [mscorlib]System.Object
0x8db9  stloc.s  0xB
0x8dbb  ldloc.s  0xB
0x8dbd  ldc.i4.0
0x8dbe  ldarg.0
0x8dbf  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8dc4  stelem.ref
0x8dc5  ldloc.s  0xB
0x8dc7  ldc.i4.1
0x8dc8  ldarg.1
0x8dc9  box      [mscorlib]System.Guid
0x8dce  stelem.ref
0x8dcf  ldloc.s  0xB
0x8dd1  ldc.i4.2
0x8dd2  ldarg.2
0x8dd3  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8dd8  stelem.ref
0x8dd9  ldloc.s  0xB
0x8ddb  ldc.i4.3
0x8ddc  ldloc.s  5
0x8dde  stelem.ref
0x8ddf  ldloc.s  0xB
0x8de1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8de6  ldc.i4.1
0x8de7  stloc.0
0x8de8  br.s     loc_8DF3
0x8dea  ldloca.s 0xA
0x8dec  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>::MoveNext()
0x8df1  brtrue.s loc_8D8A
0x8df3  leave.s  loc_8E03
0x8df5  ldloca.s 0xA
0x8df7  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>
0x8dfd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e02  endfinally
0x8e03  ldloc.0
0x8e04  brtrue.s loc_8E12
0x8e06  ldloc.s  8
0x8e08  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e0d  brtrue   loc_8CF5
0x8e12  leave.s  loc_8E60
0x8e14  ldloc.s  8
0x8e16  brfalse.s loc_8E1F
0x8e18  ldloc.s  8
0x8e1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e1f  endfinally
0x8e20  ldc.i4   0x8C5640
0x8e25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8e2a  ldc.i4.s 0xA
0x8e2c  ldstr    aTheAudienceUri_2// "The audience uri did not match a web ap"...
0x8e31  ldc.i4.3
0x8e32  newarr   [mscorlib]System.Object
0x8e37  stloc.s  0xC
0x8e39  ldloc.s  0xC
0x8e3b  ldc.i4.0
0x8e3c  ldarg.0
0x8e3d  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8e42  stelem.ref
0x8e43  ldloc.s  0xC
0x8e45  ldc.i4.1
0x8e46  ldarg.1
0x8e47  box      [mscorlib]System.Guid
0x8e4c  stelem.ref
0x8e4d  ldloc.s  0xC
0x8e4f  ldc.i4.2
0x8e50  ldarg.2
0x8e51  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone
0x8e56  stelem.ref
0x8e57  ldloc.s  0xC
0x8e59  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8e5e  ldc.i4.0
0x8e5f  stloc.0
0x8e60  ldloc.0
0x8e61  ret
```
