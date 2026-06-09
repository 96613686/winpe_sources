# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::ResurrectAllTilesForIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)

- ea: `0x1800c96c0`
- end: `0x1800ca05e`
- name: `?ResurrectAllTilesForIdentifier@CuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIUnifiedTileIdentifier@345@@Z`
- size: `2462`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000befc`
- `0x18001ac50`
- `0x18001aca4`
- `0x18002dde0`
- `0x18004a8c0`
- `0x18004bb78`
- `0x1800756e4`
- `0x18007ae80`
- `0x180087bd8`
- `0x1800b4fd0`
- `0x1800c96c0`
- `0x1800ca064`
- `0x1800cb764`
- `0x1800cc45c`
- `0x1800cc528`
- `0x180130448`
- `0x1801ac964`
- `0x1801b1d44`
- `0x180201e50`
- `0x1802405fc`
- `0x1802422dc`
- `0x1802424e4`
- `0x18033aacc`
- `0x18033adec`
- `0x18033d470`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c99e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c99e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9f83`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c9fdb`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c9fdb`

## string_xrefs

- `0x1800c97e3`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1800c9844`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1800c98bc`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1800c993f`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1800c99cd`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`
- `0x1800c9a6f`: `shellcommon\shell\tiles\curatedtilecollections\collectionmanagement\lib\curatedtilecollectionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::ResurrectAllTilesForIdentifier(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *this,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *a2)
{
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *v3; // r12
  int v4; // r14d
  struct DataStoreCache::CuratedTileCollectionTransformer::ICuratedTileCollectionTransformer **v6; // r9
  __int64 result; // rax
  _QWORD *i; // rbx
  const char *v9; // r9
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v10; // rsi
  const struct _GUID *v11; // rax
  _QWORD *v12; // rsi
  std::_Ref_count_base *v13; // rcx
  _QWORD *v14; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rdi
  DataStoreCache::CuratedTileCollectionTransformer::CuratedTile *v18; // r15
  bool v19; // si
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v20; // rsi
  const struct _GUID *LayoutId; // rax
  _QWORD *TileIdentifier; // rax
  int v23; // esi
  _QWORD *v24; // rax
  __int64 v25; // rax
  int Collection; // eax
  struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *v27; // r12
  int v28; // eax
  void (__fastcall *v29)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *); // rsi
  const OLECHAR *v30; // rcx
  __int64 v31; // rax
  __int64 (__fastcall *v32)(__int64, __int64, GUID *); // r9
  __int64 v33; // r10
  int v34; // eax
  int v35; // eax
  int v36; // [rsp+20h] [rbp-1D8h]
  char v37; // [rsp+30h] [rbp-1C8h] BYREF
  _BYTE v38[7]; // [rsp+31h] [rbp-1C7h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *v39; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 v40; // [rsp+40h] [rbp-1B8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-1A8h] BYREF
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v43; // [rsp+58h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v44; // [rsp+60h] [rbp-198h]
  DataStoreCache::CuratedTileCollectionTransformer::CuratedTile *v45; // [rsp+68h] [rbp-190h] BYREF
  std::_Ref_count_base *v46; // [rsp+70h] [rbp-188h]
  __int64 v47; // [rsp+78h] [rbp-180h] BYREF
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *v48; // [rsp+80h] [rbp-178h]
  __int64 v49; // [rsp+88h] [rbp-170h] BYREF
  std::_Ref_count_base *v50; // [rsp+90h] [rbp-168h]
  _BYTE v51[8]; // [rsp+A0h] [rbp-158h] BYREF
  _QWORD *v52; // [rsp+A8h] [rbp-150h]
  _BYTE v53[16]; // [rsp+E0h] [rbp-118h] BYREF
  _BYTE v54[16]; // [rsp+F0h] [rbp-108h] BYREF
  _BYTE v55[16]; // [rsp+100h] [rbp-F8h] BYREF
  _QWORD v56[3]; // [rsp+110h] [rbp-E8h] BYREF
  unsigned __int64 v57; // [rsp+128h] [rbp-D0h]
  GUID iid; // [rsp+130h] [rbp-C8h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+150h] [rbp-A8h] BYREF
  _BYTE v60[32]; // [rsp+170h] [rbp-88h] BYREF
  GUID v61; // [rsp+190h] [rbp-68h] BYREF
  struct _GUID v62; // [rsp+1A0h] [rbp-58h] BYREF
  struct _GUID v63; // [rsp+1B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v3 = this;
  v48 = this;
  v4 = 0;
  LODWORD(v39) = 0;
  if ( !WindowsInternal::Shell::UnifiedTile::IsTileEligibleForGraveyarding(a2, a2) )
    return 0;
  try
  {
    v40 = 0;
    DataStoreCache::CuratedTileCollectionTransformer::CreateCuratedTileCollectionTransformer(
      0,
      *((struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager **)v3 + 7),
      (struct Windows::System::IUser *)&v40,
      v6);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v40 + 96LL))(v40, L"Graveyard") )
    {
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
      return 0;
    }
    (*(void (__fastcall **)(__int64, DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot **, const WCHAR *, _QWORD))(*(_QWORD *)v40 + 80LL))(
      v40,
      &v43,
      L"Graveyard",
      0);
    DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::GetTiles(v43, v51);
    v17 = v52;
    for ( i = (_QWORD *)*v52; ; i = (_QWORD *)*i )
    {
      if ( i == v17 )
      {
        std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
        if ( v44 )
          std::_Ref_count_base::_Decref(v44);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
        return 0;
      }
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v45,
        i + 4);
      v18 = v45;
      std::wstring::wstring(v56, L"graveyard_collectionId");
      v4 |= 1u;
      LODWORD(v39) = v4;
      v19 = 1;
      if ( (unsigned __int8)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::HasCustomProperty(v18, v56) )
      {
        std::wstring::wstring(lpsz, L"graveyard_parentId");
        v4 |= 2u;
        LODWORD(v39) = v4;
        if ( (unsigned __int8)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::HasCustomProperty(
                                v18,
                                lpsz) )
          v19 = 0;
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      }
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      }
      if ( v19 )
      {
        v20 = v43;
        LayoutId = DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetLayoutId(v18, &v62);
        DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::DeleteTile(v20, LayoutId);
        goto LABEL_5;
      }
      v38[0] = 0;
      TileIdentifier = (_QWORD *)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetTileIdentifier(
                                   v18,
                                   &v47);
      v23 = (*(__int64 (__fastcall **)(_QWORD, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, _BYTE *))(*(_QWORD *)*TileIdentifier + 80LL))(
              *TileIdentifier,
              a2,
              v38);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x247,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
          (const char *)(unsigned int)v23,
          v36);
        if ( v46 )
          std::_Ref_count_base::_Decref(v46);
        std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
        if ( v44 )
          std::_Ref_count_base::_Decref(v44);
        goto LABEL_41;
      }
      if ( v38[0] )
        break;
