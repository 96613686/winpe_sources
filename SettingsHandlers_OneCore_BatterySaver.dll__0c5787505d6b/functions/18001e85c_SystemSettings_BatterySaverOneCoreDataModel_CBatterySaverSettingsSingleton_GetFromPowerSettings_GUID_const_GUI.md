# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton::GetFromPowerSettings(_GUID const *,_GUID const *,ulong,bool,ulong *)

- ea: `0x18001e85c`
- end: `0x18001e923`
- name: `?GetFromPowerSettings@CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBU_GUID@@0K_NPEAK@Z`
- size: `199`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, UCHAR, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e5a4`

## callees

- `0x18001e85c`
- `0x18001ee80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e8fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e8fa`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18001e890`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18001e890`
- `api-ms-win-power-setting-l1-1-0!PowerReadDCValue` at `0x18001e8df`
- `api-ms-win-power-setting-l1-1-0!PowerReadDCValue` at `0x18001e8df`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton::GetFromPowerSettings(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton *this,
        struct _GUID *a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned int Buffer,
        unsigned int *a6)
{
  __int64 result; // rax
  signed int ActiveScheme; // ebx
  DWORD DCValue; // eax
  GUID *v10; // rcx
  GUID *ActivePolicyGuid; // [rsp+58h] [rbp+10h] BYREF
  const struct _GUID *BufferSize; // [rsp+60h] [rbp+18h] BYREF

  BufferSize = a3;
  ActivePolicyGuid = a2;
  result = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::GetInitResult(
             this,
             a2);
  if ( (int)result >= 0 )
  {
    ActivePolicyGuid = 0;
    ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
    if ( ActiveScheme || !ActivePolicyGuid )
    {
      *a6 = a4;
    }
    else
    {
      Buffer = 0;
      LODWORD(BufferSize) = 4;
      DCValue = PowerReadDCValue(
                  0,
                  ActivePolicyGuid,
                  &GUID_ENERGY_SAVER_SUBGROUP,
                  &GUID_ENERGY_SAVER_BATTERY_THRESHOLD,
                  0,
                  (PUCHAR)&Buffer,
                  (LPDWORD)&BufferSize);
      v10 = ActivePolicyGuid;
      ActiveScheme = DCValue;
      if ( !DCValue )
        a4 = Buffer;
      *a6 = a4;
      LocalFree(v10);
    }
    if ( ActiveScheme > 0 )
      return (unsigned __int16)ActiveScheme | 0x80070000;
    return (unsigned int)ActiveScheme;
  }
  return result;
}

```

## disassembly

```asm
0x18001e85c  mov     [rsp+arg_0], rbx
0x18001e861  mov     [rsp+arg_10], r8
0x18001e866  mov     [rsp+ActivePolicyGuid], rdx
0x18001e86b  push    rdi
0x18001e86c  sub     rsp, 40h
0x18001e870  mov     edi, r9d
0x18001e873  call    ?GetInitResult@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::GetInitResult(void)
0x18001e878  test    eax, eax
0x18001e87a  js      loc_18001E918
0x18001e880  lea     rdx, [rsp+48h+ActivePolicyGuid]; ActivePolicyGuid
0x18001e885  mov     [rsp+48h+ActivePolicyGuid], 0
0x18001e88e  xor     ecx, ecx; UserRootPowerKey
0x18001e890  call    cs:__imp_PowerGetActiveScheme
0x18001e896  mov     ebx, eax
0x18001e898  test    eax, eax
0x18001e89a  jnz     short loc_18001E902
0x18001e89c  mov     rdx, [rsp+48h+ActivePolicyGuid]; SchemeGuid
0x18001e8a1  test    rdx, rdx
0x18001e8a4  jz      short loc_18001E902
0x18001e8a6  mov     [rsp+48h+arg_20], eax
0x18001e8aa  lea     r9, GUID_ENERGY_SAVER_BATTERY_THRESHOLD; PowerSettingGuid
0x18001e8b1  lea     rax, [rsp+48h+arg_10]
0x18001e8b6  mov     dword ptr [rsp+48h+arg_10], 4
0x18001e8be  mov     [rsp+48h+BufferSize], rax; BufferSize
0x18001e8c3  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18001e8ca  lea     rax, [rsp+48h+arg_20]
0x18001e8cf  xor     ecx, ecx; RootPowerKey
0x18001e8d1  mov     [rsp+48h+Buffer], rax; Buffer
0x18001e8d6  mov     [rsp+48h+Type], 0; Type
0x18001e8df  call    cs:__imp_PowerReadDCValue
0x18001e8e5  mov     rcx, [rsp+48h+ActivePolicyGuid]; hMem
0x18001e8ea  test    eax, eax
0x18001e8ec  mov     ebx, eax
0x18001e8ee  mov     rax, [rsp+48h+arg_28]
0x18001e8f3  cmovz   edi, [rsp+48h+arg_20]
0x18001e8f8  mov     [rax], edi
0x18001e8fa  call    cs:__imp_LocalFree
0x18001e900  jmp     short loc_18001E909
0x18001e902  mov     rax, [rsp+48h+arg_28]
0x18001e907  mov     [rax], edi
0x18001e909  test    ebx, ebx
0x18001e90b  jle     short loc_18001E916
0x18001e90d  movzx   ebx, bx
0x18001e910  or      ebx, 80070000h
0x18001e916  mov     eax, ebx
0x18001e918  mov     rbx, [rsp+48h+arg_0]
0x18001e91d  add     rsp, 40h
0x18001e921  pop     rdi
0x18001e922  retn
```
