# CPITRSettings::SetMaxGlobalSize(PITR::PITR_SETTINGS_LEVEL,ulong)

- ea: `0x18001be00`
- end: `0x18001bf4d`
- name: `?SetMaxGlobalSize@CPITRSettings@@UEAAJW4PITR_SETTINGS_LEVEL@PITR@@K@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180009e04`
- `0x18001be00`
- `0x18001c130`
- `0x18001def0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beba`
- `WDSCORE!CurrentIP` at `0x18001bec2`
- `WDSCORE!CurrentIP` at `0x18001bec2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001bf28`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001bf28`

## string_xrefs

- `0x18001bf11`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001becb`: `SetMaxGlobalSize: Failed to update scheduled task. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRSettings::SetMaxGlobalSize(__int64 *a1, unsigned int a2, unsigned int a3)
{
  int v7; // esi
  __int64 v8; // rcx
  int v9; // ebp
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // [rsp+60h] [rbp-28h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    && !(*(unsigned int (__fastcall **)(__int64 *, _QWORD))(*a1 + 184))(a1, a2) )
  {
    return 2147946720LL;
  }
  v7 = CPITRSettings::SetSettingDWORD((__int64)a1, (__int64)L"MaxGlobalSize", a2, a3);
  if ( v7 >= 0 )
  {
    v8 = *a1;
    v13 = 1;
    (*(void (__fastcall **)(__int64 *, __int64, int *))(v8 + 160))(a1, 5, &v13);
    if ( a2 == v13 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1[3] + 56LL))(a1[3], 0);
      if ( v9 < 0 )
      {
        LastError = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(0x3000000u, "SetMaxGlobalSize: Failed to update scheduled task. Error: 0x%08X", v9);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          2845,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSettings::SetMaxGlobalSize",
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
0x18001be00  mov     [rsp+arg_18], rbx
0x18001be05  push    rbp
0x18001be06  push    rsi
0x18001be07  push    rdi
0x18001be08  sub     rsp, 70h
0x18001be0c  mov     rax, cs:__security_cookie
0x18001be13  xor     rax, rsp
0x18001be16  mov     [rsp+88h+var_20], rax
0x18001be1b  mov     esi, r8d
0x18001be1e  mov     edi, edx
0x18001be20  mov     rbx, rcx
0x18001be23  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001be2a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001be2f  test    al, al
0x18001be31  jz      short loc_18001BE55
0x18001be33  mov     rax, [rbx]
0x18001be36  mov     edx, edi
0x18001be38  mov     rcx, rbx
0x18001be3b  mov     rax, [rax+0B8h]
0x18001be42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be47  test    eax, eax
0x18001be49  jnz     short loc_18001BE55
0x18001be4b  mov     eax, 800710E0h
0x18001be50  jmp     loc_18001BF30
0x18001be55  mov     r9d, esi
0x18001be58  lea     rdx, aMaxglobalsize; "MaxGlobalSize"
0x18001be5f  mov     r8d, edi
0x18001be62  mov     rcx, rbx
0x18001be65  call    ?SetSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@K@Z; CPITRSettings::SetSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL,ulong)
0x18001be6a  mov     esi, eax
0x18001be6c  test    eax, eax
0x18001be6e  js      loc_18001BF2E
0x18001be74  mov     rcx, [rbx]
0x18001be77  lea     r8, [rsp+88h+var_28]
0x18001be7c  mov     edx, 5
0x18001be81  mov     [rsp+88h+var_28], 1
0x18001be89  mov     rax, [rcx+0A0h]
0x18001be90  mov     rcx, rbx
0x18001be93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be98  cmp     edi, [rsp+88h+var_28]
0x18001be9c  jnz     loc_18001BF2E
0x18001bea2  mov     rcx, [rbx+18h]
0x18001bea6  xor     edx, edx
0x18001bea8  mov     rax, [rcx]
0x18001beab  mov     rax, [rax+38h]
0x18001beaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beb4  mov     ebp, eax
0x18001beb6  test    eax, eax
0x18001beb8  jns     short loc_18001BF2E
0x18001beba  call    cs:__imp_GetLastError
0x18001bec0  mov     edi, eax
0x18001bec2  call    cs:__imp_CurrentIP
0x18001bec8  mov     r8d, ebp
0x18001becb  lea     rdx, aSetmaxglobalsi; "SetMaxGlobalSize: Failed to update sche"...
0x18001bed2  mov     ecx, 3000000h; unsigned int
0x18001bed7  mov     rbx, rax
0x18001beda  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001bedf  mov     [rsp+88h+var_38], 0
0x18001bee7  lea     rcx, aCpitrsettingsS_2; "CPITRSettings::SetMaxGlobalSize"
0x18001beee  mov     [rsp+88h+var_40], 0
0x18001bef7  lea     r8, aD; "D"
0x18001befe  mov     [rsp+88h+var_48], edi
0x18001bf02  xor     r9d, r9d
0x18001bf05  mov     [rsp+88h+var_50], rbx
0x18001bf0a  xor     edx, edx
0x18001bf0c  mov     [rsp+88h+var_58], rcx
0x18001bf11  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001bf18  mov     [rsp+88h+var_60], rcx
0x18001bf1d  mov     rcx, rax
0x18001bf20  mov     [rsp+88h+var_68], 0B1Dh
0x18001bf28  call    cs:__imp_WdsSetupLogMessageW
0x18001bf2e  mov     eax, esi
0x18001bf30  mov     rcx, [rsp+88h+var_20]
0x18001bf35  xor     rcx, rsp; StackCookie
0x18001bf38  call    __security_check_cookie
0x18001bf3d  mov     rbx, [rsp+88h+arg_18]
0x18001bf45  add     rsp, 70h
0x18001bf49  pop     rdi
0x18001bf4a  pop     rsi
0x18001bf4b  pop     rbp
0x18001bf4c  retn
```
