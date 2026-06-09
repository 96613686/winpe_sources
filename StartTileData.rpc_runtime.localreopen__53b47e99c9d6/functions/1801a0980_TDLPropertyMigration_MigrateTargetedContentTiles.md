# TDLPropertyMigration::MigrateTargetedContentTiles

- ea: `0x1801a0980`
- end: `0x1801a10b4`
- name: `TDLPropertyMigration::MigrateTargetedContentTiles`
- size: `1844`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802c7e50`

## callees

- `0x18000ce94`
- `0x18001dac0`
- `0x18004a468`
- `0x18004c064`
- `0x18004ffc0`
- `0x18006fe30`
- `0x1800756e4`
- `0x18007ae80`
- `0x1800f0eb4`
- `0x180161204`
- `0x18019f248`
- `0x1801a0980`
- `0x1801a10bc`
- `0x1801a14fc`
- `0x1801a163c`
- `0x1801a169c`
- `0x1801a175c`
- `0x180201e50`
- `0x180251458`
- `0x1802514c4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a0e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a0d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a0d96`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801a0a25`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801a0a25`
- `ntdll!RtlPublishWnfStateData` at `0x1801a1010`
- `ntdll!RtlPublishWnfStateData` at `0x1801a1010`

## string_xrefs

- `0x1801a0fea`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1801a0a39`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0a96`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0b03`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0b52`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0b9d`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0bef`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0e62`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0ed8`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0eed`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0f02`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0f17`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0f2c`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0f41`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0f56`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a0fc0`: `shellcommon\shell\tiles\tdlpropertymigration\lib\tdlpropertymigration.cpp`
- `0x1801a09c7`: `^PreInstalled\.DefaultStartLayout(\d+)\.(\d+)$`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 TDLPropertyMigration::MigrateTargetedContentTiles()
{
  unsigned __int64 v0; // rbx
  int ActivationFactory; // eax
  unsigned __int64 v2; // rbx
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, unsigned __int64, _QWORD); // rbx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  char v16; // si
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  int v28; // eax
  HSTRING v29; // r8
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, __int64, __int64 *); // rdi
  const WCHAR *Reserved1; // rdx
  __int64 v37; // rbx
  int v38; // eax
  int v39; // eax
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v41)(_QWORD, GUID *, __int64 *); // rbx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  __int64 v58; // [rsp+88h] [rbp-78h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v60[8]; // [rsp+98h] [rbp-68h] BYREF
  int v61; // [rsp+A0h] [rbp-60h]
  __int64 v62; // [rsp+B0h] [rbp-50h] BYREF
  int v63; // [rsp+B8h] [rbp-48h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  _BYTE v65[40]; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v66; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v67; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v69; // [rsp+128h] [rbp+28h]
  HSTRING_HEADER v70; // [rsp+130h] [rbp+30h] BYREF
  __int64 v71; // [rsp+148h] [rbp+48h]
  _BYTE v72[32]; // [rsp+150h] [rbp+50h] BYREF
  HSTRING_HEADER v73; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v69 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy!App",
    0x3Bu,
    0x3Au);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v65,
    L"^PreInstalled\\.DefaultStartLayout(\\d+)\\.(\\d+)$");
  std::wstring::wstring(v72, L"$1!$2");
  v59 = 0;
  v67 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v66,
    L"WindowsInternal.Shell.UnifiedTile.TargetedContentUnifiedTileIdentifier",
    0x47u,
    0x46u);
  v0 = v67;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  ActivationFactory = RoGetActivationFactory(v0, &GUID_1ffce3b9_51ad_429f_be82_8829d0c1181b, &v59);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v46);
  v58 = 0;
  v67 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v66,
    L"WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.CuratedTileCollectionManager",
    0x56u,
    0x55u);
  v2 = v67;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v3 = Windows::Foundation::ActivateInstance<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollectionManager>(
         v2,
         &v58);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)v3,
      v46);
  v50 = 0;
  v4 = v58;
  v5 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v58 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v67 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, L"Start.TileGrid", 0xFu, 0xEu);
  v6 = v5(v4, v67, &v50);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)v6,
      v46);
  v57 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  v8 = **v50;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v9 = v8(v7, &GUID_adbf8965_6056_4126_ab26_6660af4661ce, &v57);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)v9,
      v46);
  v56 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  v11 = (*v50)[13];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))v11)(
          v10,
          &v56);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)v12,
      v46);
  v55 = 0;
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v56;
  v14 = **v56;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v15 = v14(v13, &GUID_29e14483_299b_51db_a4a9_4fa71439ba45, &v55);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
      (const char *)(unsigned int)v15,
      v46);
  v16 = 0;
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
    v60,
    v55);
  v62 = 0;
  v63 = -1;
  v64 = 0;
  while ( v61 != -1 )
  {
    v17 = wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::operator*(v60);
    v47 = 0;
    v18 = *(_QWORD *)v17;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v17 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v20 = v19(v18, &v47);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
        (const char *)(unsigned int)v20,
        v46);
    v49 = 0;
    v21 = v47;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v23 = v22(v21, &v49);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
        (const char *)(unsigned int)v23,
        v46);
    v48 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 48LL))(v49, &v48);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
        (const char *)(unsigned int)v24,
        v46);
    if ( v48 == 1 )
    {
      v54 = 0;
      v25 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
              &v49,
              &v54);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C5,
          (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
          (const char *)(unsigned int)v25,
          v46);
      v51 = 0;
      v26 = v54;
      v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 48LL);
      WindowsDeleteString(0);
      v51 = 0;
      v28 = v27(v26, &v51);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C8,
          (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
          (const char *)(unsigned int)v28,
          v46);
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)v51,
                            v69,
                            v29) )
      {
        string = 0;
        v30 = v54;
        v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v32 = v31(v30, &string);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CE,
            (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
            (const char *)(unsigned int)v32,
            v46);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        std::regex_replace<std::regex_traits<unsigned short>,unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
          &v66,
          StringRawBuffer,
          v65,
          v72);
        if ( *(_QWORD *)&v66.Reserved.Reserved2[16] )
        {
          v52 = 0;
          v34 = v59;
          v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v59 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          Reserved1 = (const WCHAR *)&v66;
          if ( v67 > 7 )
            Reserved1 = (const WCHAR *)v66.Reserved.Reserved1;
          v37 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                              &v73,
                              Reserved1,
                              *(UINT32 *)&v66.Reserved.Reserved2[16])
                          + 24);
          v71 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v70, L"DynamicLayouts", 0xFu, 0xEu);
          v38 = v35(v34, v71, v37, &v52);
          if ( v38 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D9,
              (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
              (const char *)(unsigned int)v38,
              v46);
          v39 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v57 + 72LL))(v57, v49, v52);
          if ( v39 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
              (const char *)(unsigned int)v39,
              v46);
          v16 = 1;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        }
        std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v66);
        WindowsDeleteString(string);
      }
      WindowsDeleteString(v51);
      v51 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile *> *,wil::err_exception_policy>::iterable_iterator::operator++(v60);
  }
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v62);
  wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v60);
  if ( v16 )
  {
    v47 = 0;
    v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    v41 = (*v50)[28];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v42 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v41)(v40, &v47);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"shellcommon\\shell\\tiles\\tdlpropertymigration\\lib\\tdlpropertymigration.cpp",
        (const char *)(unsigned int)v42,
        v46);
    v43 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v47);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x714,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)v43,
        v46);
    v44 = RtlPublishWnfStateData(WNF_SHEL_START_LAYOUT_MIGRATED, 0, 0, 0) | 0x10000000;
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v44,
        0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v72);
  return std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v65);
}

