# Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler::ProcessResponseAsync$_ResumeCoro$1

- ea: `0x180140920`
- end: `0x180141550`
- name: `Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler::ProcessResponseAsync$_ResumeCoro$1`
- size: `3120`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801160b0`

## callees

- `0x1800135e0`
- `0x180016cf4`
- `0x18002c020`
- `0x18002e010`
- `0x18006e3e8`
- `0x18006ef0c`
- `0x180079cdc`
- `0x18009ed4c`
- `0x1800a30c4`
- `0x1800ac3a4`
- `0x1800ae3d0`
- `0x1800c67cc`
- `0x1800c69f8`
- `0x1800da770`
- `0x1800e48f8`
- `0x1800e49a0`
- `0x1800e7a84`
- `0x1800ed8b0`
- `0x1800ee2a0`
- `0x180102048`
- `0x180116060`
- `0x180116910`
- `0x1801201a0`
- `0x1801202a0`
- `0x180123338`
- `0x1801238a6`
- `0x180128e9c`
- `0x18012ae58`
- `0x18012aecc`
- `0x180135400`
- `0x18013678c`
- `0x1801392d0`
- `0x18013ceb4`
- `0x18013ceec`
- `0x18013d490`
- `0x18013d4f8`
- `0x18013e174`
- `0x18013e204`
- `0x18013f15c`
- `0x18013f188`
- `0x18013f4dc`
- `0x18013f718`
- `0x18013f7e8`
- `0x18013fa08`
- `0x18013fb00`
- `0x18013fdf8`
- `0x18013fe60`
- `0x180140920`
- `0x180141a70`
- `0x1801c3ef4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140ec1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140ee4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140f10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140f3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140ec1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140ee4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140f10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140f3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801410f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1801410f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler::ProcessResponseAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const struct winrt::impl::slim_source_location *v5; // rax
  __int64 v6; // rbx
  unsigned __int64 VersionForStoredCacheEntry; // rax
  int v8; // eax
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  const WCHAR *v15; // rbx
  bool v16; // r12
  bool v17; // al
  const WCHAR *v18; // rax
  const WCHAR *v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  const WCHAR *v24; // rax
  LPCWSTR v25; // rdx
  __int64 v26; // rcx
  void *v27; // rax
  __int64 v28; // rbx
  __int128 v29; // xmm6
  __int128 v30; // xmm7
  __int128 v31; // xmm8
  __int128 v32; // xmm9
  __int128 v33; // xmm10
  __int128 v34; // xmm11
  __int128 v35; // xmm12
  __int128 v36; // xmm13
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  const struct winrt::impl::slim_source_location *v40; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-278h]
  winrt::Windows::Web::Http::IHttpRequestMessageFactory *v42; // [rsp+48h] [rbp-250h]
  winrt::Windows::Web::Http::IHttpRequestMessageFactory *v43; // [rsp+48h] [rbp-250h]
  boost::detail::shared_count *v44; // [rsp+60h] [rbp-238h]
  Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo *v45; // [rsp+68h] [rbp-230h]
  _BYTE pExceptionObject[24]; // [rsp+C0h] [rbp-1D8h] BYREF
  _BYTE v47[24]; // [rsp+D8h] [rbp-1C0h] BYREF
  __int64 v49; // [rsp+100h] [rbp-198h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_66;
    case 2:
      *(_DWORD *)(a1 + 1520) = 0;
      v2 = a1 - 112;
      *(_QWORD *)(a1 + 16) = a1 - 112;
      *(_QWORD *)(a1 + 24) = a1 - 112;
      *(_BYTE *)(a1 - 112 + 48) = 1;
      v3 = winrt::impl::consume_Windows_Web_Http_IHttpResponseMessage<winrt::Windows::Web::Http::IHttpResponseMessage>::Content(
             a1 + 1592,
             a1 + 32);
      v4 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
             v3,
             a1 + 40);
      if ( *(_DWORD *)(v2 + 96) == 2 )
      {
        v5 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1472);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v5);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = v4;
      *(_QWORD *)(a1 + 64) = 0;
      *(_BYTE *)(a1 + 72) = 1;
      *(_WORD *)(a1 + 8) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::ProfileDataItemResponseHandlerImpl *,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type>(
                              a1 + 48,
                              a1) )
        return;
      goto LABEL_7;
    case 6:
