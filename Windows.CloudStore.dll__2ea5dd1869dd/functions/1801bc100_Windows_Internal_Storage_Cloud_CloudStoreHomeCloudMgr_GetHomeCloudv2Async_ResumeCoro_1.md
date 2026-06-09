# Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetHomeCloudv2Async$_ResumeCoro$1

- ea: `0x1801bc100`
- end: `0x1801bcf20`
- name: `Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetHomeCloudv2Async$_ResumeCoro$1`
- size: `3616`
- prototype: ``
- caller_count: `1`
- callee_count: `62`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180111e20`

## callees

- `0x18001355c`
- `0x180016cf4`
- `0x1800238d0`
- `0x180024fd0`
- `0x18002e010`
- `0x18005274c`
- `0x18006d7b4`
- `0x18006e16c`
- `0x18006e3e8`
- `0x18006ef0c`
- `0x180079cdc`
- `0x180079d2c`
- `0x18007ae10`
- `0x180088128`
- `0x180090158`
- `0x1800ac3a4`
- `0x1800ae3d0`
- `0x1800c3960`
- `0x1800c3fac`
- `0x1800c482c`
- `0x1800e320c`
- `0x1800e48f8`
- `0x1800e49a0`
- `0x1800e619c`
- `0x1800e7a84`
- `0x1800e9e98`
- `0x1800e9ee4`
- `0x1800ea6f4`
- `0x1800ee2a0`
- `0x1800face0`
- `0x1800fe5bc`
- `0x180102048`
- `0x180102bb8`
- `0x18011b160`
- `0x18011b570`
- `0x1801201a0`
- `0x1801202a0`
- `0x1801238a6`
- `0x18012a62c`
- `0x18012aecc`
- `0x180134b60`
- `0x180135400`
- `0x18013678c`
- `0x1801373b8`
- `0x1801392d0`
- `0x18013bac0`
- `0x1801646e0`
- `0x180170d94`
- `0x1801a9350`
- `0x1801b03b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1801bc2a7`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1801bc2a7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1801bc21b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bc636`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bc636`

## string_xrefs

- `0x1801bc63c`: `https://activity.windows.com`
- `0x1801bc9be`: `**!!##!!**LogProtocol Config Missing Config for %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
void __fastcall Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetHomeCloudv2Async__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // rbx
  _WORD *v3; // rdi
  __int64 v4; // r15
  const char *v5; // rbx
  __int64 v6; // r8
  int v7; // r10d
  unsigned __int64 v8; // r9
  const char *v9; // rdx
  __int64 v10; // rcx
  winrt::hstring *v11; // rax
  const unsigned __int16 *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64, __int64); // r15
  __int64 v17; // rax
  __int64 v18; // rax
  const struct winrt::impl::slim_source_location *v19; // rax
  _WORD *v20; // r13
  __int64 v21; // r15
  __int64 View; // rax
  __int64 v23; // r13
  _QWORD *ServiceEnvironmentConfig; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  const WCHAR *v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rbx
  unsigned int v31; // eax
  enum AsyncStatus v32; // edx
  char IsSuccessStatusCode; // di
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  const struct winrt::impl::slim_source_location *v37; // rax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // r12
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rbx
  const char **v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdi
  const unsigned __int16 *v47; // rax
  Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr *v48; // rcx
  __int64 v49; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-208h]
  __int64 v52; // [rsp+50h] [rbp-1D8h]
  _WORD *v53; // [rsp+60h] [rbp-1C8h]
  _WORD *v55; // [rsp+70h] [rbp-1B8h]
  _BYTE pExceptionObject[24]; // [rsp+98h] [rbp-190h] BYREF
  _BYTE v57[40]; // [rsp+B0h] [rbp-178h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-150h]
  const char *v59; // [rsp+110h] [rbp-118h]
  unsigned __int64 v60; // [rsp+128h] [rbp-100h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  v55 = (_WORD *)(a1 + 8);
  v3 = (_WORD *)(a1 + 8);
  v53 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_65;
    case 2:
      v4 = *(_QWORD *)(a1 + 824);
      std::enable_shared_from_this<Windows::Internal::Storage::Cloud::Downloader::Core::IAccountInfoFetcher>::shared_from_this(
        v4 + 8,
        a1 + 16);
      *(_QWORD *)(a1 + 128) = a1 - 112;
      *(_BYTE *)(a1 - 112 + 48) = 1;
      *(_QWORD *)(a1 + 800) = a1 + 48;
      v5 = (const char *)(a1 + 32);
      std::wstring::wstring(a1 + 32, a1 + 864);
      v60 = *(_QWORD *)(a1 + 56);
      if ( v60 > 7 )
        v59 = *(const char **)v5;
      v6 = *(_QWORD *)std::wstring::end(a1 + 32, a1 + 64);
      if ( v8 <= 7 )
      {
        LODWORD(v9) = a1 + 32;
      }
      else
      {
        v9 = *(const char **)v5;
        v59 = *(const char **)v5;
      }
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        a1 + 72,
        (_DWORD)v9,
        v6,
        v7,
        *(__int64 *)&_o_towlower);
      v60 = *(_QWORD *)(a1 + 56);
      if ( v60 > 7 )
      {
        v5 = *(const char **)v5;
        v59 = v5;
      }
      v10 = winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Security::Credentials::WebAccount>(
              *(_QWORD *)(a1 + 832),
              a1 + 80);
      v11 = (winrt::hstring *)winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(
                                v10,
                                a1 + 88);
      v12 = winrt::hstring::c_str(v11);
      Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::TryLoadProtocolHomeCloudInfoFromCache(
        v4,
        a1 + 96,
        v12,
        v5);
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 88);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 80));
      v13 = (__int64 *)winrt::clock::now(a1 + 112);
      v14 = *v13;
      *(_QWORD *)(a1 + 120) = *v13;
      if ( *(_QWORD *)(a1 + 104) > (unsigned __int64)(v14 + 10000000LL * (rand() % 14400 - 7200) - 864000000000LL)
        && *(_QWORD *)(a1 + 96) )
      {
        goto LABEL_62;
      }
      winrt::Windows::Web::Http::HttpRequestMessage::HttpRequestMessage((winrt::Windows::Web::Http::HttpRequestMessage *)(a1 + 144));
      winrt::Windows::Web::Http::HttpResponseMessage::HttpResponseMessage((winrt::Windows::Web::Http::HttpResponseMessage *)(a1 + 152));
      v15 = *(_QWORD *)(v4 + 128);
      v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v15 + 8LL);
      v17 = winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Security::Credentials::WebAccount>(
              *(_QWORD *)(a1 + 832),
              a1 + 160);
      v18 = v16(v15, a1 + 168, v17);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 728);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v19);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = v18;
      *(_QWORD *)(a1 + 192) = 0;
      *(_BYTE *)(a1 + 200) = 1;
      v20 = v53;
      *v53 = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>>::promise_type>(
                               a1 + 176,
                               a1) )
      {
LABEL_19:
        winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,1>::await_resume(
          a1 + 176,
          a1 + 208);
        winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 176);
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 168));
        v21 = a1 + 144;
        View = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
                 a1 + 144,
                 a1 + 216);
        winrt::impl::consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection<winrt::Windows::Web::Http::Headers::IHttpRequestHeaderCollection>::Authorization(
          View,
          a1 + 208);
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 216));
        v52 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
                a1 + 144,
                a1 + 224);
        v23 = *((_QWORD *)v20 + 102);
        *(_QWORD *)(a1 + 232) = *(_QWORD *)Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::BuildClientInfoHeaderString(
                                             *(_QWORD *)(v23 + 24),
                                             a1 + 264);
        winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 272), L"X-AFS-ClientInfo");
        winrt::impl::consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection<winrt::Windows::Web::Http::Headers::IHttpRequestHeaderCollection>::Append(
          v52,
          a1 + 272,
          a1 + 232);
        winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 264);
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 224));
        *(_OWORD *)(a1 + 304) = 0;
        *(_QWORD *)(a1 + 320) = 0;
        *(_QWORD *)(a1 + 328) = 7;
        *(_WORD *)(a1 + 304) = 0;
        ServiceEnvironmentConfig = (_QWORD *)Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetServiceEnvironmentConfig(
                                               v23,
                                               a1 + 336);
        v25 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ServiceEnvironmentConfig + 24LL))(*ServiceEnvironmentConfig);
        if ( v25[3] > 7u )
          v25 = (_QWORD *)*v25;
        std::wstring::assign(a1 + 304, v25);
        if ( *(_QWORD *)(a1 + 344) )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 344));
        winrt::param::hstring::hstring(a1 + 360, a1 + 304);
        v26 = winrt::Windows::Foundation::Uri::Uri(
                (winrt::Windows::Foundation::Uri *)(a1 + 352),
                (const struct winrt::param::hstring *)(a1 + 360));
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit>::Append(
          v21,
          v26);
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 352));
        *(_QWORD *)(a1 + 392) = 0;
        v27 = winrt::hstring::c_str((winrt::hstring *)(*(_QWORD *)(a1 + 800) + 816LL));
        v28 = CompareStringOrdinal(v27, -1, L"pdrs", -1, 1);
        v29 = L"https://roaming.windows.cloud.microsoft";
        if ( v28 != 2 )
          v29 = L"https://activity.windows.com";
        winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 408), v29);
        winrt::Windows::Foundation::Uri::Uri(
          (winrt::Windows::Foundation::Uri *)(a1 + 400),
          (const struct winrt::param::hstring *)(a1 + 408));
        v30 = winrt::impl::consume_Windows_Web_Http_IHttpClient<winrt::Windows::Web::Http::IHttpClient>::SendRequestAsync(
                a1 + 856,
                a1 + 440,
                v21);
        v31 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>>::Status(v30);
        if ( !v31 )
          v31 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>(v30);
        winrt::impl::check_status_canceled((winrt::impl *)v31, v32);
        winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>::GetResults(
          v30,
          a1 + 448);
        winrt::Windows::ApplicationModel::AppExtensions::AppExtensionCatalog::operator=(a1 + 152, a1 + 448);
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 448));
        winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 440));
        IsSuccessStatusCode = winrt::impl::consume_Windows_Web_Http_IHttpResponseMessage<winrt::Windows::Web::Http::IHttpResponseMessage>::IsSuccessStatusCode(a1 + 152);
        v34 = winrt::impl::consume_Windows_Web_Http_IHttpResponseMessage<winrt::Windows::Web::Http::IHttpResponseMessage>::StatusCode(a1 + 152);
        if ( !IsSuccessStatusCode )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
            (const char *)(v34 | 0x80190000),
            bIgnoreCase);
        v35 = winrt::impl::consume_Windows_Web_Http_IHttpResponseMessage<winrt::Windows::Web::Http::IHttpResponseMessage>::Content(
                a1 + 152,
                a1 + 456);
        v36 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
                v35,
                a1 + 464);
        if ( *(_DWORD *)(a1 - 16) == 2 )
        {
          v37 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 752);
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v57, v37);
          throw (winrt::hresult_canceled *)v57;
        }
        *(_QWORD *)(a1 + 472) = 0;
        *(_QWORD *)(a1 + 480) = v36;
        *(_QWORD *)(a1 + 488) = 0;
        *(_BYTE *)(a1 + 496) = 1;
        v3 = v53;
        *v53 = 8;
        if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::Storage::Cloud::Downloader::Core::ProfileDataItemResponseHandlerImpl *,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit,winrt::Windows::Web::Http::HttpResponseMessage,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>,winrt::hstring,Windows::Internal::Storage::Cloud::Core::CorrelationVector,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>>::promise_type>(
                                 a1 + 472,
                                 a1) )
        {
LABEL_36:
          winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,1>::await_resume(
            a1 + 472,
            a1 + 504);
          winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 472);
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 464));
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 456));
          v38 = winrt::hstring::c_str((winrt::hstring *)(a1 + 504));
          Windows::Internal::Storage::Cloud::Downloader::Types::ProtocolConfigJsonParser::Parse(a1 + 512, v38);
          v39 = *((_QWORD *)v3 + 102);
          v40 = winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Security::Credentials::WebAccount>(
                  *(_QWORD *)(a1 + 832),
                  a1 + 584);
          v41 = winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(
                  v40,
                  a1 + 576);
          v42 = *(_QWORD *)(a1 + 120);
          Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::UpdateProtocolConfigCache(v39, v41, a1 + 512, v42);
          winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 584));
          *(_QWORD *)(a1 + 104) = v42;
          v43 = (const char **)(a1 + 32);
          v60 = *(_QWORD *)(a1 + 56);
          if ( v60 > 7 )
            v59 = *v43;
          std::wstring::wstring(a1 + 592);
          v45 = std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring>(
                  v44,
                  (_QWORD *)(a1 + 592));
          v46 = std::_Hash<std::_Umap_traits<std::wstring,std::vector<CloudStoreUtilities::FlatBufferAttrList>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<CloudStoreUtilities::FlatBufferAttrList>>>,0>>::_Find_last<std::wstring>(
                  (_QWORD *)(a1 + 512),
                  (_QWORD *)(a1 + 776),
                  a1 + 592,
                  v45)[1];
          if ( !v46 )
          {
            v46 = *(_QWORD *)(a1 + 520);
            v58 = v46;
          }
          std::wstring::~wstring(a1 + 592);
          v58 = *(_QWORD *)(a1 + 520);
          if ( v46 == v58 )
          {
            v60 = *(_QWORD *)(a1 + 56);
            if ( v60 <= 7 )
            {
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0xE4,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                (const char *)0x80070490LL,
                (int)"**!!##!!**LogProtocol Config Missing Config for %ls",
                (const char *)(a1 + 32),
                a1);
            }
            else
            {
              v59 = *v43;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0xE4,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                (const char *)0x80070490LL,
                (int)"**!!##!!**LogProtocol Config Missing Config for %ls",
                v59,
                a1);
            }
            winrt::Windows::ApplicationModel::AppExtensions::AppExtensionCatalog::operator=(
              *(_QWORD *)(a1 + 128) + 104LL,
              a1 + 400);
            __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__0A__std___std__QEAA_XZ(a1 + 512);
            winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 504);
            winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 400));
            winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 392));
            std::wstring::~wstring(a1 + 304);
            winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 208));
            winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
            winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
            winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
            std::wstring::~wstring(a1 + 32);
            if ( *(_QWORD *)(a1 + 24) )
              std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
          }
          else
          {
            std::wstring::wstring(a1 + 624);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
              v46 + 48,
              a1 + 656,
              a1 + 624);
            std::wstring::~wstring(a1 + 624);
            if ( *(_QWORD *)(a1 + 656) == *(_QWORD *)(v46 + 56) )
            {
              v60 = *(_QWORD *)(a1 + 56);
              if ( v60 <= 7 )
              {
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)0xEF,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                  (const char *)0x8007139FLL,
                  (int)"**!!##!!**LogProfile Data Roaming Home Cloud Not Found for %ls",
                  (const char *)(a1 + 32),
                  a1);
              }
              else
              {
                v59 = *v43;
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)0xEF,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                  (const char *)0x8007139FLL,
                  (int)"**!!##!!**LogProfile Data Roaming Home Cloud Not Found for %ls",
                  v59,
                  a1);
              }
              winrt::Windows::ApplicationModel::AppExtensions::AppExtensionCatalog::operator=(
                *(_QWORD *)(a1 + 128) + 104LL,
                a1 + 400);
              __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__0A__std___std__QEAA_XZ(a1 + 512);
              winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 504);
              winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 400));
              winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 392));
              std::wstring::~wstring(a1 + 304);
              winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 208));
              winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
              winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
              winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
              std::wstring::~wstring(a1 + 32);
              if ( *(_QWORD *)(a1 + 24) )
                std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
            }
            else
            {
              std::wstring::operator std::basic_string_view<unsigned short>(*(_QWORD *)(a1 + 656) + 48LL, a1 + 664);
              winrt::hstring::operator=(a1 + 96);
              v47 = winrt::hstring::c_str((winrt::hstring *)(a1 + 96));
              if ( Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::ValidateHttpsPrefixOnUrl(v48, v47) )
              {
                v60 = *(_QWORD *)(a1 + 56);
                if ( v60 <= 7 )
                {
                  wil::details::in1diag3::Log_HrMsg(
                    retaddr,
                    (void *)0xF9,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                    (const char *)0x8007139FLL,
                    (int)"**!!##!!**LogProfile Data Roaming Home Cloud Does Not Start With HTTPS:// in %ls",
                    (const char *)(a1 + 32),
                    a1);
                }
                else
                {
                  v59 = *v43;
                  wil::details::in1diag3::Log_HrMsg(
                    retaddr,
                    (void *)0xF9,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\http\\src\\cloudstorehomecloudmgr.cpp",
                    (const char *)0x8007139FLL,
                    (int)"**!!##!!**LogProfile Data Roaming Home Cloud Does Not Start With HTTPS:// in %ls",
                    v59,
                    a1);
                }
                winrt::Windows::ApplicationModel::AppExtensions::AppExtensionCatalog::operator=(
                  *(_QWORD *)(a1 + 128) + 104LL,
                  a1 + 400);
                __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__0A__std___std__QEAA_XZ(a1 + 512);
                winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 504);
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 400));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 392));
                std::wstring::~wstring(a1 + 304);
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 208));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
                winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
                std::wstring::~wstring(a1 + 32);
                if ( *(_QWORD *)(a1 + 24) )
                  std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
              }
              else
              {
                __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__0A__std___std__QEAA_XZ(a1 + 512);
                winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 504);
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 400));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 392));
                std::wstring::~wstring(a1 + 304);
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 208));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
LABEL_62:
                *(_QWORD *)(a1 + 688) = *(_QWORD *)(a1 + 96);
                v49 = winrt::Windows::Foundation::Uri::Uri(
                        (winrt::Windows::Foundation::Uri *)(a1 + 680),
                        (const struct winrt::param::hstring *)(a1 + 688));
                winrt::Windows::ApplicationModel::AppExtensions::AppExtensionCatalog::operator=(
                  *(_QWORD *)(a1 + 128) + 104LL,
                  v49);
                winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 680));
                winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
                std::wstring::~wstring(a1 + 32);
                if ( *(_QWORD *)(a1 + 24) )
                  std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
              }
            }
          }
          *(_QWORD *)(a1 + 720) = a1 - 112;
          v2 = v55;
          *v55 = 0;
          if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadUnitId>,winrt::hstring,winrt::hstring,winrt::hstring,std::shared_ptr<winrt::Windows::Internal::Storage::Cloud::Downloader::ILogger>,wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>,wil::com_ptr_t<Windows::Web::Http::IHttpClient,wil::err_exception_policy>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::IAccountInfoFetcher>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils>,std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadResult,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>,winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadProgress>::final_suspend_awaiter::await_suspend() )
          {
LABEL_65:
            std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::Storage::Cloud::CloudStoreHttpClient *,winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>::promise_type::~promise_type(a1 - 112);
            Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetHomeCloudv2Async_::_23_::_parameters_::__parameters_(v2 + 408);
            if ( *(_WORD *)(a1 + 10) )
              operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x3E0);
          }
        }
      }
      return;
    case 6:
      v20 = (_WORD *)(a1 + 8);
      goto LABEL_19;
    case 7:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 176);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 168));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
      std::wstring::~wstring(a1 + 32);
      if ( *(_QWORD *)(a1 + 24) )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
      goto LABEL_65;
    case 8:
      goto LABEL_36;
    case 9:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(a1 + 472);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 464));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 456));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 400));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 392));
      std::wstring::~wstring(a1 + 304);
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 208));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 152));
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)(a1 + 144));
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 96);
      std::wstring::~wstring(a1 + 32);
      if ( *(_QWORD *)(a1 + 24) )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)(a1 + 24));
      goto LABEL_65;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1801bc100  mov     r11, rsp
0x1801bc103  mov     [r11+10h], rbx
0x1801bc107  mov     [r11+18h], rsi
0x1801bc10b  mov     [r11+8], rcx
0x1801bc10f  push    rdi
0x1801bc110  push    r12
0x1801bc112  push    r13
0x1801bc114  push    r14
0x1801bc116  push    r15
0x1801bc118  sub     rsp, 200h
0x1801bc11f  mov     rax, cs:__security_cookie
0x1801bc126  xor     rax, rsp
0x1801bc129  mov     [rsp+228h+var_30], rax
0x1801bc131  mov     rsi, rcx
0x1801bc134  mov     [rsp+228h+var_1F8], rcx
0x1801bc139  mov     [rsp+228h+var_1C0], rcx
0x1801bc13e  lea     rbx, [rsi+8]
0x1801bc142  mov     [rsp+228h+var_1B8], rbx
0x1801bc147  movzx   eax, word ptr [rbx]
0x1801bc14a  mov     [rsp+228h+var_1D0], ax
0x1801bc14f  mov     r13d, 1
0x1801bc155  add     ax, r13w
0x1801bc159  cmp     ax, 0Ah; switch 11 cases
0x1801bc15d  ja      def_1801BC180; jumptable 00000001801BC180 default case, cases 1,5,6
0x1801bc163  mov     rdi, rbx
0x1801bc166  mov     [rsp+228h+var_1C8], rbx
0x1801bc16b  movsx   rax, ax
0x1801bc16f  lea     rdx, __ImageBase
0x1801bc176  mov     ecx, ds:(jpt_1801BC180 - 180000000h)[rdx+rax*4]
0x1801bc17d  add     rcx, rdx
0x1801bc180  jmp     rcx; switch jump
0x1801bc182  xor     r14d, r14d; jumptable 00000001801BC180 case 4
0x1801bc185  jmp     loc_1801BCE98
0x1801bc18a  xor     r14d, r14d; jumptable 00000001801BC180 case 3
0x1801bc18d  mov     r15, [rbx+330h]
0x1801bc194  lea     rcx, [r15+8]
0x1801bc198  lea     rdx, [rsi+10h]
0x1801bc19c  call    ?shared_from_this@?$enable_shared_from_this@VIAccountInfoFetcher@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@QEAA?AV?$shared_ptr@VIAccountInfoFetcher@Core@Downloader@Cloud@Storage@Internal@Windows@@@2@XZ; std::enable_shared_from_this<Windows::Internal::Storage::Cloud::Downloader::Core::IAccountInfoFetcher>::shared_from_this(void)
0x1801bc1a1  nop
0x1801bc1a2  lea     rax, [rsi-70h]
0x1801bc1a6  mov     [rsi+80h], rax
0x1801bc1ad  mov     [rax+30h], r13b
0x1801bc1b1  lea     rdx, [rsi+30h]
0x1801bc1b5  mov     [rsi+320h], rdx
0x1801bc1bc  lea     rbx, [rsi+20h]
0x1801bc1c0  add     rdx, 330h
0x1801bc1c7  mov     rcx, rbx
0x1801bc1ca  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x1801bc1cf  nop
0x1801bc1d0  mov     r9, [rsi+38h]
0x1801bc1d4  mov     [rsp+228h+var_100], r9
0x1801bc1dc  cmp     r9, 7
0x1801bc1e0  jbe     short loc_1801BC1EF
0x1801bc1e2  mov     r10, [rbx]
0x1801bc1e5  mov     [rsp+228h+var_118], r10
0x1801bc1ed  jmp     short loc_1801BC1F2
0x1801bc1ef  mov     r10, rbx
0x1801bc1f2  lea     rdx, [rsi+40h]
0x1801bc1f6  mov     rcx, rbx
0x1801bc1f9  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1801bc1fe  mov     r8, [rax]
0x1801bc201  cmp     r9, 7
0x1801bc205  jbe     short loc_1801BC214
0x1801bc207  mov     rdx, [rbx]
0x1801bc20a  mov     [rsp+228h+var_118], rdx
0x1801bc212  jmp     short loc_1801BC217
0x1801bc214  mov     rdx, rbx
0x1801bc217  lea     rcx, [rsi+48h]
0x1801bc21b  mov     rax, cs:__imp__o_towlower
0x1801bc222  mov     qword ptr [rsp+228h+bIgnoreCase], rax
0x1801bc227  mov     r9, r10
0x1801bc22a  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1801bc22f  mov     rax, [rsi+38h]
0x1801bc233  mov     [rsp+228h+var_100], rax
0x1801bc23b  cmp     rax, 7
0x1801bc23f  jbe     short loc_1801BC24C
0x1801bc241  mov     rbx, [rbx]
0x1801bc244  mov     [rsp+228h+var_118], rbx
0x1801bc24c  lea     rdx, [rsi+50h]
0x1801bc250  mov     rcx, [rsi+340h]
0x1801bc257  call    ??$as@UWebAccount@Credentials@Security@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x1801bc25c  mov     rcx, rax
0x1801bc25f  lea     rdx, [rsi+58h]
0x1801bc263  call    ?Id@?$consume_Windows_Security_Credentials_IWebAccount2@UWebAccount@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(void)
0x1801bc268  nop
0x1801bc269  mov     rcx, rax; this
0x1801bc26c  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801bc271  mov     r9, rbx
0x1801bc274  mov     r8, rax
0x1801bc277  lea     rdx, [rsi+60h]
0x1801bc27b  mov     rcx, r15
0x1801bc27e  call    ?TryLoadProtocolHomeCloudInfoFromCache@CloudStoreHomeCloudMgr@Cloud@Storage@Internal@Windows@@AEAA?AUHomeCloudInfo@2345@PEBG0@Z; Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::TryLoadProtocolHomeCloudInfoFromCache(ushort const *,ushort const *)
0x1801bc283  nop
0x1801bc284  lea     rcx, [rsi+58h]
0x1801bc288  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bc28d  nop
0x1801bc28e  lea     rcx, [rsi+50h]; this
0x1801bc292  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc297  lea     rcx, [rsi+70h]
0x1801bc29b  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x1801bc2a0  mov     rbx, [rax]
0x1801bc2a3  mov     [rsi+78h], rbx
0x1801bc2a7  call    cs:__imp_rand
0x1801bc2ad  mov     r8d, eax
0x1801bc2b0  mov     eax, 91A2B3C5h
0x1801bc2b5  imul    r8d
0x1801bc2b8  add     edx, r8d
0x1801bc2bb  sar     edx, 0Dh
0x1801bc2be  mov     ecx, edx
0x1801bc2c0  shr     ecx, 1Fh
0x1801bc2c3  add     edx, ecx
0x1801bc2c5  imul    ecx, edx, 3840h
0x1801bc2cb  sub     r8d, ecx
0x1801bc2ce  lea     eax, [r8-1C20h]
0x1801bc2d5  cdqe
0x1801bc2d7  imul    rcx, rax, 989680h
0x1801bc2de  mov     rax, 0FFFFFF36D5964000h
0x1801bc2e8  add     rcx, rax
0x1801bc2eb  add     rcx, rbx
0x1801bc2ee  mov     rax, [rsi+68h]
0x1801bc2f2  mov     [rsp+228h+var_1A8], rax
0x1801bc2fa  cmp     rax, rcx
0x1801bc2fd  jbe     short loc_1801BC311
0x1801bc2ff  mov     rax, [rsi+60h]
0x1801bc303  mov     [rsp+228h+var_1B0], rax
0x1801bc308  test    rax, rax
0x1801bc30b  jnz     loc_1801BCD6D
0x1801bc311  lea     rcx, [rsi+90h]; this
0x1801bc318  call    ??0HttpRequestMessage@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::HttpRequestMessage::HttpRequestMessage(void)
0x1801bc31d  nop
0x1801bc31e  lea     rcx, [rsi+98h]; this
0x1801bc325  call    ??0HttpResponseMessage@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::HttpResponseMessage::HttpResponseMessage(void)
0x1801bc32a  nop
0x1801bc32b  mov     rbx, [r15+80h]
0x1801bc332  mov     rax, [rbx]
0x1801bc335  mov     r15, [rax+8]
0x1801bc339  lea     rdx, [rsi+0A0h]
0x1801bc340  mov     rcx, [rsi+340h]
0x1801bc347  call    ??$as@UWebAccount@Credentials@Security@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x1801bc34c  lea     rdx, [rsi+0A8h]
0x1801bc353  mov     r8, rax
0x1801bc356  mov     rcx, rbx
0x1801bc359  mov     rax, r15
0x1801bc35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc361  nop
0x1801bc362  mov     ecx, [rsi-10h]
0x1801bc365  nop
0x1801bc366  cmp     ecx, 2
0x1801bc369  jnz     short loc_1801BC39B
0x1801bc36b  lea     rcx, [rsi+2D8h]
0x1801bc372  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1801bc377  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1801bc37a  lea     rcx, [rsp+228h+pExceptionObject]; this
0x1801bc382  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1801bc387  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1801bc38e  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x1801bc396  call    _CxxThrowException_0
0x1801bc39b  lea     rcx, [rsi+0B0h]
0x1801bc3a2  mov     [rcx], r14
0x1801bc3a5  mov     [rsi+0B8h], rax
0x1801bc3ac  mov     [rsi+0C0h], r14
0x1801bc3b3  mov     [rsi+0C8h], r13b
0x1801bc3ba  mov     eax, 6
0x1801bc3bf  mov     r13, [rsp+228h+var_1C8]
0x1801bc3c4  mov     [r13+0], ax
0x1801bc3c9  mov     rdx, [rsp+228h+var_1C0]
0x1801bc3ce  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpCredentialsHeaderValue@Headers@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@U1234@U1234@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@UHttpCredentialsHeaderValue@Headers@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpCredentialsHeaderValue@Headers@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@U1234@U1234@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue>>::promise_type>)
0x1801bc3d3  test    al, al
0x1801bc3d5  jz      short loc_1801BC44F
0x1801bc3d7  jmp     loc_1801BCEC5
0x1801bc3dc  lea     rcx, [rsi+0B0h]; jumptable 00000001801BC180 case 8
0x1801bc3e3  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x1801bc3e8  nop
0x1801bc3e9  lea     rcx, [rsi+0A8h]; this
0x1801bc3f0  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc3f5  nop
0x1801bc3f6  lea     rcx, [rsi+98h]; this
0x1801bc3fd  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc402  nop
0x1801bc403  lea     rcx, [rsi+90h]; this
0x1801bc40a  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc40f  nop
0x1801bc410  lea     rcx, [rsi+60h]
0x1801bc414  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bc419  nop
0x1801bc41a  lea     rcx, [rsi+20h]
0x1801bc41e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801bc423  nop
0x1801bc424  mov     rax, [rsi+18h]
0x1801bc428  mov     [rsp+228h+var_1E8], rax
0x1801bc42d  xor     r14d, r14d
0x1801bc430  test    rax, rax
0x1801bc433  jz      short loc_1801BC444
0x1801bc435  mov     rcx, [rsi+18h]; this
0x1801bc439  mov     [rsp+228h+var_1E8], rcx
0x1801bc43e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801bc443  nop
0x1801bc444  jmp     loc_1801BCE98
0x1801bc449  xor     r14d, r14d; jumptable 00000001801BC180 case 7
0x1801bc44c  mov     r13, rbx
0x1801bc44f  lea     rbx, [rsi+0D0h]
0x1801bc456  lea     rdi, [rsi+0B0h]
0x1801bc45d  mov     rdx, rbx
0x1801bc460  mov     rcx, rdi
0x1801bc463  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,1>::await_resume(void)
0x1801bc468  nop
0x1801bc469  mov     rcx, rdi
0x1801bc46c  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UDownloadErrorDetails@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::Downloader::DownloadErrorDetails>,1>>(void)
0x1801bc471  nop
0x1801bc472  lea     rcx, [rsi+0A8h]; this
0x1801bc479  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc47e  lea     rdi, [rsi+0D8h]
0x1801bc485  lea     r15, [rsi+90h]
0x1801bc48c  mov     [rsp+228h+var_1E0], r15
0x1801bc491  mov     rdx, rdi
0x1801bc494  mov     rcx, r15
0x1801bc497  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(void)
0x1801bc49c  nop
0x1801bc49d  mov     rdx, rbx
0x1801bc4a0  mov     rcx, rax
0x1801bc4a3  call    ?Authorization@?$consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection@UIHttpRequestHeaderCollection@Headers@Http@Web@Windows@winrt@@@impl@winrt@@QEBA@AEBUHttpCredentialsHeaderValue@Headers@Http@Web@Windows@3@@Z; winrt::impl::consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection<winrt::Windows::Web::Http::Headers::IHttpRequestHeaderCollection>::Authorization(winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue const &)
0x1801bc4a8  nop
0x1801bc4a9  mov     rcx, rdi; this
0x1801bc4ac  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc4b1  lea     r12, [rsi+0E0h]
0x1801bc4b8  mov     rdx, r12
0x1801bc4bb  mov     rcx, r15
0x1801bc4be  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(void)
0x1801bc4c3  mov     [rsp+228h+var_1D8], rax
0x1801bc4c8  mov     r13, [r13+330h]
0x1801bc4cf  lea     rdx, [rsi+108h]
0x1801bc4d6  mov     rcx, [r13+18h]
0x1801bc4da  call    ?BuildClientInfoHeaderString@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@QEAA?AUhstring@winrt@@XZ; Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::BuildClientInfoHeaderString(void)
0x1801bc4df  nop
0x1801bc4e0  lea     rdi, [rsi+0E8h]
0x1801bc4e7  mov     rax, [rax]
0x1801bc4ea  mov     [rdi], rax
0x1801bc4ed  lea     rbx, [rsi+110h]
0x1801bc4f4  lea     rdx, aXAfsClientinfo; "X-AFS-ClientInfo"
0x1801bc4fb  mov     rcx, rbx; this
0x1801bc4fe  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801bc503  mov     r8, rdi
0x1801bc506  mov     rdx, rbx
0x1801bc509  mov     rcx, [rsp+228h+var_1D8]
0x1801bc50e  call    ?Append@?$consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection@UIHttpRequestHeaderCollection@Headers@Http@Web@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Web_Http_Headers_IHttpRequestHeaderCollection<winrt::Windows::Web::Http::Headers::IHttpRequestHeaderCollection>::Append(winrt::param::hstring const &,winrt::param::hstring const &)
0x1801bc513  nop
0x1801bc514  lea     rcx, [rsi+108h]
0x1801bc51b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bc520  nop
0x1801bc521  mov     rcx, r12; this
0x1801bc524  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x1801bc529  lea     rdi, [rsi+130h]
0x1801bc530  mov     [rsp+228h+var_1D8], rdi
0x1801bc535  xorps   xmm0, xmm0
0x1801bc538  movups  xmmword ptr [rdi], xmm0
0x1801bc53b  mov     [rsi+140h], r14
0x1801bc542  mov     qword ptr [rsi+148h], 7
0x1801bc54d  xor     eax, eax
0x1801bc54f  mov     [rdi], ax
0x1801bc552  lea     rdx, [rsi+150h]
0x1801bc559  mov     rcx, r13
0x1801bc55c  call    ?GetServiceEnvironmentConfig@CloudStoreHomeCloudMgr@Cloud@Storage@Internal@Windows@@AEAA?AV?$shared_ptr@VIServiceEnvironmentConfig@Cloud@Storage@Internal@Windows@@@std@@PEBG@Z; Windows::Internal::Storage::Cloud::CloudStoreHomeCloudMgr::GetServiceEnvironmentConfig(ushort const *)
0x1801bc561  nop
0x1801bc562  mov     rcx, [rax]
0x1801bc565  mov     rax, [rcx]
0x1801bc568  mov     rax, [rax+18h]
0x1801bc56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc571  cmp     qword ptr [rax+18h], 7
0x1801bc576  jbe     short loc_1801BC57B
0x1801bc578  mov     rax, [rax]
0x1801bc57b  mov     rdx, rax
0x1801bc57e  mov     rcx, rdi
0x1801bc581  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801bc586  nop
0x1801bc587  mov     rax, [rsi+158h]
0x1801bc58e  mov     [rsp+228h+var_198], rax
0x1801bc596  test    rax, rax
0x1801bc599  jz      short loc_1801BC5B0
0x1801bc59b  mov     rcx, [rsi+158h]; this
0x1801bc5a2  mov     [rsp+228h+var_198], rcx
0x1801bc5aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801bc5af  nop
0x1801bc5b0  jmp     short loc_1801BC5C4
0x1801bc5b2  xor     r14d, r14d
0x1801bc5b5  mov     rsi, [rsp+228h+var_1F8]
0x1801bc5ba  mov     rdi, [rsp+228h+var_1D8]
0x1801bc5bf  mov     r15, [rsp+228h+var_1E0]
0x1801bc5c4  lea     rbx, [rsi+168h]
0x1801bc5cb  mov     rdx, rdi
0x1801bc5ce  mov     rcx, rbx
0x1801bc5d1  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1801bc5d6  lea     rdi, [rsi+160h]
0x1801bc5dd  mov     rdx, rbx; struct winrt::param::hstring *
0x1801bc5e0  mov     rcx, rdi; this
0x1801bc5e3  call    ??0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@3@@Z; winrt::Windows::Foundation::Uri::Uri(winrt::param::hstring const &)
0x1801bc5e8  nop
0x1801bc5e9  mov     rdx, rax
0x1801bc5ec  mov     rcx, r15
0x1801bc5ef  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemRequestUnit@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemRequestUnit@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@AEBUProfileDataItemRequestUnit@Downloader@Cloud@Storage@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit>::Append(winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemRequestUnit const &)
0x1801bc5f4  nop
  ... truncated ...
```
