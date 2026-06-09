# Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal(_GUID const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800ad22c`
- end: `0x1800ad4d8`
- name: `?RemoveNetworkInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(struct _GUID *this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x18001d940`
- `0x1800ab1c4`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x18000dad8`
- `0x1800483d4`
- `0x1800492f0`
- `0x18006931c`
- `0x18009b018`
- `0x1800ac950`
- `0x1800acc84`
- `0x1800ad22c`
- `0x1800ad4e0`
- `0x18018753c`
- `0x180198574`
- `0x180198604`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ad377`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800ad377`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ad29d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800ad29d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad30d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad44c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad30d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad44c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad2e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad33e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad35b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad418`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad47d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad49a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad2e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad33e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad35b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad418`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad47d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad49a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad2a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad458`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad2a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad458`

## pseudocode

```c
int __fastcall Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal(
        struct _GUID *this,
        __int64 a2,
        PSRWLOCK *a3)
{
  struct _GUID *v4; // r15
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // eax
  PSRWLOCK v10; // rcx
  unsigned __int8 *Data4; // rdi
  int v12; // ebp
  PSRWLOCK v13; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rbx
  __int64 v18; // rbp
  __int64 v19; // r14
  PSRWLOCK v20; // rcx
  PSRWLOCK v21; // rcx
  unsigned int v22; // [rsp+20h] [rbp-58h] BYREF
  char v23; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v25; // [rsp+80h] [rbp+8h] BYREF

  v4 = this + 35;
  while ( 1 )
  {
    v7 = utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(v4, a2);
    if ( (struct _GUID *)v7 == v4 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x84E,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
               (const char *)0x490,
               v22);
    v8 = *(_QWORD *)(v7 + 40);
    v9 = *(_DWORD *)(v8 + 104);
    if ( (v9 & 1) == 0 )
      break;
    v25 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v8 + 120),
      (struct Csl::RundownProtection *)&v25);
    LODWORD((*a3)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v8 + 112), *a3, 0xFFFFFFFF, 0);
    LODWORD((*a3)[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v25);
  }
  *(_DWORD *)(v8 + 104) = v9 | 1;
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(this, a3);
  v10 = *a3;
  if ( *a3 )
  {
    LODWORD(v10[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v10);
    *a3 = 0;
  }
  Data4 = this[28].Data4;
  v12 = Container::Manager::Core::Details::ContainerObject::RemoveNetworkImpl(this, (struct _GUID *)v8);
  AcquireSRWLockExclusive((PSRWLOCK)this[28].Data4);
  this[29].Data1 = GetCurrentThreadId();
  if ( a3 == (PSRWLOCK *)&v22 )
  {
    if ( this != (struct _GUID *)-456LL )
    {
      this[29].Data1 = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this[28].Data4);
    }
  }
  else
  {
    v13 = *a3;
    if ( *a3 )
    {
      LODWORD(v13[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v13);
    }
    *a3 = (PSRWLOCK)Data4;
  }
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)this);
  *(_DWORD *)(v8 + 104) &= ~1u;
  WakeAllConditionVariable((PCONDITION_VARIABLE)(v8 + 112));
  if ( v12 >= 0 )
  {
    v15 = utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(v4, a2);
    LOBYTE(v16) = 1;
    v17 = (_QWORD *)v15;
    v18 = *(_QWORD *)(v15 + 40);
    *(_QWORD *)(v15 + 40) = 0;
    utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(
      v15,
      v16);
    utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(
      v4,
      v17);
    --*(_QWORD *)v4[1].Data4;
    v19 = v17[5];
    v17[5] = 0;
    if ( v19 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)(v19 + 16));
      operator delete((void *)v19, (const struct std::nothrow_t *)0x88);
    }
    operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
    v20 = *a3;
    if ( *a3 )
    {
      LODWORD(v20[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v20);
      *a3 = 0;
    }
    Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v18 + 120));
    if ( v18 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)(v18 + 16));
      operator delete((void *)v18, (const struct std::nothrow_t *)0x88);
    }
    AcquireSRWLockExclusive((PSRWLOCK)Data4);
    *((_DWORD *)Data4 + 2) = GetCurrentThreadId();
    if ( a3 == (PSRWLOCK *)&v23 )
    {
      if ( Data4 )
      {
        *((_DWORD *)Data4 + 2) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)Data4);
      }
    }
    else
    {
      v21 = *a3;
      if ( *a3 )
      {
        LODWORD(v21[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v21);
      }
      *a3 = (PSRWLOCK)Data4;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v12,
      v22);
    return v12;
  }
}

