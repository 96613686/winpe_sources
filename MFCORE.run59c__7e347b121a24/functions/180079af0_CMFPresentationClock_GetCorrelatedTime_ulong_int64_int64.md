# CMFPresentationClock::GetCorrelatedTime(ulong,__int64 *,__int64 *)

- ea: `0x180079af0`
- end: `0x18007a0d4`
- name: `?GetCorrelatedTime@CMFPresentationClock@@UEAAJKPEA_J0@Z`
- size: `1508`
- prototype: `__int64 __fastcall(CMFPresentationClock *__hidden this, unsigned int, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18001616c`
- `0x18001b9b0`
- `0x18002fee0`
- `0x180031c00`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d16c`
- `0x180050d6c`
- `0x180079af0`
- `0x1800ec0e0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a091`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007a091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a04e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007a04e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180079bf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180079bf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180079c4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180079c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079e94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079fa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079e94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079fa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079b4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079e40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079f49`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079b4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079e40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079f49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079bd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079bd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079d17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079dc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079dc0`

## pseudocode

```c
__int64 __fastcall CMFPresentationClock::GetCorrelatedTime(
        CMFPresentationClock *this,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  CallStackTracing *v4; // rdi
  char *v6; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  CallStackTracing *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // edi
  __int64 v15; // r13
  __int64 v16; // r12
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v18; // rcx
  int v19; // ebp
  __int64 v20; // rcx
  __int64 v21; // rdx
  DWORD v22; // edi
  int v23; // eax
  __int64 v24; // rdx
  const char *v25; // rcx
  __int64 v26; // r8
  __int64 *v27; // rdi
  CallStackTracing *v28; // rax
  __int64 *v29; // r14
  DWORD v30; // r12d
  __int64 *v31; // rax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  CallStackContext *v36; // r14
  DWORD v37; // eax
  DWORD v38; // ecx
  CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  int v43; // eax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v45; // eax
  __int64 v47; // [rsp+30h] [rbp-48h] BYREF
  __int64 v48[8]; // [rsp+38h] [rbp-40h] BYREF
  DWORD dwErrCode; // [rsp+80h] [rbp+8h] BYREF
  __int64 *v50; // [rsp+90h] [rbp+18h]
  __int64 *v51; // [rsp+98h] [rbp+20h]

  v51 = a4;
  v50 = a3;
  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v6 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v6 = Value;
    }
    else if ( !GetLastError() )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v9 = CallStackTracing::s_wpInstance;
      }
      v10 = (**(__int64 (__fastcall ***)(CallStackTracing *))v9)(v9);
      if ( v10 )
        v6 = (char *)v10;
    }
    SetLastError(LastError);
    v11 = *((unsigned int *)v6 + 497);
    if ( (unsigned int)v11 < *((_DWORD *)v6 + 498) )
    {
      v12 = 2 * v11;
      *(_QWORD *)&v6[8 * v12] = "CMFPresentationClock::GetTimeInternal";
      *(_DWORD *)&v6[8 * v12 + 8] = 2081;
    }
    ++*((_DWORD *)v6 + 497);
  }
  if ( *((_DWORD *)this + 18) == GetCurrentThreadId() )
    ++*((_DWORD *)this + 19);
  else
    AcquireSRWLockShared((PSRWLOCK)this + 8);
  v13 = *((_QWORD *)this + 10);
  v14 = *((_DWORD *)this + 152);
  v15 = *((_QWORD *)this + 77);
  v16 = *((_QWORD *)this + 78);
  if ( v13 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*((_QWORD *)this + 10));
  CurrentThreadId = GetCurrentThreadId();
  v18 = (CMFPresentationClock *)((char *)this + 64);
  if ( *((_DWORD *)this + 18) == CurrentThreadId )
    CMFSRWLock::UnlockExclusive(v18);
  else
    ReleaseSRWLockShared((PSRWLOCK)v18);
  if ( v13 )
  {
    v48[0] = 0;
    v47 = 0;
    if ( v14 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&dwErrCode,
        "CMFPresentationClock::GetClockTime",
        2024);
      if ( (unsigned __int8)byte_1803CECE9 < 0x20u )
      {
LABEL_28:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&dwErrCode);
        v19 = 0;
        goto LABEL_29;
      }
      v20 = (unsigned __int128)(v15 * (__int128)0x346DC5D63886594BLL) >> 64;
      v21 = 77;
