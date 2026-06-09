# DpxResumeAndShowProgress(IDpxJob *,ulong,ICbsBusinessScenario *)

- ea: `0x1800cc408`
- end: `0x1800cc83b`
- name: `?DpxResumeAndShowProgress@@YAJPEAUIDpxJob@@KPEAUICbsBusinessScenario@@@Z`
- size: `1075`
- prototype: `__int64 __fastcall(struct IDpxJob *lpParameter, unsigned int, struct ICbsBusinessScenario *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cf934`

## callees

- `0x1800150c0`
- `0x18004a680`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800a9014`
- `0x1800ae508`
- `0x1800cc408`
- `0x1800cf0c0`
- `0x1800eb920`
- `0x1800ec920`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cc6cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cc6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc616`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800cc601`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800cc601`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800cc78c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800cc78c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cc4df`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cc4df`

## string_xrefs

- `0x1800cc635`: `Failed to resume DPX thread after setting impersonation token`
- `0x1800cc51f`: `CreateThreadFailed`
- `0x1800cc5a5`: `Failed to duplicate token on DPX thread`
- `0x1800cc74b`: `Unable to update progress in during DPX expansion.`
- `0x1800cc7f3`: `Unable to update progress in during DPX expansion.`

## pseudocode

```c
__int64 __fastcall DpxResumeAndShowProgress(
        struct IDpxJob *lpParameter,
        unsigned int a2,
        struct ICbsBusinessScenario *a3)
{
  __int64 v3; // r13
  HANDLE v7; // rax
  HANDLE v8; // rbx
  signed int LastError; // edi
  DWORD v10; // eax
  __int64 v11; // rdx
  signed int v12; // eax
  DWORD v13; // edi
  __int64 v14; // rdx
  DWORD v15; // ebx
  DWORD v16; // eax
  int v17; // eax
  char v18; // si
  int v19; // r12d
  DWORD v20; // eax
  int v21; // eax
  unsigned __int64 v22; // rax
  int v23; // edi
  unsigned int v24; // eax
  const char *v25; // r9
  unsigned int v26; // eax
  int dwCreationFlags; // [rsp+20h] [rbp-79h]
  unsigned int dwCreationFlagsa; // [rsp+20h] [rbp-79h]
  HANDLE hThread; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v30[2]; // [rsp+38h] [rbp-61h] BYREF
  void *Thread; // [rsp+40h] [rbp-59h] BYREF
  DWORD ExitCode; // [rsp+48h] [rbp-51h] BYREF
  DWORD ThreadId; // [rsp+4Ch] [rbp-4Dh] BYREF
  _BYTE v34[48]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v35; // [rsp+80h] [rbp-19h]
  __int64 v36; // [rsp+88h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v3 = a2;
  if ( lpParameter )
  {
    hThread = 0;
    ThreadId = 0;
    v7 = CreateThread(0, 0, DpxThreadResumeJobProc, lpParameter, 4u, &ThreadId);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hThread, v7);
    v8 = hThread;
    if ( hThread )
    {
      Thread = hThread;
      v12 = DuplicateCurrentThreadToken(&Thread);
      v13 = v12;
      if ( v12 < 0 )
      {
        ExitCode = v12;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to duplicate token on DPX thread");
          *(_QWORD *)v30 = &ExitCode;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v30);
        }
        v14 = 336;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
          (const char *)v13,
          dwCreationFlagsa);
        v15 = v13;
        goto LABEL_46;
      }
      if ( ResumeThread(v8) == -1 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to resume DPX thread after setting impersonation token");
          if ( LastError > 0 )
            v16 = (unsigned __int16)LastError | 0x80070000;
          else
            v16 = LastError;
          ExitCode = v16;
          *(_QWORD *)v30 = &ExitCode;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v30);
        }
        if ( LastError )
        {
          v11 = 342;
LABEL_26:
          v17 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
                  (const char *)(unsigned int)LastError,
                  dwCreationFlagsa);
LABEL_27:
          v15 = v17;
          goto LABEL_46;
        }
      }
      else
      {
        v18 = 1;
        v19 = 0;
        while ( v18 )
        {
          memset_0(v34, 0, 0x58u);
          v20 = WaitForSingleObject(v8, 0x3E8u);
          if ( v20 )
          {
            if ( v20 == 258 )
            {
              v21 = ((__int64 (__fastcall *)(struct IDpxJob *, _BYTE *))lpParameter->lpVtbl->GetProgress)(
                      lpParameter,
                      v34);
              if ( v21 < 0 )
              {
                LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v21, "Unable to GetProgress on the DPX job.");
              }
              else if ( v36 )
              {
                v22 = v35 * v3 / (unsigned __int64)(v35 + v36);
                v23 = v22;
                if ( a3 )
                {
                  v24 = (*(__int64 (__fastcall **)(struct ICbsBusinessScenario *, __int64, __int64, _QWORD))(*(_QWORD *)a3 + 40LL))(
                          a3,
                          48,
                          4294967294LL,
                          (unsigned int)(v22 - v19));
                  LogAdapter::TraceAtLevelIfFailed<long,>(1, v24, "Unable to update progress in during DPX expansion.");
                }
                v19 = v23;
              }
            }
            else
            {
              v18 = 0;
            }
          }
          else
          {
            ExitCode = 0;
            if ( !GetExitCodeThread(v8, &ExitCode) )
            {
              v17 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x163,
                      (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
                      v25);
              goto LABEL_27;
            }
            v13 = ExitCode;
            v18 = 0;
            if ( (ExitCode & 0x80000000) != 0 )
            {
              v14 = 356;
              goto LABEL_17;
            }
          }
        }
        if ( a3 )
        {
          v26 = (*(__int64 (__fastcall **)(struct ICbsBusinessScenario *, __int64, __int64, _QWORD))(*(_QWORD *)a3 + 40LL))(
                  a3,
                  48,
                  4294967294LL,
                  (unsigned int)(v3 - v19));
          LogAdapter::TraceAtLevelIfFailed<long,>(1, v26, "Unable to update progress in during DPX expansion.");
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
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"CreateThreadFailed");
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        else
          v10 = LastError;
        ExitCode = v10;
        Thread = &ExitCode;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&Thread);
      }
      if ( LastError )
      {
        v11 = 330;
        goto LABEL_26;
      }
    }
    v15 = 0;
LABEL_46:
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hThread);
    return v15;
  }
  ExitCode = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No dpx job specified");
    hThread = &ExitCode;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&hThread);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13D,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
    (const char *)0x80070057LL,
    dwCreationFlags);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800cc408  mov     [rsp-8+arg_18], rbx
0x1800cc40d  push    rbp
0x1800cc40e  push    rsi
0x1800cc40f  push    rdi
0x1800cc410  push    r12
0x1800cc412  push    r13
0x1800cc414  push    r14
0x1800cc416  push    r15
0x1800cc418  lea     rbp, [rsp-27h]
0x1800cc41d  sub     rsp, 0C0h
0x1800cc424  mov     rax, cs:__security_cookie
0x1800cc42b  xor     rax, rsp
0x1800cc42e  mov     [rbp+57h+var_40], rax
0x1800cc432  mov     r13d, edx
0x1800cc435  mov     r15, r8
0x1800cc438  mov     r14, rcx
0x1800cc43b  test    rcx, rcx
0x1800cc43e  jnz     short loc_1800CC4B1
0x1800cc440  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc447  mov     edi, 80070057h
0x1800cc44c  mov     [rbp+57h+ExitCode], edi
0x1800cc44f  test    rcx, rcx
0x1800cc452  jz      short loc_1800CC492
0x1800cc454  lea     ebx, [r14+3]
0x1800cc458  xor     edx, edx
0x1800cc45a  mov     r8d, ebx
0x1800cc45d  lea     r9, aNoDpxJobSpecif; "No dpx job specified"
0x1800cc464  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cc469  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc470  lea     rax, [rbp+57h+ExitCode]
0x1800cc474  mov     [rbp+57h+hThread], rax
0x1800cc478  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc47f  lea     rax, [rbp+57h+hThread]
0x1800cc483  mov     r8d, ebx
0x1800cc486  mov     dl, 1
0x1800cc488  mov     qword ptr [rsp+0F0h+dwCreationFlags], rax; int
0x1800cc48d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc492  mov     rcx, [rbp+5Fh]; this
0x1800cc496  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cc49d  mov     r9d, edi; char *
0x1800cc4a0  mov     edx, 13Dh; void *
0x1800cc4a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc4aa  mov     eax, edi
0x1800cc4ac  jmp     loc_1800CC813
0x1800cc4b1  lea     rax, [rbp+57h+ThreadId]
0x1800cc4b5  mov     [rbp+57h+hThread], 0
0x1800cc4bd  mov     [rsp+0F0h+lpThreadId], rax; lpThreadId
0x1800cc4c2  lea     r8, ?DpxThreadResumeJobProc@@YAKPEAX@Z; lpStartAddress
0x1800cc4c9  mov     r9, r14; lpParameter
0x1800cc4cc  mov     [rsp+0F0h+dwCreationFlags], 4; dwCreationFlags
0x1800cc4d4  xor     edx, edx; dwStackSize
0x1800cc4d6  mov     [rbp+57h+ThreadId], 0
0x1800cc4dd  xor     ecx, ecx; lpThreadAttributes
0x1800cc4df  call    cs:__imp_CreateThread
0x1800cc4e6  nop     dword ptr [rax+rax+00h]
0x1800cc4eb  mov     rdx, rax
0x1800cc4ee  lea     rcx, [rbp+57h+hThread]
0x1800cc4f2  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800cc4f7  mov     rbx, [rbp+57h+hThread]
0x1800cc4fb  test    rbx, rbx
0x1800cc4fe  jnz     short loc_1800CC57E
0x1800cc500  call    cs:__imp_GetLastError
0x1800cc507  nop     dword ptr [rax+rax+00h]
0x1800cc50c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc513  mov     edi, eax
0x1800cc515  test    rcx, rcx
0x1800cc518  jz      short loc_1800CC56C
0x1800cc51a  mov     ebx, 3
0x1800cc51f  lea     r9, aCreatethreadfa; "CreateThreadFailed"
0x1800cc526  mov     r8d, ebx
0x1800cc529  xor     edx, edx
0x1800cc52b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cc530  test    edi, edi
0x1800cc532  jg      short loc_1800CC538
0x1800cc534  mov     eax, edi
0x1800cc536  jmp     short loc_1800CC540
0x1800cc538  movzx   eax, di
0x1800cc53b  or      eax, 80070000h
0x1800cc540  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc547  lea     r9, a0; ": {0}"
0x1800cc54e  mov     [rbp+57h+ExitCode], eax
0x1800cc551  mov     r8d, ebx
0x1800cc554  lea     rax, [rbp+57h+ExitCode]
0x1800cc558  mov     dl, 1
0x1800cc55a  mov     [rbp+57h+Thread], rax
0x1800cc55e  lea     rax, [rbp+57h+Thread]
0x1800cc562  mov     qword ptr [rsp+0F0h+dwCreationFlags], rax
0x1800cc567  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc56c  test    edi, edi
0x1800cc56e  jz      loc_1800CC806
0x1800cc574  mov     edx, 14Ah
0x1800cc579  jmp     loc_1800CC68F
0x1800cc57e  lea     rcx, [rbp+57h+Thread]; Thread
0x1800cc582  mov     [rbp+57h+Thread], rbx
0x1800cc586  call    ?DuplicateCurrentThreadToken@@YAJQEAPEAX@Z; DuplicateCurrentThreadToken(void * * const)
0x1800cc58b  mov     edi, eax
0x1800cc58d  test    eax, eax
0x1800cc58f  jns     short loc_1800CC5FE
0x1800cc591  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc598  mov     [rbp+57h+ExitCode], eax
0x1800cc59b  test    rcx, rcx
0x1800cc59e  jz      short loc_1800CC5DF
0x1800cc5a0  mov     ebx, 3
0x1800cc5a5  lea     r9, aFailedToDuplic_5; "Failed to duplicate token on DPX thread"
0x1800cc5ac  mov     r8d, ebx
0x1800cc5af  xor     edx, edx
0x1800cc5b1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cc5b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc5bd  lea     rax, [rbp+57h+ExitCode]
0x1800cc5c1  mov     qword ptr [rbp+57h+var_B8], rax
0x1800cc5c5  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc5cc  lea     rax, [rbp+57h+var_B8]
0x1800cc5d0  mov     r8d, ebx
0x1800cc5d3  mov     dl, 1
0x1800cc5d5  mov     qword ptr [rsp+0F0h+dwCreationFlags], rax; int
0x1800cc5da  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc5df  mov     edx, 150h; void *
0x1800cc5e4  mov     rcx, [rbp+5Fh]; this
0x1800cc5e8  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cc5ef  mov     r9d, edi; char *
0x1800cc5f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cc5f7  mov     ebx, edi
0x1800cc5f9  jmp     loc_1800CC808
0x1800cc5fe  mov     rcx, rbx; hThread
0x1800cc601  call    cs:__imp_ResumeThread
0x1800cc608  nop     dword ptr [rax+rax+00h]
0x1800cc60d  cmp     eax, 0FFFFFFFFh
0x1800cc610  jnz     loc_1800CC6A9
0x1800cc616  call    cs:__imp_GetLastError
0x1800cc61d  nop     dword ptr [rax+rax+00h]
0x1800cc622  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc629  mov     edi, eax
0x1800cc62b  test    rcx, rcx
0x1800cc62e  jz      short loc_1800CC682
0x1800cc630  mov     ebx, 3
0x1800cc635  lea     r9, aFailedToResume_0; "Failed to resume DPX thread after setti"...
0x1800cc63c  mov     r8d, ebx
0x1800cc63f  xor     edx, edx
0x1800cc641  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cc646  test    edi, edi
0x1800cc648  jg      short loc_1800CC64E
0x1800cc64a  mov     eax, edi
0x1800cc64c  jmp     short loc_1800CC656
0x1800cc64e  movzx   eax, di
0x1800cc651  or      eax, 80070000h
0x1800cc656  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc65d  lea     r9, a0; ": {0}"
0x1800cc664  mov     [rbp+57h+ExitCode], eax
0x1800cc667  mov     r8d, ebx
0x1800cc66a  lea     rax, [rbp+57h+ExitCode]
0x1800cc66e  mov     dl, 1
0x1800cc670  mov     qword ptr [rbp+57h+var_B8], rax
0x1800cc674  lea     rax, [rbp+57h+var_B8]
0x1800cc678  mov     qword ptr [rsp+0F0h+dwCreationFlags], rax; unsigned int
0x1800cc67d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc682  test    edi, edi
0x1800cc684  jz      loc_1800CC806
0x1800cc68a  mov     edx, 156h; void *
0x1800cc68f  mov     rcx, [rbp+5Fh]; this
0x1800cc693  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cc69a  mov     r9d, edi; char *
0x1800cc69d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cc6a2  mov     ebx, eax
0x1800cc6a4  jmp     loc_1800CC808
0x1800cc6a9  mov     sil, 1
0x1800cc6ac  xor     r12d, r12d
0x1800cc6af  test    sil, sil
0x1800cc6b2  jz      loc_1800CC7CE
0x1800cc6b8  xor     edx, edx; Val
0x1800cc6ba  lea     rcx, [rbp+57h+var_A0]; void *
0x1800cc6be  lea     r8d, [rdx+58h]; Size
0x1800cc6c2  call    memset_0
0x1800cc6c7  mov     edx, 3E8h; dwMilliseconds
0x1800cc6cc  mov     rcx, rbx; hHandle
0x1800cc6cf  call    cs:__imp_WaitForSingleObject
0x1800cc6d6  nop     dword ptr [rax+rax+00h]
0x1800cc6db  test    eax, eax
0x1800cc6dd  jz      loc_1800CC77E
0x1800cc6e3  cmp     eax, 102h
0x1800cc6e8  jz      short loc_1800CC6EF
0x1800cc6ea  xor     sil, sil
0x1800cc6ed  jmp     short loc_1800CC6AF
0x1800cc6ef  mov     rax, [r14]
0x1800cc6f2  lea     rdx, [rbp+57h+var_A0]
0x1800cc6f6  mov     rcx, r14
0x1800cc6f9  mov     rax, [rax+58h]
0x1800cc6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc702  test    eax, eax
0x1800cc704  js      short loc_1800CC766
0x1800cc706  mov     rdx, [rbp+57h+var_68]
0x1800cc70a  test    rdx, rdx
0x1800cc70d  jz      short loc_1800CC6AF
0x1800cc70f  mov     rcx, [rbp+57h+var_70]
0x1800cc713  mov     rax, r13
0x1800cc716  imul    rax, rcx
0x1800cc71a  lea     r8, [rcx+rdx]
0x1800cc71e  xor     edx, edx
0x1800cc720  div     r8
0x1800cc723  mov     rdi, rax
0x1800cc726  test    r15, r15
0x1800cc729  jz      short loc_1800CC75E
0x1800cc72b  mov     rcx, [r15]
0x1800cc72e  mov     r9d, edi
0x1800cc731  sub     r9d, r12d
0x1800cc734  mov     edx, 30h ; '0'
0x1800cc739  mov     r8d, 0FFFFFFFEh
0x1800cc73f  mov     rax, [rcx+28h]
0x1800cc743  mov     rcx, r15
0x1800cc746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc74b  lea     r8, aUnableToUpdate; "Unable to update progress in during DPX"...
0x1800cc752  mov     edx, eax
0x1800cc754  mov     ecx, 1
0x1800cc759  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800cc75e  mov     r12d, edi
0x1800cc761  jmp     loc_1800CC6AF
0x1800cc766  lea     r8, aUnableToGetpro; "Unable to GetProgress on the DPX job."
0x1800cc76d  mov     edx, eax
0x1800cc76f  mov     ecx, 2
0x1800cc774  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800cc779  jmp     loc_1800CC6AF
0x1800cc77e  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x1800cc782  mov     [rbp+57h+ExitCode], 0
0x1800cc789  mov     rcx, rbx; hThread
0x1800cc78c  call    cs:__imp_GetExitCodeThread
0x1800cc793  nop     dword ptr [rax+rax+00h]
0x1800cc798  test    eax, eax
0x1800cc79a  jz      short loc_1800CC7B4
0x1800cc79c  mov     edi, [rbp+57h+ExitCode]
0x1800cc79f  xor     sil, sil
0x1800cc7a2  test    edi, edi
0x1800cc7a4  jns     loc_1800CC6AF
0x1800cc7aa  mov     edx, 164h
0x1800cc7af  jmp     loc_1800CC5E4
0x1800cc7b4  mov     rcx, [rbp+5Fh]; this
0x1800cc7b8  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cc7bf  mov     edx, 163h; void *
0x1800cc7c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cc7c9  jmp     loc_1800CC6A2
0x1800cc7ce  test    r15, r15
0x1800cc7d1  jz      short loc_1800CC806
0x1800cc7d3  mov     rax, [r15]
0x1800cc7d6  sub     r13d, r12d
0x1800cc7d9  mov     r9d, r13d
0x1800cc7dc  mov     edx, 30h ; '0'
0x1800cc7e1  mov     r8d, 0FFFFFFFEh
0x1800cc7e7  mov     rcx, r15
0x1800cc7ea  mov     rax, [rax+28h]
0x1800cc7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc7f3  lea     r8, aUnableToUpdate; "Unable to update progress in during DPX"...
0x1800cc7fa  mov     edx, eax
0x1800cc7fc  mov     ecx, 1
0x1800cc801  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800cc806  xor     ebx, ebx
0x1800cc808  lea     rcx, [rbp+57h+hThread]
0x1800cc80c  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800cc811  mov     eax, ebx
0x1800cc813  mov     rcx, [rbp+57h+var_40]
0x1800cc817  xor     rcx, rsp; StackCookie
0x1800cc81a  call    __security_check_cookie
0x1800cc81f  mov     rbx, [rsp+0F0h+arg_18]
0x1800cc827  add     rsp, 0C0h
0x1800cc82e  pop     r15
0x1800cc830  pop     r14
0x1800cc832  pop     r13
0x1800cc834  pop     r12
0x1800cc836  pop     rdi
0x1800cc837  pop     rsi
0x1800cc838  pop     rbp
0x1800cc839  retn
```
