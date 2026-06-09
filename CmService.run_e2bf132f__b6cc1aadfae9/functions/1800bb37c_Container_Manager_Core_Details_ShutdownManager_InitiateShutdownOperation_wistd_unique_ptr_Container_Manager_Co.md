# Container::Manager::Core::Details::ShutdownManager::InitiateShutdownOperation(wistd::unique_ptr<Container::Manager::Core::Details::InProcClientContainerHandle,wistd::default_delete<Container::Manager::Core::Details::InProcClientContainerHandle>>,_CMS_ACTIVITY_ID,CmTraceProvider::ContainerShutdownOperation &)

- ea: `0x1800bb37c`
- end: `0x1800bb88b`
- name: `?InitiateShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@AEAAJV?$unique_ptr@VInProcClientContainerHandle@Details@Core@Manager@Container@@U?$default_delete@VInProcClientContainerHandle@Details@Core@Manager@Container@@@wistd@@@wistd@@W4_CMS_ACTIVITY_ID@@AEAVContainerShutdownOperation@CmTraceProvider@@@Z`
- size: `1295`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x1800bb1fc`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18003c7d0`
- `0x18004b37c`
- `0x18004eb4c`
- `0x180050290`
- `0x180073694`
- `0x1800ba9a0`
- `0x1800bb37c`
- `0x1800bba28`
- `0x1800bbb8c`
- `0x1800bbf3c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb453`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bb453`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800bb47c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800bb47c`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800bb6a7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800bb7a5`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800bb6a7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800bb7a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb626`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb542`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb5a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb5ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb542`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb5a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb5ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bb691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb46b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb46b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bb48a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bb48a`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ShutdownManager::InitiateShutdownOperation(
        RTL_SRWLOCK *a1,
        Container::Manager::Core::Details::InProcClientContainerHandle **a2,
        unsigned int a3,
        CmTraceProvider::ContainerShutdownOperation *a4)
{
  RTL_SRWLOCK **v6; // rax
  RTL_SRWLOCK **v7; // rdi
  Container::Manager::Core::Details::InProcClientContainerHandle *v8; // rax
  Container::Manager::Core::Details::InProcClientContainerHandle *v9; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v11; // r9
  struct _TP_TIMER *v12; // r13
  PTP_TIMER v13; // r14
  DWORD LastError; // ebx
  unsigned int v15; // r14d
  Container::Manager::Core::Details::InProcClientContainerHandle *v16; // rbx
  RTL_SRWLOCK *v18; // r14
  RTL_SRWLOCK *v19; // r12
  Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *v20; // rcx
  const char *v21; // r9
  Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *v22; // rbx
  Container::Manager::Core::Details::InProcClientContainerHandle *v23; // rbx
  const char *v24; // r9
  RTL_SRWLOCK *v25; // rbx
  _DWORD *Ptr; // rdi
  Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *v27; // r13
  unsigned int v28; // edi
  Container::Manager::Core::Details::InProcClientContainerHandle *v29; // rbx
  bool v30; // zf
  __int64 v31; // r8
  Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *v32; // rbx
  Container::Manager::Core::Details::InProcClientContainerHandle *v33; // rbx
  int started; // [rsp+20h] [rbp-E0h]
  Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *v36; // [rsp+28h] [rbp-D8h] BYREF
  RTL_SRWLOCK *v37; // [rsp+30h] [rbp-D0h] BYREF
  char v38; // [rsp+38h] [rbp-C8h]
  CmTraceProvider::ContainerShutdownOperation *v39; // [rsp+40h] [rbp-C0h]
  __int128 v40; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v41[42]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v42[42]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v39 = a4;
  v6 = (RTL_SRWLOCK **)operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
      (const char *)0x8007000ELL,
      a3);
    v23 = *a2;
    *a2 = 0;
    if ( !v23 )
      return 2147942414LL;
    Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v23);
LABEL_43:
    operator delete(v23, (const struct std::nothrow_t *)0x28);
    return 2147942414LL;
  }
  *v6 = 0;
  v6[1] = 0;
  v6[2] = 0;
  v6[3] = 0;
  v6[4] = 0;
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v6 + 5,
    "ContainerShutdownOperation");
  v36 = (Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *)v7;
  v7[5] = (RTL_SRWLOCK *)&CmTraceProvider::ContainerShutdownOperation::`vftable';
  *v7 = a1;
  v8 = *a2;
  *a2 = 0;
  v9 = (Container::Manager::Core::Details::InProcClientContainerHandle *)v7[1];
  v7[1] = (RTL_SRWLOCK *)v8;
  if ( v9 )
  {
    Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x28);
  }
  v40 = *(_OWORD *)&v7[1]->Ptr;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Container::Manager::Core::Details::ShutdownManager::ShutdownOperationTimeoutCallback,
                      v7,
                      0);
  v12 = (struct _TP_TIMER *)v7[3];
  v13 = ThreadpoolTimer;
  if ( v12 )
  {
    LastError = GetLastError();
    CloseThreadpoolTimer(v12);
    SetLastError(LastError);
  }
  v7[3] = (RTL_SRWLOCK *)v13;
  if ( !v13 )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xAA,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
            v11);
    Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation((Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *)v7);
    operator delete(v7, (const struct std::nothrow_t *)0x178);
    v16 = *a2;
    *a2 = 0;
    if ( v16 )
    {
      Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v16);
      operator delete(v16, (const struct std::nothrow_t *)0x28);
    }
    return v15;
  }
  v18 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v19 = a1 + 4;
  utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::find<void>(
    v19,
    &v37,
    &v40);
  if ( v37 != v19 )
  {
    CmTraceProvider::ContainerShutdownOperation::Stop(v39, 3u, 0);
    if ( v18 )
      ReleaseSRWLockExclusive(v18);
    Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation((Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *)v7);
    v20 = (Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *)v7;
    goto LABEL_37;
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>>,0>::emplace<_GUID &,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>,0>(
    v19,
    &v37,
    &v40,
    &v36);
  if ( !v37 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
      (const char *)0x8007000ELL,
      a3);
    if ( v18 )
      ReleaseSRWLockExclusive(v18);
    v22 = v36;
    if ( v36 )
    {
      Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(v36);
      operator delete(v22, (const struct std::nothrow_t *)0x178);
    }
    v23 = *a2;
    *a2 = 0;
    if ( !v23 )
      return 2147942414LL;
    Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v23);
    goto LABEL_43;
  }
  if ( !v38 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
      v21);
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  started = Container::Manager::Core::Details::ShutdownManager::StartOperationActivity(v7, a3);
  if ( started >= 0 )
  {
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v41,
      v39,
      0);
    v30 = *((_DWORD *)v7 + 88) == 0;
    v41[0] = &CmTraceProvider::ContainerShutdownOperation::`vftable';
    LOBYTE(v31) = !v30;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v42,
      v7 + 5,
      v31);
    v42[0] = &CmTraceProvider::ContainerShutdownOperation::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
      v7 + 5,
      v41);
    v42[0] = &CmTraceProvider::ContainerShutdownOperation::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v42);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v42);
    v41[0] = &CmTraceProvider::ContainerShutdownOperation::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v41);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v41);
    *((_DWORD *)v7 + 8) = 1;
    WakeByAddressAll(v7 + 4);
    v32 = v36;
    if ( !v36 )
    {
LABEL_38:
      v33 = *a2;
      *a2 = 0;
      if ( v33 )
      {
        Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v33);
        operator delete(v33, (const struct std::nothrow_t *)0x28);
      }
      return 0;
    }
    Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(v36);
    v20 = v32;
LABEL_37:
    operator delete(v20, (const struct std::nothrow_t *)0x178);
    goto LABEL_38;
  }
  AcquireSRWLockExclusive(v18);
  utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::find<void>(
    v19,
    &v37,
    &v40);
  v25 = v37;
  if ( v37 == v19 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
      v24);
  Ptr = v37[5].Ptr;
  v37[5].Ptr = 0;
  v27 = v36;
  if ( v36 )
  {
    Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(v36);
    operator delete(v27, (const struct std::nothrow_t *)0x178);
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>>,0>::erase(
    v19,
    &v37,
    v25);
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  Ptr[8] = 1;
  WakeByAddressAll(Ptr + 8);
  if ( Ptr )
  {
    Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation((Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *)Ptr);
    operator delete(Ptr, (const struct std::nothrow_t *)0x178);
  }
  v28 = started;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFA,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\shutdown.cpp",
    (const char *)(unsigned int)started,
    started);
  v29 = *a2;
  *a2 = 0;
  if ( v29 )
  {
    Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(v29);
    operator delete(v29, (const struct std::nothrow_t *)0x28);
  }
  return v28;
}

```

