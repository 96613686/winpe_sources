# System.Deployment.Application.ComponentStore::PrepareSetSubscriptionProperties

- ea: `0xf610`
- end: `0xf85e`
- name: `System.Deployment.Application.ComponentStore::PrepareSetSubscriptionProperties`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf500`

## callees

- `0x25b0`
- `0x2600`
- `0x2f00`
- `0xd520`
- `0xd5e0`
- `0xf610`
- `0xfa10`
- `0xfb60`
- `0xffc0`
- `0xffe0`
- `0x17d40`
- `0x1ece0`
- `0x1ed00`
- `0x1ed20`
- `0x1ed40`
- `0x1ed60`
- `0x1ed80`
- `0x1eda0`
- `0x1edc0`
- `0x1ede0`
- `0x1ee00`
- `0x1ee20`
- `0x1ee40`
- `0x1ee60`
- `0x1ee80`

## string_xrefs

- `0xf6d4`: `DeploymentProviderUri`
- `0xf729`: `UpdateSkippedDeployment`
- `0xf743`: `UpdateSkipTime`

## pseudocode

```c

```

## disassembly

```asm
0xf610  ldstr    aChangingSubscr// "Changing Subscription Properties:"
0xf615  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xf61a  ldstr    aOldSubscriptio// "Old subscription state = "
0xf61f  ldarg.2
0xf620  callvirt instance string [mscorlib]System.Object::ToString()
0xf625  call     string [mscorlib]System.String::Concat(string, string)
0xf62a  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xf62f  ldstr    aNewSubscriptio// "New subscription state = "
0xf634  ldarg.3
0xf635  callvirt instance string [mscorlib]System.Object::ToString()
0xf63a  call     string [mscorlib]System.String::Concat(string, string)
0xf63f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xf644  ldc.i4.s 0xC
0xf646  newarr   System.Deployment.Application.SubscriptionStateVariable
0xf64b  dup
0xf64c  ldc.i4.0
0xf64d  ldstr    aIsshellvisible// "IsShellVisible"
0xf652  ldarg.3
0xf653  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsShellVisible
0xf658  box      [mscorlib]System.Boolean
0xf65d  ldarg.2
0xf65e  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xf663  box      [mscorlib]System.Boolean
0xf668  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf66d  stelem.ref
0xf66e  dup
0xf66f  ldc.i4.1
0xf670  ldstr    aPreviousbind// "PreviousBind"
0xf675  ldarg.3
0xf676  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xf67b  ldarg.2
0xf67c  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_PreviousBind()
0xf681  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf686  stelem.ref
0xf687  dup
0xf688  ldc.i4.2
0xf689  ldstr    aPendingbind// "PendingBind"
0xf68e  ldarg.3
0xf68f  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xf694  ldarg.2
0xf695  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_PendingBind()
0xf69a  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf69f  stelem.ref
0xf6a0  dup
0xf6a1  ldc.i4.3
0xf6a2  ldstr    aExcludeddeploy// "ExcludedDeployment"
0xf6a7  ldarg.3
0xf6a8  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::ExcludedDeployment
0xf6ad  ldarg.2
0xf6ae  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_ExcludedDeployment()
0xf6b3  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf6b8  stelem.ref
0xf6b9  dup
0xf6ba  ldc.i4.4
0xf6bb  ldstr    aPendingdeploym_0// "PendingDeployment"
0xf6c0  ldarg.3
0xf6c1  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xf6c6  ldarg.2
0xf6c7  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PendingDeployment()
0xf6cc  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf6d1  stelem.ref
0xf6d2  dup
0xf6d3  ldc.i4.5
0xf6d4  ldstr    aDeploymentprov// "DeploymentProviderUri"
0xf6d9  ldarg.3
0xf6da  ldfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0xf6df  ldarg.2
0xf6e0  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xf6e5  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf6ea  stelem.ref
0xf6eb  dup
0xf6ec  ldc.i4.6
0xf6ed  ldstr    aMinimumrequire// "MinimumRequiredVersion"
0xf6f2  ldarg.3
0xf6f3  ldfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xf6f8  ldarg.2
0xf6f9  callvirt instance class [mscorlib]System.Version System.Deployment.Application.SubscriptionState::get_MinimumRequiredVersion()
0xf6fe  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf703  stelem.ref
0xf704  dup
0xf705  ldc.i4.7
0xf706  ldstr    aLastchecktime// "LastCheckTime"
0xf70b  ldarg.3
0xf70c  ldfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::LastCheckTime
0xf711  box      [mscorlib]System.DateTime
0xf716  ldarg.2
0xf717  callvirt instance valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionState::get_LastCheckTime()
0xf71c  box      [mscorlib]System.DateTime
0xf721  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf726  stelem.ref
0xf727  dup
0xf728  ldc.i4.8
0xf729  ldstr    aUpdateskippedd// "UpdateSkippedDeployment"
0xf72e  ldarg.3
0xf72f  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::UpdateSkippedDeployment
0xf734  ldarg.2
0xf735  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_UpdateSkippedDeployment()
0xf73a  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf73f  stelem.ref
0xf740  dup
0xf741  ldc.i4.s 9
0xf743  ldstr    aUpdateskiptime// "UpdateSkipTime"
0xf748  ldarg.3
0xf749  ldfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::UpdateSkipTime
0xf74e  box      [mscorlib]System.DateTime
0xf753  ldarg.2
0xf754  callvirt instance valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionState::get_UpdateSkipTime()
0xf759  box      [mscorlib]System.DateTime
0xf75e  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf763  stelem.ref
0xf764  dup
0xf765  ldc.i4.s 0xA
0xf767  ldstr    aApptype// "AppType"
0xf76c  ldarg.3
0xf76d  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionStateInternal::appType
0xf772  conv.u2
0xf773  box      [mscorlib]System.UInt16
0xf778  ldarg.2
0xf779  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0xf77e  conv.u2
0xf77f  box      [mscorlib]System.UInt16
0xf784  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf789  stelem.ref
0xf78a  dup
0xf78b  ldc.i4.s 0xB
0xf78d  ldstr    aCurrentbind// "CurrentBind"
0xf792  ldarg.3
0xf793  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xf798  ldarg.2
0xf799  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xf79e  newobj   instance void System.Deployment.Application.SubscriptionStateVariable::.ctor(string name, object newValue, object oldValue)
0xf7a3  stelem.ref
0xf7a4  stloc.0
0xf7a5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xf7aa  stloc.1
0xf7ab  ldloc.0
0xf7ac  stloc.2
0xf7ad  ldc.i4.0
0xf7ae  stloc.3
0xf7af  br.s     loc_F807
0xf7b1  ldloc.2
0xf7b2  ldloc.3
0xf7b3  ldelem.ref
0xf7b4  stloc.s  4
0xf7b6  ldarg.2
0xf7b7  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xf7bc  brfalse.s loc_F7CF
0xf7be  ldloc.s  4
0xf7c0  callvirt instance bool System.Deployment.Application.SubscriptionStateVariable::get_IsUnchanged()
0xf7c5  brfalse.s loc_F7CF
0xf7c7  ldarg.3
0xf7c8  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xf7cd  brtrue.s loc_F803
0xf7cf  ldloc.1
0xf7d0  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.Constants::DeploymentPropertySet
0xf7d5  ldloc.s  4
0xf7d7  ldfld    string System.Deployment.Application.SubscriptionStateVariable::PropertyName
0xf7dc  ldarg.3
0xf7dd  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xf7e2  brtrue.s loc_F7E7
0xf7e4  ldnull
0xf7e5  br.s     loc_F7F3
0xf7e7  ldloc.s  4
0xf7e9  ldfld    object System.Deployment.Application.SubscriptionStateVariable::NewValue
0xf7ee  call     string System.Deployment.Application.ComponentStore::ToPropertyString(object propValue)
0xf7f3  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationMetadataProperty::.ctor(valuetype [mscorlib]System.Guid PropertySet, string Name, string Value)
0xf7f8  box      System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf7fd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xf802  pop
0xf803  ldloc.3
0xf804  ldc.i4.1
0xf805  add
0xf806  stloc.3
0xf807  ldloc.3
0xf808  ldloc.2
0xf809  ldlen
0xf80a  conv.i4
0xf80b  blt.s    loc_F7B1
0xf80d  ldloc.1
0xf80e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf813  ldc.i4.0
0xf814  ble.s    loc_F85D
0xf816  ldloc.1
0xf817  ldtoken  System.Deployment.Internal.Isolation.StoreOperationMetadataProperty
0xf81c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf821  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xf826  castclass valuetype System.Deployment.Internal.Isolation.StoreOperationMetadataProperty[]
0xf82b  stloc.s  5
0xf82d  ldc.i4.1
0xf82e  newarr   System.Deployment.Application.DefinitionIdentity
0xf833  dup
0xf834  ldc.i4.0
0xf835  ldarg.2
0xf836  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0xf83b  stelem.ref
0xf83c  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(class System.Deployment.Application.DefinitionIdentity[] idPath)
0xf841  stloc.s  6
0xf843  ldarg.1
0xf844  ldloc.s  6
0xf846  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0xf84b  ldarg.0
0xf84c  call     instance valuetype System.Deployment.Internal.Isolation.StoreApplicationReference System.Deployment.Application.ComponentStore::get_InstallReference()
0xf851  ldloc.s  5
0xf853  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationSetDeploymentMetadata::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId Deployment, valuetype System.Deployment.Internal.Isolation.StoreApplicationReference Reference, valuetype System.Deployment.Internal.Isolation.StoreOperationMetadataProperty[] SetProperties)
0xf858  callvirt instance void System.Deployment.Internal.Isolation.StoreTransaction::Add(valuetype System.Deployment.Internal.Isolation.StoreOperationSetDeploymentMetadata o)
0xf85d  ret
```
