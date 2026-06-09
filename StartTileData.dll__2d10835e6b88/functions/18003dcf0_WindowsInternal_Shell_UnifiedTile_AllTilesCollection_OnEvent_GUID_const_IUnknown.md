# WindowsInternal::Shell::UnifiedTile::AllTilesCollection::OnEvent(_GUID const &,IUnknown *)

- ea: `0x18003dcf0`
- end: `0x18003e6ff`
- name: `?OnEvent@AllTilesCollection@UnifiedTile@Shell@WindowsInternal@@UEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `2575`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::AllTilesCollection *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ce94`
- `0x180015960`
- `0x18001aca4`
- `0x18001f0a0`
- `0x18001f268`
- `0x180020474`
- `0x180022020`
- `0x1800223a4`
- `0x180025f1c`
- `0x18003dcf0`
- `0x18003e708`
- `0x1800436b0`
- `0x180046768`
- `0x180046874`
- `0x180047710`
- `0x1800d3b58`
- `0x18011d03c`
- `0x180138118`
- `0x180161204`
- `0x1801a5ce8`
- `0x1801e5200`
- `0x1802f2550`
- `0x1802f68e0`
- `0x1802f6928`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e06d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e299`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e06d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e299`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e264`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e2ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e264`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e2ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003de97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003de97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003deea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003deea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e3b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5df`

## string_xrefs

- `0x18003df82`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003dfcf`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003e185`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003e3c4`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003e431`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003e4ba`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18003e543`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::AllTilesCollection::OnEvent(
        WindowsInternal::Shell::UnifiedTile::AllTilesCollection *this,
        const struct _GUID *a2,
        struct IUnknown *a3)
{
  __int64 v6; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v8; // r8
  int v9; // eax
  struct DataStoreCache::IDataItemChangeEvent *v10; // rdx
  unsigned int v11; // ebx
  WindowsInternal::Shell::UnifiedTile *v12; // rcx
  const char *v13; // r9
  __int64 result; // rax
  _QWORD *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **v18; // r9
  char v19; // di
  __int64 v20; // rax
  __int64 *v21; // rax
  __int64 v22; // rsi
  __int64 v23; // r12
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v24; // rcx
  struct DataStoreCache::IDataItem *v25; // rcx
  WindowsInternal::Shell::UnifiedTile *v26; // rcx
  WindowsInternal::Shell::UnifiedTile *v27; // rcx
  struct DataStoreCache::IDataItem *v28; // rcx
  WindowsInternal::Shell::UnifiedTile *v29; // rcx
  HSTRING v30; // rdi
  __int64 v31; // rax
  HSTRING *v32; // rax
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  unsigned int v36; // ebx
  HSTRING v37; // rcx
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v38; // rcx
  struct DataStoreCache::IDataItem *v39; // rcx
  WindowsInternal::Shell::UnifiedTile *v40; // rcx
  WindowsInternal::Shell::UnifiedTile *v41; // rcx
  __int64 v42; // rax
  __int64 *v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rdi
  int CollectionTileFromDataItem; // eax
  __int64 v47; // rax
  __int64 v48; // rsi
  HSTRING v49; // rdi
  __int64 v50; // rcx
  WindowsInternal::Shell::UnifiedTile *v51; // rcx
  WindowsInternal::Shell::UnifiedTile *v52; // rcx
  HSTRING *v53; // rax
  int v54; // eax
  int v55; // eax
  HSTRING v56; // rsi
  __int64 v57; // rax
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile **v58; // [rsp+20h] [rbp-D8h]
  int v59; // [rsp+20h] [rbp-D8h]
  int v60; // [rsp+20h] [rbp-D8h]
  int v61; // [rsp+20h] [rbp-D8h]
  HSTRING v62; // [rsp+30h] [rbp-C8h] BYREF
  WindowsInternal::Shell::UnifiedTile *v63; // [rsp+38h] [rbp-C0h] BYREF
  struct DataStoreCache::IDataItem *v64; // [rsp+40h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B0h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v66; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+58h] [rbp-A0h] BYREF
  HSTRING StringRawBuffer; // [rsp+60h] [rbp-98h] BYREF
  HSTRING v69; // [rsp+68h] [rbp-90h] BYREF
  HSTRING v70[2]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v71[32]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v72[24]; // [rsp+A0h] [rbp-58h] BYREF
  int v73; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  WindowsInternal::Shell::UnifiedTile *v75; // [rsp+118h] [rbp+20h] BYREF

  UnifiedTileTelemetry::WatchCurrentThread(v71, "AllTilesCollection_OnEvent");
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data4;
  try
  {
    if ( v6 )
    {
LABEL_8:
      if ( v73 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v72);
      wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v71);
      return 0;
    }
    v63 = 0;
    QueryInterface = a3->lpVtbl->QueryInterface;
    v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v63);
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
           a3,
           &GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e,
           v8);
    v11 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
        (const char *)(unsigned int)v9,
        (int)v58);
      v27 = v63;
      if ( v63 )
      {
LABEL_30:
        v63 = 0;
        (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v27 + 16LL))(v27);
      }
    }
    else
    {
      if ( !WindowsInternal::Shell::UnifiedTile::CouldDataItemChangeAffectAppListVisibility(v63, v10) )
      {
LABEL_6:
        v12 = v63;
        if ( v63 )
        {
          v63 = 0;
          (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        goto LABEL_8;
      }
      (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, WindowsInternal::Shell::UnifiedTile **))(*(_QWORD *)v63 + 40LL))(
        v63,
        &v75);
      v15 = (_QWORD *)(*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v75 + 24LL))(v75);
      v16 = *v15 - TileData;
      if ( *v15 == (_QWORD)TileData )
        v16 = v15[1] - *((_QWORD *)&TileData + 1);
      if ( v16 )
      {
LABEL_27:
        v26 = v75;
        if ( v75 )
        {
          v75 = 0;
          (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v26 + 16LL))(v26);
        }
        goto LABEL_6;
      }
      v64 = 0;
      v17 = Microsoft::WRL::WeakRef::As<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(
              (char *)this + 120,
              &v64);
      v11 = v17;
      if ( v17 >= 0 )
      {
        if ( v64 )
        {
          v66 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
          if ( WindowsInternal::Shell::UnifiedTile::GetUnifiedTileFromDataItem(
                 v75,
                 v64,
                 (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *)&v66,
                 v18) < 0
            || (v19 = 1, !v66) )
          {
            v19 = 0;
          }
          AcquireSRWLockShared((PSRWLOCK)this + 19);
          StringRawBuffer = (HSTRING)((char *)this + 152);
          v20 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                  v75,
                  &string);
          v21 = (__int64 *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::find(
                             (char *)this + 56,
                             v70,
                             v20);
          v22 = *((_QWORD *)this + 8);
          v23 = *v21;
          WindowsDeleteString(string);
          if ( this != (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)-152LL )
            ReleaseSRWLockShared((PSRWLOCK)this + 19);
          if ( v23 != v22 )
          {
            if ( v19
              && WindowsInternal::Shell::UnifiedTile::AllTilesCollection::ShouldIncludeTile(
                   (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)((char *)this - 24),
                   v66) )
            {
              goto LABEL_23;
            }
            v30 = 0;
            string = 0;
            AcquireSRWLockExclusive((PSRWLOCK)this + 19);
            v69 = (HSTRING)((char *)this + 152);
            v31 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                    v75,
                    &StringRawBuffer);
            std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::find(
              (char *)this + 56,
              v70,
              v31);
            WindowsDeleteString(StringRawBuffer);
            if ( v70[0] != *((HSTRING *)this + 8) )
            {
              v56 = (HSTRING)*((_QWORD *)v70[0] + 3);
              if ( v56 )
              {
                v67 = *((_QWORD *)v70[0] + 3);
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v67);
                v67 = 0;
                v30 = v56;
                string = v56;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
              }
              v57 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                      v75,
                      &StringRawBuffer);
              std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::_Erase<DataStoreCache::DataItemIdentifier>(
                (char *)this + 56,
                v57);
              WindowsDeleteString(StringRawBuffer);
            }
            if ( this != (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)-152LL )
              ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
            if ( !v30 )
            {
LABEL_57:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
LABEL_23:
              v24 = v66;
              if ( v66 )
              {
                v66 = 0;
                (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v24 + 16LL))(v24);
              }
              v25 = v64;
              if ( v64 )
              {
                v64 = 0;
                (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v25 + 16LL))(v25);
              }
              goto LABEL_27;
            }
            v32 = (HSTRING *)(*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                               v75,
                               v70);
            StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*v32, 0);
            UnifiedTileTelemetry::AllTilesCollection_TileRemoved<unsigned short const *>(&StringRawBuffer);
            WindowsDeleteString(v70[0]);
            v62 = 0;
            StringRawBuffer = v30;
            v70[0] = 0;
            v69 = 0;
            v67 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
            v33 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs,std::nullptr_t,std::nullptr_t,std::nullptr_t,WindowsInternal::Shell::UnifiedTile::ICollectionTile *>(
                    (unsigned int)&v62,
                    (unsigned int)&v67,
                    (unsigned int)&v69,
                    (unsigned int)v70,
                    (__int64)&StringRawBuffer);
            v34 = v33;
            if ( v33 >= 0 )
            {
              v35 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<WindowsInternal::Shell::UnifiedTile::AllTilesCollection *,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs *>(
                      (char *)this + 184,
                      (char *)this - 24,
                      v62);
              v36 = v35;
              if ( v35 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x156,
                  (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
                  (const char *)(unsigned int)v35,
                  v59);
                v37 = v62;
                if ( v62 )
                {
                  v62 = 0;
                  (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
                }
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v30 + 16LL))(v30);
                v38 = v66;
                if ( v66 )
                {
                  v66 = 0;
                  (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v38 + 16LL))(v38);
                }
                v39 = v64;
                if ( v64 )
                {
                  v64 = 0;
                  (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v39 + 16LL))(v39);
                }
                v40 = v75;
                if ( v75 )
                {
                  v75 = 0;
                  (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v40 + 16LL))(v40);
                }
                v41 = v63;
                if ( v63 )
                {
                  v63 = 0;
                  (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v41 + 16LL))(v41);
                }
                wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v71);
                return v36;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
              goto LABEL_57;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x155,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
              (const char *)(unsigned int)v33,
              v59);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
            v52 = v75;
            if ( v75 )
              goto LABEL_81;
LABEL_82:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v71);
            return v34;
          }
          if ( !v19
            || !WindowsInternal::Shell::UnifiedTile::AllTilesCollection::ShouldIncludeTile(
                  (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)((char *)this - 24),
                  v66) )
          {
            goto LABEL_23;
          }
          v62 = 0;
          AcquireSRWLockExclusive((PSRWLOCK)this + 19);
          StringRawBuffer = (HSTRING)((char *)this + 152);
          v42 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                  v75,
                  &string);
          v43 = (__int64 *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::find(
                             (char *)this + 56,
                             v70,
                             v42);
          v44 = *((_QWORD *)this + 8);
          v45 = *v43;
          WindowsDeleteString(string);
          if ( v45 == v44 )
          {
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v62);
            CollectionTileFromDataItem = WindowsInternal::Shell::UnifiedTile::GetCollectionTileFromDataItem(
                                           v75,
                                           v64,
                                           (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *)(((unsigned __int64)this - 8) & -(__int64)(this != (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)24)),
                                           (struct WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer *)&v62,
                                           v58);
            if ( CollectionTileFromDataItem < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x12F,
                (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
                (const char *)(unsigned int)CollectionTileFromDataItem,
                v60);
            if ( v62 )
            {
              v47 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                      v75,
                      &string);
              v48 = *(_QWORD *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier,>(
                                 (char *)this + 56,
                                 v70,
                                 v47);
              v49 = v62;
              if ( v62 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v62 + 8LL))(v62);
              v50 = *(_QWORD *)(v48 + 24);
              *(_QWORD *)(v48 + 24) = v49;
              if ( v50 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              WindowsDeleteString(string);
            }
          }
          if ( this != (WindowsInternal::Shell::UnifiedTile::AllTilesCollection *)-152LL )
            ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
          if ( !v62 )
          {
LABEL_64:
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v62);
            goto LABEL_23;
          }
          v53 = (HSTRING *)(*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, HSTRING *))(*(_QWORD *)v75 + 32LL))(
                             v75,
                             &v69);
          string = (HSTRING)WindowsGetStringRawBuffer(*v53, 0);
          UnifiedTileTelemetry::AllTilesCollection_TileAdded<unsigned short const *>(&string);
          WindowsDeleteString(v69);
          v67 = 0;
          v69 = 0;
          string = v62;
          v70[0] = 0;
          StringRawBuffer = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
          v54 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs,std::nullptr_t,std::nullptr_t,std::nullptr_t,WindowsInternal::Shell::UnifiedTile::CollectionTile *>(
                  (unsigned int)&v67,
                  (unsigned int)&StringRawBuffer,
                  (unsigned int)v70,
                  (unsigned int)&string,
                  (__int64)&v69);
          v34 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13B,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
              (const char *)(unsigned int)v54,
              v61);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
            v52 = v75;
            if ( !v75 )
              goto LABEL_82;
          }
          else
          {
            v55 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<WindowsInternal::Shell::UnifiedTile::AllTilesCollection *,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs *>(
                    (char *)this + 184,
                    (char *)this - 24,
                    v67);
            v34 = v55;
            if ( v55 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
              goto LABEL_64;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13C,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
              (const char *)(unsigned int)v55,
              v61);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
            v52 = v75;
            if ( !v75 )
              goto LABEL_82;
          }
LABEL_81:
          v75 = 0;
          (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v52 + 16LL))(v52);
          goto LABEL_82;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
        v51 = v75;
        if ( v75 )
        {
          v75 = 0;
          (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v51 + 16LL))(v51);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v71);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
        (const char *)(unsigned int)v17,
        (int)v58);
      v28 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v75;
      if ( v75 )
      {
        v75 = 0;
        (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v27 = v63;
      if ( v63 )
        goto LABEL_30;
    }
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v71);
    result = v11;
  }
  catch ( ... )
  {
    LODWORD(v75) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x15D,
                     (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
                     v13);
    return (unsigned int)v75;
  }
  return result;
}

```

