# PITRTelemetry_EnumerateSnapshotIds(PITR::IPITRBase *,void (*)(ushort const *,void *),void *)

- ea: `0x18000da94`
- end: `0x18000dc88`
- name: `?PITRTelemetry_EnumerateSnapshotIds@@YAXPEAUIPITRBase@PITR@@P6AXPEBGPEAX@Z2@Z`
- size: `500`
- prototype: `void __fastcall(struct PITR::IPITRBase *, void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000a4f0`

## callees

- `0x180004664`
- `0x18000da94`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbf3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db91`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dc5a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db91`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dc5a`
- `WDSCORE!CurrentIP` at `0x18000db40`
- `WDSCORE!CurrentIP` at `0x18000dbfb`
- `WDSCORE!CurrentIP` at `0x18000db40`
- `WDSCORE!CurrentIP` at `0x18000dbfb`

## string_xrefs

- `0x18000db0a`: `base\diagnosis\srt\pitr\task\dll\pitrtelemetry.cpp`
- `0x18000dc29`: `base\diagnosis\srt\pitr\task\dll\pitrtelemetry.cpp`

## pseudocode

```c
void __fastcall PITRTelemetry_EnumerateSnapshotIds(
        struct PITR::IPITRBase *a1,
        void (*a2)(const unsigned __int16 *, void *),
        void *a3)
{
  __int64 v5; // rax
  int v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  int v9; // esi
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  _WORD *v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  __int64 v17; // [rsp+60h] [rbp-58h] BYREF
  __int64 v18; // [rsp+68h] [rbp-50h] BYREF

  if ( a1 && a2 )
  {
    v5 = *(_QWORD *)a1;
    v17 = 0;
    v6 = (*(__int64 (__fastcall **)(struct PITR::IPITRBase *, __int64 *))(v5 + 32))(a1, &v17);
    if ( v6 >= 0 )
    {
      v7 = v17;
      if ( v17 )
      {
        while ( 1 )
        {
          v18 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, &v18);
          v9 = v8;
          if ( v8 >= 0 )
          {
            v13 = (_WORD *)(**(__int64 (__fastcall ***)(__int64))v18)(v18);
            if ( !v13 || !*v13 )
              v13 = 0;
            ((void (__fastcall *)(_WORD *, void *))a2)(v13, a3);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18);
          }
          else
          {
            if ( v8 == -2147024637 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              return;
            }
            LastError = GetLastError();
            v11 = CurrentIP();
            v12 = ConstructPartialMsgW(
                    50331648,
                    "PITRTelemetry_EnumerateSnapshotIds: Enumeration GetNext failed. Hr=0x%08X",
                    v9);
            WdsSetupLogMessageW(
              v12,
              0,
              L"D",
              0,
              156,
              L"base\\diagnosis\\srt\\pitr\\task\\dll\\pitrtelemetry.cpp",
              L"PITRTelemetry_EnumerateSnapshotIds",
              v11,
              LastError,
              0,
              0);
          }
          v7 = v17;
        }
      }
    }
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            50331648,
            "PITRTelemetry_EnumerateSnapshotIds: Failed to obtain snapshot enumerator. Hr=0x%08X",
            v6);
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      143,
      L"base\\diagnosis\\srt\\pitr\\task\\dll\\pitrtelemetry.cpp",
      L"PITRTelemetry_EnumerateSnapshotIds",
      v15,
      v14,
      0,
      0);
  }
}

