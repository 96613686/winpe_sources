# DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::InstallApp(std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile> const &,HSTRING__ *,uint,Windows::Foundation::Collections::IPropertySet *,StartPlaceHolderTelemetry::PlaceholderTileActivated &)

- ea: `0x1801fa4a0`
- end: `0x1801fac4c`
- name: `?InstallApp@PlaceholderTileTransformer@Internal@1DataStoreCache@@UEAAJAEBV?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@std@@PEAUHSTRING__@@IPEAUIPropertySet@Collections@Foundation@Windows@@AEAVPlaceholderTileActivated@StartPlaceHolderTelemetry@@@Z`
- size: `1964`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, StartPlaceHolderTelemetry::PlaceholderTileActivated *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000afe8`
- `0x18000ce94`
- `0x18001ac50`
- `0x18001aca4`
- `0x1800285c4`
- `0x18002dde0`
- `0x18003153c`
- `0x18004fba8`
- `0x18004ffc0`
- `0x18006fe30`
- `0x180087bd8`
- `0x180128b6c`
- `0x18015cfa4`
- `0x180161204`
- `0x18019c778`
- `0x1801d04f4`
- `0x1801fa4a0`
- `0x1801fac54`
- `0x1801fac74`
- `0x1801fac94`
- `0x1801facb4`
- `0x180201e50`
- `0x18035e25c`
- `0x18035e354`
- `0x1803621fc`
- `0x180362238`
- `0x180362620`
- `0x180362ac4`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa8b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa8c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fabfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fac0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa8b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa8c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fabfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fac0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa7c6`

## string_xrefs

