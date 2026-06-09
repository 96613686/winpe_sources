# CPITRSettings::SetFeatureActive(PITR::PITR_SETTINGS_LEVEL,int)

- ea: `0x18001b980`
- end: `0x18001baea`
- name: `?SetFeatureActive@CPITRSettings@@UEAAJW4PITR_SETTINGS_LEVEL@PITR@@H@Z`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD **, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180009e04`
- `0x18001b980`
- `0x18001c130`
- `0x18001def0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba3d`
- `WDSCORE!CurrentIP` at `0x18001ba45`
- `WDSCORE!CurrentIP` at `0x18001ba45`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001baab`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001baab`

## string_xrefs

- `0x18001ba94`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001ba4e`: `SetFeatureActive: Failed to update scheduled task. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRSettings::SetFeatureActive(_QWORD **a1, unsigned int a2, int a3)
{
  int v7; // esi
  void (__fastcall **v8)(_QWORD **, __int64, int *); // rcx
  int v9; // ebp
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // [rsp+60h] [rbp-28h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    return CPITRSettings::SetSettingDWORD((__int64)a1, (__int64)L"Active", a2, a3 != 0);
  if ( !((unsigned int (__fastcall *)(_QWORD **, _QWORD))(*a1)[3])(a1, a2) )
    return 2147946720LL;
  v7 = CPITRSettings::SetSettingDWORD((__int64)a1, (__int64)L"Active", a2, a3 != 0);
  if ( v7 >= 0 )
  {
    v8 = (void (__fastcall **)(_QWORD **, __int64, int *))*a1;
    v13 = 1;
    (*v8)(a1, 5, &v13);
    if ( a2 == v13 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*a1[3] + 56LL))(a1[3], 0);
      if ( v9 < 0 )
      {
        LastError = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(0x3000000u, "SetFeatureActive: Failed to update scheduled task. Error: 0x%08X", v9);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          2506,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSettings::SetFeatureActive",
          v11,
          LastError,
          0,
          0);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b980  mov     [rsp+arg_10], rbx
0x18001b985  push    rbp
0x18001b986  push    rsi
0x18001b987  push    rdi
0x18001b988  sub     rsp, 70h
0x18001b98c  mov     rax, cs:__security_cookie
0x18001b993  xor     rax, rsp
0x18001b996  mov     [rsp+88h+var_20], rax
0x18001b99b  mov     esi, r8d
0x18001b99e  mov     edi, edx
0x18001b9a0  mov     rbx, rcx
0x18001b9a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001b9aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001b9af  mov     rcx, rbx
0x18001b9b2  test    al, al
0x18001b9b4  jz      loc_18001BAB5
0x18001b9ba  mov     rax, [rbx]
0x18001b9bd  mov     edx, edi
0x18001b9bf  mov     rax, [rax+18h]
0x18001b9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9c8  test    eax, eax
0x18001b9ca  jnz     short loc_18001B9D6
0x18001b9cc  mov     eax, 800710E0h
0x18001b9d1  jmp     loc_18001BACD
0x18001b9d6  xor     r9d, r9d
0x18001b9d9  lea     rdx, aActive; "Active"
0x18001b9e0  test    esi, esi
0x18001b9e2  mov     r8d, edi
0x18001b9e5  mov     rcx, rbx
0x18001b9e8  setnz   r9b
0x18001b9ec  call    ?SetSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@K@Z; CPITRSettings::SetSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL,ulong)
0x18001b9f1  mov     esi, eax
0x18001b9f3  test    eax, eax
0x18001b9f5  js      loc_18001BAB1
0x18001b9fb  mov     rcx, [rbx]
0x18001b9fe  lea     r8, [rsp+88h+var_28]
0x18001ba03  mov     edx, 5
0x18001ba08  mov     [rsp+88h+var_28], 1
0x18001ba10  mov     rax, [rcx]
0x18001ba13  mov     rcx, rbx
0x18001ba16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba1b  cmp     edi, [rsp+88h+var_28]
0x18001ba1f  jnz     loc_18001BAB1
0x18001ba25  mov     rcx, [rbx+18h]
0x18001ba29  xor     edx, edx
0x18001ba2b  mov     rax, [rcx]
0x18001ba2e  mov     rax, [rax+38h]
0x18001ba32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba37  mov     ebp, eax
0x18001ba39  test    eax, eax
0x18001ba3b  jns     short loc_18001BAB1
0x18001ba3d  call    cs:__imp_GetLastError
0x18001ba43  mov     edi, eax
0x18001ba45  call    cs:__imp_CurrentIP
0x18001ba4b  mov     r8d, ebp
0x18001ba4e  lea     rdx, aSetfeatureacti; "SetFeatureActive: Failed to update sche"...
0x18001ba55  mov     ecx, 3000000h; unsigned int
0x18001ba5a  mov     rbx, rax
0x18001ba5d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001ba62  mov     [rsp+88h+var_38], 0
0x18001ba6a  lea     rcx, aCpitrsettingsS_1; "CPITRSettings::SetFeatureActive"
0x18001ba71  mov     [rsp+88h+var_40], 0
0x18001ba7a  lea     r8, aD; "D"
0x18001ba81  mov     [rsp+88h+var_48], edi
0x18001ba85  xor     r9d, r9d
0x18001ba88  mov     [rsp+88h+var_50], rbx
0x18001ba8d  xor     edx, edx
0x18001ba8f  mov     [rsp+88h+var_58], rcx
0x18001ba94  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001ba9b  mov     [rsp+88h+var_60], rcx
0x18001baa0  mov     rcx, rax
0x18001baa3  mov     [rsp+88h+var_68], 9CAh
0x18001baab  call    cs:__imp_WdsSetupLogMessageW
0x18001bab1  mov     eax, esi
0x18001bab3  jmp     short loc_18001BACD
0x18001bab5  xor     r9d, r9d
0x18001bab8  lea     rdx, aActive; "Active"
0x18001babf  test    esi, esi
0x18001bac1  mov     r8d, edi
0x18001bac4  setnz   r9b
0x18001bac8  call    ?SetSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@K@Z; CPITRSettings::SetSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL,ulong)
0x18001bacd  mov     rcx, [rsp+88h+var_20]
0x18001bad2  xor     rcx, rsp; StackCookie
0x18001bad5  call    __security_check_cookie
0x18001bada  mov     rbx, [rsp+88h+arg_10]
0x18001bae2  add     rsp, 70h
0x18001bae6  pop     rdi
0x18001bae7  pop     rsi
0x18001bae8  pop     rbp
0x18001bae9  retn
```
