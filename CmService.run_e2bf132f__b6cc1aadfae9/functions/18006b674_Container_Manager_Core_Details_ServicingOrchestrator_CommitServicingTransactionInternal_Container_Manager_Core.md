# Container::Manager::Core::Details::ServicingOrchestrator::CommitServicingTransactionInternal(Container::Manager::Core::Details::ServicingTransaction &,Csl::List<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>> &)

- ea: `0x18006b674`
- end: `0x18006c2ad`
- name: `?CommitServicingTransactionInternal@ServicingOrchestrator@Details@Core@Manager@Container@@AEAAJAEAVServicingTransaction@2345@AEAV?$List@V?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@@Csl@@@Z`
- size: `3129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002a7b0`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x1800329ec`
- `0x180032c1c`
- `0x180033568`
- `0x18003417c`
- `0x1800393cc`
- `0x18003943c`
- `0x18003bb80`
- `0x18003c750`
- `0x180047260`
- `0x18004910c`
- `0x1800492f0`
- `0x1800493c8`
- `0x18004feb4`
- `0x18005a7ec`
- `0x18005bee8`
- `0x1800601f8`
- `0x180063cd0`
- `0x180066000`
- `0x180069440`
- `0x18006984c`
- `0x180069f38`
- `0x18006b674`
- `0x18006c2b4`
- `0x18006d8b8`
- `0x18006d9c4`
- `0x180070910`
- `0x1800726c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b6d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b718`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b6d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006b718`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b7af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b7cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ba36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ba53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006be75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bf09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bf83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bfab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c02c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c0b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c0d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c13d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c169`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b7af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b7cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006b9ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ba36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ba53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006be75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bf09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bf83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bfab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c02c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c0b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c0d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c13d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c169`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b6e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b6e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b724`

## string_xrefs

- `0x18006b907`: `ServicingOrchestrator_CommitServicingTransaction`
- `0x18006bb56`: `ServicingOrchestrator_CommitServicingTransaction`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ServicingOrchestrator::CommitServicingTransactionInternal(
        __int64 a1,
        __int64 a2,
        Container::Manager::Core::Details::ResourceOperation ***a3)
{
  __int64 v3; // rdi
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // esi
  int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // r15
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // r14
  char v15; // bl
  Container::Manager::Core::ResourceHandle *v16; // rsi
  Container::Manager::Core::ResourceHandle *v17; // r13
  Container::Manager::Core::ResourceHandle *v18; // rax
  Container::Manager::Core::ResourceHandle *v19; // rdi
  int v20; // eax
  const char *v21; // r9
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  char v24; // al
  char v25; // al
  Container::Manager::Core::ResourceHandle *v26; // rcx
  __int64 v27; // rcx
  void *v28; // rbx
  __int64 v29; // rax
  __int64 k; // rbx
  Container::Manager::Core::ResourceHandle *v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  char *v35; // rax
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rcx
  int v39; // edi
  UUID **v40; // rbx
  UUID **v41; // rdi
  const char *v42; // r9
  signed __int64 v43; // r8
  Container::Manager::Core::ResourceHandle *v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rcx
  signed __int64 v48; // r8
  Container::Manager::Core::ResourceHandle *v49; // rbx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  void *v53; // rbx
  __int64 v54; // rcx
  void *v55; // rbx
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // rcx
  void *v59; // rbx
  __int64 v61; // r8
  int v62; // eax
  Container::Manager::Core::ResourceHandle **i; // rbx
  enum ResourceType Type; // eax
  Container::Manager::Core::ResourceHandle *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rax
  Container::Manager::Core::Details::ResourceOperation **j; // rbx
  int started; // eax
  __int64 v70; // rcx
  void *v71; // rbx
  unsigned int v72; // [rsp+28h] [rbp-E0h]
  void *v73[2]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v74; // [rsp+40h] [rbp-C8h]
  _QWORD v75[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v76; // [rsp+58h] [rbp-B0h]
  __int64 v77; // [rsp+60h] [rbp-A8h]
  Container::Manager::Core::ResourceHandle *v78; // [rsp+68h] [rbp-A0h]
  Container::Manager::Core::ResourceHandle *v79[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v80; // [rsp+88h] [rbp-80h]
  __int64 v81; // [rsp+90h] [rbp-78h] BYREF
  UUID *Uuid1; // [rsp+98h] [rbp-70h] BYREF
  void *v83[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v84; // [rsp+B0h] [rbp-58h]
  void *v85[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int16 v86; // [rsp+D0h] [rbp-38h]
  _QWORD v87[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v88[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v89[10]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  char v94; // [rsp+170h] [rbp+68h]

  v3 = a1 + 160;
  *(_OWORD *)v85 = 0;
  *(__m128i *)&v79[1] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v86 = 0;
  *(_OWORD *)v73 = *(_OWORD *)&v79[1];
  v80 = -1;
  v74 = -1;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 160));
  v77 = 0;
  *(_DWORD *)(v3 + 8) = GetCurrentThreadId();
  v75[0] = v75;
  v75[1] = v75;
  v76 = v75;
  AcquireSRWLockExclusive((PSRWLOCK)(a2 + 24));
  *(_DWORD *)(a2 + 32) = GetCurrentThreadId();
  if ( *(_DWORD *)(a2 + 64) == 3 )
  {
    v5 = 6705;
    v6 = 3801;
LABEL_5:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
           (const char *)v5,
           v72);
LABEL_10:
    *(_DWORD *)(a2 + 32) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
    *(_DWORD *)(v3 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v3);
    goto LABEL_111;
  }
  if ( *(_DWORD *)(a2 + 64) == 4 )
  {
    v5 = 303;
    v6 = 3805;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(a2 + 64) != 2 )
  {
    v5 = 5023;
    v6 = 3809;
    goto LABEL_5;
  }
  v8 = Csl::DurableRegistryTransaction::Initialize(v85);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)v8,
      v72);
    goto LABEL_10;
  }
  v9 = *(_QWORD *)(a2 + 40);
  v10 = 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a2 + 48) - v9) >> 2);
  if ( v10 )
  {
    if ( v10 >= 0x1000000000000000LL
      || !(unsigned __int8)utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(&v79[1]) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)0x8007000ELL,
        v72);
      *(_DWORD *)(a2 + 32) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
      *(_DWORD *)(v3 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v3);
      v26 = v79[1];
      if ( v79[1] == (Container::Manager::Core::ResourceHandle *)-1LL )
      {
LABEL_38:
        v7 = -2147024882;
        goto LABEL_111;
      }
LABEL_37:
      operator delete(v26, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_38;
    }
    v9 = *(_QWORD *)(a2 + 40);
  }
  v11 = *(_QWORD *)(a2 + 48);
  v12 = 0xCCCCCCCCCCCCCCCDuLL * ((v11 - v9) >> 2);
  if ( v12 )
  {
    v13 = 8;
    if ( v12 > 8 )
    {
      if ( v12 > 0xFFFFFFFFFFFFFFFLL )
        goto LABEL_34;
      v13 = 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a2 + 48) - v9) >> 2);
    }
    if ( (unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>::_SetCapacity(
                            v73,
                            v13,
                            0xFFFFFFFFFFFFFFFLL) )
    {
      v11 = *(_QWORD *)(a2 + 48);
      goto LABEL_21;
    }
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)0x8007000ELL,
      v72);
    *(_DWORD *)(a2 + 32) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
    *(_DWORD *)(v3 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v3);
    v28 = v73[0];
    if ( v73[0] != (void *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
        v27,
        v73[0],
        ((char *)v73[1] - (char *)v73[0]) >> 3);
      operator delete(v28, (const struct std::nothrow_t *)&std::nothrow);
    }
    v26 = v79[1];
    if ( v79[1] == (Container::Manager::Core::ResourceHandle *)-1LL )
      goto LABEL_38;
    goto LABEL_37;
  }
LABEL_21:
  v14 = *(_QWORD *)(a2 + 40);
  v15 = 0;
  v16 = v79[2];
  v17 = v79[1];
  v94 = 0;
  while ( 1 )
  {
    if ( v14 == v11 )
    {
      v56 = Container::Manager::Core::Details::ServicingTransaction::DeleteRegistryState(
              (Container::Manager::Core::Details::ServicingTransaction *)a2,
              v85[1]);
      v39 = v56;
      if ( v56 >= 0 )
      {
        if ( v94
          && (v39 = Container::Manager::Core::Details::ServicingStore::SetLayersRegisteredForServicing(a1, v75, v85[1]),
              v39 < 0) )
        {
          v57 = 3920;
        }
        else
        {
          v39 = Csl::DurableRegistryTransaction::Commit((Csl::DurableRegistryTransaction *)v85);
          if ( v39 >= 0 )
          {
            *(_DWORD *)(a2 + 64) = 3;
            *(_DWORD *)(a2 + 32) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
            if ( v94 )
              utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(a1 + 176, v75, v61);
            *(_DWORD *)(a1 + 168) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 160));
            v62 = Csl::DurableRegistryTransaction::Flush((Csl::DurableRegistryTransaction *)v85);
            if ( v62 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xF66,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
                (const char *)(unsigned int)v62,
                v72);
            for ( i = (Container::Manager::Core::ResourceHandle **)v17;
                  i != (Container::Manager::Core::ResourceHandle **)v16;
                  ++i )
            {
              Type = Container::Manager::Core::ResourceHandle::GetType(*i);
              v65 = *i;
              if ( Type == 2 )
              {
                v66 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(v65);
                if ( *(_BYTE *)(v66 + 360) )
                  *(_BYTE *)(v66 + 360) = 0;
              }
              else
              {
                v67 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(v65);
                if ( *(_BYTE *)(v67 + 368) )
                  *(_BYTE *)(v67 + 368) = 0;
              }
            }
            for ( j = *a3; j; j = (Container::Manager::Core::Details::ResourceOperation **)j[4] )
            {
              *((_BYTE *)*j + 12) = 0;
              started = Container::Manager::Core::Details::ResourceOperation::StartIfNeeded(*j);
              if ( started < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xF83,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
                  (const char *)(unsigned int)started,
                  v72);
            }
            utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
            v71 = v73[0];
            if ( v73[0] != (void *)-1LL )
            {
              utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
                v70,
                v73[0],
                ((char *)v73[1] - (char *)v73[0]) >> 3);
              operator delete(v71, (const struct std::nothrow_t *)&std::nothrow);
            }
            if ( v17 != (Container::Manager::Core::ResourceHandle *)-1LL )
              operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
            Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)v85);
            return 0;
          }
          v57 = 3925;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v57,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
          (const char *)(unsigned int)v39,
          v72);
        *(_DWORD *)(a2 + 32) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
        utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
        v50 = a1 + 160;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF49,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
          (const char *)(unsigned int)v56,
          v72);
        *(_DWORD *)(a2 + 32) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
        utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
        v50 = a1 + 160;
      }
      *(_DWORD *)(v50 + 8) = 0;
LABEL_106:
      ReleaseSRWLockExclusive((PSRWLOCK)v50);
      v59 = v73[0];
      if ( v73[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v58,
          v73[0],
          ((char *)v73[1] - (char *)v73[0]) >> 3);
        operator delete(v59, (const struct std::nothrow_t *)&std::nothrow);
      }
      if ( v17 != (Container::Manager::Core::ResourceHandle *)-1LL )
        operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v39;
      goto LABEL_111;
    }
    v18 = (Container::Manager::Core::ResourceHandle *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v18;
    if ( !v18 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF2,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)0x8007000ELL,
        v72);
LABEL_93:
      *(_DWORD *)(a2 + 32) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
      *(_DWORD *)(a1 + 168) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 160));
      v55 = v73[0];
      if ( v73[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v54,
          v73[0],
          ((char *)v73[1] - (char *)v73[0]) >> 3);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      if ( v17 != (Container::Manager::Core::ResourceHandle *)-1LL )
      {
        v26 = v17;
        goto LABEL_37;
      }
      goto LABEL_38;
    }
    *((_QWORD *)v18 + 5) = 0;
    *(_QWORD *)v18 = (char *)v18 + 16;
    *((_QWORD *)v18 + 1) = (char *)v18 + 16;
    *((_WORD *)v18 + 8) = 0;
    *((_DWORD *)v18 + 8) = 0;
    *((_QWORD *)v18 + 8) = 0;
    *((_QWORD *)v18 + 9) = 0;
    *((_BYTE *)v18 + 80) = 0;
    *((_QWORD *)v18 + 6) = 0;
    *((_QWORD *)v18 + 7) = 0;
    v79[0] = v18;
    v87[0] = L"ServicingOrchestrator_CommitServicingTransaction";
    v87[1] = 48;
    v20 = Container::Manager::Core::ResourceHandle::Initialize(v18, v87);
    v72 = v20;
    if ( v20 < 0 )
    {
      v51 = 3829;
      goto LABEL_86;
    }
    v20 = Container::Manager::Core::Details::ResourceBroker::OpenResource(
            *(RTL_SRWLOCK **)(a1 + 128),
            v14 + 4,
            *(_DWORD *)v14,
            (__int64)v79);
    v72 = v20;
    if ( v20 < 0 )
      break;
    if ( v16 != (Container::Manager::Core::ResourceHandle *)v80 )
      goto LABEL_39;
    v22 = (v80 - (__int64)v17) >> 3;
    v23 = 7 * (v22 >> 2) + 8;
    if ( v23 > 0xFFFFFFFFFFFFFFFLL )
      v23 = 0xFFFFFFFFFFFFFFFLL;
    if ( v22 < v23
      && (v24 = utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(&v79[1]),
          v16 = v79[2],
          v17 = v79[1],
          v24) )
    {
LABEL_39:
      *(_QWORD *)v16 = v19;
      v16 = (Container::Manager::Core::ResourceHandle *)((char *)v16 + 8);
      v79[2] = v16;
      v25 = 0;
    }
    else
    {
      v25 = 1;
    }
    if ( v25 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xEFC,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        v21);
    if ( Container::Manager::Core::ResourceHandle::GetType(v19) != 2 )
      goto LABEL_59;
    v29 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(v19);
    if ( *(_DWORD *)(v29 + 52) != 5 )
    {
      if ( *(_DWORD *)(v29 + 52) )
        goto LABEL_59;
    }
    if ( !v15 )
    {
      if ( !(unsigned __int8)utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::insert<utl::_TreeConstIt<_GUID>,void>(
                               v75,
                               *(_QWORD *)(a1 + 192),
                               a1 + 176) )
      {
        v45 = 3848;
        goto LABEL_72;
      }
      v94 = 1;
    }
    for ( k = (__int64)v76;
          ;
          k = utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(
                k,
                v34) )
    {
      if ( (_QWORD *)k == v75 )
        goto LABEL_56;
      v31 = (Container::Manager::Core::ResourceHandle *)operator new(
                                                          0x58u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
      v78 = v31;
      if ( !v31 )
      {
        v45 = 3859;
        goto LABEL_72;
      }
      *((_QWORD *)v31 + 5) = 0;
      *(_QWORD *)v31 = (char *)v31 + 16;
      *((_QWORD *)v31 + 1) = (char *)v31 + 16;
      *((_WORD *)v31 + 8) = 0;
      v88[0] = L"ServicingOrchestrator_CommitServicingTransaction";
      *((_DWORD *)v31 + 8) = 0;
      *((_QWORD *)v31 + 8) = 0;
      *((_QWORD *)v31 + 9) = 0;
      *((_BYTE *)v31 + 80) = 0;
      *((_QWORD *)v31 + 6) = 0;
      *((_QWORD *)v31 + 7) = 0;
      v81 = (__int64)v31;
      v88[1] = 48;
      v32 = Container::Manager::Core::ResourceHandle::Initialize(v31, v88);
      v72 = v32;
      if ( v32 < 0 )
      {
        v46 = 3862;
        goto LABEL_74;
      }
      Uuid1 = (UUID *)(k + 24);
      v32 = Container::Manager::Core::Details::ResourceBroker::OpenResource(
              *(RTL_SRWLOCK **)(a1 + 128),
              k + 24,
              2u,
              (__int64)&v81);
      v72 = v32;
      if ( v32 < 0 )
      {
        v46 = 3867;
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
          (const char *)(unsigned int)v32,
          v72);
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v78);
        operator delete(v78, (const struct std::nothrow_t *)0x58);
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v19);
        goto LABEL_87;
      }
      v81 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(v78);
      v33 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(v19);
      if ( *(_QWORD *)(v33 + 140) == *(_QWORD *)(v81 + 140) && *(_QWORD *)(v33 + 148) == *(_QWORD *)(v81 + 148) )
        break;
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v78);
      operator delete(v78, (const struct std::nothrow_t *)0x58);
      LOBYTE(v34) = 1;
    }
    utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::erase(v75, Uuid1);
    Container::Manager::Core::ResourceHandle::~ResourceHandle(v78);
    operator delete(v78, (const struct std::nothrow_t *)0x58);
LABEL_56:
    v35 = (char *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v35 )
      *(_OWORD *)(v35 + 24) = *(_OWORD *)(v14 + 4);
    utl::_Tree<_GUID,utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>>,0>::_EmplaceImpl(
      v75,
      v89,
      v36,
      v35);
    if ( !v89[0] )
    {
      v45 = 3879;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)0x8007000ELL,
        v72);
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v19);
      operator delete(v19, (const struct std::nothrow_t *)0x58);
      goto LABEL_93;
    }
LABEL_59:
    *(_OWORD *)v83 = 0;
    v84 = 0;
    v37 = Container::Manager::Core::Details::ServicingOrchestrator::CommitServicingTransactionResource(
            a1,
            v79,
            v85[1],
            v83);
    v39 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        (const char *)(unsigned int)v37,
        v72);
      if ( BYTE8(v84) && v83[0] != (void *)-1LL )
      {
        v48 = (char *)v83[1] - (char *)v83[0];
        v83[1] = v83[0];
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Csl::ListEntry<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>,wistd::default_delete<Csl::ListEntry<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>>>>>(
          v47,
          v83[0],
          v48 >> 3);
        operator delete(v83[0], (const struct std::nothrow_t *)&std::nothrow);
      }
      v49 = v79[0];
      if ( v79[0] )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v79[0]);
        operator delete(v49, (const struct std::nothrow_t *)0x58);
      }
      *(_DWORD *)(a2 + 32) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
      v50 = a1 + 160;
      *(_DWORD *)(a1 + 168) = 0;
      goto LABEL_106;
    }
    if ( BYTE8(v84) )
    {
      v40 = (UUID **)v83[0];
      v41 = (UUID **)v83[1];
      while ( v40 != v41 )
      {
        Uuid1 = *v40;
        *v40 = 0;
        Csl::List<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>::EmplaceBack(a3, &Uuid1);
        ++v40;
      }
    }
    else if ( !(unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,0>(
                                  v73,
                                  v79) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF44,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        v42);
    }
    if ( BYTE8(v84) && v83[0] != (void *)-1LL )
    {
      v43 = (char *)v83[1] - (char *)v83[0];
      v83[1] = v83[0];
      utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Csl::ListEntry<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>,wistd::default_delete<Csl::ListEntry<utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation>>>>>>(
        v38,
        v83[0],
        v43 >> 3);
      operator delete(v83[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    v44 = v79[0];
    if ( v79[0] )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v79[0]);
      operator delete(v44, (const struct std::nothrow_t *)0x58);
    }
    v15 = v94;
    v14 += 20;
  }
  v51 = 3834;
LABEL_86:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v51,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
    (const char *)(unsigned int)v20,
    v72);
  Container::Manager::Core::ResourceHandle::~ResourceHandle(v19);
LABEL_87:
  operator delete(v19, (const struct std::nothrow_t *)0x58);
  *(_DWORD *)(a2 + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(a2 + 24));
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v75);
  *(_DWORD *)(a1 + 168) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 160));
  v53 = v73[0];
  if ( v73[0] != (void *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v52,
      v73[0],
      ((char *)v73[1] - (char *)v73[0]) >> 3);
    operator delete(v53, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( v17 != (Container::Manager::Core::ResourceHandle *)-1LL )
    operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v72;
LABEL_111:
  Csl::DurableRegistryTransaction::~DurableRegistryTransaction((Csl::DurableRegistryTransaction *)v85);
  return v7;
}

```