- `0x1801fa5d2`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa64d`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa737`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa813`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa88d`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa958`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa9da`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fab4a`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fabc6`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\placeholdertiletransformer.cpp`
- `0x1801fa861`: `WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.AppInstallBroker`
- `0x1801fa6b2`: `placeholderTileTransformer_InstallVerb`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::InstallApp(
        _QWORD *a1,
        _QWORD **a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        StartPlaceHolderTelemetry::PlaceholderTileActivated *a6)
{
  char v9; // si
  const WCHAR *v10; // rdx
  __int64 PackageFamilyName; // rax
  char v12; // bl
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **TileIdentifier; // rax
  int MainPackageFamilyName; // ebx
  __int64 v15; // rdx
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  int v19; // esi
  __int64 v20; // rdx
  HSTRING_HEADER *v21; // rax
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  int v24; // eax
  bool v25; // si
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  int v31; // edi
  HSTRING_HEADER *v32; // rax
  int v33; // eax
  UINT32 v34; // ebx
  __int64 SkuId; // rax
  const WCHAR *v36; // rdx
  UINT32 v37; // ebx
  __int64 StoreCampaignId; // rax
  const WCHAR *v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rax
  int v43; // eax
  int v44; // edi
  int v45; // eax
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  bool v48[8]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v51; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v52; // [rsp+70h] [rbp-90h]
  const WCHAR *v53; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  _BYTE v58[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v59; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v60; // [rsp+B0h] [rbp-50h] BYREF
  int v61[2]; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER v64; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER v65; // [rsp+110h] [rbp+10h] BYREF
  __int64 v66; // [rsp+128h] [rbp+28h]
  HSTRING_HEADER v67; // [rsp+130h] [rbp+30h] BYREF
  __int64 v68; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v52 = a4;
  v57 = a5;
  v9 = 0;
  LODWORD(v53) = 0;
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(*a2, &v55);
  v10 = (const WCHAR *)v55;
  if ( *(_QWORD *)(v55 + 24) > 7u )
    v10 = *(const WCHAR **)v55;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v60, v10, *(_DWORD *)(v55 + 16));
  string = 0;
  PackageFamilyName = DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetPackageFamilyName(*a2, &v64);
  v12 = 1;
  LODWORD(v53) = 1;
  if ( !*(_QWORD *)(*(_QWORD *)PackageFamilyName + 16LL) )
  {
    v12 = 3;
    if ( !*(_QWORD *)(*(_QWORD *)DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(*a2, v58)
                    + 16LL) )
      v9 = 1;
  }
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    if ( v59 )
      std::_Ref_count_base::_Decref(v59);
  }
  if ( (v12 & 1) != 0 && *(_QWORD *)&v64.Reserved.Reserved2[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v64.Reserved.Reserved2[8]);
  if ( v9 )
  {
    WindowsDeleteString(string);
    string = 0;
    TileIdentifier = (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **)DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetTileIdentifier(
                                                                                              *a2,
                                                                                              &v53);
    MainPackageFamilyName = DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetMainPackageFamilyName(
                              *TileIdentifier,
                              &string);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v53);
    if ( MainPackageFamilyName < 0 )
    {
      v15 = 503;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)MainPackageFamilyName,
        v46);
LABEL_16:
      WindowsDeleteString(string);
      string = 0;
      *(_QWORD *)v61 = 0;
LABEL_17:
      if ( v56 )
        std::_Ref_count_base::_Decref(v56);
      return (unsigned int)MainPackageFamilyName;
    }
  }
  else
  {
    DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetPackageFamilyName(*a2, &v53);
    v17 = v53;
    if ( *((_QWORD *)v53 + 3) > 7u )
      v17 = *(const unsigned __int16 **)v53;
    v18 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)&string,
            v17,
            *((_DWORD *)v53 + 4));
    MainPackageFamilyName = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v18,
        v46);
      if ( v54 )
        std::_Ref_count_base::_Decref(v54);
      goto LABEL_16;
    }
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD **))(*a1 + 272LL))(a1, a2) )
  {
    v48[0] = 0;
    MainPackageFamilyName = DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::IsPackageInstalled(
                              (DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer *)(a1 - 9),
                              string,
                              v48);
    if ( MainPackageFamilyName < 0 )
    {
      v15 = 535;
      goto LABEL_15;
    }
    if ( v48[0] )
    {
      StartPlaceHolderTelemetry::PlaceholderTileActivated::ClickedWhileInstalled(a6);
      if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 4) != 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0z_EventWriteTransfer(
          &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
          AppAlreadyInstalled,
          StringRawBuffer);
      }
      goto LABEL_71;
    }
    v50 = 0;
    WindowsDeleteString(0);
    v50 = 0;
    v24 = Cortana::Common::CorrelationVectorHelper::CreateCorrelationVector(&v50);
    MainPackageFamilyName = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)v24,
        v46);
LABEL_38:
      WindowsDeleteString(v50);
      v50 = 0;
      goto LABEL_16;
    }
    v25 = *(_QWORD *)v61 != 0;
    v51 = 0;
    v26 = a1[14];
    v63 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.AppInstallBroker",
      0x4Au,
      0x49u);
    MainPackageFamilyName = Windows::Foundation::GetActivationFactoryAsUser<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IAppInstallBroker>>(
                              v63,
                              v26,
                              &v51);
    if ( MainPackageFamilyName < 0 )
    {
      v28 = 549;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
        (const char *)(unsigned int)MainPackageFamilyName,
        v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      WindowsDeleteString(v50);
      v50 = 0;
      WindowsDeleteString(string);
      string = 0;
      *(_QWORD *)v61 = 0;
      goto LABEL_17;
    }
    if ( !v25 )
      goto LABEL_51;
    v48[0] = 0;
    LOBYTE(v27) = 1;
    MainPackageFamilyName = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, bool *))(*v51 + 136))(
                              v51,
                              *(_QWORD *)v61,
                              v27,
                              v48);
    if ( MainPackageFamilyName < 0 )
    {
      v28 = 554;
      goto LABEL_41;
    }
    if ( v48[0] )
    {
      StartPlaceHolderTelemetry::PlaceholderTileActivated::MovedToFrontOfInstallQueue(a6);
      v29 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING))(*v51 + 144))(v51, *(_QWORD *)v61, v50);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholderti"
                        "letransformer.cpp",
          (const char *)(unsigned int)v29,
          v46);
      v31 = v61[0];
      LOBYTE(v30) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
        v30,
        0);
      v53 = L"pdp";
      v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v53);
      v33 = StoreUriHelpers::ActivateStoreAsync(a1[14], v52, v57, v32[1].Reserved.Reserved1);
      MainPackageFamilyName = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x239,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholderti"
                        "letransformer.cpp",
          (const char *)(unsigned int)v33,
          v31);
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        goto LABEL_38;
      }
    }
    else
    {
LABEL_51:
      v34 = *(_DWORD *)(*(_QWORD *)DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetSkuId(*a2, v58) + 16LL);
      SkuId = DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetSkuId(*a2, &v64);
      v36 = *(const WCHAR **)SkuId;
      if ( *(_QWORD *)(*(_QWORD *)SkuId + 24LL) > 7u )
        v36 = *(const WCHAR **)v36;
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v67, v36, v34);
      if ( *(_QWORD *)&v64.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v64.Reserved.Reserved2[8]);
      if ( v59 )
        std::_Ref_count_base::_Decref(v59);
      v37 = *(_DWORD *)(*(_QWORD *)DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetStoreCampaignId(
                                     *a2,
                                     &hstringHeader)
                      + 16LL);
      StoreCampaignId = DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetStoreCampaignId(*a2, &v53);
      v39 = *(const WCHAR **)StoreCampaignId;
      if ( *(_QWORD *)(*(_QWORD *)StoreCampaignId + 24LL) > 7u )
        v39 = *(const WCHAR **)v39;
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v65, v39, v37);
      if ( v54 )
        std::_Ref_count_base::_Decref(v54);
      if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
      LOBYTE(v41) = 3;
      LOBYTE(v40) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
        v40,
        v41);
      DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetPlaceholderOrigin(**a2);
      v42 = *v51;
      if ( v25 )
      {
        v47 = a3;
        v43 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64))(v42 + 72))(v51, *(_QWORD *)v61, v68, v66);
      }
      else
      {
        v47 = (int)v50;
        v43 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, __int64))(v42 + 64))(v51, string, v66, a3);
      }
      LODWORD(v53) = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x25D,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholderti"
                        "letransformer.cpp",
          (const char *)(unsigned int)v43,
          v47);
        StartPlaceHolderTelemetry::PlaceholderTileActivated::InstallFailed<long const &>(a6, &v53);
        v44 = v61[0];
        v63 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"pdp", 4u, 3u);
        v45 = StoreUriHelpers::ActivateStoreAsync(a1[14], v52, v57, v63);
        MainPackageFamilyName = v45;
        if ( v45 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x268,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholder"
                          "tiletransformer.cpp",
            (const char *)(unsigned int)v45,
            v44);
          v66 = 0;
          v68 = 0;
          goto LABEL_50;
        }
      }
      v66 = 0;
      v68 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    WindowsDeleteString(v50);
    v50 = 0;
LABEL_71:
    WindowsDeleteString(string);
    string = 0;
    *(_QWORD *)v61 = 0;
    goto LABEL_72;
  }
  StartPlaceHolderTelemetry::PlaceholderTileActivated::ClickedWhileInstalling(a6);
  v63 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"placeholderTileTransformer_InstallVerb",
    0x27u,
    0x26u);
  v19 = v61[0];
  LOBYTE(v20) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl'::`2'::impl,
    v20,
    0);
  v53 = L"pdp";
  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v64, &v53);
  v22 = StoreUriHelpers::ActivateStoreAsync(a1[14], v52, v57, v21[1].Reserved.Reserved1);
  MainPackageFamilyName = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\placeholdertiletransformer.cpp",
      (const char *)(unsigned int)v22,
      v19);
    WindowsDeleteString(string);
    string = 0;
    *(_QWORD *)v61 = 0;
    goto LABEL_17;
  }
  WindowsDeleteString(string);
  string = 0;
  *(_QWORD *)v61 = 0;
