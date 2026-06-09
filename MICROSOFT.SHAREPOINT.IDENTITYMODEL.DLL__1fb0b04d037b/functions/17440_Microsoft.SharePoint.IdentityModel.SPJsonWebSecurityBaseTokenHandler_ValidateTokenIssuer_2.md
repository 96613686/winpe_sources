# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_2

- ea: `0x17440`
- end: `0x1757e`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_2`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x17070`
- `0x17280`

## callees

- `0x169c0`
- `0x17440`

## string_xrefs

- `0x174a2`: `The tokenIssuer is null or empty.`
- `0x174ac`: `tokenIssuer`
- `0x174e5`: `SPJsonWebSecurityBaseTokenHandler: ValidateTokenIssuer accepted Issuer '{0}' because no registered STS matches the signing certificate '{1}'`
- `0x17524`: `SPJsonWebSecurityBaseTokenHandler: Issuer name in token '{0}' matches the registered issuer name for trusted sts '{1}'.`
- `0x17550`: `SPJsonWebSecurityBaseTokenHandler: Issuer name in token '{0}' doesn't match any of the registered issuer names for trusted sts '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x17440  ldarg.1
0x17441  brtrue.s loc_17464
0x17443  ldc.i4   0x650404
0x17448  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1744d  ldc.i4.s 0xA
0x1744f  ldstr    aTheSigningkeyI// "The signingKey is null."
0x17454  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17459  ldstr    aSigningkey// "signingKey"
0x1745e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17463  throw
0x17464  ldarg.1
0x17465  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::get_Certificate()
0x1746a  brtrue.s loc_1748E
0x1746c  ldc.i4   0x650405
0x17471  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17476  ldc.i4.s 0xA
0x17478  ldstr    aTheSigningkeyS// "The signingKey's Certificate property i"...
0x1747d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17482  ldnull
0x17483  ldstr    aSigningkey// "signingKey"
0x17488  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1748d  throw
0x1748e  ldarg.2
0x1748f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x17494  brfalse.s loc_174B7
0x17496  ldc.i4   0x650406
0x1749b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x174a0  ldc.i4.s 0xA
0x174a2  ldstr    aTheTokenissuer// "The tokenIssuer is null or empty."
0x174a7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x174ac  ldstr    aTokenissuer// "tokenIssuer"
0x174b1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x174b6  throw
0x174b7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x174bc  stloc.0
0x174bd  ldloc.0
0x174be  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedSecurityTokenServices()
0x174c3  ldarg.1
0x174c4  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::get_Certificate()
0x174c9  ldarg.2
0x174ca  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService>::GetProviderBySigningCertificate(!!T0, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x174cf  stloc.1
0x174d0  ldnull
0x174d1  ldloc.1
0x174d2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x174d7  brfalse.s loc_1750A
0x174d9  ldc.i4   0x1C349F
0x174de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x174e3  ldc.i4.s 0x64
0x174e5  ldstr    aSpjsonwebsecur// "SPJsonWebSecurityBaseTokenHandler: Vali"...
0x174ea  ldc.i4.2
0x174eb  newarr   [mscorlib]System.Object
0x174f0  stloc.2
0x174f1  ldloc.2
0x174f2  ldc.i4.0
0x174f3  ldarg.2
0x174f4  stelem.ref
0x174f5  ldloc.2
0x174f6  ldc.i4.1
0x174f7  ldarg.1
0x174f8  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::get_Certificate()
0x174fd  callvirt instance string [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Subject()
0x17502  stelem.ref
0x17503  ldloc.2
0x17504  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17509  ret
0x1750a  ldarg.2
0x1750b  ldloc.1
0x1750c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_RegisteredIssuerName()
0x17511  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::IssuerNameMatches(string, string)
0x17516  brfalse.s loc_17544
0x17518  ldc.i4   0x1DC7CE
0x1751d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17522  ldc.i4.s 0x64
0x17524  ldstr    aSpjsonwebsecur_0// "SPJsonWebSecurityBaseTokenHandler: Issu"...
0x17529  ldc.i4.2
0x1752a  newarr   [mscorlib]System.Object
0x1752f  stloc.3
0x17530  ldloc.3
0x17531  ldc.i4.0
0x17532  ldarg.2
0x17533  stelem.ref
0x17534  ldloc.3
0x17535  ldc.i4.1
0x17536  ldloc.1
0x17537  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x1753c  stelem.ref
0x1753d  ldloc.3
0x1753e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17543  ret
0x17544  ldc.i4   0x1C34A2
0x17549  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1754e  ldc.i4.s 0xA
0x17550  ldstr    aSpjsonwebsecur_1// "SPJsonWebSecurityBaseTokenHandler: Issu"...
0x17555  ldc.i4.2
0x17556  newarr   [mscorlib]System.Object
0x1755b  stloc.s  4
0x1755d  ldloc.s  4
0x1755f  ldc.i4.0
0x17560  ldarg.2
0x17561  stelem.ref
0x17562  ldloc.s  4
0x17564  ldc.i4.1
0x17565  ldloc.1
0x17566  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x1756b  stelem.ref
0x1756c  ldloc.s  4
0x1756e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17573  ldstr    aIssuerNameIsNo// "Issuer name is not registered"
0x17578  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x1757d  throw
```
