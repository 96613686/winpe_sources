# WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::RuntimeClassInitialize(DataStoreCache::IDataManager *,HSTRING__ *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *)

- ea: `0x180022f2c`
- end: `0x180023ad3`
- name: `?RuntimeClassInitialize@AppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUIDataManager@DataStoreCache@@PEAUHSTRING__@@PEAUIUnifiedTileManager@234@@Z`
- size: `2983`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *__hidden this, struct IDataManager *, HSTRING, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *)`
- caller_count: `1`
- callee_count: `35`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180099c84`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180021b78`
- `0x18002266c`
- `0x180022f2c`
- `0x1800240ac`
- `0x1800250dc`
- `0x18002519c`
- `0x18002e184`
- `0x18002e760`
- `0x18002e8c4`
- `0x18003763c`
- `0x180037d34`
- `0x180037f6c`
- `0x1800385d0`
- `0x18003ab30`
- `0x180042cf0`
- `0x180042d20`
- `0x1800436b0`
- `0x180045678`
- `0x180046874`
- `0x180049338`
- `0x180075c30`
- `0x1800a40d4`
- `0x1800d912c`
- `0x1800dd938`
- `0x1800dda54`
- `0x180105f10`
- `0x180115d74`
- `0x180115db0`
- `0x180128dec`
- `0x18012c2fc`
- `0x180161204`
- `0x1802f4ff8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800230d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800230d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002373b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800237a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002383f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800238cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002399d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002373b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800237a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002383f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800238cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002399d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002317c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800235a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002317c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800235a8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180022fba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180022fba`

## string_xrefs

- `0x180022f8d`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x18002310b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x180023878`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x180023a33`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x180023a56`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x180023a79`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x1800234a8`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`
- `0x180023aa7`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::RuntimeClassInitialize(
        WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *this,
        struct IDataManager *a2,
        HSTRING a3,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *a4)
{
  struct DataStoreCache::IDataItem *v4; // r13
  HSTRING v6; // r15
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  HRESULT Guid; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  RTL_SRWLOCK *v21; // rbx
  __int64 **v22; // r14
  __int64 **v23; // rsi
  __int64 *v24; // rdi
  WindowsInternal::Shell::UnifiedTile **v25; // rax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **v26; // r8
  int Instance; // edi
  int v28; // eax
  __int64 v29; // rcx
  int v30; // edi
  __int64 v31; // r13
  HSTRING *v32; // rax
  HSTRING v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall *v36)(__int64, HSTRING__ *); // rdi
  int v37; // eax
  __int64 v38; // r15
  __int64 (__fastcall *v39)(__int64, __int64 *); // rdi
  int v40; // eax
  __int64 v41; // rcx
  int v42; // eax
  unsigned int v43; // edi
  __int64 v44; // rdi
  int v45; // eax
  unsigned int v46; // esi
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdi
  int v52; // eax
  int v53; // edi
  int CollectionTileFromDataItem; // eax
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile *v55; // rdi
  const struct DataStoreCache::DataItemIdentifier *v56; // rax
  __int64 v57; // rcx
  int v58; // edi
  int v59; // eax
  const char *v60; // r9
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // [rsp+20h] [rbp-168h]
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile **v65; // [rsp+20h] [rbp-168h]
  HSTRING__ v66[2]; // [rsp+30h] [rbp-158h] BYREF
  __int64 v67; // [rsp+38h] [rbp-150h] BYREF
  __int64 v68; // [rsp+40h] [rbp-148h] BYREF
  unsigned int v69; // [rsp+48h] [rbp-140h]
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile *v70; // [rsp+50h] [rbp-138h] BYREF
  HSTRING v71; // [rsp+58h] [rbp-130h] BYREF
  __int64 v72; // [rsp+60h] [rbp-128h] BYREF
  HSTRING v73; // [rsp+68h] [rbp-120h] BYREF
  __int64 v74; // [rsp+70h] [rbp-118h] BYREF
  WindowsInternal::Shell::UnifiedTile::SimpleContainer *v75; // [rsp+78h] [rbp-110h] BYREF
  HSTRING string; // [rsp+80h] [rbp-108h] BYREF
  __int64 v77; // [rsp+88h] [rbp-100h] BYREF
  int v78[2]; // [rsp+90h] [rbp-F8h] BYREF
  __int64 v79; // [rsp+98h] [rbp-F0h] BYREF
  _BYTE v80[16]; // [rsp+A0h] [rbp-E8h] BYREF
  char v81[8]; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 **v82; // [rsp+B8h] [rbp-D0h]
  HSTRING v83; // [rsp+F0h] [rbp-98h]
  char v84[24]; // [rsp+F8h] [rbp-90h] BYREF
  char v85[8]; // [rsp+110h] [rbp-78h] BYREF
  __int64 v86; // [rsp+118h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]
  HSTRING v89; // [rsp+1A0h] [rbp+18h] BYREF
  struct DataStoreCache::IDataItem *v90; // [rsp+1A8h] [rbp+20h] BYREF

  v90 = a4;
  v89 = a3;
  v4 = a4;
  v6 = (HSTRING)this;
  v69 = 0;
  v71 = (HSTRING)((char *)this + 80);
  v7 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v71);
  v8 = Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(v4, v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
      (const char *)(unsigned int)v8,
      v64);
    return v9;
  }
  Guid = CoCreateGuid((GUID *)v6 + 15);
  try
  {
    v12 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
        (const char *)(unsigned int)Guid,
        v64);
      result = v12;
    }
    else
    {
      v13 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v6 + 32, &v89);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
          (const char *)(unsigned int)v13,
          v64);
        result = v14;
      }
      else
      {
        v15 = ((__int64 (__fastcall *)(struct IDataManager *, struct WindowsInternal::Shell::UnifiedTile::CollectionTile **, __int128 *))a2->lpVtbl->GetTypeInfoCount)(
                a2,
                &v70,
                &TileData);
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>::operator=(
          v6 + 22,
          v15);
        v16 = v70;
        if ( v70 )
        {
          v70 = 0;
          (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::CollectionTile *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v71 = 0;
        v74 = 0;
        v73 = v6;
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(v6 + 26);
        v17 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::SimpleContainer,WindowsInternal::Shell::UnifiedTile::SimpleContainer,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &,std::nullptr_t,std::nullptr_t>(
                (int)v6 + 104,
                (unsigned int)&v73,
                (unsigned int)&v90,
                (unsigned int)&v74,
                (__int64)&v71);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x133,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
            (const char *)(unsigned int)v17,
            (int)v65);
          result = v18;
        }
        else
        {
          Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(v6 + 24, a2);
          v68 = 0;
          v71 = v6;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          v19 = Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *>(
                  &v68,
                  &v71);
          v20 = v19;
          if ( v19 >= 0 )
          {
            *(_DWORD *)(v6 + 68) = *(_DWORD *)(HSTRING)(*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)v6 + 12) + 40LL))(
                                                         *((_QWORD *)v6 + 12),
                                                         &v67,
                                                         v68);
            v21 = (RTL_SRWLOCK *)(v6 + 66);
            AcquireSRWLockExclusive((PSRWLOCK)v6 + 33);
            v83 = v6 + 66;
            (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v6 + 11) + 32LL))(*((_QWORD *)v6 + 11), v81);
            v22 = v82;
            v23 = (__int64 **)*v82;
            while ( 1 )
            {
              if ( v23 == v22 )
              {
                v44 = *((_QWORD *)v6 + 15);
LABEL_43:
                v44 = *(_QWORD *)v44;
                while ( v44 != *((_QWORD *)v6 + 15) )
                {
                  if ( WindowsInternal::Shell::UnifiedTile::SimpleContainer::Size(*(WindowsInternal::Shell::UnifiedTile::SimpleContainer **)(v44 + 24)) != 1 )
                    goto LABEL_43;
                  WindowsInternal::Shell::UnifiedTile::SimpleContainer::GetCollectionTiles(*(_QWORD *)(v44 + 24), v85);
                  v45 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddCollectionTile(
                          *((WindowsInternal::Shell::UnifiedTile::SimpleContainer **)v6 + 13),
                          (const struct DataStoreCache::DataItemIdentifier *)(*(_QWORD *)v86 + 16LL),
                          *(struct WindowsInternal::Shell::UnifiedTile::CollectionTile **)(*(_QWORD *)v86 + 24LL),
                          0);
                  v46 = v45;
                  if ( v45 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x172,
                      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                      (const char *)(unsigned int)v45,
                      (int)v65);
                    std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>>>,0>>(v85);
                    std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                    if ( v21 )
                      ReleaseSRWLockExclusive(v21);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
                    return v46;
                  }
                  v47 = std::_Hash<std::_Umap_traits<winrt::hstring,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<winrt::hstring,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteEqualTo>,std::allocator<std::pair<winrt::hstring const,DataStoreCache::DataItemIdentifier>>,0>>::_Try_emplace<winrt::hstring const &,>(
                          v6 + 44,
                          v80,
                          v44 + 16);
                  DataStoreCache::DataItemIdentifier::operator=((HSTRING *)(*(_QWORD *)v47 + 24LL));
                  v49 = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher::operator()(
                          v48,
                          v44 + 16);
                  std::_Hash<std::_Umap_traits<winrt::hstring,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>,std::_Uhash_compare<winrt::hstring,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteEqualTo>,std::allocator<std::pair<winrt::hstring const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>>>,0>>::_Erase_bucket(
                    v6 + 28,
                    v44,
                    v49 & *((_QWORD *)v6 + 20));
                  v44 = std::list<std::pair<winrt::hstring const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>>>::_Unchecked_erase(v6 + 30);
                  std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>>>,0>>(v85);
                }
                std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                if ( v21 )
                  ReleaseSRWLockExclusive(v21);
                v61 = v68;
                if ( v68 )
                {
                  v68 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                }
                return 0;
              }
              v24 = v23[3];
              v67 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
              v67 = 0;
              *(_QWORD *)&v66[0].unused = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
              v25 = (WindowsInternal::Shell::UnifiedTile **)(*(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v24 + 32))(
                                                              v24,
                                                              &string);
              Instance = WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(*v25, v66, v26);
              WindowsDeleteString(string);
              string = 0;
              if ( Instance < 0 )
                break;
              v28 = (*(__int64 (__fastcall **)(struct DataStoreCache::IDataItem *, _QWORD, __int64 *))(*(_QWORD *)v4 + 72LL))(
                      v4,
                      *(_QWORD *)&v66[0].unused,
                      &v67);
              if ( v28 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x93,
                  (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
                  (const char *)(unsigned int)v28,
                  (int)v65);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
LABEL_50:
                v30 = v69 | 2;
                v32 = &v73;
                v31 = 0;
                v72 = 0;
                goto LABEL_22;
              }
              v29 = *(_QWORD *)&v66[0].unused;
              if ( *(_QWORD *)&v66[0].unused )
              {
                *(_QWORD *)&v66[0].unused = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              }
              if ( !v67
                || !(unsigned __int8)WindowsInternal::Shell::UnifiedTile::_anonymous_namespace_::IsAppListEligible(v67) )
              {
                goto LABEL_50;
              }
              v30 = v69 | 1;
              v31 = v67;
              if ( v67 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 8LL))(v67);
              v32 = (HSTRING *)&v74;
              v72 = 0;
LABEL_22:
              v72 = v31;
              *v32 = 0;
              if ( (v30 & 2) != 0 )
              {
                v30 &= ~2u;
                v69 = v30;
                v33 = v73;
                if ( v73 )
                {
                  v73 = 0;
                  (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v33 + 16LL))(v33);
                }
              }
              else
              {
                v69 = v30;
              }
              if ( (v30 & 1) != 0 )
              {
                v69 = v30 & 0xFFFFFFFE;
                v34 = v74;
                if ( v74 )
                {
                  v74 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
              }
              v35 = v67;
              if ( v67 )
              {
                v67 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              }
              if ( v31 )
              {
                v67 = 0;
                *(_QWORD *)&v66[0].unused = 0;
                v36 = *(__int64 (__fastcall **)(__int64, HSTRING__ *))(*(_QWORD *)v31 + 56LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
                v37 = v36(v31, v66);
                if ( v37 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x111,
                    (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                    (const char *)(unsigned int)v37,
                    (int)v65);
                }
                else
                {
                  v38 = *(_QWORD *)&v66[0].unused;
                  v39 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)&v66[0].unused + 96LL);
                  winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                  v40 = v39(v38, &v67);
                  if ( v40 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x113,
                      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                      (const char *)(unsigned int)v40,
                      (int)v65);
                  v6 = (HSTRING)this;
                }
                v41 = *(_QWORD *)&v66[0].unused;
                if ( *(_QWORD *)&v66[0].unused )
                {
                  *(_QWORD *)&v66[0].unused = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                }
                if ( v67 )
                {
                  std::_Hash<std::_Umap_traits<winrt::hstring,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>,std::_Uhash_compare<winrt::hstring,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteEqualTo>,std::allocator<std::pair<winrt::hstring const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>>>,0>>::find(
                    v6 + 28,
                    &v77,
                    &v67);
                  if ( v77 == *((_QWORD *)v6 + 15) )
                  {
                    *(_QWORD *)&v66[0].unused = 0;
                    *(_QWORD *)v78 = *(_QWORD *)WindowsInternal::Shell::UnifiedTile::_anonymous_namespace_::GetSuiteSortName(
                                                  v80,
                                                  v31);
                    v79 = v67;
                    v75 = (WindowsInternal::Shell::UnifiedTile::SimpleContainer *)v6;
                    Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(v66);
                    v58 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::SimpleContainer,WindowsInternal::Shell::UnifiedTile::SimpleContainer,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager * &,HSTRING__ *,HSTRING__ *>(
                            (unsigned int)v66,
                            (unsigned int)&v75,
                            (unsigned int)&v90,
                            (unsigned int)&v79,
                            (__int64)v78);
                    winrt::handle_type<winrt::impl::hstring_traits>::close(v80);
                    if ( v58 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x156,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                        (const char *)(unsigned int)v58,
                        (int)v65);
                      if ( *(_QWORD *)&v66[0].unused )
                      {
                        *(_QWORD *)&v66[0].unused = 0;
                        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release();
                      }
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                      if ( v21 )
                        ReleaseSRWLockExclusive(v21);
                      v63 = v68;
                      if ( v68 )
                      {
                        v68 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                      }
                      return (unsigned int)v58;
                    }
                    v59 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddDataItem(
                            *(WindowsInternal::Shell::UnifiedTile::SimpleContainer **)&v66[0].unused,
                            (struct DataStoreCache::IDataItem *)v23[3],
                            0);
                    v53 = v59;
                    if ( v59 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x157,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                        (const char *)(unsigned int)v59,
                        (int)v65);
                      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(v66);
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
                      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                      if ( v21 )
                        ReleaseSRWLockExclusive(v21);
LABEL_94:
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
                      return (unsigned int)v53;
                    }
                    std::_Hash<std::_Umap_traits<winrt::hstring,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>,std::_Uhash_compare<winrt::hstring,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteEqualTo>,std::allocator<std::pair<winrt::hstring const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>>>,0>>::emplace<winrt::hstring,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer> &>(
                      v6 + 28,
                      v84,
                      &v67,
                      v66);
                    if ( *(_QWORD *)&v66[0].unused )
                    {
                      *(_QWORD *)&v66[0].unused = 0;
                      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release();
                    }
                  }
                  else
                  {
                    v42 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddDataItem(
                            *(WindowsInternal::Shell::UnifiedTile::SimpleContainer **)(v77 + 24),
                            (struct DataStoreCache::IDataItem *)v23[3],
                            0);
                    v43 = v42;
                    if ( v42 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x14F,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                        (const char *)(unsigned int)v42,
                        (int)v65);
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                      if ( v21 )
                        ReleaseSRWLockExclusive(v21);
                      v62 = v68;
                      if ( v68 )
                      {
                        v68 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                      }
                      return v43;
                    }
                  }
                }
                else
                {
                  *(_QWORD *)&v66[0].unused = 0;
                  v51 = *((_QWORD *)v6 + 13);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
                  v52 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>>(
                          v51,
                          &GUID_6fe03efc_a8af_4faf_9c23_bc0cb5bf29d3,
                          v66);
                  v53 = v52;
                  if ( v52 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x15E,
                      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                      (const char *)(unsigned int)v52,
                      (int)v65);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
                    winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
                    std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                    if ( v21 )
                      ReleaseSRWLockExclusive(v21);
                    goto LABEL_94;
                  }
                  v70 = 0;
                  Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v70);
                  CollectionTileFromDataItem = WindowsInternal::Shell::UnifiedTile::GetCollectionTileFromDataItem(
                                                 (WindowsInternal::Shell::UnifiedTile *)v23[3],
                                                 v90,
                                                 *(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager **)&v66[0].unused,
                                                 (struct WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer *)&v70,
                                                 v65);
                  if ( CollectionTileFromDataItem < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x161,
                      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                      (const char *)(unsigned int)CollectionTileFromDataItem,
                      (int)v65);
                  v55 = v70;
                  if ( v70 )
                  {
                    v75 = (WindowsInternal::Shell::UnifiedTile::SimpleContainer *)*((_QWORD *)v6 + 13);
                    v56 = (const struct DataStoreCache::DataItemIdentifier *)(*(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v23[3] + 32))(
                                                                               v23[3],
                                                                               &v71);
                    v53 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddCollectionTile(v75, v56, v55, 0);
                    WindowsDeleteString(v71);
                    v71 = 0;
                    if ( v53 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x164,
                        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                        (const char *)(unsigned int)v53,
                        (int)v65);
                      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v70);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v66);
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
                      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v81);
                      if ( v21 )
                        ReleaseSRWLockExclusive(v21);
                      goto LABEL_94;
                    }
                  }
                  Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v70);
                  v57 = *(_QWORD *)&v66[0].unused;
                  if ( *(_QWORD *)&v66[0].unused )
                  {
                    *(_QWORD *)&v66[0].unused = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                  }
                }
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              }
              v23 = (__int64 **)*v23;
              v4 = v90;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x92,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
              (const char *)(unsigned int)Instance,
              (int)v65);
            v50 = *(_QWORD *)&v66[0].unused;
            if ( *(_QWORD *)&v66[0].unused )
            {
              *(_QWORD *)&v66[0].unused = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
            }
            goto LABEL_50;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13A,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
            (const char *)(unsigned int)v19,
            (int)v65);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          result = v20;
        }
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v90) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x17E,
                     (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                     v60);
    return (unsigned int)v90;
  }
  return result;
}

```

