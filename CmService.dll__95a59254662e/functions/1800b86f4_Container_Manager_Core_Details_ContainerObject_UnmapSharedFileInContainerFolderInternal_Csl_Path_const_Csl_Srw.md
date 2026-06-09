# Container::Manager::Core::Details::ContainerObject::UnmapSharedFileInContainerFolderInternal(Csl::Path const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800b86f4`
- end: `0x1800b8d41`
- name: `?UnmapSharedFileInContainerFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@7@@Z`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180068ab0`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x18002cbe0`
- `0x18003134c`
- `0x180031564`
- `0x1800483d4`
- `0x1800492f0`
- `0x180049508`
- `0x180068f14`
- `0x180071f58`
- `0x1800982a8`
- `0x180098fe0`
- `0x1800ad4e0`
- `0x1800b86f4`
- `0x1800b8d48`
- `0x180125814`
- `0x180198574`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b8bef`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b8bef`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b8a30`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800b8a30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8b8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8b59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8b59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8b96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b8b96`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::UnmapSharedFileInContainerFolderInternal(
        __int64 a1,
        Csl::Path *a2,
        PSRWLOCK *a3)
{
  PSRWLOCK *v5; // r12
  void *v6; // rcx
  __int64 v7; // rdx
  void **v8; // rax
  __int64 v9; // r8
  void **v10; // rdi
  void **v11; // rsi
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r13
  __int64 i; // r11
  __int64 v19; // rsi
  char *v20; // rsi
  char *v21; // r14
  char *v22; // r15
  __int64 v23; // rax
  const char *v24; // r9
  int v25; // esi
  char v26; // al
  void **v27; // rsi
  unsigned int v28; // edi
  char *v29; // r11
  void **v30; // r14
  void **v31; // r11
  __int64 v32; // rax
  PSRWLOCK v33; // rcx
  RTL_SRWLOCK *v34; // rsi
  int updated; // r14d
  PSRWLOCK v36; // rcx
  void *v37; // [rsp+28h] [rbp-59h] BYREF
  char *v38; // [rsp+30h] [rbp-51h]
  _WORD v39[8]; // [rsp+38h] [rbp-49h] BYREF
  void *v40[2]; // [rsp+48h] [rbp-39h] BYREF
  _WORD v41[8]; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v42[2]; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v43[4]; // [rsp+78h] [rbp-9h] BYREF
  char v44; // [rsp+98h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  __int64 v48; // [rsp+100h] [rbp+7Fh] BYREF

  v40[0] = v41;
  v40[1] = v41;
  v41[0] = 0;
  v5 = a3;
  if ( !Csl::Path::GetParentPath(a2, (struct Path *)v40) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1703,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v37);
    v6 = v40[0];
    if ( v40[0] == v41 )
      return 2147942414LL;
LABEL_20:
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v39[0] = 0;
  v37 = v39;
  v38 = (char *)v39;
  if ( !(unsigned __int8)Csl::Path::GetFileName(a2, &v37) )
  {
    v7 = 5895;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v37);
    goto LABEL_17;
  }
  v42[0] = v37;
  v42[1] = (v38 - (_BYTE *)v37) >> 1;
  if ( !(unsigned __int8)Csl::LowercaseString(v42, &v37) )
  {
    v7 = 5896;
    goto LABEL_6;
  }
  v43[3] = 0;
  v43[0] = v43;
  v43[1] = v43;
  v43[2] = v43;
  v8 = (void **)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v8;
  v11 = v8 + 3;
  if ( !v8
    || (v8[3] = v8 + 5,
        v8[4] = v8 + 5,
        *((_WORD *)v8 + 20) = 0,
        !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            v8 + 3,
                            v37,
                            (v38 - (_BYTE *)v37) >> 1)) )
  {
    if ( v10 )
    {
      if ( *v11 != v11 + 2 )
        operator delete(*v11, (const struct std::nothrow_t *)&std::nothrow);
      operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
      v10 = 0;
    }
  }
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_EmplaceImpl(
    v43,
    v42,
    v9,
    v10);
  if ( !v42[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x170F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v37);
    utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v43);
