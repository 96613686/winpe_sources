# Container::Manager::Core::Details::ContainerStorage::Initialize(_GUID const &,_CMS_CLIENT_ID,Container::Manager::Core::Details::ResourceType,_GUID const &,Container::Manager::Core::Details::ContainerStorageState,Csl::Path,Container::Manager::Core::Details::ContainerStorageFlags,utl::optional<Csl::Path>,utl::optional<_GUID> const &,Csl::RegistryKey const &,utl::optional<Container::Manager::Core::Details::DebugConfiguration>,utl::optional<unsigned __int64>,void *)

- ea: `0x180082e18`
- end: `0x180083e97`
- name: `?Initialize@ContainerStorage@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@W4_CMS_CLIENT_ID@@W4ResourceType@2345@0W4ContainerStorageState@2345@VPath@Csl@@W4ContainerStorageFlags@2345@V?$optional@VPath@Csl@@@utl@@AEBV?$optional@U_GUID@@@utl@@AEBVRegistryKey@Csl@@V?$optional@UDebugConfiguration@Details@Core@Manager@Container@@@utl@@V?$optional@_K@utl@@PEAX@Z`
- size: `4223`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, __int64, int, __int64, int, __int64, __int64, __int64, Container::Manager::Core::Details::DebugConfiguration *, __int64, PSECURITY_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008431c`
- `0x180084648`

## callees

- `0x180004fc4`
- `0x180008bf0`
- `0x180008c98`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x180023c58`
- `0x18002c030`
- `0x18002e95c`
- `0x18002ebd4`
- `0x18002ec00`
- `0x18002fae4`
- `0x180032bb0`
- `0x180032d70`
- `0x18003d400`
- `0x18003e190`
- `0x18003e9f4`
- `0x1800471dc`
- `0x18004e6c4`
- `0x18005067c`
- `0x180053ea0`
- `0x1800802f0`
- `0x18008039c`
- `0x180082e18`
- `0x1800bfc60`
- `0x1801094d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008306e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008306e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083163`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800831e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008329d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008331f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008342e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083521`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800835e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800836ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008380c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008395e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083a46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083b8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083d54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083e77`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083163`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800831e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008329d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008331f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008342e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083521`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800835e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800836ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008380c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008395e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083a46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083b8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083d54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180083e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800839e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083b16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083b2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083e19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800839e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083b16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083b2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083e19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800834ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800837d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083a11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083b54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083d18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800834ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800837d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083a11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083b54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083d18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083e42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerStorage::Initialize(
        char *pv,
        _OWORD *a2,
        int a3,
        int a4,
        _OWORD *a5,
        int a6,
        _QWORD *a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        Container::Manager::Core::Details::DebugConfiguration *a12,
        _OWORD *a13,
        PSECURITY_DESCRIPTOR a14)
{
  unsigned int LastError; // ebx
  __int64 v17; // rdx
  Container::Manager::Core::Details::DebugConfiguration *v18; // rcx
  __int64 v19; // rax
  utl::_RefCountBase *v20; // rbx
  utl::_RefCountBase *v21; // r13
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  utl::_RefCountBase *v26; // rdi
  utl::_RefCountBase *v27; // rsi
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  Container::Manager::Core::Details::DebugConfiguration *v31; // rdi
  __int64 v32; // rax
  utl::_RefCountBase *v33; // rdx
  utl::_RefCountBase *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  Container::Manager::Core::Details::DebugConfiguration *v37; // rcx
  int CurrentProcessUserSid; // eax
  HLOCAL v39; // rdi
  int DefaultSecurityDescriptor; // eax
  void *v41; // rdx
  Csl *v42; // rsi
  int v43; // eax
  void *v44; // rdx
  void *v45; // rdx
  int v46; // eax
  unsigned int v47; // [rsp+28h] [rbp-E0h]
  int v48; // [rsp+28h] [rbp-E0h]
  unsigned int v49; // [rsp+38h] [rbp-D0h]
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  void *v51[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v52; // [rsp+58h] [rbp-B0h] BYREF
  void *v53[2]; // [rsp+68h] [rbp-A0h] BYREF
  _WORD v54[8]; // [rsp+78h] [rbp-90h] BYREF
  utl::_RefCountBase *v55; // [rsp+88h] [rbp-80h]
  HLOCAL v56; // [rsp+90h] [rbp-78h] BYREF
  utl::_RefCountBase *v57[2]; // [rsp+98h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor[2]; // [rsp+A8h] [rbp-60h] BYREF
  utl::_RefCountBase *v59[2]; // [rsp+B8h] [rbp-50h] BYREF
  void *v60[2]; // [rsp+C8h] [rbp-40h] BYREF
  _WORD v61[8]; // [rsp+D8h] [rbp-30h] BYREF
  utl::_RefCountBase *v62[2]; // [rsp+E8h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp-10h] BYREF
  utl::_RefCountBase *v64; // [rsp+100h] [rbp-8h]
  utl::_RefCountBase *v65; // [rsp+108h] [rbp+0h]
  PTP_WORK pwk; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v67[288]; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]

  if ( (unsigned int)(a4 - 1) > 1 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4F0,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
                  (const char *)0x32,
                  v47);
    if ( (_QWORD *)*a7 != a7 + 2 )
      operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
LABEL_4:
    if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
      operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
    if ( *((_BYTE *)a12 + 216) )
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(a12);
    return LastError;
  }
  v51[0] = &v52;
  v51[1] = &v52;
  v52 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v51,
                           *a7,
                           (__int64)(a7[1] - *a7) >> 1) )
  {
    v17 = 1270;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)0x8007000ELL,
      v47);
    goto LABEL_13;
  }
  v59[0] = (utl::_RefCountBase *)L"sandbox.vmgs";
  v59[1] = (utl::_RefCountBase *)12;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v51) )
  {
    v17 = 1271;
    goto LABEL_12;
  }
  *(_OWORD *)v59 = 0;
  if ( a6 == 2 )
  {
    v19 = utl::make_shared<Csl::CompletionEvent<void>,>(v57);
    v20 = *(utl::_RefCountBase **)v19;
    v21 = *(utl::_RefCountBase **)(v19 + 8);
    *(_QWORD *)v19 = 0;
    *(_QWORD *)(v19 + 8) = 0;
    v59[0] = v20;
    v59[1] = v21;
    if ( v57[1] )
      utl::_RefCountBase::_DecStrong(v57[1]);
    if ( !v20 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x501,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8007000ELL,
        v47);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_13;
    }
    Csl::CompletionEvent<void>::CompleteInternal(v20, 0);
  }
  else
  {
    v21 = v59[1];
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     Container::Manager::Core::Details::ContainerStorage::MaterializeContainerStorageThread,
                     pv,
                     0);
  pwk = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x50B,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
                  v23);
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    if ( v51[0] != &v52 )
      operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( (_QWORD *)*a7 != a7 + 2 )
      operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_4;
  }
  v53[0] = v54;
  v53[1] = v54;
  v54[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v53,
                           *a7,
                           (__int64)(a7[1] - *a7) >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)0x8007000ELL,
      v47);
    if ( v53[0] != v54 )
      operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    goto LABEL_13;
  }
  v57[0] = (utl::_RefCountBase *)L"Bindings";
  v57[1] = (utl::_RefCountBase *)8;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v53) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x510,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)0x8007000ELL,
      v47);
    if ( v53[0] != v54 )
      operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    goto LABEL_13;
  }
  *(_OWORD *)v57 = 0;
  if ( a6 == 2 )
  {
    v25 = utl::make_shared<Container::Manager::Core::Details::BindingStore,>(v62);
    v26 = *(utl::_RefCountBase **)v25;
    v65 = *(utl::_RefCountBase **)(v25 + 8);
    v27 = v65;
    *(_QWORD *)v25 = 0;
    *(_QWORD *)(v25 + 8) = 0;
    v57[0] = v26;
    v57[1] = v27;
    if ( v62[1] )
      utl::_RefCountBase::_DecStrong(v62[1]);
    if ( !v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x518,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8007000ELL,
        v47);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
LABEL_13:
      if ( v51[0] != &v52 )
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)*a7 != a7 + 2 )
        operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
      if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
        operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
      v18 = a12;
      if ( !*((_BYTE *)a12 + 216) )
        return 2147942414LL;
      goto LABEL_140;
    }
    v28 = Container::Manager::Core::Details::BindingStore::Initialize(v26, (const struct Path *)v53);
    v29 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v28,
        v47);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
