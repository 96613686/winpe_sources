# Windows::Security::Authentication::Web::CWebAuthOperation::ConvertWABOperationToWAMRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)

- ea: `0x18001ed50`
- end: `0x18001f1eb`
- name: `?ConvertWABOperationToWAMRequest@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJPEAPEAUIWebTokenRequest@Core@2345@@Z`
- size: `1179`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, Windows::Security::Authentication::Web::Core::IWebTokenRequest **ppWebTokenRequest)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019484`

## callees

- `0x180001150`
- `0x180006060`
- `0x1800060b8`
- `0x1800060d8`
- `0x1800159f4`
- `0x18001b9e8`
- `0x18001be4c`
- `0x18001e824`
- `0x18001ed50`
- `0x18001f8ec`
- `0x18001fe18`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ee29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ef8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ee29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ef8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ee0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ef78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ee0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ef78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ee4a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001efb0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ee4a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001efb0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f122`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001f122`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::ConvertWABOperationToWAMRequest(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        Windows::Security::Authentication::Web::Core::IWebTokenRequest **ppWebTokenRequest)
{
  signed int LastError; // eax
  Windows::Security::Authentication::Web::CWebAuthOperation *v5; // rcx
  const _GUID *v6; // r8
  const _GUID *v7; // r9
  int ActivationFactory; // ebx
  HSTRING__ *hstring; // rbx
  Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *ptr; // rdi
  HRESULT (__fastcall *FindAccountProviderAsync)(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *, HSTRING__ *, Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> **); // rbx
  Microsoft::WRL::Details::Dummy v12; // r8
  __int64 v13; // rax
  Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *v14; // rdi
  HRESULT v15; // edx
  void *v16; // r8
  HSTRING__ *v18; // rbx
  Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory *v19; // rdi
  HRESULT (__fastcall *CreateWithProvider)(Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory *, Windows::Security::Credentials::IWebAccountProvider *, Windows::Security::Authentication::Web::Core::IWebTokenRequest **); // rbx
  Windows::Security::Authentication::Web::Core::IWebTokenRequest *v21; // rdi
  HRESULT (__fastcall *get_Properties)(Windows::Security::Authentication::Web::Core::IWebTokenRequest *, Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> **); // rbx
  Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> *v23; // rsi
  HSTRING__ *v24; // rbx
  HRESULT (__fastcall *Insert)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,HSTRING__ *> *, HSTRING__ *, HSTRING__ *, unsigned __int8 *); // rdi
  Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> *v26; // rsi
  HSTRING__ *v27; // rbx
  HRESULT (__fastcall *v28)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,HSTRING__ *> *, HSTRING__ *, HSTRING__ *, unsigned __int8 *); // rdi
  Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> *v29; // rsi
  HRESULT (__fastcall *v30)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,HSTRING__ *> *, HSTRING__ *, HSTRING__ *, unsigned __int8 *); // rdi
  HSTRING__ *v31; // rbx
  Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> *v32; // rsi
  HRESULT (__fastcall *v33)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,HSTRING__ *> *, HSTRING__ *, HSTRING__ *, unsigned __int8 *); // rdi
  __int64 v34; // rax
  HSTRING__ *v35; // rbx
  Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> *v36; // rsi
  HRESULT (__fastcall *v37)(Windows::Foundation::Collections::IMap_impl<HSTRING__ *,HSTRING__ *> *, HSTRING__ *, HSTRING__ *, unsigned __int8 *); // rdi
  HSTRING__ *Reserved1; // rbx
  unsigned __int8 bUnused[8]; // [rsp+30h] [rbp-69h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> > requestProperties; // [rsp+38h] [rbp-61h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> tokenRequest; // [rsp+40h] [rbp-59h] BYREF
  const wchar_t *providerId; // [rsp+48h] [rbp-51h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> spAccountProvider; // [rsp+50h] [rbp-49h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > stringGuid; // [rsp+58h] [rbp-41h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> > findProviderOperation; // [rsp+60h] [rbp-39h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory> tokenRequestFactory; // [rsp+68h] [rbp-31h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> spWebAuthenticationCoreManagerStatics; // [rsp+70h] [rbp-29h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > webAuthOptionsString; // [rsp+78h] [rbp-21h] BYREF
  Windows::Internal::StringReference string; // [rsp+80h] [rbp-19h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v50; // [rsp+A0h] [rbp+7h] BYREF

  spWebAuthenticationCoreManagerStatics.ptr_ = 0;
  spAccountProvider.ptr_ = 0;
  tokenRequestFactory.ptr_ = 0;
  tokenRequest.ptr_ = 0;
  requestProperties.ptr_ = 0;
  findProviderOperation.ptr_ = 0;
  bUnused[0] = 0;
  webAuthOptionsString.m_ptr = 0;
  stringGuid.m_ptr = 0;
  providerId = GetProviderIdForWebAuthRequest(this, &this->m_MutexHandle.m_ptr, &this->m_MutexRegValue._hstring);
  if ( providerId )
    goto LABEL_31;
  LastError = GetLastError();
  ActivationFactory = LastError;
  if ( LastError > 0 )
    ActivationFactory = (unsigned __int16)LastError | 0x80070000;
  if ( ActivationFactory >= 0 )
  {
LABEL_31:
    if ( WindowsCreateStringReference(
           RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager,
           0x45u,
           &string._header,
           &string._hstring) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    hstring = string._hstring;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spWebAuthenticationCoreManagerStatics);
    ActivationFactory = RoGetActivationFactory(
                          hstring,
                          &GUID_6aca7c92_a581_4479_9c10_752eff44fd34,
                          &spWebAuthenticationCoreManagerStatics);
    if ( ActivationFactory >= 0 )
    {
      ptr = spWebAuthenticationCoreManagerStatics.ptr_;
      FindAccountProviderAsync = spWebAuthenticationCoreManagerStatics.ptr_->FindAccountProviderAsync;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&findProviderOperation);
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v50, &providerId, v12);
      ActivationFactory = FindAccountProviderAsync(ptr, *(HSTRING__ **)(v13 + 24), &findProviderOperation.ptr_);
      if ( ActivationFactory >= 0 )
      {
        v14 = findProviderOperation.ptr_;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAccountProvider);
        ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
                              v14,
                              v15,
                              v16);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = v14->GetResults(v14, &spAccountProvider.ptr_);
          if ( ActivationFactory >= 0 )
          {
            if ( spAccountProvider.ptr_ )
            {
              if ( WindowsCreateStringReference(
                     RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest,
                     0x38u,
                     &string._header,
                     &string._hstring) < 0 )
                RaiseException(0xC000000D, 1u, 0, 0);
              v18 = string._hstring;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequestFactory);
              ActivationFactory = RoGetActivationFactory(
                                    v18,
                                    &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9,
                                    &tokenRequestFactory);
              if ( ActivationFactory >= 0 )
              {
                v19 = tokenRequestFactory.ptr_;
                CreateWithProvider = tokenRequestFactory.ptr_->CreateWithProvider;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequest);
                ActivationFactory = CreateWithProvider(v19, spAccountProvider.ptr_, &tokenRequest.ptr_);
                if ( ActivationFactory >= 0 )
                {
                  v21 = tokenRequest.ptr_;
                  get_Properties = tokenRequest.ptr_->get_Properties;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestProperties);
                  ActivationFactory = get_Properties(v21, &requestProperties.ptr_);
                  if ( ActivationFactory >= 0 )
                  {
                    v23 = requestProperties.ptr_;
                    v24 = this->m_TargetUri._hstring;
                    Insert = requestProperties.ptr_->Insert;
                    Windows::Internal::StringReference::_ConstructorHelper(
                      &string,
                      g_WAB2WAMBridgeStartURLPropertyName_0);
                    ActivationFactory = Insert(v23, string._hstring, v24, bUnused);
                    if ( ActivationFactory >= 0 )
                    {
                      v26 = requestProperties.ptr_;
                      v27 = this->m_EndUri._hstring;
                      v28 = requestProperties.ptr_->Insert;
                      Windows::Internal::StringReference::_ConstructorHelper(
                        &string,
                        g_WAB2WAMBridgeEndURLPropertyName_0);
                      ActivationFactory = v28(v26, string._hstring, v27, bUnused);
                      if ( ActivationFactory >= 0 )
                      {
                        ActivationFactory = Windows::Security::Authentication::Web::CWebAuthOperation::StringFromWebAuthOptions(
                                              v5,
                                              this->m_WebAuthOptions,
                                              &webAuthOptionsString.m_ptr);
                        if ( ActivationFactory >= 0 )
                        {
                          v29 = requestProperties.ptr_;
                          v30 = requestProperties.ptr_->Insert;
                          Windows::Internal::StringReference::_ConstructorHelper(&string, webAuthOptionsString.m_ptr);
                          v31 = string._hstring;
                          Windows::Internal::StringReference::_ConstructorHelper(
                            (Windows::Internal::StringReference *)&v50,
                            g_WAB2WAMBridgeOptionsPropertyName_0);
                          ActivationFactory = v30(v29, (HSTRING__ *)v50.header_.Reserved.Reserved1, v31, bUnused);
                          if ( ActivationFactory >= 0 )
                          {
                            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                              &stringGuid,
                              0);
                            ActivationFactory = StringFromCLSID(
                                                  &this->m_WamBridgeBrokerActivity.m_pActivityData->m_Id,
                                                  &stringGuid.m_ptr);
                            if ( ActivationFactory >= 0 )
                            {
                              v32 = requestProperties.ptr_;
                              v33 = requestProperties.ptr_->Insert;
                              providerId = stringGuid.m_ptr;
                              Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                (Microsoft::WRL::Wrappers::HStringReference *)&string,
                                &providerId,
                                (Microsoft::WRL::Details::Dummy)v6);
                              v35 = *(HSTRING__ **)(v34 + 24);
                              Windows::Internal::StringReference::_ConstructorHelper(
                                (Windows::Internal::StringReference *)&v50,
                                g_WAB2WAMBridgeTelemetryIdPropertyName_0);
                              ActivationFactory = v33(v32, (HSTRING__ *)v50.header_.Reserved.Reserved1, v35, bUnused);
                              if ( ActivationFactory >= 0 )
                              {
                                v36 = requestProperties.ptr_;
                                v37 = requestProperties.ptr_->Insert;
                                Windows::Internal::StringReference::_ConstructorHelper(
                                  (Windows::Internal::StringReference *)&v50,
                                  s_WAB2WAMBridgeWindowsAppGroup);
                                Reserved1 = (HSTRING__ *)v50.header_.Reserved.Reserved1;
                                Windows::Internal::StringReference::_ConstructorHelper(
                                  &string,
                                  g_WAB2WAMBridgeSSOAppGroupPropertyName);
                                ActivationFactory = v37(v36, string._hstring, Reserved1, bUnused);
                                if ( ActivationFactory >= 0 )
                                {
                                  ActivationFactory = 0;
                                  *ppWebTokenRequest = tokenRequest.ptr_;
                                  tokenRequest.ptr_ = 0;
                                  goto LABEL_15;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              ActivationFactory = -2144927148;
            }
          }
        }
      }
    }
  }
  if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 2 )
  {
    LODWORD(providerId) = ActivationFactory;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (const _tlgProvider_t *)v5,
      &tlgEvent_11._tlgChannel,
      v6,
      v7,
      (const _tlgWrapperByVal<4> *)&providerId);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&stringGuid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&webAuthOptionsString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&findProviderOperation);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestProperties);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequest);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequestFactory);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAccountProvider);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spWebAuthenticationCoreManagerStatics);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001ed50  mov     [rsp-8+arg_10], rbx
0x18001ed55  push    rbp
0x18001ed56  push    rsi
0x18001ed57  push    rdi
0x18001ed58  push    r14
0x18001ed5a  push    r15
0x18001ed5c  lea     rbp, [rsp-37h]
0x18001ed61  sub     rsp, 0D0h
0x18001ed68  mov     rax, cs:__security_cookie
0x18001ed6f  xor     rax, rsp
0x18001ed72  mov     [rbp+57h+var_30], rax
0x18001ed76  mov     r15, ppWebTokenRequest
0x18001ed79  mov     [rbp+57h+spWebAuthenticationCoreManagerStatics.ptr_], 0
0x18001ed81  lea     ppWebTokenRequest, [this+108h]; handle
0x18001ed88  mov     [rbp+57h+spAccountProvider.ptr_], 0
0x18001ed90  lea     r8, [this+110h]; regValue
0x18001ed97  mov     [rbp+57h+tokenRequestFactory.ptr_], 0
0x18001ed9f  mov     r14, this
0x18001eda2  mov     [rbp+57h+tokenRequest.ptr_], 0
0x18001edaa  mov     [rbp+57h+requestProperties.ptr_], 0
0x18001edb2  mov     [rbp+57h+findProviderOperation.ptr_], 0
0x18001edba  mov     [rbp+57h+bUnused], 0
0x18001edbe  mov     [rbp+57h+webAuthOptionsString.m_ptr], 0
0x18001edc6  mov     [rbp+57h+stringGuid.m_ptr], 0
0x18001edce  call    _GetProviderIdForWebAuthRequest
0x18001edd3  mov     [rbp+57h+providerId], rax
0x18001edd7  test    rax, rax
0x18001edda  jnz     short loc_18001EDF9
0x18001eddc  call    cs:__imp_GetLastError
0x18001ede2  mov     ebx, eax
0x18001ede4  test    eax, eax
0x18001ede6  jle     short loc_18001EDF1
0x18001ede8  movzx   ebx, ax
0x18001edeb  or      ebx, 80070000h
0x18001edf1  test    ebx, ebx
0x18001edf3  js      loc_18001EED4
0x18001edf9  lea     r9, [rbp+57h+string]; string
0x18001edfd  mov     edx, 45h ; 'E'; length
0x18001ee02  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001ee06  lea     this, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; sourceString
0x18001ee0d  call    cs:__imp_WindowsCreateStringReference
0x18001ee13  mov     esi, 1
0x18001ee18  test    eax, eax
0x18001ee1a  jns     short loc_18001EE2F
0x18001ee1c  xor     r9d, r9d; lpArguments
0x18001ee1f  xor     r8d, r8d; nNumberOfArguments
0x18001ee22  mov     edx, esi; dwExceptionFlags
0x18001ee24  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001ee29  call    cs:__imp_RaiseException
0x18001ee2f  mov     rbx, [rbp+57h+string]
0x18001ee33  lea     this, [rbp+57h+spWebAuthenticationCoreManagerStatics]; this
0x18001ee37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee3c  lea     r8, [rbp+57h+spWebAuthenticationCoreManagerStatics]
0x18001ee40  mov     this, rbx
0x18001ee43  lea     ppWebTokenRequest, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18001ee4a  call    cs:__imp_RoGetActivationFactory
0x18001ee50  mov     ebx, eax
0x18001ee52  test    eax, eax
0x18001ee54  js      short loc_18001EED4
0x18001ee56  mov     rdi, [rbp+57h+spWebAuthenticationCoreManagerStatics.ptr_]
0x18001ee5a  lea     this, [rbp+57h+findProviderOperation]; this
0x18001ee5e  mov     rax, [rdi]
0x18001ee61  mov     rbx, [rax+58h]
0x18001ee65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee6a  lea     ppWebTokenRequest, [rbp+57h+providerId]; strRef
0x18001ee6e  lea     this, [rbp+57h+var_50]; this
0x18001ee72  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ee77  lea     r8, [rbp+57h+findProviderOperation]
0x18001ee7b  mov     this, rdi
0x18001ee7e  mov     ppWebTokenRequest, [rax+18h]
0x18001ee82  mov     rax, rbx
0x18001ee85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee8a  mov     ebx, eax
0x18001ee8c  test    eax, eax
0x18001ee8e  js      short loc_18001EED4
0x18001ee90  mov     rdi, [rbp+57h+findProviderOperation.ptr_]
0x18001ee94  lea     this, [rbp+57h+spAccountProvider]; this
0x18001ee98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee9d  mov     this, rdi; pOperation
0x18001eea0  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x18001eea5  mov     ebx, eax
0x18001eea7  test    eax, eax
0x18001eea9  js      short loc_18001EED4
0x18001eeab  mov     rax, [rdi]
0x18001eeae  lea     ppWebTokenRequest, [rbp+57h+spAccountProvider]
0x18001eeb2  mov     this, rdi
0x18001eeb5  mov     rax, [rax+40h]
0x18001eeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebe  mov     ebx, eax
0x18001eec0  test    eax, eax
0x18001eec2  js      short loc_18001EED4
0x18001eec4  cmp     [rbp+57h+spAccountProvider.ptr_], 0
0x18001eec9  jnz     loc_18001EF64
0x18001eecf  mov     ebx, 80270254h
0x18001eed4  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x18001eeda  cmp     eax, 2
0x18001eedd  jbe     short loc_18001EEF7
0x18001eedf  lea     rax, [rbp+57h+providerId]; __annotation("_TlgWrite:|397|g_hMyWABTraceLoggingProvider|"WAM Request creation failed."=|"hr"=")
0x18001eee3  mov     dword ptr [rbp+57h+providerId], ebx
0x18001eee6  lea     ppWebTokenRequest, _tlgEvent_11._tlgChannel; <wrappedArgs_0>
0x18001eeed  mov     [rsp+0F0h+var_D0], rax; <writerArgs_0>
0x18001eef2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001eef7  lea     this, [rbp+57h+stringGuid]; this
0x18001eefb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ef00  lea     this, [rbp+57h+webAuthOptionsString]; this
0x18001ef04  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ef09  lea     this, [rbp+57h+findProviderOperation]; this
0x18001ef0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef12  lea     this, [rbp+57h+requestProperties]; this
0x18001ef16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef1b  lea     this, [rbp+57h+tokenRequest]; this
0x18001ef1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef24  lea     this, [rbp+57h+tokenRequestFactory]; this
0x18001ef28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef2d  lea     this, [rbp+57h+spAccountProvider]; this
0x18001ef31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef36  lea     this, [rbp+57h+spWebAuthenticationCoreManagerStatics]; this
0x18001ef3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef3f  mov     eax, ebx
0x18001ef41  mov     this, [rbp+57h+var_30]
0x18001ef45  xor     this, rsp; StackCookie
0x18001ef48  call    __security_check_cookie
0x18001ef4d  mov     rbx, [rsp+0F0h+arg_10]
0x18001ef55  add     rsp, 0D0h
0x18001ef5c  pop     r15
0x18001ef5e  pop     r14
0x18001ef60  pop     rdi
0x18001ef61  pop     rsi
0x18001ef62  pop     rbp
0x18001ef63  retn
0x18001ef64  lea     r9, [rbp+57h+string]; string
0x18001ef68  mov     edx, 38h ; '8'; length
0x18001ef6d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001ef71  lea     this, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; sourceString
0x18001ef78  call    cs:__imp_WindowsCreateStringReference
0x18001ef7e  test    eax, eax
0x18001ef80  jns     short loc_18001EF95
0x18001ef82  xor     r9d, r9d; lpArguments
0x18001ef85  xor     r8d, r8d; nNumberOfArguments
0x18001ef88  mov     edx, esi; dwExceptionFlags
0x18001ef8a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001ef8f  call    cs:__imp_RaiseException
0x18001ef95  mov     rbx, [rbp+57h+string]
0x18001ef99  lea     this, [rbp+57h+tokenRequestFactory]; this
0x18001ef9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001efa2  lea     r8, [rbp+57h+tokenRequestFactory]
0x18001efa6  mov     this, rbx
0x18001efa9  lea     ppWebTokenRequest, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x18001efb0  call    cs:__imp_RoGetActivationFactory
0x18001efb6  mov     ebx, eax
0x18001efb8  test    eax, eax
0x18001efba  js      loc_18001EED4
0x18001efc0  mov     rdi, [rbp+57h+tokenRequestFactory.ptr_]
0x18001efc4  lea     this, [rbp+57h+tokenRequest]; this
0x18001efc8  mov     rax, [rdi]
0x18001efcb  mov     rbx, [rax+40h]
0x18001efcf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001efd4  mov     ppWebTokenRequest, [rbp+57h+spAccountProvider.ptr_]
0x18001efd8  lea     r8, [rbp+57h+tokenRequest]
0x18001efdc  mov     this, rdi
0x18001efdf  mov     rax, rbx
0x18001efe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe7  mov     ebx, eax
0x18001efe9  test    eax, eax
0x18001efeb  js      loc_18001EED4
0x18001eff1  mov     rdi, [rbp+57h+tokenRequest.ptr_]
0x18001eff5  lea     this, [rbp+57h+requestProperties]; this
0x18001eff9  mov     rax, [rdi]
0x18001effc  mov     rbx, [rax+50h]
0x18001f000  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f005  lea     ppWebTokenRequest, [rbp+57h+requestProperties]
0x18001f009  mov     this, rdi
0x18001f00c  mov     rax, rbx
0x18001f00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f014  mov     ebx, eax
0x18001f016  test    eax, eax
0x18001f018  js      loc_18001EED4
0x18001f01e  mov     rsi, [rbp+57h+requestProperties.ptr_]
0x18001f022  lea     this, [rbp+57h+string]; this
0x18001f026  mov     ppWebTokenRequest, cs:g_WAB2WAMBridgeStartURLPropertyName_0; stringRef
0x18001f02d  mov     rbx, [r14+0C8h]
0x18001f034  mov     rax, [rsi]
0x18001f037  mov     rdi, [rax+50h]
0x18001f03b  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f040  mov     ppWebTokenRequest, [rbp+57h+string]
0x18001f044  lea     r9, [rbp+57h+bUnused]
0x18001f048  mov     r8, rbx
0x18001f04b  mov     this, rsi
0x18001f04e  mov     rax, rdi
0x18001f051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f056  mov     ebx, eax
0x18001f058  test    eax, eax
0x18001f05a  js      loc_18001EED4
0x18001f060  mov     rsi, [rbp+57h+requestProperties.ptr_]
0x18001f064  lea     this, [rbp+57h+string]; this
0x18001f068  mov     ppWebTokenRequest, cs:g_WAB2WAMBridgeEndURLPropertyName_0; stringRef
0x18001f06f  mov     rbx, [r14+0D0h]
0x18001f076  mov     rax, [rsi]
0x18001f079  mov     rdi, [rax+50h]
0x18001f07d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f082  mov     ppWebTokenRequest, [rbp+57h+string]
0x18001f086  lea     r9, [rbp+57h+bUnused]
0x18001f08a  mov     r8, rbx
0x18001f08d  mov     this, rsi
0x18001f090  mov     rax, rdi
0x18001f093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f098  mov     ebx, eax
0x18001f09a  test    eax, eax
0x18001f09c  js      loc_18001EED4
0x18001f0a2  mov     edx, [r14+104h]; options
0x18001f0a9  lea     r8, [rbp+57h+webAuthOptionsString]; result
0x18001f0ad  call    ?StringFromWebAuthOptions@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJW4WebAuthenticationOptions@2345@PEAPEAG@Z; Windows::Security::Authentication::Web::CWebAuthOperation::StringFromWebAuthOptions(Windows::Security::Authentication::Web::WebAuthenticationOptions,ushort * *)
0x18001f0b2  mov     ebx, eax
0x18001f0b4  test    eax, eax
0x18001f0b6  js      loc_18001EED4
0x18001f0bc  mov     rsi, [rbp+57h+requestProperties.ptr_]
0x18001f0c0  lea     this, [rbp+57h+string]; this
0x18001f0c4  mov     ppWebTokenRequest, [rbp+57h+webAuthOptionsString.m_ptr]; stringRef
0x18001f0c8  mov     rax, [rsi]
0x18001f0cb  mov     rdi, [rax+50h]
0x18001f0cf  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f0d4  mov     ppWebTokenRequest, cs:g_WAB2WAMBridgeOptionsPropertyName_0; stringRef
0x18001f0db  lea     this, [rbp+57h+var_50]; this
0x18001f0df  mov     rbx, [rbp+57h+string]
0x18001f0e3  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f0e8  mov     ppWebTokenRequest, qword ptr [rbp+57h+var_50.header_.Reserved]
0x18001f0ec  lea     r9, [rbp+57h+bUnused]
0x18001f0f0  mov     r8, rbx
0x18001f0f3  mov     this, rsi
0x18001f0f6  mov     rax, rdi
0x18001f0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0fe  mov     ebx, eax
0x18001f100  test    eax, eax
0x18001f102  js      loc_18001EED4
0x18001f108  xor     edx, edx; ptr
0x18001f10a  lea     this, [rbp+57h+stringGuid]; this
0x18001f10e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f113  mov     this, [r14+228h]
0x18001f11a  lea     ppWebTokenRequest, [rbp+57h+stringGuid]; lplpsz
0x18001f11e  add     this, 8; rclsid
0x18001f122  call    cs:__imp_StringFromCLSID
0x18001f128  mov     ebx, eax
0x18001f12a  test    eax, eax
0x18001f12c  js      loc_18001EED4
0x18001f132  mov     rsi, [rbp+57h+requestProperties.ptr_]
0x18001f136  lea     ppWebTokenRequest, [rbp+57h+providerId]; strRef
0x18001f13a  lea     this, [rbp+57h+string]; this
0x18001f13e  mov     rax, [rsi]
0x18001f141  mov     rdi, [rax+50h]
0x18001f145  mov     rax, [rbp+57h+stringGuid.m_ptr]
0x18001f149  mov     [rbp+57h+providerId], rax
0x18001f14d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f152  mov     ppWebTokenRequest, cs:g_WAB2WAMBridgeTelemetryIdPropertyName_0; stringRef
0x18001f159  lea     this, [rbp+57h+var_50]; this
0x18001f15d  mov     rbx, [rax+18h]
0x18001f161  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f166  mov     ppWebTokenRequest, qword ptr [rbp+57h+var_50.header_.Reserved]
0x18001f16a  lea     r9, [rbp+57h+bUnused]
0x18001f16e  mov     r8, rbx
0x18001f171  mov     this, rsi
0x18001f174  mov     rax, rdi
0x18001f177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f17c  mov     ebx, eax
0x18001f17e  test    eax, eax
0x18001f180  js      loc_18001EED4
0x18001f186  mov     rsi, [rbp+57h+requestProperties.ptr_]
0x18001f18a  lea     this, [rbp+57h+var_50]; this
0x18001f18e  mov     ppWebTokenRequest, cs:s_WAB2WAMBridgeWindowsAppGroup; stringRef
0x18001f195  mov     rax, [rsi]
0x18001f198  mov     rdi, [rax+50h]
0x18001f19c  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f1a1  mov     ppWebTokenRequest, cs:g_WAB2WAMBridgeSSOAppGroupPropertyName; stringRef
0x18001f1a8  lea     this, [rbp+57h+string]; this
0x18001f1ac  mov     rbx, qword ptr [rbp+57h+var_50.header_.Reserved]
0x18001f1b0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f1b5  mov     ppWebTokenRequest, [rbp+57h+string]
0x18001f1b9  lea     r9, [rbp+57h+bUnused]
0x18001f1bd  mov     r8, rbx
0x18001f1c0  mov     this, rsi
0x18001f1c3  mov     rax, rdi
0x18001f1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1cb  mov     ebx, eax
0x18001f1cd  test    eax, eax
0x18001f1cf  js      loc_18001EED4
0x18001f1d5  mov     rax, [rbp+57h+tokenRequest.ptr_]
0x18001f1d9  xor     ebx, ebx
0x18001f1db  mov     [r15], rax
0x18001f1de  mov     [rbp+57h+tokenRequest.ptr_], 0
0x18001f1e6  jmp     loc_18001EEF7
```
