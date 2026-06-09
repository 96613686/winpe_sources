# System.Deployment.Application.ComponentStore::PrepareSetDeploymentProperties

- ea: `0xf1a0`
- end: `0xf27a`
- name: `System.Deployment.Application.ComponentStore::PrepareSetDeploymentProperties`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xf160`
- `0xf8f0`

## callees

- `0x25b0`
- `0x2600`
- `0x2f00`
- `0xd5e0`
- `0xf1a0`
- `0xfa10`
- `0xfb60`

## string_xrefs

- `0xf222`: `DeploymentSourceUri`
- `0xf239`: `ApplicationSourceUri`

## pseudocode

```c

```

## disassembly

```asm
0xf1a0  ldnull
0xf1a1  stloc.0
0xf1a2  ldnull
0xf1a3  stloc.1
0xf1a4  ldnull
0xf1a5  stloc.2
0xf1a6  ldarg.3
0xf1a7  brfalse.s loc_F215
0xf1a9  ldarg.3
0xf1aa  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xf1af  call     string System.Deployment.Application.ComponentStore::ToPropertyString(object propValue)
0xf1b4  stloc.0
0xf1b5  ldarg.3
0xf1b6  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::AppSourceUri
0xf1bb  call     string System.Deployment.Application.ComponentStore::ToPropertyString(object propValue)
0xf1c0  stloc.1
0xf1c1  ldarg.3
0xf1c2  ldfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0xf1c7  brfalse.s loc_F1F4
0xf1c9  ldarg.3
0xf1ca  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0xf1cf  ldc.i4.3
0xf1d0  beq.s    loc_F215
0xf1d2  ldarg.3
0xf1d3  ldfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0xf1d8  callvirt instance class [mscorlib]System.Security.Policy.PolicyStatement [mscorlib]System.Security.Policy.ApplicationTrust::get_DefaultGrantSet()
0xf1dd  callvirt instance class [mscorlib]System.Security.PermissionSet [mscorlib]System.Security.Policy.PolicyStatement::get_PermissionSet()
0xf1e2  callvirt instance bool [mscorlib]System.Security.PermissionSet::IsUnrestricted()
0xf1e7  box      [mscorlib]System.Boolean
0xf1ec  call     string System.Deployment.Application.ComponentStore::ToPropertyString(object propValue)
0xf1f1  stloc.2
0xf1f2  br.s     loc_F215
0xf1f4  ldarg.3
0xf1f5  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xf1fa  brfalse.s loc_F215
0xf1fc  ldarg.3
0xf1fd  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsFullTrustRequested
0xf202  brfalse.s loc_F215
0xf204  ldarg.3
0xf205  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsFullTrustRequested
0xf20a  box      [mscorlib]System.Boolean
0xf20f  call     string System.Deployment.Application.ComponentStore::ToPropertyString(object propValue)
0xf214  stloc.2
0xf215  ldc.i4.3
0xf216  newarr   System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf21b  dup
0xf21c  ldc.i4.0
0xf21d  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.Constants::DeploymentPropertySet
0xf222  ldstr    aDeploymentsour// "DeploymentSourceUri"
0xf227  ldloc.0
0xf228  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationMetadataProperty::.ctor(valuetype [mscorlib]System.Guid PropertySet, string Name, string Value)
0xf22d  stelem   System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf232  dup
0xf233  ldc.i4.1
0xf234  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.Constants::DeploymentPropertySet
0xf239  ldstr    aApplicationsou// "ApplicationSourceUri"
0xf23e  ldloc.1
0xf23f  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationMetadataProperty::.ctor(valuetype [mscorlib]System.Guid PropertySet, string Name, string Value)
0xf244  stelem   System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf249  dup
0xf24a  ldc.i4.2
0xf24b  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.Constants::DeploymentPropertySet
0xf250  ldstr    aIsfulltrust// "IsFullTrust"
0xf255  ldloc.2
0xf256  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationMetadataProperty::.ctor(valuetype [mscorlib]System.Guid PropertySet, string Name, string Value)
0xf25b  stelem   System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf260  stloc.3
0xf261  ldarg.1
0xf262  ldarg.2
0xf263  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0xf268  ldarg.0
0xf269  call     instance valuetype System.Deployment.Internal.Isolation.StoreApplicationReference System.Deployment.Application.ComponentStore::get_InstallReference()
0xf26e  ldloc.3
0xf26f  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationSetDeploymentMetadata::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId Deployment, valuetype System.Deployment.Internal.Isolation.StoreApplicationReference Reference, valuetype System.Deployment.Internal.Isolation.StoreOperationMetadataProperty[] SetProperties)
0xf274  callvirt instance void System.Deployment.Internal.Isolation.StoreTransaction::Add(valuetype System.Deployment.Internal.Isolation.StoreOperationSetDeploymentMetadata o)
0xf279  ret
```
