# System.Web.ClientServices.Providers.ClientSettingsProvider::GetIsCacheMoreFresh

- ea: `0x364e0`
- end: `0x3652c`
- name: `System.Web.ClientServices.Providers.ClientSettingsProvider::GetIsCacheMoreFresh`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x355d0`
- `0x356e0`

## callees

- `0x364e0`
- `0x36590`
- `0x37d70`
- `0x380e0`

## string_xrefs

- `0x36510`: `IsCacheMoreFresh`

## pseudocode

```c

```

## disassembly

```asm
0x364e0  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingFileSystemStore
0x364e5  brtrue.s loc_364EE
0x364e7  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x364ec  brfalse.s loc_3650F
0x364ee  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x364f3  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x364f8  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x364fd  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x36502  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x36507  stloc.0
0x36508  ldloc.0
0x36509  callvirt instance bool System.Web.ClientServices.Providers.ClientData::get_SettingsCacheIsMoreFresh()
0x3650e  ret
0x3650f  ldarg.0
0x36510  ldstr    aIscachemorefre// "IsCacheMoreFresh"
0x36515  call     instance string System.Web.ClientServices.Providers.ClientSettingsProvider::GetTagValue(string tagName)
0x3651a  stloc.1
0x3651b  ldloc.1
0x3651c  brfalse.s loc_3652A
0x3651e  ldloc.1
0x3651f  ldstr    a1// "1"
0x36524  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36529  ret
0x3652a  ldc.i4.0
0x3652b  ret
```
