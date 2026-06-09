# CMMCSSOutputQueue::ReceiveMultiple(IMediaSample * *,long,long *)

- ea: `0x180011950`
- end: `0x180011f31`
- name: `?ReceiveMultiple@CMMCSSOutputQueue@@QEAAJPEAPEAUIMediaSample@@JPEAJ@Z`
- size: `1505`
- prototype: `__int64 __fastcall(CMMCSSOutputQueue *__hidden this, struct IMediaSample **, int, int *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180011260`
- `0x180011f40`
- `0x1800141a0`
- `0x1800ba6f0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180011950`
- `0x180051ce4`
- `0x180076738`
- `0x18007c8e8`
- `0x1800ba67c`
- `0x1800ba6b4`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011bb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011bb6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011a20`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011b2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011a20`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011b2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ee2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011ee2`

## pseudocode

```c
__int64 __fastcall CMMCSSOutputQueue::ReceiveMultiple(
        struct _RTL_CRITICAL_SECTION *this,
        struct IMediaSample **a2,
        int a3,
        int *a4)
{
  struct IMediaSample **v6; // r15
  LONG RecursionCount; // eax
  __int64 v9; // r14
  int v10; // r13d
  int v11; // esi
  CallStackTracing *v12; // rdi
  __int64 LockSemaphore_low; // rcx
  bool v14; // zf
  __int64 v15; // rax
  int LockSemaphore; // ecx
  char *v17; // rbp
  DWORD LastError; // r15d
  char *Value; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  LONG v22; // eax
  int v23; // edx
  int v24; // edi
  __int64 v25; // rcx
  GUID *v26; // rbp
  DWORD v27; // r15d
  GUID *v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // esi
  int *v32; // r13
  unsigned int v33; // edi
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  CallStackTracing *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r14
  CallStackTracing *v40; // rax
  CallStackTracing *v41; // rax
  int v43; // [rsp+80h] [rbp+18h] BYREF
  int *v44; // [rsp+88h] [rbp+20h]

  v44 = a4;
  v6 = a2;
  EnterCriticalSection(this);
  RecursionCount = this[3].RecursionCount;
  if ( !this[1].LockSemaphore )
  {
    v9 = 0;
    if ( !RecursionCount )
    {
      v10 = 0;
      v11 = 0;
      HIDWORD(this[2].SpinCount) = 0;
LABEL_4:
      v12 = CallStackTracing::s_wpInstance;
      while ( v11 < a3 )
      {
        LockSemaphore_low = SLODWORD(this[2].LockSemaphore);
        v14 = (_DWORD)LockSemaphore_low == HIDWORD(this[1].OwningThread);
        if ( (int)LockSemaphore_low < SHIDWORD(this[1].OwningThread) )
        {
          v15 = v11++;
          *((_QWORD *)this[2].OwningThread + LockSemaphore_low) = v6[v15];
          LockSemaphore = ++LODWORD(this[2].LockSemaphore);
LABEL_8:
          v14 = LockSemaphore == HIDWORD(this[1].OwningThread);
        }
        if ( v14 || !a3 && (this[3].LockCount || !LODWORD(this[1].OwningThread)) )
        {
          v43 = 0;
          if ( !v12 )
          {
            CallStackTracing::InitInstance();
            v12 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v12 + 8) )
          {
            v17 = (char *)v12 + 208;
            LastError = GetLastError();
            Value = (char *)TlsGetValue(*((_DWORD *)v12 + 3));
            if ( Value )
            {
              v17 = Value;
            }
            else if ( !GetLastError() )
            {
              v35 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v40;
                if ( v40
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                {
                  v35 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v35 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
              if ( v36 )
                v17 = (char *)v36;
            }
            SetLastError(LastError);
            v20 = *((unsigned int *)v17 + 497);
            if ( (unsigned int)v20 < *((_DWORD *)v17 + 498) )
            {
              v21 = 2 * v20;
              *(_QWORD *)&v17[8 * v21] = "CMMCSSOutputQueue::ReceiveMultiple";
              *(_DWORD *)&v17[8 * v21 + 8] = 704;
            }
            ++*((_DWORD *)v17 + 497);
          }
          if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              22,
              WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids,
              this,
              this[2].LockSemaphore);
          if ( this[3].RecursionCount )
          {
            v23 = 0;
            v43 = 0;
          }
          else
          {
            v22 = (*(__int64 (__fastcall **)(_QWORD, HANDLE, _QWORD, int *))(**(_QWORD **)&this[1].LockCount + 56LL))(
                    *(_QWORD *)&this[1].LockCount,
                    this[2].OwningThread,
                    LODWORD(this[2].LockSemaphore),
                    &v43);
            v23 = v43;
            this[3].RecursionCount = v22;
          }
          v24 = 0;
          v10 += LODWORD(this[2].LockSemaphore) - v23;
          if ( SLODWORD(this[2].LockSemaphore) > 0 )
          {
            do
            {
              v25 = *((_QWORD *)this[2].OwningThread + v24);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              ++v24;
            }
            while ( v24 < SLODWORD(this[2].LockSemaphore) );
          }
          v12 = CallStackTracing::s_wpInstance;
          v6 = a2;
          LODWORD(this[2].LockSemaphore) = 0;
          if ( *((_BYTE *)v12 + 8) )
          {
            v26 = (GUID *)((char *)v12 + 208);
            v27 = GetLastError();
            v28 = (GUID *)TlsGetValue(*((_DWORD *)v12 + 3));
            if ( v28 )
            {
              v26 = v28;
            }
            else if ( !GetLastError() )
            {
              v37 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v41;
                if ( v41
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                {
                  v37 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v37 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              v38 = (**(__int64 (__fastcall ***)(CallStackTracing *))v37)(v37);
              if ( v38 )
                v26 = (GUID *)v38;
            }
            SetLastError(v27);
            v29 = *(_DWORD *)&v26[124].Data2;
            v12 = CallStackTracing::s_wpInstance;
            v6 = a2;
            if ( v29 )
            {
              v30 = v29 - 1;
              *(_DWORD *)&v26[124].Data2 = v30;
              if ( !v30 )
              {
                *(_DWORD *)&v26[124].Data2 = 0;
                *(_QWORD *)&v26[126].Data1 = 0;
                *(_DWORD *)&v26[124].Data4[4] = 0;
                v26[125] = GUID_00000000_0000_0000_0000_000000000000;
                *(_DWORD *)v26[126].Data4 = 0;
                v26[124].Data1 = GetCurrentThreadId();
                goto LABEL_4;
              }
            }
          }
        }
      }
      LockSemaphore = (int)this[2].LockSemaphore;
      if ( !LockSemaphore || !this[3].LockCount )
      {
        v31 = v11 - v10;
        v32 = v44;
        *v44 = v31;
        if ( v31 < 0 )
          *v32 = 0;
        goto LABEL_33;
      }
      goto LABEL_8;
    }
    *a4 = 0;
    if ( a3 > 0 )
    {
      do
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMMCSSOutputQueue::ReceiveMultiple", 671);
        if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            21,
            WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids,
            this,
            a3,
            this[3].RecursionCount);
        ((void (__fastcall *)(struct IMediaSample *))v6[v9]->lpVtbl->Release)(v6[v9]);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (int)v9 < a3 );
    }
LABEL_33:
    v33 = this[3].RecursionCount;
    goto LABEL_34;
  }
  v39 = 0;
  if ( RecursionCount )
  {
    *a4 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CMMCSSOutputQueue::ReceiveMultiple", 733);
    if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        23,
        WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids,
        this,
        a3,
        this[3].RecursionCount);
    if ( a3 > 0 )
    {
      do
      {
        ((void (__fastcall *)(struct IMediaSample *))v6[v39]->lpVtbl->Release)(v6[v39]);
        v39 = (unsigned int)(v39 + 1);
      }
      while ( (int)v39 < a3 );
    }
    v33 = this[3].RecursionCount;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
LABEL_34:
    LeaveCriticalSection(this);
    return v33;
  }
  HIDWORD(this[2].SpinCount) = 0;
  if ( a3 > 0 )
  {
    do
    {
      DShow::COutputQueue::QueueSample((DShow::COutputQueue *)this, v6[v39]);
      v39 = (unsigned int)(v39 + 1);
    }
    while ( (int)v39 < a3 );
  }
  v14 = LODWORD(this[1].OwningThread) == 0;
  *a4 = a3;
  if ( v14 || LODWORD(this[2].LockSemaphore) + *((_DWORD *)this[1].LockSemaphore + 4) >= SHIDWORD(this[1].OwningThread) )
    CMMCSSOutputQueue::NotifyThread((CMMCSSOutputQueue *)this);
  LeaveCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180011950  mov     [rsp+arg_18], r9
