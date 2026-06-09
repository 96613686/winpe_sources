# Container::Manager::Core::Details::ResourceBroker::MergeResources(utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>,utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>>>,Csl::DurableRegistryTransaction)

- ea: `0x18005eff0`
- end: `0x18005f868`
- name: `?MergeResources@ResourceBroker@Details@Core@Manager@Container@@QEAAJV?$vector@V?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@V?$vector@V?$unique_ptr@VContainerStorage@Details@Core@Manager@Container@@U?$default_delete@VContainerStorage@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VContainerStorage@Details@Core@Manager@Container@@U?$default_delete@VContainerStorage@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@VDurableRegistryTransaction@Csl@@@Z`
- size: `2168`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006a0a8`

## callees

- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18002c5b4`
- `0x180032344`
- `0x1800329ec`
- `0x180032b24`
- `0x180032d70`
- `0x18003bb20`
- `0x1800471dc`
- `0x18004dfa0`
- `0x18004e000`
- `0x18004e644`
- `0x18004e84c`
- `0x18004f630`
- `0x18005ad78`
- `0x18005aea4`
- `0x18005e8f0`
- `0x18005eff0`
- `0x1800660a4`
- `0x1800cb3f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f424`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f424`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f699`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005f36d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18005f36d`

## string_xrefs

- `0x18005f39e`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18005f38f`: `Failed to delete subkey transacted with name '%ws'`
- `0x18005f07d`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f23e`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f2ad`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f2e9`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f52c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f5e3`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f6aa`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f760`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f83e`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005f853`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ResourceBroker::MergeResources(
        RTL_SRWLOCK *a1,
        const struct _GUID ***a2,
        __int64 a3,
        Csl::DurableRegistryTransaction *a4)
{
  Csl::DurableRegistryTransaction *v4; // rsi
  const struct _GUID **v7; // rdi
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // rbx
  const struct _GUID **v12; // rdx
  const struct _GUID **v13; // r8
  void *v14; // rdx
  bool v15; // zf
  void **v16; // r13
  int v17; // eax
  unsigned int v18; // esi
  __int64 *Ptr; // rax
  const struct _GUID *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  utl::_RefCountBase *v23; // rcx
  Container::Manager::Core::Details::Resource *v24; // r12
  struct _GUID *v25; // rax
  int v26; // eax
  const char *v27; // r9
  Container::Manager::Core::Details::Resource *v28; // rsi
  __int64 v29; // rcx
  void *v30; // rbx
  HKEY *v31; // rbx
  HKEY *v32; // rdi
  void *v33; // r13
  int v34; // eax
  const char *v35; // rsi
  unsigned int v36; // eax
  __int64 v37; // rdx
  HKEY v38; // r13
  int v39; // eax
  HKEY *v40; // r13
  DWORD LastError; // esi
  HKEY v42; // rcx
  Container::Manager::Core::Details::Resource *v43; // rsi
  HKEY v44; // rax
  int v45; // eax
  unsigned int v46; // r13d
  const char *v47; // r9
  Container::Manager::Core::Details::Resource *v48; // rsi
  __int64 v49; // rcx
  void *v50; // rbx
  const struct _GUID **v51; // rdx
  const struct _GUID **v52; // r8
  void *v53; // rdx
  __int64 v54; // r8
  void *v55; // rbx
  const struct _GUID **v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // rdx
  unsigned __int64 v60; // r9
  __int64 v61; // rdx
  int v62; // eax
  __int64 v63; // rcx
  const struct _GUID **v64; // rdx
  __int64 v65; // r8
  void *v66; // rdx
  __int64 v67; // r8
  const struct _GUID **v69; // rdx
  const struct _GUID **v70; // r8
  void *v71; // rdx
  __int64 v72; // r8
  int hTransaction; // [rsp+20h] [rbp-A9h]
  int hTransactionb; // [rsp+20h] [rbp-A9h]
  int hTransactiona; // [rsp+20h] [rbp-A9h]
  void *v76[2]; // [rsp+40h] [rbp-89h] BYREF
  __int64 v77; // [rsp+50h] [rbp-79h]
  HKEY v78; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-69h] BYREF
  _WORD v80[8]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v81; // [rsp+80h] [rbp-49h] BYREF
  __int64 v82; // [rsp+90h] [rbp-39h]
  __int128 v83; // [rsp+98h] [rbp-31h] BYREF
  char v84; // [rsp+B0h] [rbp-19h]
  _OWORD v85[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v86; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  Container::Manager::Core::Details::Resource *v89; // [rsp+138h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+140h] [rbp+77h] BYREF
  Csl::DurableRegistryTransaction *v91; // [rsp+148h] [rbp+7Fh]

  v91 = a4;
  v4 = a4;
  *(__m128i *)v76 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v77 = -1;
  v7 = a2[1];
  v8 = *a2;
  v9 = ((__int64)(*(_QWORD *)(a3 + 8) - *(_QWORD *)a3) >> 3) + v7 - *a2;
  if ( v9 )
  {
    if ( v9 >= 0x1000000000000000LL
      || !(unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::_SetCapacity(v76) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD97,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        hTransaction);
      v11 = v76[0];
      if ( v76[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(
          v10,
          v76[0],
          ((char *)v76[1] - (char *)v76[0]) >> 3);
        operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
      }
      v12 = *a2;
      if ( *a2 != (const struct _GUID **)-1LL )
      {
        v13 = a2[1];
        a2[1] = v12;
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(
          v10,
          v12,
          v13 - v12);
        operator delete(*a2, (const struct std::nothrow_t *)&std::nothrow);
      }
      v14 = *(void **)a3;
      v15 = *(_QWORD *)a3 == -1;
LABEL_66:
      if ( !v15 )
      {
        v58 = *(_QWORD *)(a3 + 8) - (_QWORD)v14;
        *(_QWORD *)(a3 + 8) = v14;
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>>>(
          v10,
          v14,
          v58 >> 3);
        operator delete(*(void **)a3, (const struct std::nothrow_t *)&std::nothrow);
      }
      v18 = -2147024882;
      goto LABEL_85;
    }
    v8 = *a2;
    v7 = a2[1];
  }
  v16 = (void **)((char *)v4 + 8);
  while ( v8 != v7 )
  {
    v16 = (void **)((char *)v4 + 8);
    v17 = Container::Manager::Core::Details::LayerStore::Remove(
            *(Container::Manager::Core::Details::LayerStore **)&(*v8)[16].Data1,
            *v8,
            *((void **)v4 + 1));
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v17,
        hTransaction);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)v18,
        hTransactionb);
      goto LABEL_25;
    }
    Ptr = (__int64 *)a1[14].Ptr;
    v20 = *v8;
    v21 = *Ptr;
    v22 = Ptr[1];
    if ( v22 )
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    *(_QWORD *)&v20[16].Data1 = v21;
    v23 = *(utl::_RefCountBase **)v20[16].Data4;
    *(_QWORD *)v20[16].Data4 = v22;
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    wil::make_unique_nothrow<Container::Manager::Core::Details::Resource,>(&v89);
    v24 = v89;
    if ( !v89 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDAA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        hTransaction);