LABEL_27:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v21,
        &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids,
        v13,
        ((unsigned __int64)v20 >> 63) + (v20 >> 11));
      goto LABEL_28;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v13 + 32LL))(v13, 0, &v47, v48);
    v19 = v23;
    if ( v23 >= 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = v27 + 26;
        v30 = GetLastError();
        v31 = (__int64 *)TlsGetValue(*((_DWORD *)v27 + 3));
        if ( v31 )
        {
          v29 = v31;
        }
        else if ( !GetLastError() )
        {
          v32 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v32 = CallStackTracing::s_wpInstance;
          }
          v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
          if ( v33 )
            v29 = (__int64 *)v33;
        }
        SetLastError(v30);
        v34 = *((unsigned int *)v29 + 497);
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( (unsigned int)v34 < *((_DWORD *)v29 + 498) )
        {
          v35 = 2 * v34;
          v25 = "CMFPresentationClock::GetClockTime";
          v29[v35] = (__int64)"CMFPresentationClock::GetClockTime";
          LODWORD(v29[v35 + 1]) = 2064;
        }
        ++*((_DWORD *)v29 + 497);
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
      {
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          79,
          &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids,
          v13,
          v47,
          v48[0]);
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      v15 = v47;
      v16 = v48[0];
      if ( *((_BYTE *)v27 + 8) )
      {
        v36 = (CallStackContext *)(v27 + 26);
        v37 = GetLastError();
        v38 = *((_DWORD *)v27 + 3);
        dwErrCode = v37;
        v39 = (CallStackContext *)TlsGetValue(v38);
        if ( v39 )
        {
          v36 = v39;
        }
        else if ( !GetLastError() )
        {
          v40 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v40 = CallStackTracing::s_wpInstance;
          }
          v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
          if ( v41 )
            v36 = (CallStackContext *)v41;
        }
        SetLastError(dwErrCode);
        v42 = *((_DWORD *)v36 + 497);
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v42 )
        {
          v43 = v42 - 1;
          *((_DWORD *)v36 + 497) = v43;
          if ( !v43 )
          {
            CallStackContext::ClearState(v36);
            goto LABEL_29;
          }
        }
      }
    }
    else
    {
      if ( v23 != -1072849853 )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&dwErrCode,
          "CMFPresentationClock::GetClockTime",
          2051);
        if ( (unsigned __int8)byte_1803CECE9 < 0x20u )
          goto LABEL_28;
        v20 = (unsigned __int128)(v15 * (__int128)0x346DC5D63886594BLL) >> 64;
        v21 = 78;
        goto LABEL_27;
      }
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    if ( v19 < 0 )
    {
      if ( !v27 )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v19 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPresentationClock::GetTimeInternal", 2102, v19);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids, this, v19);
      goto LABEL_81;
    }
LABEL_29:
    *v50 = v15;
    if ( v51 )
      *v51 = v16;
    v22 = GetCurrentThreadId();
    if ( *((_DWORD *)this + 18) == v22 )
    {
      ++*((_DWORD *)this + 19);
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 8);
      *((_DWORD *)this + 18) = v22;
    }
    if ( v16 >= *((_QWORD *)this + 78) )
    {
      *((_QWORD *)this + 77) = v15;
      *((_QWORD *)this + 78) = v16;
    }
    v45 = *((_DWORD *)this + 19);
    if ( v45 )
    {
      *((_DWORD *)this + 19) = v45 - 1;
    }
    else
    {
      *((_DWORD *)this + 18) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    }
LABEL_81:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_82;
  }
  v19 = -1072849855;
