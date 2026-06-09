# Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveTokenCore_0

- ea: `0x15890`
- end: `0x15a92`
- name: `Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveTokenCore_0`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xea80`
- `0x156d0`
- `0x15890`
- `0x283e0`
- `0x2c520`

## string_xrefs

- `0x15971`: `SkipValidatingTokenAgainstBadgerIssuer`
- `0x1599c`: `Skip validating token against Badger trusted issuer. KeyIdentifierClause: '{0}', ServiceName: '{1}'.`
- `0x159dd`: `Validated key identifier clause using trusted security token service. KeyIdentifierClause: '{0}', ServiceName: '{1}'.`
- `0x15a6f`: `Could not validate security key identifier clause. KeyIdentifierClause: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x15890  ldc.i4   0x139879C
0x15895  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1589a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x1589f  ldstr    aKeyidentifierc// "keyIdentifierClause"
0x158a4  ldarg.1
0x158a5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x158aa  ldarg.2
0x158ab  ldnull
0x158ac  stind.ref
0x158ad  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x158b2  brtrue.s loc_158D2
0x158b4  ldarg.1
0x158b5  isinst   Microsoft.SharePoint.IdentityModel.SPHashedProofSecretKeyIdentifierClause
0x158ba  brfalse.s loc_158D2
0x158bc  ldarg.1
0x158bd  isinst   Microsoft.SharePoint.IdentityModel.SPHashedProofSecretKeyIdentifierClause
0x158c2  stloc.0
0x158c3  ldarg.2
0x158c4  ldloc.0
0x158c5  callvirt instance unsigned int8[] [System.IdentityModel]System.ServiceModel.Security.BinarySecretKeyIdentifierClause::GetKeyBytes()
0x158ca  newobj   instance void Microsoft.SharePoint.IdentityModel.SPHashedProofSecretSecurityToken::.ctor(unsigned int8[] key)
0x158cf  stind.ref
0x158d0  ldc.i4.1
0x158d1  ret
0x158d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x158d7  stloc.1
0x158d8  ldloc.1
0x158d9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProviderCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedLoginProviders()
0x158de  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider>::GetEnumerator()
0x158e3  stloc.s  5
0x158e5  br.s     loc_15936
0x158e7  ldloc.s  5
0x158e9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider>::get_Current()
0x158ee  stloc.2
0x158ef  ldarg.0
0x158f0  ldloc.2
0x158f1  ldarg.1
0x158f2  ldarg.2
0x158f3  call     instance bool Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveTokenCoreWithAccessProvider(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.IAccessProvider provider, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause keyIdentifierClause, [out] class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken& token)
0x158f8  brfalse.s loc_15936
0x158fa  ldc.i4   0x139879D
0x158ff  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x15904  ldc.i4.s 0x64
0x15906  ldstr    aValidatedKeyId_4// "Validated key identifier clause using t"...
0x1590b  ldc.i4.2
0x1590c  newarr   [mscorlib]System.Object
0x15911  stloc.s  6
0x15913  ldloc.s  6
0x15915  ldc.i4.0
0x15916  ldarg.1
0x15917  callvirt instance string [mscorlib]System.Object::ToString()
0x1591c  stelem.ref
0x1591d  ldloc.s  6
0x1591f  ldc.i4.1
0x15920  ldloc.2
0x15921  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x15926  stelem.ref
0x15927  ldloc.s  6
0x15929  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1592e  ldc.i4.1
0x1592f  stloc.s  4
0x15931  leave    loc_15A8F
0x15936  ldloc.s  5
0x15938  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1593d  brtrue.s loc_158E7
0x1593f  leave.s  loc_1594D
0x15941  ldloc.s  5
0x15943  brfalse.s loc_1594C
0x15945  ldloc.s  5
0x15947  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1594c  endfinally
0x1594d  ldloc.1
0x1594e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedSecurityTokenServices()
0x15953  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService>::GetEnumerator()
0x15958  stloc.s  7
0x1595a  br       loc_15A0D
0x1595f  ldloc.s  7
0x15961  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService>::get_Current()
0x15966  stloc.3
0x15967  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::SkipValidatingTokenAgainstBadgerIssuer
0x1596c  ldstr    a1302018// "1/30/2018"
0x15971  ldstr    aSkipvalidating// "SkipValidatingTokenAgainstBadgerIssuer"
0x15976  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x1597b  brtrue.s loc_159C6
0x1597d  ldloc.3
0x1597e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x15983  ldstr    aBadgerTrust// "Badger-Trust"
0x15988  ldc.i4.5
0x15989  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1598e  brfalse.s loc_159C6
0x15990  ldc.i4   0x2214212
0x15995  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x1599a  ldc.i4.s 0x64
0x1599c  ldstr    aSkipValidating// "Skip validating token against Badger tr"...
0x159a1  ldc.i4.2
0x159a2  newarr   [mscorlib]System.Object
0x159a7  stloc.s  8
0x159a9  ldloc.s  8
0x159ab  ldc.i4.0
0x159ac  ldarg.1
0x159ad  callvirt instance string [mscorlib]System.Object::ToString()
0x159b2  stelem.ref
0x159b3  ldloc.s  8
0x159b5  ldc.i4.1
0x159b6  ldloc.3
0x159b7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x159bc  stelem.ref
0x159bd  ldloc.s  8
0x159bf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x159c4  br.s     loc_15A0D
0x159c6  ldarg.0
0x159c7  ldloc.3
0x159c8  ldarg.1
0x159c9  ldarg.2
0x159ca  call     instance bool Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveTokenCoreWithAccessProvider(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.IAccessProvider provider, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause keyIdentifierClause, [out] class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken& token)
0x159cf  brfalse.s loc_15A0D
0x159d1  ldc.i4   0x139879E
0x159d6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x159db  ldc.i4.s 0x64
0x159dd  ldstr    aValidatedKeyId_5// "Validated key identifier clause using t"...
0x159e2  ldc.i4.2
0x159e3  newarr   [mscorlib]System.Object
0x159e8  stloc.s  9
0x159ea  ldloc.s  9
0x159ec  ldc.i4.0
0x159ed  ldarg.1
0x159ee  callvirt instance string [mscorlib]System.Object::ToString()
0x159f3  stelem.ref
0x159f4  ldloc.s  9
0x159f6  ldc.i4.1
0x159f7  ldloc.3
0x159f8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x159fd  stelem.ref
0x159fe  ldloc.s  9
0x15a00  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15a05  ldc.i4.1
0x15a06  stloc.s  4
0x15a08  leave    loc_15A8F
0x15a0d  ldloc.s  7
0x15a0f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15a14  brtrue   loc_1595F
0x15a19  leave.s  loc_15A27
0x15a1b  ldloc.s  7
0x15a1d  brfalse.s loc_15A26
0x15a1f  ldloc.s  7
0x15a21  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15a26  endfinally
0x15a27  ldarg.0
0x15a28  ldloc.1
0x15a29  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProvider()
0x15a2e  ldarg.1
0x15a2f  ldarg.2
0x15a30  call     instance bool Microsoft.SharePoint.IdentityModel.SPIssuerTokenResolver::TryResolveTokenCoreWithAccessProvider(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.IAccessProvider provider, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause keyIdentifierClause, [out] class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken& token)
0x15a35  brfalse.s loc_15A63
0x15a37  ldc.i4   0x139879F
0x15a3c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x15a41  ldc.i4.s 0x64
0x15a43  ldstr    aValidatedKeyId_6// "Validated key identifier clause using l"...
0x15a48  ldc.i4.1
0x15a49  newarr   [mscorlib]System.Object
0x15a4e  stloc.s  0xA
0x15a50  ldloc.s  0xA
0x15a52  ldc.i4.0
0x15a53  ldarg.1
0x15a54  callvirt instance string [mscorlib]System.Object::ToString()
0x15a59  stelem.ref
0x15a5a  ldloc.s  0xA
0x15a5c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15a61  ldc.i4.1
0x15a62  ret
0x15a63  ldc.i4   0x13987A0
0x15a68  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Token()
0x15a6d  ldc.i4.s 0xA
0x15a6f  ldstr    aCouldNotValida_0// "Could not validate security key identif"...
0x15a74  ldc.i4.1
0x15a75  newarr   [mscorlib]System.Object
0x15a7a  stloc.s  0xB
0x15a7c  ldloc.s  0xB
0x15a7e  ldc.i4.0
0x15a7f  ldarg.1
0x15a80  callvirt instance string [mscorlib]System.Object::ToString()
0x15a85  stelem.ref
0x15a86  ldloc.s  0xB
0x15a88  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15a8d  ldc.i4.0
0x15a8e  ret
0x15a8f  ldloc.s  4
0x15a91  ret
```
