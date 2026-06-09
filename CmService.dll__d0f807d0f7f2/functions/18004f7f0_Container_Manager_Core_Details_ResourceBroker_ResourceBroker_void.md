# Container::Manager::Core::Details::ResourceBroker::~ResourceBroker(void)

- ea: `0x18004f7f0`
- end: `0x18004fe03`
- name: `??1ResourceBroker@Details@Core@Manager@Container@@QEAA@XZ`
- size: `1555`
- prototype: `void(Container::Manager::Core::Details::ResourceBroker *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180076510`

## callees

- `0x180004fc4`
- `0x180007b3c`
- `0x18000a10c`
- `0x180016718`
- `0x18003ed4c`
- `0x1800471dc`
- `0x18004f0e4`
- `0x18004f7f0`
- `0x180050a10`
- `0x18005d248`
- `0x180065b98`
- `0x180066354`
- `0x1800e8950`
- `0x1800eb50c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004f851`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004f851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004f877`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004fc4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004f877`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004fc4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f819`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f97c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f819`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f97c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f83d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f992`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f83d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f885`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc60`

## string_xrefs

- `0x18004fcc7`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x18004fcd9`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x18004fca0`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fcb5`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fd0a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fd1f`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fd50`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fd65`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fd96`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fdab`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fddc`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18004fdf1`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ResourceBroker::~ResourceBroker(
        Container::Manager::Core::Details::ResourceBroker *this)
{
  struct _TP_WORK *v2; // rsi
  DWORD LastError; // ebx
  const char *v4; // r9
  utl::_RefCountBase *v5; // rcx
  utl::_RefCountBase *v6; // rcx
  utl::_RefCountBase *v7; // rcx
  utl::_RefCountBase *v8; // rcx
  utl::_RefCountBase *v9; // rcx
  char *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rbx
  utl::_RefCountBase *v14; // rcx
  __int64 v15; // rax
  char *v16; // r10
  __int64 v17; // rax
  char *v18; // r10
  __int64 v19; // rax
  char *v20; // r10
  __int64 v21; // rax
  char *v22; // r10
  __int64 v23; // rax
  utl::_RefCountBase *v24; // rcx
  utl::_RefCountBase *v25; // rcx
  utl::_RefCountBase *v26; // rcx
  utl::_RefCountBase *v27; // rcx
  utl::_RefCountBase *v28; // rcx
  Container::Manager::Core::Details::BaseImageManager *v29; // rbx
  _QWORD *v30; // rbx
  HKEY v31; // rcx
  _QWORD *v32; // rbx
  utl::_RefCountBase *v33; // rcx
  _QWORD *v34; // rbx
  HKEY v35; // rcx
  char *v36; // rbx
  struct _TP_WORK *v37; // rcx
  HKEY v38; // rcx
  Container::Manager::Core::Details::Resource *v39; // rax
  unsigned int v40; // eax
  int v41; // eax
  const char *v42; // r9
  Container::Manager::Core::Details::Resource *v43; // rax
  unsigned int v44; // eax
  int v45; // eax
  const char *v46; // r9
  Container::Manager::Core::Details::Resource *v47; // rax
  unsigned int v48; // eax
  int v49; // eax
  const char *v50; // r9
  Container::Manager::Core::Details::Resource *v51; // rax
  unsigned int v52; // eax
  int v53; // eax
  const char *v54; // r9
  Container::Manager::Core::Details::Resource *v55; // rax
  unsigned int v56; // eax
  int v57; // eax
  const char *v58; // r9
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v61; // [rsp+40h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 14) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 2);
    GetCurrentThreadId();
    *((_BYTE *)this + 32) = 0;
    *((_DWORD *)this + 6) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 5), 1);
    v2 = (struct _TP_WORK *)*((_QWORD *)this + 5);
    if ( v2 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v2);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 5) = 0;
    Container::Manager::Core::Details::ResourceBroker::UnwindResourceGraph(this);
    *((_QWORD *)this + 33) = 0;
    v5 = (utl::_RefCountBase *)*((_QWORD *)this + 34);
    *((_QWORD *)this + 34) = 0;
    if ( v5 )
      utl::_RefCountBase::_DecStrong(v5);
    *((_QWORD *)this + 35) = 0;
    v6 = (utl::_RefCountBase *)*((_QWORD *)this + 36);
    *((_QWORD *)this + 36) = 0;
    if ( v6 )
      utl::_RefCountBase::_DecStrong(v6);
    *((_QWORD *)this + 37) = 0;
    v7 = (utl::_RefCountBase *)*((_QWORD *)this + 38);
    *((_QWORD *)this + 38) = 0;
    if ( v7 )
      utl::_RefCountBase::_DecStrong(v7);
    *((_QWORD *)this + 39) = 0;
    v8 = (utl::_RefCountBase *)*((_QWORD *)this + 40);
    *((_QWORD *)this + 40) = 0;
    if ( v8 )
      utl::_RefCountBase::_DecStrong(v8);
    *((_QWORD *)this + 41) = 0;
    v9 = (utl::_RefCountBase *)*((_QWORD *)this + 42);
    *((_QWORD *)this + 42) = 0;
    if ( v9 )
      utl::_RefCountBase::_DecStrong(v9);
    v10 = (char *)this + 192;
    v11 = *((_QWORD *)this + 26);
    v61 = v11;
    while ( (char *)v11 != v10 )
    {
      v12 = *(_QWORD *)(v11 + 40);
      if ( *(_DWORD *)(v12 + 16) != 4 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
          v4);
      if ( !*(_BYTE *)(v12 + 88) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
          v4);
      v13 = *(_QWORD *)(v12 + 80);
      AcquireSRWLockExclusive((PSRWLOCK)v13);
      *(_DWORD *)(v13 + 72) = 3;
      ReleaseSRWLockExclusive((PSRWLOCK)v13);
      Container::Manager::Core::Details::Zygote::Delete((Container::Manager::Core::Details::Zygote *)v13);
      *(_QWORD *)(v13 + 136) = 0;
      v14 = *(utl::_RefCountBase **)(v13 + 144);
      *(_QWORD *)(v13 + 144) = 0;
      if ( v14 )
        utl::_RefCountBase::_DecStrong(v14);
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v11 = v61;
    }
    v15 = *((_QWORD *)this + 26);
    v61 = v15;
    while ( (char *)v15 != v10 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v15 + 40) + 152LL) )
      {
        v43 = (Container::Manager::Core::Details::Resource *)wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->();
        v44 = Container::Manager::Core::Details::Resource::LogResourceInformation(v43);
        v45 = wil::verify_hresult<long>(v44);
        if ( v45 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAE3,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v45,
            savedregs);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xAE6,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v46);
      }
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v15 = v61;
    }
    v16 = (char *)this + 80;
    v17 = *((_QWORD *)this + 12);
    v61 = v17;
    while ( (char *)v17 != v16 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v17 + 40) + 152LL) )
      {
        v47 = (Container::Manager::Core::Details::Resource *)wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->();
        v48 = Container::Manager::Core::Details::Resource::LogResourceInformation(v47);
        v49 = wil::verify_hresult<long>(v48);
        if ( v49 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAF1,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v49,
            savedregs);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xAF4,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v50);
      }
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v17 = v61;
    }
    v18 = (char *)this + 120;
    v19 = *((_QWORD *)this + 17);
    v61 = v19;
    while ( (char *)v19 != v18 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v19 + 40) + 152LL) )
      {
        v51 = (Container::Manager::Core::Details::Resource *)wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->();
        v52 = Container::Manager::Core::Details::Resource::LogResourceInformation(v51);
        v53 = wil::verify_hresult<long>(v52);
        if ( v53 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAFF,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v53,
            savedregs);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB02,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v54);
      }
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v19 = v61;
    }
    v20 = (char *)this + 160;
    v21 = *((_QWORD *)this + 22);
    v61 = v21;
    while ( (char *)v21 != v20 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v21 + 40) + 152LL) )
      {
        v55 = (Container::Manager::Core::Details::Resource *)wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->();
        v56 = Container::Manager::Core::Details::Resource::LogResourceInformation(v55);
        v57 = wil::verify_hresult<long>(v56);
        if ( v57 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB0D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v57,
            savedregs);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB10,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v58);
      }
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v21 = v61;
    }
    v22 = (char *)this + 232;
    v23 = *((_QWORD *)this + 31);
    v61 = v23;
    while ( (char *)v23 != v22 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v23 + 40) + 152LL) )
      {
        v39 = (Container::Manager::Core::Details::Resource *)wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->();
        v40 = Container::Manager::Core::Details::Resource::LogResourceInformation(v39);
        v41 = wil::verify_hresult<long>(v40);
        if ( v41 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB1B,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v41,
            savedregs);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB1E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v42);
      }
      utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v61);
      v23 = v61;
    }
  }
  v24 = (utl::_RefCountBase *)*((_QWORD *)this + 42);
  if ( v24 )
    utl::_RefCountBase::_DecStrong(v24);
  v25 = (utl::_RefCountBase *)*((_QWORD *)this + 40);
  if ( v25 )
    utl::_RefCountBase::_DecStrong(v25);
  v26 = (utl::_RefCountBase *)*((_QWORD *)this + 38);
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  v27 = (utl::_RefCountBase *)*((_QWORD *)this + 36);
  if ( v27 )
    utl::_RefCountBase::_DecStrong(v27);
  v28 = (utl::_RefCountBase *)*((_QWORD *)this + 34);
  if ( v28 )
    utl::_RefCountBase::_DecStrong(v28);
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear((char *)this + 232);
  v29 = (Container::Manager::Core::Details::BaseImageManager *)*((_QWORD *)this + 28);
  *((_QWORD *)this + 28) = 0;
  if ( v29 )
  {
    Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(v29);
    operator delete(v29, (const struct std::nothrow_t *)0x10);
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear((char *)this + 192);
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear((char *)this + 160);
  v30 = (_QWORD *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = 0;
  if ( v30 )
  {
    v31 = (HKEY)v30[1];
    if ( v31 )
      RegCloseKey(v31);
    operator delete(v30, (const struct std::nothrow_t *)0x10);
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear((char *)this + 120);
  v32 = (_QWORD *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v32 )
  {
    v33 = (utl::_RefCountBase *)v32[1];
    if ( v33 )
      utl::_RefCountBase::_DecStrong(v33);
    operator delete(v32, (const struct std::nothrow_t *)0x10);
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear((char *)this + 80);
  v34 = (_QWORD *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v34 )
  {
    v35 = (HKEY)v34[1];
    if ( v35 )
      RegCloseKey(v35);
    operator delete(v34, (const struct std::nothrow_t *)0x10);
  }
  v36 = (char *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v36 )
  {
    wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>::~unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>(v36 + 24);
    operator delete(v36, (const struct std::nothrow_t *)0x20);
  }
  v37 = (struct _TP_WORK *)*((_QWORD *)this + 5);
  if ( v37 )
    CloseThreadpoolWork(v37);
  v38 = (HKEY)*((_QWORD *)this + 1);
  if ( v38 )
    RegCloseKey(v38);
}

```

