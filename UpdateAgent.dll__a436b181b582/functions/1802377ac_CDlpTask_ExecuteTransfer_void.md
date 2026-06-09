# CDlpTask::ExecuteTransfer(void)

- ea: `0x1802377ac`
- end: `0x180237f8e`
- name: `?ExecuteTransfer@CDlpTask@@AEAAJXZ`
- size: `2018`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1802349e0`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x18022a80c`
- `0x180233cf0`
- `0x1802377ac`
- `0x180245754`
- `0x180247474`
- `0x18024bde4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180237b53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180237e55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180237b53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180237e55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802379ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180237c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180237cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802379ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180237c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180237cac`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180237c9c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180237c9c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1802379eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1802379eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180237a7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180237a7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18023788d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18023788d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180237f61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180237f61`

## string_xrefs

- `0x18023784e`: `CDlpTask::ExecuteTransfer`
- `0x180237dde`: `CDlpTask::ExecuteTransfer`
- `0x180237b35`: `Transfer execution thread timeout period: [%d ms]`
- `0x180237e3e`: `Waiting for transfer thread to exit.`
- `0x180237e8f`: `Transfer thread has exited.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ExecuteTransfer(union _ULARGE_INTEGER *this)
{
  HANDLE Thread; // rbx
  signed int v3; // r14d
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  signed int LastError; // eax
  ULONGLONG v9; // rax
  union _ULARGE_INTEGER *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  DWORD HighPart; // edi
  __int64 v15; // rax
  DWORD v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  bool v19; // sf
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-39h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-31h]
  union _ULARGE_INTEGER v27; // [rsp+40h] [rbp-19h] BYREF
  DWORD ExitCode; // [rsp+48h] [rbp-11h] BYREF
  signed int v29; // [rsp+4Ch] [rbp-Dh] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-9h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-1h] BYREF
  union _ULARGE_INTEGER v32; // [rsp+60h] [rbp+7h]
  __int64 v33; // [rsp+68h] [rbp+Fh]

  v33 = -2;
  Thread = 0;
  ExitCode = 0;
  v29 = 0;
  SystemTimeAsFileTime = 0;
  v30 = 0;
  v27.QuadPart = 0;
  v3 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *, unsigned __int64 *, union _ULARGE_INTEGER *))(this->QuadPart + 224))(
         this,
         &v30,
         &v27);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
      goto LABEL_80;
    v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
    v5 = 0;
    if ( !v4 )
      goto LABEL_7;
    LODWORD(lpThreadId) = v3;
    dwCreationFlags[0] = 3218;
    goto LABEL_5;
  }
  this[181] = v27;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v32 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
  v3 = CProgressData::Set((CProgressData *)&this[117], (union _ULARGE_INTEGER)SystemTimeAsFileTime, v27);
  if ( v3 >= 0 )
  {
    v3 = CProgressList::Reset((CProgressList *)&this[127]);
    if ( v3 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        goto LABEL_80;
      v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
      v5 = 0;
      if ( !v4 )
        goto LABEL_7;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3228;
      goto LABEL_5;
    }
    v3 = CProgressList::AddItem((CProgressList *)&this[127], (struct CProgressData *)&this[117]);
    if ( v3 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        goto LABEL_80;
      v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
      v5 = 0;
      if ( !v4 )
        goto LABEL_7;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3229;
      goto LABEL_5;
    }
    Thread = CreateThread(0, 0, CDlpTask::ExecuteTransferThreadProc, this, 0, 0);
    if ( !Thread )
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
      if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        goto LABEL_80;
      v4 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
      v5 = 0;
      if ( v3 >= 0 || !v4 )
        goto LABEL_7;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3239;
LABEL_5:
      v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v4,
             4,
             L"%s(%d): Result = 0x%X",
             L"CDlpTask::ExecuteTransfer",
             *(_QWORD *)dwCreationFlags,
             lpThreadId);
      v5 = (unsigned int)v6;
      if ( v6 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6, v7);
      goto LABEL_7;
    }
    this[180].HighPart = GetTickCount();
    this[182].QuadPart = 0;
    if ( v30 )
      v9 = 100 * v27.QuadPart / v30;
    else
      v9 = 0;
    this[183].QuadPart = v9;
    v3 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 1u);
    v10 = this + 22;
    v11 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
    if ( v3 >= 0 )
    {
      if ( v11 )
      {
        HighPart = this[179].HighPart;
        v15 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v10->QuadPart + 16))(this + 22);
        CDlpLogT<CEmptyType>::DlpLogFormat(v15, 2, L"Transfer execution thread timeout period: [%d ms]", HighPart);
      }
      while ( 1 )
      {
        v16 = WaitForSingleObject(Thread, this[179].HighPart);
        if ( !v16 )
          break;
        if ( v16 != 258 )
        {
          if ( v16 != -1 )
          {
            v3 = -2147418113;
            if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
              goto LABEL_76;
            v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
            v13 = 0;
            if ( v12 )
            {
              LODWORD(lpThreadId) = -2147418113;
              dwCreationFlags[0] = 3279;
              goto LABEL_73;
            }
            goto LABEL_75;
          }
          v17 = GetLastError();
          v3 = v17;
          if ( v17 > 0 )
            v3 = (unsigned __int16)v17 | 0x80070000;
          if ( v3 >= 0 || !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
            goto LABEL_76;
          v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
          v13 = 0;
          if ( !v12 )
            goto LABEL_75;
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3274;
          goto LABEL_73;
        }
        v3 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 0);
        if ( v3 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
            goto LABEL_76;
          v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
          v13 = 0;
          if ( v12 )
          {
            LODWORD(lpThreadId) = v3;
            dwCreationFlags[0] = 3271;
            goto LABEL_73;
          }
          goto LABEL_75;
        }
      }
      if ( !GetExitCodeThread(Thread, &ExitCode) )
      {
        v18 = GetLastError();
        v3 = v18;
        if ( v18 )
        {
          if ( v18 > 0 )
            v3 = (unsigned __int16)v18 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
          goto LABEL_76;
        v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
        v13 = 0;
        if ( v3 < 0 && v12 )
        {
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3262;
          goto LABEL_73;
        }
        goto LABEL_75;
      }
      v3 = CDlpTask::ProgressHandlerTransfer((CDlpTask *)this, 2u);
      if ( v3 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
          goto LABEL_76;
        v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
        v13 = 0;
        if ( v12 )
        {
          LODWORD(lpThreadId) = v3;
          dwCreationFlags[0] = 3266;
          goto LABEL_73;
        }
        goto LABEL_75;
      }
      v3 = ExitCode;
      v19 = (ExitCode & 0x80000000) != 0;
      if ( (int)ExitCode > 0 )
      {
        v3 = (unsigned __int16)ExitCode | 0x80070000;
        v19 = 1;
      }
      if ( !v19 || !(*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        goto LABEL_76;
      v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
      v13 = 0;
      if ( !v12 )
        goto LABEL_75;
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3267;
    }
    else
    {
      if ( !v11 )
      {
LABEL_76:
        if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        {
          v22 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
          CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2, L"Waiting for transfer thread to exit.");
        }
        WaitForSingleObject(Thread, 0xFFFFFFFF);
        if ( (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22) )
        {
          v23 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(this[22].QuadPart + 16))(this + 22);
          CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"Transfer thread has exited.");
        }
        goto LABEL_80;
      }
      v12 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *))(v10->QuadPart + 16))(this + 22);
      v13 = 0;
      if ( !v12 )
      {
LABEL_75:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
        goto LABEL_76;
      }
      LODWORD(lpThreadId) = v3;
      dwCreationFlags[0] = 3249;
    }
