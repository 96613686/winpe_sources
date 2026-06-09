# Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(Csl::Path const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800b8d48`
- end: `0x1800b9039`
- name: `?UnmapSharedFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@7@@Z`
- size: `753`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001e850`
- `0x1800a3768`
- `0x1800b8344`
- `0x1800b86f4`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x18000dad8`
- `0x1800785d4`
- `0x1800982a8`
- `0x1800ad4e0`
- `0x1800b8d48`
- `0x1800ba6b8`
- `0x1800ba77c`
- `0x180125384`
- `0x180198404`
- `0x180198494`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b8ecd`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b8ecd`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b8de8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b8de8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8e63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8f78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8e63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8eb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8f3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8fc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8eb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8f3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8f84`

## pseudocode

```c
int __fastcall Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(
        __int64 a1,
        __int64 a2,
        PSRWLOCK *a3)
{
  __int64 v3; // rbp
  __int64 v7; // rax
  unsigned int v9; // r12d
  __int64 v10; // rbx
  __int64 v11; // rbx
  PSRWLOCK v12; // rcx
  RTL_SRWLOCK *v13; // rdi
  int v14; // r14d
  PSRWLOCK v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // r14
  PSRWLOCK v21; // rcx
  PSRWLOCK v22; // rcx
  unsigned int v23; // [rsp+20h] [rbp-48h] BYREF
  char v24; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v26; // [rsp+70h] [rbp+8h] BYREF
  char v27; // [rsp+88h] [rbp+20h] BYREF

  v3 = a1 + 736;
  v7 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
         a1 + 736,
         a2);
  if ( v7 == v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1607,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
             (const char *)0x490,
             v23);
  v9 = 0;
  while ( 1 )
  {
    v10 = *(_QWORD *)(v7 + 72);
    if ( v10 == v7 + 56 )
      break;
    v11 = *(_QWORD *)(v10 + 56);
    if ( *(_BYTE *)v11 )
    {
      v26 = 0;
      Csl::RundownReference::TryAcquireRundownProtection(
        (Csl::RundownReference *)(v11 + 296),
        (struct Csl::RundownProtection *)&v26);
      LODWORD((*a3)[1].Ptr) = 0;
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v11 + 288), *a3, 0xFFFFFFFF, 0);
      LODWORD((*a3)[1].Ptr) = GetCurrentThreadId();
      Csl::RundownProtection::Reset((Csl::RundownProtection *)&v26);
      v7 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
             v3,
             a2);
      if ( v7 == v3 )
        return 0;
    }
    else
    {
      *(_BYTE *)v11 = 1;
      v12 = *a3;
      if ( *a3 )
      {
        LODWORD(v12[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v12);
        *a3 = 0;
      }
      v13 = (RTL_SRWLOCK *)(a1 + 456);
      v14 = Container::Manager::Hcs::ComputeSystem::UnmapSharedFolder(*(_QWORD *)(a1 + 1256), v11 + 8, v9);
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
      *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
      if ( a3 == (PSRWLOCK *)&v23 )
      {
        if ( a1 != -456 )
        {
          *(_DWORD *)(a1 + 464) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 456));
        }
      }
      else
      {
        v15 = *a3;
        if ( *a3 )
        {
          LODWORD(v15[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v15);
        }
        *a3 = v13;
      }
      *(_BYTE *)v11 = 0;
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v11 + 288));
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x164B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v14,
          v23);
        return v14;
      }
      v16 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
              v3,
              a2);
      v17 = v11 + 48;
      if ( !*(_BYTE *)(v11 + 232) )
        v17 = v11 + 240;
      v18 = v16 + 56;
      v19 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
              v16 + 56,
              v17);
      v20 = *(_QWORD *)(v19 + 56);
      *(_QWORD *)(v19 + 56) = 0;
      utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::erase(
        v18,
        &v27,
        v19);
      v21 = *a3;
      if ( *a3 )
      {
        LODWORD(v21[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v21);
        *a3 = 0;
      }
      Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v20 + 296));
      if ( v20 )
      {
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v20 + 8));
        operator delete((void *)v20, (const struct std::nothrow_t *)0x138);
      }
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
      *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
      if ( a3 == (PSRWLOCK *)&v24 )
      {
        if ( a1 != -456 )
        {
          *(_DWORD *)(a1 + 464) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 456));
        }
      }
      else
      {
        v22 = *a3;
        if ( *a3 )
        {
          LODWORD(v22[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v22);
        }
        *a3 = v13;
      }
      v7 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
             v3,
             a2);
      if ( v7 == v3 )
        return 0;
      v9 |= 1u;
    }
  }
  if ( v7 != v3 )
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::erase(
      v3,
      &v26,
      v7);
  return 0;
}

