# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(bool)

- ea: `0x1800f8d40`
- end: `0x1800f9071`
- name: `?Terminate@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@QEAAJ_N@Z`
- size: `817`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, bool)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009f058`
- `0x1800b77ac`
- `0x1800efa5c`
- `0x1800efb64`
- `0x1800f0ef8`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x1800103a4`
- `0x180016718`
- `0x18003dbf8`
- `0x18003f7d8`
- `0x1800471dc`
- `0x180049a0c`
- `0x1800f4d24`
- `0x1800f8634`
- `0x1800f8d40`
- `0x180123048`
- `0x180125150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8eb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8e24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8e9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8ed4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8e24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8e9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8ebe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8ebe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(
        PSRWLOCK SRWLock,
        bool a2)
{
  unsigned int Ptr; // ebx
  int v5; // ebx
  _QWORD *v6; // rax
  int v7; // eax
  void *v8; // rdi
  int *v9; // rbx
  void *v10; // rbx
  int Address; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v13[5]; // [rsp+24h] [rbp-DCh] BYREF
  utl::_RefCountBase *v14; // [rsp+38h] [rbp-C8h]
  int *p_Address; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  Ptr = (unsigned int)SRWLock[23].Ptr;
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "ContainerTerminationStateTransition");
  v16[0] = &CmTraceProvider::ContainerTerminationStateTransition::`vftable';
  CmTraceProvider::ContainerTerminationStateTransition::StartActivity(
    (CmTraceProvider::ContainerTerminationStateTransition *)v16,
    (const struct _GUID *)&SRWLock[21],
    Ptr,
    a2);
  AcquireSRWLockExclusive(SRWLock);
  LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
  if ( !LODWORD(SRWLock[2].Ptr) )
  {
    if ( !HIDWORD(SRWLock[5].Ptr) )
    {
      v5 = -2147019873;
LABEL_10:
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_31;
    }
    Address = 0;
    v13[0] = -2147467259;
    p_Address = &Address;
    v6 = SRWLock[10].Ptr;
    if ( v6 == SRWLock[11].Ptr )
    {
      if ( !(unsigned __int8)utl::vector<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *,utl::allocator<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *>>::_PushBackOne2<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *>(
                               &SRWLock[9],
                               &p_Address) )
      {
        v5 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
          (const char *)0x8007000ELL,
          Address);
        goto LABEL_10;
      }
    }
    else
    {
      *v6 = &Address;
      SRWLock[10].Ptr = (char *)SRWLock[10].Ptr + 8;
    }
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(SRWLock);
    wil::slim_event_t<1>::wait(&Address);
    if ( v13[0] < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
        (const char *)v13[0],
        Address);
      v5 = -2147019873;
      goto LABEL_31;
    }
    AcquireSRWLockExclusive(SRWLock);
    GetCurrentThreadId();
  }
  LODWORD(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(SRWLock);
  if ( !a2
    && Container::Manager::Hcs::ComputeSystem::HasCrashed((Container::Manager::Hcs::ComputeSystem *)SRWLock[20].Ptr) )
  {
    wil::slim_event_t<1>::wait((volatile void *)(*((_QWORD *)SRWLock[184].Ptr + 1) + 4LL));
  }
  *(_OWORD *)&v13[1] = 0;
  v14 = 0;
  v7 = Container::Manager::Hcs::ComputeSystem::TerminateAsync(SRWLock[20].Ptr, &v13[1]);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v7,
      Address);
    Csl::AsyncOperation<void>::Cleanup(&v13[1]);
    if ( v14 )
      utl::_RefCountBase::_DecStrong(v14);
