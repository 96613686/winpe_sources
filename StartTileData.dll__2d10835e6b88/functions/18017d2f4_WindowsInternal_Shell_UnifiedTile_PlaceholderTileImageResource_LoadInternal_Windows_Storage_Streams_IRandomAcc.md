# WindowsInternal::Shell::UnifiedTile::PlaceholderTileImageResource::LoadInternal(Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18017d2f4`
- end: `0x18017d978`
- name: `?LoadInternal@PlaceholderTileImageResource@UnifiedTile@Shell@WindowsInternal@@AEBAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `1668`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::PlaceholderTileImageResource *__hidden this, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1802e6f48`
- `0x1802e73dc`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001dfb8`
- `0x180035518`
- `0x18004fd50`
- `0x1800873c4`
- `0x180087bd8`
- `0x18017d1cc`
- `0x18017d204`
- `0x18017d2cc`
- `0x18017d2f4`
- `0x18017d980`
- `0x18017d99c`
- `0x18017d9d0`
- `0x18017da38`
- `0x18017da60`
- `0x18017dad0`
- `0x180201e50`
- `0x1802e640c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017d920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017d3ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18017d4ff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18017d4ff`

## string_xrefs

- `0x18017d60b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x18017d6a9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x18017d73f`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x18017d7da`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x18017d5ee`: `Windows.ShellCommon.SharedResources`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::PlaceholderTileImageResource::LoadInternal(
        WindowsInternal::Shell::UnifiedTile::PlaceholderTileImageResource *this,
        struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // r15
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r8
  _QWORD *v10; // rax
  HSTRING_HEADER *v11; // rax
  int v12; // r14d
  __int64 v13; // rbx
  __int64 v14; // rbx
  int v15; // ebx
  const WCHAR *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdi
  struct IResourceManager **v19; // r8
  int SystemProfileResourceMap; // eax
  unsigned int v21; // ebx
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v23; // rdi
  __int64 (__fastcall *v24)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rdi
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  unsigned int v35; // ebx
  struct Windows::Storage::Streams::IRandomAccessStream *v36; // rcx
  __int64 v37; // rbx
  struct Windows::Storage::Streams::IRandomAccessStream *v38; // rax
  struct Windows::Storage::Streams::IRandomAccessStream *v39; // rcx
  int v40[2]; // [rsp+20h] [rbp-2F8h] BYREF
  HSTRING string; // [rsp+28h] [rbp-2F0h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v42; // [rsp+30h] [rbp-2E8h] BYREF
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v43; // [rsp+38h] [rbp-2E0h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-2D8h] BYREF
  __int64 v45; // [rsp+48h] [rbp-2D0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-2C8h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v47; // [rsp+58h] [rbp-2C0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-2B8h] BYREF
  char v49[8]; // [rsp+70h] [rbp-2A8h] BYREF
  char v50[48]; // [rsp+78h] [rbp-2A0h] BYREF
  int v51[2]; // [rsp+A8h] [rbp-270h] BYREF
  HSTRING_HEADER v52; // [rsp+B0h] [rbp-268h] BYREF
  WCHAR pszBuf[264]; // [rsp+D0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  *a2 = 0;
  *(_QWORD *)v40 = 0;
  tip2::tip_test<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::start_and_watch_errors(
    v40,
    v49);
  wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(v40);
  string = 0;
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetTileIdentifier(**((_QWORD **)this + 9), v40);
  v4 = *(_QWORD *)v40;
  v5 = *(void (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v40 + 72LL);
  WindowsDeleteString(string);
  string = 0;
  v5(v4, &string);
  if ( *(_QWORD *)v40 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v7 = *(_QWORD *)v51;
  *(_QWORD *)v40 = *(_QWORD *)v51;
  if ( *(_QWORD *)v51 )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
  tip2::details::shared_data<0,0,0>::begin_update(v7 + 8);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( StringRawBuffer[v9] );
  std::wstring::_Assign<unsigned short>(v7 + 312, StringRawBuffer);
  if ( v7 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v7 + 8);
    wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::reset(v40);
  }
  wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(v40);
  v42 = 0;
  if ( *(_QWORD *)(*((_QWORD *)this + 11) + 16LL) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v10 = (_QWORD *)*((_QWORD *)this + 11);
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    *(_QWORD *)v40 = v10;
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v52, (const WCHAR **)v40);
    v12 = anonymous_namespace_::LoadStreamFromFile(*((_QWORD *)this + 13), v11[1].Reserved.Reserved1, &v42);
    v13 = *(_QWORD *)v51;
    *(_QWORD *)v40 = *(_QWORD *)v51;
    if ( *(_QWORD *)v51 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
    tip2::details::shared_data<0,0,0>::begin_update(v13 + 8);
    *(_DWORD *)(v13 + 276) = v12;
    tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v40);
    v14 = *(_QWORD *)v51;
    *(_QWORD *)v40 = *(_QWORD *)v51;
    if ( *(_QWORD *)v51 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
    tip2::details::shared_data<0,0,0>::begin_update(v14 + 8);
    v15 = *(_DWORD *)(v14 + 276) >> 31;
    tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v40);
    if ( (_BYTE)v15 )
    {
      v16 = (const WCHAR *)*((_QWORD *)this + 11);
      if ( *((_QWORD *)v16 + 3) > 7u )
        v16 = *(const WCHAR **)v16;
      PathUnExpandEnvStringsW(v16, pszBuf, 0x104u);
      v17 = *(_QWORD *)v51;
      *(_QWORD *)v40 = *(_QWORD *)v51;
      if ( *(_QWORD *)v51 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
      tip2::details::shared_data<0,0,0>::begin_update(v17 + 8);
      do
        ++v8;
      while ( pszBuf[v8] );
      std::wstring::_Assign<unsigned short>(v17 + 280, pszBuf);
      tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v40);
    }
  }
  else
  {
    v18 = *(_QWORD *)v51;
    *(_QWORD *)v40 = *(_QWORD *)v51;
    if ( *(_QWORD *)v51 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
    tip2::details::shared_data<0,0,0>::begin_update(v18 + 8);
    *(_BYTE *)(v18 + 272) = 1;
    tip2::details::shared_data<0,0,0>::end_update(v18 + 8);
    wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::reset(v40);
    wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(v40);
  }
  v48 = 0;
  if ( !v42
    || (*(int (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, __int64 *))(*(_QWORD *)v42 + 48LL))(
         v42,
         &v48) < 0
    || !v48 )
  {
    v43 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    SystemProfileResourceMap = GetSystemProfileResourceMap(L"Windows.ShellCommon.SharedResources", L"Files", v19, &v43);
    v21 = SystemProfileResourceMap;
    if ( SystemProfileResourceMap < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)(unsigned int)SystemProfileResourceMap,
        v40[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      WindowsDeleteString(string);
      string = 0;
      tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v49);
      return v21;
    }
    v44 = 0;
    v23 = v43;
    v24 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, PVOID, _QWORD))(*(_QWORD *)v43 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v52, (const WCHAR **)&off_1803F5590);
    v26 = v24(v23, v25[1].Reserved.Reserved1, &v44);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)(unsigned int)v26,
        v40[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      WindowsDeleteString(string);
      string = 0;
      tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v49);
      return v27;
    }
    v45 = 0;
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
    v29 = **v44;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    v30 = v29(v28, &GUID_69e5b468_f6fc_4013_aaa2_d53f1757d3b5, &v45);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)(unsigned int)v30,
        v40[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      WindowsDeleteString(string);
      string = 0;
      tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v49);
      return v31;
    }
    v46 = 0;
    v32 = v45;
    v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v34 = v33(v32, &v46);
    v35 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)(unsigned int)v34,
        v40[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      WindowsDeleteString(string);
      string = 0;
      tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(v49);
      return v35;
    }
    wil::wait_for_completion<Windows::Storage::Streams::IRandomAccessStream *,Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>(
      v40,
      v46);
    v36 = *(struct Windows::Storage::Streams::IRandomAccessStream **)v40;
    *(_QWORD *)v40 = 0;
    v47 = v42;
    v42 = v36;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v40);
    v37 = *(_QWORD *)v51;
    v47 = *(struct Windows::Storage::Streams::IRandomAccessStream **)v51;
    if ( *(_QWORD *)v51 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v51 + 344LL));
    tip2::details::shared_data<0,0,0>::begin_update(v37 + 8);
    *(_BYTE *)(v37 + 273) = 1;
    tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
  v38 = v42;
  v42 = 0;
  *a2 = v38;
  tip2::details::shared_data<0,0,0>::complete_without_lock(*(_QWORD *)v51 + 8LL);
  v39 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v39 + 16LL))(v39);
  }
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(v51);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v50);
  return 0;
}

```