## disassembly

```asm
0x18003dcf0  mov     rax, rsp
0x18003dcf3  mov     [rax+8], rbx
0x18003dcf7  mov     [rax+10h], rsi
0x18003dcfb  push    rdi
0x18003dcfc  push    r12
0x18003dcfe  push    r13
0x18003dd00  push    r14
0x18003dd02  push    r15
0x18003dd04  sub     rsp, 0D0h
0x18003dd0b  mov     rdi, r8
0x18003dd0e  mov     rbx, rdx
0x18003dd11  mov     r14, rcx
0x18003dd14  lea     rdx, aAlltilescollec_2; "AllTilesCollection_OnEvent"
0x18003dd1b  lea     rcx, [rax-78h]
0x18003dd1f  call    ?WatchCurrentThread@UnifiedTileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UnifiedTileTelemetry::WatchCurrentThread(char const *)
0x18003dd24  nop
0x18003dd25  mov     rax, [rbx]
0x18003dd28  sub     rax, qword ptr cs:_GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1
0x18003dd2f  jnz     short loc_18003DD3C
0x18003dd31  mov     rax, [rbx+8]
0x18003dd35  sub     rax, qword ptr cs:_GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data4
0x18003dd3c  xor     r13d, r13d
0x18003dd3f  test    rax, rax
0x18003dd42  jnz     short loc_18003DDA2
0x18003dd44  mov     [rsp+0F8h+var_C0], r13
0x18003dd49  mov     rax, [rdi]
0x18003dd4c  mov     rbx, [rax]
0x18003dd4f  lea     rcx, [rsp+0F8h+var_C0]
0x18003dd54  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x18003dd59  mov     r8, rax
0x18003dd5c  lea     rdx, _GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e
0x18003dd63  mov     rcx, rdi
0x18003dd66  mov     rax, rbx
0x18003dd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd6e  mov     ebx, eax
0x18003dd70  test    eax, eax
0x18003dd72  js      loc_18003DF77
0x18003dd78  mov     rcx, [rsp+0F8h+var_C0]; this
0x18003dd7d  call    ?CouldDataItemChangeAffectAppListVisibility@UnifiedTile@Shell@WindowsInternal@@YA_NPEAUIDataItemChangeEvent@DataStoreCache@@@Z; WindowsInternal::Shell::UnifiedTile::CouldDataItemChangeAffectAppListVisibility(DataStoreCache::IDataItemChangeEvent *)
0x18003dd82  test    al, al
0x18003dd84  jnz     short loc_18003DDE6
0x18003dd86  mov     rcx, [rsp+0F8h+var_C0]
0x18003dd8b  test    rcx, rcx
0x18003dd8e  jz      short loc_18003DDA2
0x18003dd90  mov     [rsp+0F8h+var_C0], r13
0x18003dd95  mov     rax, [rcx]
0x18003dd98  mov     rax, [rax+10h]
0x18003dd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dda1  nop
0x18003dda2  cmp     [rsp+0F8h+var_40], r13d
0x18003ddaa  jz      short loc_18003DDBA
0x18003ddac  lea     rcx, [rsp+0F8h+var_58]; this
0x18003ddb4  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003ddb9  nop
0x18003ddba  lea     rcx, [rsp+0F8h+var_78]; this
0x18003ddc2  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x18003ddc7  xor     eax, eax
0x18003ddc9  lea     r11, [rsp+0F8h+var_28]
0x18003ddd1  mov     rbx, [r11+30h]
0x18003ddd5  mov     rsi, [r11+38h]
0x18003ddd9  mov     rsp, r11
0x18003dddc  pop     r15
0x18003ddde  pop     r14
0x18003dde0  pop     r13
0x18003dde2  pop     r12
0x18003dde4  pop     rdi
0x18003dde5  retn
0x18003dde6  mov     rcx, [rsp+0F8h+var_C0]
0x18003ddeb  mov     rax, [rcx]
0x18003ddee  lea     rdx, [rsp+0F8h+arg_18]
0x18003ddf6  mov     rax, [rax+28h]
0x18003ddfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddff  nop
0x18003de00  mov     rcx, [rsp+0F8h+arg_18]
0x18003de08  mov     rax, [rcx]
0x18003de0b  mov     rax, [rax+18h]
0x18003de0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de14  mov     rcx, [rax]
0x18003de17  sub     rcx, qword ptr cs:TileData
0x18003de1e  jnz     short loc_18003DE2B
0x18003de20  mov     rcx, [rax+8]
0x18003de24  sub     rcx, qword ptr cs:TileData+8
0x18003de2b  test    rcx, rcx
0x18003de2e  jnz     loc_18003DF50
0x18003de34  mov     [rsp+0F8h+var_B8], r13
0x18003de39  lea     rcx, [r14+78h]
0x18003de3d  lea     rdx, [rsp+0F8h+var_B8]
0x18003de42  call    ??$As@UIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>>)
0x18003de47  mov     ebx, eax
0x18003de49  test    eax, eax
0x18003de4b  js      loc_18003DFC4
0x18003de51  cmp     [rsp+0F8h+var_B8], r13
0x18003de56  jz      loc_18003E3DA
0x18003de5c  mov     [rsp+0F8h+var_A8], r13
0x18003de61  lea     rcx, [rsp+0F8h+var_A8]
0x18003de66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003de6b  lea     r8, [rsp+0F8h+var_A8]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *
0x18003de70  mov     rdx, [rsp+0F8h+var_B8]; struct DataStoreCache::IDataItem *
0x18003de75  mov     rcx, [rsp+0F8h+arg_18]; this
0x18003de7d  call    ?GetUnifiedTileFromDataItem@UnifiedTile@Shell@WindowsInternal@@YAJPEAUIDataItem@DataStoreCache@@PEAUIUnifiedTileManager@123@PEAPEAUIUnifiedTile@123@@Z; WindowsInternal::Shell::UnifiedTile::GetUnifiedTileFromDataItem(DataStoreCache::IDataItem *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,WindowsInternal::Shell::UnifiedTile::IUnifiedTile * *)
0x18003de82  test    eax, eax
0x18003de84  jns     loc_18003E04F
0x18003de8a  mov     dil, r13b
0x18003de8d  lea     rbx, [r14+98h]
0x18003de94  mov     rcx, rbx; SRWLock
0x18003de97  call    cs:__imp_AcquireSRWLockShared
0x18003de9d  mov     [rsp+0F8h+var_98], rbx
0x18003dea2  lea     r15, [r14+38h]
0x18003dea6  mov     rcx, [rsp+0F8h+arg_18]
0x18003deae  mov     rax, [rcx]
0x18003deb1  lea     rdx, [rsp+0F8h+string]
0x18003deb6  mov     rax, [rax+20h]
0x18003deba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003debf  mov     r8, rax
0x18003dec2  lea     rdx, [rsp+0F8h+var_88]
0x18003dec7  mov     rcx, r15
0x18003deca  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x18003decf  mov     rsi, [r14+40h]
0x18003ded3  mov     r12, [rax]
0x18003ded6  mov     rcx, [rsp+0F8h+string]; string
0x18003dedb  call    cs:__imp_WindowsDeleteString
0x18003dee1  nop
0x18003dee2  test    rbx, rbx
0x18003dee5  jz      short loc_18003DEF0
0x18003dee7  mov     rcx, rbx; SRWLock
0x18003deea  call    cs:__imp_ReleaseSRWLockShared
0x18003def0  cmp     r12, rsi
0x18003def3  jz      loc_18003E26F
0x18003def9  test    dil, dil
0x18003defc  jz      loc_18003E062
0x18003df02  lea     rcx, [r14-18h]; this
0x18003df06  mov     rdx, [rsp+0F8h+var_A8]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *
0x18003df0b  call    ?ShouldIncludeTile@AllTilesCollection@UnifiedTile@Shell@WindowsInternal@@AEBA_NPEAUIUnifiedTile@234@@Z; WindowsInternal::Shell::UnifiedTile::AllTilesCollection::ShouldIncludeTile(WindowsInternal::Shell::UnifiedTile::IUnifiedTile *)
0x18003df10  test    al, al
0x18003df12  jz      loc_18003E062
0x18003df18  mov     rcx, [rsp+0F8h+var_A8]
0x18003df1d  test    rcx, rcx
0x18003df20  jz      short loc_18003DF34
0x18003df22  mov     [rsp+0F8h+var_A8], r13
0x18003df27  mov     rax, [rcx]
0x18003df2a  mov     rax, [rax+10h]
0x18003df2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df33  nop
0x18003df34  mov     rcx, [rsp+0F8h+var_B8]
0x18003df39  test    rcx, rcx
0x18003df3c  jz      short loc_18003DF50
0x18003df3e  mov     [rsp+0F8h+var_B8], r13
0x18003df43  mov     rax, [rcx]
0x18003df46  mov     rax, [rax+10h]
0x18003df4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df4f  nop
0x18003df50  mov     rcx, [rsp+0F8h+arg_18]
0x18003df58  test    rcx, rcx
0x18003df5b  jz      short loc_18003DF72
0x18003df5d  mov     [rsp+0F8h+arg_18], r13
0x18003df65  mov     rax, [rcx]
0x18003df68  mov     rax, [rax+10h]
0x18003df6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df71  nop
0x18003df72  jmp     loc_18003DD86
0x18003df77  mov     rcx, [rsp+0F8h]; this
0x18003df7f  mov     r9d, ebx; char *
0x18003df82  lea     r8, aShellcommonShe_154; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18003df89  mov     edx, 111h; void *
0x18003df8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003df93  nop
0x18003df94  mov     rcx, [rsp+0F8h+var_C0]
0x18003df99  test    rcx, rcx
0x18003df9c  jz      short loc_18003DFB0
0x18003df9e  mov     [rsp+0F8h+var_C0], r13
0x18003dfa3  mov     rax, [rcx]
0x18003dfa6  mov     rax, [rax+10h]
0x18003dfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfaf  nop
0x18003dfb0  lea     rcx, [rsp+0F8h+var_78]; this
0x18003dfb8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003dfbd  mov     eax, ebx
0x18003dfbf  jmp     loc_18003DDC9
0x18003dfc4  mov     rcx, [rsp+0F8h]; this
0x18003dfcc  mov     r9d, ebx; char *
0x18003dfcf  lea     r8, aShellcommonShe_154; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18003dfd6  mov     edx, 119h; void *
0x18003dfdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dfe0  nop
0x18003dfe1  mov     rcx, [rsp+0F8h+var_B8]
0x18003dfe6  test    rcx, rcx
0x18003dfe9  jz      short loc_18003DFFD
0x18003dfeb  mov     [rsp+0F8h+var_B8], r13
0x18003dff0  mov     rax, [rcx]
0x18003dff3  mov     rax, [rax+10h]
0x18003dff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dffc  nop
0x18003dffd  mov     rcx, [rsp+0F8h+arg_18]
0x18003e005  test    rcx, rcx
0x18003e008  jz      short loc_18003E01F
0x18003e00a  mov     [rsp+0F8h+arg_18], r13
0x18003e012  mov     rax, [rcx]
0x18003e015  mov     rax, [rax+10h]
0x18003e019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e01e  nop
0x18003e01f  mov     rcx, [rsp+0F8h+var_C0]
0x18003e024  test    rcx, rcx
0x18003e027  jz      short loc_18003E03B
0x18003e029  mov     [rsp+0F8h+var_C0], r13
0x18003e02e  mov     rax, [rcx]
0x18003e031  mov     rax, [rax+10h]
0x18003e035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e03a  nop
0x18003e03b  lea     rcx, [rsp+0F8h+var_78]; this
0x18003e043  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003e048  mov     eax, ebx
0x18003e04a  jmp     loc_18003DDC9
0x18003e04f  cmp     [rsp+0F8h+var_A8], r13
0x18003e054  mov     dil, 1
0x18003e057  jnz     loc_18003DE8D
0x18003e05d  jmp     loc_18003DE8A
0x18003e062  mov     rdi, r13
0x18003e065  mov     [rsp+0F8h+string], r13
0x18003e06a  mov     rcx, rbx; SRWLock
0x18003e06d  call    cs:__imp_AcquireSRWLockExclusive
0x18003e073  mov     [rsp+0F8h+var_90], rbx
0x18003e078  mov     rcx, [rsp+0F8h+arg_18]
0x18003e080  mov     rax, [rcx]
0x18003e083  lea     rdx, [rsp+0F8h+var_98]
0x18003e088  mov     rax, [rax+20h]
0x18003e08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e091  mov     r8, rax
0x18003e094  lea     rdx, [rsp+0F8h+var_88]
0x18003e099  mov     rcx, r15
0x18003e09c  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x18003e0a1  mov     rcx, [rsp+0F8h+var_98]; string
0x18003e0a6  call    cs:__imp_WindowsDeleteString
0x18003e0ac  mov     rax, [rsp+0F8h+var_88]
0x18003e0b1  cmp     rax, [r14+40h]
0x18003e0b5  jnz     loc_18003E681
0x18003e0bb  test    rbx, rbx
0x18003e0be  jnz     loc_18003E261
0x18003e0c4  test    rdi, rdi
0x18003e0c7  jz      loc_18003E252
0x18003e0cd  mov     rcx, [rsp+0F8h+arg_18]
0x18003e0d5  mov     rax, [rcx]
0x18003e0d8  lea     rdx, [rsp+0F8h+var_88]
0x18003e0dd  mov     rax, [rax+20h]
0x18003e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0e6  xor     edx, edx; length
0x18003e0e8  mov     rcx, [rax]; string
0x18003e0eb  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e0f1  mov     [rsp+0F8h+var_98], rax
0x18003e0f6  lea     rcx, [rsp+0F8h+var_98]
0x18003e0fb  call    ??$AllTilesCollection_TileRemoved@PEBG@UnifiedTileTelemetry@@SAX$$QEAPEBG@Z; UnifiedTileTelemetry::AllTilesCollection_TileRemoved<ushort const *>(ushort const * &&)
0x18003e100  mov     rcx, [rsp+0F8h+var_88]; string
0x18003e105  call    cs:__imp_WindowsDeleteString
0x18003e10b  mov     [rsp+0F8h+var_C8], r13
0x18003e110  mov     [rsp+0F8h+var_98], rdi
0x18003e115  mov     [rsp+0F8h+var_88], r13
0x18003e11a  mov     [rsp+0F8h+var_90], r13
0x18003e11f  mov     [rsp+0F8h+var_A0], r13
0x18003e124  lea     rcx, [rsp+0F8h+var_C8]
0x18003e129  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e12e  lea     rax, [rsp+0F8h+var_98]
0x18003e133  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x18003e138  lea     r9, [rsp+0F8h+var_88]
0x18003e13d  lea     r8, [rsp+0F8h+var_90]
0x18003e142  lea     rdx, [rsp+0F8h+var_A0]
0x18003e147  lea     rcx, [rsp+0F8h+var_C8]
0x18003e14c  call    ??$MakeAndInitialize@VContentsChangedEventArgs@UnifiedTile@Shell@WindowsInternal@@UIContentsChangedEventArgs@234@$$T$$T$$TPEAUICollectionTile@234@@Details@WRL@Microsoft@@YAJPEAPEAUIContentsChangedEventArgs@UnifiedTile@Shell@WindowsInternal@@$$QEA$$T11$$QEAPEAUICollectionTile@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs,std::nullptr_t,std::nullptr_t,std::nullptr_t,WindowsInternal::Shell::UnifiedTile::ICollectionTile *>(WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs * *,WindowsInternal::Shell::UnifiedTile::$$T11$$QEAPEAUICollectionTile &&)
0x18003e151  mov     ebx, eax
0x18003e153  test    eax, eax
0x18003e155  js      loc_18003E538
0x18003e15b  lea     rdx, [r14-18h]
0x18003e15f  lea     rcx, [r14+0B8h]
0x18003e166  mov     r8, [rsp+0F8h+var_C8]
0x18003e16b  call    ??$InvokeAll@PEAVAllTilesCollection@UnifiedTile@Shell@WindowsInternal@@PEAUIContentsChangedEventArgs@234@@?$EventSource@U?$ITypedEventHandler@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@PEAVContentsChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVAllTilesCollection@UnifiedTile@Shell@WindowsInternal@@PEAUIContentsChangedEventArgs@456@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,WindowsInternal::Shell::UnifiedTile::ContentsChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<WindowsInternal::Shell::UnifiedTile::AllTilesCollection *,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs *>(WindowsInternal::Shell::UnifiedTile::AllTilesCollection *,WindowsInternal::Shell::UnifiedTile::IContentsChangedEventArgs *)
0x18003e170  mov     ebx, eax
0x18003e172  test    eax, eax
0x18003e174  jns     loc_18003E6E4
0x18003e17a  mov     rcx, [rsp+0F8h]; this
0x18003e182  mov     r9d, eax; char *
0x18003e185  lea     r8, aShellcommonShe_154; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18003e18c  mov     edx, 156h; void *
0x18003e191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e196  nop
0x18003e197  mov     rcx, [rsp+0F8h+var_C8]
0x18003e19c  test    rcx, rcx
0x18003e19f  jz      short loc_18003E1B3
0x18003e1a1  mov     [rsp+0F8h+var_C8], r13
0x18003e1a6  mov     rax, [rcx]
0x18003e1a9  mov     rax, [rax+10h]
0x18003e1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1b2  nop
0x18003e1b3  test    rdi, rdi
0x18003e1b6  jz      short loc_18003E1C8
0x18003e1b8  mov     rax, [rdi]
0x18003e1bb  mov     rcx, rdi
0x18003e1be  mov     rax, [rax+10h]
0x18003e1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1c7  nop
0x18003e1c8  mov     rcx, [rsp+0F8h+var_A8]
0x18003e1cd  test    rcx, rcx
0x18003e1d0  jz      short loc_18003E1E4
  ... truncated ...
```
