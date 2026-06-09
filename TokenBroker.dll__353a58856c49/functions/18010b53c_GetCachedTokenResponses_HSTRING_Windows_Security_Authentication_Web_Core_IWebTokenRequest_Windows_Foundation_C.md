# GetCachedTokenResponses(HSTRING__ *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,CacheEntryLookupResult *,Windows::Internal::Security::Authentication::TokenBroker::TB_REQUEST_ID *,Windows::Storage::Streams::IBuffer * *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x18010b53c`
- end: `0x18010bd0e`
- name: `?GetCachedTokenResponses@@YAJPEAUHSTRING__@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@7@PEAW4CacheEntryLookupResult@@PEAUTB_REQUEST_ID@TokenBroker@56Internal@7@PEAPEAUIBuffer@Streams@Storage@7@5@Z`
- size: `2002`
- prototype: `__int64 __fastcall(HSTRING string2, __int64, __int64, _DWORD *, HSTRING, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ee994`

## callees

- `0x1800050b0`
- `0x180007350`
- `0x18000bd40`
- `0x18001a510`
- `0x1800344b8`
- `0x1800454f0`
- `0x18004a59c`
- `0x18004e750`
- `0x18004e850`
- `0x18004fdbc`
- `0x180053cfc`
- `0x180063ff0`
- `0x18007f6e0`
- `0x18008e690`
- `0x18009adec`
- `0x180109088`
- `0x18010913c`
- `0x18010a138`
- `0x18010a528`
- `0x18010b384`
- `0x18010b53c`
- `0x18010bd14`
- `0x18010bffc`
- `0x18010c07c`
- `0x18010c148`
- `0x18010c210`
- `0x18010c284`
- `0x18010c2f8`
- `0x18010c554`
- `0x18010dc5c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010b5fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bab8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010b5fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b5ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010baa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b5ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010baa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010b5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ba52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ba94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bbe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010b5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ba52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ba94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bbe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bc4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010bce5`

## string_xrefs

