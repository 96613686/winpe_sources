# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Win8SimpleLayoutConverter::ResolveAppIdsInLayout(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutRoot>)

- ea: `0x18016fdb8`
- end: `0x180170393`
- name: `?ResolveAppIdsInLayout@Win8SimpleLayoutConverter@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJV?$shared_ptr@ULayoutRoot@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@Z`
- size: `1499`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18016fc40`

## callees

- `0x18000b5f0`
- `0x18000befc`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001aca4`
- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x180060178`
- `0x18007ae80`
- `0x180085590`
- `0x18016ee50`
- `0x18016fdb8`
- `0x18017039c`
- `0x180170780`
- `0x180170800`
- `0x180170868`
- `0x18017088c`
- `0x18017099c`
- `0x180170b2c`
- `0x180170f00`
- `0x18017a918`
- `0x18017cee8`
- `0x18017cf20`
- `0x180201e50`
- `0x180221014`
- `0x18023a7dc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801701aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801701aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ffd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180170052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017023c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801702c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ffd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180170052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017023c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801702c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017028d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017028d`

## string_xrefs

- `0x18016ff13`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`
- `0x18016ffff`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`
- `0x18017009d`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`
- `0x1801700c6`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`
- `0x18017026a`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`
- `0x1801702b2`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\win8layoutconverter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Win8SimpleLayoutConverter::ResolveAppIdsInLayout(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 **v5; // rdi
  __int64 *v6; // rbx
  std::_Ref_count_base *v7; // rcx
  _QWORD *Tiles; // rax
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile **v10; // r13
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile **v11; // rax
  _QWORD *TileIdentifier; // rax
  int v13; // eax
  int v14; // r12d
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rsi
  int v18; // eax
  bool v19; // si
  __int64 v20; // r9
  __int64 i; // rsi
  __int64 v22; // r14
  _QWORD *v23; // rax
  const WCHAR *p_lpString2; // r8
  const WCHAR *v25; // rcx
  char v26; // si
  struct _GUID *UniqueId; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rsi
  int v31; // eax
  const char *StringRawBuffer; // rax
  const struct _GUID *v33; // rsi
  struct _GUID *v34; // r14
  const char *v35; // r9
  std::_Ref_count_base *v36; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-188h]
  bool v38; // [rsp+30h] [rbp-178h]
  char v39[3]; // [rsp+31h] [rbp-177h] BYREF
  unsigned int v40; // [rsp+34h] [rbp-174h] BYREF
  HSTRING v41; // [rsp+38h] [rbp-170h] BYREF
  HSTRING string; // [rsp+40h] [rbp-168h] BYREF
  __int64 v43; // [rsp+48h] [rbp-160h] BYREF
  __int64 v44; // [rsp+50h] [rbp-158h] BYREF
  char v45[8]; // [rsp+58h] [rbp-150h] BYREF
  char v46[8]; // [rsp+60h] [rbp-148h] BYREF
  char v47[8]; // [rsp+68h] [rbp-140h] BYREF
  char v48[8]; // [rsp+70h] [rbp-138h] BYREF
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile **v49; // [rsp+78h] [rbp-130h] BYREF
  std::_Ref_count_base *v50; // [rsp+80h] [rbp-128h]
  _QWORD *v51; // [rsp+88h] [rbp-120h]
  _QWORD *v52; // [rsp+90h] [rbp-118h]
  __int128 v53; // [rsp+98h] [rbp-110h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-100h]
  char v55[8]; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-E8h] BYREF
  struct _GUID *v58[3]; // [rsp+D0h] [rbp-D8h] BYREF
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile **v59; // [rsp+E8h] [rbp-C0h] BYREF
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile **v60; // [rsp+F0h] [rbp-B8h]
  __int128 v61; // [rsp+100h] [rbp-A8h]
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutGroup *v62; // [rsp+110h] [rbp-98h] BYREF
  std::_Ref_count_base *v63; // [rsp+118h] [rbp-90h]
  char v64[8]; // [rsp+120h] [rbp-88h] BYREF
  std::_Ref_count_base *v65; // [rsp+128h] [rbp-80h]
  HSTRING_HEADER lpString2; // [rsp+130h] [rbp-78h] BYREF
  unsigned __int64 v67; // [rsp+148h] [rbp-60h]
  struct _GUID v68; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v2 = a2;
  v51 = a2;
  v52 = a2;
  v3 = 0;
  v40 = 0;
  DesktopTilesData::DesktopTilesData((DesktopTilesData *)v55);
  v4 = *(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutRoot::GetGroups(
                    *v2,
                    &v49);
  if ( v50 )
    std::_Ref_count_base::_Decref(v50);
  v5 = *(__int64 ***)(v4 + 8);
  v6 = *v5;
  while ( 1 )
  {
    if ( v6 == (__int64 *)v5 )
    {
      std::vector<std::tuple<std::wstring,_GUID>>::_Tidy(&v56);
      v7 = (std::_Ref_count_base *)v2[1];
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
      return 0;
    }
    v61 = *((_OWORD *)v6 + 1);
    std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
      &v62,
      v6 + 4);
    std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(v58);
    Tiles = (_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutGroup::GetTiles(
                        v62,
                        v64);
    try
    {
      WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetValues<_GUID,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::hashGUIDStartLayout,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>>>,std::unordered_map>(
        &v59,
        *Tiles);
      if ( v65 )
        std::_Ref_count_base::_Decref(v65);
      v10 = v59;
      v11 = v60;
      v49 = v60;
LABEL_12:
      if ( v10 == v11 )
      {
        std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::~vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v59);
        v33 = v58[0];
        v34 = v58[1];
        while ( v33 != v34 )
          WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutGroup::RemoveTile(v62, v33++);
        std::vector<bond::GUID>::_Tidy(v58);
        if ( v63 )
          std::_Ref_count_base::_Decref(v63);
        v6 = (__int64 *)*v6;
        v2 = v51;
        continue;
      }
      v40 = 0;
      TileIdentifier = (_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                                   *v10,
                                   v45);
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*TileIdentifier + 48LL))(
              *TileIdentifier,
              &v40);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
      v38 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v45);
      v43 = 0;
      v67 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &lpString2,
        L"Windows.Internal.StateRepository.Application",
        0x2Du,
        0x2Cu);
      v14 = v3 | 1;
      if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
                  v67,
                  &v43) >= 0
        && v40 == 1 )
      {
        v15 = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                *v10,
                v46);
        wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
          v15,
          &v44);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v46);
        string = 0;
        v16 = v44;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v18 = v17(v16, &string);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
            (const char *)(unsigned int)v18,
            bIgnoreCase);
        v39[0] = 0;
        if ( (*(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v43 + 56LL))(v43, string, v39) < 0 )
        {
          v19 = 0;
        }
        else
        {
          v19 = v39[0] != 0;
          v38 = v39[0] != 0;
        }
        v3 = v14 & 0xFFFFFFFE;
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
        if ( !v19 )
        {
LABEL_25:
          if ( v40 != 2 )
            goto LABEL_42;
          if ( v55[0] )
          {
            v20 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
              (const char *)0x80004001LL,
              bIgnoreCase);
            v20 = 2147500033LL;
          }
          if ( (int)v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x60,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
              (const char *)v20,
              bIgnoreCase);
          v53 = 0;
          v54 = 0;
          std::vector<std::tuple<std::wstring,_GUID>>::_Construct_n<std::tuple<std::wstring,_GUID> * const &,std::tuple<std::wstring,_GUID> * const &>(
            &v53,
            0xAAAAAAAAAAAAAAABuLL * ((v57 - v56) >> 4),
            &v56,
            &v57);
          v22 = *((_QWORD *)&v53 + 1);
          for ( i = v53; i != v22; i += 48 )
          {
            v23 = (_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                              *v10,
                              v47);
            WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetAumid(&lpString2, *v23);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v47);
            p_lpString2 = (const WCHAR *)&lpString2;
            if ( v67 > 7 )
              p_lpString2 = (const WCHAR *)lpString2.Reserved.Reserved1;
            v25 = (const WCHAR *)(i + 16);
            if ( *(_QWORD *)(i + 40) > 7u )
              v25 = *(const WCHAR **)v25;
            if ( CompareStringOrdinal(v25, -1, p_lpString2, -1, 0) == 2 )
            {
              v26 = 1;
              std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&lpString2);
              goto LABEL_41;
            }
            std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&lpString2);
          }
          v26 = v38;
