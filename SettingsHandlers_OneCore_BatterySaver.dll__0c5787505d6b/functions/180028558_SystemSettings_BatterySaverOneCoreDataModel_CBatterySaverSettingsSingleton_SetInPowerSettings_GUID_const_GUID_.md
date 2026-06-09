# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton::SetInPowerSettings(_GUID const *,_GUID const *,ulong,bool)

- ea: `0x180028558`
- end: `0x1800285ed`
- name: `?SetInPowerSettings@CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@0K_N@Z`
- size: `149`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton *this, const struct _GUID *, struct _GUID *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028920`

## callees

- `0x18001ee80`
- `0x180028558`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285cd`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180028583`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180028583`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800285ad`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800285ad`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1800285c0`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1800285c0`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton::SetInPowerSettings(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton *this,
        const struct _GUID *a2,
        struct _GUID *a3,
        DWORD a4)
{
  __int64 result; // rax
  DWORD ActiveScheme; // ebx
  GUID *ActivePolicyGuid; // [rsp+50h] [rbp+18h] BYREF

  ActivePolicyGuid = a3;
  result = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::GetInitResult(
             this,
             a2);
  if ( (int)result >= 0 )
  {
    ActivePolicyGuid = 0;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
    if ( !ActiveScheme )
    {
      if ( !ActivePolicyGuid )
        return ActiveScheme;
      ActiveScheme = PowerWriteDCValueIndex(
                       0,
                       ActivePolicyGuid,
                       &GUID_ENERGY_SAVER_SUBGROUP,
                       &GUID_ENERGY_SAVER_BATTERY_THRESHOLD,
                       a4);
      if ( !ActiveScheme )
        ActiveScheme = PowerSetActiveScheme(0, ActivePolicyGuid);
      LocalFree(ActivePolicyGuid);
    }
    if ( (int)ActiveScheme > 0 )
      return (unsigned __int16)ActiveScheme | 0x80070000;
    return ActiveScheme;
  }
  return result;
}

```

## disassembly

```asm
0x180028558  mov     [rsp+arg_0], rbx
0x18002855d  mov     [rsp+ActivePolicyGuid], r8
0x180028562  push    rdi
0x180028563  sub     rsp, 30h
0x180028567  mov     edi, r9d
0x18002856a  call    ?GetInitResult@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::GetInitResult(void)
0x18002856f  test    eax, eax
0x180028571  js      short loc_1800285E2
0x180028573  lea     rdx, [rsp+38h+ActivePolicyGuid]; ActivePolicyGuid
0x180028578  mov     [rsp+38h+ActivePolicyGuid], 0
0x180028581  xor     ecx, ecx; UserRootPowerKey
0x180028583  call    cs:__imp_PowerGetActiveScheme
0x180028589  mov     ebx, eax
0x18002858b  test    eax, eax
0x18002858d  jnz     short loc_1800285D3
0x18002858f  mov     rdx, [rsp+38h+ActivePolicyGuid]; SchemeGuid
0x180028594  test    rdx, rdx
0x180028597  jz      short loc_1800285E0
0x180028599  lea     r9, GUID_ENERGY_SAVER_BATTERY_THRESHOLD; PowerSettingGuid
0x1800285a0  mov     [rsp+38h+DcValueIndex], edi; DcValueIndex
0x1800285a4  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800285ab  xor     ecx, ecx; RootPowerKey
0x1800285ad  call    cs:__imp_PowerWriteDCValueIndex
0x1800285b3  mov     ebx, eax
0x1800285b5  test    eax, eax
0x1800285b7  jnz     short loc_1800285C8
0x1800285b9  mov     rdx, [rsp+38h+ActivePolicyGuid]; SchemeGuid
0x1800285be  xor     ecx, ecx; UserRootPowerKey
0x1800285c0  call    cs:__imp_PowerSetActiveScheme
0x1800285c6  mov     ebx, eax
0x1800285c8  mov     rcx, [rsp+38h+ActivePolicyGuid]; hMem
0x1800285cd  call    cs:__imp_LocalFree
0x1800285d3  test    ebx, ebx
0x1800285d5  jle     short loc_1800285E0
0x1800285d7  movzx   ebx, bx
0x1800285da  or      ebx, 80070000h
0x1800285e0  mov     eax, ebx
0x1800285e2  mov     rbx, [rsp+38h+arg_0]
0x1800285e7  add     rsp, 30h
0x1800285eb  pop     rdi
0x1800285ec  retn
```