LABEL_70:
      if ( v51[0] != &v52 )
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)*a7 != a7 + 2 )
        operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
      if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
        operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
      if ( *((_BYTE *)a12 + 216) )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(a12);
      return v29;
    }
  }
  else
  {
    v27 = v57[1];
    v65 = v57[1];
  }
  hKey = 0;
  v30 = Csl::RegistryKey::Duplicate(a11, v24, &hKey);
  v29 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)v30,
      v47);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v27 )
      utl::_RefCountBase::_DecStrong(v27);
    if ( v53[0] != v54 )
      operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    CloseThreadpoolWork(ThreadpoolWork);
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    goto LABEL_70;
  }
  *(_OWORD *)v62 = 0;
  v31 = a12;
  if ( *((_BYTE *)a12 + 216) )
  {
    v60[0] = v61;
    v60[1] = v61;
    v61[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v60,
                             *a7,
                             (__int64)(a7[1] - *a7) >> 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x526,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8007000ELL,
        v47);
      if ( v60[0] != v61 )
        operator delete(v60[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
LABEL_131:
      if ( v51[0] != &v52 )
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)*a7 != a7 + 2 )
        operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
      if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
        operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
      if ( !*((_BYTE *)a12 + 216) )
        return 2147942414LL;
      v18 = a12;
LABEL_140:
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(v18);
      return 2147942414LL;
    }
    AbsoluteSecurityDescriptor[0] = L"Debug";
    AbsoluteSecurityDescriptor[1] = (PSECURITY_DESCRIPTOR)5;
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v60) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x527,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8007000ELL,
        v47);
      if ( v60[0] != v61 )
        operator delete(v60[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_131;
    }
    v32 = utl::make_shared<Container::Manager::Core::Details::DebugConfigurationState,>(&hMem);
    AbsoluteSecurityDescriptor[0] = *(PSECURITY_DESCRIPTOR *)v32;
    v33 = (utl::_RefCountBase *)AbsoluteSecurityDescriptor[0];
    v55 = *(utl::_RefCountBase **)(v32 + 8);
    v34 = v55;
    *(_QWORD *)v32 = 0;
    *(_QWORD *)(v32 + 8) = 0;
    v62[0] = v33;
    v62[1] = v34;
    if ( v64 )
    {
      utl::_RefCountBase::_DecStrong(v64);
      v33 = (utl::_RefCountBase *)AbsoluteSecurityDescriptor[0];
    }
    if ( !v33 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8007000ELL,
        v47);
      if ( v60[0] != v61 )
        operator delete(v60[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_131;
    }
    if ( !*((_BYTE *)a12 + 216) )
      __int2c();
    v35 = Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(v67, a12);
    v36 = Container::Manager::Core::Details::DebugConfigurationState::Initialize(
            AbsoluteSecurityDescriptor[0],
            v35,
            v60);
    v49 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v36,
        v47);
      if ( v60[0] != v61 )
        operator delete(v60[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
LABEL_157:
      if ( v51[0] != &v52 )
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)*a7 != a7 + 2 )
        operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
      if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
        operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
      if ( !*((_BYTE *)a12 + 216) )
        return v49;
      v37 = a12;
LABEL_166:
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(v37);
      return v49;
    }
    if ( v60[0] != v61 )
      operator delete(v60[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  else
  {
    v55 = v62[1];
  }
  v56 = 0;
  if ( a14 )
  {
    v46 = Csl::DuplicateSecurityDescriptor(a14);
    v49 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v46,
        v47);
      if ( v56 )
        LocalFree(v56);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_157;
    }
  }
  else
  {
    hMem = 0;
    CurrentProcessUserSid = Csl::GetCurrentProcessUserSid(&hMem);
    v49 = CurrentProcessUserSid;
    if ( CurrentProcessUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)CurrentProcessUserSid,
        v47);
      if ( hMem )
        LocalFree(hMem);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_157;
    }
    AbsoluteSecurityDescriptor[0] = 0;
    v39 = hMem;
    DefaultSecurityDescriptor = Csl::CreateDefaultSecurityDescriptor(
                                  hMem,
                                  0x1F01BFu,
                                  (PGENERIC_MAPPING)&stru_1801D41F8,
                                  -4,
                                  (__int64)AbsoluteSecurityDescriptor);
    v49 = DefaultSecurityDescriptor;
    if ( DefaultSecurityDescriptor < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x542,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)DefaultSecurityDescriptor,
        v48);
      if ( AbsoluteSecurityDescriptor[0] )
        Csl::DeleteSecurityObjectWrapper((Csl *)AbsoluteSecurityDescriptor[0], v41);
      if ( v39 )
        LocalFree(v39);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
      goto LABEL_201;
    }
    v42 = (Csl *)AbsoluteSecurityDescriptor[0];
    v43 = Csl::DuplicateSecurityDescriptor(AbsoluteSecurityDescriptor[0]);
    v49 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x545,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v43,
        v48);
      if ( v42 )
        Csl::DeleteSecurityObjectWrapper(v42, v45);
      if ( v39 )
        LocalFree(v39);
      if ( v56 )
        LocalFree(v56);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v65 )
        utl::_RefCountBase::_DecStrong(v65);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      CloseThreadpoolWork(ThreadpoolWork);
      if ( v21 )
        utl::_RefCountBase::_DecStrong(v21);