LABEL_82:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&dwErrCode);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180079af0  mov     [rsp+arg_18], r9
0x180079af5  mov     [rsp+arg_10], r8
0x180079afa  push    rbx
0x180079afb  push    rbp
0x180079afc  push    rsi
0x180079afd  push    rdi
0x180079afe  push    r12
0x180079b00  push    r13
0x180079b02  push    r15
0x180079b04  sub     rsp, 40h
0x180079b08  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b0f  mov     r15, rcx
0x180079b12  test    rdi, rdi
0x180079b15  jnz     short loc_180079B23
0x180079b17  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180079b1c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b23  cmp     byte ptr [rdi+8], 0
0x180079b27  lea     rcx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x180079b2e  jz      loc_180079BD5
0x180079b34  lea     rbx, [rdi+0D0h]
0x180079b3b  call    cs:__imp_GetLastError
0x180079b42  nop     dword ptr [rax+rax+00h]
0x180079b47  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180079b4a  mov     esi, eax
0x180079b4c  call    cs:__imp_TlsGetValue
0x180079b53  nop     dword ptr [rax+rax+00h]
0x180079b58  test    rax, rax
0x180079b5b  jz      short loc_180079B62
0x180079b5d  mov     rbx, rax
0x180079b60  jmp     short loc_180079B9D
0x180079b62  call    cs:__imp_GetLastError
0x180079b69  nop     dword ptr [rax+rax+00h]
0x180079b6e  test    eax, eax
0x180079b70  jnz     short loc_180079B9D
0x180079b72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b79  test    rcx, rcx
0x180079b7c  jnz     short loc_180079B8A
0x180079b7e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180079b83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b8a  mov     rax, [rcx]
0x180079b8d  mov     rax, [rax]
0x180079b90  call    cs:__guard_dispatch_icall_fptr
0x180079b96  test    rax, rax
0x180079b99  cmovnz  rbx, rax
0x180079b9d  mov     ecx, esi; dwErrCode
0x180079b9f  call    cs:__imp_SetLastError
0x180079ba6  nop     dword ptr [rax+rax+00h]
0x180079bab  mov     eax, [rbx+7C4h]
0x180079bb1  lea     rcx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x180079bb8  cmp     eax, [rbx+7C8h]
0x180079bbe  jnb     short loc_180079BCF
0x180079bc0  add     rax, rax
0x180079bc3  mov     [rbx+rax*8], rcx
0x180079bc7  mov     dword ptr [rbx+rax*8+8], 821h
0x180079bcf  inc     dword ptr [rbx+7C4h]
0x180079bd5  call    cs:__imp_GetCurrentThreadId
0x180079bdc  nop     dword ptr [rax+rax+00h]
0x180079be1  mov     ecx, [r15+48h]
0x180079be5  cmp     ecx, eax
0x180079be7  jnz     short loc_180079BEF
0x180079be9  inc     dword ptr [r15+4Ch]
0x180079bed  jmp     short loc_180079BFF
0x180079bef  lea     rcx, [r15+40h]; SRWLock
0x180079bf3  call    cs:__imp_AcquireSRWLockShared
0x180079bfa  nop     dword ptr [rax+rax+00h]
0x180079bff  mov     rbx, [r15+50h]
0x180079c03  mov     edi, [r15+260h]
0x180079c0a  mov     r13, [r15+268h]
0x180079c11  mov     r12, [r15+270h]
0x180079c18  test    rbx, rbx
0x180079c1b  jz      short loc_180079C2D
0x180079c1d  mov     rax, [rbx]
0x180079c20  mov     rcx, rbx
0x180079c23  mov     rax, [rax+8]
0x180079c27  call    cs:__guard_dispatch_icall_fptr
0x180079c2d  call    cs:__imp_GetCurrentThreadId
0x180079c34  nop     dword ptr [rax+rax+00h]
0x180079c39  mov     ecx, [r15+48h]
0x180079c3d  cmp     ecx, eax
0x180079c3f  lea     rcx, [r15+40h]; this
0x180079c43  jnz     short loc_180079C4C
0x180079c45  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x180079c4a  jmp     short loc_180079C58
0x180079c4c  call    cs:__imp_ReleaseSRWLockShared
0x180079c53  nop     dword ptr [rax+rax+00h]
0x180079c58  test    rbx, rbx
0x180079c5b  jnz     short loc_180079C67
0x180079c5d  mov     ebp, 0C00D9C41h
0x180079c62  jmp     loc_18007A0B5
0x180079c67  mov     [rsp+78h+arg_8], r14
0x180079c6f  mov     [rsp+78h+var_40], 0
0x180079c78  mov     [rsp+78h+var_48], 0
0x180079c81  test    edi, edi
0x180079c83  jz      loc_180079D3A
0x180079c89  mov     r8d, 7E8h; int
0x180079c8f  lea     rdx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x180079c96  lea     rcx, [rsp+78h+dwErrCode]; this
0x180079c9e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180079ca3  cmp     cs:byte_1803CECE9, 20h ; ' '
0x180079caa  jb      short loc_180079CED
0x180079cac  mov     rax, 346DC5D63886594Bh
0x180079cb6  imul    r13
0x180079cb9  mov     rcx, rdx
0x180079cbc  mov     edx, 4Dh ; 'M'
0x180079cc1  sar     rcx, 0Bh
0x180079cc5  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x180079ccc  mov     rax, rcx
0x180079ccf  mov     r9, rbx
0x180079cd2  shr     rax, 3Fh
0x180079cd6  add     rcx, rax
0x180079cd9  mov     dword ptr [rsp+78h+var_58], ecx
0x180079cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ce4  mov     rcx, [rcx+38h]
0x180079ce8  call    WPP_SF_qD
0x180079ced  lea     rcx, [rsp+78h+dwErrCode]; this
0x180079cf5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180079cfa  xor     ebp, ebp
0x180079cfc  mov     rax, [rsp+78h+arg_10]
0x180079d04  mov     [rax], r13
0x180079d07  mov     rax, [rsp+78h+arg_18]
0x180079d0f  test    rax, rax
0x180079d12  jz      short loc_180079D17
0x180079d14  mov     [rax], r12
0x180079d17  call    cs:__imp_GetCurrentThreadId
0x180079d1e  nop     dword ptr [rax+rax+00h]
0x180079d23  mov     ecx, [r15+48h]
0x180079d27  mov     edi, eax
0x180079d29  cmp     ecx, eax
0x180079d2b  jnz     loc_18007A04A
0x180079d31  inc     dword ptr [r15+4Ch]
0x180079d35  jmp     loc_18007A05E
0x180079d3a  mov     rax, [rbx]
0x180079d3d  lea     r9, [rsp+78h+var_40]
0x180079d42  lea     r8, [rsp+78h+var_48]
0x180079d47  xor     edx, edx
0x180079d49  mov     rcx, rbx
0x180079d4c  mov     rax, [rax+20h]
0x180079d50  call    cs:__guard_dispatch_icall_fptr
0x180079d56  mov     ebp, eax
0x180079d58  test    eax, eax
0x180079d5a  jns     loc_180079E05
0x180079d60  cmp     eax, 0C00D9C43h
0x180079d65  jz      short loc_180079DA8
0x180079d67  mov     r8d, 803h; int
0x180079d6d  lea     rdx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x180079d74  lea     rcx, [rsp+78h+dwErrCode]; this
0x180079d7c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180079d81  cmp     cs:byte_1803CECE9, 20h ; ' '
0x180079d88  jb      loc_180079CED
0x180079d8e  mov     rax, 346DC5D63886594Bh
0x180079d98  imul    r13
0x180079d9b  mov     rcx, rdx
0x180079d9e  mov     edx, 4Eh ; 'N'
0x180079da3  jmp     loc_180079CC1
0x180079da8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079daf  test    ebp, ebp
0x180079db1  jns     loc_180079CFC
0x180079db7  test    rdi, rdi
0x180079dba  jnz     loc_180079FEE
0x180079dc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079dc7  nop     dword ptr [rax+rax+00h]
0x180079dcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079dd3  mov     rcx, rax
0x180079dd6  test    rax, rax
0x180079dd9  jz      loc_180079FE0
0x180079ddf  mov     rax, [rax]
0x180079de2  mov     edx, 7F0h
0x180079de7  mov     rax, [rax+8]
0x180079deb  call    cs:__guard_dispatch_icall_fptr
0x180079df1  test    eax, eax
0x180079df3  jz      loc_180079FE0
0x180079df9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e00  jmp     loc_180079FEE
0x180079e05  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e0c  test    rdi, rdi
0x180079e0f  jnz     short loc_180079E1D
0x180079e11  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180079e16  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e1d  cmp     byte ptr [rdi+8], 0
0x180079e21  jz      loc_180079ED5
0x180079e27  lea     r14, [rdi+0D0h]
0x180079e2e  call    cs:__imp_GetLastError
0x180079e35  nop     dword ptr [rax+rax+00h]
0x180079e3a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180079e3d  mov     r12d, eax
0x180079e40  call    cs:__imp_TlsGetValue
0x180079e47  nop     dword ptr [rax+rax+00h]
0x180079e4c  test    rax, rax
0x180079e4f  jz      short loc_180079E56
0x180079e51  mov     r14, rax
0x180079e54  jmp     short loc_180079E91
0x180079e56  call    cs:__imp_GetLastError
0x180079e5d  nop     dword ptr [rax+rax+00h]
0x180079e62  test    eax, eax
0x180079e64  jnz     short loc_180079E91
0x180079e66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e6d  test    rcx, rcx
0x180079e70  jnz     short loc_180079E7E
0x180079e72  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180079e77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e7e  mov     rax, [rcx]
0x180079e81  mov     rax, [rax]
0x180079e84  call    cs:__guard_dispatch_icall_fptr
0x180079e8a  test    rax, rax
0x180079e8d  cmovnz  r14, rax
0x180079e91  mov     ecx, r12d; dwErrCode
0x180079e94  call    cs:__imp_SetLastError
0x180079e9b  nop     dword ptr [rax+rax+00h]
0x180079ea0  mov     eax, [r14+7C4h]
0x180079ea7  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079eae  cmp     eax, [r14+7C8h]
0x180079eb5  jnb     short loc_180079ECE
0x180079eb7  add     rax, rax
0x180079eba  lea     rcx, aCmfpresentatio_11; "CMFPresentationClock::GetClockTime"
0x180079ec1  mov     [r14+rax*8], rcx
0x180079ec5  mov     dword ptr [r14+rax*8+8], 810h
0x180079ece  inc     dword ptr [r14+7C4h]
0x180079ed5  cmp     cs:byte_1803CECE9, 20h ; ' '
0x180079edc  jb      short loc_180079F18
0x180079ede  mov     rax, [rsp+78h+var_40]
0x180079ee3  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x180079eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ef1  mov     edx, 4Fh ; 'O'
0x180079ef6  mov     [rsp+78h+var_50], rax
0x180079efb  mov     r9, rbx
0x180079efe  mov     rax, [rsp+78h+var_48]
0x180079f03  mov     [rsp+78h+var_58], rax
0x180079f08  mov     rcx, [rcx+38h]
0x180079f0c  call    WPP_SF_qqq
0x180079f11  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079f18  cmp     byte ptr [rdi+8], 0
0x180079f1c  mov     r13, [rsp+78h+var_48]
0x180079f21  mov     r12, [rsp+78h+var_40]
0x180079f26  jz      loc_180079DAF
0x180079f2c  lea     r14, [rdi+0D0h]
0x180079f33  call    cs:__imp_GetLastError
0x180079f3a  nop     dword ptr [rax+rax+00h]
0x180079f3f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180079f42  mov     [rsp+78h+dwErrCode], eax
0x180079f49  call    cs:__imp_TlsGetValue
0x180079f50  nop     dword ptr [rax+rax+00h]
0x180079f55  test    rax, rax
0x180079f58  jz      short loc_180079F5F
0x180079f5a  mov     r14, rax
0x180079f5d  jmp     short loc_180079F9A
0x180079f5f  call    cs:__imp_GetLastError
0x180079f66  nop     dword ptr [rax+rax+00h]
0x180079f6b  test    eax, eax
0x180079f6d  jnz     short loc_180079F9A
0x180079f6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079f76  test    rcx, rcx
0x180079f79  jnz     short loc_180079F87
0x180079f7b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180079f80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079f87  mov     rax, [rcx]
0x180079f8a  mov     rax, [rax]
0x180079f8d  call    cs:__guard_dispatch_icall_fptr
0x180079f93  test    rax, rax
0x180079f96  cmovnz  r14, rax
0x180079f9a  mov     ecx, [rsp+78h+dwErrCode]; dwErrCode
0x180079fa1  call    cs:__imp_SetLastError
0x180079fa8  nop     dword ptr [rax+rax+00h]
0x180079fad  mov     eax, [r14+7C4h]
0x180079fb4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079fbb  test    eax, eax
0x180079fbd  jz      loc_180079DAF
0x180079fc3  sub     eax, 1
0x180079fc6  mov     [r14+7C4h], eax
0x180079fcd  jnz     loc_180079DAF
0x180079fd3  mov     rcx, r14; this
0x180079fd6  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180079fdb  jmp     loc_180079CFC
0x180079fe0  lea     rdi, qword_1803CE250
0x180079fe7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180079fee  cmp     byte ptr [rdi+8], 0
0x180079ff2  jz      short loc_18007A01C
0x180079ff4  mov     rcx, rdi; this
0x180079ff7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079ffc  cmp     [rax+7CCh], ebp
0x18007a002  jz      short loc_18007A01C
0x18007a004  mov     r9d, ebp; int
0x18007a007  lea     rdx, aCmfpresentatio_7; "CMFPresentationClock::GetTimeInternal"
0x18007a00e  mov     r8d, 836h; int
0x18007a014  mov     rcx, rax; this
0x18007a017  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a01c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a023  jb      short loc_18007A09D
0x18007a025  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a02c  lea     r8, WPP_4f7d8de4e6d13a2456f3b7c35d379f01_Traceguids
0x18007a033  mov     edx, 50h ; 'P'
0x18007a038  mov     dword ptr [rsp+78h+var_58], ebp
0x18007a03c  mov     r9, r15
0x18007a03f  mov     rcx, [rcx+10h]
0x18007a043  call    WPP_SF_qD
0x18007a048  jmp     short loc_18007A09D
0x18007a04a  lea     rcx, [r15+40h]; SRWLock
0x18007a04e  call    cs:__imp_AcquireSRWLockExclusive
0x18007a055  nop     dword ptr [rax+rax+00h]
0x18007a05a  mov     [r15+48h], edi
0x18007a05e  cmp     r12, [r15+270h]
  ... truncated ...
```
