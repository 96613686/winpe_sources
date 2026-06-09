# CxThreadManager::CxThreadManager(unsigned __int64,uint (*)(void *),bool)

- ea: `0x183069880`
- end: `0x183069b42`
- name: `??0CxThreadManager@@QEAA@_KP6AIPEAX@Z_N@Z`
- size: `706`
- prototype: `CxThreadManager *__fastcall(CxThreadManager *__hidden this, unsigned __int64, unsigned int (*)(void *), bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x182d3a3b0`

## callees

- `0x1815ce350`
- `0x182dcca70`
- `0x183069880`
- `0x1832c3a50`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x1830699c3`
- `KERNEL32!CreateEventA` at `0x183069a1d`
- `KERNEL32!CreateEventA` at `0x1830699c3`
- `KERNEL32!CreateEventA` at `0x183069a1d`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x183069aa4`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x183069aa4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1830699d1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x183069a2b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x183069ab2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1830699d1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x183069a2b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x183069ab2`

## string_xrefs

- `0x1830699f6`: `Failed to create event for Thread '%d' (errno = '%d'): '%s'.`
- `0x183069a50`: `Failed to create event for Thread '%d' (errno = '%d'): '%s'.`
- `0x183069ad7`: `Thread '%d' failed to start (errno = '%d'): '%s'.`

## pseudocode

```c
CxThreadManager *__fastcall CxThreadManager::CxThreadManager(
        CxThreadManager *this,
        unsigned __int64 a2,
        unsigned int (*a3)(void *),
        char a4)
{
  char *v7; // rax
  char *v8; // rdx
  unsigned __int64 v9; // rcx
  char *v10; // rax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rbp
  __int64 v15; // rsi
  HANDLE EventA; // rax
  int v17; // ebx
  HANDLE v18; // rax
  int v19; // ebx
  void *v20; // r9
  uintptr_t v21; // rax
  int v22; // ebx
  unsigned int ThrdAddr[4]; // [rsp+30h] [rbp-448h] BYREF
  char v25[1024]; // [rsp+40h] [rbp-438h] BYREF

  *((_BYTE *)this + 8) = a4;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  v7 = (char *)operator new(saturated_mul(a2, 0x48u));
  *(_QWORD *)ThrdAddr = v7;
  v8 = v7;
  if ( v7 )
  {
    v9 = a2;
    if ( a2 )
    {
      v10 = v7 + 24;
      do
      {
        *((_QWORD *)v10 - 3) = 0;
        *((_QWORD *)v10 - 2) = 0;
        *(_QWORD *)v10 = 0;
        v10[16] = 0;
        *((_QWORD *)v10 + 3) = -1;
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 5) = 0;
        v10 += 72;
        --v9;
      }
      while ( v9 );
    }
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 4) = v8;
  v11 = 8 * a2;
  if ( !is_mul_ok(a2, 8u) )
    v11 = -1;
  *((_QWORD *)this + 5) = operator new(v11);
  v12 = 8 * a2;
  if ( !is_mul_ok(a2, 8u) )
    v12 = -1;
  *((_QWORD *)this + 6) = operator new(v12);
  v13 = 8 * a2;
  if ( !is_mul_ok(a2, 8u) )
    v13 = -1;
  *((_QWORD *)this + 7) = operator new(v13);
  v14 = 0;
  *((_QWORD *)this + 2) = a3;
  *((_BYTE *)this + 9) = 0;
  ++CxThreadManager::m_iTotalNumThreadManagerOjbects;
  CxThreadManager::m_iTotalThreadsCount += (int)a2;
  *(_QWORD *)this = a2;
  if ( a2 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)(*((_QWORD *)this + 4) + v15 + 48) = v14;
      EventA = CreateEventA(0, 0, 0, 0);
      if ( !EventA )
      {
        v17 = *_errno();
        CxStrError(v25, 0x400u, v17);
        CxThrowError("Failed to create event for Thread '%d' (errno = '%d'): '%s'.", v14, v17, v25);
      }
      *(_QWORD *)(*((_QWORD *)this + 4) + v15 + 24) = EventA;
      *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v14) = EventA;
      v18 = CreateEventA(0, 0, 0, 0);
      if ( !v18 )
      {
        v19 = *_errno();
        CxStrError(v25, 0x400u, v19);
        CxThrowError("Failed to create event for Thread '%d' (errno = '%d'): '%s'.", v14, v19, v25);
      }
      *(_QWORD *)(*((_QWORD *)this + 4) + v15 + 32) = v18;
      *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v14) = v18;
      *(_QWORD *)(v15 + *((_QWORD *)this + 4)) = this;
      *(_QWORD *)(*((_QWORD *)this + 4) + v15 + 64) = a3;
      v20 = (void *)(v15 + *((_QWORD *)this + 4));
      ThrdAddr[0] = 0;
      v21 = _beginthreadex(0, 0, CxThreadManager::CallThreadProc, v20, 0, ThrdAddr);
      if ( !v21 )
      {
        v22 = *_errno();
        CxStrError(v25, 0x400u, v22);
        CxThrowError("Thread '%d' failed to start (errno = '%d'): '%s'.", v14, v22, v25);
      }
      *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v14++) = v21;
      *(_QWORD *)(*((_QWORD *)this + 4) + v15 + 8) = v21;
      *(_DWORD *)(*((_QWORD *)this + 4) + v15 + 16) = ThrdAddr[0];
      v15 += 72;
    }
    while ( v14 < *(_QWORD *)this );
  }
  return this;
}