LABEL_17:
    if ( v37 != v39 )
      operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v40[0];
    if ( v40[0] == v41 )
      return 2147942414LL;
    goto LABEL_20;
  }
  v13 = a1 + 736;
  v14 = 0;
  for ( v42[0] = a1 + 736; ; v13 = v42[0] )
  {
    v15 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
            v13,
            v40);
    if ( v15 == v13 )
      break;
    v17 = v15 + 56;
    for ( i = *(_QWORD *)(v15 + 72);
          i != v17;
          i = utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(
                i,
                v16) )
    {
      v19 = *(_QWORD *)(i + 56);
      if ( *(_BYTE *)(v19 + 232) )
      {
        v20 = (char *)(v19 + 152);
        if ( *((char **)v20 + 2) != v20 )
        {
          v21 = *(char **)v20;
          v22 = v20;
          do
          {
            if ( (unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                                    v21 + 24,
                                    &v37) )
            {
              v23 = 16;
            }
            else
            {
              v22 = v21;
              v23 = 8;
            }
            v21 = *(char **)&v21[v23];
          }
          while ( v21 != (char *)&utl::_TreeSentinel );
          v5 = a3;
          if ( v22 != v20
            && !(unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                                   &v37,
                                   v22 + 24) )
          {
            v14 = *(_QWORD *)(i + 56);
            goto LABEL_38;
          }
        }
      }
      LOBYTE(v16) = 1;
    }
    v25 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x16B9,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)0x490,
            (unsigned int)v37);
    if ( v25 < 0 )
      goto LABEL_85;
LABEL_38:
    v26 = *(_BYTE *)(v14 + 232);
    if ( !v26 )
      __int2c();
    v27 = (void **)(v14 + 152);
    if ( *(_QWORD *)(v14 + 176) == 1 )
    {
      if ( !v26 )
        __int2c();
      if ( !*(_BYTE *)(v14 + 80) )
      {
        v28 = Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(a1, (__int64)v40, v5);
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v43);
        if ( v37 != v39 )
          operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
        if ( v40[0] != v41 )
          operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
        return v28;
      }
    }
    if ( !*(_BYTE *)v14 )
    {
      *(_BYTE *)v14 = 1;
      if ( !v26 )
        __int2c();
      if ( *(_QWORD *)(v14 + 168) == v14 + 152 )
        goto LABEL_90;
      v29 = (char *)*v27;
      v30 = (void **)(v14 + 152);
      do
      {
        if ( (unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                                v29 + 24,
                                &v37) )
        {
          v32 = 2;
        }
        else
        {
          v30 = v31;
          v32 = 1;
        }
        v29 = (char *)v31[v32];
      }
      while ( v29 != (char *)&utl::_TreeSentinel );
      if ( v30 == v27
        || (unsigned __int8)utl::operator<<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                              &v37,
                              v30 + 3) )
      {
LABEL_90:
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x173F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          v24);
      }
      utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(
        v14 + 152,
        v30);
      --*(_QWORD *)(v14 + 176);
      if ( v30[3] != v30 + 5 )
        operator delete(v30[3], (const struct std::nothrow_t *)&std::nothrow);
      operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
      v33 = *a3;
      if ( *a3 )
      {
        LODWORD(v33[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v33);
        *a3 = 0;
      }
      v34 = (RTL_SRWLOCK *)(a1 + 456);
      updated = Container::Manager::Hcs::ComputeSystem::UpdateSharedFolder(
                  *(Container::Manager::Hcs::ComputeSystem **)(a1 + 1256),
                  (const struct Container::Manager::Hcs::MappedFolderConfiguration *)(v14 + 8));
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
      *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
      if ( a3 == (PSRWLOCK *)&v44 )
      {
        if ( a1 != -456 )
        {
          *(_DWORD *)(a1 + 464) = 0;
          ReleaseSRWLockExclusive(v34);
        }
      }
      else
      {
        v36 = *a3;
        if ( *a3 )
        {
          LODWORD(v36[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v36);
        }
        *a3 = v34;
      }
      *(_BYTE *)v14 = 0;
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v14 + 288));
      if ( updated >= 0 )
      {
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v43);
        if ( v37 != v39 )
          operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
        if ( v40[0] != v41 )
          operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
        return 0;
      }
      else
      {
        if ( !*(_BYTE *)(v14 + 232) )
          __int2c();
        utl::set<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::merge<utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
          v14 + 152,
          v43);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1756,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)updated,
          (int)v37);
        utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v43);
        if ( v37 != v39 )
          operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
        if ( v40[0] != v41 )
          operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
        return (unsigned int)updated;
      }
    }
    v48 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v14 + 296),
      (struct Csl::RundownProtection *)&v48);
    LODWORD((*v5)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v14 + 288), *v5, 0xFFFFFFFF, 0);
    LODWORD((*v5)[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v48);
  }
  v25 = -2147023728;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16A4,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)0x80070490LL,
    (int)v37);
