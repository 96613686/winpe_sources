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
  __int64 v8; // r8
  __int64 v9; // r9
  _QWORD *i; // rbx
  const char *v11; // r9
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v12; // rsi
  const struct _GUID *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *v16; // rsi
  std::_Ref_count_base *v17; // rcx
  _QWORD *v18; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rdi
  DataStoreCache::CuratedTileCollectionTransformer::CuratedTile *v22; // r15
  bool v23; // si
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v24; // rsi
  const struct _GUID *LayoutId; // rax
  _QWORD *TileIdentifier; // rax
  int v27; // esi
  _QWORD *v28; // rax
  HSTRING_HEADER *v29; // rax
  int Collection; // eax
  struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *v31; // r12
  int v32; // eax
  void (__fastcall *v33)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *); // rsi
  const OLECHAR *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 (__fastcall *v37)(__int64, __int64, GUID *); // r9
  __int64 v38; // r10
  int v39; // eax
  int v40; // eax
  int v41; // [rsp+20h] [rbp-1D8h]
  char v42; // [rsp+30h] [rbp-1C8h] BYREF
  _BYTE v43[7]; // [rsp+31h] [rbp-1C7h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *v44; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 v45; // [rsp+40h] [rbp-1B8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-1A8h] BYREF
  DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot *v48; // [rsp+58h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v49; // [rsp+60h] [rbp-198h]
  DataStoreCache::CuratedTileCollectionTransformer::CuratedTile *v50; // [rsp+68h] [rbp-190h] BYREF
  std::_Ref_count_base *v51; // [rsp+70h] [rbp-188h]
  __int64 v52; // [rsp+78h] [rbp-180h] BYREF
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *v53; // [rsp+80h] [rbp-178h]
  __int64 v54; // [rsp+88h] [rbp-170h] BYREF
  std::_Ref_count_base *v55; // [rsp+90h] [rbp-168h]
  _BYTE v56[8]; // [rsp+A0h] [rbp-158h] BYREF
  _QWORD *v57; // [rsp+A8h] [rbp-150h]
  _BYTE v58[16]; // [rsp+E0h] [rbp-118h] BYREF
  _BYTE v59[16]; // [rsp+F0h] [rbp-108h] BYREF
  _BYTE v60[16]; // [rsp+100h] [rbp-F8h] BYREF
  _QWORD v61[3]; // [rsp+110h] [rbp-E8h] BYREF
  unsigned __int64 v62; // [rsp+128h] [rbp-D0h]
  GUID iid; // [rsp+130h] [rbp-C8h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+150h] [rbp-A8h] BYREF
  HSTRING_HEADER v65; // [rsp+170h] [rbp-88h] BYREF
  GUID v66; // [rsp+190h] [rbp-68h] BYREF
  struct _GUID v67; // [rsp+1A0h] [rbp-58h] BYREF
  struct _GUID v68; // [rsp+1B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v3 = this;
  v53 = this;
  v4 = 0;
  LODWORD(v44) = 0;
  if ( !WindowsInternal::Shell::UnifiedTile::IsTileEligibleForGraveyarding(a2, a2) )
    return 0;
  try
  {
    v45 = 0;
    DataStoreCache::CuratedTileCollectionTransformer::CreateCuratedTileCollectionTransformer(
      0,
      *((struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager **)v3 + 7),
      (struct Windows::System::IUser *)&v45,
      v6);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v45 + 96LL))(v45, L"Graveyard") )
    {
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
      return 0;
    }
    (*(void (__fastcall **)(__int64, DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot **, const WCHAR *, _QWORD))(*(_QWORD *)v45 + 80LL))(
      v45,
      &v48,
      L"Graveyard",
      0);
    DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::GetTiles(v48, v56);
    v21 = v57;
    for ( i = (_QWORD *)*v57; ; i = (_QWORD *)*i )
    {
      if ( i == v21 )
      {
        std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
        return 0;
      }
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v50,
        i + 4,
        v8,
        v9);
      v22 = v50;
      std::wstring::wstring(v61, L"graveyard_collectionId");
      v4 |= 1u;
      LODWORD(v44) = v4;
      v23 = 1;
      if ( (unsigned __int8)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::HasCustomProperty(v22, v61) )
      {
        std::wstring::wstring(lpsz, L"graveyard_parentId");
        v4 |= 2u;
        LODWORD(v44) = v4;
        if ( (unsigned __int8)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::HasCustomProperty(
                                v22,
                                lpsz) )
          v23 = 0;
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      }
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      }
      if ( v23 )
      {
        v24 = v48;
        LayoutId = DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetLayoutId(v22, &v67);
        DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::DeleteTile(v24, LayoutId);
        goto LABEL_5;
      }
      v43[0] = 0;
      TileIdentifier = (_QWORD *)DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetTileIdentifier(
                                   v22,
                                   &v52);
      v27 = (*(__int64 (__fastcall **)(_QWORD, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, _BYTE *))(*(_QWORD *)*TileIdentifier + 80LL))(
              *TileIdentifier,
              a2,
              v43);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v52);
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x247,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
          (const char *)(unsigned int)v27,
          v41);
        if ( v51 )
          std::_Ref_count_base::_Decref(v51);
        std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
        goto LABEL_41;
      }
      if ( v43[0] )
        break;
