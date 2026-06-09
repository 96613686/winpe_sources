# InternalGetSettingAndSendData(TelemetrySession *,SrSettings::ISrSettings *,ushort const *)

- ea: `0x18000220c`
- end: `0x18000244d`
- name: `?InternalGetSettingAndSendData@@YAJPEAVTelemetrySession@@PEAUISrSettings@SrSettings@@PEBG@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct TelemetrySession *this, struct SrSettings::ISrSettings *, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180003140`

## callees

- `0x1800021c0`
- `0x18000220c`
- `0x180004344`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002424`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002424`
- `KERNEL32!GetLastError` at `0x18000223d`
- `KERNEL32!GetLastError` at `0x1800022ce`
- `KERNEL32!GetLastError` at `0x18000232b`
- `KERNEL32!GetLastError` at `0x18000239d`
- `KERNEL32!GetLastError` at `0x18000223d`
- `KERNEL32!GetLastError` at `0x1800022ce`
- `KERNEL32!GetLastError` at `0x18000232b`
- `KERNEL32!GetLastError` at `0x18000239d`
- `WDSCORE!CurrentIP` at `0x180002245`
- `WDSCORE!CurrentIP` at `0x1800022d6`
- `WDSCORE!CurrentIP` at `0x180002333`
- `WDSCORE!CurrentIP` at `0x1800023a5`
- `WDSCORE!CurrentIP` at `0x180002245`
- `WDSCORE!CurrentIP` at `0x1800022d6`
- `WDSCORE!CurrentIP` at `0x180002333`
- `WDSCORE!CurrentIP` at `0x1800023a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800022ab`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002397`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002404`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800022ab`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002397`
- `WDSCORE!WdsSetupLogMessageW` at `0x180002404`

## string_xrefs

- `0x18000226a`: `base\diagnosis\srt\setuprecoverydatatask\qmrdatatask\dll\src\qmrdatatask.cpp`
- `0x1800022fe`: `base\diagnosis\srt\setuprecoverydatatask\qmrdatatask\dll\src\qmrdatatask.cpp`
- `0x18000235d`: `base\diagnosis\srt\setuprecoverydatatask\qmrdatatask\dll\src\qmrdatatask.cpp`
- `0x1800023ca`: `base\diagnosis\srt\setuprecoverydatatask\qmrdatatask\dll\src\qmrdatatask.cpp`

## pseudocode

