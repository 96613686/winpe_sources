# DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileUninstallVerb::Execute(WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *)

- ea: `0x1801540a0`
- end: `0x18015465e`
- name: `?Execute@PlaceholderTileUninstallVerb@Internal@PlaceholderTileTransformer@DataStoreCache@@UEAAJPEAUIVerbExecutionArgs@UnifiedTile@Shell@WindowsInternal@@@Z`
- size: `1470`
- prototype: `__int64 __fastcall(DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileUninstallVerb *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18000ee88`
- `0x18001ac50`
- `0x18001dac0`
- `0x1800285c4`
- `0x18002ca10`
- `0x180040d88`
- `0x18004ffc0`
- `0x1800756e4`
- `0x18007ae80`
- `0x1800f0ef4`
- `0x1800ffc20`
- `0x180128b6c`
- `0x18014e3d8`
- `0x180152f24`
- `0x1801540a0`
- `0x180154664`
- `0x18015469c`
- `0x1801546d8`
- `0x180154850`
- `0x180161204`
- `0x18017da60`
- `0x180185548`
- `0x180201e50`
- `0x18035c590`
- `0x18035e760`
- `0x18035e7d4`
- `0x180360400`
- `0x180360548`
- `0x1803636a0`
- `0x180366428`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801541a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015448e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015453c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801541a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015448e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015453c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801541cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801544db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015456c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801541cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801544db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015456c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154592`

## string_xrefs

- `0x180154205`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x18015422b`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x180154263`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801542a2`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x18015435f`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801544b8`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801542f1`: `placeholderTileTransformer_UninstallVerb`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileUninstallVerb::Execute(
        DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileUninstallVerb *this,
        struct WindowsInternal::Shell::UnifiedTile::IVerbExecutionArgs *a2,
        __int64 a3)
{
  _QWORD *v4; // rax
  void *v5; // rcx
  _QWORD *v6; // r14
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  HSTRING v14; // rdi
  __int64 (__fastcall *v15)(HSTRING, _QWORD **, __int64); // rbx
  int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // rdx
  int PlaceholderOrigin; // edi
  int RestorePolicyBehaviorFlags; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v25; // eax
  wil *v26; // rcx
  PCWSTR v27; // rax
  __int64 v28; // rbx
  _QWORD *v29; // rax
  unsigned int v31; // ebx
  int v32; // [rsp+20h] [rbp-D8h]
  int v33[2]; // [rsp+20h] [rbp-D8h] BYREF
  HSTRING v34; // [rsp+28h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-C8h] BYREF
  int v36; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B0h] BYREF
  int v39; // [rsp+50h] [rbp-A8h] BYREF
  PCWSTR v40; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD *v41; // [rsp+60h] [rbp-98h] BYREF
  std::_Ref_count_base *v42; // [rsp+68h] [rbp-90h]
  int CatalogSource; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v44[4]; // [rsp+74h] [rbp-84h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-80h] BYREF
  __int64 v46; // [rsp+90h] [rbp-68h]
  void **v47; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v48[48]; // [rsp+A0h] [rbp-58h] BYREF
  HSTRING v49; // [rsp+D0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  pv = 0;
  string = 0;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
    a2,
    a3);
  v34 = 0;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::ensure_data(&v34);
  tip2::details::shared_data<0,0,0>::start(*v4 + 8LL, &v41);
  v47 = &tip2::test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v48,
    (struct wil::details::IFailureCallback *)&v47,
    0,
    1);
  v49 = v34;
  if ( v34 )
    _InterlockedIncrement((volatile signed __int32 *)v34 + 82);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>(&v34);
  v5 = pv;
  pv = v49;
  if ( v49 )
    _InterlockedIncrement((volatile signed __int32 *)v49 + 82);
  if ( v5 )
    tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>::Release(v5);
  tip2::test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(&v47);
  v6 = (_QWORD *)((char *)this + 144);
  v40 = (PCWSTR)((char *)this + 144);
  v7 = *((_QWORD *)this + 18);
  v8 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v7 + 72LL);
  WindowsDeleteString(string);
  string = 0;
  if ( v8(v7, &string) >= 0 )
  {
    *(_QWORD *)v33 = WindowsGetStringRawBuffer(string, 0);
    StartPlaceHolderTelemetry::PlaceholderTileUninstallStarted<unsigned short const *>(v33);
  }
  v37 = 0;
  v9 = Microsoft::WRL::WeakRef::As<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>(
         (char *)this + 152,
         &v37);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F0,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)v9,
      v33[0]);
  if ( !v37 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F1,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)0x8007139FLL,
      v33[0]);
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v6 + 48LL))(*v6, &v39);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F4,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)v10,
      v33[0]);
  if ( v39 == 1 )
  {
    v34 = 0;
    v13 = Microsoft::WRL::ComPtr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>::As<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal>(
            &v37,
            &v34);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F9,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v13,
        v33[0]);
    (*(void (__fastcall **)(__int64, _QWORD **, _QWORD))(*(_QWORD *)v37 + 136LL))(v37, &v41, *v6);
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(HSTRING, _QWORD **, __int64))(*(_QWORD *)v34 + 264LL);
    v46 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"placeholderTileTransformer_UninstallVerb",
      0x29u,
      0x28u);
    v16 = v15(v14, &v41, v46);
    LOBYTE(v17) = 3;
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
      v18,
      v17);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                             &pv,
                             v33)
              + 324LL) = v16;
    tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(v33);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x602,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v16,
        v33[0]);
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  }
  LOBYTE(v12) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
    v11,
    v12);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 160LL))(v37, *v6) )
  {
    (*(void (__fastcall **)(__int64, _QWORD **, _QWORD))(*(_QWORD *)v37 + 136LL))(v37, &v41, *v6);
    PlaceholderOrigin = DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetPlaceholderOrigin(*v41);
    v36 = PlaceholderOrigin;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                             &pv,
                             v33)
              + 272LL) = PlaceholderOrigin;
    tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(v33);
    CatalogSource = DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetCatalogSource(*v41);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                             &pv,
                             v33)
              + 276LL) = CatalogSource;
    tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(v33);
    RestorePolicyBehaviorFlags = DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetRestorePolicyBehaviorFlags(*v41);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                             &pv,
                             v33)
              + 280LL) = RestorePolicyBehaviorFlags;
    tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(v33);
    if ( PlaceholderOrigin == 2 )
    {
      v34 = 0;
      v21 = *v6;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v6 + 56LL);
      WindowsDeleteString(0);
      try
      {
        v34 = 0;
        v23 = v22(v21, &v34);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x617,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholder"
                          "tiletransformer.cpp",
            (const char *)(unsigned int)v23,
            v33[0]);
        winrt::impl::call_factory_cast<winrt::Windows::Internal::Shell::AppRestore::RestorableTilesStore (*)(winrt::Windows::Internal::Shell::AppRestore::IRestorableTileItemsManagerStatics const &),winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::IRestorableTileItemsManagerStatics,_lambda_307fc4b1d6629a6f5ee6399fd0bc73d9_>(v33);
        StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
        winrt::param::hstring::hstring((winrt::param::hstring *)&v47, StringRawBuffer);
        LODWORD(hstringHeader.Reserved.Reserved1) = 0;
        *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        v25 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)v33 + 64LL))(*(_QWORD *)v33, v47);
        winrt::check_hresult(v44, v25, &hstringHeader);
        winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)v33);
        WindowsDeleteString(v34);
      }
      catch ( ... )
      {
        v31 = wil::ResultFromCaughtException(v26);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x61E,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholderti"
                        "letransformer.cpp",
          (const char *)v31,
          v32);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                                 &pv,
                                 v33)
                  + 320LL) = v31;
        tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(v33);
        v6 = v40;
      }
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 112LL))(v37, *v6);
    if ( string )
    {
      v40 = WindowsGetStringRawBuffer(string, 0);
      StartPlaceHolderTelemetry::PlaceholderTileUninstalled<unsigned short const *,enum DataStoreCache::PlaceholderTileTransformer::PlaceholderOriginType &,enum winrt::Windows::Internal::Shell::AppRestore::CatalogSource const &>(
        &v40,
        &v36,
        &CatalogSource);
      v27 = WindowsGetStringRawBuffer(string, 0);
      v28 = std::wstring::wstring(&v47, v27);
      v29 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(
                        &pv,
                        &v40);
      std::wstring::operator=(*v29 + 288LL, v28);
      tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(&v40);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&v47);
    }
    if ( v42 )
      std::_Ref_count_base::_Decref(v42);
  }
  if ( pv )
    tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>(&pv);
  return 0;
}

```

