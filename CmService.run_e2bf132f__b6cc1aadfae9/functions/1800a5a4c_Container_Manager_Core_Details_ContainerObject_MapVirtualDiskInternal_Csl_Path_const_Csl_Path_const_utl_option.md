# Container::Manager::Core::Details::ContainerObject::MapVirtualDiskInternal(Csl::Path const &,Csl::Path const &,utl::optional<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>)

- ea: `0x1800a5a4c`
- end: `0x1800a6470`
- name: `?MapVirtualDiskInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@0V?$optional@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@Z`
- size: `2596`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067600`
- `0x1800a556c`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x180016774`
- `0x18003ee40`
- `0x180042b58`
- `0x18004891c`
- `0x18004f11c`
- `0x18004feb4`
- `0x1800505a4`
- `0x180078644`
- `0x180098a50`
- `0x180098d8c`
- `0x18009aa3c`
- `0x18009b018`
- `0x1800a5a4c`
- `0x1800ac950`
- `0x1800aca94`
- `0x1800ad4e0`
- `0x1800b7474`
- `0x1800ba2c0`
- `0x1800ba810`
- `0x180122e90`
- `0x180123a48`
- `0x18012489c`
- `0x180198404`
- `0x180198494`

## import_xrefs

- `ntdll!RtlClearBitEx` at `0x1800a629f`
- `ntdll!RtlClearBitEx` at `0x1800a629f`
- `ntdll!RtlFindClearBitsAndSetEx` at `0x1800a6064`
- `ntdll!RtlFindClearBitsAndSetEx` at `0x1800a6064`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a63a0`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a63a0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a5e06`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a5e06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5d92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a6138`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a6264`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5d92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a6138`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a6264`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a60de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6166`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a61ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6338`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a63b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a60de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6166`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a61ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6338`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a63b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5d9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5d9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6270`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a5e57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a5e57`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::MapVirtualDiskInternal(
        Container::Manager::Hcs *a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4)
{
  unsigned int v7; // edi
  __int64 v8; // r8
  __int64 v9; // rdx
  void *v10; // rcx
  char *v11; // rax
  char *v12; // r15
  _WORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  _BYTE *v17; // rax
  _QWORD *v18; // rbx
  PSRWLOCK *v19; // rdi
  Container::Manager::Core::ResourceHandle *v20; // rax
  Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *v21; // rcx
  Container::Manager::Core::ResourceHandle *v22; // rbx
  char v23; // al
  Container::Manager::Core::ResourceHandle *v24; // rcx
  Container::Manager::Core::ResourceHandle *v25; // rbx
  Container::Manager::Core::ResourceHandle *v26; // rbx
  Container::Manager::Hcs *v27; // rdi
  RTL_SRWLOCK *v28; // rbx
  DWORD CurrentThreadId; // eax
  void *v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // r9
  __int64 v34; // rdx
  int v35; // eax
  unsigned __int64 *v36; // rax
  void *v37; // rdi
  _OWORD *v38; // rcx
  unsigned __int64 v39; // rcx
  Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *v40; // rbx
  void **v41; // rbx
  _OWORD *InsertionPointUniqueUpper; // rax
  Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *v43; // rax
  RTL_SRWLOCK *v44; // rcx
  __int64 ClearBitsAndSet; // rax
  Container::Manager::Hcs *v46; // r12
  const struct Path *v47; // r8
  RTL_SRWLOCK *v48; // rcx
  int v49; // eax
  __int64 v50; // r8
  __int64 v51; // rdx
  RTL_SRWLOCK *v52; // rdi
  const struct Path *v53; // r8
  int v54; // eax
  int v55; // eax
  char *v56; // r12
  DWORD v57; // eax
  Container::Manager::Core::Details::ContainerObject *v58; // rcx
  void *v59; // rcx
  __int64 v60; // r15
  RTL_SRWLOCK *v61; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-79h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-79h]
  void *v65; // [rsp+30h] [rbp-69h] BYREF
  char *v66; // [rsp+38h] [rbp-61h]
  __int128 v67; // [rsp+40h] [rbp-59h] BYREF
  void *v68; // [rsp+50h] [rbp-49h] BYREF
  void *v69; // [rsp+58h] [rbp-41h] BYREF
  PSRWLOCK v70; // [rsp+60h] [rbp-39h] BYREF
  void *v71; // [rsp+68h] [rbp-31h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-29h] BYREF
  void *v73[2]; // [rsp+78h] [rbp-21h] BYREF
  _WORD v74[8]; // [rsp+88h] [rbp-11h] BYREF
  _OWORD v75[5]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  Container::Manager::Hcs *v77; // [rsp+100h] [rbp+67h] BYREF

  v77 = a1;
  if ( *((_DWORD *)a1 + 22) == 2 )
  {
    v7 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD35,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x80004001LL,
      bIgnoreCase);
