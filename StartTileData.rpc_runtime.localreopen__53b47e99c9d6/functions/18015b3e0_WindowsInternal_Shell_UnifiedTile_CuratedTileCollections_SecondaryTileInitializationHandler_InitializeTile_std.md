# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::InitializeTile(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>)

- ea: `0x18015b3e0`
- end: `0x18015c0a9`
- name: `?InitializeTile@SecondaryTileInitializationHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@UEAAXV?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@Z`
- size: `3273`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000befc`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x1800756e4`
- `0x18007ae80`
- `0x180087bd8`
- `0x18010aa74`
- `0x1801238dc`
- `0x18015b388`
- `0x18015b3e0`
- `0x18015c0b0`
- `0x18015c0d4`
- `0x18015c754`
- `0x18015c778`
- `0x18015cfa4`
- `0x18015d8f8`
- `0x18015da80`
- `0x18015dad8`
- `0x180161204`
- `0x18017cee8`
- `0x18017cf20`
- `0x18017e110`
- `0x18017e464`
- `0x18017fcb0`
- `0x1801a04b0`
- `0x1801c4c74`
- `0x1801d43b0`
- `0x180201e50`
- `0x180220cfc`
- `0x18035c1ec`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18015b701`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18015b701`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015bb5f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015bb5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b62e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015c00a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015c025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b62e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015c00a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015c025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015b69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015b97e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015b69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015b97e`

## string_xrefs

- `0x18015b4a0`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18015b53d`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18015b584`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`
- `0x18015b5ac`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\secondarytileinitializationhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
void __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::InitializeTile(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // esi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 TileIdentifier; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  int v17; // eax
  PCWSTR StringRawBuffer; // rax
  WCHAR *v19; // rax
  WCHAR *v20; // r8
  __int64 v21; // rcx
  char IsSpartanOrAnaheimEdge; // bl
  __int64 v23; // rcx
  int v24; // esi
  const WCHAR *v25; // r12
  __int64 *v27; // rbx
  __int64 (__fastcall *v28)(__int64 *, _QWORD); // rdi
  const WCHAR *v29; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rbx
  __int64 v33; // rdi
  const WCHAR **DisplayName; // rax
  const WCHAR *v35; // rax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, int *); // rbx
  int v40; // eax
  PCWSTR v41; // rax
  _QWORD *v42; // rdx
  char v43; // al
  __int64 v44; // rbx
  int v45; // esi
  char v46; // bl
  __int64 ForegroundText; // rax
  const WCHAR *v48; // rcx
  int v49; // ebx
  int v50; // eax
  _QWORD *v51; // rdx
  __int64 v52; // rbx
  _QWORD *v53; // rdx
  __int64 v54; // rbx
  const WCHAR *v55; // rdx
  __int64 v56; // rbx
  __int64 v57; // rdx
  int v58; // eax
  __int64 v59; // rdx
  int v60; // eax
  _QWORD *BackgroundColor; // rax
  int v62; // esi
  char v63; // bl
  __int64 v64; // rbx
  __int64 v65; // rdi
  unsigned int v66; // eax
  int v67; // eax
  int v68; // eax
  __int64 v69; // rdx
  int v70; // eax
  std::_Ref_count_base *v71; // rcx
  __int64 v72; // rax
  const char *v73; // rdx
  __int64 v74; // rcx
  int v75; // ecx
  const char *v76; // rax
  int lpDestStr; // [rsp+20h] [rbp-198h]
  int lpDestStra; // [rsp+20h] [rbp-198h]
  int lpDestStrb; // [rsp+20h] [rbp-198h]
  int lpDestStrc; // [rsp+20h] [rbp-198h]
  char v81; // [rsp+40h] [rbp-178h]
  int v82[2]; // [rsp+48h] [rbp-170h] BYREF
  __int64 *v83; // [rsp+50h] [rbp-168h] BYREF
  HSTRING string; // [rsp+58h] [rbp-160h] BYREF
  HSTRING v85; // [rsp+60h] [rbp-158h] BYREF
  _QWORD v86[2]; // [rsp+68h] [rbp-150h] BYREF
  const WCHAR *v87; // [rsp+78h] [rbp-140h] BYREF
  std::_Ref_count_base *v88; // [rsp+80h] [rbp-138h]
  _QWORD *v89; // [rsp+88h] [rbp-130h] BYREF
  std::_Ref_count_base *v90; // [rsp+90h] [rbp-128h]
  _QWORD *v91; // [rsp+98h] [rbp-120h] BYREF
  std::_Ref_count_base *v92; // [rsp+A0h] [rbp-118h]
  __int64 v93; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-108h] BYREF
  _QWORD *v95; // [rsp+B8h] [rbp-100h] BYREF
  std::_Ref_count_base *v96; // [rsp+C0h] [rbp-F8h]
  __int64 v97; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v98; // [rsp+D0h] [rbp-E8h] BYREF
  std::_Ref_count_base *v99; // [rsp+D8h] [rbp-E0h]
  _QWORD *v100; // [rsp+E0h] [rbp-D8h]
  std::exception *v101[2]; // [rsp+E8h] [rbp-D0h] BYREF
  char v102; // [rsp+F8h] [rbp-C0h]
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-B8h] BYREF
  __int64 v104; // [rsp+118h] [rbp-A0h]
  WCHAR DestStr[4]; // [rsp+120h] [rbp-98h] BYREF
  int cchSrc; // [rsp+130h] [rbp-88h]
  unsigned __int64 v107; // [rsp+138h] [rbp-80h]
  _BYTE v108[16]; // [rsp+140h] [rbp-78h] BYREF
  const char *v109; // [rsp+150h] [rbp-68h]
  int v110; // [rsp+158h] [rbp-60h]
  int v111; // [rsp+15Ch] [rbp-5Ch]
  int v112; // [rsp+160h] [rbp-58h] BYREF
  std::_Ref_count_base *v113; // [rsp+168h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v100 = a2;
  v4 = 0;
  LODWORD(v86[0]) = 0;
  if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
  {
    v5 = (_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::ToLoggingString(
                     *a2,
                     v108);
    v4 = 1;
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    McTemplateU0z_EventWriteTransfer(
      &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
      SecondaryTileInitialization_InitializeSecondaryTile_Start,
      v5);
  }
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v108);
  }
  v101[1] = (std::exception *)a1;
  v102 = 1;
  try
  {
    if ( (unsigned int)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(*a2) != 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytileini"
                      "tializationhandler.cpp",
        (const char *)0x80070057LL,
        lpDestStr);
    v6 = (_QWORD *)std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
                     &v91,
                     a2);
    if ( !WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::DoesSecondaryTileExist(
            a1,
            v6) )
    {
      TileIdentifier = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                         *a2,
                         v86);
      wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
        TileIdentifier,
        &v94);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v86);
      string = 0;
      v8 = v94;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v94 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v10 = v9(v8, &string);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v10,
          lpDestStr);
      if ( *(_QWORD *)(a1 + 64) )
      {
        wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(v86);
        v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD))(*(_QWORD *)v86[0] + 416LL))(
                v86[0],
                string,
                *(_QWORD *)(a1 + 64));
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5C,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytil"
                          "einitializationhandler.cpp",
            (const char *)(unsigned int)v11,
            lpDestStr);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v86);
      }
      v83 = 0;
      v12 = **(_QWORD **)(a1 + 16);
      v104 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.UI.StartScreen.SecondaryTile",
        0x25u,
        0x24u);
      v13 = Windows::Foundation::ActivateInstanceAsUser<Windows::UI::StartScreen::ISecondaryTile>(v104, v12, &v83);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x60,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v13,
          lpDestStr);
      v85 = 0;
      v14 = v94;
      v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v94 + 56LL);
      WindowsDeleteString(0);
      v85 = 0;
      v16 = v15(v14, &v85);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v16,
          lpDestStr);
      v17 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(*v83 + 48))(v83, v85);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v17,
          lpDestStr);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(DestStr, StringRawBuffer);
      if ( v107 > 7 )
      {
        v19 = *(WCHAR **)DestStr;
        v20 = *(WCHAR **)DestStr;
      }
      else
      {
        v19 = DestStr;
        v20 = DestStr;
      }
      if ( !LCMapStringW(0x7Fu, 0x200u, v20, cchSrc, v19, cchSrc) )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)0x80004005LL,
          lpDestStra);
      std::wstring::operator std::basic_string_view<unsigned short>(DestStr, &v91);
      IsSpartanOrAnaheimEdge = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::IsSpartanOrAnaheimEdge(
                                 v21,
                                 &v91);
      v81 = IsSpartanOrAnaheimEdge;
      v23 = *(_QWORD *)(*a2 + 32LL);
      if ( v23 )
        DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetArguments(v23, &v98);
      else
        std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
          &v98,
          *a2 + 104LL);
      v24 = v4 | 0x40;
      LODWORD(v86[0]) = v24;
      v25 = (const WCHAR *)v98;
      if ( !v98 && IsSpartanOrAnaheimEdge )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)0x8000FFFFLL,
          lpDestStra);
      v27 = v83;
      v28 = *(__int64 (__fastcall **)(__int64 *, _QWORD))(*v83 + 64);
      if ( v98 )
      {
        if ( *(_QWORD *)(v98 + 24) <= 7u )
          v29 = (const WCHAR *)v98;
        else
          v29 = *(const WCHAR **)v98;
      }
      else
      {
        v29 = &String1;
      }
      v87 = v29;
      v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v87);
      v31 = v28(v27, *(_QWORD *)(v30 + 24));
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v31,
          lpDestStra);
      v32 = v83;
      v33 = *v83;
      if ( *(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetDisplayName(
                        *a2,
                        &v89) )
      {
        DisplayName = (const WCHAR **)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetDisplayName(
                                        *a2,
                                        &v91);
        v24 |= 2u;
        LODWORD(v86[0]) = v24;
        v35 = *DisplayName;
        if ( *((_QWORD *)v35 + 3) > 7u )
          v35 = *(const WCHAR **)v35;
      }
      else
      {
        v35 = &String1;
      }
      v87 = v35;
      v36 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v87) + 24);
      v37 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v33 + 96))(v32, v36);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v37,
          lpDestStra);
      v104 = 0;
      if ( (v24 & 2) != 0 )
      {
        v24 &= ~2u;
        if ( v92 )
          std::_Ref_count_base::_Decref(v92);
      }
      if ( v90 )
        std::_Ref_count_base::_Decref(v90);
      wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTile,wil::err_exception_policy>::query<Windows::UI::StartScreen::ISecondaryTile2>(
        &v83,
        &v97);
      *(_QWORD *)v82 = 0;
      v38 = v97;
      v39 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v97 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v82);
      v40 = v39(v38, v82);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v40,
          lpDestStra);
      if ( v25 )
      {
        if ( *((_QWORD *)v25 + 3) > 7u )
          v25 = *(const WCHAR **)v25;
      }
      else
      {
        v25 = &String1;
      }
      std::wstring::wstring(&v112, v25);
      v41 = WindowsGetStringRawBuffer(v85, 0);
      std::wstring::wstring(&hstringHeader, v41);
      std::wstring::operator std::basic_string_view<unsigned short>(DestStr, &v91);
      WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::GetRelativePath(
        (unsigned int)&v112,
        (unsigned int)v108,
        (unsigned int)&v91,
        (unsigned int)&hstringHeader,
        (__int64)&v112);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v112);
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v91,
        *a2 + 120LL);
      v42 = v91;
      if ( !v91 || (v43 = 0, !v91[2]) )
        v43 = 1;
      if ( v43 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)0x80070057LL,
          lpDestStrb);
      v44 = *(_QWORD *)v82;
      if ( v91[3] > 7u )
        v42 = (_QWORD *)*v91;
      std::wstring::wstring(&hstringHeader, v42);
      std::wstring::operator std::basic_string_view<unsigned short>(DestStr, &v89);
      WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::AddSecondaryTileLogo(
        a1,
        (unsigned int)&v89,
        (unsigned int)&hstringHeader,
        (unsigned int)v108,
        v44,
        1,
        v81);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      v45 = v24 | 4;
      if ( !*(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetForegroundText(
                         *a2,
                         &v95)
        || (v45 |= 8u,
            v46 = 1,
            !*(_QWORD *)(*(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetForegroundText(
                                      *a2,
                                      &v89)
                       + 16LL)) )
      {
        v46 = 0;
      }
      if ( (v45 & 8) != 0 )
      {
        v45 &= ~8u;
        if ( v90 )
          std::_Ref_count_base::_Decref(v90);
      }
      if ( (v45 & 4) != 0 )
      {
        v45 &= ~4u;
        if ( v96 )
          std::_Ref_count_base::_Decref(v96);
      }
      if ( v46 )
      {
        ForegroundText = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetForegroundText(
                           *a2,
                           &v89);
        v48 = *(const WCHAR **)ForegroundText;
        if ( *(_QWORD *)(*(_QWORD *)ForegroundText + 24LL) > 7u )
          v48 = *(const WCHAR **)v48;
        v49 = CompareStringOrdinal(v48, -1, L"dark", -1, 1);
        if ( v90 )
          std::_Ref_count_base::_Decref(v90);
        v50 = (*(__int64 (__fastcall **)(__int64 *, bool))(*v83 + 208))(v83, v49 != 2);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytil"
                          "einitializationhandler.cpp",
            (const char *)(unsigned int)v50,
            lpDestStrc);
      }
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v89,
        *a2 + 152LL);
      v51 = v89;
      if ( v89 && v89[2] )
      {
        v52 = *(_QWORD *)v82;
        if ( v89[3] > 7u )
          v51 = (_QWORD *)*v89;
        std::wstring::wstring(&hstringHeader, v51);
        std::wstring::operator std::basic_string_view<unsigned short>(DestStr, &v95);
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::AddSecondaryTileLogo(
          a1,
          (unsigned int)&v95,
          (unsigned int)&hstringHeader,
          (unsigned int)v108,
          v52,
          0,
          v81);
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      }
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v95,
        *a2 + 184LL);
      v53 = v95;
      if ( v95 && v95[2] )
      {
        v54 = *(_QWORD *)v82;
        if ( v95[3] > 7u )
          v53 = (_QWORD *)*v95;
        std::wstring::wstring(&hstringHeader, v53);
        std::wstring::operator std::basic_string_view<unsigned short>(DestStr, &v87);
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::AddSecondaryTileLogo(
          a1,
          (unsigned int)&v87,
          (unsigned int)&hstringHeader,
          (unsigned int)v108,
          v54,
          2,
          v81);
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      }
      std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(
        &v87,
        *a2 + 136LL);
      v55 = v87;
      if ( v87 && *((_QWORD *)v87 + 2) )
      {
        v56 = *(_QWORD *)v82;
        if ( *((_QWORD *)v87 + 3) > 7u )
          v55 = *(const WCHAR **)v87;
        std::wstring::wstring(&hstringHeader, v55);
        std::wstring::operator std::basic_string_view<unsigned short>(DestStr, v86);
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::AddSecondaryTileLogo(
          a1,
          (unsigned int)v86,
          (unsigned int)&hstringHeader,
          (unsigned int)v108,
          v56,
          3,
          v81);
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      }
      v57 = *a2;
      if ( *(_BYTE *)(*a2 + 298LL) )
      {
        LOBYTE(v57) = *(_BYTE *)(v57 + 299);
        v58 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v82 + 160LL))(*(_QWORD *)v82, v57);
        if ( v58 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x96,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytil"
                          "einitializationhandler.cpp",
            (const char *)(unsigned int)v58,
            lpDestStrc);
      }
      v59 = *a2;
      if ( *(_BYTE *)(*a2 + 300LL) )
      {
        LOBYTE(v59) = *(_BYTE *)(v59 + 301);
        v60 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v82 + 176LL))(*(_QWORD *)v82, v59);
        if ( v60 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9B,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytil"
                          "einitializationhandler.cpp",
            (const char *)(unsigned int)v60,
            lpDestStrc);
      }
      BackgroundColor = (_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetBackgroundColor(
                                    *a2,
                                    &hstringHeader);
      v62 = v45 | 0x10;
      LODWORD(v86[0]) = v62;
      if ( !*BackgroundColor
        || (LOBYTE(v62) = v62 | 0x20,
            v63 = 1,
            !*(_QWORD *)(*(_QWORD *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetBackgroundColor(
                                      *a2,
                                      &v112)
                       + 16LL)) )
      {
        v63 = 0;
      }
      if ( (v62 & 0x20) != 0 )
      {
        LOBYTE(v62) = v62 & 0xDF;
        if ( v113 )
          std::_Ref_count_base::_Decref(v113);
      }
      if ( (v62 & 0x10) != 0 && *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
      if ( v63 )
      {
        v64 = *(_QWORD *)v82;
        v65 = **(_QWORD **)v82;
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetBackgroundColor(
          *a2,
          &hstringHeader);
        v66 = ColorHelpers::WindowsUIColorFromString();
        v67 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v65 + 144))(v64, v66);
        if ( v67 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA0,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytil"
                          "einitializationhandler.cpp",
            (const char *)(unsigned int)v67,
            lpDestStrc);
        if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
      }
      wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTile,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTilePrivate>(
        &v83,
        &v93);
      v68 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v93 + 48LL))(v93, string);
      if ( v68 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v68,
          lpDestStrc);
      LOBYTE(v69) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::GetImpl'::`2'::impl,
        v69);
      v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 104LL))(v93);
      if ( v70 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\secondarytilei"
                        "nitializationhandler.cpp",
          (const char *)(unsigned int)v70,
          lpDestStrc);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v93);
      if ( v88 )
        std::_Ref_count_base::_Decref(v88);
      if ( v96 )
        std::_Ref_count_base::_Decref(v96);
      if ( v90 )
        std::_Ref_count_base::_Decref(v90);
      if ( v92 )
        std::_Ref_count_base::_Decref(v92);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v108);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v82);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v97);
      if ( v99 )
        std::_Ref_count_base::_Decref(v99);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(DestStr);
      WindowsDeleteString(v85);
      v85 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v83);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v94);
    }
    if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
        SecondaryTileInitialization_InitializeSecondaryTile_Stop);
    v71 = (std::_Ref_count_base *)a2[1];
    if ( v71 )
      std::_Ref_count_base::_Decref(v71);
  }
  catch ( std::exception *v101 )
  {
    if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 2) != 0 )
    {
      v72 = (*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v101[0] + 8LL))(v101[0]);
      v73 = (const char *)v72;
      if ( v72 )
      {
        v74 = -1;
        do
          ++v74;
        while ( *(_BYTE *)(v72 + v74) );
        v75 = v74 + 1;
      }
      else
      {
        v75 = 5;
      }
      v76 = "NULL";
      if ( v73 )
        v76 = v73;
      v109 = v76;
      v110 = v75;
      v111 = 0;
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
        SecondaryTileInitialization_InitializeSecondaryTile_Failure);
    }
    v87 = (const WCHAR *)std::current_exception(&hstringHeader);
    __ExceptionPtrRethrow(v87);
    JUMPOUT(0x1803A0382LL);
  }
}

