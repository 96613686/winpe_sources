# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x140007de4`
- end: `0x140007fa8`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `452`
- prototype: `__int64 __fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, _BYTE *hMem, void *, struct _SU_OBJECT **)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140002e4c`
- `0x14000df58`
- `0x14000e1c8`
- `0x140012ca0`
- `0x140019498`

## callees

- `0x140004854`
- `0x140004dd8`
- `0x140007de4`
- `0x1400083dc`
- `0x140008454`
- `0x1400084ac`
- `0x140020010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140007e74`
- `ADVAPI32!OpenThreadToken` at `0x140007e74`
- `KERNEL32!LocalFree` at `0x140007f75`
- `KERNEL32!LocalFree` at `0x140007f75`
- `KERNEL32!CreateThreadpoolWork` at `0x140007f04`
- `KERNEL32!CreateThreadpoolWork` at `0x140007f04`
- `KERNEL32!SubmitThreadpoolWork` at `0x140007f21`
- `KERNEL32!SubmitThreadpoolWork` at `0x140007f21`
- `KERNEL32!SetLastError` at `0x140007e4d`
- `KERNEL32!SetLastError` at `0x140007e91`
- `KERNEL32!SetLastError` at `0x140007e4d`
- `KERNEL32!SetLastError` at `0x140007e91`
- `KERNEL32!GetLastError` at `0x140007e7e`
- `KERNEL32!GetLastError` at `0x140007e7e`
- `KERNEL32!CloseThreadpoolWork` at `0x140007f67`
- `KERNEL32!CloseThreadpoolWork` at `0x140007f67`
- `KERNEL32!InitializeCriticalSection` at `0x140007e0d`
- `KERNEL32!InitializeCriticalSection` at `0x140007e0d`
- `KERNEL32!LocalAlloc` at `0x140007e3a`
- `KERNEL32!LocalAlloc` at `0x140007e3a`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x140007f36`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x140007f36`
- `KERNEL32!GetCurrentThread` at `0x140007e5f`
- `KERNEL32!GetCurrentThread` at `0x140007e5f`

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
  SI_GET_CONTEXT::~SI_GET_CONTEXT(&CriticalSection);
  return v12;
}