## disassembly

```asm
0x18004f7f0  mov     [rsp-18h+arg_8], rbx
0x18004f7f5  mov     [rsp-18h+arg_10], rsi
0x18004f7fa  push    rbp
0x18004f7fb  push    rdi
0x18004f7fc  push    r14; int
0x18004f7fe  mov     rbp, rsp
0x18004f801  sub     rsp, 20h
0x18004f805  mov     rdi, rcx
0x18004f808  xor     r14d, r14d
0x18004f80b  cmp     [rcx+70h], r14
0x18004f80f  jz      loc_18004FADE
0x18004f815  add     rcx, 10h; SRWLock
0x18004f819  call    cs:__imp_AcquireSRWLockExclusive
0x18004f820  nop     dword ptr [rax+rax+00h]
0x18004f825  call    cs:__imp_GetCurrentThreadId
0x18004f82c  nop     dword ptr [rax+rax+00h]
0x18004f831  mov     [rdi+20h], r14b
0x18004f835  mov     [rdi+18h], r14d
0x18004f839  lea     rcx, [rdi+10h]; SRWLock
0x18004f83d  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f844  nop     dword ptr [rax+rax+00h]
0x18004f849  lea     edx, [r14+1]; fCancelPendingCallbacks
0x18004f84d  mov     rcx, [rdi+28h]; pwk
0x18004f851  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004f858  nop     dword ptr [rax+rax+00h]
0x18004f85d  mov     rsi, [rdi+28h]
0x18004f861  test    rsi, rsi
0x18004f864  jz      short loc_18004F891
0x18004f866  call    cs:__imp_GetLastError
0x18004f86d  nop     dword ptr [rax+rax+00h]
0x18004f872  mov     ebx, eax
0x18004f874  mov     rcx, rsi; pwk
0x18004f877  call    cs:__imp_CloseThreadpoolWork
0x18004f87e  nop     dword ptr [rax+rax+00h]
0x18004f883  mov     ecx, ebx; dwErrCode
0x18004f885  call    cs:__imp_SetLastError
0x18004f88c  nop     dword ptr [rax+rax+00h]
0x18004f891  mov     [rdi+28h], r14
0x18004f895  mov     rcx, rdi; this
0x18004f898  call    ?UnwindResourceGraph@ResourceBroker@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ResourceBroker::UnwindResourceGraph(void)
0x18004f89d  mov     [rdi+108h], r14
0x18004f8a4  mov     rcx, [rdi+110h]; this
0x18004f8ab  mov     [rdi+110h], r14
0x18004f8b2  test    rcx, rcx
0x18004f8b5  jz      short loc_18004F8BD
0x18004f8b7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f8bc  nop
0x18004f8bd  mov     [rdi+118h], r14
0x18004f8c4  mov     rcx, [rdi+120h]; this
0x18004f8cb  mov     [rdi+120h], r14
0x18004f8d2  test    rcx, rcx
0x18004f8d5  jz      short loc_18004F8DD
0x18004f8d7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f8dc  nop
0x18004f8dd  mov     [rdi+128h], r14
0x18004f8e4  mov     rcx, [rdi+130h]; this
0x18004f8eb  mov     [rdi+130h], r14
0x18004f8f2  test    rcx, rcx
0x18004f8f5  jz      short loc_18004F8FD
0x18004f8f7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f8fc  nop
0x18004f8fd  mov     [rdi+138h], r14
0x18004f904  mov     rcx, [rdi+140h]; this
0x18004f90b  mov     [rdi+140h], r14
0x18004f912  test    rcx, rcx
0x18004f915  jz      short loc_18004F91D
0x18004f917  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f91c  nop
0x18004f91d  mov     [rdi+148h], r14
0x18004f924  mov     rcx, [rdi+150h]; this
0x18004f92b  mov     [rdi+150h], r14
0x18004f932  test    rcx, rcx
0x18004f935  jz      short loc_18004F93D
0x18004f937  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f93c  nop
0x18004f93d  lea     rsi, [rdi+0C0h]
0x18004f944  mov     rax, [rsi+10h]
0x18004f948  mov     [rbp+arg_0], rax
0x18004f94c  cmp     rax, rsi
0x18004f94f  jz      loc_18004F9D8
0x18004f955  mov     rbx, [rax+28h]
0x18004f959  mov     rcx, [rbp+18h]; this
0x18004f95d  cmp     dword ptr [rbx+10h], 4
0x18004f961  jnz     loc_18004FCD9
0x18004f967  mov     rcx, [rbp+18h]; this
0x18004f96b  cmp     [rbx+58h], r14b
0x18004f96f  jz      loc_18004FCC7
0x18004f975  mov     rbx, [rbx+50h]
0x18004f979  mov     rcx, rbx; SRWLock
0x18004f97c  call    cs:__imp_AcquireSRWLockExclusive
0x18004f983  nop     dword ptr [rax+rax+00h]
0x18004f988  mov     dword ptr [rbx+48h], 3
0x18004f98f  mov     rcx, rbx; SRWLock
0x18004f992  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f999  nop     dword ptr [rax+rax+00h]
0x18004f99e  mov     rcx, rbx; this
0x18004f9a1  call    ?Delete@Zygote@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::Zygote::Delete(void)
0x18004f9a6  mov     [rbx+88h], r14
0x18004f9ad  mov     rcx, [rbx+90h]; this
0x18004f9b4  mov     [rbx+90h], r14
0x18004f9bb  test    rcx, rcx
0x18004f9be  jz      short loc_18004F9C6
0x18004f9c0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f9c5  nop
0x18004f9c6  lea     rcx, [rbp+arg_0]
0x18004f9ca  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004f9cf  mov     rax, [rbp+arg_0]
0x18004f9d3  jmp     loc_18004F94C
0x18004f9d8  mov     rax, [rsi+10h]
0x18004f9dc  mov     [rbp+arg_0], rax
0x18004f9e0  cmp     rax, rsi
0x18004f9e3  jz      short loc_18004FA08
0x18004f9e5  lea     rcx, [rax+28h]
0x18004f9e9  mov     rax, [rcx]
0x18004f9ec  cmp     [rax+98h], r14
0x18004f9f3  jnz     loc_18004FCEB
0x18004f9f9  lea     rcx, [rbp+arg_0]
0x18004f9fd  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004fa02  mov     rax, [rbp+arg_0]
0x18004fa06  jmp     short loc_18004F9E0
0x18004fa08  lea     r10, [rdi+50h]
0x18004fa0c  mov     rax, [r10+10h]
0x18004fa10  mov     [rbp+arg_0], rax
0x18004fa14  cmp     rax, r10
0x18004fa17  jz      short loc_18004FA3C
0x18004fa19  lea     rcx, [rax+28h]
0x18004fa1d  mov     rax, [rcx]
0x18004fa20  cmp     [rax+98h], r14
0x18004fa27  jnz     loc_18004FD31
0x18004fa2d  lea     rcx, [rbp+arg_0]
0x18004fa31  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004fa36  mov     rax, [rbp+arg_0]
0x18004fa3a  jmp     short loc_18004FA14
0x18004fa3c  lea     r10, [rdi+78h]
0x18004fa40  mov     rax, [r10+10h]
0x18004fa44  mov     [rbp+arg_0], rax
0x18004fa48  cmp     rax, r10
0x18004fa4b  jz      short loc_18004FA70
0x18004fa4d  lea     rcx, [rax+28h]
0x18004fa51  mov     rax, [rcx]
0x18004fa54  cmp     [rax+98h], r14
0x18004fa5b  jnz     loc_18004FD77
0x18004fa61  lea     rcx, [rbp+arg_0]
0x18004fa65  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004fa6a  mov     rax, [rbp+arg_0]
0x18004fa6e  jmp     short loc_18004FA48
0x18004fa70  lea     r10, [rdi+0A0h]
0x18004fa77  mov     rax, [r10+10h]
0x18004fa7b  mov     [rbp+arg_0], rax
0x18004fa7f  cmp     rax, r10
0x18004fa82  jz      short loc_18004FAA7
0x18004fa84  lea     rcx, [rax+28h]
0x18004fa88  mov     rax, [rcx]
0x18004fa8b  cmp     [rax+98h], r14
0x18004fa92  jnz     loc_18004FDBD
0x18004fa98  lea     rcx, [rbp+arg_0]
0x18004fa9c  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004faa1  mov     rax, [rbp+arg_0]
0x18004faa5  jmp     short loc_18004FA7F
0x18004faa7  lea     r10, [rdi+0E8h]
0x18004faae  mov     rax, [r10+10h]
0x18004fab2  mov     [rbp+arg_0], rax
0x18004fab6  cmp     rax, r10
0x18004fab9  jz      short loc_18004FADE
0x18004fabb  lea     rcx, [rax+28h]
0x18004fabf  mov     rax, [rcx]
0x18004fac2  cmp     [rax+98h], r14
0x18004fac9  jnz     loc_18004FC81
0x18004facf  lea     rcx, [rbp+arg_0]
0x18004fad3  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x18004fad8  mov     rax, [rbp+arg_0]
0x18004fadc  jmp     short loc_18004FAB6
0x18004fade  mov     rcx, [rdi+150h]; this
0x18004fae5  test    rcx, rcx
0x18004fae8  jz      short loc_18004FAF0
0x18004faea  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004faef  nop
0x18004faf0  mov     rcx, [rdi+140h]; this
0x18004faf7  test    rcx, rcx
0x18004fafa  jz      short loc_18004FB02
0x18004fafc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004fb01  nop
0x18004fb02  mov     rcx, [rdi+130h]; this
0x18004fb09  test    rcx, rcx
0x18004fb0c  jz      short loc_18004FB14
0x18004fb0e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004fb13  nop
0x18004fb14  mov     rcx, [rdi+120h]; this
0x18004fb1b  test    rcx, rcx
0x18004fb1e  jz      short loc_18004FB26
0x18004fb20  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004fb25  nop
0x18004fb26  mov     rcx, [rdi+110h]; this
0x18004fb2d  test    rcx, rcx
0x18004fb30  jz      short loc_18004FB38
0x18004fb32  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004fb37  nop
0x18004fb38  lea     rcx, [rdi+0E8h]
0x18004fb3f  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear(void)
0x18004fb44  mov     rbx, [rdi+0E0h]
0x18004fb4b  mov     [rdi+0E0h], r14
0x18004fb52  mov     esi, 10h
0x18004fb57  test    rbx, rbx
0x18004fb5a  jz      short loc_18004FB6E
0x18004fb5c  mov     rcx, rbx; this
0x18004fb5f  call    ??1BaseImageManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BaseImageManager::~BaseImageManager(void)
0x18004fb64  mov     edx, esi; struct std::nothrow_t *
0x18004fb66  mov     rcx, rbx; void *
0x18004fb69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fb6e  lea     rcx, [rdi+0C0h]
0x18004fb75  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear(void)
0x18004fb7a  lea     rcx, [rdi+0A0h]
0x18004fb81  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear(void)
0x18004fb86  mov     rbx, [rdi+98h]
0x18004fb8d  mov     [rdi+98h], r14
0x18004fb94  test    rbx, rbx
0x18004fb97  jz      short loc_18004FBB9
0x18004fb99  mov     rcx, [rbx+8]; hKey
0x18004fb9d  test    rcx, rcx
0x18004fba0  jz      short loc_18004FBAE
0x18004fba2  call    cs:__imp_RegCloseKey
0x18004fba9  nop     dword ptr [rax+rax+00h]
0x18004fbae  mov     rdx, rsi; struct std::nothrow_t *
0x18004fbb1  mov     rcx, rbx; void *
0x18004fbb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fbb9  lea     rcx, [rdi+78h]
0x18004fbbd  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear(void)
0x18004fbc2  mov     rbx, [rdi+70h]
0x18004fbc6  mov     [rdi+70h], r14
0x18004fbca  test    rbx, rbx
0x18004fbcd  jz      short loc_18004FBE9
0x18004fbcf  mov     rcx, [rbx+8]; this
0x18004fbd3  test    rcx, rcx
0x18004fbd6  jz      short loc_18004FBDE
0x18004fbd8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004fbdd  nop
0x18004fbde  mov     rdx, rsi; struct std::nothrow_t *
0x18004fbe1  mov     rcx, rbx; void *
0x18004fbe4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fbe9  lea     rcx, [rdi+50h]
0x18004fbed  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>,0>::clear(void)
0x18004fbf2  mov     rbx, [rdi+48h]
0x18004fbf6  mov     [rdi+48h], r14
0x18004fbfa  test    rbx, rbx
0x18004fbfd  jz      short loc_18004FC1F
0x18004fbff  mov     rcx, [rbx+8]; hKey
0x18004fc03  test    rcx, rcx
0x18004fc06  jz      short loc_18004FC14
0x18004fc08  call    cs:__imp_RegCloseKey
0x18004fc0f  nop     dword ptr [rax+rax+00h]
0x18004fc14  mov     rdx, rsi; struct std::nothrow_t *
0x18004fc17  mov     rcx, rbx; void *
0x18004fc1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fc1f  mov     rbx, [rdi+30h]
0x18004fc23  mov     [rdi+30h], r14
0x18004fc27  test    rbx, rbx
0x18004fc2a  jz      short loc_18004FC42
0x18004fc2c  lea     rcx, [rbx+18h]
0x18004fc30  call    ??1?$unique_ptr@V?$ListEntry@PEAVComputeSystemReaperContext@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVComputeSystemReaperContext@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>::~unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>(void)
0x18004fc35  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18004fc3a  mov     rcx, rbx; void *
0x18004fc3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fc42  mov     rcx, [rdi+28h]; pwk
0x18004fc46  test    rcx, rcx
0x18004fc49  jz      short loc_18004FC57
0x18004fc4b  call    cs:__imp_CloseThreadpoolWork
0x18004fc52  nop     dword ptr [rax+rax+00h]
0x18004fc57  mov     rcx, [rdi+8]; hKey
0x18004fc5b  test    rcx, rcx
0x18004fc5e  jz      short loc_18004FC6D
0x18004fc60  call    cs:__imp_RegCloseKey
0x18004fc67  nop     dword ptr [rax+rax+00h]
0x18004fc6c  nop
0x18004fc6d  mov     rbx, [rsp+20h+arg_8]
0x18004fc72  mov     rsi, [rsp+20h+arg_10]
0x18004fc77  add     rsp, 20h
0x18004fc7b  pop     r14
0x18004fc7d  pop     rdi
0x18004fc7e  pop     rbp
0x18004fc7f  retn
0x18004fc81  call    ??C?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@QEBAPEAVResource@Details@Core@Manager@Container@@XZ; wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>::operator->(void)
0x18004fc86  mov     rcx, rax; this
0x18004fc89  call    ?LogResourceInformation@Resource@Details@Core@Manager@Container@@AEBAJXZ; Container::Manager::Core::Details::Resource::LogResourceInformation(void)
0x18004fc8e  mov     ecx, eax
0x18004fc90  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004fc95  test    eax, eax
0x18004fc97  jns     short loc_18004FCB1
0x18004fc99  mov     rcx, [rbp+18h]; this
0x18004fc9d  mov     r9d, eax; char *
0x18004fca0  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18004fca7  mov     edx, 0B1Bh; void *
0x18004fcac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004fcb1  mov     rcx, [rbp+18h]; this
0x18004fcb5  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18004fcbc  mov     edx, 0B1Eh; void *
0x18004fcc1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004fcc7  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18004fcce  mov     edx, 6Bh ; 'k'; void *
0x18004fcd3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004fcd9  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
  ... truncated ...
```