LABEL_61:
      v55 = v76[0];
      if ( v76[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(
          v10,
          v76[0],
          ((char *)v76[1] - (char *)v76[0]) >> 3);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      v56 = *a2;
      if ( *a2 != (const struct _GUID **)-1LL )
      {
        v57 = (char *)a2[1] - (char *)v56;
        a2[1] = v56;
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(
          v10,
          v56,
          v57 >> 3);
        operator delete(*a2, (const struct std::nothrow_t *)&std::nothrow);
      }
      v14 = *(void **)a3;
      v15 = *(_QWORD *)a3 == -1;
      goto LABEL_66;
    }
    v25 = (struct _GUID *)*v8;
    *v8 = 0;
    hKey = (HKEY)v25;
    v26 = Container::Manager::Core::Details::Resource::Initialize(
            (_DWORD)v24,
            (unsigned int)&hKey,
            (_DWORD)a1,
            (int)a1 + 264,
            (__int64)&a1[35],
            (int)a1 + 296,
            (__int64)&a1[39],
            (__int64)&a1[41]);
    v18 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB2,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v26,
        hTransaction);
      if ( v24 )
      {
        Container::Manager::Core::Details::Resource::~Resource(v24);
        operator delete(v24, (const struct std::nothrow_t *)0x110);
      }
