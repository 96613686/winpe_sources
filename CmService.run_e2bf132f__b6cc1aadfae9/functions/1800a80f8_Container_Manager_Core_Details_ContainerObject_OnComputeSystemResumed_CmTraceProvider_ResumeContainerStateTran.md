# Container::Manager::Core::Details::ContainerObject::OnComputeSystemResumed(CmTraceProvider::ResumeContainerStateTransition const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800a80f8`
- end: `0x1800a8411`
- name: `?OnComputeSystemResumed@ContainerObject@Details@Core@Manager@Container@@AEAAXAEBVResumeContainerStateTransition@CmTraceProvider@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aa830`

## callees

- `0x180004fc4`
- `0x180016718`
- `0x180042b58`
- `0x1800471dc`
- `0x180049a0c`
- `0x180077dd8`
- `0x180098e58`
- `0x1800a321c`
- `0x1800a3340`
- `0x1800a6be0`
- `0x1800a80f8`
- `0x1800abe60`
- `0x1800ac894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8191`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8387`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8191`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a8147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a81c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a81df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a8342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a83b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a83cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a8147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a81c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a81df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a8342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a83b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a83cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a819d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a819d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8393`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ContainerObject::OnComputeSystemResumed(
        Container::Manager::Core::Details::ContainerObject *this,
        __int64 a2,
        char *a3)
{
  bool IsRuntimeFeatureConfigurationsUpdateRequired; // r15
  bool IsHotPatchUpdateRequired; // al
  bool v8; // r14
  __int64 v9; // rcx
  int v10; // r12d
  __int64 v11; // rcx
  utl::_RefCountBase *v12; // rax
  int v13; // eax
  void *v14; // rbx
  __int64 v15; // rcx
  RTL_SRWLOCK *v16; // rdi
  __int64 v17; // rcx
  void *v18; // rbx
  int v19; // [rsp+20h] [rbp-59h]
  char v20; // [rsp+30h] [rbp-49h] BYREF
  char v21; // [rsp+38h] [rbp-41h] BYREF
  utl::_RefCountBase *v22[2]; // [rsp+40h] [rbp-39h] BYREF
  void *v23[2]; // [rsp+50h] [rbp-29h] BYREF
  int v24; // [rsp+60h] [rbp-19h]
  char v25; // [rsp+68h] [rbp-11h]
  _QWORD v26[2]; // [rsp+70h] [rbp-9h] BYREF
  int Address; // [rsp+80h] [rbp+7h] BYREF
  __int64 v28; // [rsp+84h] [rbp+Bh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v30; // [rsp+E0h] [rbp+67h] BYREF

  IsRuntimeFeatureConfigurationsUpdateRequired = Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired(this);
  IsHotPatchUpdateRequired = Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(this);
  v8 = IsHotPatchUpdateRequired;
  if ( IsRuntimeFeatureConfigurationsUpdateRequired || IsHotPatchUpdateRequired )
  {
    v9 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      *(_DWORD *)(v9 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v9);
      *(_QWORD *)a3 = 0;
    }
    *(_OWORD *)v22 = 0;
    v30 = 0;
    v10 = Container::Manager::Core::Details::ContainerObject::NotifyAgentResuming(this, (__int64)v22, (__int64)&v30);
    AcquireSRWLockExclusive((PSRWLOCK)this + 57);
    *((_DWORD *)this + 116) = GetCurrentThreadId();
    if ( a3 == &v20 )
    {
      *((_DWORD *)this + 116) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
    }
    else
    {
      v11 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3 )
      {
        *(_DWORD *)(v11 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v11);
      }
      *(_QWORD *)a3 = (char *)this + 456;
    }
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x30D6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v10,
        v19);
    }
    else
    {
      if ( IsRuntimeFeatureConfigurationsUpdateRequired )
        *(_OWORD *)((char *)this + 792) = *(_OWORD *)v22;
      if ( v8 )
        *((_QWORD *)this + 103) = v30;
    }
  }
  if ( *((_BYTE *)this + 152) )
  {
    utl::make_shared<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext,>(v22);
    v12 = v22[0];
    if ( v22[0] )
    {
      *((_DWORD *)v22[0] + 6) = 7;
      *(_OWORD *)((char *)v12 + 28) = *(_OWORD *)(*(_QWORD *)(a2 + 272) + 8LL);
      if ( !*((_BYTE *)v12 + 44) )
        *((_BYTE *)v12 + 44) = 1;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v25 = 0;
      v26[1] = v26;
      v26[0] = v26;
      Address = 0;
      v28 = 0;
      v13 = Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(this, 7, v22, v23);
      if ( v13 >= 0 )
      {
        Container::Manager::Core::Details::ContainerObject::QueueWorkItemGroup(this, v23);
        v15 = *(_QWORD *)a3;
        if ( *(_QWORD *)a3 )
        {
          *(_DWORD *)(v15 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v15);
          *(_QWORD *)a3 = 0;
        }
        wil::slim_event_t<1>::wait(&Address);
        if ( (int)(BYTE4(v28) != 0 ? v28 : 0) < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3105,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            BYTE4(v28) != 0 ? (const char *)(unsigned int)v28 : 0,
            v19);
        v16 = (RTL_SRWLOCK *)((char *)this + 456);
        AcquireSRWLockExclusive(v16);
        LODWORD(v16[1].Ptr) = GetCurrentThreadId();
        if ( a3 == &v21 )
        {
          LODWORD(v16[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v16);
        }
        else
        {
          v17 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3 )
          {
            *(_DWORD *)(v17 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v17);
          }
          *(_QWORD *)a3 = v16;
        }
        v18 = v23[0];
        v23[0] = 0;
        if ( v18 )
        {
          Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v18);
          operator delete(v18, (const struct std::nothrow_t *)0x20);
        }
      }
      else
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x30FB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v13,
          v19);
        v14 = v23[0];
        v23[0] = 0;
        if ( v14 )
        {
          Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v14);
          operator delete(v14, (const struct std::nothrow_t *)0x20);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x30E8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        v19);
      if ( v22[1] )
        utl::_RefCountBase::_DecStrong(v22[1]);
    }
  }
}

```

