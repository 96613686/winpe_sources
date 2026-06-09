# System.Deployment.Application.ComponentStore::GetSubscriptionStateInternal_0

- ea: `0xe520`
- end: `0xe77e`
- name: `System.Deployment.Application.ComponentStore::GetSubscriptionStateInternal_0`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xe510`

## callees

- `0xd520`
- `0xd600`
- `0xd610`
- `0xda80`
- `0xe520`
- `0xeac0`
- `0xeb30`
- `0xebe0`
- `0xec60`
- `0xece0`
- `0xed30`
- `0xed80`
- `0xee00`
- `0xee60`
- `0xfbf0`
- `0x14780`
- `0x14ba0`
- `0x17d40`
- `0x23020`

## string_xrefs

- `0xe5bd`: `DeploymentProviderUri`
- `0xe5f3`: `UpdateSkippedDeployment`
- `0xe605`: `UpdateSkipTime`
- `0xe669`: `DeploymentSourceUri`
- `0xe6a8`: `ApplicationSourceUri`
- `0xe739`: `Exception thrown for GetAssemblyManifest in GetSubscriptionStateInternal: `

## pseudocode

```c

```

## disassembly

```asm
0xe520  newobj   instance void System.Deployment.Application.SubscriptionStateInternal::.ctor()
0xe525  stloc.0
0xe526  ldloc.0
0xe527  ldarg.0
0xe528  ldarg.1
0xe529  call     instance bool System.Deployment.Application.ComponentStore::IsSubscriptionInstalled(class System.Deployment.Application.DefinitionIdentity subId)
0xe52e  stfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xe533  ldloc.0
0xe534  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xe539  brfalse  loc_E77C
0xe53e  ldc.i4.1
0xe53f  newarr   System.Deployment.Application.DefinitionIdentity
0xe544  dup
0xe545  ldc.i4.0
0xe546  ldarg.1
0xe547  stelem.ref
0xe548  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(class System.Deployment.Application.DefinitionIdentity[] idPath)
0xe54d  stloc.1
0xe54e  ldloc.0
0xe54f  ldarg.0
0xe550  ldloc.1
0xe551  ldstr    aIsshellvisible// "IsShellVisible"
0xe556  call     instance bool System.Deployment.Application.ComponentStore::GetPropertyBoolean(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe55b  stfld    bool System.Deployment.Application.SubscriptionStateInternal::IsShellVisible
0xe560  ldloc.0
0xe561  ldarg.0
0xe562  ldloc.1
0xe563  ldstr    aCurrentbind// "CurrentBind"
0xe568  call     instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ComponentStore::GetPropertyDefinitionAppId(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe56d  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe572  ldloc.0
0xe573  ldarg.0
0xe574  ldloc.1
0xe575  ldstr    aPreviousbind// "PreviousBind"
0xe57a  call     instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ComponentStore::GetPropertyDefinitionAppId(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe57f  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe584  ldloc.0
0xe585  ldarg.0
0xe586  ldloc.1
0xe587  ldstr    aPendingbind// "PendingBind"
0xe58c  call     instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ComponentStore::GetPropertyDefinitionAppId(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe591  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xe596  ldloc.0
0xe597  ldarg.0
0xe598  ldloc.1
0xe599  ldstr    aExcludeddeploy// "ExcludedDeployment"
0xe59e  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.ComponentStore::GetPropertyDefinitionIdentity(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5a3  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::ExcludedDeployment
0xe5a8  ldloc.0
0xe5a9  ldarg.0
0xe5aa  ldloc.1
0xe5ab  ldstr    aPendingdeploym_0// "PendingDeployment"
0xe5b0  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.ComponentStore::GetPropertyDefinitionIdentity(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5b5  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xe5ba  ldloc.0
0xe5bb  ldarg.0
0xe5bc  ldloc.1
0xe5bd  ldstr    aDeploymentprov// "DeploymentProviderUri"
0xe5c2  call     instance class [System]System.Uri System.Deployment.Application.ComponentStore::GetPropertyUri(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5c7  stfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0xe5cc  ldloc.0
0xe5cd  ldarg.0
0xe5ce  ldloc.1
0xe5cf  ldstr    aMinimumrequire// "MinimumRequiredVersion"
0xe5d4  call     instance class [mscorlib]System.Version System.Deployment.Application.ComponentStore::GetPropertyVersion(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5d9  stfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xe5de  ldloc.0
0xe5df  ldarg.0
0xe5e0  ldloc.1
0xe5e1  ldstr    aLastchecktime// "LastCheckTime"
0xe5e6  call     instance valuetype [mscorlib]System.DateTime System.Deployment.Application.ComponentStore::GetPropertyDateTime(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5eb  stfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::LastCheckTime
0xe5f0  ldloc.0
0xe5f1  ldarg.0
0xe5f2  ldloc.1
0xe5f3  ldstr    aUpdateskippedd// "UpdateSkippedDeployment"
0xe5f8  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.ComponentStore::GetPropertyDefinitionIdentity(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe5fd  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::UpdateSkippedDeployment
0xe602  ldloc.0
0xe603  ldarg.0
0xe604  ldloc.1
0xe605  ldstr    aUpdateskiptime// "UpdateSkipTime"
0xe60a  call     instance valuetype [mscorlib]System.DateTime System.Deployment.Application.ComponentStore::GetPropertyDateTime(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe60f  stfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::UpdateSkipTime
0xe614  ldloc.0
0xe615  ldarg.0
0xe616  ldloc.1
0xe617  ldstr    aApptype// "AppType"
0xe61c  call     instance valuetype System.Deployment.Application.AppType System.Deployment.Application.ComponentStore::GetPropertyAppType(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe621  stfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionStateInternal::appType
0xe626  ldloc.0
0xe627  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe62c  brtrue.s loc_E63E
0xe62e  ldstr    aExNocurrentbin// "Ex_NoCurrentBind"
0xe633  call     string System.Deployment.Application.Resources::GetString(string s)
0xe638  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xe63d  throw
0xe63e  ldloc.0
0xe63f  ldloc.0
0xe640  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe645  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0xe64a  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::CurrentDeployment
0xe64f  ldloc.0
0xe650  ldarg.0
0xe651  ldloc.0
0xe652  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::CurrentDeployment
0xe657  call     instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ComponentStore::GetAssemblyManifest(class System.Deployment.Application.DefinitionIdentity asmId)
0xe65c  stfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::CurrentDeploymentManifest
0xe661  ldloc.0
0xe662  ldarg.0
0xe663  ldloc.0
0xe664  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe669  ldstr    aDeploymentsour// "DeploymentSourceUri"
0xe66e  call     instance class [System]System.Uri System.Deployment.Application.ComponentStore::GetPropertyUri(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe673  stfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::CurrentDeploymentSourceUri
0xe678  ldloc.0
0xe679  ldloc.0
0xe67a  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe67f  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_ApplicationIdentity()
0xe684  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::CurrentApplication
0xe689  ldloc.0
0xe68a  ldarg.0
0xe68b  ldloc.0
0xe68c  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe691  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_ApplicationIdentity()
0xe696  call     instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ComponentStore::GetAssemblyManifest(class System.Deployment.Application.DefinitionIdentity asmId)
0xe69b  stfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::CurrentApplicationManifest
0xe6a0  ldloc.0
0xe6a1  ldarg.0
0xe6a2  ldloc.0
0xe6a3  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xe6a8  ldstr    aApplicationsou// "ApplicationSourceUri"
0xe6ad  call     instance class [System]System.Uri System.Deployment.Application.ComponentStore::GetPropertyUri(class System.Deployment.Application.DefinitionAppId appId, string propName)
0xe6b2  stfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::CurrentApplicationSourceUri
0xe6b7  ldloc.0
0xe6b8  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe6bd  brtrue.s loc_E6C2
0xe6bf  ldnull
0xe6c0  br.s     loc_E6CD
0xe6c2  ldloc.0
0xe6c3  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe6c8  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0xe6cd  stloc.2
0xe6ce  ldloc.0
0xe6cf  ldloc.2
0xe6d0  brfalse.s loc_E6F3
0xe6d2  ldloc.0
0xe6d3  ldfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xe6d8  ldnull
0xe6d9  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xe6de  brtrue.s loc_E6F6
0xe6e0  ldloc.2
0xe6e1  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0xe6e6  ldloc.0
0xe6e7  ldfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xe6ec  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xe6f1  brtrue.s loc_E6F6
0xe6f3  ldnull
0xe6f4  br.s     loc_E6F7
0xe6f6  ldloc.2
0xe6f7  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::RollbackDeployment
0xe6fc  ldloc.0
0xe6fd  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe702  brfalse.s loc_E77C
0xe704  ldloc.0
0xe705  ldloc.0
0xe706  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe70b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_ApplicationIdentity()
0xe710  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PreviousApplication
0xe715  ldloc.0
0xe716  ldarg.0
0xe717  ldloc.0
0xe718  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe71d  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_ApplicationIdentity()
0xe722  call     instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ComponentStore::GetAssemblyManifest(class System.Deployment.Application.DefinitionIdentity asmId)
0xe727  stfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::PreviousApplicationManifest
0xe72c  leave.s  loc_E77C
0xe72e  stloc.3
0xe72f  ldloc.3
0xe730  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0xe735  brfalse.s loc_E739
0xe737  rethrow
0xe739  ldstr    aExceptionThrow// "Exception thrown for GetAssemblyManifes"...
0xe73e  ldloc.3
0xe73f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xe744  callvirt instance string [mscorlib]System.Object::ToString()
0xe749  ldstr    asc_32300// ":"
0xe74e  ldloc.3
0xe74f  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe754  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xe759  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xe75e  ldloc.0
0xe75f  ldnull
0xe760  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xe765  ldloc.0
0xe766  ldnull
0xe767  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::RollbackDeployment
0xe76c  ldloc.0
0xe76d  ldnull
0xe76e  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PreviousApplication
0xe773  ldloc.0
0xe774  ldnull
0xe775  stfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionStateInternal::PreviousApplicationManifest
0xe77a  leave.s  loc_E77C
0xe77c  ldloc.0
0xe77d  ret
```
