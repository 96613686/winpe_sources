# CxThreadManager::ExecuteThreads(unsigned __int64,bool,ulong,bool)

- ea: `0x18306a070`
- end: `0x18306a38e`
- name: `?ExecuteThreads@CxThreadManager@@QEAA_N_K_NK1@Z`
- size: `798`
- prototype: `bool(CxThreadManager *__hidden this, unsigned __int64, bool, unsigned int, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x182d39be0`
- `0x183069b90`

## callees

- `0x182dcc5d0`
- `0x182dcc8c0`
- `0x182dcca70`
- `0x18304fd40`
- `0x183050390`
- `0x1830503a0`
- `0x183050540`
- `0x1830505f0`
- `0x183051b30`
- `0x183051b90`
- `0x183069fe0`
- `0x18306a070`
- `0x18306a490`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18306a29e`
- `KERNEL32!LocalFree` at `0x18306a29e`
- `KERNEL32!FormatMessageA` at `0x18306a282`
- `KERNEL32!FormatMessageA` at `0x18306a282`
- `KERNEL32!SetEvent` at `0x18306a197`
- `KERNEL32!SetEvent` at `0x18306a197`
- `KERNEL32!ResetEvent` at `0x18306a175`
- `KERNEL32!ResetEvent` at `0x18306a1f6`
- `KERNEL32!ResetEvent` at `0x18306a218`
- `KERNEL32!ResetEvent` at `0x18306a175`
- `KERNEL32!ResetEvent` at `0x18306a1f6`
- `KERNEL32!ResetEvent` at `0x18306a218`
- `KERNEL32!GetLastError` at `0x18306a258`
- `KERNEL32!GetLastError` at `0x18306a258`

## string_xrefs

- `0x18306a187`: `Failed to reset run completed event for thread number '%d'.`
- `0x18306a22a`: `Failed to reset run completed event for thread number '%d'.`
- `0x18306a1a9`: `Failed To resume thread number '%d'.`
- `0x18306a208`: `Failed to reset start event for thread number '%d'.`
- `0x18306a244`: `WAIT_TIMEOUT error. Threads failed to reach signaled state.\n`
- `0x18306a10f`: `The number of threads specified for a computation must greater than 0 and no greater than the number of threads allocated. The number of threads to be used is being set to 1.`
- `0x18306a126`: `The number of threads specified for a computation must greater than 0 and no greater than the number of threads allocated. The number of threads to be used is being set to  %d.`

## pseudocode

```c
char __fastcall CxThreadManager::ExecuteThreads(
        CxThreadManager *this,
        int a2,
        unsigned __int8 a3,
        unsigned int a4,
        bool a5)
{
  unsigned __int64 v7; // rsi
  CxThreadManager *v8; // rdi
  bool v10; // r14
  __int64 v11; // rbx
  int NumProcessorsToUse; // eax
  unsigned __int64 j; // rbx
  __int64 v14; // r15
  unsigned int v15; // r12d
  unsigned __int64 k; // rbx
  __int64 v17; // r15
  DWORD LastError; // eax
  unsigned __int64 i; // rbx
  char v20; // bl
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  CHAR Buffer[8]; // [rsp+50h] [rbp-58h] BYREF
  const std::exception *v25; // [rsp+58h] [rbp-50h] BYREF

  LODWORD(v7) = a2;
  v8 = this;
  *((_BYTE *)this + 24) = a5;
  if ( GetExitAllThreads() )
  {
    if ( GetAlreadyThreading() )
      return 0;
    SetExitAllThreads(0);
  }
  v10 = a5 && GetDoFakeThreading();
  v7 = (int)v7;
  v11 = *(_QWORD *)v8;
  if ( (int)v7 == -1 )
    v7 = (int)v11;
  if ( !v7 )
  {
    NumProcessorsToUse = GetNumProcessorsToUse();
    v7 = NumProcessorsToUse;
    if ( !NumProcessorsToUse )
    {
      CxReportWarning(
        "The number of threads specified for a computation must greater than 0 and no greater than the number of threads "
        "allocated. The number of threads to be used is being set to 1.");
      v7 = 1;
    }
  }
  if ( (int)v7 > (int)v11 )
  {
    CxReportWarning(
      "The number of threads specified for a computation must greater than 0 and no greater than the number of threads al"
      "located. The number of threads to be used is being set to  %d.",
      v11);
    v7 = (int)v11;
  }
  try
  {
    if ( v10 || *((_BYTE *)v8 + 9) )
    {
      *((_BYTE *)v8 + 9) = 1;
      if ( GetDoFakeThreading() )
        SetDoingFakeThreading(1);
      for ( i = 0; i < v7; ++i )
        ExecThreadProc((struct CxThreadInfo *)(*((_QWORD *)v8 + 4) + 72 * i));
      if ( GetDoingFakeThreading() )
        SetDoingFakeThreading(0);
    }
    else
    {
      CxThreadManager::m_iTotalNumThreadsExecuting += (int)v7;
      *((_BYTE *)v8 + 9) = 1;
      for ( j = 0; j < v7; ++j )
      {
        v14 = *((_QWORD *)v8 + 4) + 72 * j;
        if ( !ResetEvent(*(HANDLE *)(v14 + 24)) )
          CxThrowError("Failed to reset run completed event for thread number '%d'.", j);
        if ( !SetEvent(*(HANDLE *)(v14 + 32)) )
          CxThrowError("Failed To resume thread number '%d'.", j);
      }
      *(_DWORD *)Buffer = 0;
      v15 = WaitHelper::WaitForMultipleObjects(v7, *((void *const **)v8 + 5), a3, a4, (unsigned int *)Buffer);
      for ( k = 0; k < v7; ++k )
      {
        v17 = *((_QWORD *)v8 + 4) + 72 * k;
        if ( !ResetEvent(*(HANDLE *)(v17 + 32)) )
          CxThrowError("Failed to reset start event for thread number '%d'.", k);
        if ( !ResetEvent(*(HANDLE *)(v17 + 24)) )
          CxThrowError("Failed to reset run completed event for thread number '%d'.", k);
      }
      switch ( v15 )
      {
        case 0x102u:
          CxPrintf("WAIT_TIMEOUT error. Threads failed to reach signaled state.\n");
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          FormatMessageA(0x1300u, 0, LastError, 0x400u, Buffer, 0, 0);
          CxPrintf("WAIT FAILED: %s\n", *(const char **)Buffer);
          LocalFree(*(HLOCAL *)Buffer);
          break;
        case 0x80u:
          CxPrintf("WAIT_ABANDONED error. Mutex signaled because it was abandoned.\n");
          break;
      }
      CxThreadManager::m_iTotalNumThreadsExecuting -= (int)v7;
    }
  }
  catch ( const std::exception *v25 )
  {
    v8 = this;
  }
  catch ( ... )
  {
    v8 = this;
  }
  v20 = 1;
  *((_BYTE *)v8 + 9) = 0;
  if ( GetExitAllThreads() && !CxThreadManager::m_iTotalNumThreadsExecuting )
  {
    SetExitAllThreads(0);
    v20 = 0;
  }
  v21 = 0;
  if ( *(_QWORD *)v8 )
  {
    v22 = 0;
    do
    {
      *(_QWORD *)(*((_QWORD *)v8 + 4) + v22 + 56) = 0;
      *(_BYTE *)(*((_QWORD *)v8 + 4) + v22 + 40) = 0;
      ++v21;
      v22 += 72;
    }
    while ( v21 < *(_QWORD *)v8 );
  }
  return v20;
}

