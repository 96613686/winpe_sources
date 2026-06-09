# Container::Manager::Core::Details::ResourceBroker::DeleteResourceTrees(utl::vector<utl::pair<_GUID,Container::Manager::Core::Details::ResourceType>,utl::allocator<utl::pair<_GUID,Container::Manager::Core::Details::ResourceType>>> const &,utl::optional<Csl::DurableRegistryTransaction>,bool)

- ea: `0x180057c8c`
- end: `0x180058360`
- name: `?DeleteResourceTrees@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBV?$vector@U?$pair@U_GUID@@W4ResourceType@Details@Core@Manager@Container@@@utl@@V?$allocator@U?$pair@U_GUID@@W4ResourceType@Details@Core@Manager@Container@@@utl@@@2@@utl@@V?$optional@VDurableRegistryTransaction@Csl@@@7@_N@Z`
- size: `1748`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ResourceBroker *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180057b10`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x1800329ec`
- `0x180032b24`
- `0x18003ed4c`
- `0x1800493c8`
- `0x18004e538`
- `0x18004fe0c`
- `0x18005389c`
- `0x180057620`
- `0x180057c8c`
- `0x18005a490`
- `0x18005b980`
- `0x18005d10c`
- `0x18005d248`
- `0x1800606ac`
- `0x180063c98`
- `0x180065d00`
- `0x180066000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057d0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057d0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057e5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057ef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800580db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800582fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057e5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057ef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800580db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800582fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057d17`

## string_xrefs

- `0x180057e30`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180057e98`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180057ec0`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180057f20`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180057fc8`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180058093`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180058151`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x1800581f5`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005834b`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ResourceBroker::DeleteResourceTrees(
        RTL_SRWLOCK *this,
        __int64 *a2,
        Csl::DurableRegistryTransaction *a3,
        char a4)
{
  RTL_SRWLOCK *v4; // r15
  __m128i si128; // xmm6
  RTL_SRWLOCK *v6; // r13
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r8
  int ResourceTreeNodesLocked; // eax
  Container::Manager::Core::Details::ResourceBroker *v13; // rcx
  int v14; // ebx
  void *v15; // r12
  Container::Manager::Core::Details::Resource **i; // rbx
  __int64 *j; // rbx
  __int64 v18; // r13
  _QWORD *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  void *v24; // rcx
  bool v25; // zf
  void *v27; // rcx
  RTL_SRWLOCK *v28; // rax
  _QWORD *v29; // rcx
  const char *v30; // r9
  void *v31; // rdi
  char *v32; // rbx
  int v33; // eax
  struct Container::Manager::Core::Details::Resource **m; // rbx
  __int64 v35; // rcx
  __int64 v36; // rdx
  void *v37[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-D0h]
  _QWORD v39[2]; // [rsp+40h] [rbp-C8h] BYREF
  RTL_SRWLOCK *v40; // [rsp+50h] [rbp-B8h]
  _QWORD v41[4]; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v42; // [rsp+78h] [rbp-90h] BYREF
  __m128i v43; // [rsp+88h] [rbp-80h]
  __m128i v44; // [rsp+98h] [rbp-70h]
  __m128i v45; // [rsp+A8h] [rbp-60h]
  __int64 v46; // [rsp+B8h] [rbp-50h]
  __int128 v47; // [rsp+C8h] [rbp-40h] BYREF
  char v48; // [rsp+E0h] [rbp-28h]
  _OWORD v49[4]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v50; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]
  RTL_SRWLOCK *k; // [rsp+188h] [rbp+80h] BYREF
  RTL_SRWLOCK *v53; // [rsp+190h] [rbp+88h] BYREF
  char v54; // [rsp+1A0h] [rbp+98h]

  v54 = a4;
  k = this;
  v4 = this + 2;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v39[0] = v39;
  v6 = this;
  v42 = si128;
  v39[1] = v39;
  v40 = (RTL_SRWLOCK *)v39;
  v41[0] = 0;
  v43 = si128;
  v44 = si128;
  v45 = si128;
  v46 = -1;
  AcquireSRWLockExclusive(this + 2);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  v9 = *a2;
  v10 = a2[1];
  v53 = v4;
  while ( 1 )
  {
    *(__m128i *)v37 = si128;
    if ( v9 == v10 )
      break;
    v11 = *(unsigned int *)(v9 + 16);
    v38 = -1;
    ResourceTreeNodesLocked = Container::Manager::Core::Details::ResourceBroker::GetResourceTreeNodesLocked(
                                v6,
                                v9,
                                v11,
                                v37);
    v14 = ResourceTreeNodesLocked;
    if ( ResourceTreeNodesLocked < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16AA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)ResourceTreeNodesLocked,
        (int)v37[0]);
      v24 = v37[0];
      v25 = v37[0] == (void *)-1LL;
