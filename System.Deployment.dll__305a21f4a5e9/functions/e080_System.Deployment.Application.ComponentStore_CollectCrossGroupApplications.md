# System.Deployment.Application.ComponentStore::CollectCrossGroupApplications

- ea: `0xe080`
- end: `0xe1fd`
- name: `System.Deployment.Application.ComponentStore::CollectCrossGroupApplications`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1f1c0`

## callees

- `0x1420`
- `0x2ab0`
- `0xd950`
- `0xdaa0`
- `0xdbd0`
- `0xdbf0`
- `0xe080`
- `0x1ece0`
- `0x1ed00`
- `0x1ede0`
- `0x1eee0`
- `0x1ef80`
- `0x1f8a0`
- `0x23c30`
- `0x24b30`
- `0x28450`

## pseudocode

```c

```

## disassembly

```asm
0xe080  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xe085  stloc.0
0xe086  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xe08b  stloc.1
0xe08c  ldarg.0
0xe08d  ldfld    class System.Deployment.Internal.Isolation.Store System.Deployment.Application.ComponentStore::_store
0xe092  ldc.i4.0
0xe093  callvirt instance class System.Deployment.Internal.Isolation.StoreAssemblyEnumeration System.Deployment.Internal.Isolation.Store::EnumAssemblies(valuetype EnumAssembliesFlags Flags)
0xe098  stloc.2
0xe099  ldloc.2
0xe09a  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Deployment.Internal.Isolation.StoreAssemblyEnumeration::GetEnumerator()
0xe09f  stloc.3
0xe0a0  br       loc_E1DA
0xe0a5  ldloc.3
0xe0a6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe0ab  unbox.any System.Deployment.Internal.Isolation.STORE_ASSEMBLY
0xe0b0  stloc.s  4
0xe0b2  ldloc.s  4
0xe0b4  ldfld    class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Internal.Isolation.STORE_ASSEMBLY::DefinitionIdentity
0xe0b9  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Internal.Isolation.IDefinitionIdentity idComPtr)
0xe0be  stloc.s  5
0xe0c0  ldloc.s  5
0xe0c2  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToSubscriptionId()
0xe0c7  stloc.s  6
0xe0c9  ldarg.0
0xe0ca  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ComponentStore::_subStore
0xe0cf  ldloc.s  6
0xe0d1  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xe0d6  stloc.s  7
0xe0d8  ldloc.s  7
0xe0da  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xe0df  brfalse  loc_E1DA
0xe0e4  ldloc.s  7
0xe0e6  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xe0eb  ldarg.1
0xe0ec  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xe0f1  stloc.s  8
0xe0f3  ldloc.s  7
0xe0f5  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PKTGroupId()
0xe0fa  ldarg.2
0xe0fb  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToPKTGroupId()
0xe100  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xe105  stloc.s  9
0xe107  ldloc.s  7
0xe109  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0xe10e  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0xe113  ldarg.2
0xe114  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToSubscriptionId()
0xe119  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0xe11e  callvirt instance bool [mscorlib]System.String::Equals(string)
0xe123  stloc.s  0xA
0xe125  ldloc.s  8
0xe127  ldloc.s  9
0xe129  and
0xe12a  ldloc.s  0xA
0xe12c  and
0xe12d  brtrue   loc_E1DA
0xe132  ldloc.s  8
0xe134  ldloc.s  9
0xe136  and
0xe137  brfalse.s loc_E169
0xe139  ldloc.s  0xA
0xe13b  brtrue.s loc_E169
0xe13d  ldloc.0
0xe13e  ldloc.s  6
0xe140  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xe145  brtrue   loc_E1DA
0xe14a  ldloc.0
0xe14b  ldloc.s  6
0xe14d  ldloc.s  7
0xe14f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xe154  ldloc.1
0xe155  ldloc.s  7
0xe157  ldc.i4.1
0xe158  newobj   instance void CrossGroupApplicationData::.ctor(class System.Deployment.Application.SubscriptionState subState, valuetype GroupType groupType)
0xe15d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xe162  pop
0xe163  ldarg.s  4
0xe165  ldc.i4.1
0xe166  stind.i1
0xe167  br.s     loc_E1DA
0xe169  ldloc.s  8
0xe16b  ldc.i4.0
0xe16c  ceq
0xe16e  ldloc.s  9
0xe170  and
0xe171  ldloc.s  0xA
0xe173  and
0xe174  brfalse.s loc_E1DA
0xe176  ldloc.0
0xe177  ldloc.s  6
0xe179  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xe17e  brtrue.s loc_E1DA
0xe180  ldloc.0
0xe181  ldloc.s  6
0xe183  ldloc.s  7
0xe185  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xe18a  ldloc.1
0xe18b  ldloc.s  7
0xe18d  ldc.i4.2
0xe18e  newobj   instance void CrossGroupApplicationData::.ctor(class System.Deployment.Application.SubscriptionState subState, valuetype GroupType groupType)
0xe193  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xe198  pop
0xe199  ldloc.s  7
0xe19b  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0xe1a0  brfalse.s loc_E1D7
0xe1a2  ldloc.s  7
0xe1a4  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0xe1a9  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xe1ae  brfalse.s loc_E1D7
0xe1b0  ldloc.s  7
0xe1b2  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0xe1b7  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xe1bc  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0xe1c1  brfalse.s loc_E1D7
0xe1c3  ldarg.s  5
0xe1c5  ldloc.s  7
0xe1c7  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0xe1cc  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xe1d1  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0xe1d6  stind.ref
0xe1d7  ldarg.3
0xe1d8  ldc.i4.1
0xe1d9  stind.i1
0xe1da  ldloc.3
0xe1db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe1e0  brtrue   loc_E0A5
0xe1e5  leave.s  loc_E1FB
0xe1e7  ldloc.3
0xe1e8  isinst   [mscorlib]System.IDisposable
0xe1ed  stloc.s  0xB
0xe1ef  ldloc.s  0xB
0xe1f1  brfalse.s loc_E1FA
0xe1f3  ldloc.s  0xB
0xe1f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe1fa  endfinally
0xe1fb  ldloc.1
0xe1fc  ret
```
