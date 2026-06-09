# CDlpTask::ExecuteTransfer(void)

- ea: `0x140038564`
- end: `0x140038d87`
- name: `?ExecuteTransfer@CDlpTask@@AEAAJXZ`
- size: `2083`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1400356d0`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002baa0`
- `0x140034ab4`
- `0x140038564`
- `0x1400459d4`
- `0x140047754`
- `0x14004c214`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140038d66`
- `KERNEL32!CloseHandle` at `0x140038d66`
- `KERNEL32!GetExitCodeThread` at `0x140038a90`
- `KERNEL32!GetExitCodeThread` at `0x140038a90`
- `KERNEL32!CreateThread` at `0x1400387ab`
- `KERNEL32!CreateThread` at `0x1400387ab`
- `KERNEL32!GetTickCount` at `0x14003883d`
- `KERNEL32!GetTickCount` at `0x14003883d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140038636`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140038636`
- `KERNEL32!GetLastError` at `0x1400387c1`
- `KERNEL32!GetLastError` at `0x140038a10`
- `KERNEL32!GetLastError` at `0x140038aa0`
- `KERNEL32!GetLastError` at `0x1400387c1`
- `KERNEL32!GetLastError` at `0x140038a10`
- `KERNEL32!GetLastError` at `0x140038aa0`
- `KERNEL32!WaitForSingleObject` at `0x140038941`
- `KERNEL32!WaitForSingleObject` at `0x140038c62`
- `KERNEL32!WaitForSingleObject` at `0x140038941`
- `KERNEL32!WaitForSingleObject` at `0x140038c62`

## string_xrefs