LABEL_31:
      if ( !v25 )
LABEL_32:
        operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
LABEL_33:
      LODWORD(v4[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v4);
      Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext((Container::Manager::Core::Details::ResourceDeletionContext *)&v42);
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
      if ( *((_BYTE *)a3 + 24) )
        Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a3);
      return (unsigned int)v14;
    }
    v15 = v37[0];
    for ( i = (Container::Manager::Core::Details::Resource **)v37[0]; i != v37[1]; ++i )
    {
      if ( *((_BYTE *)*i + 256) && !v54 && LOBYTE(v6[4].Ptr) )
      {
        v21 = 303;
        v22 = 5821;
LABEL_21:
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v22,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                (const char *)v21,
                (unsigned int)v37[0]);
        if ( v15 != (void *)-1LL )
          operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_33;
      }
      if ( Container::Manager::Core::Details::ResourceBroker::IsResourceOpenLocked(v13, *i) )
      {
        v23 = Container::Manager::Core::Details::Resource::LogResourceInformation(*i);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16CE,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v23,
            (int)v37[0]);
        v21 = 32;
        v22 = 5840;
        goto LABEL_21;
      }
    }
    for ( j = (__int64 *)v15; j != v37[1]; ++j )
    {
      v18 = *j;
      v19 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v19 )
        v19[3] = v18;
      utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::_EmplaceImpl(
        v39,
        &v41[1],
        v20,
        v19);
      if ( !v41[1] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16DC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          (const char *)0x8007000ELL,
          (int)v37[0]);
        if ( v15 != (void *)-1LL )
          operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_56;
      }
    }
    if ( v15 != (void *)-1LL )
      operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
    v6 = k;
    v9 += 20;
  }
  v38 = -1;
  if ( !v41[0]
    || v41[0] < 0x1000000000000000uLL
    && (unsigned __int8)utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(v37) )
  {
    v28 = v40;
    for ( k = v40; ; v28 = k )
    {
      v29 = v39;
      if ( v28 == (RTL_SRWLOCK *)v39 )
        break;
      v41[1] = v28[3].Ptr;
      if ( !(unsigned __int8)utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>>::emplace_back<Container::Manager::Core::Details::Resource * &,0>(
                               v37,
                               &v41[1]) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x16E5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v30);
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&k);
    }
    if ( v54 )
    {
      v31 = v37[0];
      v32 = (char *)v37[0];
      v41[3] = -1;
      *(__m128i *)&v41[1] = si128;
      while ( v32 != v37[1] )
      {
        if ( !*(_BYTE *)(*(_QWORD *)v32 + 257LL)
          && !(unsigned __int8)utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>>::emplace_back<Container::Manager::Core::Details::Resource * &,0>(
                                 &v41[1],
                                 v32) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16FC,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)0x8007000ELL,
            (int)v37[0]);
          if ( v41[1] != -1 )
            operator delete((void *)v41[1], (const struct std::nothrow_t *)&std::nothrow);
          if ( v31 != (void *)-1LL )
          {
            v27 = v31;
            goto LABEL_55;
          }
          goto LABEL_56;
        }
        v32 += 8;
      }
      LOBYTE(v47) = 0;
      v48 = 0;
      if ( *((_BYTE *)a3 + 24) )
      {
        v47 = 0;
        Csl::DurableRegistryTransaction::operator=(&v47, a3);
        v48 = 1;
      }
      v33 = Container::Manager::Core::Details::ResourceBroker::CommitResourcesForDeletionLocked(v29, &v41[1], &v47);
      v14 = v33;
      if ( v33 >= 0 )
      {
        for ( m = (struct Container::Manager::Core::Details::Resource **)v31; m != v37[1]; ++m )
        {
          if ( !*((_BYTE *)*m + 256) )
            Container::Manager::Core::Details::ResourceBroker::QueueResourceForDeletionLocked(
              (Container::Manager::Core::Details::ResourceBroker *)v6,
              *m);
        }
        Container::Manager::Core::Details::ResourceBroker::StartCleanupWorkIfNeededLocked((Container::Manager::Core::Details::ResourceBroker *)v6);
        if ( v41[1] != -1 )
          operator delete((void *)v41[1], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_81;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1707,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v33,
        (int)v37[0]);
      if ( v41[1] != -1 )
        operator delete((void *)v41[1], (const struct std::nothrow_t *)&std::nothrow);
      if ( v31 != (void *)-1LL )
      {
        v24 = v31;
        goto LABEL_32;
      }
      goto LABEL_33;
    }
    v14 = Container::Manager::Core::Details::ResourceDeletionContext::Initialize(&v42, v37);
    if ( v14 >= 0 )
    {
      LOBYTE(v47) = 0;
      v48 = 0;
      if ( *((_BYTE *)a3 + 24) )
      {
        v47 = 0;
        Csl::DurableRegistryTransaction::operator=(&v47, a3);
        v48 = 1;
      }
      v14 = Container::Manager::Core::Details::ResourceBroker::CommitResourcesForDeletionLocked(v35, v37, &v47);
      if ( v14 >= 0 )
      {
        v49[0] = v42;
        v49[1] = v43;
        v49[2] = v44;
        v49[3] = v45;
        v50 = v46;
        v42 = si128;
        v43.m128i_i64[0] = -1;
        v43.m128i_i64[1] = -1;
        v44 = si128;
        v45 = si128;
        v46 = -1;
        Container::Manager::Core::Details::ResourceBroker::DeleteAndRemoveResourcesLocked(v6, v49, &v53, 0);
        v4 = v53;
        v31 = v37[0];
LABEL_81:
        if ( v31 != (void *)-1LL )
          operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
        if ( v4 )
        {
          LODWORD(v4[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v4);
        }
        Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext((Container::Manager::Core::Details::ResourceDeletionContext *)&v42);
        utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
        if ( *((_BYTE *)a3 + 24) )
          Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a3);
        return 0;
      }
      v36 = 5920;
    }
    else
    {
      v36 = 5912;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)(unsigned int)v14,
      (int)v37[0]);
    v24 = v37[0];
    v25 = v37[0] == (void *)-1LL;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16E1,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
    (const char *)0x8007000ELL,
    (int)v37[0]);
  v27 = v37[0];
  if ( v37[0] != (void *)-1LL )