LABEL_5:
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
    }
    std::wstring::wstring(&iid, L"graveyard_collectionId");
    DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetCustomProperty(v18, v56, &iid);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&iid);
    std::wstring::wstring(v60, L"graveyard_parentId");
    DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetCustomProperty(v18, lpsz, v60);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v60);
    if ( (unsigned __int8)std::wstring::_Equal(v56, L"Graveyard") )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)0x80070057LL,
        v36);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
      if ( v44 )
        std::_Ref_count_base::_Decref(v44);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
      return 2147942487LL;
    }
    v39 = 0;
    v24 = v56;
    if ( v57 > 7 )
      v24 = (_QWORD *)v56[0];
    *(_QWORD *)&iid.Data1 = v24;
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v60, &iid);
    Collection = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::GetCollection(
                   (WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *)((char *)v3 - 16),
                   *(HSTRING *)(v25 + 24),
                   &v39);
    v23 = Collection;
    if ( Collection < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)Collection,
        v36);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
      if ( v44 )
        std::_Ref_count_base::_Decref(v44);
      goto LABEL_41;
    }
    v42 = 0;
    v27 = v39;
    v28 = (**(__int64 (__fastcall ***)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *, GUID *, __int64 *))v39)(
            v39,
            &GUID_20477929_b8fb_43e2_9c9e_a346c98180e1,
            &v42);
    v23 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v28,
        v36);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
      if ( v44 )
        std::_Ref_count_base::_Decref(v44);
      goto LABEL_41;
    }
    string = 0;
    v29 = *(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *))(*(_QWORD *)a2 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v29(a2, &string);
    v37 = 0;
    if ( (*(int (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, _QWORD, char *))(*(_QWORD *)v27 + 112LL))(
           v27,
           a2,
           0,
           &v37) >= 0 )
    {
      if ( !v37 )
        goto LABEL_74;
      *(_QWORD *)&iid.Data1 = WindowsGetStringRawBuffer(string, 0);
      CuratedTileCollectionTransformerTelemetry::ResurrectingDuplicateTileInStart<unsigned short const *>(&iid);
    }
    if ( v37 )
    {
LABEL_42:
      v10 = v43;
      v11 = DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetLayoutId(v18, &v63);
      DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::DeleteTile(v10, v11);
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::BeginBatchUpdate(v18, &v49);
      std::wstring::wstring(v60, L"graveyard_collectionId");
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(v18, v60);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v60);
      std::wstring::wstring(v60, L"graveyard_parentId");
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(v18, v60);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v60);
      v12 = (_QWORD *)std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
                        v54,
                        &v49);
      *(_QWORD *)&iid.Data1 = v12;
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v12 + 8LL))(*v12, v55);
      v4 |= 4u;
      v13 = (std::_Ref_count_base *)v12[1];
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(v55);
      if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
      {
        v14 = v56;
        if ( v57 > 7 )
          v14 = (_QWORD *)v56[0];
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0zz_EventWriteTransfer(
          v16,
          CuratedTileCollectionTransformer_UTMIntregation_TileResurrected,
          StringRawBuffer,
          v14);
      }
      if ( v50 )
        std::_Ref_count_base::_Decref(v50);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      v3 = v48;
      goto LABEL_5;
    }
