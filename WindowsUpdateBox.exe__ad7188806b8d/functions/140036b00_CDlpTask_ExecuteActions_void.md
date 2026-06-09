# CDlpTask::ExecuteActions(void)

- ea: `0x140036b00`
- end: `0x140037a6b`
- name: `?ExecuteActions@CDlpTask@@AEAAJXZ`
- size: `3947`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1400356d0`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x140036b00`
- `0x140038e64`
- `0x1400452c8`
- `0x14004c2b0`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140037a32`
- `KERNEL32!CloseHandle` at `0x140037a32`
- `KERNEL32!ResetEvent` at `0x140036cd7`
- `KERNEL32!ResetEvent` at `0x140036d6c`
- `KERNEL32!ResetEvent` at `0x140036e01`
- `KERNEL32!ResetEvent` at `0x140036cd7`
- `KERNEL32!ResetEvent` at `0x140036d6c`
- `KERNEL32!ResetEvent` at `0x140036e01`
- `KERNEL32!GetExitCodeThread` at `0x140037199`
- `KERNEL32!GetExitCodeThread` at `0x140037199`
- `KERNEL32!CreateThread` at `0x140036ea0`
- `KERNEL32!CreateThread` at `0x140036ea0`
- `KERNEL32!SetEvent` at `0x1400372f3`
- `KERNEL32!SetEvent` at `0x1400378b4`
- `KERNEL32!SetEvent` at `0x1400372f3`
- `KERNEL32!SetEvent` at `0x1400378b4`
- `KERNEL32!GetTickCount` at `0x140036f57`
- `KERNEL32!GetTickCount` at `0x140036f57`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140036c41`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140036c41`
- `KERNEL32!GetLastError` at `0x140036ce7`
- `KERNEL32!GetLastError` at `0x140036d7c`
- `KERNEL32!GetLastError` at `0x140036e11`
- `KERNEL32!GetLastError` at `0x140036eb7`
- `KERNEL32!GetLastError` at `0x140037303`
- `KERNEL32!GetLastError` at `0x140037389`
- `KERNEL32!GetLastError` at `0x140037434`
- `KERNEL32!GetLastError` at `0x140036ce7`
- `KERNEL32!GetLastError` at `0x140036d7c`
- `KERNEL32!GetLastError` at `0x140036e11`
- `KERNEL32!GetLastError` at `0x140036eb7`
- `KERNEL32!GetLastError` at `0x140037303`
- `KERNEL32!GetLastError` at `0x140037389`
- `KERNEL32!GetLastError` at `0x140037434`
- `KERNEL32!WaitForSingleObject` at `0x1400379b1`
- `KERNEL32!WaitForSingleObject` at `0x1400379b1`
- `KERNEL32!LeaveCriticalSection` at `0x140036c26`
- `KERNEL32!LeaveCriticalSection` at `0x140036c26`
- `KERNEL32!WaitForMultipleObjects` at `0x140037121`
- `KERNEL32!WaitForMultipleObjects` at `0x140037121`
- `KERNEL32!EnterCriticalSection` at `0x140036be9`
- `KERNEL32!EnterCriticalSection` at `0x140036be9`

## string_xrefs

- `0x140036ba1`: `CDlpTask::ExecuteActions`
- `0x140037030`: `CDlpTask::ExecuteActions`
- `0x1400370be`: `CDlpTask::ExecuteActions`
- `0x14003782c`: `CDlpTask::ExecuteActions`
- `0x140036fac`: `Action execution thread timeout period: [%d ms]`
- `0x140037895`: `Signalling actions thread to shut down.`
- `0x140037993`: `Waiting for actions thread to exit.`
- `0x1400379e9`: `Actions thread has exited.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecuteActions(CDlpTask *this)
{
  void *v2; // rbx
  signed int v3; // edi
  __int64 v4; // rax
  unsigned int v5; // esi
  int v6; // eax
  __int64 v7; // rax
  void *v8; // rcx
  signed int LastError; // eax
  void *v10; // rcx
  signed int v11; // eax
  void *v12; // rcx
  signed int v13; // eax
  HANDLE Thread; // rbx
  signed int v15; // eax
  int v16; // r13d
  void *v17; // rax
  char *v18; // rsi
  unsigned int v19; // edi
  __int64 v20; // rax
  int v21; // r12d
  __int64 v22; // rax
  unsigned int v23; // edi
  int v24; // eax
  void *v25; // r14
  signed int v26; // edi
  __int64 v27; // rax
  unsigned int v28; // esi
  int v29; // eax
  DWORD v30; // eax
  DWORD v31; // r13d
  bool v32; // sf
  __int64 v33; // rax
  unsigned int v34; // esi
  void *v35; // rcx
  signed int v36; // eax
  signed int v37; // eax
  signed int v38; // eax
  unsigned int v39; // r12d
  int v40; // eax
  char *v41; // rsi
  __int64 v42; // rax
  void *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-69h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-61h]
  struct IDlpAction *v50; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-41h]
  int v52; // [rsp+4Ch] [rbp-3Dh]
  signed int v53; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v54; // [rsp+54h] [rbp-35h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-31h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v57; // [rsp+70h] [rbp-19h]
  int v58; // [rsp+88h] [rbp-1h]
  unsigned int v59; // [rsp+F0h] [rbp+67h] BYREF
  union _ULARGE_INTEGER v60; // [rsp+F8h] [rbp+6Fh] BYREF
  int v61; // [rsp+100h] [rbp+77h] BYREF
  DWORD ExitCode; // [rsp+108h] [rbp+7Fh] BYREF

  v57 = -2;
  v50 = 0;
  v2 = 0;
  v61 = 0;
  v59 = 0;
  ExitCode = 0;
  *(_OWORD *)Handles = 0;
  v53 = 0;
  SystemTimeAsFileTime = 0;
  v3 = CDlpState::Get((CDlpTask *)((char *)this + 872), (enum WINDLP_STATE *)&v59);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3371;
    goto LABEL_5;
  }
  v54 = *((_DWORD *)this + 95);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
  v58 = 1;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v58 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 968));
    v58 = 0;
  }
  *((_QWORD *)this + 181) = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v60 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
  v7 = *((_QWORD *)this + 148);
  if ( !v7 )
    v7 = 0;
  v3 = CULargeInteger::Set(*(CULargeInteger **)(v7 + 8LL * (int)v59), v60);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v4 )
    {
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3383;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
    goto LABEL_206;
  }
  v8 = (void *)*((_QWORD *)this + 29);
  if ( !v8 )
    v8 = 0;
  if ( !ResetEvent(v8) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3387;
    goto LABEL_5;
  }
  v10 = (void *)*((_QWORD *)this + 30);
  if ( !v10 )
    v10 = 0;
  if ( !ResetEvent(v10) )
  {
    v11 = GetLastError();
    v3 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v3 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3388;
    goto LABEL_5;
  }
  v12 = (void *)*((_QWORD *)this + 31);
  if ( !v12 )
    v12 = 0;
  if ( !ResetEvent(v12) )
  {
    v13 = GetLastError();
    v3 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3389;
    goto LABEL_5;
  }
  Thread = CreateThread(0, 0, CDlpTask::ExecuteActionsThreadProc, this, 0, 0);
  if ( !Thread )
  {
    v2 = 0;
    v15 = GetLastError();
    v3 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v3 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_206;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3399;
LABEL_5:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpTask::ExecuteActions",
           *(_QWORD *)dwCreationFlags,
           lpThreadId);
    v5 = v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_7;
  }
  v16 = 1;
  v52 = 1;
  v17 = (void *)*((_QWORD *)this + 30);
  if ( !v17 )
    v17 = 0;
  Handles[0] = v17;
  Handles[1] = Thread;
  *((_DWORD *)this + 361) = GetTickCount();
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  v18 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v19 = *((_DWORD *)this + 360);
    v20 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v20, 2, L"Action execution thread timeout period: [%d ms]", v19);
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  v21 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(this, v59, &v50);
  if ( v21 < 0 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
    {
      v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
      v23 = 0;
      if ( v22 )
      {
        LODWORD(lpThreadId) = v21;
        dwCreationFlags[0] = 3418;
        v24 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v22,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTask::ExecuteActions",
                *(_QWORD *)dwCreationFlags,
                lpThreadId);
        v23 = v24;
        if ( v24 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
    }
LABEL_70:
    v25 = Thread;
    goto LABEL_188;
  }
  v60.LowPart = 1;
  v26 = CDlpTask::ProgressHandlerAction(this, v50, v59, (unsigned int *)&v60);
  if ( v26 < 0 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
    {
      v27 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
      v28 = 0;
      if ( v27 )
      {
        LODWORD(lpThreadId) = v26;
        dwCreationFlags[0] = 3420;
        v29 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v27,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTask::ExecuteActions",
                *(_QWORD *)dwCreationFlags,
                lpThreadId);
        v28 = v29;
        if ( v29 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v29);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v28);
    }
    v21 = v26;
    goto LABEL_70;
  }
  v51 = v59;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v16 )
      {
        if ( !*((_DWORD *)this + 353) )
        {
          v39 = v54;
          while ( v59 < v39 )
          {
            if ( v50 )
            {
              (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v50 + 16LL))(v50);
              v50 = 0;
            }
            v26 = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, struct IDlpAction **))(*(_QWORD *)this + 120LL))(
                    this,
                    v59,
                    &v50);
            if ( v26 < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
                goto LABEL_187;
              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
              v34 = 0;
              if ( v33 )
              {
                LODWORD(lpThreadId) = v26;
                dwCreationFlags[0] = 3509;
                goto LABEL_184;
              }
              goto LABEL_186;
            }
            v60.LowPart |= 2u;
            v26 = CDlpTask::ProgressHandlerAction(this, v50, v59, (unsigned int *)&v60);
            if ( v26 < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
                goto LABEL_187;
              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
              v34 = 0;
              if ( v33 )
              {
                LODWORD(lpThreadId) = v26;
                dwCreationFlags[0] = 3511;
                goto LABEL_184;
              }
              goto LABEL_186;
            }
            v26 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v50 + 24LL))(v50, &v61);
            if ( v26 < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
                goto LABEL_187;
              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
              v34 = 0;
              if ( v33 )
              {
                LODWORD(lpThreadId) = v26;
                dwCreationFlags[0] = 3514;
                goto LABEL_184;
              }
              goto LABEL_186;
            }
            if ( ((v61 - 4) & 0xFFFFFFFD) != 0 )
            {
              v26 = -2147019873;
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
                goto LABEL_187;
              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
              v34 = 0;
              if ( v33 )
              {
                LODWORD(lpThreadId) = -2147019873;
                dwCreationFlags[0] = 3516;
                goto LABEL_184;
              }
              goto LABEL_186;
            }
            if ( v59 + 1 < v59 )
            {
              v26 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
            }
            else
            {
              ++v59;
              v26 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v26);
            if ( v26 < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
                goto LABEL_187;
              v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
              v34 = 0;
              if ( v33 )
              {
                LODWORD(lpThreadId) = v26;
                dwCreationFlags[0] = 3518;
                goto LABEL_184;
              }
              goto LABEL_186;
            }
          }
        }
        goto LABEL_187;
      }
      v30 = WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 360));
      v31 = v30;
      if ( !v30 )
        goto LABEL_83;
      if ( v30 == 1 )
        break;
      if ( v30 != 258 )
      {
        if ( v30 == -1 )
        {
          v37 = GetLastError();
          v26 = v37;
          if ( v37 > 0 )
            v26 = (unsigned __int16)v37 | 0x80070000;
          if ( v26 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
            goto LABEL_187;
          v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
          v34 = 0;
          if ( !v33 )
            goto LABEL_186;
          LODWORD(lpThreadId) = v26;
          dwCreationFlags[0] = 3492;
        }
        else
        {
          v26 = -2147418113;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
            goto LABEL_187;
          v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
          v34 = 0;
          if ( !v33 )
            goto LABEL_186;
          LODWORD(lpThreadId) = -2147418113;
          dwCreationFlags[0] = 3497;
        }
LABEL_184:
        v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v33,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTask::ExecuteActions",
                *(_QWORD *)dwCreationFlags,
                lpThreadId);
        v34 = v40;
        if ( v40 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
        goto LABEL_186;
      }
LABEL_83:
      if ( v50 )
      {
        (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v50 + 16LL))(v50);
        v50 = 0;
      }
      v26 = (*(__int64 (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
              this,
              &v50,
              &v59);
      if ( v26 == -2147023728 )
      {
        v26 = 0;
      }
      else if ( v26 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
          goto LABEL_187;
        v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
        v34 = 0;
        if ( v33 )
        {
          LODWORD(lpThreadId) = v26;
          dwCreationFlags[0] = 3439;
          goto LABEL_184;
        }
        goto LABEL_186;
      }
      if ( !v50 )
        goto LABEL_109;
      v26 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v50 + 24LL))(v50, &v61);
      if ( v26 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
          goto LABEL_187;
        v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
        v34 = 0;
        if ( v33 )
        {
          LODWORD(lpThreadId) = v26;
          dwCreationFlags[0] = 3442;
          goto LABEL_184;
        }
        goto LABEL_186;
      }
      if ( v61 )
      {
        if ( v61 != 6 )
        {
          if ( v61 == -1073741824 )
            goto LABEL_109;
LABEL_105:
          if ( !v31 || (*((_BYTE *)this + 1420) & 1) != 0 )
            v60.LowPart |= 4u;
          v26 = CDlpTask::ProgressHandlerAction(this, v50, v59, (unsigned int *)&v60);
          if ( v26 < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
              goto LABEL_187;
            v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
            v34 = 0;
            if ( v33 )
            {
              LODWORD(lpThreadId) = v26;
              dwCreationFlags[0] = 3471;
              goto LABEL_184;
            }
            goto LABEL_186;
          }
          goto LABEL_109;
        }
        v60.LowPart |= 2u;
        v26 = CDlpTask::ProgressHandlerAction(this, v50, v59, (unsigned int *)&v60);
        if ( v26 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
            goto LABEL_187;
          v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
          v34 = 0;
          if ( !v33 )
            goto LABEL_186;
          LODWORD(lpThreadId) = v26;
          dwCreationFlags[0] = 3456;
          goto LABEL_184;
        }
      }
      else
      {
        if ( v51 == v59 )
          goto LABEL_105;
        v60.LowPart = 1;
        v26 = CDlpTask::ProgressHandlerAction(this, v50, v59, (unsigned int *)&v60);
        if ( v26 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
            goto LABEL_187;
          v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
          v34 = 0;
          if ( v33 )
          {
            LODWORD(lpThreadId) = v26;
            dwCreationFlags[0] = 3448;
            goto LABEL_184;
          }
          goto LABEL_186;
        }
        v51 = v59;
      }
