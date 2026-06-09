# Csl::AsyncOperation<void>::Initialize(utl::shared_ptr<Csl::CompletionEvent<void>>)

- ea: `0x18005a894`
- end: `0x18005ac45`
- name: `?Initialize@?$AsyncOperation@X@Csl@@QEAAJV?$shared_ptr@V?$CompletionEvent@X@Csl@@@utl@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180050c7c`
- `0x1800615ec`
- `0x180065c70`
- `0x180071c6c`
- `0x18008496c`
- `0x1800ae55c`
- `0x1800e2178`
- `0x1800e6bc0`
- `0x1800e9a90`
- `0x1800ea864`
- `0x1800ee61c`
- `0x1800f1810`
- `0x1800f2ea0`
- `0x180125ad4`
- `0x180125c2c`
- `0x180177374`
- `0x18017fb80`
- `0x180181f40`
- `0x1801824c0`
- `0x180195504`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18003dbf8`
- `0x1800471dc`
- `0x18004891c`
- `0x18005a894`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005aa20`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005aa20`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005a907`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005a907`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005a946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005a974`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005a946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005a974`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a990`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005aa00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a990`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005aa00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005aa34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005aa48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005abbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005aa34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005aa48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005abbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a954`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Csl::AsyncOperation<void>::Initialize(__int64 a1, RTL_SRWLOCK **a2)
{
  char *v4; // rax
  char *v5; // rsi
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v7; // r9
  struct _TP_WORK **v8; // r15
  struct _TP_WORK *v9; // rbp
  DWORD LastError; // edi
  RTL_SRWLOCK *v11; // rdi
  RTL_SRWLOCK *v12; // rbp
  unsigned __int64 v13; // rbx
  unsigned __int64 *v14; // rax
  int Ptr; // ebx
  void *v16; // rbx
  RTL_SRWLOCK *v17; // rax
  RTL_SRWLOCK *v18; // rdx
  utl::_RefCountBase *v19; // rcx
  utl::_RefCountBase *v20; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  utl::_RefCountBase *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int8 v27; // r8
  __int64 v28; // r10
  _QWORD *v29; // rax
  utl::_RefCountBase *v30; // rcx
  int v31; // [rsp+20h] [rbp-48h] BYREF
  __int64 v32; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int8 v33; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslAsync.h",
      (const char *)0x8007000ELL,
      v31);