LABEL_73:
    v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v12,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::ExecuteTransfer",
            *(_QWORD *)dwCreationFlags,
            lpThreadId);
    v13 = (unsigned int)v20;
    if ( v20 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20, v21);
    goto LABEL_75;
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
LABEL_80:
  if ( (*(int (__fastcall **)(union _ULARGE_INTEGER *, unsigned __int64 *, union _ULARGE_INTEGER *))(this->QuadPart + 224))(
         this,
         &v30,
         &v27) >= 0 )
  {
    (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, __int64, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, _DWORD))this[2].QuadPart)(
      this + 2,
      4099,
      1,
      &v27,
      this + 186,
      0);
    (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, __int64, unsigned __int64 *, union _ULARGE_INTEGER *, _DWORD))this[2].QuadPart)(
      this + 2,
      4100,
      1,
      &v30,
      this + 186,
      0);
  }
  v29 = v3;
  (*(void (__fastcall **)(union _ULARGE_INTEGER *, __int64, _QWORD, signed int *, union _ULARGE_INTEGER *, _DWORD))this[2].QuadPart)(
    this + 2,
    4103,
    0,
    &v29,
    this + 186,
    0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( Thread )
    CloseHandle(Thread);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802377ac  push    rbp
0x1802377ae  push    rbx
0x1802377af  push    rsi
0x1802377b0  push    rdi
0x1802377b1  push    r14
0x1802377b3  push    r15
0x1802377b5  lea     rbp, [rsp-2Fh]
0x1802377ba  sub     rsp, 88h
0x1802377c1  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x1802377c9  mov     rax, cs:__security_cookie
0x1802377d0  xor     rax, rsp
0x1802377d3  mov     [rbp+57h+var_40], rax
0x1802377d7  mov     r15, rcx
0x1802377da  xor     ebx, ebx
0x1802377dc  mov     [rbp+57h+ExitCode], ebx
0x1802377df  mov     [rbp+57h+var_64], ebx
0x1802377e2  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1802377e6  mov     [rbp+57h+var_60], rbx
0x1802377ea  mov     qword ptr [rbp+57h+var_70], rbx
0x1802377ee  mov     rax, [rcx]
0x1802377f1  lea     r8, [rbp+57h+var_70]
0x1802377f5  lea     rdx, [rbp+57h+var_60]
0x1802377f9  mov     rax, [rax+0E0h]
0x180237800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237805  mov     r14d, eax
0x180237808  test    eax, eax
0x18023780a  jns     short loc_18023787E
0x18023780c  lea     rdi, [r15+0B0h]
0x180237813  mov     rdx, [rdi]
0x180237816  mov     rcx, rdi
0x180237819  mov     rax, [rdx+10h]
0x18023781d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237822  test    rax, rax
0x180237825  jz      loc_180237EA0
0x18023782b  mov     rax, [rdi]
0x18023782e  mov     rcx, rdi
0x180237831  mov     rax, [rax+10h]
0x180237835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023783a  xor     ecx, ecx
0x18023783c  test    rax, rax
0x18023783f  jz      short loc_180237874
0x180237841  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237846  mov     [rsp+0B0h+dwCreationFlags], 0C92h
0x18023784e  lea     r9, aCdlptaskExecut_2; "CDlpTask::ExecuteTransfer"
0x180237855  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18023785c  mov     edx, 4
0x180237861  mov     rcx, rax
0x180237864  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180237869  test    eax, eax
0x18023786b  mov     ecx, eax
0x18023786d  jns     short loc_180237874
0x18023786f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180237874  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180237879  jmp     loc_180237EA0
0x18023787e  mov     rax, qword ptr [rbp+57h+var_70]
0x180237882  mov     [r15+5A8h], rax
0x180237889  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18023788d  call    cs:__imp_GetSystemTimeAsFileTime
0x180237894  nop     dword ptr [rax+rax+00h]
0x180237899  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x18023789c  mov     dword ptr [rbp+57h+var_50+4], eax
0x18023789f  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1802378a2  mov     dword ptr [rbp+57h+var_50], eax
0x1802378a5  lea     rsi, [r15+3A8h]
0x1802378ac  mov     r8, qword ptr [rbp+57h+var_70]; union _ULARGE_INTEGER
0x1802378b0  mov     rdx, qword ptr [rbp+57h+var_50]; union _ULARGE_INTEGER
0x1802378b4  mov     rcx, rsi; this
0x1802378b7  call    ?Set@CProgressData@@QEAAJT_ULARGE_INTEGER@@0@Z; CProgressData::Set(_ULARGE_INTEGER,_ULARGE_INTEGER)
0x1802378bc  mov     r14d, eax
0x1802378bf  test    eax, eax
0x1802378c1  jns     short loc_18023790E
0x1802378c3  lea     rdi, [r15+0B0h]
0x1802378ca  mov     rax, [rdi]
0x1802378cd  mov     rcx, rdi
0x1802378d0  mov     rax, [rax+10h]
0x1802378d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802378d9  test    rax, rax
0x1802378dc  jz      loc_180237EA0
0x1802378e2  mov     rax, [rdi]
0x1802378e5  mov     rcx, rdi
0x1802378e8  mov     rax, [rax+10h]
0x1802378ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802378f1  xor     ecx, ecx
0x1802378f3  test    rax, rax
0x1802378f6  jz      loc_180237874
0x1802378fc  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237901  mov     [rsp+0B0h+dwCreationFlags], 0C98h
0x180237909  jmp     loc_18023784E
0x18023790e  lea     rdi, [r15+3F8h]
0x180237915  mov     rcx, rdi; this
0x180237918  call    ?Reset@CProgressList@@QEAAJXZ; CProgressList::Reset(void)
0x18023791d  mov     r14d, eax
0x180237920  test    eax, eax
0x180237922  jns     short loc_18023796F
0x180237924  lea     rdi, [r15+0B0h]
0x18023792b  mov     rax, [rdi]
0x18023792e  mov     rcx, rdi
0x180237931  mov     rax, [rax+10h]
0x180237935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023793a  test    rax, rax
0x18023793d  jz      loc_180237EA0
0x180237943  mov     rax, [rdi]
0x180237946  mov     rcx, rdi
0x180237949  mov     rax, [rax+10h]
0x18023794d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237952  xor     ecx, ecx
0x180237954  test    rax, rax
0x180237957  jz      loc_180237874
0x18023795d  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237962  mov     [rsp+0B0h+dwCreationFlags], 0C9Ch
0x18023796a  jmp     loc_18023784E
0x18023796f  mov     rdx, rsi; struct CProgressData *
0x180237972  mov     rcx, rdi; this
0x180237975  call    ?AddItem@CProgressList@@QEAAJPEAVCProgressData@@@Z; CProgressList::AddItem(CProgressData *)
0x18023797a  mov     r14d, eax
0x18023797d  test    eax, eax
0x18023797f  jns     short loc_1802379CC
0x180237981  lea     rdi, [r15+0B0h]
0x180237988  mov     rax, [rdi]
0x18023798b  mov     rcx, rdi
0x18023798e  mov     rax, [rax+10h]
0x180237992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237997  test    rax, rax
0x18023799a  jz      loc_180237EA0
0x1802379a0  mov     rax, [rdi]
0x1802379a3  mov     rcx, rdi
0x1802379a6  mov     rax, [rax+10h]
0x1802379aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802379af  xor     ecx, ecx
0x1802379b1  test    rax, rax
0x1802379b4  jz      loc_180237874
0x1802379ba  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x1802379bf  mov     [rsp+0B0h+dwCreationFlags], 0C9Dh
0x1802379c7  jmp     loc_18023784E
0x1802379cc  mov     [rsp+0B0h+lpThreadId], 0; lpThreadId
0x1802379d5  mov     [rsp+0B0h+dwCreationFlags], 0; dwCreationFlags
0x1802379dd  mov     r9, r15; lpParameter
0x1802379e0  lea     r8, ?ExecuteTransferThreadProc@CDlpTask@@SAKPEAX@Z; lpStartAddress
0x1802379e7  xor     edx, edx; dwStackSize
0x1802379e9  xor     ecx, ecx; lpThreadAttributes
0x1802379eb  call    cs:__imp_CreateThread
0x1802379f2  nop     dword ptr [rax+rax+00h]
0x1802379f7  mov     rbx, rax
0x1802379fa  test    rax, rax
0x1802379fd  jnz     short loc_180237A7B
0x1802379ff  call    cs:__imp_GetLastError
0x180237a06  nop     dword ptr [rax+rax+00h]
0x180237a0b  mov     r14d, eax
0x180237a0e  test    eax, eax
0x180237a10  jnz     short loc_180237A1A
0x180237a12  mov     r14d, 80004005h
0x180237a18  jmp     short loc_180237A27
0x180237a1a  jle     short loc_180237A27
0x180237a1c  movzx   r14d, ax
0x180237a20  or      r14d, 80070000h
0x180237a27  lea     rdi, [r15+0B0h]
0x180237a2e  mov     rax, [rdi]
0x180237a31  mov     rcx, rdi
0x180237a34  mov     rax, [rax+10h]
0x180237a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237a3d  test    rax, rax
0x180237a40  jz      loc_180237EA0
0x180237a46  mov     rax, [rdi]
0x180237a49  mov     rcx, rdi
0x180237a4c  mov     rax, [rax+10h]
0x180237a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237a55  xor     ecx, ecx
0x180237a57  test    r14d, r14d
0x180237a5a  jns     loc_180237874
0x180237a60  test    rax, rax
0x180237a63  jz      loc_180237874
0x180237a69  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237a6e  mov     [rsp+0B0h+dwCreationFlags], 0CA7h
0x180237a76  jmp     loc_18023784E
0x180237a7b  call    cs:__imp_GetTickCount
0x180237a82  nop     dword ptr [rax+rax+00h]
0x180237a87  mov     [r15+5A4h], eax
0x180237a8e  mov     qword ptr [r15+5B0h], 0
0x180237a99  mov     rcx, [rbp+57h+var_60]
0x180237a9d  test    rcx, rcx
0x180237aa0  jz      short loc_180237AAE
0x180237aa2  imul    rax, qword ptr [rbp+57h+var_70], 64h ; 'd'
0x180237aa7  xor     edx, edx
0x180237aa9  div     rcx
0x180237aac  jmp     short loc_180237AB0
0x180237aae  xor     eax, eax
0x180237ab0  mov     [r15+5B8h], rax
0x180237ab7  mov     edx, 1; unsigned int
0x180237abc  mov     rcx, r15; this
0x180237abf  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x180237ac4  mov     r14d, eax
0x180237ac7  lea     rsi, [r15+0B0h]
0x180237ace  mov     rax, [rsi]
0x180237ad1  mov     rax, [rax+10h]
0x180237ad5  mov     rcx, rsi
0x180237ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237add  test    r14d, r14d
0x180237ae0  jns     short loc_180237B17
0x180237ae2  test    rax, rax
0x180237ae5  jz      loc_180237E09
0x180237aeb  mov     rax, [rsi]
0x180237aee  mov     rcx, rsi
0x180237af1  mov     rax, [rax+10h]
0x180237af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237afa  xor     ecx, ecx
0x180237afc  test    rax, rax
0x180237aff  jz      loc_180237E04
0x180237b05  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237b0a  mov     [rsp+0B0h+dwCreationFlags], 0CB1h
0x180237b12  jmp     loc_180237DDE
0x180237b17  test    rax, rax
0x180237b1a  jz      short loc_180237B49
0x180237b1c  mov     edi, [r15+59Ch]
0x180237b23  mov     rax, [rsi]
0x180237b26  mov     rcx, rsi
0x180237b29  mov     rax, [rax+10h]
0x180237b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237b32  mov     r9d, edi
0x180237b35  lea     r8, aTransferExecut; "Transfer execution thread timeout perio"...
0x180237b3c  mov     edx, 2
0x180237b41  mov     rcx, rax
0x180237b44  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180237b49  mov     edx, [r15+59Ch]; dwMilliseconds
0x180237b50  mov     rcx, rbx; hHandle
0x180237b53  call    cs:__imp_WaitForSingleObject
0x180237b5a  nop     dword ptr [rax+rax+00h]
0x180237b5f  test    eax, eax
0x180237b61  jz      loc_180237C95
0x180237b67  cmp     eax, 102h
0x180237b6c  jnz     short loc_180237BCB
0x180237b6e  xor     edx, edx; unsigned int
0x180237b70  mov     rcx, r15; this
0x180237b73  call    ?ProgressHandlerTransfer@CDlpTask@@AEAAJK@Z; CDlpTask::ProgressHandlerTransfer(ulong)
0x180237b78  mov     r14d, eax
0x180237b7b  test    eax, eax
0x180237b7d  jns     short loc_180237B49
0x180237b7f  mov     rax, [r15+0B0h]
0x180237b86  mov     rcx, rsi
0x180237b89  mov     rax, [rax+10h]
0x180237b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237b92  test    rax, rax
0x180237b95  jz      loc_180237E09
0x180237b9b  mov     rax, [r15+0B0h]
0x180237ba2  mov     rcx, rsi
0x180237ba5  mov     rax, [rax+10h]
0x180237ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237bae  xor     ecx, ecx
0x180237bb0  test    rax, rax
0x180237bb3  jz      loc_180237E04
0x180237bb9  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237bbe  mov     [rsp+0B0h+dwCreationFlags], 0CC7h
0x180237bc6  jmp     loc_180237DDE
0x180237bcb  cmp     eax, 0FFFFFFFFh
0x180237bce  jz      short loc_180237C22
0x180237bd0  mov     r14d, 8000FFFFh
0x180237bd6  mov     rax, [r15+0B0h]
0x180237bdd  mov     rcx, rsi
0x180237be0  mov     rax, [rax+10h]
0x180237be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237be9  test    rax, rax
0x180237bec  jz      loc_180237E09
0x180237bf2  mov     rax, [r15+0B0h]
0x180237bf9  mov     rcx, rsi
0x180237bfc  mov     rax, [rax+10h]
0x180237c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237c05  xor     ecx, ecx
0x180237c07  test    rax, rax
0x180237c0a  jz      loc_180237E04
0x180237c10  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237c15  mov     [rsp+0B0h+dwCreationFlags], 0CCFh
0x180237c1d  jmp     loc_180237DDE
0x180237c22  call    cs:__imp_GetLastError
0x180237c29  nop     dword ptr [rax+rax+00h]
0x180237c2e  mov     r14d, eax
0x180237c31  test    eax, eax
0x180237c33  jle     short loc_180237C40
0x180237c35  movzx   r14d, ax
0x180237c39  or      r14d, 80070000h
0x180237c40  test    r14d, r14d
0x180237c43  jns     loc_180237E09
0x180237c49  mov     rax, [r15+0B0h]
0x180237c50  mov     rcx, rsi
0x180237c53  mov     rax, [rax+10h]
0x180237c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237c5c  test    rax, rax
0x180237c5f  jz      loc_180237E09
0x180237c65  mov     rax, [r15+0B0h]
0x180237c6c  mov     rcx, rsi
0x180237c6f  mov     rax, [rax+10h]
0x180237c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237c78  xor     ecx, ecx
0x180237c7a  test    rax, rax
0x180237c7d  jz      loc_180237E04
0x180237c83  mov     dword ptr [rsp+0B0h+lpThreadId], r14d
0x180237c88  mov     [rsp+0B0h+dwCreationFlags], 0CCAh
0x180237c90  jmp     loc_180237DDE
0x180237c95  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x180237c99  mov     rcx, rbx; hThread
0x180237c9c  call    cs:__imp_GetExitCodeThread
0x180237ca3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
