# Container::Manager::Core::Details::ContainerObject::AddNetworkInternal(_GUID const &,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x18009bcc4`
- end: `0x18009c126`
- name: `?AddNetworkInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@V?$optional@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@utl@@1AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `1122`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct _GUID *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x18009b5cc`
- `0x1800ab1c4`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x1800483d4`
- `0x1800492f0`
- `0x18006931c`
- `0x180098914`
- `0x18009b018`
- `0x18009b778`
- `0x18009bcc4`
- `0x1800ac950`
- `0x1800ad4e0`
- `0x1801873cc`
- `0x180198404`
- `0x180198494`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18009bf5c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18009bf5c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009bdb6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009bdb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009beed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009c047`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009beed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009c047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009be8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009bf20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009bf40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c011`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c094`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009be8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009bf20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009bf40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c011`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009c094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c053`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::AddNetworkInternal(
        struct _GUID *a1,
        struct _GUID *a2,
        __int128 *a3,
        __int128 *a4,
        PSRWLOCK *a5)
{
  struct _GUID *v8; // rax
  struct _GUID *v9; // rsi
  struct _GUID v10; // xmm0
  struct _GUID *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // ebx
  struct _GUID *v15; // rcx
  struct _GUID *v16; // rdi
  __int64 v17; // rsi
  PSRWLOCK v18; // rcx
  __int64 v19; // xmm1_8
  __int64 v20; // xmm1_8
  unsigned __int8 *Data4; // rbx
  int v22; // r12d
  PSRWLOCK v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  const char *v26; // r9
  _QWORD *v27; // rsi
  char *v28; // r13
  __int64 v29; // r15
  __int64 v30; // r14
  PSRWLOCK v31; // rcx
  PSRWLOCK v32; // rcx
  void *v34; // rbx
  unsigned int v35; // [rsp+20h] [rbp-61h]
  int v36; // [rsp+20h] [rbp-61h]
  void *v37; // [rsp+30h] [rbp-51h] BYREF
  __int128 v38; // [rsp+40h] [rbp-41h] BYREF
  __int64 v39; // [rsp+50h] [rbp-31h]
  char v40; // [rsp+60h] [rbp-21h] BYREF
  char v41; // [rsp+68h] [rbp-19h] BYREF
  __int128 v42; // [rsp+70h] [rbp-11h]
  __int64 v43; // [rsp+80h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v8 = (struct _GUID *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x698,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v35);
    return v14;
  }
  v10 = *a2;
  v37 = v8;
  v11 = a1 + 35;
  *v8 = v10;
  v8[1] = GUID_NULL;
  v8[2] = GUID_NULL;
  LOBYTE(v8[4].Data1) = 1;
  *(_DWORD *)&v8[4].Data2 = 0;
  v8[3] = GUID_NULL;
  *(_QWORD *)v8[4].Data4 = (char *)v8 + 88;
  *(_QWORD *)&v8[5].Data1 = (char *)v8 + 88;
  *(_WORD *)v8[5].Data4 = 0;
  *(_QWORD *)&v8[7].Data1 = 0;
  *(_QWORD *)v8[7].Data4 = 0;
  v8[8].Data1 = 0;
  *(_DWORD *)v8[6].Data4 = 0;
  while ( 1 )
  {
    v12 = utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(&a1[35], a2);
    if ( (struct _GUID *)v12 == v11 )
      break;
    v13 = *(_QWORD *)(v12 + 40);
    if ( (*(_BYTE *)(v13 + 104) & 1) == 0 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6BB,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)0xB7,
              v35);
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)&v9[1]);
      v15 = v9;
