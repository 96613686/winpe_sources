# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x1801afb94`
- end: `0x1801afd58`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `452`
- prototype: `void *__fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, HLOCAL hMem, void *, struct _SU_OBJECT **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1801b2510`
- `0x1801b590c`
- `0x1801ba890`
- `0x1801bc28c`

## callees

- `0x1801af890`
- `0x1801af998`
- `0x1801afb94`
- `0x1801afefc`
- `0x1801aff74`
- `0x1801affcc`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801afc2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801afc2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afbfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afc41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afbfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afc41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801afc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801afc0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801afc24`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801afc24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801afbbd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801afbbd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801afcb4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801afcb4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801afcd1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801afcd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801afce6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801afce6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801afd17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801afd17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801afd25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801afd25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801afbea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801afbea`

## pseudocode

```c
__int64 __fastcall SiFindFirst(
        int (*a1)(void *, void *, void *, void *, struct _SP_IDS **),
        int (*a2)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **),
        void *a3,
        void *a4,
        _BYTE *hMem,
        void *a6,
        struct _SU_OBJECT **a7)
{
  struct _SU_OBJECT **v11; // r12
  __int64 v12; // r15
  _QWORD *v13; // rax
  void *v14; // rbx
  HANDLE CurrentThread; // rax
  int Control; // eax
  HLOCAL v17; // r14
  struct _TP_WORK *v18; // rdi
  unsigned int i; // esi
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+30h] [rbp-71h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-49h] BYREF
  unsigned int *v23; // [rsp+60h] [rbp-41h] BYREF
  int v24; // [rsp+68h] [rbp-39h]
  int (*v25)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **); // [rsp+70h] [rbp-31h]
  void *v26; // [rsp+78h] [rbp-29h]
  void *v27; // [rsp+80h] [rbp-21h]
  __int64 v28; // [rsp+88h] [rbp-19h]
  __int64 v29; // [rsp+90h] [rbp-11h]
  void *v30; // [rsp+98h] [rbp-9h]

  InitializeCriticalSection(&CriticalSection);
  v11 = a7;
  TokenHandle = 0;
  v12 = -1;
  v23 = 0;
  v24 = 0;
  v30 = 0;
  hMem = 0;
  *a7 = 0;
  v13 = LocalAlloc(0x40u, 0x10u);
  v14 = v13;
  if ( !v13 )
  {
    SetLastError(0x5AAu);
    goto LABEL_22;
  }
  v13[1] = v13;
  *v13 = v13;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
LABEL_21:
      SuFindClose(v14);
      goto LABEL_22;
    }
    SetLastError(0);
  }
  if ( !((unsigned int (__fastcall *)(void *, void *, _QWORD, _QWORD, unsigned int **))a1)(a3, a4, 0, 0, &v23) )
    goto LABEL_21;
  v25 = a2;
  v26 = a3;
  v27 = a4;
  v28 = 0;
  v29 = 0;
  v30 = v14;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&hMem);
  v17 = hMem;
  if ( !Control )
    goto LABEL_18;
  if ( hMem[46] )
  {
    v18 = 0;
    SI_GET_CONTEXT::Callback(&CriticalSection);
  }
  else
  {
    v18 = CreateThreadpoolWork(SiFindFirstCallback, &CriticalSection, &ThreadpoolEnv);
    if ( !v18 )
      goto LABEL_18;
    for ( i = 0; i < *v23; ++i )
      SubmitThreadpoolWork(v18);
    WaitForThreadpoolWorkCallbacks(v18, 0);
  }
  if ( (unsigned int)SuFindNext(v14, v11) )
  {
    v12 = (__int64)v14;
    v14 = 0;
  }
  if ( v18 )
    CloseThreadpoolWork(v18);
LABEL_18:
  if ( v17 )
    LocalFree(v17);
  if ( v14 )
    goto LABEL_21;
LABEL_22:
  SI_GET_CONTEXT::~SI_GET_CONTEXT((SI_GET_CONTEXT *)&CriticalSection);
  return v12;
}

```

## disassembly

