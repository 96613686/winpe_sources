# CPITRSettings::SetSnapshotInterval(PITR::PITR_SETTINGS_LEVEL,ulong)

- ea: `0x18001c230`
- end: `0x18001c377`
- name: `?SetSnapshotInterval@CPITRSettings@@UEAAJW4PITR_SETTINGS_LEVEL@PITR@@K@Z`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180009e04`
- `0x18001c130`
- `0x18001c230`
- `0x18001def0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2e4`
- `WDSCORE!CurrentIP` at `0x18001c2ec`
- `WDSCORE!CurrentIP` at `0x18001c2ec`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001c352`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001c352`

## string_xrefs

- `0x18001c33b`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001c2f5`: `SetSnapshotInterval: Failed to update scheduled task. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRSettings::SetSnapshotInterval(__int64 *a1, unsigned int a2, unsigned int a3)
{
  int v7; // esi
  __int64 v8; // rcx
  int v9; // ebp
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // [rsp+60h] [rbp-28h] BYREF

  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    && !(*(unsigned int (__fastcall **)(__int64 *, _QWORD))(*a1 + 88))(a1, a2) )
  {
    return 2147946720LL;
  }
  v7 = CPITRSettings::SetSettingDWORD((__int64)a1, (__int64)L"SnapshotInterval", a2, a3);
  if ( v7 >= 0 )
  {
    v8 = *a1;
    v13 = 1;
    (*(void (__fastcall **)(__int64 *, __int64, int *))(v8 + 64))(a1, 5, &v13);
    if ( a2 == v13 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1[3] + 56LL))(a1[3], 0);
      if ( v9 < 0 )
      {
        LastError = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(50331648, "SetSnapshotInterval: Failed to update scheduled task. Error: 0x%08X", v9);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          2661,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSettings::SetSnapshotInterval",
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
0x18001c230  mov     [rsp+arg_18], rbx
0x18001c235  push    rbp
0x18001c236  push    rsi
0x18001c237  push    rdi
0x18001c238  sub     rsp, 70h
0x18001c23c  mov     rax, cs:__security_cookie
0x18001c243  xor     rax, rsp
0x18001c246  mov     [rsp+88h+var_20], rax
0x18001c24b  mov     esi, r8d
0x18001c24e  mov     edi, edx
0x18001c250  mov     rbx, rcx
0x18001c253  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18001c25a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001c25f  test    al, al
0x18001c261  jz      short loc_18001C282
0x18001c263  mov     rax, [rbx]
0x18001c266  mov     edx, edi
0x18001c268  mov     rcx, rbx
0x18001c26b  mov     rax, [rax+58h]
0x18001c26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c274  test    eax, eax
0x18001c276  jnz     short loc_18001C282
0x18001c278  mov     eax, 800710E0h
0x18001c27d  jmp     loc_18001C35A
0x18001c282  mov     r9d, esi
0x18001c285  lea     rdx, aSnapshotinterv; "SnapshotInterval"
0x18001c28c  mov     r8d, edi
0x18001c28f  mov     rcx, rbx
0x18001c292  call    ?SetSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@K@Z; CPITRSettings::SetSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL,ulong)
0x18001c297  mov     esi, eax
0x18001c299  test    eax, eax
0x18001c29b  js      loc_18001C358
0x18001c2a1  mov     rcx, [rbx]
0x18001c2a4  lea     r8, [rsp+88h+var_28]
0x18001c2a9  mov     edx, 5
0x18001c2ae  mov     [rsp+88h+var_28], 1
0x18001c2b6  mov     rax, [rcx+40h]
0x18001c2ba  mov     rcx, rbx
0x18001c2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c2  cmp     edi, [rsp+88h+var_28]
0x18001c2c6  jnz     loc_18001C358
0x18001c2cc  mov     rcx, [rbx+18h]
0x18001c2d0  xor     edx, edx
0x18001c2d2  mov     rax, [rcx]
0x18001c2d5  mov     rax, [rax+38h]
0x18001c2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2de  mov     ebp, eax
0x18001c2e0  test    eax, eax
0x18001c2e2  jns     short loc_18001C358
0x18001c2e4  call    cs:__imp_GetLastError
0x18001c2ea  mov     edi, eax
0x18001c2ec  call    cs:__imp_CurrentIP
0x18001c2f2  mov     r8d, ebp
0x18001c2f5  lea     rdx, aSetsnapshotint; "SetSnapshotInterval: Failed to update s"...
0x18001c2fc  mov     ecx, 3000000h; unsigned int
0x18001c301  mov     rbx, rax
0x18001c304  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001c309  mov     [rsp+88h+var_38], 0
0x18001c311  lea     rcx, aCpitrsettingsS; "CPITRSettings::SetSnapshotInterval"
0x18001c318  mov     [rsp+88h+var_40], 0
0x18001c321  lea     r8, aD; "D"
0x18001c328  mov     [rsp+88h+var_48], edi
0x18001c32c  xor     r9d, r9d
0x18001c32f  mov     [rsp+88h+var_50], rbx
0x18001c334  xor     edx, edx
0x18001c336  mov     [rsp+88h+var_58], rcx
0x18001c33b  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001c342  mov     [rsp+88h+var_60], rcx
0x18001c347  mov     rcx, rax
0x18001c34a  mov     [rsp+88h+var_68], 0A65h
0x18001c352  call    cs:__imp_WdsSetupLogMessageW
0x18001c358  mov     eax, esi
0x18001c35a  mov     rcx, [rsp+88h+var_20]
0x18001c35f  xor     rcx, rsp; StackCookie
0x18001c362  call    __security_check_cookie
0x18001c367  mov     rbx, [rsp+88h+arg_18]
0x18001c36f  add     rsp, 70h
0x18001c373  pop     rdi
0x18001c374  pop     rsi
0x18001c375  pop     rbp
0x18001c376  retn
```
