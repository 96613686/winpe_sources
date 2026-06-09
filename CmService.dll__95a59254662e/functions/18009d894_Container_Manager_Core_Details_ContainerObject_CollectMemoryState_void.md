# Container::Manager::Core::Details::ContainerObject::CollectMemoryState(void *)

- ea: `0x18009d894`
- end: `0x18009db10`
- name: `?CollectMemoryState@ContainerObject@Details@Core@Manager@Container@@QEAAJPEAX@Z`
- size: `636`
- prototype: `int(Container::Manager::Core::Details::ContainerObject *__hidden this, void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180020a30`
- `0x1800769dc`
- `0x1800bad00`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x1800313c0`
- `0x180032304`
- `0x18009b018`
- `0x18009d894`
- `0x18009db18`
- `0x1800ac950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d937`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d9a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009dab5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d937`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d9a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009dab5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d984`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d9f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009da2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009dadf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d984`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d9f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009da2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009dadf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009dac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009dac1`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateEmptyRuntimeStateFile` at `0x18009da3e`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateEmptyRuntimeStateFile` at `0x18009da3e`

## string_xrefs

- `0x18009da54`: `Failed to create empty runtime state file at %ws`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::CollectMemoryState(
        Container::Manager::Core::Details::ContainerObject *this,
        void *a2)
{
  unsigned int v3; // ebx
  int FinalPathByHandle; // eax
  RTL_SRWLOCK *v6; // rbx
  unsigned int v7; // eax
  RTL_SRWLOCK *v8; // rcx
  int v9; // esi
  unsigned int EmptyRuntimeStateFile; // edi
  int v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+20h] [rbp-38h]
  PCWSTR runtimeStateFilePath[2]; // [rsp+30h] [rbp-28h] BYREF
  _WORD v14[12]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  PSRWLOCK SRWLock; // [rsp+80h] [rbp+28h] BYREF

  if ( *((_DWORD *)this + 22) != 1 )
  {
    v3 = -2147024846;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x80070032LL,
      v11);
    return v3;
  }
  runtimeStateFilePath[0] = v14;
  runtimeStateFilePath[1] = v14;
  v14[0] = 0;
  FinalPathByHandle = Csl::GetFinalPathByHandle(a2, 0, (unsigned int)runtimeStateFilePath, (struct Path *)a2);
  v3 = FinalPathByHandle;
  if ( FinalPathByHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)FinalPathByHandle,
      v11);
    if ( runtimeStateFilePath[0] != v14 )
      operator delete((void *)runtimeStateFilePath[0], (const struct std::nothrow_t *)&std::nothrow);
    return v3;
  }
  v6 = (RTL_SRWLOCK *)((char *)this + 456);
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  *((_DWORD *)this + 116) = GetCurrentThreadId();
  v7 = *((_DWORD *)this + 218) - 2;
  SRWLock = (PSRWLOCK)((char *)this + 456);
  if ( v7 <= 2 )
  {
    Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
      this,
      &SRWLock);
    v8 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v8);
    }
    v9 = Container::Manager::Core::Details::ContainerObject::CollectMemoryStateWakeReferenceAcquired(
           this,
           (const struct Path *)runtimeStateFilePath);
    AcquireSRWLockExclusive((PSRWLOCK)this + 57);
    *((_DWORD *)this + 116) = GetCurrentThreadId();
    Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(this);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v9,
        v11);
      if ( this != (Container::Manager::Core::Details::ContainerObject *)-456LL )
      {
        *((_DWORD *)this + 116) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
      }
      if ( runtimeStateFilePath[0] != v14 )
        operator delete((void *)runtimeStateFilePath[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v9;
    }
    goto LABEL_23;
  }
  if ( this != (Container::Manager::Core::Details::ContainerObject *)-456LL )
  {
    *((_DWORD *)this + 116) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
  }
  EmptyRuntimeStateFile = HcsCreateEmptyRuntimeStateFile(runtimeStateFilePath[0]);
  if ( (EmptyRuntimeStateFile & 0x80000000) == 0 )
  {
    AcquireSRWLockExclusive(v6);
    LODWORD(v6[1].Ptr) = GetCurrentThreadId();
LABEL_23:
    if ( v6 )
    {
      LODWORD(v6[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v6);
    }
    if ( runtimeStateFilePath[0] != v14 )
      operator delete((void *)runtimeStateFilePath[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x4C4,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
    (const char *)EmptyRuntimeStateFile,
    (int)"Failed to create empty runtime state file at %ws",
    (const char *)runtimeStateFilePath[0]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4FD,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)EmptyRuntimeStateFile,
    v12);
  if ( runtimeStateFilePath[0] != v14 )
    operator delete((void *)runtimeStateFilePath[0], (const struct std::nothrow_t *)&std::nothrow);
  return EmptyRuntimeStateFile;
}

```

