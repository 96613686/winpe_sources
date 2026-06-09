# Container::Manager::Core::Details::ContainerObject::ProcessMirrorNetworkWorkItem(Container::Manager::Core::Details::ContainerObject::MirrorNetworkWorkItem &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800ab1c4`
- end: `0x1800ab9bb`
- name: `?ProcessMirrorNetworkWorkItem@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAUMirrorNetworkWorkItem@12345@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `2039`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800b9b40`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000b49c`
- `0x1800103a4`
- `0x180016718`
- `0x180042b58`
- `0x180047440`
- `0x1800475c4`
- `0x18004891c`
- `0x180049a0c`
- `0x18004eb4c`
- `0x180050290`
- `0x18006931c`
- `0x18009bcc4`
- `0x1800ab1c4`
- `0x1800ad22c`
- `0x1800afb88`
- `0x1800b0b24`
- `0x1800b74f4`
- `0x180188a2c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab732`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ab732`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ab621`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ab621`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800ab867`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800ab867`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab574`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab91a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab574`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab91a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab275`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab2fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab54d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab5a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab5f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab8da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab94a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab966`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab275`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab2fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab54d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab5a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab5f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab8da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab94a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ab966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab926`
- `RPCRT4!UuidCompare` at `0x1800ab791`
- `RPCRT4!UuidCompare` at `0x1800ab7d9`
- `RPCRT4!UuidCompare` at `0x1800ab791`
- `RPCRT4!UuidCompare` at `0x1800ab7d9`

## string_xrefs

- `0x1800ab22e`: `CreateContainerStateTransition_MirrorNetworks`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ContainerObject::ProcessMirrorNetworkWorkItem(
        struct _GUID *a1,
        __int64 a2,
        char *a3)
{
  __int64 v6; // rdi
  void **v7; // r12
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  UUID *v13; // r12
  char *v14; // rax
  PSRWLOCK v15; // rbx
  _QWORD *v16; // rax
  char *v17; // rax
  _QWORD *v18; // rax
  char v19; // al
  PSRWLOCK *v20; // rax
  PSRWLOCK v21; // rbx
  RTL_SRWLOCK *Ptr; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  struct _GUID *v25; // rdx
  __int64 v26; // rdx
  __int128 v27; // xmm0
  int v28; // eax
  wil::details::in1diag3 *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  struct _GUID *v33; // rbx
  __int64 v34; // r13
  __int64 v35; // rax
  unsigned __int8 *Data4; // r12
  __int64 v37; // rcx
  unsigned __int8 *v38; // r14
  __int64 *v39; // rcx
  __int64 *v40; // rdx
  __int64 v41; // rax
  _DWORD *v42; // rcx
  _QWORD *v43; // rcx
  _QWORD *v44; // rdx
  __int64 v45; // rax
  PSRWLOCK v46; // rcx
  int updated; // eax
  unsigned __int8 *v48; // rsi
  PSRWLOCK v49; // rcx
  __int64 v50; // rcx
  int v51; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v53; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  char v55; // [rsp+60h] [rbp-A0h] BYREF
  char v56; // [rsp+68h] [rbp-98h] BYREF
  __int128 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  _QWORD v59[34]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v60; // [rsp+1A0h] [rbp+A0h]
  _QWORD v61[39]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v62; // [rsp+318h] [rbp+218h]
  _QWORD v63[42]; // [rsp+330h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v6 = *(_QWORD *)(a2 + 24);
  if ( v6 && *(_DWORD *)(v6 + 24) )
  {
    if ( *(_DWORD *)(v6 + 24) == 3 )
    {
      if ( *(_BYTE *)(v6 + 384) )
        goto LABEL_16;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v59,
        "CreateContainerStateTransition_MirrorNetworks");
      v7 = &CmTraceProvider::CreateContainerStateTransition_MirrorNetworks::`vftable';
      v59[0] = &CmTraceProvider::CreateContainerStateTransition_MirrorNetworks::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v59, SRWLock);
      v8 = v60;
      *(_OWORD *)(v60 + 24) = *(_OWORD *)(v6 + 28);
      *(_BYTE *)(v8 + 4) = 1;
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
      CmTraceProvider::CreateContainerStateTransition_MirrorNetworks::StartActivity(
        (CmTraceProvider::CreateContainerStateTransition_MirrorNetworks *)v59,
        *(_DWORD *)(v6 + 8));
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v61,
        v59,
        0);
      v10 = v6 + 48;
    }
    else
    {
      if ( *(_BYTE *)(v6 + 728) )
        goto LABEL_16;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v59,
        "ResumeContainerStateTransition_MirrorNetworks");
      v7 = &CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks::`vftable';
      v59[0] = &CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v59, SRWLock);
      v11 = v60;
      *(_OWORD *)(v60 + 24) = *(_OWORD *)(v6 + 28);
      *(_BYTE *)(v11 + 4) = 1;
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
      CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks::StartActivity(
        (CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks *)v59,
        *(_DWORD *)(v6 + 8),
        *(_DWORD *)(v6 + 12),
        *(_DWORD *)(v6 + 16),
        *(_DWORD *)(v6 + 20));
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v61,
        v59,
        0);
      v10 = v6 + 392;
    }
    v61[0] = v7;
    if ( *(_BYTE *)(v10 + 336) )
    {
      LOBYTE(v9) = *(_DWORD *)(v10 + 312) != 0;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v63,
        v10,
        v9);
      v63[0] = v7;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
        v10,
        v61);
      v63[0] = v7;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v63);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v63);
    }
    else
    {
      LOBYTE(v9) = v62 != 0;
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v10,
        v61,
        v9);
      *(_QWORD *)v10 = v7;
      *(_BYTE *)(v10 + 336) = 1;
    }
    v61[0] = v7;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v61);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v61);
    v59[0] = v7;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v59);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v59);
  }
