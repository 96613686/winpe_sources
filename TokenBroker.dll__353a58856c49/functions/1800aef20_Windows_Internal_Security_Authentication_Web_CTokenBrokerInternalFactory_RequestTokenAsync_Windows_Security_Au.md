# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::RequestTokenAsync(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,uint,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> * *)

- ea: `0x1800aef20`
- end: `0x1800af929`
- name: `?RequestTokenAsync@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebTokenRequest@Core@2346@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@IPEAPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@6@@Z`
- size: `2569`
- prototype: `__int64 __fastcall(__int64, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001e00c`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x180023a80`
- `0x180024118`
- `0x18002ea84`
- `0x18002fbf0`
- `0x180031270`
- `0x1800439d0`
- `0x18004a4fc`
- `0x18004a75c`
- `0x18004dd84`
- `0x1800512b0`
- `0x180052120`
- `0x180053cfc`
- `0x180063ff0`
- `0x1800682e4`
- `0x18007f6e0`
- `0x180080228`
- `0x180089458`
- `0x18008e690`
- `0x1800a43bc`
- `0x1800aef20`
- `0x1800b048c`
- `0x1800b33f0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af839`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af839`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800af8b0`

## string_xrefs

- `0x1800aefcb`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af011`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af079`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af0da`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af14d`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af1b9`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af233`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af2b0`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af378`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af40c`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af4b4`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af55d`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af5e1`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af665`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af724`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af80f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800af484`: `delegatedTokenRequests`
- `0x1800aefa1`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::RequestTokenAsync`
- `0x1800aef63`: `TokenBrokerInternalRequestTokenAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::RequestTokenAsync(
        __int64 a1,
        struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  struct IUnknown *v8; // rsi
  __int64 v9; // rcx
  __int64 (__fastcall *v11)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  HSTRING v18; // rdi
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // edx
  __int64 (__fastcall *v24)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, GUID *, HSTRING *); // rbx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  HSTRING *v29; // rax
  int v30; // eax
  unsigned int v31; // ebx
  int BuiltInProviderType; // ebx
  int PluginPFN; // eax
  unsigned int v34; // ebx
  Windows::Internal::Security::Authentication::TokenBroker *CallingAppName; // rax
  HSTRING v36; // rbx
  int TokenBindingContext; // eax
  unsigned int v38; // esi
  unsigned __int64 v39; // rdx
  int v40; // eax
  unsigned int v41; // edi
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned __int64 *v44; // [rsp+20h] [rbp-258h]
  int v45; // [rsp+20h] [rbp-258h]
  struct Windows::Security::Credentials::IWebAccountProvider *v46; // [rsp+30h] [rbp-248h] BYREF
  __int64 v47; // [rsp+38h] [rbp-240h] BYREF
  HSTRING v48; // [rsp+40h] [rbp-238h] BYREF
  HSTRING string; // [rsp+48h] [rbp-230h] BYREF
  _BYTE v50[16]; // [rsp+50h] [rbp-228h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v51; // [rsp+60h] [rbp-218h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-210h] BYREF
  char v53; // [rsp+70h] [rbp-208h]
  unsigned __int64 v54; // [rsp+78h] [rbp-200h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker **v55; // [rsp+80h] [rbp-1F8h] BYREF
  char v56; // [rsp+88h] [rbp-1F0h]
  _QWORD v57[4]; // [rsp+90h] [rbp-1E8h] BYREF
  int v58; // [rsp+B0h] [rbp-1C8h]
  int v59; // [rsp+B4h] [rbp-1C4h]
  _QWORD v60[42]; // [rsp+C0h] [rbp-1B8h] BYREF
  HSTRING v61; // [rsp+210h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v8 = (struct IUnknown *)(a1 & -(__int64)(a1 != 40));
  wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v60);
  v60[0] = &TbLogProvider::TokenBrokerInternalRequestTokenAsync::`vftable';
  TbLogProvider::TokenBrokerInternalRequestTokenAsync::StartActivity(
    (TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60,
    v8,
    a2);
  LOBYTE(v44) = 0;
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    v50,
    v8,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::RequestTokenAsync");
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x794,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070057LL,
      (int)v44);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x795,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070057LL,
      (int)v44);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return 2147942487LL;
  }
  v46 = 0;
  v11 = *(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v12 = v11(a2, &v46);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v12,
      (int)v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return v13;
  }
  v47 = 0;
  v14 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(
          &v46,
          &v47);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v14,
      (int)v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return v15;
  }
  v54 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v47 + 48LL))(v47, &v54);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v16,
      (int)v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return v17;
  }
  wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(&v48);
  v18 = v48;
  if ( !v48 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x8007000ELL,
      (int)v44);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v48,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return 2147942414LL;
  }
  v19 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
          (Windows::Internal::Security::Authentication::Web::CallerContext *)v48,
          v8,
          v54,
          1);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v19,
      (int)v44);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v48,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return v20;
  }
  TokenHandle = 0;
  v53 = 0;
  v21 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v18 + 2));
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v21,
      (int)v44);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v48,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return v22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl)
    && Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v18) )
  {
    v55 = 0;
    string = 0;
    v24 = **(__int64 (__fastcall ***)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, GUID *, HSTRING *))a2;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
    v25 = v24(a2, &GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78, &string);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B1,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v25,
        (int)v44);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v48,
        0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
      TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
      return v26;
    }
    v27 = (*(__int64 (__fastcall **)(HSTRING, Windows::Internal::Security::Authentication::TokenBroker ***))(*(_QWORD *)string + 48LL))(
            string,
            &v55);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B3,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v27,
        (int)v44);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v48,
        0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
      TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
      return v28;
    }
    if ( v55 )
    {
      v29 = (HSTRING *)Windows::Internal::StringReference::StringReference(&v61, L"delegatedTokenRequests");
      v30 = Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(
              (Windows::Internal::Security::Authentication::Web::CallerContext *)v18,
              *v29);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B7,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v30,
          (int)v44);
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          &v48,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
        TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
        return v31;
      }
    }
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVWebAccount_Credentials_Security_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&string);
  }
  Windows::Internal::Security::Authentication::Web::PrimeTokenBrokerOnFirstInvocation(
    (Windows::Internal::Security::Authentication::Web *)*((unsigned int *)v18 + 6),
    v23);
  BuiltInProviderType = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(v46);
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v18)
    && BuiltInProviderType == 4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070005LL,
      (int)v44);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v48,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return 2147942405LL;
  }
  else if ( BuiltInProviderType == 2 && (unsigned int)EnforceEdpForAad(*((void **)v18 + 39)) == -2147024540 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070164LL,
      (int)v44);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v48,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
    TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
    return 2147942756LL;
  }
  else
  {
    string = 0;
    PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v46, &string);
    v34 = PluginPFN;
    if ( PluginPFN >= 0 )
    {
      v51 = 0;
      v55 = &v51;
      v56 = 1;
      CallingAppName = (Windows::Internal::Security::Authentication::TokenBroker *)Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppName((Windows::Internal::Security::Authentication::Web::CallerContext *)v18);
      v36 = string;
      TokenBindingContext = Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBindingContext(
                              CallingAppName,
                              string,
                              v18,
                              (struct Windows::Internal::Security::Authentication::Web::CallerContext *)&v51,
                              v44);
      v38 = TokenBindingContext;
      if ( TokenBindingContext >= 0 )
      {
        v59 = 0;
        v57[0] = a2;
        v57[1] = a3;
        v57[3] = v51;
        v48 = 0;
        v57[2] = v18;
        v58 = a4;
        v51 = 0;
        v40 = Windows::Internal::Security::Authentication::Web::MakeAsyncWamOperation<Windows::Internal::Security::Authentication::Web::CTokenBrokerOperation,TbLogProvider::TokenBrokerInternalRequestTokenAsync,Windows::Internal::Security::Authentication::Web::RequestTokenOperationParams,Windows::Security::Authentication::Web::Core::WebTokenRequestResult,>(
                v60,
                v57,
                a5);
        v41 = v40;
        if ( v40 >= 0 )
        {
          wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v60);
          if ( v51 )
            Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v51, v43);
          if ( v36 )
            WindowsDeleteString(v36);
          Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            &v48,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
          TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7E7,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)(unsigned int)v40,
            v45);
          if ( v51 )
            Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v51, v42);
          if ( v36 )
            WindowsDeleteString(v36);
          Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            &v48,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
          TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
          return v41;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DC,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)TokenBindingContext,
          v45);
        if ( v51 )
          Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v51, v39);
        if ( v36 )
          WindowsDeleteString(v36);
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          &v48,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
        TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
        return v38;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7CF,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)PluginPFN,
        (int)v44);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v48,
        0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v50);
      TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync((TbLogProvider::TokenBrokerInternalRequestTokenAsync *)v60);
      return v34;
    }
  }
}

```

