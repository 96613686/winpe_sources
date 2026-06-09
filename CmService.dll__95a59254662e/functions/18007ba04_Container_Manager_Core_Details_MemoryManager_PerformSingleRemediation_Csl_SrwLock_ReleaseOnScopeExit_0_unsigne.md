# Container::Manager::Core::Details::MemoryManager::PerformSingleRemediation(Csl::SrwLock::ReleaseOnScopeExit<0> &,unsigned __int64,unsigned __int64 &)

- ea: `0x18007ba04`
- end: `0x18007bfa2`
- name: `?PerformSingleRemediation@MemoryManager@Details@Core@Manager@Container@@AEAA?AW4MemoryRemediationAction@2345@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@_KAEA_K@Z`
- size: `1438`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::MemoryManager *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007b748`

## callees

- `0x180004bd0`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18000a10c`
- `0x18000dab0`
- `0x18001063c`
- `0x180042b58`
- `0x18007a934`
- `0x18007ad8c`
- `0x18007adac`
- `0x18007afd4`
- `0x18007ba04`
- `0x18007bfa8`
- `0x18007c61c`
- `0x18007c6b4`
- `0x18007c7ac`
- `0x18007cebc`
- `0x18007d06c`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x18007bed8`
- `ntdll!RtlRbRemoveNode` at `0x18007bed8`
- `ntdll!NtSetInformationProcess` at `0x18007bc64`
- `ntdll!NtSetInformationProcess` at `0x18007bdc2`
- `ntdll!NtSetInformationProcess` at `0x18007bc64`
- `ntdll!NtSetInformationProcess` at `0x18007bdc2`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18007bf01`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18007bf01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bd17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bd17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bb22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bd56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007be85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bb22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bd56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007be85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007bd23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007bd23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::MemoryManager::PerformSingleRemediation(
        Container::Manager::Core::Details::MemoryManager *this,
        __int64 *a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  __int64 *v4; // r14
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // ecx
  unsigned int v11; // esi
  bool v12; // r12
  __int64 v13; // rcx
  int v14; // r13d
  unsigned __int64 ProcessPrivateWorkingSetBytes; // r14
  void *v16; // rax
  Container::Manager::Core::Details *v17; // rax
  void *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rbx
  int v21; // ecx
  void *v22; // rax
  unsigned int v23; // eax
  int CompressionStoreSize; // eax
  __int64 *v25; // r12
  __int64 v26; // rcx
  const struct _GUID *v27; // rbx
  void *MemoryHostingProcess; // rax
  NTSTATUS v29; // eax
  Container::Manager::Core::Details *v30; // rax
  void *v31; // rdx
  unsigned __int64 v32; // rax
  int v34; // [rsp+20h] [rbp-E0h]
  bool v35; // [rsp+30h] [rbp-D0h]
  void *v36; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  char *v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  unsigned __int64 *v40; // [rsp+58h] [rbp-A8h]
  char v41; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD ProcessInformation[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+7Ch] [rbp-84h]
  _QWORD v46[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v40 = a4;
  v39 = a3;
  v4 = a2;
  v38 = (char *)a2;
  *a4 = 0;
  v6 = (unsigned __int64)this + 56;
  while ( 1 )
  {
    v7 = *(_QWORD *)(v6 + 8);
    v8 = *(_QWORD *)v6;
    if ( (v7 & 1) != 0 )
    {
      if ( !v8 )
        return 0;
      v8 ^= v6;
    }
    if ( !v8 )
      return 0;
    if ( (*(_QWORD *)(v6 + 8) & 1LL) != 0 )
      v9 = v7 == 1 ? 0LL : v7 ^ (v6 | 1);
    else
      v9 = *(_QWORD *)(v6 + 8);
    LODWORD(v36) = 0;
    _BitScanForward(&v10, *(_DWORD *)(v9 + 44));
    v11 = 1 << v10;
    if ( (!*(_BYTE *)(v9 + 96) || v11 == 16 && *(_QWORD *)(v9 + 128) >= *(_QWORD *)(v9 + 88))
      && (*((_BYTE *)this + 49)
       || v11 != 1
       && v11 != 2
       && v11 != 4
       && (v11 != 8 && v11 != 16 || *((int *)this + 27) < 1 || ((v11 - 8) & 0xFFFFFFF7) == 0 && !a3)) )
    {
      return 0;
    }
    *(_DWORD *)(v9 + 52) = v11;
    v12 = (*(_DWORD *)(v9 + 40) & 2) != 0;
    v13 = *v4;
    if ( *v4 )
    {
      *(_DWORD *)(v13 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v13);
      *v4 = 0;
    }
    v14 = 0;
    v35 = 1;
    ProcessPrivateWorkingSetBytes = 0;
    v37 = 0;
    switch ( v11 )
    {
      case 1u:
        Container::Manager::Core::Details::MemoryManager::ReprioritizeContainerPrivateWorkingSet(
          this,
          (const struct Container::Manager::Core::Details::ContainerMemoryContext *)v9,
          2u);
        break;
      case 2u:
        v45 = 0;
        v44 = 3;
        v27 = *(const struct _GUID **)(v9 + 24);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
          v46,
          "MemoryManager_OutSwapContainer");
        v46[0] = &CmTraceProvider::MemoryManager_OutSwapContainer::`vftable';
        CmTraceProvider::MemoryManager_OutSwapContainer::StartActivity(
          (CmTraceProvider::MemoryManager_OutSwapContainer *)v46,
          v27);
        MemoryHostingProcess = Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess((Container::Manager::Core::Details::ContainerMemoryContext *)v9);
        v29 = NtSetInformationProcess(
                MemoryHostingProcess,
                ProcessThreadStackAllocation|ProcessUserModeIOPL,
                &v44,
                0xCu);
        if ( v29 >= 0 )
        {
          wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v46, 0);
          v46[0] = &CmTraceProvider::MemoryManager_OutSwapContainer::`vftable';
          v14 = 0;
        }
        else
        {
          v14 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xA17,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
                  (const char *)(unsigned int)v29,
                  v34);
          v46[0] = &CmTraceProvider::MemoryManager_OutSwapContainer::`vftable';
        }
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v46);
        if ( v14 >= 0 )
        {
          v30 = (Container::Manager::Core::Details *)Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess((Container::Manager::Core::Details::ContainerMemoryContext *)v9);
          *(_QWORD *)(v9 + 104) = Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(v30, v31);
        }
        goto LABEL_45;
      case 4u:
      case 8u:
        if ( v11 == 4 )
        {
          v17 = (Container::Manager::Core::Details *)Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess((Container::Manager::Core::Details::ContainerMemoryContext *)v9);
          ProcessPrivateWorkingSetBytes = Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(
                                            v17,
                                            v18);
        }
        else
        {
          ProcessPrivateWorkingSetBytes = *(_QWORD *)(v9 + 112);
        }
        v19 = 3;
        ProcessInformation[0] = 3;
        ProcessInformation[1] = 1;
        v43 = 3;
        v20 = *(_QWORD *)(v9 + 24);
        v21 = *(_DWORD *)(v20 + 92) & 2;
        if ( v21 )
          v19 = 35;
        v43 = v19;
        if ( *((_BYTE *)this + 32) )
        {
          v43 = v21 != 0 ? 43 : 11;
          if ( v11 == 8 )
            v43 = (v21 != 0 ? 43 : 11) | 0x10;
        }
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
          v46,
          "MemoryManager_EmptyPrivatesContainer");
        v46[0] = &CmTraceProvider::MemoryManager_EmptyPrivatesContainer::`vftable';
        CmTraceProvider::MemoryManager_EmptyPrivatesContainer::StartActivity(
          (CmTraceProvider::MemoryManager_EmptyPrivatesContainer *)v46,
          (const struct _GUID *)v20,
          v43);
        v22 = Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess((Container::Manager::Core::Details::ContainerMemoryContext *)v9);
        v23 = NtSetInformationProcess(v22, ProcessThreadStackAllocation|ProcessUserModeIOPL, ProcessInformation, 0xCu);
        if ( (int)(v23 + 0x80000000) >= 0 && v23 != -1073741558 )
          wil::details::in1diag3::FailFast_NtStatus(
            retaddr,
            (void *)0xA9D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
            (const char *)v23,
            v34);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v46, 0);
        v46[0] = &CmTraceProvider::MemoryManager_EmptyPrivatesContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v46);
        if ( v11 == 4 && v12 )
        {
          CompressionStoreSize = Container::Manager::Core::Details::MemoryManager::GetCompressionStoreSize(
                                   this,
                                   (const struct Container::Manager::Core::Details::ContainerMemoryContext *)v9,
                                   (unsigned __int64 *)(v9 + 112));
          if ( CompressionStoreSize < 0 )
          {
            *(_QWORD *)(v9 + 112) = 0;
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x8AD,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
              (const char *)(unsigned int)CompressionStoreSize,
              v34);
          }
        }