```

## disassembly

```asm
0x183069880  mov     [rsp+arg_18], rbx
0x183069885  push    rbp
0x183069886  push    rsi
0x183069887  push    rdi
0x183069888  push    r12
0x18306988a  push    r15
0x18306988c  sub     rsp, 450h
0x183069893  mov     rax, cs:__security_cookie
0x18306989a  xor     rax, rsp
0x18306989d  mov     [rsp+478h+var_38], rax
0x1830698a5  xor     r12d, r12d
0x1830698a8  mov     [rcx+8], r9b
0x1830698ac  mov     rbx, rdx
0x1830698af  mov     [rcx], r12
0x1830698b2  mov     rdi, rcx
0x1830698b5  mov     [rcx+20h], r12
0x1830698b9  mov     [rcx+28h], r12
0x1830698bd  mov     eax, 48h ; 'H'
0x1830698c2  mul     rdx
0x1830698c5  mov     [rcx+30h], r12
0x1830698c9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1830698d0  mov     [rcx+38h], r12
0x1830698d4  mov     r15, r8
0x1830698d7  cmovo   rax, rsi
0x1830698db  mov     rcx, rax; unsigned __int64
0x1830698de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1830698e3  mov     qword ptr [rsp+478h+var_448], rax
0x1830698e8  mov     rdx, rax
0x1830698eb  test    rax, rax
0x1830698ee  jz      short loc_183069927
0x1830698f0  mov     rcx, rbx
0x1830698f3  test    rbx, rbx
0x1830698f6  jz      short loc_18306992A
0x1830698f8  add     rax, 18h
0x1830698fc  nop     dword ptr [rax+00h]
0x183069900  mov     [rax-18h], r12
0x183069904  mov     [rax-10h], r12
0x183069908  mov     [rax], r12
0x18306990b  mov     [rax+10h], r12b
0x18306990f  mov     [rax+18h], rsi
0x183069913  mov     [rax+20h], r12
0x183069917  mov     [rax+28h], r12
0x18306991b  lea     rax, [rax+48h]
0x18306991f  sub     rcx, 1
0x183069923  jnz     short loc_183069900
0x183069925  jmp     short loc_18306992A
0x183069927  mov     rdx, r12
0x18306992a  mov     [rdi+20h], rdx
0x18306992e  mov     eax, 8
0x183069933  mul     rbx
0x183069936  cmovo   rax, rsi
0x18306993a  mov     rcx, rax; unsigned __int64
0x18306993d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x183069942  mov     [rdi+28h], rax
0x183069946  mov     eax, 8
0x18306994b  mul     rbx
0x18306994e  cmovo   rax, rsi
0x183069952  mov     rcx, rax; unsigned __int64
0x183069955  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18306995a  mov     [rdi+30h], rax
0x18306995e  mov     eax, 8
0x183069963  mul     rbx
0x183069966  cmovo   rax, rsi
0x18306996a  mov     rcx, rax; unsigned __int64
0x18306996d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x183069972  mov     [rdi+38h], rax
0x183069976  mov     rbp, r12
0x183069979  mov     [rdi+10h], r15
0x18306997d  mov     [rdi+9], r12b
0x183069981  inc     cs:?m_iTotalNumThreadManagerOjbects@CxThreadManager@@0_KA; unsigned __int64 CxThreadManager::m_iTotalNumThreadManagerOjbects
0x183069988  movsxd  rax, ebx
0x18306998b  add     cs:?m_iTotalThreadsCount@CxThreadManager@@0_KA, rax; unsigned __int64 CxThreadManager::m_iTotalThreadsCount
0x183069992  mov     [rdi], rbx
0x183069995  test    rbx, rbx
0x183069998  jz      loc_183069B18
0x18306999e  mov     [rsp+478h+arg_10], r14
0x1830699a6  mov     rsi, r12
0x1830699a9  nop     dword ptr [rax+00000000h]
0x1830699b0  mov     rax, [rdi+20h]
0x1830699b4  xor     r9d, r9d; lpName
0x1830699b7  xor     r8d, r8d; bInitialState
0x1830699ba  xor     edx, edx; bManualReset
0x1830699bc  xor     ecx, ecx; lpEventAttributes
0x1830699be  mov     [rax+rsi+30h], rbp
0x1830699c3  call    cs:__imp_CreateEventA
0x1830699c9  mov     r14, rax
0x1830699cc  test    rax, rax
0x1830699cf  jnz     short loc_183069A02
0x1830699d1  call    cs:__imp__errno
0x1830699d7  mov     edx, 400h; unsigned __int64
0x1830699dc  lea     rcx, [rsp+478h+var_438]; char *
0x1830699e1  mov     ebx, [rax]
0x1830699e3  mov     r8d, ebx; int
0x1830699e6  call    ?CxStrError@@YAPEADPEAD_KH@Z; CxStrError(char *,unsigned __int64,int)
0x1830699eb  lea     r9, [rsp+478h+var_438]
0x1830699f0  mov     r8d, ebx
0x1830699f3  mov     rdx, rbp
0x1830699f6  lea     rcx, aFailedToCreate; "Failed to create event for Thread '%d' "...
0x1830699fd  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x183069a02  mov     rax, [rdi+20h]
0x183069a06  xor     r9d, r9d; lpName
0x183069a09  xor     r8d, r8d; bInitialState
0x183069a0c  xor     edx, edx; bManualReset
0x183069a0e  xor     ecx, ecx; lpEventAttributes
0x183069a10  mov     [rax+rsi+18h], r14
0x183069a15  mov     rax, [rdi+28h]
0x183069a19  mov     [rax+rbp*8], r14
0x183069a1d  call    cs:__imp_CreateEventA
0x183069a23  mov     r14, rax
0x183069a26  test    rax, rax
0x183069a29  jnz     short loc_183069A5C
0x183069a2b  call    cs:__imp__errno
0x183069a31  mov     edx, 400h; unsigned __int64
0x183069a36  lea     rcx, [rsp+478h+var_438]; char *
0x183069a3b  mov     ebx, [rax]
0x183069a3d  mov     r8d, ebx; int
0x183069a40  call    ?CxStrError@@YAPEADPEAD_KH@Z; CxStrError(char *,unsigned __int64,int)
0x183069a45  lea     r9, [rsp+478h+var_438]
0x183069a4a  mov     r8d, ebx
0x183069a4d  mov     rdx, rbp
0x183069a50  lea     rcx, aFailedToCreate; "Failed to create event for Thread '%d' "...
0x183069a57  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x183069a5c  mov     rax, [rdi+20h]
0x183069a60  lea     r8, ?CallThreadProc@CxThreadManager@@CAIPEAX@Z; StartAddress
0x183069a67  xor     edx, edx; StackSize
0x183069a69  xor     ecx, ecx; Security
0x183069a6b  mov     [rax+rsi+20h], r14
0x183069a70  mov     rax, [rdi+30h]
0x183069a74  mov     [rax+rbp*8], r14
0x183069a78  mov     rax, [rdi+20h]
0x183069a7c  mov     [rsi+rax], rdi
0x183069a80  mov     rax, [rdi+20h]
0x183069a84  mov     [rax+rsi+40h], r15
0x183069a89  lea     rax, [rsp+478h+var_448]
0x183069a8e  mov     r9, [rdi+20h]
0x183069a92  mov     [rsp+478h+ThrdAddr], rax; ThrdAddr
0x183069a97  add     r9, rsi; ArgList
0x183069a9a  mov     [rsp+478h+InitFlag], r12d; InitFlag
0x183069a9f  mov     [rsp+478h+var_448], r12d
0x183069aa4  call    cs:__imp__beginthreadex
0x183069aaa  mov     r14, rax
0x183069aad  test    rax, rax
0x183069ab0  jnz     short loc_183069AE3
0x183069ab2  call    cs:__imp__errno
0x183069ab8  mov     edx, 400h; unsigned __int64
0x183069abd  lea     rcx, [rsp+478h+var_438]; char *
0x183069ac2  mov     ebx, [rax]
0x183069ac4  mov     r8d, ebx; int
0x183069ac7  call    ?CxStrError@@YAPEADPEAD_KH@Z; CxStrError(char *,unsigned __int64,int)
0x183069acc  lea     r9, [rsp+478h+var_438]
0x183069ad1  mov     r8d, ebx
0x183069ad4  mov     rdx, rbp
0x183069ad7  lea     rcx, aThreadDFailedT; "Thread '%d' failed to start (errno = '%"...
0x183069ade  call    ?CxThrowError@@YAXPEBDZZ; CxThrowError(char const *,...)
0x183069ae3  mov     rcx, [rdi+38h]
0x183069ae7  mov     [rcx+rbp*8], r14
0x183069aeb  inc     rbp
0x183069aee  mov     rcx, [rdi+20h]
0x183069af2  mov     [rcx+rsi+8], r14
0x183069af7  mov     rdx, [rdi+20h]
0x183069afb  mov     ecx, [rsp+478h+var_448]
0x183069aff  mov     [rdx+rsi+10h], ecx
0x183069b03  add     rsi, 48h ; 'H'
0x183069b07  cmp     rbp, [rdi]
0x183069b0a  jb      loc_1830699B0
0x183069b10  mov     r14, [rsp+478h+arg_10]
0x183069b18  mov     rax, rdi
0x183069b1b  mov     rcx, [rsp+478h+var_38]
0x183069b23  xor     rcx, rsp; StackCookie
0x183069b26  call    __security_check_cookie
0x183069b2b  mov     rbx, [rsp+478h+arg_18]
0x183069b33  add     rsp, 450h
0x183069b3a  pop     r15
0x183069b3c  pop     r12
0x183069b3e  pop     rdi
0x183069b3f  pop     rsi
0x183069b40  pop     rbp
0x183069b41  retn
```