LABEL_113:
    if ( !*(_BYTE *)(a4 + 8) )
      return v7;
    v22 = *(Container::Manager::Core::ResourceHandle **)a4;
    *(_QWORD *)a4 = 0;
    if ( !v22 )
      return v7;
    goto LABEL_115;
  }
  v8 = a2[1] - *a2;
  v9 = *a2;
  v65 = &v67;
  v66 = (char *)&v67;
  LOWORD(v67) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v65,
                           v9,
                           v8 >> 1) )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    v10 = v65;
    if ( v65 == &v67 )
      goto LABEL_113;
LABEL_112:
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_113;
  }
  v11 = (char *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
LABEL_111:
    v10 = v65;
    if ( v65 == &v67 )
      goto LABEL_113;
    goto LABEL_112;
  }
  *((_QWORD *)v11 + 8) = 0;
  v13 = v11 + 16;
  *(_QWORD *)v12 = v13;
  *((_QWORD *)v12 + 1) = v13;
  *((_DWORD *)v12 + 18) = 0;
  *v13 = 0;
  *((_QWORD *)v12 + 4) = v12 + 48;
  *((_QWORD *)v12 + 5) = v12 + 48;
  *((_WORD *)v12 + 24) = 0;
  *((_QWORD *)v12 + 10) = 0;
  *((_DWORD *)v12 + 22) = 0;
  *((_WORD *)v12 + 48) = 0;
  *(_OWORD *)(v12 + 104) = 0;
  *(_OWORD *)(v12 + 120) = 0;
  *((_QWORD *)v12 + 17) = 0;
  *((_QWORD *)v12 + 18) = 0;
  *((_QWORD *)v12 + 19) = 0;
  v12[160] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v12,
                           *a2,
                           (__int64)(a2[1] - *a2) >> 1) )
  {
    v14 = 3391;
LABEL_9:
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk((Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v12);
    operator delete(v12, (const struct std::nothrow_t *)0xA8);
    goto LABEL_111;
  }
  v15 = *a3;
  v16 = (a3[1] - *a3) >> 1;
  v70 = (PSRWLOCK)(v12 + 32);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v12 + 32,
                           v15,
                           v16) )
  {
    v14 = 3392;
    goto LABEL_9;
  }
  if ( *(_BYTE *)(a4 + 8) )
  {
    v17 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
    {
      *(_QWORD *)v17 = 0;
      v17[8] = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 0;
    }
    else
    {
      v17 = 0;
    }
    v18 = v12 + 120;
    v69 = v17;
    if ( v12[128] )
    {
      wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>::operator=(
        v12 + 120,
        &v69);
      v19 = (PSRWLOCK *)v69;
    }
    else
    {
      *v18 = v17;
      v19 = 0;
      v12[128] = 1;
    }
    if ( v19 )
    {
      wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>::~unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>(v19 + 3);
      SRWLock = *v19;
      v20 = (Container::Manager::Core::ResourceHandle *)SRWLock;
      *v19 = 0;
      if ( v20 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v20);
        operator delete(SRWLock, (const struct std::nothrow_t *)0x58);
      }
      operator delete(v19, (const struct std::nothrow_t *)0x20);
    }
    if ( v12[128] && !*v18 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD49,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
LABEL_26:
      Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk((Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v12);
      v21 = (Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v12;
LABEL_27:
      operator delete(v21, (const struct std::nothrow_t *)0xA8);
LABEL_28:
      if ( v65 != &v67 )
        operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
      if ( !*(_BYTE *)(a4 + 8) )
        return v7;
      v22 = *(Container::Manager::Core::ResourceHandle **)a4;
      *(_QWORD *)a4 = 0;
      if ( !v22 )
        return v7;
LABEL_115:
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v22);
      operator delete(v22, (const struct std::nothrow_t *)0x58);
      return v7;
    }
    v23 = v12[112];
    if ( *(_BYTE *)(a4 + 8) )
    {
      v24 = *(Container::Manager::Core::ResourceHandle **)a4;
      *(_QWORD *)a4 = 0;
      if ( v23 )
      {
        v25 = (Container::Manager::Core::ResourceHandle *)*((_QWORD *)v12 + 13);
        *((_QWORD *)v12 + 13) = v24;
        if ( v25 )
        {
          Container::Manager::Core::ResourceHandle::~ResourceHandle(v25);
          operator delete(v25, (const struct std::nothrow_t *)0x58);
        }
      }
      else
      {
        *((_QWORD *)v12 + 13) = v24;
        v12[112] = 1;
      }
    }
    else if ( v23 )
    {
      v26 = (Container::Manager::Core::ResourceHandle *)*((_QWORD *)v12 + 13);
      *((_QWORD *)v12 + 13) = 0;
      if ( v26 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v26);
        operator delete(v26, (const struct std::nothrow_t *)0x58);
      }
      v12[112] = 0;
    }
  }
  v27 = v77;
  *((_QWORD *)v12 + 8) = v77;
  v28 = (RTL_SRWLOCK *)((char *)v27 + 456);
  AcquireSRWLockExclusive((PSRWLOCK)v27 + 57);
  CurrentThreadId = GetCurrentThreadId();
  v30 = (char *)v27 + 680;
  SRWLock = v28;
  v69 = v30;
  LODWORD(v28[1].Ptr) = CurrentThreadId;
  while ( 1 )
  {
    v31 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(
            v30,
            &v71);
    if ( *(void **)v31 == v30 )
      break;
    v32 = *(_QWORD *)(*(_QWORD *)v31 + 56LL);
    if ( *(_DWORD *)(v32 + 72) )
    {
      if ( CompareStringOrdinal(
             *(LPCWCH *)(v32 + 32),
             (__int64)(*(_QWORD *)(v32 + 40) - *(_QWORD *)(v32 + 32)) >> 1,
             (LPCWCH)v70->Ptr,
             ((char *)v70[1].Ptr - (char *)v70->Ptr) >> 1,
             1) == 2 )
      {
        v33 = 183;
        v34 = 3497;
      }
      else
      {
        v33 = 2404;
        v34 = 3501;
      }
      v35 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v34,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)v33,
              bIgnoreCasea);
      LODWORD(v28[1].Ptr) = 0;
      v7 = v35;
      ReleaseSRWLockExclusive(v28);
      goto LABEL_26;
    }
    v68 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v32 + 80),
      (struct Csl::RundownProtection *)&v68);
    LODWORD(v28[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v32 + 152), v28, 0xFFFFFFFF, 0);
    LODWORD(v28[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v68);
    v30 = v69;
  }
  v36 = (unsigned __int64 *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = v36;
  if ( v36 )
  {
    v38 = v36 + 5;
    if ( v65 == &v67 )
    {
      v36[3] = (unsigned __int64)v38;
      v36[4] = (unsigned __int64)v36 + 2 * ((v66 - (char *)&v65 - 16) >> 1) + 40;
      *v38 = v67;
    }
    else
    {
      v36[3] = (unsigned __int64)v65;
      v36[4] = (unsigned __int64)v66;
      *(_QWORD *)v38 = v67;
    }
    v39 = (unsigned __int64)v69;
    v65 = &v67;
    v66 = (char *)&v67;
    LOWORD(v67) = 0;
    v36[7] = (unsigned __int64)v12;
    if ( *(_QWORD *)(v39 + 16) == v39 )
    {
      v40 = 0;
      *v36 = v39 | 1;
      v36[1] = (unsigned __int64)&utl::_TreeSentinel;
      v36[2] = (unsigned __int64)&utl::_TreeSentinel;
      *(_QWORD *)v39 = v36;
      *(_QWORD *)(v39 + 8) = v36;
      *(_QWORD *)(v39 + 16) = v36;
      ++*(_QWORD *)(v39 + 24);
    }
    else
    {
      v41 = (void **)(v36 + 3);
      v71 = v36;
      v68 = 0;
      InsertionPointUniqueUpper = (_OWORD *)utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindInsertionPointUniqueUpper(
                                              v39,
                                              v75,
                                              &v68,
                                              v36 + 3);
      v37 = v68;
      v75[0] = *InsertionPointUniqueUpper;
      if ( v68 )
      {
        v68 = v41[4];
        v43 = (Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v68;
        v41[4] = 0;
        if ( v43 )
        {
          Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(v43);
          operator delete(v68, (const struct std::nothrow_t *)0xA8);
        }
        if ( *v41 != v41 + 2 )
          operator delete(*v41, (const struct std::nothrow_t *)&std::nothrow);
        operator delete(v71, (const struct std::nothrow_t *)&std::nothrow);
      }
      else
      {
        utl::_Tree<_GUID,utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>>,0>::_InsertAt(
          v69,
          v75,
          v71);
        v37 = v71;
      }
      v40 = 0;
    }
  }
  else
  {
    v40 = (Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v12;
  }
  if ( !v37 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD73,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
LABEL_67:
    v44 = (RTL_SRWLOCK *)((char *)v77 + 456);
    *((_DWORD *)v77 + 116) = 0;
    ReleaseSRWLockExclusive(v44);
    if ( !v40 )
      goto LABEL_28;
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(v40);
    v21 = v40;
    goto LABEL_27;
  }
  v71 = (char *)v77 + 720;
  ClearBitsAndSet = RtlFindClearBitsAndSetEx((char *)v77 + 720, 1);
  if ( ClearBitsAndSet == -1 )
  {
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::erase(
      v69,
      &v70);
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xDBA,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
           (const char *)0x4E0,
           bIgnoreCase);
    goto LABEL_67;
  }
  v12[97] = 1;
  v12[96] = ClearBitsAndSet;
  if ( !v12[160] )
    v12[160] = 1;
  v46 = v77;
  Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
    v77,
    &SRWLock);
  v48 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v48);
  }
  v49 = Container::Manager::Hcs::GrantVmWpAccessToFile(v46, (const struct _GUID *)v12, v47);
  v7 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xE00,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v49,
      bIgnoreCase);
    goto LABEL_92;
  }
  v50 = *((_QWORD *)v12 + 1) - *(_QWORD *)v12;
  v51 = *(_QWORD *)v12;
  v52 = (RTL_SRWLOCK *)*((_QWORD *)v46 + 156);
  v73[0] = v74;
  v73[1] = v74;
  v74[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v73,
                           v51,
                           v50 >> 1) )
    goto LABEL_80;
  AcquireSRWLockExclusive(v52);
  utl::_Tree<Csl::Path,Csl::Path,utl::less<Csl::Path>,utl::allocator<Csl::Path>,0>::emplace<Csl::Path,0>(
    &v52[23],
    v75,
    v73);
  if ( !*(_QWORD *)&v75[0] )
  {
    if ( v52 )
      ReleaseSRWLockExclusive(v52);
LABEL_80:
    if ( v73[0] != v74 )
      operator delete(v73[0], (const struct std::nothrow_t *)&std::nothrow);
    v7 = -2147024882;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xDF3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    goto LABEL_89;
  }
  if ( v52 )
    ReleaseSRWLockExclusive(v52);
  if ( v73[0] != v74 )
    operator delete(v73[0], (const struct std::nothrow_t *)&std::nothrow);
  v54 = Container::Manager::Hcs::ComputeSystem::MapVirtualDisk(
          *((Container::Manager::Hcs::ComputeSystem **)v46 + 157),
          (const struct Path *)v12,
          (const struct Path *)v70,
          v12[96]);
  v7 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xDE9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v54,
      bIgnoreCase);
    Container::Manager::Core::Details::ComputeSystemReaperContext::RemoveFileFromRevokeVmwpAccessList(
      *((PSRWLOCK *)v46 + 156),
      (const struct Path *)v12);