LABEL_45:
        v6 = (unsigned __int64)this + 56;
        break;
      case 0x10u:
        v36 = 0;
        Container::Manager::Core::Details::MemoryManager::PiecemealEmptyContainerPrivateWorkingSet(
          this,
          (const struct Container::Manager::Core::Details::ContainerMemoryContext *)v9,
          0x4000000u,
          &v36,
          &v37);
        v16 = v36;
        *(_QWORD *)(v9 + 120) = v36;
        ProcessPrivateWorkingSetBytes = v37;
        *(_QWORD *)(v9 + 128) += v37;
        v35 = (unsigned __int64)v16 >= *((_QWORD *)this + 5);
        break;
      default:
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x8CF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
          0);
    }
    if ( !*((_BYTE *)this + 32) )
      goto LABEL_50;
    if ( v11 != 4 )
    {
      if ( v11 != 16 )
        goto LABEL_50;
LABEL_49:
      ProcessPrivateWorkingSetBytes = (3 * ProcessPrivateWorkingSetBytes) >> 2;
      goto LABEL_50;
    }
    if ( !v12 )
      goto LABEL_49;
    v32 = *(_QWORD *)(v9 + 112);
    if ( ProcessPrivateWorkingSetBytes < v32 )
      v32 = ProcessPrivateWorkingSetBytes;
    ProcessPrivateWorkingSetBytes -= v32;
