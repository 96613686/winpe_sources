# CDlpTask::ExecuteActions(void)

- ea: `0x180235db0`
- end: `0x180236c93`
- name: `?ExecuteActions@CDlpTask@@AEAAJXZ`
- size: `3811`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1802349e0`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x180233cf0`
- `0x180235db0`
- `0x180245018`
- `0x18024be68`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180236bc4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180236bc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235e9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235e9f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023653a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180236acb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023653a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180236acb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235e12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235e66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235e12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235e66`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180235f6f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180235ff4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180236081`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180235f6f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180235ff4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180236081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180235f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023613e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802365ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023678d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180235f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023613e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802365ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180236655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023678d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802363ed`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1802363ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180236126`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180236126`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802361e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802361e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180235ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180235ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180236c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180236c46`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x18023637f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x18023637f`

## string_xrefs

- `0x180236ab3`: `Signalling actions thread to shut down.`
- `0x180236bad`: `Waiting for actions thread to exit.`
- `0x180236bf6`: `Actions thread has exited.`
- `0x180235f38`: `CDlpTask::ExecuteActions`
- `0x1802361a3`: `CDlpTask::ExecuteActions`
- `0x1802362c6`: `CDlpTask::ExecuteActions`
- `0x180236a54`: `CDlpTask::ExecuteActions`
- `0x18023623f`: `Action execution thread timeout period: [%d ms]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecuteActions(CDlpTask *this)
{
  HANDLE Thread; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  signed int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  char *v15; // rsi
  unsigned int v16; // edi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  DWORD LowPart; // eax
  DWORD v22; // eax
  DWORD v23; // r13d
  bool v24; // sf
  __int64 v25; // rax
  __int64 v26; // rcx
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  unsigned int v30; // r13d
  int v31; // eax
  char *v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  int dwCreationFlags; // [rsp+28h] [rbp-69h]
  DWORD dwCreationFlagsa[2]; // [rsp+28h] [rbp-69h]
  signed int lpThreadId; // [rsp+30h] [rbp-61h]
  LPDWORD lpThreadIda; // [rsp+30h] [rbp-61h]
  unsigned int v42; // [rsp+48h] [rbp-49h] BYREF
  unsigned int v43; // [rsp+4Ch] [rbp-45h] BYREF
  struct IDlpAction *v44; // [rsp+50h] [rbp-41h] BYREF
  int v45; // [rsp+58h] [rbp-39h] BYREF
  DWORD ExitCode; // [rsp+5Ch] [rbp-35h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-31h]
  union _ULARGE_INTEGER v48; // [rsp+68h] [rbp-29h]
  signed int v49; // [rsp+70h] [rbp-21h] BYREF
  unsigned int v50; // [rsp+74h] [rbp-1Dh]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-19h] BYREF
  HANDLE Handles[4]; // [rsp+80h] [rbp-11h] BYREF
  int v53; // [rsp+A0h] [rbp+Fh]
  __int64 v54; // [rsp+B0h] [rbp+1Fh]

  v54 = -2;
  v44 = 0;
  Thread = 0;
  v45 = 0;
  v42 = 0;
  ExitCode = 0;
  *(_OWORD *)Handles = 0;
  v49 = 0;
  SystemTimeAsFileTime = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 888);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v53 = 1;
  v42 = *((_DWORD *)this + 218);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection(v3);
  v53 = 0;
  v50 = *((_DWORD *)this + 95);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
  v53 = 1;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v53 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
    v53 = 0;
  }
  *((_QWORD *)this + 181) = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v48 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
  v4 = CULargeInteger::Set(
         *(CULargeInteger **)(*((_QWORD *)this + 148) + 8LL * (int)v42),
         (union _ULARGE_INTEGER)SystemTimeAsFileTime);
  if ( v4 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_188;
    v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v6 = 0;
    if ( !v5 )
      goto LABEL_9;
    lpThreadId = v4;
    dwCreationFlags = 3383;
    goto LABEL_7;
  }
  if ( !ResetEvent(*((HANDLE *)this + 29)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_188;
    v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v6 = 0;
    if ( v4 < 0 && v5 )
    {
      lpThreadId = v4;
      dwCreationFlags = 3387;
      goto LABEL_7;
    }
LABEL_9:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
    goto LABEL_188;
  }
  if ( !ResetEvent(*((HANDLE *)this + 30)) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_188;
    v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v6 = 0;
    if ( v4 >= 0 || !v5 )
      goto LABEL_9;
    lpThreadId = v4;
    dwCreationFlags = 3388;
    goto LABEL_7;
  }
  if ( !ResetEvent(*((HANDLE *)this + 31)) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_188;
    v5 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v6 = 0;
    if ( v4 >= 0 || !v5 )
      goto LABEL_9;
    lpThreadId = v4;
    dwCreationFlags = 3389;
LABEL_7:
    v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v5,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpTask::ExecuteActions",
           dwCreationFlags,
           lpThreadId);
    v6 = (unsigned int)v7;
    if ( v7 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
    goto LABEL_9;
  }
  Thread = CreateThread(0, 0, CDlpTask::ExecuteActionsThreadProc, this, 0, 0);
  if ( !Thread )
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
    {
      v12 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v13 = 0;
      if ( v4 < 0 )
      {
        if ( v12 )
        {
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3399;
          v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v12,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpTask::ExecuteActions",
                  *(_QWORD *)dwCreationFlagsa,
                  lpThreadIda);
          v13 = (unsigned int)v14;
          if ( v14 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
        }
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
    }
    Thread = 0;
    goto LABEL_188;
  }
  Handles[0] = *((HANDLE *)this + 30);
  Handles[1] = Thread;
  *((_DWORD *)this + 361) = GetTickCount();
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  v15 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v16 = *((_DWORD *)this + 360);
    v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v17, 2, L"Action execution thread timeout period: [%d ms]", v16);
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  v4 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(this, v42, &v44);
  if ( v4 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
      goto LABEL_172;
    v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
    v19 = 0;
    if ( !v18 )
      goto LABEL_59;
    LODWORD(lpThreadIda) = v4;
    dwCreationFlagsa[0] = 3418;
    goto LABEL_57;
  }
  v43 = 1;
  v4 = CDlpTask::ProgressHandlerAction(this, v44, v42, &v43);
  if ( v4 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
      goto LABEL_172;
    v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
    v19 = 0;
    if ( !v18 )
    {
LABEL_59:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
      goto LABEL_172;
    }
    LODWORD(lpThreadIda) = v4;
    dwCreationFlagsa[0] = 3420;
LABEL_57:
    v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v18,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::ExecuteActions",
            *(_QWORD *)dwCreationFlagsa,
            lpThreadIda);
    v19 = (unsigned int)v20;
    if ( v20 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
    goto LABEL_59;
  }
  LowPart = 1;
  v47 = v42;