## disassembly

```asm
0x1801540a0  mov     [rsp+arg_8], rbx
0x1801540a5  mov     [rsp+arg_10], rsi
0x1801540aa  push    rdi
0x1801540ab  push    r14
0x1801540ad  push    r15
0x1801540af  sub     rsp, 0E0h
0x1801540b6  mov     rax, cs:__security_cookie
0x1801540bd  xor     rax, rsp
0x1801540c0  mov     [rsp+0F8h+var_20], rax
0x1801540c8  mov     r15, rcx
0x1801540cb  xor     esi, esi
0x1801540cd  mov     [rsp+0F8h+pv], rsi
0x1801540d2  mov     [rsp+0F8h+string], rsi
0x1801540d7  mov     r8b, 3
0x1801540da  mov     dl, 1
0x1801540dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders> `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl(void)'::`2'::impl
0x1801540e3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801540e8  mov     [rsp+0F8h+var_D0], rsi
0x1801540ed  lea     rcx, [rsp+0F8h+var_D0]
0x1801540f2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::ensure_data(void)
0x1801540f7  mov     rcx, [rax]
0x1801540fa  add     rcx, 8
0x1801540fe  lea     rdx, [rsp+0F8h+var_98]
0x180154103  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180154108  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::`vftable'
0x18015410f  mov     [rsp+0F8h+var_60], rax
0x180154117  mov     r9b, 1; bool
0x18015411a  xor     r8d, r8d; struct wil::CallContextInfo *
0x18015411d  lea     rdx, [rsp+0F8h+var_60]; struct wil::details::IFailureCallback *
0x180154125  lea     rcx, [rsp+0F8h+var_58]; this
0x18015412d  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180154132  mov     rax, [rsp+0F8h+var_D0]
0x180154137  mov     [rsp+0F8h+var_28], rax
0x18015413f  test    rax, rax
0x180154142  jz      short loc_18015414B
0x180154144  lock inc dword ptr [rax+148h]
0x18015414b  lea     rcx, [rsp+0F8h+var_D0]
0x180154150  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>,wil::err_returncode_policy>(void)
0x180154155  mov     rax, [rsp+0F8h+var_28]
0x18015415d  mov     rcx, [rsp+0F8h+pv]; pv
0x180154162  mov     [rsp+0F8h+pv], rax
0x180154167  test    rax, rax
0x18015416a  jz      short loc_180154173
0x18015416c  lock inc dword ptr [rax+148h]
0x180154173  test    rcx, rcx
0x180154176  jz      short loc_18015417D
0x180154178  call    ?Release@?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>::Release(void)
0x18015417d  lea     rcx, [rsp+0F8h+var_60]
0x180154185  call    ??1?$test_watcher@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_watcher<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x18015418a  lea     r14, [r15+90h]
0x180154191  mov     [rsp+0F8h+var_A0], r14
0x180154196  mov     rdi, [r14]
0x180154199  mov     rax, [rdi]
0x18015419c  mov     rbx, [rax+48h]
0x1801541a0  mov     rcx, [rsp+0F8h+string]; string
0x1801541a5  call    cs:__imp_WindowsDeleteString
0x1801541ab  mov     [rsp+0F8h+string], rsi
0x1801541b0  lea     rdx, [rsp+0F8h+string]
0x1801541b5  mov     rcx, rdi
0x1801541b8  mov     rax, rbx
0x1801541bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801541c0  test    eax, eax
0x1801541c2  js      short loc_1801541E0
0x1801541c4  xor     edx, edx; length
0x1801541c6  mov     rcx, [rsp+0F8h+string]; string
0x1801541cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1801541d1  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1801541d6  lea     rcx, [rsp+0F8h+var_D8]
0x1801541db  call    ??$PlaceholderTileUninstallStarted@PEBG@StartPlaceHolderTelemetry@@SAX$$QEAPEBG@Z; StartPlaceHolderTelemetry::PlaceholderTileUninstallStarted<ushort const *>(ushort const * &&)
0x1801541e0  mov     [rsp+0F8h+var_B8], rsi
0x1801541e5  lea     rcx, [r15+98h]
0x1801541ec  lea     rdx, [rsp+0F8h+var_B8]
0x1801541f1  call    ??$As@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>>)
0x1801541f6  mov     rcx, [rsp+0F8h]; this
0x1801541fe  test    eax, eax
0x180154200  jns     short loc_180154216
0x180154202  mov     r9d, eax; char *
0x180154205  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x18015420c  mov     edx, 5F0h; void *
0x180154211  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180154216  mov     rcx, [rsp+0F8h]; this
0x18015421e  cmp     [rsp+0F8h+var_B8], rsi
0x180154223  jnz     short loc_18015423C
0x180154225  mov     r9d, 8007139Fh; char *
0x18015422b  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x180154232  mov     edx, 5F1h; void *
0x180154237  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015423c  mov     [rsp+0F8h+var_A8], esi
0x180154240  mov     rcx, [r14]
0x180154243  mov     rax, [rcx]
0x180154246  lea     rdx, [rsp+0F8h+var_A8]
0x18015424b  mov     rax, [rax+30h]
0x18015424f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154254  mov     rcx, [rsp+0F8h]; this
0x18015425c  test    eax, eax
0x18015425e  jns     short loc_180154274
0x180154260  mov     r9d, eax; char *
0x180154263  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x18015426a  mov     edx, 5F4h; void *
0x18015426f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180154274  cmp     [rsp+0F8h+var_A8], 1
0x180154279  jnz     loc_18015438B
0x18015427f  mov     [rsp+0F8h+var_D0], rsi
0x180154284  lea     rdx, [rsp+0F8h+var_D0]
0x180154289  lea     rcx, [rsp+0F8h+var_B8]
0x18015428e  call    ??$As@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@@?$ComPtr@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPlaceholderTileTransformerInternal@Internal@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>::As<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::PlaceholderTileTransformer::Internal::IPlaceholderTileTransformerInternal>>)
0x180154293  mov     rcx, [rsp+0F8h]; this
0x18015429b  test    eax, eax
0x18015429d  jns     short loc_1801542B3
0x18015429f  mov     r9d, eax; char *
0x1801542a2  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801542a9  mov     edx, 5F9h; void *
0x1801542ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801542b3  mov     rcx, [rsp+0F8h+var_B8]
0x1801542b8  mov     rax, [rcx]
0x1801542bb  mov     r8, [r14]
0x1801542be  lea     rdx, [rsp+0F8h+var_98]
0x1801542c3  mov     rax, [rax+88h]
0x1801542ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801542cf  nop
0x1801542d0  mov     rdi, [rsp+0F8h+var_D0]
0x1801542d5  mov     rax, [rdi]
0x1801542d8  mov     rbx, [rax+108h]
0x1801542df  mov     [rsp+0F8h+var_68], rsi
0x1801542e7  mov     r9d, 28h ; '('; unsigned int
0x1801542ed  lea     r8d, [r9+1]; unsigned int
0x1801542f1  lea     rdx, aPlaceholdertil_75; "placeholderTileTransformer_UninstallVer"...
0x1801542f8  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x1801542fd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180154302  nop
0x180154303  mov     r8, [rsp+0F8h+var_68]
0x18015430b  lea     rdx, [rsp+0F8h+var_98]
0x180154310  mov     rcx, rdi
0x180154313  mov     rax, rbx
0x180154316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015431b  mov     ebx, eax
0x18015431d  mov     r8b, 3
0x180154320  mov     dl, 1
0x180154322  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders> `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl(void)'::`2'::impl
0x180154329  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18015432e  lea     rdx, [rsp+0F8h+var_D8]
0x180154333  lea     rcx, [rsp+0F8h+pv]
0x180154338  call    ??C?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(void)
0x18015433d  mov     rcx, [rax]
0x180154340  mov     [rcx+144h], ebx
0x180154346  lea     rcx, [rsp+0F8h+var_D8]
0x18015434b  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x180154350  mov     rcx, [rsp+0F8h]; this
0x180154358  test    ebx, ebx
0x18015435a  jns     short loc_180154371
0x18015435c  mov     r9d, ebx; char *
0x18015435f  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x180154366  mov     edx, 602h; void *
0x18015436b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180154370  nop
0x180154371  mov     rcx, [rsp+0F8h+var_90]; this
0x180154376  test    rcx, rcx
0x180154379  jz      short loc_180154381
0x18015437b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180154380  nop
0x180154381  lea     rcx, [rsp+0F8h+var_D0]
0x180154386  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015438b  mov     r8b, 3
0x18015438e  mov     dl, 1
0x180154390  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders> `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl(void)'::`2'::impl
0x180154397  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18015439c  mov     rcx, [rsp+0F8h+var_B8]
0x1801543a1  mov     rax, [rcx]
0x1801543a4  mov     rdx, [r14]
0x1801543a7  mov     rax, [rax+0A0h]
0x1801543ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801543b3  test    al, al
0x1801543b5  jz      loc_1801545F3
0x1801543bb  mov     rcx, [rsp+0F8h+var_B8]
0x1801543c0  mov     rax, [rcx]
0x1801543c3  mov     r8, [r14]
0x1801543c6  lea     rdx, [rsp+0F8h+var_98]
0x1801543cb  mov     rax, [rax+88h]
0x1801543d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801543d7  nop
0x1801543d8  mov     rcx, [rsp+0F8h+var_98]
0x1801543dd  mov     rcx, [rcx]
0x1801543e0  call    ?GetPlaceholderOrigin@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AW4PlaceholderOriginType@23@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetPlaceholderOrigin(void)
0x1801543e5  mov     edi, eax
0x1801543e7  mov     [rsp+0F8h+var_C0], eax
0x1801543eb  lea     rdx, [rsp+0F8h+var_D8]
0x1801543f0  lea     rcx, [rsp+0F8h+pv]
0x1801543f5  call    ??C?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(void)
0x1801543fa  mov     rcx, [rax]
0x1801543fd  mov     [rcx+110h], edi
0x180154403  lea     rcx, [rsp+0F8h+var_D8]
0x180154408  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x18015440d  mov     rcx, [rsp+0F8h+var_98]
0x180154412  mov     rcx, [rcx]
0x180154415  call    ?GetCatalogSource@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AW4CatalogSource@AppRestore@Shell@Internal@Windows@winrt@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetCatalogSource(void)
0x18015441a  mov     ebx, eax
0x18015441c  mov     [rsp+0F8h+var_88], eax
0x180154420  lea     rdx, [rsp+0F8h+var_D8]
0x180154425  lea     rcx, [rsp+0F8h+pv]
0x18015442a  call    ??C?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(void)
0x18015442f  mov     rcx, [rax]
0x180154432  mov     [rcx+114h], ebx
0x180154438  lea     rcx, [rsp+0F8h+var_D8]
0x18015443d  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x180154442  mov     rcx, [rsp+0F8h+var_98]
0x180154447  mov     rcx, [rcx]
0x18015444a  call    ?GetRestorePolicyBehaviorFlags@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AW4RestorePolicyBehavior@AppRestore@Shell@Internal@Windows@winrt@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetRestorePolicyBehaviorFlags(void)
0x18015444f  mov     ebx, eax
0x180154451  lea     rdx, [rsp+0F8h+var_D8]
0x180154456  lea     rcx, [rsp+0F8h+pv]
0x18015445b  call    ??C?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(void)
0x180154460  mov     rcx, [rax]
0x180154463  mov     [rcx+118h], ebx
0x180154469  lea     rcx, [rsp+0F8h+var_D8]
0x18015446e  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x180154473  nop
0x180154474  cmp     edi, 2
0x180154477  jnz     loc_180154543
0x18015447d  mov     [rsp+0F8h+var_D0], rsi
0x180154482  mov     rdi, [r14]
0x180154485  mov     rax, [rdi]
0x180154488  mov     rbx, [rax+38h]
0x18015448c  xor     ecx, ecx; string
0x18015448e  call    cs:__imp_WindowsDeleteString
0x180154494  mov     [rsp+0F8h+var_D0], rsi
0x180154499  lea     rdx, [rsp+0F8h+var_D0]
0x18015449e  mov     rcx, rdi
0x1801544a1  mov     rax, rbx
0x1801544a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801544a9  mov     rcx, [rsp+0F8h]; this
0x1801544b1  test    eax, eax
0x1801544b3  jns     short loc_1801544C9
0x1801544b5  mov     r9d, eax; char *
0x1801544b8  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801544bf  mov     edx, 617h; void *
0x1801544c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801544c9  lea     rcx, [rsp+0F8h+var_D8]
0x1801544ce  call    ??$call_factory_cast@P6A?AURestorableTilesStore@AppRestore@Shell@Internal@Windows@winrt@@AEBUIRestorableTileItemsManagerStatics@23456@@ZURestorableTileItemsManager@23456@U723456@V_lambda_307fc4b1d6629a6f5ee6399fd0bc73d9_@@@impl@winrt@@YA?A_P$$QEAV_lambda_307fc4b1d6629a6f5ee6399fd0bc73d9_@@@Z
0x1801544d3  nop
0x1801544d4  xor     edx, edx; length
0x1801544d6  mov     rcx, [rsp+0F8h+var_D0]; string
0x1801544db  call    cs:__imp_WindowsGetStringRawBuffer
0x1801544e1  mov     rdx, rax; unsigned __int16 *
0x1801544e4  lea     rcx, [rsp+0F8h+var_60]; this
0x1801544ec  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801544f1  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x1801544f6  mov     dword ptr [rsp+0F8h+hstringHeader.Reserved], esi
0x1801544fa  xorps   xmm0, xmm0
0x1801544fd  movdqu  xmmword ptr [rsp+0F8h+hstringHeader.Reserved+8], xmm0
0x180154506  mov     rax, [rcx]
0x180154509  mov     rdx, [rsp+0F8h+var_60]
0x180154511  mov     rax, [rax+40h]
0x180154515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015451a  lea     r8, [rsp+0F8h+hstringHeader]
0x18015451f  mov     edx, eax
0x180154521  lea     rcx, [rsp+0F8h+var_84]
0x180154526  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18015452b  nop
0x18015452c  lea     rcx, [rsp+0F8h+var_D8]; this
0x180154531  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x180154536  nop
0x180154537  mov     rcx, [rsp+0F8h+var_D0]; string
0x18015453c  call    cs:__imp_WindowsDeleteString
0x180154542  nop
0x180154543  jmp     short loc_18015454C
0x180154545  xor     esi, esi
0x180154547  mov     r14, [rsp+0F8h+var_A0]
0x18015454c  mov     rcx, [rsp+0F8h+var_B8]
0x180154551  mov     rax, [rcx]
0x180154554  mov     rdx, [r14]
0x180154557  mov     rax, [rax+70h]
0x18015455b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154560  mov     rcx, [rsp+0F8h+string]; string
0x180154565  test    rcx, rcx
0x180154568  jz      short loc_1801545E4
0x18015456a  xor     edx, edx; length
0x18015456c  call    cs:__imp_WindowsGetStringRawBuffer
0x180154572  mov     [rsp+0F8h+var_A0], rax
0x180154577  lea     r8, [rsp+0F8h+var_88]
0x18015457c  lea     rdx, [rsp+0F8h+var_C0]
0x180154581  lea     rcx, [rsp+0F8h+var_A0]
0x180154586  call    ??$PlaceholderTileUninstalled@PEBGAEAW4PlaceholderOriginType@PlaceholderTileTransformer@DataStoreCache@@AEBW4CatalogSource@AppRestore@Shell@Internal@Windows@winrt@@@StartPlaceHolderTelemetry@@SAX$$QEAPEBGAEAW4PlaceholderOriginType@PlaceholderTileTransformer@DataStoreCache@@AEBW4CatalogSource@AppRestore@Shell@Internal@Windows@winrt@@@Z; StartPlaceHolderTelemetry::PlaceholderTileUninstalled<ushort const *,DataStoreCache::PlaceholderTileTransformer::PlaceholderOriginType &,winrt::Windows::Internal::Shell::AppRestore::CatalogSource const &>(ushort const * &&,DataStoreCache::PlaceholderTileTransformer::PlaceholderOriginType &,winrt::Windows::Internal::Shell::AppRestore::CatalogSource const &)
0x18015458b  xor     edx, edx; length
0x18015458d  mov     rcx, [rsp+0F8h+string]; string
0x180154592  call    cs:__imp_WindowsGetStringRawBuffer
0x180154598  mov     rdx, rax
0x18015459b  lea     rcx, [rsp+0F8h+var_60]
0x1801545a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801545a8  mov     rbx, rax
0x1801545ab  lea     rdx, [rsp+0F8h+var_A0]
0x1801545b0  lea     rcx, [rsp+0F8h+pv]
0x1801545b5  call    ??C?$tip_test@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::operator->(void)
0x1801545ba  mov     rcx, [rax]
0x1801545bd  add     rcx, 120h
0x1801545c4  mov     rdx, rbx
0x1801545c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801545cc  lea     rcx, [rsp+0F8h+var_A0]
0x1801545d1  call    ??1?$test_data_control@V?$merged_data@U_tip_PlaceholderTileUninstalledTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>::~test_data_control<tip2::details::merged_data<_tip_PlaceholderTileUninstalledTest,_tip_PlaceholderTileUninstalledTest>>(void)
0x1801545d6  lea     rcx, [rsp+0F8h+var_60]; void *
0x1801545de  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
  ... truncated ...
```