LABEL_41:
          v3 |= 2u;
          std::vector<std::tuple<std::wstring,_GUID>>::_Tidy(&v53);
          if ( !v26 )
          {
LABEL_42:
            UniqueId = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetUniqueId(
                         *v10,
                         &v68);
            std::vector<_GUID>::push_back(v58, UniqueId);
            v41 = 0;
            v28 = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                    *v10,
                    v48);
            v29 = *(_QWORD *)v28;
            v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v28 + 56LL);
            WindowsDeleteString(v41);
            v41 = 0;
            v31 = v30(v29, &v41);
            if ( v31 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x74,
                (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
                (const char *)(unsigned int)v31,
                bIgnoreCase);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v48);
            StringRawBuffer = (const char *)WindowsGetStringRawBuffer(v41, 0);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x75,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
              (const char *)0x8002802BLL,
              (int)"Tile doesn't exist on system: %ls",
              StringRawBuffer);
            WindowsDeleteString(v41);
            v41 = 0;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        v10 += 2;
        v11 = v49;
        goto LABEL_12;
      }
      v3 = v14 & 0xFFFFFFFE;
      goto LABEL_25;
    }
    catch ( ... )
    {
      v40 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x7F,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\win8layoutconverter.cpp",
              v35);
      v36 = (std::_Ref_count_base *)v52[1];
      if ( v36 )
        std::_Ref_count_base::_Decref(v36);
      return v40;
    }
  }
}

