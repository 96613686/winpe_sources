# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x18019c360`
- end: `0x18019c56d`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `525`
- prototype: `void *__fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, HLOCAL hMem, void *, struct _SU_OBJECT **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180088c10`
- `0x1801a1c44`

## callees

- `0x18019c12c`
- `0x18019c270`
- `0x18019c360`
- `0x18019c6c0`
- `0x18019c74c`
- `0x18019c7a8`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18019c4cd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18019c4cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18019c4aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18019c4aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18019c4e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18019c4e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18019c51f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18019c51f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18019c389`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18019c389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c431`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019c408`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019c408`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019c3ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019c3ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019c3bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019c3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019c533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019c533`

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
0x18019c360  push    rbp
0x18019c362  push    rbx
0x18019c363  push    rsi
0x18019c364  push    rdi
0x18019c365  push    r12
0x18019c367  push    r13
0x18019c369  push    r14
0x18019c36b  push    r15
0x18019c36d  lea     rbp, [rsp-7]
0x18019c372  sub     rsp, 0A8h
0x18019c379  mov     r13, rcx
0x18019c37c  mov     rdi, r9
0x18019c37f  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x18019c383  mov     rsi, r8
0x18019c386  mov     r14, rdx
0x18019c389  call    cs:__imp_InitializeCriticalSection
0x18019c390  nop     dword ptr [rax+rax+00h]
0x18019c395  mov     r12, [rbp+3Fh+arg_30]
0x18019c399  xor     eax, eax
0x18019c39b  mov     [rbp+3Fh+TokenHandle], rax
0x18019c39f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18019c3a3  mov     [rbp+3Fh+var_80], rax
0x18019c3a7  mov     [rbp+3Fh+var_78], eax
0x18019c3aa  lea     edx, [rax+10h]; uBytes
0x18019c3ad  mov     [rbp+3Fh+var_48], rax
0x18019c3b1  lea     ecx, [rax+40h]; uFlags
0x18019c3b4  mov     [rbp+3Fh+hMem], rax
0x18019c3b8  mov     [r12], rax
0x18019c3bc  call    cs:__imp_LocalAlloc
0x18019c3c3  nop     dword ptr [rax+rax+00h]
0x18019c3c8  mov     rbx, rax
0x18019c3cb  test    rax, rax
0x18019c3ce  jnz     short loc_18019C3E6
0x18019c3d0  mov     ecx, 5AAh; dwErrCode
0x18019c3d5  call    cs:__imp_SetLastError
0x18019c3dc  nop     dword ptr [rax+rax+00h]
0x18019c3e1  jmp     loc_18019C54C
0x18019c3e6  mov     [rax+8], rbx
0x18019c3ea  mov     [rax], rbx
0x18019c3ed  call    cs:__imp_GetCurrentThread
0x18019c3f4  nop     dword ptr [rax+rax+00h]
0x18019c3f9  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x18019c3fd  xor     r8d, r8d; OpenAsSelf
0x18019c400  mov     rcx, rax; ThreadHandle
0x18019c403  mov     edx, 2000Ch; DesiredAccess
0x18019c408  call    cs:__imp_OpenThreadToken
0x18019c40f  nop     dword ptr [rax+rax+00h]
0x18019c414  test    eax, eax
0x18019c416  jnz     short loc_18019C43D
0x18019c418  call    cs:__imp_GetLastError
0x18019c41f  nop     dword ptr [rax+rax+00h]
0x18019c424  cmp     eax, 3F0h
0x18019c429  jnz     loc_18019C544
0x18019c42f  xor     ecx, ecx; dwErrCode
0x18019c431  call    cs:__imp_SetLastError
0x18019c438  nop     dword ptr [rax+rax+00h]
0x18019c43d  lea     rax, [rbp+3Fh+var_80]
0x18019c441  xor     r9d, r9d
0x18019c444  mov     [rsp+0E0h+var_C0], rax
0x18019c449  xor     r8d, r8d
0x18019c44c  mov     rax, r13
0x18019c44f  mov     rdx, rdi
0x18019c452  mov     rcx, rsi
0x18019c455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c45a  xor     r13d, r13d
0x18019c45d  test    eax, eax
0x18019c45f  jz      loc_18019C544
0x18019c465  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x18019c469  mov     [rbp+3Fh+var_70], r14
0x18019c46d  mov     [rbp+3Fh+var_68], rsi
0x18019c471  mov     [rbp+3Fh+var_60], rdi
0x18019c475  mov     [rbp+3Fh+var_58], r13
0x18019c479  mov     [rbp+3Fh+var_50], r13
0x18019c47d  mov     [rbp+3Fh+var_48], rbx
0x18019c481  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x18019c486  mov     r14, [rbp+3Fh+hMem]
0x18019c48a  test    eax, eax
0x18019c48c  jz      loc_18019C52B
0x18019c492  cmp     [r14+2Eh], r13b
0x18019c496  jnz     short loc_18019C4F6
0x18019c498  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18019c49f  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x18019c4a3  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18019c4aa  call    cs:__imp_CreateThreadpoolWork
0x18019c4b1  nop     dword ptr [rax+rax+00h]
0x18019c4b6  mov     rdi, rax
0x18019c4b9  test    rax, rax
0x18019c4bc  jz      short loc_18019C52B
0x18019c4be  mov     rcx, [rbp+3Fh+var_80]
0x18019c4c2  mov     esi, r13d
0x18019c4c5  cmp     [rcx], r13d
0x18019c4c8  jbe     short loc_18019C4E3
0x18019c4ca  mov     rcx, rdi; pwk
0x18019c4cd  call    cs:__imp_SubmitThreadpoolWork
0x18019c4d4  nop     dword ptr [rax+rax+00h]
0x18019c4d9  mov     rcx, [rbp+3Fh+var_80]
0x18019c4dd  inc     esi
0x18019c4df  cmp     esi, [rcx]
0x18019c4e1  jb      short loc_18019C4CA
0x18019c4e3  xor     edx, edx; fCancelPendingCallbacks
0x18019c4e5  mov     rcx, rdi; pwk
0x18019c4e8  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18019c4ef  nop     dword ptr [rax+rax+00h]
0x18019c4f4  jmp     short loc_18019C502
0x18019c4f6  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x18019c4fa  mov     rdi, r13
0x18019c4fd  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x18019c502  mov     rdx, r12; struct _SU_OBJECT **
0x18019c505  mov     rcx, rbx; void *
0x18019c508  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x18019c50d  test    eax, eax
0x18019c50f  jz      short loc_18019C517
0x18019c511  mov     r15, rbx
0x18019c514  mov     rbx, r13
0x18019c517  test    rdi, rdi
0x18019c51a  jz      short loc_18019C52B
0x18019c51c  mov     rcx, rdi; pwk
0x18019c51f  call    cs:__imp_CloseThreadpoolWork
0x18019c526  nop     dword ptr [rax+rax+00h]
0x18019c52b  test    r14, r14
0x18019c52e  jz      short loc_18019C53F
0x18019c530  mov     rcx, r14; hMem
0x18019c533  call    cs:__imp_LocalFree
0x18019c53a  nop     dword ptr [rax+rax+00h]
0x18019c53f  test    rbx, rbx
0x18019c542  jz      short loc_18019C54C
0x18019c544  mov     rcx, rbx; hMem
0x18019c547  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x18019c54c  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x18019c550  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x18019c555  mov     rax, r15
0x18019c558  add     rsp, 0A8h
0x18019c55f  pop     r15
0x18019c561  pop     r14
0x18019c563  pop     r13
0x18019c565  pop     r12
0x18019c567  pop     rdi
0x18019c568  pop     rsi
0x18019c569  pop     rbx
0x18019c56a  pop     rbp
0x18019c56b  retn
```