LABEL_201:
      if ( v51[0] != &v52 )
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)*a7 != a7 + 2 )
        operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
      if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
        operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
      v37 = a12;
      if ( !*((_BYTE *)a12 + 216) )
        return v49;
      goto LABEL_166;
    }
    if ( v42 )
      Csl::DeleteSecurityObjectWrapper(v42, v44);
    if ( v39 )
      LocalFree(v39);
    v31 = a12;
  }
  *(_OWORD *)pv = *a2;
  *((_DWORD *)pv + 9) = a3;
  *((_DWORD *)pv + 4) = a4;
  *(_OWORD *)(pv + 20) = *a5;
  Csl::RegistryKey::operator=(pv + 40, &hKey);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 48,
    a7);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 80,
    v51);
  *((_DWORD *)pv + 60) = a6;
  utl::shared_ptr<Csl::CompletionEvent<void>>::operator=(pv + 248, v59);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
    pv + 264,
    &pwk);
  utl::shared_ptr<Csl::CompletionEvent<void>>::operator=(pv + 320, v57);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 112,
    v53);
  *((_DWORD *)pv + 68) = a8;
  utl::optional<Csl::Path>::operator=(pv + 280, a9);
  *((_OWORD *)pv + 22) = *(_OWORD *)a10;
  *((_DWORD *)pv + 92) = *(_DWORD *)(a10 + 16);
  utl::shared_ptr<Csl::CompletionEvent<void>>::operator=(pv + 376, v62);
  *(_OWORD *)(pv + 392) = *a13;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
    pv + 408,
    &v56);
  if ( v56 )
    LocalFree(v56);
  if ( v62[1] )
    utl::_RefCountBase::_DecStrong(v62[1]);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v57[1] )
    utl::_RefCountBase::_DecStrong(v57[1]);
  if ( v53[0] != v54 )
    operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( pwk )
    CloseThreadpoolWork(pwk);
  if ( v59[1] )
    utl::_RefCountBase::_DecStrong(v59[1]);
  if ( v51[0] != &v52 )
    operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (_QWORD *)*a7 != a7 + 2 )
    operator delete((void *)*a7, (const struct std::nothrow_t *)&std::nothrow);
  if ( *(_BYTE *)(a9 + 32) && *(_QWORD *)a9 != a9 + 16 )
    operator delete(*(void **)a9, (const struct std::nothrow_t *)&std::nothrow);
  if ( *((_BYTE *)v31 + 216) )
    Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(v31);
  return 0;
}

