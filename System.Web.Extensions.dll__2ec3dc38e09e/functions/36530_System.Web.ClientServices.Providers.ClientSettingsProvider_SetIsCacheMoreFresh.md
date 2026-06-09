# System.Web.ClientServices.Providers.ClientSettingsProvider::SetIsCacheMoreFresh

- ea: `0x36530`
- end: `0x36581`
- name: `System.Web.ClientServices.Providers.ClientSettingsProvider::SetIsCacheMoreFresh`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x35e00`
- `0x36150`

## callees

- `0x36530`
- `0x365f0`
- `0x37d80`
- `0x37dd0`
- `0x380e0`

## string_xrefs

- `0x36567`: `IsCacheMoreFresh`

## pseudocode

```c

```

## disassembly

```asm
0x36530  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingFileSystemStore
0x36535  brtrue.s loc_3653E
0x36537  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x3653c  brfalse.s loc_36566
0x3653e  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x36543  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x36548  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x3654d  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x36552  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x36557  stloc.0
0x36558  ldloc.0
0x36559  ldarg.1
0x3655a  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_SettingsCacheIsMoreFresh(bool value)
0x3655f  ldloc.0
0x36560  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x36565  ret
0x36566  ldarg.0
0x36567  ldstr    aIscachemorefre// "IsCacheMoreFresh"
0x3656c  ldarg.1
0x3656d  brtrue.s loc_36576
0x3656f  ldstr    a0_0// "0"
0x36574  br.s     loc_3657B
0x36576  ldstr    a1// "1"
0x3657b  call     instance void System.Web.ClientServices.Providers.ClientSettingsProvider::SetTagValue(string tagName, string tagValue)
0x36580  ret
```