## disassembly

```asm
0x1800a80f8  push    rbp
0x1800a80fa  push    rbx
0x1800a80fb  push    rsi
0x1800a80fc  push    rdi
0x1800a80fd  push    r12
0x1800a80ff  push    r13
0x1800a8101  push    r14
0x1800a8103  push    r15
0x1800a8105  lea     rbp, [rsp-1Fh]
0x1800a810a  sub     rsp, 98h
0x1800a8111  mov     rbx, r8
0x1800a8114  mov     r13, rdx
0x1800a8117  mov     rdi, rcx
0x1800a811a  call    ?IsRuntimeFeatureConfigurationsUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired(void)
0x1800a811f  mov     r15b, al
0x1800a8122  mov     rcx, rdi; this
0x1800a8125  call    ?IsHotPatchUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(void)
0x1800a812a  mov     r14b, al
0x1800a812d  xor     esi, esi
0x1800a812f  test    r15b, r15b
0x1800a8132  jnz     short loc_1800A813C
0x1800a8134  test    al, al
0x1800a8136  jz      loc_1800A822D
0x1800a813c  mov     rcx, [rbx]; SRWLock
0x1800a813f  test    rcx, rcx
0x1800a8142  jz      short loc_1800A8156
0x1800a8144  mov     [rcx+8], esi
0x1800a8147  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a814e  nop     dword ptr [rax+rax+00h]
0x1800a8153  mov     [rbx], rsi
0x1800a8156  xorps   xmm0, xmm0
0x1800a8159  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1800a815d  mov     [rbp+57h+arg_0], rsi
0x1800a8161  lea     rax, [rbp+57h+arg_0]
0x1800a8165  mov     [rsp+0D0h+var_A8], rax
0x1800a816a  lea     rax, [rbp+57h+var_90]
0x1800a816e  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800a8173  mov     r9b, r14b
0x1800a8176  mov     r8b, r15b
0x1800a8179  mov     rdx, r13
0x1800a817c  mov     rcx, rdi
0x1800a817f  call    ?NotifyAgentResuming@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVResumeContainerStateTransition@CmTraceProvider@@_N1AEAV?$optional@_K@utl@@AEAV?$optional@K@9@@Z; Container::Manager::Core::Details::ContainerObject::NotifyAgentResuming(CmTraceProvider::ResumeContainerStateTransition const &,bool,bool,utl::optional<unsigned __int64> &,utl::optional<ulong> &)
0x1800a8184  mov     r12d, eax
0x1800a8187  lea     rsi, [rdi+1C8h]
0x1800a818e  mov     rcx, rsi; SRWLock
0x1800a8191  call    cs:__imp_AcquireSRWLockExclusive
0x1800a8198  nop     dword ptr [rax+rax+00h]
0x1800a819d  call    cs:__imp_GetCurrentThreadId
0x1800a81a4  nop     dword ptr [rax+rax+00h]
0x1800a81a9  mov     [rsi+8], eax
0x1800a81ac  lea     rax, [rbp+57h+var_A0]
0x1800a81b0  cmp     rbx, rax
0x1800a81b3  jz      short loc_1800A81D5
0x1800a81b5  mov     rcx, [rbx]; SRWLock
0x1800a81b8  test    rcx, rcx
0x1800a81bb  jz      short loc_1800A81D0
0x1800a81bd  mov     dword ptr [rcx+8], 0
0x1800a81c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a81cb  nop     dword ptr [rax+rax+00h]
0x1800a81d0  mov     [rbx], rsi
0x1800a81d3  jmp     short loc_1800A81EB
0x1800a81d5  mov     dword ptr [rsi+8], 0
0x1800a81dc  mov     rcx, rsi; SRWLock
0x1800a81df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a81e6  nop     dword ptr [rax+rax+00h]
0x1800a81eb  xor     esi, esi
0x1800a81ed  test    r12d, r12d
0x1800a81f0  js      short loc_1800A8215
0x1800a81f2  test    r15b, r15b
0x1800a81f5  jz      short loc_1800A8203
0x1800a81f7  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x1800a81fb  movdqu  xmmword ptr [rdi+318h], xmm0
0x1800a8203  test    r14b, r14b
0x1800a8206  jz      short loc_1800A822D
0x1800a8208  mov     rax, [rbp+57h+arg_0]
0x1800a820c  mov     [rdi+338h], rax
0x1800a8213  jmp     short loc_1800A822D
0x1800a8215  mov     rcx, [rbp+5Fh]; this
0x1800a8219  mov     r9d, r12d; char *
0x1800a821c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a8223  mov     edx, 30D6h; void *
0x1800a8228  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a822d  cmp     [rdi+98h], sil
0x1800a8234  jz      loc_1800A83FC
0x1800a823a  lea     rcx, [rbp+57h+var_90]
0x1800a823e  call    ??$make_shared@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext,>(void)
0x1800a8243  mov     rax, [rbp+57h+var_90]
0x1800a8247  test    rax, rax
0x1800a824a  jnz     short loc_1800A827C
0x1800a824c  mov     rcx, [rbp+5Fh]; this
0x1800a8250  mov     r9d, 8007000Eh; char *
0x1800a8256  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a825d  mov     edx, 30E8h; void *
0x1800a8262  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a8267  nop
0x1800a8268  mov     rcx, [rbp+57h+var_90+8]; this
0x1800a826c  test    rcx, rcx
0x1800a826f  jz      short loc_1800A8277
0x1800a8271  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a8276  nop
0x1800a8277  jmp     loc_1800A83FC
0x1800a827c  mov     edx, 7
0x1800a8281  mov     [rax+18h], edx
0x1800a8284  mov     rcx, [r13+110h]
0x1800a828b  movups  xmm0, xmmword ptr [rcx+8]
0x1800a828f  movdqu  xmmword ptr [rax+1Ch], xmm0
0x1800a8294  cmp     [rax+2Ch], sil
0x1800a8298  jnz     short loc_1800A829E
0x1800a829a  mov     byte ptr [rax+2Ch], 1
0x1800a829e  xorps   xmm0, xmm0
0x1800a82a1  movdqa  xmmword ptr [rbp+57h+var_80], xmm0
0x1800a82a6  mov     [rbp+57h+var_70], esi
0x1800a82a9  mov     [rbp+57h+var_68], sil
0x1800a82ad  lea     rax, [rbp+57h+var_60]
0x1800a82b1  mov     [rbp+57h+var_58], rax
0x1800a82b5  lea     rax, [rbp+57h+var_60]
0x1800a82b9  mov     [rbp+57h+var_60], rax
0x1800a82bd  mov     [rbp+57h+Address], esi
0x1800a82c0  xor     eax, eax
0x1800a82c2  mov     [rbp+57h+var_4C], rax
0x1800a82c6  mov     byte ptr [rbp+57h+var_4C], sil
0x1800a82ca  mov     byte ptr [rbp+57h+var_4C+4], sil
0x1800a82ce  movaps  xmm0, xmmword ptr [rbp+57h+var_90]
0x1800a82d2  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x1800a82d7  lea     r9, [rbp+57h+var_80]
0x1800a82db  lea     r8, [rbp+57h+var_90]
0x1800a82df  mov     rcx, rdi
0x1800a82e2  call    ?QueueMirrorNetworkWorkItems@ContainerObject@Details@Core@Manager@Container@@AEAAJW4MirrorNetworkWorkItemType@12345@V?$shared_ptr@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@@utl@@PEAUWorkItemGroup@12345@@Z; Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(Container::Manager::Core::Details::ContainerObject::MirrorNetworkWorkItemType,utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext>,Container::Manager::Core::Details::ContainerObject::WorkItemGroup *)
0x1800a82e7  test    eax, eax
0x1800a82e9  jns     short loc_1800A832B
0x1800a82eb  mov     rcx, [rbp+5Fh]; this
0x1800a82ef  mov     r9d, eax; char *
0x1800a82f2  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a82f9  mov     edx, 30FBh; void *
0x1800a82fe  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a8303  mov     rbx, [rbp+57h+var_80]
0x1800a8307  mov     [rbp+57h+var_80], rsi
0x1800a830b  test    rbx, rbx
0x1800a830e  jz      short loc_1800A8326
0x1800a8310  mov     rcx, rbx
0x1800a8313  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800a8318  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800a831d  mov     rcx, rbx; void *
0x1800a8320  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a8325  nop
0x1800a8326  jmp     loc_1800A83FC
0x1800a832b  lea     rdx, [rbp+57h+var_80]
0x1800a832f  mov     rcx, rdi
0x1800a8332  call    ?QueueWorkItemGroup@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAUWorkItemGroup@12345@W4WorkItemPriority@12345@@Z; Container::Manager::Core::Details::ContainerObject::QueueWorkItemGroup(Container::Manager::Core::Details::ContainerObject::WorkItemGroup &,Container::Manager::Core::Details::ContainerObject::WorkItemPriority)
0x1800a8337  mov     rcx, [rbx]; SRWLock
0x1800a833a  test    rcx, rcx
0x1800a833d  jz      short loc_1800A8351
0x1800a833f  mov     [rcx+8], esi
0x1800a8342  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a8349  nop     dword ptr [rax+rax+00h]
0x1800a834e  mov     [rbx], rsi
0x1800a8351  lea     rcx, [rbp+57h+Address]; Address
0x1800a8355  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x1800a835a  mov     al, byte ptr [rbp+57h+var_4C+4]
0x1800a835d  neg     al
0x1800a835f  sbb     r9d, r9d
0x1800a8362  and     r9d, dword ptr [rbp+57h+var_4C]; char *
0x1800a8366  mov     rcx, [rbp+5Fh]; this
0x1800a836a  jge     short loc_1800A837D
0x1800a836c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a8373  mov     edx, 3105h; void *
0x1800a8378  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a837d  add     rdi, 1C8h
0x1800a8384  mov     rcx, rdi; SRWLock
0x1800a8387  call    cs:__imp_AcquireSRWLockExclusive
0x1800a838e  nop     dword ptr [rax+rax+00h]
0x1800a8393  call    cs:__imp_GetCurrentThreadId
0x1800a839a  nop     dword ptr [rax+rax+00h]
0x1800a839f  mov     [rdi+8], eax
0x1800a83a2  lea     rax, [rbp+57h+var_98]
0x1800a83a6  cmp     rbx, rax
0x1800a83a9  jz      short loc_1800A83C7
0x1800a83ab  mov     rcx, [rbx]; SRWLock
0x1800a83ae  test    rcx, rcx
0x1800a83b1  jz      short loc_1800A83C2
0x1800a83b3  mov     [rcx+8], esi
0x1800a83b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a83bd  nop     dword ptr [rax+rax+00h]
0x1800a83c2  mov     [rbx], rdi
0x1800a83c5  jmp     short loc_1800A83D9
0x1800a83c7  mov     [rdi+8], esi
0x1800a83ca  mov     rcx, rdi; SRWLock
0x1800a83cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a83d4  nop     dword ptr [rax+rax+00h]
0x1800a83d9  mov     rbx, [rbp+57h+var_80]
0x1800a83dd  mov     [rbp+57h+var_80], rsi
0x1800a83e1  test    rbx, rbx
0x1800a83e4  jz      short loc_1800A83FC
0x1800a83e6  mov     rcx, rbx
0x1800a83e9  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800a83ee  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800a83f3  mov     rcx, rbx; void *
0x1800a83f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a83fb  nop
0x1800a83fc  add     rsp, 98h
0x1800a8403  pop     r15
0x1800a8405  pop     r14
0x1800a8407  pop     r13
0x1800a8409  pop     r12
0x1800a840b  pop     rdi
0x1800a840c  pop     rsi
0x1800a840d  pop     rbx
0x1800a840e  pop     rbp
0x1800a840f  retn
```