LABEL_89:
    v55 = Container::Manager::Hcs::RevokeVmWpAccessToFile(v46, (const struct _GUID *)v12, v53);
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDFA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v55,
        bIgnoreCase);
  }
LABEL_92:
  v56 = (char *)v77 + 456;
  AcquireSRWLockExclusive((PSRWLOCK)v77 + 57);
  v57 = GetCurrentThreadId();
  v58 = v77;
  *((_DWORD *)v56 + 2) = v57;
  v70 = (PSRWLOCK)v56;
  Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(v58);
  if ( (v7 & 0x80000000) != 0 )
  {
    RtlClearBitEx(v71, (unsigned __int8)v12[96]);
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(
      v69,
      &v77);
    v59 = v69;
    v60 = *((_QWORD *)v77 + 7);
    *((_QWORD *)v77 + 7) = 0;
    utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::erase(
      v59,
      &v77);
    v77 = 0;
    Csl::SrwLock::ReleaseOnScopeExit<0>::operator=(&v77, &v70);
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::StopOperation(v60, &v77);
    Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v60 + 80));
    if ( v60 )
    {
      Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk((Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk *)v60);
      operator delete((void *)v60, (const struct std::nothrow_t *)0xA8);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE21,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)v7,
      bIgnoreCase);
    v61 = v70;
    if ( v70 )
    {
      LODWORD(v70[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v61);
    }
    if ( v40 )
    {
      Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(v40);
      operator delete(v40, (const struct std::nothrow_t *)0xA8);
    }
    if ( v65 != &v67 )
      operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
    if ( *(_BYTE *)(a4 + 8) )
      wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::`scalar deleting destructor'(a4);
    return v7;
  }
  *((_DWORD *)v12 + 18) = 1;
  v12[160] = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)v12 + 19);
  *((_DWORD *)v56 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v56);
  if ( v40 )
  {
    Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(v40);
    operator delete(v40, (const struct std::nothrow_t *)0xA8);
  }
  if ( v65 != &v67 )
    operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
  if ( *(_BYTE *)(a4 + 8) )
    wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::`scalar deleting destructor'(a4);
  return 0;
}