0x180011955  mov     [rsp+arg_8], rdx
0x18001195a  push    rbx
0x18001195b  push    rdi
0x18001195c  push    r12
0x18001195e  push    r13
0x180011960  push    r14
0x180011962  push    r15
0x180011964  sub     rsp, 38h
0x180011968  mov     r13, r9
0x18001196b  mov     r12d, r8d
0x18001196e  mov     r15, rdx
0x180011971  mov     rbx, rcx
0x180011974  call    cs:__imp_EnterCriticalSection
0x18001197b  nop     dword ptr [rax+rax+00h]
0x180011980  cmp     qword ptr [rbx+40h], 0
0x180011985  mov     eax, [rbx+84h]
0x18001198b  jnz     loc_180011D4F
0x180011991  xor     r14d, r14d
0x180011994  test    eax, eax
0x180011996  jnz     loc_180011C1E
0x18001199c  mov     [rsp+68h+var_38], rsi
0x1800119a1  mov     r13d, r14d
0x1800119a4  mov     esi, r14d
0x1800119a7  mov     [rsp+68h+arg_0], rbp
0x1800119ac  mov     [rbx+74h], r14d
0x1800119b0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800119b7  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x1800119be  cmp     esi, r12d
0x1800119c1  jge     loc_180011BCD
0x1800119c7  movsxd  rcx, dword ptr [rbx+68h]
0x1800119cb  cmp     ecx, [rbx+3Ch]
0x1800119ce  jge     short loc_1800119EA
0x1800119d0  movsxd  rax, esi
0x1800119d3  inc     esi
0x1800119d5  mov     rdx, [r15+rax*8]
0x1800119d9  mov     rax, [rbx+60h]
0x1800119dd  mov     [rax+rcx*8], rdx
0x1800119e1  inc     dword ptr [rbx+68h]
0x1800119e4  mov     ecx, [rbx+68h]
0x1800119e7  cmp     ecx, [rbx+3Ch]
0x1800119ea  jnz     loc_180011CA5
0x1800119f0  mov     [rsp+68h+arg_10], r14d
0x1800119f8  test    rdi, rdi
0x1800119fb  jz      loc_180011E4D
0x180011a01  cmp     [rdi+8], r14b
0x180011a05  jz      short loc_180011A72
0x180011a07  lea     rbp, [rdi+0D0h]
0x180011a0e  call    cs:__imp_GetLastError
0x180011a15  nop     dword ptr [rax+rax+00h]
0x180011a1a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180011a1d  mov     r15d, eax
0x180011a20  call    cs:__imp_TlsGetValue
0x180011a27  nop     dword ptr [rax+rax+00h]
0x180011a2c  test    rax, rax
0x180011a2f  jz      loc_180011CD9
0x180011a35  mov     rbp, rax
0x180011a38  mov     ecx, r15d; dwErrCode
0x180011a3b  call    cs:__imp_SetLastError
0x180011a42  nop     dword ptr [rax+rax+00h]
0x180011a47  mov     eax, [rbp+7C4h]
0x180011a4d  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011a54  cmp     eax, [rbp+7C8h]
0x180011a5a  jnb     short loc_180011A6C
0x180011a5c  add     rax, rax
0x180011a5f  mov     [rbp+rax*8+0], r8
0x180011a64  mov     dword ptr [rbp+rax*8+8], 2C0h
0x180011a6c  inc     dword ptr [rbp+7C4h]
0x180011a72  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180011a79  jnb     loc_180011EB4
0x180011a7f  mov     eax, [rbx+84h]
0x180011a85  test    eax, eax
0x180011a87  jnz     loc_180011CCA
0x180011a8d  mov     rcx, [rbx+30h]
0x180011a91  lea     r9, [rsp+68h+arg_10]
0x180011a99  mov     r8d, [rbx+68h]
0x180011a9d  mov     rdx, [rbx+60h]
0x180011aa1  mov     rax, [rcx]
0x180011aa4  mov     rax, [rax+38h]
0x180011aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aad  mov     edx, [rsp+68h+arg_10]
0x180011ab4  mov     [rbx+84h], eax
0x180011aba  mov     ecx, 60h ; '`'
0x180011abf  mov     rax, rbx
0x180011ac2  mov     edi, r14d
0x180011ac5  lea     r15, [rcx+rbx]
0x180011ac9  mov     ecx, [rbx+68h]
0x180011acc  mov     eax, ecx
0x180011ace  sub     eax, edx
0x180011ad0  add     r13d, eax
0x180011ad3  test    ecx, ecx
0x180011ad5  jle     short loc_180011AF4
0x180011ad7  mov     rax, [r15]
0x180011ada  movsxd  rcx, edi
0x180011add  mov     rcx, [rax+rcx*8]
0x180011ae1  mov     rax, [rcx]
0x180011ae4  mov     rax, [rax+10h]
0x180011ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aed  inc     edi
0x180011aef  cmp     edi, [rbx+68h]
0x180011af2  jl      short loc_180011AD7
0x180011af4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011afb  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011b02  mov     r15, [rsp+68h+arg_8]
0x180011b07  mov     [rbx+68h], r14d
0x180011b0b  cmp     [rdi+8], r14b
0x180011b0f  jz      loc_1800119BE
0x180011b15  lea     rbp, [rdi+0D0h]
0x180011b1c  call    cs:__imp_GetLastError
0x180011b23  nop     dword ptr [rax+rax+00h]
0x180011b28  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180011b2b  mov     r15d, eax
0x180011b2e  call    cs:__imp_TlsGetValue
0x180011b35  nop     dword ptr [rax+rax+00h]
0x180011b3a  test    rax, rax
0x180011b3d  jz      loc_180011D14
0x180011b43  mov     rbp, rax
0x180011b46  mov     ecx, r15d; dwErrCode
0x180011b49  call    cs:__imp_SetLastError
0x180011b50  nop     dword ptr [rax+rax+00h]
0x180011b55  mov     eax, [rbp+7C4h]
0x180011b5b  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011b62  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011b69  mov     r15, [rsp+68h+arg_8]
0x180011b6e  test    eax, eax
0x180011b70  jz      loc_1800119BE
0x180011b76  sub     eax, 1
0x180011b79  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011b80  mov     [rbp+7C4h], eax
0x180011b86  jnz     loc_1800119BE
0x180011b8c  mov     [rbp+7C4h], r14d
0x180011b93  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180011b9a  mov     [rbp+7E0h], r14
0x180011ba1  mov     [rbp+7CCh], r14d
0x180011ba8  movups  xmmword ptr [rbp+7D0h], xmm0
0x180011baf  mov     [rbp+7E8h], r14d
0x180011bb6  call    cs:__imp_GetCurrentThreadId
0x180011bbd  nop     dword ptr [rax+rax+00h]
0x180011bc2  mov     [rbp+7C0h], eax
0x180011bc8  jmp     loc_1800119B0
0x180011bcd  mov     ecx, [rbx+68h]
0x180011bd0  test    ecx, ecx
0x180011bd2  jnz     loc_180011E3B
0x180011bd8  mov     rbp, [rsp+68h+arg_0]
0x180011bdd  sub     esi, r13d
0x180011be0  mov     r13, [rsp+68h+arg_18]
0x180011be8  mov     [r13+0], esi
0x180011bec  mov     rsi, [rsp+68h+var_38]
0x180011bf1  jns     short loc_180011BF7
0x180011bf3  mov     [r13+0], r14d
0x180011bf7  mov     edi, [rbx+84h]
0x180011bfd  mov     rcx, rbx; lpCriticalSection
0x180011c00  call    cs:__imp_LeaveCriticalSection
0x180011c07  nop     dword ptr [rax+rax+00h]
0x180011c0c  mov     eax, edi
0x180011c0e  add     rsp, 38h
0x180011c12  pop     r15
0x180011c14  pop     r14
0x180011c16  pop     r13
0x180011c18  pop     r12
0x180011c1a  pop     rdi
0x180011c1b  pop     rbx
0x180011c1c  retn
0x180011c1e  mov     [r13+0], r14d
0x180011c22  test    r12d, r12d
0x180011c25  jle     short loc_180011BF7
0x180011c27  mov     r8d, 29Fh; int
0x180011c2d  lea     rdx, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011c34  lea     rcx, [rsp+68h+arg_10]; this
0x180011c3c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180011c41  cmp     cs:byte_1800EACCB, 10h
0x180011c48  jb      short loc_180011C7B
0x180011c4a  mov     rax, cs:WPP_GLOBAL_Control
0x180011c51  lea     r8, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids
0x180011c58  mov     edx, 15h
0x180011c5d  mov     r9, rbx
0x180011c60  mov     rcx, [rax+88h]
0x180011c67  mov     eax, [rbx+84h]
0x180011c6d  mov     [rsp+68h+var_40], eax
0x180011c71  mov     [rsp+68h+var_48], r12d
0x180011c76  call    WPP_SF_qDD
0x180011c7b  mov     rcx, [r15+r14*8]
0x180011c7f  mov     rax, [rcx]
0x180011c82  mov     rax, [rax+10h]
0x180011c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c8b  lea     rcx, [rsp+68h+arg_10]; this
0x180011c93  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011c98  inc     r14d
0x180011c9b  cmp     r14d, r12d
0x180011c9e  jl      short loc_180011C27
0x180011ca0  jmp     loc_180011BF7
0x180011ca5  test    r12d, r12d
0x180011ca8  jnz     loc_1800119BE
0x180011cae  cmp     [rbx+80h], r14d
0x180011cb5  jnz     loc_1800119F0
0x180011cbb  cmp     [rbx+38h], r14d
0x180011cbf  jnz     loc_1800119BE
0x180011cc5  jmp     loc_1800119F0
0x180011cca  mov     edx, r14d
0x180011ccd  mov     [rsp+68h+arg_10], edx
0x180011cd4  jmp     loc_180011ABA
0x180011cd9  call    cs:__imp_GetLastError
0x180011ce0  nop     dword ptr [rax+rax+00h]
0x180011ce5  test    eax, eax
0x180011ce7  jnz     loc_180011A38
0x180011ced  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011cf4  test    rcx, rcx
0x180011cf7  jz      loc_180011E65
0x180011cfd  mov     rax, [rcx]
0x180011d00  mov     rax, [rax]
0x180011d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d08  test    rax, rax
0x180011d0b  cmovnz  rbp, rax
0x180011d0f  jmp     loc_180011A38
0x180011d14  call    cs:__imp_GetLastError
0x180011d1b  nop     dword ptr [rax+rax+00h]
0x180011d20  test    eax, eax
0x180011d22  jnz     loc_180011B46
0x180011d28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011d2f  test    rcx, rcx
0x180011d32  jz      loc_180011EE2
0x180011d38  mov     rax, [rcx]
0x180011d3b  mov     rax, [rax]
0x180011d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d43  test    rax, rax
0x180011d46  cmovnz  rbp, rax
0x180011d4a  jmp     loc_180011B46
0x180011d4f  xor     r14d, r14d
0x180011d52  test    eax, eax
0x180011d54  jz      loc_180011DE7
0x180011d5a  mov     r8d, 2DDh; int
0x180011d60  mov     [r13+0], r14d
0x180011d64  lea     rdx, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011d6b  lea     rcx, [rsp+68h+arg_10]; this
0x180011d73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180011d78  cmp     cs:byte_1800EACCB, 10h
0x180011d7f  jb      short loc_180011DB2
0x180011d81  mov     rax, cs:WPP_GLOBAL_Control
0x180011d88  lea     r8, WPP_a72c45aecc5034263e449ab15c8e8695_Traceguids
0x180011d8f  mov     edx, 17h
0x180011d94  mov     r9, rbx
0x180011d97  mov     rcx, [rax+88h]
0x180011d9e  mov     eax, [rbx+84h]
0x180011da4  mov     [rsp+68h+var_40], eax
0x180011da8  mov     [rsp+68h+var_48], r12d
0x180011dad  call    WPP_SF_qDD
0x180011db2  test    r12d, r12d
0x180011db5  jle     short loc_180011DCF
0x180011db7  mov     rcx, [r15+r14*8]
0x180011dbb  mov     rax, [rcx]
0x180011dbe  mov     rax, [rax+10h]
0x180011dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc7  inc     r14d
0x180011dca  cmp     r14d, r12d
0x180011dcd  jl      short loc_180011DB7
0x180011dcf  mov     edi, [rbx+84h]
0x180011dd5  lea     rcx, [rsp+68h+arg_10]; this
0x180011ddd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011de2  jmp     loc_180011BFD
0x180011de7  mov     [rbx+74h], r14d
0x180011deb  test    r12d, r12d
0x180011dee  jle     short loc_180011E04
0x180011df0  mov     rdx, [r15+r14*8]; struct IMediaSample *
0x180011df4  mov     rcx, rbx; this
0x180011df7  call    ?QueueSample@COutputQueue@DShow@@IEAAXPEAUIMediaSample@@@Z; DShow::COutputQueue::QueueSample(IMediaSample *)
0x180011dfc  inc     r14d
0x180011dff  cmp     r14d, r12d
0x180011e02  jl      short loc_180011DF0
0x180011e04  cmp     dword ptr [rbx+38h], 0
0x180011e08  mov     [r13+0], r12d
0x180011e0c  jz      short loc_180011E1D
0x180011e0e  mov     rax, [rbx+40h]
0x180011e12  mov     ecx, [rax+10h]
0x180011e15  add     ecx, [rbx+68h]
0x180011e18  cmp     ecx, [rbx+3Ch]
0x180011e1b  jl      short loc_180011E25
0x180011e1d  mov     rcx, rbx; this
0x180011e20  call    ?NotifyThread@CMMCSSOutputQueue@@IEAAXXZ; CMMCSSOutputQueue::NotifyThread(void)
0x180011e25  mov     rcx, rbx; lpCriticalSection
0x180011e28  call    cs:__imp_LeaveCriticalSection
0x180011e2f  nop     dword ptr [rax+rax+00h]
0x180011e34  xor     eax, eax
0x180011e36  jmp     loc_180011C0E
0x180011e3b  cmp     [rbx+80h], r14d
0x180011e42  jz      loc_180011BD8
0x180011e48  jmp     loc_1800119E7
0x180011e4d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180011e52  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e59  lea     r8, aCmmcssoutputqu_1; "CMMCSSOutputQueue::ReceiveMultiple"
0x180011e60  jmp     loc_180011A01
0x180011e65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011e6c  nop     dword ptr [rax+rax+00h]
0x180011e71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011e78  mov     rcx, rax
0x180011e7b  test    rax, rax
0x180011e7e  jz      short loc_180011EA1
0x180011e80  mov     rax, [rax]
0x180011e83  mov     edx, 7F0h
0x180011e88  mov     rax, [rax+8]
0x180011e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