- `0x1400385f3`: `CDlpTask::ExecuteTransfer`
- `0x1400388d2`: `CDlpTask::ExecuteTransfer`
- `0x140038bd5`: `CDlpTask::ExecuteTransfer`
- `0x140038923`: `Transfer execution thread timeout period: [%d ms]`
- `0x140038c45`: `Waiting for transfer thread to exit.`
- `0x140038c9c`: `Transfer thread has exited.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecuteTransfer(union _ULARGE_INTEGER *this)
{
  void *v2; // rdi
  signed int v3; // r14d
  __int64 v4; // rax
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  HANDLE Thread; // rsi
  signed int v9; // eax
  ULONGLONG v10; // rax
  int v11; // r13d
  union _ULARGE_INTEGER *v12; // r12
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // edi
  int v16; // eax
  DWORD HighPart; // edi
  __int64 v18; // rax
  DWORD v19; // eax
  signed int v20; // r14d
  __int64 v21; // rax
  unsigned int v22; // edi
  signed int LastError; // eax
  signed int v24; // eax
  HANDLE v25; // rdi
  int v26; // eax
  union _ULARGE_INTEGER *v27; // r12
  __int64 v28; // rax
  __int64 v29; // rax
  union _ULARGE_INTEGER *v30; // rsi
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-40h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-38h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-20h] BYREF
  union _ULARGE_INTEGER v35; // [rsp+48h] [rbp-18h]
  __int64 v36; // [rsp+50h] [rbp-10h]
  DWORD ExitCode; // [rsp+A0h] [rbp+40h] BYREF
  signed int v38; // [rsp+A8h] [rbp+48h] BYREF
  union _ULARGE_INTEGER v39; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int64 v40; // [rsp+B8h] [rbp+58h] BYREF

  v36 = -2;
  v2 = 0;
  ExitCode = 0;
  SystemTimeAsFileTime = 0;
  v40 = 0;
  v39.QuadPart = 0;
  v3 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *, unsigned __int64 *, union _ULARGE_INTEGER *))(this->QuadPart + 224))(
         this,
         &v40,
         &v39);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
      goto LABEL_86;
    v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
    v5 = 0;
    if ( !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3218;
    goto LABEL_5;
  }
  this[181] = v39;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v35 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
  v7 = CProgressData::Set((CProgressData *)&this[117], (union _ULARGE_INTEGER)SystemTimeAsFileTime, v39, 0);
  v3 = v7;
  if ( v7 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v3 >= 0 )
  {
    v3 = CProgressList::Reset((CProgressList *)&this[127]);
    if ( v3 >= 0 )
    {
      v3 = CProgressList::AddItem((CProgressList *)&this[127], (struct CProgressData *)&this[117]);
      if ( v3 >= 0 )
      {
        Thread = CreateThread(0, 0, CDlpTask::ExecuteTransferThreadProc, this, 0, 0);
        if ( Thread )
        {
          this[180].HighPart = GetTickCount();
          this[182].QuadPart = 0;
          if ( v40 )
            v10 = 100 * v39.QuadPart / v40;
          else
            v10 = 0;
          this[183].QuadPart = v10;
          v11 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 1u);
          v12 = this + 22;
          v13 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
          if ( v11 >= 0 )
          {
            if ( v13 )
            {
              HighPart = this[179].HighPart;
              v18 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v12->QuadPart + 16))(this + 22);
              CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"Transfer execution thread timeout period: [%d ms]", HighPart);
            }
            while ( 1 )
            {
              v19 = WaitForSingleObject(Thread, this[179].HighPart);
              if ( !v19 )
                break;
              if ( v19 != 258 )
              {
                if ( v19 == -1 )
                {
                  LastError = GetLastError();
                  v20 = LastError;
                  if ( LastError > 0 )
                    v20 = (unsigned __int16)LastError | 0x80070000;
                  if ( v20 < 0
                    && (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
                  {
                    v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
                    v22 = 0;
                    if ( v21 )
                    {
                      LODWORD(lpThreadId) = v20;
                      dwCreationFlags[0] = 3274;
                      goto LABEL_77;
                    }
                    goto LABEL_79;
                  }
                }
                else
                {
                  v20 = -2147418113;
                  if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
                  {
                    v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
                    v22 = 0;
                    if ( v21 )
                    {
                      LODWORD(lpThreadId) = -2147418113;
                      dwCreationFlags[0] = 3279;
                      goto LABEL_77;
                    }
LABEL_79:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
                  }
                }
LABEL_80:
                v25 = Thread;
                goto LABEL_81;
              }
              v20 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 0);
              if ( v20 < 0 )
              {
                if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
                {
                  v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
                  v22 = 0;
                  if ( v21 )
                  {
                    LODWORD(lpThreadId) = v20;
                    dwCreationFlags[0] = 3271;
LABEL_77:
                    v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
                            v21,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDlpTask::ExecuteTransfer",
                            *(_QWORD *)dwCreationFlags,
                            lpThreadId);
                    v22 = v26;
                    if ( v26 < 0 )
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
                  }
                  goto LABEL_79;
                }
                goto LABEL_80;
              }
            }
            if ( !GetExitCodeThread(Thread, &ExitCode) )
            {
              v24 = GetLastError();
              v20 = v24;
              if ( v24 )
              {
                if ( v24 > 0 )
                  v20 = (unsigned __int16)v24 | 0x80070000;
              }
              else
              {
                v20 = -2147467259;
              }
              if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
              {
                v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
                v22 = 0;
                if ( v20 < 0 && v21 )
                {
                  LODWORD(lpThreadId) = v20;
                  dwCreationFlags[0] = 3262;
                  goto LABEL_77;
                }
                goto LABEL_79;
              }
              goto LABEL_80;
            }
            v20 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 2u);
            if ( v20 < 0 )
            {
              if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
              {
                v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
                v22 = 0;
                if ( v21 )
                {
                  LODWORD(lpThreadId) = v20;
                  dwCreationFlags[0] = 3266;
                  goto LABEL_77;
                }
                goto LABEL_79;
              }
              goto LABEL_80;
            }
            v20 = ExitCode;
            if ( (int)ExitCode > 0 )
              v20 = (unsigned __int16)ExitCode | 0x80070000;
            v25 = Thread;
            if ( v20 < 0 && (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
            {
              v21 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
              v22 = 0;
              if ( v21 )
              {
                LODWORD(lpThreadId) = v20;
                dwCreationFlags[0] = 3267;
                goto LABEL_77;
              }
              goto LABEL_79;
            }
LABEL_81:
            v11 = v20;
            Thread = v25;
          }
          else if ( v13 )
          {
            v14 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v12->QuadPart + 16))(this + 22);
            v15 = 0;
            if ( v14 )
            {
              LODWORD(lpThreadId) = v11;
              dwCreationFlags[0] = 3249;
              v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v14,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpTask::ExecuteTransfer",
                      *(_QWORD *)dwCreationFlags,
                      lpThreadId);
              v15 = v16;
              if ( v16 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
          }
          v27 = this + 22;
          if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
          {
            v28 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v27->QuadPart + 16))(this + 22);
            CDlpLogT<CEmptyType>::DlpLogFormat(v28, 2, L"Waiting for transfer thread to exit.");
          }
          WaitForSingleObject(Thread, 0xFFFFFFFF);
          v2 = Thread;
          v3 = v11;
          if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v27->QuadPart + 16))(this + 22) )
          {
            v29 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v27->QuadPart + 16))(this + 22);
            CDlpLogT<CEmptyType>::DlpLogFormat(v29, 2, L"Transfer thread has exited.");
          }
          goto LABEL_86;
        }
        v2 = 0;
        v9 = GetLastError();
        v3 = v9;
        if ( v9 )
        {
          if ( v9 > 0 )
            v3 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
          goto LABEL_86;
        v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
        v5 = 0;
        if ( v3 >= 0 || !v4 )
          goto LABEL_7;
        LODWORD(lpThreadId) = v3;
        dwCreationFlags[0] = 3239;
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
          goto LABEL_86;
        v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
        v5 = 0;
        if ( !v4 )
          goto LABEL_7;
        LODWORD(lpThreadId) = v3;
        dwCreationFlags[0] = 3229;
      }
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        goto LABEL_86;
      v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
      v5 = 0;
      if ( !v4 )
        goto LABEL_7;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3228;
    }
LABEL_5:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpTask::ExecuteTransfer",
           *(_QWORD *)dwCreationFlags,
           lpThreadId);
    v5 = v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_7;
  }
  if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
  {
    v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
    v5 = 0;
    if ( v4 )
    {
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3224;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  }
LABEL_86:
  v30 = this + 2;
  if ( (*(int (__fastcall **)(union _ULARGE_INTEGER *, unsigned __int64 *, union _ULARGE_INTEGER *))(this->QuadPart + 224))(
         this,
         &v40,
         &v39) >= 0 )
  {
    (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, __int64, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, _DWORD))v30->QuadPart)(
      this + 2,
      4099,
      1,
      &v39,
      this + 186,
      0);
    (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, __int64, unsigned __int64 *, union _ULARGE_INTEGER *, _DWORD))v30->QuadPart)(
      this + 2,
      4100,
      1,
      &v40,
      this + 186,
      0);
  }
  v38 = v3;
  (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, _QWORD, signed int *, union _ULARGE_INTEGER *, _DWORD))v30->QuadPart)(
    this + 2,
    4103,
    0,
    &v38,
    this + 186,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140038564  push    rbp
0x140038566  push    rsi
0x140038567  push    rdi
0x140038568  push    r12
0x14003856a  push    r13
0x14003856c  push    r14
0x14003856e  push    r15
0x140038570  mov     rbp, rsp
0x140038573  sub     rsp, 60h
0x140038577  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x14003857f  mov     r15, rcx
0x140038582  xor     edi, edi
0x140038584  mov     [rbp+ExitCode], edi
0x140038587  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rdi
0x14003858b  mov     [rbp+arg_18], rdi
0x14003858f  mov     qword ptr [rbp+arg_10], rdi
0x140038593  mov     rax, [rcx]
0x140038596  lea     r8, [rbp+arg_10]
0x14003859a  lea     rdx, [rbp+arg_18]
0x14003859e  mov     rax, [rax+0E0h]
0x1400385a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385aa  mov     r14d, eax
0x1400385ad  test    eax, eax
0x1400385af  jns     short loc_140038627
0x1400385b1  lea     rsi, [r15+0B0h]
0x1400385b8  mov     rdx, [rsi]
0x1400385bb  mov     rcx, rsi
0x1400385be  mov     rax, [rdx+10h]
0x1400385c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385c7  test    rax, rax
0x1400385ca  jz      loc_140038CAD
0x1400385d0  mov     rax, [rsi]
0x1400385d3  mov     rcx, rsi
0x1400385d6  mov     rax, [rax+10h]
0x1400385da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385df  xor     esi, esi
0x1400385e1  test    rax, rax
0x1400385e4  jz      short loc_14003861B
0x1400385e6  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x1400385eb  mov     [rsp+60h+dwCreationFlags], 0C92h
0x1400385f3  lea     r9, aCdlptaskExecut_2; "CDlpTask::ExecuteTransfer"
0x1400385fa  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140038601  mov     edx, 4
0x140038606  mov     rcx, rax
0x140038609  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003860e  test    eax, eax
0x140038610  mov     esi, eax
0x140038612  jns     short loc_14003861B
0x140038614  mov     ecx, eax
0x140038616  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003861b  mov     ecx, esi
0x14003861d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140038622  jmp     loc_140038CAD
0x140038627  mov     rax, qword ptr [rbp+arg_10]
0x14003862b  mov     [r15+5A8h], rax
0x140038632  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140038636  call    cs:__imp_GetSystemTimeAsFileTime
0x14003863d  nop     dword ptr [rax+rax+00h]
0x140038642  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140038645  mov     dword ptr [rbp+var_18+4], eax
0x140038648  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14003864b  mov     dword ptr [rbp+var_18], eax
0x14003864e  lea     r12, [r15+3A8h]
0x140038655  xor     r9d, r9d; union _ULARGE_INTEGER
0x140038658  mov     r8, qword ptr [rbp+arg_10]; union _ULARGE_INTEGER
0x14003865c  mov     rdx, qword ptr [rbp+var_18]; union _ULARGE_INTEGER
0x140038660  mov     rcx, r12; this
0x140038663  call    ?Set@CProgressData@@QEAAJT_ULARGE_INTEGER@@00@Z; CProgressData::Set(_ULARGE_INTEGER,_ULARGE_INTEGER,_ULARGE_INTEGER)
0x140038668  mov     r14d, eax
0x14003866b  test    eax, eax
0x14003866d  jns     short loc_140038676
0x14003866f  mov     ecx, eax
0x140038671  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140038676  mov     ecx, r14d
0x140038679  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003867e  test    r14d, r14d
0x140038681  jns     short loc_1400386CE
0x140038683  lea     rsi, [r15+0B0h]
0x14003868a  mov     rax, [rsi]
0x14003868d  mov     rcx, rsi
0x140038690  mov     rax, [rax+10h]
0x140038694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038699  test    rax, rax
0x14003869c  jz      loc_140038CAD
0x1400386a2  mov     rax, [rsi]
0x1400386a5  mov     rcx, rsi
0x1400386a8  mov     rax, [rax+10h]
0x1400386ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400386b1  xor     esi, esi
0x1400386b3  test    rax, rax
0x1400386b6  jz      loc_14003861B
0x1400386bc  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x1400386c1  mov     [rsp+60h+dwCreationFlags], 0C98h
0x1400386c9  jmp     loc_1400385F3
0x1400386ce  lea     rsi, [r15+3F8h]
0x1400386d5  mov     rcx, rsi; this
0x1400386d8  call    ?Reset@CProgressList@@QEAAJXZ; CProgressList::Reset(void)
0x1400386dd  mov     r14d, eax
0x1400386e0  test    eax, eax
0x1400386e2  jns     short loc_14003872F
0x1400386e4  lea     rsi, [r15+0B0h]
0x1400386eb  mov     rax, [rsi]
0x1400386ee  mov     rcx, rsi
0x1400386f1  mov     rax, [rax+10h]
0x1400386f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400386fa  test    rax, rax
0x1400386fd  jz      loc_140038CAD
0x140038703  mov     rax, [rsi]
0x140038706  mov     rcx, rsi
0x140038709  mov     rax, [rax+10h]
0x14003870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038712  xor     esi, esi
0x140038714  test    rax, rax
0x140038717  jz      loc_14003861B
0x14003871d  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x140038722  mov     [rsp+60h+dwCreationFlags], 0C9Ch
0x14003872a  jmp     loc_1400385F3
0x14003872f  mov     rdx, r12; struct CProgressData *
0x140038732  mov     rcx, rsi; this
0x140038735  call    ?AddItem@CProgressList@@QEAAJPEAVCProgressData@@@Z; CProgressList::AddItem(CProgressData *)
0x14003873a  mov     r14d, eax
0x14003873d  test    eax, eax
0x14003873f  jns     short loc_14003878C
0x140038741  lea     rsi, [r15+0B0h]
0x140038748  mov     rax, [rsi]
0x14003874b  mov     rcx, rsi
0x14003874e  mov     rax, [rax+10h]
0x140038752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038757  test    rax, rax
0x14003875a  jz      loc_140038CAD
0x140038760  mov     rax, [rsi]
0x140038763  mov     rcx, rsi
0x140038766  mov     rax, [rax+10h]
0x14003876a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003876f  xor     esi, esi
0x140038771  test    rax, rax
0x140038774  jz      loc_14003861B
0x14003877a  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x14003877f  mov     [rsp+60h+dwCreationFlags], 0C9Dh
0x140038787  jmp     loc_1400385F3
0x14003878c  mov     [rsp+60h+lpThreadId], 0; lpThreadId
0x140038795  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x14003879d  mov     r9, r15; lpParameter
0x1400387a0  lea     r8, ?ExecuteTransferThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x1400387a7  xor     edx, edx; dwStackSize
0x1400387a9  xor     ecx, ecx; lpThreadAttributes
0x1400387ab  call    cs:__imp_CreateThread
0x1400387b2  nop     dword ptr [rax+rax+00h]
0x1400387b7  mov     rsi, rax
0x1400387ba  test    rax, rax
0x1400387bd  jnz     short loc_14003883D
0x1400387bf  xor     edi, edi
0x1400387c1  call    cs:__imp_GetLastError
0x1400387c8  nop     dword ptr [rax+rax+00h]
0x1400387cd  mov     r14d, eax
0x1400387d0  test    eax, eax
0x1400387d2  jnz     short loc_1400387DC
0x1400387d4  mov     r14d, 80004005h
0x1400387da  jmp     short loc_1400387E9
0x1400387dc  jle     short loc_1400387E9
0x1400387de  movzx   r14d, ax
0x1400387e2  or      r14d, 80070000h
0x1400387e9  lea     rsi, [r15+0B0h]
0x1400387f0  mov     rax, [rsi]
0x1400387f3  mov     rcx, rsi
0x1400387f6  mov     rax, [rax+10h]
0x1400387fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400387ff  test    rax, rax
0x140038802  jz      loc_140038CAD
0x140038808  mov     rax, [rsi]
0x14003880b  mov     rcx, rsi
0x14003880e  mov     rax, [rax+10h]
0x140038812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038817  xor     esi, esi
0x140038819  test    r14d, r14d
0x14003881c  jns     loc_14003861B
0x140038822  test    rax, rax
0x140038825  jz      loc_14003861B
0x14003882b  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x140038830  mov     [rsp+60h+dwCreationFlags], 0CA7h
0x140038838  jmp     loc_1400385F3
0x14003883d  call    cs:__imp_GetTickCount
0x140038844  nop     dword ptr [rax+rax+00h]
0x140038849  mov     [r15+5A4h], eax
0x140038850  mov     qword ptr [r15+5B0h], 0
0x14003885b  mov     rcx, [rbp+arg_18]
0x14003885f  test    rcx, rcx
0x140038862  jz      short loc_140038870
0x140038864  imul    rax, qword ptr [rbp+arg_10], 64h ; 'd'
0x140038869  xor     edx, edx
0x14003886b  div     rcx
0x14003886e  jmp     short loc_140038872
0x140038870  xor     eax, eax
0x140038872  mov     [r15+5B8h], rax
0x140038879  mov     edx, 1; unsigned int
0x14003887e  mov     rcx, r15; this
0x140038881  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x140038886  mov     r13d, eax
0x140038889  lea     r12, [r15+0B0h]
0x140038890  mov     rcx, [r12]
0x140038894  mov     rax, [rcx+10h]
0x140038898  mov     rcx, r12
0x14003889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400388a0  test    r13d, r13d
0x1400388a3  jns     short loc_140038904
0x1400388a5  test    rax, rax
0x1400388a8  jz      loc_140038C16
0x1400388ae  mov     rax, [r12]
0x1400388b2  mov     rcx, r12
0x1400388b5  mov     rax, [rax+10h]
0x1400388b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400388be  xor     edi, edi
0x1400388c0  test    rax, rax
0x1400388c3  jz      short loc_1400388F8
0x1400388c5  mov     dword ptr [rsp+60h+lpThreadId], r13d
0x1400388ca  mov     [rsp+60h+dwCreationFlags], 0CB1h
0x1400388d2  lea     r9, aCdlptaskExecut_2; "CDlpTask::ExecuteTransfer"
0x1400388d9  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1400388e0  lea     edx, [rdi+4]
0x1400388e3  mov     rcx, rax
0x1400388e6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1400388eb  mov     edi, eax
0x1400388ed  test    eax, eax
0x1400388ef  jns     short loc_1400388F8
0x1400388f1  mov     ecx, eax
0x1400388f3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400388f8  mov     ecx, edi
0x1400388fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400388ff  jmp     loc_140038C16
0x140038904  test    rax, rax
0x140038907  jz      short loc_140038937
0x140038909  mov     edi, [r15+59Ch]
0x140038910  mov     rax, [r12]
0x140038914  mov     rcx, r12
0x140038917  mov     rax, [rax+10h]
0x14003891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038920  mov     r9d, edi
0x140038923  lea     r8, aTransferExecut; "Transfer execution thread timeout perio"...
0x14003892a  mov     edx, 2
0x14003892f  mov     rcx, rax
0x140038932  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140038937  mov     edx, [r15+59Ch]; dwMilliseconds
0x14003893e  mov     rcx, rsi; hHandle
0x140038941  call    cs:__imp_WaitForSingleObject
0x140038948  nop     dword ptr [rax+rax+00h]
0x14003894d  test    eax, eax
0x14003894f  jz      loc_140038A83
0x140038955  cmp     eax, 102h
0x14003895a  jnz     short loc_1400389B9
0x14003895c  xor     edx, edx; unsigned int
0x14003895e  mov     rcx, r15; this
0x140038961  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x140038966  mov     r14d, eax
0x140038969  test    eax, eax
0x14003896b  jns     short loc_140038937
0x14003896d  mov     rax, [r15+0B0h]
0x140038974  mov     rcx, r12
0x140038977  mov     rax, [rax+10h]
0x14003897b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038980  test    rax, rax
0x140038983  jz      loc_140038C04
0x140038989  mov     rax, [r15+0B0h]
0x140038990  mov     rcx, r12
0x140038993  mov     rax, [rax+10h]
0x140038997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003899c  xor     edi, edi
0x14003899e  test    rax, rax
0x1400389a1  jz      loc_140038BFD
0x1400389a7  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x1400389ac  mov     [rsp+60h+dwCreationFlags], 0CC7h
0x1400389b4  jmp     loc_140038BD5
0x1400389b9  cmp     eax, 0FFFFFFFFh
0x1400389bc  jz      short loc_140038A10
0x1400389be  mov     r14d, 8000FFFFh
0x1400389c4  mov     rax, [r15+0B0h]
0x1400389cb  mov     rcx, r12
0x1400389ce  mov     rax, [rax+10h]
0x1400389d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400389d7  test    rax, rax
0x1400389da  jz      loc_140038C04
0x1400389e0  mov     rax, [r15+0B0h]
0x1400389e7  mov     rcx, r12
0x1400389ea  mov     rax, [rax+10h]
0x1400389ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400389f3  xor     edi, edi
0x1400389f5  test    rax, rax
0x1400389f8  jz      loc_140038BFD
0x1400389fe  mov     dword ptr [rsp+60h+lpThreadId], r14d
0x140038a03  mov     [rsp+60h+dwCreationFlags], 0CCFh
0x140038a0b  jmp     loc_140038BD5
0x140038a10  call    cs:__imp_GetLastError
0x140038a17  nop     dword ptr [rax+rax+00h]
0x140038a1c  mov     r14d, eax
0x140038a1f  test    eax, eax
0x140038a21  jle     short loc_140038A2E
0x140038a23  movzx   r14d, ax
0x140038a27  or      r14d, 80070000h
0x140038a2e  test    r14d, r14d
0x140038a31  jns     loc_140038C04
0x140038a37  mov     rax, [r15+0B0h]
  ... truncated ...
```