LABEL_7:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_resume(
        a1 + 48,
        a1 + 80);
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 48);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 40));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 32));
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = *(_QWORD *)(a1 + 80);
      if ( !(unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                               (const struct winrt::param::hstring *)(a1 + 96),
                               (struct winrt::Windows::Data::Json::JsonObject *)(a1 + 88)) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\src\\clouddatastorecollectionresponsehandler.cpp",
          (const char *)0x803B001BLL,
          bIgnoreCase);
      v42 = (winrt::Windows::Web::Http::IHttpRequestMessageFactory *)winrt::Windows::Data::Json::JsonArray::JsonArray((winrt::Windows::Data::Json::JsonArray *)(a1 + 128));
      winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 136), L"activities");
      winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
        a1 + 88,
        a1 + 168,
        a1 + 136,
        v42);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 128));
      if ( !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(a1 + 168) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\src\\clouddatastorecollectionresponsehandler.cpp",
          (const char *)0x8007000DLL,
          bIgnoreCase);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl'::`2'::impl) )
      {
        v6 = *(_QWORD *)(a1 + 1560);
        VersionForStoredCacheEntry = Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetVersionForStoredCacheEntry();
        if ( *(_BYTE *)(v6 + 32) )
          VersionForStoredCacheEntry = *(_QWORD *)(v6 + 24);
      }
      else
      {
        VersionForStoredCacheEntry = Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetVersionForStoredCacheEntry();
      }
      *(_QWORD *)(a1 + 176) = VersionForStoredCacheEntry;
      *(_QWORD *)(a1 + 184) = a1 + 168;
      *(_DWORD *)(a1 + 192) = 0;
      *(_DWORD *)(a1 + 1496) = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(a1 + 168);
      v8 = 0;
      goto LABEL_25;
    case 7:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 48);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 40));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 32));
      goto LABEL_66;
    case 8:
      break;
    case 9:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 1280);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 1272));
      if ( *(_QWORD *)(a1 + 1192) )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 1192));
      v9 = *(std::_Ref_count_base **)(a1 + 1504);
      if ( v9 )
        std::_Ref_count_base::_Decref(v9);
      std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Tidy(a1 + 312);
      Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails((Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails *)(a1 + 296));
      Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails((Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails *)(a1 + 280));
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)(a1 + 248));
      Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo::~CloudDataStoreTypeInfo((Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo *)(a1 + 208));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 200));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 168));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 88));
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 80);
      goto LABEL_66;
    default:
      __debugbreak();
      return;
  }
  while ( 2 )
  {
    winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,1>::await_resume(
      a1 + 1280,
      a1 + 1312);
    winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 1312));
    winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 1280);
    winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 1272));
    if ( *(_QWORD *)(a1 + 1192) )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 1192));
    v10 = *(std::_Ref_count_base **)(a1 + 1504);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    while ( 2 )
    {
      std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Tidy(a1 + 312);
      Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails((Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails *)(a1 + 296));
      Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails((Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails *)(a1 + 280));
      while ( 1 )
      {
        boost::detail::shared_count::~shared_count((boost::detail::shared_count *)(a1 + 248));
        Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo::~CloudDataStoreTypeInfo((Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo *)(a1 + 208));
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 200));
        v8 = *(_DWORD *)(a1 + 192) + 1;
        *(_DWORD *)(a1 + 192) = v8;