LABEL_7:
      operator delete(v15, (const struct std::nothrow_t *)0x88);
      return v14;
    }
    *(_QWORD *)&v38 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v13 + 120),
      (struct Csl::RundownProtection *)&v38);
    LODWORD((*a5)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v13 + 112), *a5, 0xFFFFFFFF, 0);
    LODWORD((*a5)[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v38);
  }
  utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>>>,0>::emplace<_GUID const &,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>,0>(
    &a1[35],
    &v38,
    a2,
    &v37);
  if ( !(_QWORD)v38 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v35);
    v16 = (struct _GUID *)v37;
    if ( v37 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)((char *)v37 + 16));
      v15 = v16;
      goto LABEL_7;
    }
    return v14;
  }
  v17 = *(_QWORD *)(v38 + 40);
  *(_DWORD *)(v17 + 104) |= 1u;
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(a1, a5);
  v18 = *a5;
  if ( *a5 )
  {
    LODWORD(v18[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v18);
    *a5 = 0;
  }
  v19 = *((_QWORD *)a4 + 2);
  v38 = *a4;
  v39 = v19;
  v20 = *((_QWORD *)a3 + 2);
  v42 = *a3;
  v43 = v20;
  Data4 = a1[28].Data4;
  v22 = Container::Manager::Core::Details::ContainerObject::AddNetworkImpl(a1, a2, v17 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)a1[28].Data4);
  a1[29].Data1 = GetCurrentThreadId();
  if ( a5 == (PSRWLOCK *)&v40 )
  {
    if ( a1 != (struct _GUID *)-456LL )
    {
      a1[29].Data1 = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)a1[28].Data4);
    }
  }
  else
  {
    v23 = *a5;
    if ( *a5 )
    {
      LODWORD(v23[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v23);
    }
    *a5 = (PSRWLOCK)Data4;
  }
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)a1);
  *(_DWORD *)(v17 + 104) &= ~1u;
  WakeAllConditionVariable((PCONDITION_VARIABLE)(v17 + 112));
  if ( v22 >= 0 )
  {
    v34 = v37;
    if ( v37 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)((char *)v37 + 16));
      operator delete(v34, (const struct std::nothrow_t *)0x88);
    }
    return 0;
  }
  else
  {
    v24 = utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(&a1[35], a2);
    v27 = (_QWORD *)v24;
    if ( (struct _GUID *)v24 == v11 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6EA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        v26);
    v28 = (char *)v37;
    v29 = *(_QWORD *)(v24 + 40);
    *(_QWORD *)(v24 + 40) = 0;
    if ( v28 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)(v28 + 16));
      operator delete(v28, (const struct std::nothrow_t *)0x88);
    }
    LOBYTE(v25) = 1;
    utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(
      v27,
      v25);
    utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(
      v11,
      v27);
    --*(_QWORD *)v11[1].Data4;
    v30 = v27[5];
    v27[5] = 0;
    if ( v30 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)(v30 + 16));
      operator delete((void *)v30, (const struct std::nothrow_t *)0x88);
    }
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
    v31 = *a5;
    if ( *a5 )
    {
      LODWORD(v31[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v31);
      *a5 = 0;
    }
    Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v29 + 120));
    if ( v29 )
    {
      Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint((Container::Manager::Hns::NetworkEndpoint *)(v29 + 16));
      operator delete((void *)v29, (const struct std::nothrow_t *)0x88);
    }
    AcquireSRWLockExclusive((PSRWLOCK)Data4);
    *((_DWORD *)Data4 + 2) = GetCurrentThreadId();
    if ( a5 == (PSRWLOCK *)&v41 )
    {
      if ( Data4 )
      {
        *((_DWORD *)Data4 + 2) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)Data4);
      }
    }
    else
    {
      v32 = *a5;
      if ( *a5 )
      {
        LODWORD(v32[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v32);
      }
      *a5 = (PSRWLOCK)Data4;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6FD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v22,
      v36);
    return (unsigned int)v22;
  }
}

