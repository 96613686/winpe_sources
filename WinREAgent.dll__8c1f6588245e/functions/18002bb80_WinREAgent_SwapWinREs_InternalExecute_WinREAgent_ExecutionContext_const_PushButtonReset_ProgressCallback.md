# WinREAgent::SwapWinREs::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002bb80`
- end: `0x18002bfea`
- name: `?InternalExecute@SwapWinREs@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `1130`
- prototype: `__int64 __fastcall(WinREAgent::SwapWinREs *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x18000d92c`
- `0x180023654`
- `0x18002ba04`
- `0x18002bb80`
- `0x18003207c`
- `0x180032480`
- `0x18003717c`
- `0x180037344`
- `0x18004b35c`
- `0x18004c418`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002bdfe`
- `KERNEL32!GetLastError` at `0x18002be40`
- `KERNEL32!GetLastError` at `0x18002be83`
- `KERNEL32!GetLastError` at `0x18002bf65`
- `KERNEL32!GetLastError` at `0x18002bfa7`
- `KERNEL32!GetLastError` at `0x18002bdfe`
- `KERNEL32!GetLastError` at `0x18002be40`
- `KERNEL32!GetLastError` at `0x18002be83`
- `KERNEL32!GetLastError` at `0x18002bf65`
- `KERNEL32!GetLastError` at `0x18002bfa7`
- `KERNEL32!MoveFileTransactedW` at `0x18002bdf4`
- `KERNEL32!MoveFileTransactedW` at `0x18002bdf4`
- `ktmw32!CommitTransaction` at `0x18002be79`
- `ktmw32!CommitTransaction` at `0x18002be79`
- `ktmw32!CreateTransaction` at `0x18002bd83`
- `ktmw32!CreateTransaction` at `0x18002bd83`

## string_xrefs

- `0x18002bc08`: `Failed to build path for updated wim new location`
- `0x18002bc71`: `Failed to copy [%s] to [%s]`
- `0x18002bce4`: `BackupWimPath`
- `0x18002bbb1`: `Does not have path to updated wim`
- `0x18002bbc5`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bc1c`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bc85`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bd3e`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002be26`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bef8`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bf47`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bf8d`: `base\diagnosis\srt\winreagent\lib\operations\src\swapwinres.cpp`
- `0x18002bbcc`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bc23`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bc8c`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bd45`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002be2d`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002beff`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bf4e`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bf94`: `WinREAgent::SwapWinREs::InternalExecute`
- `0x18002bcbe`: `SwapWinREs: Save destionation new WinRE path to Rollback info`
- `0x18002bcd3`: `DestNewWimPath`
- `0x18002bd2a`: `Failed to save destionation new WinRE path into rolblack info`
- `0x18002bf79`: `Failed to create transaction handle`
- `0x18002be12`: `Failed to replace old winre.wim with updated one`
- `0x18002be97`: `Failed to commit transaction`
- `0x18002bf33`: `Failed to cleanup the updated wim`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinREAgent::SwapWinREs::InternalExecute(
        WinREAgent::SwapWinREs *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  _QWORD *v4; // r14
  int v6; // ebx
  int v7; // edi
  const WCHAR *v8; // rbx
  __int64 v9; // rdi
  HANDLE Transaction; // rax
  HANDLE *v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // esi
  HANDLE *v15; // rax
  signed int LastError; // eax
  signed int v17; // eax
  signed int v18; // eax
  unsigned int v19; // esi
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-38h] BYREF
  __int64 v21; // [rsp+48h] [rbp-30h] BYREF
  __int64 v22; // [rsp+50h] [rbp-28h] BYREF
  void **v23; // [rsp+58h] [rbp-20h] BYREF
  HANDLE v24; // [rsp+60h] [rbp-18h] BYREF

  v4 = (_QWORD *)((char *)a2 + 280);
  if ( !*(_DWORD *)(*((_QWORD *)a2 + 35) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::SwapWinREs::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
      51,
      L"Does not have path to updated wim");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpExistingFileName);
  v6 = BuildDestinationPath(a2, &lpExistingFileName);
  if ( v6 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v6,
      "WinREAgent::SwapWinREs::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
      56,
      L"Failed to build path for updated wim new location");
    ATL::CStringData::Release((ATL::CStringData *)(lpExistingFileName - 12));
    return (unsigned int)v6;
  }
  v7 = PushButtonReset::File::Copy(v4, &lpExistingFileName, 0);
  v8 = lpExistingFileName;
  if ( v7 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "WinREAgent::SwapWinREs::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
      59,
      L"Failed to copy [%s] to [%s]",
      *v4,
      lpExistingFileName);
    goto LABEL_7;
  }
  if ( *((_QWORD *)a2 + 56) )
  {
    PushButtonReset::Logging::Trace(0, L"SwapWinREs: Save destionation new WinRE path to Rollback info");
    v9 = *((_QWORD *)a2 + 56);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v22,
      (__int64)L"DestNewWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v21,
      (__int64)L"BackupWimPath");
    v7 = WinREAgent::RollbackHelper::WriteToConfig(v9, &v21, &v22, &lpExistingFileName);
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
    if ( v7 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v7,
        "WinREAgent::SwapWinREs::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        68,
        L"Failed to save destionation new WinRE path into rolblack info");
      goto LABEL_7;
    }
  }
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, (LPWSTR)L"SwapWinREs");
  v23 = &RAII::CAutoCleanup<void *>::`vftable';
  v24 = Transaction;
  if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v23)
    && *(_QWORD *)((__int64 (__fastcall *)(void ***))v23[4])(&v23) != -1 )
  {
    v11 = (HANDLE *)((__int64 (__fastcall *)(void ***))v23[4])(&v23);
    if ( MoveFileTransactedW(v8, *((LPCWSTR *)a2 + 15), 0, 0, 1u, *v11) )
    {
      v15 = (HANDLE *)((__int64 (__fastcall *)(void ***))v23[4])(&v23);
      if ( CommitTransaction(*v15) )
      {
        if ( *((_QWORD *)a2 + 56)
          && (PushButtonReset::Logging::Trace(0, L"SwapWinREs: Add checkpoint [%u]", 3),
              v7 = WinREAgent::RollbackHelper::SetCheckpoint(*((_QWORD *)a2 + 56), 3),
              v7 < 0) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v7,
            "WinREAgent::SwapWinREs::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
            109,
            L"Failed to set checkpoint for SwapWinREs");
        }
        else
        {
          v7 = PushButtonReset::File::Delete(v4);
          if ( v7 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v7,
              "WinREAgent::SwapWinREs::InternalExecute",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
              115,
              L"Failed to cleanup the updated wim");
            v7 = 0;
          }
        }
        v23 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&v24);
        goto LABEL_7;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::SwapWinREs::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        101,
        L"Failed to commit transaction");
    }
    else
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v12,
        "WinREAgent::SwapWinREs::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
        96,
        L"Failed to replace old winre.wim with updated one");
    }
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    v23 = &RAII::CAutoCleanup<void *>::`vftable';
    RAII::CleanupInfo<void *>::Release(&v24);
    v7 = v14;
