# Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureSigningAndEnctyption

- ea: `0x1f8b0`
- end: `0x1f976`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureSigningAndEnctyption`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1f740`

## callees

- `0x1f8b0`

## string_xrefs

- `0x1f8b3`: `configuration`
- `0x1f8ec`: `STS Configuration: Local Login Provider is missing.`
- `0x1f911`: `STS Configuration: Local Login Provider is missing it's signing certificate.`
- `0x1f93f`: `STS Configuration: Successfully configured signing certificate.`
- `0x1f958`: `STS Configuration: Failed to configure signing certificate. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f8b0  ldarg.0
0x1f8b1  brtrue.s loc_1F8BE
0x1f8b3  ldstr    aConfiguration// "configuration"
0x1f8b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f8bd  throw
0x1f8be  ldnull
0x1f8bf  ldarg.1
0x1f8c0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1f8c5  brfalse.s loc_1F8D2
0x1f8c7  ldstr    aStsmanager// "stsManager"
0x1f8cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f8d1  throw
0x1f8d2  ldnull
0x1f8d3  ldarg.1
0x1f8d4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProvider()
0x1f8d9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1f8de  brfalse.s loc_1F8F8
0x1f8e0  ldc.i4   0x15D655
0x1f8e5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f8ea  ldc.i4.s 0xA
0x1f8ec  ldstr    aStsConfigurati_3// "STS Configuration: Local Login Provider"...
0x1f8f1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f8f6  br.s     loc_1F933
0x1f8f8  ldarg.1
0x1f8f9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProvider()
0x1f8fe  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x1f903  brtrue.s loc_1F91D
0x1f905  ldc.i4   0x15D656
0x1f90a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f90f  ldc.i4.s 0xA
0x1f911  ldstr    aStsConfigurati_4// "STS Configuration: Local Login Provider"...
0x1f916  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f91b  br.s     loc_1F933
0x1f91d  ldarg.0
0x1f91e  ldarg.1
0x1f91f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProvider()
0x1f924  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x1f929  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.X509SigningCredentials::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x1f92e  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.SecurityTokenServiceConfiguration::set_SigningCredentials(class [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials)
0x1f933  ldc.i4   0x15D657
0x1f938  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f93d  ldc.i4.s 0x64
0x1f93f  ldstr    aStsConfigurati_5// "STS Configuration: Successfully configu"...
0x1f944  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f949  leave.s  loc_1F975
0x1f94b  stloc.0
0x1f94c  ldc.i4   0x15D658
0x1f951  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f956  ldc.i4.s 0xA
0x1f958  ldstr    aStsConfigurati_6// "STS Configuration: Failed to configure "...
0x1f95d  ldc.i4.1
0x1f95e  newarr   [mscorlib]System.Object
0x1f963  stloc.1
0x1f964  ldloc.1
0x1f965  ldc.i4.0
0x1f966  ldloc.0
0x1f967  callvirt instance string [mscorlib]System.Object::ToString()
0x1f96c  stelem.ref
0x1f96d  ldloc.1
0x1f96e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f973  rethrow
0x1f975  ret
```