```

## disassembly

```asm
0x1801a0980  push    rbp
0x1801a0982  push    rbx
0x1801a0983  push    rsi
0x1801a0984  push    rdi
0x1801a0985  push    r14
0x1801a0987  lea     rbp, [rsp-0A0h]
0x1801a098f  sub     rsp, 1A0h
0x1801a0996  mov     rax, cs:__security_cookie
0x1801a099d  xor     rax, rsp
0x1801a09a0  mov     [rbp+0C0h+var_30], rax
0x1801a09a7  xor     r14d, r14d
0x1801a09aa  mov     [rbp+0C0h+var_98], r14
0x1801a09ae  lea     r9d, [r14+3Ah]; unsigned int
0x1801a09b2  lea     r8d, [r14+3Bh]; unsigned int
0x1801a09b6  lea     rdx, ?c_ContentDeliveryManagerApplicationUserModelId@Shared@CreativeFramework@@3QBGB; "Microsoft.Windows.ContentDeliveryManage"...
0x1801a09bd  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x1801a09c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a09c6  nop
0x1801a09c7  lea     rdx, aPreinstalledDe; "^PreInstalled\\.DefaultStartLayout(\\d+"...
0x1801a09ce  lea     rcx, [rbp+0C0h+var_F8]
0x1801a09d2  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x1801a09d7  nop
0x1801a09d8  lea     rdx, a12; "$1!$2"
0x1801a09df  lea     rcx, [rbp+0C0h+var_70]
0x1801a09e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a09e8  nop
0x1801a09e9  mov     [rbp+0C0h+var_130], r14
0x1801a09ed  mov     [rbp+0C0h+var_B8], r14
0x1801a09f1  lea     r9d, [r14+46h]; unsigned int
0x1801a09f5  lea     r8d, [r14+47h]; unsigned int
0x1801a09f9  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_TargetedContentUnifiedTileIdentifier@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Targe"...
0x1801a0a00  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x1801a0a04  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a0a09  nop
0x1801a0a0a  mov     rbx, [rbp+0C0h+var_B8]
0x1801a0a0e  lea     rcx, [rbp+0C0h+var_130]
0x1801a0a12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0a17  lea     r8, [rbp+0C0h+var_130]
0x1801a0a1b  lea     rdx, _GUID_1ffce3b9_51ad_429f_be82_8829d0c1181b
0x1801a0a22  mov     rcx, rbx
0x1801a0a25  call    cs:__imp_RoGetActivationFactory
0x1801a0a2b  mov     rcx, [rbp+0C8h]; this
0x1801a0a32  test    eax, eax
0x1801a0a34  jns     short loc_1801A0A4B
0x1801a0a36  mov     r9d, eax; char *
0x1801a0a39  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0a40  mov     edx, 1A4h; void *
0x1801a0a45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0a4b  mov     [rbp+0C0h+var_138], r14
0x1801a0a4f  mov     [rbp+0C0h+var_B8], r14
0x1801a0a53  mov     r9d, 55h ; 'U'; unsigned int
0x1801a0a59  lea     r8d, [r9+1]; unsigned int
0x1801a0a5d  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_CuratedTileCollectionManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Curat"...
0x1801a0a64  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x1801a0a68  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a0a6d  nop
0x1801a0a6e  mov     rbx, [rbp+0C0h+var_B8]
0x1801a0a72  lea     rcx, [rbp+0C0h+var_138]
0x1801a0a76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0a7b  lea     rdx, [rbp+0C0h+var_138]
0x1801a0a7f  mov     rcx, rbx
0x1801a0a82  call    ??$ActivateInstance@UICuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUICuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Z; Windows::Foundation::ActivateInstance<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollectionManager>(HSTRING__ *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollectionManager * *)
0x1801a0a87  nop
0x1801a0a88  mov     rcx, [rbp+0C8h]; this
0x1801a0a8f  test    eax, eax
0x1801a0a91  jns     short loc_1801A0AA8
0x1801a0a93  mov     r9d, eax; char *
0x1801a0a96  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0a9d  mov     edx, 1A7h; void *
0x1801a0aa2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0aa8  mov     [rsp+1C0h+var_178], r14
0x1801a0aad  mov     rdi, [rbp+0C0h+var_138]
0x1801a0ab1  mov     rax, [rdi]
0x1801a0ab4  mov     rbx, [rax+38h]
0x1801a0ab8  lea     rcx, [rsp+1C0h+var_178]
0x1801a0abd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0ac2  mov     [rbp+0C0h+var_B8], r14
0x1801a0ac6  mov     r9d, 0Eh; unsigned int
0x1801a0acc  lea     r8d, [r9+1]; unsigned int
0x1801a0ad0  lea     rdx, ?c_startTileGridCollectionId@CollectionConstants@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Start.TileGrid"
0x1801a0ad7  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x1801a0adb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a0ae0  nop
0x1801a0ae1  lea     r8, [rsp+1C0h+var_178]
0x1801a0ae6  mov     rdx, [rbp+0C0h+var_B8]
0x1801a0aea  mov     rcx, rdi
0x1801a0aed  mov     rax, rbx
0x1801a0af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0af5  mov     rcx, [rbp+0C8h]; this
0x1801a0afc  test    eax, eax
0x1801a0afe  jns     short loc_1801A0B15
0x1801a0b00  mov     r9d, eax; char *
0x1801a0b03  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0b0a  mov     edx, 1AAh; void *
0x1801a0b0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0b15  mov     [rbp+0C0h+var_140], r14
0x1801a0b19  mov     rbx, [rsp+1C0h+var_178]
0x1801a0b1e  mov     rax, [rbx]
0x1801a0b21  mov     rdi, [rax]
0x1801a0b24  lea     rcx, [rbp+0C0h+var_140]
0x1801a0b28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0b2d  lea     r8, [rbp+0C0h+var_140]
0x1801a0b31  lea     rdx, _GUID_adbf8965_6056_4126_ab26_6660af4661ce
0x1801a0b38  mov     rcx, rbx
0x1801a0b3b  mov     rax, rdi
0x1801a0b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0b43  nop
0x1801a0b44  mov     rcx, [rbp+0C8h]; this
0x1801a0b4b  test    eax, eax
0x1801a0b4d  jns     short loc_1801A0B64
0x1801a0b4f  mov     r9d, eax; char *
0x1801a0b52  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0b59  mov     edx, 1ADh; void *
0x1801a0b5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0b64  mov     [rsp+1C0h+var_148], r14
0x1801a0b69  mov     rdi, [rsp+1C0h+var_178]
0x1801a0b6e  mov     rax, [rdi]
0x1801a0b71  mov     rbx, [rax+68h]
0x1801a0b75  lea     rcx, [rsp+1C0h+var_148]
0x1801a0b7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0b7f  lea     rdx, [rsp+1C0h+var_148]
0x1801a0b84  mov     rcx, rdi
0x1801a0b87  mov     rax, rbx
0x1801a0b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0b8f  mov     rcx, [rbp+0C8h]; this
0x1801a0b96  test    eax, eax
0x1801a0b98  jns     short loc_1801A0BAF
0x1801a0b9a  mov     r9d, eax; char *
0x1801a0b9d  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0ba4  mov     edx, 1B0h; void *
0x1801a0ba9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0baf  mov     [rsp+1C0h+var_150], r14
0x1801a0bb4  mov     rbx, [rsp+1C0h+var_148]
0x1801a0bb9  mov     rax, [rbx]
0x1801a0bbc  mov     rdi, [rax]
0x1801a0bbf  lea     rcx, [rsp+1C0h+var_150]
0x1801a0bc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0bc9  lea     r8, [rsp+1C0h+var_150]
0x1801a0bce  lea     rdx, _GUID_29e14483_299b_51db_a4a9_4fa71439ba45
0x1801a0bd5  mov     rcx, rbx
0x1801a0bd8  mov     rax, rdi
0x1801a0bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0be0  nop
0x1801a0be1  mov     rcx, [rbp+0C8h]; this
0x1801a0be8  test    eax, eax
0x1801a0bea  jns     short loc_1801A0C01
0x1801a0bec  mov     r9d, eax; char *
0x1801a0bef  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0bf6  mov     edx, 1B3h; void *
0x1801a0bfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a0c01  mov     sil, r14b
0x1801a0c04  mov     rdx, [rsp+1C0h+var_150]
0x1801a0c09  lea     rcx, [rbp+0C0h+var_128]
0x1801a0c0d  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@U_GUID@@PEAUICuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@U_GUID@@PEAUICuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *> *)
0x1801a0c12  nop
0x1801a0c13  mov     [rbp+0C0h+var_110], r14
0x1801a0c17  mov     [rbp+0C0h+var_108], 0FFFFFFFFh
0x1801a0c1e  mov     [rbp+0C0h+var_100], r14
0x1801a0c22  cmp     [rbp+0C0h+var_120], 0FFFFFFFFh
0x1801a0c26  jz      loc_1801A0F68
0x1801a0c2c  lea     rcx, [rbp+0C0h+var_128]
0x1801a0c30  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@U_GUID@@PEAUICuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@U_GUID@@PEAUICuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileGroup *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x1801a0c35  mov     [rsp+1C0h+var_190], r14
0x1801a0c3a  mov     rdi, [rax]
0x1801a0c3d  mov     rax, [rdi]
0x1801a0c40  mov     rbx, [rax+38h]
0x1801a0c44  lea     rcx, [rsp+1C0h+var_190]
0x1801a0c49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0c4e  lea     rdx, [rsp+1C0h+var_190]
0x1801a0c53  mov     rcx, rdi
0x1801a0c56  mov     rax, rbx
0x1801a0c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0c5e  mov     rcx, [rbp+0C8h]; this
0x1801a0c65  test    eax, eax
0x1801a0c67  js      loc_1801A0F53
0x1801a0c6d  mov     [rsp+1C0h+var_180], r14
0x1801a0c72  mov     rdi, [rsp+1C0h+var_190]
0x1801a0c77  mov     rax, [rdi]
0x1801a0c7a  mov     rbx, [rax+30h]
0x1801a0c7e  lea     rcx, [rsp+1C0h+var_180]
0x1801a0c83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0c88  lea     rdx, [rsp+1C0h+var_180]
0x1801a0c8d  mov     rcx, rdi
0x1801a0c90  mov     rax, rbx
0x1801a0c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0c98  mov     rcx, [rbp+0C8h]; this
0x1801a0c9f  test    eax, eax
0x1801a0ca1  js      loc_1801A0F3E
0x1801a0ca7  mov     [rsp+1C0h+var_188], r14d
0x1801a0cac  mov     rcx, [rsp+1C0h+var_180]
0x1801a0cb1  mov     rax, [rcx]
0x1801a0cb4  lea     rdx, [rsp+1C0h+var_188]
0x1801a0cb9  mov     rax, [rax+30h]
0x1801a0cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0cc2  mov     rcx, [rbp+0C8h]; this
0x1801a0cc9  test    eax, eax
0x1801a0ccb  js      loc_1801A0F29
0x1801a0cd1  cmp     [rsp+1C0h+var_188], 1
0x1801a0cd6  jnz     loc_1801A0EB2
0x1801a0cdc  mov     [rsp+1C0h+var_158], r14
0x1801a0ce1  lea     rdx, [rsp+1C0h+var_158]
0x1801a0ce6  lea     rcx, [rsp+1C0h+var_180]
0x1801a0ceb  call    ??$As@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>>)
0x1801a0cf0  mov     rcx, [rbp+0C8h]; this
0x1801a0cf7  test    eax, eax
0x1801a0cf9  js      loc_1801A0F14
0x1801a0cff  mov     [rsp+1C0h+var_170], r14
0x1801a0d04  mov     rdi, [rsp+1C0h+var_158]
0x1801a0d09  mov     rax, [rdi]
0x1801a0d0c  mov     rbx, [rax+30h]
0x1801a0d10  xor     ecx, ecx; string
0x1801a0d12  call    cs:__imp_WindowsDeleteString
0x1801a0d18  mov     [rsp+1C0h+var_170], r14
0x1801a0d1d  lea     rdx, [rsp+1C0h+var_170]
0x1801a0d22  mov     rcx, rdi
0x1801a0d25  mov     rax, rbx
0x1801a0d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0d2d  mov     rcx, [rbp+0C8h]; this
0x1801a0d34  test    eax, eax
0x1801a0d36  js      loc_1801A0EFF
0x1801a0d3c  mov     rdx, [rbp+0C0h+var_98]; HSTRING
0x1801a0d40  mov     rcx, [rsp+1C0h+var_170]; this
0x1801a0d45  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801a0d4a  test    eax, eax
0x1801a0d4c  jnz     loc_1801A0E97
0x1801a0d52  mov     [rsp+1C0h+string], r14
0x1801a0d57  mov     rdi, [rsp+1C0h+var_158]
0x1801a0d5c  mov     rax, [rdi]
0x1801a0d5f  mov     rbx, [rax+38h]
0x1801a0d63  xor     ecx, ecx; string
0x1801a0d65  call    cs:__imp_WindowsDeleteString
0x1801a0d6b  mov     [rsp+1C0h+string], r14
0x1801a0d70  lea     rdx, [rsp+1C0h+string]
0x1801a0d75  mov     rcx, rdi
0x1801a0d78  mov     rax, rbx
0x1801a0d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0d80  mov     rcx, [rbp+0C8h]; this
0x1801a0d87  test    eax, eax
0x1801a0d89  js      loc_1801A0EEA
0x1801a0d8f  xor     edx, edx; length
0x1801a0d91  mov     rcx, [rsp+1C0h+string]; string
0x1801a0d96  call    cs:__imp_WindowsGetStringRawBuffer
0x1801a0d9c  lea     r9, [rbp+0C0h+var_70]
0x1801a0da0  lea     r8, [rbp+0C0h+var_F8]
0x1801a0da4  mov     rdx, rax
0x1801a0da7  lea     rcx, [rbp+0C0h+var_D0]
0x1801a0dab  call    ??$regex_replace@V?$regex_traits@G@std@@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV10@W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::wstring const &,std::regex_constants::match_flag_type)
0x1801a0db0  nop
0x1801a0db1  cmp     qword ptr [rbp+0C0h+var_D0.Reserved+10h], r14
0x1801a0db5  jz      loc_1801A0E81
0x1801a0dbb  mov     [rsp+1C0h+var_168], r14
0x1801a0dc0  mov     rsi, [rbp+0C0h+var_130]
0x1801a0dc4  mov     rax, [rsi]
0x1801a0dc7  mov     rdi, [rax+30h]
0x1801a0dcb  lea     rcx, [rsp+1C0h+var_168]
0x1801a0dd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0dd5  lea     rdx, [rbp+0C0h+var_D0]
0x1801a0dd9  cmp     [rbp+0C0h+var_B8], 7
0x1801a0dde  cmova   rdx, qword ptr [rbp+0C0h+var_D0.Reserved]; sourceString
0x1801a0de3  mov     r8d, dword ptr [rbp+0C0h+var_D0.Reserved+10h]; length
0x1801a0de7  lea     rcx, [rbp+0C0h+var_50]; hstringHeader
0x1801a0deb  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1801a0df0  nop
0x1801a0df1  mov     rbx, [rax+18h]
0x1801a0df5  mov     [rbp+0C0h+var_78], r14
0x1801a0df9  mov     r9d, 0Eh; unsigned int
0x1801a0dff  lea     r8d, [r9+1]; unsigned int
0x1801a0e03  lea     rdx, ?c_dynamicLayouts@SubscriptionIds@TargetedContent@CreativeFramework@@3QBGB; "DynamicLayouts"
0x1801a0e0a  lea     rcx, [rbp+0C0h+var_90]; hstringHeader
0x1801a0e0e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a0e13  nop
0x1801a0e14  lea     r9, [rsp+1C0h+var_168]
0x1801a0e19  mov     r8, rbx
0x1801a0e1c  mov     rdx, [rbp+0C0h+var_78]
0x1801a0e20  mov     rcx, rsi
0x1801a0e23  mov     rax, rdi
0x1801a0e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0e2b  mov     rcx, [rbp+0C8h]; this
0x1801a0e32  test    eax, eax
0x1801a0e34  js      loc_1801A0ED5
0x1801a0e3a  mov     rcx, [rbp+0C0h+var_140]
0x1801a0e3e  mov     rax, [rcx]
0x1801a0e41  mov     r8, [rsp+1C0h+var_168]
0x1801a0e46  mov     rdx, [rsp+1C0h+var_180]
0x1801a0e4b  mov     rax, [rax+48h]
0x1801a0e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0e54  mov     rcx, [rbp+0C8h]; this
0x1801a0e5b  test    eax, eax
0x1801a0e5d  jns     short loc_1801A0E73
0x1801a0e5f  mov     r9d, eax; char *
0x1801a0e62  lea     r8, aShellcommonShe_68; "shellcommon\\shell\\tiles\\tdlpropertym"...
0x1801a0e69  mov     edx, 1DFh; void *
0x1801a0e6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801a0e73  mov     sil, 1
0x1801a0e76  lea     rcx, [rsp+1C0h+var_168]
0x1801a0e7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a0e80  nop
0x1801a0e81  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1801a0e85  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1801a0e8a  nop
  ... truncated ...
```