LABEL_109:
      if ( !v31 )
      {
        v35 = (void *)*((_QWORD *)this + 31);
        if ( !v35 )
          v35 = 0;
        if ( !SetEvent(v35) )
        {
          v36 = GetLastError();
          v26 = v36;
          if ( v36 )
          {
            if ( v36 > 0 )
              v26 = (unsigned __int16)v36 | 0x80070000;
          }
          else
          {
            v26 = -2147467259;
          }
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
          {
            v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
            v34 = 0;
            if ( v26 < 0 && v33 )
            {
              LODWORD(lpThreadId) = v26;
              dwCreationFlags[0] = 3480;
              goto LABEL_184;
            }
            goto LABEL_186;
          }
          goto LABEL_187;
        }
      }
      v16 = v52;
    }
    v16 = 0;
    if ( !GetExitCodeThread(Thread, &ExitCode) )
      break;
    v26 = ExitCode;
    v32 = (ExitCode & 0x80000000) != 0;
    if ( (int)ExitCode > 0 )
    {
      v26 = (unsigned __int16)ExitCode | 0x80070000;
      v32 = 1;
    }
    if ( v32 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
        goto LABEL_187;
      v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
      v34 = 0;
      if ( v33 )
      {
        LODWORD(lpThreadId) = v26;
        dwCreationFlags[0] = 3487;
        goto LABEL_184;
      }
LABEL_186:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v34);
      goto LABEL_187;
    }
    v52 = 0;
  }
  v38 = GetLastError();
  v26 = v38;
  if ( v38 )
  {
    if ( v38 > 0 )
      v26 = (unsigned __int16)v38 | 0x80070000;
  }
  else
  {
    v26 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176) )
  {
    v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 176);
    v34 = 0;
    if ( v26 < 0 && v33 )
    {
      LODWORD(lpThreadId) = v26;
      dwCreationFlags[0] = 3486;
      goto LABEL_184;
    }
    goto LABEL_186;
  }