LABEL_44:
    v30 = (utl::_RefCountBase *)a2[1];
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    return 2147942414LL;
  }
  *(_DWORD *)v4 = 0;
  *((_DWORD *)v4 + 1) = -2147467259;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *((_QWORD *)v4 + 4) = 0;
  *((_DWORD *)v4 + 10) = -1;
  v4[44] = 0;
  ThreadpoolWork = CreateThreadpoolWork(Csl::Details::AsyncOperationImpl<void>::InvokeCallback, v4, 0);
  if ( ThreadpoolWork )
  {
    v8 = (struct _TP_WORK **)(v5 + 32);
    if ( v5 + 32 == (char *)&v31 )
    {
      *(_DWORD *)v5 = 1;
      CloseThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      v9 = *v8;
      if ( *v8 )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(v9);
        SetLastError(LastError);
      }
      *v8 = ThreadpoolWork;
      *(_DWORD *)v5 = 1;
    }
    goto LABEL_8;
  }
  v22 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x199,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslAsync.h",
          v7);
  v23 = v22;
  if ( v22 >= 0 )
  {
LABEL_8:
    v11 = *a2;
    v12 = *a2 + 1;
    AcquireSRWLockExclusive(v12);
    v13 = (unsigned __int64)&v11[2];
    if ( v11[4].Ptr == &v11[2] )
    {
      v14 = (unsigned __int64 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v14 )
      {
        v14[3] = (unsigned __int64)v5;
        *v14 = v13 | 1;
        v14[1] = (unsigned __int64)&utl::_TreeSentinel;
        v14[2] = (unsigned __int64)&utl::_TreeSentinel;
        *(_QWORD *)v13 = v14;
        v11[3].Ptr = v14;
        v11[4].Ptr = v14;
        ++v11[5].Ptr;
LABEL_11:
        if ( HIDWORD(v11->Ptr) )
        {
          Ptr = (int)v11->Ptr;
          AcquireSRWLockExclusive((PSRWLOCK)v5 + 1);
          *(_DWORD *)v5 = 2;
          *((_DWORD *)v5 + 1) = Ptr;
          if ( *((_QWORD *)v5 + 2) )
            SubmitThreadpoolWork(*((PTP_WORK *)v5 + 4));
          if ( v5 != (char *)-8LL )
            ReleaseSRWLockExclusive((PSRWLOCK)v5 + 1);
        }
        if ( v12 )
          ReleaseSRWLockExclusive(v12);
        v16 = *(void **)a1;
        *(_QWORD *)a1 = v5;
        if ( v16 )
        {
          Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v16);
          operator delete(v16, (const struct std::nothrow_t *)0x30);
        }
        v17 = *a2;
        v18 = a2[1];
        *a2 = 0;
        a2[1] = 0;
        *(_QWORD *)(a1 + 8) = v17;
        v19 = *(utl::_RefCountBase **)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v18;
        if ( v19 )
          utl::_RefCountBase::_DecStrong(v19);
        v20 = (utl::_RefCountBase *)a2[1];
        if ( v20 )
          utl::_RefCountBase::_DecStrong(v20);
        return 0;
      }
    }
    else
    {
      v25 = *(_QWORD *)v13;
      v26 = 0;
      do
      {
        if ( (unsigned __int64)v5 >= *(_QWORD *)(v25 + 24) )
        {
          v26 = v25;
          v27 = 1;
        }
        else
        {
          v27 = 0;
        }
        v28 = v25;
        v25 = *(_QWORD *)(v25 + 8LL * v27 + 8);
      }
      while ( (void **)v25 != &utl::_TreeSentinel );
      if ( v26 && *(_QWORD *)(v26 + 24) < (unsigned __int64)v5 )
        v26 = 0;
      v32 = v28;
      v33 = v27;
      if ( v26 )
        goto LABEL_11;
      v29 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v29 )
      {
        v29[3] = v5;
        utl::_Tree<_GUID,utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>>,0>::_InsertAt(
          &v11[2],
          &v32,
          v29);
        goto LABEL_11;
      }
    }
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x477,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslAsync.h",
      (const char *)0x8007000ELL,
      v31);
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v5);
    operator delete(v5, (const struct std::nothrow_t *)0x30);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x474,
    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslAsync.h",
    (const char *)(unsigned int)v22,
    v31);
  Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v5);
  operator delete(v5, (const struct std::nothrow_t *)0x30);
  v24 = (utl::_RefCountBase *)a2[1];
  if ( v24 )
    utl::_RefCountBase::_DecStrong(v24);
  return v23;
}

