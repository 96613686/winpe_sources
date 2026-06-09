# PITRTelemetry_LogAllSnapshotSizes(PITR::IPITRBase *,_GUID const *)

- ea: `0x18000df6c`
- end: `0x18000e165`
- name: `?PITRTelemetry_LogAllSnapshotSizes@@YAXPEAUIPITRBase@PITR@@PEBU_GUID@@@Z`
- size: `505`
- prototype: `void __fastcall(struct PITR::IPITRBase *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000a4f0`

## callees

- `0x180004664`
- `0x18000de04`
- `0x18000df6c`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e065`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e13b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e065`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e13b`
- `WDSCORE!CurrentIP` at `0x18000e00d`
- `WDSCORE!CurrentIP` at `0x18000e0d5`
- `WDSCORE!CurrentIP` at `0x18000e00d`
- `WDSCORE!CurrentIP` at `0x18000e0d5`

## string_xrefs

- `0x18000dfd3`: `base\diagnosis\srt\pitr\task\dll\pitrtelemetry.cpp`
- `0x18000e10a`: `base\diagnosis\srt\pitr\task\dll\pitrtelemetry.cpp`

## pseudocode

```c
void __fastcall PITRTelemetry_LogAllSnapshotSizes(struct PITR::IPITRBase *a1, const struct _GUID *a2)
{
  __int64 v2; // rax
  int v4; // esi
  __int64 v5; // rcx
  int v6; // eax
  int v7; // esi
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  __int64 v16; // [rsp+60h] [rbp-48h] BYREF
  __int64 v17; // [rsp+68h] [rbp-40h] BYREF

  if ( a1 )
  {
    v2 = *(_QWORD *)a1;
    v16 = 0;
    v4 = (*(__int64 (__fastcall **)(struct PITR::IPITRBase *, __int64 *))(v2 + 32))(a1, &v16);
    if ( v4 >= 0 )
    {
      v5 = v16;
      if ( v16 )
      {
        while ( 1 )
        {
          v17 = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 8LL))(v5, &v17);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v11 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))v17)(v17);
            v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
            PITRTelemetry_GetIndividualSnapshotSize(v11, v12, a2);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
          }
          else
          {
            if ( v6 == -2147024637 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              return;
            }
            LastError = GetLastError();
            v9 = CurrentIP();
            v10 = ConstructPartialMsgW(
                    50331648,
                    "PITRTelemetry_LogAllSnapshotSizes: Enumeration GetNext failed. Hr=0x%08X",
                    v7);
            WdsSetupLogMessageW(
              v10,
              0,
              L"D",
              0,
              194,
              L"base\\diagnosis\\srt\\pitr\\task\\dll\\pitrtelemetry.cpp",
              L"PITRTelemetry_LogAllSnapshotSizes",
              v9,
              LastError,
              0,
              0);
          }
          v5 = v16;
        }
      }
    }
    v13 = GetLastError();
    v14 = CurrentIP();
    v15 = ConstructPartialMsgW(
            50331648,
            "PITRTelemetry_LogAllSnapshotSizes: Failed to obtain snapshot enumerator for size telemetry. Hr=0x%08X",
            v4);
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      181,
      L"base\\diagnosis\\srt\\pitr\\task\\dll\\pitrtelemetry.cpp",
      L"PITRTelemetry_LogAllSnapshotSizes",
      v14,
      v13,
      0,
      0);
  }
}