LABEL_7:
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
    return (unsigned int)v7;
  }
  v17 = GetLastError();
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v17,
    "WinREAgent::SwapWinREs::InternalExecute",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\swapwinres.cpp",
    83,
    L"Failed to create transaction handle");
  v18 = GetLastError();
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  v23 = &RAII::CAutoCleanup<void *>::`vftable';
  RAII::CleanupInfo<void *>::Release(&v24);
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  return v19;
}

```

## disassembly

```asm
0x18002bb80  push    rbp
0x18002bb82  push    rbx
0x18002bb83  push    rsi
0x18002bb84  push    rdi
0x18002bb85  push    r12
0x18002bb87  push    r14
0x18002bb89  mov     rbp, rsp
0x18002bb8c  sub     rsp, 78h
0x18002bb90  mov     rax, cs:__security_cookie
0x18002bb97  xor     rax, rsp
0x18002bb9a  mov     [rbp+var_10], rax
0x18002bb9e  mov     rsi, rdx
0x18002bba1  lea     r14, [rdx+118h]
0x18002bba8  mov     rax, [r14]
0x18002bbab  cmp     dword ptr [rax-10h], 0
0x18002bbaf  jnz     short loc_18002BBEC
0x18002bbb1  lea     rax, aDoesNotHavePat; "Does not have path to updated wim"
0x18002bbb8  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bbbd  mov     [rsp+78h+IsolationFlags], 33h ; '3'
0x18002bbc5  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bbcc  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bbd3  mov     edx, 80070057h
0x18002bbd8  mov     ecx, 2
0x18002bbdd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bbe2  mov     eax, 80070057h
0x18002bbe7  jmp     loc_18002BFD1
0x18002bbec  lea     rcx, [rbp+lpExistingFileName]
0x18002bbf0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002bbf5  nop
0x18002bbf6  lea     rdx, [rbp+lpExistingFileName]
0x18002bbfa  mov     rcx, rsi
0x18002bbfd  call    BuildDestinationPath
0x18002bc02  mov     ebx, eax
0x18002bc04  test    eax, eax
0x18002bc06  jns     short loc_18002BC4B
0x18002bc08  lea     rax, aFailedToBuildP; "Failed to build path for updated wim ne"...
0x18002bc0f  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bc14  mov     [rsp+78h+IsolationFlags], 38h ; '8'
0x18002bc1c  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bc23  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bc2a  mov     edx, ebx
0x18002bc2c  mov     ecx, 2
0x18002bc31  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bc36  nop
0x18002bc37  mov     rcx, [rbp+lpExistingFileName]
0x18002bc3b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bc3f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bc44  mov     eax, ebx
0x18002bc46  jmp     loc_18002BFD1
0x18002bc4b  xor     r8d, r8d
0x18002bc4e  lea     rdx, [rbp+lpExistingFileName]
0x18002bc52  mov     rcx, r14
0x18002bc55  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x18002bc5a  mov     edi, eax
0x18002bc5c  mov     rbx, [rbp+lpExistingFileName]
0x18002bc60  test    eax, eax
0x18002bc62  jns     short loc_18002BCB0
0x18002bc64  mov     [rsp+78h+var_40], rbx
0x18002bc69  mov     rcx, [r14]
0x18002bc6c  mov     [rsp+78h+Description], rcx
0x18002bc71  lea     rax, aFailedToCopyST; "Failed to copy [%s] to [%s]"
0x18002bc78  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bc7d  mov     [rsp+78h+IsolationFlags], 3Bh ; ';'
0x18002bc85  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bc8c  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bc93  mov     edx, edi
0x18002bc95  mov     ecx, 2
0x18002bc9a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bc9f  nop
0x18002bca0  lea     rcx, [rbx-18h]; this
0x18002bca4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bca9  mov     eax, edi
0x18002bcab  jmp     loc_18002BFD1
0x18002bcb0  cmp     qword ptr [rsi+1C0h], 0
0x18002bcb8  jz      loc_18002BD5D
0x18002bcbe  lea     rdx, aSwapwinresSave; "SwapWinREs: Save destionation new WinRE"...
0x18002bcc5  xor     ecx, ecx
0x18002bcc7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002bccc  mov     rdi, [rsi+1C0h]
0x18002bcd3  lea     rdx, aDestnewwimpath; "DestNewWimPath"
0x18002bcda  lea     rcx, [rbp+var_28]
0x18002bcde  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002bce3  nop
0x18002bce4  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002bceb  lea     rcx, [rbp+var_30]
0x18002bcef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002bcf4  nop
0x18002bcf5  lea     r9, [rbp+lpExistingFileName]
0x18002bcf9  lea     r8, [rbp+var_28]
0x18002bcfd  lea     rdx, [rbp+var_30]
0x18002bd01  mov     rcx, rdi
0x18002bd04  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002bd09  mov     edi, eax
0x18002bd0b  mov     rcx, [rbp+var_30]
0x18002bd0f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bd13  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bd18  nop
0x18002bd19  mov     rcx, [rbp+var_28]
0x18002bd1d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002bd21  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bd26  test    edi, edi
0x18002bd28  jns     short loc_18002BD5D
0x18002bd2a  lea     rax, aFailedToSaveDe; "Failed to save destionation new WinRE p"...
0x18002bd31  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bd36  mov     [rsp+78h+IsolationFlags], 44h ; 'D'
0x18002bd3e  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bd45  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bd4c  mov     edx, edi
0x18002bd4e  mov     ecx, 2
0x18002bd53  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bd58  jmp     loc_18002BCA0
0x18002bd5d  lea     rax, Description; "SwapWinREs"
0x18002bd64  mov     [rsp+78h+Description], rax; Description
0x18002bd69  mov     [rsp+78h+Timeout], 0; Timeout
0x18002bd71  mov     [rsp+78h+IsolationFlags], 0; IsolationFlags
0x18002bd79  xor     r9d, r9d; IsolationLevel
0x18002bd7c  xor     r8d, r8d; CreateOptions
0x18002bd7f  xor     edx, edx; UOW
0x18002bd81  xor     ecx, ecx; lpTransactionAttributes
0x18002bd83  call    cs:__imp_CreateTransaction
0x18002bd89  lea     r12, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x18002bd90  mov     [rbp+var_20], r12
0x18002bd94  mov     [rbp+var_18], rax
0x18002bd98  lea     rcx, [rbp+var_20]
0x18002bd9c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002bda1  cmp     qword ptr [rax], 0
0x18002bda5  jz      loc_18002BF65
0x18002bdab  mov     rax, [rbp+var_20]
0x18002bdaf  lea     rcx, [rbp+var_20]
0x18002bdb3  mov     rax, [rax+20h]
0x18002bdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbc  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18002bdc0  jz      loc_18002BF65
0x18002bdc6  mov     rax, [rbp+var_20]
0x18002bdca  lea     rcx, [rbp+var_20]
0x18002bdce  mov     rax, [rax+20h]
0x18002bdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdd7  mov     rcx, [rax]
0x18002bdda  mov     qword ptr [rsp+78h+Timeout], rcx; hTransaction
0x18002bddf  mov     [rsp+78h+IsolationFlags], 1; dwFlags
0x18002bde7  xor     r9d, r9d; lpData
0x18002bdea  xor     r8d, r8d; lpProgressRoutine
0x18002bded  mov     rdx, [rsi+78h]; lpNewFileName
0x18002bdf1  mov     rcx, rbx; lpExistingFileName
0x18002bdf4  call    cs:__imp_MoveFileTransactedW
0x18002bdfa  test    eax, eax
0x18002bdfc  jnz     short loc_18002BE65
0x18002bdfe  call    cs:__imp_GetLastError
0x18002be04  mov     edi, 80070000h
0x18002be09  test    eax, eax
0x18002be0b  jle     short loc_18002BE12
0x18002be0d  movzx   eax, ax
0x18002be10  or      eax, edi
0x18002be12  lea     rcx, aFailedToReplac_0; "Failed to replace old winre.wim with up"...
0x18002be19  mov     qword ptr [rsp+78h+Timeout], rcx
0x18002be1e  mov     [rsp+78h+IsolationFlags], 60h ; '`'
0x18002be26  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002be2d  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002be34  mov     edx, eax
0x18002be36  mov     ecx, 2
0x18002be3b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002be40  call    cs:__imp_GetLastError
0x18002be46  test    eax, eax
0x18002be48  mov     esi, eax
0x18002be4a  jle     short loc_18002BE51
0x18002be4c  movzx   esi, ax
0x18002be4f  or      esi, edi
0x18002be51  mov     [rbp+var_20], r12
0x18002be55  lea     rcx, [rbp+var_18]
0x18002be59  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18002be5e  mov     edi, esi
0x18002be60  jmp     loc_18002BCA0
0x18002be65  mov     rax, [rbp+var_20]
0x18002be69  lea     rcx, [rbp+var_20]
0x18002be6d  mov     rax, [rax+20h]
0x18002be71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be76  mov     rcx, [rax]; TransactionHandle
0x18002be79  call    cs:__imp_CommitTransaction
0x18002be7f  test    eax, eax
0x18002be81  jnz     short loc_18002BEB0
0x18002be83  call    cs:__imp_GetLastError
0x18002be89  mov     edi, 80070000h
0x18002be8e  test    eax, eax
0x18002be90  jle     short loc_18002BE97
0x18002be92  movzx   eax, ax
0x18002be95  or      eax, edi
0x18002be97  lea     rcx, aFailedToCommit; "Failed to commit transaction"
0x18002be9e  mov     qword ptr [rsp+78h+Timeout], rcx
0x18002bea3  mov     [rsp+78h+IsolationFlags], 65h ; 'e'
0x18002beab  jmp     loc_18002BE26
0x18002beb0  cmp     qword ptr [rsi+1C0h], 0
0x18002beb8  jz      short loc_18002BF25
0x18002beba  mov     edi, 3
0x18002bebf  mov     r8d, edi
0x18002bec2  lea     rdx, aSwapwinresAddC; "SwapWinREs: Add checkpoint [%u]"
0x18002bec9  xor     ecx, ecx
0x18002becb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002bed0  mov     edx, edi
0x18002bed2  mov     rcx, [rsi+1C0h]
0x18002bed9  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x18002bede  mov     edi, eax
0x18002bee0  test    eax, eax
0x18002bee2  jns     short loc_18002BF25
0x18002bee4  lea     rax, aFailedToSetChe; "Failed to set checkpoint for SwapWinREs"
0x18002beeb  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bef0  mov     [rsp+78h+IsolationFlags], 6Dh ; 'm'
0x18002bef8  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002beff  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bf06  mov     edx, edi
0x18002bf08  mov     ecx, 2
0x18002bf0d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bf12  nop
0x18002bf13  mov     [rbp+var_20], r12
0x18002bf17  lea     rcx, [rbp+var_18]
0x18002bf1b  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18002bf20  jmp     loc_18002BCA0
0x18002bf25  mov     rcx, r14
0x18002bf28  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x18002bf2d  mov     edi, eax
0x18002bf2f  test    eax, eax
0x18002bf31  jns     short loc_18002BF13
0x18002bf33  lea     rax, aFailedToCleanu_3; "Failed to cleanup the updated wim"
0x18002bf3a  mov     qword ptr [rsp+78h+Timeout], rax
0x18002bf3f  mov     [rsp+78h+IsolationFlags], 73h ; 's'
0x18002bf47  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bf4e  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bf55  mov     edx, edi
0x18002bf57  mov     ecx, 1
0x18002bf5c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bf61  xor     edi, edi
0x18002bf63  jmp     short loc_18002BF13
0x18002bf65  call    cs:__imp_GetLastError
0x18002bf6b  mov     edi, 80070000h
0x18002bf70  test    eax, eax
0x18002bf72  jle     short loc_18002BF79
0x18002bf74  movzx   eax, ax
0x18002bf77  or      eax, edi
0x18002bf79  lea     rcx, aFailedToCreate; "Failed to create transaction handle"
0x18002bf80  mov     qword ptr [rsp+78h+Timeout], rcx
0x18002bf85  mov     [rsp+78h+IsolationFlags], 53h ; 'S'
0x18002bf8d  lea     r9, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002bf94  lea     r8, aWinreagentSwap_1; "WinREAgent::SwapWinREs::InternalExecute"
0x18002bf9b  mov     edx, eax
0x18002bf9d  mov     ecx, 2
0x18002bfa2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002bfa7  call    cs:__imp_GetLastError
0x18002bfad  mov     esi, eax
0x18002bfaf  test    eax, eax
0x18002bfb1  jle     short loc_18002BFB8
0x18002bfb3  movzx   esi, ax
0x18002bfb6  or      esi, edi
0x18002bfb8  mov     [rbp+var_20], r12
0x18002bfbc  lea     rcx, [rbp+var_18]
0x18002bfc0  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18002bfc5  nop
0x18002bfc6  lea     rcx, [rbx-18h]; this
0x18002bfca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002bfcf  mov     eax, esi
0x18002bfd1  mov     rcx, [rbp+var_10]
0x18002bfd5  xor     rcx, rsp; StackCookie
0x18002bfd8  call    __security_check_cookie
0x18002bfdd  add     rsp, 78h
0x18002bfe1  pop     r14
0x18002bfe3  pop     r12
0x18002bfe5  pop     rdi
0x18002bfe6  pop     rsi
0x18002bfe7  pop     rbx
0x18002bfe8  pop     rbp
0x18002bfe9  retn
```