```

## disassembly

```asm
0x18005a894  mov     [rsp+arg_0], rbx
0x18005a899  mov     [rsp+arg_8], rbp
0x18005a89e  push    rsi
0x18005a89f  push    rdi
0x18005a8a0  push    r12
0x18005a8a2  push    r14
0x18005a8a4  push    r15
0x18005a8a6  sub     rsp, 40h
0x18005a8aa  mov     r14, rdx
0x18005a8ad  mov     r12, rcx
0x18005a8b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005a8b7  mov     r15d, 30h ; '0'
0x18005a8bd  mov     ecx, r15d; unsigned __int64
0x18005a8c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005a8c5  mov     rsi, rax
0x18005a8c8  test    rax, rax
0x18005a8cb  jz      loc_18005ABFC
0x18005a8d1  mov     dword ptr [rax], 0
0x18005a8d7  mov     dword ptr [rax+4], 80004005h
0x18005a8de  xor     eax, eax
0x18005a8e0  mov     [rsi+8], rax
0x18005a8e4  mov     [rsi+10h], rax
0x18005a8e8  mov     [rsi+18h], rax
0x18005a8ec  mov     [rsi+20h], rax
0x18005a8f0  mov     dword ptr [rsi+28h], 0FFFFFFFFh
0x18005a8f7  mov     [rsi+2Ch], al
0x18005a8fa  xor     r8d, r8d; pcbe
0x18005a8fd  mov     rdx, rsi; pv
0x18005a900  lea     rcx, ?InvokeCallback@?$AsyncOperationImpl@X@Details@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005a907  call    cs:__imp_CreateThreadpoolWork
0x18005a90e  nop     dword ptr [rax+rax+00h]
0x18005a913  mov     rbx, rax
0x18005a916  test    rax, rax
0x18005a919  jz      loc_18005AABA
0x18005a91f  lea     r15, [rsi+20h]
0x18005a923  lea     rax, [rsp+68h+var_48]
0x18005a928  cmp     r15, rax
0x18005a92b  jz      short loc_18005A96B
0x18005a92d  mov     rbp, [r15]
0x18005a930  test    rbp, rbp
0x18005a933  jz      short loc_18005A960
0x18005a935  call    cs:__imp_GetLastError
0x18005a93c  nop     dword ptr [rax+rax+00h]
0x18005a941  mov     edi, eax
0x18005a943  mov     rcx, rbp; pwk
0x18005a946  call    cs:__imp_CloseThreadpoolWork
0x18005a94d  nop     dword ptr [rax+rax+00h]
0x18005a952  mov     ecx, edi; dwErrCode
0x18005a954  call    cs:__imp_SetLastError
0x18005a95b  nop     dword ptr [rax+rax+00h]
0x18005a960  mov     [r15], rbx
0x18005a963  mov     dword ptr [rsi], 1
0x18005a969  jmp     short loc_18005A980
0x18005a96b  mov     dword ptr [rsi], 1
0x18005a971  mov     rcx, rbx; pwk
0x18005a974  call    cs:__imp_CloseThreadpoolWork
0x18005a97b  nop     dword ptr [rax+rax+00h]
0x18005a980  mov     r15d, 30h ; '0'
0x18005a986  mov     rdi, [r14]
0x18005a989  lea     rbp, [rdi+8]
0x18005a98d  mov     rcx, rbp; SRWLock
0x18005a990  call    cs:__imp_AcquireSRWLockExclusive
0x18005a997  nop     dword ptr [rax+rax+00h]
0x18005a99c  lea     rbx, [rdi+10h]
0x18005a9a0  cmp     [rbx+10h], rbx
0x18005a9a4  jnz     loc_18005AB1D
0x18005a9aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005a9b1  mov     ecx, 20h ; ' '; unsigned __int64
0x18005a9b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005a9bb  test    rax, rax
0x18005a9be  jz      loc_18005ABB6
0x18005a9c4  mov     [rax+18h], rsi
0x18005a9c8  mov     rcx, rbx
0x18005a9cb  or      rcx, 1
0x18005a9cf  mov     [rax], rcx
0x18005a9d2  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18005a9d9  mov     [rax+8], r9
0x18005a9dd  mov     [rax+10h], r9
0x18005a9e1  mov     [rbx], rax
0x18005a9e4  mov     [rbx+8], rax
0x18005a9e8  mov     [rbx+10h], rax
0x18005a9ec  inc     qword ptr [rbx+18h]
0x18005a9f0  mov     eax, [rdi+4]
0x18005a9f3  test    eax, eax
0x18005a9f5  jz      short loc_18005AA40
0x18005a9f7  mov     ebx, [rdi]
0x18005a9f9  lea     rdi, [rsi+8]
0x18005a9fd  mov     rcx, rdi; SRWLock
0x18005aa00  call    cs:__imp_AcquireSRWLockExclusive
0x18005aa07  nop     dword ptr [rax+rax+00h]
0x18005aa0c  mov     dword ptr [rsi], 2
0x18005aa12  mov     [rsi+4], ebx
0x18005aa15  cmp     qword ptr [rsi+10h], 0
0x18005aa1a  jz      short loc_18005AA2C
0x18005aa1c  mov     rcx, [rsi+20h]; pwk
0x18005aa20  call    cs:__imp_SubmitThreadpoolWork
0x18005aa27  nop     dword ptr [rax+rax+00h]
0x18005aa2c  test    rdi, rdi
0x18005aa2f  jz      short loc_18005AA40
0x18005aa31  mov     rcx, rdi; SRWLock
0x18005aa34  call    cs:__imp_ReleaseSRWLockExclusive
0x18005aa3b  nop     dword ptr [rax+rax+00h]
0x18005aa40  test    rbp, rbp
0x18005aa43  jz      short loc_18005AA54
0x18005aa45  mov     rcx, rbp; SRWLock
0x18005aa48  call    cs:__imp_ReleaseSRWLockExclusive
0x18005aa4f  nop     dword ptr [rax+rax+00h]
0x18005aa54  mov     rbx, [r12]
0x18005aa58  mov     [r12], rsi
0x18005aa5c  test    rbx, rbx
0x18005aa5f  jz      short loc_18005AA74
0x18005aa61  mov     rcx, rbx
0x18005aa64  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18005aa69  mov     rdx, r15; struct std::nothrow_t *
0x18005aa6c  mov     rcx, rbx; void *
0x18005aa6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005aa74  mov     rax, [r14]
0x18005aa77  mov     rdx, [r14+8]
0x18005aa7b  mov     qword ptr [r14], 0
0x18005aa82  mov     qword ptr [r14+8], 0
0x18005aa8a  mov     [r12+8], rax
0x18005aa8f  mov     rcx, [r12+10h]; this
0x18005aa94  mov     [r12+10h], rdx
0x18005aa99  test    rcx, rcx
0x18005aa9c  jz      short loc_18005AAA4
0x18005aa9e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005aaa3  nop
0x18005aaa4  mov     rcx, [r14+8]; this
0x18005aaa8  test    rcx, rcx
0x18005aaab  jz      short loc_18005AAB3
0x18005aaad  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005aab2  nop
0x18005aab3  xor     eax, eax
0x18005aab5  jmp     loc_18005AC2D
0x18005aaba  mov     rcx, [rsp+68h]; this
0x18005aabf  lea     r8, aOnecoreBaseGen_27; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18005aac6  mov     edx, 199h; void *
0x18005aacb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005aad0  mov     ebx, eax
0x18005aad2  test    eax, eax
0x18005aad4  jns     loc_18005A986
0x18005aada  mov     rcx, [rsp+68h]; this
0x18005aadf  mov     r9d, eax; char *
0x18005aae2  lea     r8, aOnecoreBaseGen_27; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18005aae9  mov     edx, 474h; void *
0x18005aaee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aaf3  mov     rcx, rsi
0x18005aaf6  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18005aafb  mov     rdx, r15; struct std::nothrow_t *
0x18005aafe  mov     rcx, rsi; void *
0x18005ab01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005ab06  nop
0x18005ab07  mov     rcx, [r14+8]; this
0x18005ab0b  test    rcx, rcx
0x18005ab0e  jz      short loc_18005AB16
0x18005ab10  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005ab15  nop
0x18005ab16  mov     eax, ebx
0x18005ab18  jmp     loc_18005AC2D
0x18005ab1d  mov     rdx, [rbx]
0x18005ab20  xor     ecx, ecx
0x18005ab22  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18005ab29  cmp     rsi, [rdx+18h]
0x18005ab2d  jnb     short loc_18005AB34
0x18005ab2f  xor     r8b, r8b
0x18005ab32  jmp     short loc_18005AB3A
0x18005ab34  mov     rcx, rdx
0x18005ab37  mov     r8b, 1
0x18005ab3a  mov     r10, rdx
0x18005ab3d  movzx   eax, r8b
0x18005ab41  mov     rdx, [rdx+rax*8+8]
0x18005ab46  cmp     rdx, r9
0x18005ab49  jnz     short loc_18005AB29
0x18005ab4b  test    rcx, rcx
0x18005ab4e  jz      short loc_18005AB5A
0x18005ab50  xor     eax, eax
0x18005ab52  cmp     [rcx+18h], rsi
0x18005ab56  cmovb   rcx, rax
0x18005ab5a  mov     [rsp+68h+var_40], r10
0x18005ab5f  mov     [rsp+68h+var_38], r8b
0x18005ab64  mov     eax, [rsp+68h+var_37]
0x18005ab68  mov     [rsp+68h+var_37], eax
0x18005ab6c  movzx   eax, [rsp+68h+var_33]
0x18005ab71  mov     [rsp+68h+var_33], ax
0x18005ab76  mov     al, [rsp+68h+var_31]
0x18005ab7a  mov     [rsp+68h+var_31], al
0x18005ab7e  test    rcx, rcx
0x18005ab81  jnz     loc_18005A9F0
0x18005ab87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005ab8e  mov     ecx, 20h ; ' '; unsigned __int64
0x18005ab93  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005ab98  test    rax, rax
0x18005ab9b  jz      short loc_18005ABB6
0x18005ab9d  mov     [rax+18h], rsi
0x18005aba1  mov     r8, rax
0x18005aba4  lea     rdx, [rsp+68h+var_40]
0x18005aba9  mov     rcx, rbx
0x18005abac  call    ?_InsertAt@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@3@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *,bool> const &,utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *)
0x18005abb1  jmp     loc_18005A9F0
0x18005abb6  test    rbp, rbp
0x18005abb9  jz      short loc_18005ABCA
0x18005abbb  mov     rcx, rbp; SRWLock
0x18005abbe  call    cs:__imp_ReleaseSRWLockExclusive
0x18005abc5  nop     dword ptr [rax+rax+00h]
0x18005abca  mov     rcx, [rsp+68h]; this
0x18005abcf  mov     r9d, 8007000Eh; char *
0x18005abd5  lea     r8, aOnecoreBaseGen_27; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18005abdc  mov     edx, 477h; void *
0x18005abe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005abe6  mov     rcx, rsi
0x18005abe9  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x18005abee  mov     rdx, r15; struct std::nothrow_t *
0x18005abf1  mov     rcx, rsi; void *
0x18005abf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005abf9  nop
0x18005abfa  jmp     short loc_18005AC19
0x18005abfc  mov     rcx, [rsp+68h]; this
0x18005ac01  mov     r9d, 8007000Eh; char *
0x18005ac07  lea     r8, aOnecoreBaseGen_27; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18005ac0e  mov     edx, 471h; void *
0x18005ac13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac18  nop
0x18005ac19  mov     rcx, [r14+8]; this
0x18005ac1d  test    rcx, rcx
0x18005ac20  jz      short loc_18005AC28
0x18005ac22  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005ac27  nop
0x18005ac28  mov     eax, 8007000Eh
0x18005ac2d  mov     rbx, [rsp+68h+arg_0]
0x18005ac32  mov     rbp, [rsp+68h+arg_8]
0x18005ac37  add     rsp, 40h
0x18005ac3b  pop     r15
0x18005ac3d  pop     r14
0x18005ac3f  pop     r12
0x18005ac41  pop     rdi
0x18005ac42  pop     rsi
0x18005ac43  retn
```