## disassembly

```asm
0x18009d894  push    rbp
0x18009d896  push    rbx
0x18009d897  push    rsi
0x18009d898  push    rdi
0x18009d899  mov     rbp, rsp
0x18009d89c  sub     rsp, 58h
0x18009d8a0  cmp     dword ptr [rcx+58h], 1
0x18009d8a4  mov     r9, rdx; struct Path *
0x18009d8a7  mov     rdi, rcx
0x18009d8aa  jz      short loc_18009D8D0
0x18009d8ac  mov     rcx, [rbp+20h]; this
0x18009d8b0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d8b7  mov     ebx, 80070032h
0x18009d8bc  mov     edx, 4D0h; void *
0x18009d8c1  mov     r9d, ebx; char *
0x18009d8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d8c9  mov     eax, ebx
0x18009d8cb  jmp     loc_18009DB06
0x18009d8d0  lea     rax, [rbp+var_18]
0x18009d8d4  xor     edx, edx; dwFlags
0x18009d8d6  mov     [rbp+runtimeStateFilePath], rax
0x18009d8da  lea     r8, [rbp+runtimeStateFilePath]; unsigned int
0x18009d8de  lea     rax, [rbp+var_18]
0x18009d8e2  mov     rcx, r9; hFile
0x18009d8e5  mov     [rbp+var_20], rax
0x18009d8e9  xor     eax, eax
0x18009d8eb  mov     [rbp+var_18], ax
0x18009d8ef  call    ?GetFinalPathByHandle@Csl@@YAJPEAXKAEAVPath@1@@Z; Csl::GetFinalPathByHandle(void *,ulong,Csl::Path &)
0x18009d8f4  mov     ebx, eax
0x18009d8f6  test    eax, eax
0x18009d8f8  jns     short loc_18009D92D
0x18009d8fa  mov     rcx, [rbp+20h]; this
0x18009d8fe  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d905  mov     r9d, eax; char *
0x18009d908  mov     edx, 4D6h; void *
0x18009d90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d912  mov     rcx, [rbp+runtimeStateFilePath]; void *
0x18009d916  lea     rax, [rbp+var_18]
0x18009d91a  cmp     rcx, rax
0x18009d91d  jz      short loc_18009D8C9
0x18009d91f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009d926  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009d92b  jmp     short loc_18009D8C9
0x18009d92d  lea     rbx, [rdi+1C8h]
0x18009d934  mov     rcx, rbx; SRWLock
0x18009d937  call    cs:__imp_AcquireSRWLockExclusive
0x18009d93e  nop     dword ptr [rax+rax+00h]
0x18009d943  call    cs:__imp_GetCurrentThreadId
0x18009d94a  nop     dword ptr [rax+rax+00h]
0x18009d94f  mov     [rbx+8], eax
0x18009d952  mov     eax, [rdi+368h]
0x18009d958  sub     eax, 2
0x18009d95b  mov     [rbp+SRWLock], rbx
0x18009d95f  cmp     eax, 2
0x18009d962  ja      loc_18009DA1F
0x18009d968  lea     rdx, [rbp+SRWLock]
0x18009d96c  mov     rcx, rdi
0x18009d96f  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009d974  mov     rcx, [rbp+SRWLock]; SRWLock
0x18009d978  test    rcx, rcx
0x18009d97b  jz      short loc_18009D990
0x18009d97d  mov     dword ptr [rcx+8], 0
0x18009d984  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d98b  nop     dword ptr [rax+rax+00h]
0x18009d990  lea     rdx, [rbp+runtimeStateFilePath]; struct Path *
0x18009d994  mov     rcx, rdi; this
0x18009d997  call    ?CollectMemoryStateWakeReferenceAcquired@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::CollectMemoryStateWakeReferenceAcquired(Csl::Path const &)
0x18009d99c  mov     rcx, rbx; SRWLock
0x18009d99f  mov     esi, eax
0x18009d9a1  call    cs:__imp_AcquireSRWLockExclusive
0x18009d9a8  nop     dword ptr [rax+rax+00h]
0x18009d9ad  call    cs:__imp_GetCurrentThreadId
0x18009d9b4  nop     dword ptr [rax+rax+00h]
0x18009d9b9  mov     rcx, rdi; this
0x18009d9bc  mov     [rbx+8], eax
0x18009d9bf  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x18009d9c4  test    esi, esi
0x18009d9c6  jns     loc_18009DAD0
0x18009d9cc  mov     rcx, [rbp+20h]; this
0x18009d9d0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d9d7  mov     r9d, esi; char *
0x18009d9da  mov     edx, 4F4h; void *
0x18009d9df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d9e4  test    rbx, rbx
0x18009d9e7  jz      short loc_18009D9FF
0x18009d9e9  mov     rcx, rbx; SRWLock
0x18009d9ec  mov     dword ptr [rbx+8], 0
0x18009d9f3  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d9fa  nop     dword ptr [rax+rax+00h]
0x18009d9ff  mov     rcx, [rbp+runtimeStateFilePath]; void *
0x18009da03  lea     rax, [rbp+var_18]
0x18009da07  cmp     rcx, rax
0x18009da0a  jz      short loc_18009DA18
0x18009da0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009da13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009da18  mov     eax, esi
0x18009da1a  jmp     loc_18009DB06
0x18009da1f  test    rbx, rbx
0x18009da22  jz      short loc_18009DA3A
0x18009da24  mov     rcx, rbx; SRWLock
0x18009da27  mov     dword ptr [rbx+8], 0
0x18009da2e  call    cs:__imp_ReleaseSRWLockExclusive
0x18009da35  nop     dword ptr [rax+rax+00h]
0x18009da3a  mov     rcx, [rbp+runtimeStateFilePath]; runtimeStateFilePath
0x18009da3e  call    cs:__imp_HcsCreateEmptyRuntimeStateFile
0x18009da45  nop     dword ptr [rax+rax+00h]
0x18009da4a  mov     edi, eax
0x18009da4c  test    eax, eax
0x18009da4e  jns     short loc_18009DAB2
0x18009da50  mov     rdx, [rbp+runtimeStateFilePath]
0x18009da54  lea     rax, aFailedToCreate_2; "Failed to create empty runtime state fi"...
0x18009da5b  mov     rcx, [rbp+20h]; this
0x18009da5f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x18009da66  mov     [rsp+58h+var_30], rdx; char *
0x18009da6b  mov     r9d, edi; char *
0x18009da6e  mov     edx, 4C4h; void *
0x18009da73  mov     qword ptr [rsp+58h+var_38], rax; int
0x18009da78  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009da7d  mov     rcx, [rbp+20h]; this
0x18009da81  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009da88  mov     r9d, edi; char *
0x18009da8b  mov     edx, 4FDh; void *
0x18009da90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009da95  mov     rcx, [rbp+runtimeStateFilePath]; void *
0x18009da99  lea     rax, [rbp+var_18]
0x18009da9d  cmp     rcx, rax
0x18009daa0  jz      short loc_18009DAAE
0x18009daa2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009daa9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009daae  mov     eax, edi
0x18009dab0  jmp     short loc_18009DB06
0x18009dab2  mov     rcx, rbx; SRWLock
0x18009dab5  call    cs:__imp_AcquireSRWLockExclusive
0x18009dabc  nop     dword ptr [rax+rax+00h]
0x18009dac1  call    cs:__imp_GetCurrentThreadId
0x18009dac8  nop     dword ptr [rax+rax+00h]
0x18009dacd  mov     [rbx+8], eax
0x18009dad0  test    rbx, rbx
0x18009dad3  jz      short loc_18009DAEB
0x18009dad5  mov     rcx, rbx; SRWLock
0x18009dad8  mov     dword ptr [rbx+8], 0
0x18009dadf  call    cs:__imp_ReleaseSRWLockExclusive
0x18009dae6  nop     dword ptr [rax+rax+00h]
0x18009daeb  mov     rcx, [rbp+runtimeStateFilePath]; void *
0x18009daef  lea     rax, [rbp+var_18]
0x18009daf3  cmp     rcx, rax
0x18009daf6  jz      short loc_18009DB04
0x18009daf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009daff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009db04  xor     eax, eax
0x18009db06  add     rsp, 58h
0x18009db0a  pop     rdi
0x18009db0b  pop     rsi
0x18009db0c  pop     rbx
0x18009db0d  pop     rbp
0x18009db0e  retn
```