LABEL_25:
      v30 = v76[0];
      if ( v76[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(
          v29,
          v76[0],
          ((char *)v76[1] - (char *)v76[0]) >> 3);
        operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
      }
LABEL_81:
      v64 = *a2;
      if ( *a2 != (const struct _GUID **)-1LL )
      {
        v65 = (char *)a2[1] - (char *)v64;
        a2[1] = v64;
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(
          v29,
          v64,
          v65 >> 3);
        operator delete(*a2, (const struct std::nothrow_t *)&std::nothrow);
      }
      v66 = *(void **)a3;
      if ( *(_QWORD *)a3 != -1 )
      {
        v67 = *(_QWORD *)(a3 + 8) - (_QWORD)v66;
        *(_QWORD *)(a3 + 8) = v66;
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>>>(
          v29,
          v66,
          v67 >> 3);
        operator delete(*(void **)a3, (const struct std::nothrow_t *)&std::nothrow);
      }
      goto LABEL_85;
    }
    if ( !(unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,0>(
                             v76,
                             &v89) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xDB5,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        v27);
    v28 = v89;
    v89 = 0;
    if ( v28 )
    {
      Container::Manager::Core::Details::Resource::~Resource(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x110);
    }
    ++v8;
    v4 = v91;
  }
  v31 = *(HKEY **)a3;
  v32 = *(HKEY **)(a3 + 8);
  while ( 1 )
  {
    if ( v31 == v32 )
    {
      memset(v85, 0, sizeof(v85));
      v86 = 0;
      v83 = 0;
      Csl::DurableRegistryTransaction::operator=(&v83, v4);
      v84 = 1;
      v81 = *(_OWORD *)v76;
      v82 = v77;
      v62 = Container::Manager::Core::Details::ResourceBroker::MergeResources(
              a1,
              &v81,
              (Csl::DurableRegistryTransaction *)&v83,
              (__int64)v85);
      v18 = v62;
      if ( v62 >= 0 )
      {
        v69 = *a2;
        if ( *a2 != (const struct _GUID **)-1LL )
        {
          v70 = a2[1];
          a2[1] = v69;
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(
            v63,
            v69,
            v70 - v69);
          operator delete(*a2, (const struct std::nothrow_t *)&std::nothrow);
        }
        v71 = *(void **)a3;
        if ( *(_QWORD *)a3 != -1 )
        {
          v72 = *(_QWORD *)(a3 + 8);
          *(_QWORD *)(a3 + 8) = v71;
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>>>(
            v63,
            v71,
            (v72 - (__int64)v71) >> 3);
          operator delete(*(void **)a3, (const struct std::nothrow_t *)&std::nothrow);
        }
        Csl::DurableRegistryTransaction::~DurableRegistryTransaction(v91);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDD9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v62,
        hTransaction);
      goto LABEL_81;
    }
    hKey = *v31;
    v33 = *v16;
    lpSubKey[0] = v80;
    lpSubKey[1] = v80;
    v80[0] = 0;
    v34 = Csl::GuidToString(hKey, lpSubKey);
    v18 = v34;
    if ( v34 < 0 )
    {
      v60 = (unsigned int)v34;
      v61 = 2694;
LABEL_76:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)v60,
        hTransaction);
      if ( lpSubKey[0] != v80 )
        operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
      v59 = 3516;
      goto LABEL_72;
    }
    v35 = (const char *)lpSubKey[0];
    v36 = RegDeleteKeyTransactedW(*((HKEY *)hKey + 5), lpSubKey[0], 0, 0, v33, 0);
    if ( v36 == 2 )
    {
      v18 = -2147024894;
LABEL_74:
      v60 = v18;
      v61 = 2696;
      goto LABEL_76;
    }
    if ( v36 )
    {
      v18 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x12B,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
              (const char *)v36,
              (unsigned int)"Failed to delete subkey transacted with name '%ws'",
              v35);
      if ( (v18 & 0x80000000) != 0 )
        goto LABEL_74;
    }
    if ( lpSubKey[0] != v80 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    v38 = *v31;
    v78 = 0;
    v39 = Csl::RegistryKey::Duplicate((char *)a1[9].Ptr + 8, v37, &v78);
    v18 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v39,
        hTransaction);
      if ( v78 )
        RegCloseKey(v78);
      v59 = 3525;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v59,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)v18,
        hTransactiona);
      goto LABEL_25;
    }
    v40 = (HKEY *)(v38 + 10);
    if ( v40 == &v78 )
    {
      v42 = v78;
    }
    else
    {
      hKey = *v40;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(hKey);
        SetLastError(LastError);
      }
      *v40 = v78;
      v42 = 0;
    }
    if ( v42 )
      RegCloseKey(v42);
    wil::make_unique_nothrow<Container::Manager::Core::Details::Resource,>(&v89);
    v43 = v89;
    if ( !v89 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDC9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)0x8007000ELL,
        hTransaction);
      goto LABEL_61;
    }
    v44 = *v31;
    *v31 = 0;
    hKey = v44;
    v45 = Container::Manager::Core::Details::Resource::Initialize(
            (__int64)v43,
            (Container::Manager::Core::Details::ContainerStorage **)&hKey,
            (__int64)a1,
            (__int64)&a1[33],
            (__int64)&a1[35],
            (int)a1 + 296);
    v46 = v45;
    if ( v45 < 0 )
      break;
    if ( !(unsigned __int8)utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,0>(
                             v76,
                             &v89) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xDD4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        v47);
    v48 = v89;
    v89 = 0;
    if ( v48 )
    {
      Container::Manager::Core::Details::Resource::~Resource(v48);
      operator delete(v48, (const struct std::nothrow_t *)0x110);
    }
    ++v31;
    v4 = v91;
    v16 = (void **)((char *)v91 + 8);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDD1,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
    (const char *)(unsigned int)v45,
    hTransaction);
  if ( v43 )
  {
    Container::Manager::Core::Details::Resource::~Resource(v43);
    operator delete(v43, (const struct std::nothrow_t *)0x110);
  }
  v50 = v76[0];
  if ( v76[0] != (void *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(
      v49,
      v76[0],
      ((char *)v76[1] - (char *)v76[0]) >> 3);
    operator delete(v50, (const struct std::nothrow_t *)&std::nothrow);
  }
  v51 = *a2;
  if ( *a2 != (const struct _GUID **)-1LL )
  {
    v52 = a2[1];
    a2[1] = v51;
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(
      v49,
      v51,
      v52 - v51);
    operator delete(*a2, (const struct std::nothrow_t *)&std::nothrow);
  }
  v53 = *(void **)a3;
  if ( *(_QWORD *)a3 != -1 )
  {
    v54 = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(a3 + 8) = v53;
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>>>(
      v49,
      v53,
      (v54 - (__int64)v53) >> 3);
    operator delete(*(void **)a3, (const struct std::nothrow_t *)&std::nothrow);
  }
  v18 = v46;
LABEL_85:
  Csl::DurableRegistryTransaction::~DurableRegistryTransaction(v91);
  return v18;
}