LABEL_72:
  if ( v56 )
    std::_Ref_count_base::_Decref(v56);
  return 0;
}

```

## disassembly

```asm
0x1801fa4a0  push    rbp
0x1801fa4a2  push    rbx
0x1801fa4a3  push    rsi
0x1801fa4a4  push    rdi
0x1801fa4a5  push    r12
0x1801fa4a7  push    r13
0x1801fa4a9  push    r14
0x1801fa4ab  push    r15
0x1801fa4ad  lea     rbp, [rsp-68h]
0x1801fa4b2  sub     rsp, 168h
0x1801fa4b9  mov     rax, cs:__security_cookie
0x1801fa4c0  xor     rax, rsp
0x1801fa4c3  mov     [rbp+0A0h+var_50], rax
0x1801fa4c7  mov     [rsp+1A0h+var_130], r9d
0x1801fa4cc  mov     r13, r8
0x1801fa4cf  mov     rdi, rdx
0x1801fa4d2  mov     r15, rcx
0x1801fa4d5  mov     rax, [rbp+0A0h+arg_20]
0x1801fa4dc  mov     [rbp+0A0h+var_108], rax
0x1801fa4e0  mov     r12, [rbp+0A0h+arg_28]
0x1801fa4e7  xor     esi, esi
0x1801fa4e9  mov     dword ptr [rsp+1A0h+var_128], esi
0x1801fa4ed  lea     rdx, [rbp+0A0h+var_118]
0x1801fa4f1  mov     rcx, [rdi]
0x1801fa4f4  call    ?GetProductId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(void)
0x1801fa4f9  nop
0x1801fa4fa  mov     rdx, [rbp+0A0h+var_118]
0x1801fa4fe  mov     r8d, [rdx+10h]; length
0x1801fa502  lea     r14d, [rsi+7]
0x1801fa506  cmp     [rdx+18h], r14
0x1801fa50a  jbe     short loc_1801FA50F
0x1801fa50c  mov     rdx, [rdx]; sourceString
0x1801fa50f  lea     rcx, [rbp+0A0h+var_F0]; hstringHeader
0x1801fa513  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1801fa518  nop
0x1801fa519  mov     [rsp+1A0h+string], rsi
0x1801fa51e  lea     rdx, [rbp+0A0h+var_B0]
0x1801fa522  mov     rcx, [rdi]
0x1801fa525  call    ?GetPackageFamilyName@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetPackageFamilyName(void)
0x1801fa52a  nop
0x1801fa52b  mov     ebx, 1
0x1801fa530  mov     dword ptr [rsp+1A0h+var_128], ebx
0x1801fa534  mov     rax, [rax]
0x1801fa537  cmp     [rax+10h], rsi
0x1801fa53b  jnz     short loc_1801FA55A
0x1801fa53d  lea     rdx, [rbp+0A0h+var_100]
0x1801fa541  mov     rcx, [rdi]
0x1801fa544  call    ?GetProductId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetProductId(void)
0x1801fa549  mov     ebx, 3
0x1801fa54e  mov     rax, [rax]
0x1801fa551  cmp     [rax+10h], rsi
0x1801fa555  jnz     short loc_1801FA55A
0x1801fa557  mov     sil, 1
0x1801fa55a  test    bl, 2
0x1801fa55d  jz      short loc_1801FA571
0x1801fa55f  and     ebx, 0FFFFFFFDh
0x1801fa562  mov     rcx, [rbp+0A0h+var_F8]; this
0x1801fa566  test    rcx, rcx
0x1801fa569  jz      short loc_1801FA571
0x1801fa56b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801fa570  nop
0x1801fa571  test    bl, 1
0x1801fa574  jz      short loc_1801FA584
0x1801fa576  mov     rcx, [rbp+0A0h+var_A8]; this
0x1801fa57a  test    rcx, rcx
0x1801fa57d  jz      short loc_1801FA584
0x1801fa57f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801fa584  test    sil, sil
0x1801fa587  jz      loc_1801FA612
0x1801fa58d  mov     rcx, [rsp+1A0h+string]; string
0x1801fa592  call    cs:__imp_WindowsDeleteString
0x1801fa598  xor     esi, esi
0x1801fa59a  mov     [rsp+1A0h+string], rsi
0x1801fa59f  lea     rdx, [rsp+1A0h+var_128]
0x1801fa5a4  mov     rcx, [rdi]
0x1801fa5a7  call    ?GetTileIdentifier@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetTileIdentifier(void)
0x1801fa5ac  lea     rdx, [rsp+1A0h+string]; HSTRING *
0x1801fa5b1  mov     rcx, [rax]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *
0x1801fa5b4  call    ?GetMainPackageFamilyName@PlaceholderTileTransformer@Internal@1DataStoreCache@@CAJPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@PEAPEAUHSTRING__@@@Z; DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::GetMainPackageFamilyName(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *,HSTRING__ * *)
0x1801fa5b9  mov     ebx, eax
0x1801fa5bb  lea     rcx, [rsp+1A0h+var_128]; void *
0x1801fa5c0  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801fa5c5  test    ebx, ebx
0x1801fa5c7  jns     loc_1801FA67F
0x1801fa5cd  mov     edx, 1F7h; void *
0x1801fa5d2  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa5d9  mov     r9d, ebx; char *
0x1801fa5dc  mov     rcx, [rbp+0A8h]; this
0x1801fa5e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa5e8  nop
0x1801fa5e9  mov     rcx, [rsp+1A0h+string]; string
0x1801fa5ee  call    cs:__imp_WindowsDeleteString
0x1801fa5f4  mov     [rsp+1A0h+string], rsi
0x1801fa5f9  mov     qword ptr [rbp+0A0h+var_D8], rsi
0x1801fa5fd  mov     rcx, [rbp+0A0h+var_110]; this
0x1801fa601  test    rcx, rcx
0x1801fa604  jz      short loc_1801FA60B
0x1801fa606  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801fa60b  mov     eax, ebx
0x1801fa60d  jmp     loc_1801FAC2C
0x1801fa612  lea     rdx, [rsp+1A0h+var_128]
0x1801fa617  mov     rcx, [rdi]
0x1801fa61a  call    ?GetPackageFamilyName@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::GetPackageFamilyName(void)
0x1801fa61f  mov     rdx, [rsp+1A0h+var_128]
0x1801fa624  mov     r8d, [rdx+10h]; unsigned int
0x1801fa628  cmp     [rdx+18h], r14
0x1801fa62c  jbe     short loc_1801FA631
0x1801fa62e  mov     rdx, [rdx]; unsigned __int16 *
0x1801fa631  lea     rcx, [rsp+1A0h+string]; this
0x1801fa636  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801fa63b  mov     ebx, eax
0x1801fa63d  xor     esi, esi
0x1801fa63f  test    eax, eax
0x1801fa641  jns     short loc_1801FA671
0x1801fa643  mov     rcx, [rbp+0A8h]; this
0x1801fa64a  mov     r9d, eax; char *
0x1801fa64d  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa654  mov     edx, 1FCh; void *
0x1801fa659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa65e  mov     rcx, [rbp+0A0h+var_120]; this
0x1801fa662  test    rcx, rcx
0x1801fa665  jz      short loc_1801FA5E9
0x1801fa667  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801fa66c  jmp     loc_1801FA5E9
0x1801fa671  mov     rcx, [rbp+0A0h+var_120]; this
0x1801fa675  test    rcx, rcx
0x1801fa678  jz      short loc_1801FA67F
0x1801fa67a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801fa67f  mov     rax, [r15]
0x1801fa682  mov     rdx, rdi
0x1801fa685  mov     rcx, r15
0x1801fa688  mov     rax, [rax+110h]
0x1801fa68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa694  test    al, al
0x1801fa696  jz      loc_1801FA77B
0x1801fa69c  mov     rcx, r12; this
0x1801fa69f  call    ?ClickedWhileInstalling@PlaceholderTileActivated@StartPlaceHolderTelemetry@@QEAAXXZ; StartPlaceHolderTelemetry::PlaceholderTileActivated::ClickedWhileInstalling(void)
0x1801fa6a4  mov     [rbp+0A0h+var_B8], rsi
0x1801fa6a8  mov     r9d, 26h ; '&'; unsigned int
0x1801fa6ae  lea     r8d, [r9+1]; unsigned int
0x1801fa6b2  lea     rdx, aPlaceholdertil_78; "placeholderTileTransformer_InstallVerb"
0x1801fa6b9  lea     rcx, [rbp+0A0h+hstringHeader]; hstringHeader
0x1801fa6bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801fa6c2  nop
0x1801fa6c3  mov     rbx, [rbp+0A0h+var_B8]
0x1801fa6c7  mov     rdi, [rsp+1A0h+string]
0x1801fa6cc  mov     rsi, qword ptr [rbp+0A0h+var_D8]
0x1801fa6d0  xor     r8d, r8d
0x1801fa6d3  mov     dl, 1
0x1801fa6d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders> `wil::Feature<__WilFeatureTraits_Feature_AppRestorePlaceholders>::GetImpl(void)'::`2'::impl
0x1801fa6dc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppRestorePlaceholders@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppRestorePlaceholders>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801fa6e1  lea     rdx, aPdp; "pdp"
0x1801fa6e8  mov     [rsp+1A0h+var_128], rdx
0x1801fa6ed  lea     rdx, [rsp+1A0h+var_128]
0x1801fa6f2  lea     rcx, [rbp+0A0h+var_B0]
0x1801fa6f6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801fa6fb  xor     r14d, r14d
0x1801fa6fe  mov     [rsp+1A0h+var_168], r14
0x1801fa703  mov     [rsp+1A0h+var_170], rbx
0x1801fa708  mov     [rsp+1A0h+var_178], rdi
0x1801fa70d  mov     qword ptr [rsp+1A0h+var_180], rsi; int
0x1801fa712  mov     r9, [rax+18h]
0x1801fa716  mov     r8, [rbp+0A0h+var_108]
0x1801fa71a  mov     edx, [rsp+1A0h+var_130]
0x1801fa71e  mov     rcx, [r15+70h]
0x1801fa722  call    ?ActivateStoreAsync@StoreUriHelpers@@YAJPEAUIUser@System@Windows@@KPEAUIPropertySet@Collections@Foundation@4@PEAUHSTRING__@@222PEAPEAU?$IAsyncOperation@_N@74@@Z; StoreUriHelpers::ActivateStoreAsync(Windows::System::IUser *,ulong,Windows::Foundation::Collections::IPropertySet *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)
0x1801fa727  mov     ebx, eax
0x1801fa729  test    eax, eax
0x1801fa72b  jns     short loc_1801FA762
0x1801fa72d  mov     rcx, [rbp+0A8h]; this
0x1801fa734  mov     r9d, eax; char *
0x1801fa737  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa73e  mov     edx, 20Ah; void *
0x1801fa743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa748  nop
0x1801fa749  mov     rcx, [rsp+1A0h+string]; string
0x1801fa74e  call    cs:__imp_WindowsDeleteString
0x1801fa754  mov     [rsp+1A0h+string], r14
0x1801fa759  mov     qword ptr [rbp+0A0h+var_D8], r14
0x1801fa75d  jmp     loc_1801FA5FD
0x1801fa762  mov     rcx, [rsp+1A0h+string]; string
0x1801fa767  call    cs:__imp_WindowsDeleteString
0x1801fa76d  mov     [rsp+1A0h+string], r14
0x1801fa772  mov     qword ptr [rbp+0A0h+var_D8], r14
0x1801fa776  jmp     loc_1801FAC1C
0x1801fa77b  mov     [rsp+1A0h+var_150], sil
0x1801fa780  lea     rcx, [r15-48h]; this
0x1801fa784  lea     r8, [rsp+1A0h+var_150]; bool *
0x1801fa789  mov     rdx, [rsp+1A0h+string]; HSTRING
0x1801fa78e  call    ?IsPackageInstalled@PlaceholderTileTransformer@Internal@1DataStoreCache@@AEAAJPEAUHSTRING__@@PEA_N@Z; DataStoreCache::PlaceholderTileTransformer::Internal::PlaceholderTileTransformer::IsPackageInstalled(HSTRING__ *,bool *)
0x1801fa793  mov     ebx, eax
0x1801fa795  test    eax, eax
0x1801fa797  jns     short loc_1801FA7A3
0x1801fa799  mov     edx, 217h
0x1801fa79e  jmp     loc_1801FA5D2
0x1801fa7a3  cmp     [rsp+1A0h+var_150], sil
0x1801fa7a8  jz      short loc_1801FA7E7
0x1801fa7aa  mov     rcx, r12; this
0x1801fa7ad  call    ?ClickedWhileInstalled@PlaceholderTileActivated@StartPlaceHolderTelemetry@@QEAAXXZ; StartPlaceHolderTelemetry::PlaceholderTileActivated::ClickedWhileInstalled(void)
0x1801fa7b2  test    cs:Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits, 4
0x1801fa7b9  jz      loc_1801FAC08
0x1801fa7bf  xor     edx, edx; length
0x1801fa7c1  mov     rcx, [rsp+1A0h+string]; string
0x1801fa7c6  call    cs:__imp_WindowsGetStringRawBuffer
0x1801fa7cc  mov     r8, rax
0x1801fa7cf  lea     rdx, AppAlreadyInstalled
0x1801fa7d6  lea     rcx, Microsoft_Windows_StartLayoutPopulation_Provider_Context
0x1801fa7dd  call    McTemplateU0z_EventWriteTransfer
0x1801fa7e2  jmp     loc_1801FAC08
0x1801fa7e7  mov     [rsp+1A0h+var_140], rsi
0x1801fa7ec  xor     ecx, ecx; string
0x1801fa7ee  call    cs:__imp_WindowsDeleteString
0x1801fa7f4  mov     [rsp+1A0h+var_140], rsi
0x1801fa7f9  lea     rcx, [rsp+1A0h+var_140]; string
0x1801fa7fe  call    ?CreateCorrelationVector@CorrelationVectorHelper@Common@Cortana@@SAJPEAPEAUHSTRING__@@@Z; Cortana::Common::CorrelationVectorHelper::CreateCorrelationVector(HSTRING__ * *)
0x1801fa803  mov     ebx, eax
0x1801fa805  test    eax, eax
0x1801fa807  jns     short loc_1801FA83A
0x1801fa809  mov     rcx, [rbp+0A8h]; this
0x1801fa810  mov     r9d, eax; char *
0x1801fa813  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa81a  mov     edx, 221h; void *
0x1801fa81f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa824  nop
0x1801fa825  mov     rcx, [rsp+1A0h+var_140]; string
0x1801fa82a  call    cs:__imp_WindowsDeleteString
0x1801fa830  mov     [rsp+1A0h+var_140], rsi
0x1801fa835  jmp     loc_1801FA5E9
0x1801fa83a  cmp     qword ptr [rbp+0A0h+var_D8], rsi
0x1801fa83e  setnz   sil
0x1801fa842  mov     [rsp+1A0h+var_138], 0
0x1801fa84b  mov     rbx, [r15+70h]
0x1801fa84f  mov     [rbp+0A0h+var_B8], 0
0x1801fa857  mov     r9d, 49h ; 'I'; unsigned int
0x1801fa85d  lea     r8d, [r9+1]; unsigned int
0x1801fa861  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_AppInstallBroker@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Curat"...
0x1801fa868  lea     rcx, [rbp+0A0h+hstringHeader]; hstringHeader
0x1801fa86c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801fa871  lea     r8, [rsp+1A0h+var_138]
0x1801fa876  mov     rdx, rbx
0x1801fa879  mov     rcx, [rbp+0A0h+var_B8]
0x1801fa87d  call    ??$GetActivationFactoryAsUser@V?$ComPtr@UIAppInstallBroker@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@V?$ComPtrRef@V?$ComPtr@UIAppInstallBroker@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactoryAsUser<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IAppInstallBroker>>(HSTRING__ *,Windows::System::IUser *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IAppInstallBroker>>)
0x1801fa882  mov     ebx, eax
0x1801fa884  test    eax, eax
0x1801fa886  jns     short loc_1801FA8DA
0x1801fa888  mov     edx, 225h; void *
0x1801fa88d  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa894  mov     r9d, ebx; char *
0x1801fa897  mov     rcx, [rbp+0A8h]; this
0x1801fa89e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa8a3  nop
0x1801fa8a4  lea     rcx, [rsp+1A0h+var_138]
0x1801fa8a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fa8ae  nop
0x1801fa8af  mov     rcx, [rsp+1A0h+var_140]; string
0x1801fa8b4  call    cs:__imp_WindowsDeleteString
0x1801fa8ba  xor     edi, edi
0x1801fa8bc  mov     [rsp+1A0h+var_140], rdi
0x1801fa8c1  mov     rcx, [rsp+1A0h+string]; string
0x1801fa8c6  call    cs:__imp_WindowsDeleteString
0x1801fa8cc  mov     [rsp+1A0h+string], rdi
0x1801fa8d1  mov     qword ptr [rbp+0A0h+var_D8], rdi
0x1801fa8d5  jmp     loc_1801FA5FD
0x1801fa8da  test    sil, sil
0x1801fa8dd  jz      loc_1801FA9FB
0x1801fa8e3  mov     [rsp+1A0h+var_150], 0
0x1801fa8e8  mov     rcx, [rsp+1A0h+var_138]
0x1801fa8ed  mov     rax, [rcx]
0x1801fa8f0  lea     r9, [rsp+1A0h+var_150]
0x1801fa8f5  mov     r8b, 1
0x1801fa8f8  mov     rdx, qword ptr [rbp+0A0h+var_D8]
0x1801fa8fc  mov     rax, [rax+88h]
0x1801fa903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa908  mov     ebx, eax
0x1801fa90a  test    eax, eax
0x1801fa90c  jns     short loc_1801FA918
0x1801fa90e  mov     edx, 22Ah
0x1801fa913  jmp     loc_1801FA88D
0x1801fa918  cmp     [rsp+1A0h+var_150], 0
0x1801fa91d  jz      loc_1801FA9FB
0x1801fa923  mov     rcx, r12; this
0x1801fa926  call    ?MovedToFrontOfInstallQueue@PlaceholderTileActivated@StartPlaceHolderTelemetry@@QEAAXXZ; StartPlaceHolderTelemetry::PlaceholderTileActivated::MovedToFrontOfInstallQueue(void)
0x1801fa92b  mov     rcx, [rsp+1A0h+var_138]
0x1801fa930  mov     rax, [rcx]
0x1801fa933  mov     r8, [rsp+1A0h+var_140]
0x1801fa938  mov     rdx, qword ptr [rbp+0A0h+var_D8]
0x1801fa93c  mov     rax, [rax+90h]
0x1801fa943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa948  mov     rcx, [rbp+0A8h]; this
0x1801fa94f  xor     esi, esi
0x1801fa951  test    eax, eax
0x1801fa953  jns     short loc_1801FA969
0x1801fa955  mov     r9d, eax; char *
0x1801fa958  lea     r8, aShellcommonShe_24; "shellcommon\\shell\\datastorecache\\tra"...
0x1801fa95f  mov     edx, 22Fh; void *
0x1801fa964  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801fa969  mov     rbx, [rsp+1A0h+string]
0x1801fa96e  mov     rdi, qword ptr [rbp+0A0h+var_D8]
0x1801fa972  xor     r8d, r8d
0x1801fa975  mov     dl, 1
  ... truncated ...
```