```

## disassembly

```asm
0x18016fdb8  push    rbx
0x18016fdba  push    rsi
0x18016fdbb  push    rdi
0x18016fdbc  push    r12
0x18016fdbe  push    r13
0x18016fdc0  push    r14
0x18016fdc2  sub     rsp, 178h
0x18016fdc9  mov     rax, cs:__security_cookie
0x18016fdd0  xor     rax, rsp
0x18016fdd3  mov     [rsp+1A8h+var_48], rax
0x18016fddb  mov     rsi, rdx
0x18016fdde  mov     [rsp+1A8h+var_120], rdx
0x18016fde6  mov     [rsp+1A8h+var_118], rdx
0x18016fdee  xor     r12d, r12d
0x18016fdf1  mov     [rsp+1A8h+var_174], r12d
0x18016fdf6  lea     rcx, [rsp+1A8h+var_F8]; this
0x18016fdfe  call    ??0DesktopTilesData@@QEAA@XZ; DesktopTilesData::DesktopTilesData(void)
0x18016fe03  nop
0x18016fe04  lea     rdx, [rsp+1A8h+var_130]
0x18016fe09  mov     rcx, [rsi]
0x18016fe0c  call    ?GetGroups@LayoutRoot@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?AV?$shared_ptr@$$CBV?$unordered_map@U_GUID@@V?$shared_ptr@VLayoutGroup@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@UhashGUIDStartLayout@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VLayoutGroup@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@@3@@std@@@std@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutRoot::GetGroups(void)
0x18016fe11  mov     rdi, [rax]
0x18016fe14  mov     rcx, [rsp+1A8h+var_128]; this
0x18016fe1c  test    rcx, rcx
0x18016fe1f  jz      short loc_18016FE26
0x18016fe21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18016fe26  mov     rdi, [rdi+8]
0x18016fe2a  mov     rbx, [rdi]
0x18016fe2d  cmp     rbx, rdi
0x18016fe30  jnz     short loc_18016FE55
0x18016fe32  lea     rcx, [rsp+1A8h+var_F0]
0x18016fe3a  call    ?_Tidy@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@AEAAXXZ; std::vector<std::tuple<std::wstring,_GUID>>::_Tidy(void)
0x18016fe3f  nop
0x18016fe40  mov     rcx, [rsi+8]; this
0x18016fe44  test    rcx, rcx
0x18016fe47  jz      short loc_18016FE4E
0x18016fe49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18016fe4e  xor     eax, eax
0x18016fe50  jmp     loc_180170372
0x18016fe55  movups  xmm0, xmmword ptr [rbx+10h]
0x18016fe59  movdqu  [rsp+1A8h+var_A8], xmm0
0x18016fe62  lea     rdx, [rbx+20h]
0x18016fe66  lea     rcx, [rsp+1A8h+var_98]
0x18016fe6e  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x18016fe73  nop
0x18016fe74  lea     rcx, [rsp+1A8h+var_D8]
0x18016fe7c  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x18016fe81  nop
0x18016fe82  lea     rdx, [rsp+1A8h+var_88]
0x18016fe8a  mov     rcx, [rsp+1A8h+var_98]
0x18016fe92  call    ?GetTiles@LayoutGroup@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?AV?$shared_ptr@$$CBV?$unordered_map@U_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@UhashGUIDStartLayout@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@@3@@std@@@std@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutGroup::GetTiles(void)
0x18016fe97  nop
0x18016fe98  mov     rdx, [rax]
0x18016fe9b  lea     rcx, [rsp+1A8h+var_C0]
0x18016fea3  call    ??$GetValues@U_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@UhashGUIDStartLayout@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@@3@Vunordered_map@3@@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@YA?AV?$vector@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@V?$allocator@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@2@@std@@AEBV?$unordered_map@U_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@UhashGUIDStartLayout@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@@3@@5@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetValues<_GUID,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::hashGUIDStartLayout,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>>>,std::unordered_map>(std::unordered_map<_GUID,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::hashGUIDStartLayout,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>>>> const &)
0x18016fea8  nop
0x18016fea9  mov     rcx, [rsp+1A8h+var_80]; this
0x18016feb1  test    rcx, rcx
0x18016feb4  jz      short loc_18016FEBB
0x18016feb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18016febb  mov     r13, [rsp+1A8h+var_C0]
0x18016fec3  mov     rax, [rsp+1A8h+var_B8]
0x18016fecb  mov     [rsp+1A8h+var_130], rax
0x18016fed0  cmp     r13, rax
0x18016fed3  jz      loc_1801702F0
0x18016fed9  mov     [rsp+1A8h+var_174], 0
0x18016fee1  lea     rdx, [rsp+1A8h+var_150]
0x18016fee6  mov     rcx, [r13+0]
0x18016feea  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18016feef  nop
0x18016fef0  mov     rcx, [rax]
0x18016fef3  mov     rax, [rcx]
0x18016fef6  lea     rdx, [rsp+1A8h+var_174]
0x18016fefb  mov     rax, [rax+30h]
0x18016feff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ff04  mov     rcx, [rsp+1A8h]; this
0x18016ff0c  test    eax, eax
0x18016ff0e  jns     short loc_18016FF25
0x18016ff10  mov     r9d, eax; char *
0x18016ff13  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18016ff1a  mov     edx, 4Ch ; 'L'; void *
0x18016ff1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18016ff25  xor     sil, sil
0x18016ff28  mov     [rsp+1A8h+var_178], sil
0x18016ff2d  lea     rcx, [rsp+1A8h+var_150]; void *
0x18016ff32  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016ff37  mov     [rsp+1A8h+var_160], 0
0x18016ff40  mov     [rsp+1A8h+var_60], 0
0x18016ff4c  mov     r9d, 2Ch ; ','; unsigned int
0x18016ff52  lea     r8d, [r9+1]; unsigned int
0x18016ff56  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18016ff5d  lea     rcx, [rsp+1A8h+lpString2]; hstringHeader
0x18016ff65  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18016ff6a  or      r12d, 1
0x18016ff6e  lea     rdx, [rsp+1A8h+var_160]
0x18016ff73  mov     rcx, [rsp+1A8h+var_60]
0x18016ff7b  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x18016ff80  test    eax, eax
0x18016ff82  js      loc_180170076
0x18016ff88  cmp     [rsp+1A8h+var_174], 1
0x18016ff8d  jnz     loc_180170076
0x18016ff93  lea     rdx, [rsp+1A8h+var_148]
0x18016ff98  mov     rcx, [r13+0]
0x18016ff9c  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18016ffa1  nop
0x18016ffa2  lea     rdx, [rsp+1A8h+var_158]
0x18016ffa7  mov     rcx, rax
0x18016ffaa  call    ??$query@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(void)
0x18016ffaf  nop
0x18016ffb0  lea     rcx, [rsp+1A8h+var_148]; void *
0x18016ffb5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18016ffba  mov     [rsp+1A8h+string], 0
0x18016ffc3  mov     r14, [rsp+1A8h+var_158]
0x18016ffc8  mov     rax, [r14]
0x18016ffcb  mov     rsi, [rax+30h]
0x18016ffcf  xor     ecx, ecx; string
0x18016ffd1  call    cs:__imp_WindowsDeleteString
0x18016ffd7  mov     [rsp+1A8h+string], 0
0x18016ffe0  lea     rdx, [rsp+1A8h+string]
0x18016ffe5  mov     rcx, r14
0x18016ffe8  mov     rax, rsi
0x18016ffeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016fff0  mov     rcx, [rsp+1A8h]; this
0x18016fff8  test    eax, eax
0x18016fffa  jns     short loc_180170010
0x18016fffc  mov     r9d, eax; char *
0x18016ffff  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180170006  mov     edx, 54h ; 'T'; void *
0x18017000b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180170010  mov     [rsp+1A8h+var_177], 0
0x180170015  mov     rcx, [rsp+1A8h+var_160]
0x18017001a  mov     rax, [rcx]
0x18017001d  lea     r8, [rsp+1A8h+var_177]
0x180170022  mov     rdx, [rsp+1A8h+string]
0x180170027  mov     rax, [rax+38h]
0x18017002b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180170030  test    eax, eax
0x180170032  js      short loc_180170044
0x180170034  cmp     [rsp+1A8h+var_177], 0
0x180170039  setnz   sil
0x18017003d  mov     [rsp+1A8h+var_178], sil
0x180170042  jmp     short loc_180170049
0x180170044  mov     sil, [rsp+1A8h+var_178]
0x180170049  and     r12d, 0FFFFFFFEh
0x18017004d  mov     rcx, [rsp+1A8h+string]; string
0x180170052  call    cs:__imp_WindowsDeleteString
0x180170058  mov     [rsp+1A8h+string], 0
0x180170061  lea     rcx, [rsp+1A8h+var_158]; void *
0x180170066  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18017006b  test    sil, sil
0x18017006e  jnz     loc_1801702D8
0x180170074  jmp     short loc_18017007A
0x180170076  and     r12d, 0FFFFFFFEh
0x18017007a  cmp     [rsp+1A8h+var_174], 2
0x18017007f  jnz     loc_1801701F4
0x180170085  cmp     [rsp+1A8h+var_F8], 0
0x18017008d  jnz     short loc_1801700B6
0x18017008f  mov     rcx, [rsp+1A8h]; this
0x180170097  mov     r9d, 80004001h; char *
0x18017009d  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801700a4  mov     edx, 2Eh ; '.'; void *
0x1801700a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801700ae  mov     r9d, 80004001h
0x1801700b4  jmp     short loc_1801700B9
0x1801700b6  xor     r9d, r9d; char *
0x1801700b9  mov     rcx, [rsp+1A8h]; this
0x1801700c1  test    r9d, r9d
0x1801700c4  jns     short loc_1801700D7
0x1801700c6  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801700cd  mov     edx, 60h ; '`'; void *
0x1801700d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801700d7  xorps   xmm0, xmm0
0x1801700da  movdqu  [rsp+1A8h+var_110], xmm0
0x1801700e3  mov     [rsp+1A8h+var_100], 0
0x1801700ef  mov     rdx, [rsp+1A8h+var_E8]
0x1801700f7  sub     rdx, [rsp+1A8h+var_F0]
0x1801700ff  sar     rdx, 4
0x180170103  mov     rax, 0AAAAAAAAAAAAAAABh
0x18017010d  imul    rdx, rax
0x180170111  lea     r9, [rsp+1A8h+var_E8]
0x180170119  lea     r8, [rsp+1A8h+var_F0]
0x180170121  lea     rcx, [rsp+1A8h+var_110]
0x180170129  call    ??$_Construct_n@AEBQEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@AEBQEAV12@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@AEAAX_KAEBQEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@1@1@Z; std::vector<std::tuple<std::wstring,_GUID>>::_Construct_n<std::tuple<std::wstring,_GUID> * const &,std::tuple<std::wstring,_GUID> * const &>(unsigned __int64,std::tuple<std::wstring,_GUID> * const &,std::tuple<std::wstring,_GUID> * const &)
0x18017012e  nop
0x18017012f  mov     rsi, qword ptr [rsp+1A8h+var_110]
0x180170137  mov     r14, qword ptr [rsp+1A8h+var_110+8]
0x18017013f  cmp     rsi, r14
0x180170142  jz      loc_1801701D5
0x180170148  lea     rdx, [rsp+1A8h+var_140]
0x18017014d  mov     rcx, [r13+0]
0x180170151  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x180170156  nop
0x180170157  mov     rdx, [rax]
0x18017015a  lea     rcx, [rsp+1A8h+lpString2]
0x180170162  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__GetAumid
0x180170167  nop
0x180170168  lea     rcx, [rsp+1A8h+var_140]; void *
0x18017016d  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180170172  lea     r8, [rsp+1A8h+lpString2]
0x18017017a  cmp     [rsp+1A8h+var_60], 7
0x180170183  cmova   r8, qword ptr [rsp+1A8h+lpString2]; lpString2
0x18017018c  lea     rcx, [rsi+10h]
0x180170190  cmp     qword ptr [rsi+28h], 7
0x180170195  jbe     short loc_18017019A
0x180170197  mov     rcx, [rcx]; lpString1
0x18017019a  mov     [rsp+1A8h+bIgnoreCase], 0; bIgnoreCase
0x1801701a2  or      eax, 0FFFFFFFFh
0x1801701a5  mov     r9d, eax; cchCount2
0x1801701a8  mov     edx, eax; cchCount1
0x1801701aa  call    cs:__imp_CompareStringOrdinal
0x1801701b0  lea     rcx, [rsp+1A8h+lpString2]; void *
0x1801701b8  cmp     eax, 2
0x1801701bb  jnz     short loc_1801701C7
0x1801701bd  mov     sil, 1
0x1801701c0  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1801701c5  jmp     short loc_1801701DA
0x1801701c7  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1801701cc  add     rsi, 30h ; '0'
0x1801701d0  jmp     loc_18017013F
0x1801701d5  mov     sil, [rsp+1A8h+var_178]
0x1801701da  or      r12d, 2
0x1801701de  lea     rcx, [rsp+1A8h+var_110]
0x1801701e6  call    ?_Tidy@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@@std@@AEAAXXZ; std::vector<std::tuple<std::wstring,_GUID>>::_Tidy(void)
0x1801701eb  test    sil, sil
0x1801701ee  jnz     loc_1801702D8
0x1801701f4  lea     rdx, [rsp+1A8h+var_58]; retstr
0x1801701fc  mov     rcx, [r13+0]; this
0x180170200  call    ?GetUniqueId@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?AU_GUID@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetUniqueId(void)
0x180170205  mov     rdx, rax
0x180170208  lea     rcx, [rsp+1A8h+var_D8]
0x180170210  call    ?push_back@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAX$$QEAU_GUID@@@Z; std::vector<_GUID>::push_back(_GUID &&)
0x180170215  mov     [rsp+1A8h+var_170], 0
0x18017021e  lea     rdx, [rsp+1A8h+var_138]
0x180170223  mov     rcx, [r13+0]
0x180170227  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18017022c  nop
0x18017022d  mov     r14, [rax]
0x180170230  mov     rax, [r14]
0x180170233  mov     rsi, [rax+38h]
0x180170237  mov     rcx, [rsp+1A8h+var_170]; string
0x18017023c  call    cs:__imp_WindowsDeleteString
0x180170242  mov     [rsp+1A8h+var_170], 0
0x18017024b  lea     rdx, [rsp+1A8h+var_170]
0x180170250  mov     rcx, r14
0x180170253  mov     rax, rsi
0x180170256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017025b  mov     rcx, [rsp+1A8h]; this
0x180170263  test    eax, eax
0x180170265  jns     short loc_18017027C
0x180170267  mov     r9d, eax; char *
0x18017026a  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180170271  mov     edx, 74h ; 't'; void *
0x180170276  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017027c  lea     rcx, [rsp+1A8h+var_138]; void *
0x180170281  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180170286  xor     edx, edx; length
0x180170288  mov     rcx, [rsp+1A8h+var_170]; string
0x18017028d  call    cs:__imp_WindowsGetStringRawBuffer
0x180170293  mov     rcx, [rsp+1A8h]; this
0x18017029b  mov     [rsp+1A8h+var_180], rax; char *
0x1801702a0  lea     rax, aTileDoesnTExis; "Tile doesn't exist on system: %ls"
0x1801702a7  mov     qword ptr [rsp+1A8h+bIgnoreCase], rax; int
0x1801702ac  mov     r9d, 8002802Bh; char *
0x1801702b2  lea     r8, aShellcommonShe_156; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801702b9  mov     edx, 75h ; 'u'; void *
0x1801702be  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801702c3  nop
0x1801702c4  mov     rcx, [rsp+1A8h+var_170]; string
0x1801702c9  call    cs:__imp_WindowsDeleteString
0x1801702cf  mov     [rsp+1A8h+var_170], 0
0x1801702d8  lea     rcx, [rsp+1A8h+var_160]
0x1801702dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801702e2  add     r13, 10h
0x1801702e6  mov     rax, [rsp+1A8h+var_130]
0x1801702eb  jmp     loc_18016FED0
0x1801702f0  lea     rcx, [rsp+1A8h+var_C0]
0x1801702f8  call    ??1?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::~vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x1801702fd  mov     rsi, [rsp+1A8h+var_D8]
0x180170305  mov     r14, [rsp+1A8h+var_D0]
0x18017030d  cmp     rsi, r14
0x180170310  jz      short loc_180170328
0x180170312  mov     rdx, rsi; struct _GUID *
0x180170315  mov     rcx, [rsp+1A8h+var_98]; this
0x18017031d  call    ?RemoveTile@LayoutGroup@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAAXAEBU_GUID@@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutGroup::RemoveTile(_GUID const &)
0x180170322  add     rsi, 10h
0x180170326  jmp     short loc_18017030D
0x180170328  lea     rcx, [rsp+1A8h+var_D8]
0x180170330  call    ?_Tidy@?$vector@UGUID@bond@@V?$allocator@UGUID@bond@@@std@@@std@@AEAAXXZ; std::vector<bond::GUID>::_Tidy(void)
0x180170335  nop
0x180170336  mov     rcx, [rsp+1A8h+var_90]; this
0x18017033e  test    rcx, rcx
0x180170341  jz      short loc_180170348
0x180170343  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180170348  mov     rbx, [rbx]
0x18017034b  mov     rsi, [rsp+1A8h+var_120]
0x180170353  jmp     loc_18016FE2D
0x180170358  mov     rax, [rsp+1A8h+var_118]
0x180170360  mov     rcx, [rax+8]; this
0x180170364  test    rcx, rcx
0x180170367  jz      short loc_18017036E
  ... truncated ...
```
