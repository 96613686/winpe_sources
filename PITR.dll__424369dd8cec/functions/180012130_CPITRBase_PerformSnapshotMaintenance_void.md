# CPITRBase::PerformSnapshotMaintenance(void)

- ea: `0x180012130`
- end: `0x18001241b`
- name: `?PerformSnapshotMaintenance@CPITRBase@@UEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800087cc`
- `0x180009e04`
- `0x18000f5f4`
- `0x180012130`
- `0x180021140`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001221d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001221d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012352`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800123f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800123f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012204`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012204`
- `WDSCORE!CurrentIP` at `0x18001218c`
- `WDSCORE!CurrentIP` at `0x180012225`
- `WDSCORE!CurrentIP` at `0x1800122ed`
- `WDSCORE!CurrentIP` at `0x18001235a`
- `WDSCORE!CurrentIP` at `0x18001218c`
- `WDSCORE!CurrentIP` at `0x180012225`
- `WDSCORE!CurrentIP` at `0x1800122ed`
- `WDSCORE!CurrentIP` at `0x18001235a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800121f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012284`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001234c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800123af`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800121f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012284`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001234c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800123af`

## string_xrefs

- `0x1800121b5`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180012247`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001230f`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001219c`: `%hs: Failed to initialize COM. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall CPITRBase::PerformSnapshotMaintenance(CPITRBase *this)
{
  struct CPITRSettings *v2; // rsi
  int SettingsInterface; // r14d
  DWORD v4; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  DWORD LastError; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  int v19; // [rsp+60h] [rbp-19h] BYREF
  struct CPITRSettings *v20; // [rsp+68h] [rbp-11h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-9h] BYREF
  __int64 v22; // [rsp+78h] [rbp-1h] BYREF
  __int64 v23; // [rsp+80h] [rbp+7h] BYREF

  v19 = 0;
  SystemTimeAsFileTime = 0;
  v2 = 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  SettingsInterface = pInitializeCOM(&v19);
  if ( SettingsInterface >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    SettingsInterface = CPITRBase::GetSettingsInterface(this, &v20);
    if ( SettingsInterface >= 0 )
    {
      v2 = v20;
      v10 = (*(__int64 (__fastcall **)(struct CPITRSettings *, __int64))(*(_QWORD *)v20 + 96LL))(v20, 5);
      v11 = (*(__int64 (__fastcall **)(struct CPITRSettings *, __int64, _QWORD))(*(_QWORD *)v2 + 128LL))(v2, 5, 0);
      SettingsInterface = CPITRBase::CleanupSnapshots(this, SystemTimeAsFileTime, v10, v11);
      if ( SettingsInterface < 0 )
      {
        LastError = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(
                0x2000000u,
                "CPITRBase::PerformSnapshotMaintenance: Failed to cleanup snapshots. Error: 0x%08X",
                SettingsInterface);
        WdsSetupLogMessageW(
          v14,
          0,
          L"D",
          0,
          5667,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::PerformSnapshotMaintenance",
          v13,
          LastError,
          0,
          0);
        v15 = GetLastError();
        v16 = CurrentIP();
        v17 = ConstructPartialMsgW(
                0x4000000u,
                "CPITRBase::PerformSnapshotMaintenance: Maintenance actions will continue.");
        WdsSetupLogMessageW(
          v17,
          0,
          L"D",
          0,
          5668,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::PerformSnapshotMaintenance",
          v16,
          v15,
          0,
          0);
        SettingsInterface = 0;
      }
    }
    else
    {
      v7 = GetLastError();
      v8 = CurrentIP();
      v9 = ConstructPartialMsgW(
             0x2000000u,
             "CPITRBase::PerformSnapshotMaintenance: Failed to get settings interface. Error: 0x%08X",
             SettingsInterface);
      WdsSetupLogMessageW(
        v9,
        0,
        L"D",
        0,
        5648,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::PerformSnapshotMaintenance",
        v8,
        v7,
        0,
        0);
      v2 = v20;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = CurrentIP();
    v6 = ConstructPartialMsgW(
           0x2000000u,
           "%hs: Failed to initialize COM. Error: 0x%08X",
           "CPITRBase::PerformSnapshotMaintenance",
           SettingsInterface);
    WdsSetupLogMessageW(
      v6,
      0,
      L"D",
      0,
      5637,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::PerformSnapshotMaintenance",
      v5,
      v4,
      0,
      0);
  }
  (*(void (__fastcall **)(CPITRBase *, __int64 *, _QWORD, __int64 *))(*(_QWORD *)this + 40LL))(this, &v23, 0, &v22);
  if ( v2 )
    (*(void (__fastcall **)(struct CPITRSettings *))(*(_QWORD *)v2 + 192LL))(v2);
  if ( v19 )
    CoUninitialize();
  return (unsigned int)SettingsInterface;
}

```

## disassembly

```asm
0x180012130  push    rbp
0x180012132  push    rbx
0x180012133  push    rsi
0x180012134  push    rdi
0x180012135  push    r12
0x180012137  push    r13
0x180012139  push    r14
0x18001213b  push    r15
0x18001213d  lea     rbp, [rsp-1Fh]
0x180012142  sub     rsp, 98h
0x180012149  mov     rax, cs:__security_cookie
0x180012150  xor     rax, rsp
0x180012153  mov     [rbp+57h+var_48], rax
0x180012157  xor     r12d, r12d
0x18001215a  mov     r15, rcx
0x18001215d  lea     rcx, [rbp+57h+var_70]; int *
0x180012161  mov     [rbp+57h+var_70], r12d
0x180012165  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180012169  mov     esi, r12d
0x18001216c  mov     [rbp+57h+var_68], r12
0x180012170  mov     [rbp+57h+var_50], r12
0x180012174  mov     [rbp+57h+var_58], r12
0x180012178  call    ?pInitializeCOM@@YAJAEAH@Z; pInitializeCOM(int &)
0x18001217d  mov     r14d, eax
0x180012180  test    eax, eax
0x180012182  jns     short loc_180012200
0x180012184  call    cs:__imp_GetLastError
0x18001218a  mov     edi, eax
0x18001218c  call    cs:__imp_CurrentIP
0x180012192  mov     r9d, r14d
0x180012195  lea     r8, aCpitrbasePerfo_3; "CPITRBase::PerformSnapshotMaintenance"
0x18001219c  lea     rdx, aHsFailedToInit; "%hs: Failed to initialize COM. Error: 0"...
0x1800121a3  mov     ecx, 2000000h; unsigned int
0x1800121a8  mov     rbx, rax
0x1800121ab  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800121b0  mov     [rsp+0D0h+var_80], r12d
0x1800121b5  lea     r13, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800121bc  mov     [rsp+0D0h+var_88], r12
0x1800121c1  lea     r8, aD; "D"
0x1800121c8  mov     [rsp+0D0h+var_90], edi
0x1800121cc  lea     r12, aCpitrbasePerfo_2; "CPITRBase::PerformSnapshotMaintenance"
0x1800121d3  mov     [rsp+0D0h+var_98], rbx
0x1800121d8  xor     r9d, r9d
0x1800121db  mov     [rsp+0D0h+var_A0], r12
0x1800121e0  xor     edx, edx
0x1800121e2  mov     [rsp+0D0h+var_A8], r13
0x1800121e7  mov     rcx, rax
0x1800121ea  mov     [rsp+0D0h+var_B0], 1605h
0x1800121f2  call    cs:__imp_WdsSetupLogMessageW
0x1800121f8  xor     r12d, r12d
0x1800121fb  jmp     loc_1800123BB
0x180012200  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012204  call    cs:__imp_GetSystemTimeAsFileTime
0x18001220a  lea     rdx, [rbp+57h+var_68]; struct CPITRSettings **
0x18001220e  mov     rcx, r15; this
0x180012211  call    ?GetSettingsInterface@CPITRBase@@QEAAJPEAPEAVCPITRSettings@@@Z; CPITRBase::GetSettingsInterface(CPITRSettings * *)
0x180012216  mov     r14d, eax
0x180012219  test    eax, eax
0x18001221b  jns     short loc_180012293
0x18001221d  call    cs:__imp_GetLastError
0x180012223  mov     edi, eax
0x180012225  call    cs:__imp_CurrentIP
0x18001222b  mov     r8d, r14d
0x18001222e  lea     rdx, aCpitrbasePerfo_0; "CPITRBase::PerformSnapshotMaintenance: "...
0x180012235  mov     ecx, 2000000h; unsigned int
0x18001223a  mov     rbx, rax
0x18001223d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012242  mov     [rsp+0D0h+var_80], r12d
0x180012247  lea     r13, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001224e  mov     [rsp+0D0h+var_88], r12
0x180012253  lea     r8, aD; "D"
0x18001225a  mov     [rsp+0D0h+var_90], edi
0x18001225e  lea     r12, aCpitrbasePerfo_2; "CPITRBase::PerformSnapshotMaintenance"
0x180012265  mov     [rsp+0D0h+var_98], rbx
0x18001226a  xor     r9d, r9d
0x18001226d  mov     [rsp+0D0h+var_A0], r12
0x180012272  xor     edx, edx
0x180012274  mov     [rsp+0D0h+var_A8], r13
0x180012279  mov     rcx, rax
0x18001227c  mov     [rsp+0D0h+var_B0], 1610h
0x180012284  call    cs:__imp_WdsSetupLogMessageW
0x18001228a  mov     rsi, [rbp+57h+var_68]
0x18001228e  jmp     loc_1800121F8
0x180012293  mov     rsi, [rbp+57h+var_68]
0x180012297  xor     r8d, r8d
0x18001229a  mov     rcx, rsi
0x18001229d  mov     rax, [rsi]
0x1800122a0  lea     edi, [r8+5]
0x1800122a4  mov     edx, edi
0x1800122a6  mov     rax, [rax+60h]
0x1800122aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122af  mov     rcx, [rsi]
0x1800122b2  mov     ebx, eax
0x1800122b4  xor     r8d, r8d
0x1800122b7  mov     edx, edi
0x1800122b9  mov     rax, [rcx+80h]
0x1800122c0  mov     rcx, rsi
0x1800122c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c8  mov     rdx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x1800122cc  mov     r9d, eax; unsigned int
0x1800122cf  mov     r8d, ebx; unsigned int
0x1800122d2  mov     rcx, r15; this
0x1800122d5  call    ?CleanupSnapshots@CPITRBase@@IEAAJU_FILETIME@@KK@Z; CPITRBase::CleanupSnapshots(_FILETIME,ulong,ulong)
0x1800122da  mov     r14d, eax
0x1800122dd  test    eax, eax
0x1800122df  jns     loc_1800123BB
0x1800122e5  call    cs:__imp_GetLastError
0x1800122eb  mov     edi, eax
0x1800122ed  call    cs:__imp_CurrentIP
0x1800122f3  mov     r8d, r14d
0x1800122f6  lea     rdx, aCpitrbasePerfo; "CPITRBase::PerformSnapshotMaintenance: "...
0x1800122fd  mov     ecx, 2000000h; unsigned int
0x180012302  mov     rbx, rax
0x180012305  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001230a  mov     [rsp+0D0h+var_80], r12d
0x18001230f  lea     r13, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180012316  mov     [rsp+0D0h+var_88], r12
0x18001231b  lea     r8, aD; "D"
0x180012322  mov     [rsp+0D0h+var_90], edi
0x180012326  lea     r12, aCpitrbasePerfo_2; "CPITRBase::PerformSnapshotMaintenance"
0x18001232d  mov     [rsp+0D0h+var_98], rbx
0x180012332  xor     r9d, r9d
0x180012335  mov     [rsp+0D0h+var_A0], r12
0x18001233a  xor     edx, edx
0x18001233c  mov     [rsp+0D0h+var_A8], r13
0x180012341  mov     rcx, rax
0x180012344  mov     [rsp+0D0h+var_B0], 1623h
0x18001234c  call    cs:__imp_WdsSetupLogMessageW
0x180012352  call    cs:__imp_GetLastError
0x180012358  mov     edi, eax
0x18001235a  call    cs:__imp_CurrentIP
0x180012360  lea     rdx, aCpitrbasePerfo_1; "CPITRBase::PerformSnapshotMaintenance: "...
0x180012367  mov     ecx, 4000000h; unsigned int
0x18001236c  mov     rbx, rax
0x18001236f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012374  mov     [rsp+0D0h+var_80], 0
0x18001237c  lea     r8, aD; "D"
0x180012383  mov     [rsp+0D0h+var_88], 0
0x18001238c  xor     r9d, r9d
0x18001238f  mov     [rsp+0D0h+var_90], edi
0x180012393  xor     edx, edx
0x180012395  mov     [rsp+0D0h+var_98], rbx
0x18001239a  mov     rcx, rax
0x18001239d  mov     [rsp+0D0h+var_A0], r12
0x1800123a2  mov     [rsp+0D0h+var_A8], r13
0x1800123a7  mov     [rsp+0D0h+var_B0], 1624h
0x1800123af  call    cs:__imp_WdsSetupLogMessageW
0x1800123b5  xor     r12d, r12d
0x1800123b8  mov     r14d, r12d
0x1800123bb  mov     rax, [r15]
0x1800123be  lea     r9, [rbp+57h+var_58]
0x1800123c2  xor     r8d, r8d
0x1800123c5  lea     rdx, [rbp+57h+var_50]
0x1800123c9  mov     rcx, r15
0x1800123cc  mov     rax, [rax+28h]
0x1800123d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d5  test    rsi, rsi
0x1800123d8  jz      short loc_1800123EC
0x1800123da  mov     rax, [rsi]
0x1800123dd  mov     rcx, rsi
0x1800123e0  mov     rax, [rax+0C0h]
0x1800123e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ec  cmp     [rbp+57h+var_70], r12d
0x1800123f0  jz      short loc_1800123F8
0x1800123f2  call    cs:__imp_CoUninitialize
0x1800123f8  mov     eax, r14d
0x1800123fb  mov     rcx, [rbp+57h+var_48]
0x1800123ff  xor     rcx, rsp; StackCookie
0x180012402  call    __security_check_cookie
0x180012407  add     rsp, 98h
0x18001240e  pop     r15
0x180012410  pop     r14
0x180012412  pop     r13
0x180012414  pop     r12
0x180012416  pop     rdi
0x180012417  pop     rsi
0x180012418  pop     rbx
0x180012419  pop     rbp
0x18001241a  retn
```