## disassembly

```asm
0x18017d2f4  mov     [rsp+arg_10], rbx
0x18017d2f9  mov     [rsp+arg_18], rsi
0x18017d2fe  push    rdi
0x18017d2ff  push    r12
0x18017d301  push    r13
0x18017d303  push    r14
0x18017d305  push    r15
0x18017d307  sub     rsp, 2F0h
0x18017d30e  mov     rax, cs:__security_cookie
0x18017d315  xor     rax, rsp
0x18017d318  mov     [rsp+318h+var_38], rax
0x18017d320  mov     r12, rdx
0x18017d323  mov     rsi, rcx
0x18017d326  xor     r13d, r13d
0x18017d329  mov     [rdx], r13
0x18017d32c  mov     qword ptr [rsp+318h+var_2F8], r13
0x18017d331  lea     rdx, [rsp+318h+var_2A8]
0x18017d336  lea     rcx, [rsp+318h+var_2F8]
0x18017d33b  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::start_and_watch_errors(void)
0x18017d340  lea     rcx, [rsp+318h+var_2F8]
0x18017d345  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(void)
0x18017d34a  nop
0x18017d34b  mov     [rsp+318h+string], r13
0x18017d350  mov     rcx, [rsi+48h]
0x18017d354  lea     rdx, [rsp+318h+var_2F8]
0x18017d359  mov     rcx, [rcx]
0x18017d35c  call    ?GetTileIdentifier@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetTileIdentifier(void)
0x18017d361  nop
0x18017d362  mov     rdi, qword ptr [rsp+318h+var_2F8]
0x18017d367  mov     rax, [rdi]
0x18017d36a  mov     rbx, [rax+48h]
0x18017d36e  mov     rcx, [rsp+318h+string]; string
0x18017d373  call    cs:__imp_WindowsDeleteString
0x18017d379  mov     [rsp+318h+string], r13
0x18017d37e  lea     rdx, [rsp+318h+string]
0x18017d383  mov     rcx, rdi
0x18017d386  mov     rax, rbx
0x18017d389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d38e  nop
0x18017d38f  mov     rcx, qword ptr [rsp+318h+var_2F8]
0x18017d394  test    rcx, rcx
0x18017d397  jz      short loc_18017D3A6
0x18017d399  mov     rax, [rcx]
0x18017d39c  mov     rax, [rax+10h]
0x18017d3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d3a5  nop
0x18017d3a6  xor     edx, edx; length
0x18017d3a8  mov     rcx, [rsp+318h+string]; string
0x18017d3ad  call    cs:__imp_WindowsGetStringRawBuffer
0x18017d3b3  mov     r15, rax
0x18017d3b6  mov     rbx, qword ptr [rsp+318h+var_270]
0x18017d3be  mov     qword ptr [rsp+318h+var_2F8], rbx
0x18017d3c3  test    rbx, rbx
0x18017d3c6  jz      short loc_18017D3CF
0x18017d3c8  lock inc dword ptr [rbx+158h]
0x18017d3cf  lea     rcx, [rbx+8]
0x18017d3d3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18017d3d8  nop
0x18017d3d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18017d3dd  mov     r8, rdi
0x18017d3e0  inc     r8
0x18017d3e3  cmp     [r15+r8*2], r13w
0x18017d3e8  jnz     short loc_18017D3E0
0x18017d3ea  lea     rcx, [rbx+138h]
0x18017d3f1  mov     rdx, r15
0x18017d3f4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18017d3f9  nop
0x18017d3fa  test    rbx, rbx
0x18017d3fd  jz      short loc_18017D412
0x18017d3ff  lea     rcx, [rbx+8]
0x18017d403  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18017d408  lea     rcx, [rsp+318h+var_2F8]
0x18017d40d  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::reset(void)
0x18017d412  lea     rcx, [rsp+318h+var_2F8]
0x18017d417  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(void)
0x18017d41c  mov     [rsp+318h+var_2E8], r13
0x18017d421  mov     rax, [rsi+58h]
0x18017d425  cmp     [rax+10h], r13
0x18017d429  jz      loc_18017D55E
0x18017d42f  lea     rcx, [rsp+318h+var_2E8]
0x18017d434  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d439  mov     rax, [rsi+58h]
0x18017d43d  cmp     qword ptr [rax+18h], 7
0x18017d442  jbe     short loc_18017D447
0x18017d444  mov     rax, [rax]
0x18017d447  mov     qword ptr [rsp+318h+var_2F8], rax
0x18017d44c  lea     rdx, [rsp+318h+var_2F8]
0x18017d451  lea     rcx, [rsp+318h+var_268]
0x18017d459  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18017d45e  lea     r8, [rsp+318h+var_2E8]
0x18017d463  mov     rdx, [rax+18h]
0x18017d467  mov     rcx, [rsi+68h]
0x18017d46b  call    _anonymous_namespace___LoadStreamFromFile
0x18017d470  mov     r14d, eax
0x18017d473  mov     rbx, qword ptr [rsp+318h+var_270]
0x18017d47b  mov     qword ptr [rsp+318h+var_2F8], rbx
0x18017d480  test    rbx, rbx
0x18017d483  jz      short loc_18017D48C
0x18017d485  lock inc dword ptr [rbx+158h]
0x18017d48c  lea     rcx, [rbx+8]
0x18017d490  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18017d495  mov     [rbx+114h], r14d
0x18017d49c  lea     rcx, [rsp+318h+var_2F8]
0x18017d4a1  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d4a6  mov     rbx, qword ptr [rsp+318h+var_270]
0x18017d4ae  mov     qword ptr [rsp+318h+var_2F8], rbx
0x18017d4b3  test    rbx, rbx
0x18017d4b6  jz      short loc_18017D4BF
0x18017d4b8  lock inc dword ptr [rbx+158h]
0x18017d4bf  lea     rcx, [rbx+8]
0x18017d4c3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18017d4c8  mov     ebx, [rbx+114h]
0x18017d4ce  shr     ebx, 1Fh
0x18017d4d1  lea     rcx, [rsp+318h+var_2F8]
0x18017d4d6  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d4db  test    bl, bl
0x18017d4dd  jz      loc_18017D5A4
0x18017d4e3  mov     rcx, [rsi+58h]
0x18017d4e7  cmp     qword ptr [rcx+18h], 7
0x18017d4ec  jbe     short loc_18017D4F1
0x18017d4ee  mov     rcx, [rcx]; pszPath
0x18017d4f1  mov     r8d, 104h; cchBuf
0x18017d4f7  lea     rdx, [rsp+318h+pszBuf]; pszBuf
0x18017d4ff  call    cs:__imp_PathUnExpandEnvStringsW
0x18017d505  mov     rbx, qword ptr [rsp+318h+var_270]
0x18017d50d  mov     qword ptr [rsp+318h+var_2F8], rbx
0x18017d512  test    rbx, rbx
0x18017d515  jz      short loc_18017D51E
0x18017d517  lock inc dword ptr [rbx+158h]
0x18017d51e  lea     rcx, [rbx+8]
0x18017d522  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18017d527  nop
0x18017d528  lea     rax, [rsp+318h+pszBuf]
0x18017d530  inc     rdi
0x18017d533  cmp     [rax+rdi*2], r13w
0x18017d538  jnz     short loc_18017D530
0x18017d53a  lea     rcx, [rbx+118h]
0x18017d541  mov     r8, rdi
0x18017d544  lea     rdx, [rsp+318h+pszBuf]
0x18017d54c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18017d551  nop
0x18017d552  lea     rcx, [rsp+318h+var_2F8]
0x18017d557  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_data_control<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d55c  jmp     short loc_18017D5A4
0x18017d55e  mov     rdi, qword ptr [rsp+318h+var_270]
0x18017d566  mov     qword ptr [rsp+318h+var_2F8], rdi; int
0x18017d56b  test    rdi, rdi
0x18017d56e  jz      short loc_18017D577
0x18017d570  lock inc dword ptr [rdi+158h]
0x18017d577  lea     rcx, [rdi+8]
0x18017d57b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18017d580  mov     byte ptr [rdi+110h], 1
0x18017d587  lea     rcx, [rdi+8]
0x18017d58b  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18017d590  lea     rcx, [rsp+318h+var_2F8]
0x18017d595  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::reset(void)
0x18017d59a  lea     rcx, [rsp+318h+var_2F8]
0x18017d59f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>,wil::err_returncode_policy>(void)
0x18017d5a4  mov     [rsp+318h+var_2B8], r13
0x18017d5a9  mov     rcx, [rsp+318h+var_2E8]
0x18017d5ae  test    rcx, rcx
0x18017d5b1  jz      short loc_18017D5D3
0x18017d5b3  mov     rax, [rcx]
0x18017d5b6  lea     rdx, [rsp+318h+var_2B8]
0x18017d5bb  mov     rax, [rax+30h]
0x18017d5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d5c4  test    eax, eax
0x18017d5c6  js      short loc_18017D5D3
0x18017d5c8  cmp     [rsp+318h+var_2B8], r13
0x18017d5cd  jnz     loc_18017D8DF
0x18017d5d3  mov     [rsp+318h+var_2E0], r13
0x18017d5d8  lea     rcx, [rsp+318h+var_2E0]
0x18017d5dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d5e2  lea     r9, [rsp+318h+var_2E0]; struct Windows::ApplicationModel::Resources::Core::IResourceMap **
0x18017d5e7  lea     rdx, aFiles; "Files"
0x18017d5ee  lea     rcx, aWindowsShellco; "Windows.ShellCommon.SharedResources"
0x18017d5f5  call    ?GetSystemProfileResourceMap@@YAJPEBG0PEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@PEAPEAUIResourceMap@2345@@Z; GetSystemProfileResourceMap(ushort const *,ushort const *,Windows::ApplicationModel::Resources::Core::IResourceManager * *,Windows::ApplicationModel::Resources::Core::IResourceMap * *)
0x18017d5fa  mov     ebx, eax
0x18017d5fc  test    eax, eax
0x18017d5fe  jns     short loc_18017D654
0x18017d600  mov     rcx, [rsp+318h]; this
0x18017d608  mov     r9d, eax; char *
0x18017d60b  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18017d612  mov     edx, 2BDh; void *
0x18017d617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017d61c  nop
0x18017d61d  lea     rcx, [rsp+318h+var_2E0]
0x18017d622  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d627  nop
0x18017d628  lea     rcx, [rsp+318h+var_2E8]
0x18017d62d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d632  nop
0x18017d633  mov     rcx, [rsp+318h+string]; string
0x18017d638  call    cs:__imp_WindowsDeleteString
0x18017d63e  mov     [rsp+318h+string], r13
0x18017d643  lea     rcx, [rsp+318h+var_2A8]
0x18017d648  call    ??1?$test_watcher@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d64d  mov     eax, ebx
0x18017d64f  jmp     loc_18017D94A
0x18017d654  mov     [rsp+318h+var_2D8], r13
0x18017d659  mov     rdi, [rsp+318h+var_2E0]
0x18017d65e  mov     rax, [rdi]
0x18017d661  mov     rbx, [rax+38h]
0x18017d665  lea     rcx, [rsp+318h+var_2D8]
0x18017d66a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d66f  lea     rdx, off_1803F5590; "Images\\SmallPlaceholder-20.png"
0x18017d676  lea     rcx, [rsp+318h+var_268]
0x18017d67e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18017d683  nop
0x18017d684  lea     r8, [rsp+318h+var_2D8]
0x18017d689  mov     rdx, [rax+18h]
0x18017d68d  mov     rcx, rdi
0x18017d690  mov     rax, rbx
0x18017d693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d698  mov     ebx, eax
0x18017d69a  test    eax, eax
0x18017d69c  jns     short loc_18017D6FD
0x18017d69e  mov     rcx, [rsp+318h]; this
0x18017d6a6  mov     r9d, eax; char *
0x18017d6a9  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18017d6b0  mov     edx, 2C0h; void *
0x18017d6b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017d6ba  nop
0x18017d6bb  lea     rcx, [rsp+318h+var_2D8]
0x18017d6c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d6c5  nop
0x18017d6c6  lea     rcx, [rsp+318h+var_2E0]
0x18017d6cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d6d0  nop
0x18017d6d1  lea     rcx, [rsp+318h+var_2E8]
0x18017d6d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d6db  nop
0x18017d6dc  mov     rcx, [rsp+318h+string]; string
0x18017d6e1  call    cs:__imp_WindowsDeleteString
0x18017d6e7  mov     [rsp+318h+string], r13
0x18017d6ec  lea     rcx, [rsp+318h+var_2A8]
0x18017d6f1  call    ??1?$test_watcher@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d6f6  mov     eax, ebx
0x18017d6f8  jmp     loc_18017D94A
0x18017d6fd  mov     [rsp+318h+var_2D0], r13
0x18017d702  mov     rbx, [rsp+318h+var_2D8]
0x18017d707  mov     rax, [rbx]
0x18017d70a  mov     rdi, [rax]
0x18017d70d  lea     rcx, [rsp+318h+var_2D0]
0x18017d712  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d717  lea     r8, [rsp+318h+var_2D0]
0x18017d71c  lea     rdx, _GUID_69e5b468_f6fc_4013_aaa2_d53f1757d3b5
0x18017d723  mov     rcx, rbx
0x18017d726  mov     rax, rdi
0x18017d729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d72e  mov     ebx, eax
0x18017d730  test    eax, eax
0x18017d732  jns     short loc_18017D79E
0x18017d734  mov     rcx, [rsp+318h]; this
0x18017d73c  mov     r9d, eax; char *
0x18017d73f  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18017d746  mov     edx, 2C3h; void *
0x18017d74b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017d750  nop
0x18017d751  lea     rcx, [rsp+318h+var_2D0]
0x18017d756  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d75b  nop
0x18017d75c  lea     rcx, [rsp+318h+var_2D8]
0x18017d761  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d766  nop
0x18017d767  lea     rcx, [rsp+318h+var_2E0]
0x18017d76c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d771  nop
0x18017d772  lea     rcx, [rsp+318h+var_2E8]
0x18017d777  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d77c  nop
0x18017d77d  mov     rcx, [rsp+318h+string]; string
0x18017d782  call    cs:__imp_WindowsDeleteString
0x18017d788  mov     [rsp+318h+string], r13
0x18017d78d  lea     rcx, [rsp+318h+var_2A8]
0x18017d792  call    ??1?$test_watcher@V?$merged_data@U_tip_PlaceholderTileLogoLoadingTest@UnifiedTile@Shell@WindowsInternal@@U1234@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>::~test_watcher<tip2::details::merged_data<WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest,WindowsInternal::Shell::UnifiedTile::_tip_PlaceholderTileLogoLoadingTest>>(void)
0x18017d797  mov     eax, ebx
0x18017d799  jmp     loc_18017D94A
0x18017d79e  mov     [rsp+318h+var_2C8], r13
0x18017d7a3  mov     rdi, [rsp+318h+var_2D0]
0x18017d7a8  mov     rax, [rdi]
0x18017d7ab  mov     rbx, [rax+30h]
0x18017d7af  lea     rcx, [rsp+318h+var_2C8]
0x18017d7b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d7b9  lea     rdx, [rsp+318h+var_2C8]
0x18017d7be  mov     rcx, rdi
0x18017d7c1  mov     rax, rbx
0x18017d7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d7c9  mov     ebx, eax
0x18017d7cb  test    eax, eax
0x18017d7cd  jns     short loc_18017D844
0x18017d7cf  mov     rcx, [rsp+318h]; this
0x18017d7d7  mov     r9d, eax; char *
0x18017d7da  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18017d7e1  mov     edx, 2C6h; void *
0x18017d7e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017d7eb  nop
0x18017d7ec  lea     rcx, [rsp+318h+var_2C8]
0x18017d7f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017d7f6  nop
  ... truncated ...
```