## disassembly

```asm
0x180022f2c  mov     [rsp+arg_18], r9
0x180022f31  mov     [rsp+arg_10], r8
0x180022f36  mov     [rsp+arg_0], rcx
0x180022f3b  push    rbx
0x180022f3c  push    rsi
0x180022f3d  push    rdi
0x180022f3e  push    r12
0x180022f40  push    r13
0x180022f42  push    r14
0x180022f44  push    r15
0x180022f46  sub     rsp, 150h
0x180022f4d  mov     r13, r9
0x180022f50  mov     rsi, rdx
0x180022f53  mov     r15, rcx
0x180022f56  xor     r12d, r12d
0x180022f59  mov     [rsp+188h+var_140], r12d
0x180022f5e  lea     rax, [rcx+50h]
0x180022f62  mov     [rsp+188h+var_130], rax
0x180022f67  lea     rcx, [rsp+188h+var_130]
0x180022f6c  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180022f71  mov     rdx, rax
0x180022f74  mov     rcx, r13
0x180022f77  call    ??$AsWeak@UIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@YAJPEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,Microsoft::WRL::WeakRef *)
0x180022f7c  mov     ebx, eax
0x180022f7e  test    eax, eax
0x180022f80  jns     short loc_180022FB3
0x180022f82  mov     rcx, [rsp+188h]; this
0x180022f8a  mov     r9d, eax; char *
0x180022f8d  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180022f94  mov     edx, 12Ch; void *
0x180022f99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f9e  mov     eax, ebx
0x180022fa0  add     rsp, 150h
0x180022fa7  pop     r15
0x180022fa9  pop     r14
0x180022fab  pop     r13
0x180022fad  pop     r12
0x180022faf  pop     rdi
0x180022fb0  pop     rsi
0x180022fb1  pop     rbx
0x180022fb2  retn
0x180022fb3  lea     rcx, [r15+0F0h]; pguid
0x180022fba  call    cs:__imp_CoCreateGuid
0x180022fc0  mov     ebx, eax
0x180022fc2  test    eax, eax
0x180022fc4  js      loc_180023A28
0x180022fca  lea     rcx, [r15+100h]; newString
0x180022fd1  lea     rdx, [rsp+188h+arg_10]; HSTRING *
0x180022fd9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180022fde  mov     ebx, eax
0x180022fe0  test    eax, eax
0x180022fe2  js      loc_180023A4B
0x180022fe8  mov     rax, [rsi]
0x180022feb  lea     r8, TileData
0x180022ff2  lea     rdx, [rsp+188h+var_138]
0x180022ff7  mov     rcx, rsi
0x180022ffa  mov     rax, [rax+18h]
0x180022ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023003  mov     rdx, rax
0x180023006  lea     rcx, [r15+58h]
0x18002300a  call    ??4?$ComPtr@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>::operator=(Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv> &&)
0x18002300f  nop
0x180023010  mov     rcx, [rsp+188h+var_138]
0x180023015  test    rcx, rcx
0x180023018  jz      short loc_18002302C
0x18002301a  mov     [rsp+188h+var_138], r12
0x18002301f  mov     rax, [rcx]
0x180023022  mov     rax, [rax+10h]
0x180023026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002302b  nop
0x18002302c  mov     [rsp+188h+var_130], r12
0x180023031  mov     [rsp+188h+var_118], r12
0x180023036  mov     [rsp+188h+var_120], r15
0x18002303b  lea     rcx, [r15+68h]
0x18002303f  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x180023044  lea     rax, [rsp+188h+var_130]
0x180023049  mov     [rsp+188h+var_168], rax; int
0x18002304e  lea     r9, [rsp+188h+var_118]
0x180023053  lea     r8, [rsp+188h+arg_18]
0x18002305b  lea     rdx, [rsp+188h+var_120]
0x180023060  lea     rcx, [r15+68h]
0x180023064  call    ??$MakeAndInitialize@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@V1234@PEAVAppsListGeneratedCollection@234@AEAPEAUIUnifiedTileManager@234@$$T$$T@Details@WRL@Microsoft@@YAJPEAPEAVSimpleContainer@UnifiedTile@Shell@WindowsInternal@@$$QEAPEAVAppsListGeneratedCollection@456@AEAPEAUIUnifiedTileManager@456@$$QEA$$T3@Z
0x180023069  mov     ebx, eax
0x18002306b  test    eax, eax
0x18002306d  js      loc_18002386D
0x180023073  mov     rdx, rsi
0x180023076  lea     rcx, [r15+60h]
0x18002307a  call    ??4?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDataItem@DataStoreCache@@@Z; Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(DataStoreCache::IDataItem *)
0x18002307f  mov     [rsp+188h+var_148], r12
0x180023084  mov     [rsp+188h+var_130], r15
0x180023089  lea     rcx, [rsp+188h+var_148]
0x18002308e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023093  lea     rdx, [rsp+188h+var_130]
0x180023098  lea     rcx, [rsp+188h+var_148]
0x18002309d  call    ??$MakeAndInitialize@VDataItemEventHandlerWrapper@DataStoreCache@@UIDataItemEventHandler@@PEAVAppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAPEAUIDataItemEventHandler@@$$QEAPEAVAppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *>(IDataItemEventHandler * *,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection * &&)
0x1800230a2  mov     ebx, eax
0x1800230a4  test    eax, eax
0x1800230a6  js      loc_180023A6E
0x1800230ac  mov     rcx, [r15+60h]
0x1800230b0  mov     rax, [rcx]
0x1800230b3  mov     r8, [rsp+188h+var_148]
0x1800230b8  lea     rdx, [rsp+188h+var_150]
0x1800230bd  mov     rax, [rax+28h]
0x1800230c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c6  mov     eax, [rax]
0x1800230c8  mov     [r15+110h], eax
0x1800230cf  lea     rbx, [r15+108h]
0x1800230d6  mov     rcx, rbx; SRWLock
0x1800230d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800230df  mov     [rsp+188h+var_98], rbx
0x1800230e7  mov     rcx, [r15+58h]
0x1800230eb  mov     rax, [rcx]
0x1800230ee  lea     rdx, [rsp+188h+var_D8]
0x1800230f6  mov     rax, [rax+20h]
0x1800230fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230ff  nop
0x180023100  mov     r14, [rsp+188h+var_D0]
0x180023108  mov     rsi, [r14]
0x18002310b  lea     r12, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180023112  cmp     rsi, r14
0x180023115  jz      loc_1800233DC
0x18002311b  mov     rdi, [rsi+18h]
0x18002311f  mov     [rsp+188h+var_150], 0
0x180023128  lea     rcx, [rsp+188h+var_150]
0x18002312d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023132  mov     [rsp+188h+var_150], 0
0x18002313b  mov     qword ptr [rsp+188h+var_158.unused], 0
0x180023144  lea     rcx, [rsp+188h+var_158]
0x180023149  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002314e  mov     rax, [rdi]
0x180023151  lea     rdx, [rsp+188h+string]
0x180023159  mov     rcx, rdi
0x18002315c  mov     rax, [rax+20h]
0x180023160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023165  lea     rdx, [rsp+188h+var_158]; HSTRING
0x18002316a  mov     rcx, [rax]; this
0x18002316d  call    ?UnifiedTileIdentifier_CreateInstance@UnifiedTile@Shell@WindowsInternal@@YAJPEAUHSTRING__@@PEAPEAUIUnifiedTileIdentifier@123@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(HSTRING__ *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)
0x180023172  mov     edi, eax
0x180023174  mov     rcx, [rsp+188h+string]; string
0x18002317c  call    cs:__imp_WindowsDeleteString
0x180023182  mov     [rsp+188h+string], 0
0x18002318e  test    edi, edi
0x180023190  js      loc_18002349D
0x180023196  mov     rax, [r13+0]
0x18002319a  lea     r8, [rsp+188h+var_150]
0x18002319f  mov     rdx, qword ptr [rsp+188h+var_158.unused]
0x1800231a4  mov     rcx, r13
0x1800231a7  mov     rax, [rax+48h]
0x1800231ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231b0  test    eax, eax
0x1800231b2  js      loc_180023A9C
0x1800231b8  mov     rcx, qword ptr [rsp+188h+var_158.unused]
0x1800231bd  test    rcx, rcx
0x1800231c0  jz      short loc_1800231D8
0x1800231c2  mov     qword ptr [rsp+188h+var_158.unused], 0
0x1800231cb  mov     rax, [rcx]
0x1800231ce  mov     rax, [rax+10h]
0x1800231d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d7  nop
0x1800231d8  mov     r13, [rsp+188h+var_150]
0x1800231dd  test    r13, r13
0x1800231e0  jz      loc_1800234DA
0x1800231e6  mov     rcx, r13
0x1800231e9  call    WindowsInternal__Shell__UnifiedTile___anonymous_namespace___IsAppListEligible
0x1800231ee  test    al, al
0x1800231f0  jz      loc_1800234DA
0x1800231f6  mov     edi, [rsp+188h+var_140]
0x1800231fa  or      edi, 1
0x1800231fd  mov     r13, [rsp+188h+var_150]
0x180023202  test    r13, r13
0x180023205  jz      short loc_180023218
0x180023207  mov     rax, [r13+0]
0x18002320b  mov     rcx, r13
0x18002320e  mov     rax, [rax+8]
0x180023212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023217  nop
0x180023218  lea     rax, [rsp+188h+var_118]
0x18002321d  mov     [rsp+188h+var_128], 0
0x180023226  mov     [rsp+188h+var_128], r13
0x18002322b  mov     qword ptr [rax], 0
0x180023232  test    dil, 2
0x180023236  jz      loc_1800236CB
0x18002323c  and     edi, 0FFFFFFFDh
0x18002323f  mov     [rsp+188h+var_140], edi
0x180023243  mov     rcx, [rsp+188h+var_120]
0x180023248  test    rcx, rcx
0x18002324b  jz      short loc_180023263
0x18002324d  mov     [rsp+188h+var_120], 0
0x180023256  mov     rax, [rcx]
0x180023259  mov     rax, [rax+10h]
0x18002325d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023262  nop
0x180023263  test    dil, 1
0x180023267  jz      short loc_180023290
0x180023269  and     edi, 0FFFFFFFEh
0x18002326c  mov     [rsp+188h+var_140], edi
0x180023270  mov     rcx, [rsp+188h+var_118]
0x180023275  test    rcx, rcx
0x180023278  jz      short loc_180023290
0x18002327a  mov     [rsp+188h+var_118], 0
0x180023283  mov     rax, [rcx]
0x180023286  mov     rax, [rax+10h]
0x18002328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002328f  nop
0x180023290  mov     rcx, [rsp+188h+var_150]
0x180023295  test    rcx, rcx
0x180023298  jz      short loc_1800232B0
0x18002329a  mov     [rsp+188h+var_150], 0
0x1800232a3  mov     rax, [rcx]
0x1800232a6  mov     rax, [rax+10h]
0x1800232aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232af  nop
0x1800232b0  test    r13, r13
0x1800232b3  jz      loc_1800233CC
0x1800232b9  mov     [rsp+188h+var_150], 0
0x1800232c2  mov     qword ptr [rsp+188h+var_158.unused], 0
0x1800232cb  mov     rax, [r13+0]
0x1800232cf  mov     rdi, [rax+38h]
0x1800232d3  lea     rcx, [rsp+188h+var_158]
0x1800232d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800232dd  lea     rdx, [rsp+188h+var_158]
0x1800232e2  mov     rcx, r13
0x1800232e5  mov     rax, rdi
0x1800232e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232ed  mov     rcx, [rsp+188h]; this
0x1800232f5  test    eax, eax
0x1800232f7  js      loc_1800236D4
0x1800232fd  mov     r15, qword ptr [rsp+188h+var_158.unused]
0x180023302  mov     rax, [r15]
0x180023305  mov     rdi, [rax+60h]
0x180023309  lea     rcx, [rsp+188h+var_150]
0x18002330e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180023313  lea     rdx, [rsp+188h+var_150]
0x180023318  mov     rcx, r15
0x18002331b  mov     rax, rdi
0x18002331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023323  mov     rcx, [rsp+188h]; this
0x18002332b  test    eax, eax
0x18002332d  js      loc_1800236E9
0x180023333  mov     r15, [rsp+188h+arg_0]
0x18002333b  mov     rcx, qword ptr [rsp+188h+var_158.unused]
0x180023340  test    rcx, rcx
0x180023343  jz      short loc_18002335B
0x180023345  mov     qword ptr [rsp+188h+var_158.unused], 0
0x18002334e  mov     rax, [rcx]
0x180023351  mov     rax, [rax+10h]
0x180023355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002335a  nop
0x18002335b  cmp     [rsp+188h+var_150], 0
0x180023361  jz      loc_1800234F3
0x180023367  lea     rcx, [r15+70h]
0x18002336b  lea     r8, [rsp+188h+var_150]
0x180023370  lea     rdx, [rsp+188h+var_100]
0x180023378  call    ?find@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@V?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@Uhstring@winrt@@USuiteHasher@AppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@USuiteEqualTo@4567@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@V?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@V?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBUhstring@winrt@@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>,std::_Uhash_compare<winrt::hstring,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteHasher,WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::SuiteEqualTo>,std::allocator<std::pair<winrt::hstring const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>>>,0>>::find(winrt::hstring const &)
0x18002337d  mov     rcx, [rsp+188h+var_100]
0x180023385  cmp     rcx, [r15+78h]
0x180023389  jz      loc_1800235EF
0x18002338f  xor     r8d, r8d; bool
0x180023392  mov     rdx, [rsi+18h]; struct DataStoreCache::IDataItem *
0x180023396  mov     rcx, [rcx+18h]; this
0x18002339a  call    ?AddDataItem@SimpleContainer@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUIDataItem@DataStoreCache@@_N@Z; WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddDataItem(DataStoreCache::IDataItem *,bool)
0x18002339f  mov     edi, eax
0x1800233a1  test    eax, eax
0x1800233a3  js      loc_180023758
0x1800233a9  lea     rcx, [rsp+188h+var_150]
0x1800233ae  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800233b3  nop
0x1800233b4  test    r13, r13
0x1800233b7  jz      short loc_1800233CA
0x1800233b9  mov     rax, [r13+0]
0x1800233bd  mov     rcx, r13
0x1800233c0  mov     rax, [rax+10h]
0x1800233c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233c9  nop
0x1800233ca  jmp     short $+2
0x1800233cc  mov     rsi, [rsi]
0x1800233cf  mov     r13, [rsp+188h+arg_18]
0x1800233d7  jmp     loc_180023112
0x1800233dc  mov     rdi, [r15+78h]
0x1800233e0  mov     rdi, [rdi]
0x1800233e3  cmp     rdi, [r15+78h]
0x1800233e7  jz      loc_1800236FE
0x1800233ed  mov     rcx, [rdi+18h]; this
0x1800233f1  call    ?Size@SimpleContainer@UnifiedTile@Shell@WindowsInternal@@QEBAIXZ; WindowsInternal::Shell::UnifiedTile::SimpleContainer::Size(void)
0x1800233f6  cmp     eax, 1
0x1800233f9  jnz     short loc_1800233E0
0x1800233fb  lea     rdx, [rsp+188h+var_78]
0x180023403  mov     rcx, [rdi+18h]
0x180023407  call    ?GetCollectionTiles@SimpleContainer@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$unordered_map@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@7@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@@std@@XZ; WindowsInternal::Shell::UnifiedTile::SimpleContainer::GetCollectionTiles(void)
0x18002340c  nop
0x18002340d  mov     rax, [rsp+188h+var_70]
0x180023415  mov     r8, [rax]
0x180023418  lea     r13, [r8+10h]
0x18002341c  xor     r9d, r9d; bool
0x18002341f  mov     r8, [r8+18h]; struct WindowsInternal::Shell::UnifiedTile::CollectionTile *
0x180023423  mov     rdx, r13; struct DataStoreCache::DataItemIdentifier *
0x180023426  mov     rcx, [r15+68h]; this
0x18002342a  call    ?AddCollectionTile@SimpleContainer@UnifiedTile@Shell@WindowsInternal@@QEAAJAEBVDataItemIdentifier@DataStoreCache@@PEAVCollectionTile@234@_N@Z; WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddCollectionTile(DataStoreCache::DataItemIdentifier const &,WindowsInternal::Shell::UnifiedTile::CollectionTile *,bool)
0x18002342f  mov     esi, eax
0x180023431  test    eax, eax
  ... truncated ...
```