```

## disassembly

```asm
0x18015b3e0  mov     r11, rsp
0x18015b3e3  mov     [r11+18h], rbx
0x18015b3e7  mov     [r11+20h], rsi
0x18015b3eb  push    rdi
0x18015b3ec  push    r12
0x18015b3ee  push    r13
0x18015b3f0  push    r14
0x18015b3f2  push    r15
0x18015b3f4  sub     rsp, 190h
0x18015b3fb  mov     rax, cs:__security_cookie
0x18015b402  xor     rax, rsp
0x18015b405  mov     [rsp+1B8h+var_38], rax
0x18015b40d  mov     r15, rdx
0x18015b410  mov     r13, rcx
0x18015b413  mov     [r11-0D8h], rdx
0x18015b41a  xor     r12d, r12d
0x18015b41d  mov     esi, r12d
0x18015b420  mov     dword ptr [rsp+1B8h+var_150], r12d
0x18015b425  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, 1
0x18015b42c  jz      short loc_18015B45F
0x18015b42e  lea     rdx, [r11-78h]
0x18015b432  mov     rcx, [r15]
0x18015b435  call    ?ToLoggingString@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::ToLoggingString(void)
0x18015b43a  lea     esi, [r12+1]
0x18015b43f  cmp     qword ptr [rax+18h], 7
0x18015b444  jbe     short loc_18015B449
0x18015b446  mov     rax, [rax]
0x18015b449  mov     r8, rax
0x18015b44c  lea     rdx, SecondaryTileInitialization_InitializeSecondaryTile_Start
0x18015b453  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x18015b45a  call    McTemplateU0z_EventWriteTransfer
0x18015b45f  test    sil, 1
0x18015b463  jz      short loc_18015B475
0x18015b465  and     esi, 0FFFFFFFEh
0x18015b468  lea     rcx, [rsp+1B8h+var_78]; void *
0x18015b470  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18015b475  mov     [rsp+1B8h+var_C8], r13
0x18015b47d  mov     [rsp+1B8h+var_C0], 1
0x18015b485  mov     rcx, [r15]
0x18015b488  call    ?GetTileType@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?BW4LayoutTileType@23456@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(void)
0x18015b48d  mov     rcx, [rsp+1B8h]; this
0x18015b495  cmp     eax, 2
0x18015b498  jz      short loc_18015B4B1
0x18015b49a  mov     r9d, 80070057h; char *
0x18015b4a0  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015b4a7  mov     edx, 50h ; 'P'; void *
0x18015b4ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b4b1  mov     rdx, r15
0x18015b4b4  lea     rcx, [rsp+1B8h+var_120]
0x18015b4bc  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x18015b4c1  mov     rdx, rax
0x18015b4c4  mov     rcx, r13
0x18015b4c7  call    ?DoesSecondaryTileExist@SecondaryTileInitializationHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAA_NV?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::DoesSecondaryTileExist(std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>)
0x18015b4cc  test    al, al
0x18015b4ce  jnz     loc_18015C03E
0x18015b4d4  lea     rdx, [rsp+1B8h+var_150]
0x18015b4d9  mov     rcx, [r15]
0x18015b4dc  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18015b4e1  nop
0x18015b4e2  lea     rdx, [rsp+1B8h+var_108]
0x18015b4ea  mov     rcx, rax
0x18015b4ed  call    ??$query@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_exception_policy>::query<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(void)
0x18015b4f2  nop
0x18015b4f3  lea     rcx, [rsp+1B8h+var_150]; void *
0x18015b4f8  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015b4fd  mov     [rsp+1B8h+string], r12
0x18015b502  mov     rdi, [rsp+1B8h+var_108]
0x18015b50a  mov     rax, [rdi]
0x18015b50d  mov     rbx, [rax+30h]
0x18015b511  xor     ecx, ecx; string
0x18015b513  call    cs:__imp_WindowsDeleteString
0x18015b519  mov     [rsp+1B8h+string], r12
0x18015b51e  lea     rdx, [rsp+1B8h+string]
0x18015b523  mov     rcx, rdi
0x18015b526  mov     rax, rbx
0x18015b529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b52e  mov     rcx, [rsp+1B8h]; this
0x18015b536  test    eax, eax
0x18015b538  jns     short loc_18015B54E
0x18015b53a  mov     r9d, eax; char *
0x18015b53d  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015b544  mov     edx, 58h ; 'X'; void *
0x18015b549  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b54e  cmp     [r13+40h], r12
0x18015b552  jz      short loc_18015B5AC
0x18015b554  lea     rcx, [rsp+1B8h+var_150]
0x18015b559  call    ??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(ushort const *)
0x18015b55e  nop
0x18015b55f  mov     rcx, [rsp+1B8h+var_150]
0x18015b564  mov     rax, [rcx]
0x18015b567  mov     r8, [r13+40h]
0x18015b56b  mov     rdx, [rsp+1B8h+string]
0x18015b570  mov     rax, [rax+1A0h]
0x18015b577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b57c  mov     rcx, [rsp+1B8h]; this
0x18015b584  lea     r14, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015b58b  test    eax, eax
0x18015b58d  jns     short loc_18015B5A0
0x18015b58f  mov     r9d, eax; char *
0x18015b592  mov     r8, r14; unsigned int
0x18015b595  mov     edx, 5Ch ; '\'; void *
0x18015b59a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18015b59f  nop
0x18015b5a0  lea     rcx, [rsp+1B8h+var_150]; void *
0x18015b5a5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015b5aa  jmp     short loc_18015B5B3
0x18015b5ac  lea     r14, aShellcommonShe_10; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015b5b3  mov     [rsp+1B8h+var_168], r12
0x18015b5b8  mov     rax, [r13+10h]
0x18015b5bc  mov     rbx, [rax]
0x18015b5bf  mov     [rsp+1B8h+var_A0], r12
0x18015b5c7  mov     r9d, 24h ; '$'; unsigned int
0x18015b5cd  lea     r8d, [r9+1]; unsigned int
0x18015b5d1  lea     rdx, ?RuntimeClass_Windows_UI_StartScreen_SecondaryTile@@3QBGB; "Windows.UI.StartScreen.SecondaryTile"
0x18015b5d8  lea     rcx, [rsp+1B8h+hstringHeader]; hstringHeader
0x18015b5e0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18015b5e5  nop
0x18015b5e6  lea     r8, [rsp+1B8h+var_168]
0x18015b5eb  mov     rdx, rbx
0x18015b5ee  mov     rcx, [rsp+1B8h+var_A0]
0x18015b5f6  call    ??$ActivateInstanceAsUser@UISecondaryTile@StartScreen@UI@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUISecondaryTile@StartScreen@UI@1@@Z; Windows::Foundation::ActivateInstanceAsUser<Windows::UI::StartScreen::ISecondaryTile>(HSTRING__ *,Windows::System::IUser *,Windows::UI::StartScreen::ISecondaryTile * *)
0x18015b5fb  mov     rcx, [rsp+1B8h]; this
0x18015b603  test    eax, eax
0x18015b605  jns     short loc_18015B618
0x18015b607  mov     r9d, eax; char *
0x18015b60a  mov     r8, r14; unsigned int
0x18015b60d  mov     edx, 60h ; '`'; void *
0x18015b612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b618  mov     [rsp+1B8h+var_158], r12
0x18015b61d  mov     rdi, [rsp+1B8h+var_108]
0x18015b625  mov     rax, [rdi]
0x18015b628  mov     rbx, [rax+38h]
0x18015b62c  xor     ecx, ecx; string
0x18015b62e  call    cs:__imp_WindowsDeleteString
0x18015b634  mov     [rsp+1B8h+var_158], r12
0x18015b639  lea     rdx, [rsp+1B8h+var_158]
0x18015b63e  mov     rcx, rdi
0x18015b641  mov     rax, rbx
0x18015b644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b649  mov     rcx, [rsp+1B8h]; this
0x18015b651  test    eax, eax
0x18015b653  jns     short loc_18015B665
0x18015b655  mov     r9d, eax; char *
0x18015b658  mov     r8, r14; unsigned int
0x18015b65b  mov     edx, 64h ; 'd'; void *
0x18015b660  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b665  mov     rcx, [rsp+1B8h+var_168]
0x18015b66a  mov     rax, [rcx]
0x18015b66d  mov     rdx, [rsp+1B8h+var_158]
0x18015b672  mov     rax, [rax+30h]
0x18015b676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b67b  mov     rcx, [rsp+1B8h]; this
0x18015b683  test    eax, eax
0x18015b685  jns     short loc_18015B697
0x18015b687  mov     r9d, eax; char *
0x18015b68a  mov     r8, r14; unsigned int
0x18015b68d  mov     edx, 65h ; 'e'; void *
0x18015b692  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b697  xor     edx, edx; length
0x18015b699  mov     rcx, [rsp+1B8h+string]; string
0x18015b69e  call    cs:__imp_WindowsGetStringRawBuffer
0x18015b6a4  mov     rdx, rax
0x18015b6a7  lea     rcx, [rsp+1B8h+DestStr]
0x18015b6af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18015b6b4  nop
0x18015b6b5  mov     r9d, [rsp+1B8h+cchSrc]; cchSrc
0x18015b6bd  cmp     [rsp+1B8h+var_80], 7
0x18015b6c6  ja      short loc_18015B6DA
0x18015b6c8  lea     rax, [rsp+1B8h+DestStr]
0x18015b6d0  lea     r8, [rsp+1B8h+DestStr]
0x18015b6d8  jmp     short loc_18015B6E5
0x18015b6da  mov     rax, qword ptr [rsp+1B8h+DestStr]
0x18015b6e2  mov     r8, rax; lpSrcStr
0x18015b6e5  mov     rbx, [rsp+1B8h]
0x18015b6ed  mov     [rsp+1B8h+cchDest], r9d; cchDest
0x18015b6f2  mov     [rsp+1B8h+lpDestStr], rax; int
0x18015b6f7  mov     edx, 200h; dwMapFlags
0x18015b6fc  mov     ecx, 7Fh; Locale
0x18015b701  call    cs:__imp_LCMapStringW
0x18015b707  test    eax, eax
0x18015b709  jnz     short loc_18015B71F
0x18015b70b  mov     r9d, 80004005h; char *
0x18015b711  mov     r8, r14; unsigned int
0x18015b714  lea     edx, [rax+69h]; void *
0x18015b717  mov     rcx, rbx; this
0x18015b71a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18015b71f  lea     rdx, [rsp+1B8h+var_120]
0x18015b727  lea     rcx, [rsp+1B8h+DestStr]
0x18015b72f  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x18015b734  lea     rdx, [rsp+1B8h+var_120]
0x18015b73c  call    ?IsSpartanOrAnaheimEdge@SecondaryTileInitializationHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileInitializationHandler::IsSpartanOrAnaheimEdge(std::basic_string_view<ushort> const &)
0x18015b741  mov     bl, al
0x18015b743  mov     [rsp+1B8h+var_178], al
0x18015b747  mov     rdx, [r15]
0x18015b74a  mov     rcx, [rdx+20h]
0x18015b74e  test    rcx, rcx
0x18015b751  jz      short loc_18015B762
0x18015b753  lea     rdx, [rsp+1B8h+var_E8]
0x18015b75b  call    ?GetArguments@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetArguments(void)
0x18015b760  jmp     short loc_18015B773
0x18015b762  add     rdx, 68h ; 'h'
0x18015b766  lea     rcx, [rsp+1B8h+var_E8]
0x18015b76e  call    ??0?$shared_ptr@U?$CloudItemAction@UPlaceholderTileCollection@Data@Windows@@@?$CloudItemUpdaterImpl@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@23@V?$CloudItemManager@V?$GenericCloudItem@UPlaceholderTileCollection@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@523@@Internal@CloudUtil@DataStoreCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>>(std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemUpdaterImpl<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>,DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>,DataStoreCache::CloudUtil::Internal::CloudItemManager<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollection,0>>>::CloudItemAction<Windows::Data::PlaceholderTileCollection>> const &)
0x18015b773  or      esi, 40h
0x18015b776  mov     dword ptr [rsp+1B8h+var_150], esi
0x18015b77a  mov     r12, [rsp+1B8h+var_E8]
0x18015b782  test    r12, r12
0x18015b785  jnz     short loc_18015B78F
0x18015b787  test    bl, bl
0x18015b789  jz      short loc_18015B78F
0x18015b78b  mov     al, 1
0x18015b78d  jmp     short loc_18015B791
0x18015b78f  xor     al, al
0x18015b791  mov     rcx, [rsp+1B8h]; this
0x18015b799  test    al, al
0x18015b79b  jz      short loc_18015B7B0
0x18015b79d  mov     r9d, 8000FFFFh; char *
0x18015b7a3  mov     r8, r14; unsigned int
0x18015b7a6  mov     edx, 6Dh ; 'm'; void *
0x18015b7ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b7b0  mov     rbx, [rsp+1B8h+var_168]
0x18015b7b5  mov     rax, [rbx]
0x18015b7b8  mov     rdi, [rax+40h]
0x18015b7bc  test    r12, r12
0x18015b7bf  jz      short loc_18015B7D4
0x18015b7c1  cmp     qword ptr [r12+18h], 7
0x18015b7c7  jbe     short loc_18015B7CF
0x18015b7c9  mov     rax, [r12]
0x18015b7cd  jmp     short loc_18015B7DB
0x18015b7cf  mov     rax, r12
0x18015b7d2  jmp     short loc_18015B7DB
0x18015b7d4  lea     rax, String1
0x18015b7db  mov     [rsp+1B8h+var_140], rax
0x18015b7e0  lea     rdx, [rsp+1B8h+var_140]
0x18015b7e5  lea     rcx, [rsp+1B8h+hstringHeader]
0x18015b7ed  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18015b7f2  nop
0x18015b7f3  mov     rdx, [rax+18h]
0x18015b7f7  mov     rcx, rbx
0x18015b7fa  mov     rax, rdi
0x18015b7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b802  mov     rcx, [rsp+1B8h]; this
0x18015b80a  test    eax, eax
0x18015b80c  jns     short loc_18015B81F
0x18015b80e  mov     r9d, eax; char *
0x18015b811  mov     r8, r14; unsigned int
0x18015b814  mov     edx, 6Eh ; 'n'; void *
0x18015b819  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b81f  mov     rbx, [rsp+1B8h+var_168]
0x18015b824  mov     rdi, [rbx]
0x18015b827  lea     rdx, [rsp+1B8h+var_130]
0x18015b82f  mov     rcx, [r15]
0x18015b832  call    ?GetDisplayName@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetDisplayName(void)
0x18015b837  nop
0x18015b838  cmp     qword ptr [rax], 0
0x18015b83c  jz      short loc_18015B865
0x18015b83e  lea     rdx, [rsp+1B8h+var_120]
0x18015b846  mov     rcx, [r15]
0x18015b849  call    ?GetDisplayName@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetDisplayName(void)
0x18015b84e  nop
0x18015b84f  or      esi, 2
0x18015b852  mov     dword ptr [rsp+1B8h+var_150], esi
0x18015b856  mov     rax, [rax]
0x18015b859  cmp     qword ptr [rax+18h], 7
0x18015b85e  jbe     short loc_18015B86C
0x18015b860  mov     rax, [rax]
0x18015b863  jmp     short loc_18015B86C
0x18015b865  lea     rax, String1
0x18015b86c  mov     [rsp+1B8h+var_140], rax
0x18015b871  lea     rdx, [rsp+1B8h+var_140]
0x18015b876  lea     rcx, [rsp+1B8h+hstringHeader]
0x18015b87e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18015b883  nop
0x18015b884  mov     rdx, [rax+18h]
0x18015b888  mov     rcx, rbx
0x18015b88b  mov     rax, [rdi+60h]
0x18015b88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b894  mov     rcx, [rsp+1B8h]; this
0x18015b89c  test    eax, eax
0x18015b89e  jns     short loc_18015B8B1
0x18015b8a0  mov     r9d, eax; char *
0x18015b8a3  mov     r8, r14; unsigned int
0x18015b8a6  mov     edx, 6Fh ; 'o'; void *
0x18015b8ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015b8b1  mov     [rsp+1B8h+var_A0], 0
0x18015b8bd  test    sil, 2
0x18015b8c1  jz      short loc_18015B8D9
0x18015b8c3  and     esi, 0FFFFFFFDh
0x18015b8c6  mov     rcx, [rsp+1B8h+var_118]; this
0x18015b8ce  test    rcx, rcx
0x18015b8d1  jz      short loc_18015B8D9
0x18015b8d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18015b8d8  nop
0x18015b8d9  mov     rcx, [rsp+1B8h+var_128]; this
0x18015b8e1  test    rcx, rcx
0x18015b8e4  jz      short loc_18015B8EB
0x18015b8e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18015b8eb  lea     rdx, [rsp+1B8h+var_F0]
0x18015b8f3  lea     rcx, [rsp+1B8h+var_168]
0x18015b8f8  call    ??$query@UISecondaryTile2@StartScreen@UI@Windows@@@?$com_ptr_t@UISecondaryTile@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UISecondaryTile2@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTile,wil::err_exception_policy>::query<Windows::UI::StartScreen::ISecondaryTile2>(void)
  ... truncated ...
```
