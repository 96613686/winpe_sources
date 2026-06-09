# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::PerformDeletion(void *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault> const *,CLEANUP_THRESHOLD,double,int,TraceLoggingCorrelationVector *,int *,double *)

- ea: `0x180029550`
- end: `0x180029a9b`
- name: `?PerformDeletion@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBV?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@W4CLEANUP_THRESHOLD@@NHPEAVTraceLoggingCorrelationVector@@PEAHPEAN@Z`
- size: `1355`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, double, int, TraceLoggingCorrelationVector *, _DWORD *, double *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002bae0`

## callees

- `0x18000638c`
- `0x18000c700`
- `0x180027008`
- `0x1800276e8`
- `0x180027bfc`
- `0x1800293a4`
- `0x180029550`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800295c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800295c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800295d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800295d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a60`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x180029705`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x180029705`
- `WDSCORE!CurrentIP` at `0x18002966f`
- `WDSCORE!CurrentIP` at `0x18002971a`
- `WDSCORE!CurrentIP` at `0x1800297e3`
- `WDSCORE!CurrentIP` at `0x18002989c`
- `WDSCORE!CurrentIP` at `0x180029907`
- `WDSCORE!CurrentIP` at `0x18002997f`
- `WDSCORE!CurrentIP` at `0x1800299e5`
- `WDSCORE!CurrentIP` at `0x18002966f`
- `WDSCORE!CurrentIP` at `0x18002971a`
- `WDSCORE!CurrentIP` at `0x1800297e3`
- `WDSCORE!CurrentIP` at `0x18002989c`
- `WDSCORE!CurrentIP` at `0x180029907`
- `WDSCORE!CurrentIP` at `0x18002997f`
- `WDSCORE!CurrentIP` at `0x1800299e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800296cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029779`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002984d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800298ee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029958`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029a39`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800296cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029779`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002984d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800298ee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029958`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029a39`

## string_xrefs

- `0x180029617`: `SeBackupPrivilege`
- `0x180029862`: `SeBackupPrivilege`
- `0x180029648`: `SeRestorePrivilege`
- `0x180029876`: `SeRestorePrivilege`
- `0x1800296b4`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x180029762`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002980d`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x1800298bc`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x180029926`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002999c`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x180029a07`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002968e`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion`
- `0x18002973c`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion`
- `0x180029819`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion`
- `0x180029675`: `Will attempt to move files to Scratch Reserve before deletion`
- `0x1800297ec`: `Deleted %d files and reclaimed %.0f bytes of space from old setup folders`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::PerformDeletion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        double a4,
        int a5,
        TraceLoggingCorrelationVector *a6,
        _DWORD *a7,
        double *a8)
{
  TraceLoggingCorrelationVector *v8; // r12
  unsigned int i; // r14d
  double v11; // xmm6_8
  HANDLE CurrentProcess; // rax
  signed int v13; // eax
  signed int v14; // esi
  int v15; // eax
  DWORD LastError; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  char *v19; // rbx
  bool v20; // al
  char *v21; // rcx
  int UpdateReserveManagerLoader; // r14d
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  __int64 v26; // rbx
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  __int64 v36; // rax
  DWORD v37; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  int v40; // r14d
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  TraceLoggingCorrelationVector *v45; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+70h] [rbp-90h] BYREF
  int v48; // [rsp+74h] [rbp-8Ch] BYREF
  _DWORD *v49; // [rsp+78h] [rbp-88h]
  char Destination[144]; // [rsp+80h] [rbp-80h] BYREF

  v8 = a6;
  i = 0;
  v49 = a7;
  TokenHandle = 0;
  v11 = 0.0;
  v47 = 0;
  v48 = 0;
  v45 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v15 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(
            TokenHandle,
            L"SeBackupPrivilege",
            1,
            &v47);
    v14 = v15;
    if ( v15 < 0
      || (v15 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(
                  TokenHandle,
                  L"SeRestorePrivilege",
                  1,
                  &v48),
          v14 = v15,
          v15 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(0x4000000, "Will attempt to move files to Scratch Reserve before deletion");
      WdsSetupLogMessageW(
        v18,
        0,
        L"D",
        0,
        1433,
        L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
        L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
        v17,
        LastError,
        0,
        0);
      v19 = 0;
      if ( a6 )
      {
        v20 = TraceLoggingCorrelationVector::ToString(a6, Destination);
        v8 = 0;
        v21 = Destination;
        if ( !v20 )
          v21 = 0;
        v19 = v21;
      }
      UpdateReserveManagerLoader = GetUpdateReserveManagerLoader(0, L"WindowsOldFastCleanup", v19, &v45);
      if ( UpdateReserveManagerLoader < 0 )
      {
        v23 = GetLastError();
        v24 = CurrentIP();
        v25 = ConstructPartialMsgW(
                50331648,
                "Failed to get reserve manager for online OS, hr = 0x%x",
                UpdateReserveManagerLoader);
        WdsSetupLogMessageW(
          v25,
          0,
          L"D",
          0,
          1444,
          L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
          L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
          v24,
          v23,
          v8,
          (_DWORD)v8);
        v45 = v8;
      }
      for ( i = (unsigned int)v8; (signed int)i < *(_DWORD *)(a2 + 4); ++i )
      {
        v26 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL * (int)i);
        if ( (int)CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::DeleteFileW(v26, (__int64)v45) >= 0
          && *(_DWORD *)(v26 + 16) == (_DWORD)v8 )
        {
          v11 = v11 + *(double *)(v26 + 32);
          if ( v11 >= a4 * 0.95 )
            break;
        }
      }
      *v49 = (_DWORD)v8;
    }
  }
  else
  {
    v13 = GetLastError();
    v8 = 0;
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v14 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
  }
  if ( a8 )
    *a8 = a4 - v11;
  v27 = GetLastError();
  v28 = CurrentIP();
  v29 = ConstructPartialMsgW(
          0x4000000,
          "Deleted %d files and reclaimed %.0f bytes of space from old setup folders",
          i,
          v11);
  WdsSetupLogMessageW(
    v29,
    0,
    L"D",
    0,
    1496,
    L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
    L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
    v28,
    v27,
    v8,
    (_DWORD)v8);
  if ( TokenHandle )
  {
    CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(
      TokenHandle,
      L"SeBackupPrivilege",
      v47,
      0);
    CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(
      TokenHandle,
      L"SeRestorePrivilege",
      v48,
      0);
  }
  if ( v14 < 0 )
  {
    v30 = GetLastError();
    v31 = CurrentIP();
    v32 = ConstructPartialMsgW(0x2000000, "ProcessTreeForDeletion failed. hr = 0x%x", v14);
    WdsSetupLogMessageW(
      v32,
      0,
      L"D",
      0,
      1519,
      L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
      L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
      v31,
      v30,
      v8,
      (_DWORD)v8);
  }
  if ( v45 != v8 )
  {
    v33 = GetLastError();
    v34 = CurrentIP();
    v35 = ConstructPartialMsgW(0x4000000, "Re-initialize Reserves");
    WdsSetupLogMessageW(
      v35,
      0,
      L"D",
      0,
      1524,
      L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
      L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
      v34,
      v33,
      v8,
      (_DWORD)v8);
    v36 = (*(__int64 (__fastcall **)(TraceLoggingCorrelationVector *))(*(_QWORD *)v45 + 8LL))(v45);
    if ( v36 )
    {
      v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2);
      if ( v40 < 0 )
      {
        v41 = GetLastError();
        v42 = CurrentIP();
        v43 = ConstructPartialMsgW(50331648, "Failed to Initialize Reserves. status: %x", v40);
        WdsSetupLogMessageW(
          v43,
          0,
          L"D",
          0,
          1538,
          L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
          L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
          v42,
          v41,
          v8,
          (_DWORD)v8);
      }
    }
    else
    {
      v37 = GetLastError();
      v38 = CurrentIP();
      v39 = ConstructPartialMsgW(0x2000000, "Failed to get Reserve Manager");
      WdsSetupLogMessageW(
        v39,
        0,
        L"D",
        0,
        1529,
        L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
        L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::PerformDeletion",
        v38,
        v37,
        v8,
        (_DWORD)v8);
    }
    (**(void (__fastcall ***)(__int64))v45)((__int64)v45);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180029550  mov     rax, rsp
0x180029553  push    rbp
0x180029554  push    rbx
0x180029555  push    rsi
0x180029556  push    rdi
0x180029557  push    r12
0x180029559  push    r13
0x18002955b  push    r14
0x18002955d  push    r15
0x18002955f  lea     rbp, [rsp-58h]
0x180029564  sub     rsp, 158h
0x18002956b  movaps  xmmword ptr [rax-58h], xmm6
0x18002956f  movaps  xmmword ptr [rax-68h], xmm7
0x180029573  movaps  xmmword ptr [rax-78h], xmm8
0x180029578  mov     rax, cs:__security_cookie
0x18002957f  xor     rax, rsp
0x180029582  mov     [rbp+90h+var_80], rax
0x180029586  mov     rax, [rbp+90h+arg_30]
0x18002958d  xor     ebx, ebx
0x18002958f  mov     r12, [rbp+90h+arg_28]
0x180029596  mov     r14d, ebx
0x180029599  mov     r13, [rbp+90h+arg_38]
0x1800295a0  movaps  xmm7, xmm3
0x1800295a3  mov     [rsp+190h+var_118], rax
0x1800295a8  mov     r15, rdx
0x1800295ab  mov     [rsp+190h+TokenHandle], rbx
0x1800295b0  xorps   xmm6, xmm6
0x1800295b3  mov     [rsp+190h+var_120], ebx
0x1800295b7  mov     [rsp+190h+var_11C], ebx
0x1800295bb  mov     [rsp+190h+var_130], rbx
0x1800295c0  call    cs:__imp_GetCurrentProcess
0x1800295c6  mov     rcx, rax; ProcessHandle
0x1800295c9  lea     r8, [rsp+190h+TokenHandle]; TokenHandle
0x1800295ce  lea     edx, [rbx+28h]; DesiredAccess
0x1800295d1  call    cs:__imp_OpenProcessToken
0x1800295d7  test    eax, eax
0x1800295d9  jnz     short loc_180029608
0x1800295db  call    cs:__imp_GetLastError
0x1800295e1  xor     r12d, r12d
0x1800295e4  mov     esi, eax
0x1800295e6  test    eax, eax
0x1800295e8  jnz     short loc_1800295F1
0x1800295ea  mov     esi, 80004005h
0x1800295ef  jmp     short loc_1800295FC
0x1800295f1  jle     short loc_1800295FC
0x1800295f3  movzx   esi, ax
0x1800295f6  or      esi, 80070000h
0x1800295fc  mov     ecx, esi
0x1800295fe  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029603  jmp     loc_1800297CC
0x180029608  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x18002960d  lea     r9, [rsp+190h+var_120]
0x180029612  mov     edi, 1
0x180029617  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x18002961e  mov     r8d, edi
0x180029621  call    ?EnablePrivilege@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBGHPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(void *,ushort const *,int,int *)
0x180029626  mov     esi, eax
0x180029628  test    eax, eax
0x18002962a  jns     short loc_18002963B
0x18002962c  mov     ecx, eax
0x18002962e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029633  xor     r12d, r12d
0x180029636  jmp     loc_1800297CC
0x18002963b  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x180029640  lea     r9, [rsp+190h+var_11C]
0x180029645  mov     r8d, edi
0x180029648  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18002964f  call    ?EnablePrivilege@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBGHPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(void *,ushort const *,int,int *)
0x180029654  mov     esi, eax
0x180029656  test    eax, eax
0x180029658  js      short loc_18002962C
0x18002965a  movaps  xmm8, xmm7
0x18002965e  mulsd   xmm8, cs:__real@3fee666666666666
0x180029667  call    cs:__imp_GetLastError
0x18002966d  mov     edi, eax
0x18002966f  call    cs:__imp_CurrentIP
0x180029675  lea     rdx, aWillAttemptToM; "Will attempt to move files to Scratch R"...
0x18002967c  mov     ecx, 4000000h; unsigned int
0x180029681  mov     rbx, rax
0x180029684  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029689  mov     [rsp+190h+var_140], r14d
0x18002968e  lea     rcx, aCfastdeleteimp; "CFastDeleteImplT<class CDirectoryProvid"...
0x180029695  mov     [rsp+190h+var_148], r14
0x18002969a  lea     r8, aD_0; "D"
0x1800296a1  mov     [rsp+190h+var_150], edi
0x1800296a5  xor     r9d, r9d
0x1800296a8  mov     [rsp+190h+var_158], rbx
0x1800296ad  xor     edx, edx
0x1800296af  mov     [rsp+190h+var_160], rcx
0x1800296b4  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x1800296bb  mov     [rsp+190h+var_168], rcx
0x1800296c0  mov     rcx, rax
0x1800296c3  mov     [rsp+190h+var_170], 599h
0x1800296cb  call    cs:__imp_WdsSetupLogMessageW
0x1800296d1  xor     ebx, ebx
0x1800296d3  test    r12, r12
0x1800296d6  jz      short loc_1800296F4
0x1800296d8  lea     rdx, [rbp+90h+Destination]; Destination
0x1800296dc  mov     rcx, r12; this
0x1800296df  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x1800296e4  xor     r12d, r12d
0x1800296e7  lea     rcx, [rbp+90h+Destination]
0x1800296eb  test    al, al
0x1800296ed  cmovz   rcx, rbx
0x1800296f1  mov     rbx, rcx
0x1800296f4  lea     r9, [rsp+190h+var_130]
0x1800296f9  mov     r8, rbx
0x1800296fc  lea     rdx, aWindowsoldfast; "WindowsOldFastCleanup"
0x180029703  xor     ecx, ecx
0x180029705  call    cs:__imp_GetUpdateReserveManagerLoader
0x18002970b  mov     r14d, eax
0x18002970e  test    eax, eax
0x180029710  jns     short loc_180029784
0x180029712  call    cs:__imp_GetLastError
0x180029718  mov     edi, eax
0x18002971a  call    cs:__imp_CurrentIP
0x180029720  mov     r8d, r14d
0x180029723  lea     rdx, aFailedToGetRes_0; "Failed to get reserve manager for onlin"...
0x18002972a  mov     ecx, 3000000h; unsigned int
0x18002972f  mov     rbx, rax
0x180029732  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029737  mov     [rsp+190h+var_140], r12d
0x18002973c  lea     rcx, aCfastdeleteimp; "CFastDeleteImplT<class CDirectoryProvid"...
0x180029743  mov     [rsp+190h+var_148], r12
0x180029748  lea     r8, aD_0; "D"
0x18002974f  mov     [rsp+190h+var_150], edi
0x180029753  xor     r9d, r9d
0x180029756  mov     [rsp+190h+var_158], rbx
0x18002975b  xor     edx, edx
0x18002975d  mov     [rsp+190h+var_160], rcx
0x180029762  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180029769  mov     [rsp+190h+var_168], rcx
0x18002976e  mov     rcx, rax
0x180029771  mov     [rsp+190h+var_170], 5A4h
0x180029779  call    cs:__imp_WdsSetupLogMessageW
0x18002977f  mov     [rsp+190h+var_130], r12
0x180029784  mov     r14d, r12d
0x180029787  cmp     [r15+4], r12d
0x18002978b  jle     short loc_1800297C4
0x18002978d  mov     rcx, [r15+8]
0x180029791  mov     rdx, [rsp+190h+var_130]
0x180029796  movsxd  rax, r14d
0x180029799  mov     rbx, [rcx+rax*8]
0x18002979d  mov     rcx, rbx
0x1800297a0  call    ?DeleteFileW@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBUCFastNtfsEntry@1@PEAVIUpdateReserveManagerLoader@@@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::DeleteFileW(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const *,IUpdateReserveManagerLoader *)
0x1800297a5  test    eax, eax
0x1800297a7  js      short loc_1800297BB
0x1800297a9  cmp     [rbx+10h], r12d
0x1800297ad  jnz     short loc_1800297BB
0x1800297af  addsd   xmm6, qword ptr [rbx+20h]
0x1800297b4  comisd  xmm6, xmm8
0x1800297b9  jnb     short loc_1800297C4
0x1800297bb  inc     r14d
0x1800297be  cmp     r14d, [r15+4]
0x1800297c2  jl      short loc_18002978D
0x1800297c4  mov     rax, [rsp+190h+var_118]
0x1800297c9  mov     [rax], r12d
0x1800297cc  test    r13, r13
0x1800297cf  jz      short loc_1800297DB
0x1800297d1  subsd   xmm7, xmm6
0x1800297d5  movsd   qword ptr [r13+0], xmm7
0x1800297db  call    cs:__imp_GetLastError
0x1800297e1  mov     edi, eax
0x1800297e3  call    cs:__imp_CurrentIP
0x1800297e9  movaps  xmm3, xmm6
0x1800297ec  lea     rdx, aDeletedDFilesA; "Deleted %d files and reclaimed %.0f byt"...
0x1800297f3  movq    r9, xmm6
0x1800297f8  mov     r8d, r14d
0x1800297fb  mov     ecx, 4000000h; unsigned int
0x180029800  mov     rbx, rax
0x180029803  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029808  mov     [rsp+190h+var_140], r12d
0x18002980d  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180029814  mov     [rsp+190h+var_148], r12
0x180029819  lea     r13, aCfastdeleteimp; "CFastDeleteImplT<class CDirectoryProvid"...
0x180029820  mov     [rsp+190h+var_150], edi
0x180029824  lea     r15, aD_0; "D"
0x18002982b  mov     [rsp+190h+var_158], rbx
0x180029830  xor     r9d, r9d
0x180029833  mov     [rsp+190h+var_160], r13
0x180029838  mov     r8, r15
0x18002983b  mov     [rsp+190h+var_168], rcx
0x180029840  xor     edx, edx
0x180029842  mov     rcx, rax
0x180029845  mov     [rsp+190h+var_170], 5D8h
0x18002984d  call    cs:__imp_WdsSetupLogMessageW
0x180029853  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x180029858  test    rcx, rcx
0x18002985b  jz      short loc_18002988A
0x18002985d  mov     r8d, [rsp+190h+var_120]
0x180029862  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x180029869  xor     r9d, r9d
0x18002986c  call    ?EnablePrivilege@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBGHPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(void *,ushort const *,int,int *)
0x180029871  mov     r8d, [rsp+190h+var_11C]
0x180029876  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18002987d  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x180029882  xor     r9d, r9d
0x180029885  call    ?EnablePrivilege@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEBGHPEAH@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::EnablePrivilege(void *,ushort const *,int,int *)
0x18002988a  mov     r14d, 2000000h
0x180029890  test    esi, esi
0x180029892  jns     short loc_1800298F4
0x180029894  call    cs:__imp_GetLastError
0x18002989a  mov     edi, eax
0x18002989c  call    cs:__imp_CurrentIP
0x1800298a2  mov     r8d, esi
0x1800298a5  lea     rdx, aProcesstreefor_0; "ProcessTreeForDeletion failed. hr = 0x%"...
0x1800298ac  mov     ecx, r14d; unsigned int
0x1800298af  mov     rbx, rax
0x1800298b2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800298b7  mov     [rsp+190h+var_140], r12d
0x1800298bc  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x1800298c3  mov     [rsp+190h+var_148], r12
0x1800298c8  xor     r9d, r9d
0x1800298cb  mov     [rsp+190h+var_150], edi
0x1800298cf  mov     r8, r15
0x1800298d2  mov     [rsp+190h+var_158], rbx
0x1800298d7  xor     edx, edx
0x1800298d9  mov     [rsp+190h+var_160], r13
0x1800298de  mov     [rsp+190h+var_168], rcx
0x1800298e3  mov     rcx, rax
0x1800298e6  mov     [rsp+190h+var_170], 5EFh
0x1800298ee  call    cs:__imp_WdsSetupLogMessageW
0x1800298f4  cmp     [rsp+190h+var_130], r12
0x1800298f9  jz      loc_180029A4F
0x1800298ff  call    cs:__imp_GetLastError
0x180029905  mov     edi, eax
0x180029907  call    cs:__imp_CurrentIP
0x18002990d  lea     rdx, aReInitializeRe; "Re-initialize Reserves"
0x180029914  mov     ecx, 4000000h; unsigned int
0x180029919  mov     rbx, rax
0x18002991c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029921  mov     [rsp+190h+var_140], r12d
0x180029926  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002992d  mov     [rsp+190h+var_148], r12
0x180029932  xor     r9d, r9d
0x180029935  mov     [rsp+190h+var_150], edi
0x180029939  mov     r8, r15
0x18002993c  mov     [rsp+190h+var_158], rbx
0x180029941  xor     edx, edx
0x180029943  mov     [rsp+190h+var_160], r13
0x180029948  mov     [rsp+190h+var_168], rcx
0x18002994d  mov     rcx, rax
0x180029950  mov     [rsp+190h+var_170], 5F4h
0x180029958  call    cs:__imp_WdsSetupLogMessageW
0x18002995e  mov     rcx, [rsp+190h+var_130]
0x180029963  mov     rax, [rcx]
0x180029966  mov     rax, [rax+8]
0x18002996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002996f  mov     rcx, rax
0x180029972  test    rax, rax
0x180029975  jnz     short loc_1800299C5
0x180029977  call    cs:__imp_GetLastError
0x18002997d  mov     edi, eax
0x18002997f  call    cs:__imp_CurrentIP
0x180029985  lea     rdx, aFailedToGetRes; "Failed to get Reserve Manager"
0x18002998c  mov     ecx, r14d; unsigned int
0x18002998f  mov     rbx, rax
0x180029992  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029997  mov     [rsp+190h+var_140], r12d
0x18002999c  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x1800299a3  mov     [rsp+190h+var_148], r12
0x1800299a8  mov     [rsp+190h+var_150], edi
0x1800299ac  mov     [rsp+190h+var_158], rbx
0x1800299b1  mov     [rsp+190h+var_160], r13
0x1800299b6  mov     [rsp+190h+var_168], rcx
0x1800299bb  mov     [rsp+190h+var_170], 5F9h
0x1800299c3  jmp     short loc_180029A2E
0x1800299c5  mov     rax, [rax]
0x1800299c8  mov     edx, 2
0x1800299cd  mov     rax, [rax+8]
0x1800299d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d6  mov     r14d, eax
0x1800299d9  test    eax, eax
0x1800299db  jns     short loc_180029A3F
0x1800299dd  call    cs:__imp_GetLastError
0x1800299e3  mov     edi, eax
0x1800299e5  call    cs:__imp_CurrentIP
0x1800299eb  mov     r8d, r14d
0x1800299ee  lea     rdx, aFailedToInitia; "Failed to Initialize Reserves. status: "...
0x1800299f5  mov     ecx, 3000000h; unsigned int
0x1800299fa  mov     rbx, rax
0x1800299fd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029a02  mov     [rsp+190h+var_140], r12d
0x180029a07  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180029a0e  mov     [rsp+190h+var_148], r12
0x180029a13  mov     [rsp+190h+var_150], edi
0x180029a17  mov     [rsp+190h+var_158], rbx
0x180029a1c  mov     [rsp+190h+var_160], r13
0x180029a21  mov     [rsp+190h+var_168], rcx
0x180029a26  mov     [rsp+190h+var_170], 602h
0x180029a2e  xor     r9d, r9d
0x180029a31  mov     r8, r15
0x180029a34  xor     edx, edx
0x180029a36  mov     rcx, rax
0x180029a39  call    cs:__imp_WdsSetupLogMessageW
0x180029a3f  mov     rcx, [rsp+190h+var_130]
0x180029a44  mov     rax, [rcx]
0x180029a47  mov     rax, [rax]
0x180029a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a4f  mov     ecx, esi
  ... truncated ...
```