## disassembly

```asm
0x1800aef20  push    rbx
0x1800aef22  push    rsi
0x1800aef23  push    rdi
0x1800aef24  push    r12
0x1800aef26  push    r13
0x1800aef28  push    r14
0x1800aef2a  push    r15
0x1800aef2c  sub     rsp, 240h
0x1800aef33  mov     rax, cs:__security_cookie
0x1800aef3a  xor     rax, rsp
0x1800aef3d  mov     [rsp+278h+var_48], rax
0x1800aef45  mov     r13d, r9d
0x1800aef48  mov     r12, r8
0x1800aef4b  mov     r14, rdx
0x1800aef4e  mov     r15, [rsp+278h+arg_20]
0x1800aef56  lea     rax, [rcx-28h]
0x1800aef5a  neg     rax
0x1800aef5d  sbb     rsi, rsi
0x1800aef60  and     rsi, rcx
0x1800aef63  lea     rdx, aTokenbrokerint_32; "TokenBrokerInternalRequestTokenAsync"
0x1800aef6a  lea     rcx, [rsp+278h+var_1B8]; struct wil::details::IFailureCallback *
0x1800aef72  call    ??0?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800aef77  lea     rax, ??_7TokenBrokerInternalRequestTokenAsync@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalRequestTokenAsync::`vftable'
0x1800aef7e  mov     [rsp+278h+var_1B8], rax
0x1800aef86  mov     r8, r14; struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *
0x1800aef89  mov     rdx, rsi; struct IUnknown *
0x1800aef8c  lea     rcx, [rsp+278h+var_1B8]; this
0x1800aef94  call    ?StartActivity@TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z; TbLogProvider::TokenBrokerInternalRequestTokenAsync::StartActivity(IUnknown *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *)
0x1800aef99  nop
0x1800aef9a  xor     edi, edi
0x1800aef9c  mov     byte ptr [rsp+278h+var_258], dil; int
0x1800aefa1  lea     r9, aWindowsInterna_12; "Windows::Internal::Security::Authentica"...
0x1800aefa8  mov     r8, rsi
0x1800aefab  lea     rdx, [rsp+278h+var_228]
0x1800aefb0  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800aefb5  nop
0x1800aefb6  test    r15, r15
0x1800aefb9  jnz     short loc_1800AEFFC
0x1800aefbb  mov     rcx, [rsp+278h]; this
0x1800aefc3  mov     ebx, 80070057h
0x1800aefc8  mov     r9d, ebx; char *
0x1800aefcb  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800aefd2  mov     edx, 794h; void *
0x1800aefd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aefdc  nop
0x1800aefdd  lea     rcx, [rsp+278h+var_228]; this
0x1800aefe2  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800aefe7  nop
0x1800aefe8  lea     rcx, [rsp+278h+var_1B8]; this
0x1800aeff0  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800aeff5  mov     eax, ebx
0x1800aeff7  jmp     loc_1800AF905
0x1800aeffc  test    r14, r14
0x1800aefff  jnz     short loc_1800AF042
0x1800af001  mov     rcx, [rsp+278h]; this
0x1800af009  mov     ebx, 80070057h
0x1800af00e  mov     r9d, ebx; char *
0x1800af011  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af018  mov     edx, 795h; void *
0x1800af01d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af022  nop
0x1800af023  lea     rcx, [rsp+278h+var_228]; this
0x1800af028  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af02d  nop
0x1800af02e  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af036  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af03b  mov     eax, ebx
0x1800af03d  jmp     loc_1800AF905
0x1800af042  mov     [rsp+278h+var_248], rdi
0x1800af047  mov     rax, [r14]
0x1800af04a  mov     rbx, [rax+30h]
0x1800af04e  lea     rcx, [rsp+278h+var_248]
0x1800af053  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af058  lea     rdx, [rsp+278h+var_248]
0x1800af05d  mov     rcx, r14
0x1800af060  mov     rax, rbx
0x1800af063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af068  mov     ebx, eax
0x1800af06a  test    eax, eax
0x1800af06c  jns     short loc_1800AF0B5
0x1800af06e  mov     rcx, [rsp+278h]; this
0x1800af076  mov     r9d, eax; char *
0x1800af079  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af080  mov     edx, 799h; void *
0x1800af085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af08a  nop
0x1800af08b  lea     rcx, [rsp+278h+var_248]
0x1800af090  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af095  nop
0x1800af096  lea     rcx, [rsp+278h+var_228]; this
0x1800af09b  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af0a0  nop
0x1800af0a1  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af0a9  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af0ae  mov     eax, ebx
0x1800af0b0  jmp     loc_1800AF905
0x1800af0b5  mov     [rsp+278h+var_240], rdi
0x1800af0ba  lea     rdx, [rsp+278h+var_240]
0x1800af0bf  lea     rcx, [rsp+278h+var_248]
0x1800af0c4  call    ??$As@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>>)
0x1800af0c9  mov     ebx, eax
0x1800af0cb  test    eax, eax
0x1800af0cd  jns     short loc_1800AF121
0x1800af0cf  mov     rcx, [rsp+278h]; this
0x1800af0d7  mov     r9d, eax; char *
0x1800af0da  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af0e1  mov     edx, 79Ch; void *
0x1800af0e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af0eb  nop
0x1800af0ec  lea     rcx, [rsp+278h+var_240]
0x1800af0f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af0f6  nop
0x1800af0f7  lea     rcx, [rsp+278h+var_248]
0x1800af0fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af101  nop
0x1800af102  lea     rcx, [rsp+278h+var_228]; this
0x1800af107  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af10c  nop
0x1800af10d  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af115  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af11a  mov     eax, ebx
0x1800af11c  jmp     loc_1800AF905
0x1800af121  mov     [rsp+278h+var_200], rdi
0x1800af126  mov     rcx, [rsp+278h+var_240]
0x1800af12b  mov     rax, [rcx]
0x1800af12e  lea     rdx, [rsp+278h+var_200]
0x1800af133  mov     rax, [rax+30h]
0x1800af137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af13c  mov     ebx, eax
0x1800af13e  test    eax, eax
0x1800af140  jns     short loc_1800AF194
0x1800af142  mov     rcx, [rsp+278h]; this
0x1800af14a  mov     r9d, eax; char *
0x1800af14d  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af154  mov     edx, 79Fh; void *
0x1800af159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af15e  nop
0x1800af15f  lea     rcx, [rsp+278h+var_240]
0x1800af164  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af169  nop
0x1800af16a  lea     rcx, [rsp+278h+var_248]
0x1800af16f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af174  nop
0x1800af175  lea     rcx, [rsp+278h+var_228]; this
0x1800af17a  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af17f  nop
0x1800af180  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af188  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af18d  mov     eax, ebx
0x1800af18f  jmp     loc_1800AF905
0x1800af194  lea     rcx, [rsp+278h+var_238]
0x1800af199  call    ??$make_unique_nothrow@VCallerContext@Web@Authentication@Security@Internal@Windows@@$$V@wil@@YA?AV?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(void)
0x1800af19e  nop
0x1800af19f  mov     rdi, [rsp+278h+var_238]
0x1800af1a4  test    rdi, rdi
0x1800af1a7  jnz     short loc_1800AF20D
0x1800af1a9  mov     rcx, [rsp+278h]; this
0x1800af1b1  mov     ebx, 8007000Eh
0x1800af1b6  mov     r9d, ebx; char *
0x1800af1b9  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af1c0  mov     edx, 7A2h; void *
0x1800af1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af1ca  nop
0x1800af1cb  xor     edx, edx
0x1800af1cd  lea     rcx, [rsp+278h+var_238]
0x1800af1d2  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800af1d7  nop
0x1800af1d8  lea     rcx, [rsp+278h+var_240]
0x1800af1dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af1e2  nop
0x1800af1e3  lea     rcx, [rsp+278h+var_248]
0x1800af1e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af1ed  nop
0x1800af1ee  lea     rcx, [rsp+278h+var_228]; this
0x1800af1f3  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af1f8  nop
0x1800af1f9  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af201  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af206  mov     eax, ebx
0x1800af208  jmp     loc_1800AF905
0x1800af20d  mov     r9b, 1; bool
0x1800af210  mov     r8, [rsp+278h+var_200]; unsigned __int64
0x1800af215  mov     rdx, rsi; struct IUnknown *
0x1800af218  mov     rcx, rdi; this
0x1800af21b  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800af220  mov     ebx, eax
0x1800af222  xor     esi, esi
0x1800af224  test    eax, eax
0x1800af226  jns     short loc_1800AF287
0x1800af228  mov     rcx, [rsp+278h]; this
0x1800af230  mov     r9d, eax; char *
0x1800af233  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af23a  mov     edx, 7A3h; void *
0x1800af23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af244  nop
0x1800af245  xor     edx, edx
0x1800af247  lea     rcx, [rsp+278h+var_238]
0x1800af24c  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800af251  nop
0x1800af252  lea     rcx, [rsp+278h+var_240]
0x1800af257  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af25c  nop
0x1800af25d  lea     rcx, [rsp+278h+var_248]
0x1800af262  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af267  nop
0x1800af268  lea     rcx, [rsp+278h+var_228]; this
0x1800af26d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af272  nop
0x1800af273  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af27b  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af280  mov     eax, ebx
0x1800af282  jmp     loc_1800AF905
0x1800af287  mov     [rsp+278h+TokenHandle], rsi
0x1800af28c  mov     [rsp+278h+var_208], sil
0x1800af291  mov     rdx, [rdi+10h]; unsigned __int64
0x1800af295  lea     rcx, [rsp+278h+TokenHandle]; TokenHandle
0x1800af29a  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800af29f  mov     ebx, eax
0x1800af2a1  test    eax, eax
0x1800af2a3  jns     short loc_1800AF30F
0x1800af2a5  mov     rcx, [rsp+278h]; this
0x1800af2ad  mov     r9d, eax; char *
0x1800af2b0  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af2b7  mov     edx, 7A5h; void *
0x1800af2bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af2c1  nop
0x1800af2c2  lea     rcx, [rsp+278h+TokenHandle]; this
0x1800af2c7  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800af2cc  nop
0x1800af2cd  xor     edx, edx
0x1800af2cf  lea     rcx, [rsp+278h+var_238]
0x1800af2d4  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800af2d9  nop
0x1800af2da  lea     rcx, [rsp+278h+var_240]
0x1800af2df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af2e4  nop
0x1800af2e5  lea     rcx, [rsp+278h+var_248]
0x1800af2ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af2ef  nop
0x1800af2f0  lea     rcx, [rsp+278h+var_228]; this
0x1800af2f5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af2fa  nop
0x1800af2fb  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af303  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af308  mov     eax, ebx
0x1800af30a  jmp     loc_1800AF905
0x1800af30f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x1800af316  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x1800af31b  test    al, al
0x1800af31d  jz      loc_1800AF528
0x1800af323  mov     rcx, rdi; this
0x1800af326  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800af32b  test    al, al
0x1800af32d  jz      loc_1800AF528
0x1800af333  mov     [rsp+278h+var_1F8], rsi
0x1800af33b  mov     [rsp+278h+string], rsi
0x1800af340  mov     rax, [r14]
0x1800af343  mov     rbx, [rax]
0x1800af346  lea     rcx, [rsp+278h+string]
0x1800af34b  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800af350  lea     r8, [rsp+278h+string]
0x1800af355  lea     rdx, _GUID_c8423c1d_aa94_48ea_86e5_4502f998ab78
0x1800af35c  mov     rcx, r14
0x1800af35f  mov     rax, rbx
0x1800af362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af367  mov     ebx, eax
0x1800af369  test    eax, eax
0x1800af36b  jns     short loc_1800AF3E2
0x1800af36d  mov     rcx, [rsp+278h]; this
0x1800af375  mov     r9d, eax; char *
0x1800af378  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800af37f  mov     edx, 7B1h; void *
0x1800af384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af389  nop
0x1800af38a  lea     rcx, [rsp+278h+string]
0x1800af38f  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800af394  nop
0x1800af395  lea     rcx, [rsp+278h+TokenHandle]; this
0x1800af39a  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800af39f  nop
0x1800af3a0  xor     edx, edx
0x1800af3a2  lea     rcx, [rsp+278h+var_238]
0x1800af3a7  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800af3ac  nop
0x1800af3ad  lea     rcx, [rsp+278h+var_240]
0x1800af3b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af3b7  nop
0x1800af3b8  lea     rcx, [rsp+278h+var_248]
0x1800af3bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800af3c2  nop
0x1800af3c3  lea     rcx, [rsp+278h+var_228]; this
0x1800af3c8  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800af3cd  nop
0x1800af3ce  lea     rcx, [rsp+278h+var_1B8]; this
0x1800af3d6  call    ??1TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalRequestTokenAsync::~TokenBrokerInternalRequestTokenAsync(void)
0x1800af3db  mov     eax, ebx
0x1800af3dd  jmp     loc_1800AF905
0x1800af3e2  mov     rcx, [rsp+278h+string]
0x1800af3e7  mov     rax, [rcx]
0x1800af3ea  lea     rdx, [rsp+278h+var_1F8]
  ... truncated ...
```