LABEL_16:
  v12 = (unsigned __int64)&a1[37];
  v13 = (UUID *)(a2 + 4);
  if ( *(struct _GUID **)&a1[38].Data1 == &a1[37] )
  {
    v14 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = (PSRWLOCK)v14;
    if ( v14 )
    {
      *(UUID *)(v14 + 24) = *v13;
      v16 = v14 + 40;
      *v16 = v16;
      v16[1] = v16;
      v16[2] = 0;
      v15->Ptr = (PVOID)(v12 | 1);
      v15[1].Ptr = &utl::_TreeSentinel;
      v15[2].Ptr = &utl::_TreeSentinel;
      *(_QWORD *)v12 = v15;
      *(_QWORD *)a1[37].Data4 = v15;
      *(_QWORD *)&a1[38].Data1 = v15;
      ++*(_QWORD *)a1[38].Data4;
LABEL_22:
      v19 = 1;
      goto LABEL_24;
    }
  }
  else
  {
    SRWLock[0] = 0;
    v53 = *(_OWORD *)utl::_Tree<_GUID,utl::pair<_GUID const,Container::Manager::Core::Details::DeploymentManager::MaterializeContext>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,Container::Manager::Core::Details::DeploymentManager::MaterializeContext>>,0>::_FindInsertionPointUniqueUpper(
                       &a1[37],
                       &v53,
                       SRWLock,
                       a2 + 4);
    v15 = SRWLock[0];
    if ( !SRWLock[0] )
    {
      v17 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = (PSRWLOCK)v17;
      if ( v17 )
      {
        *(UUID *)(v17 + 24) = *v13;
        v18 = v17 + 40;
        *v18 = v18;
        v18[1] = v18;
        v18[2] = 0;
        utl::_Tree<_GUID,utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>>,0>::_InsertAt(
          &a1[37],
          &v53,
          v15);
        goto LABEL_22;
      }
    }
  }
  v19 = 0;
LABEL_24:
  if ( !v15 )
  {
    v26 = 2949;
    goto LABEL_73;
  }
  if ( v19 )
    goto LABEL_33;
  LODWORD(SRWLock[0]) = 0;
  v20 = (PSRWLOCK *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v20 )
  {
    v26 = 2941;
LABEL_73:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v51);
    goto LABEL_74;
  }
  v21 = v15 + 5;
  v20[2] = (PSRWLOCK)SRWLock;
  Ptr = (RTL_SRWLOCK *)v21[1].Ptr;
  v20[1] = Ptr;
  *v20 = v21;
  Ptr->Ptr = v20;
  v21[1].Ptr = v20;
  ++v21[2].Ptr;
  v23 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 )
  {
    *(_DWORD *)(v23 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v23);
    *(_QWORD *)a3 = 0;
  }
  wil::slim_event_t<1>::wait(SRWLock);
  AcquireSRWLockExclusive((PSRWLOCK)a1[28].Data4);
  a1[29].Data1 = GetCurrentThreadId();
  if ( a3 == &v55 )
  {
    if ( a1 != (struct _GUID *)-456LL )
    {
      a1[29].Data1 = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)a1[28].Data4);
    }
  }
  else
  {
    v24 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      *(_DWORD *)(v24 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v24);
    }
    *(_QWORD *)a3 = (char *)a1 + 456;
  }
