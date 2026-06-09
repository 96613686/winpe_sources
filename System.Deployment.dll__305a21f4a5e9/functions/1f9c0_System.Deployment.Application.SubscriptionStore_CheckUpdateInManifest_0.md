# System.Deployment.Application.SubscriptionStore::CheckUpdateInManifest_0

- ea: `0x1f9c0`
- end: `0x1fac4`
- name: `System.Deployment.Application.SubscriptionStore::CheckUpdateInManifest_0`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xd120`
- `0x1f9b0`

## callees

- `0xda80`
- `0x146f0`
- `0x17d40`
- `0x1ece0`
- `0x1ede0`
- `0x1ef80`
- `0x1f8b0`
- `0x1f9c0`
- `0x1fd60`
- `0x1fd90`
- `0x1fda0`
- `0x23020`
- `0x24970`

## string_xrefs

- `0x1f9f3`: `Cross family update detected. Check if only PKT has changed between versions.`
- `0x1f9fd`: `updateCodebaseUri=`
- `0x1fa0f`: `, subState.DeploymentProviderUri=`

## pseudocode

```c

```

## disassembly

```asm
0x1f9c0  ldarg.1
0x1f9c1  ldarg.3
0x1f9c2  call     void System.Deployment.Application.SubscriptionStore::CheckOnlineShellVisibleConflict(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f9c7  ldarg.1
0x1f9c8  ldarg.3
0x1f9c9  call     void System.Deployment.Application.SubscriptionStore::CheckInstalledAndUpdateableConflict(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f9ce  ldarg.1
0x1f9cf  ldarg.3
0x1f9d0  call     void System.Deployment.Application.SubscriptionStore::CheckMinimumRequiredVersion(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f9d5  ldarg.0
0x1f9d6  ldarg.3
0x1f9d7  call     instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f9dc  stloc.0
0x1f9dd  ldloc.0
0x1f9de  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f9e3  ldarg.1
0x1f9e4  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f9e9  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1f9ee  brtrue   loc_1FAAA
0x1f9f3  ldstr    aCrossFamilyUpd// "Cross family update detected. Check if "...
0x1f9f8  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f9fd  ldstr    aUpdatecodebase// "updateCodebaseUri="
0x1fa02  ldarg.2
0x1fa03  dup
0x1fa04  brtrue.s loc_1FA0A
0x1fa06  pop
0x1fa07  ldnull
0x1fa08  br.s     loc_1FA0F
0x1fa0a  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa0f  ldstr    aSubstateDeploy// ", subState.DeploymentProviderUri="
0x1fa14  ldarg.1
0x1fa15  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1fa1a  dup
0x1fa1b  brtrue.s loc_1FA21
0x1fa1d  pop
0x1fa1e  ldnull
0x1fa1f  br.s     loc_1FA26
0x1fa21  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa26  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1fa2b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1fa30  ldstr    aSubstate// "subState="
0x1fa35  ldarg.1
0x1fa36  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1fa3b  dup
0x1fa3c  brtrue.s loc_1FA42
0x1fa3e  pop
0x1fa3f  ldnull
0x1fa40  br.s     loc_1FA47
0x1fa42  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa47  ldstr    aMansubstateSub// ", manSubState.SubscriptionId="
0x1fa4c  ldloc.0
0x1fa4d  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1fa52  dup
0x1fa53  brtrue.s loc_1FA59
0x1fa55  pop
0x1fa56  ldnull
0x1fa57  br.s     loc_1FA5E
0x1fa59  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa5e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1fa63  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1fa68  ldarg.2
0x1fa69  ldarg.1
0x1fa6a  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1fa6f  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1fa74  brfalse.s loc_1FA99
0x1fa76  ldarg.1
0x1fa77  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PKTGroupId()
0x1fa7c  ldloc.0
0x1fa7d  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PKTGroupId()
0x1fa82  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1fa87  brfalse.s loc_1FA99
0x1fa89  ldstr    aPktHasChanged// "PKT has changed."
0x1fa8e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1fa93  ldarg.s  5
0x1fa95  ldc.i4.1
0x1fa96  stind.i1
0x1fa97  br.s     loc_1FAAA
0x1fa99  ldc.i4.8
0x1fa9a  ldstr    aExDeploymentid// "Ex_DeploymentIdentityNotInSubscription"
0x1fa9f  call     string System.Deployment.Application.Resources::GetString(string s)
0x1faa4  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1faa9  throw
0x1faaa  ldarg.3
0x1faab  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1fab0  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x1fab5  stloc.1
0x1fab6  ldloc.1
0x1fab7  ldarg.s  4
0x1fab9  callvirt instance int32 [mscorlib]System.Version::CompareTo(class [mscorlib]System.Version)
0x1fabe  brtrue.s loc_1FAC2
0x1fac0  ldnull
0x1fac1  ret
0x1fac2  ldloc.1
0x1fac3  ret
```