```

## disassembly

```asm
0x18005eff0  mov     [rsp-8+arg_18], r9
0x18005eff5  mov     [rsp-8+arg_0], rcx
0x18005effa  push    rbp
0x18005effb  push    rbx
0x18005effc  push    rsi
0x18005effd  push    rdi
0x18005effe  push    r12
0x18005f000  push    r13
0x18005f002  push    r14
0x18005f004  push    r15
0x18005f006  lea     rbp, [rsp-1Fh]
0x18005f00b  sub     rsp, 0E8h
0x18005f012  mov     rsi, r9
0x18005f015  mov     r14, r8
0x18005f018  mov     r15, rdx
0x18005f01b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18005f023  movdqu  xmmword ptr [rsp+120h+var_E0], xmm0
0x18005f029  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005f02d  mov     [rbp+57h+var_D0], r13
0x18005f031  mov     rdi, [rdx+8]
0x18005f035  mov     rbx, [rdx]
0x18005f038  mov     rdx, rdi
0x18005f03b  sub     rdx, rbx
0x18005f03e  sar     rdx, 3
0x18005f042  mov     rax, [r8+8]
0x18005f046  sub     rax, [r8]
0x18005f049  sar     rax, 3
0x18005f04d  add     rdx, rax
0x18005f050  jz      loc_18005F10E
0x18005f056  cmp     rdx, 8
0x18005f05a  jbe     loc_18005F0F0
0x18005f060  mov     rax, 0FFFFFFFFFFFFFFFh
0x18005f06a  cmp     rdx, rax
0x18005f06d  jbe     loc_18005F0F5
0x18005f073  mov     rcx, [rbp+5Fh]; this
0x18005f077  mov     r9d, 8007000Eh; char *
0x18005f07d  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005f084  mov     edx, 0D97h; void *
0x18005f089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f08e  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005f095  mov     rbx, [rsp+120h+var_E0]
0x18005f09a  cmp     rbx, r13
0x18005f09d  jz      short loc_18005F0BE
0x18005f09f  mov     r8, [rsp+120h+var_E0+8]
0x18005f0a4  sub     r8, rbx
0x18005f0a7  sar     r8, 3
0x18005f0ab  mov     rdx, rbx
0x18005f0ae  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>> &,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>> *,unsigned __int64)
0x18005f0b3  mov     rdx, r12; struct std::nothrow_t *
0x18005f0b6  mov     rcx, rbx; void *
0x18005f0b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f0be  mov     rdx, [r15]
0x18005f0c1  cmp     rdx, r13
0x18005f0c4  jz      short loc_18005F0E5
0x18005f0c6  mov     r8, [r15+8]
0x18005f0ca  mov     [r15+8], rdx
0x18005f0ce  sub     r8, rdx
0x18005f0d1  sar     r8, 3
0x18005f0d5  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>> &,wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>> *,unsigned __int64)
0x18005f0da  mov     rdx, r12; struct std::nothrow_t *
0x18005f0dd  mov     rcx, [r15]; void *
0x18005f0e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f0e5  mov     rdx, [r14]
0x18005f0e8  cmp     rdx, r13
0x18005f0eb  jmp     loc_18005F64D
0x18005f0f0  mov     edx, 8
0x18005f0f5  lea     rcx, [rsp+120h+var_E0]
0x18005f0fa  call    ?_SetCapacity@?$vector@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::_SetCapacity(unsigned __int64)
0x18005f0ff  test    al, al
0x18005f101  jz      loc_18005F073
0x18005f107  mov     rbx, [r15]
0x18005f10a  mov     rdi, [r15+8]
0x18005f10e  lea     r13, [rsi+8]
0x18005f112  cmp     rbx, rdi
0x18005f115  jz      loc_18005F2FF
0x18005f11b  mov     rcx, [rbx]
0x18005f11e  lea     r13, [rsi+8]
0x18005f122  mov     r8, [r13+0]; void *
0x18005f126  mov     rdx, rcx; struct _GUID *
0x18005f129  mov     rcx, [rcx+100h]; this
0x18005f130  call    ?Remove@LayerStore@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@PEAX@Z; Container::Manager::Core::Details::LayerStore::Remove(_GUID const &,void *)
0x18005f135  mov     esi, eax
0x18005f137  test    eax, eax
0x18005f139  js      loc_18005F2CA
0x18005f13f  mov     rsi, [rbp+57h+arg_0]
0x18005f143  mov     rax, [rsi+70h]
0x18005f147  mov     r8, [rbx]
0x18005f14a  mov     rcx, [rax]
0x18005f14d  mov     rdx, [rax+8]
0x18005f151  test    rdx, rdx
0x18005f154  jz      short loc_18005F15A
0x18005f156  lock inc dword ptr [rdx+8]
0x18005f15a  mov     [r8+100h], rcx
0x18005f161  mov     rcx, [r8+108h]; this
0x18005f168  mov     [r8+108h], rdx
0x18005f16f  test    rcx, rcx
0x18005f172  jz      short loc_18005F17A
0x18005f174  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005f179  nop
0x18005f17a  lea     rcx, [rbp+57h+arg_8]
0x18005f17e  call    ??$make_unique_nothrow@VResource@Details@Core@Manager@Container@@$$V@wil@@YA?AV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Container::Manager::Core::Details::Resource,>(void)
0x18005f183  mov     r12, [rbp+57h+arg_8]
0x18005f187  test    r12, r12
0x18005f18a  jz      loc_18005F2A3
0x18005f190  mov     rax, [rbx]
0x18005f193  mov     qword ptr [rbx], 0
0x18005f19a  mov     [rbp+57h+hKey], rax
0x18005f19e  lea     rax, [rsi+148h]
0x18005f1a5  lea     rcx, [rsi+138h]
0x18005f1ac  lea     rdx, [rsi+128h]
0x18005f1b3  lea     r8, [rsi+118h]
0x18005f1ba  lea     r9, [rsi+108h]
0x18005f1c1  mov     [rsp+120h+var_E8], rax
0x18005f1c6  mov     [rsp+120h+var_F0], rcx
0x18005f1cb  mov     [rsp+120h+pExtendedParameter], rdx
0x18005f1d0  mov     [rsp+120h+hTransaction], r8; int
0x18005f1d5  mov     r8, rsi
0x18005f1d8  lea     rdx, [rbp+57h+hKey]
0x18005f1dc  mov     rcx, r12
0x18005f1df  call    ?Initialize@Resource@Details@Core@Manager@Container@@AEAAJV?$unique_ptr@VLayer@Details@Core@Manager@Container@@U?$default_delete@VLayer@Details@Core@Manager@Container@@@wistd@@@wistd@@PEAVResourceBroker@2345@AEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VConfigurationBuilder@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VLogManager@Details@Core@Manager@Container@@@utl@@@Z; Container::Manager::Core::Details::Resource::Initialize(wistd::unique_ptr<Container::Manager::Core::Details::Layer,wistd::default_delete<Container::Manager::Core::Details::Layer>>,Container::Manager::Core::Details::ResourceBroker *,utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &,utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> const &,utl::shared_ptr<Container::Manager::Core::Details::ConfigurationBuilder> const &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &,utl::shared_ptr<Container::Manager::Core::Details::LogManager> const &)
0x18005f1e4  mov     esi, eax
0x18005f1e6  test    eax, eax
0x18005f1e8  js      short loc_18005F237
0x18005f1ea  mov     rsi, [rbp+5Fh]
0x18005f1ee  lea     rdx, [rbp+57h+arg_8]
0x18005f1f2  lea     rcx, [rsp+120h+var_E0]
0x18005f1f7  call    ??$emplace_back@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@$0A@@?$vector@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAA_N$$QEAV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,0>(wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>> &&)
0x18005f1fc  test    al, al
0x18005f1fe  jz      loc_18005F853
0x18005f204  mov     rsi, [rbp+57h+arg_8]
0x18005f208  mov     [rbp+57h+arg_8], 0
0x18005f210  test    rsi, rsi
0x18005f213  jz      short loc_18005F22A
0x18005f215  mov     rcx, rsi; this
0x18005f218  call    ??1Resource@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::Resource::~Resource(void)
0x18005f21d  mov     edx, 110h; struct std::nothrow_t *
0x18005f222  mov     rcx, rsi; void *
0x18005f225  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f22a  add     rbx, 8
0x18005f22e  mov     rsi, [rbp+57h+arg_18]
0x18005f232  jmp     loc_18005F112
0x18005f237  mov     rcx, [rbp+5Fh]; this
0x18005f23b  mov     r9d, eax; char *
0x18005f23e  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005f245  mov     edx, 0DB2h; void *
0x18005f24a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f24f  test    r12, r12
0x18005f252  jz      short loc_18005F269
0x18005f254  mov     rcx, r12; this
0x18005f257  call    ??1Resource@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::Resource::~Resource(void)
0x18005f25c  mov     edx, 110h; struct std::nothrow_t *
0x18005f261  mov     rcx, r12; void *
0x18005f264  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f269  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005f270  mov     rbx, [rsp+120h+var_E0]
0x18005f275  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005f279  jz      loc_18005F771
0x18005f27f  mov     r8, [rsp+120h+var_E0+8]
0x18005f284  sub     r8, rbx
0x18005f287  sar     r8, 3
0x18005f28b  mov     rdx, rbx
0x18005f28e  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>> &,wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>> *,unsigned __int64)
0x18005f293  mov     rdx, r12; struct std::nothrow_t *
0x18005f296  mov     rcx, rbx; void *
0x18005f299  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f29e  jmp     loc_18005F771
0x18005f2a3  mov     rcx, [rbp+5Fh]; this
0x18005f2a7  mov     r9d, 8007000Eh; char *
0x18005f2ad  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005f2b4  mov     edx, 0DAAh; void *
0x18005f2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f2be  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005f2c5  jmp     loc_18005F5F4
0x18005f2ca  mov     rcx, [rbp+5Fh]; this
0x18005f2ce  mov     r9d, esi; char *
0x18005f2d1  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005f2d8  mov     edx, 0A7Eh; void *
0x18005f2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f2e2  mov     rcx, [rbp+5Fh]; this
0x18005f2e6  mov     r9d, esi; char *
0x18005f2e9  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005f2f0  mov     edx, 0D9Dh; void *
0x18005f2f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f2fa  jmp     loc_18005F269
0x18005f2ff  mov     rbx, [r14]
0x18005f302  mov     rdi, [r14+8]
0x18005f306  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005f30d  cmp     rbx, rdi
0x18005f310  jz      loc_18005F705
0x18005f316  mov     rcx, [rbx]
0x18005f319  mov     [rbp+57h+hKey], rcx
0x18005f31d  mov     r13, [r13+0]
0x18005f321  lea     rax, [rbp+57h+var_B0]
0x18005f325  mov     [rbp+57h+lpSubKey], rax
0x18005f329  lea     rax, [rbp+57h+var_B0]
0x18005f32d  mov     [rbp+57h+var_B8], rax
0x18005f331  xor     eax, eax
0x18005f333  mov     [rbp+57h+var_B0], ax
0x18005f337  lea     rdx, [rbp+57h+lpSubKey]
0x18005f33b  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18005f340  mov     esi, eax
0x18005f342  test    eax, eax
0x18005f344  js      loc_18005F6D1
0x18005f34a  mov     rsi, [rbp+57h+lpSubKey]
0x18005f34e  mov     [rsp+120h+pExtendedParameter], 0; pExtendedParameter
0x18005f357  mov     [rsp+120h+hTransaction], r13; hTransaction
0x18005f35c  xor     r9d, r9d; Reserved
0x18005f35f  xor     r8d, r8d; samDesired
0x18005f362  mov     rdx, rsi; lpSubKey
0x18005f365  mov     rcx, [rbp+57h+hKey]
0x18005f369  mov     rcx, [rcx+28h]; hKey
0x18005f36d  call    cs:__imp_RegDeleteKeyTransactedW
0x18005f374  nop     dword ptr [rax+rax+00h]
0x18005f379  cmp     eax, 2
0x18005f37c  jz      loc_18005F6C2
0x18005f382  test    eax, eax
0x18005f384  jz      short loc_18005F3B9
0x18005f386  mov     rcx, [rbp+5Fh]; this
0x18005f38a  mov     [rsp+120h+pExtendedParameter], rsi; char *
0x18005f38f  lea     rdx, aFailedToDelete_1; "Failed to delete subkey transacted with"...
0x18005f396  mov     [rsp+120h+hTransaction], rdx; int
0x18005f39b  mov     r9d, eax; char *
0x18005f39e  lea     r8, aOnecoreBaseGen_77; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18005f3a5  mov     edx, 12Bh; void *
0x18005f3aa  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18005f3af  mov     esi, eax
0x18005f3b1  test    eax, eax
0x18005f3b3  js      loc_18005F6C7
0x18005f3b9  lea     rax, [rbp+57h+var_B0]
0x18005f3bd  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18005f3c1  cmp     rcx, rax
0x18005f3c4  jz      short loc_18005F3CE
0x18005f3c6  mov     rdx, r12; struct std::nothrow_t *
0x18005f3c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f3ce  mov     r13, [rbx]
0x18005f3d1  mov     [rbp+57h+var_C8], 0
0x18005f3d9  mov     rcx, [rbp+57h+arg_0]
0x18005f3dd  mov     rcx, [rcx+48h]
0x18005f3e1  add     rcx, 8
0x18005f3e5  lea     r8, [rbp+57h+var_C8]
0x18005f3e9  call    ?Duplicate@RegistryKey@Csl@@QEBAJW4RegistryKeyAccess@2@AEAV12@@Z; Csl::RegistryKey::Duplicate(Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x18005f3ee  mov     esi, eax
0x18005f3f0  test    eax, eax
0x18005f3f2  js      loc_18005F678
0x18005f3f8  add     r13, 28h ; '('
0x18005f3fc  lea     rax, [rbp+57h+var_C8]
0x18005f400  cmp     r13, rax
0x18005f403  jz      short loc_18005F44A
0x18005f405  mov     rax, [r13+0]
0x18005f409  mov     [rbp+57h+hKey], rax
0x18005f40d  test    rax, rax
0x18005f410  jz      short loc_18005F43E
0x18005f412  call    cs:__imp_GetLastError
0x18005f419  nop     dword ptr [rax+rax+00h]
0x18005f41e  mov     esi, eax
0x18005f420  mov     rcx, [rbp+57h+hKey]; hKey
0x18005f424  call    cs:__imp_RegCloseKey
0x18005f42b  nop     dword ptr [rax+rax+00h]
0x18005f430  mov     ecx, esi; dwErrCode
0x18005f432  call    cs:__imp_SetLastError
0x18005f439  nop     dword ptr [rax+rax+00h]
0x18005f43e  mov     rax, [rbp+57h+var_C8]
0x18005f442  mov     [r13+0], rax
0x18005f446  xor     ecx, ecx
0x18005f448  jmp     short loc_18005F44E
0x18005f44a  mov     rcx, [rbp+57h+var_C8]; hKey
0x18005f44e  test    rcx, rcx
0x18005f451  jz      short loc_18005F45F
0x18005f453  call    cs:__imp_RegCloseKey
0x18005f45a  nop     dword ptr [rax+rax+00h]
0x18005f45f  lea     rcx, [rbp+57h+arg_8]
0x18005f463  call    ??$make_unique_nothrow@VResource@Details@Core@Manager@Container@@$$V@wil@@YA?AV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Container::Manager::Core::Details::Resource,>(void)
0x18005f468  mov     rsi, [rbp+57h+arg_8]
0x18005f46c  test    rsi, rsi
0x18005f46f  jz      loc_18005F5D9
0x18005f475  mov     rax, [rbx]
0x18005f478  mov     qword ptr [rbx], 0
0x18005f47f  mov     [rbp+57h+hKey], rax
0x18005f483  mov     r10, [rbp+57h+arg_0]
0x18005f487  lea     rax, [r10+148h]
0x18005f48e  lea     rcx, [r10+138h]
0x18005f495  lea     rdx, [r10+128h]
0x18005f49c  lea     r8, [r10+118h]
0x18005f4a3  lea     r9, [r10+108h]
0x18005f4aa  mov     [rsp+120h+var_E8], rax
0x18005f4af  mov     [rsp+120h+var_F0], rcx
0x18005f4b4  mov     [rsp+120h+pExtendedParameter], rdx
0x18005f4b9  mov     [rsp+120h+hTransaction], r8; int
0x18005f4be  mov     r8, r10
0x18005f4c1  lea     rdx, [rbp+57h+hKey]
0x18005f4c5  mov     rcx, rsi
0x18005f4c8  call    ?Initialize@Resource@Details@Core@Manager@Container@@AEAAJV?$unique_ptr@VContainerStorage@Details@Core@Manager@Container@@U?$default_delete@VContainerStorage@Details@Core@Manager@Container@@@wistd@@@wistd@@PEAVResourceBroker@2345@AEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VConfigurationBuilder@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VLogManager@Details@Core@Manager@Container@@@utl@@@Z; Container::Manager::Core::Details::Resource::Initialize(wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>,Container::Manager::Core::Details::ResourceBroker *,utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &,utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> const &,utl::shared_ptr<Container::Manager::Core::Details::ConfigurationBuilder> const &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &,utl::shared_ptr<Container::Manager::Core::Details::LogManager> const &)
0x18005f4cd  mov     r13d, eax
0x18005f4d0  test    eax, eax
0x18005f4d2  js      short loc_18005F525
0x18005f4d4  mov     rsi, [rbp+5Fh]
0x18005f4d8  lea     rdx, [rbp+57h+arg_8]
0x18005f4dc  lea     rcx, [rsp+120h+var_E0]
0x18005f4e1  call    ??$emplace_back@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@$0A@@?$vector@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@QEAA_N$$QEAV?$unique_ptr@VResource@Details@Core@Manager@Container@@U?$default_delete@VResource@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z; utl::vector<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>>>::emplace_back<wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>>,0>(wistd::unique_ptr<Container::Manager::Core::Details::Resource,wistd::default_delete<Container::Manager::Core::Details::Resource>> &&)
0x18005f4e6  test    al, al
  ... truncated ...
```
