# WinREAgent::SwapWinREs::Undo(WinREAgent::ExecutionContext *)

- ea: `0x18002c0c8`
- end: `0x18002c445`
- name: `?Undo@SwapWinREs@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `893`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x18000d92c`
- `0x180023654`
- `0x18002ba04`
- `0x18002c0c8`
- `0x18003717c`
- `0x180037344`
- `0x18004b35c`
- `0x18004d2ac`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c2f3`
- `KERNEL32!GetLastError` at `0x18002c33b`
- `KERNEL32!GetLastError` at `0x18002c37d`
- `KERNEL32!GetLastError` at `0x18002c3bc`
- `KERNEL32!GetLastError` at `0x18002c3fe`
- `KERNEL32!GetLastError` at `0x18002c2f3`
- `KERNEL32!GetLastError` at `0x18002c33b`
- `KERNEL32!GetLastError` at `0x18002c37d`
- `KERNEL32!GetLastError` at `0x18002c3bc`
- `KERNEL32!GetLastError` at `0x18002c3fe`
- `KERNEL32!MoveFileTransactedW` at `0x18002c2e9`
- `KERNEL32!MoveFileTransactedW` at `0x18002c2e9`
- `ktmw32!CommitTransaction` at `0x18002c331`
- `ktmw32!CommitTransaction` at `0x18002c331`
- `ktmw32!CreateTransaction` at `0x18002c274`
- `ktmw32!CreateTransaction` at `0x18002c274`

## string_xrefs

- `0x18002c1ad`: `Failed to build path for updated wim new location`
- `0x18002c21b`: `Failed to copy [%s] to [%s]`
- `0x18002c11b`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c16a`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c1c1`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c22f`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c363`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c3e4`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002c3d0`: `Failed to create transaction handle`
- `0x18002c34f`: `Failed to commit transaction`
- `0x18002c107`: `No backup wim path`
- `0x18002c122`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c171`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c1c8`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c236`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c36a`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c3eb`: `WinREAgent::SwapWinREs::Undo`
- `0x18002c156`: `Backup wim path [%s] doesn't exist`
- `0x18002c1e7`: `Copy [%s] to [%s]`
- `0x18002c307`: `Failed to replace winre.wim with backup`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinREAgent::SwapWinREs::Undo(struct WinREAgent::ExecutionContext *a1)
{
  _QWORD *v2; // rdi
  unsigned int v4; // ebx
  int v5; // esi
  LPCWSTR v6; // rbx
  HANDLE Transaction; // rax
  HANDLE *v8; // rax
  signed int v9; // eax
  HANDLE *v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  signed int v14; // eax
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-28h] BYREF
  void **v16; // [rsp+48h] [rbp-20h] BYREF
  HANDLE v17; // [rsp+50h] [rbp-18h] BYREF

  PushButtonReset::Logging::Trace(0, L"SwapWinREs::Undo Start");
  v2 = (_QWORD *)((char *)a1 + 312);
  if ( !*(_DWORD *)(*((_QWORD *)a1 + 39) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::SwapWinREs::Undo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
      161,
      L"No backup wim path");
    return 2147500037LL;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)a1 + 312) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943568LL,
      "WinREAgent::SwapWinREs::Undo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
      168,
      L"Backup wim path [%s] doesn't exist",
      *v2);
    return 2147943568LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpExistingFileName);
  v4 = BuildDestinationPath(a1, &lpExistingFileName);
  if ( (v4 & 0x80000000) == 0 )
  {
    PushButtonReset::Logging::Trace(0, L"Copy [%s] to [%s]", *v2, lpExistingFileName);
    v5 = PushButtonReset::File::Copy((_QWORD *)a1 + 39, &lpExistingFileName, 0);
    if ( v5 < 0 )
    {
      v6 = lpExistingFileName;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::SwapWinREs::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        178,
        L"Failed to copy [%s] to [%s]",
        *v2,
        lpExistingFileName);
LABEL_22:
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
      return (unsigned int)v5;
    }
    Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, (LPWSTR)L"SwapWinREs");
    v16 = &RAII::CAutoCleanup<void *>::`vftable';
    v17 = Transaction;
    if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v16)
      || *(_QWORD *)((__int64 (__fastcall *)(void ***))v16[4])(&v16) == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::SwapWinREs::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        193,
        L"Failed to create transaction handle");
      v14 = GetLastError();
      v4 = v14;
      if ( v14 > 0 )
        v4 = (unsigned __int16)v14 | 0x80070000;
      v16 = &RAII::CAutoCleanup<void *>::`vftable';
      RAII::CleanupInfo<void *>::Release(&v17);
      goto LABEL_29;
    }
    v8 = (HANDLE *)((__int64 (__fastcall *)(void ***))v16[4])(&v16);
    v6 = lpExistingFileName;
    if ( MoveFileTransactedW(lpExistingFileName, *((LPCWSTR *)a1 + 15), 0, 0, 1u, *v8) )
    {
      v10 = (HANDLE *)((__int64 (__fastcall *)(void ***))v16[4])(&v16);
      if ( CommitTransaction(*v10) )
      {
        PushButtonReset::Logging::Trace(0, L"SwapWinREs::Undo Start");
LABEL_21:
        v16 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&v17);
        goto LABEL_22;
      }
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "WinREAgent::SwapWinREs::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        211,
        L"Failed to commit transaction");
    }
    else
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "WinREAgent::SwapWinREs::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        206,
        L"Failed to replace winre.wim with backup");
    }
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_21;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    v4,
    "WinREAgent::SwapWinREs::Undo",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
    174,
    L"Failed to build path for updated wim new location");