```

## disassembly

```asm
0x1800ad22c  push    rbx
0x1800ad22e  push    rbp
0x1800ad22f  push    rsi
0x1800ad230  push    rdi
0x1800ad231  push    r12
0x1800ad233  push    r13
0x1800ad235  push    r14
0x1800ad237  push    r15
0x1800ad239  sub     rsp, 38h
0x1800ad23d  mov     rsi, r8
0x1800ad240  lea     r15, [rcx+230h]
0x1800ad247  mov     r12, rdx
0x1800ad24a  mov     r14, rcx
0x1800ad24d  xor     r13d, r13d
0x1800ad250  mov     rdx, r12
0x1800ad253  mov     rcx, r15
0x1800ad256  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x1800ad25b  cmp     rax, r15
0x1800ad25e  jz      loc_1800AD4AA
0x1800ad264  mov     rbx, [rax+28h]
0x1800ad268  mov     eax, [rbx+68h]
0x1800ad26b  test    al, 1
0x1800ad26d  jz      short loc_1800AD2CA
0x1800ad26f  lea     rcx, [rbx+78h]; this
0x1800ad273  mov     [rsp+78h+arg_0], r13
0x1800ad27b  lea     rdx, [rsp+78h+arg_0]; struct Csl::RundownProtection *
0x1800ad283  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800ad288  mov     rax, [rsi]
0x1800ad28b  lea     rcx, [rbx+70h]; ConditionVariable
0x1800ad28f  xor     r9d, r9d; Flags
0x1800ad292  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800ad296  mov     [rax+8], r13d
0x1800ad29a  mov     rdx, [rsi]; SRWLock
0x1800ad29d  call    cs:__imp_SleepConditionVariableSRW
0x1800ad2a4  nop     dword ptr [rax+rax+00h]
0x1800ad2a9  call    cs:__imp_GetCurrentThreadId
0x1800ad2b0  nop     dword ptr [rax+rax+00h]
0x1800ad2b5  mov     rcx, [rsi]
0x1800ad2b8  mov     [rcx+8], eax
0x1800ad2bb  lea     rcx, [rsp+78h+arg_0]; this
0x1800ad2c3  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800ad2c8  jmp     short loc_1800AD250
0x1800ad2ca  or      eax, 1
0x1800ad2cd  mov     rdx, rsi
0x1800ad2d0  mov     rcx, r14
0x1800ad2d3  mov     [rbx+68h], eax
0x1800ad2d6  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800ad2db  mov     rcx, [rsi]; SRWLock
0x1800ad2de  test    rcx, rcx
0x1800ad2e1  jz      short loc_1800AD2F6
0x1800ad2e3  mov     [rcx+8], r13d
0x1800ad2e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad2ee  nop     dword ptr [rax+rax+00h]
0x1800ad2f3  mov     [rsi], r13
0x1800ad2f6  mov     rdx, rbx; struct _GUID *
0x1800ad2f9  mov     rcx, r14; this
0x1800ad2fc  call    ?RemoveNetworkImpl@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAUMappedNetwork@12345@@Z; Container::Manager::Core::Details::ContainerObject::RemoveNetworkImpl(Container::Manager::Core::Details::ContainerObject::MappedNetwork &)
0x1800ad301  lea     rdi, [r14+1C8h]
0x1800ad308  mov     ebp, eax
0x1800ad30a  mov     rcx, rdi; SRWLock
0x1800ad30d  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad314  nop     dword ptr [rax+rax+00h]
0x1800ad319  call    cs:__imp_GetCurrentThreadId
0x1800ad320  nop     dword ptr [rax+rax+00h]
0x1800ad325  mov     [rdi+8], eax
0x1800ad328  lea     rax, [rsp+78h+var_58]
0x1800ad32d  cmp     rsi, rax
0x1800ad330  jz      short loc_1800AD34F
0x1800ad332  mov     rcx, [rsi]; SRWLock
0x1800ad335  test    rcx, rcx
0x1800ad338  jz      short loc_1800AD34A
0x1800ad33a  mov     [rcx+8], r13d
0x1800ad33e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad345  nop     dword ptr [rax+rax+00h]
0x1800ad34a  mov     [rsi], rdi
0x1800ad34d  jmp     short loc_1800AD367
0x1800ad34f  test    rdi, rdi
0x1800ad352  jz      short loc_1800AD367
0x1800ad354  mov     rcx, rdi; SRWLock
0x1800ad357  mov     [rdi+8], r13d
0x1800ad35b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad362  nop     dword ptr [rax+rax+00h]
0x1800ad367  mov     rcx, r14; this
0x1800ad36a  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x1800ad36f  and     dword ptr [rbx+68h], 0FFFFFFFEh
0x1800ad373  lea     rcx, [rbx+70h]; ConditionVariable
0x1800ad377  call    cs:__imp_WakeAllConditionVariable
0x1800ad37e  nop     dword ptr [rax+rax+00h]
0x1800ad383  test    ebp, ebp
0x1800ad385  jns     short loc_1800AD3A7
0x1800ad387  mov     rcx, [rsp+78h]; this
0x1800ad38c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ad393  mov     r9d, ebp; char *
0x1800ad396  mov     edx, 87Dh; void *
0x1800ad39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad3a0  mov     eax, ebp
0x1800ad3a2  jmp     loc_1800AD4C6
0x1800ad3a7  mov     rdx, r12
0x1800ad3aa  mov     rcx, r15
0x1800ad3ad  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x1800ad3b2  mov     dl, 1
0x1800ad3b4  mov     rcx, rax
0x1800ad3b7  mov     rbx, rax
0x1800ad3ba  mov     rbp, [rax+28h]
0x1800ad3be  mov     [rax+28h], r13
0x1800ad3c2  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(bool)
0x1800ad3c7  mov     rdx, rbx
0x1800ad3ca  mov     rcx, r15
0x1800ad3cd  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>> *)
0x1800ad3d2  dec     qword ptr [r15+18h]
0x1800ad3d6  mov     r15d, 88h
0x1800ad3dc  mov     r14, [rbx+28h]
0x1800ad3e0  mov     [rbx+28h], r13
0x1800ad3e4  test    r14, r14
0x1800ad3e7  jz      short loc_1800AD3FD
0x1800ad3e9  lea     rcx, [r14+10h]; this
0x1800ad3ed  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x1800ad3f2  mov     edx, r15d; struct std::nothrow_t *
0x1800ad3f5  mov     rcx, r14; void *
0x1800ad3f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad3fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ad404  mov     rcx, rbx; void *
0x1800ad407  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad40c  mov     rcx, [rsi]; SRWLock
0x1800ad40f  test    rcx, rcx
0x1800ad412  jz      short loc_1800AD427
0x1800ad414  mov     [rcx+8], r13d
0x1800ad418  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad41f  nop     dword ptr [rax+rax+00h]
0x1800ad424  mov     [rsi], r13
0x1800ad427  lea     rcx, [rbp+78h]; this
0x1800ad42b  call    ?WaitForRundownProtectionRelease@RundownReference@Csl@@QEAAXXZ; Csl::RundownReference::WaitForRundownProtectionRelease(void)
0x1800ad430  test    rbp, rbp
0x1800ad433  jz      short loc_1800AD449
0x1800ad435  lea     rcx, [rbp+10h]; this
0x1800ad439  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x1800ad43e  mov     rdx, r15; struct std::nothrow_t *
0x1800ad441  mov     rcx, rbp; void *
0x1800ad444  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad449  mov     rcx, rdi; SRWLock
0x1800ad44c  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad453  nop     dword ptr [rax+rax+00h]
0x1800ad458  call    cs:__imp_GetCurrentThreadId
0x1800ad45f  nop     dword ptr [rax+rax+00h]
0x1800ad464  mov     [rdi+8], eax
0x1800ad467  lea     rax, [rsp+78h+var_50]
0x1800ad46c  cmp     rsi, rax
0x1800ad46f  jz      short loc_1800AD48E
0x1800ad471  mov     rcx, [rsi]; SRWLock
0x1800ad474  test    rcx, rcx
0x1800ad477  jz      short loc_1800AD489
0x1800ad479  mov     [rcx+8], r13d
0x1800ad47d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad484  nop     dword ptr [rax+rax+00h]
0x1800ad489  mov     [rsi], rdi
0x1800ad48c  jmp     short loc_1800AD4A6
0x1800ad48e  test    rdi, rdi
0x1800ad491  jz      short loc_1800AD4A6
0x1800ad493  mov     rcx, rdi; SRWLock
0x1800ad496  mov     [rdi+8], r13d
0x1800ad49a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad4a1  nop     dword ptr [rax+rax+00h]
0x1800ad4a6  xor     eax, eax
0x1800ad4a8  jmp     short loc_1800AD4C6
0x1800ad4aa  mov     rcx, [rsp+78h]; this
0x1800ad4af  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ad4b6  mov     r9d, 490h; char *
0x1800ad4bc  mov     edx, 84Eh; void *
0x1800ad4c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ad4c6  add     rsp, 38h
0x1800ad4ca  pop     r15
0x1800ad4cc  pop     r14
0x1800ad4ce  pop     r13
0x1800ad4d0  pop     r12
0x1800ad4d2  pop     rdi
0x1800ad4d3  pop     rsi
0x1800ad4d4  pop     rbp
0x1800ad4d5  pop     rbx
0x1800ad4d6  retn
```