- `0x18010bac2`: `EnumApiCacheExpiration`
- `0x18010bb35`: `ProviderDefaultAccountCacheExpiration`
- `0x18010bb73`: `UICacheExpiration`
- `0x18010baf1`: `CacheExpiration`
- `0x18010b5ba`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010b750`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010b7b8`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010b892`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010b96a`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ba1f`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`
- `0x18010ba7d`: `onecore\ds\security\tokenbroker\datastore\lib\token.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetCachedTokenResponses(
        HSTRING string2,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        HSTRING a5,
        _QWORD *a6,
        _QWORD *a7)
{
  int v10; // eax
  int PluginPFN; // ebx
  PCWSTR StringRawBuffer; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int TokenCacheEntry; // eax
  int v18; // r9d
  int v19; // r15d
  int v20; // eax
  struct Windows::Storage::Streams::IBuffer **v21; // r9
  int BufferFromByteArray; // eax
  rsize_t v23; // rdx
  int v24; // ebx
  HSTRING v25; // rsi
  int v26; // esi
  __int64 v27; // rdx
  HSTRING *v28; // rax
  int CachedJson; // eax
  __int64 v30; // r14
  __int64 (__fastcall *v31)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v32; // eax
  __int64 v33; // rdx
  PCWSTR v34; // rax
  GlobalCacheExpirationRegistry *v35; // rax
  GlobalCacheExpirationRegistry *Instance; // rax
  GlobalCacheExpirationRegistry *v37; // rax
  GlobalCacheExpirationRegistry *v38; // rax
  int v39; // esi
  __int64 v40; // rax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  bool v43; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v44; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v46; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v47[2]; // [rsp+70h] [rbp-90h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v48; // [rsp+78h] [rbp-88h] BYREF
  void *Source; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v53; // [rsp+A0h] [rbp-60h] BYREF
  rsize_t SourceSize; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v55; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-48h] BYREF
  int v57; // [rsp+C0h] [rbp-40h]
  __int128 v58; // [rsp+C8h] [rbp-38h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int64 v60; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-18h]
  HSTRING v62; // [rsp+F0h] [rbp-10h] BYREF
  char v63; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v61 = a3;
  v55 = string2;
  v62 = a5;
  string = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL))(a2, &string);
  PluginPFN = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
      (const char *)(unsigned int)v10,
      v41);
LABEL_3:
    if ( string )
      WindowsDeleteString(string);
    return (unsigned int)PluginPFN;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  _o__wcsicmp(L"enumerate.accounts.local", StringRawBuffer);
  if ( IsTokenCachingDisabled() )
  {
    if ( (unsigned int)dword_180175000 > 4 )
    {
      v55 = (HSTRING)"The test hook to disable caching is set";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v14,
        (unsigned int)byte_180157DA1,
        v15,
        v16,
        (__int64)&v55);
    }
    *a4 = 0;
    goto LABEL_76;
  }
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v46 = 0;
  LODWORD(v60) = 0;
  v51 = 0;
  TokenCacheEntry = FindTokenCacheEntry(
                      string2,
                      (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v56,
                      (__int64)&v46,
                      (__int64)&v60,
                      (__int64)&v51);
  v19 = TokenCacheEntry;
  if ( (unsigned int)dword_180175000 > 5 )
  {
    LODWORD(v44) = TokenCacheEntry;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180175000,
      (unsigned int)byte_180157D79,
      0,
      v18,
      (__int64)&v44);
  }
  if ( v19 >= 0 )
  {
    Source = 0;
    LODWORD(SourceSize) = 0;
    v52 = 0;
    LODWORD(v44) = 0;
    v48 = 0;
    LODWORD(v53) = 0;
    v20 = ReadTokenCacheEntry(
            v46,
            3,
            (__int64)&v56,
            (__int64)&Source,
            (int *)&SourceSize,
            &v52,
            &v44,
            (__int64)&v48,
            (int *)&v53);
    PluginPFN = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)v20,
        v42);
LABEL_17:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Source);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v46);
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v56);
      goto LABEL_3;
    }
    *(_QWORD *)v47 = 0;
    BufferFromByteArray = Windows::Internal::Security::Authentication::TokenBroker::GetBufferFromByteArray(
                            v48,
                            (unsigned __int8 *)(unsigned int)v53,
                            (unsigned int)v47,
                            v21);
    PluginPFN = BufferFromByteArray;
    if ( BufferFromByteArray < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
        (const char *)(unsigned int)BufferFromByteArray,
        v42);
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
      goto LABEL_17;
    }
    v24 = SourceSize;
    v25 = v62;
    memcpy_s_3(v62 + 1, v23, Source, (unsigned int)SourceSize);
    *(_DWORD *)v25 = v24;
    v62 = (HSTRING)v51;
    v63 = 1;
    if ( (unsigned __int8)IsCacheEntryExpired(v52, &v62)
      || (v26 = (int)v44, (unsigned __int8)IsInvalidExpirationForUIRequired((unsigned int)v44, v52)) )
    {
      *a4 = 2;
      *a6 = 0;
      if ( a7 )
        *a7 = 0;
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl)
        || !IsXboxConsole() )
      {
LABEL_34:
        if ( a7 && IsTokenRequestLoggingEnabled() )
        {
          v30 = v61;
          GetCachedTokenRequest(v55, a2, v61, a7);
        }
        else
        {
          v30 = v61;
        }
        v50 = 0;
        v31 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v32 = v31(a2, &v50);
        PluginPFN = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11C,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
            (const char *)(unsigned int)v32,
            v42);
LABEL_50:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          goto LABEL_20;
        }
        if ( !Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider(v50) )
        {
          WindowsDeleteString(0);
          v44 = 0;
          PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                        v50,
                        &v44);
          if ( PluginPFN < 0 )
          {
            v33 = 293;
            goto LABEL_54;
          }
          v43 = 1;
          v34 = WindowsGetStringRawBuffer(string, 0);
          if ( (unsigned int)_o__wcsicmp(L"enumerate.accounts.local", v34) )
          {
            Instance = GlobalCacheExpirationRegistry::GetInstance(L"CacheExpiration");
            PluginPFN = GlobalCacheExpirationRegistry::IsEntryValid(
                          Instance,
                          (const struct Windows::Internal::String *)&v44,
                          v51,
                          &v43);
            if ( PluginPFN < 0 )
            {
              v33 = 306;
              goto LABEL_54;
            }
            if ( !v30
              && !Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsConnectedAccountProvider(v50) )
            {
              v37 = GlobalCacheExpirationRegistry::GetInstance(L"ProviderDefaultAccountCacheExpiration");
              PluginPFN = GlobalCacheExpirationRegistry::IsEntryValid(
                            v37,
                            (const struct Windows::Internal::String *)&v44,
                            v51,
                            &v43);
              if ( PluginPFN < 0 )
              {
                v33 = 314;
                goto LABEL_54;
              }
            }
          }
          else
          {
            v35 = GlobalCacheExpirationRegistry::GetInstance(L"EnumApiCacheExpiration");
            PluginPFN = GlobalCacheExpirationRegistry::IsEntryValid(
                          v35,
                          (const struct Windows::Internal::String *)&v44,
                          v51,
                          &v43);
            if ( PluginPFN < 0 )
            {
              v33 = 302;
              goto LABEL_54;
            }
          }
          if ( v26 == 3 )
          {
            if ( !v43 )
            {
LABEL_70:
              if ( (unsigned int)dword_180175000 > 4 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  &dword_180175000,
                  byte_180157CB3,
                  0,
                  0);
              *a4 = 2;
              *a6 = 0;
              if ( v44 )
                WindowsDeleteString(v44);
LABEL_74:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Source);
              goto LABEL_75;
            }
            v38 = GlobalCacheExpirationRegistry::GetInstance(L"UICacheExpiration");
            PluginPFN = GlobalCacheExpirationRegistry::IsEntryValid(
                          v38,
                          (const struct Windows::Internal::String *)&v44,
                          v51,
                          &v43);
            if ( PluginPFN < 0 )
            {
              v33 = 325;
LABEL_54:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v33,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
                (const char *)(unsigned int)PluginPFN,
                v42);
              if ( v44 )
                WindowsDeleteString(v44);
              goto LABEL_50;
            }
          }
          if ( !v43 )
            goto LABEL_70;
          if ( v44 )
            WindowsDeleteString(v44);
        }
        if ( v26 )
        {
          v39 = v26 - 2;
          if ( v39 )
          {
            if ( v39 == 1 )
              *a4 = 3;
          }
          else
          {
            *a4 = 4;
          }
        }
        else
        {
          *a4 = 1;
        }
        v40 = *(_QWORD *)v47;
        *(_QWORD *)v47 = 0;
        *a6 = v40;
        goto LABEL_74;
      }
      SourceSize = 0;
      v52 = 0;
      v44 = 0;
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
      PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBrokerInternalStaticsT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics13>(&v44);
      if ( PluginPFN < 0 )
      {
        v27 = 225;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)PluginPFN,
          v42);
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
        goto LABEL_20;
      }
      PluginPFN = (*(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)v44 + 48LL))(v44, &v52);
      if ( PluginPFN < 0 )
      {
        v27 = 228;
        goto LABEL_27;
      }
      v28 = (HSTRING *)Windows::Internal::StringReference::StringReference(&v62, L"currentBootId");
      CachedJson = RetrieveCachedJsonField<unsigned __int64>(v46, *v28);
      v19 = CachedJson;
      if ( CachedJson == -2089484279 )
      {
        if ( (unsigned int)dword_180175000 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_180175000,
            byte_180157D2D,
            0,
            0);
        goto LABEL_33;
      }
      if ( CachedJson >= 0 )
      {
        if ( SourceSize == v52 )
        {
LABEL_33:
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
          goto LABEL_34;
        }
        if ( (unsigned int)dword_180175000 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_180175000,
            byte_180157CF5,
            0,
            0);
        PluginPFN = ClearSpecificCacheEntry(
                      v55,
                      (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v56,
                      0);
        if ( PluginPFN < 0 )
        {
          v27 = 258;
          goto LABEL_27;
        }
        *a4 = 0;
        *a6 = 0;
        if ( a7 )
          *a7 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\token.cpp",
          (const char *)(unsigned int)CachedJson,
          v42);
      }
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v44);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Source);
    goto LABEL_91;
  }
  *a4 = -1;
  if ( v19 == -2147024894 )
  {
    *a4 = 0;
LABEL_75:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v46);
    Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v56);
LABEL_76:
    if ( string )
      WindowsDeleteString(string);
    return 0;
  }
LABEL_91:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v46);
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v56);
  if ( string )
    WindowsDeleteString(string);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18010b53c  push    rbp
0x18010b53e  push    rbx
0x18010b53f  push    rsi
0x18010b540  push    rdi
0x18010b541  push    r12
0x18010b543  push    r13
0x18010b545  push    r14
0x18010b547  push    r15
0x18010b549  lea     rbp, [rsp-28h]
0x18010b54e  sub     rsp, 128h
0x18010b555  mov     rax, cs:__security_cookie
0x18010b55c  xor     rax, rsp
0x18010b55f  mov     [rbp+60h+var_50], rax
0x18010b563  mov     rdi, r9
0x18010b566  mov     r15, r8
0x18010b569  mov     [rbp+60h+var_78], r8
0x18010b56d  mov     r13, rdx
0x18010b570  mov     rsi, rcx
0x18010b573  mov     [rbp+60h+var_B0], rcx
0x18010b577  mov     rax, [rbp+60h+arg_20]
0x18010b57e  mov     [rbp+60h+var_70], rax
0x18010b582  mov     r12, [rbp+60h+arg_28]
0x18010b589  mov     r14, [rbp+60h+arg_30]
0x18010b590  mov     [rsp+160h+string], 0
0x18010b599  mov     rax, [rdx]
0x18010b59c  lea     rdx, [rsp+160h+string]
0x18010b5a1  mov     rcx, r13
0x18010b5a4  mov     rax, [rax+38h]
0x18010b5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b5ad  mov     ebx, eax
0x18010b5af  test    eax, eax
0x18010b5b1  jns     short loc_18010B5E3
0x18010b5b3  mov     rcx, [rbp+68h]; this
0x18010b5b7  mov     r9d, eax; char *
0x18010b5ba  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010b5c1  mov     edx, 4Dh ; 'M'; void *
0x18010b5c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b5cb  nop
0x18010b5cc  mov     rcx, [rsp+160h+string]; string
0x18010b5d1  test    rcx, rcx
0x18010b5d4  jz      short loc_18010B5DC
0x18010b5d6  call    cs:__imp_WindowsDeleteString
0x18010b5dc  mov     eax, ebx
0x18010b5de  jmp     loc_18010BCEE
0x18010b5e3  xor     edx, edx; length
0x18010b5e5  mov     rcx, [rsp+160h+string]; string
0x18010b5ea  call    cs:__imp_WindowsGetStringRawBuffer
0x18010b5f0  mov     rdx, rax
0x18010b5f3  lea     rcx, aEnumerateAccou; "enumerate.accounts.local"
0x18010b5fa  call    cs:__imp__o__wcsicmp
0x18010b600  call    ?IsTokenCachingDisabled@@YA_NXZ; IsTokenCachingDisabled(void)
0x18010b605  xor     ebx, ebx
0x18010b607  test    al, al
0x18010b609  jz      short loc_18010B63D
0x18010b60b  mov     eax, cs:dword_180175000
0x18010b611  cmp     eax, 4
0x18010b614  jbe     short loc_18010B636
0x18010b616  lea     rax, aTheTestHookToD; "The test hook to disable caching is set"
0x18010b61d  mov     [rbp+60h+var_B0], rax
0x18010b621  lea     rax, [rbp+60h+var_B0]
0x18010b625  mov     [rsp+160h+var_140], rax
0x18010b62a  lea     rdx, byte_180157DA1
0x18010b631  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010b636  mov     [rdi], ebx
0x18010b638  jmp     loc_18010BC2E
0x18010b63d  mov     [rbp+60h+var_A8], rbx
0x18010b641  mov     [rbp+60h+var_A0], ebx
0x18010b644  xorps   xmm0, xmm0
0x18010b647  movdqu  [rbp+60h+var_98], xmm0
0x18010b64c  mov     [rbp+60h+var_88], rbx
0x18010b650  mov     [rsp+160h+var_F8], rbx
0x18010b655  mov     dword ptr [rbp+60h+var_80], ebx
0x18010b658  mov     [rbp+60h+var_D0], rbx
0x18010b65c  lea     rax, [rbp+60h+var_D0]
0x18010b660  mov     [rsp+160h+var_128], rax; __int64
0x18010b665  lea     rax, [rbp+60h+var_80]
0x18010b669  mov     [rsp+160h+var_130], rax; __int64
0x18010b66e  lea     rax, [rsp+160h+var_F8]
0x18010b673  mov     [rsp+160h+var_138], rax; __int64
0x18010b678  lea     rax, [rbp+60h+var_A8]
0x18010b67c  mov     [rsp+160h+var_140], rax; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x18010b681  mov     r9d, 2
0x18010b687  mov     r8, r15
0x18010b68a  mov     rdx, r13
0x18010b68d  mov     rcx, rsi; string2
0x18010b690  call    ?FindTokenCacheEntry@@YAJQEAUHSTRING__@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@7@W4StoredObjectType@TokenBroker@56Internal@7@AEAVStoredObjectId@TokenBroker@56Internal@7@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAKPEA_J@Z; FindTokenCacheEntry(HSTRING__ * const,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *,__int64 *)
0x18010b695  mov     r15d, eax
0x18010b698  mov     ecx, cs:dword_180175000
0x18010b69e  cmp     ecx, 5
0x18010b6a1  jbe     short loc_18010B6C7
0x18010b6a3  mov     dword ptr [rsp+160h+var_108], eax
0x18010b6a7  lea     rax, [rsp+160h+var_108]
0x18010b6ac  mov     [rsp+160h+var_140], rax
0x18010b6b1  xor     r8d, r8d
0x18010b6b4  lea     rdx, byte_180157D79
0x18010b6bb  lea     rcx, dword_180175000
0x18010b6c2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18010b6c7  test    r15d, r15d
0x18010b6ca  jns     short loc_18010B6E6
0x18010b6cc  mov     dword ptr [rdi], 0FFFFFFFFh
0x18010b6d2  cmp     r15d, 80070002h
0x18010b6d9  jnz     loc_18010BCC6
0x18010b6df  mov     [rdi], ebx
0x18010b6e1  jmp     loc_18010BC19
0x18010b6e6  mov     [rbp+60h+Source], rbx
0x18010b6ea  mov     dword ptr [rbp+60h+SourceSize], ebx
0x18010b6ed  mov     [rbp+60h+var_C8], rbx
0x18010b6f1  mov     dword ptr [rsp+160h+var_108], ebx
0x18010b6f5  mov     [rsp+160h+var_E8], rbx
0x18010b6fa  mov     dword ptr [rbp+60h+var_C0], ebx
0x18010b6fd  lea     rax, [rbp+60h+var_C0]
0x18010b701  mov     [rsp+160h+var_120], rax; __int64
0x18010b706  lea     rax, [rsp+160h+var_E8]
0x18010b70b  mov     [rsp+160h+var_128], rax; __int64
0x18010b710  lea     rax, [rsp+160h+var_108]
0x18010b715  mov     [rsp+160h+var_130], rax; __int64
0x18010b71a  lea     rax, [rbp+60h+var_C8]
0x18010b71e  mov     [rsp+160h+var_138], rax; __int64
0x18010b723  lea     rax, [rbp+60h+SourceSize]
0x18010b727  mov     [rsp+160h+var_140], rax; int
0x18010b72c  lea     r9, [rbp+60h+Source]
0x18010b730  lea     r8, [rbp+60h+var_A8]
0x18010b734  mov     edx, 3
0x18010b739  mov     rcx, [rsp+160h+var_F8]; unsigned __int16 *
0x18010b73e  call    ?ReadTokenCacheEntry@@YAJPEBGW4SerializedObjectType@TokenBroker@Authentication@Security@Internal@Windows@@AEAVStoredObjectId@23456@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAKPEA_JPEAW4WebTokenRequestStatus@Core@Web@346@34@Z; ReadTokenCacheEntry(ushort const *,Windows::Internal::Security::Authentication::TokenBroker::SerializedObjectType,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *,__int64 *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x18010b743  mov     ebx, eax
0x18010b745  test    eax, eax
0x18010b747  jns     short loc_18010B790
0x18010b749  mov     rcx, [rbp+68h]; this
0x18010b74d  mov     r9d, eax; char *
0x18010b750  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010b757  mov     edx, 0A5h; void *
0x18010b75c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b761  nop
0x18010b762  lea     rcx, [rsp+160h+var_E8]
0x18010b767  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010b76c  nop
0x18010b76d  lea     rcx, [rbp+60h+Source]
0x18010b771  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010b776  nop
0x18010b777  lea     rcx, [rsp+160h+var_F8]
0x18010b77c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18010b781  nop
0x18010b782  lea     rcx, [rbp+60h+var_A8]; this
0x18010b786  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x18010b78b  jmp     loc_18010B5CC
0x18010b790  mov     qword ptr [rsp+160h+var_F0], 0
0x18010b799  lea     r8, [rsp+160h+var_F0]; unsigned int
0x18010b79e  mov     edx, dword ptr [rbp+60h+var_C0]; unsigned __int8 *
0x18010b7a1  mov     rcx, [rsp+160h+var_E8]; this
0x18010b7a6  call    ?GetBufferFromByteArray@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAEIPEAPEAUIBuffer@Streams@Storage@5@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetBufferFromByteArray(uchar *,uint,Windows::Storage::Streams::IBuffer * *)
0x18010b7ab  mov     ebx, eax
0x18010b7ad  test    eax, eax
0x18010b7af  jns     short loc_18010B7D6
0x18010b7b1  mov     rcx, [rbp+68h]; this
0x18010b7b5  mov     r9d, eax; char *
0x18010b7b8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010b7bf  mov     edx, 0B4h; void *
0x18010b7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b7c9  nop
0x18010b7ca  lea     rcx, [rsp+160h+var_F0]
0x18010b7cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010b7d4  jmp     short loc_18010B762
0x18010b7d6  mov     ebx, dword ptr [rbp+60h+SourceSize]
0x18010b7d9  mov     r9d, ebx; SourceSize
0x18010b7dc  mov     rsi, [rbp+60h+var_70]
0x18010b7e0  lea     rcx, [rsi+4]; Destination
0x18010b7e4  mov     r8, [rbp+60h+Source]; Source
0x18010b7e8  call    memcpy_s_3
0x18010b7ed  mov     [rsi], ebx
0x18010b7ef  mov     rax, [rbp+60h+var_D0]
0x18010b7f3  mov     [rbp+60h+var_70], rax
0x18010b7f7  mov     [rbp+60h+var_68], 1
0x18010b7fb  mov     eax, [rbp+60h+var_67]
0x18010b7fe  mov     [rbp+60h+var_67], eax
0x18010b801  movzx   eax, [rbp+60h+var_63]
0x18010b805  mov     [rbp+60h+var_63], ax
0x18010b809  mov     al, [rbp+60h+var_61]
0x18010b80c  mov     [rbp+60h+var_61], al
0x18010b80f  lea     rdx, [rbp+60h+var_70]
0x18010b813  mov     rcx, [rbp+60h+var_C8]
0x18010b817  call    ?IsCacheEntryExpired@@YA_N_JV?$optional@_J@std@@@Z; IsCacheEntryExpired(__int64,std::optional<__int64>)
0x18010b81c  test    al, al
0x18010b81e  jnz     loc_18010BC8C
0x18010b824  mov     rdx, [rbp+60h+var_C8]
0x18010b828  mov     esi, dword ptr [rsp+160h+var_108]
0x18010b82c  mov     ecx, esi
0x18010b82e  call    ?IsInvalidExpirationForUIRequired@@YA_NW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@_J@Z; IsInvalidExpirationForUIRequired(Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,__int64)
0x18010b833  test    al, al
0x18010b835  jnz     loc_18010BC8C
0x18010b83b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x18010b842  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x18010b847  xor     r15d, r15d
0x18010b84a  test    al, al
0x18010b84c  jz      loc_18010B92D
0x18010b852  call    ?IsXboxConsole@@YA_NXZ; IsXboxConsole(void)
0x18010b857  test    al, al
0x18010b859  jz      loc_18010B92D
0x18010b85f  mov     [rbp+60h+SourceSize], r15
0x18010b863  mov     [rbp+60h+var_C8], r15
0x18010b867  mov     [rsp+160h+var_108], r15
0x18010b86c  lea     rcx, [rsp+160h+var_108]
0x18010b871  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010b876  lea     rcx, [rsp+160h+var_108]
0x18010b87b  call    ??$CreateTokenBrokerInternalStaticsT@UITokenBrokerInternalStatics13@Web@Authentication@Security@Internal@Windows@@@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAPEAUITokenBrokerInternalStatics13@Web@1234@@Z; Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBrokerInternalStaticsT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics13>(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics13 * *)
0x18010b880  mov     ebx, eax
0x18010b882  test    eax, eax
0x18010b884  jns     short loc_18010B8AE
0x18010b886  mov     edx, 0E1h; void *
0x18010b88b  mov     rcx, [rbp+68h]; this
0x18010b88f  mov     r9d, ebx; char *
0x18010b892  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010b899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b89e  nop
0x18010b89f  lea     rcx, [rsp+160h+var_108]
0x18010b8a4  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010b8a9  jmp     loc_18010B7CA
0x18010b8ae  mov     rcx, [rsp+160h+var_108]
0x18010b8b3  mov     rax, [rcx]
0x18010b8b6  lea     rdx, [rbp+60h+var_C8]
0x18010b8ba  mov     rax, [rax+30h]
0x18010b8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b8c3  mov     ebx, eax
0x18010b8c5  test    eax, eax
0x18010b8c7  jns     short loc_18010B8D0
0x18010b8c9  mov     edx, 0E4h
0x18010b8ce  jmp     short loc_18010B88B
0x18010b8d0  lea     rdx, aCurrentbootid; "currentBootId"
0x18010b8d7  lea     rcx, [rbp+60h+var_70]; string
0x18010b8db  call    ??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[14])
0x18010b8e0  lea     r8, [rbp+60h+SourceSize]
0x18010b8e4  mov     rdx, [rax]; HSTRING
0x18010b8e7  mov     rcx, [rsp+160h+var_F8]; unsigned __int16 *
0x18010b8ec  call    ??$RetrieveCachedJsonField@_K@@YAJPEBGPEAUHSTRING__@@PEA_K@Z; RetrieveCachedJsonField<unsigned __int64>(ushort const *,HSTRING__ *,unsigned __int64 *)
0x18010b8f1  mov     r15d, eax
0x18010b8f4  cmp     eax, 83750009h
0x18010b8f9  jnz     short loc_18010B95E
0x18010b8fb  mov     eax, cs:dword_180175000
0x18010b901  cmp     eax, 5
0x18010b904  jbe     short loc_18010B920
0x18010b906  xor     r9d, r9d
0x18010b909  xor     r8d, r8d
0x18010b90c  lea     rdx, byte_180157D2D
0x18010b913  lea     rcx, dword_180175000
0x18010b91a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010b91f  nop
0x18010b920  lea     rcx, [rsp+160h+var_108]
0x18010b925  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010b92a  xor     r15d, r15d
0x18010b92d  test    r14, r14
0x18010b930  jz      loc_18010B9EA
0x18010b936  call    ?IsTokenRequestLoggingEnabled@@YA_NXZ; IsTokenRequestLoggingEnabled(void)
0x18010b93b  test    al, al
0x18010b93d  jz      loc_18010B9EA
0x18010b943  mov     r9, r14
0x18010b946  mov     r14, [rbp+60h+var_78]
0x18010b94a  mov     r8, r14
0x18010b94d  mov     rdx, r13
0x18010b950  mov     rcx, [rbp+60h+var_B0]
0x18010b954  call    ?GetCachedTokenRequest@@YAXPEAUHSTRING__@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@7@PEAPEAUIBuffer@Streams@Storage@7@@Z; GetCachedTokenRequest(HSTRING__ *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Storage::Streams::IBuffer * *)
0x18010b959  jmp     loc_18010B9EE
0x18010b95e  test    r15d, r15d
0x18010b961  jns     short loc_18010B97D
0x18010b963  mov     rcx, [rbp+68h]; this
0x18010b967  mov     r9d, r15d; char *
0x18010b96a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010b971  mov     edx, 0F7h; void *
0x18010b976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b97b  jmp     short loc_18010B9DB
0x18010b97d  mov     rax, [rbp+60h+var_C8]
0x18010b981  cmp     [rbp+60h+SourceSize], rax
0x18010b985  jz      short loc_18010B920
0x18010b987  mov     eax, cs:dword_180175000
0x18010b98d  cmp     eax, 5
0x18010b990  jbe     short loc_18010B9AB
0x18010b992  xor     r9d, r9d
0x18010b995  xor     r8d, r8d
0x18010b998  lea     rdx, byte_180157CF5
0x18010b99f  lea     rcx, dword_180175000
0x18010b9a6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010b9ab  xor     r8d, r8d; bool
0x18010b9ae  lea     rdx, [rbp+60h+var_A8]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x18010b9b2  mov     rcx, [rbp+60h+var_B0]; HSTRING
0x18010b9b6  call    ?ClearSpecificCacheEntry@@YAJQEAUHSTRING__@@AEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@_N@Z; ClearSpecificCacheEntry(HSTRING__ * const,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,bool)
0x18010b9bb  mov     ebx, eax
0x18010b9bd  xor     esi, esi
0x18010b9bf  test    eax, eax
0x18010b9c1  jns     short loc_18010B9CD
0x18010b9c3  mov     edx, 102h
0x18010b9c8  jmp     loc_18010B88B
0x18010b9cd  mov     [rdi], esi
0x18010b9cf  mov     [r12], rsi
0x18010b9d3  test    r14, r14
0x18010b9d6  jz      short loc_18010B9DB
0x18010b9d8  mov     [r14], rsi
0x18010b9db  lea     rcx, [rsp+160h+var_108]
0x18010b9e0  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18010b9e5  jmp     loc_18010BCA6
0x18010b9ea  mov     r14, [rbp+60h+var_78]
0x18010b9ee  mov     [rbp+60h+var_D8], r15
  ... truncated ...
```