## disassembly

```asm
0x18006b674  mov     rax, rsp
0x18006b677  mov     [rax+18h], r8
0x18006b67b  mov     [rax+10h], rdx
0x18006b67f  mov     [rax+8], rcx
0x18006b683  push    rbp
0x18006b684  push    rbx
0x18006b685  push    rsi
0x18006b686  push    rdi
0x18006b687  push    r12
0x18006b689  push    r13
0x18006b68b  push    r14
0x18006b68d  push    r15
0x18006b68f  lea     rbp, [rax-48h]
0x18006b693  sub     rsp, 108h
0x18006b69a  xorps   xmm0, xmm0
0x18006b69d  lea     rdi, [rcx+0A0h]
0x18006b6a4  movdqu  xmmword ptr [rbp+40h+var_88], xmm0
0x18006b6a9  or      r13, 0FFFFFFFFFFFFFFFFh
0x18006b6ad  xor     r12d, r12d
0x18006b6b0  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006b6b8  mov     rcx, rdi; SRWLock
0x18006b6bb  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x18006b6c1  mov     r14, rdx
0x18006b6c4  mov     [rbp+40h+var_78], r12w
0x18006b6c9  movdqu  xmmword ptr [rsp+140h+var_120+8], xmm0
0x18006b6cf  mov     [rbp+40h+var_C0], r13
0x18006b6d3  mov     [rsp+140h+var_108], r13
0x18006b6d8  call    cs:__imp_AcquireSRWLockExclusive
0x18006b6df  nop     dword ptr [rax+rax+00h]
0x18006b6e4  call    cs:__imp_GetCurrentThreadId
0x18006b6eb  nop     dword ptr [rax+rax+00h]
0x18006b6f0  lea     rbx, [r14+18h]
0x18006b6f4  mov     [rsp+140h+var_E8], r12
0x18006b6f9  mov     [rdi+8], eax
0x18006b6fc  mov     rcx, rbx; SRWLock
0x18006b6ff  lea     rax, [rsp+140h+var_100]
0x18006b704  mov     [rsp+140h+var_100], rax
0x18006b709  lea     rax, [rsp+140h+var_100]
0x18006b70e  mov     [rsp+140h+var_F8], rax
0x18006b713  mov     [rsp+140h+var_F0], rax
0x18006b718  call    cs:__imp_AcquireSRWLockExclusive
0x18006b71f  nop     dword ptr [rax+rax+00h]
0x18006b724  call    cs:__imp_GetCurrentThreadId
0x18006b72b  nop     dword ptr [rax+rax+00h]
0x18006b730  mov     [rbx+8], eax
0x18006b733  cmp     dword ptr [r14+40h], 3
0x18006b738  jnz     short loc_18006B747
0x18006b73a  mov     r9d, 1A31h
0x18006b740  mov     edx, 0ED9h
0x18006b745  jmp     short loc_18006B759
0x18006b747  cmp     dword ptr [r14+40h], 4
0x18006b74c  jnz     short loc_18006B76D
0x18006b74e  mov     r9d, 12Fh; char *
0x18006b754  mov     edx, 0EDDh; void *
0x18006b759  mov     rcx, [rbp+48h]; this
0x18006b75d  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006b764  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006b769  mov     esi, eax
0x18006b76b  jmp     short loc_18006B7A8
0x18006b76d  cmp     dword ptr [r14+40h], 2
0x18006b772  jz      short loc_18006B781
0x18006b774  mov     r9d, 139Fh
0x18006b77a  mov     edx, 0EE1h
0x18006b77f  jmp     short loc_18006B759
0x18006b781  lea     rcx, [rbp+40h+var_88]
0x18006b785  call    ?Initialize@DurableRegistryTransaction@Csl@@QEAAJW4RegistryHive@2@@Z; Csl::DurableRegistryTransaction::Initialize(Csl::RegistryHive)
0x18006b78a  mov     esi, eax
0x18006b78c  test    eax, eax
0x18006b78e  jns     short loc_18006B7DD
0x18006b790  mov     rcx, [rbp+48h]; this
0x18006b794  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006b79b  mov     r9d, eax; char *
0x18006b79e  mov     edx, 0EE6h; void *
0x18006b7a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b7a8  mov     rcx, rbx; SRWLock
0x18006b7ab  mov     [rbx+8], r12d
0x18006b7af  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b7b6  nop     dword ptr [rax+rax+00h]
0x18006b7bb  lea     rcx, [rsp+140h+var_100]
0x18006b7c0  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006b7c5  mov     rcx, rdi; SRWLock
0x18006b7c8  mov     [rdi+8], r12d
0x18006b7cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b7d3  nop     dword ptr [rax+rax+00h]
0x18006b7d8  jmp     loc_18006C11D
0x18006b7dd  mov     rcx, [r14+28h]
0x18006b7e1  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18006b7eb  mov     rax, [r14+30h]
0x18006b7ef  mov     r8, 0FFFFFFFFFFFFFFFh
0x18006b7f9  sub     rax, rcx
0x18006b7fc  sar     rax, 2
0x18006b800  imul    rax, rsi
0x18006b804  test    rax, rax
0x18006b807  jz      short loc_18006B848
0x18006b809  mov     edx, 8
0x18006b80e  cmp     rax, rdx
0x18006b811  jbe     short loc_18006B828
0x18006b813  cmp     rax, r8
0x18006b816  ja      loc_18006B9AF
0x18006b81c  mov     rdx, rax
0x18006b81f  cmp     rax, rax
0x18006b822  ja      loc_18006B9AF
0x18006b828  lea     rcx, [rsp+140h+var_D8+8]
0x18006b82d  call    ?_SetCapacity@?$vector@PEAVResourceHandle@Core@Manager@Container@@V?$allocator@PEAVResourceHandle@Core@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(unsigned __int64)
0x18006b832  test    al, al
0x18006b834  jz      loc_18006B9AF
0x18006b83a  mov     rcx, [r14+28h]
0x18006b83e  mov     r8, 0FFFFFFFFFFFFFFFh
0x18006b848  mov     r15, [r14+30h]
0x18006b84c  mov     rax, r15
0x18006b84f  sub     rax, rcx
0x18006b852  sar     rax, 2
0x18006b856  imul    rax, rsi
0x18006b85a  test    rax, rax
0x18006b85d  jz      short loc_18006B894
0x18006b85f  mov     edx, 8
0x18006b864  cmp     rax, rdx
0x18006b867  jbe     short loc_18006B87E
0x18006b869  cmp     rax, r8
0x18006b86c  ja      loc_18006BA14
0x18006b872  mov     rdx, rax
0x18006b875  cmp     rax, rax
0x18006b878  ja      loc_18006BA14
0x18006b87e  lea     rcx, [rsp+140h+var_120+8]
0x18006b883  call    ?_SetCapacity@?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>::_SetCapacity(unsigned __int64)
0x18006b888  test    al, al
0x18006b88a  jz      loc_18006BA14
0x18006b890  mov     r15, [r14+30h]
0x18006b894  mov     r14, [r14+28h]
0x18006b898  mov     bl, r12b
0x18006b89b  mov     rsi, qword ptr [rsp+140h+var_D8+10h]
0x18006b8a0  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006b8a7  mov     r13, qword ptr [rsp+140h+var_D8+8]
0x18006b8ac  mov     [rbp+40h+arg_18], bl
0x18006b8af  cmp     r14, r15
0x18006b8b2  jz      loc_18006BFF3
0x18006b8b8  mov     rdx, r12; struct std::nothrow_t *
0x18006b8bb  mov     ecx, 58h ; 'X'; unsigned __int64
0x18006b8c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006b8c5  xor     edx, edx
0x18006b8c7  mov     rdi, rax
0x18006b8ca  test    rax, rax
0x18006b8cd  jz      loc_18006BF59
0x18006b8d3  lea     rcx, [rax+10h]
0x18006b8d7  mov     [rax+28h], rdx
0x18006b8db  mov     [rax], rcx
0x18006b8de  mov     [rax+8], rcx
0x18006b8e2  mov     [rcx], dx
0x18006b8e5  mov     rcx, rdi
0x18006b8e8  mov     [rax+20h], edx
0x18006b8eb  mov     [rax+40h], rdx
0x18006b8ef  mov     [rax+48h], rdx
0x18006b8f3  mov     [rax+50h], dl
0x18006b8f6  mov     [rax+30h], rdx
0x18006b8fa  mov     [rax+38h], rdx
0x18006b8fe  lea     rdx, [rbp+40h+var_70]
0x18006b902  mov     qword ptr [rsp+140h+var_D8], rax
0x18006b907  lea     rax, aServicingorche_2; "ServicingOrchestrator_CommitServicingTr"...
0x18006b90e  mov     [rbp+40h+var_70], rax
0x18006b912  mov     [rbp+40h+var_68], 30h ; '0'
0x18006b91a  call    ?Initialize@ResourceHandle@Core@Manager@Container@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Container::Manager::Core::ResourceHandle::Initialize(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18006b91f  mov     dword ptr [rsp+140h+var_120], eax; int
0x18006b923  test    eax, eax
0x18006b925  js      loc_18006BEA5
0x18006b92b  mov     rcx, [rbp+40h+arg_0]
0x18006b92f  lea     rdx, [r14+4]
0x18006b933  mov     r8d, [r14]
0x18006b936  lea     r9, [rsp+140h+var_D8]
0x18006b93b  mov     rcx, [rcx+80h]
0x18006b942  call    ?OpenResource@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@W4ResourceType@2345@AEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ResourceBroker::OpenResource(_GUID const &,Container::Manager::Core::Details::ResourceType,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> &)
0x18006b947  mov     dword ptr [rsp+140h+var_120], eax; int
0x18006b94b  test    eax, eax
0x18006b94d  js      loc_18006BE9E
0x18006b953  mov     rcx, [rbp+40h+var_C0]
0x18006b957  cmp     rsi, rcx
0x18006b95a  jnz     loc_18006BAAB
0x18006b960  sub     rcx, r13
0x18006b963  sar     rcx, 3
0x18006b967  mov     rax, rcx
0x18006b96a  shr     rax, 2
0x18006b96e  imul    rdx, rax, 7
0x18006b972  mov     rax, 0FFFFFFFFFFFFFFFh
0x18006b97c  add     rdx, 8
0x18006b980  cmp     rdx, rax
0x18006b983  cmova   rdx, rax
0x18006b987  cmp     rcx, rdx
0x18006b98a  jnb     short loc_18006B9A8
0x18006b98c  lea     rcx, [rsp+140h+var_D8+8]
0x18006b991  call    ?_SetCapacity@?$vector@PEAVResourceHandle@Core@Manager@Container@@V?$allocator@PEAVResourceHandle@Core@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Core::ResourceHandle *,utl::allocator<Container::Manager::Core::ResourceHandle *>>::_SetCapacity(unsigned __int64)
0x18006b996  mov     rsi, qword ptr [rsp+140h+var_D8+10h]
0x18006b99b  mov     r13, qword ptr [rsp+140h+var_D8+8]
0x18006b9a0  test    al, al
0x18006b9a2  jnz     loc_18006BAAB
0x18006b9a8  mov     al, 1
0x18006b9aa  jmp     loc_18006BAB9
0x18006b9af  mov     rcx, [rbp+48h]; this
0x18006b9b3  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006b9ba  mov     r9d, 8007000Eh; char *
0x18006b9c0  mov     edx, 0EE8h; void *
0x18006b9c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b9ca  mov     rcx, rbx; SRWLock
0x18006b9cd  mov     [rbx+8], r12d
0x18006b9d1  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b9d8  nop     dword ptr [rax+rax+00h]
0x18006b9dd  lea     rcx, [rsp+140h+var_100]
0x18006b9e2  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006b9e7  mov     rcx, rdi; SRWLock
0x18006b9ea  mov     [rdi+8], r12d
0x18006b9ee  call    cs:__imp_ReleaseSRWLockExclusive
0x18006b9f5  nop     dword ptr [rax+rax+00h]
0x18006b9fa  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x18006b9ff  cmp     rcx, r13
0x18006ba02  jz      loc_18006BAA1
0x18006ba08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006ba0f  jmp     loc_18006BA9C
0x18006ba14  mov     rcx, [rbp+48h]; this
0x18006ba18  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006ba1f  mov     r9d, 8007000Eh; char *
0x18006ba25  mov     edx, 0EE9h; void *
0x18006ba2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ba2f  mov     rcx, rbx; SRWLock
0x18006ba32  mov     [rbx+8], r12d
0x18006ba36  call    cs:__imp_ReleaseSRWLockExclusive
0x18006ba3d  nop     dword ptr [rax+rax+00h]
0x18006ba42  lea     rcx, [rsp+140h+var_100]
0x18006ba47  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ba4c  mov     rcx, rdi; SRWLock
0x18006ba4f  mov     [rdi+8], r12d
0x18006ba53  call    cs:__imp_ReleaseSRWLockExclusive
0x18006ba5a  nop     dword ptr [rax+rax+00h]
0x18006ba5f  mov     rbx, [rsp+140h+var_120+8]
0x18006ba64  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006ba6b  cmp     rbx, r13
0x18006ba6e  jz      short loc_18006BA8F
0x18006ba70  mov     r8, [rsp+140h+var_110]
0x18006ba75  mov     rdx, rbx
0x18006ba78  sub     r8, rbx
0x18006ba7b  sar     r8, 3
0x18006ba7f  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x18006ba84  mov     rdx, r12; struct std::nothrow_t *
0x18006ba87  mov     rcx, rbx; void *
0x18006ba8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006ba8f  mov     rcx, qword ptr [rsp+140h+var_D8+8]; void *
0x18006ba94  cmp     rcx, r13
0x18006ba97  jz      short loc_18006BAA1
0x18006ba99  mov     rdx, r12; struct std::nothrow_t *
0x18006ba9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006baa1  mov     esi, 8007000Eh
0x18006baa6  jmp     loc_18006C11D
0x18006baab  mov     [rsi], rdi
0x18006baae  add     rsi, 8
0x18006bab2  mov     qword ptr [rsp+140h+var_D8+10h], rsi
0x18006bab7  xor     al, al
0x18006bab9  mov     rcx, [rbp+48h]; this
0x18006babd  test    al, al
0x18006babf  jnz     loc_18006C286
0x18006bac5  mov     rcx, rdi; this
0x18006bac8  call    ?GetType@ResourceHandle@Core@Manager@Container@@QEBA?AW4ResourceType@Details@234@XZ; Container::Manager::Core::ResourceHandle::GetType(void)
0x18006bacd  cmp     eax, 2
0x18006bad0  jnz     loc_18006BC9D
0x18006bad6  mov     rcx, rdi
0x18006bad9  call    ??$Get@VLayer@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVLayer@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(void)
0x18006bade  cmp     dword ptr [rax+34h], 5
0x18006bae2  jz      short loc_18006BAEE
0x18006bae4  cmp     dword ptr [rax+34h], 0
0x18006bae8  jnz     loc_18006BC9D
0x18006baee  test    bl, bl
0x18006baf0  jnz     short loc_18006BB1A
0x18006baf2  mov     rdx, [rbp+40h+arg_0]
0x18006baf6  lea     rcx, [rsp+140h+var_100]
0x18006bafb  lea     r8, [rdx+0B0h]
0x18006bb02  mov     rdx, [rdx+0C0h]
0x18006bb09  call    ??$insert@V?$_TreeConstIt@U_GUID@@@utl@@X@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@QEAA_NV?$_TreeConstIt@U_GUID@@@1@0@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::insert<utl::_TreeConstIt<_GUID>,void>(utl::_TreeConstIt<_GUID>,utl::_TreeConstIt<_GUID>)
0x18006bb0e  test    al, al
0x18006bb10  jz      loc_18006BD72
0x18006bb16  mov     [rbp+40h+arg_18], 1
0x18006bb1a  mov     rbx, [rsp+140h+var_F0]
0x18006bb1f  lea     rax, [rsp+140h+var_100]
0x18006bb24  cmp     rbx, rax
0x18006bb27  jz      loc_18006BC65
0x18006bb2d  mov     rdx, r12; struct std::nothrow_t *
0x18006bb30  mov     ecx, 58h ; 'X'; unsigned __int64
0x18006bb35  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006bb3a  xor     r8d, r8d
0x18006bb3d  mov     [rsp+140h+var_E0], rax
0x18006bb42  test    rax, rax
0x18006bb45  jz      loc_18006BDF0
0x18006bb4b  lea     rdx, [rax+10h]
0x18006bb4f  mov     [rax+28h], r8
0x18006bb53  mov     [rax], rdx
0x18006bb56  lea     rcx, aServicingorche_2; "ServicingOrchestrator_CommitServicingTr"...
0x18006bb5d  mov     [rax+8], rdx
0x18006bb61  mov     [rdx], r8w
0x18006bb65  lea     rdx, [rbp+40h+var_60]
0x18006bb69  mov     [rbp+40h+var_60], rcx
0x18006bb6d  mov     rcx, rax
0x18006bb70  mov     [rax+20h], r8d
0x18006bb74  mov     [rax+40h], r8
0x18006bb78  mov     [rax+48h], r8
0x18006bb7c  mov     [rax+50h], r8b
  ... truncated ...
```