LABEL_65:
  for ( v48.LowPart = LowPart; ; LowPart = v48.LowPart )
  {
    if ( !LowPart )
    {
      if ( !*((_DWORD *)this + 353) )
      {
        v30 = v50;
        while ( v42 < v30 )
        {
          if ( v44 )
          {
            (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v44 + 16LL))(v44);
            v44 = 0;
          }
          v4 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(
                 this,
                 v42,
                 &v44);
          if ( v4 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
              goto LABEL_172;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
            v26 = 0;
            if ( v25 )
            {
              LODWORD(lpThreadIda) = v4;
              dwCreationFlagsa[0] = 3509;
              goto LABEL_169;
            }
            goto LABEL_171;
          }
          v43 |= 2u;
          v4 = CDlpTask::ProgressHandlerAction(this, v44, v42, &v43);
          if ( v4 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
              goto LABEL_172;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
            v26 = 0;
            if ( v25 )
            {
              LODWORD(lpThreadIda) = v4;
              dwCreationFlagsa[0] = 3511;
              goto LABEL_169;
            }
            goto LABEL_171;
          }
          v4 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v44 + 24LL))(v44, &v45);
          if ( v4 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
              goto LABEL_172;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
            v26 = 0;
            if ( v25 )
            {
              LODWORD(lpThreadIda) = v4;
              dwCreationFlagsa[0] = 3514;
              goto LABEL_169;
            }
            goto LABEL_171;
          }
          if ( ((v45 - 4) & 0xFFFFFFFD) != 0 )
          {
            v4 = -2147019873;
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
              goto LABEL_172;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
            v26 = 0;
            if ( v25 )
            {
              LODWORD(lpThreadIda) = -2147019873;
              dwCreationFlagsa[0] = 3516;
              goto LABEL_169;
            }
            goto LABEL_171;
          }
          if ( v42 + 1 < v42 )
          {
            v4 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v42;
            v4 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
          if ( v4 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
              goto LABEL_172;
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
            v26 = 0;
            if ( v25 )
            {
              LODWORD(lpThreadIda) = v4;
              dwCreationFlagsa[0] = 3518;
              goto LABEL_169;
            }
            goto LABEL_171;
          }
        }
      }
      goto LABEL_172;
    }
    v22 = WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 360));
    v23 = v22;
    if ( v22 )
    {
      if ( v22 == 1 )
      {
        if ( GetExitCodeThread(Thread, &ExitCode) )
        {
          v4 = ExitCode;
          v24 = (ExitCode & 0x80000000) != 0;
          if ( (int)ExitCode > 0 )
          {
            v4 = (unsigned __int16)ExitCode | 0x80070000;
            v24 = 1;
          }
          if ( !v24 )
          {
            LowPart = 0;
            goto LABEL_65;
          }
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
            goto LABEL_172;
          v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
          v26 = 0;
          if ( !v25 )
            goto LABEL_171;
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3487;
        }
        else
        {
          v28 = GetLastError();
          v4 = v28;
          if ( v28 )
          {
            if ( v28 > 0 )
              v4 = (unsigned __int16)v28 | 0x80070000;
          }
          else
          {
            v4 = -2147467259;
          }
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
            goto LABEL_172;
          v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
          v26 = 0;
          if ( v4 >= 0 || !v25 )
            goto LABEL_171;
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3486;
        }
        goto LABEL_169;
      }
      if ( v22 != 258 )
      {
        if ( v22 == -1 )
        {
          v27 = GetLastError();
          v4 = v27;
          if ( v27 > 0 )
            v4 = (unsigned __int16)v27 | 0x80070000;
          if ( v4 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
            goto LABEL_172;
          v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
          v26 = 0;
          if ( !v25 )
            goto LABEL_171;
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3492;
        }
        else
        {
          v4 = -2147418113;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
            goto LABEL_172;
          v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
          v26 = 0;
          if ( !v25 )
            goto LABEL_171;
          LODWORD(lpThreadIda) = -2147418113;
          dwCreationFlagsa[0] = 3497;
        }
        goto LABEL_169;
      }
    }
    if ( v44 )
    {
      (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    v4 = (*(__int64 (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
           this,
           &v44,
           &v42);
    if ( v4 == -2147023728 )
    {
      v4 = 0;
    }
    else if ( v4 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
        goto LABEL_172;
      v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
      v26 = 0;
      if ( v25 )
      {
        LODWORD(lpThreadIda) = v4;
        dwCreationFlagsa[0] = 3439;
        goto LABEL_169;
      }
      goto LABEL_171;
    }
    if ( v44 )
    {
      v4 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v44 + 24LL))(v44, &v45);
      if ( v4 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
          goto LABEL_172;
        v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
        v26 = 0;
        if ( v25 )
        {
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3442;
          goto LABEL_169;
        }
        goto LABEL_171;
      }
      if ( v45 )
      {
        if ( v45 == 6 )
        {
          v43 |= 2u;
          v4 = CDlpTask::ProgressHandlerAction(this, v44, v42, &v43);
          if ( v4 >= 0 )
            goto LABEL_96;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
            goto LABEL_172;
          v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
          v26 = 0;
          if ( !v25 )
            goto LABEL_171;
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3456;
          goto LABEL_169;
        }
        if ( v45 == -1073741824 )
          goto LABEL_96;
      }
      else if ( v47 != v42 )
      {
        v43 = 1;
        v4 = CDlpTask::ProgressHandlerAction(this, v44, v42, &v43);
        if ( v4 >= 0 )
        {
          v47 = v42;
          goto LABEL_96;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
          goto LABEL_172;
        v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
        v26 = 0;
        if ( !v25 )
          goto LABEL_171;
        LODWORD(lpThreadIda) = v4;
        dwCreationFlagsa[0] = 3448;
LABEL_169:
        v31 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v25,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTask::ExecuteActions",
                *(_QWORD *)dwCreationFlagsa,
                lpThreadIda);
        v26 = (unsigned int)v31;
        if ( v31 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v31);
        goto LABEL_171;
      }
      if ( !v23 || (*((_BYTE *)this + 1420) & 1) != 0 )
        v43 |= 4u;
      v4 = CDlpTask::ProgressHandlerAction(this, v44, v42, &v43);
      if ( v4 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
          goto LABEL_172;
        v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
        v26 = 0;
        if ( v25 )
        {
          LODWORD(lpThreadIda) = v4;
          dwCreationFlagsa[0] = 3471;
          goto LABEL_169;
        }
LABEL_171:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
        goto LABEL_172;
      }
    }
LABEL_96:
    if ( !v23 && !SetEvent(*((HANDLE *)this + 31)) )
      break;
  }
  v29 = GetLastError();
  v4 = v29;
  if ( v29 )
  {
    if ( v29 > 0 )
      v4 = (unsigned __int16)v29 | 0x80070000;
  }
  else
  {
    v4 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176) )
  {
    v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 176);
    v26 = 0;
    if ( v4 < 0 && v25 )
    {
      LODWORD(lpThreadIda) = v4;
      dwCreationFlagsa[0] = 3480;
      goto LABEL_169;
    }
    goto LABEL_171;
  }