```

## disassembly

```asm
0x18000df6c  test    rcx, rcx
0x18000df6f  jz      locret_18000E164
0x18000df75  mov     [rsp+arg_10], rbx
0x18000df7a  push    rbp
0x18000df7b  push    rsi
0x18000df7c  push    rdi
0x18000df7d  push    r14
0x18000df7f  push    r15
0x18000df81  sub     rsp, 80h
0x18000df88  mov     rax, cs:__security_cookie
0x18000df8f  xor     rax, rsp
0x18000df92  mov     [rsp+0A8h+var_38], rax
0x18000df97  mov     rax, [rcx]
0x18000df9a  mov     r15, rdx
0x18000df9d  lea     rdx, [rsp+0A8h+var_48]
0x18000dfa2  mov     [rsp+0A8h+var_48], 0
0x18000dfab  mov     rax, [rax+20h]
0x18000dfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb4  mov     esi, eax
0x18000dfb6  test    eax, eax
0x18000dfb8  js      loc_18000E0CD
0x18000dfbe  mov     rcx, [rsp+0A8h+var_48]
0x18000dfc3  test    rcx, rcx
0x18000dfc6  jz      loc_18000E0CD
0x18000dfcc  lea     rbp, aPitrtelemetryL_1; "PITRTelemetry_LogAllSnapshotSizes"
0x18000dfd3  lea     r14, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\task\\dll\\"...
0x18000dfda  mov     [rsp+0A8h+var_40], 0
0x18000dfe3  lea     rdx, [rsp+0A8h+var_40]
0x18000dfe8  mov     rax, [rcx]
0x18000dfeb  mov     rax, [rax+8]
0x18000dfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff4  mov     esi, eax
0x18000dff6  test    eax, eax
0x18000dff8  jns     short loc_18000E06D
0x18000dffa  cmp     eax, 80070103h
0x18000dfff  jz      loc_18000E0BA
0x18000e005  call    cs:__imp_GetLastError
0x18000e00b  mov     edi, eax
0x18000e00d  call    cs:__imp_CurrentIP
0x18000e013  mov     r8d, esi
0x18000e016  lea     rdx, aPitrtelemetryL; "PITRTelemetry_LogAllSnapshotSizes: Enum"...
0x18000e01d  mov     ecx, 3000000h; unsigned int
0x18000e022  mov     rbx, rax
0x18000e025  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e02a  mov     [rsp+0A8h+var_58], 0
0x18000e032  lea     r8, aD; "D"
0x18000e039  mov     [rsp+0A8h+var_60], 0
0x18000e042  xor     r9d, r9d
0x18000e045  mov     [rsp+0A8h+var_68], edi
0x18000e049  xor     edx, edx
0x18000e04b  mov     [rsp+0A8h+var_70], rbx
0x18000e050  mov     rcx, rax
0x18000e053  mov     [rsp+0A8h+var_78], rbp
0x18000e058  mov     [rsp+0A8h+var_80], r14
0x18000e05d  mov     [rsp+0A8h+var_88], 0C2h
0x18000e065  call    cs:__imp_WdsSetupLogMessageW
0x18000e06b  jmp     short loc_18000E0B0
0x18000e06d  mov     rcx, [rsp+0A8h+var_40]
0x18000e072  mov     rax, [rcx]
0x18000e075  mov     rax, [rax]
0x18000e078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e07d  mov     rcx, [rsp+0A8h+var_40]
0x18000e082  mov     rbx, rax
0x18000e085  mov     rdx, [rcx]
0x18000e088  mov     rax, [rdx+20h]
0x18000e08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e091  mov     r8, r15; struct _GUID *
0x18000e094  mov     rdx, rax; __int64
0x18000e097  mov     rcx, rbx; unsigned __int16 *
0x18000e09a  call    ?PITRTelemetry_GetIndividualSnapshotSize@@YAXPEBG_JPEBU_GUID@@@Z; PITRTelemetry_GetIndividualSnapshotSize(ushort const *,__int64,_GUID const *)
0x18000e09f  mov     rcx, [rsp+0A8h+var_40]
0x18000e0a4  mov     rax, [rcx]
0x18000e0a7  mov     rax, [rax+40h]
0x18000e0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b0  mov     rcx, [rsp+0A8h+var_48]
0x18000e0b5  jmp     loc_18000DFDA
0x18000e0ba  mov     rcx, [rsp+0A8h+var_48]
0x18000e0bf  mov     rax, [rcx]
0x18000e0c2  mov     rax, [rax+10h]
0x18000e0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0cb  jmp     short loc_18000E141
0x18000e0cd  call    cs:__imp_GetLastError
0x18000e0d3  mov     edi, eax
0x18000e0d5  call    cs:__imp_CurrentIP
0x18000e0db  mov     r8d, esi
0x18000e0de  lea     rdx, aPitrtelemetryL_0; "PITRTelemetry_LogAllSnapshotSizes: Fail"...
0x18000e0e5  mov     ecx, 3000000h; unsigned int
0x18000e0ea  mov     rbx, rax
0x18000e0ed  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e0f2  mov     [rsp+0A8h+var_58], 0
0x18000e0fa  lea     rbp, aPitrtelemetryL_1; "PITRTelemetry_LogAllSnapshotSizes"
0x18000e101  mov     [rsp+0A8h+var_60], 0
0x18000e10a  lea     r14, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\task\\dll\\"...
0x18000e111  mov     [rsp+0A8h+var_68], edi
0x18000e115  lea     r8, aD; "D"
0x18000e11c  mov     [rsp+0A8h+var_70], rbx
0x18000e121  xor     r9d, r9d
0x18000e124  mov     [rsp+0A8h+var_78], rbp
0x18000e129  xor     edx, edx
0x18000e12b  mov     [rsp+0A8h+var_80], r14
0x18000e130  mov     rcx, rax
0x18000e133  mov     [rsp+0A8h+var_88], 0B5h
0x18000e13b  call    cs:__imp_WdsSetupLogMessageW
0x18000e141  mov     rcx, [rsp+0A8h+var_38]
0x18000e146  xor     rcx, rsp; StackCookie
0x18000e149  call    __security_check_cookie
0x18000e14e  mov     rbx, [rsp+0A8h+arg_10]
0x18000e156  add     rsp, 80h
0x18000e15d  pop     r15
0x18000e15f  pop     r14
0x18000e161  pop     rdi
0x18000e162  pop     rsi
0x18000e163  pop     rbp
0x18000e164  retn
```
