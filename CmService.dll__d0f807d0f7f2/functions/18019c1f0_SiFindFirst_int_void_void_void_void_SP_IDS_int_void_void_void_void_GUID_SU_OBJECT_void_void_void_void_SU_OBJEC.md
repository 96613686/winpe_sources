# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x18019c1f0`
- end: `0x18019c3fd`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `525`
- prototype: `void *__fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, HLOCAL hMem, void *, struct _SU_OBJECT **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180088c10`
- `0x1801a1ad4`

## callees

- `0x18019bfbc`
- `0x18019c100`
- `0x18019c1f0`
- `0x18019c550`
- `0x18019c5dc`
- `0x18019c638`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18019c35d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18019c35d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18019c33a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18019c33a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18019c378`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18019c378`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18019c3af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18019c3af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18019c219`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18019c219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c2c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c2c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019c298`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019c298`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019c27d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019c27d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019c24c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019c24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019c3c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019c3c3`

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
0x18019c1f0  push    rbp
0x18019c1f2  push    rbx
0x18019c1f3  push    rsi
0x18019c1f4  push    rdi
0x18019c1f5  push    r12
0x18019c1f7  push    r13
0x18019c1f9  push    r14
0x18019c1fb  push    r15
0x18019c1fd  lea     rbp, [rsp-7]
0x18019c202  sub     rsp, 0A8h
0x18019c209  mov     r13, rcx
0x18019c20c  mov     rdi, r9
0x18019c20f  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x18019c213  mov     rsi, r8
0x18019c216  mov     r14, rdx
0x18019c219  call    cs:__imp_InitializeCriticalSection
0x18019c220  nop     dword ptr [rax+rax+00h]
0x18019c225  mov     r12, [rbp+3Fh+arg_30]
0x18019c229  xor     eax, eax
0x18019c22b  mov     [rbp+3Fh+TokenHandle], rax
0x18019c22f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18019c233  mov     [rbp+3Fh+var_80], rax
0x18019c237  mov     [rbp+3Fh+var_78], eax
0x18019c23a  lea     edx, [rax+10h]; uBytes
0x18019c23d  mov     [rbp+3Fh+var_48], rax
0x18019c241  lea     ecx, [rax+40h]; uFlags
0x18019c244  mov     [rbp+3Fh+hMem], rax
0x18019c248  mov     [r12], rax
0x18019c24c  call    cs:__imp_LocalAlloc
0x18019c253  nop     dword ptr [rax+rax+00h]
0x18019c258  mov     rbx, rax
0x18019c25b  test    rax, rax
0x18019c25e  jnz     short loc_18019C276
0x18019c260  mov     ecx, 5AAh; dwErrCode
0x18019c265  call    cs:__imp_SetLastError
0x18019c26c  nop     dword ptr [rax+rax+00h]
0x18019c271  jmp     loc_18019C3DC
0x18019c276  mov     [rax+8], rbx
0x18019c27a  mov     [rax], rbx
0x18019c27d  call    cs:__imp_GetCurrentThread
0x18019c284  nop     dword ptr [rax+rax+00h]
0x18019c289  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x18019c28d  xor     r8d, r8d; OpenAsSelf
0x18019c290  mov     rcx, rax; ThreadHandle
0x18019c293  mov     edx, 2000Ch; DesiredAccess
0x18019c298  call    cs:__imp_OpenThreadToken
0x18019c29f  nop     dword ptr [rax+rax+00h]
0x18019c2a4  test    eax, eax
0x18019c2a6  jnz     short loc_18019C2CD
0x18019c2a8  call    cs:__imp_GetLastError
0x18019c2af  nop     dword ptr [rax+rax+00h]
0x18019c2b4  cmp     eax, 3F0h
0x18019c2b9  jnz     loc_18019C3D4
0x18019c2bf  xor     ecx, ecx; dwErrCode
0x18019c2c1  call    cs:__imp_SetLastError
0x18019c2c8  nop     dword ptr [rax+rax+00h]
0x18019c2cd  lea     rax, [rbp+3Fh+var_80]
0x18019c2d1  xor     r9d, r9d
0x18019c2d4  mov     [rsp+0E0h+var_C0], rax
0x18019c2d9  xor     r8d, r8d
0x18019c2dc  mov     rax, r13
0x18019c2df  mov     rdx, rdi
0x18019c2e2  mov     rcx, rsi
0x18019c2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c2ea  xor     r13d, r13d
0x18019c2ed  test    eax, eax
0x18019c2ef  jz      loc_18019C3D4
0x18019c2f5  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x18019c2f9  mov     [rbp+3Fh+var_70], r14
0x18019c2fd  mov     [rbp+3Fh+var_68], rsi
0x18019c301  mov     [rbp+3Fh+var_60], rdi
0x18019c305  mov     [rbp+3Fh+var_58], r13
0x18019c309  mov     [rbp+3Fh+var_50], r13
0x18019c30d  mov     [rbp+3Fh+var_48], rbx
0x18019c311  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x18019c316  mov     r14, [rbp+3Fh+hMem]
0x18019c31a  test    eax, eax
0x18019c31c  jz      loc_18019C3BB
0x18019c322  cmp     [r14+2Eh], r13b
0x18019c326  jnz     short loc_18019C386
0x18019c328  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18019c32f  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x18019c333  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18019c33a  call    cs:__imp_CreateThreadpoolWork
0x18019c341  nop     dword ptr [rax+rax+00h]
0x18019c346  mov     rdi, rax
0x18019c349  test    rax, rax
0x18019c34c  jz      short loc_18019C3BB
0x18019c34e  mov     rcx, [rbp+3Fh+var_80]
0x18019c352  mov     esi, r13d
0x18019c355  cmp     [rcx], r13d
0x18019c358  jbe     short loc_18019C373
0x18019c35a  mov     rcx, rdi; pwk
0x18019c35d  call    cs:__imp_SubmitThreadpoolWork
0x18019c364  nop     dword ptr [rax+rax+00h]
0x18019c369  mov     rcx, [rbp+3Fh+var_80]
0x18019c36d  inc     esi
0x18019c36f  cmp     esi, [rcx]
0x18019c371  jb      short loc_18019C35A
0x18019c373  xor     edx, edx; fCancelPendingCallbacks
0x18019c375  mov     rcx, rdi; pwk
0x18019c378  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18019c37f  nop     dword ptr [rax+rax+00h]
0x18019c384  jmp     short loc_18019C392
0x18019c386  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x18019c38a  mov     rdi, r13
0x18019c38d  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x18019c392  mov     rdx, r12; struct _SU_OBJECT **
0x18019c395  mov     rcx, rbx; void *
0x18019c398  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x18019c39d  test    eax, eax
0x18019c39f  jz      short loc_18019C3A7
0x18019c3a1  mov     r15, rbx
0x18019c3a4  mov     rbx, r13
0x18019c3a7  test    rdi, rdi
0x18019c3aa  jz      short loc_18019C3BB
0x18019c3ac  mov     rcx, rdi; pwk
0x18019c3af  call    cs:__imp_CloseThreadpoolWork
0x18019c3b6  nop     dword ptr [rax+rax+00h]
0x18019c3bb  test    r14, r14
0x18019c3be  jz      short loc_18019C3CF
0x18019c3c0  mov     rcx, r14; hMem
0x18019c3c3  call    cs:__imp_LocalFree
0x18019c3ca  nop     dword ptr [rax+rax+00h]
0x18019c3cf  test    rbx, rbx
0x18019c3d2  jz      short loc_18019C3DC
0x18019c3d4  mov     rcx, rbx; hMem
0x18019c3d7  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x18019c3dc  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x18019c3e0  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x18019c3e5  mov     rax, r15
0x18019c3e8  add     rsp, 0A8h
0x18019c3ef  pop     r15
0x18019c3f1  pop     r14
0x18019c3f3  pop     r13
0x18019c3f5  pop     r12
0x18019c3f7  pop     rdi
0x18019c3f8  pop     rsi
0x18019c3f9  pop     rbx
0x18019c3fa  pop     rbp
0x18019c3fb  retn
```
