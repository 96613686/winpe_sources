# Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::.ctor

- ea: `0x1f740`
- end: `0x1f84a`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::.ctor`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1fad0`

## callees

- `0x1f740`
- `0x1f8b0`
- `0x1f980`
- `0x1f9f0`

## string_xrefs

- `0x1f7d7`: `urn:schemas-microsoft-com:sharepoint:service`
- `0x1f757`: `STS Configuration: Starting configuration.`
- `0x1f77c`: `STS Configuration: Could not load SPSecurityTokenServiceManager.`
- `0x1f811`: `STS Configuration: Changed WSTrist13RequestSerializer to use SPRequestSecurityTokenerializer.`
- `0x1f83f`: `STS Configuration: Successfully completed configuration.`

## pseudocode

```c

```

## disassembly

```asm
0x1f740  ldarg.0
0x1f741  ldstr    aSharepoint// "SharePoint"
0x1f746  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.SecurityTokenServiceConfiguration::.ctor(string)
0x1f74b  ldc.i4   0x15D652
0x1f750  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f755  ldc.i4.s 0x64
0x1f757  ldstr    aStsConfigurati// "STS Configuration: Starting configurati"...
0x1f75c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f761  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x1f766  stloc.0
0x1f767  ldnull
0x1f768  ldloc.0
0x1f769  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1f76e  brfalse.s loc_1F78C
0x1f770  ldc.i4   0x15D653
0x1f775  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f77a  ldc.i4.s 0xA
0x1f77c  ldstr    aStsConfigurati_0// "STS Configuration: Could not load SPSec"...
0x1f781  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f786  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1f78b  throw
0x1f78c  ldarg.0
0x1f78d  ldtoken  Microsoft.SharePoint.IdentityModel.SPSecurityTokenService
0x1f792  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f797  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.SecurityTokenServiceConfiguration::set_SecurityTokenService(class [mscorlib]System.Type)
0x1f79c  ldarg.0
0x1f79d  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIssuerNameRegistry::get_LocalIssuerNameRegistry()
0x1f7a2  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::set_IssuerNameRegistry(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry)
0x1f7a7  ldarg.0
0x1f7a8  ldc.i4.1
0x1f7a9  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::set_DisableWsdl(bool)
0x1f7ae  ldarg.0
0x1f7af  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPCertificateValidator [Microsoft.SharePoint]Microsoft.SharePoint.SPCertificateValidator::get_Default()
0x1f7b4  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::set_CertificateValidator(class [System.IdentityModel]System.IdentityModel.Selectors.X509CertificateValidator)
0x1f7b9  ldarg.0
0x1f7ba  ldc.i4.4
0x1f7bb  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x1f7c0  ldarg.0
0x1f7c1  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceRestriction [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_AudienceRestriction()
0x1f7c6  ldc.i4.1
0x1f7c7  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceRestriction::set_AudienceMode(valuetype [System.IdentityModel]System.IdentityModel.Selectors.AudienceUriMode)
0x1f7cc  ldarg.0
0x1f7cd  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceRestriction [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_AudienceRestriction()
0x1f7d2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceRestriction::get_AllowedAudienceUris()
0x1f7d7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:sharepoint:se"...
0x1f7dc  newobj   instance void [System]System.Uri::.ctor(string)
0x1f7e1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::Add(var<u1>)
0x1f7e6  ldarg.0
0x1f7e7  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_SecurityTokenHandlerCollectionManager()
0x1f7ec  stloc.1
0x1f7ed  ldarg.0
0x1f7ee  ldloc.0
0x1f7ef  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureSigningAndEnctyption(class Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration configuration, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager stsManager)
0x1f7f4  ldloc.1
0x1f7f5  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureDefaultTokenHandlerCollection(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager collectionManager)
0x1f7fa  ldarg.0
0x1f7fb  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPTrust13RequestSerializer::.ctor()
0x1f800  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.SecurityTokenServiceConfiguration::set_WSTrust13RequestSerializer(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrust13RequestSerializer)
0x1f805  ldc.i4   0xCB305
0x1f80a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f80f  ldc.i4.s 0x64
0x1f811  ldstr    aStsConfigurati_1// "STS Configuration: Changed WSTrist13Req"...
0x1f816  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f81b  ldloc.0
0x1f81c  ldloc.1
0x1f81d  ldstr    aOnbehalfof// "OnBehalfOf"
0x1f822  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureTokenHandlerCollectionForLocalIssuer(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager manager, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager collectionManager, string key)
0x1f827  ldloc.0
0x1f828  ldloc.1
0x1f829  ldstr    aActas// "ActAs"
0x1f82e  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureTokenHandlerCollectionForLocalIssuer(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager manager, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager collectionManager, string key)
0x1f833  ldc.i4   0x15D654
0x1f838  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f83d  ldc.i4.s 0x64
0x1f83f  ldstr    aStsConfigurati_2// "STS Configuration: Successfully complet"...
0x1f844  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f849  ret
```
