# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ValidateBadgerToken

- ea: `0x6d40`
- end: `0x6e75`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ValidateBadgerToken`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x6d40`

## string_xrefs

- `0x6e5f`: `SPApplicationAuthenticationModule: Validate badger token.`
- `0x6d7c`: `badger SPTrustedSecurityTokenService does not exist.`
- `0x6d93`: `SPApplicationAuthenticationModule: Security Token Service: {0}.`
- `0x6e15`: `SPApplicationAuthenticationModule: Security Token Service Provider certificate is null.`
- `0x6e34`: `https://onedrive.com/`

## pseudocode

```c

```

## disassembly

```asm
0x6d40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.X509SecurityKey>::.ctor()
0x6d45  stloc.0
0x6d46  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x6d4b  stloc.1
0x6d4c  ldloc.1
0x6d4d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedSecurityTokenServices()
0x6d52  ldstr    aBadgerTrust// "Badger-Trust"
0x6d57  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService>::GetProviderByName(!!T0)
0x6d5c  stloc.2
0x6d5d  ldnull
0x6d5e  ldloc.2
0x6d5f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x6d64  brfalse.s loc_6D87
0x6d66  ldc.i4   0x2151514
0x6d6b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x6d70  ldc.i4.s 0xA
0x6d72  ldstr    aBadgerTrustedI// "Badger trusted issuer does not exist."
0x6d77  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x6d7c  ldstr    aBadgerSptruste// "badger SPTrustedSecurityTokenService do"...
0x6d81  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6d86  throw
0x6d87  ldc.i4   0x2151515
0x6d8c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x6d91  ldc.i4.s 0x32
0x6d93  ldstr    aSpapplicationa_101// "SPApplicationAuthenticationModule: Secu"...
0x6d98  ldc.i4.1
0x6d99  newarr   [mscorlib]System.Object
0x6d9e  stloc.s  7
0x6da0  ldloc.s  7
0x6da2  ldc.i4.0
0x6da3  ldloc.2
0x6da4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x6da9  stelem.ref
0x6daa  ldloc.s  7
0x6dac  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x6db1  ldloc.2
0x6db2  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x6db7  brfalse.s loc_6E09
0x6db9  ldloc.0
0x6dba  ldloc.2
0x6dbb  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x6dc0  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.X509SecurityKey::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x6dc5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.X509SecurityKey>::Add(var<u1>)
0x6dca  ldloc.2
0x6dcb  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPX509Certificate2ReadOnlyCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_AdditionalSigningCertificates()
0x6dd0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::GetEnumerator()
0x6dd5  stloc.s  8
0x6dd7  br.s     loc_6DF2
0x6dd9  ldloc.s  8
0x6ddb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Current()
0x6de0  pop
0x6de1  ldloc.0
0x6de2  ldloc.2
0x6de3  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x6de8  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.X509SecurityKey::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x6ded  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.X509SecurityKey>::Add(var<u1>)
0x6df2  ldloc.s  8
0x6df4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6df9  brtrue.s loc_6DD9
0x6dfb  leave.s  loc_6E1F
0x6dfd  ldloc.s  8
0x6dff  brfalse.s loc_6E08
0x6e01  ldloc.s  8
0x6e03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e08  endfinally
0x6e09  ldc.i4   0x2151516
0x6e0e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x6e13  ldc.i4.s 0xA
0x6e15  ldstr    aSpapplicationa_102// "SPApplicationAuthenticationModule: Secu"...
0x6e1a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x6e1f  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::.ctor()
0x6e24  stloc.s  6
0x6e26  ldloc.s  6
0x6e28  ldstr    aHttpBadgerSvcM// "http://badger.svc.ms/v1.0/auth"
0x6e2d  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidIssuer(string)
0x6e32  ldloc.s  6
0x6e34  ldstr    aHttpsOnedriveC// "https://onedrive.com/"
0x6e39  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidAudience(string)
0x6e3e  ldloc.s  6
0x6e40  ldloc.0
0x6e41  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_IssuerSigningKeys(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>)
0x6e46  ldloc.s  6
0x6e48  stloc.3
0x6e49  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::.ctor()
0x6e4e  stloc.s  4
0x6e50  ldnull
0x6e51  stloc.s  5
0x6e53  ldc.i4   0x2151517
0x6e58  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x6e5d  ldc.i4.s 0x64
0x6e5f  ldstr    aSpapplicationa_84// "SPApplicationAuthenticationModule: Vali"...
0x6e64  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x6e69  ldloc.s  4
0x6e6b  ldarg.1
0x6e6c  ldloc.3
0x6e6d  ldloca.s 5
0x6e6f  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::ValidateToken(string, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken&)
0x6e74  ret
```