LABEL_172:
  v32 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"Signalling actions thread to shut down.");
  }
  SetEvent(*((HANDLE *)this + 29));
  if ( v4 < 0 )
  {
    if ( v44 )
    {
      (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    if ( (*(int (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
           this,
           &v44,
           &v42) >= 0
      && v44
      && (*(int (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v44 + 24LL))(v44, &v45) >= 0
      && v45 == 3 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176) )
      {
        v34 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176);
        CDlpLogT<CEmptyType>::DlpLogFormat(v34, 2, L"Cancelling running action...");
      }
      (*(void (__fastcall **)(struct IDlpAction *, CDlpTask *))(*(_QWORD *)v44 + 40LL))(v44, this);
    }
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176) )
  {
    v35 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v35, 2, L"Waiting for actions thread to exit.");
  }
  WaitForSingleObject(Thread, 0xFFFFFFFF);
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176) )
  {
    v36 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v36, 2, L"Actions thread has exited.");
  }
LABEL_188:
  v49 = v4;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, signed int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    8196,
    0,
    &v49,
    0,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( Thread )
    CloseHandle(Thread);
  if ( v44 )
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v44 + 16LL))(v44);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180235db0  mov     rax, rsp
0x180235db3  push    rbp
0x180235db4  push    rdi
0x180235db5  push    r13
0x180235db7  push    r14
0x180235db9  push    r15
0x180235dbb  lea     rbp, [rax-5Fh]
0x180235dbf  sub     rsp, 0C0h
0x180235dc6  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFEh
0x180235dce  mov     [rax+10h], rbx
0x180235dd2  mov     [rax+18h], rsi
0x180235dd6  mov     rax, cs:__security_cookie
0x180235ddd  xor     rax, rsp
0x180235de0  mov     [rbp+57h+var_30], rax
0x180235de4  mov     r14, rcx
0x180235de7  mov     [rbp+57h+var_98], 0
0x180235def  xor     ebx, ebx
0x180235df1  mov     [rbp+57h+var_90], ebx
0x180235df4  mov     [rbp+57h+var_A0], ebx
0x180235df7  mov     [rbp+57h+ExitCode], ebx
0x180235dfa  xorps   xmm0, xmm0
0x180235dfd  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x180235e01  mov     [rbp+57h+var_78], ebx
0x180235e04  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180235e08  lea     rdi, [rcx+378h]
0x180235e0f  mov     rcx, rdi; lpCriticalSection
0x180235e12  call    cs:__imp_EnterCriticalSection
0x180235e19  nop     dword ptr [rax+rax+00h]
0x180235e1e  lea     r15d, [rbx+1]
0x180235e22  mov     [rbp+57h+var_48], r15d
0x180235e26  mov     eax, [r14+368h]
0x180235e2d  mov     [rbp+57h+var_A0], eax
0x180235e30  xor     ecx, ecx
0x180235e32  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180235e37  nop
0x180235e38  mov     eax, [rbp+57h+var_48]
0x180235e3b  test    eax, eax
0x180235e3d  jz      short loc_180235E51
0x180235e3f  mov     rcx, rdi; lpCriticalSection
0x180235e42  call    cs:__imp_LeaveCriticalSection
0x180235e49  nop     dword ptr [rax+rax+00h]
0x180235e4e  mov     [rbp+57h+var_48], ebx
0x180235e51  mov     r13d, [r14+17Ch]
0x180235e58  mov     [rbp+57h+var_74], r13d
0x180235e5c  lea     rdi, [r14+3C8h]
0x180235e63  mov     rcx, rdi; lpCriticalSection
0x180235e66  call    cs:__imp_EnterCriticalSection
0x180235e6d  nop     dword ptr [rax+rax+00h]
0x180235e72  mov     [rbp+57h+var_48], r15d
0x180235e76  xor     eax, eax
0x180235e78  mov     [r14+3A8h], rax
0x180235e7f  mov     [r14+3B0h], rax
0x180235e86  mov     [r14+3B8h], rax
0x180235e8d  xor     ecx, ecx
0x180235e8f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180235e94  nop
0x180235e95  mov     eax, [rbp+57h+var_48]
0x180235e98  test    eax, eax
0x180235e9a  jz      short loc_180235EB2
0x180235e9c  mov     rcx, rdi; lpCriticalSection
0x180235e9f  call    cs:__imp_LeaveCriticalSection
0x180235ea6  nop     dword ptr [rax+rax+00h]
0x180235eab  mov     [rbp+57h+var_48], 0
0x180235eb2  mov     qword ptr [r14+5A8h], 0
0x180235ebd  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180235ec1  call    cs:__imp_GetSystemTimeAsFileTime
0x180235ec8  nop     dword ptr [rax+rax+00h]
0x180235ecd  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x180235ed0  mov     dword ptr [rbp+57h+var_80+4], eax
0x180235ed3  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180235ed6  mov     dword ptr [rbp+57h+var_80], eax
0x180235ed9  mov     rax, [r14+4A0h]
0x180235ee0  movsxd  rcx, [rbp+57h+var_A0]
0x180235ee4  mov     rdx, qword ptr [rbp+57h+var_80]; union _ULARGE_INTEGER
0x180235ee8  mov     rcx, [rax+rcx*8]; this
0x180235eec  call    ?Set@CULargeInteger@@QEAAJT_ULARGE_INTEGER@@@Z; CULargeInteger::Set(_ULARGE_INTEGER)
0x180235ef1  mov     edi, eax
0x180235ef3  test    eax, eax
0x180235ef5  jns     short loc_180235F68
0x180235ef7  lea     rsi, [r14+0B0h]
0x180235efe  mov     rdx, [rsi]
0x180235f01  mov     rcx, rsi
0x180235f04  mov     rax, [rdx+10h]
0x180235f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235f0d  test    rax, rax
0x180235f10  jz      loc_180236C07
0x180235f16  mov     rax, [rsi]
0x180235f19  mov     rcx, rsi
0x180235f1c  mov     rax, [rax+10h]
0x180235f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235f25  xor     ecx, ecx
0x180235f27  test    rax, rax
0x180235f2a  jz      short loc_180235F5E
0x180235f2c  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180235f30  mov     [rsp+0E0h+dwCreationFlags], 0D37h
0x180235f38  lea     r9, aCdlptaskExecut_0; "CDlpTask::ExecuteActions"
0x180235f3f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180235f46  mov     edx, 4
0x180235f4b  mov     rcx, rax
0x180235f4e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180235f53  test    eax, eax
0x180235f55  mov     ecx, eax
0x180235f57  jns     short loc_180235F5E
0x180235f59  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180235f5e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180235f63  jmp     loc_180236C07
0x180235f68  mov     rcx, [r14+0E8h]; hEvent
0x180235f6f  call    cs:__imp_ResetEvent
0x180235f76  nop     dword ptr [rax+rax+00h]
0x180235f7b  test    eax, eax
0x180235f7d  jnz     short loc_180235FED
0x180235f7f  call    cs:__imp_GetLastError
0x180235f86  nop     dword ptr [rax+rax+00h]
0x180235f8b  mov     edi, eax
0x180235f8d  test    eax, eax
0x180235f8f  jnz     short loc_180235F98
0x180235f91  mov     edi, 80004005h
0x180235f96  jmp     short loc_180235FA3
0x180235f98  jle     short loc_180235FA3
0x180235f9a  movzx   edi, ax
0x180235f9d  or      edi, 80070000h
0x180235fa3  lea     rsi, [r14+0B0h]
0x180235faa  mov     rax, [rsi]
0x180235fad  mov     rcx, rsi
0x180235fb0  mov     rax, [rax+10h]
0x180235fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235fb9  test    rax, rax
0x180235fbc  jz      loc_180236C07
0x180235fc2  mov     rax, [rsi]
0x180235fc5  mov     rcx, rsi
0x180235fc8  mov     rax, [rax+10h]
0x180235fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235fd1  xor     ecx, ecx
0x180235fd3  test    edi, edi
0x180235fd5  jns     short loc_180235F5E
0x180235fd7  test    rax, rax
0x180235fda  jz      short loc_180235F5E
0x180235fdc  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180235fe0  mov     [rsp+0E0h+dwCreationFlags], 0D3Bh
0x180235fe8  jmp     loc_180235F38
0x180235fed  mov     rcx, [r14+0F0h]; hEvent
0x180235ff4  call    cs:__imp_ResetEvent
0x180235ffb  nop     dword ptr [rax+rax+00h]
0x180236000  test    eax, eax
0x180236002  jnz     short loc_18023607A
0x180236004  call    cs:__imp_GetLastError
0x18023600b  nop     dword ptr [rax+rax+00h]
0x180236010  mov     edi, eax
0x180236012  test    eax, eax
0x180236014  jnz     short loc_18023601D
0x180236016  mov     edi, 80004005h
0x18023601b  jmp     short loc_180236028
0x18023601d  jle     short loc_180236028
0x18023601f  movzx   edi, ax
0x180236022  or      edi, 80070000h
0x180236028  lea     rsi, [r14+0B0h]
0x18023602f  mov     rax, [rsi]
0x180236032  mov     rcx, rsi
0x180236035  mov     rax, [rax+10h]
0x180236039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023603e  test    rax, rax
0x180236041  jz      loc_180236C07
0x180236047  mov     rax, [rsi]
0x18023604a  mov     rcx, rsi
0x18023604d  mov     rax, [rax+10h]
0x180236051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180236056  xor     ecx, ecx
0x180236058  test    edi, edi
0x18023605a  jns     loc_180235F5E
0x180236060  test    rax, rax
0x180236063  jz      loc_180235F5E
0x180236069  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x18023606d  mov     [rsp+0E0h+dwCreationFlags], 0D3Ch
0x180236075  jmp     loc_180235F38
0x18023607a  mov     rcx, [r14+0F8h]; hEvent
0x180236081  call    cs:__imp_ResetEvent
0x180236088  nop     dword ptr [rax+rax+00h]
0x18023608d  test    eax, eax
0x18023608f  jnz     short loc_180236107
0x180236091  call    cs:__imp_GetLastError
0x180236098  nop     dword ptr [rax+rax+00h]
0x18023609d  mov     edi, eax
0x18023609f  test    eax, eax
0x1802360a1  jnz     short loc_1802360AA
0x1802360a3  mov     edi, 80004005h
0x1802360a8  jmp     short loc_1802360B5
0x1802360aa  jle     short loc_1802360B5
0x1802360ac  movzx   edi, ax
0x1802360af  or      edi, 80070000h
0x1802360b5  lea     rsi, [r14+0B0h]
0x1802360bc  mov     rax, [rsi]
0x1802360bf  mov     rcx, rsi
0x1802360c2  mov     rax, [rax+10h]
0x1802360c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802360cb  test    rax, rax
0x1802360ce  jz      loc_180236C07
0x1802360d4  mov     rax, [rsi]
0x1802360d7  mov     rcx, rsi
0x1802360da  mov     rax, [rax+10h]
0x1802360de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802360e3  xor     ecx, ecx
0x1802360e5  test    edi, edi
0x1802360e7  jns     loc_180235F5E
0x1802360ed  test    rax, rax
0x1802360f0  jz      loc_180235F5E
0x1802360f6  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x1802360fa  mov     [rsp+0E0h+dwCreationFlags], 0D3Dh
0x180236102  jmp     loc_180235F38
0x180236107  mov     [rsp+0E0h+lpThreadId], 0; lpThreadId
0x180236110  mov     [rsp+0E0h+dwCreationFlags], 0; dwCreationFlags
0x180236118  mov     r9, r14; lpParameter
0x18023611b  lea     r8, ?ExecuteActionsThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x180236122  xor     edx, edx; dwStackSize
0x180236124  xor     ecx, ecx; lpThreadAttributes
0x180236126  call    cs:__imp_CreateThread
0x18023612d  nop     dword ptr [rax+rax+00h]
0x180236132  mov     rbx, rax
0x180236135  test    rax, rax
0x180236138  jnz     loc_1802361D3
0x18023613e  call    cs:__imp_GetLastError
0x180236145  nop     dword ptr [rax+rax+00h]
0x18023614a  mov     edi, eax
0x18023614c  test    eax, eax
0x18023614e  jnz     short loc_180236157
0x180236150  mov     edi, 80004005h
0x180236155  jmp     short loc_180236162
0x180236157  jle     short loc_180236162
0x180236159  movzx   edi, ax
0x18023615c  or      edi, 80070000h
0x180236162  lea     rbx, [r14+0B0h]
0x180236169  mov     rax, [rbx]
0x18023616c  mov     rcx, rbx
0x18023616f  mov     rax, [rax+10h]
0x180236173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180236178  test    rax, rax
0x18023617b  jz      short loc_1802361CC
0x18023617d  mov     rax, [rbx]
0x180236180  mov     rcx, rbx
0x180236183  mov     rax, [rax+10h]
0x180236187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023618c  xor     ecx, ecx
0x18023618e  test    edi, edi
0x180236190  jns     short loc_1802361C7
0x180236192  test    rax, rax
0x180236195  jz      short loc_1802361C7
0x180236197  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x18023619b  mov     [rsp+0E0h+dwCreationFlags], 0D47h
0x1802361a3  lea     r9, aCdlptaskExecut_0; "CDlpTask::ExecuteActions"
0x1802361aa  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1802361b1  lea     edx, [rcx+4]
0x1802361b4  mov     rcx, rax
0x1802361b7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1802361bc  mov     ecx, eax
0x1802361be  test    eax, eax
0x1802361c0  jns     short loc_1802361C7
0x1802361c2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1802361c7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802361cc  xor     ebx, ebx
0x1802361ce  jmp     loc_180236C07
0x1802361d3  mov     rax, [r14+0F0h]
0x1802361da  mov     [rbp+57h+Handles], rax
0x1802361de  mov     [rbp+57h+Handles+8], rbx
0x1802361e2  call    cs:__imp_GetTickCount
0x1802361e9  nop     dword ptr [rax+rax+00h]
0x1802361ee  mov     [r14+5A4h], eax
0x1802361f5  mov     qword ptr [r14+5B0h], 0
0x180236200  mov     qword ptr [r14+5B8h], 0
0x18023620b  lea     rsi, [r14+0B0h]
0x180236212  mov     rax, [rsi]
0x180236215  mov     rcx, rsi
0x180236218  mov     rax, [rax+10h]
0x18023621c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180236221  test    rax, rax
0x180236224  jz      short loc_180236253
0x180236226  mov     edi, [r14+5A0h]
0x18023622d  mov     rax, [rsi]
0x180236230  mov     rcx, rsi
0x180236233  mov     rax, [rax+10h]
0x180236237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023623c  mov     r9d, edi
0x18023623f  lea     r8, aActionExecutio; "Action execution thread timeout period:"...
0x180236246  mov     edx, 2
0x18023624b  mov     rcx, rax
0x18023624e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180236253  mov     rcx, [rbp+57h+var_98]
0x180236257  test    rcx, rcx
0x18023625a  jz      short loc_180236270
0x18023625c  mov     rax, [rcx]
0x18023625f  mov     rax, [rax+10h]
0x180236263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180236268  mov     [rbp+57h+var_98], 0
0x180236270  mov     rax, [r14]
0x180236273  lea     r8, [rbp+57h+var_98]
0x180236277  mov     edx, [rbp+57h+var_A0]
0x18023627a  mov     rcx, r14
0x18023627d  mov     rax, [rax+78h]
0x180236281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180236286  mov     edi, eax
0x180236288  test    eax, eax
0x18023628a  jns     short loc_1802362F6
  ... truncated ...
```
