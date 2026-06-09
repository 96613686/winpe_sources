# CMFPresentationClock::GetTimeInternal(__int64 *,__int64 *)

- ea: `0x18007a2d0`
- end: `0x18007a8ba`
- name: `?GetTimeInternal@CMFPresentationClock@@IEAAJPEA_J0@Z`
- size: `1514`
- prototype: `__int64 __fastcall(CMFPresentationClock *__hidden this, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18007a0e0`

## callees

- `0x18001616c`
- `0x18001b9b0`
- `0x18002fee0`
- `0x180031c00`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d16c`
- `0x180050d6c`
- `0x18007a2d0`
- `0x1800ec0e0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a87a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a87a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007a3d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007a3d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007a42c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007a42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a71c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a71c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a37f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a78a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a37f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a78a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a32c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a623`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a732`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a32c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a623`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a3b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a40d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a4f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a3b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a40d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007a4f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a5a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a5a3`

## pseudocode

```c
__int64 __fastcall CMFPresentationClock::GetTimeInternal(CMFPresentationClock *this, __int64 *a2, __int64 *a3)
{
  CallStackTracing *v3; // rdi
  char *v5; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  CallStackTracing *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  int v13; // edi
  __int64 v14; // r13
  __int64 v15; // r12
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v17; // rcx
  int v18; // ebp
  __int64 v19; // rcx
  __int64 v20; // rdx
  DWORD v21; // edi
  int v22; // eax
  __int64 v23; // rdx
  const char *v24; // rcx
  __int64 v25; // r8
  __int64 *v26; // rdi
  CallStackTracing *v27; // rax
  __int64 *v28; // r14
  DWORD v29; // r12d
  __int64 *v30; // rax
  CallStackTracing *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  CallStackContext *v35; // r14
  DWORD v36; // eax
  DWORD v37; // ecx
  CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  int v42; // eax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v44; // eax
  __int64 v46[3]; // [rsp+30h] [rbp-58h] BYREF
  DWORD dwErrCode; // [rsp+90h] [rbp+8h] BYREF
  __int64 *v48; // [rsp+98h] [rbp+10h]
  __int64 *v49; // [rsp+A0h] [rbp+18h]
  __int64 v50; // [rsp+A8h] [rbp+20h] BYREF

  v49 = a3;
  v48 = a2;
  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v5 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v8 = CallStackTracing::s_wpInstance;
      }
      v9 = (**(__int64 (__fastcall ***)(CallStackTracing *))v8)(v8);
      if ( v9 )
        v5 = (char *)v9;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v5 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v5[8 * v11] = "CMFPresentationClock::GetTimeInternal";
      *(_DWORD *)&v5[8 * v11 + 8] = 2081;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( *((_DWORD *)this + 18) == GetCurrentThreadId() )
    ++*((_DWORD *)this + 19);
  else
    AcquireSRWLockShared((PSRWLOCK)this + 8);
  v12 = *((_QWORD *)this + 10);
  v13 = *((_DWORD *)this + 152);
  v14 = *((_QWORD *)this + 77);
  v15 = *((_QWORD *)this + 78);
  if ( v12 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*((_QWORD *)this + 10));
  CurrentThreadId = GetCurrentThreadId();
  v17 = (CMFPresentationClock *)((char *)this + 64);
  if ( *((_DWORD *)this + 18) == CurrentThreadId )
    CMFSRWLock::UnlockExclusive(v17);
  else
    ReleaseSRWLockShared((PSRWLOCK)v17);
  if ( v12 )
  {
    v46[0] = 0;
    v50 = 0;
    if ( v13 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&dwErrCode,
        "CMFPresentationClock::GetClockTime",
        2024);
      if ( (unsigned __int8)byte_1803CECE9 < 0x20u )
      {
LABEL_28:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&dwErrCode);
        v18 = 0;
        goto LABEL_29;
      }
      v19 = (unsigned __int128)(v14 * (__int128)0x346DC5D63886594BLL) >> 64;
      v20 = 77;
LABEL_27:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v20,
        &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids,
        v12,
        ((unsigned __int64)v19 >> 63) + (v19 >> 11));
      goto LABEL_28;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v12 + 32LL))(v12, 0, &v50, v46);
    v18 = v22;
    if ( v22 >= 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = v26 + 26;
        v29 = GetLastError();
        v30 = (__int64 *)TlsGetValue(*((_DWORD *)v26 + 3));
        if ( v30 )
        {
          v28 = v30;
        }
        else if ( !GetLastError() )
        {
          v31 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v31 = CallStackTracing::s_wpInstance;
          }
          v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
          if ( v32 )
            v28 = (__int64 *)v32;
        }
        SetLastError(v29);
        v33 = *((unsigned int *)v28 + 497);
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( (unsigned int)v33 < *((_DWORD *)v28 + 498) )
        {
          v34 = 2 * v33;
          v24 = "CMFPresentationClock::GetClockTime";
          v28[v34] = (__int64)"CMFPresentationClock::GetClockTime";
          LODWORD(v28[v34 + 1]) = 2064;
        }
        ++*((_DWORD *)v28 + 497);
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
      {
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          79,
          &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids,
          v12,
          v50,
          v46[0]);
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      v14 = v50;
      v15 = v46[0];
      if ( *((_BYTE *)v26 + 8) )
      {
        v35 = (CallStackContext *)(v26 + 26);
        v36 = GetLastError();
        v37 = *((_DWORD *)v26 + 3);
        dwErrCode = v36;
        v38 = (CallStackContext *)TlsGetValue(v37);
        if ( v38 )
        {
          v35 = v38;
        }
        else if ( !GetLastError() )
        {
          v39 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v39 = CallStackTracing::s_wpInstance;
          }
          v40 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
          if ( v40 )
            v35 = (CallStackContext *)v40;
        }
        SetLastError(dwErrCode);
        v41 = *((_DWORD *)v35 + 497);
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v41 )
        {
          v42 = v41 - 1;
          *((_DWORD *)v35 + 497) = v42;
          if ( !v42 )
          {
            CallStackContext::ClearState(v35);
            goto LABEL_29;
          }
        }
      }
    }
    else
    {
      if ( v22 != -1072849853 )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&dwErrCode,
          "CMFPresentationClock::GetClockTime",
          2051);
        if ( (unsigned __int8)byte_1803CECE9 < 0x20u )
          goto LABEL_28;
        v19 = (unsigned __int128)(v14 * (__int128)0x346DC5D63886594BLL) >> 64;
        v20 = 78;
        goto LABEL_27;
      }
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    if ( v18 < 0 )
    {
      if ( !v26 )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v18 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPresentationClock::GetTimeInternal", 2102, v18);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids, this, v18);
      goto LABEL_81;
    }
LABEL_29:
    *v48 = v14;
    if ( v49 )
      *v49 = v15;
    v21 = GetCurrentThreadId();
    if ( *((_DWORD *)this + 18) == v21 )
    {
      ++*((_DWORD *)this + 19);
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 8);
      *((_DWORD *)this + 18) = v21;
    }
    if ( v15 >= *((_QWORD *)this + 78) )
    {
      *((_QWORD *)this + 77) = v14;
      *((_QWORD *)this + 78) = v15;
    }
    v44 = *((_DWORD *)this + 19);
    if ( v44 )
    {
      *((_DWORD *)this + 19) = v44 - 1;
    }
    else
    {
      *((_DWORD *)this + 18) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    }
LABEL_81:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_82;
  }
  v18 = -1072849855;
LABEL_82:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&dwErrCode);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18007a2d0  mov     [rsp+arg_10], r8
0x18007a2d5  mov     [rsp+arg_8], rdx
0x18007a2da  push    rbx
0x18007a2db  push    rbp
0x18007a2dc  push    rsi
0x18007a2dd  push    rdi
0x18007a2de  push    r12
0x18007a2e0  push    r13
0x18007a2e2  push    r15
0x18007a2e4  sub     rsp, 50h
0x18007a2e8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a2ef  mov     r15, rcx
0x18007a2f2  test    rdi, rdi
0x18007a2f5  jnz     short loc_18007A303
0x18007a2f7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007a2fc  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a303  cmp     byte ptr [rdi+8], 0
0x18007a307  lea     rcx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x18007a30e  jz      loc_18007A3B5
0x18007a314  lea     rbx, [rdi+0D0h]
0x18007a31b  call    cs:__imp_GetLastError
0x18007a322  nop     dword ptr [rax+rax+00h]
0x18007a327  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18007a32a  mov     esi, eax
0x18007a32c  call    cs:__imp_TlsGetValue
0x18007a333  nop     dword ptr [rax+rax+00h]
0x18007a338  test    rax, rax
0x18007a33b  jz      short loc_18007A342
0x18007a33d  mov     rbx, rax
0x18007a340  jmp     short loc_18007A37D
0x18007a342  call    cs:__imp_GetLastError
0x18007a349  nop     dword ptr [rax+rax+00h]
0x18007a34e  test    eax, eax
0x18007a350  jnz     short loc_18007A37D
0x18007a352  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a359  test    rcx, rcx
0x18007a35c  jnz     short loc_18007A36A
0x18007a35e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007a363  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a36a  mov     rax, [rcx]
0x18007a36d  mov     rax, [rax]
0x18007a370  call    cs:__guard_dispatch_icall_fptr
0x18007a376  test    rax, rax
0x18007a379  cmovnz  rbx, rax
0x18007a37d  mov     ecx, esi; dwErrCode
0x18007a37f  call    cs:__imp_SetLastError
0x18007a386  nop     dword ptr [rax+rax+00h]
0x18007a38b  mov     eax, [rbx+7C4h]
0x18007a391  lea     rcx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x18007a398  cmp     eax, [rbx+7C8h]
0x18007a39e  jnb     short loc_18007A3AF
0x18007a3a0  add     rax, rax
0x18007a3a3  mov     [rbx+rax*8], rcx
0x18007a3a7  mov     dword ptr [rbx+rax*8+8], 821h
0x18007a3af  inc     dword ptr [rbx+7C4h]
0x18007a3b5  call    cs:__imp_GetCurrentThreadId
0x18007a3bc  nop     dword ptr [rax+rax+00h]
0x18007a3c1  mov     ecx, [r15+48h]
0x18007a3c5  cmp     ecx, eax
0x18007a3c7  jnz     short loc_18007A3CF
0x18007a3c9  inc     dword ptr [r15+4Ch]
0x18007a3cd  jmp     short loc_18007A3DF
0x18007a3cf  lea     rcx, [r15+40h]; SRWLock
0x18007a3d3  call    cs:__imp_AcquireSRWLockShared
0x18007a3da  nop     dword ptr [rax+rax+00h]
0x18007a3df  mov     rbx, [r15+50h]
0x18007a3e3  mov     edi, [r15+260h]
0x18007a3ea  mov     r13, [r15+268h]
0x18007a3f1  mov     r12, [r15+270h]
0x18007a3f8  test    rbx, rbx
0x18007a3fb  jz      short loc_18007A40D
0x18007a3fd  mov     rax, [rbx]
0x18007a400  mov     rcx, rbx
0x18007a403  mov     rax, [rax+8]
0x18007a407  call    cs:__guard_dispatch_icall_fptr
0x18007a40d  call    cs:__imp_GetCurrentThreadId
0x18007a414  nop     dword ptr [rax+rax+00h]
0x18007a419  mov     ecx, [r15+48h]
0x18007a41d  cmp     ecx, eax
0x18007a41f  lea     rcx, [r15+40h]; this
0x18007a423  jnz     short loc_18007A42C
0x18007a425  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18007a42a  jmp     short loc_18007A438
0x18007a42c  call    cs:__imp_ReleaseSRWLockShared
0x18007a433  nop     dword ptr [rax+rax+00h]
0x18007a438  test    rbx, rbx
0x18007a43b  jnz     short loc_18007A447
0x18007a43d  mov     ebp, 0C00D9C41h
0x18007a442  jmp     loc_18007A89B
0x18007a447  mov     [rsp+88h+var_40], r14
0x18007a44c  mov     [rsp+88h+var_58], 0
0x18007a455  mov     [rsp+88h+arg_18], 0
0x18007a461  test    edi, edi
0x18007a463  jz      loc_18007A51A
0x18007a469  mov     r8d, 7E8h; int
0x18007a46f  lea     rdx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x18007a476  lea     rcx, [rsp+88h+dwErrCode]; this
0x18007a47e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a483  cmp     cs:byte_1803CECE9, 20h ; ' '
0x18007a48a  jb      short loc_18007A4CD
0x18007a48c  mov     rax, 346DC5D63886594Bh
0x18007a496  imul    r13
0x18007a499  mov     rcx, rdx
0x18007a49c  mov     edx, 4Dh ; 'M'
0x18007a4a1  sar     rcx, 0Bh
0x18007a4a5  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x18007a4ac  mov     rax, rcx
0x18007a4af  mov     r9, rbx
0x18007a4b2  shr     rax, 3Fh
0x18007a4b6  add     rcx, rax
0x18007a4b9  mov     dword ptr [rsp+88h+var_68], ecx
0x18007a4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a4c4  mov     rcx, [rcx+38h]
0x18007a4c8  call    WPP_SF_qD
0x18007a4cd  lea     rcx, [rsp+88h+dwErrCode]; this
0x18007a4d5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007a4da  xor     ebp, ebp
0x18007a4dc  mov     rax, [rsp+88h+arg_8]
0x18007a4e4  mov     [rax], r13
0x18007a4e7  mov     rax, [rsp+88h+arg_10]
0x18007a4ef  test    rax, rax
0x18007a4f2  jz      short loc_18007A4F7
0x18007a4f4  mov     [rax], r12
0x18007a4f7  call    cs:__imp_GetCurrentThreadId
0x18007a4fe  nop     dword ptr [rax+rax+00h]
0x18007a503  mov     ecx, [r15+48h]
0x18007a507  mov     edi, eax
0x18007a509  cmp     ecx, eax
0x18007a50b  jnz     loc_18007A833
0x18007a511  inc     dword ptr [r15+4Ch]
0x18007a515  jmp     loc_18007A847
0x18007a51a  mov     rax, [rbx]
0x18007a51d  lea     r9, [rsp+88h+var_58]
0x18007a522  lea     r8, [rsp+88h+arg_18]
0x18007a52a  xor     edx, edx
0x18007a52c  mov     rcx, rbx
0x18007a52f  mov     rax, [rax+20h]
0x18007a533  call    cs:__guard_dispatch_icall_fptr
0x18007a539  mov     ebp, eax
0x18007a53b  test    eax, eax
0x18007a53d  jns     loc_18007A5E8
0x18007a543  cmp     eax, 0C00D9C43h
0x18007a548  jz      short loc_18007A58B
0x18007a54a  mov     r8d, 803h; int
0x18007a550  lea     rdx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x18007a557  lea     rcx, [rsp+88h+dwErrCode]; this
0x18007a55f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a564  cmp     cs:byte_1803CECE9, 20h ; ' '
0x18007a56b  jb      loc_18007A4CD
0x18007a571  mov     rax, 346DC5D63886594Bh
0x18007a57b  imul    r13
0x18007a57e  mov     rcx, rdx
0x18007a581  mov     edx, 4Eh ; 'N'
0x18007a586  jmp     loc_18007A4A1
0x18007a58b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a592  test    ebp, ebp
0x18007a594  jns     loc_18007A4DC
0x18007a59a  test    rdi, rdi
0x18007a59d  jnz     loc_18007A7D7
0x18007a5a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a5aa  nop     dword ptr [rax+rax+00h]
0x18007a5af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a5b6  mov     rcx, rax
0x18007a5b9  test    rax, rax
0x18007a5bc  jz      loc_18007A7C9
0x18007a5c2  mov     rax, [rax]
0x18007a5c5  mov     edx, 7F0h
0x18007a5ca  mov     rax, [rax+8]
0x18007a5ce  call    cs:__guard_dispatch_icall_fptr
0x18007a5d4  test    eax, eax
0x18007a5d6  jz      loc_18007A7C9
0x18007a5dc  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a5e3  jmp     loc_18007A7D7
0x18007a5e8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a5ef  test    rdi, rdi
0x18007a5f2  jnz     short loc_18007A600
0x18007a5f4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007a5f9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a600  cmp     byte ptr [rdi+8], 0
0x18007a604  jz      loc_18007A6B8
0x18007a60a  lea     r14, [rdi+0D0h]
0x18007a611  call    cs:__imp_GetLastError
0x18007a618  nop     dword ptr [rax+rax+00h]
0x18007a61d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18007a620  mov     r12d, eax
0x18007a623  call    cs:__imp_TlsGetValue
0x18007a62a  nop     dword ptr [rax+rax+00h]
0x18007a62f  test    rax, rax
0x18007a632  jz      short loc_18007A639
0x18007a634  mov     r14, rax
0x18007a637  jmp     short loc_18007A674
0x18007a639  call    cs:__imp_GetLastError
0x18007a640  nop     dword ptr [rax+rax+00h]
0x18007a645  test    eax, eax
0x18007a647  jnz     short loc_18007A674
0x18007a649  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a650  test    rcx, rcx
0x18007a653  jnz     short loc_18007A661
0x18007a655  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007a65a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a661  mov     rax, [rcx]
0x18007a664  mov     rax, [rax]
0x18007a667  call    cs:__guard_dispatch_icall_fptr
0x18007a66d  test    rax, rax
0x18007a670  cmovnz  r14, rax
0x18007a674  mov     ecx, r12d; dwErrCode
0x18007a677  call    cs:__imp_SetLastError
0x18007a67e  nop     dword ptr [rax+rax+00h]
0x18007a683  mov     eax, [r14+7C4h]
0x18007a68a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a691  cmp     eax, [r14+7C8h]
0x18007a698  jnb     short loc_18007A6B1
0x18007a69a  add     rax, rax
0x18007a69d  lea     rcx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x18007a6a4  mov     [r14+rax*8], rcx
0x18007a6a8  mov     dword ptr [r14+rax*8+8], 810h
0x18007a6b1  inc     dword ptr [r14+7C4h]
0x18007a6b8  cmp     cs:byte_1803CECE9, 20h ; ' '
0x18007a6bf  jb      short loc_18007A6FE
0x18007a6c1  mov     rax, [rsp+88h+var_58]
0x18007a6c6  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x18007a6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6d4  mov     edx, 4Fh ; 'O'
0x18007a6d9  mov     [rsp+88h+var_60], rax
0x18007a6de  mov     r9, rbx
0x18007a6e1  mov     rax, [rsp+88h+arg_18]
0x18007a6e9  mov     [rsp+88h+var_68], rax
0x18007a6ee  mov     rcx, [rcx+38h]
0x18007a6f2  call    WPP_SF_qqq
0x18007a6f7  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a6fe  cmp     byte ptr [rdi+8], 0
0x18007a702  mov     r13, [rsp+88h+arg_18]
0x18007a70a  mov     r12, [rsp+88h+var_58]
0x18007a70f  jz      loc_18007A592
0x18007a715  lea     r14, [rdi+0D0h]
0x18007a71c  call    cs:__imp_GetLastError
0x18007a723  nop     dword ptr [rax+rax+00h]
0x18007a728  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18007a72b  mov     [rsp+88h+dwErrCode], eax
0x18007a732  call    cs:__imp_TlsGetValue
0x18007a739  nop     dword ptr [rax+rax+00h]
0x18007a73e  test    rax, rax
0x18007a741  jz      short loc_18007A748
0x18007a743  mov     r14, rax
0x18007a746  jmp     short loc_18007A783
0x18007a748  call    cs:__imp_GetLastError
0x18007a74f  nop     dword ptr [rax+rax+00h]
0x18007a754  test    eax, eax
0x18007a756  jnz     short loc_18007A783
0x18007a758  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a75f  test    rcx, rcx
0x18007a762  jnz     short loc_18007A770
0x18007a764  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007a769  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a770  mov     rax, [rcx]
0x18007a773  mov     rax, [rax]
0x18007a776  call    cs:__guard_dispatch_icall_fptr
0x18007a77c  test    rax, rax
0x18007a77f  cmovnz  r14, rax
0x18007a783  mov     ecx, [rsp+88h+dwErrCode]; dwErrCode
0x18007a78a  call    cs:__imp_SetLastError
0x18007a791  nop     dword ptr [rax+rax+00h]
0x18007a796  mov     eax, [r14+7C4h]
0x18007a79d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a7a4  test    eax, eax
0x18007a7a6  jz      loc_18007A592
0x18007a7ac  sub     eax, 1
0x18007a7af  mov     [r14+7C4h], eax
0x18007a7b6  jnz     loc_18007A592
0x18007a7bc  mov     rcx, r14; this
0x18007a7bf  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18007a7c4  jmp     loc_18007A4DC
0x18007a7c9  lea     rdi, qword_1803CE250
0x18007a7d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a7d7  cmp     byte ptr [rdi+8], 0
0x18007a7db  jz      short loc_18007A805
0x18007a7dd  mov     rcx, rdi; this
0x18007a7e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a7e5  cmp     [rax+7CCh], ebp
0x18007a7eb  jz      short loc_18007A805
0x18007a7ed  mov     r9d, ebp; int
0x18007a7f0  lea     rdx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x18007a7f7  mov     r8d, 836h; int
0x18007a7fd  mov     rcx, rax; this
0x18007a800  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a805  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a80c  jb      short loc_18007A886
0x18007a80e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a815  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x18007a81c  mov     edx, 50h ; 'P'
0x18007a821  mov     dword ptr [rsp+88h+var_68], ebp
0x18007a825  mov     r9, r15
0x18007a828  mov     rcx, [rcx+10h]
0x18007a82c  call    WPP_SF_qD
0x18007a831  jmp     short loc_18007A886
0x18007a833  lea     rcx, [r15+40h]; SRWLock
0x18007a837  call    cs:__imp_AcquireSRWLockExclusive
0x18007a83e  nop     dword ptr [rax+rax+00h]
0x18007a843  mov     [r15+48h], edi
0x18007a847  cmp     r12, [r15+270h]
  ... truncated ...
```
