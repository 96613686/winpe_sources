# Container::Manager::Core::Details::ContainerObject::OnUpdatesCompleted(void)

- ea: `0x1800a94bc`
- end: `0x1800a9871`
- name: `?OnUpdatesCompleted@ContainerObject@Details@Core@Manager@Container@@AEAAJXZ`
- size: `949`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800a9880`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x18003c7d0`
- `0x1800493c8`
- `0x180049454`
- `0x18004feb4`
- `0x18005620c`
- `0x18005a30c`
- `0x180062edc`
- `0x180063cd0`
- `0x180065c70`
- `0x18006e1f0`
- `0x1800a94bc`
- `0x1800d6fc0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a97f2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800a97f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a95f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a97ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a95f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a97ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a96e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a976a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a9806`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a96e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a976a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a9806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9601`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9601`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::OnUpdatesCompleted(
        Container::Manager::Core::Details::ContainerObject *this)
{
  __int64 v2; // rcx
  int LayerSequenceNumberMap; // ebx
  const char *v4; // r9
  __m128i *Id; // rax
  _QWORD *v6; // rcx
  RTL_SRWLOCK *v7; // rbx
  const struct _GUID *v8; // rax
  DWORD CurrentThreadId; // eax
  Container::Manager::Core::Details::ResourceOperation **v10; // r14
  __int64 v11; // rcx
  int ResourceOperation; // eax
  unsigned int v13; // r15d
  Container::Manager::Core::ResourceHandle *v14; // rbx
  Container::Manager::Core::Details::ResourceOperation *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  Container::Manager::Core::ResourceHandle *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rbx
  bool v22; // zf
  _QWORD v23[4]; // [rsp+20h] [rbp-39h] BYREF
  int v24; // [rsp+40h] [rbp-19h]
  char v25; // [rsp+44h] [rbp-15h]
  char v26; // [rsp+45h] [rbp-14h]
  char v27; // [rsp+46h] [rbp-13h]
  Container::Manager::Core::ResourceHandle *v28[2]; // [rsp+48h] [rbp-11h]
  __int128 v29; // [rsp+58h] [rbp-1h]
  __int128 v30; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v31; // [rsp+78h] [rbp+1Fh]
  __int64 v32; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v34; // [rsp+C0h] [rbp+67h] BYREF

  if ( (*(_BYTE *)(*((_QWORD *)this + 188) + 288LL) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)this + 179);
    v23[0] = v23;
    v23[3] = 0;
    v23[1] = v23;
    v23[2] = v23;
    v32 = 0;
    v30 = 0;
    v31 = 0;
    LayerSequenceNumberMap = Container::Manager::Core::Details::ServicingOrchestrator::GetLayerSequenceNumberMap(
                               v2,
                               v23,
                               &v30);
    if ( (_BYTE)v32 )
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(&v30);
    if ( LayerSequenceNumberMap < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x320B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)LayerSequenceNumberMap,
        v23[0]);