LABEL_33:
  v25 = (struct _GUID *)(a2 + 4);
  if ( *(_DWORD *)a2 == 1 )
  {
    if ( (struct _GUID *)utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(
                           &a1[35],
                           v25) != &a1[35] )
      goto LABEL_54;
    while ( a1[39].Data1 )
    {
      *(_DWORD *)(*(_QWORD *)a3 + 8LL) = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)a1[39].Data4, *(PSRWLOCK *)a3, 0xFFFFFFFF, 0);
      *(_DWORD *)(*(_QWORD *)a3 + 8LL) = GetCurrentThreadId();
    }
    v27 = 0;
    v53 = 0;
    v54 = 0;
    if ( LOBYTE(a1[9].Data1) )
    {
      *(_QWORD *)&v53 = *(_QWORD *)&a1[7].Data1;
      *((_QWORD *)&v53 + 1) = (__int64)(*(_QWORD *)a1[7].Data4 - v53) >> 1;
      LOBYTE(v54) = 1;
      v27 = v53;
    }
    v57 = v27;
    v58 = v54;
    v53 = 0;
    v54 = 0;
    v28 = Container::Manager::Core::Details::ContainerObject::AddNetworkInternal(a1, v13, (__int64)a3);
    v29 = retaddr;
    if ( v28 >= 0 )
      goto LABEL_54;
    v30 = 2979;
    goto LABEL_53;
  }
  if ( *(_DWORD *)a2 == 2 )
  {
    if ( (struct _GUID *)utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(
                           &a1[35],
                           v25) != &a1[35] )
    {
      ++a1[39].Data1;
      v31 = Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal(a1);
      if ( v31 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBB5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v31,
          v51);
      if ( a1[39].Data1-- == 1 )
        WakeAllConditionVariable((PCONDITION_VARIABLE)a1[39].Data4);
    }
    goto LABEL_54;
  }
  v28 = Container::Manager::Core::Details::ContainerObject::SynchronizeNetwork(a1, v25);
  v29 = retaddr;
  if ( v28 < 0 )
  {
    v30 = 3015;
LABEL_53:
    wil::details::in1diag3::_Log_Hr(
      v29,
      (void *)v30,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v28,
      v51);
  }
LABEL_54:
  v33 = a1 + 37;
  if ( *(struct _GUID **)&a1[38].Data1 != &a1[37] )
  {
    v34 = *(_QWORD *)v12;
    do
    {
      LODWORD(SRWLock[0]) = 0;
      if ( UuidCompare((UUID *)(v34 + 24), v13, (RPC_STATUS *)SRWLock) >= 0 )
      {
        v33 = (struct _GUID *)v34;
        v35 = 8;
      }
      else
      {
        v35 = 16;
      }
      v34 = *(_QWORD *)(v35 + v34);
    }
    while ( (_UNKNOWN *)v34 != &utl::_TreeSentinel );
    v12 = (unsigned __int64)&a1[37];
    if ( v33 != &a1[37] )
    {
      LODWORD(SRWLock[0]) = 0;
      if ( UuidCompare(v13, (struct _GUID *)((char *)v33 + 24), (RPC_STATUS *)SRWLock) < 0 )
        v33 = a1 + 37;
    }
  }
  Data4 = v33[2].Data4;
  v37 = *(_QWORD *)v33[2].Data4;
  if ( (unsigned __int8 *)v37 == v33[2].Data4 )
  {
    if ( *(_UNKNOWN **)&v33[1].Data1 != &utl::_TreeSentinel && v33 == *(struct _GUID **)&v33[1].Data1 )
      __int2c();
    utl::_TreeNodeHeader<Csl::Details::AsyncOperationImpl<void> *>::_HeadUnlinkNode(v12, v33);
    --*(_QWORD *)(v12 + 24);
    v38 = v33[2].Data4;
    while ( 1 )
    {
      v39 = *(__int64 **)v38;
      if ( *(unsigned __int8 **)v38 == v38 )
        break;
      v40 = (__int64 *)v39[1];
      v41 = *v39;
      *v40 = *v39;
      *(_QWORD *)(v41 + 8) = v40;
      operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
    }
    *(_QWORD *)v33[3].Data4 = 0;
    operator delete(v33, (const struct std::nothrow_t *)&std::nothrow);
  }
  else
  {
    v42 = *(_DWORD **)(v37 + 16);
    *v42 = 1;
    WakeByAddressAll(v42);
    v43 = *(_QWORD **)Data4;
    v44 = *(_QWORD **)(*(_QWORD *)Data4 + 8LL);
    v45 = **(_QWORD **)Data4;
    *v44 = v45;
    *(_QWORD *)(v45 + 8) = v44;
    operator delete(v43, (const struct std::nothrow_t *)&std::nothrow);
    --*(_QWORD *)v33[3].Data4;
  }