```asm
0x1801afb94  push    rbp
0x1801afb96  push    rbx
0x1801afb97  push    rsi
0x1801afb98  push    rdi
0x1801afb99  push    r12
0x1801afb9b  push    r13
0x1801afb9d  push    r14
0x1801afb9f  push    r15
0x1801afba1  lea     rbp, [rsp-7]
0x1801afba6  sub     rsp, 0A8h
0x1801afbad  mov     r13, rcx
0x1801afbb0  mov     rdi, r9
0x1801afbb3  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x1801afbb7  mov     rsi, r8
0x1801afbba  mov     r14, rdx
0x1801afbbd  call    cs:__imp_InitializeCriticalSection
0x1801afbc3  mov     r12, [rbp+3Fh+arg_30]
0x1801afbc7  xor     eax, eax
0x1801afbc9  mov     [rbp+3Fh+TokenHandle], rax
0x1801afbcd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801afbd1  mov     [rbp+3Fh+var_80], rax
0x1801afbd5  mov     [rbp+3Fh+var_78], eax
0x1801afbd8  lea     edx, [rax+10h]; uBytes
0x1801afbdb  mov     [rbp+3Fh+var_48], rax
0x1801afbdf  lea     ecx, [rax+40h]; uFlags
0x1801afbe2  mov     [rbp+3Fh+hMem], rax
0x1801afbe6  mov     [r12], rax
0x1801afbea  call    cs:__imp_LocalAlloc
0x1801afbf0  mov     rbx, rax
0x1801afbf3  test    rax, rax
0x1801afbf6  jnz     short loc_1801AFC08
0x1801afbf8  mov     ecx, 5AAh; dwErrCode
0x1801afbfd  call    cs:__imp_SetLastError
0x1801afc03  jmp     loc_1801AFD38
0x1801afc08  mov     [rax+8], rbx
0x1801afc0c  mov     [rax], rbx
0x1801afc0f  call    cs:__imp_GetCurrentThread
0x1801afc15  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x1801afc19  xor     r8d, r8d; OpenAsSelf
0x1801afc1c  mov     rcx, rax; ThreadHandle
0x1801afc1f  mov     edx, 2000Ch; DesiredAccess
0x1801afc24  call    cs:__imp_OpenThreadToken
0x1801afc2a  test    eax, eax
0x1801afc2c  jnz     short loc_1801AFC47
0x1801afc2e  call    cs:__imp_GetLastError
0x1801afc34  cmp     eax, 3F0h
0x1801afc39  jnz     loc_1801AFD30
0x1801afc3f  xor     ecx, ecx; dwErrCode
0x1801afc41  call    cs:__imp_SetLastError
0x1801afc47  lea     rax, [rbp+3Fh+var_80]
0x1801afc4b  xor     r9d, r9d
0x1801afc4e  mov     [rsp+0E0h+var_C0], rax
0x1801afc53  xor     r8d, r8d
0x1801afc56  mov     rax, r13
0x1801afc59  mov     rdx, rdi
0x1801afc5c  mov     rcx, rsi
0x1801afc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc64  xor     r13d, r13d
0x1801afc67  test    eax, eax
0x1801afc69  jz      loc_1801AFD30
0x1801afc6f  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x1801afc73  mov     [rbp+3Fh+var_70], r14
0x1801afc77  mov     [rbp+3Fh+var_68], rsi
0x1801afc7b  mov     [rbp+3Fh+var_60], rdi
0x1801afc7f  mov     [rbp+3Fh+var_58], r13
0x1801afc83  mov     [rbp+3Fh+var_50], r13
0x1801afc87  mov     [rbp+3Fh+var_48], rbx
0x1801afc8b  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x1801afc90  mov     r14, [rbp+3Fh+hMem]
0x1801afc94  test    eax, eax
0x1801afc96  jz      loc_1801AFD1D
0x1801afc9c  cmp     [r14+2Eh], r13b
0x1801afca0  jnz     short loc_1801AFCEE
0x1801afca2  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801afca9  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x1801afcad  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801afcb4  call    cs:__imp_CreateThreadpoolWork
0x1801afcba  mov     rdi, rax
0x1801afcbd  test    rax, rax
0x1801afcc0  jz      short loc_1801AFD1D
0x1801afcc2  mov     rcx, [rbp+3Fh+var_80]
0x1801afcc6  mov     esi, r13d
0x1801afcc9  cmp     [rcx], r13d
0x1801afccc  jbe     short loc_1801AFCE1
0x1801afcce  mov     rcx, rdi; pwk
0x1801afcd1  call    cs:__imp_SubmitThreadpoolWork
0x1801afcd7  mov     rcx, [rbp+3Fh+var_80]
0x1801afcdb  inc     esi
0x1801afcdd  cmp     esi, [rcx]
0x1801afcdf  jb      short loc_1801AFCCE
0x1801afce1  xor     edx, edx; fCancelPendingCallbacks
0x1801afce3  mov     rcx, rdi; pwk
0x1801afce6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801afcec  jmp     short loc_1801AFCFA
0x1801afcee  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x1801afcf2  mov     rdi, r13
0x1801afcf5  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x1801afcfa  mov     rdx, r12; struct _SU_OBJECT **
0x1801afcfd  mov     rcx, rbx; void *
0x1801afd00  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x1801afd05  test    eax, eax
0x1801afd07  jz      short loc_1801AFD0F
0x1801afd09  mov     r15, rbx
0x1801afd0c  mov     rbx, r13
0x1801afd0f  test    rdi, rdi
0x1801afd12  jz      short loc_1801AFD1D
0x1801afd14  mov     rcx, rdi; pwk
0x1801afd17  call    cs:__imp_CloseThreadpoolWork
0x1801afd1d  test    r14, r14
0x1801afd20  jz      short loc_1801AFD2B
0x1801afd22  mov     rcx, r14; hMem
0x1801afd25  call    cs:__imp_LocalFree
0x1801afd2b  test    rbx, rbx
0x1801afd2e  jz      short loc_1801AFD38
0x1801afd30  mov     rcx, rbx; hMem
0x1801afd33  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x1801afd38  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x1801afd3c  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x1801afd41  mov     rax, r15
0x1801afd44  add     rsp, 0A8h
0x1801afd4b  pop     r15
0x1801afd4d  pop     r14
0x1801afd4f  pop     r13
0x1801afd51  pop     r12
0x1801afd53  pop     rdi
0x1801afd54  pop     rsi
0x1801afd55  pop     rbx
0x1801afd56  pop     rbp
0x1801afd57  retn
```