```

## disassembly

```asm
0x180082e18  mov     rax, rsp
0x180082e1b  mov     [rax+20h], r9d
0x180082e1f  mov     [rax+18h], r8d
0x180082e23  mov     [rax+10h], rdx
0x180082e27  mov     [rax+8], rcx
0x180082e2b  push    rbp
0x180082e2c  push    rbx
0x180082e2d  push    rsi
0x180082e2e  push    rdi
0x180082e2f  push    r12
0x180082e31  push    r13
0x180082e33  push    r14
0x180082e35  push    r15
0x180082e37  lea     rbp, [rax-138h]
0x180082e3e  sub     rsp, 1F8h
0x180082e45  mov     rdi, rcx
0x180082e48  lea     eax, [r9-1]
0x180082e4c  cmp     eax, 1
0x180082e4f  jbe     loc_180082ED7
0x180082e55  mov     rcx, [rbp+138h]; this
0x180082e5c  mov     r9d, 32h ; '2'; char *
0x180082e62  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180082e69  mov     edx, 4F0h; void *
0x180082e6e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180082e73  mov     ebx, eax
0x180082e75  mov     rdx, [rbp+130h+arg_30]
0x180082e7c  mov     rcx, [rdx]; void *
0x180082e7f  add     rdx, 10h
0x180082e83  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180082e8a  cmp     rcx, rdx
0x180082e8d  jz      short loc_180082E97
0x180082e8f  mov     rdx, r15; struct std::nothrow_t *
0x180082e92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082e97  xor     r14d, r14d
0x180082e9a  mov     rax, [rbp+130h+arg_40]
0x180082ea1  cmp     [rax+20h], r14b
0x180082ea5  jz      short loc_180082EBB
0x180082ea7  mov     rcx, [rax]; void *
0x180082eaa  add     rax, 10h
0x180082eae  cmp     rcx, rax
0x180082eb1  jz      short loc_180082EBB
0x180082eb3  mov     rdx, r15; struct std::nothrow_t *
0x180082eb6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082ebb  mov     rcx, [rbp+130h+arg_58]; this
0x180082ec2  cmp     [rcx+0D8h], r14b
0x180082ec9  jz      short loc_180082ED0
0x180082ecb  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x180082ed0  mov     eax, ebx
0x180082ed2  jmp     loc_180083DCB
0x180082ed7  lea     rax, [rsp+230h+var_1E0]
0x180082edc  mov     [rsp+230h+var_1F0], rax
0x180082ee1  lea     rax, [rsp+230h+var_1E0]
0x180082ee6  mov     qword ptr [rsp+230h+var_1E8], rax
0x180082eeb  xor     r14d, r14d
0x180082eee  mov     [rsp+230h+var_1E0], r14w
0x180082ef4  mov     r12, [rbp+130h+arg_30]
0x180082efb  mov     r8, [r12+8]
0x180082f00  sub     r8, [r12]
0x180082f04  sar     r8, 1
0x180082f07  mov     rdx, [r12]
0x180082f0b  lea     rcx, [rsp+230h+var_1F0]
0x180082f10  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180082f15  test    al, al
0x180082f17  jnz     loc_180082FAA
0x180082f1d  mov     edx, 4F6h; void *
0x180082f22  mov     r9d, 8007000Eh; char *
0x180082f28  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180082f2f  mov     rcx, [rbp+138h]; this
0x180082f36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082f3b  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180082f42  lea     rax, [rsp+230h+var_1E0]
0x180082f47  mov     rcx, [rsp+230h+var_1F0]; void *
0x180082f4c  cmp     rcx, rax
0x180082f4f  jz      short loc_180082F59
0x180082f51  mov     rdx, r15; struct std::nothrow_t *
0x180082f54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082f59  lea     rax, [r12+10h]
0x180082f5e  cmp     [r12], rax
0x180082f62  jz      short loc_180082F70
0x180082f64  mov     rdx, r15; struct std::nothrow_t *
0x180082f67  mov     rcx, [r12]; void *
0x180082f6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082f70  mov     rax, [rbp+130h+arg_40]
0x180082f77  cmp     [rax+20h], r14b
0x180082f7b  jz      short loc_180082F91
0x180082f7d  mov     rcx, [rax]; void *
0x180082f80  add     rax, 10h
0x180082f84  cmp     rcx, rax
0x180082f87  jz      short loc_180082F91
0x180082f89  mov     rdx, r15; struct std::nothrow_t *
0x180082f8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082f91  mov     rcx, [rbp+130h+arg_58]
0x180082f98  cmp     [rcx+0D8h], r14b
0x180082f9f  jz      loc_180083749
0x180082fa5  jmp     loc_180083744
0x180082faa  lea     rax, aSandboxVmgs; "sandbox.vmgs"
0x180082fb1  mov     [rbp+130h+var_180], rax
0x180082fb5  mov     [rbp+130h+var_180+8], 0Ch
0x180082fbd  lea     rdx, [rbp+130h+var_180]
0x180082fc1  lea     rcx, [rsp+230h+var_1F0]; this
0x180082fc6  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180082fcb  test    al, al
0x180082fcd  jnz     short loc_180082FD9
0x180082fcf  mov     edx, 4F7h
0x180082fd4  jmp     loc_180082F22
0x180082fd9  xorps   xmm0, xmm0
0x180082fdc  movdqu  xmmword ptr [rbp+130h+var_180], xmm0
0x180082fe1  mov     esi, [rbp+130h+arg_28]
0x180082fe7  cmp     esi, 2
0x180082fea  jnz     short loc_18008305D
0x180082fec  lea     rcx, [rbp+130h+var_1A0]
0x180082ff0  call    ??$make_shared@V?$CompletionEvent@X@Csl@@$$V@utl@@YA?AV?$shared_ptr@V?$CompletionEvent@X@Csl@@@0@XZ; utl::make_shared<Csl::CompletionEvent<void>,>(void)
0x180082ff5  mov     rbx, [rax]
0x180082ff8  mov     r13, [rax+8]
0x180082ffc  mov     [rax], r14
0x180082fff  mov     [rax+8], r14
0x180083003  mov     [rbp+130h+var_180], rbx
0x180083007  mov     [rbp+130h+var_180+8], r13
0x18008300b  mov     rcx, [rbp+130h+var_1A0+8]; this
0x18008300f  test    rcx, rcx
0x180083012  jz      short loc_18008301A
0x180083014  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180083019  nop
0x18008301a  test    rbx, rbx
0x18008301d  jnz     short loc_180083051
0x18008301f  mov     rcx, [rbp+138h]; this
0x180083026  mov     r9d, 8007000Eh; char *
0x18008302c  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180083033  mov     edx, 501h; void *
0x180083038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008303d  nop
0x18008303e  test    r13, r13
0x180083041  jz      short loc_18008304C
0x180083043  mov     rcx, r13; this
0x180083046  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008304b  nop
0x18008304c  jmp     loc_180082F3B
0x180083051  xor     edx, edx
0x180083053  mov     rcx, rbx
0x180083056  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x18008305b  jmp     short loc_180083061
0x18008305d  mov     r13, [rbp+130h+var_180+8]
0x180083061  xor     r8d, r8d; pcbe
0x180083064  mov     rdx, rdi; pv
0x180083067  lea     rcx, ?MaterializeContainerStorageThread@ContainerStorage@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18008306e  call    cs:__imp_CreateThreadpoolWork
0x180083075  nop     dword ptr [rax+rax+00h]
0x18008307a  mov     rbx, rax
0x18008307d  mov     [rbp+130h+pwk], rax
0x180083081  test    rax, rax
0x180083084  jnz     short loc_1800830EC
0x180083086  mov     rcx, [rbp+138h]; this
0x18008308d  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180083094  mov     edx, 50Bh; void *
0x180083099  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008309e  mov     ebx, eax
0x1800830a0  test    r13, r13
0x1800830a3  jz      short loc_1800830AE
0x1800830a5  mov     rcx, r13; this
0x1800830a8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800830ad  nop
0x1800830ae  mov     rcx, [rsp+230h+var_1F0]; void *
0x1800830b3  lea     rax, [rsp+230h+var_1E0]
0x1800830b8  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800830bf  cmp     rcx, rax
0x1800830c2  jz      short loc_1800830CC
0x1800830c4  mov     rdx, r15; struct std::nothrow_t *
0x1800830c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800830cc  lea     rax, [r12+10h]
0x1800830d1  cmp     [r12], rax
0x1800830d5  jz      loc_180082E9A
0x1800830db  mov     rdx, r15; struct std::nothrow_t *
0x1800830de  mov     rcx, [r12]; void *
0x1800830e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800830e7  jmp     loc_180082E9A
0x1800830ec  lea     rax, [rsp+70h]
0x1800830f1  mov     [rsp+230h+var_1D0], rax
0x1800830f6  lea     rax, [rsp+70h]
0x1800830fb  mov     qword ptr [rsp+230h+var_1C8], rax
0x180083100  mov     [rsp+70h], r14w
0x180083106  mov     r8, [r12+8]
0x18008310b  sub     r8, [r12]
0x18008310f  sar     r8, 1
0x180083112  mov     rdx, [r12]
0x180083116  lea     rcx, [rsp+230h+var_1D0]
0x18008311b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180083120  test    al, al
0x180083122  jnz     short loc_180083183
0x180083124  mov     rcx, [rbp+138h]; this
0x18008312b  mov     r9d, 8007000Eh; char *
0x180083131  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180083138  mov     edx, 50Fh; void *
0x18008313d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083142  mov     rcx, [rsp+230h+var_1D0]; void *
0x180083147  lea     rax, [rsp+70h]
0x18008314c  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180083153  cmp     rcx, rax
0x180083156  jz      short loc_180083160
0x180083158  mov     rdx, r15; struct std::nothrow_t *
0x18008315b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180083160  mov     rcx, rbx; pwk
0x180083163  call    cs:__imp_CloseThreadpoolWork
0x18008316a  nop     dword ptr [rax+rax+00h]
0x18008316f  nop
0x180083170  test    r13, r13
0x180083173  jz      short loc_18008317E
0x180083175  mov     rcx, r13; this
0x180083178  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008317d  nop
0x18008317e  jmp     loc_180082F42
0x180083183  lea     rax, aBindings; "Bindings"
0x18008318a  mov     [rbp+130h+var_1A0], rax
0x18008318e  mov     [rbp+130h+var_1A0+8], 8
0x180083196  lea     rdx, [rbp+130h+var_1A0]
0x18008319a  lea     rcx, [rsp+230h+var_1D0]; this
0x18008319f  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800831a4  test    al, al
0x1800831a6  jnz     short loc_180083207
0x1800831a8  mov     rcx, [rbp+138h]; this
0x1800831af  mov     r9d, 8007000Eh; char *
0x1800831b5  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800831bc  mov     edx, 510h; void *
0x1800831c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800831c6  mov     rcx, [rsp+230h+var_1D0]; void *
0x1800831cb  lea     rax, [rsp+70h]
0x1800831d0  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800831d7  cmp     rcx, rax
0x1800831da  jz      short loc_1800831E4
0x1800831dc  mov     rdx, r15; struct std::nothrow_t *
0x1800831df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800831e4  mov     rcx, rbx; pwk
0x1800831e7  call    cs:__imp_CloseThreadpoolWork
0x1800831ee  nop     dword ptr [rax+rax+00h]
0x1800831f3  nop
0x1800831f4  test    r13, r13
0x1800831f7  jz      short loc_180083202
0x1800831f9  mov     rcx, r13; this
0x1800831fc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180083201  nop
0x180083202  jmp     loc_180082F42
0x180083207  xorps   xmm0, xmm0
0x18008320a  movdqu  xmmword ptr [rbp+130h+var_1A0], xmm0
0x18008320f  cmp     esi, 2
0x180083212  jnz     loc_1800833A5
0x180083218  lea     rcx, [rbp+130h+var_150]
0x18008321c  call    ??$make_shared@VBindingStore@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@VBindingStore@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::BindingStore,>(void)
0x180083221  mov     rdi, [rax]
0x180083224  mov     rsi, [rax+8]
0x180083228  mov     [rbp+130h+var_130], rsi
0x18008322c  mov     [rax], r14
0x18008322f  mov     [rax+8], r14
0x180083233  mov     [rbp+130h+var_1A0], rdi
0x180083237  mov     [rbp+130h+var_1A0+8], rsi
0x18008323b  mov     rcx, [rbp+130h+var_150+8]; this
0x18008323f  test    rcx, rcx
0x180083242  jz      short loc_18008324A
0x180083244  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180083249  nop
0x18008324a  test    rdi, rdi
0x18008324d  jnz     short loc_1800832BD
0x18008324f  mov     rcx, [rbp+138h]; this
0x180083256  mov     r9d, 8007000Eh; char *
0x18008325c  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180083263  mov     edx, 518h; void *
0x180083268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008326d  nop
0x18008326e  test    rsi, rsi
0x180083271  jz      short loc_18008327C
0x180083273  mov     rcx, rsi; this
0x180083276  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18008327b  nop
0x18008327c  mov     rcx, [rsp+230h+var_1D0]; void *
0x180083281  lea     rax, [rsp+70h]
0x180083286  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18008328d  cmp     rcx, rax
0x180083290  jz      short loc_18008329A
0x180083292  mov     rdx, r15; struct std::nothrow_t *
0x180083295  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008329a  mov     rcx, rbx; pwk
0x18008329d  call    cs:__imp_CloseThreadpoolWork
0x1800832a4  nop     dword ptr [rax+rax+00h]
0x1800832a9  nop
0x1800832aa  test    r13, r13
0x1800832ad  jz      short loc_1800832B8
0x1800832af  mov     rcx, r13; this
0x1800832b2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800832b7  nop
0x1800832b8  jmp     loc_180082F42
0x1800832bd  lea     rdx, [rsp+230h+var_1D0]; struct Path *
0x1800832c2  mov     rcx, rdi; this
0x1800832c5  call    ?Initialize@BindingStore@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::BindingStore::Initialize(Csl::Path const &)
0x1800832ca  mov     edi, eax
0x1800832cc  test    eax, eax
0x1800832ce  jns     loc_1800833AD
0x1800832d4  mov     rcx, [rbp+138h]; this
0x1800832db  mov     r9d, eax; char *
0x1800832de  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800832e5  mov     edx, 51Ah; void *
0x1800832ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800832ef  nop
  ... truncated ...
```