LABEL_5:
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
    }
    std::wstring::wstring(&iid, L"graveyard_collectionId");
    DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetCustomProperty(v22, v61, &iid);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&iid);
    std::wstring::wstring(&v65, L"graveyard_parentId");
    DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetCustomProperty(v22, lpsz, &v65);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v65);
    if ( (unsigned __int8)std::wstring::_Equal(v61, L"Graveyard") )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)0x80070057LL,
        v41);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
      return 2147942487LL;
    }
    v44 = 0;
    v28 = v61;
    if ( v62 > 7 )
      v28 = (_QWORD *)v61[0];
    *(_QWORD *)&iid.Data1 = v28;
    v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v65, (const WCHAR **)&iid);
    Collection = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::GetCollection(
                   (WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *)((char *)v3 - 16),
                   (HSTRING)v29[1].Reserved.Reserved1,
                   &v44);
    v27 = Collection;
    if ( Collection < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)Collection,
        v41);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
      goto LABEL_41;
    }
    v47 = 0;
    v31 = v44;
    v32 = (**(__int64 (__fastcall ***)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *, GUID *, __int64 *))v44)(
            v44,
            &GUID_20477929_b8fb_43e2_9c9e_a346c98180e1,
            &v47);
    v27 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v32,
        v41);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
      goto LABEL_41;
    }
    string = 0;
    v33 = *(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *))(*(_QWORD *)a2 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v33(a2, &string);
    v42 = 0;
    if ( (*(int (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, _QWORD, char *))(*(_QWORD *)v31 + 112LL))(
           v31,
           a2,
           0,
           &v42) >= 0 )
    {
      if ( !v42 )
        goto LABEL_74;
      *(_QWORD *)&iid.Data1 = WindowsGetStringRawBuffer(string, 0);
      CuratedTileCollectionTransformerTelemetry::ResurrectingDuplicateTileInStart<unsigned short const *>(&iid);
    }
    if ( v42 )
    {
LABEL_42:
      v12 = v48;
      v13 = DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::GetLayoutId(v22, &v68);
      DataStoreCache::CuratedTileCollectionTransformer::CuratedRoot::DeleteTile(v12, v13);
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::BeginBatchUpdate(v22, &v54);
      std::wstring::wstring(&v65, L"graveyard_collectionId");
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(v22, &v65);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v65);
      std::wstring::wstring(&v65, L"graveyard_parentId");
      DataStoreCache::CuratedTileCollectionTransformer::CuratedTile::RemoveCustomProperty(v22, &v65);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v65);
      v16 = (_QWORD *)std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
                        v59,
                        &v54,
                        v14,
                        v15);
      *(_QWORD *)&iid.Data1 = v16;
      (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v16 + 8LL))(*v16, v60);
      v4 |= 4u;
      v17 = (std::_Ref_count_base *)v16[1];
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(v60);
      if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
      {
        v18 = v61;
        if ( v62 > 7 )
          v18 = (_QWORD *)v61[0];
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0zz_EventWriteTransfer(
          v20,
          CuratedTileCollectionTransformer_UTMIntregation_TileResurrected,
          StringRawBuffer,
          v18);
      }
      if ( v55 )
        std::_Ref_count_base::_Decref(v55);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      v3 = v53;
      goto LABEL_5;
    }
LABEL_74:
    v34 = (const OLECHAR *)lpsz;
    if ( lpsz[3] > (LPCOLESTR)7 )
      v34 = lpsz[0];
    iid = GUID_NULL;
    IIDFromString(v34, &iid);
    v66 = iid;
    v36 = std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
            v58,
            &v50,
            v35,
            *(_QWORD *)(*(_QWORD *)v47 + 304LL));
    v39 = v37(v38, v36, &v66);
    v27 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v39,
        v41);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
      goto LABEL_41;
    }
    v40 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *))(*(_QWORD *)v31 + 216LL))(v31);
    v27 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26A,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectionmanagement\\lib\\curatedtilecollectionmanager.cpp",
        (const char *)(unsigned int)v40,
        v41);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v47);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(lpsz);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v61);
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>(v56);
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
LABEL_41:
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
      return (unsigned int)v27;
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
                           v11);
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