LABEL_74:
  if ( v6 )
  {
    if ( ++*(_DWORD *)(v6 + 4) == *(_DWORD *)v6 )
    {
      v46 = *(PSRWLOCK *)a3;
      if ( *(_QWORD *)a3 )
      {
        LODWORD(v46[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v46);
        *(_QWORD *)a3 = 0;
      }
      updated = Container::Manager::Hns::UpdateMirroredNetworkingState(a1);
      if ( updated < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBF3,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)updated,
          v51);
      v48 = a1[28].Data4;
      AcquireSRWLockExclusive((PSRWLOCK)v48);
      *((_DWORD *)v48 + 2) = GetCurrentThreadId();
      if ( a3 == &v56 )
      {
        if ( v48 )
        {
          *((_DWORD *)v48 + 2) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v48);
        }
      }
      else
      {
        v49 = *(PSRWLOCK *)a3;
        if ( *(_QWORD *)a3 )
        {
          LODWORD(v49[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v49);
        }
        *(_QWORD *)a3 = v48;
      }
      if ( *(_DWORD *)(v6 + 24) )
      {
        v50 = v6 + 48;
        if ( *(_DWORD *)(v6 + 24) != 3 )
          v50 = v6 + 392;
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v50,
          0);
      }
    }
  }
}