LABEL_187:
  v21 = v26;
  v25 = Thread;
LABEL_188:
  v41 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v42 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v42, 2, L"Signalling actions thread to shut down.");
  }
  v43 = (void *)*((_QWORD *)this + 29);
  if ( !v43 )
    v43 = 0;
  SetEvent(v43);
  if ( v21 < 0 )
  {
    if ( v50 )
    {
      (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( (*(int (__fastcall **)(CDlpTask *, struct IDlpAction **, unsigned int *))(*(_QWORD *)this + 160LL))(
           this,
           &v50,
           &v59) >= 0
      && v50
      && (*(int (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v50 + 24LL))(v50, &v61) >= 0
      && v61 == 3 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176) )
      {
        v44 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176);
        CDlpLogT<CEmptyType>::DlpLogFormat(v44, 2, L"Cancelling running action...");
      }
      (*(void (__fastcall **)(struct IDlpAction *, CDlpTask *))(*(_QWORD *)v50 + 40LL))(v50, this);
    }
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176) )
  {
    v45 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v45, 2, L"Waiting for actions thread to exit.");
  }
  WaitForSingleObject(v25, 0xFFFFFFFF);
  v2 = v25;
  v3 = v21;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176) )
  {
    v46 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))((char *)this + 176);
    CDlpLogT<CEmptyType>::DlpLogFormat(v46, 2, L"Actions thread has exited.");
  }