LABEL_35:
      utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v23);
      return (unsigned int)LayerSequenceNumberMap;
    }
    utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::find<void>(
      v23,
      &v34,
      *((_QWORD *)this + 188) + 140LL);
    if ( (_QWORD *)v34 == v23 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x320E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        v4);
    Id = (__m128i *)Container::Manager::Core::ResourceHandle::GetId(*(Container::Manager::Core::ResourceHandle **)(v34 + 40));
    v6 = (_QWORD *)*((_QWORD *)this + 188);
    if ( *v6 != Id->m128i_i64[0] || v6[1] != _mm_srli_si128(*Id, 8).m128i_u64[0] )
    {
      LayerSequenceNumberMap = wil::details::in1diag3::Return_Win32(
                                 retaddr,
                                 (void *)0x3216,
                                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                                 (const char *)0x4D5,
                                 v23[0]);
      goto LABEL_35;
    }
    utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,unsigned long>>>,0>::clear(v23);
  }
  v7 = (RTL_SRWLOCK *)*((_QWORD *)this + 154);
  v8 = Container::Manager::Core::ResourceHandle::GetId(*((Container::Manager::Core::ResourceHandle **)this + 160));
  Container::Manager::Core::Details::ComputeReaper::WaitForStorageCleanupIfNeeded(v7, v8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  CurrentThreadId = GetCurrentThreadId();
  v25 = 0;
  v29 = 0;
  *((_DWORD *)this + 116) = CurrentThreadId;
  v10 = (Container::Manager::Core::Details::ResourceOperation **)((char *)this + 1608);
  LOBYTE(v29) = 0;
  *((_QWORD *)&v31 + 1) = v29;
  *(_DWORD *)((char *)&v32 + 1) = *(_DWORD *)((char *)&v29 + 9);
  *(_OWORD *)v28 = 0;
  *(_WORD *)((char *)&v32 + 5) = *(_WORD *)((char *)&v29 + 13);
  v26 = 0;
  v27 = 0;
  BYTE6(v30) = 0;
  v11 = *((_QWORD *)this + 160);
  HIBYTE(v32) = HIBYTE(v29);
  LOBYTE(v28[0]) = 0;
  LOBYTE(v28[1]) = 0;
  BYTE8(v29) = 0;
  v24 = 5;
  LODWORD(v30) = 5;
  WORD2(v30) = 0;
  BYTE8(v30) = 0;
  LOBYTE(v31) = 0;
  LOBYTE(v32) = 0;
  ResourceOperation = Container::Manager::Core::ResourceHandle::CreateOrGetResourceOperation(
                        v11,
                        &v30,
                        (char *)this + 1608);
  v13 = ResourceOperation;
  if ( ResourceOperation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3232,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)ResourceOperation,
      v23[0]);
    if ( LOBYTE(v28[1]) )
    {
      v14 = v28[0];
      v28[0] = 0;
      if ( v14 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v14);
        operator delete(v14, (const struct std::nothrow_t *)0x58);
      }
    }
    *((_DWORD *)this + 116) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
    return v13;
  }
  v16 = *v10;
  if ( *((_BYTE *)this + 1624) )
  {
    v17 = Container::Manager::Core::Details::ResourceOperation::SetPriority(v16, 1);
    if ( v17 < 0 )
    {
      v18 = 12856;
LABEL_20:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v17,
        v23[0]);
    }
  }
  else
  {
    v17 = Container::Manager::Core::Details::ResourceOperation::SetPriority(v16, 0);
    if ( v17 < 0 )
    {
      v18 = 12861;
      goto LABEL_20;
    }
  }
  if ( LOBYTE(v28[1]) )
  {
    v19 = v28[0];
    v28[0] = 0;
    if ( v19 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v19);
      operator delete(v19, (const struct std::nothrow_t *)0x58);
    }
  }
  *((_DWORD *)this + 116) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
  LayerSequenceNumberMap = Container::Manager::Core::Details::ResourceOperation::StartIfNeeded(*v10);
  if ( LayerSequenceNumberMap < 0 )
  {
    v20 = 12869;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)LayerSequenceNumberMap,
      v23[0]);
    return (unsigned int)LayerSequenceNumberMap;
  }
  LayerSequenceNumberMap = Container::Manager::Core::Details::ResourceOperation::WatchForCompletion(
                             *v10,
                             *((_QWORD *)this + 162));
  if ( LayerSequenceNumberMap < 0 )
  {
    v20 = 12874;
    goto LABEL_26;
  }
  v21 = **((_QWORD **)this + 162);
  AcquireSRWLockExclusive((PSRWLOCK)(v21 + 8));
  v22 = *(_DWORD *)v21 == 2;
  *(_QWORD *)(v21 + 16) = Container::Manager::Core::Details::ContainerObject::OnContainerStorageMaterialized;
  *(_QWORD *)(v21 + 24) = this;
  if ( v22 )
    SubmitThreadpoolWork(*(PTP_WORK *)(v21 + 32));
  if ( v21 != -8 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v21 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800a94bc  mov     [rsp-8+arg_8], rbx
0x1800a94c1  mov     [rsp-8+arg_10], rsi
0x1800a94c6  push    rbp
0x1800a94c7  push    rdi
0x1800a94c8  push    r12
0x1800a94ca  push    r14
0x1800a94cc  push    r15
0x1800a94ce  lea     rbp, [rsp-37h]
0x1800a94d3  sub     rsp, 90h
0x1800a94da  mov     rax, [rcx+5E0h]
0x1800a94e1  xor     r12d, r12d
0x1800a94e4  mov     rdi, rcx
0x1800a94e7  test    byte ptr [rax+120h], 10h
0x1800a94ee  jz      loc_1800A95CD
0x1800a94f4  mov     rcx, [rcx+598h]
0x1800a94fb  lea     rax, [rbp+57h+var_90]
0x1800a94ff  mov     [rbp+57h+var_90], rax
0x1800a9503  lea     r8, [rbp+57h+var_48]
0x1800a9507  lea     rax, [rbp+57h+var_90]
0x1800a950b  mov     [rbp+57h+var_78], r12
0x1800a950f  xorps   xmm0, xmm0
0x1800a9512  mov     [rbp+57h+var_88], rax
0x1800a9516  mov     [rbp+57h+var_80], rax
0x1800a951a  lea     rdx, [rbp+57h+var_90]
0x1800a951e  xor     eax, eax
0x1800a9520  mov     [rbp+57h+var_28], rax
0x1800a9524  movups  [rbp+57h+var_48], xmm0
0x1800a9528  movups  [rbp+57h+var_38], xmm0
0x1800a952c  call    ?GetLayerSequenceNumberMap@ServicingOrchestrator@Details@Core@Manager@Container@@SAJAEAVResourceBroker@2345@AEAV?$map@U_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@@utl@@AEBV?$optional@V?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@@8@@Z; Container::Manager::Core::Details::ServicingOrchestrator::GetLayerSequenceNumberMap(Container::Manager::Core::Details::ResourceBroker &,utl::map<_GUID,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>> &,utl::optional<utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>> const &)
0x1800a9531  mov     ebx, eax
0x1800a9533  cmp     byte ptr [rbp+57h+var_28], r12b
0x1800a9537  jz      short loc_1800A9542
0x1800a9539  lea     rcx, [rbp+57h+var_48]
0x1800a953d  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x1800a9542  test    ebx, ebx
0x1800a9544  jns     short loc_1800A9563
0x1800a9546  mov     rcx, [rbp+5Fh]; this
0x1800a954a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a9551  mov     r9d, ebx; char *
0x1800a9554  mov     edx, 320Bh; void *
0x1800a9559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a955e  jmp     loc_1800A9833
0x1800a9563  mov     r8, [rdi+5E0h]
0x1800a956a  lea     rdx, [rbp+57h+arg_0]
0x1800a956e  add     r8, 8Ch
0x1800a9575  lea     rcx, [rbp+57h+var_90]
0x1800a9579  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::find<void>(_GUID const &)
0x1800a957e  mov     rcx, [rbp+57h+arg_0]
0x1800a9582  lea     rax, [rbp+57h+var_90]
0x1800a9586  cmp     rcx, rax
0x1800a9589  jz      loc_1800A985B
0x1800a958f  mov     rcx, [rcx+28h]; this
0x1800a9593  call    ?GetId@ResourceHandle@Core@Manager@Container@@QEBAAEBU_GUID@@XZ; Container::Manager::Core::ResourceHandle::GetId(void)
0x1800a9598  mov     rcx, [rdi+5E0h]
0x1800a959f  movups  xmm0, xmmword ptr [rax]
0x1800a95a2  movq    rax, xmm0
0x1800a95a7  cmp     [rcx], rax
0x1800a95aa  jnz     loc_1800A9816
0x1800a95b0  psrldq  xmm0, 8
0x1800a95b5  movq    rax, xmm0
0x1800a95ba  cmp     [rcx+8], rax
0x1800a95be  jnz     loc_1800A9816
0x1800a95c4  lea     rcx, [rbp+57h+var_90]
0x1800a95c8  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::clear(void)
0x1800a95cd  mov     rcx, [rdi+500h]; this
0x1800a95d4  mov     rbx, [rdi+4D0h]
0x1800a95db  call    ?GetId@ResourceHandle@Core@Manager@Container@@QEBAAEBU_GUID@@XZ; Container::Manager::Core::ResourceHandle::GetId(void)
0x1800a95e0  mov     rdx, rax; struct _GUID *
0x1800a95e3  mov     rcx, rbx; SRWLock
0x1800a95e6  call    ?WaitForStorageCleanupIfNeeded@ComputeReaper@Details@Core@Manager@Container@@QEBAXAEBU_GUID@@@Z; Container::Manager::Core::Details::ComputeReaper::WaitForStorageCleanupIfNeeded(_GUID const &)
0x1800a95eb  lea     rsi, [rdi+1C8h]
0x1800a95f2  mov     rcx, rsi; SRWLock
0x1800a95f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800a95fc  nop     dword ptr [rax+rax+00h]
0x1800a9601  call    cs:__imp_GetCurrentThreadId
0x1800a9608  nop     dword ptr [rax+rax+00h]
0x1800a960d  xorps   xmm0, xmm0
0x1800a9610  mov     [rbp+57h+var_6C], r12b
0x1800a9614  movups  [rbp+57h+var_58], xmm0
0x1800a9618  mov     [rsi+8], eax
0x1800a961b  lea     r14, [rdi+648h]
0x1800a9622  mov     dl, r12b
0x1800a9625  mov     byte ptr [rbp+57h+var_58], r12b
0x1800a9629  mov     rax, qword ptr [rbp+57h+var_58]
0x1800a962d  mov     cl, r12b
0x1800a9630  mov     qword ptr [rbp+57h+var_38+8], rax
0x1800a9634  mov     r9d, 5
0x1800a963a  mov     eax, dword ptr [rbp+57h+var_58+9]
0x1800a963d  mov     r8, r14
0x1800a9640  mov     dword ptr [rbp+57h+var_28+1], eax
0x1800a9643  movzx   eax, word ptr [rbp+57h+var_58+0Dh]
0x1800a9647  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800a964b  mov     word ptr [rbp+57h+var_28+5], ax
0x1800a964f  mov     al, byte ptr [rbp+57h+var_58+0Fh]
0x1800a9652  mov     [rbp+57h+var_6B], dl
0x1800a9655  mov     [rbp+57h+var_6A], cl
0x1800a9658  mov     byte ptr [rbp+57h+var_48+5], dl
0x1800a965b  lea     rdx, [rbp+57h+var_48]
0x1800a965f  mov     byte ptr [rbp+57h+var_48+6], cl
0x1800a9662  mov     rcx, [rdi+500h]
0x1800a9669  mov     byte ptr [rbp+57h+var_28+7], al
0x1800a966c  mov     byte ptr [rbp+57h+var_68], r12b
0x1800a9670  mov     byte ptr [rbp+57h+var_68+8], r12b
0x1800a9674  mov     byte ptr [rbp+57h+var_58+8], r12b
0x1800a9678  mov     [rbp+57h+var_70], r9d
0x1800a967c  mov     dword ptr [rbp+57h+var_48], r9d
0x1800a9680  mov     byte ptr [rbp+57h+var_48+4], r12b
0x1800a9684  mov     byte ptr [rbp+57h+var_48+8], r12b
0x1800a9688  mov     byte ptr [rbp+57h+var_38], r12b
0x1800a968c  mov     byte ptr [rbp+57h+var_28], r12b
0x1800a9690  call    ?CreateOrGetResourceOperation@ResourceHandle@Core@Manager@Container@@QEAAJUResourceOperationConfiguration@Details@234@AEAV?$shared_ptr@VResourceOperation@Details@Core@Manager@Container@@@utl@@@Z; Container::Manager::Core::ResourceHandle::CreateOrGetResourceOperation(Container::Manager::Core::Details::ResourceOperationConfiguration,utl::shared_ptr<Container::Manager::Core::Details::ResourceOperation> &)
0x1800a9695  mov     r15d, eax
0x1800a9698  test    eax, eax
0x1800a969a  jns     short loc_1800A96F7
0x1800a969c  mov     rcx, [rbp+5Fh]; this
0x1800a96a0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a96a7  mov     r9d, eax; char *
0x1800a96aa  mov     edx, 3232h; void *
0x1800a96af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a96b4  cmp     byte ptr [rbp+57h+var_68+8], r12b
0x1800a96b8  jz      short loc_1800A96DC
0x1800a96ba  mov     rbx, [rbp+57h+var_68]
0x1800a96be  mov     [rbp+57h+var_68], r12
0x1800a96c2  test    rbx, rbx
0x1800a96c5  jz      short loc_1800A96DC
0x1800a96c7  mov     rcx, rbx; this
0x1800a96ca  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a96cf  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800a96d4  mov     rcx, rbx; void *
0x1800a96d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a96dc  mov     rcx, rsi; SRWLock
0x1800a96df  mov     [rsi+8], r12d
0x1800a96e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a96ea  nop     dword ptr [rax+rax+00h]
0x1800a96ef  mov     eax, r15d
0x1800a96f2  jmp     loc_1800A983E
0x1800a96f7  mov     rcx, [r14]
0x1800a96fa  cmp     [rdi+658h], r12b
0x1800a9701  jz      short loc_1800A9718
0x1800a9703  mov     edx, 1
0x1800a9708  call    ?SetPriority@ResourceOperation@Details@Core@Manager@Container@@QEAAJW4ResourceOperationPriority@2345@@Z; Container::Manager::Core::Details::ResourceOperation::SetPriority(Container::Manager::Core::Details::ResourceOperationPriority)
0x1800a970d  test    eax, eax
0x1800a970f  jns     short loc_1800A973B
0x1800a9711  mov     edx, 3238h
0x1800a9716  jmp     short loc_1800A9728
0x1800a9718  xor     edx, edx
0x1800a971a  call    ?SetPriority@ResourceOperation@Details@Core@Manager@Container@@QEAAJW4ResourceOperationPriority@2345@@Z; Container::Manager::Core::Details::ResourceOperation::SetPriority(Container::Manager::Core::Details::ResourceOperationPriority)
0x1800a971f  test    eax, eax
0x1800a9721  jns     short loc_1800A973B
0x1800a9723  mov     edx, 323Dh; void *
0x1800a9728  mov     rcx, [rbp+5Fh]; this
0x1800a972c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a9733  mov     r9d, eax; char *
0x1800a9736  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a973b  cmp     byte ptr [rbp+57h+var_68+8], r12b
0x1800a973f  jz      short loc_1800A9763
0x1800a9741  mov     rbx, [rbp+57h+var_68]
0x1800a9745  mov     [rbp+57h+var_68], r12
0x1800a9749  test    rbx, rbx
0x1800a974c  jz      short loc_1800A9763
0x1800a974e  mov     rcx, rbx; this
0x1800a9751  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a9756  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800a975b  mov     rcx, rbx; void *
0x1800a975e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a9763  mov     rcx, rsi; SRWLock
0x1800a9766  mov     [rsi+8], r12d
0x1800a976a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a9771  nop     dword ptr [rax+rax+00h]
0x1800a9776  mov     rcx, [r14]; this
0x1800a9779  call    ?StartIfNeeded@ResourceOperation@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::ResourceOperation::StartIfNeeded(void)
0x1800a977e  mov     ebx, eax
0x1800a9780  test    eax, eax
0x1800a9782  jns     short loc_1800A97A1
0x1800a9784  mov     edx, 3245h; void *
0x1800a9789  mov     rcx, [rbp+5Fh]; this
0x1800a978d  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a9794  mov     r9d, ebx; char *
0x1800a9797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a979c  jmp     loc_1800A983C
0x1800a97a1  mov     rdx, [rdi+510h]
0x1800a97a8  mov     rcx, [r14]
0x1800a97ab  call    ?WatchForCompletion@ResourceOperation@Details@Core@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Core::Details::ResourceOperation::WatchForCompletion(Csl::AsyncOperation<void> &)
0x1800a97b0  mov     ebx, eax
0x1800a97b2  test    eax, eax
0x1800a97b4  jns     short loc_1800A97BD
0x1800a97b6  mov     edx, 324Ah
0x1800a97bb  jmp     short loc_1800A9789
0x1800a97bd  mov     rax, [rdi+510h]
0x1800a97c4  mov     rbx, [rax]
0x1800a97c7  lea     rsi, [rbx+8]
0x1800a97cb  mov     rcx, rsi; SRWLock
0x1800a97ce  call    cs:__imp_AcquireSRWLockExclusive
0x1800a97d5  nop     dword ptr [rax+rax+00h]
0x1800a97da  cmp     dword ptr [rbx], 2
0x1800a97dd  lea     rax, ?OnContainerStorageMaterialized@ContainerObject@Details@Core@Manager@Container@@CAXJPEAX@Z; Container::Manager::Core::Details::ContainerObject::OnContainerStorageMaterialized(long,void *)
0x1800a97e4  mov     [rbx+10h], rax
0x1800a97e8  mov     [rbx+18h], rdi
0x1800a97ec  jnz     short loc_1800A97FE
0x1800a97ee  mov     rcx, [rbx+20h]; pwk
0x1800a97f2  call    cs:__imp_SubmitThreadpoolWork
0x1800a97f9  nop     dword ptr [rax+rax+00h]
0x1800a97fe  test    rsi, rsi
0x1800a9801  jz      short loc_1800A9812
0x1800a9803  mov     rcx, rsi; SRWLock
0x1800a9806  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a980d  nop     dword ptr [rax+rax+00h]
0x1800a9812  xor     eax, eax
0x1800a9814  jmp     short loc_1800A983E
0x1800a9816  mov     rcx, [rbp+5Fh]; this
0x1800a981a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a9821  mov     r9d, 4D5h; char *
0x1800a9827  mov     edx, 3216h; void *
0x1800a982c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a9831  mov     ebx, eax
0x1800a9833  lea     rcx, [rbp+57h+var_90]
0x1800a9837  call    ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@U?$pair@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@K@utl@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::pair<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,ulong>>>,0>::clear(void)
0x1800a983c  mov     eax, ebx
0x1800a983e  lea     r11, [rsp+0B0h+var_20]
0x1800a9846  mov     rbx, [r11+38h]
0x1800a984a  mov     rsi, [r11+40h]
0x1800a984e  mov     rsp, r11
0x1800a9851  pop     r15
0x1800a9853  pop     r14
0x1800a9855  pop     r12
0x1800a9857  pop     rdi
0x1800a9858  pop     rbp
0x1800a9859  retn
0x1800a985b  mov     rcx, [rbp+5Fh]; this
0x1800a985f  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a9866  mov     edx, 320Eh; void *
0x1800a986b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