```

## disassembly

```asm
0x1800b8d48  mov     [rsp+arg_8], rbx
0x1800b8d4d  push    rbp
0x1800b8d4e  push    rsi
0x1800b8d4f  push    rdi
0x1800b8d50  push    r12
0x1800b8d52  push    r13
0x1800b8d54  push    r14
0x1800b8d56  push    r15
0x1800b8d58  sub     rsp, 30h
0x1800b8d5c  lea     rbp, [rcx+2E0h]
0x1800b8d63  mov     r13, rcx
0x1800b8d66  mov     rcx, rbp
0x1800b8d69  mov     rsi, r8
0x1800b8d6c  mov     r15, rdx
0x1800b8d6f  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b8d74  cmp     rax, rbp
0x1800b8d77  jnz     short loc_1800B8D9A
0x1800b8d79  mov     rcx, [rsp+68h]; this
0x1800b8d7e  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b8d85  mov     r9d, 490h; char *
0x1800b8d8b  mov     edx, 1607h; void *
0x1800b8d90  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b8d95  jmp     loc_1800B9023
0x1800b8d9a  xor     r14d, r14d
0x1800b8d9d  mov     r12d, r14d
0x1800b8da0  mov     rbx, [rax+48h]
0x1800b8da4  lea     rcx, [rax+38h]
0x1800b8da8  cmp     rbx, rcx
0x1800b8dab  jz      loc_1800B900C
0x1800b8db1  mov     rbx, [rbx+38h]
0x1800b8db5  cmp     [rbx], r14b
0x1800b8db8  jz      short loc_1800B8E25
0x1800b8dba  lea     rcx, [rbx+128h]; this
0x1800b8dc1  mov     [rsp+68h+arg_0], r14
0x1800b8dc6  lea     rdx, [rsp+68h+arg_0]; struct Csl::RundownProtection *
0x1800b8dcb  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800b8dd0  mov     rax, [rsi]
0x1800b8dd3  lea     rcx, [rbx+120h]; ConditionVariable
0x1800b8dda  xor     r9d, r9d; Flags
0x1800b8ddd  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800b8de1  mov     [rax+8], r14d
0x1800b8de5  mov     rdx, [rsi]; SRWLock
0x1800b8de8  call    cs:__imp_SleepConditionVariableSRW
0x1800b8def  nop     dword ptr [rax+rax+00h]
0x1800b8df4  call    cs:__imp_GetCurrentThreadId
0x1800b8dfb  nop     dword ptr [rax+rax+00h]
0x1800b8e00  mov     rcx, [rsi]
0x1800b8e03  mov     [rcx+8], eax
0x1800b8e06  lea     rcx, [rsp+68h+arg_0]; this
0x1800b8e0b  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800b8e10  mov     rdx, r15
0x1800b8e13  mov     rcx, rbp
0x1800b8e16  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b8e1b  cmp     rax, rbp
0x1800b8e1e  jnz     short loc_1800B8DA0
0x1800b8e20  jmp     loc_1800B9021
0x1800b8e25  mov     byte ptr [rbx], 1
0x1800b8e28  mov     rcx, [rsi]; SRWLock
0x1800b8e2b  test    rcx, rcx
0x1800b8e2e  jz      short loc_1800B8E43
0x1800b8e30  mov     [rcx+8], r14d
0x1800b8e34  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8e3b  nop     dword ptr [rax+rax+00h]
0x1800b8e40  mov     [rsi], r14
0x1800b8e43  mov     rcx, [r13+4E8h]
0x1800b8e4a  lea     rdx, [rbx+8]
0x1800b8e4e  mov     r8d, r12d
0x1800b8e51  call    ?UnmapSharedFolder@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVMappedFolderConfiguration@234@W4UnmapSharedFolderFlags@234@@Z; Container::Manager::Hcs::ComputeSystem::UnmapSharedFolder(Container::Manager::Hcs::MappedFolderConfiguration const &,Container::Manager::Hcs::UnmapSharedFolderFlags)
0x1800b8e56  lea     rdi, [r13+1C8h]
0x1800b8e5d  mov     r14d, eax
0x1800b8e60  mov     rcx, rdi; SRWLock
0x1800b8e63  call    cs:__imp_AcquireSRWLockExclusive
0x1800b8e6a  nop     dword ptr [rax+rax+00h]
0x1800b8e6f  call    cs:__imp_GetCurrentThreadId
0x1800b8e76  nop     dword ptr [rax+rax+00h]
0x1800b8e7b  mov     [rdi+8], eax
0x1800b8e7e  lea     rax, [rsp+68h+var_48]
0x1800b8e83  cmp     rsi, rax
0x1800b8e86  jz      short loc_1800B8EA8
0x1800b8e88  mov     rcx, [rsi]; SRWLock
0x1800b8e8b  test    rcx, rcx
0x1800b8e8e  jz      short loc_1800B8EA3
0x1800b8e90  mov     dword ptr [rcx+8], 0
0x1800b8e97  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8e9e  nop     dword ptr [rax+rax+00h]
0x1800b8ea3  mov     [rsi], rdi
0x1800b8ea6  jmp     short loc_1800B8EC3
0x1800b8ea8  test    rdi, rdi
0x1800b8eab  jz      short loc_1800B8EC3
0x1800b8ead  mov     rcx, rdi; SRWLock
0x1800b8eb0  mov     dword ptr [rdi+8], 0
0x1800b8eb7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8ebe  nop     dword ptr [rax+rax+00h]
0x1800b8ec3  lea     rcx, [rbx+120h]; ConditionVariable
0x1800b8eca  mov     byte ptr [rbx], 0
0x1800b8ecd  call    cs:__imp_WakeAllConditionVariable
0x1800b8ed4  nop     dword ptr [rax+rax+00h]
0x1800b8ed9  test    r14d, r14d
0x1800b8edc  js      loc_1800B8FEE
0x1800b8ee2  mov     rdx, r15
0x1800b8ee5  mov     rcx, rbp
0x1800b8ee8  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b8eed  cmp     byte ptr [rbx+0E8h], 0
0x1800b8ef4  lea     rdx, [rbx+30h]
0x1800b8ef8  jnz     short loc_1800B8F01
0x1800b8efa  lea     rdx, [rbx+0F0h]
0x1800b8f01  lea     rbx, [rax+38h]
0x1800b8f05  mov     rcx, rbx
0x1800b8f08  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b8f0d  mov     r8, rax
0x1800b8f10  lea     rdx, [rsp+68h+arg_18]
0x1800b8f18  mov     rcx, rbx
0x1800b8f1b  mov     r14, [rax+38h]
0x1800b8f1f  mov     qword ptr [rax+38h], 0
0x1800b8f27  call    ?erase@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::erase(utl::_TreeConstIt<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>)
0x1800b8f2c  mov     rcx, [rsi]; SRWLock
0x1800b8f2f  test    rcx, rcx
0x1800b8f32  jz      short loc_1800B8F4E
0x1800b8f34  mov     dword ptr [rcx+8], 0
0x1800b8f3b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8f42  nop     dword ptr [rax+rax+00h]
0x1800b8f47  mov     qword ptr [rsi], 0
0x1800b8f4e  lea     rcx, [r14+128h]; this
0x1800b8f55  call    ?WaitForRundownProtectionRelease@RundownReference@Csl@@QEAAXXZ; Csl::RundownReference::WaitForRundownProtectionRelease(void)
0x1800b8f5a  test    r14, r14
0x1800b8f5d  jz      short loc_1800B8F75
0x1800b8f5f  lea     rcx, [r14+8]; this
0x1800b8f63  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800b8f68  mov     edx, 138h; struct std::nothrow_t *
0x1800b8f6d  mov     rcx, r14; void *
0x1800b8f70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8f75  mov     rcx, rdi; SRWLock
0x1800b8f78  call    cs:__imp_AcquireSRWLockExclusive
0x1800b8f7f  nop     dword ptr [rax+rax+00h]
0x1800b8f84  call    cs:__imp_GetCurrentThreadId
0x1800b8f8b  nop     dword ptr [rax+rax+00h]
0x1800b8f90  mov     [rdi+8], eax
0x1800b8f93  xor     r14d, r14d
0x1800b8f96  lea     rax, [rsp+68h+var_40]
0x1800b8f9b  cmp     rsi, rax
0x1800b8f9e  jz      short loc_1800B8FBD
0x1800b8fa0  mov     rcx, [rsi]; SRWLock
0x1800b8fa3  test    rcx, rcx
0x1800b8fa6  jz      short loc_1800B8FB8
0x1800b8fa8  mov     [rcx+8], r14d
0x1800b8fac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8fb3  nop     dword ptr [rax+rax+00h]
0x1800b8fb8  mov     [rsi], rdi
0x1800b8fbb  jmp     short loc_1800B8FD5
0x1800b8fbd  test    rdi, rdi
0x1800b8fc0  jz      short loc_1800B8FD5
0x1800b8fc2  mov     rcx, rdi; SRWLock
0x1800b8fc5  mov     [rdi+8], r14d
0x1800b8fc9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8fd0  nop     dword ptr [rax+rax+00h]
0x1800b8fd5  mov     rdx, r15
0x1800b8fd8  mov     rcx, rbp
0x1800b8fdb  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b8fe0  cmp     rax, rbp
0x1800b8fe3  jz      short loc_1800B9021
0x1800b8fe5  or      r12d, 1
0x1800b8fe9  jmp     loc_1800B8DA0
0x1800b8fee  mov     rcx, [rsp+68h]; this
0x1800b8ff3  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b8ffa  mov     r9d, r14d; char *
0x1800b8ffd  mov     edx, 164Bh; void *
0x1800b9002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9007  mov     eax, r14d
0x1800b900a  jmp     short loc_1800B9023
0x1800b900c  cmp     rax, rbp
0x1800b900f  jz      short loc_1800B9021
0x1800b9011  mov     r8, rax
0x1800b9014  lea     rdx, [rsp+68h+arg_0]
0x1800b9019  mov     rcx, rbp
0x1800b901c  call    ?erase@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@2@V?$_TreeConstIt@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@2@@Z
0x1800b9021  xor     eax, eax
0x1800b9023  mov     rbx, [rsp+68h+arg_8]
0x1800b9028  add     rsp, 30h
0x1800b902c  pop     r15
0x1800b902e  pop     r14
0x1800b9030  pop     r13
0x1800b9032  pop     r12
0x1800b9034  pop     rdi
0x1800b9035  pop     rsi
0x1800b9036  pop     rbp
0x1800b9037  retn
```
