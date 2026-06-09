# Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureTokenHandlerCollectionForLocalIssuer

- ea: `0x1f9f0`
- end: `0x1fabc`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::ConfigureTokenHandlerCollectionForLocalIssuer`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1f740`

## callees

- `0xd220`
- `0x16940`
- `0x1f9f0`

## string_xrefs

- `0x1f9fc`: `STS Configuration: Configuring Security Token Handler collection. OperationType: '{0}'.`
- `0x1fa46`: `STS Configuration: Added SPFormsUserNameSecurityTokenHandler instance to handler collection for OnBehalOf.`
- `0x1fa68`: `STS Configuration: Added SPJsonWebSecurityBaseTokenHandler instnace to handler collection for OnBehalOf.`
- `0x1fab1`: `STS Configuration: Added SPIdentityAndProofTokenHandler instnace to handler collection for OnBehalOf.`

## pseudocode

```c

```

## disassembly

```asm
0x1f9f0  ldc.i4   0x15D65B
0x1f9f5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f9fa  ldc.i4.s 0x64
0x1f9fc  ldstr    aStsConfigurati_8// "STS Configuration: Configuring Security"...
0x1fa01  ldc.i4.1
0x1fa02  newarr   [mscorlib]System.Object
0x1fa07  stloc.3
0x1fa08  ldloc.3
0x1fa09  ldc.i4.0
0x1fa0a  ldarg.2
0x1fa0b  stelem.ref
0x1fa0c  ldloc.3
0x1fa0d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1fa12  ldarg.0
0x1fa13  ldarg.1
0x1fa14  ldarg.2
0x1fa15  ldloca.s 0
0x1fa17  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::ConfigureTokenHandlerCollection(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollectionManager, string, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection&)
0x1fa1c  ldarg.2
0x1fa1d  ldstr    aOnbehalfof// "OnBehalfOf"
0x1fa22  ldc.i4.5
0x1fa23  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1fa28  stloc.1
0x1fa29  ldloc.1
0x1fa2a  brfalse  loc_1FABB
0x1fa2f  ldloc.0
0x1fa30  newobj   instance void Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::.ctor()
0x1fa35  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler)
0x1fa3a  ldc.i4   0x15D65C
0x1fa3f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fa44  ldc.i4.s 0x64
0x1fa46  ldstr    aStsConfigurati_9// "STS Configuration: Added SPFormsUserNam"...
0x1fa4b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fa50  ldloc.0
0x1fa51  ldc.i4.1
0x1fa52  newobj   instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode mode)
0x1fa57  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler)
0x1fa5c  ldc.i4   0xCB306
0x1fa61  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fa66  ldc.i4.s 0x64
0x1fa68  ldstr    aStsConfigurati_10// "STS Configuration: Added SPJsonWebSecur"...
0x1fa6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fa72  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x1fa77  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProviderOrThrow()
0x1fa7c  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider::get_EncryptionCertificate()
0x1fa81  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.X509EncryptingCredentials::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x1fa86  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenHandler::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.X509EncryptingCredentials)
0x1fa8b  stloc.2
0x1fa8c  ldloc.2
0x1fa8d  ldnull
0x1fa8e  ldftn    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler> Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceConfiguration::GetSecurityTokenHandlers()
0x1fa94  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.CreateSecurityTokenHandlerCollection::.ctor(object, native int)
0x1fa99  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenHandler::SetCreateSecurityTokenHandlerCollectionCallback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.CreateSecurityTokenHandlerCollection)
0x1fa9e  ldloc.0
0x1fa9f  ldloc.2
0x1faa0  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::AddOrReplace(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler)
0x1faa5  ldc.i4   0x35F7D3
0x1faaa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1faaf  ldc.i4.s 0x64
0x1fab1  ldstr    aStsConfigurati_11// "STS Configuration: Added SPIdentityAndP"...
0x1fab6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fabb  ret
```