```

## disassembly

```asm
0x18306a070  push    rbx
0x18306a072  push    rsi
0x18306a073  push    rdi
0x18306a074  push    r12
0x18306a076  push    r13
0x18306a078  push    r14
0x18306a07a  push    r15
0x18306a07c  sub     rsp, 70h
0x18306a080  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFEh
0x18306a089  mov     rax, cs:__security_cookie
0x18306a090  xor     rax, rsp
0x18306a093  mov     [rsp+0A8h+var_48], rax
0x18306a098  mov     r13d, r9d
0x18306a09b  movzx   r12d, r8b
0x18306a09f  mov     rsi, rdx
0x18306a0a2  mov     rdi, rcx
0x18306a0a5  mov     [rsp+0A8h+var_68], rcx
0x18306a0aa  movzx   ebx, [rsp+0A8h+arg_20]
0x18306a0b2  mov     [rcx+18h], bl
0x18306a0b5  call    ?GetExitAllThreads@@YA_NXZ; GetExitAllThreads(void)
0x18306a0ba  cmp     al, 1
0x18306a0bc  jnz     short loc_18306A0D7
0x18306a0be  call    ?GetAlreadyThreading@@YA_NXZ; GetAlreadyThreading(void)
0x18306a0c3  test    al, al
0x18306a0c5  jnz     short loc_18306A0D0
0x18306a0c7  xor     ecx, ecx; bool
0x18306a0c9  call    ?SetExitAllThreads@@YAX_N@Z; SetExitAllThreads(bool)
0x18306a0ce  jmp     short loc_18306A0D7
0x18306a0d0  xor     al, al
0x18306a0d2  jmp     loc_18306A371
0x18306a0d7  test    bl, bl
0x18306a0d9  jz      short loc_18306A0E9
0x18306a0db  call    ?GetDoFakeThreading@@YA_NXZ; GetDoFakeThreading(void)
0x18306a0e0  test    al, al
0x18306a0e2  jz      short loc_18306A0E9
0x18306a0e4  mov     r14b, 1
0x18306a0e7  jmp     short loc_18306A0EC
0x18306a0e9  xor     r14b, r14b
0x18306a0ec  movsxd  rsi, esi
0x18306a0ef  mov     rbx, [rdi]
0x18306a0f2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18306a0f6  jnz     short loc_18306A0FB
0x18306a0f8  movsxd  rsi, ebx
0x18306a0fb  cmp     rsi, 1
0x18306a0ff  jnb     short loc_18306A120
0x18306a101  call    ?GetNumProcessorsToUse@@YAHXZ; GetNumProcessorsToUse(void)
0x18306a106  movsxd  rsi, eax
0x18306a109  cmp     rsi, 1
0x18306a10d  jnb     short loc_18306A120
0x18306a10f  lea     rcx, aTheNumberOfThr_0; "The number of threads specified for a c"...
0x18306a116  call    ?CxReportWarning@@YAXPEBDZZ; CxReportWarning(char const *,...)
0x18306a11b  mov     esi, 1
0x18306a120  cmp     esi, ebx
0x18306a122  jle     short loc_18306A135
0x18306a124  mov     edx, ebx
0x18306a126  lea     rcx, aTheNumberOfThr; "The number of threads specified for a c"...
0x18306a12d  call    ?CxReportWarning@@YAXPEBDZZ; CxReportWarning(char const *,...)
0x18306a132  movsxd  rsi, ebx
0x18306a135  test    r14b, r14b
0x18306a138  jnz     loc_18306A2C7
0x18306a13e  cmp     [rdi+9], r14b
0x18306a142  jnz     loc_18306A2C7
0x18306a148  movsxd  rax, esi
0x18306a14b  add     cs:?m_iTotalNumThreadsExecuting@CxThreadManager@@0_KA, rax; unsigned __int64 CxThreadManager::m_iTotalNumThreadsExecuting
0x18306a152  mov     byte ptr [rdi+9], 1
0x18306a156  xor     r14d, r14d
0x18306a159  mov     ebx, r14d
0x18306a15c  nop     dword ptr [rax+00h]
0x18306a160  cmp     rbx, rsi
0x18306a163  jnb     short loc_18306A1BA
0x18306a165  lea     rcx, [rbx+rbx*8]
0x18306a169  mov     rax, [rdi+20h]
0x18306a16d  lea     r15, [rax+rcx*8]
0x18306a171  mov     rcx, [r15+18h]; hEvent
0x18306a175  call    cs:__imp_ResetEvent
0x18306a17b  test    eax, eax
0x18306a17d  setnz   al
0x18306a180  test    al, al
0x18306a182  jnz     short loc_18306A193
0x18306a184  mov     rdx, rbx
0x18306a187  lea     rcx, aFailedToResetR; "Failed to reset run completed event for"...
0x18306a18e  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x18306a193  mov     rcx, [r15+20h]; hEvent
0x18306a197  call    cs:__imp_SetEvent
0x18306a19d  test    eax, eax
0x18306a19f  setnz   al
0x18306a1a2  test    al, al
0x18306a1a4  jnz     short loc_18306A1B5
0x18306a1a6  mov     rdx, rbx
0x18306a1a9  lea     rcx, aFailedToResume; "Failed To resume thread number '%d'."
0x18306a1b0  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x18306a1b5  inc     rbx
0x18306a1b8  jmp     short loc_18306A160
0x18306a1ba  mov     dword ptr [rsp+0A8h+Buffer], r14d
0x18306a1bf  movzx   r8d, r12b; int
0x18306a1c3  lea     rax, [rsp+0A8h+Buffer]
0x18306a1c8  mov     [rsp+0A8h+lpBuffer], rax; unsigned int *
0x18306a1cd  mov     r9d, r13d; unsigned int
0x18306a1d0  mov     rdx, [rdi+28h]; void **
0x18306a1d4  mov     ecx, esi; unsigned int
0x18306a1d6  call    ?WaitForMultipleObjects@WaitHelper@@SAKKPEBQEAXHKAEAK@Z; WaitHelper::WaitForMultipleObjects(ulong,void * const *,int,ulong,ulong &)
0x18306a1db  mov     r12d, eax
0x18306a1de  mov     rbx, r14
0x18306a1e1  cmp     rbx, rsi
0x18306a1e4  jnb     short loc_18306A23B
0x18306a1e6  lea     rcx, [rbx+rbx*8]
0x18306a1ea  mov     rax, [rdi+20h]
0x18306a1ee  lea     r15, [rax+rcx*8]
0x18306a1f2  mov     rcx, [r15+20h]; hEvent
0x18306a1f6  call    cs:__imp_ResetEvent
0x18306a1fc  test    eax, eax
0x18306a1fe  setnz   al
0x18306a201  test    al, al
0x18306a203  jnz     short loc_18306A214
0x18306a205  mov     rdx, rbx
0x18306a208  lea     rcx, aFailedToResetS; "Failed to reset start event for thread "...
0x18306a20f  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x18306a214  mov     rcx, [r15+18h]; hEvent
0x18306a218  call    cs:__imp_ResetEvent
0x18306a21e  test    eax, eax
0x18306a220  setnz   al
0x18306a223  test    al, al
0x18306a225  jnz     short loc_18306A236
0x18306a227  mov     rdx, rbx
0x18306a22a  lea     rcx, aFailedToResetR; "Failed to reset run completed event for"...
0x18306a231  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x18306a236  inc     rbx
0x18306a239  jmp     short loc_18306A1E1
0x18306a23b  cmp     r12d, 102h
0x18306a242  jnz     short loc_18306A252
0x18306a244  lea     rcx, aWaitTimeoutErr; "WAIT_TIMEOUT error. Threads failed to r"...
0x18306a24b  call    ?CxPrintf@@YAXPEBDZZ; CxPrintf(char const *,...)
0x18306a250  jmp     short loc_18306A2BB
0x18306a252  cmp     r12d, 0FFFFFFFFh
0x18306a256  jnz     short loc_18306A2A6
0x18306a258  call    cs:__imp_GetLastError
0x18306a25e  mov     r8d, eax; dwMessageId
0x18306a261  mov     [rsp+0A8h+Arguments], r14; Arguments
0x18306a266  mov     [rsp+0A8h+nSize], r14d; nSize
0x18306a26b  lea     rax, [rsp+0A8h+Buffer]
0x18306a270  mov     [rsp+0A8h+lpBuffer], rax; lpBuffer
0x18306a275  xor     edx, edx; lpSource
0x18306a277  mov     ecx, 1300h; dwFlags
0x18306a27c  mov     r9d, 400h; dwLanguageId
0x18306a282  call    cs:__imp_FormatMessageA
0x18306a288  mov     rdx, qword ptr [rsp+0A8h+Buffer]
0x18306a28d  lea     rcx, aWaitFailedS; "WAIT FAILED: %s\n"
0x18306a294  call    ?CxPrintf@@YAXPEBDZZ; CxPrintf(char const *,...)
0x18306a299  mov     rcx, qword ptr [rsp+0A8h+Buffer]; hMem
0x18306a29e  call    cs:__imp_LocalFree
0x18306a2a4  jmp     short loc_18306A2BB
0x18306a2a6  cmp     r12d, 80h
0x18306a2ad  jnz     short loc_18306A2BB
0x18306a2af  lea     rcx, aWaitAbandonedE; "WAIT_ABANDONED error. Mutex signaled be"...
0x18306a2b6  call    ?CxPrintf@@YAXPEBDZZ; CxPrintf(char const *,...)
0x18306a2bb  movsxd  rax, esi
0x18306a2be  sub     cs:?m_iTotalNumThreadsExecuting@CxThreadManager@@0_KA, rax; unsigned __int64 CxThreadManager::m_iTotalNumThreadsExecuting
0x18306a2c5  jmp     short loc_18306A30D
0x18306a2c7  mov     byte ptr [rdi+9], 1
0x18306a2cb  call    ?GetDoFakeThreading@@YA_NXZ; GetDoFakeThreading(void)
0x18306a2d0  test    al, al
0x18306a2d2  jz      short loc_18306A2DB
0x18306a2d4  mov     cl, 1; bool
0x18306a2d6  call    ?SetDoingFakeThreading@@YAX_N@Z; SetDoingFakeThreading(bool)
0x18306a2db  xor     r14d, r14d
0x18306a2de  mov     ebx, r14d
0x18306a2e1  cmp     rbx, rsi
0x18306a2e4  jnb     short loc_18306A2FC
0x18306a2e6  lea     rcx, [rbx+rbx*8]
0x18306a2ea  mov     rax, [rdi+20h]
0x18306a2ee  lea     rcx, [rax+rcx*8]; struct CxThreadInfo *
0x18306a2f2  call    ?ExecThreadProc@@YAIPEAUCxThreadInfo@@@Z; ExecThreadProc(CxThreadInfo *)
0x18306a2f7  inc     rbx
0x18306a2fa  jmp     short loc_18306A2E1
0x18306a2fc  call    ?GetDoingFakeThreading@@YA_NXZ; GetDoingFakeThreading(void)
0x18306a301  test    al, al
0x18306a303  jz      short loc_18306A30D
0x18306a305  xor     ecx, ecx; bool
0x18306a307  call    ?SetDoingFakeThreading@@YAX_N@Z; SetDoingFakeThreading(bool)
0x18306a30c  nop
0x18306a30d  jmp     short loc_18306A317
0x18306a30f  mov     rdi, [rsp+0A8h+var_68]
0x18306a314  xor     r14d, r14d
0x18306a317  mov     bl, 1
0x18306a319  mov     byte ptr [rdi+9], 0
0x18306a31d  call    ?GetExitAllThreads@@YA_NXZ; GetExitAllThreads(void)
0x18306a322  cmp     al, bl
0x18306a324  jnz     short loc_18306A339
0x18306a326  cmp     cs:?m_iTotalNumThreadsExecuting@CxThreadManager@@0_KA, 0; unsigned __int64 CxThreadManager::m_iTotalNumThreadsExecuting
0x18306a32e  jnz     short loc_18306A339
0x18306a330  xor     ecx, ecx; bool
0x18306a332  call    ?SetExitAllThreads@@YAX_N@Z; SetExitAllThreads(bool)
0x18306a337  xor     bl, bl
0x18306a339  mov     r8, r14
0x18306a33c  cmp     qword ptr [rdi], 0
0x18306a340  jbe     short loc_18306A36E
0x18306a342  mov     rdx, r14
0x18306a345  nop     word ptr [rax+rax+00000000h]
0x18306a350  mov     rcx, [rdi+20h]
0x18306a354  mov     [rcx+rdx+38h], r14
0x18306a359  mov     rcx, [rdi+20h]
0x18306a35d  mov     byte ptr [rcx+rdx+28h], 0
0x18306a362  inc     r8
0x18306a365  lea     rdx, [rdx+48h]
0x18306a369  cmp     r8, [rdi]
0x18306a36c  jb      short loc_18306A350
0x18306a36e  movzx   eax, bl
0x18306a371  mov     rcx, [rsp+0A8h+var_48]
0x18306a376  xor     rcx, rsp; StackCookie
0x18306a379  call    __security_check_cookie
0x18306a37e  add     rsp, 70h
0x18306a382  pop     r15
0x18306a384  pop     r14
0x18306a386  pop     r13
0x18306a388  pop     r12
0x18306a38a  pop     rdi
0x18306a38b  pop     rsi
0x18306a38c  pop     rbx
0x18306a38d  retn
```
