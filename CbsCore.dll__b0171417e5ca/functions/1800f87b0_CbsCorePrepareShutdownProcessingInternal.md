# CbsCorePrepareShutdownProcessingInternal

- ea: `0x1800f87b0`
- end: `0x1800f8ae3`
- name: `CbsCorePrepareShutdownProcessingInternal`
- size: `819`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f8740`

## callees

- `0x18004a920`
- `0x18005b180`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800f84c8`
- `0x1800f87b0`
- `0x180123cf0`
- `0x1801bcb4c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f8978`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f8978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8a58`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f8a40`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f8a40`

## string_xrefs

- `0x1800f8878`: `System\CurrentControlSet\Services\TrustedInstaller`
- `0x1800f88da`: `System\CurrentControlSet\Services\TrustedInstaller`
- `0x1800f88a1`: `Unable to read PreshutdownTimeout from the registry`
- `0x1800f8943`: `Unable to make service wait.`
- `0x1800f88fd`: `Unable to read BlockTimeIncrement from the registry`
- `0x1800f89ae`: `Shtd: Failed to create shutdown processing event.`
- `0x1800f8a72`: `Shtd: Failed to create progress thread.`

## pseudocode

```c
int __fastcall CbsCorePrepareShutdownProcessingInternal(LPVOID lpParameter)
{
  unsigned int CurrentProgress; // eax
  unsigned int DWORDValue; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  signed int LastError; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int dwCreationFlags; // [rsp+20h] [rbp-20h]
  __int128 v13; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF
  unsigned int *v16; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v17; // [rsp+88h] [rbp+48h] BYREF

  v17 = 1;
  LODWORD(v16) = 1;
  v15 = 11;
  if ( dword_1803B3F08 )
    return -2146498272;
  if ( !vhProgressThread )
  {
    LogAdapter::TraceAtLevel<>(1, "Shtd: Prepare for shutdown processing.");
    v13 = CbsShutdownProcessingStartEvent;
    CbsGenericEventReport(&v13, L"Shtd: Prepare for shutdown processing.");
    CurrentProgress = CCbsSessionManager::GetCurrentProgress(
                        (CCbsSessionManager *)qword_1803B11E8,
                        &v17,
                        (unsigned int *)&v16,
                        (enum RELEASE_TYPE::RELEASE *)&v15);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, CurrentProgress, "Shtd: Unable to get current progress information.");
    InitializeProgress(v17, (unsigned int)v16, v15);
    DWORDValue = CbsRegQueryDWORDValue(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Services\\TrustedInstaller",
                   1u,
                   L"PreshutdownTimeout",
                   &vdwPreshutdownTimeout);
    if ( (int)(DWORDValue + 0x80000000) >= 0 && DWORDValue != -2147024894 )
      LogAdapter::TraceAtLevelIfFailed<long,>(1, DWORDValue, "Unable to read PreshutdownTimeout from the registry");
    if ( !vdwPreshutdownTimeout )
      vdwPreshutdownTimeout = 1800000;
    v5 = CbsRegQueryDWORDValue(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\TrustedInstaller",
           1u,
           L"BlockTimeIncrement",
           &vdwBlockTimeIncrement);
    if ( ((v5 + 0x80000000) & 0x80000000) == 0 && v5 != -2147024894 )
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v5, "Unable to read BlockTimeIncrement from the registry");
    v6 = vdwBlockTimeIncrement;
    if ( !vdwBlockTimeIncrement )
      v6 = 900;
    vdwWaitHint = vdwPreshutdownTimeout;
    vdwBlockTimeIncrement = 1000 * v6;
    v7 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 88LL))(lpParameter);
    LogAdapter::TraceAtLevelIfFailed<long,>(2, v7, "Unable to make service wait.");
    LogAdapter::TraceAtLevel<unsigned long,unsigned long>(
      1,
      "Shtd: PreshutdownTimeout: {}ms, BlockTimeIncrement: {}ms",
      &vdwPreshutdownTimeout,
      &vdwBlockTimeIncrement);
    vhShutdownProcessingCompletionEvent = CreateEventW(0, 1, 0, 0);
    if ( vhShutdownProcessingCompletionEvent )
    {
      vhProgressThread = CreateThread(0, 0, ShutdownProgressThreadProc, lpParameter, 0, 0);
      if ( !vhProgressThread )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Shtd: Failed to create progress thread.");
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          else
            v11 = LastError;
          v15 = v11;
          v16 = &v15;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)&v16);
        }
        if ( LastError )
        {
          v10 = 113;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v10,
                   (unsigned int)"onecore\\base\\cbs\\core\\cbscoreshutdown.cpp",
                   (const char *)(unsigned int)LastError,
                   dwCreationFlags);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Shtd: Failed to create shutdown processing event.");
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        else
          v9 = LastError;
        v15 = v9;
        v16 = &v15;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&v16);
      }
      if ( LastError )
      {
        v10 = 110;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v10,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbscoreshutdown.cpp",
                 (const char *)(unsigned int)LastError,
                 dwCreationFlags);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800f87b0  mov     [rsp-28h+arg_0], rbx