```

## disassembly

```asm
0x1800a5a4c  mov     [rsp-8+arg_0], rcx
0x1800a5a51  push    rbp
0x1800a5a52  push    rbx
0x1800a5a53  push    rsi
0x1800a5a54  push    rdi
0x1800a5a55  push    r12
0x1800a5a57  push    r13
0x1800a5a59  push    r14
0x1800a5a5b  push    r15
0x1800a5a5d  lea     rbp, [rsp-1Fh]
0x1800a5a62  sub     rsp, 0B8h
0x1800a5a69  cmp     dword ptr [rcx+58h], 2
0x1800a5a6d  mov     r14, r9
0x1800a5a70  mov     rdi, r8
0x1800a5a73  mov     rbx, rdx
0x1800a5a76  jnz     short loc_1800A5A9C
0x1800a5a78  mov     rcx, [rbp+5Fh]; this
0x1800a5a7c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a5a83  mov     edi, 80004001h
0x1800a5a88  mov     edx, 0D35h; void *
0x1800a5a8d  mov     r9d, edi; char *
0x1800a5a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5a95  xor     esi, esi
0x1800a5a97  jmp     loc_1800A6433
0x1800a5a9c  mov     r8, [rdx+8]
0x1800a5aa0  lea     rax, [rbp+57h+var_B0]
0x1800a5aa4  sub     r8, [rdx]
0x1800a5aa7  lea     rcx, [rbp+57h+var_C0]
0x1800a5aab  mov     rdx, [rdx]
0x1800a5aae  xor     esi, esi
0x1800a5ab0  mov     [rbp+57h+var_C0], rax
0x1800a5ab4  lea     rax, [rbp+57h+var_B0]
0x1800a5ab8  sar     r8, 1
0x1800a5abb  mov     [rbp+57h+var_B8], rax
0x1800a5abf  mov     word ptr [rbp+57h+var_B0], si
0x1800a5ac3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a5ac8  test    al, al
0x1800a5aca  jnz     short loc_1800A5B06
0x1800a5acc  mov     rcx, [rbp+5Fh]; this
0x1800a5ad0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a5ad7  mov     edi, 8007000Eh
0x1800a5adc  mov     edx, 0D3Ah; void *
0x1800a5ae1  mov     r9d, edi; char *
0x1800a5ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5ae9  mov     rcx, [rbp+57h+var_C0]
0x1800a5aed  lea     rax, [rbp+57h+var_B0]
0x1800a5af1  cmp     rcx, rax
0x1800a5af4  jz      loc_1800A6433
0x1800a5afa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a5b01  jmp     loc_1800A642E
0x1800a5b06  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a5b0d  mov     r12d, 0A8h
0x1800a5b13  mov     rdx, r13; struct std::nothrow_t *
0x1800a5b16  mov     ecx, r12d; unsigned __int64
0x1800a5b19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a5b1e  mov     r15, rax
0x1800a5b21  test    rax, rax
0x1800a5b24  jz      loc_1800A6401
0x1800a5b2a  mov     [r15+40h], rsi
0x1800a5b2e  add     rax, 10h
0x1800a5b32  mov     [r15], rax
0x1800a5b35  xorps   xmm0, xmm0
0x1800a5b38  mov     [r15+8], rax
0x1800a5b3c  xorps   xmm1, xmm1
0x1800a5b3f  mov     [r15+48h], esi
0x1800a5b43  mov     rcx, r15
0x1800a5b46  mov     [rax], si
0x1800a5b49  lea     rax, [r15+30h]
0x1800a5b4d  mov     [r15+20h], rax
0x1800a5b51  mov     [r15+28h], rax
0x1800a5b55  mov     [rax], si
0x1800a5b58  mov     [r15+50h], rsi
0x1800a5b5c  mov     [r15+58h], esi
0x1800a5b60  mov     [r15+60h], si
0x1800a5b65  movups  xmmword ptr [r15+68h], xmm0
0x1800a5b6a  movups  xmmword ptr [r15+78h], xmm1
0x1800a5b6f  mov     [r15+88h], rsi
0x1800a5b76  mov     [r15+90h], rsi
0x1800a5b7d  mov     [r15+98h], rsi
0x1800a5b84  mov     [r15+0A0h], sil
0x1800a5b8b  mov     r8, [rbx+8]
0x1800a5b8f  sub     r8, [rbx]
0x1800a5b92  mov     rdx, [rbx]
0x1800a5b95  sar     r8, 1
0x1800a5b98  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a5b9d  test    al, al
0x1800a5b9f  jnz     short loc_1800A5BD6
0x1800a5ba1  mov     edx, 0D3Fh; void *
0x1800a5ba6  mov     rcx, [rbp+5Fh]; this
0x1800a5baa  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a5bb1  mov     edi, 8007000Eh
0x1800a5bb6  mov     r9d, edi; char *
0x1800a5bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5bbe  mov     rcx, r15; this
0x1800a5bc1  call    ??1MappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(void)
0x1800a5bc6  mov     rdx, r12; struct std::nothrow_t *
0x1800a5bc9  mov     rcx, r15; void *
0x1800a5bcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5bd1  jmp     loc_1800A641E
0x1800a5bd6  mov     r8, [rdi+8]
0x1800a5bda  lea     rax, [r15+20h]
0x1800a5bde  sub     r8, [rdi]
0x1800a5be1  mov     rcx, rax
0x1800a5be4  mov     rdx, [rdi]
0x1800a5be7  sar     r8, 1
0x1800a5bea  mov     [rbp+57h+var_90], rax
0x1800a5bee  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a5bf3  test    al, al
0x1800a5bf5  jnz     short loc_1800A5BFE
0x1800a5bf7  mov     edx, 0D40h
0x1800a5bfc  jmp     short loc_1800A5BA6
0x1800a5bfe  mov     r12d, 58h ; 'X'
0x1800a5c04  cmp     [r14+8], sil
0x1800a5c08  jz      loc_1800A5D80
0x1800a5c0e  mov     rdx, r13; struct std::nothrow_t *
0x1800a5c11  lea     ecx, [r12-38h]; unsigned __int64
0x1800a5c16  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a5c1b  test    rax, rax
0x1800a5c1e  jz      short loc_1800A5C31
0x1800a5c20  mov     [rax], rsi
0x1800a5c23  mov     [rax+8], sil
0x1800a5c27  mov     [rax+10h], rsi
0x1800a5c2b  mov     [rax+18h], rsi
0x1800a5c2f  jmp     short loc_1800A5C34
0x1800a5c31  mov     rax, rsi
0x1800a5c34  lea     rbx, [r15+78h]
0x1800a5c38  mov     [rbp+57h+var_98], rax
0x1800a5c3c  cmp     [rbx+8], sil
0x1800a5c40  jz      short loc_1800A5C54
0x1800a5c42  lea     rdx, [rbp+57h+var_98]
0x1800a5c46  mov     rcx, rbx
0x1800a5c49  call    ??4?$unique_ptr@V?$ListEntry@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>::operator=(wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>> &&)
0x1800a5c4e  mov     rdi, [rbp+57h+var_98]
0x1800a5c52  jmp     short loc_1800A5C5E
0x1800a5c54  mov     [rbx], rax
0x1800a5c57  mov     rdi, rsi
0x1800a5c5a  mov     byte ptr [rbx+8], 1
0x1800a5c5e  test    rdi, rdi
0x1800a5c61  jz      short loc_1800A5C9C
0x1800a5c63  lea     rcx, [rdi+18h]
0x1800a5c67  call    ??1?$unique_ptr@V?$ListEntry@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>::~unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>>(void)
0x1800a5c6c  mov     rax, [rdi]
0x1800a5c6f  mov     [rbp+57h+SRWLock], rax
0x1800a5c73  mov     [rdi], rsi
0x1800a5c76  test    rax, rax
0x1800a5c79  jz      short loc_1800A5C8F
0x1800a5c7b  mov     rcx, rax; this
0x1800a5c7e  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a5c83  mov     rcx, [rbp+57h+SRWLock]; void *
0x1800a5c87  mov     rdx, r12; struct std::nothrow_t *
0x1800a5c8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5c8f  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800a5c94  mov     rcx, rdi; void *
0x1800a5c97  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5c9c  cmp     [rbx+8], sil
0x1800a5ca0  jz      short loc_1800A5D17
0x1800a5ca2  cmp     [rbx], rsi
0x1800a5ca5  jnz     short loc_1800A5D17
0x1800a5ca7  mov     rcx, [rbp+5Fh]; this
0x1800a5cab  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a5cb2  mov     edi, 8007000Eh
0x1800a5cb7  mov     edx, 0D49h; void *
0x1800a5cbc  mov     r9d, edi; char *
0x1800a5cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5cc4  mov     rcx, r15; this
0x1800a5cc7  call    ??1MappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk::~MappedVirtualDisk(void)
0x1800a5ccc  mov     rcx, r15; void *
0x1800a5ccf  mov     edx, 0A8h; struct std::nothrow_t *
0x1800a5cd4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5cd9  mov     rcx, [rbp+57h+var_C0]; void *
0x1800a5cdd  lea     rax, [rbp+57h+var_B0]
0x1800a5ce1  cmp     rcx, rax
0x1800a5ce4  jz      short loc_1800A5CEE
0x1800a5ce6  mov     rdx, r13; struct std::nothrow_t *
0x1800a5ce9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5cee  cmp     [r14+8], sil
0x1800a5cf2  jz      loc_1800A6459
0x1800a5cf8  mov     rbx, [r14]
0x1800a5cfb  mov     [r14], rsi
0x1800a5cfe  test    rbx, rbx
0x1800a5d01  jz      loc_1800A6459
0x1800a5d07  mov     rcx, rbx; this
0x1800a5d0a  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a5d0f  mov     rdx, r12
0x1800a5d12  jmp     loc_1800A6451
0x1800a5d17  mov     al, [r15+70h]
0x1800a5d1b  cmp     [r14+8], sil
0x1800a5d1f  jz      short loc_1800A5D58
0x1800a5d21  mov     rcx, [r14]
0x1800a5d24  mov     [r14], rsi
0x1800a5d27  test    al, al
0x1800a5d29  jz      short loc_1800A5D4D
0x1800a5d2b  mov     rbx, [r15+68h]
0x1800a5d2f  mov     [r15+68h], rcx
0x1800a5d33  test    rbx, rbx
0x1800a5d36  jz      short loc_1800A5D80
0x1800a5d38  mov     rcx, rbx; this
0x1800a5d3b  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a5d40  mov     rdx, r12; struct std::nothrow_t *
0x1800a5d43  mov     rcx, rbx; void *
0x1800a5d46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5d4b  jmp     short loc_1800A5D80
0x1800a5d4d  mov     [r15+68h], rcx
0x1800a5d51  mov     byte ptr [r15+70h], 1
0x1800a5d56  jmp     short loc_1800A5D80
0x1800a5d58  test    al, al
0x1800a5d5a  jz      short loc_1800A5D80
0x1800a5d5c  mov     rbx, [r15+68h]
0x1800a5d60  mov     [r15+68h], rsi
0x1800a5d64  test    rbx, rbx
0x1800a5d67  jz      short loc_1800A5D7C
0x1800a5d69  mov     rcx, rbx; this
0x1800a5d6c  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a5d71  mov     rdx, r12; struct std::nothrow_t *
0x1800a5d74  mov     rcx, rbx; void *
0x1800a5d77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a5d7c  mov     [r15+70h], sil
0x1800a5d80  mov     rdi, [rbp+57h+arg_0]
0x1800a5d84  mov     [r15+40h], rdi
0x1800a5d88  lea     rbx, [rdi+1C8h]
0x1800a5d8f  mov     rcx, rbx; SRWLock
0x1800a5d92  call    cs:__imp_AcquireSRWLockExclusive
0x1800a5d99  nop     dword ptr [rax+rax+00h]
0x1800a5d9e  call    cs:__imp_GetCurrentThreadId
0x1800a5da5  nop     dword ptr [rax+rax+00h]
0x1800a5daa  add     rdi, 2A8h
0x1800a5db1  mov     [rbp+57h+SRWLock], rbx
0x1800a5db5  mov     [rbp+57h+var_98], rdi
0x1800a5db9  mov     [rbx+8], eax
0x1800a5dbc  lea     r8, [rbp+57h+var_C0]
0x1800a5dc0  mov     rcx, rdi
0x1800a5dc3  lea     rdx, [rbp+57h+var_88]
0x1800a5dc7  call    ??$find@X@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedVirtualDisk@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedVirtualDisk>>>>,0>::find<void>(Csl::Path const &)
0x1800a5dcc  mov     rcx, [rax]
0x1800a5dcf  cmp     rcx, rdi
0x1800a5dd2  jz      loc_1800A5EA9
0x1800a5dd8  mov     rdi, [rcx+38h]
0x1800a5ddc  cmp     [rdi+48h], esi
0x1800a5ddf  jnz     short loc_1800A5E30
0x1800a5de1  lea     rcx, [rdi+50h]; this
0x1800a5de5  mov     [rbp+57h+var_A0], rsi
0x1800a5de9  lea     rdx, [rbp+57h+var_A0]; struct Csl::RundownProtection *
0x1800a5ded  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800a5df2  lea     rcx, [rdi+98h]; ConditionVariable
0x1800a5df9  mov     [rbx+8], esi
0x1800a5dfc  xor     r9d, r9d; Flags
0x1800a5dff  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800a5e03  mov     rdx, rbx; SRWLock
0x1800a5e06  call    cs:__imp_SleepConditionVariableSRW
0x1800a5e0d  nop     dword ptr [rax+rax+00h]
0x1800a5e12  call    cs:__imp_GetCurrentThreadId
0x1800a5e19  nop     dword ptr [rax+rax+00h]
0x1800a5e1e  lea     rcx, [rbp+57h+var_A0]; this
0x1800a5e22  mov     [rbx+8], eax
0x1800a5e25  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800a5e2a  mov     rdi, [rbp+57h+var_98]
0x1800a5e2e  jmp     short loc_1800A5DBC
0x1800a5e30  mov     rax, [rbp+57h+var_90]
0x1800a5e34  mov     rcx, [rdi+20h]; lpString1
0x1800a5e38  mov     rdx, [rdi+28h]
0x1800a5e3c  sub     rdx, rcx
0x1800a5e3f  mov     [rsp+0F0h+bIgnoreCase], 1; unsigned int
0x1800a5e47  mov     r9, [rax+8]
0x1800a5e4b  sub     r9, [rax]
0x1800a5e4e  mov     r8, [rax]; lpString2
0x1800a5e51  sar     r9, 1; cchCount2
0x1800a5e54  sar     rdx, 1; cchCount1
0x1800a5e57  call    cs:__imp_CompareStringOrdinal
0x1800a5e5e  nop     dword ptr [rax+rax+00h]
0x1800a5e63  mov     rcx, [rbp+5Fh]; this
0x1800a5e67  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a5e6e  cmp     eax, 2
0x1800a5e71  jnz     short loc_1800A5E9C
0x1800a5e73  mov     r9d, 0B7h; char *
0x1800a5e79  mov     edx, 0DA9h; void *
0x1800a5e7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a5e83  mov     rcx, rbx; SRWLock
0x1800a5e86  mov     [rbx+8], esi
0x1800a5e89  mov     edi, eax
0x1800a5e8b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a5e92  nop     dword ptr [rax+rax+00h]
0x1800a5e97  jmp     loc_1800A5CC4
0x1800a5e9c  mov     r9d, 964h
0x1800a5ea2  mov     edx, 0DADh
0x1800a5ea7  jmp     short loc_1800A5E7E
0x1800a5ea9  mov     rdx, r13; struct std::nothrow_t *
0x1800a5eac  mov     ecx, 40h ; '@'; unsigned __int64
0x1800a5eb1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a5eb6  mov     rdi, rax
0x1800a5eb9  test    rax, rax
0x1800a5ebc  jz      loc_1800A5FF4
0x1800a5ec2  lea     rcx, [rax+28h]
0x1800a5ec6  mov     rax, [rbp+57h+var_C0]
0x1800a5eca  lea     rdx, [rbp+57h+var_B0]
0x1800a5ece  cmp     rax, rdx
0x1800a5ed1  jnz     short loc_1800A5EFF
0x1800a5ed3  mov     [rdi+18h], rcx
0x1800a5ed7  lea     rdx, [rbp+57h+var_C0]
0x1800a5edb  mov     rax, [rbp+57h+var_B8]
0x1800a5edf  sub     rax, rdx
  ... truncated ...
```