```c
__int64 __fastcall InternalGetSettingAndSendData(
        struct TelemetrySession *this,
        struct SrSettings::ISrSettings *a2,
        const char *a3)
{
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int v9; // esi
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  unsigned __int16 *v18; // [rsp+60h] [rbp-38h] BYREF

  v18 = 0;
  LastError = GetLastError();
  v7 = CurrentIP();
  v8 = ConstructPartialMsgW(0x4000000u, "InternalGetSettingAndSendData: Querying setting: [%s]", a3);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    204,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\qmrdatatask\\dll\\src\\qmrdatatask.cpp",
    L"InternalGetSettingAndSendData",
    v7,
    LastError,
    0,
    0);
  v9 = (*(__int64 (__fastcall **)(struct SrSettings::ISrSettings *, const char *, unsigned __int16 **))(*(_QWORD *)a2 + 16LL))(
         a2,
         a3,
         &v18);
  v10 = GetLastError();
  v11 = CurrentIP();
  if ( v9 >= 0 )
  {
    v13 = ConstructPartialMsgW(
            0x4000000u,
            "InternalGetSettingAndSendData: Queried setting [%s] and found value [%s]",
            a3,
            (const char *)v18);
    WdsSetupLogMessageW(
      v13,
      0,
      L"D",
      0,
      212,
      L"base\\diagnosis\\srt\\setuprecoverydatatask\\qmrdatatask\\dll\\src\\qmrdatatask.cpp",
      L"InternalGetSettingAndSendData",
      v11,
      v10,
      0,
      0);
  }
  else
  {
    v12 = ConstructPartialMsgW(0x2000000u, "InternalGetSettingAndSendData: Failed to query %s. Error: 0x%08X", a3, v9);
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      208,
      L"base\\diagnosis\\srt\\setuprecoverydatatask\\qmrdatatask\\dll\\src\\qmrdatatask.cpp",
      L"InternalGetSettingAndSendData",
      v11,
      v10,
      0,
      0);
  }
  v14 = GetLastError();
  v15 = CurrentIP();
  v16 = ConstructPartialMsgW(0x4000000u, "InternalGetSettingAndSendData: Sending telemetry for setting: [%s]", a3);
  WdsSetupLogMessageW(
    v16,
    0,
    L"D",
    0,
    215,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\qmrdatatask\\dll\\src\\qmrdatatask.cpp",
    L"InternalGetSettingAndSendData",
    v15,
    v14,
    0,
    0);
  TelemetrySession::TraceQMRSetting(this, (const unsigned __int16 *)a3, v18);
  if ( v18 )
    operator delete[](v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000220c  mov     [rsp+arg_18], rbx
0x180002211  push    rbp
0x180002212  push    rsi
0x180002213  push    rdi
0x180002214  push    r13
0x180002216  push    r14
0x180002218  sub     rsp, 70h
0x18000221c  mov     rax, cs:__security_cookie
0x180002223  xor     rax, rsp
0x180002226  mov     [rsp+98h+var_30], rax
0x18000222b  mov     rbp, r8
0x18000222e  mov     [rsp+98h+var_38], 0
0x180002237  mov     rsi, rdx
0x18000223a  mov     r14, rcx
0x18000223d  call    cs:__imp_GetLastError
0x180002243  mov     edi, eax
0x180002245  call    cs:__imp_CurrentIP
0x18000224b  mov     r8, rbp
0x18000224e  lea     rdx, aInternalgetset; "InternalGetSettingAndSendData: Querying"...
0x180002255  mov     ecx, 4000000h; unsigned int
0x18000225a  mov     rbx, rax
0x18000225d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002262  mov     [rsp+98h+var_48], 0
0x18000226a  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x180002271  mov     [rsp+98h+var_50], 0
0x18000227a  lea     r13, aInternalgetset_3; "InternalGetSettingAndSendData"
0x180002281  mov     [rsp+98h+var_58], edi
0x180002285  lea     r8, aD_0; "D"
0x18000228c  mov     [rsp+98h+var_60], rbx
0x180002291  xor     r9d, r9d
0x180002294  mov     [rsp+98h+var_68], r13
0x180002299  xor     edx, edx
0x18000229b  mov     [rsp+98h+var_70], rcx
0x1800022a0  mov     rcx, rax
0x1800022a3  mov     [rsp+98h+var_78], 0CCh
0x1800022ab  call    cs:__imp_WdsSetupLogMessageW
0x1800022b1  mov     rax, [rsi]
0x1800022b4  lea     r8, [rsp+98h+var_38]
0x1800022b9  mov     rdx, rbp
0x1800022bc  mov     rcx, rsi
0x1800022bf  mov     rax, [rax+10h]
0x1800022c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c8  mov     esi, eax
0x1800022ca  test    eax, eax
0x1800022cc  jns     short loc_18000232B
0x1800022ce  call    cs:__imp_GetLastError
0x1800022d4  mov     edi, eax
0x1800022d6  call    cs:__imp_CurrentIP
0x1800022dc  mov     r9d, esi
0x1800022df  lea     rdx, aInternalgetset_0; "InternalGetSettingAndSendData: Failed t"...
0x1800022e6  mov     r8, rbp
0x1800022e9  mov     ecx, 2000000h; unsigned int
0x1800022ee  mov     rbx, rax
0x1800022f1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800022f6  mov     [rsp+98h+var_48], 0
0x1800022fe  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x180002305  mov     [rsp+98h+var_50], 0
0x18000230e  mov     [rsp+98h+var_58], edi
0x180002312  mov     [rsp+98h+var_60], rbx
0x180002317  mov     [rsp+98h+var_68], r13
0x18000231c  mov     [rsp+98h+var_70], rcx
0x180002321  mov     [rsp+98h+var_78], 0D0h
0x180002329  jmp     short loc_180002388
0x18000232b  call    cs:__imp_GetLastError
0x180002331  mov     edi, eax
0x180002333  call    cs:__imp_CurrentIP
0x180002339  mov     r9, [rsp+98h+var_38]
0x18000233e  lea     rdx, aInternalgetset_2; "InternalGetSettingAndSendData: Queried "...
0x180002345  mov     r8, rbp
0x180002348  mov     ecx, 4000000h; unsigned int
0x18000234d  mov     rbx, rax
0x180002350  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002355  mov     [rsp+98h+var_48], 0
0x18000235d  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x180002364  mov     [rsp+98h+var_50], 0
0x18000236d  mov     [rsp+98h+var_58], edi
0x180002371  mov     [rsp+98h+var_60], rbx
0x180002376  mov     [rsp+98h+var_68], r13
0x18000237b  mov     [rsp+98h+var_70], rcx
0x180002380  mov     [rsp+98h+var_78], 0D4h
0x180002388  xor     r9d, r9d
0x18000238b  lea     r8, aD_0; "D"
0x180002392  xor     edx, edx
0x180002394  mov     rcx, rax
0x180002397  call    cs:__imp_WdsSetupLogMessageW
0x18000239d  call    cs:__imp_GetLastError
0x1800023a3  mov     edi, eax
0x1800023a5  call    cs:__imp_CurrentIP
0x1800023ab  mov     r8, rbp
0x1800023ae  lea     rdx, aInternalgetset_1; "InternalGetSettingAndSendData: Sending "...
0x1800023b5  mov     ecx, 4000000h; unsigned int
0x1800023ba  mov     rbx, rax
0x1800023bd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800023c2  mov     [rsp+98h+var_48], 0
0x1800023ca  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x1800023d1  mov     [rsp+98h+var_50], 0
0x1800023da  lea     r8, aD_0; "D"
0x1800023e1  mov     [rsp+98h+var_58], edi
0x1800023e5  xor     r9d, r9d
0x1800023e8  mov     [rsp+98h+var_60], rbx
0x1800023ed  xor     edx, edx
0x1800023ef  mov     [rsp+98h+var_68], r13
0x1800023f4  mov     [rsp+98h+var_70], rcx
0x1800023f9  mov     rcx, rax
0x1800023fc  mov     [rsp+98h+var_78], 0D7h
0x180002404  call    cs:__imp_WdsSetupLogMessageW
0x18000240a  mov     r8, [rsp+98h+var_38]; unsigned __int16 *
0x18000240f  mov     rdx, rbp; unsigned __int16 *
0x180002412  mov     rcx, r14; this
0x180002415  call    ?TraceQMRSetting@TelemetrySession@@QEBAXPEBG0@Z; TelemetrySession::TraceQMRSetting(ushort const *,ushort const *)
0x18000241a  mov     rcx, [rsp+98h+var_38]
0x18000241f  test    rcx, rcx
0x180002422  jz      short loc_18000242A
0x180002424  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000242a  mov     eax, esi
0x18000242c  mov     rcx, [rsp+98h+var_30]
0x180002431  xor     rcx, rsp; StackCookie
0x180002434  call    __security_check_cookie
0x180002439  mov     rbx, [rsp+98h+arg_18]
0x180002441  add     rsp, 70h
0x180002445  pop     r14
0x180002447  pop     r13
0x180002449  pop     rdi
0x18000244a  pop     rsi
0x18000244b  pop     rbp
0x18000244c  retn
```
