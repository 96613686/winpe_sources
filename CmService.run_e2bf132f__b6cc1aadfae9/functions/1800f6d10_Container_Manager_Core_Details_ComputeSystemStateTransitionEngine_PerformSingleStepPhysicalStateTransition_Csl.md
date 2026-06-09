# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::PerformSingleStepPhysicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800f6d10`
- end: `0x1800f75d6`
- name: `?PerformSingleStepPhysicalStateTransition@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `2246`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800f69cc`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x1800103a4`
- `0x18003dbf8`
- `0x18003f7d8`
- `0x1800471dc`
- `0x1800f44f4`
- `0x1800f4a70`
- `0x1800f4b54`
- `0x1800f4c38`
- `0x1800f5fa8`
- `0x1800f6828`
- `0x1800f6d10`
- `0x1800f8544`
- `0x1800f951c`
- `0x180101fac`
- `0x1801225a0`
- `0x180123ce8`
- `0x18012475c`
- `0x180124ed8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f6ffc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f6ffc`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800f6fb2`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800f6fb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6e07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6eda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6fd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7049`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7109`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7315`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6e07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6eda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6fd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7049`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7109`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7315`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6ddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6e50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6f0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6f23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f707d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f70e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f713a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7152`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f71ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f725f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f72f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7346`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f735e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f73b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6ddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6e50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6f0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6f23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f707d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f70e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f713a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7152`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f71ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f725f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f72f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f7346`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f735e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f73b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6ee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f6ee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7321`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::PerformSingleStepPhysicalStateTransition(
        PSRWLOCK SRWLock,
        char *a2)
{
  const struct _GUID *v4; // rbx
  PSRWLOCK v5; // r12
  int v6; // eax
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  void *v10; // rbx
  unsigned int Async; // ebx
  __int64 v12; // rcx
  char *v13; // rbx
  char *v14; // rdi
  _DWORD *v15; // rcx
  void *v16; // rbx
  RTL_SRWLOCK *v17; // rdi
  __int64 v18; // rcx
  int v19; // ebx
  __int64 v20; // rcx
  int v21; // r15d
  __int64 v22; // rcx
  int started; // edi
  __int64 v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // ebx
  int v31; // ebx
  void *v32; // rdi
  void *v33; // rbx
  void *v35; // rbx
  void *v36; // rbx
  int v37; // [rsp+20h] [rbp-E0h]
  int Ptr; // [rsp+30h] [rbp-D0h] BYREF
  void *v39[2]; // [rsp+38h] [rbp-C8h] BYREF
  utl::_RefCountBase *v40; // [rsp+48h] [rbp-B8h]
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  char v42; // [rsp+58h] [rbp-A8h] BYREF
  char v43; // [rsp+60h] [rbp-A0h] BYREF
  char v44; // [rsp+68h] [rbp-98h] BYREF
  char v45; // [rsp+70h] [rbp-90h] BYREF
  char v46; // [rsp+78h] [rbp-88h] BYREF
  char v47; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v48[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v4 = (const struct _GUID *)&SRWLock[21];
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v48,
    "ContainerStateTransition");
  v48[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
  CmTraceProvider::ContainerStateTransition::StartActivity((CmTraceProvider::ContainerStateTransition *)v48, v4);
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v5 = SRWLock + 2;
  if ( LODWORD(SRWLock[2].Ptr) )
  {
    if ( SLODWORD(v5->Ptr) >= 3 )
    {
      if ( HIDWORD(SRWLock[5].Ptr) == 4 )
      {
        Ptr = (int)SRWLock[8].Ptr;
        CmTraceProvider::ContainerStateTransition::PauseComputeSystem<unsigned long>(v48, &Ptr);
        LODWORD(SRWLock[16].Ptr) = 4;
        if ( !LOBYTE(SRWLock[19].Ptr) )
          LOBYTE(SRWLock[19].Ptr) = 1;
        v25 = (unsigned int)SRWLock[8].Ptr;
        HIDWORD(SRWLock[18].Ptr) = v25;
        v26 = *(_QWORD *)a2;
        if ( *(_QWORD *)a2 )
        {
          *(_DWORD *)(v26 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v26);
          *(_QWORD *)a2 = 0;
        }
        started = Container::Manager::Hcs::ComputeSystem::PauseAsync(SRWLock[20].Ptr, v25, v39);
        AcquireSRWLockExclusive(SRWLock);
        LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
        if ( a2 == &v45 )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(SRWLock);
        }
        else
        {
          v27 = *(_QWORD *)a2;
          if ( *(_QWORD *)a2 )
          {
            *(_DWORD *)(v27 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v27);
          }
          *(_QWORD *)a2 = SRWLock;
        }
        if ( started >= 0 )
          goto LABEL_32;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x434,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
          (const char *)(unsigned int)started,
          v37);
        Csl::AsyncOperation<void>::Cleanup(v39);
        if ( v40 )
          utl::_RefCountBase::_DecStrong(v40);
      }
      else
      {
        if ( LODWORD(v5->Ptr) != 4 )
        {
          v8 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x463,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
            (const char *)0x8000FFFFLL,
            v37);
          Csl::AsyncOperation<void>::Cleanup(v39);
          if ( v40 )
            utl::_RefCountBase::_DecStrong(v40);
          v36 = v39[0];
          if ( v39[0] )
          {
            Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v39[0]);
            operator delete(v36, (const struct std::nothrow_t *)0x30);
          }
          v48[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
          goto LABEL_113;
        }
        Ptr = HIDWORD(SRWLock[4].Ptr);
        CmTraceProvider::ContainerStateTransition::ResumeComputeSystem<unsigned long>(v48, &Ptr);
        LODWORD(SRWLock[16].Ptr) = 3;
        if ( LOBYTE(SRWLock[19].Ptr) )
          LOBYTE(SRWLock[19].Ptr) = 0;
        v28 = *(_QWORD *)a2;
        if ( *(_QWORD *)a2 )
        {
          *(_DWORD *)(v28 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v28);
          *(_QWORD *)a2 = 0;
        }
        started = Container::Manager::Hcs::ComputeSystem::ResumeAsync(SRWLock[20].Ptr, v39);
        AcquireSRWLockExclusive(SRWLock);
        LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
        if ( a2 == &v46 )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(SRWLock);
        }
        else
        {
          v29 = *(_QWORD *)a2;
          if ( *(_QWORD *)a2 )
          {
            *(_DWORD *)(v29 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v29);
          }
          *(_QWORD *)a2 = SRWLock;
        }
        if ( started >= 0 )
          goto LABEL_32;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
          (const char *)(unsigned int)started,
          v37);
        Csl::AsyncOperation<void>::Cleanup(v39);
        if ( v40 )
          utl::_RefCountBase::_DecStrong(v40);
      }
    }
    else
    {
      Ptr = (int)SRWLock[23].Ptr;
      v21 = 1;
      if ( Ptr == 1 )
        v21 = (int)SRWLock[57].Ptr;
      v41 = v21;
      CmTraceProvider::ContainerStateTransition::StartComputeSystem<unsigned long,unsigned long>(v48, &v41, &Ptr);
      LODWORD(SRWLock[16].Ptr) = 3;
      v22 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v22 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v22);
        *(_QWORD *)a2 = 0;
      }
      started = Container::Manager::Hcs::ComputeSystem::StartAsync(SRWLock[20].Ptr, v39);
      AcquireSRWLockExclusive(SRWLock);
      LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
      if ( a2 == &v44 )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(SRWLock);
      }
      else
      {
        v24 = *(_QWORD *)a2;
        if ( *(_QWORD *)a2 )
        {
          *(_DWORD *)(v24 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v24);
        }
        *(_QWORD *)a2 = SRWLock;
      }
      if ( started >= 0 )
        goto LABEL_32;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x403,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
        (const char *)(unsigned int)started,
        v37);
      Csl::AsyncOperation<void>::Cleanup(v39);
      if ( v40 )
        utl::_RefCountBase::_DecStrong(v40);
    }
LABEL_104:
    v35 = v39[0];
    if ( v39[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v39[0]);
      operator delete(v35, (const struct std::nothrow_t *)0x30);
    }
    Async = started;
LABEL_107:
    v48[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v48);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v48);
    return Async;
  }
  v41 = (int)SRWLock[23].Ptr;
  if ( v41 == 1 )
    v6 = (int)SRWLock[57].Ptr;
  else
    v6 = 1;
  Ptr = v6;
  CmTraceProvider::ContainerStateTransition::CreateComputeSystem<unsigned long,unsigned long>(v48, &Ptr, &v41);
  LODWORD(SRWLock[16].Ptr) = 2;
  v7 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    *(_DWORD *)(v7 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v7);
    *(_QWORD *)a2 = 0;
  }
  v8 = Container::Manager::Core::Details::Silo::Setup((Container::Manager::Core::Details::Silo *)&SRWLock[191]);
  if ( v8 < 0 )
  {
    AcquireSRWLockExclusive(SRWLock);
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
    if ( a2 == &v42 )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
    }
    else
    {
      v9 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v9 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v9);
      }
      *(_QWORD *)a2 = SRWLock;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v8,
      v37);
    Csl::AsyncOperation<void>::Cleanup(v39);
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    v10 = v39[0];
    if ( v39[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v39[0]);
      operator delete(v10, (const struct std::nothrow_t *)0x30);
    }
    v48[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
LABEL_113:
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v48);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v48);
    return (unsigned int)v8;
  }
  Async = Container::Manager::Hcs::ComputeSystem::CreateAsync(SRWLock[20].Ptr, v4, v39);
  AcquireSRWLockExclusive(SRWLock);
  LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  if ( a2 == &v43 )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(SRWLock);
  }
  else
  {
    v12 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      *(_DWORD *)(v12 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v12);
    }
    *(_QWORD *)a2 = SRWLock;
  }
  if ( (Async & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)Async,
      v37);
    Csl::AsyncOperation<void>::Cleanup(v39);
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
LABEL_95:
    v32 = v39[0];
    if ( v39[0] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v39[0]);
      operator delete(v32, (const struct std::nothrow_t *)0x30);
    }
    goto LABEL_107;
  }
  if ( LODWORD(v5->Ptr) != 5 )
  {
    LODWORD(v5->Ptr) = 1;
    Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::InvokeStateTransitionCallback(
      SRWLock,
      0,
      (__int64)a2);
    v13 = (char *)SRWLock[9].Ptr;
    v14 = (char *)SRWLock[10].Ptr;
    while ( v13 != v14 )
    {
      *(_DWORD *)(*(_QWORD *)v13 + 4LL) = 0;
      v15 = *(_DWORD **)v13;
      *v15 = 1;
      WakeByAddressAll(v15);
      v13 += 8;
    }
    SRWLock[10].Ptr = SRWLock[9].Ptr;
  }
LABEL_32:
  v16 = v39[0];
  v17 = (RTL_SRWLOCK *)((char *)v39[0] + 8);
  AcquireSRWLockExclusive((PSRWLOCK)v39[0] + 1);
  *((_QWORD *)v16 + 2) = Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnAsyncStateTransitionCompleted;
  *((_QWORD *)v16 + 3) = SRWLock;
  if ( *(_DWORD *)v16 == 2 )
    SubmitThreadpoolWork(*((PTP_WORK *)v16 + 4));
  if ( v17 )
    ReleaseSRWLockExclusive(v17);
  do
  {
    while ( 1 )
    {
      v18 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        *(_DWORD *)(v18 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v18);
        *(_QWORD *)a2 = 0;
      }
      v19 = Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::WaitForStateTransitionThreadEvent(
              SRWLock,
              7);
      AcquireSRWLockExclusive(SRWLock);
      LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
      if ( a2 == &v47 )
      {
        if ( SRWLock )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(SRWLock);
        }
      }
      else
      {
        v20 = *(_QWORD *)a2;
        if ( *(_QWORD *)a2 )
        {
          *(_DWORD *)(v20 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v20);
        }
        *(_QWORD *)a2 = SRWLock;
      }
      v30 = v19 - 1;
      if ( !v30 )
      {
        started = -2147467260;
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v48,
          2147500036LL);
        Csl::AsyncOperation<void>::Cleanup(v39);
        if ( v40 )
          utl::_RefCountBase::_DecStrong(v40);
        goto LABEL_104;
      }
      v31 = v30 - 1;
      if ( v31 )
        break;
      Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::PerformAllQosStateTransitions(
        SRWLock,
        (__int64)a2);
    }
  }
  while ( v31 != 2 );
  if ( !*((_DWORD *)v39[1] + 1) )
  {
    Async = -2147023436;
    goto LABEL_93;
  }
  Async = *(_DWORD *)v39[1];
  if ( *(int *)v39[1] < 0 )
  {
LABEL_93:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)Async,
      v37);
    Csl::AsyncOperation<void>::Cleanup(v39);
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    goto LABEL_95;
  }
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v48, 0);
  Csl::AsyncOperation<void>::Cleanup(v39);
  if ( v40 )
    utl::_RefCountBase::_DecStrong(v40);
  v33 = v39[0];
  if ( v39[0] )
  {
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v39[0]);
    operator delete(v33, (const struct std::nothrow_t *)0x30);
  }
  v48[0] = &CmTraceProvider::ContainerStateTransition::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v48);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v48);
  return 0;
}

```