LABEL_50:
    AcquireSRWLockExclusive((PSRWLOCK)this);
    *((_DWORD *)this + 2) = GetCurrentThreadId();
    v25 = (__int64 *)v38;
    if ( v38 == &v41 )
    {
      if ( this )
      {
        *((_DWORD *)this + 2) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)this);
      }
    }
    else
    {
      v26 = *(_QWORD *)v38;
      if ( *(_QWORD *)v38 )
      {
        *(_DWORD *)(v26 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v26);
      }
      *v25 = (__int64)this;
    }
    *(_DWORD *)(v9 + 52) = 0;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x90A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\memorymanager.cpp",
        (const char *)(unsigned int)v14,
        v34);
      goto LABEL_70;
    }
    if ( v35 )
    {
      *(_DWORD *)(v9 + 48) |= v11;
LABEL_70:
      *(_DWORD *)(v9 + 44) &= ~v11;
    }
    if ( *(_QWORD *)(v9 + 16) != -1 )
    {
      RtlRbRemoveNode(v6, v9);
      *(_QWORD *)(v9 + 16) = -1;
      if ( *(_DWORD *)(v9 + 44) )
        Csl::IntrusivePriorityQueue<Container::Manager::Core::Details::ContainerMemoryContext,0,&private: static long Container::Manager::Core::Details::MemoryManager::CompareContainerMemoryContexts(Container::Manager::Core::Details::ContainerMemoryContext const &,Container::Manager::Core::Details::ContainerMemoryContext const &)>::Push(
          v6,
          v9);
    }
    WakeConditionVariable((PCONDITION_VARIABLE)(v9 + 56));
    if ( *((_DWORD *)this + 22) )
    {
      *((_DWORD *)this + 22) = 0;
      Container::Manager::Core::Details::MemoryManager::CheckUpdateRemediationThreadPriority(this);
    }
    if ( v14 >= 0 )
    {
      *v40 = ProcessPrivateWorkingSetBytes;
      return v11;
    }
    v4 = v25;
    a3 = v39;
  }
}