LABEL_29:
  ATL::CStringData::Release((ATL::CStringData *)(lpExistingFileName - 12));
  return v4;
}

```

## disassembly

```asm
0x18002c0c8  push    rbp
0x18002c0ca  push    rbx
0x18002c0cb  push    rsi
0x18002c0cc  push    rdi
0x18002c0cd  push    r12
0x18002c0cf  push    r14
0x18002c0d1  mov     rbp, rsp
0x18002c0d4  sub     rsp, 68h
0x18002c0d8  mov     rax, cs:__security_cookie
0x18002c0df  xor     rax, rsp
0x18002c0e2  mov     [rbp+var_10], rax
0x18002c0e6  mov     r14, rcx
0x18002c0e9  lea     rdx, aSwapwinresUndo; "SwapWinREs::Undo Start"
0x18002c0f0  xor     ecx, ecx
0x18002c0f2  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c0f7  lea     rdi, [r14+138h]
0x18002c0fe  mov     rax, [rdi]
0x18002c101  cmp     dword ptr [rax-10h], 0
0x18002c105  jnz     short loc_18002C142
0x18002c107  lea     rax, aNoBackupWimPat; "No backup wim path"
0x18002c10e  mov     qword ptr [rsp+68h+Timeout], rax
0x18002c113  mov     [rsp+68h+IsolationFlags], 0A1h
0x18002c11b  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c122  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c129  mov     edx, 80004005h
0x18002c12e  mov     ecx, 2
0x18002c133  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c138  mov     eax, 80004005h
0x18002c13d  jmp     loc_18002C42C
0x18002c142  mov     rcx, rdi
0x18002c145  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002c14a  test    al, al
0x18002c14c  jnz     short loc_18002C191
0x18002c14e  mov     rax, [rdi]
0x18002c151  mov     [rsp+68h+Description], rax
0x18002c156  lea     rax, aBackupWimPathS_0; "Backup wim path [%s] doesn't exist"
0x18002c15d  mov     qword ptr [rsp+68h+Timeout], rax
0x18002c162  mov     [rsp+68h+IsolationFlags], 0A8h
0x18002c16a  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c171  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c178  mov     edx, 80070490h
0x18002c17d  mov     ecx, 2
0x18002c182  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c187  mov     eax, 80070490h
0x18002c18c  jmp     loc_18002C42C
0x18002c191  lea     rcx, [rbp+lpExistingFileName]
0x18002c195  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002c19a  nop
0x18002c19b  lea     rdx, [rbp+lpExistingFileName]
0x18002c19f  mov     rcx, r14
0x18002c1a2  call    BuildDestinationPath
0x18002c1a7  mov     ebx, eax
0x18002c1a9  test    eax, eax
0x18002c1ab  jns     short loc_18002C1E0
0x18002c1ad  lea     rax, aFailedToBuildP; "Failed to build path for updated wim ne"...
0x18002c1b4  mov     qword ptr [rsp+68h+Timeout], rax
0x18002c1b9  mov     [rsp+68h+IsolationFlags], 0AEh
0x18002c1c1  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c1c8  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c1cf  mov     edx, ebx
0x18002c1d1  mov     ecx, 2
0x18002c1d6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c1db  jmp     loc_18002C41D
0x18002c1e0  mov     r9, [rbp+lpExistingFileName]
0x18002c1e4  mov     r8, [rdi]
0x18002c1e7  lea     rdx, aCopySToS; "Copy [%s] to [%s]"
0x18002c1ee  xor     ecx, ecx
0x18002c1f0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c1f5  xor     r8d, r8d
0x18002c1f8  lea     rdx, [rbp+lpExistingFileName]
0x18002c1fc  mov     rcx, rdi
0x18002c1ff  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x18002c204  mov     esi, eax
0x18002c206  test    eax, eax
0x18002c208  jns     short loc_18002C24E
0x18002c20a  mov     rbx, [rbp+lpExistingFileName]
0x18002c20e  mov     [rsp+68h+var_30], rbx
0x18002c213  mov     rcx, [rdi]
0x18002c216  mov     [rsp+68h+Description], rcx
0x18002c21b  lea     rax, aFailedToCopyST; "Failed to copy [%s] to [%s]"
0x18002c222  mov     qword ptr [rsp+68h+Timeout], rax
0x18002c227  mov     [rsp+68h+IsolationFlags], 0B2h
0x18002c22f  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c236  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c23d  mov     edx, esi
0x18002c23f  mov     ecx, 2
0x18002c244  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c249  jmp     loc_18002C39C
0x18002c24e  lea     rax, Description; "SwapWinREs"
0x18002c255  mov     [rsp+68h+Description], rax; Description
0x18002c25a  mov     [rsp+68h+Timeout], 0; Timeout
0x18002c262  mov     [rsp+68h+IsolationFlags], 0; IsolationFlags
0x18002c26a  xor     r9d, r9d; IsolationLevel
0x18002c26d  xor     r8d, r8d; CreateOptions
0x18002c270  xor     edx, edx; UOW
0x18002c272  xor     ecx, ecx; lpTransactionAttributes
0x18002c274  call    cs:__imp_CreateTransaction
0x18002c27a  lea     r12, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x18002c281  mov     [rbp+var_20], r12
0x18002c285  mov     [rbp+var_18], rax
0x18002c289  lea     rcx, [rbp+var_20]
0x18002c28d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002c292  cmp     qword ptr [rax], 0
0x18002c296  jz      loc_18002C3BC
0x18002c29c  mov     rax, [rbp+var_20]
0x18002c2a0  lea     rcx, [rbp+var_20]
0x18002c2a4  mov     rax, [rax+20h]
0x18002c2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2ad  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18002c2b1  jz      loc_18002C3BC
0x18002c2b7  mov     rax, [rbp+var_20]
0x18002c2bb  lea     rcx, [rbp+var_20]
0x18002c2bf  mov     rax, [rax+20h]
0x18002c2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2c8  mov     rcx, [rax]
0x18002c2cb  mov     qword ptr [rsp+68h+Timeout], rcx; hTransaction
0x18002c2d0  mov     [rsp+68h+IsolationFlags], 1; dwFlags
0x18002c2d8  xor     r9d, r9d; lpData
0x18002c2db  xor     r8d, r8d; lpProgressRoutine
0x18002c2de  mov     rdx, [r14+78h]; lpNewFileName
0x18002c2e2  mov     rbx, [rbp+lpExistingFileName]
0x18002c2e6  mov     rcx, rbx; lpExistingFileName
0x18002c2e9  call    cs:__imp_MoveFileTransactedW
0x18002c2ef  test    eax, eax
0x18002c2f1  jnz     short loc_18002C31D
0x18002c2f3  call    cs:__imp_GetLastError
0x18002c2f9  mov     edi, 80070000h
0x18002c2fe  test    eax, eax
0x18002c300  jle     short loc_18002C307
0x18002c302  movzx   eax, ax
0x18002c305  or      eax, edi
0x18002c307  lea     rcx, aFailedToReplac_1; "Failed to replace winre.wim with backup"
0x18002c30e  mov     qword ptr [rsp+68h+Timeout], rcx
0x18002c313  mov     [rsp+68h+IsolationFlags], 0CEh
0x18002c31b  jmp     short loc_18002C363
0x18002c31d  mov     rax, [rbp+var_20]
0x18002c321  lea     rcx, [rbp+var_20]
0x18002c325  mov     rax, [rax+20h]
0x18002c329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c32e  mov     rcx, [rax]; TransactionHandle
0x18002c331  call    cs:__imp_CommitTransaction
0x18002c337  test    eax, eax
0x18002c339  jnz     short loc_18002C3AC
0x18002c33b  call    cs:__imp_GetLastError
0x18002c341  mov     edi, 80070000h
0x18002c346  test    eax, eax
0x18002c348  jle     short loc_18002C34F
0x18002c34a  movzx   eax, ax
0x18002c34d  or      eax, edi
0x18002c34f  lea     rcx, aFailedToCommit; "Failed to commit transaction"
0x18002c356  mov     qword ptr [rsp+68h+Timeout], rcx
0x18002c35b  mov     [rsp+68h+IsolationFlags], 0D3h
0x18002c363  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c36a  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c371  mov     edx, eax
0x18002c373  mov     ecx, 2
0x18002c378  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c37d  call    cs:__imp_GetLastError
0x18002c383  test    eax, eax
0x18002c385  mov     esi, eax
0x18002c387  jle     short loc_18002C38E
0x18002c389  movzx   esi, ax
0x18002c38c  or      esi, edi
0x18002c38e  mov     [rbp+var_20], r12
0x18002c392  lea     rcx, [rbp+var_18]
0x18002c396  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18002c39b  nop
0x18002c39c  lea     rcx, [rbx-18h]; this
0x18002c3a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c3a5  mov     eax, esi
0x18002c3a7  jmp     loc_18002C42C
0x18002c3ac  lea     rdx, aSwapwinresUndo; "SwapWinREs::Undo Start"
0x18002c3b3  xor     ecx, ecx
0x18002c3b5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c3ba  jmp     short loc_18002C38E
0x18002c3bc  call    cs:__imp_GetLastError
0x18002c3c2  mov     edi, 80070000h
0x18002c3c7  test    eax, eax
0x18002c3c9  jle     short loc_18002C3D0
0x18002c3cb  movzx   eax, ax
0x18002c3ce  or      eax, edi
0x18002c3d0  lea     rcx, aFailedToCreate; "Failed to create transaction handle"
0x18002c3d7  mov     qword ptr [rsp+68h+Timeout], rcx
0x18002c3dc  mov     [rsp+68h+IsolationFlags], 0C1h
0x18002c3e4  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c3eb  lea     r8, aWinreagentSwap; "WinREAgent::SwapWinREs::Undo"
0x18002c3f2  mov     edx, eax
0x18002c3f4  mov     ecx, 2
0x18002c3f9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c3fe  call    cs:__imp_GetLastError
0x18002c404  mov     ebx, eax
0x18002c406  test    eax, eax
0x18002c408  jle     short loc_18002C40F
0x18002c40a  movzx   ebx, ax
0x18002c40d  or      ebx, edi
0x18002c40f  mov     [rbp+var_20], r12
0x18002c413  lea     rcx, [rbp+var_18]
0x18002c417  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18002c41c  nop
0x18002c41d  mov     rcx, [rbp+lpExistingFileName]
0x18002c421  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c425  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c42a  mov     eax, ebx
0x18002c42c  mov     rcx, [rbp+var_10]
0x18002c430  xor     rcx, rsp; StackCookie
0x18002c433  call    __security_check_cookie
0x18002c438  add     rsp, 68h
0x18002c43c  pop     r14
0x18002c43e  pop     r12
0x18002c440  pop     rdi
0x18002c441  pop     rsi
0x18002c442  pop     rbx
0x18002c443  pop     rbp
0x18002c444  retn
```