```

## disassembly

```asm
0x140007de4  push    rbp
0x140007de6  push    rbx
0x140007de7  push    rsi
0x140007de8  push    rdi
0x140007de9  push    r12
0x140007deb  push    r13
0x140007ded  push    r14
0x140007def  push    r15
0x140007df1  lea     rbp, [rsp-7]
0x140007df6  sub     rsp, 0A8h
0x140007dfd  mov     r13, rcx
0x140007e00  mov     rdi, r9
0x140007e03  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x140007e07  mov     rsi, r8
0x140007e0a  mov     r14, rdx
0x140007e0d  call    cs:__imp_InitializeCriticalSection
0x140007e13  mov     r12, [rbp+3Fh+arg_30]
0x140007e17  xor     eax, eax
0x140007e19  mov     [rbp+3Fh+TokenHandle], rax
0x140007e1d  or      r15, 0FFFFFFFFFFFFFFFFh
0x140007e21  mov     [rbp+3Fh+var_80], rax
0x140007e25  mov     [rbp+3Fh+var_78], eax
0x140007e28  lea     edx, [rax+10h]; uBytes
0x140007e2b  mov     [rbp+3Fh+var_48], rax
0x140007e2f  lea     ecx, [rax+40h]; uFlags
0x140007e32  mov     [rbp+3Fh+hMem], rax
0x140007e36  mov     [r12], rax
0x140007e3a  call    cs:__imp_LocalAlloc
0x140007e40  mov     rbx, rax
0x140007e43  test    rax, rax
0x140007e46  jnz     short loc_140007E58
0x140007e48  mov     ecx, 5AAh; dwErrCode
0x140007e4d  call    cs:__imp_SetLastError
0x140007e53  jmp     loc_140007F88
0x140007e58  mov     [rax+8], rbx
0x140007e5c  mov     [rax], rbx
0x140007e5f  call    cs:__imp_GetCurrentThread
0x140007e65  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x140007e69  xor     r8d, r8d; OpenAsSelf
0x140007e6c  mov     rcx, rax; ThreadHandle
0x140007e6f  mov     edx, 2000Ch; DesiredAccess
0x140007e74  call    cs:__imp_OpenThreadToken
0x140007e7a  test    eax, eax
0x140007e7c  jnz     short loc_140007E97
0x140007e7e  call    cs:__imp_GetLastError
0x140007e84  cmp     eax, 3F0h
0x140007e89  jnz     loc_140007F80
0x140007e8f  xor     ecx, ecx; dwErrCode
0x140007e91  call    cs:__imp_SetLastError
0x140007e97  lea     rax, [rbp+3Fh+var_80]
0x140007e9b  xor     r9d, r9d
0x140007e9e  mov     [rsp+0E0h+var_C0], rax
0x140007ea3  xor     r8d, r8d
0x140007ea6  mov     rax, r13
0x140007ea9  mov     rdx, rdi
0x140007eac  mov     rcx, rsi
0x140007eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007eb4  xor     r13d, r13d
0x140007eb7  test    eax, eax
0x140007eb9  jz      loc_140007F80
0x140007ebf  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x140007ec3  mov     [rbp+3Fh+var_70], r14
0x140007ec7  mov     [rbp+3Fh+var_68], rsi
0x140007ecb  mov     [rbp+3Fh+var_60], rdi
0x140007ecf  mov     [rbp+3Fh+var_58], r13
0x140007ed3  mov     [rbp+3Fh+var_50], r13
0x140007ed7  mov     [rbp+3Fh+var_48], rbx
0x140007edb  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x140007ee0  mov     r14, [rbp+3Fh+hMem]
0x140007ee4  test    eax, eax
0x140007ee6  jz      loc_140007F6D
0x140007eec  cmp     [r14+2Eh], r13b
0x140007ef0  jnz     short loc_140007F3E
0x140007ef2  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x140007ef9  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x140007efd  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140007f04  call    cs:__imp_CreateThreadpoolWork
0x140007f0a  mov     rdi, rax
0x140007f0d  test    rax, rax
0x140007f10  jz      short loc_140007F6D
0x140007f12  mov     rcx, [rbp+3Fh+var_80]
0x140007f16  mov     esi, r13d
0x140007f19  cmp     [rcx], r13d
0x140007f1c  jbe     short loc_140007F31
0x140007f1e  mov     rcx, rdi; pwk
0x140007f21  call    cs:__imp_SubmitThreadpoolWork
0x140007f27  mov     rcx, [rbp+3Fh+var_80]
0x140007f2b  inc     esi
0x140007f2d  cmp     esi, [rcx]
0x140007f2f  jb      short loc_140007F1E
0x140007f31  xor     edx, edx; fCancelPendingCallbacks
0x140007f33  mov     rcx, rdi; pwk
0x140007f36  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x140007f3c  jmp     short loc_140007F4A
0x140007f3e  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x140007f42  mov     rdi, r13
0x140007f45  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x140007f4a  mov     rdx, r12; struct _SU_OBJECT **
0x140007f4d  mov     rcx, rbx; void *
0x140007f50  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x140007f55  test    eax, eax
0x140007f57  jz      short loc_140007F5F
0x140007f59  mov     r15, rbx
0x140007f5c  mov     rbx, r13
0x140007f5f  test    rdi, rdi
0x140007f62  jz      short loc_140007F6D
0x140007f64  mov     rcx, rdi; pwk
0x140007f67  call    cs:__imp_CloseThreadpoolWork
0x140007f6d  test    r14, r14
0x140007f70  jz      short loc_140007F7B
0x140007f72  mov     rcx, r14; hMem
0x140007f75  call    cs:__imp_LocalFree
0x140007f7b  test    rbx, rbx
0x140007f7e  jz      short loc_140007F88
0x140007f80  mov     rcx, rbx; hMem
0x140007f83  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x140007f88  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x140007f8c  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x140007f91  mov     rax, r15
0x140007f94  add     rsp, 0A8h
0x140007f9b  pop     r15
0x140007f9d  pop     r14
0x140007f9f  pop     r13
0x140007fa1  pop     r12
0x140007fa3  pop     rdi
0x140007fa4  pop     rsi
0x140007fa5  pop     rbx
0x140007fa6  pop     rbp
0x140007fa7  retn
```