LABEL_85:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1717,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)(unsigned int)v25,
    (int)v37);
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>::~_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,unsigned long>>,0>(v43);
  if ( v37 != v39 )
    operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
  if ( v40[0] != v41 )
    operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800b86f4  mov     rax, rsp
0x1800b86f7  mov     [rax+10h], rbx
0x1800b86fb  mov     [rax+18h], r8
0x1800b86ff  mov     [rax+8], rcx
0x1800b8703  push    rbp
0x1800b8704  push    rsi
0x1800b8705  push    rdi
0x1800b8706  push    r12
0x1800b8708  push    r13
0x1800b870a  push    r14
0x1800b870c  push    r15
0x1800b870e  lea     rbp, [rax-5Fh]
0x1800b8712  sub     rsp, 0A0h
0x1800b8719  mov     rbx, rdx
0x1800b871c  lea     rax, [rbp+57h+var_80]
0x1800b8720  mov     [rbp+57h+var_90], rax
0x1800b8724  lea     rdx, [rbp+57h+var_90]; struct Path *
0x1800b8728  lea     rax, [rbp+57h+var_80]
0x1800b872c  mov     r14, rcx
0x1800b872f  xor     r15d, r15d
0x1800b8732  mov     [rbp+57h+var_88], rax
0x1800b8736  mov     rcx, rbx; this
0x1800b8739  mov     [rbp+57h+var_80], r15w
0x1800b873e  mov     r12, r8
0x1800b8741  call    ?GetParentPath@Path@Csl@@QEBA_NAEAV12@@Z; Csl::Path::GetParentPath(Csl::Path &)
0x1800b8746  test    al, al
0x1800b8748  jnz     short loc_1800B8782
0x1800b874a  mov     rcx, [rbp+5Fh]; this
0x1800b874e  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b8755  mov     r9d, 8007000Eh; char *
0x1800b875b  mov     edx, 1703h; void *
0x1800b8760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8765  mov     rcx, [rbp+57h+var_90]
0x1800b8769  lea     rax, [rbp+57h+var_80]
0x1800b876d  cmp     rcx, rax
0x1800b8770  jz      loc_1800B88E8
0x1800b8776  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800b877d  jmp     loc_1800B88E3
0x1800b8782  lea     rax, [rbp+57h+var_A0]
0x1800b8786  mov     [rbp+57h+var_A0], r15w
0x1800b878b  mov     [rbp+57h+var_B0], rax
0x1800b878f  lea     rdx, [rbp+57h+var_B0]
0x1800b8793  lea     rax, [rbp+57h+var_A0]
0x1800b8797  mov     rcx, rbx
0x1800b879a  mov     [rbp+57h+var_A8], rax
0x1800b879e  call    ?GetFileName@Path@Csl@@QEBA_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::Path::GetFileName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800b87a3  test    al, al
0x1800b87a5  jnz     short loc_1800B87CE
0x1800b87a7  mov     edx, 1707h; void *
0x1800b87ac  mov     rcx, [rbp+5Fh]; this
0x1800b87b0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b87b7  mov     r9d, 8007000Eh; char *
0x1800b87bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b87c2  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800b87c9  jmp     loc_1800B88BE
0x1800b87ce  mov     rax, [rbp+57h+var_B0]
0x1800b87d2  lea     rdx, [rbp+57h+var_B0]
0x1800b87d6  mov     rcx, [rbp+57h+var_A8]
0x1800b87da  sub     rcx, rax
0x1800b87dd  mov     [rbp+57h+var_70], rax
0x1800b87e1  sar     rcx, 1
0x1800b87e4  mov     [rbp+57h+var_68], rcx
0x1800b87e8  lea     rcx, [rbp+57h+var_70]
0x1800b87ec  call    ?LowercaseString@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@Z; Csl::LowercaseString(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800b87f1  test    al, al
0x1800b87f3  jnz     short loc_1800B87FC
0x1800b87f5  mov     edx, 1708h
0x1800b87fa  jmp     short loc_1800B87AC
0x1800b87fc  lea     rax, [rbp+57h+var_60]
0x1800b8800  mov     [rbp+57h+var_48], r15
0x1800b8804  mov     [rbp+57h+var_60], rax
0x1800b8808  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800b880f  lea     rax, [rbp+57h+var_60]
0x1800b8813  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8816  mov     ecx, 38h ; '8'; unsigned __int64
0x1800b881b  mov     [rbp+57h+var_58], rax
0x1800b881f  mov     [rbp+57h+var_50], rax
0x1800b8823  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8828  mov     rdi, rax
0x1800b882b  lea     rsi, [rax+18h]
0x1800b882f  test    rax, rax
0x1800b8832  jz      short loc_1800B885D
0x1800b8834  lea     rcx, [rsi+10h]
0x1800b8838  mov     [rsi], rcx
0x1800b883b  mov     [rsi+8], rcx
0x1800b883f  mov     [rcx], r15w
0x1800b8843  mov     rcx, rsi
0x1800b8846  mov     r8, [rbp+57h+var_A8]
0x1800b884a  mov     rdx, [rbp+57h+var_B0]
0x1800b884e  sub     r8, rdx
0x1800b8851  sar     r8, 1
0x1800b8854  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800b8859  test    al, al
0x1800b885b  jnz     short loc_1800B8884
0x1800b885d  test    rdi, rdi
0x1800b8860  jz      short loc_1800B8884
0x1800b8862  lea     rax, [rsi+10h]
0x1800b8866  cmp     [rsi], rax
0x1800b8869  jz      short loc_1800B8876
0x1800b886b  mov     rcx, [rsi]; void *
0x1800b886e  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8871  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8876  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8879  mov     rcx, rdi; void *
0x1800b887c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8881  mov     rdi, r15
0x1800b8884  mov     r9, rdi
0x1800b8887  lea     rdx, [rbp+57h+var_70]
0x1800b888b  lea     rcx, [rbp+57h+var_60]
0x1800b888f  call    ?_EmplaceImpl@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@_N@2@PEAU?$_TreeNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@0@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_EmplaceImpl(utl::_TreeNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *,utl::_TreeNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x1800b8894  cmp     [rbp+57h+var_70], r15
0x1800b8898  jnz     short loc_1800B88F2
0x1800b889a  mov     rcx, [rbp+5Fh]; this
0x1800b889e  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b88a5  mov     r9d, 8007000Eh; char *
0x1800b88ab  mov     edx, 170Fh; void *
0x1800b88b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b88b5  lea     rcx, [rbp+57h+var_60]
0x1800b88b9  call    ??1?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>::~_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>(void)
0x1800b88be  mov     rcx, [rbp+57h+var_B0]; void *
0x1800b88c2  lea     rax, [rbp+57h+var_A0]
0x1800b88c6  cmp     rcx, rax
0x1800b88c9  jz      short loc_1800B88D3
0x1800b88cb  mov     rdx, rbx; struct std::nothrow_t *
0x1800b88ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b88d3  mov     rcx, [rbp+57h+var_90]; void *
0x1800b88d7  lea     rax, [rbp+57h+var_80]
0x1800b88db  cmp     rcx, rax
0x1800b88de  jz      short loc_1800B88E8
0x1800b88e0  mov     rdx, rbx; struct std::nothrow_t *
0x1800b88e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b88e8  mov     eax, 8007000Eh
0x1800b88ed  jmp     loc_1800B8D0F
0x1800b88f2  lea     rsi, [r14+2E0h]
0x1800b88f9  mov     rdi, r15
0x1800b88fc  mov     [rbp+57h+var_70], rsi
0x1800b8900  lea     rdx, [rbp+57h+var_90]
0x1800b8904  mov     rcx, rsi
0x1800b8907  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800b890c  cmp     rax, rsi
0x1800b890f  jz      loc_1800B8CA5
0x1800b8915  lea     r13, [rax+38h]
0x1800b8919  mov     r11, [r13+10h]
0x1800b891d  cmp     r11, r13
0x1800b8920  jz      loc_1800B89AE
0x1800b8926  mov     rsi, [r11+38h]
0x1800b892a  cmp     [rsi+0E8h], r15b
0x1800b8931  jz      short loc_1800B899C
0x1800b8933  add     rsi, 98h
0x1800b893a  cmp     [rsi+10h], rsi
0x1800b893e  jz      short loc_1800B899C
0x1800b8940  mov     r14, [rsi]
0x1800b8943  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800b894a  mov     r15, rsi
0x1800b894d  lea     rcx, [r14+18h]
0x1800b8951  lea     rdx, [rbp+57h+var_B0]
0x1800b8955  call    ??$?MGU?$char_traits@G@utl@@V?$allocator@G@1@@utl@@YA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@0@Z; utl::operator<<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800b895a  test    al, al
0x1800b895c  jnz     short loc_1800B8968
0x1800b895e  mov     r15, r14
0x1800b8961  mov     eax, 8
0x1800b8966  jmp     short loc_1800B896D
0x1800b8968  mov     eax, 10h
0x1800b896d  mov     r14, [r14+rax]
0x1800b8971  cmp     r14, r12
0x1800b8974  jnz     short loc_1800B894D
0x1800b8976  mov     r12, [rbp+57h+arg_10]
0x1800b897a  cmp     r15, rsi
0x1800b897d  jz      short loc_1800B8999
0x1800b897f  lea     rdx, [r15+18h]
0x1800b8983  lea     rcx, [rbp+57h+var_B0]
0x1800b8987  call    ??$?MGU?$char_traits@G@utl@@V?$allocator@G@1@@utl@@YA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@0@Z; utl::operator<<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800b898c  xor     r15d, r15d
0x1800b898f  test    al, al
0x1800b8991  jnz     short loc_1800B899C
0x1800b8993  mov     rdi, [r11+38h]
0x1800b8997  jmp     short loc_1800B89D3
0x1800b8999  xor     r15d, r15d
0x1800b899c  mov     dl, 1
0x1800b899e  mov     rcx, r11
0x1800b89a1  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>::_Traverse(bool)
0x1800b89a6  mov     r11, rax
0x1800b89a9  jmp     loc_1800B891D
0x1800b89ae  mov     rcx, [rbp+5Fh]; this
0x1800b89b2  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b89b9  mov     r9d, 490h; char *
0x1800b89bf  mov     edx, 16B9h; void *
0x1800b89c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b89c9  mov     esi, eax
0x1800b89cb  test    eax, eax
0x1800b89cd  js      loc_1800B8CC2
0x1800b89d3  mov     al, [rdi+0E8h]
0x1800b89d9  test    al, al
0x1800b89db  jnz     short loc_1800B89DF
0x1800b89dd  int     2Ch; Windows NT - assertion failure
0x1800b89df  lea     rsi, [rdi+98h]
0x1800b89e6  cmp     qword ptr [rsi+18h], 1
0x1800b89eb  jnz     short loc_1800B89F9
0x1800b89ed  test    al, al
0x1800b89ef  jnz     short loc_1800B89F3
0x1800b89f1  int     2Ch; Windows NT - assertion failure
0x1800b89f3  cmp     [rdi+50h], r15b
0x1800b89f7  jz      short loc_1800B8A61
0x1800b89f9  cmp     [rdi], r15b
0x1800b89fc  jz      loc_1800B8AAD
0x1800b8a02  lea     rcx, [rdi+128h]; this
0x1800b8a09  mov     [rbp+57h+arg_18], r15
0x1800b8a0d  lea     rdx, [rbp+57h+arg_18]; struct Csl::RundownProtection *
0x1800b8a11  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800b8a16  mov     rax, [r12]
0x1800b8a1a  lea     rcx, [rdi+120h]; ConditionVariable
0x1800b8a21  xor     r9d, r9d; Flags
0x1800b8a24  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800b8a28  mov     [rax+8], r15d
0x1800b8a2c  mov     rdx, [r12]; SRWLock
0x1800b8a30  call    cs:__imp_SleepConditionVariableSRW
0x1800b8a37  nop     dword ptr [rax+rax+00h]
0x1800b8a3c  call    cs:__imp_GetCurrentThreadId
0x1800b8a43  nop     dword ptr [rax+rax+00h]
0x1800b8a48  mov     rcx, [r12]
0x1800b8a4c  mov     [rcx+8], eax
0x1800b8a4f  lea     rcx, [rbp+57h+arg_18]; this
0x1800b8a53  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800b8a58  mov     rsi, [rbp+57h+var_70]
0x1800b8a5c  jmp     loc_1800B8900
0x1800b8a61  mov     rcx, [rbp+57h+arg_0]
0x1800b8a65  lea     rdx, [rbp+57h+var_90]
0x1800b8a69  mov     r8, r12
0x1800b8a6c  call    ?UnmapSharedFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@7@@Z; Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(Csl::Path const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b8a71  lea     rcx, [rbp+57h+var_60]
0x1800b8a75  mov     edi, eax
0x1800b8a77  call    ??1?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@K@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>::~_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ulong>>,0>(void)
0x1800b8a7c  mov     rcx, [rbp+57h+var_B0]; void *
0x1800b8a80  lea     rax, [rbp+57h+var_A0]
0x1800b8a84  cmp     rcx, rax
0x1800b8a87  jz      short loc_1800B8A91
0x1800b8a89  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8a8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8a91  mov     rcx, [rbp+57h+var_90]; void *
0x1800b8a95  lea     rax, [rbp+57h+var_80]
0x1800b8a99  cmp     rcx, rax
0x1800b8a9c  jz      short loc_1800B8AA6
0x1800b8a9e  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8aa1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8aa6  mov     eax, edi
0x1800b8aa8  jmp     loc_1800B8D0F
0x1800b8aad  mov     byte ptr [rdi], 1
0x1800b8ab0  test    al, al
0x1800b8ab2  jnz     short loc_1800B8AB6
0x1800b8ab4  int     2Ch; Windows NT - assertion failure
0x1800b8ab6  cmp     [rsi+10h], rsi
0x1800b8aba  jz      loc_1800B8D2B
0x1800b8ac0  mov     r11, [rsi]
0x1800b8ac3  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800b8aca  mov     r14, rsi
0x1800b8acd  lea     rcx, [r11+18h]
0x1800b8ad1  lea     rdx, [rbp+57h+var_B0]
0x1800b8ad5  call    ??$?MGU?$char_traits@G@utl@@V?$allocator@G@1@@utl@@YA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@0@Z; utl::operator<<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800b8ada  test    al, al
0x1800b8adc  jnz     short loc_1800B8AE8
0x1800b8ade  mov     r14, r11
0x1800b8ae1  mov     eax, 8
0x1800b8ae6  jmp     short loc_1800B8AED
0x1800b8ae8  mov     eax, 10h
0x1800b8aed  mov     r11, [r11+rax]
0x1800b8af1  cmp     r11, r12
0x1800b8af4  jnz     short loc_1800B8ACD
0x1800b8af6  mov     r12, [rbp+57h+arg_10]
0x1800b8afa  cmp     r14, rsi
0x1800b8afd  jz      loc_1800B8D2B
0x1800b8b03  lea     r15, [r14+18h]
0x1800b8b07  mov     rdx, r15
0x1800b8b0a  lea     rcx, [rbp+57h+var_B0]
0x1800b8b0e  call    ??$?MGU?$char_traits@G@utl@@V?$allocator@G@1@@utl@@YA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@0@0@Z; utl::operator<<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800b8b13  test    al, al
0x1800b8b15  jnz     loc_1800B8D2B
0x1800b8b1b  mov     rdx, r14
0x1800b8b1e  mov     rcx, rsi
0x1800b8b21  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>> *)
0x1800b8b26  dec     qword ptr [rsi+18h]
0x1800b8b2a  lea     rax, [r15+10h]
0x1800b8b2e  cmp     [r15], rax
0x1800b8b31  jz      short loc_1800B8B3E
0x1800b8b33  mov     rcx, [r15]; void *
0x1800b8b36  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8b39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8b3e  mov     rdx, rbx; struct std::nothrow_t *
0x1800b8b41  mov     rcx, r14; void *
0x1800b8b44  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8b49  mov     rcx, [r12]; SRWLock
0x1800b8b4d  xor     r15d, r15d
0x1800b8b50  test    rcx, rcx
0x1800b8b53  jz      short loc_1800B8B69
0x1800b8b55  mov     [rcx+8], r15d
0x1800b8b59  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b8b60  nop     dword ptr [rax+rax+00h]
0x1800b8b65  mov     [r12], r15
0x1800b8b69  mov     rsi, [rbp+57h+arg_0]
0x1800b8b6d  lea     rdx, [rdi+8]; struct Container::Manager::Hcs::MappedFolderConfiguration *
0x1800b8b71  mov     rcx, [rsi+4E8h]; this
  ... truncated ...
```
