# System.Web.ClientServices.Providers.ClientData::.cctor

- ea: `0x38030`
- end: `0x380a9`
- name: `System.Web.ClientServices.Providers.ClientData::.cctor`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task`

## string_xrefs

- `0x38061`: `RolesCachedDateUtc`
- `0x3808b`: `SettingsCacheIsMoreFresh`

## pseudocode

```c

```

## disassembly

```asm
0x38030  ldc.i4.s 0xD
0x38032  newarr   [mscorlib]System.String
0x38037  dup
0x38038  ldc.i4.0
0x38039  ldstr    aLastloggedinus// "LastLoggedInUserName"
0x3803e  stelem.ref
0x3803f  dup
0x38040  ldc.i4.1
0x38041  ldstr    aLastloggedinda// "LastLoggedInDateUtc"
0x38046  stelem.ref
0x38047  dup
0x38048  ldc.i4.2
0x38049  ldstr    aPasswordhash_0// "PasswordHash"
0x3804e  stelem.ref
0x3804f  dup
0x38050  ldc.i4.3
0x38051  ldstr    aPasswordsalt_0// "PasswordSalt"
0x38056  stelem.ref
0x38057  dup
0x38058  ldc.i4.4
0x38059  ldstr    aRoles// "Roles"
0x3805e  stelem.ref
0x3805f  dup
0x38060  ldc.i4.5
0x38061  ldstr    aRolescacheddat_1// "RolesCachedDateUtc"
0x38066  stelem.ref
0x38067  dup
0x38068  ldc.i4.6
0x38069  ldstr    aSettingsnames// "SettingsNames"
0x3806e  stelem.ref
0x3806f  dup
0x38070  ldc.i4.7
0x38071  ldstr    aSettingsstored// "SettingsStoredAs"
0x38076  stelem.ref
0x38077  dup
0x38078  ldc.i4.8
0x38079  ldstr    aSettingsvalues// "SettingsValues"
0x3807e  stelem.ref
0x3807f  dup
0x38080  ldc.i4.s 9
0x38082  ldstr    aSettingsneedre// "SettingsNeedReset"
0x38087  stelem.ref
0x38088  dup
0x38089  ldc.i4.s 0xA
0x3808b  ldstr    aSettingscachei// "SettingsCacheIsMoreFresh"
0x38090  stelem.ref
0x38091  dup
0x38092  ldc.i4.s 0xB
0x38094  ldstr    aCookienames// "CookieNames"
0x38099  stelem.ref
0x3809a  dup
0x3809b  ldc.i4.s 0xC
0x3809d  ldstr    aCookievalues// "CookieValues"
0x380a2  stelem.ref
0x380a3  stsfld   string[] System.Web.ClientServices.Providers.ClientData::_StoredValueNames
0x380a8  ret
```