LABEL_18:
    v8 = *(void **)&v13[1];
    if ( *(_QWORD *)&v13[1] )
    {
      Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(*(_DWORD **)&v13[1]);
      operator delete(v8, (const struct std::nothrow_t *)0x30);
    }
    goto LABEL_31;
  }
  v9 = *(int **)&v13[3];
  if ( !(unsigned __int8)wil::slim_event_t<1>::wait((volatile void *)(*(_QWORD *)&v13[3] + 4LL)) )
  {
    v5 = -2147023436;
    goto LABEL_23;
  }
  v5 = *v9;
  if ( v5 < 0 )
  {
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)v5,
      Address);
    Csl::AsyncOperation<void>::Cleanup(&v13[1]);
    if ( v14 )
      utl::_RefCountBase::_DecStrong(v14);
    goto LABEL_18;
  }
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, 0);
  Csl::AsyncOperation<void>::Cleanup(&v13[1]);
  if ( v14 )
    utl::_RefCountBase::_DecStrong(v14);
  v10 = *(void **)&v13[1];
  if ( *(_QWORD *)&v13[1] )
  {
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(*(_DWORD **)&v13[1]);
    operator delete(v10, (const struct std::nothrow_t *)0x30);
  }
  v5 = 0;
LABEL_31:
  v16[0] = &CmTraceProvider::ContainerTerminationStateTransition::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800f8d40  mov     [rsp-8+arg_10], rbx