0x1800f87b5  push    rbp
0x1800f87b6  push    rsi
0x1800f87b7  push    r12
0x1800f87b9  push    r13
0x1800f87bb  push    r14
0x1800f87bd  mov     rbp, rsp
0x1800f87c0  sub     rsp, 40h
0x1800f87c4  cmp     cs:dword_1803B3F08, 0
0x1800f87cb  mov     esi, 1
0x1800f87d0  mov     [rbp+arg_18], esi
0x1800f87d3  mov     rbx, rcx
0x1800f87d6  mov     dword ptr [rbp+arg_10], esi
0x1800f87d9  mov     [rbp+arg_8], 0Bh
0x1800f87e0  jz      short loc_1800F87EC
0x1800f87e2  mov     eax, 800F0920h
0x1800f87e7  jmp     loc_1800F8AD0
0x1800f87ec  cmp     cs:?vhProgressThread@@3PEAXEA, 0; void * vhProgressThread
0x1800f87f4  jnz     loc_1800F8ACE
0x1800f87fa  lea     rdx, aShtdPrepareFor; "Shtd: Prepare for shutdown processing."
0x1800f8801  mov     ecx, esi
0x1800f8803  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800f8808  movups  xmm0, cs:CbsShutdownProcessingStartEvent
0x1800f880f  lea     rdx, aShtdPrepareFor_0; "Shtd: Prepare for shutdown processing."
0x1800f8816  lea     rcx, [rbp+var_10]
0x1800f881a  movdqu  [rbp+var_10], xmm0
0x1800f881f  call    CbsGenericEventReport
0x1800f8824  mov     rcx, cs:qword_1803B11E8; this
0x1800f882b  lea     r9, [rbp+arg_8]; enum RELEASE_TYPE::RELEASE *
0x1800f882f  lea     r8, [rbp+arg_10]; unsigned int *
0x1800f8833  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800f8837  call    ?GetCurrentProgress@CCbsSessionManager@@QEAAJPEAI0PEAW4RELEASE@RELEASE_TYPE@@@Z; CCbsSessionManager::GetCurrentProgress(uint *,uint *,RELEASE_TYPE::RELEASE *)
0x1800f883c  mov     r14d, 3
0x1800f8842  lea     r8, aShtdUnableToGe; "Shtd: Unable to get current progress in"...
0x1800f8849  mov     ecx, r14d
0x1800f884c  mov     edx, eax
0x1800f884e  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f8853  mov     r8d, [rbp+arg_8]
0x1800f8857  mov     edx, dword ptr [rbp+arg_10]
0x1800f885a  mov     ecx, [rbp+arg_18]
0x1800f885d  call    ?InitializeProgress@@YAXIIW4RELEASE@RELEASE_TYPE@@@Z; InitializeProgress(uint,uint,RELEASE_TYPE::RELEASE)
0x1800f8862  lea     rax, ?vdwPreshutdownTimeout@@3KA; ulong vdwPreshutdownTimeout
0x1800f8869  mov     r8d, esi; unsigned int
0x1800f886c  lea     r9, aPreshutdowntim; "PreshutdownTimeout"
0x1800f8873  mov     qword ptr [rsp+40h+dwCreationFlags], rax; unsigned int *
0x1800f8878  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tr"...
0x1800f887f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800f8886  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800f888b  mov     r13d, 80000000h
0x1800f8891  lea     ecx, [rax+r13]
0x1800f8895  test    r13d, ecx
0x1800f8898  jnz     short loc_1800F88B1
0x1800f889a  cmp     eax, 80070002h
0x1800f889f  jz      short loc_1800F88B1
0x1800f88a1  lea     r8, aUnableToReadPr_0; "Unable to read PreshutdownTimeout from "...
0x1800f88a8  mov     edx, eax
0x1800f88aa  mov     ecx, esi
0x1800f88ac  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f88b1  cmp     cs:?vdwPreshutdownTimeout@@3KA, 0; ulong vdwPreshutdownTimeout
0x1800f88b8  jnz     short loc_1800F88C4
0x1800f88ba  mov     cs:?vdwPreshutdownTimeout@@3KA, 1B7740h; ulong vdwPreshutdownTimeout
0x1800f88c4  lea     r12, ?vdwBlockTimeIncrement@@3KA; ulong vdwBlockTimeIncrement
0x1800f88cb  mov     r8d, esi; unsigned int
0x1800f88ce  lea     r9, aBlocktimeincre; "BlockTimeIncrement"
0x1800f88d5  mov     qword ptr [rsp+40h+dwCreationFlags], r12; unsigned int *
0x1800f88da  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tr"...
0x1800f88e1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800f88e8  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800f88ed  lea     ecx, [rax+r13]
0x1800f88f1  test    r13d, ecx
0x1800f88f4  jnz     short loc_1800F890D
0x1800f88f6  cmp     eax, 80070002h
0x1800f88fb  jz      short loc_1800F890D
0x1800f88fd  lea     r8, aUnableToReadBl_0; "Unable to read BlockTimeIncrement from "...
0x1800f8904  mov     edx, eax
0x1800f8906  mov     ecx, esi
0x1800f8908  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f890d  mov     eax, cs:?vdwBlockTimeIncrement@@3KA; ulong vdwBlockTimeIncrement
0x1800f8913  test    eax, eax
0x1800f8915  jnz     short loc_1800F891C
0x1800f8917  mov     eax, 384h
0x1800f891c  mov     edx, cs:?vdwPreshutdownTimeout@@3KA; ulong vdwPreshutdownTimeout
0x1800f8922  mov     rcx, rbx
0x1800f8925  imul    eax, 3E8h
0x1800f892b  mov     cs:?vdwWaitHint@@3KA, edx; ulong vdwWaitHint
0x1800f8931  mov     cs:?vdwBlockTimeIncrement@@3KA, eax; ulong vdwBlockTimeIncrement
0x1800f8937  mov     rax, [rbx]
0x1800f893a  mov     rax, [rax+58h]
0x1800f893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8943  lea     r8, aUnableToMakeSe; "Unable to make service wait."
0x1800f894a  mov     edx, eax
0x1800f894c  mov     ecx, 2
0x1800f8951  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800f8956  mov     r9, r12
0x1800f8959  lea     r8, ?vdwPreshutdownTimeout@@3KA; ulong vdwPreshutdownTimeout
0x1800f8960  lea     rdx, aShtdPreshutdow; "Shtd: PreshutdownTimeout: {}ms, BlockTi"...
0x1800f8967  mov     ecx, esi
0x1800f8969  call    ??$TraceAtLevel@KK@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK2@Z; LogAdapter::TraceAtLevel<ulong,ulong>(LogAdapter::LogLevel,char const * const,ulong const &,ulong const &)
0x1800f896e  xor     r9d, r9d; lpName
0x1800f8971  xor     r8d, r8d; bInitialState
0x1800f8974  mov     edx, esi; bManualReset
0x1800f8976  xor     ecx, ecx; lpEventAttributes
0x1800f8978  call    cs:__imp_CreateEventW
0x1800f897f  nop     dword ptr [rax+rax+00h]
0x1800f8984  mov     cs:?vhShutdownProcessingCompletionEvent@@3PEAXEA, rax; void * vhShutdownProcessingCompletionEvent
0x1800f898b  test    rax, rax
0x1800f898e  jnz     loc_1800F8A21
0x1800f8994  call    cs:__imp_GetLastError
0x1800f899b  nop     dword ptr [rax+rax+00h]
0x1800f89a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f89a7  mov     ebx, eax
0x1800f89a9  test    rcx, rcx
0x1800f89ac  jz      short loc_1800F89FC
0x1800f89ae  lea     r9, aShtdFailedToCr_0; "Shtd: Failed to create shutdown process"...
0x1800f89b5  mov     r8d, r14d
0x1800f89b8  xor     edx, edx
0x1800f89ba  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f89bf  test    ebx, ebx
0x1800f89c1  jg      short loc_1800F89C7
0x1800f89c3  mov     eax, ebx
0x1800f89c5  jmp     short loc_1800F89CF
0x1800f89c7  movzx   eax, bx
0x1800f89ca  or      eax, 80070000h
0x1800f89cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f89d6  lea     r9, a0; ": {0}"
0x1800f89dd  mov     [rbp+arg_8], eax
0x1800f89e0  mov     r8d, r14d
0x1800f89e3  lea     rax, [rbp+arg_8]
0x1800f89e7  mov     dl, sil
0x1800f89ea  mov     [rbp+arg_10], rax
0x1800f89ee  lea     rax, [rbp+arg_10]
0x1800f89f2  mov     qword ptr [rsp+40h+dwCreationFlags], rax; unsigned int
0x1800f89f7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f89fc  test    ebx, ebx
0x1800f89fe  jz      loc_1800F8ACE
0x1800f8a04  mov     edx, 6Eh ; 'n'; void *
0x1800f8a09  mov     rcx, [rbp+28h]; this
0x1800f8a0d  lea     r8, aOnecoreBaseCbs_129; "onecore\\base\\cbs\\core\\cbscoreshutdo"...
0x1800f8a14  mov     r9d, ebx; char *
0x1800f8a17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f8a1c  jmp     loc_1800F8AD0
0x1800f8a21  mov     [rsp+40h+lpThreadId], 0; lpThreadId
0x1800f8a2a  lea     r8, ?ShutdownProgressThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800f8a31  mov     r9, rbx; lpParameter
0x1800f8a34  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x1800f8a3c  xor     edx, edx; dwStackSize
0x1800f8a3e  xor     ecx, ecx; lpThreadAttributes
0x1800f8a40  call    cs:__imp_CreateThread
0x1800f8a47  nop     dword ptr [rax+rax+00h]
0x1800f8a4c  mov     cs:?vhProgressThread@@3PEAXEA, rax; void * vhProgressThread
0x1800f8a53  test    rax, rax
0x1800f8a56  jnz     short loc_1800F8ACE
0x1800f8a58  call    cs:__imp_GetLastError
0x1800f8a5f  nop     dword ptr [rax+rax+00h]
0x1800f8a64  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f8a6b  mov     ebx, eax
0x1800f8a6d  test    rcx, rcx
0x1800f8a70  jz      short loc_1800F8AC0
0x1800f8a72  lea     r9, aShtdFailedToCr; "Shtd: Failed to create progress thread."
0x1800f8a79  mov     r8d, r14d
0x1800f8a7c  xor     edx, edx
0x1800f8a7e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f8a83  test    ebx, ebx
0x1800f8a85  jg      short loc_1800F8A8B
0x1800f8a87  mov     eax, ebx
0x1800f8a89  jmp     short loc_1800F8A93
0x1800f8a8b  movzx   eax, bx
0x1800f8a8e  or      eax, 80070000h
0x1800f8a93  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f8a9a  lea     r9, a0; ": {0}"
0x1800f8aa1  mov     [rbp+arg_8], eax
0x1800f8aa4  mov     r8d, r14d
0x1800f8aa7  lea     rax, [rbp+arg_8]
0x1800f8aab  mov     dl, sil
0x1800f8aae  mov     [rbp+arg_10], rax
0x1800f8ab2  lea     rax, [rbp+arg_10]
0x1800f8ab6  mov     qword ptr [rsp+40h+dwCreationFlags], rax
0x1800f8abb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f8ac0  test    ebx, ebx
0x1800f8ac2  jz      short loc_1800F8ACE
0x1800f8ac4  mov     edx, 71h ; 'q'
0x1800f8ac9  jmp     loc_1800F8A09
0x1800f8ace  xor     eax, eax
0x1800f8ad0  mov     rbx, [rsp+40h+arg_0]
0x1800f8ad5  add     rsp, 40h
0x1800f8ad9  pop     r14
0x1800f8adb  pop     r13
0x1800f8add  pop     r12
0x1800f8adf  pop     rsi
0x1800f8ae0  pop     rbp
0x1800f8ae1  retn
```