## disassembly

```asm
0x1800f6d10  mov     [rsp-8+arg_10], rbx
0x1800f6d15  push    rbp
0x1800f6d16  push    rsi
0x1800f6d17  push    rdi
0x1800f6d18  push    r12
0x1800f6d1a  push    r13
0x1800f6d1c  push    r14
0x1800f6d1e  push    r15
0x1800f6d20  lea     rbp, [rsp-0F0h]
0x1800f6d28  sub     rsp, 1F0h
0x1800f6d2f  mov     rax, cs:__security_cookie
0x1800f6d36  xor     rax, rsp
0x1800f6d39  mov     [rbp+120h+var_40], rax
0x1800f6d40  mov     r14, rdx
0x1800f6d43  mov     rsi, rcx
0x1800f6d46  lea     rbx, [rcx+0A8h]
0x1800f6d4d  lea     rdx, aContainerstate; "ContainerStateTransition"
0x1800f6d54  lea     rcx, [rbp+120h+var_190]
0x1800f6d58  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f6d5d  lea     r15, ??_7ContainerStateTransition@CmTraceProvider@@6B@; const CmTraceProvider::ContainerStateTransition::`vftable'
0x1800f6d64  mov     [rbp+120h+var_190], r15
0x1800f6d68  mov     rdx, rbx; struct _GUID *
0x1800f6d6b  lea     rcx, [rbp+120h+var_190]; this
0x1800f6d6f  call    ?StartActivity@ContainerStateTransition@CmTraceProvider@@QEAAXAEBU_GUID@@@Z; CmTraceProvider::ContainerStateTransition::StartActivity(_GUID const &)
0x1800f6d74  nop
0x1800f6d75  xorps   xmm0, xmm0
0x1800f6d78  movdqu  xmmword ptr [rsp+220h+var_1E8], xmm0
0x1800f6d7e  xor     r13d, r13d
0x1800f6d81  mov     [rsp+220h+var_1D8], r13
0x1800f6d86  lea     r12, [rsi+10h]
0x1800f6d8a  cmp     [r12], r13d
0x1800f6d8e  jnz     loc_1800F7091
0x1800f6d94  mov     eax, [rsi+0B8h]
0x1800f6d9a  mov     [rsp+220h+var_1D0], eax
0x1800f6d9e  lea     r15d, [r13+1]
0x1800f6da2  cmp     eax, r15d
0x1800f6da5  jnz     short loc_1800F6DAF
0x1800f6da7  mov     eax, [rsi+1C8h]
0x1800f6dad  jmp     short loc_1800F6DB2
0x1800f6daf  mov     eax, r15d
0x1800f6db2  mov     [rsp+220h+var_1F0], eax
0x1800f6db6  lea     r8, [rsp+220h+var_1D0]
0x1800f6dbb  lea     rdx, [rsp+220h+var_1F0]
0x1800f6dc0  lea     rcx, [rbp+120h+var_190]
0x1800f6dc4  call    ??$CreateComputeSystem@KK@ContainerStateTransition@CmTraceProvider@@QEAAX$$QEAK0@Z; CmTraceProvider::ContainerStateTransition::CreateComputeSystem<ulong,ulong>(ulong &&,ulong &&)
0x1800f6dc9  mov     dword ptr [rsi+80h], 2
0x1800f6dd3  mov     rcx, [r14]; SRWLock
0x1800f6dd6  test    rcx, rcx
0x1800f6dd9  jz      short loc_1800F6DEE
0x1800f6ddb  mov     [rcx+8], r13d
0x1800f6ddf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6de6  nop     dword ptr [rax+rax+00h]
0x1800f6deb  mov     [r14], r13
0x1800f6dee  lea     rcx, [rsi+5F8h]; this
0x1800f6df5  call    ?Setup@Silo@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::Silo::Setup(void)
0x1800f6dfa  mov     edi, eax
0x1800f6dfc  test    eax, eax
0x1800f6dfe  jns     loc_1800F6EC1
0x1800f6e04  mov     rcx, rsi; SRWLock
0x1800f6e07  call    cs:__imp_AcquireSRWLockExclusive
0x1800f6e0e  nop     dword ptr [rax+rax+00h]
0x1800f6e13  call    cs:__imp_GetCurrentThreadId
0x1800f6e1a  nop     dword ptr [rax+rax+00h]
0x1800f6e1f  mov     [rsi+8], eax
0x1800f6e22  lea     rax, [rsp+220h+var_1C8]
0x1800f6e27  cmp     r14, rax
0x1800f6e2a  jz      short loc_1800F6E49
0x1800f6e2c  mov     rcx, [r14]; SRWLock
0x1800f6e2f  test    rcx, rcx
0x1800f6e32  jz      short loc_1800F6E44
0x1800f6e34  mov     [rcx+8], r13d
0x1800f6e38  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6e3f  nop     dword ptr [rax+rax+00h]
0x1800f6e44  mov     [r14], rsi
0x1800f6e47  jmp     short loc_1800F6E5C
0x1800f6e49  mov     [rsi+8], r13d
0x1800f6e4d  mov     rcx, rsi; SRWLock
0x1800f6e50  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6e57  nop     dword ptr [rax+rax+00h]
0x1800f6e5c  mov     rcx, [rbp+128h]; this
0x1800f6e63  mov     r9d, edi; char *
0x1800f6e66  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f6e6d  mov     edx, 3B4h; void *
0x1800f6e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6e77  lea     rcx, [rsp+220h+var_1E8]
0x1800f6e7c  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f6e81  nop
0x1800f6e82  mov     rcx, [rsp+220h+var_1D8]; this
0x1800f6e87  test    rcx, rcx
0x1800f6e8a  jz      short loc_1800F6E92
0x1800f6e8c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f6e91  nop
0x1800f6e92  mov     rbx, [rsp+220h+var_1E8]
0x1800f6e97  test    rbx, rbx
0x1800f6e9a  jz      short loc_1800F6EB1
0x1800f6e9c  mov     rcx, rbx
0x1800f6e9f  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f6ea4  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800f6ea9  mov     rcx, rbx; void *
0x1800f6eac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f6eb1  lea     rax, ??_7ContainerStateTransition@CmTraceProvider@@6B@; const CmTraceProvider::ContainerStateTransition::`vftable'
0x1800f6eb8  mov     [rbp+120h+var_190], rax
0x1800f6ebc  jmp     loc_1800F7597
0x1800f6ec1  lea     r8, [rsp+220h+var_1E8]
0x1800f6ec6  mov     rdx, rbx
0x1800f6ec9  mov     rcx, [rsi+0A0h]
0x1800f6ed0  call    ?CreateAsync@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBUComputeSystemConfiguration@234@AEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::CreateAsync(Container::Manager::Hcs::ComputeSystemConfiguration const &,Csl::AsyncOperation<void> &)
0x1800f6ed5  mov     ebx, eax
0x1800f6ed7  mov     rcx, rsi; SRWLock
0x1800f6eda  call    cs:__imp_AcquireSRWLockExclusive
0x1800f6ee1  nop     dword ptr [rax+rax+00h]
0x1800f6ee6  call    cs:__imp_GetCurrentThreadId
0x1800f6eed  nop     dword ptr [rax+rax+00h]
0x1800f6ef2  mov     [rsi+8], eax
0x1800f6ef5  lea     rax, [rsp+220h+var_1C0]
0x1800f6efa  cmp     r14, rax
0x1800f6efd  jz      short loc_1800F6F1C
0x1800f6eff  mov     rcx, [r14]; SRWLock
0x1800f6f02  test    rcx, rcx
0x1800f6f05  jz      short loc_1800F6F17
0x1800f6f07  mov     [rcx+8], r13d
0x1800f6f0b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6f12  nop     dword ptr [rax+rax+00h]
0x1800f6f17  mov     [r14], rsi
0x1800f6f1a  jmp     short loc_1800F6F2F
0x1800f6f1c  mov     [rsi+8], r13d
0x1800f6f20  mov     rcx, rsi; SRWLock
0x1800f6f23  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6f2a  nop     dword ptr [rax+rax+00h]
0x1800f6f2f  test    ebx, ebx
0x1800f6f31  jns     short loc_1800F6F6E
0x1800f6f33  mov     rcx, [rbp+128h]; this
0x1800f6f3a  mov     r9d, ebx; char *
0x1800f6f3d  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f6f44  mov     edx, 3BFh; void *
0x1800f6f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6f4e  lea     rcx, [rsp+220h+var_1E8]
0x1800f6f53  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f6f58  nop
0x1800f6f59  mov     rcx, [rsp+220h+var_1D8]; this
0x1800f6f5e  test    rcx, rcx
0x1800f6f61  jz      short loc_1800F6F69
0x1800f6f63  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f6f68  nop
0x1800f6f69  jmp     loc_1800F743B
0x1800f6f6e  cmp     dword ptr [r12], 5
0x1800f6f73  jz      short loc_1800F6FCC
0x1800f6f75  mov     [r12], r15d
0x1800f6f79  mov     [rsp+220h+var_1F8], r14; __int64
0x1800f6f7e  mov     [rsp+220h+var_200], r13b; int
0x1800f6f83  xor     r9d, r9d
0x1800f6f86  mov     r8, r12
0x1800f6f89  mov     rdx, [rsi+5E0h]
0x1800f6f90  mov     rcx, rsi; SRWLock
0x1800f6f93  call    ?InvokeStateTransitionCallback@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEAAXP6AXAEBUComputeSystemState@2345@JPEAX@Z0J_NAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::InvokeStateTransitionCallback(void (*)(Container::Manager::Core::Details::ComputeSystemState const &,long,void *),Container::Manager::Core::Details::ComputeSystemState const &,long,bool,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800f6f98  mov     rbx, [rsi+48h]
0x1800f6f9c  mov     rdi, [rsi+50h]
0x1800f6fa0  cmp     rbx, rdi
0x1800f6fa3  jz      short loc_1800F6FC4
0x1800f6fa5  mov     rax, [rbx]
0x1800f6fa8  mov     [rax+4], r13d
0x1800f6fac  mov     rcx, [rbx]; Address
0x1800f6faf  mov     [rcx], r15d
0x1800f6fb2  call    cs:__imp_WakeByAddressAll
0x1800f6fb9  nop     dword ptr [rax+rax+00h]
0x1800f6fbe  add     rbx, 8
0x1800f6fc2  jmp     short loc_1800F6FA0
0x1800f6fc4  mov     rax, [rsi+48h]
0x1800f6fc8  mov     [rsi+50h], rax
0x1800f6fcc  mov     rbx, [rsp+220h+var_1E8]
0x1800f6fd1  lea     rdi, [rbx+8]
0x1800f6fd5  mov     rcx, rdi; SRWLock
0x1800f6fd8  call    cs:__imp_AcquireSRWLockExclusive
0x1800f6fdf  nop     dword ptr [rax+rax+00h]
0x1800f6fe4  lea     rax, ?OnAsyncStateTransitionCompleted@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@CAXJPEAX@Z; Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::OnAsyncStateTransitionCompleted(long,void *)
0x1800f6feb  mov     [rbx+10h], rax
0x1800f6fef  mov     [rbx+18h], rsi
0x1800f6ff3  cmp     dword ptr [rbx], 2
0x1800f6ff6  jnz     short loc_1800F7008
0x1800f6ff8  mov     rcx, [rbx+20h]; pwk
0x1800f6ffc  call    cs:__imp_SubmitThreadpoolWork
0x1800f7003  nop     dword ptr [rax+rax+00h]
0x1800f7008  test    rdi, rdi
0x1800f700b  jz      short loc_1800F701C
0x1800f700d  mov     rcx, rdi; SRWLock
0x1800f7010  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7017  nop     dword ptr [rax+rax+00h]
0x1800f701c  mov     rcx, [r14]; SRWLock
0x1800f701f  test    rcx, rcx
0x1800f7022  jz      short loc_1800F7037
0x1800f7024  mov     [rcx+8], r13d
0x1800f7028  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f702f  nop     dword ptr [rax+rax+00h]
0x1800f7034  mov     [r14], r13
0x1800f7037  mov     edx, 7
0x1800f703c  mov     rcx, rsi
0x1800f703f  call    ?WaitForStateTransitionThreadEvent@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEBA?AW4ComputeSystemStateTransitionEngineEvent@2345@W462345@@Z; Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::WaitForStateTransitionThreadEvent(Container::Manager::Core::Details::ComputeSystemStateTransitionEngineEvent)
0x1800f7044  mov     ebx, eax
0x1800f7046  mov     rcx, rsi; SRWLock
0x1800f7049  call    cs:__imp_AcquireSRWLockExclusive
0x1800f7050  nop     dword ptr [rax+rax+00h]
0x1800f7055  call    cs:__imp_GetCurrentThreadId
0x1800f705c  nop     dword ptr [rax+rax+00h]
0x1800f7061  mov     [rsi+8], eax
0x1800f7064  lea     rax, [rbp+120h+var_1A0]
0x1800f7068  cmp     r14, rax
0x1800f706b  jz      loc_1800F73AD
0x1800f7071  mov     rcx, [r14]; SRWLock
0x1800f7074  test    rcx, rcx
0x1800f7077  jz      short loc_1800F7089
0x1800f7079  mov     [rcx+8], r13d
0x1800f707d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7084  nop     dword ptr [rax+rax+00h]
0x1800f7089  mov     [r14], rsi
0x1800f708c  jmp     loc_1800F73C5
0x1800f7091  mov     ebx, 3
0x1800f7096  cmp     [r12], ebx
0x1800f709a  jge     loc_1800F71A1
0x1800f70a0  mov     eax, [rsi+0B8h]
0x1800f70a6  mov     [rsp+220h+var_1F0], eax
0x1800f70aa  lea     r15d, [rbx-2]
0x1800f70ae  cmp     eax, r15d
0x1800f70b1  jnz     short loc_1800F70BA
0x1800f70b3  mov     r15d, [rsi+1C8h]
0x1800f70ba  mov     [rsp+220h+var_1D0], r15d
0x1800f70bf  lea     r8, [rsp+220h+var_1F0]
0x1800f70c4  lea     rdx, [rsp+220h+var_1D0]
0x1800f70c9  lea     rcx, [rbp+120h+var_190]
0x1800f70cd  call    ??$StartComputeSystem@KK@ContainerStateTransition@CmTraceProvider@@QEAAX$$QEAK0@Z; CmTraceProvider::ContainerStateTransition::StartComputeSystem<ulong,ulong>(ulong &&,ulong &&)
0x1800f70d2  mov     [rsi+80h], ebx
0x1800f70d8  mov     rcx, [r14]; SRWLock
0x1800f70db  test    rcx, rcx
0x1800f70de  jz      short loc_1800F70F3
0x1800f70e0  mov     [rcx+8], r13d
0x1800f70e4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f70eb  nop     dword ptr [rax+rax+00h]
0x1800f70f0  mov     [r14], r13
0x1800f70f3  lea     rdx, [rsp+220h+var_1E8]
0x1800f70f8  mov     rcx, [rsi+0A0h]
0x1800f70ff  call    ?StartAsync@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::StartAsync(Csl::AsyncOperation<void> &)
0x1800f7104  mov     edi, eax
0x1800f7106  mov     rcx, rsi; SRWLock
0x1800f7109  call    cs:__imp_AcquireSRWLockExclusive
0x1800f7110  nop     dword ptr [rax+rax+00h]
0x1800f7115  call    cs:__imp_GetCurrentThreadId
0x1800f711c  nop     dword ptr [rax+rax+00h]
0x1800f7121  mov     [rsi+8], eax
0x1800f7124  lea     rax, [rsp+220h+var_1B8]
0x1800f7129  cmp     r14, rax
0x1800f712c  jz      short loc_1800F714B
0x1800f712e  mov     rcx, [r14]; SRWLock
0x1800f7131  test    rcx, rcx
0x1800f7134  jz      short loc_1800F7146
0x1800f7136  mov     [rcx+8], r13d
0x1800f713a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7141  nop     dword ptr [rax+rax+00h]
0x1800f7146  mov     [r14], rsi
0x1800f7149  jmp     short loc_1800F715E
0x1800f714b  mov     [rsi+8], r13d
0x1800f714f  mov     rcx, rsi; SRWLock
0x1800f7152  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f7159  nop     dword ptr [rax+rax+00h]
0x1800f715e  test    edi, edi
0x1800f7160  jns     loc_1800F6FCC
0x1800f7166  mov     rcx, [rbp+128h]; this
0x1800f716d  mov     r9d, edi; char *
0x1800f7170  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f7177  mov     edx, 403h; void *
0x1800f717c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7181  lea     rcx, [rsp+220h+var_1E8]
0x1800f7186  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f718b  nop
0x1800f718c  mov     rcx, [rsp+220h+var_1D8]; this
0x1800f7191  test    rcx, rcx
0x1800f7194  jz      short loc_1800F719C
0x1800f7196  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f719b  nop
0x1800f719c  jmp     loc_1800F74F7
0x1800f71a1  cmp     dword ptr [rsi+2Ch], 4
0x1800f71a5  jnz     loc_1800F72AE
0x1800f71ab  mov     eax, [rsi+40h]
0x1800f71ae  mov     [rsp+220h+var_1F0], eax
0x1800f71b2  lea     rdx, [rsp+220h+var_1F0]
0x1800f71b7  lea     rcx, [rbp+120h+var_190]
0x1800f71bb  call    ??$PauseComputeSystem@K@ContainerStateTransition@CmTraceProvider@@QEAAX$$QEAK@Z; CmTraceProvider::ContainerStateTransition::PauseComputeSystem<ulong>(ulong &&)
0x1800f71c0  mov     dword ptr [rsi+80h], 4
0x1800f71ca  cmp     [rsi+98h], r13b
0x1800f71d1  jnz     short loc_1800F71DA
0x1800f71d3  mov     byte ptr [rsi+98h], 1
0x1800f71da  mov     ebx, [rsi+40h]
0x1800f71dd  mov     [rsi+94h], ebx
0x1800f71e3  mov     rcx, [r14]; SRWLock
0x1800f71e6  test    rcx, rcx
0x1800f71e9  jz      short loc_1800F71FE
0x1800f71eb  mov     [rcx+8], r13d
0x1800f71ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f71f6  nop     dword ptr [rax+rax+00h]
0x1800f71fb  mov     [r14], r13
0x1800f71fe  lea     r8, [rsp+220h+var_1E8]
0x1800f7203  mov     edx, ebx
  ... truncated ...
```