0x1800f8d45  push    rbp
0x1800f8d46  push    rsi
0x1800f8d47  push    rdi
0x1800f8d48  push    r12
0x1800f8d4a  push    r14
0x1800f8d4c  lea     rbp, [rsp-0B0h]
0x1800f8d54  sub     rsp, 1B0h
0x1800f8d5b  mov     rax, cs:__security_cookie
0x1800f8d62  xor     rax, rsp
0x1800f8d65  mov     [rbp+0D0h+var_30], rax
0x1800f8d6c  mov     r14b, dl
0x1800f8d6f  mov     rsi, rcx
0x1800f8d72  mov     ebx, [rcx+0B8h]
0x1800f8d78  lea     rdx, aContainertermi; "ContainerTerminationStateTransition"
0x1800f8d7f  lea     rcx, [rsp+1D0h+var_180]
0x1800f8d84  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f8d89  lea     r12, ??_7ContainerTerminationStateTransition@CmTraceProvider@@6B@; const CmTraceProvider::ContainerTerminationStateTransition::`vftable'
0x1800f8d90  mov     [rsp+1D0h+var_180], r12
0x1800f8d95  mov     r9b, r14b; bool
0x1800f8d98  mov     r8d, ebx; unsigned int
0x1800f8d9b  lea     rdx, [rsi+0A8h]; struct _GUID *
0x1800f8da2  lea     rcx, [rsp+1D0h+var_180]; this
0x1800f8da7  call    ?StartActivity@ContainerTerminationStateTransition@CmTraceProvider@@QEAAXAEBU_GUID@@K_N@Z; CmTraceProvider::ContainerTerminationStateTransition::StartActivity(_GUID const &,ulong,bool)
0x1800f8dac  nop
0x1800f8dad  mov     rcx, rsi; SRWLock
0x1800f8db0  call    cs:__imp_AcquireSRWLockExclusive
0x1800f8db7  nop     dword ptr [rax+rax+00h]
0x1800f8dbc  call    cs:__imp_GetCurrentThreadId
0x1800f8dc3  nop     dword ptr [rax+rax+00h]
0x1800f8dc8  mov     [rsi+8], eax
0x1800f8dcb  cmp     dword ptr [rsi+10h], 0
0x1800f8dcf  jnz     loc_1800F8ECA
0x1800f8dd5  cmp     dword ptr [rsi+2Ch], 0
0x1800f8dd9  jnz     short loc_1800F8DE5
0x1800f8ddb  mov     ebx, 8007139Fh
0x1800f8de0  jmp     loc_1800F8E94
0x1800f8de5  mov     [rsp+1D0h+Address], 0; int
0x1800f8ded  mov     dword ptr [rsp+1D0h+var_1AC], 80004005h
0x1800f8df5  lea     rcx, [rsi+48h]
0x1800f8df9  lea     rax, [rsp+1D0h+Address]
0x1800f8dfe  mov     [rsp+1D0h+var_190], rax
0x1800f8e03  mov     rax, [rcx+8]
0x1800f8e07  cmp     rax, [rcx+10h]
0x1800f8e0b  jz      short loc_1800F8E66
0x1800f8e0d  lea     rdx, [rsp+1D0h+Address]
0x1800f8e12  mov     [rax], rdx
0x1800f8e15  add     qword ptr [rcx+8], 8
0x1800f8e1a  mov     dword ptr [rsi+8], 0
0x1800f8e21  mov     rcx, rsi; SRWLock
0x1800f8e24  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f8e2b  nop     dword ptr [rax+rax+00h]
0x1800f8e30  lea     rcx, [rsp+1D0h+Address]; Address
0x1800f8e35  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800f8e3a  mov     r9d, dword ptr [rsp+1D0h+var_1AC]; char *
0x1800f8e3f  mov     rcx, [rbp+0D8h]; this
0x1800f8e46  test    r9d, r9d
0x1800f8e49  jns     short loc_1800F8EAF
0x1800f8e4b  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f8e52  mov     edx, 20Fh; void *
0x1800f8e57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8e5c  mov     ebx, 8007139Fh
0x1800f8e61  jmp     loc_1800F902F
0x1800f8e66  lea     rdx, [rsp+1D0h+var_190]
0x1800f8e6b  call    ??$_PushBackOne2@PEAUComputeSystemInitializationWaiter@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@@?$vector@PEAUComputeSystemInitializationWaiter@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@V?$allocator@PEAUComputeSystemInitializationWaiter@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@@utl@@@utl@@AEAA_N$$QEAPEAUComputeSystemInitializationWaiter@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@@Z; utl::vector<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *,utl::allocator<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *>>::_PushBackOne2<Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter *>(Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::ComputeSystemInitializationWaiter * &&)
0x1800f8e70  test    al, al
0x1800f8e72  jnz     short loc_1800F8E1A
0x1800f8e74  mov     rcx, [rbp+0D8h]; this
0x1800f8e7b  mov     ebx, 8007000Eh
0x1800f8e80  mov     r9d, ebx; char *
0x1800f8e83  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f8e8a  mov     edx, 203h; void *
0x1800f8e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8e94  mov     dword ptr [rsi+8], 0
0x1800f8e9b  mov     rcx, rsi; SRWLock
0x1800f8e9e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f8ea5  nop     dword ptr [rax+rax+00h]
0x1800f8eaa  jmp     loc_1800F902F
0x1800f8eaf  mov     rcx, rsi; SRWLock
0x1800f8eb2  call    cs:__imp_AcquireSRWLockExclusive
0x1800f8eb9  nop     dword ptr [rax+rax+00h]
0x1800f8ebe  call    cs:__imp_GetCurrentThreadId
0x1800f8ec5  nop     dword ptr [rax+rax+00h]
0x1800f8eca  mov     dword ptr [rsi+8], 0
0x1800f8ed1  mov     rcx, rsi; SRWLock
0x1800f8ed4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f8edb  nop     dword ptr [rax+rax+00h]
0x1800f8ee0  test    r14b, r14b
0x1800f8ee3  jnz     short loc_1800F8F09
0x1800f8ee5  mov     rcx, [rsi+0A0h]; this
0x1800f8eec  call    ?HasCrashed@ComputeSystem@Hcs@Manager@Container@@QEBA_NXZ; Container::Manager::Hcs::ComputeSystem::HasCrashed(void)
0x1800f8ef1  test    al, al
0x1800f8ef3  jz      short loc_1800F8F09
0x1800f8ef5  mov     rax, [rsi+5C0h]
0x1800f8efc  mov     rcx, [rax+8]
0x1800f8f00  add     rcx, 4; Address
0x1800f8f04  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800f8f09  xorps   xmm0, xmm0
0x1800f8f0c  movdqu  xmmword ptr [rsp+1D0h+var_1AC+4], xmm0
0x1800f8f12  mov     [rsp+1D0h+var_198], 0
0x1800f8f1b  lea     rdx, [rsp+1D0h+var_1AC+4]
0x1800f8f20  mov     rcx, [rsi+0A0h]
0x1800f8f27  call    ?TerminateAsync@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::TerminateAsync(Csl::AsyncOperation<void> &)
0x1800f8f2c  mov     ebx, eax
0x1800f8f2e  test    eax, eax
0x1800f8f30  jns     short loc_1800F8F90
0x1800f8f32  mov     rcx, [rbp+0D8h]; this
0x1800f8f39  mov     r9d, eax; char *
0x1800f8f3c  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f8f43  mov     edx, 22Bh; void *
0x1800f8f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8f4d  lea     rcx, [rsp+1D0h+var_1AC+4]
0x1800f8f52  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f8f57  nop
0x1800f8f58  mov     rcx, [rsp+1D0h+var_198]; this
0x1800f8f5d  test    rcx, rcx
0x1800f8f60  jz      short loc_1800F8F68
0x1800f8f62  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f8f67  nop
0x1800f8f68  mov     rdi, qword ptr [rsp+1D0h+var_1AC+4]
0x1800f8f6d  test    rdi, rdi
0x1800f8f70  jz      loc_1800F902F
0x1800f8f76  mov     rcx, rdi
0x1800f8f79  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f8f7e  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800f8f83  mov     rcx, rdi; void *
0x1800f8f86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f8f8b  jmp     loc_1800F902F
0x1800f8f90  mov     rbx, qword ptr [rsp+1D0h+var_1AC+0Ch]
0x1800f8f95  lea     rcx, [rbx+4]; Address
0x1800f8f99  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800f8f9e  test    al, al
0x1800f8fa0  jnz     short loc_1800F8FA9
0x1800f8fa2  mov     ebx, 800705B4h
0x1800f8fa7  jmp     short loc_1800F8FAF
0x1800f8fa9  mov     ebx, [rbx]
0x1800f8fab  test    ebx, ebx
0x1800f8fad  jns     short loc_1800F8FE7
0x1800f8faf  mov     rcx, [rbp+0D8h]; this
0x1800f8fb6  mov     r9d, ebx; char *
0x1800f8fb9  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f8fc0  mov     edx, 22Ch; void *
0x1800f8fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8fca  lea     rcx, [rsp+1D0h+var_1AC+4]
0x1800f8fcf  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f8fd4  nop
0x1800f8fd5  mov     rcx, [rsp+1D0h+var_198]; this
0x1800f8fda  test    rcx, rcx
0x1800f8fdd  jz      short loc_1800F8FE5
0x1800f8fdf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f8fe4  nop
0x1800f8fe5  jmp     short loc_1800F8F68
0x1800f8fe7  xor     edx, edx
0x1800f8fe9  lea     rcx, [rsp+1D0h+var_180]
0x1800f8fee  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800f8ff3  lea     rcx, [rsp+1D0h+var_1AC+4]
0x1800f8ff8  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x1800f8ffd  nop
0x1800f8ffe  mov     rcx, [rsp+1D0h+var_198]; this
0x1800f9003  test    rcx, rcx
0x1800f9006  jz      short loc_1800F900E
0x1800f9008  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800f900d  nop
0x1800f900e  mov     rbx, qword ptr [rsp+1D0h+var_1AC+4]
0x1800f9013  test    rbx, rbx
0x1800f9016  jz      short loc_1800F902D
0x1800f9018  mov     rcx, rbx
0x1800f901b  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x1800f9020  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800f9025  mov     rcx, rbx; void *
0x1800f9028  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f902d  xor     ebx, ebx
0x1800f902f  mov     [rsp+1D0h+var_180], r12
0x1800f9034  lea     rcx, [rsp+1D0h+var_180]
0x1800f9039  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800f903e  lea     rcx, [rsp+1D0h+var_180]
0x1800f9043  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800f9048  mov     eax, ebx
0x1800f904a  mov     rcx, [rbp+0D0h+var_30]
0x1800f9051  xor     rcx, rsp; StackCookie
0x1800f9054  call    __security_check_cookie
0x1800f9059  mov     rbx, [rsp+1D0h+arg_10]
0x1800f9061  add     rsp, 1B0h
0x1800f9068  pop     r14
0x1800f906a  pop     r12
0x1800f906c  pop     rdi
0x1800f906d  pop     rsi
0x1800f906e  pop     rbp
0x1800f906f  retn
```