LABEL_25:
        if ( v8 == *(_DWORD *)(a1 + 1496) )
          goto LABEL_65;
        winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(a1 + 184, a1 + 200);
        *(_QWORD *)(a1 + 208) = 0;
        *(_QWORD *)(a1 + 216) = 0;
        *(_QWORD *)(a1 + 224) = 0;
        *(_QWORD *)(a1 + 232) = 0;
        *(_QWORD *)(a1 + 240) = 0;
        *(_QWORD *)(a1 + 248) = 0;
        *(_DWORD *)(a1 + 256) = 0;
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 24) + 96LL) == 2
          || (v12 = std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>(
                      a1 + 264,
                      a1 + 1760,
                      a1 + 240,
                      v11),
              Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::StoreSingleResponseActivity(
                a1 + 200,
                a1 + 1616,
                *(_QWORD *)(a1 + 176),
                a1 + 208,
                v13,
                v12),
              *(_DWORD *)(*(_QWORD *)(a1 + 24) + 96LL) == 2) )
        {
          boost::detail::shared_count::~shared_count((boost::detail::shared_count *)(a1 + 248));
          Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo::~CloudDataStoreTypeInfo((Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo *)(a1 + 208));
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 200));
LABEL_65:
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 168));
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 88));
          winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 80);
          *(_QWORD *)(a1 + 1320) = a1 - 112;
          *(_WORD *)(a1 + 8) = 0;
          if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadUnitId>,winrt::hstring,winrt::hstring,winrt::hstring,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>,wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>,wil::com_ptr_t<Windows::Web::Http::IHttpClient,wil::err_exception_policy>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::IAccountInfoFetcher>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>::final_suspend_awaiter::await_suspend() )
          {
LABEL_66:
            winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::AssetOverActivityResponseHandler *,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadUnitId,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::AssetOverActivityResponseHandler *,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadUnitId,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>(a1 - 112);
            Windows::Internal::Storage::Cloud::Downloader::Core::AssetOverActivityResponseHandler::ProcessResponseAsync_::_28_::_parameters_::__parameters_(a1 + 1560);
            if ( *(_WORD *)(a1 + 10) )
              operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x760);
          }
          return;
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl'::`2'::impl) )
        {
          v18 = winrt::hstring::c_str((winrt::hstring *)(a1 + 216));
          v16 = CompareStringOrdinal(v18, -1, L"Windows.Data.Apps.AppMetaData", -1, 1) == 2;
          v19 = winrt::hstring::c_str((winrt::hstring *)(a1 + 216));
          v17 = CompareStringOrdinal(v19, -1, L"Windows.Data.Apps.AppLevelTileInfo", -1, 1) == 2;
          goto LABEL_33;
        }
        v14 = *(_QWORD *)(a1 + 1560);
        if ( *(_BYTE *)(v14 + 41) && !*(_BYTE *)(v14 + 40) )
        {
          v15 = winrt::hstring::c_str((winrt::hstring *)(a1 + 216));
          v16 = CompareStringOrdinal(v15, -1, L"Windows.Data.Apps.AppMetaData", -1, 1) == 2;
          v17 = CompareStringOrdinal(v15, -1, L"Windows.Data.Apps.AppLevelTileInfo", -1, 1) == 2;
LABEL_33:
          if ( v16 || v17 )
            break;
        }
      }
      v20 = (_QWORD *)(a1 + 280);
      *(_QWORD *)(a1 + 280) = 0;
      *(_QWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 296) = 0;
      *(_QWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 312) = 0;
      *(_QWORD *)(a1 + 320) = 0;
      *(_QWORD *)(a1 + 328) = 0;
      if ( v16 )
      {
        Windows::Data::Apps::AppMetaData::AppMetaData((Windows::Data::Apps::AppMetaData *)(a1 + 336));
        if ( (unsigned __int8)Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler::DeserializeTypeFromBlob<Windows::Data::Apps::AppMetaData>(
                                v21,
                                a1 + 240,
                                a1 + 336) )
        {
          std::wstring::operator std::basic_string_view<unsigned short>(a1 + 400, a1 + 800);
          winrt::hstring::operator=(a1 + 280);
          std::wstring::operator std::basic_string_view<unsigned short>(a1 + 440, a1 + 816);
          winrt::hstring::operator=(a1 + 296);
        }
        Windows::Data::Apps::AppMetaData::~AppMetaData((Windows::Data::Apps::AppMetaData *)(a1 + 336));
      }
      else if ( v17 )
      {
        Windows::Data::Apps::AppLevelTileInfo::AppLevelTileInfo((Windows::Data::Apps::AppLevelTileInfo *)(a1 + 832));
        if ( (unsigned __int8)Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler::DeserializeTypeFromBlob<Windows::Data::Apps::AppLevelTileInfo>(
                                v22,
                                a1 + 240,
                                a1 + 832) )
        {
          std::wstring::operator std::basic_string_view<unsigned short>(a1 + 864, a1 + 1136);
          winrt::hstring::operator=(a1 + 280);
          std::wstring::operator std::basic_string_view<unsigned short>(a1 + 904, a1 + 1152);
          winrt::hstring::operator=(a1 + 296);
        }
        Windows::Data::Apps::AppLevelTileInfo::~AppLevelTileInfo((Windows::Data::Apps::AppLevelTileInfo *)(a1 + 832));
      }
      if ( *v20 )
      {
        v23 = a1 + 312;
        if ( *(_QWORD *)(a1 + 320) == *(_QWORD *)(a1 + 328) )
          std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Emplace_reallocate<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId const &>(
            v23,
            *(_QWORD *)(a1 + 320),
            a1 + 280);
        else
          std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Emplace_back_with_unused_capacity<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId const &>(
            v23,
            a1 + 280);
      }
      if ( *(_QWORD *)(a1 + 296) )
      {
        if ( !*v20
          || (winrt::hstring::c_str((winrt::hstring *)(a1 + 280)),
              v24 = winrt::hstring::c_str((winrt::hstring *)(a1 + 296)),
              lstrcmpW(v24, v25)) )
        {
          v26 = a1 + 312;
          if ( *(_QWORD *)(a1 + 320) == *(_QWORD *)(a1 + 328) )
            std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Emplace_reallocate<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId const &>(
              v26,
              *(_QWORD *)(a1 + 320),
              a1 + 296);
          else
            std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Emplace_back_with_unused_capacity<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId const &>(
              v26,
              a1 + 296);
        }
      }
      if ( !((__int64)(*(_QWORD *)(a1 + 320) - *(_QWORD *)(a1 + 312)) >> 4) )
        continue;
      break;
    }
    v27 = operator new(0x50u);
    *(_QWORD *)(a1 + 1512) = v27;
    v28 = std::_Ref_count_obj2<Windows::Internal::Storage::Cloud::Downloader::Core::AssetDetailsRequestHandler>::_Ref_count_obj2<Windows::Internal::Storage::Cloud::Downloader::Core::AssetDetailsRequestHandler>((__int64)v27);
    *(_QWORD *)(a1 + 1504) = v28;
    *(_DWORD *)(a1 + 1520) |= 1u;
    *(_QWORD *)(a1 + 1168) = v28 + 16;
    *(_QWORD *)(a1 + 1176) = v28;
    std::make_shared<Windows::Internal::Storage::Cloud::Downloader::Core::AssetDetailsResponseHandler,>(a1 + 1184);
    v45 = *(Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo **)(a1 + 1600);
    v44 = *(boost::detail::shared_count **)(*(_QWORD *)v45 + 16LL);
    v29 = *(_OWORD *)(a1 + 1624);
    v30 = *(_OWORD *)(a1 + 1640);
    v31 = *(_OWORD *)(a1 + 1656);
    v32 = *(_OWORD *)(a1 + 1672);
    v33 = *(_OWORD *)(a1 + 1688);
    v34 = *(_OWORD *)(a1 + 1704);
    v35 = *(_OWORD *)(a1 + 1720);
    v36 = *(_OWORD *)(a1 + 1736);
    v43 = *(winrt::Windows::Web::Http::IHttpRequestMessageFactory **)(a1 + 1752);
    *(_QWORD *)(a1 + 1216) = a1 + 1200;
    *(_QWORD *)(a1 + 1200) = 0;
    *(_QWORD *)(a1 + 1208) = 0;
    if ( *(_QWORD *)(a1 + 1192) )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 1192) + 8LL), 1u);
    *(_QWORD *)(a1 + 1200) = *(_QWORD *)(a1 + 1184);
    *(_QWORD *)(a1 + 1208) = *(_QWORD *)(a1 + 1192);
    *(_QWORD *)(a1 + 1240) = a1 + 1224;
    *(_QWORD *)(a1 + 1224) = 0;
    *(_QWORD *)(a1 + 1232) = 0;
    if ( v28 )
      _InterlockedAdd((volatile signed __int32 *)(v28 + 8), 1u);
    v49 = v28 + 16;
    *(_QWORD *)(a1 + 1224) = v28 + 16;
    *(_QWORD *)(a1 + 1232) = v28;
    *(_QWORD *)(a1 + 1256) = a1 + 1248;
    v37 = winrt::hstring::hstring((winrt::hstring *)(a1 + 1248), (const struct winrt::hstring *)(a1 + 1616));
    v38 = winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId,std::allocator<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>>(
            a1 + 1264,
            a1 + 312);
    *(_OWORD *)(a1 + 1328) = v29;
    *(_OWORD *)(a1 + 1344) = v30;
    *(_OWORD *)(a1 + 1360) = v31;
    *(_OWORD *)(a1 + 1376) = v32;
    *(_OWORD *)(a1 + 1392) = v33;
    *(_OWORD *)(a1 + 1408) = v34;
    *(_OWORD *)(a1 + 1424) = v35;
    *(_OWORD *)(a1 + 1440) = v36;
    *(_QWORD *)(a1 + 1456) = v43;
    v39 = ((__int64 (__fastcall *)(Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo *, __int64, __int64, __int64, __int64, __int64, __int64))v44)(
            v45,
            a1 + 1272,
            v38,
            v37,
            a1 + 1224,
            a1 + 1200,
            a1 + 1328);
    if ( *(_DWORD *)(a1 - 16) == 2 )
    {
      v40 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1528);
      winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v47, v40);
      throw (winrt::hresult_canceled *)v47;
    }
    *(_QWORD *)(a1 + 1280) = 0;
    *(_QWORD *)(a1 + 1288) = v39;
    *(_QWORD *)(a1 + 1296) = 0;
    *(_BYTE *)(a1 + 1304) = 1;
    *(_WORD *)(a1 + 8) = 8;
    if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::CloudDataStoreCollectionResponseHandler *,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadUnitId,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type>(
                             a1 + 1280,
                             a1) )
      continue;
    break;
  }
}