LABEL_55:
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
LABEL_56:
  LODWORD(v4[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v4);
  Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext((Container::Manager::Core::Details::ResourceDeletionContext *)&v42);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
  if ( *((_BYTE *)a3 + 24) )
    Csl::DurableRegistryTransaction::~DurableRegistryTransaction(a3);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180057c8c  mov     rax, rsp
0x180057c8f  mov     [rax+18h], rbx
0x180057c93  mov     [rax+20h], r9b
0x180057c97  mov     [rax+8], rcx
0x180057c9b  push    rbp
0x180057c9c  push    rsi
0x180057c9d  push    rdi
0x180057c9e  push    r12
0x180057ca0  push    r13
0x180057ca2  push    r14
0x180057ca4  push    r15
0x180057ca6  lea     rbp, [rax-78h]
0x180057caa  sub     rsp, 140h
0x180057cb1  movaps  xmmword ptr [rax-48h], xmm6
0x180057cb5  lea     r15, [rcx+10h]
0x180057cb9  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180057cc1  lea     rax, [rsp+170h+var_138]
0x180057cc6  mov     [rsp+170h+var_138], rax
0x180057ccb  mov     r13, rcx
0x180057cce  lea     rax, [rsp+170h+var_138]
0x180057cd3  movdqa  [rsp+170h+var_108+8], xmm6
0x180057cd9  xor     r12d, r12d
0x180057cdc  mov     [rsp+170h+var_130], rax
0x180057ce1  mov     rcx, r15; SRWLock
0x180057ce4  mov     [rsp+170h+var_128], rax
0x180057ce9  mov     r14, r8
0x180057cec  mov     qword ptr [rsp+170h+var_120], r12
0x180057cf1  mov     rsi, rdx
0x180057cf4  movdqa  [rbp+70h+var_F0], xmm6
0x180057cf9  movdqa  [rbp+70h+var_E0], xmm6
0x180057cfe  movdqa  [rbp+70h+var_D0], xmm6
0x180057d03  mov     [rbp+70h+var_C0], 0FFFFFFFFFFFFFFFFh
0x180057d0b  call    cs:__imp_AcquireSRWLockExclusive
0x180057d12  nop     dword ptr [rax+rax+00h]
0x180057d17  call    cs:__imp_GetCurrentThreadId
0x180057d1e  nop     dword ptr [rax+rax+00h]
0x180057d23  mov     [r15+8], eax
0x180057d27  mov     rdi, [rsi]
0x180057d2a  mov     rsi, [rsi+8]
0x180057d2e  mov     [rbp+70h+arg_8], r15
0x180057d35  movdqu  xmmword ptr [rsp+170h+var_158+8], xmm6; int
0x180057d3b  cmp     rdi, rsi
0x180057d3e  jz      loc_180057F87
0x180057d44  mov     r8d, [rdi+10h]
0x180057d48  lea     r9, [rsp+170h+var_158+8]
0x180057d4d  mov     rdx, rdi
0x180057d50  mov     [rsp+170h+var_140], 0FFFFFFFFFFFFFFFFh
0x180057d59  mov     rcx, r13
0x180057d5c  call    ?GetResourceTreeNodesLocked@ResourceBroker@Details@Core@Manager@Container@@AEBAJAEBU_GUID@@W4ResourceType@2345@AEAV?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@@Z; Container::Manager::Core::Details::ResourceBroker::GetResourceTreeNodesLocked(_GUID const &,Container::Manager::Core::Details::ResourceType,utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>> &)
0x180057d61  mov     ebx, eax
0x180057d63  test    eax, eax
0x180057d65  js      loc_180057F1C
0x180057d6b  mov     r12, [rsp+170h+var_158+8]
0x180057d70  mov     rbx, r12
0x180057d73  cmp     rbx, [rsp+170h+var_148]
0x180057d78  jz      short loc_180057DAC
0x180057d7a  mov     rdx, [rbx]; struct Container::Manager::Core::Details::Resource *
0x180057d7d  xor     eax, eax
0x180057d7f  cmp     [rdx+100h], al
0x180057d85  jz      short loc_180057D99
0x180057d87  cmp     [rbp+70h+arg_18], al
0x180057d8d  jnz     short loc_180057D99
0x180057d8f  cmp     [r13+20h], al
0x180057d93  jnz     loc_180057E21
0x180057d99  call    ?IsResourceOpenLocked@ResourceBroker@Details@Core@Manager@Container@@AEBA_NPEAVResource@2345@@Z; Container::Manager::Core::Details::ResourceBroker::IsResourceOpenLocked(Container::Manager::Core::Details::Resource *)
0x180057d9e  test    al, al
0x180057da0  jnz     loc_180057E88
0x180057da6  add     rbx, 8
0x180057daa  jmp     short loc_180057D73
0x180057dac  mov     rbx, r12
0x180057daf  cmp     rbx, [rsp+170h+var_148]
0x180057db4  jz      short loc_180057DF9
0x180057db6  mov     r13, [rbx]
0x180057db9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057dc0  mov     ecx, 20h ; ' '; unsigned __int64
0x180057dc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180057dca  test    rax, rax
0x180057dcd  jz      short loc_180057DD3
0x180057dcf  mov     [rax+18h], r13
0x180057dd3  mov     r9, rax
0x180057dd6  lea     rdx, [rsp+170h+var_120+8]
0x180057ddb  lea     rcx, [rsp+170h+var_138]
0x180057de0  call    ?_EmplaceImpl@?$_Tree@PEAVResource@Details@Core@Manager@Container@@PEAV12345@U?$less@PEAVResource@Details@Core@Manager@Container@@@utl@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@7@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@_N@2@PEAU?$_TreeNode@PEAVResource@Details@Core@Manager@Container@@@2@0@Z; utl::_Tree<Container::Manager::Core::Details::Resource *,Container::Manager::Core::Details::Resource *,utl::less<Container::Manager::Core::Details::Resource *>,utl::allocator<Container::Manager::Core::Details::Resource *>,0>::_EmplaceImpl(utl::_TreeNode<Container::Manager::Core::Details::Resource *> *,utl::_TreeNode<Container::Manager::Core::Details::Resource *> *)
0x180057de5  xor     r13d, r13d
0x180057de8  cmp     qword ptr [rsp+170h+var_120+8], r13
0x180057ded  jz      loc_180057EBC
0x180057df3  add     rbx, 8
0x180057df7  jmp     short loc_180057DAF
0x180057df9  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180057dfd  jz      short loc_180057E0E
0x180057dff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057e06  mov     rcx, r12; void *
0x180057e09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057e0e  mov     r13, [rbp+70h+arg_0]
0x180057e15  add     rdi, 14h
0x180057e19  xor     r12d, r12d
0x180057e1c  jmp     loc_180057D35
0x180057e21  mov     r9d, 12Fh; char *
0x180057e27  mov     edx, 16BDh; void *
0x180057e2c  mov     rcx, [rbp+78h]; this
0x180057e30  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180057e37  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180057e3c  mov     ebx, eax
0x180057e3e  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180057e42  jz      short loc_180057E53
0x180057e44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057e4b  mov     rcx, r12; void *
0x180057e4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057e53  mov     rcx, r15; SRWLock
0x180057e56  mov     dword ptr [r15+8], 0
0x180057e5e  call    cs:__imp_ReleaseSRWLockExclusive
0x180057e65  nop     dword ptr [rax+rax+00h]
0x180057e6a  lea     rcx, [rsp+170h+var_108+8]; this
0x180057e6f  call    ??1ResourceDeletionContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext(void)
0x180057e74  lea     rcx, [rsp+170h+var_138]
0x180057e79  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x180057e7e  cmp     byte ptr [r14+18h], 0
0x180057e83  jmp     loc_180057F76
0x180057e88  mov     rcx, [rbx]; this
0x180057e8b  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x180057e90  test    eax, eax
0x180057e92  jns     short loc_180057EAC
0x180057e94  mov     rcx, [rbp+78h]; this
0x180057e98  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180057e9f  mov     r9d, eax; char *
0x180057ea2  mov     edx, 16CEh; void *
0x180057ea7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057eac  mov     r9d, 20h ; ' '
0x180057eb2  mov     edx, 16D0h
0x180057eb7  jmp     loc_180057E2C
0x180057ebc  mov     rcx, [rbp+78h]; this
0x180057ec0  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180057ec7  mov     r9d, 8007000Eh; char *
0x180057ecd  mov     edx, 16DCh; void *
0x180057ed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057ed7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180057edb  jz      short loc_180057EEC
0x180057edd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057ee4  mov     rcx, r12; void *
0x180057ee7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057eec  mov     rcx, r15; SRWLock
0x180057eef  mov     [r15+8], r13d
0x180057ef3  call    cs:__imp_ReleaseSRWLockExclusive
0x180057efa  nop     dword ptr [rax+rax+00h]
0x180057eff  lea     rcx, [rsp+170h+var_108+8]; this
0x180057f04  call    ??1ResourceDeletionContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext(void)
0x180057f09  lea     rcx, [rsp+170h+var_138]
0x180057f0e  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x180057f13  cmp     [r14+18h], r13b
0x180057f17  jmp     loc_1800580FF
0x180057f1c  mov     rcx, [rbp+78h]; this
0x180057f20  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180057f27  mov     r9d, ebx; char *
0x180057f2a  mov     edx, 16AAh; void *
0x180057f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057f34  mov     rcx, [rsp+170h+var_158+8]; void *
0x180057f39  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180057f3d  jz      short loc_180057F4B
0x180057f3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180057f46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057f4b  mov     rcx, r15; SRWLock
0x180057f4e  mov     [r15+8], r12d
0x180057f52  call    cs:__imp_ReleaseSRWLockExclusive
0x180057f59  nop     dword ptr [rax+rax+00h]
0x180057f5e  lea     rcx, [rsp+170h+var_108+8]; this
0x180057f63  call    ??1ResourceDeletionContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext(void)
0x180057f68  lea     rcx, [rsp+170h+var_138]
0x180057f6d  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x180057f72  cmp     [r14+18h], r12b
0x180057f76  jz      short loc_180057F80
0x180057f78  mov     rcx, r14; this
0x180057f7b  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x180057f80  mov     eax, ebx
0x180057f82  jmp     loc_18005832A
0x180057f87  mov     rdx, qword ptr [rsp+170h+var_120]
0x180057f8c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180057f90  mov     [rsp+170h+var_140], rsi
0x180057f95  test    rdx, rdx
0x180057f98  jz      short loc_180057FF2
0x180057f9a  cmp     rdx, 8
0x180057f9e  jbe     short loc_180057FB1
0x180057fa0  mov     rax, 0FFFFFFFFFFFFFFFh
0x180057faa  cmp     rdx, rax
0x180057fad  ja      short loc_180057FC4
0x180057faf  jmp     short loc_180057FB6
0x180057fb1  mov     edx, 8
0x180057fb6  lea     rcx, [rsp+170h+var_158+8]
0x180057fbb  call    ?_SetCapacity@?$vector@PEAVResourceHandle@Core@Manager@Container@@V?$allocator@PEAVResourceHandle@Core@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(unsigned __int64)
0x180057fc0  test    al, al
0x180057fc2  jnz     short loc_180057FF2
0x180057fc4  mov     rcx, [rbp+78h]; this
0x180057fc8  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180057fcf  mov     r9d, 8007000Eh; char *
0x180057fd5  mov     edx, 16E1h; void *
0x180057fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057fdf  mov     rcx, [rsp+170h+var_158+8]
0x180057fe4  cmp     rcx, rsi
0x180057fe7  jz      loc_1800580D4
0x180057fed  jmp     loc_1800580C8
0x180057ff2  mov     rax, [rsp+170h+var_128]
0x180057ff7  mov     [rbp+70h+arg_0], rax
0x180057ffe  lea     rcx, [rsp+170h+var_138]
0x180058003  cmp     rax, rcx
0x180058006  jz      short loc_180058041
0x180058008  mov     rcx, [rax+18h]
0x18005800c  lea     rdx, [rsp+170h+var_120+8]
0x180058011  mov     rbx, [rbp+78h]
0x180058015  mov     qword ptr [rsp+170h+var_120+8], rcx
0x18005801a  lea     rcx, [rsp+170h+var_158+8]
0x18005801f  call    ??$emplace_back@AEAPEAVResource@Details@Core@Manager@Container@@$0A@@?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@QEAA_NAEAPEAVResource@Details@Core@Manager@Container@@@Z; utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>>::emplace_back<Container::Manager::Core::Details::Resource * &,0>(Container::Manager::Core::Details::Resource * &)
0x180058024  test    al, al
0x180058026  jz      loc_18005834B
0x18005802c  lea     rcx, [rbp+70h+arg_0]
0x180058033  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x180058038  mov     rax, [rbp+70h+arg_0]
0x18005803f  jmp     short loc_180057FFE
0x180058041  cmp     [rbp+70h+arg_18], r12b
0x180058048  jz      loc_1800581D7
0x18005804e  mov     rdi, [rsp+170h+var_158+8]
0x180058053  mov     rbx, rdi
0x180058056  mov     qword ptr [rsp+170h+var_108], rsi
0x18005805b  movdqu  xmmword ptr [rsp+170h+var_120+8], xmm6
0x180058061  cmp     rbx, [rsp+170h+var_148]
0x180058066  jz      loc_180058113
0x18005806c  mov     rax, [rbx]
0x18005806f  cmp     [rax+101h], r12b
0x180058076  jnz     short loc_180058089
0x180058078  mov     rdx, rbx
0x18005807b  lea     rcx, [rsp+170h+var_120+8]
0x180058080  call    ??$emplace_back@AEAPEAVResource@Details@Core@Manager@Container@@$0A@@?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@QEAA_NAEAPEAVResource@Details@Core@Manager@Container@@@Z; utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>>::emplace_back<Container::Manager::Core::Details::Resource * &,0>(Container::Manager::Core::Details::Resource * &)
0x180058085  test    al, al
0x180058087  jz      short loc_18005808F
0x180058089  add     rbx, 8
0x18005808d  jmp     short loc_180058061
0x18005808f  mov     rcx, [rbp+78h]; this
0x180058093  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005809a  mov     r9d, 8007000Eh; char *
0x1800580a0  mov     edx, 16FCh; void *
0x1800580a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800580aa  mov     rcx, qword ptr [rsp+170h+var_120+8]; void *
0x1800580af  cmp     rcx, rsi
0x1800580b2  jz      short loc_1800580C0
0x1800580b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800580bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800580c0  cmp     rdi, rsi
0x1800580c3  jz      short loc_1800580D4
0x1800580c5  mov     rcx, rdi; void *
0x1800580c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800580cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800580d4  mov     rcx, r15; SRWLock
0x1800580d7  mov     [r15+8], r12d
0x1800580db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800580e2  nop     dword ptr [rax+rax+00h]
0x1800580e7  lea     rcx, [rsp+170h+var_108+8]; this
0x1800580ec  call    ??1ResourceDeletionContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ResourceDeletionContext::~ResourceDeletionContext(void)
0x1800580f1  lea     rcx, [rsp+170h+var_138]
0x1800580f6  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x1800580fb  cmp     [r14+18h], r12b
0x1800580ff  jz      short loc_180058109
0x180058101  mov     rcx, r14; this
0x180058104  call    ??1DurableRegistryTransaction@Csl@@QEAA@XZ; Csl::DurableRegistryTransaction::~DurableRegistryTransaction(void)
0x180058109  mov     eax, 8007000Eh
0x18005810e  jmp     loc_18005832A
0x180058113  mov     byte ptr [rbp+70h+var_B0], r12b
0x180058117  mov     [rbp+70h+var_98], r12b
0x18005811b  cmp     [r14+18h], r12b
0x18005811f  jz      short loc_180058139
0x180058121  xorps   xmm0, xmm0
0x180058124  lea     rcx, [rbp+70h+var_B0]
0x180058128  mov     rdx, r14
0x18005812b  movdqu  [rbp+70h+var_B0], xmm0
0x180058130  call    ??4DurableRegistryTransaction@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::DurableRegistryTransaction::operator=(Csl::DurableRegistryTransaction &&)
0x180058135  mov     [rbp+70h+var_98], 1
0x180058139  lea     r8, [rbp+70h+var_B0]
0x18005813d  lea     rdx, [rsp+170h+var_120+8]
0x180058142  call    ?CommitResourcesForDeletionLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBV?$vector@PEAVResource@Details@Core@Manager@Container@@V?$allocator@PEAVResource@Details@Core@Manager@Container@@@utl@@@utl@@V?$optional@VDurableRegistryTransaction@Csl@@@7@@Z; Container::Manager::Core::Details::ResourceBroker::CommitResourcesForDeletionLocked(utl::vector<Container::Manager::Core::Details::Resource *,utl::allocator<Container::Manager::Core::Details::Resource *>> const &,utl::optional<Csl::DurableRegistryTransaction>)
0x180058147  mov     ebx, eax
0x180058149  test    eax, eax
0x18005814b  jns     short loc_18005818C
0x18005814d  mov     rcx, [rbp+78h]; this
0x180058151  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180058158  mov     r9d, eax; char *
0x18005815b  mov     edx, 1707h; void *
0x180058160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058165  mov     rcx, qword ptr [rsp+170h+var_120+8]; void *
0x18005816a  cmp     rcx, rsi
0x18005816d  jz      short loc_18005817B
0x18005816f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180058176  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005817b  cmp     rdi, rsi
0x18005817e  jz      loc_180057F4B
0x180058184  mov     rcx, rdi
0x180058187  jmp     loc_180057F3F
0x18005818c  mov     rbx, rdi
0x18005818f  cmp     rbx, [rsp+170h+var_148]
0x180058194  jz      short loc_1800581B0
0x180058196  mov     rdx, [rbx]; struct Container::Manager::Core::Details::Resource *
0x180058199  cmp     [rdx+100h], r12b
0x1800581a0  jnz     short loc_1800581AA
0x1800581a2  mov     rcx, r13; this
  ... truncated ...
```