```

## disassembly

```asm
0x18000da94  test    rcx, rcx
0x18000da97  jz      locret_18000DC87
0x18000da9d  mov     [rsp+arg_18], rbx
0x18000daa2  push    rbp
0x18000daa3  push    rsi
0x18000daa4  push    rdi
0x18000daa5  push    r12
0x18000daa7  push    r13
0x18000daa9  push    r14
0x18000daab  push    r15
0x18000daad  sub     rsp, 80h
0x18000dab4  mov     rax, cs:__security_cookie
0x18000dabb  xor     rax, rsp
0x18000dabe  mov     [rsp+0B8h+var_48], rax
0x18000dac3  xor     r13d, r13d
0x18000dac6  mov     r12, r8
0x18000dac9  mov     rbp, rdx
0x18000dacc  test    rdx, rdx
0x18000dacf  jz      loc_18000DC60
0x18000dad5  mov     rax, [rcx]
0x18000dad8  lea     rdx, [rsp+0B8h+var_58]
0x18000dadd  mov     [rsp+0B8h+var_58], r13
0x18000dae2  mov     rax, [rax+20h]
0x18000dae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daeb  mov     esi, eax
0x18000daed  test    eax, eax
0x18000daef  js      loc_18000DBF3
0x18000daf5  mov     rcx, [rsp+0B8h+var_58]
0x18000dafa  test    rcx, rcx
0x18000dafd  jz      loc_18000DBF3
0x18000db03  lea     r14, aPitrtelemetryE_0; "PITRTelemetry_EnumerateSnapshotIds"
0x18000db0a  lea     r15, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\task\\dll\\"...
0x18000db11  mov     [rsp+0B8h+var_50], r13
0x18000db16  lea     rdx, [rsp+0B8h+var_50]
0x18000db1b  mov     rax, [rcx]
0x18000db1e  mov     rax, [rax+8]
0x18000db22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db27  mov     esi, eax
0x18000db29  test    eax, eax
0x18000db2b  jns     short loc_18000DB99
0x18000db2d  cmp     eax, 80070103h
0x18000db32  jz      loc_18000DBE0
0x18000db38  call    cs:__imp_GetLastError
0x18000db3e  mov     edi, eax
0x18000db40  call    cs:__imp_CurrentIP
0x18000db46  mov     r8d, esi
0x18000db49  lea     rdx, aPitrtelemetryE; "PITRTelemetry_EnumerateSnapshotIds: Enu"...
0x18000db50  mov     ecx, 3000000h; unsigned int
0x18000db55  mov     rbx, rax
0x18000db58  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000db5d  mov     [rsp+0B8h+var_68], r13d
0x18000db62  lea     r8, aD; "D"
0x18000db69  mov     [rsp+0B8h+var_70], r13
0x18000db6e  xor     r9d, r9d
0x18000db71  mov     [rsp+0B8h+var_78], edi
0x18000db75  xor     edx, edx
0x18000db77  mov     [rsp+0B8h+var_80], rbx
0x18000db7c  mov     rcx, rax
0x18000db7f  mov     [rsp+0B8h+var_88], r14
0x18000db84  mov     [rsp+0B8h+var_90], r15
0x18000db89  mov     [rsp+0B8h+var_98], 9Ch
0x18000db91  call    cs:__imp_WdsSetupLogMessageW
0x18000db97  jmp     short loc_18000DBD6
0x18000db99  mov     rcx, [rsp+0B8h+var_50]
0x18000db9e  mov     rax, [rcx]
0x18000dba1  mov     rax, [rax]
0x18000dba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba9  test    rax, rax
0x18000dbac  jz      short loc_18000DBB4
0x18000dbae  cmp     [rax], r13w
0x18000dbb2  jnz     short loc_18000DBB7
0x18000dbb4  mov     rax, r13
0x18000dbb7  mov     rcx, rax
0x18000dbba  mov     rdx, r12
0x18000dbbd  mov     rax, rbp
0x18000dbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc5  mov     rcx, [rsp+0B8h+var_50]
0x18000dbca  mov     rax, [rcx]
0x18000dbcd  mov     rax, [rax+40h]
0x18000dbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd6  mov     rcx, [rsp+0B8h+var_58]
0x18000dbdb  jmp     loc_18000DB11
0x18000dbe0  mov     rcx, [rsp+0B8h+var_58]
0x18000dbe5  mov     rax, [rcx]
0x18000dbe8  mov     rax, [rax+10h]
0x18000dbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf1  jmp     short loc_18000DC60
0x18000dbf3  call    cs:__imp_GetLastError
0x18000dbf9  mov     edi, eax
0x18000dbfb  call    cs:__imp_CurrentIP
0x18000dc01  mov     r8d, esi
0x18000dc04  lea     rdx, aPitrtelemetryE_1; "PITRTelemetry_EnumerateSnapshotIds: Fai"...
0x18000dc0b  mov     ecx, 3000000h; unsigned int
0x18000dc10  mov     rbx, rax
0x18000dc13  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dc18  mov     [rsp+0B8h+var_68], r13d
0x18000dc1d  lea     r14, aPitrtelemetryE_0; "PITRTelemetry_EnumerateSnapshotIds"
0x18000dc24  mov     [rsp+0B8h+var_70], r13
0x18000dc29  lea     r15, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\task\\dll\\"...
0x18000dc30  mov     [rsp+0B8h+var_78], edi
0x18000dc34  lea     r8, aD; "D"
0x18000dc3b  mov     [rsp+0B8h+var_80], rbx
0x18000dc40  xor     r9d, r9d
0x18000dc43  mov     [rsp+0B8h+var_88], r14
0x18000dc48  xor     edx, edx
0x18000dc4a  mov     [rsp+0B8h+var_90], r15
0x18000dc4f  mov     rcx, rax
0x18000dc52  mov     [rsp+0B8h+var_98], 8Fh
0x18000dc5a  call    cs:__imp_WdsSetupLogMessageW
0x18000dc60  mov     rcx, [rsp+0B8h+var_48]
0x18000dc65  xor     rcx, rsp; StackCookie
0x18000dc68  call    __security_check_cookie
0x18000dc6d  mov     rbx, [rsp+0B8h+arg_18]
0x18000dc75  add     rsp, 80h
0x18000dc7c  pop     r15
0x18000dc7e  pop     r14
0x18000dc80  pop     r13
0x18000dc82  pop     r12
0x18000dc84  pop     rdi
0x18000dc85  pop     rsi
0x18000dc86  pop     rbp
0x18000dc87  retn
```