```

## disassembly

```asm
0x180140920  mov     r11, rsp
0x180140923  mov     [r11+10h], rbx
0x180140927  mov     [r11+18h], rsi
0x18014092b  mov     [r11+8], rcx
0x18014092f  push    rdi
0x180140930  push    r12
0x180140932  push    r13
0x180140934  push    r14
0x180140936  push    r15
0x180140938  sub     rsp, 270h
0x18014093f  movaps  xmmword ptr [r11-38h], xmm6
0x180140944  movaps  xmmword ptr [r11-48h], xmm7
0x180140949  movaps  xmmword ptr [r11-58h], xmm8
0x18014094e  movaps  xmmword ptr [r11-68h], xmm9
0x180140953  movaps  xmmword ptr [r11-78h], xmm10
0x180140958  movaps  xmmword ptr [r11-88h], xmm11
0x180140960  movaps  xmmword ptr [r11-98h], xmm12
0x180140968  movaps  xmmword ptr [r11-0A8h], xmm13
0x180140970  mov     rax, cs:__security_cookie
0x180140977  xor     rax, rsp
0x18014097a  mov     [rsp+298h+var_B0], rax
0x180140982  mov     rdi, rcx
0x180140985  mov     [rsp+298h+var_258], rcx
0x18014098a  movzx   eax, word ptr [rdi+8]
0x18014098e  mov     [rsp+298h+var_228], ax
0x180140993  mov     r14d, 1
0x180140999  add     ax, r14w
0x18014099d  cmp     ax, 0Ah; switch 11 cases
0x1801409a1  ja      def_1801409BC; jumptable 00000001801409BC default case, cases 1,5,6
0x1801409a7  movsx   rax, ax
0x1801409ab  lea     rdx, __ImageBase
0x1801409b2  mov     ecx, ds:(jpt_1801409BC - 180000000h)[rdx+rax*4]
0x1801409b9  add     rcx, rdx
0x1801409bc  jmp     rcx; switch jump
0x1801409be  xor     esi, esi; jumptable 00000001801409BC case 4
0x1801409c0  jmp     loc_1801414A2
0x1801409c5  xor     esi, esi; jumptable 00000001801409BC case 3
0x1801409c7  mov     [rdi+5F0h], esi
0x1801409cd  lea     rbx, [rdi-70h]
0x1801409d1  mov     [rdi+10h], rbx
0x1801409d5  mov     [rdi+18h], rbx
0x1801409d9  mov     [rbx+30h], r14b
0x1801409dd  lea     rdx, [rdi+20h]
0x1801409e1  lea     rcx, [rdi+638h]
0x1801409e8  call    ?Content@?$consume_Windows_Web_Http_IHttpResponseMessage@UIHttpResponseMessage@Http@Web@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Web_Http_IHttpResponseMessage<winrt::Windows::Web::Http::IHttpResponseMessage>::Content(void)
0x1801409ed  nop
0x1801409ee  lea     rdx, [rdi+28h]
0x1801409f2  mov     rcx, rax
0x1801409f5  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x1801409fa  nop
0x1801409fb  mov     ecx, [rbx+60h]
0x1801409fe  nop
0x1801409ff  cmp     ecx, 2
0x180140a02  jnz     short loc_180140A34
0x180140a04  lea     rcx, [rdi+5C0h]
0x180140a0b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180140a10  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180140a13  lea     rcx, [rsp+298h+pExceptionObject]; this
0x180140a1b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180140a20  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180140a27  lea     rcx, [rsp+298h+pExceptionObject]; pExceptionObject
0x180140a2f  call    _CxxThrowException_0
0x180140a34  lea     rcx, [rdi+30h]
0x180140a38  mov     [rcx], rsi
0x180140a3b  mov     [rdi+38h], rax
0x180140a3f  mov     [rdi+40h], rsi
0x180140a43  mov     [rdi+48h], r14b
0x180140a47  mov     eax, 6
0x180140a4c  mov     [rdi+8], ax
0x180140a50  mov     rdx, rdi
0x180140a53  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVProfileDataItemResponseHandlerImpl@Core@Downloader@Cloud@Storage@Internal@3@UProfileDataItemRequestUnit@789Internal@34@UHttpResponseMessage@Http@Web@34@V?$shared_ptr@VDownloaderCore@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@Uhstring@4@VCorrelationVector@689Internal@3@V?$shared_ptr@VILogger@Downloader@Cloud@Storage@Internal@Windows@winrt@@@std@@@experimental@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@Uhstring@winrt@@_K@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVProfileDataItemResponseHandlerImpl@Core@Downloader@Cloud@Storage@Internal@3@UProfileDataItemRequestUnit@789Internal@34@UHttpResponseMessage@Http@Web@34@V?$shared_ptr@VDownloaderCore@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@Uhstring@4@VCorrelationVector@689Internal@3@V?$shared_ptr@VILogger@Downloader@Cloud@Storage@Internal@Windows@winrt@@@std@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::ProfileDataItemResponseHandlerImpl *,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::ProfileDataItemResponseHandlerImpl *,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type>)
0x180140a58  test    al, al
0x180140a5a  jz      short loc_180140A88
0x180140a5c  jmp     loc_1801414CE
0x180140a61  lea     rcx, [rdi+30h]; jumptable 00000001801409BC case 8
0x180140a65  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x180140a6a  nop
0x180140a6b  lea     rcx, [rdi+28h]; this
0x180140a6f  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140a74  nop
0x180140a75  lea     rcx, [rdi+20h]; this
0x180140a79  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140a7e  nop
0x180140a7f  xor     esi, esi
0x180140a81  jmp     loc_1801414A2
0x180140a86  xor     esi, esi; jumptable 00000001801409BC case 7
0x180140a88  lea     rdx, [rdi+50h]
0x180140a8c  lea     rcx, [rdi+30h]
0x180140a90  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@Uhstring@winrt@@_K@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_resume(void)
0x180140a95  nop
0x180140a96  lea     rcx, [rdi+30h]
0x180140a9a  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x180140a9f  nop
0x180140aa0  lea     rcx, [rdi+28h]; this
0x180140aa4  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140aa9  nop
0x180140aaa  lea     rcx, [rdi+20h]; this
0x180140aae  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140ab3  lea     r12, [rdi+58h]
0x180140ab7  mov     [r12], rsi
0x180140abb  lea     rcx, [rdi+60h]; struct winrt::param::hstring *
0x180140abf  mov     rax, [rdi+50h]
0x180140ac3  mov     [rsp+298h+var_200], rax
0x180140acb  mov     [rcx], rax
0x180140ace  mov     rdx, r12; struct winrt::Windows::Data::Json::JsonObject *
0x180140ad1  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x180140ad6  mov     rcx, [rsp+298h]; this
0x180140ade  test    al, al
0x180140ae0  jnz     short loc_180140AF9
0x180140ae2  mov     r9d, 803B001Bh; char *
0x180140ae8  lea     r8, aOnecoreuapShel_71; "onecoreuap\\shell\\cloudstore\\download"...
0x180140aef  mov     edx, 48h ; 'H'; void *
0x180140af4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180140af9  lea     r13, [rdi+80h]
0x180140b00  mov     rcx, r13; this
0x180140b03  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x180140b08  mov     [rsp+298h+var_250], rax
0x180140b0d  lea     rbx, [rdi+88h]
0x180140b14  lea     rdx, aActivities; "activities"
0x180140b1b  mov     rcx, rbx; this
0x180140b1e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180140b23  lea     r15, [rdi+0A8h]
0x180140b2a  mov     r9, [rsp+298h+var_250]
0x180140b2f  mov     r8, rbx
0x180140b32  mov     rdx, r15
0x180140b35  mov     rcx, r12
0x180140b38  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)
0x180140b3d  nop
0x180140b3e  mov     rcx, r13; this
0x180140b41  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140b46  mov     rcx, r15
0x180140b49  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180140b4e  mov     rcx, [rsp+298h]; this
0x180140b56  test    eax, eax
0x180140b58  jnz     short loc_180140B6F
0x180140b5a  mov     r9d, 8007000Dh; char *
0x180140b60  lea     r8, aOnecoreuapShel_71; "onecoreuap\\shell\\cloudstore\\download"...
0x180140b67  lea     edx, [rax+4Bh]; void *
0x180140b6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180140b6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AadAssetsRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore> `wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl(void)'::`2'::impl
0x180140b76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(void)
0x180140b7b  test    al, al
0x180140b7d  jz      short loc_180140B97
0x180140b7f  mov     rbx, [rdi+618h]
0x180140b86  call    ?GetVersionForStoredCacheEntry@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@SA_KXZ; Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetVersionForStoredCacheEntry(void)
0x180140b8b  cmp     [rbx+20h], sil
0x180140b8f  jz      short loc_180140B9C
0x180140b91  mov     rax, [rbx+18h]
0x180140b95  jmp     short loc_180140B9C
0x180140b97  call    ?GetVersionForStoredCacheEntry@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@SA_KXZ; Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::GetVersionForStoredCacheEntry(void)
0x180140b9c  mov     [rdi+0B0h], rax
0x180140ba3  mov     [rdi+0B8h], r15
0x180140baa  mov     [rdi+0C0h], esi
0x180140bb0  mov     rcx, r15
0x180140bb3  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180140bb8  mov     [rdi+5D8h], eax
0x180140bbe  mov     eax, esi
0x180140bc0  jmp     loc_180140DA5
0x180140bc5  lea     rcx, [rdi+500h]; jumptable 00000001801409BC case 10
0x180140bcc  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x180140bd1  nop
0x180140bd2  lea     rcx, [rdi+4F8h]; this
0x180140bd9  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140bde  nop
0x180140bdf  mov     rax, [rdi+4A8h]
0x180140be6  mov     [rsp+298h+var_240], rax
0x180140beb  xor     esi, esi
0x180140bed  test    rax, rax
0x180140bf0  jz      short loc_180140C04
0x180140bf2  mov     rcx, [rdi+4A8h]; this
0x180140bf9  mov     [rsp+298h+var_240], rcx
0x180140bfe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140c03  nop
0x180140c04  mov     rcx, [rdi+5E0h]; this
0x180140c0b  test    rcx, rcx
0x180140c0e  jz      short loc_180140C16
0x180140c10  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140c15  nop
0x180140c16  lea     rcx, [rdi+138h]
0x180140c1d  call    ?_Tidy@?$vector@UAssetDownloadUnitId@Downloader@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UAssetDownloadUnitId@Downloader@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@AEAAXXZ; std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Tidy(void)
0x180140c22  nop
0x180140c23  lea     rcx, [rdi+128h]; this
0x180140c2a  call    ??1ConsentDetails@Core@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails(void)
0x180140c2f  nop
0x180140c30  lea     rcx, [rdi+118h]; this
0x180140c37  call    ??1ConsentDetails@Core@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails(void)
0x180140c3c  nop
0x180140c3d  lea     rcx, [rdi+0F8h]; this
0x180140c44  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180140c49  nop
0x180140c4a  lea     rcx, [rdi+0D0h]; this
0x180140c51  call    ??1CloudDataStoreTypeInfo@Utils@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo::~CloudDataStoreTypeInfo(void)
0x180140c56  nop
0x180140c57  lea     rcx, [rdi+0C8h]; this
0x180140c5e  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140c63  nop
0x180140c64  lea     rcx, [rdi+0A8h]; this
0x180140c6b  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140c70  nop
0x180140c71  lea     rcx, [rdi+58h]; this
0x180140c75  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140c7a  nop
0x180140c7b  lea     rcx, [rdi+50h]
0x180140c7f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180140c84  nop
0x180140c85  jmp     loc_1801414A2
0x180140c8a  xor     esi, esi; jumptable 00000001801409BC case 9
0x180140c8c  lea     rbx, [rdi+520h]
0x180140c93  lea     r15, [rdi+500h]
0x180140c9a  mov     rdx, rbx
0x180140c9d  mov     rcx, r15
0x180140ca0  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UDownloadResult@Downloader@Cloud@Storage@Internal@Windows@winrt@@UDownloadProgress@234567@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,1>::await_resume(void)
0x180140ca5  mov     rcx, rbx; this
0x180140ca8  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140cad  nop
0x180140cae  mov     rcx, r15
0x180140cb1  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x180140cb6  nop
0x180140cb7  lea     rcx, [rdi+4F8h]; this
0x180140cbe  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140cc3  nop
0x180140cc4  mov     rax, [rdi+4A8h]
0x180140ccb  mov     [rsp+298h+var_240], rax
0x180140cd0  test    rax, rax
0x180140cd3  jz      short loc_180140CE7
0x180140cd5  mov     rcx, [rdi+4A8h]; this
0x180140cdc  mov     [rsp+298h+var_240], rcx
0x180140ce1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140ce6  nop
0x180140ce7  mov     rcx, [rdi+5E0h]; this
0x180140cee  test    rcx, rcx
0x180140cf1  jz      loc_1801413BE
0x180140cf7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140cfc  jmp     loc_1801413BE
0x180140d01  mov     rdi, [rsp+298h+var_258]
0x180140d06  xor     esi, esi
0x180140d08  mov     rax, [rdi+4A8h]
0x180140d0f  test    rax, rax
0x180140d12  mov     [rsp+298h+var_240], rax
0x180140d17  jz      short loc_180140D2B
0x180140d19  mov     rcx, [rdi+4A8h]; this
0x180140d20  mov     [rsp+298h+var_240], rcx
0x180140d25  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140d2a  nop
0x180140d2b  mov     rcx, [rdi+5E0h]; this
0x180140d32  test    rcx, rcx
0x180140d35  jz      short loc_180140D3D
0x180140d37  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180140d3c  nop
0x180140d3d  lea     rcx, [rdi+138h]
0x180140d44  call    ?_Tidy@?$vector@UAssetDownloadUnitId@Downloader@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UAssetDownloadUnitId@Downloader@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@AEAAXXZ; std::vector<winrt::Windows::Internal::Storage::Cloud::Downloader::AssetDownloadUnitId>::_Tidy(void)
0x180140d49  nop
0x180140d4a  lea     rcx, [rdi+128h]; this
0x180140d51  call    ??1ConsentDetails@Core@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails(void)
0x180140d56  nop
0x180140d57  lea     rcx, [rdi+118h]; this
0x180140d5e  call    ??1ConsentDetails@Core@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Core::ConsentDetails::~ConsentDetails(void)
0x180140d63  nop
0x180140d64  lea     rcx, [rdi+0F8h]; this
0x180140d6b  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180140d70  nop
0x180140d71  lea     rcx, [rdi+0D0h]; this
0x180140d78  call    ??1CloudDataStoreTypeInfo@Utils@Downloader@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Downloader::Utils::CloudDataStoreTypeInfo::~CloudDataStoreTypeInfo(void)
0x180140d7d  nop
0x180140d7e  lea     rcx, [rdi+0C8h]; this
0x180140d85  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x180140d8a  mov     r14d, 1
0x180140d90  mov     eax, [rdi+0C0h]
0x180140d96  mov     [rsp+298h+var_1F0], eax
0x180140d9d  inc     eax
0x180140d9f  mov     [rdi+0C0h], eax
0x180140da5  mov     [rsp+298h+var_1F0], eax
0x180140dac  cmp     eax, [rdi+5D8h]
0x180140db2  jz      loc_180141457
0x180140db8  lea     r15, [rdi+0C8h]
0x180140dbf  mov     [rsp+298h+var_250], r15
0x180140dc4  lea     rcx, [rdi+0B8h]
0x180140dcb  mov     rdx, r15
0x180140dce  call    ??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)
0x180140dd3  nop
0x180140dd4  lea     rbx, [rdi+0D0h]
0x180140ddb  mov     [rsp+298h+var_230], rbx
0x180140de0  mov     [rbx], rsi
0x180140de3  lea     r13, [rdi+0D8h]
0x180140dea  mov     [r13+0], rsi
0x180140dee  mov     [rdi+0E0h], rsi
0x180140df5  mov     [rdi+0E8h], rsi
0x180140dfc  lea     r8, [rdi+0F0h]
0x180140e03  mov     [r8], rsi
0x180140e06  lea     r12, [rdi+0F8h]
0x180140e0d  mov     [rsp+298h+var_238], r12
0x180140e12  mov     [r12], rsi
0x180140e16  mov     [rdi+100h], esi
0x180140e1c  mov     rax, [rdi+18h]
0x180140e20  mov     eax, [rax+60h]
0x180140e23  nop
0x180140e24  cmp     eax, 2
0x180140e27  jz      loc_18014143C
0x180140e2d  lea     rcx, [rdi+108h]
0x180140e34  lea     rdx, [rbx+610h]
  ... truncated ...
```