```

## disassembly

```asm
0x18007ba04  mov     [rsp-8+arg_10], rbx
0x18007ba09  push    rbp
0x18007ba0a  push    rsi
0x18007ba0b  push    rdi
0x18007ba0c  push    r12
0x18007ba0e  push    r13
0x18007ba10  push    r14
0x18007ba12  push    r15
0x18007ba14  lea     rbp, [rsp-0F0h]
0x18007ba1c  sub     rsp, 1F0h
0x18007ba23  mov     rax, cs:__security_cookie
0x18007ba2a  xor     rax, rsp
0x18007ba2d  mov     [rbp+120h+var_40], rax
0x18007ba34  mov     rax, r9
0x18007ba37  mov     [rsp+220h+var_1C8], rax
0x18007ba3c  mov     [rsp+220h+var_1D0], r8
0x18007ba41  mov     r14, rdx
0x18007ba44  mov     [rsp+220h+var_1D8], rdx
0x18007ba49  mov     r15, rcx
0x18007ba4c  xor     r9d, r9d
0x18007ba4f  mov     [rax], r9
0x18007ba52  lea     rbx, [rcx+38h]
0x18007ba56  mov     rcx, [rbx+8]
0x18007ba5a  mov     rdx, rcx
0x18007ba5d  and     edx, 1
0x18007ba60  mov     rax, [rbx]
0x18007ba63  jz      short loc_18007BA71
0x18007ba65  test    rax, rax
0x18007ba68  jz      loc_18007BF43
0x18007ba6e  xor     rax, rbx
0x18007ba71  test    rax, rax
0x18007ba74  jz      loc_18007BF43
0x18007ba7a  test    rdx, rdx
0x18007ba7d  jz      short loc_18007BA96
0x18007ba7f  cmp     rcx, 1
0x18007ba83  jnz     short loc_18007BA8A
0x18007ba85  mov     rdi, r9
0x18007ba88  jmp     short loc_18007BA99
0x18007ba8a  mov     rdi, rbx
0x18007ba8d  or      rdi, 1
0x18007ba91  xor     rdi, rcx
0x18007ba94  jmp     short loc_18007BA99
0x18007ba96  mov     rdi, rcx
0x18007ba99  mov     dword ptr [rsp+220h+var_1E8], r9d
0x18007ba9e  bsf     ecx, [rdi+2Ch]
0x18007baa2  mov     esi, 1
0x18007baa7  shl     esi, cl
0x18007baa9  cmp     [rdi+60h], r9b
0x18007baad  jz      short loc_18007BAC1
0x18007baaf  cmp     esi, 10h
0x18007bab2  jnz     short loc_18007BB08
0x18007bab4  mov     rax, [rdi+58h]
0x18007bab8  cmp     [rdi+80h], rax
0x18007babf  jb      short loc_18007BB08
0x18007bac1  cmp     [r15+31h], r9b
0x18007bac5  jnz     loc_18007BF43
0x18007bacb  mov     eax, esi
0x18007bacd  sub     eax, 1
0x18007bad0  jz      short loc_18007BB08
0x18007bad2  sub     eax, 1
0x18007bad5  jz      short loc_18007BB08
0x18007bad7  sub     eax, 2
0x18007bada  jz      short loc_18007BB08
0x18007badc  sub     eax, 4
0x18007badf  jz      short loc_18007BAEA
0x18007bae1  cmp     eax, 8
0x18007bae4  jnz     loc_18007BF43
0x18007baea  cmp     dword ptr [r15+6Ch], 1
0x18007baef  jl      loc_18007BF43
0x18007baf5  lea     eax, [rsi-8]
0x18007baf8  test    eax, 0FFFFFFF7h
0x18007bafd  jnz     short loc_18007BB08
0x18007baff  test    r8, r8
0x18007bb02  jz      loc_18007BF43
0x18007bb08  mov     [rdi+34h], esi
0x18007bb0b  mov     r12d, [rdi+28h]
0x18007bb0f  shr     r12d, 1
0x18007bb12  and     r12b, 1
0x18007bb16  mov     rcx, [r14]; SRWLock
0x18007bb19  test    rcx, rcx
0x18007bb1c  jz      short loc_18007BB34
0x18007bb1e  mov     [rcx+8], r9d
0x18007bb22  call    cs:__imp_ReleaseSRWLockExclusive
0x18007bb29  nop     dword ptr [rax+rax+00h]
0x18007bb2e  xor     r9d, r9d; char *
0x18007bb31  mov     [r14], r9
0x18007bb34  mov     r13d, r9d
0x18007bb37  mov     [rsp+220h+var_1F0], 1
0x18007bb3c  mov     r14, r9
0x18007bb3f  mov     [rsp+220h+var_1E0], r9
0x18007bb44  mov     eax, esi
0x18007bb46  sub     eax, 1
0x18007bb49  jz      loc_18007BE43
0x18007bb4f  sub     eax, 1
0x18007bb52  jz      loc_18007BD6B
0x18007bb58  sub     eax, 2
0x18007bb5b  jz      short loc_18007BBB3
0x18007bb5d  sub     eax, 4
0x18007bb60  jz      short loc_18007BBB3
0x18007bb62  cmp     eax, 8
0x18007bb65  jnz     loc_18007BF89
0x18007bb6b  mov     [rsp+220h+var_1E8], r9
0x18007bb70  lea     rax, [rsp+220h+var_1E0]
0x18007bb75  mov     qword ptr [rsp+220h+var_200], rax; unsigned __int64 *
0x18007bb7a  lea     r9, [rsp+220h+var_1E8]; void **
0x18007bb7f  mov     r8d, 4000000h; unsigned __int64
0x18007bb85  mov     rdx, rdi; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x18007bb88  mov     rcx, r15; this
0x18007bb8b  call    ?PiecemealEmptyContainerPrivateWorkingSet@MemoryManager@Details@Core@Manager@Container@@AEBAXAEBUContainerMemoryContext@2345@_KPEAPEAXPEA_K@Z; Container::Manager::Core::Details::MemoryManager::PiecemealEmptyContainerPrivateWorkingSet(Container::Manager::Core::Details::ContainerMemoryContext const &,unsigned __int64,void * *,unsigned __int64 *)
0x18007bb90  mov     rax, [rsp+220h+var_1E8]
0x18007bb95  mov     [rdi+78h], rax
0x18007bb99  mov     r14, [rsp+220h+var_1E0]
0x18007bb9e  add     [rdi+80h], r14
0x18007bba5  cmp     rax, [r15+28h]
0x18007bba9  setnb   [rsp+220h+var_1F0]
0x18007bbae  jmp     loc_18007BCF7
0x18007bbb3  cmp     esi, 4
0x18007bbb6  jnz     short loc_18007BBD0
0x18007bbb8  mov     rcx, rdi; this
0x18007bbbb  call    ?GetMemoryHostingProcess@ContainerMemoryContext@Details@Core@Manager@Container@@QEBAPEAXXZ; Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(void)
0x18007bbc0  mov     rcx, rax; this
0x18007bbc3  call    ?QueryProcessPrivateWorkingSetBytes@Details@Core@Manager@Container@@YA_KPEAX@Z; Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(void *)
0x18007bbc8  mov     r14, rax
0x18007bbcb  xor     r9d, r9d
0x18007bbce  jmp     short loc_18007BBD4
0x18007bbd0  mov     r14, [rdi+70h]
0x18007bbd4  mov     eax, 3
0x18007bbd9  mov     [rsp+220h+ProcessInformation], eax
0x18007bbdd  mov     [rsp+220h+var_1B4], 1
0x18007bbe5  mov     [rsp+220h+var_1B0], eax
0x18007bbe9  mov     rbx, [rdi+18h]
0x18007bbed  mov     ecx, [rbx+5Ch]
0x18007bbf0  and     ecx, 2
0x18007bbf3  lea     edx, [rax+20h]
0x18007bbf6  cmovnz  eax, edx
0x18007bbf9  mov     [rsp+220h+var_1B0], eax
0x18007bbfd  cmp     [r15+20h], r9b
0x18007bc01  jz      short loc_18007BC1D
0x18007bc03  neg     ecx
0x18007bc05  sbb     eax, eax
0x18007bc07  and     eax, 20h
0x18007bc0a  add     eax, 0Bh
0x18007bc0d  mov     [rsp+220h+var_1B0], eax
0x18007bc11  cmp     esi, 8
0x18007bc14  jnz     short loc_18007BC1D
0x18007bc16  or      eax, 10h
0x18007bc19  mov     [rsp+220h+var_1B0], eax
0x18007bc1d  lea     rdx, aMemorymanagerE; "MemoryManager_EmptyPrivatesContainer"
0x18007bc24  lea     rcx, [rbp+120h+var_190]
0x18007bc28  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007bc2d  lea     rax, ??_7MemoryManager_EmptyPrivatesContainer@CmTraceProvider@@6B@; const CmTraceProvider::MemoryManager_EmptyPrivatesContainer::`vftable'
0x18007bc34  mov     [rbp+120h+var_190], rax
0x18007bc38  mov     r8d, [rsp+220h+var_1B0]; unsigned int
0x18007bc3d  mov     rdx, rbx; struct _GUID *
0x18007bc40  lea     rcx, [rbp+120h+var_190]; this
0x18007bc44  call    ?StartActivity@MemoryManager_EmptyPrivatesContainer@CmTraceProvider@@QEAAXAEBU_GUID@@K@Z; CmTraceProvider::MemoryManager_EmptyPrivatesContainer::StartActivity(_GUID const &,ulong)
0x18007bc49  nop
0x18007bc4a  mov     rcx, rdi; this
0x18007bc4d  call    ?GetMemoryHostingProcess@ContainerMemoryContext@Details@Core@Manager@Container@@QEBAPEAXXZ; Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(void)
0x18007bc52  mov     rcx, rax; ProcessHandle
0x18007bc55  mov     r9d, 0Ch; ProcessInformationLength
0x18007bc5b  lea     r8, [rsp+220h+ProcessInformation]; ProcessInformation
0x18007bc60  lea     edx, [r9+2Dh]; ProcessInformationClass
0x18007bc64  call    cs:__imp_NtSetInformationProcess
0x18007bc6b  nop     dword ptr [rax+rax+00h]
0x18007bc70  mov     r9d, eax; char *
0x18007bc73  mov     ecx, 80000000h
0x18007bc78  add     eax, ecx
0x18007bc7a  test    ecx, eax
0x18007bc7c  jnz     short loc_18007BC8B
0x18007bc7e  cmp     r9d, 0C000010Ah
0x18007bc85  jnz     loc_18007BF70
0x18007bc8b  xor     edx, edx
0x18007bc8d  lea     rcx, [rbp+120h+var_190]
0x18007bc91  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007bc96  lea     rax, ??_7MemoryManager_EmptyPrivatesContainer@CmTraceProvider@@6B@; const CmTraceProvider::MemoryManager_EmptyPrivatesContainer::`vftable'
0x18007bc9d  mov     [rbp+120h+var_190], rax
0x18007bca1  lea     rcx, [rbp+120h+var_190]
0x18007bca5  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18007bcaa  lea     rcx, [rbp+120h+var_190]
0x18007bcae  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18007bcb3  cmp     esi, 4
0x18007bcb6  jnz     short loc_18007BCF3
0x18007bcb8  test    r12b, r12b
0x18007bcbb  jz      short loc_18007BCF3
0x18007bcbd  lea     r8, [rdi+70h]; unsigned __int64 *
0x18007bcc1  mov     rdx, rdi; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x18007bcc4  mov     rcx, r15; this
0x18007bcc7  call    ?GetCompressionStoreSize@MemoryManager@Details@Core@Manager@Container@@AEBAJAEBUContainerMemoryContext@2345@AEA_K@Z; Container::Manager::Core::Details::MemoryManager::GetCompressionStoreSize(Container::Manager::Core::Details::ContainerMemoryContext const &,unsigned __int64 &)
0x18007bccc  test    eax, eax
0x18007bcce  jns     short loc_18007BCF3
0x18007bcd0  mov     qword ptr [rdi+70h], 0
0x18007bcd8  mov     rcx, [rbp+128h]; this
0x18007bcdf  mov     r9d, eax; char *
0x18007bce2  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007bce9  mov     edx, 8ADh; void *
0x18007bcee  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007bcf3  lea     rbx, [r15+38h]
0x18007bcf7  cmp     byte ptr [r15+20h], 0
0x18007bcfc  jz      short loc_18007BD14
0x18007bcfe  cmp     esi, 4
0x18007bd01  jz      loc_18007BE59
0x18007bd07  cmp     esi, 10h
0x18007bd0a  jnz     short loc_18007BD14
0x18007bd0c  lea     r14, [r14+r14*2]
0x18007bd10  shr     r14, 2
0x18007bd14  mov     rcx, r15; SRWLock
0x18007bd17  call    cs:__imp_AcquireSRWLockExclusive
0x18007bd1e  nop     dword ptr [rax+rax+00h]
0x18007bd23  call    cs:__imp_GetCurrentThreadId
0x18007bd2a  nop     dword ptr [rax+rax+00h]
0x18007bd2f  mov     [r15+8], eax
0x18007bd33  lea     rax, [rsp+220h+var_1C0]
0x18007bd38  mov     r12, [rsp+220h+var_1D8]
0x18007bd3d  cmp     r12, rax
0x18007bd40  jz      loc_18007BE75
0x18007bd46  mov     rcx, [r12]; SRWLock
0x18007bd4a  test    rcx, rcx
0x18007bd4d  jz      short loc_18007BD62
0x18007bd4f  mov     dword ptr [rcx+8], 0
0x18007bd56  call    cs:__imp_ReleaseSRWLockExclusive
0x18007bd5d  nop     dword ptr [rax+rax+00h]
0x18007bd62  mov     [r12], r15
0x18007bd66  jmp     loc_18007BE91
0x18007bd6b  mov     [rsp+220h+var_1A4], 0
0x18007bd74  mov     [rsp+220h+var_1A8], 3
0x18007bd7c  mov     rbx, [rdi+18h]
0x18007bd80  lea     rdx, aMemorymanagerO; "MemoryManager_OutSwapContainer"
0x18007bd87  lea     rcx, [rbp+120h+var_190]
0x18007bd8b  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007bd90  lea     r13, ??_7MemoryManager_OutSwapContainer@CmTraceProvider@@6B@; const CmTraceProvider::MemoryManager_OutSwapContainer::`vftable'
0x18007bd97  mov     [rbp+120h+var_190], r13
0x18007bd9b  mov     rdx, rbx; struct _GUID *
0x18007bd9e  lea     rcx, [rbp+120h+var_190]; this
0x18007bda2  call    ?StartActivity@MemoryManager_OutSwapContainer@CmTraceProvider@@QEAAXAEBU_GUID@@@Z; CmTraceProvider::MemoryManager_OutSwapContainer::StartActivity(_GUID const &)
0x18007bda7  nop
0x18007bda8  mov     rcx, rdi; this
0x18007bdab  call    ?GetMemoryHostingProcess@ContainerMemoryContext@Details@Core@Manager@Container@@QEBAPEAXXZ; Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(void)
0x18007bdb0  mov     rcx, rax; ProcessHandle
0x18007bdb3  mov     r9d, 0Ch; ProcessInformationLength
0x18007bdb9  lea     r8, [rsp+220h+var_1A8]; ProcessInformation
0x18007bdbe  lea     edx, [r9+2Dh]; ProcessInformationClass
0x18007bdc2  call    cs:__imp_NtSetInformationProcess
0x18007bdc9  nop     dword ptr [rax+rax+00h]
0x18007bdce  test    eax, eax
0x18007bdd0  jns     short loc_18007BDFD
0x18007bdd2  mov     rcx, [rbp+128h]; this
0x18007bdd9  mov     r9d, eax; char *
0x18007bddc  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007bde3  mov     edx, 0A17h; void *
0x18007bde8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007bded  mov     r13d, eax
0x18007bdf0  lea     rax, ??_7MemoryManager_OutSwapContainer@CmTraceProvider@@6B@; const CmTraceProvider::MemoryManager_OutSwapContainer::`vftable'
0x18007bdf7  mov     [rbp+120h+var_190], rax
0x18007bdfb  jmp     short loc_18007BE0F
0x18007bdfd  xor     edx, edx
0x18007bdff  lea     rcx, [rbp+120h+var_190]
0x18007be03  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007be08  mov     [rbp+120h+var_190], r13
0x18007be0c  xor     r13d, r13d
0x18007be0f  lea     rcx, [rbp+120h+var_190]
0x18007be13  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18007be18  lea     rcx, [rbp+120h+var_190]
0x18007be1c  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18007be21  test    r13d, r13d
0x18007be24  js      loc_18007BCF3
0x18007be2a  mov     rcx, rdi; this
0x18007be2d  call    ?GetMemoryHostingProcess@ContainerMemoryContext@Details@Core@Manager@Container@@QEBAPEAXXZ; Container::Manager::Core::Details::ContainerMemoryContext::GetMemoryHostingProcess(void)
0x18007be32  mov     rcx, rax; this
0x18007be35  call    ?QueryProcessPrivateWorkingSetBytes@Details@Core@Manager@Container@@YA_KPEAX@Z; Container::Manager::Core::Details::QueryProcessPrivateWorkingSetBytes(void *)
0x18007be3a  mov     [rdi+68h], rax
0x18007be3e  jmp     loc_18007BCF3
0x18007be43  mov     r8d, 2; unsigned int
0x18007be49  mov     rdx, rdi; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x18007be4c  mov     rcx, r15; this
0x18007be4f  call    ?ReprioritizeContainerPrivateWorkingSet@MemoryManager@Details@Core@Manager@Container@@AEBAXAEBUContainerMemoryContext@2345@K@Z; Container::Manager::Core::Details::MemoryManager::ReprioritizeContainerPrivateWorkingSet(Container::Manager::Core::Details::ContainerMemoryContext const &,ulong)
0x18007be54  jmp     loc_18007BCF7
0x18007be59  test    r12b, r12b
0x18007be5c  jz      loc_18007BD0C
0x18007be62  mov     rax, [rdi+70h]
0x18007be66  cmp     r14, rax
0x18007be69  cmovb   rax, r14
0x18007be6d  sub     r14, rax
0x18007be70  jmp     loc_18007BD14
0x18007be75  test    r15, r15
0x18007be78  jz      short loc_18007BE91
0x18007be7a  mov     dword ptr [r15+8], 0
0x18007be82  mov     rcx, r15; SRWLock
0x18007be85  call    cs:__imp_ReleaseSRWLockExclusive
0x18007be8c  nop     dword ptr [rax+rax+00h]
0x18007be91  mov     dword ptr [rdi+34h], 0
0x18007be98  test    r13d, r13d
0x18007be9b  js      short loc_18007BEA9
0x18007be9d  cmp     [rsp+220h+var_1F0], 0
0x18007bea2  jz      short loc_18007BECB
0x18007bea4  or      [rdi+30h], esi
0x18007bea7  jmp     short loc_18007BEC4
0x18007bea9  mov     rcx, [rbp+128h]; this
0x18007beb0  mov     r9d, r13d; char *
0x18007beb3  lea     r8, aOnecoreBaseGen_32; "onecore\\base\\gendrv\\silos\\clem\\cor"...
  ... truncated ...
```