```

## disassembly

```asm
0x18009bcc4  mov     [rsp-8+arg_10], r8
0x18009bcc9  push    rbp
0x18009bcca  push    rbx
0x18009bccb  push    rsi
0x18009bccc  push    rdi
0x18009bccd  push    r12
0x18009bccf  push    r13
0x18009bcd1  push    r14
0x18009bcd3  push    r15
0x18009bcd5  lea     rbp, [rsp-17h]
0x18009bcda  sub     rsp, 98h
0x18009bce1  mov     r15, rdx
0x18009bce4  mov     r13, rcx
0x18009bce7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009bcee  mov     ecx, 88h; unsigned __int64
0x18009bcf3  mov     r12, r9
0x18009bcf6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009bcfb  xor     ebx, ebx
0x18009bcfd  mov     rsi, rax
0x18009bd00  test    rax, rax
0x18009bd03  jz      loc_18009C0E0
0x18009bd09  movups  xmm0, xmmword ptr [r15]
0x18009bd0d  mov     rdi, [rbp+4Fh+arg_20]
0x18009bd11  lea     rcx, [rax+58h]
0x18009bd15  mov     [rbp+4Fh+var_A0], rax
0x18009bd19  lea     r14, [r13+230h]
0x18009bd20  movdqu  xmmword ptr [rax], xmm0
0x18009bd24  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009bd2b  movdqu  xmmword ptr [rax+10h], xmm0
0x18009bd30  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18009bd37  movdqu  xmmword ptr [rax+20h], xmm1
0x18009bd3c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009bd43  mov     byte ptr [rax+40h], 1
0x18009bd47  mov     [rax+44h], ebx
0x18009bd4a  movdqu  xmmword ptr [rax+30h], xmm0
0x18009bd4f  mov     [rax+48h], rcx
0x18009bd53  mov     [rax+50h], rcx
0x18009bd57  mov     [rcx], bx
0x18009bd5a  mov     [rax+70h], rbx
0x18009bd5e  mov     [rax+78h], rbx
0x18009bd62  mov     [rax+80h], ebx
0x18009bd68  mov     [rax+68h], ebx
0x18009bd6b  mov     rdx, r15
0x18009bd6e  mov     rcx, r14
0x18009bd71  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x18009bd76  cmp     rax, r14
0x18009bd79  jz      loc_18009BE17
0x18009bd7f  mov     rbx, [rax+28h]
0x18009bd83  test    byte ptr [rbx+68h], 1
0x18009bd87  jz      short loc_18009BDDF
0x18009bd89  lea     rcx, [rbx+78h]; this
0x18009bd8d  mov     qword ptr [rbp+4Fh+var_90], 0
0x18009bd95  lea     rdx, [rbp+4Fh+var_90]; struct Csl::RundownProtection *
0x18009bd99  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x18009bd9e  mov     rax, [rdi]
0x18009bda1  lea     rcx, [rbx+70h]; ConditionVariable
0x18009bda5  xor     r9d, r9d; Flags
0x18009bda8  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18009bdac  mov     dword ptr [rax+8], 0
0x18009bdb3  mov     rdx, [rdi]; SRWLock
0x18009bdb6  call    cs:__imp_SleepConditionVariableSRW
0x18009bdbd  nop     dword ptr [rax+rax+00h]
0x18009bdc2  call    cs:__imp_GetCurrentThreadId
0x18009bdc9  nop     dword ptr [rax+rax+00h]
0x18009bdce  mov     rcx, [rdi]
0x18009bdd1  mov     [rcx+8], eax
0x18009bdd4  lea     rcx, [rbp+4Fh+var_90]; this
0x18009bdd8  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x18009bddd  jmp     short loc_18009BD6B
0x18009bddf  mov     rcx, [rbp+57h]; this
0x18009bde3  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009bdea  mov     r9d, 0B7h; char *
0x18009bdf0  mov     edx, 6BBh; void *
0x18009bdf5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009bdfa  lea     rcx, [rsi+10h]; this
0x18009bdfe  mov     ebx, eax
0x18009be00  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009be05  mov     rcx, rsi; void *
0x18009be08  mov     edx, 88h; struct std::nothrow_t *
0x18009be0d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009be12  jmp     loc_18009C0FD
0x18009be17  lea     r9, [rbp+4Fh+var_A0]
0x18009be1b  mov     r8, r15
0x18009be1e  lea     rdx, [rbp+4Fh+var_90]
0x18009be22  mov     rcx, r14
0x18009be25  call    ??$emplace@AEBU_GUID@@V?$unique_ptr@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$unique_ptr@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unique_ptr@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@V?$unique_ptr@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@_N@1@AEBU_GUID@@$$QEAV?$unique_ptr@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedNetwork@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>>>,0>::emplace<_GUID const &,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>>,0>(_GUID const &,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedNetwork,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedNetwork>> &&)
0x18009be2a  mov     rsi, qword ptr [rbp+4Fh+var_90]
0x18009be2e  xor     ebx, ebx
0x18009be30  test    rsi, rsi
0x18009be33  jnz     short loc_18009BE6D
0x18009be35  mov     rcx, [rbp+57h]; this
0x18009be39  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009be40  mov     ebx, 8007000Eh
0x18009be45  mov     edx, 6A9h; void *
0x18009be4a  mov     r9d, ebx; char *
0x18009be4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009be52  mov     rdi, [rbp+4Fh+var_A0]
0x18009be56  test    rdi, rdi
0x18009be59  jz      loc_18009C0FD
0x18009be5f  lea     rcx, [rdi+10h]; this
0x18009be63  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009be68  mov     rcx, rdi
0x18009be6b  jmp     short loc_18009BE08
0x18009be6d  mov     rsi, [rsi+28h]
0x18009be71  mov     rdx, rdi
0x18009be74  mov     rcx, r13
0x18009be77  or      dword ptr [rsi+68h], 1
0x18009be7b  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009be80  mov     rcx, [rdi]; SRWLock
0x18009be83  test    rcx, rcx
0x18009be86  jz      short loc_18009BE9A
0x18009be88  mov     [rcx+8], ebx
0x18009be8b  call    cs:__imp_ReleaseSRWLockExclusive
0x18009be92  nop     dword ptr [rax+rax+00h]
0x18009be97  mov     [rdi], rbx
0x18009be9a  movups  xmm0, xmmword ptr [r12]
0x18009be9f  lea     rax, [rsi+10h]
0x18009bea3  mov     rbx, [rbp+4Fh+arg_10]
0x18009bea7  movsd   xmm1, qword ptr [r12+10h]
0x18009beae  lea     r9, [rbp+4Fh+var_90]
0x18009beb2  movaps  [rbp+4Fh+var_90], xmm0
0x18009beb6  lea     r8, [rbp+4Fh+var_60]
0x18009beba  movsd   [rbp+4Fh+var_80], xmm1
0x18009bebf  mov     rdx, r15; struct _GUID *
0x18009bec2  movups  xmm0, xmmword ptr [rbx]
0x18009bec5  mov     rcx, r13; struct _GUID *
0x18009bec8  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18009becd  movsd   xmm1, qword ptr [rbx+10h]
0x18009bed2  movaps  [rbp+4Fh+var_60], xmm0
0x18009bed6  movsd   [rbp+4Fh+var_50], xmm1
0x18009bedb  call    ?AddNetworkImpl@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@V?$optional@V?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@utl@@1AEAVNetworkEndpoint@Hns@45@@Z; Container::Manager::Core::Details::ContainerObject::AddNetworkImpl(_GUID const &,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,utl::optional<utl::basic_string_view<ushort,utl::char_traits<ushort>>>,Container::Manager::Hns::NetworkEndpoint &)
0x18009bee0  lea     rbx, [r13+1C8h]
0x18009bee7  mov     r12d, eax
0x18009beea  mov     rcx, rbx; SRWLock
0x18009beed  call    cs:__imp_AcquireSRWLockExclusive
0x18009bef4  nop     dword ptr [rax+rax+00h]
0x18009bef9  call    cs:__imp_GetCurrentThreadId
0x18009bf00  nop     dword ptr [rax+rax+00h]
0x18009bf05  mov     [rbx+8], eax
0x18009bf08  lea     rax, [rbp+4Fh+var_70]
0x18009bf0c  cmp     rdi, rax
0x18009bf0f  jz      short loc_18009BF31
0x18009bf11  mov     rcx, [rdi]; SRWLock
0x18009bf14  test    rcx, rcx
0x18009bf17  jz      short loc_18009BF2C
0x18009bf19  mov     dword ptr [rcx+8], 0
0x18009bf20  call    cs:__imp_ReleaseSRWLockExclusive
0x18009bf27  nop     dword ptr [rax+rax+00h]
0x18009bf2c  mov     [rdi], rbx
0x18009bf2f  jmp     short loc_18009BF4C
0x18009bf31  test    rbx, rbx
0x18009bf34  jz      short loc_18009BF4C
0x18009bf36  mov     rcx, rbx; SRWLock
0x18009bf39  mov     dword ptr [rbx+8], 0
0x18009bf40  call    cs:__imp_ReleaseSRWLockExclusive
0x18009bf47  nop     dword ptr [rax+rax+00h]
0x18009bf4c  mov     rcx, r13; this
0x18009bf4f  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x18009bf54  and     dword ptr [rsi+68h], 0FFFFFFFEh
0x18009bf58  lea     rcx, [rsi+70h]; ConditionVariable
0x18009bf5c  call    cs:__imp_WakeAllConditionVariable
0x18009bf63  nop     dword ptr [rax+rax+00h]
0x18009bf68  test    r12d, r12d
0x18009bf6b  jns     loc_18009C0BD
0x18009bf71  mov     rdx, r15
0x18009bf74  mov     rcx, r14
0x18009bf77  call    ??$_FindImpl@U_GUID@@@?$_Tree@U_GUID@@U1@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,utl::less<_GUID>,utl::allocator<_GUID>,0>::_FindImpl<_GUID>(_GUID const &)
0x18009bf7c  mov     rcx, [rbp+57h]; this
0x18009bf80  mov     rsi, rax
0x18009bf83  cmp     rax, r14
0x18009bf86  jz      loc_18009C114
0x18009bf8c  mov     r13, [rbp+4Fh+var_A0]
0x18009bf90  mov     r15, [rax+28h]
0x18009bf94  mov     qword ptr [rax+28h], 0
0x18009bf9c  test    r13, r13
0x18009bf9f  jz      short loc_18009BFB7
0x18009bfa1  lea     rcx, [r13+10h]; this
0x18009bfa5  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009bfaa  mov     edx, 88h; struct std::nothrow_t *
0x18009bfaf  mov     rcx, r13; void *
0x18009bfb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009bfb7  mov     dl, 1
0x18009bfb9  mov     rcx, rsi
0x18009bfbc  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(bool)
0x18009bfc1  mov     rdx, rsi
0x18009bfc4  mov     rcx, r14
0x18009bfc7  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>> *)
0x18009bfcc  dec     qword ptr [r14+18h]
0x18009bfd0  xor     r13d, r13d
0x18009bfd3  mov     r14, [rsi+28h]
0x18009bfd7  mov     [rsi+28h], r13
0x18009bfdb  test    r14, r14
0x18009bfde  jz      short loc_18009BFF6
0x18009bfe0  lea     rcx, [r14+10h]; this
0x18009bfe4  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009bfe9  mov     edx, 88h; struct std::nothrow_t *
0x18009bfee  mov     rcx, r14; void *
0x18009bff1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009bff6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009bffd  mov     rcx, rsi; void *
0x18009c000  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009c005  mov     rcx, [rdi]; SRWLock
0x18009c008  test    rcx, rcx
0x18009c00b  jz      short loc_18009C020
0x18009c00d  mov     [rcx+8], r13d
0x18009c011  call    cs:__imp_ReleaseSRWLockExclusive
0x18009c018  nop     dword ptr [rax+rax+00h]
0x18009c01d  mov     [rdi], r13
0x18009c020  lea     rcx, [r15+78h]; this
0x18009c024  call    ?WaitForRundownProtectionRelease@RundownReference@Csl@@QEAAXXZ; Csl::RundownReference::WaitForRundownProtectionRelease(void)
0x18009c029  test    r15, r15
0x18009c02c  jz      short loc_18009C044
0x18009c02e  lea     rcx, [r15+10h]; this
0x18009c032  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009c037  mov     edx, 88h; struct std::nothrow_t *
0x18009c03c  mov     rcx, r15; void *
0x18009c03f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009c044  mov     rcx, rbx; SRWLock
0x18009c047  call    cs:__imp_AcquireSRWLockExclusive
0x18009c04e  nop     dword ptr [rax+rax+00h]
0x18009c053  call    cs:__imp_GetCurrentThreadId
0x18009c05a  nop     dword ptr [rax+rax+00h]
0x18009c05f  mov     [rbx+8], eax
0x18009c062  lea     rax, [rbp+4Fh+var_68]
0x18009c066  cmp     rdi, rax
0x18009c069  jz      short loc_18009C088
0x18009c06b  mov     rcx, [rdi]; SRWLock
0x18009c06e  test    rcx, rcx
0x18009c071  jz      short loc_18009C083
0x18009c073  mov     [rcx+8], r13d
0x18009c077  call    cs:__imp_ReleaseSRWLockExclusive
0x18009c07e  nop     dword ptr [rax+rax+00h]
0x18009c083  mov     [rdi], rbx
0x18009c086  jmp     short loc_18009C0A0
0x18009c088  test    rbx, rbx
0x18009c08b  jz      short loc_18009C0A0
0x18009c08d  mov     rcx, rbx; SRWLock
0x18009c090  mov     [rbx+8], r13d
0x18009c094  call    cs:__imp_ReleaseSRWLockExclusive
0x18009c09b  nop     dword ptr [rax+rax+00h]
0x18009c0a0  mov     rcx, [rbp+57h]; this
0x18009c0a4  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009c0ab  mov     r9d, r12d; char *
0x18009c0ae  mov     edx, 6FDh; void *
0x18009c0b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c0b8  mov     eax, r12d
0x18009c0bb  jmp     short loc_18009C0FF
0x18009c0bd  mov     rbx, [rbp+4Fh+var_A0]
0x18009c0c1  test    rbx, rbx
0x18009c0c4  jz      short loc_18009C0DC
0x18009c0c6  lea     rcx, [rbx+10h]; this
0x18009c0ca  call    ??1NetworkEndpoint@Hns@Manager@Container@@QEAA@XZ; Container::Manager::Hns::NetworkEndpoint::~NetworkEndpoint(void)
0x18009c0cf  mov     edx, 88h; struct std::nothrow_t *
0x18009c0d4  mov     rcx, rbx; void *
0x18009c0d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009c0dc  xor     eax, eax
0x18009c0de  jmp     short loc_18009C0FF
0x18009c0e0  mov     rcx, [rbp+57h]; this
0x18009c0e4  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009c0eb  mov     ebx, 8007000Eh
0x18009c0f0  mov     edx, 698h; void *
0x18009c0f5  mov     r9d, ebx; char *
0x18009c0f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c0fd  mov     eax, ebx
0x18009c0ff  add     rsp, 98h
0x18009c106  pop     r15
0x18009c108  pop     r14
0x18009c10a  pop     r13
0x18009c10c  pop     r12
0x18009c10e  pop     rdi
0x18009c10f  pop     rsi
0x18009c110  pop     rbx
0x18009c111  pop     rbp
0x18009c112  retn
0x18009c114  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009c11b  mov     edx, 6EAh; void *
0x18009c120  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
