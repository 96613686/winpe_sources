# Container::Manager::Core::Details::ContainerObject::UnmapVirtualDisk(Csl::Path const &)

- ea: `0x1800b9040`
- end: `0x1800b9328`
- name: `?UnmapVirtualDisk@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this, const struct Path *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001ef60`
- `0x18001f110`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x180078644`
- `0x180098d8c`
- `0x18009b018`
- `0x18009f20c`
- `0x1800ac950`
- `0x1800aca94`
- `0x1800ad4e0`
- `0x1800b7474`
- `0x1800b9040`
- `0x1800ba810`
- `0x18012489c`
- `0x1801256e4`
- `0x180198574`
- `0x180198604`

## import_xrefs

- `ntdll!RtlClearBitEx` at `0x1800b9220`
- `ntdll!RtlClearBitEx` at `0x1800b9220`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b90e4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b90e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9191`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9191`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9201`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b92cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b930a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9201`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b92cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b930a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b906e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b90f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b919d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b906e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b90f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b919d`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::UnmapVirtualDisk(
        Container::Manager::Core::Details::ContainerObject *this,
        const struct Path *a2)
{
  RTL_SRWLOCK *v2; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rbx
  RTL_SRWLOCK *v7; // rcx
  const struct Path *v8; // r8
  int v9; // r14d
  int v10; // eax
  DWORD v11; // eax
  RTL_SRWLOCK *v12; // rcx
  _QWORD *Ptr; // rbx
  __int64 v15; // rax
  RTL_SRWLOCK *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // ebx
  _QWORD v20[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  PSRWLOCK v22; // [rsp+70h] [rbp+40h] BYREF
  PSRWLOCK SRWLock; // [rsp+80h] [rbp+50h] BYREF
  _QWORD *v24; // [rsp+88h] [rbp+58h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 456);
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  CurrentThreadId = GetCurrentThreadId();
  SRWLock = v2;
  LODWORD(v2[1].Ptr) = CurrentThreadId;
  while ( 1 )
  {
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(
      (char *)this + 680,
      &v24,
      a2);
    if ( v24 == (_QWORD *)((char *)this + 680) )
    {
      v17 = 3671;
      goto LABEL_23;
    }
    v6 = v24[7];
    if ( !*(_DWORD *)(v6 + 72) )
    {
      v17 = 3681;
LABEL_23:
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v17,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)0x490,
              v20[0]);
      LODWORD(v2[1].Ptr) = 0;
      v19 = v18;
      ReleaseSRWLockExclusive(v2);
      return v19;
    }
    if ( !*(_BYTE *)(v6 + 160) )
      break;
    v22 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v6 + 80),
      (struct Csl::RundownProtection *)&v22);
    LODWORD(v2[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v6 + 152), v2, 0xFFFFFFFF, 0);
    LODWORD(v2[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v22);
  }
  *(_BYTE *)(v6 + 160) = 1;
  *(_DWORD *)(v6 + 72) = 2;
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
    this,
    &SRWLock);
  v7 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v7);
  }
  v9 = Container::Manager::Hcs::ComputeSystem::UnmapVirtualDisk(
         *((Container::Manager::Hcs::ComputeSystem **)this + 157),
         (const struct Path *)(v6 + 32),
         *(_BYTE *)(v6 + 96));
  if ( v9 >= 0 )
  {
    v10 = Container::Manager::Hcs::RevokeVmWpAccessToFile(this, (const struct _GUID *)v6, v8);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE91,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v10,
        v20[0]);
    Container::Manager::Core::Details::ComputeSystemReaperContext::RemoveFileFromRevokeVmwpAccessList(
      *((PSRWLOCK *)this + 156),
      (const struct Path *)v6);
  }
  AcquireSRWLockExclusive(v2);
  v11 = GetCurrentThreadId();
  v22 = v2;
  LODWORD(v2[1].Ptr) = v11;
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(this);
  if ( v9 >= 0 )
  {
    RtlClearBitEx((char *)this + 720, *(unsigned __int8 *)(v6 + 96));
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(
      (char *)this + 680,
      &SRWLock,
      v6);
    Ptr = SRWLock[7].Ptr;
    SRWLock[7].Ptr = 0;
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::erase(
      (char *)this + 680,
      &SRWLock);
    if ( Ptr[17] )
    {
      v20[0] = Ptr[17];
      v15 = Ptr[18];
      Ptr[17] = 0;
      v20[1] = v15;
      Ptr[18] = 0;
      Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(this, v20, &v22);
    }
    SRWLock = v22;
    v22 = 0;
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::StopOperation(Ptr, &SRWLock);
    Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(Ptr + 10));
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk((Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)Ptr);
    operator delete(Ptr, (const struct std::nothrow_t *)0xA8);
    v16 = v22;
    if ( v22 )
    {
      LODWORD(v22[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v16);
    }
    return 0;
  }
  else
  {
    SRWLock = v22;
    *(_DWORD *)(v6 + 72) = 1;
    v22 = 0;
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::StopOperation(v6, &SRWLock);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v9,
      v20[0]);
    v12 = v22;
    if ( v22 )
    {
      LODWORD(v22[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v12);
    }
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1800b9040  push    rbp
0x1800b9042  push    rbx
0x1800b9043  push    rsi
0x1800b9044  push    rdi
0x1800b9045  push    r12
0x1800b9047  push    r14
0x1800b9049  push    r15
0x1800b904b  mov     rbp, rsp
0x1800b904e  sub     rsp, 30h
0x1800b9052  lea     rdi, [rcx+1C8h]
0x1800b9059  mov     rsi, rcx
0x1800b905c  mov     rcx, rdi; SRWLock
0x1800b905f  mov     r14, rdx
0x1800b9062  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9069  nop     dword ptr [rax+rax+00h]
0x1800b906e  call    cs:__imp_GetCurrentThreadId
0x1800b9075  nop     dword ptr [rax+rax+00h]
0x1800b907a  mov     [rbp+SRWLock], rdi
0x1800b907e  lea     r15, [rsi+2A8h]
0x1800b9085  mov     [rdi+8], eax
0x1800b9088  xor     r12d, r12d
0x1800b908b  mov     r8, r14
0x1800b908e  lea     rdx, [rbp+arg_18]
0x1800b9092  mov     rcx, r15
0x1800b9095  call    ??$find@X@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(Csl::Path const &)
0x1800b909a  mov     rax, [rbp+arg_18]
0x1800b909e  cmp     rax, r15
0x1800b90a1  jz      loc_1800B92E6
0x1800b90a7  mov     rbx, [rax+38h]
0x1800b90ab  cmp     [rbx+48h], r12d
0x1800b90af  jz      loc_1800B92DF
0x1800b90b5  cmp     [rbx+0A0h], r12b
0x1800b90bc  jz      short loc_1800B910A
0x1800b90be  lea     rcx, [rbx+50h]; this
0x1800b90c2  mov     [rbp+arg_0], r12
0x1800b90c6  lea     rdx, [rbp+arg_0]; struct Csl::RundownProtection *
0x1800b90ca  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800b90cf  lea     rcx, [rbx+98h]; ConditionVariable
0x1800b90d6  mov     [rdi+8], r12d
0x1800b90da  xor     r9d, r9d; Flags
0x1800b90dd  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800b90e1  mov     rdx, rdi; SRWLock
0x1800b90e4  call    cs:__imp_SleepConditionVariableSRW
0x1800b90eb  nop     dword ptr [rax+rax+00h]
0x1800b90f0  call    cs:__imp_GetCurrentThreadId
0x1800b90f7  nop     dword ptr [rax+rax+00h]
0x1800b90fc  lea     rcx, [rbp+arg_0]; this
0x1800b9100  mov     [rdi+8], eax
0x1800b9103  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800b9108  jmp     short loc_1800B908B
0x1800b910a  lea     rdx, [rbp+SRWLock]
0x1800b910e  mov     byte ptr [rbx+0A0h], 1
0x1800b9115  mov     rcx, rsi
0x1800b9118  mov     dword ptr [rbx+48h], 2
0x1800b911f  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9124  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b9128  test    rcx, rcx
0x1800b912b  jz      short loc_1800B913D
0x1800b912d  mov     [rcx+8], r12d
0x1800b9131  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9138  nop     dword ptr [rax+rax+00h]
0x1800b913d  mov     r8b, [rbx+60h]; unsigned __int8
0x1800b9141  lea     rdx, [rbx+20h]; struct Path *
0x1800b9145  mov     rcx, [rsi+4E8h]; this
0x1800b914c  call    ?UnmapVirtualDisk@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVPath@Csl@@E@Z; Container::Manager::Hcs::ComputeSystem::UnmapVirtualDisk(Csl::Path const &,uchar)
0x1800b9151  mov     r14d, eax
0x1800b9154  test    eax, eax
0x1800b9156  js      short loc_1800B918E
0x1800b9158  mov     rdx, rbx; struct _GUID *
0x1800b915b  mov     rcx, rsi; this
0x1800b915e  call    ?RevokeVmWpAccessToFile@Hcs@Manager@Container@@YAJAEBU_GUID@@AEBVPath@Csl@@@Z; Container::Manager::Hcs::RevokeVmWpAccessToFile(_GUID const &,Csl::Path const &)
0x1800b9163  test    eax, eax
0x1800b9165  jns     short loc_1800B917F
0x1800b9167  mov     rcx, [rbp+38h]; this
0x1800b916b  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b9172  mov     r9d, eax; char *
0x1800b9175  mov     edx, 0E91h; void *
0x1800b917a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b917f  mov     rcx, [rsi+4E0h]; SRWLock
0x1800b9186  mov     rdx, rbx; struct Path *
0x1800b9189  call    ?RemoveFileFromRevokeVmwpAccessList@ComputeSystemReaperContext@Details@Core@Manager@Container@@QEAAXAEBVPath@Csl@@@Z; Container::Manager::Core::Details::ComputeSystemReaperContext::RemoveFileFromRevokeVmwpAccessList(Csl::Path const &)
0x1800b918e  mov     rcx, rdi; SRWLock
0x1800b9191  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9198  nop     dword ptr [rax+rax+00h]
0x1800b919d  call    cs:__imp_GetCurrentThreadId
0x1800b91a4  nop     dword ptr [rax+rax+00h]
0x1800b91a9  mov     rcx, rsi; this
0x1800b91ac  mov     [rbp+arg_0], rdi
0x1800b91b0  mov     [rdi+8], eax
0x1800b91b3  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x1800b91b8  test    r14d, r14d
0x1800b91bb  jns     short loc_1800B9215
0x1800b91bd  mov     rax, [rbp+arg_0]
0x1800b91c1  lea     rdx, [rbp+SRWLock]
0x1800b91c5  mov     rcx, rbx
0x1800b91c8  mov     [rbp+SRWLock], rax
0x1800b91cc  mov     dword ptr [rbx+48h], 1
0x1800b91d3  mov     [rbp+arg_0], r12
0x1800b91d7  call    ?StopOperation@MappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@QEAAXV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::StopOperation(Csl::SrwLock::ReleaseOnScopeExit<0>)
0x1800b91dc  mov     rcx, [rbp+38h]; this
0x1800b91e0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b91e7  mov     r9d, r14d; char *
0x1800b91ea  mov     edx, 0EA9h; void *
0x1800b91ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b91f4  mov     rcx, [rbp+arg_0]; SRWLock
0x1800b91f8  test    rcx, rcx
0x1800b91fb  jz      short loc_1800B920D
0x1800b91fd  mov     [rcx+8], r12d
0x1800b9201  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9208  nop     dword ptr [rax+rax+00h]
0x1800b920d  mov     eax, r14d
0x1800b9210  jmp     loc_1800B9318
0x1800b9215  movzx   edx, byte ptr [rbx+60h]
0x1800b9219  lea     rcx, [rsi+2D0h]
0x1800b9220  call    cs:__imp_RtlClearBitEx
0x1800b9227  nop     dword ptr [rax+rax+00h]
0x1800b922c  mov     r8, rbx
0x1800b922f  lea     rdx, [rbp+SRWLock]
0x1800b9233  mov     rcx, r15
0x1800b9236  call    ??$find@X@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(Csl::Path const &)
0x1800b923b  mov     r8, [rbp+SRWLock]
0x1800b923f  lea     rdx, [rbp+SRWLock]
0x1800b9243  mov     rcx, r15
0x1800b9246  mov     rbx, [r8+38h]
0x1800b924a  mov     [r8+38h], r12
0x1800b924e  call    ?erase@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::erase(utl::_TreeConstIt<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>)
0x1800b9253  mov     rax, [rbx+88h]
0x1800b925a  test    rax, rax
0x1800b925d  jz      short loc_1800B928C
0x1800b925f  mov     [rbp+var_10], rax
0x1800b9263  lea     r8, [rbp+arg_0]
0x1800b9267  mov     rax, [rbx+90h]
0x1800b926e  lea     rdx, [rbp+var_10]
0x1800b9272  mov     [rbx+88h], r12
0x1800b9279  mov     rcx, rsi
0x1800b927c  mov     [rbp+var_8], rax
0x1800b9280  mov     [rbx+90h], r12
0x1800b9287  call    ?DereferenceMappedLayer@ContainerObject@Details@Core@Manager@Container@@AEAAXV?$shared_ptr@UMappedLayer@ContainerObject@Details@Core@Manager@Container@@@utl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::DereferenceMappedLayer(utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MappedLayer>,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b928c  mov     rax, [rbp+arg_0]
0x1800b9290  lea     rdx, [rbp+SRWLock]
0x1800b9294  mov     rcx, rbx
0x1800b9297  mov     [rbp+SRWLock], rax
0x1800b929b  mov     [rbp+arg_0], r12
0x1800b929f  call    ?StopOperation@MappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@QEAAXV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::StopOperation(Csl::SrwLock::ReleaseOnScopeExit<0>)
0x1800b92a4  lea     rcx, [rbx+50h]; this
0x1800b92a8  call    ?WaitForRundownProtectionRelease@RundownReference@Csl@@QEAAXXZ; Csl::RundownReference::WaitForRundownProtectionRelease(void)
0x1800b92ad  mov     rcx, rbx; this
0x1800b92b0  call    ??1MappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(void)
0x1800b92b5  mov     edx, 0A8h; struct std::nothrow_t *
0x1800b92ba  mov     rcx, rbx; void *
0x1800b92bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b92c2  mov     rcx, [rbp+arg_0]; SRWLock
0x1800b92c6  test    rcx, rcx
0x1800b92c9  jz      short loc_1800B92DB
0x1800b92cb  mov     [rcx+8], r12d
0x1800b92cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b92d6  nop     dword ptr [rax+rax+00h]
0x1800b92db  xor     eax, eax
0x1800b92dd  jmp     short loc_1800B9318
0x1800b92df  mov     edx, 0E61h
0x1800b92e4  jmp     short loc_1800B92EB
0x1800b92e6  mov     edx, 0E57h; void *
0x1800b92eb  mov     rcx, [rbp+38h]; this
0x1800b92ef  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b92f6  mov     r9d, 490h; char *
0x1800b92fc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b9301  mov     rcx, rdi; SRWLock
0x1800b9304  mov     [rdi+8], r12d
0x1800b9308  mov     ebx, eax
0x1800b930a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9311  nop     dword ptr [rax+rax+00h]
0x1800b9316  mov     eax, ebx
0x1800b9318  add     rsp, 30h
0x1800b931c  pop     r15
0x1800b931e  pop     r14
0x1800b9320  pop     r12
0x1800b9322  pop     rdi
0x1800b9323  pop     rsi
0x1800b9324  pop     rbx
0x1800b9325  pop     rbp
0x1800b9326  retn
```