LABEL_206:
  v53 = v3;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, signed int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    8196,
    0,
    &v53,
    0,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v2 )
    CloseHandle(v2);
  if ( v50 )
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v50 + 16LL))(v50);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140036b00  push    rbp
0x140036b02  push    rbx
0x140036b03  push    rsi
0x140036b04  push    rdi
0x140036b05  push    r12
0x140036b07  push    r13
0x140036b09  push    r14
0x140036b0b  push    r15
0x140036b0d  lea     rbp, [rsp-1Fh]
0x140036b12  sub     rsp, 0A8h
0x140036b19  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x140036b21  mov     r15, rcx
0x140036b24  xor     r13d, r13d
0x140036b27  mov     [rbp+57h+var_A0], r13
0x140036b2b  mov     ebx, r13d
0x140036b2e  mov     [rbp+57h+arg_10], r13d
0x140036b32  mov     [rbp+57h+arg_0], r13d
0x140036b36  mov     [rbp+57h+ExitCode], r13d
0x140036b3a  xorps   xmm0, xmm0
0x140036b3d  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x140036b41  mov     [rbp+57h+var_90], r13d
0x140036b45  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r13
0x140036b49  add     rcx, 368h; this
0x140036b50  lea     rdx, [rbp+57h+arg_0]; enum WINDLP_STATE *
0x140036b54  call    ?Get@CDlpState@@QEAAJPEAW4WINDLP_STATE@@@Z; CDlpState::Get(WINDLP_STATE *)
0x140036b59  mov     edi, eax
0x140036b5b  test    eax, eax
0x140036b5d  jns     short loc_140036BD5
0x140036b5f  lea     rsi, [r15+0B0h]
0x140036b66  mov     rdx, [rsi]
0x140036b69  mov     rcx, rsi
0x140036b6c  mov     rax, [rdx+10h]
0x140036b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b75  test    rax, rax
0x140036b78  jz      loc_1400379FA
0x140036b7e  mov     rax, [rsi]
0x140036b81  mov     rcx, rsi
0x140036b84  mov     rax, [rax+10h]
0x140036b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b8d  mov     esi, r13d
0x140036b90  test    rax, rax
0x140036b93  jz      short loc_140036BC9
0x140036b95  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036b99  mov     [rsp+0E0h+dwCreationFlags], 0D2Bh
0x140036ba1  lea     r9, aCdlptaskExecut_0; "CDlpTask::ExecuteActions"
0x140036ba8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140036baf  mov     edx, 4
0x140036bb4  mov     rcx, rax
0x140036bb7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140036bbc  test    eax, eax
0x140036bbe  mov     esi, eax
0x140036bc0  jns     short loc_140036BC9
0x140036bc2  mov     ecx, eax
0x140036bc4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140036bc9  mov     ecx, esi
0x140036bcb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140036bd0  jmp     loc_1400379FA
0x140036bd5  mov     eax, [r15+17Ch]
0x140036bdc  mov     [rbp+57h+var_8C], eax
0x140036bdf  lea     rdi, [r15+3C8h]
0x140036be6  mov     rcx, rdi; lpCriticalSection
0x140036be9  call    cs:__imp_EnterCriticalSection
0x140036bf0  nop     dword ptr [rax+rax+00h]
0x140036bf5  mov     esi, 1
0x140036bfa  mov     [rbp+57h+var_58], esi
0x140036bfd  xor     eax, eax
0x140036bff  mov     [r15+3A8h], rax
0x140036c06  mov     [r15+3B0h], rax
0x140036c0d  mov     [r15+3B8h], rax
0x140036c14  xor     ecx, ecx
0x140036c16  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140036c1b  nop
0x140036c1c  mov     eax, [rbp+57h+var_58]
0x140036c1f  test    eax, eax
0x140036c21  jz      short loc_140036C36
0x140036c23  mov     rcx, rdi; lpCriticalSection
0x140036c26  call    cs:__imp_LeaveCriticalSection
0x140036c2d  nop     dword ptr [rax+rax+00h]
0x140036c32  mov     [rbp+57h+var_58], r13d
0x140036c36  mov     [r15+5A8h], r13
0x140036c3d  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140036c41  call    cs:__imp_GetSystemTimeAsFileTime
0x140036c48  nop     dword ptr [rax+rax+00h]
0x140036c4d  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x140036c50  mov     dword ptr [rbp+57h+arg_8+4], eax
0x140036c53  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140036c56  mov     dword ptr [rbp+57h+arg_8], eax
0x140036c59  mov     rax, [r15+4A0h]
0x140036c60  test    rax, rax
0x140036c63  cmovz   rax, r13
0x140036c67  movsxd  rcx, [rbp+57h+arg_0]
0x140036c6b  mov     rdx, qword ptr [rbp+57h+arg_8]; union _ULARGE_INTEGER
0x140036c6f  mov     rcx, [rax+rcx*8]; this
0x140036c73  call    ?Set@CULargeInteger@@QEAAJT_ULARGE_INTEGER@@@Z; CULargeInteger::Set(_ULARGE_INTEGER)
0x140036c78  mov     edi, eax
0x140036c7a  test    eax, eax
0x140036c7c  jns     short loc_140036CC9
0x140036c7e  lea     rsi, [r15+0B0h]
0x140036c85  mov     rax, [rsi]
0x140036c88  mov     rcx, rsi
0x140036c8b  mov     rax, [rax+10h]
0x140036c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036c94  test    rax, rax
0x140036c97  jz      loc_1400379FA
0x140036c9d  mov     rax, [rsi]
0x140036ca0  mov     rcx, rsi
0x140036ca3  mov     rax, [rax+10h]
0x140036ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036cac  mov     esi, r13d
0x140036caf  test    rax, rax
0x140036cb2  jz      loc_140036BC9
0x140036cb8  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036cbc  mov     [rsp+0E0h+dwCreationFlags], 0D37h
0x140036cc4  jmp     loc_140036BA1
0x140036cc9  mov     rcx, [r15+0E8h]
0x140036cd0  test    rcx, rcx
0x140036cd3  cmovz   rcx, r13; hEvent
0x140036cd7  call    cs:__imp_ResetEvent
0x140036cde  nop     dword ptr [rax+rax+00h]
0x140036ce3  test    eax, eax
0x140036ce5  jnz     short loc_140036D5E
0x140036ce7  call    cs:__imp_GetLastError
0x140036cee  nop     dword ptr [rax+rax+00h]
0x140036cf3  mov     edi, eax
0x140036cf5  test    eax, eax
0x140036cf7  jnz     short loc_140036D00
0x140036cf9  mov     edi, 80004005h
0x140036cfe  jmp     short loc_140036D0B
0x140036d00  jle     short loc_140036D0B
0x140036d02  movzx   edi, ax
0x140036d05  or      edi, 80070000h
0x140036d0b  lea     rsi, [r15+0B0h]
0x140036d12  mov     rax, [rsi]
0x140036d15  mov     rcx, rsi
0x140036d18  mov     rax, [rax+10h]
0x140036d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036d21  test    rax, rax
0x140036d24  jz      loc_1400379FA
0x140036d2a  mov     rax, [rsi]
0x140036d2d  mov     rcx, rsi
0x140036d30  mov     rax, [rax+10h]
0x140036d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036d39  mov     esi, r13d
0x140036d3c  test    edi, edi
0x140036d3e  jns     loc_140036BC9
0x140036d44  test    rax, rax
0x140036d47  jz      loc_140036BC9
0x140036d4d  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036d51  mov     [rsp+0E0h+dwCreationFlags], 0D3Bh
0x140036d59  jmp     loc_140036BA1
0x140036d5e  mov     rcx, [r15+0F0h]
0x140036d65  test    rcx, rcx
0x140036d68  cmovz   rcx, r13; hEvent
0x140036d6c  call    cs:__imp_ResetEvent
0x140036d73  nop     dword ptr [rax+rax+00h]
0x140036d78  test    eax, eax
0x140036d7a  jnz     short loc_140036DF3
0x140036d7c  call    cs:__imp_GetLastError
0x140036d83  nop     dword ptr [rax+rax+00h]
0x140036d88  mov     edi, eax
0x140036d8a  test    eax, eax
0x140036d8c  jnz     short loc_140036D95
0x140036d8e  mov     edi, 80004005h
0x140036d93  jmp     short loc_140036DA0
0x140036d95  jle     short loc_140036DA0
0x140036d97  movzx   edi, ax
0x140036d9a  or      edi, 80070000h
0x140036da0  lea     rsi, [r15+0B0h]
0x140036da7  mov     rax, [rsi]
0x140036daa  mov     rcx, rsi
0x140036dad  mov     rax, [rax+10h]
0x140036db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036db6  test    rax, rax
0x140036db9  jz      loc_1400379FA
0x140036dbf  mov     rax, [rsi]
0x140036dc2  mov     rcx, rsi
0x140036dc5  mov     rax, [rax+10h]
0x140036dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036dce  mov     esi, r13d
0x140036dd1  test    edi, edi
0x140036dd3  jns     loc_140036BC9
0x140036dd9  test    rax, rax
0x140036ddc  jz      loc_140036BC9
0x140036de2  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036de6  mov     [rsp+0E0h+dwCreationFlags], 0D3Ch
0x140036dee  jmp     loc_140036BA1
0x140036df3  mov     rcx, [r15+0F8h]
0x140036dfa  test    rcx, rcx
0x140036dfd  cmovz   rcx, r13; hEvent
0x140036e01  call    cs:__imp_ResetEvent
0x140036e08  nop     dword ptr [rax+rax+00h]
0x140036e0d  test    eax, eax
0x140036e0f  jnz     short loc_140036E88
0x140036e11  call    cs:__imp_GetLastError
0x140036e18  nop     dword ptr [rax+rax+00h]
0x140036e1d  mov     edi, eax
0x140036e1f  test    eax, eax
0x140036e21  jnz     short loc_140036E2A
0x140036e23  mov     edi, 80004005h
0x140036e28  jmp     short loc_140036E35
0x140036e2a  jle     short loc_140036E35
0x140036e2c  movzx   edi, ax
0x140036e2f  or      edi, 80070000h
0x140036e35  lea     rsi, [r15+0B0h]
0x140036e3c  mov     rax, [rsi]
0x140036e3f  mov     rcx, rsi
0x140036e42  mov     rax, [rax+10h]
0x140036e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e4b  test    rax, rax
0x140036e4e  jz      loc_1400379FA
0x140036e54  mov     rax, [rsi]
0x140036e57  mov     rcx, rsi
0x140036e5a  mov     rax, [rax+10h]
0x140036e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e63  mov     esi, r13d
0x140036e66  test    edi, edi
0x140036e68  jns     loc_140036BC9
0x140036e6e  test    rax, rax
0x140036e71  jz      loc_140036BC9
0x140036e77  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036e7b  mov     [rsp+0E0h+dwCreationFlags], 0D3Dh
0x140036e83  jmp     loc_140036BA1
0x140036e88  mov     [rsp+0E0h+lpThreadId], r13; lpThreadId
0x140036e8d  mov     [rsp+0E0h+dwCreationFlags], r13d; dwCreationFlags
0x140036e92  mov     r9, r15; lpParameter
0x140036e95  lea     r8, ?ExecuteActionsThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x140036e9c  xor     edx, edx; dwStackSize
0x140036e9e  xor     ecx, ecx; lpThreadAttributes
0x140036ea0  call    cs:__imp_CreateThread
0x140036ea7  nop     dword ptr [rax+rax+00h]
0x140036eac  mov     rbx, rax
0x140036eaf  test    rax, rax
0x140036eb2  jnz     short loc_140036F2E
0x140036eb4  mov     rbx, r13
0x140036eb7  call    cs:__imp_GetLastError
0x140036ebe  nop     dword ptr [rax+rax+00h]
0x140036ec3  mov     edi, eax
0x140036ec5  test    eax, eax
0x140036ec7  jnz     short loc_140036ED0
0x140036ec9  mov     edi, 80004005h
0x140036ece  jmp     short loc_140036EDB
0x140036ed0  jle     short loc_140036EDB
0x140036ed2  movzx   edi, ax
0x140036ed5  or      edi, 80070000h
0x140036edb  lea     rsi, [r15+0B0h]
0x140036ee2  mov     rax, [rsi]
0x140036ee5  mov     rcx, rsi
0x140036ee8  mov     rax, [rax+10h]
0x140036eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ef1  test    rax, rax
0x140036ef4  jz      loc_1400379FA
0x140036efa  mov     rax, [rsi]
0x140036efd  mov     rcx, rsi
0x140036f00  mov     rax, [rax+10h]
0x140036f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f09  mov     esi, r13d
0x140036f0c  test    edi, edi
0x140036f0e  jns     loc_140036BC9
0x140036f14  test    rax, rax
0x140036f17  jz      loc_140036BC9
0x140036f1d  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x140036f21  mov     [rsp+0E0h+dwCreationFlags], 0D47h
0x140036f29  jmp     loc_140036BA1
0x140036f2e  mov     r13d, esi
0x140036f31  mov     [rbp+57h+var_94], esi
0x140036f34  mov     rax, [r15+0F0h]
0x140036f3b  xor     r14d, r14d
0x140036f3e  test    rax, rax
0x140036f41  cmovz   rax, r14
0x140036f45  mov     [rbp+57h+Handles], rax
0x140036f49  mov     eax, r14d
0x140036f4c  test    rbx, rbx
0x140036f4f  cmovnz  rax, rbx
0x140036f53  mov     [rbp+57h+Handles+8], rax
0x140036f57  call    cs:__imp_GetTickCount
0x140036f5e  nop     dword ptr [rax+rax+00h]
0x140036f63  mov     [r15+5A4h], eax
0x140036f6a  mov     [r15+5B0h], r14
0x140036f71  mov     [r15+5B8h], r14
0x140036f78  lea     rsi, [r15+0B0h]
0x140036f7f  mov     rax, [rsi]
0x140036f82  mov     rcx, rsi
0x140036f85  mov     rax, [rax+10h]
0x140036f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f8e  test    rax, rax
0x140036f91  jz      short loc_140036FBF
0x140036f93  mov     edi, [r15+5A0h]
0x140036f9a  mov     rax, [rsi]
0x140036f9d  mov     rcx, rsi
0x140036fa0  mov     rax, [rax+10h]
0x140036fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036fa9  mov     r9d, edi
0x140036fac  lea     r8, aActionExecutio; "Action execution thread timeout period:"...
0x140036fb3  lea     edx, [r14+2]
0x140036fb7  mov     rcx, rax
0x140036fba  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140036fbf  mov     rcx, [rbp+57h+var_A0]
0x140036fc3  test    rcx, rcx
0x140036fc6  jz      short loc_140036FD8
0x140036fc8  mov     rax, [rcx]
  ... truncated ...
```