```

## disassembly

```asm
0x1800ab1c4  mov     [rsp-8+arg_18], rbx
0x1800ab1c9  push    rbp
0x1800ab1ca  push    rsi
0x1800ab1cb  push    rdi
0x1800ab1cc  push    r12
0x1800ab1ce  push    r13
0x1800ab1d0  push    r14
0x1800ab1d2  push    r15
0x1800ab1d4  lea     rbp, [rsp-390h]
0x1800ab1dc  sub     rsp, 490h
0x1800ab1e3  mov     rax, cs:__security_cookie
0x1800ab1ea  xor     rax, rsp
0x1800ab1ed  mov     [rbp+3C0h+var_40], rax
0x1800ab1f4  mov     r15, r8
0x1800ab1f7  mov     r13, rdx
0x1800ab1fa  mov     rsi, rcx
0x1800ab1fd  mov     rdi, [rdx+18h]
0x1800ab201  xor     r14d, r14d
0x1800ab204  test    rdi, rdi
0x1800ab207  jz      loc_1800AB3F8
0x1800ab20d  cmp     [rdi+18h], r14d
0x1800ab211  jz      loc_1800AB3F8
0x1800ab217  cmp     dword ptr [rdi+18h], 3
0x1800ab21b  jnz     loc_1800AB2A9
0x1800ab221  cmp     [rdi+180h], r14b
0x1800ab228  jnz     loc_1800AB3F8
0x1800ab22e  lea     rdx, aCreatecontaine_4; "CreateContainerStateTransition_MirrorNe"...
0x1800ab235  lea     rcx, [rbp+3C0h+var_430]
0x1800ab239  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800ab23e  lea     r12, ??_7CreateContainerStateTransition_MirrorNetworks@CmTraceProvider@@6B@; const CmTraceProvider::CreateContainerStateTransition_MirrorNetworks::`vftable'
0x1800ab245  mov     [rbp+3C0h+var_430], r12
0x1800ab249  lea     rdx, [rsp+4C0h+SRWLock]
0x1800ab24e  lea     rcx, [rbp+3C0h+var_430]
0x1800ab252  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800ab257  mov     rax, [rbp+3C0h+var_320]
0x1800ab25e  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800ab262  movdqu  xmmword ptr [rax+18h], xmm0
0x1800ab267  mov     byte ptr [rax+4], 1
0x1800ab26b  mov     rcx, [rsp+4C0h+SRWLock]; SRWLock
0x1800ab270  test    rcx, rcx
0x1800ab273  jz      short loc_1800AB281
0x1800ab275  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ab27c  nop     dword ptr [rax+rax+00h]
0x1800ab281  mov     edx, [rdi+8]; unsigned int
0x1800ab284  lea     rcx, [rbp+3C0h+var_430]; this
0x1800ab288  call    ?StartActivity@CreateContainerStateTransition_MirrorNetworks@CmTraceProvider@@QEAAXK@Z; CmTraceProvider::CreateContainerStateTransition_MirrorNetworks::StartActivity(ulong)
0x1800ab28d  xor     r8d, r8d
0x1800ab290  lea     rdx, [rbp+3C0h+var_430]
0x1800ab294  lea     rcx, [rbp+3C0h+var_2E0]
0x1800ab29b  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800ab2a0  lea     rbx, [rdi+30h]
0x1800ab2a4  jmp     loc_1800AB33E
0x1800ab2a9  cmp     [rdi+2D8h], r14b
0x1800ab2b0  jnz     loc_1800AB3F8
0x1800ab2b6  lea     rdx, aResumecontaine_0; "ResumeContainerStateTransition_MirrorNe"...
0x1800ab2bd  lea     rcx, [rbp+3C0h+var_430]
0x1800ab2c1  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800ab2c6  lea     r12, ??_7ResumeContainerStateTransition_MirrorNetworks@CmTraceProvider@@6B@; const CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks::`vftable'
0x1800ab2cd  mov     [rbp+3C0h+var_430], r12
0x1800ab2d1  lea     rdx, [rsp+4C0h+SRWLock]
0x1800ab2d6  lea     rcx, [rbp+3C0h+var_430]
0x1800ab2da  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800ab2df  mov     rax, [rbp+3C0h+var_320]
0x1800ab2e6  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800ab2ea  movdqu  xmmword ptr [rax+18h], xmm0
0x1800ab2ef  mov     byte ptr [rax+4], 1
0x1800ab2f3  mov     rcx, [rsp+4C0h+SRWLock]; SRWLock
0x1800ab2f8  test    rcx, rcx
0x1800ab2fb  jz      short loc_1800AB309
0x1800ab2fd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ab304  nop     dword ptr [rax+rax+00h]
0x1800ab309  mov     eax, [rdi+14h]
0x1800ab30c  mov     [rsp+4C0h+var_4A0], eax; int
0x1800ab310  mov     r9d, [rdi+10h]; unsigned int
0x1800ab314  mov     r8d, [rdi+0Ch]; unsigned int
0x1800ab318  mov     edx, [rdi+8]; unsigned int
0x1800ab31b  lea     rcx, [rbp+3C0h+var_430]; this
0x1800ab31f  call    ?StartActivity@ResumeContainerStateTransition_MirrorNetworks@CmTraceProvider@@QEAAXKKKK@Z; CmTraceProvider::ResumeContainerStateTransition_MirrorNetworks::StartActivity(ulong,ulong,ulong,ulong)
0x1800ab324  xor     r8d, r8d
0x1800ab327  lea     rdx, [rbp+3C0h+var_430]
0x1800ab32b  lea     rcx, [rbp+3C0h+var_2E0]
0x1800ab332  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800ab337  lea     rbx, [rdi+188h]
0x1800ab33e  mov     [rbp+3C0h+var_2E0], r12
0x1800ab345  cmp     [rbx+150h], r14b
0x1800ab34c  jz      short loc_1800AB39F
0x1800ab34e  cmp     [rbx+138h], r14d
0x1800ab355  setnz   r8b
0x1800ab359  mov     rdx, rbx
0x1800ab35c  lea     rcx, [rbp+3C0h+var_190]
0x1800ab363  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800ab368  mov     [rbp+3C0h+var_190], r12
0x1800ab36f  lea     rdx, [rbp+3C0h+var_2E0]
0x1800ab376  mov     rcx, rbx
0x1800ab379  call    ??4?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x1800ab37e  mov     [rbp+3C0h+var_190], r12
0x1800ab385  lea     rcx, [rbp+3C0h+var_190]
0x1800ab38c  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800ab391  lea     rcx, [rbp+3C0h+var_190]
0x1800ab398  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800ab39d  jmp     short loc_1800AB3C3
0x1800ab39f  cmp     [rbp+3C0h+var_1A8], r14d
0x1800ab3a6  setnz   r8b
0x1800ab3aa  lea     rdx, [rbp+3C0h+var_2E0]
0x1800ab3b1  mov     rcx, rbx
0x1800ab3b4  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x1800ab3b9  mov     [rbx], r12
0x1800ab3bc  mov     byte ptr [rbx+150h], 1
0x1800ab3c3  mov     [rbp+3C0h+var_2E0], r12
0x1800ab3ca  lea     rcx, [rbp+3C0h+var_2E0]
0x1800ab3d1  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800ab3d6  lea     rcx, [rbp+3C0h+var_2E0]
0x1800ab3dd  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800ab3e2  mov     [rbp+3C0h+var_430], r12
0x1800ab3e6  lea     rcx, [rbp+3C0h+var_430]
0x1800ab3ea  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800ab3ef  lea     rcx, [rbp+3C0h+var_430]
0x1800ab3f3  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800ab3f8  lea     r14, [rsi+250h]
0x1800ab3ff  lea     r12, [r13+4]
0x1800ab403  cmp     [r14+10h], r14
0x1800ab407  jnz     short loc_1800AB46D
0x1800ab409  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab410  mov     ecx, 40h ; '@'; unsigned __int64
0x1800ab415  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ab41a  mov     rbx, rax
0x1800ab41d  test    rax, rax
0x1800ab420  jz      loc_1800AB4E6
0x1800ab426  movups  xmm0, xmmword ptr [r12]
0x1800ab42b  movdqu  xmmword ptr [rax+18h], xmm0
0x1800ab430  add     rax, 28h ; '('
0x1800ab434  mov     [rax], rax
0x1800ab437  mov     [rax+8], rax
0x1800ab43b  mov     qword ptr [rax+10h], 0
0x1800ab443  mov     rax, r14
0x1800ab446  or      rax, 1
0x1800ab44a  mov     [rbx], rax
0x1800ab44d  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800ab454  mov     [rbx+8], rcx
0x1800ab458  mov     [rbx+10h], rcx
0x1800ab45c  mov     [r14], rbx
0x1800ab45f  mov     [r14+8], rbx
0x1800ab463  mov     [r14+10h], rbx
0x1800ab467  inc     qword ptr [r14+18h]
0x1800ab46b  jmp     short loc_1800AB4E2
0x1800ab46d  mov     [rsp+4C0h+SRWLock], 0
0x1800ab476  mov     r9, r12
0x1800ab479  lea     r8, [rsp+4C0h+SRWLock]
0x1800ab47e  lea     rdx, [rsp+4C0h+var_480]
0x1800ab483  mov     rcx, r14
0x1800ab486  call    ?_FindInsertionPointUniqueUpper@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UMaterializeContext@DeploymentManager@Details@Core@Manager@Container@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UMaterializeContext@DeploymentManager@Details@Core@Manager@Container@@@utl@@@3@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@UMaterializeContext@DeploymentManager@Details@Core@Manager@Container@@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@UMaterializeContext@DeploymentManager@Details@Core@Manager@Container@@@utl@@@2@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,Container::Manager::Core::Details::DeploymentManager::MaterializeContext>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,Container::Manager::Core::Details::DeploymentManager::MaterializeContext>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Core::Details::DeploymentManager::MaterializeContext>> * &,_GUID const &)
0x1800ab48b  movups  xmm0, xmmword ptr [rax]
0x1800ab48e  movdqu  [rsp+4C0h+var_480], xmm0
0x1800ab494  mov     rbx, [rsp+4C0h+SRWLock]
0x1800ab499  test    rbx, rbx
0x1800ab49c  jnz     short loc_1800AB4E6
0x1800ab49e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab4a5  lea     ecx, [rbx+40h]; unsigned __int64
0x1800ab4a8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ab4ad  mov     rbx, rax
0x1800ab4b0  test    rax, rax
0x1800ab4b3  jz      short loc_1800AB4E6
0x1800ab4b5  movups  xmm0, xmmword ptr [r12]
0x1800ab4ba  movdqu  xmmword ptr [rax+18h], xmm0
0x1800ab4bf  add     rax, 28h ; '('
0x1800ab4c3  mov     [rax], rax
0x1800ab4c6  mov     [rax+8], rax
0x1800ab4ca  mov     qword ptr [rax+10h], 0
0x1800ab4d2  mov     r8, rbx
0x1800ab4d5  lea     rdx, [rsp+4C0h+var_480]
0x1800ab4da  mov     rcx, r14
0x1800ab4dd  call    ?_InsertAt@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@3@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *,bool> const &,utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *)
0x1800ab4e2  mov     al, 1
0x1800ab4e4  jmp     short loc_1800AB4E8
0x1800ab4e6  xor     al, al
0x1800ab4e8  test    rbx, rbx
0x1800ab4eb  jz      loc_1800AB898
0x1800ab4f1  test    al, al
0x1800ab4f3  jnz     loc_1800AB5B7
0x1800ab4f9  mov     dword ptr [rsp+4C0h+SRWLock], 0
0x1800ab501  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab508  mov     ecx, 18h; unsigned __int64
0x1800ab50d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ab512  test    rax, rax
0x1800ab515  jz      loc_1800AB5FF
0x1800ab51b  add     rbx, 28h ; '('
0x1800ab51f  lea     rcx, [rsp+4C0h+SRWLock]
0x1800ab524  mov     [rax+10h], rcx
0x1800ab528  mov     rcx, [rbx+8]
0x1800ab52c  mov     [rax+8], rcx
0x1800ab530  mov     [rax], rbx
0x1800ab533  mov     [rcx], rax
0x1800ab536  mov     [rbx+8], rax
0x1800ab53a  inc     qword ptr [rbx+10h]
0x1800ab53e  mov     rcx, [r15]; SRWLock
0x1800ab541  test    rcx, rcx
0x1800ab544  jz      short loc_1800AB560
0x1800ab546  mov     dword ptr [rcx+8], 0
0x1800ab54d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ab554  nop     dword ptr [rax+rax+00h]
0x1800ab559  mov     qword ptr [r15], 0
0x1800ab560  lea     rcx, [rsp+4C0h+SRWLock]; Address
0x1800ab565  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800ab56a  lea     rbx, [rsi+1C8h]
0x1800ab571  mov     rcx, rbx; SRWLock
0x1800ab574  call    cs:__imp_AcquireSRWLockExclusive
0x1800ab57b  nop     dword ptr [rax+rax+00h]
0x1800ab580  call    cs:__imp_GetCurrentThreadId
0x1800ab587  nop     dword ptr [rax+rax+00h]
0x1800ab58c  mov     [rbx+8], eax
0x1800ab58f  lea     rax, [rsp+4C0h+var_460]
0x1800ab594  cmp     r15, rax
0x1800ab597  jz      short loc_1800AB5E2
0x1800ab599  mov     rcx, [r15]; SRWLock
0x1800ab59c  test    rcx, rcx
0x1800ab59f  jz      short loc_1800AB5B4
0x1800ab5a1  mov     dword ptr [rcx+8], 0
0x1800ab5a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ab5af  nop     dword ptr [rax+rax+00h]
0x1800ab5b4  mov     [r15], rbx
0x1800ab5b7  mov     rdx, r12; struct _GUID *
0x1800ab5ba  cmp     dword ptr [r13+0], 1
0x1800ab5bf  jnz     loc_1800AB6D4
0x1800ab5c5  lea     rbx, [rsi+230h]
0x1800ab5cc  mov     rcx, rbx
0x1800ab5cf  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x1800ab5d4  cmp     rax, rbx
0x1800ab5d7  jnz     loc_1800AB76A
0x1800ab5dd  xor     r13d, r13d
0x1800ab5e0  jmp     short loc_1800AB63F
0x1800ab5e2  test    rbx, rbx
0x1800ab5e5  jz      short loc_1800AB5B7
0x1800ab5e7  mov     dword ptr [rbx+8], 0
0x1800ab5ee  mov     rcx, rbx; SRWLock
0x1800ab5f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ab5f8  nop     dword ptr [rax+rax+00h]
0x1800ab5fd  jmp     short loc_1800AB5B7
0x1800ab5ff  mov     edx, 0B7Dh
0x1800ab604  jmp     loc_1800AB89D
0x1800ab609  mov     rax, [r15]
0x1800ab60c  mov     [rax+8], r13d
0x1800ab610  xor     r9d, r9d; Flags
0x1800ab613  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800ab617  mov     rdx, [r15]; SRWLock
0x1800ab61a  lea     rcx, [rsi+278h]; ConditionVariable
0x1800ab621  call    cs:__imp_SleepConditionVariableSRW
0x1800ab628  nop     dword ptr [rax+rax+00h]
0x1800ab62d  call    cs:__imp_GetCurrentThreadId
0x1800ab634  nop     dword ptr [rax+rax+00h]
0x1800ab639  mov     rcx, [r15]
0x1800ab63c  mov     [rcx+8], eax
0x1800ab63f  cmp     [rsi+270h], r13d
0x1800ab646  ja      short loc_1800AB609
0x1800ab648  xorps   xmm0, xmm0
0x1800ab64b  xor     eax, eax
0x1800ab64d  movups  [rsp+4C0h+var_480], xmm0
0x1800ab652  mov     [rsp+4C0h+var_470], rax
0x1800ab657  cmp     [rsi+90h], r13b
0x1800ab65e  jz      short loc_1800AB682
0x1800ab660  mov     rax, [rsi+70h]
0x1800ab664  mov     qword ptr [rsp+4C0h+var_480], rax
0x1800ab669  mov     rcx, [rsi+78h]
0x1800ab66d  sub     rcx, rax
0x1800ab670  sar     rcx, 1
0x1800ab673  mov     qword ptr [rsp+4C0h+var_480+8], rcx
0x1800ab678  mov     byte ptr [rsp+4C0h+var_470], 1
0x1800ab67d  movups  xmm0, [rsp+4C0h+var_480]
0x1800ab682  xorps   xmm1, xmm1
0x1800ab685  xor     eax, eax
0x1800ab687  movaps  [rsp+4C0h+var_450], xmm0
0x1800ab68c  movsd   xmm0, [rsp+4C0h+var_470]
0x1800ab692  movsd   [rbp+3C0h+var_440], xmm0
0x1800ab697  movaps  [rsp+4C0h+var_480], xmm1
0x1800ab69c  mov     [rsp+4C0h+var_470], rax
0x1800ab6a1  mov     qword ptr [rsp+4C0h+var_4A0], r15; __int64
0x1800ab6a6  lea     r9, [rsp+4C0h+var_450]
0x1800ab6ab  lea     r8, [rsp+4C0h+var_480]
0x1800ab6b0  mov     rdx, r12; struct _GUID *
0x1800ab6b3  mov     rcx, rsi; struct _GUID *
0x1800ab6b6  call    ?AddNetworkInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@V?$optional@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@utl@@1AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AddNetworkInternal(_GUID const &,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800ab6bb  mov     rcx, [rbp+3C8h]
0x1800ab6c2  test    eax, eax
0x1800ab6c4  jns     loc_1800AB76A
0x1800ab6ca  mov     edx, 0BA3h
0x1800ab6cf  jmp     loc_1800AB75B
0x1800ab6d4  cmp     dword ptr [r13+0], 2
0x1800ab6d9  jnz     short loc_1800AB740
0x1800ab6db  lea     rbx, [rsi+230h]
0x1800ab6e2  mov     rcx, rbx
0x1800ab6e5  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x1800ab6ea  cmp     rax, rbx
0x1800ab6ed  jz      short loc_1800AB76A
0x1800ab6ef  inc     dword ptr [rsi+270h]
0x1800ab6f5  mov     r8, r15
0x1800ab6f8  mov     rdx, r12
0x1800ab6fb  mov     rcx, rsi; this
0x1800ab6fe  call    ?RemoveNetworkInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal(_GUID const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800ab703  mov     rcx, [rbp+3C8h]; this
0x1800ab70a  test    eax, eax
0x1800ab70c  jns     short loc_1800AB722
  ... truncated ...
```