## disassembly

```asm
0x1800bb37c  push    rbp
0x1800bb37e  push    rbx
0x1800bb37f  push    rsi
0x1800bb380  push    rdi
0x1800bb381  push    r12
0x1800bb383  push    r13
0x1800bb385  push    r14
0x1800bb387  push    r15
0x1800bb389  lea     rbp, [rsp-218h]
0x1800bb391  sub     rsp, 318h
0x1800bb398  mov     rax, cs:__security_cookie
0x1800bb39f  xor     rax, rsp
0x1800bb3a2  mov     [rbp+250h+var_50], rax
0x1800bb3a9  mov     rsi, rdx
0x1800bb3ac  mov     [rsp+350h+var_310], r9
0x1800bb3b1  mov     r12, rcx
0x1800bb3b4  mov     dword ptr [rsp+350h+var_330], r8d; int
0x1800bb3b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bb3c0  mov     ecx, 178h; unsigned __int64
0x1800bb3c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bb3ca  xor     r14d, r14d
0x1800bb3cd  mov     rdi, rax
0x1800bb3d0  test    rax, rax
0x1800bb3d3  jz      loc_1800BB7F2
0x1800bb3d9  lea     rdx, aContainershutd_0; "ContainerShutdownOperation"
0x1800bb3e0  mov     [rax], r14
0x1800bb3e3  lea     rcx, [rax+28h]
0x1800bb3e7  mov     [rax+8], r14
0x1800bb3eb  mov     [rax+10h], r14
0x1800bb3ef  mov     [rax+18h], r14
0x1800bb3f3  mov     [rax+20h], r14
0x1800bb3f7  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800bb3fc  lea     rax, ??_7ContainerShutdownOperation@CmTraceProvider@@6B@; const CmTraceProvider::ContainerShutdownOperation::`vftable'
0x1800bb403  mov     [rsp+350h+var_328], rdi
0x1800bb408  mov     [rdi+28h], rax
0x1800bb40c  lea     r15d, [r14+28h]
0x1800bb410  mov     [rdi], r12
0x1800bb413  mov     rax, [rsi]
0x1800bb416  mov     [rsi], r14
0x1800bb419  mov     rbx, [rdi+8]
0x1800bb41d  mov     [rdi+8], rax
0x1800bb421  test    rbx, rbx
0x1800bb424  jz      short loc_1800BB439
0x1800bb426  mov     rcx, rbx; this
0x1800bb429  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb42e  mov     edx, r15d; struct std::nothrow_t *
0x1800bb431  mov     rcx, rbx; void *
0x1800bb434  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb439  mov     rax, [rdi+8]
0x1800bb43d  lea     rcx, ?ShutdownOperationTimeoutCallback@ShutdownManager@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800bb444  xor     r8d, r8d; pcbe
0x1800bb447  mov     rdx, rdi; pv
0x1800bb44a  movups  xmm0, xmmword ptr [rax]
0x1800bb44d  movdqu  [rsp+350h+var_308], xmm0
0x1800bb453  call    cs:__imp_CreateThreadpoolTimer
0x1800bb45a  nop     dword ptr [rax+rax+00h]
0x1800bb45f  mov     r13, [rdi+18h]
0x1800bb463  mov     r14, rax
0x1800bb466  test    r13, r13
0x1800bb469  jz      short loc_1800BB496
0x1800bb46b  call    cs:__imp_GetLastError
0x1800bb472  nop     dword ptr [rax+rax+00h]
0x1800bb477  mov     rcx, r13; pti
0x1800bb47a  mov     ebx, eax
0x1800bb47c  call    cs:__imp_CloseThreadpoolTimer
0x1800bb483  nop     dword ptr [rax+rax+00h]
0x1800bb488  mov     ecx, ebx; dwErrCode
0x1800bb48a  call    cs:__imp_SetLastError
0x1800bb491  nop     dword ptr [rax+rax+00h]
0x1800bb496  xor     r13d, r13d
0x1800bb499  mov     [rdi+18h], r14
0x1800bb49d  test    r14, r14
0x1800bb4a0  jnz     short loc_1800BB4F8
0x1800bb4a2  mov     rcx, [rbp+258h]; this
0x1800bb4a9  lea     r8, aOnecoreBaseGen_44; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800bb4b0  mov     edx, 0AAh; void *
0x1800bb4b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bb4ba  mov     rcx, rdi; this
0x1800bb4bd  mov     r14d, eax
0x1800bb4c0  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb4c5  mov     edx, 178h; struct std::nothrow_t *
0x1800bb4ca  mov     rcx, rdi; void *
0x1800bb4cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb4d2  mov     rbx, [rsi]
0x1800bb4d5  mov     [rsi], r13
0x1800bb4d8  test    rbx, rbx
0x1800bb4db  jz      short loc_1800BB4F0
0x1800bb4dd  mov     rcx, rbx; this
0x1800bb4e0  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb4e5  mov     rdx, r15; struct std::nothrow_t *
0x1800bb4e8  mov     rcx, rbx; void *
0x1800bb4eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb4f0  mov     eax, r14d
0x1800bb4f3  jmp     loc_1800BB835
0x1800bb4f8  lea     r14, [r12+10h]
0x1800bb4fd  mov     rcx, r14; SRWLock
0x1800bb500  call    cs:__imp_AcquireSRWLockExclusive
0x1800bb507  nop     dword ptr [rax+rax+00h]
0x1800bb50c  add     r12, 20h ; ' '
0x1800bb510  lea     r8, [rsp+350h+var_308]
0x1800bb515  mov     rcx, r12
0x1800bb518  lea     rdx, [rsp+350h+var_320]
0x1800bb51d  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::find<void>(_GUID const &)
0x1800bb522  cmp     [rsp+350h+var_320], r12
0x1800bb527  jz      short loc_1800BB55E
0x1800bb529  mov     rcx, [rsp+350h+var_310]; this
0x1800bb52e  xor     r8d, r8d; int
0x1800bb531  lea     edx, [r8+3]; unsigned int
0x1800bb535  call    ?Stop@ContainerShutdownOperation@CmTraceProvider@@QEAAXKJ@Z; CmTraceProvider::ContainerShutdownOperation::Stop(ulong,long)
0x1800bb53a  test    r14, r14
0x1800bb53d  jz      short loc_1800BB54E
0x1800bb53f  mov     rcx, r14; SRWLock
0x1800bb542  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bb549  nop     dword ptr [rax+rax+00h]
0x1800bb54e  mov     rcx, rdi; this
0x1800bb551  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb556  mov     rcx, rdi
0x1800bb559  jmp     loc_1800BB7C6
0x1800bb55e  lea     r9, [rsp+350h+var_328]
0x1800bb563  mov     rcx, r12
0x1800bb566  lea     r8, [rsp+350h+var_308]
0x1800bb56b  lea     rdx, [rsp+350h+var_320]
0x1800bb570  call    ??$emplace@AEAU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@_N@1@AEAU_GUID@@$$QEAV?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>>,0>::emplace<_GUID &,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>,0>(_GUID &,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>> &&)
0x1800bb575  cmp     [rsp+350h+var_320], r13
0x1800bb57a  jnz     short loc_1800BB5EC
0x1800bb57c  mov     rcx, [rbp+258h]; this
0x1800bb583  lea     r8, aOnecoreBaseGen_44; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800bb58a  mov     r9d, 8007000Eh; char *
0x1800bb590  mov     edx, 0C5h; void *
0x1800bb595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb59a  test    r14, r14
0x1800bb59d  jz      short loc_1800BB5AE
0x1800bb59f  mov     rcx, r14; SRWLock
0x1800bb5a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bb5a9  nop     dword ptr [rax+rax+00h]
0x1800bb5ae  mov     rbx, [rsp+350h+var_328]
0x1800bb5b3  test    rbx, rbx
0x1800bb5b6  jz      short loc_1800BB5CD
0x1800bb5b8  mov     rcx, rbx; this
0x1800bb5bb  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb5c0  mov     edx, 178h; struct std::nothrow_t *
0x1800bb5c5  mov     rcx, rbx; void *
0x1800bb5c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb5cd  mov     rbx, [rsi]
0x1800bb5d0  mov     [rsi], r13
0x1800bb5d3  test    rbx, rbx
0x1800bb5d6  jz      loc_1800BB830
0x1800bb5dc  mov     rcx, rbx; this
0x1800bb5df  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb5e4  mov     rdx, r15
0x1800bb5e7  jmp     loc_1800BB828
0x1800bb5ec  cmp     [rsp+350h+var_318], r13b
0x1800bb5f1  jz      loc_1800BB872
0x1800bb5f7  test    r14, r14
0x1800bb5fa  jz      short loc_1800BB60B
0x1800bb5fc  mov     rcx, r14; SRWLock
0x1800bb5ff  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bb606  nop     dword ptr [rax+rax+00h]
0x1800bb60b  mov     edx, dword ptr [rsp+350h+var_330]
0x1800bb60f  mov     rcx, rdi
0x1800bb612  call    ?StartOperationActivity@ShutdownManager@Details@Core@Manager@Container@@CAJPEAUShutdownOperation@12345@W4_CMS_ACTIVITY_ID@@@Z; Container::Manager::Core::Details::ShutdownManager::StartOperationActivity(Container::Manager::Core::Details::ShutdownManager::ShutdownOperation *,_CMS_ACTIVITY_ID)
0x1800bb617  mov     dword ptr [rsp+350h+var_330], eax; int
0x1800bb61b  test    eax, eax
0x1800bb61d  jns     loc_1800BB715
0x1800bb623  mov     rcx, r14; SRWLock
0x1800bb626  call    cs:__imp_AcquireSRWLockExclusive
0x1800bb62d  nop     dword ptr [rax+rax+00h]
0x1800bb632  lea     r8, [rsp+350h+var_308]
0x1800bb637  mov     rcx, r12
0x1800bb63a  lea     rdx, [rsp+350h+var_320]
0x1800bb63f  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::find<void>(_GUID const &)
0x1800bb644  mov     rbx, [rsp+350h+var_320]
0x1800bb649  cmp     rbx, r12
0x1800bb64c  jz      loc_1800BB859
0x1800bb652  mov     rdi, [rbx+28h]
0x1800bb656  mov     [rbx+28h], r13
0x1800bb65a  mov     r13, [rsp+350h+var_328]
0x1800bb65f  test    r13, r13
0x1800bb662  jz      short loc_1800BB679
0x1800bb664  mov     rcx, r13; this
0x1800bb667  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb66c  mov     edx, 178h; struct std::nothrow_t *
0x1800bb671  mov     rcx, r13; void *
0x1800bb674  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb679  mov     r8, rbx
0x1800bb67c  lea     rdx, [rsp+350h+var_320]
0x1800bb681  mov     rcx, r12
0x1800bb684  call    ?erase@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@U?$default_delete@UShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>>,0>::erase(utl::_TreeConstIt<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation,wistd::default_delete<Container::Manager::Core::Details::ShutdownManager::ShutdownOperation>>>>)
0x1800bb689  test    r14, r14
0x1800bb68c  jz      short loc_1800BB69D
0x1800bb68e  mov     rcx, r14; SRWLock
0x1800bb691  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bb698  nop     dword ptr [rax+rax+00h]
0x1800bb69d  lea     rcx, [rdi+20h]; Address
0x1800bb6a1  mov     dword ptr [rcx], 1
0x1800bb6a7  call    cs:__imp_WakeByAddressAll
0x1800bb6ae  nop     dword ptr [rax+rax+00h]
0x1800bb6b3  test    rdi, rdi
0x1800bb6b6  jz      short loc_1800BB6CD
0x1800bb6b8  mov     rcx, rdi; this
0x1800bb6bb  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb6c0  mov     edx, 178h; struct std::nothrow_t *
0x1800bb6c5  mov     rcx, rdi; void *
0x1800bb6c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb6cd  mov     edi, dword ptr [rsp+350h+var_330]
0x1800bb6d1  lea     r8, aOnecoreBaseGen_44; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800bb6d8  mov     rcx, [rbp+258h]; this
0x1800bb6df  mov     r9d, edi; char *
0x1800bb6e2  mov     edx, 0FAh; void *
0x1800bb6e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb6ec  mov     rbx, [rsi]
0x1800bb6ef  mov     qword ptr [rsi], 0
0x1800bb6f6  test    rbx, rbx
0x1800bb6f9  jz      short loc_1800BB70E
0x1800bb6fb  mov     rcx, rbx; this
0x1800bb6fe  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb703  mov     rdx, r15; struct std::nothrow_t *
0x1800bb706  mov     rcx, rbx; void *
0x1800bb709  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb70e  mov     eax, edi
0x1800bb710  jmp     loc_1800BB835
0x1800bb715  mov     rdx, [rsp+350h+var_310]
0x1800bb71a  lea     rcx, [rsp+350h+var_2F0]
0x1800bb71f  xor     r8d, r8d
0x1800bb722  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800bb727  cmp     [rdi+160h], r13d
0x1800bb72e  lea     r14, ??_7ContainerShutdownOperation@CmTraceProvider@@6B@; const CmTraceProvider::ContainerShutdownOperation::`vftable'
0x1800bb735  lea     rdx, [rdi+28h]
0x1800bb739  mov     [rsp+350h+var_2F0], r14
0x1800bb73e  setnz   r8b
0x1800bb742  lea     rcx, [rbp+250h+var_1A0]
0x1800bb749  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800bb74e  lea     rdx, [rsp+350h+var_2F0]
0x1800bb753  mov     [rbp+250h+var_1A0], r14
0x1800bb75a  lea     rcx, [rdi+28h]
0x1800bb75e  call    ??4?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800bb763  lea     rcx, [rbp+250h+var_1A0]
0x1800bb76a  mov     [rbp+250h+var_1A0], r14
0x1800bb771  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800bb776  lea     rcx, [rbp+250h+var_1A0]
0x1800bb77d  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800bb782  lea     rcx, [rsp+350h+var_2F0]
0x1800bb787  mov     [rsp+350h+var_2F0], r14
0x1800bb78c  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800bb791  lea     rcx, [rsp+350h+var_2F0]
0x1800bb796  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800bb79b  lea     rcx, [rdi+20h]; Address
0x1800bb79f  mov     dword ptr [rcx], 1
0x1800bb7a5  call    cs:__imp_WakeByAddressAll
0x1800bb7ac  nop     dword ptr [rax+rax+00h]
0x1800bb7b1  mov     rbx, [rsp+350h+var_328]
0x1800bb7b6  test    rbx, rbx
0x1800bb7b9  jz      short loc_1800BB7D0
0x1800bb7bb  mov     rcx, rbx; this
0x1800bb7be  call    ??1ShutdownOperation@ShutdownManager@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ShutdownManager::ShutdownOperation::~ShutdownOperation(void)
0x1800bb7c3  mov     rcx, rbx; void *
0x1800bb7c6  mov     edx, 178h; struct std::nothrow_t *
0x1800bb7cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb7d0  mov     rbx, [rsi]
0x1800bb7d3  mov     [rsi], r13
0x1800bb7d6  test    rbx, rbx
0x1800bb7d9  jz      short loc_1800BB7EE
0x1800bb7db  mov     rcx, rbx; this
0x1800bb7de  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb7e3  mov     rdx, r15; struct std::nothrow_t *
0x1800bb7e6  mov     rcx, rbx; void *
0x1800bb7e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb7ee  xor     eax, eax
0x1800bb7f0  jmp     short loc_1800BB835
0x1800bb7f2  mov     rcx, [rbp+258h]; this
0x1800bb7f9  lea     r8, aOnecoreBaseGen_44; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800bb800  mov     r9d, 8007000Eh; char *
0x1800bb806  mov     edx, 97h; void *
0x1800bb80b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb810  mov     rbx, [rsi]
0x1800bb813  mov     [rsi], r14
0x1800bb816  test    rbx, rbx
0x1800bb819  jz      short loc_1800BB830
0x1800bb81b  mov     rcx, rbx; this
0x1800bb81e  call    ??1InProcClientContainerHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::InProcClientContainerHandle::~InProcClientContainerHandle(void)
0x1800bb823  mov     edx, 28h ; '('; struct std::nothrow_t *
0x1800bb828  mov     rcx, rbx; void *
0x1800bb82b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb830  mov     eax, 8007000Eh
0x1800bb835  mov     rcx, [rbp+250h+var_50]
0x1800bb83c  xor     rcx, rsp; StackCookie
0x1800bb83f  call    __security_check_cookie
0x1800bb844  add     rsp, 318h
0x1800bb84b  pop     r15
0x1800bb84d  pop     r14
0x1800bb84f  pop     r13
0x1800bb851  pop     r12
0x1800bb853  pop     rdi
0x1800bb854  pop     rsi
0x1800bb855  pop     rbx
0x1800bb856  pop     rbp
0x1800bb857  retn
0x1800bb859  mov     rcx, [rbp+258h]; this
0x1800bb860  lea     r8, aOnecoreBaseGen_44; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800bb867  mov     edx, 0E0h; void *
  ... truncated ...
```
