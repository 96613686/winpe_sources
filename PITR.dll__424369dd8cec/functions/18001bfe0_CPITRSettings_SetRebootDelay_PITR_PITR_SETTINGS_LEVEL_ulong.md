# CPITRSettings::SetRebootDelay(PITR::PITR_SETTINGS_LEVEL,ulong)

- ea: `0x18001bfe0`
- end: `0x18001c127`
- name: `?SetRebootDelay@CPITRSettings@@UEAAJW4PITR_SETTINGS_LEVEL@PITR@@K@Z`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180009e04`
- `0x18001bfe0`
- `0x18001c130`
- `0x18001def0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c094`
- `WDSCORE!CurrentIP` at `0x18001c09c`
- `WDSCORE!CurrentIP` at `0x18001c09c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001c102`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001c102`

## string_xrefs

- `0x18001c0eb`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001c0a5`: `SetRebootDelay: Failed to update scheduled task. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRSettings::SetRebootDelay(__int64 *a1, unsigned int a2, unsigned int a3)
{
  int v7; // esi
  __int64 v8; // rcx
  int v9; // ebp
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // [rsp+60h] [rbp-28h] BYREF

  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    && !(*(unsigned int (__fastcall **)(__int64 *, _QWORD))(*a1 + 56))(a1, a2) )
  {
    return 2147946720LL;
  }
  v7 = CPITRSettings::SetSettingDWORD((__int64)a1, (__int64)L"RebootDelay", a2, a3);
  if ( v7 >= 0 )
  {
    v8 = *a1;
    v13 = 1;
    (*(void (__fastcall **)(__int64 *, __int64, int *))(v8 + 32))(a1, 5, &v13);
    if ( a2 == v13 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1[3] + 56LL))(a1[3], 0);
      if ( v9 < 0 )
      {
        LastError = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(50331648, "SetRebootDelay: Failed to update scheduled task. Error: 0x%08X", v9);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          2586,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSettings::SetRebootDelay",
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
0x18001bfe0  mov     [rsp+arg_18], rbx
0x18001bfe5  push    rbp
0x18001bfe6  push    rsi
0x18001bfe7  push    rdi
0x18001bfe8  sub     rsp, 70h
0x18001bfec  mov     rax, cs:__security_cookie
0x18001bff3  xor     rax, rsp
0x18001bff6  mov     [rsp+88h+var_20], rax
0x18001bffb  mov     esi, r8d
0x18001bffe  mov     edi, edx
0x18001c000  mov     rbx, rcx
0x18001c003  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001c00a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001c00f  test    al, al
0x18001c011  jz      short loc_18001C032
0x18001c013  mov     rax, [rbx]
0x18001c016  mov     edx, edi
0x18001c018  mov     rcx, rbx
0x18001c01b  mov     rax, [rax+38h]
0x18001c01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c024  test    eax, eax
0x18001c026  jnz     short loc_18001C032
0x18001c028  mov     eax, 800710E0h
0x18001c02d  jmp     loc_18001C10A
0x18001c032  mov     r9d, esi
0x18001c035  lea     rdx, aRebootdelay; "RebootDelay"
0x18001c03c  mov     r8d, edi
0x18001c03f  mov     rcx, rbx
0x18001c042  call    ?SetSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@K@Z; CPITRSettings::SetSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL,ulong)
0x18001c047  mov     esi, eax
0x18001c049  test    eax, eax
0x18001c04b  js      loc_18001C108
0x18001c051  mov     rcx, [rbx]
0x18001c054  lea     r8, [rsp+88h+var_28]
0x18001c059  mov     edx, 5
0x18001c05e  mov     [rsp+88h+var_28], 1
0x18001c066  mov     rax, [rcx+20h]
0x18001c06a  mov     rcx, rbx
0x18001c06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c072  cmp     edi, [rsp+88h+var_28]
0x18001c076  jnz     loc_18001C108
0x18001c07c  mov     rcx, [rbx+18h]
0x18001c080  xor     edx, edx
0x18001c082  mov     rax, [rcx]
0x18001c085  mov     rax, [rax+38h]
0x18001c089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c08e  mov     ebp, eax
0x18001c090  test    eax, eax
0x18001c092  jns     short loc_18001C108
0x18001c094  call    cs:__imp_GetLastError
0x18001c09a  mov     edi, eax
0x18001c09c  call    cs:__imp_CurrentIP
0x18001c0a2  mov     r8d, ebp
0x18001c0a5  lea     rdx, aSetrebootdelay; "SetRebootDelay: Failed to update schedu"...
0x18001c0ac  mov     ecx, 3000000h; unsigned int
0x18001c0b1  mov     rbx, rax
0x18001c0b4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001c0b9  mov     [rsp+88h+var_38], 0
0x18001c0c1  lea     rcx, aCpitrsettingsS_0; "CPITRSettings::SetRebootDelay"
0x18001c0c8  mov     [rsp+88h+var_40], 0
0x18001c0d1  lea     r8, aD; "D"
0x18001c0d8  mov     [rsp+88h+var_48], edi
0x18001c0dc  xor     r9d, r9d
0x18001c0df  mov     [rsp+88h+var_50], rbx
0x18001c0e4  xor     edx, edx
0x18001c0e6  mov     [rsp+88h+var_58], rcx
0x18001c0eb  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001c0f2  mov     [rsp+88h+var_60], rcx
0x18001c0f7  mov     rcx, rax
0x18001c0fa  mov     [rsp+88h+var_68], 0A1Ah
0x18001c102  call    cs:__imp_WdsSetupLogMessageW
0x18001c108  mov     eax, esi
0x18001c10a  mov     rcx, [rsp+88h+var_20]
0x18001c10f  xor     rcx, rsp; StackCookie
0x18001c112  call    __security_check_cookie
0x18001c117  mov     rbx, [rsp+88h+arg_18]
0x18001c11f  add     rsp, 70h
0x18001c123  pop     rdi
0x18001c124  pop     rsi
0x18001c125  pop     rbp
0x18001c126  retn
```