LABEL_74:
    v30 = (const OLECHAR *)lpsz;
    if ( lpsz[3] > (LPCOLESTR)7 )
      v30 = lpsz[0];
    iid = GUID_NULL;
    IIDFromString(v30, &iid);
    v61 = iid;
    v31 = std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
            v53,
            &v45);
    v34 = v32(v33, v31, &v61);
    v23 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v34,
        v36);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
      if ( v44 )
        std::_Ref_count_base::_Decref(v44);
      goto LABEL_41;
    }
    v35 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *))(*(_QWORD *)v27 + 216LL))(v27);
    v23 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26A,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v35,
        v36);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v56);
      if ( v46 )
        std::_Ref_count_base::_Decref(v46);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v51);
      if ( v44 )
        std::_Ref_count_base::_Decref(v44);
LABEL_41:
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
      return (unsigned int)v23;
    }
    goto LABEL_42;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x27A,
                           (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\c"
                                         "uratedtilecollectionmanager.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800c96c0  mov     [rsp+arg_10], rbx
0x1800c96c5  mov     [rsp+arg_18], rsi
0x1800c96ca  push    rdi
0x1800c96cb  push    r12
0x1800c96cd  push    r13
0x1800c96cf  push    r14
0x1800c96d1  push    r15
0x1800c96d3  sub     rsp, 1D0h
0x1800c96da  mov     rax, cs:__security_cookie
0x1800c96e1  xor     rax, rsp
0x1800c96e4  mov     [rsp+1F8h+var_38], rax
0x1800c96ec  mov     r13, rdx
0x1800c96ef  mov     r12, rcx
0x1800c96f2  mov     [rsp+1F8h+var_178], rcx
0x1800c96fa  xor     r14d, r14d
0x1800c96fd  mov     dword ptr [rsp+1F8h+var_1C0], r14d
0x1800c9702  mov     rcx, rdx; this
0x1800c9705  call    ?IsTileEligibleForGraveyarding@UnifiedTile@Shell@WindowsInternal@@YA_NPEAUIUnifiedTileIdentifier@123@@Z; WindowsInternal::Shell::UnifiedTile::IsTileEligibleForGraveyarding(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x1800c970a  test    al, al
0x1800c970c  jnz     loc_1800C9C51
0x1800c9712  xor     eax, eax
0x1800c9714  mov     rcx, [rsp+1F8h+var_38]
0x1800c971c  xor     rcx, rsp; StackCookie
0x1800c971f  call    __security_check_cookie
0x1800c9724  lea     r11, [rsp+1F8h+var_28]
0x1800c972c  mov     rbx, [r11+40h]
0x1800c9730  mov     rsi, [r11+48h]
0x1800c9734  mov     rsp, r11
0x1800c9737  pop     r15
0x1800c9739  pop     r14
0x1800c973b  pop     r13
0x1800c973d  pop     r12
0x1800c973f  pop     rdi
0x1800c9740  retn
0x1800c9741  mov     rcx, [rsp+1F8h+string]; string
0x1800c9746  call    cs:__imp_WindowsDeleteString
0x1800c974c  mov     [rsp+1F8h+string], 0
0x1800c9755  lea     rcx, [rsp+1F8h+var_1A8]; void *
0x1800c975a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c975f  nop
0x1800c9760  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x1800c9765  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c976a  nop
0x1800c976b  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c9773  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9778  nop
0x1800c9779  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c9781  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9786  mov     r12, [rsp+1F8h+var_178]
0x1800c978e  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c9793  test    rcx, rcx
0x1800c9796  jz      short loc_1800C979D
0x1800c9798  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c979d  mov     rbx, [rbx]
0x1800c97a0  cmp     rbx, rdi
0x1800c97a3  jnz     loc_1800C9CDC
0x1800c97a9  lea     rcx, [rsp+1F8h+var_158]
0x1800c97b1  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c97b6  nop
0x1800c97b7  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c97bc  test    rcx, rcx
0x1800c97bf  jz      short loc_1800C97C7
0x1800c97c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c97c6  nop
0x1800c97c7  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c97cc  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c97d1  xor     eax, eax
0x1800c97d3  jmp     loc_1800C9714
0x1800c97d8  mov     rcx, [rsp+1F8h]; this
0x1800c97e0  mov     r9d, esi; char *
0x1800c97e3  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c97ea  mov     edx, 247h; void *
0x1800c97ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c97f4  nop
0x1800c97f5  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c97fa  test    rcx, rcx
0x1800c97fd  jz      short loc_1800C9805
0x1800c97ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9804  nop
0x1800c9805  lea     rcx, [rsp+1F8h+var_158]
0x1800c980d  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c9812  nop
0x1800c9813  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c9818  test    rcx, rcx
0x1800c981b  jz      short loc_1800C9823
0x1800c981d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9822  nop
0x1800c9823  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c9828  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c982d  mov     eax, esi
0x1800c982f  jmp     loc_1800C9714
0x1800c9834  mov     rcx, [rsp+1F8h]; this
0x1800c983c  mov     ebx, 80070057h
0x1800c9841  mov     r9d, ebx; char *
0x1800c9844  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c984b  mov     edx, 251h; void *
0x1800c9850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9855  nop
0x1800c9856  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c985e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9863  nop
0x1800c9864  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c986c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9871  nop
0x1800c9872  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c9877  test    rcx, rcx
0x1800c987a  jz      short loc_1800C9882
0x1800c987c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9881  nop
0x1800c9882  lea     rcx, [rsp+1F8h+var_158]
0x1800c988a  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c988f  nop
0x1800c9890  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c9895  test    rcx, rcx
0x1800c9898  jz      short loc_1800C98A0
0x1800c989a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c989f  nop
0x1800c98a0  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c98a5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c98aa  mov     eax, ebx
0x1800c98ac  jmp     loc_1800C9714
0x1800c98b1  mov     rcx, [rsp+1F8h]; this
0x1800c98b9  mov     r9d, esi; char *
0x1800c98bc  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c98c3  mov     edx, 254h; void *
0x1800c98c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c98cd  nop
0x1800c98ce  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x1800c98d3  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c98d8  nop
0x1800c98d9  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c98e1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c98e6  nop
0x1800c98e7  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c98ef  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c98f4  nop
0x1800c98f5  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c98fa  test    rcx, rcx
0x1800c98fd  jz      short loc_1800C9905
0x1800c98ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9904  nop
0x1800c9905  lea     rcx, [rsp+1F8h+var_158]
0x1800c990d  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c9912  nop
0x1800c9913  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c9918  test    rcx, rcx
0x1800c991b  jz      short loc_1800C9923
0x1800c991d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9922  nop
0x1800c9923  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c9928  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c992d  mov     eax, esi
0x1800c992f  jmp     loc_1800C9714
0x1800c9934  mov     rcx, [rsp+1F8h]; this
0x1800c993c  mov     r9d, esi; char *
0x1800c993f  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c9946  mov     edx, 257h; void *
0x1800c994b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9950  nop
0x1800c9951  lea     rcx, [rsp+1F8h+var_1A8]; void *
0x1800c9956  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c995b  nop
0x1800c995c  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x1800c9961  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9966  nop
0x1800c9967  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c996f  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9974  nop
0x1800c9975  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c997d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9982  nop
0x1800c9983  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c9988  test    rcx, rcx
0x1800c998b  jz      short loc_1800C9993
0x1800c998d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9992  nop
0x1800c9993  lea     rcx, [rsp+1F8h+var_158]
0x1800c999b  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c99a0  nop
0x1800c99a1  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c99a6  test    rcx, rcx
0x1800c99a9  jz      short loc_1800C99B1
0x1800c99ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c99b0  nop
0x1800c99b1  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c99b6  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c99bb  mov     eax, esi
0x1800c99bd  jmp     loc_1800C9714
0x1800c99c2  mov     rcx, [rsp+1F8h]; this
0x1800c99ca  mov     r9d, esi; char *
0x1800c99cd  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c99d4  mov     edx, 269h; void *
0x1800c99d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c99de  nop
0x1800c99df  mov     rcx, [rsp+1F8h+string]; string
0x1800c99e4  call    cs:__imp_WindowsDeleteString
0x1800c99ea  mov     [rsp+1F8h+string], 0
0x1800c99f3  lea     rcx, [rsp+1F8h+var_1A8]; void *
0x1800c99f8  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c99fd  nop
0x1800c99fe  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x1800c9a03  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9a08  nop
0x1800c9a09  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c9a11  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9a16  nop
0x1800c9a17  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c9a1f  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9a24  nop
0x1800c9a25  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c9a2a  test    rcx, rcx
0x1800c9a2d  jz      short loc_1800C9A35
0x1800c9a2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9a34  nop
0x1800c9a35  lea     rcx, [rsp+1F8h+var_158]
0x1800c9a3d  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c9a42  nop
0x1800c9a43  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c9a48  test    rcx, rcx
0x1800c9a4b  jz      short loc_1800C9A53
0x1800c9a4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9a52  nop
0x1800c9a53  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c9a58  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9a5d  mov     eax, esi
0x1800c9a5f  jmp     loc_1800C9714
0x1800c9a64  mov     rcx, [rsp+1F8h]; this
0x1800c9a6c  mov     r9d, esi; char *
0x1800c9a6f  lea     r8, aShellcommonShe_237; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c9a76  mov     edx, 26Ah; void *
0x1800c9a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9a80  nop
0x1800c9a81  mov     rcx, [rsp+1F8h+string]; string
0x1800c9a86  call    cs:__imp_WindowsDeleteString
0x1800c9a8c  mov     [rsp+1F8h+string], 0
0x1800c9a95  lea     rcx, [rsp+1F8h+var_1A8]; void *
0x1800c9a9a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9a9f  nop
0x1800c9aa0  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x1800c9aa5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9aaa  nop
0x1800c9aab  lea     rcx, [rsp+1F8h+lpsz]; void *
0x1800c9ab3  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9ab8  nop
0x1800c9ab9  lea     rcx, [rsp+1F8h+var_E8]; void *
0x1800c9ac1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9ac6  nop
0x1800c9ac7  mov     rcx, [rsp+1F8h+var_188]; this
0x1800c9acc  test    rcx, rcx
0x1800c9acf  jz      short loc_1800C9AD7
0x1800c9ad1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9ad6  nop
0x1800c9ad7  lea     rcx, [rsp+1F8h+var_158]
0x1800c9adf  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(void)
0x1800c9ae4  nop
0x1800c9ae5  mov     rcx, [rsp+1F8h+var_198]; this
0x1800c9aea  test    rcx, rcx
0x1800c9aed  jz      short loc_1800C9AF5
0x1800c9aef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9af4  nop
0x1800c9af5  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x1800c9afa  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1800c9aff  mov     eax, esi
0x1800c9b01  jmp     loc_1800C9714
0x1800c9b06  mov     rsi, [rsp+1F8h+var_1A0]
0x1800c9b0b  lea     rdx, [rsp+1F8h+var_48]; retstr
0x1800c9b13  mov     rcx, r15; this
0x1800c9b16  call    ?GetLayoutId@CuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@QEAA?AU_GUID@@XZ; DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetLayoutId(void)
0x1800c9b1b  mov     rdx, rax; struct _GUID *
0x1800c9b1e  mov     rcx, rsi; this
0x1800c9b21  call    ?DeleteTile@CuratedRoot@CuratedTileCollectionTransformer@DataStoreCache@@QEAAXAEBU_GUID@@@Z; DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::DeleteTile(_GUID const &)
0x1800c9b26  lea     rdx, [rsp+1F8h+var_170]
0x1800c9b2e  mov     rcx, r15
0x1800c9b31  call    ?BeginBatchUpdate@CuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@VICuratedCollectionBatchCookieImpl@CuratedTileCollectionTransformer@DataStoreCache@@@std@@XZ; DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::BeginBatchUpdate(void)
0x1800c9b36  nop
0x1800c9b37  lea     rdx, aGraveyardColle; "graveyard_collectionId"
0x1800c9b3e  lea     rcx, [rsp+1F8h+var_88]
0x1800c9b46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9b4b  nop
0x1800c9b4c  lea     rdx, [rsp+1F8h+var_88]
0x1800c9b54  mov     rcx, r15
0x1800c9b57  call    ?RemoveCustomProperty@CuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(std::wstring const &)
0x1800c9b5c  nop
0x1800c9b5d  lea     rcx, [rsp+1F8h+var_88]; void *
0x1800c9b65  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9b6a  lea     rdx, aGraveyardParen; "graveyard_parentId"
0x1800c9b71  lea     rcx, [rsp+1F8h+var_88]
0x1800c9b79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9b7e  nop
0x1800c9b7f  lea     rdx, [rsp+1F8h+var_88]
0x1800c9b87  mov     rcx, r15
0x1800c9b8a  call    ?RemoveCustomProperty@CuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(std::wstring const &)
0x1800c9b8f  nop
0x1800c9b90  lea     rcx, [rsp+1F8h+var_88]; void *
0x1800c9b98  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1800c9b9d  lea     rdx, [rsp+1F8h+var_170]
0x1800c9ba5  lea     rcx, [rsp+1F8h+var_108]
0x1800c9bad  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x1800c9bb2  mov     rsi, rax
0x1800c9bb5  mov     qword ptr [rsp+1F8h+iid.Data1], rax
  ... truncated ...
```
