# Windows::Security::Authentication::Web::CWebAuthBrokerFactory::AuthenticateWithCallbackUriAsync(Windows::Security::Authentication::Web::WebAuthenticationOptions,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> * *)

- ea: `0x180017770`
- end: `0x180017ded`
- name: `?AuthenticateWithCallbackUriAsync@CWebAuthBrokerFactory@Web@Authentication@Security@Windows@@UEAAJW4WebAuthenticationOptions@2345@PEAUIUriRuntimeClass@Foundation@5@1PEAPEAU?$IAsyncOperation@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@85@@Z`
- size: `1661`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthBrokerFactory *this, unsigned __int32 options, Windows::Foundation::IUriRuntimeClass *requestUri, HSTRING__ *callbackUri, Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> **ppAsyncInfo)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b20`
- `0x180003330`
- `0x180004940`
- `0x180006060`
- `0x180006e5c`
- `0x18000737c`
- `0x18000f568`
- `0x180011b30`
- `0x1800161c0`
- `0x180017770`
- `0x180018774`
- `0x18001bfc4`
- `0x1800204ee`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800177fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800178bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017a3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b06`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800177fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800178bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017a3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800179d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800179d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800178a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017aed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800178a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017aed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017b94`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180017a4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180017b14`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180017a4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180017b14`
- `WINHTTP!WinHttpCrackUrl` at `0x180017a82`
- `WINHTTP!WinHttpCrackUrl` at `0x180017a82`

## string_xrefs

- `0x18001789d`: `Request URI parameter is not present`
- `0x180017a1e`: `URI Scheme is not https`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthBrokerFactory::AuthenticateWithCallbackUriAsync(
        Windows::Security::Authentication::Web::CWebAuthBrokerFactory *this,
        unsigned __int32 options,
        Windows::Foundation::IUriRuntimeClass *requestUri,
        HSTRING__ *callbackUri,
        Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> **ppAsyncInfo)
{
  unsigned int v8; // edi
  WPP_PROJECT_CONTROL_BLOCK *v9; // rcx
  unsigned int v10; // ebx
  int v11; // eax
  WPP_PROJECT_CONTROL_BLOCK *v12; // rcx
  unsigned __int16 v13; // dx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v15; // r14
  DWORD Logger; // eax
  unsigned __int16 v17; // dx
  const _GUID *v18; // r8
  const wchar_t *v19; // rcx
  int v20; // eax
  Windows::Security::Authentication::Web::CWebAuthOperation *ptr; // rbx
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > > *v22; // rdi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT hr; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int brokerFlags; // [rsp+44h] [rbp-BCh] BYREF
  ABI::Windows::Foundation::AsyncStatus status; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *> > spAsyncInfo; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int dwUri; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::CWebAuthOperation> spAsyncWorker; // [rsp+60h] [rbp-A0h] BYREF
  Windows::Internal::String request; // [rsp+68h] [rbp-98h] BYREF
  _AUTH_BROKER_CLIENT_CONTEXT *clientContext; // [rsp+70h] [rbp-90h] BYREF
  Windows::Internal::String scheme; // [rsp+78h] [rbp-88h] BYREF
  Windows::Internal::String callback; // [rsp+80h] [rbp-80h] BYREF
  Windows::Security::Authentication::Web::WebAuthenticationOptions v35; // [rsp+88h] [rbp-78h] BYREF
  _WINHTTP_URL_COMPONENTS urlComponents; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+108h] [rbp+8h] BYREF
  Windows::Internal::StringReference https; // [rsp+120h] [rbp+20h] BYREF

  v35 = options;
  hr = 0;
  request._hstring = 0;
  callback._hstring = 0;
  scheme._hstring = 0;
  spAsyncInfo.ptr_ = 0;
  spAsyncWorker.ptr_ = 0;
  if ( WindowsCreateStringReference(L"https", 5u, &https._header, &https._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  clientContext = 0;
  status = Started;
  v8 = 0;
  dwUri = 0;
  memset_0(&urlComponents, 0, sizeof(urlComponents));
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0xCu, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids, options);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !requestUri )
  {
    if ( v9 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v9[1].ReserveSpace[28] & 8) != 0
      && v9[1].Control.Level >= 2u )
    {
      WPP_SF_(v9[1].Control.Logger, 0xDu, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
    }
    if ( WindowsCreateStringReference(L"Request URI parameter is not present", 0x24u, &hstringHeader, &string) >= 0 )
      goto LABEL_14;
LABEL_13:
    RaiseException(0xC000000D, 1u, 0, 0);
LABEL_14:
    v10 = -2147024809;
LABEL_40:
    RoOriginateError(v10, string);
    goto LABEL_86;
  }
  if ( !ppAsyncInfo )
  {
    if ( v9 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v9[1].ReserveSpace[28] & 8) != 0
      && v9[1].Control.Level >= 2u )
    {
      WPP_SF_(v9[1].Control.Logger, 0xEu, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
    }
    v10 = -2147024809;
    goto LABEL_86;
  }
  *ppAsyncInfo = 0;
  v11 = requestUri->get_AbsoluteUri(requestUri, (HSTRING__ **)&request);
  hr = v11;
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_86;
    }
    v13 = 15;
LABEL_26:
    WPP_SF_d(v12[1].Control.Logger, v13, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids, v11);
LABEL_85:
    v10 = hr;
    goto LABEL_86;
  }
  v11 = requestUri->get_SchemeName(requestUri, (HSTRING__ **)&scheme);
  hr = v11;
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_86;
    }
    v13 = 16;
    goto LABEL_26;
  }
  brokerFlags = 0;
  WindowsCompareStringOrdinal(scheme._hstring, https._hstring, (INT32 *)&brokerFlags);
  if ( brokerFlags )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x11u, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
    }
    if ( WindowsCreateStringReference(L"URI Scheme is not https", 0x17u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v10 = -2146892955;
    goto LABEL_40;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(request._hstring, &dwUri);
  urlComponents.dwStructSize = 104;
  v15 = StringRawBuffer;
  if ( !WinHttpCrackUrl(StringRawBuffer, dwUri, 0, &urlComponents) )
  {
    hr = -2147024809;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      Logger = GetLastError();
      WPP_SF_SDd(WPP_GLOBAL_Control[1].Control.Logger, v17, v18, v15, Logger, -2147024809);
    }
    if ( WindowsCreateStringReference(L"Invalid Url", 0xBu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    RoOriginateError((unsigned int)hr, string);
    goto LABEL_85;
  }
  if ( (options & 1) != 0 )
    v8 = 0x20000;
  brokerFlags = v8;
  if ( (options & 2) != 0 )
  {
    v8 |= 0x10000u;
    brokerFlags = v8;
  }
  if ( (options & 4) != 0 )
  {
    v8 |= 0x80000u;
    brokerFlags = v8;
  }
  if ( (options & 8) != 0 )
  {
    v8 |= 0x100000u;
    brokerFlags = v8;
  }
  if ( GetAuthHostRegDWORDValue(L"EnableTestEnterprise") )
  {
    v8 |= 0x100000u;
    brokerFlags = v8;
  }
  if ( (v8 & 0x10000) != 0 && (v8 & 0x80000) != 0 )
  {
    if ( WindowsCreateStringReference(L"Invalid multiple options", 0x18u, &hstringHeader, &string) >= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( GetAuthHostFeatureControlRegDWORDValue(v19) )
  {
    v8 |= 0x40000u;
    brokerFlags = v8;
  }
  hr = GetAndVerifyAuthBrokerClientContext(v8, &clientContext);
  v10 = hr;
  if ( hr >= 0 )
  {
    v20 = VerifyAuthBrokerCallbackUri(callbackUri, requestUri, clientContext, &callback._hstring, v8, (int *)&status);
    hr = v20;
    if ( v20 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncWorker);
      hr = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::CWebAuthOperation,Windows::Security::Authentication::Web::CWebAuthOperation,Windows::Internal::String &,Windows::Internal::String &,_AUTH_BROKER_CLIENT_CONTEXT * &,unsigned int &,int &,enum Windows::Security::Authentication::Web::WebAuthenticationOptions &>(
             &spAsyncWorker.ptr_,
             &request,
             &callback,
             &clientContext,
             &brokerFlags,
             (int *)&status,
             &v35);
      if ( hr < 0 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x15u, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
        }
      }
      else
      {
        ptr = spAsyncWorker.ptr_;
        status = Started;
        v22 = &spAsyncWorker.ptr_->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >;
        spAsyncWorker.ptr_->get_Status(
          &spAsyncWorker.ptr_->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >,
          &status);
        if ( status == Error )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x14u, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
          }
          v22->get_ErrorCode(v22, &hr);
        }
        else
        {
          QueryInterface = ptr->QueryInterface;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncInfo);
          hr = QueryInterface(ptr, &GUID_b34952ac_265e_5947_8735_e9318f4301ff, (void **)&spAsyncInfo.ptr_);
          if ( hr >= 0 )
          {
            *ppAsyncInfo = spAsyncInfo.ptr_;
            spAsyncInfo.ptr_ = 0;
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
           && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
           && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x13u, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids, v20);
    }
    FreeAuthBrokerClientContext(clientContext);
    goto LABEL_85;
  }
LABEL_86:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncWorker);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncInfo);
  Windows::Internal::String::~String(&scheme);
  Windows::Internal::String::~String(&callback);
  Windows::Internal::String::~String(&request);
  return v10;
}

```

## disassembly

```asm
0x180017770  mov     [rsp-8+arg_0], rbx
0x180017775  push    rbp
0x180017776  push    rsi
0x180017777  push    rdi
0x180017778  push    r12
0x18001777a  push    r13
0x18001777c  push    r14
0x18001777e  push    r15
0x180017780  lea     rbp, [rsp-50h]
0x180017785  sub     rsp, 150h
0x18001778c  mov     rax, cs:__security_cookie
0x180017793  xor     rax, rsp
0x180017796  mov     [rbp+80h+var_40], rax
0x18001779a  mov     r12, [rbp+80h+arg_20]
0x1800177a1  lea     this, aHttps; "https"
0x1800177a8  xor     r14d, r14d
0x1800177ab  mov     [rbp+80h+var_F8], options
0x1800177ae  mov     r13, callbackUri
0x1800177b1  mov     [rsp+180h+hr], r14d
0x1800177b6  mov     r15, requestUri
0x1800177b9  mov     [rsp+180h+request._hstring], r14
0x1800177be  mov     esi, options
0x1800177c0  mov     [rbp+80h+callback._hstring], r14
0x1800177c4  lea     options, [r14+5]; length
0x1800177c8  mov     [rsp+180h+scheme._hstring], r14
0x1800177cd  lea     callbackUri, [rbp+80h+https]; string
0x1800177d1  mov     [rsp+180h+spAsyncInfo.ptr_], r14
0x1800177d6  lea     requestUri, [rbp+80h+https._header]; hstringHeader
0x1800177da  mov     [rsp+180h+spAsyncWorker.ptr_], r14
0x1800177df  call    cs:__imp_WindowsCreateStringReference
0x1800177e5  lea     ebx, [r14+1]
0x1800177e9  test    eax, eax
0x1800177eb  jns     short loc_180017800
0x1800177ed  xor     r9d, r9d; lpArguments
0x1800177f0  xor     r8d, r8d; nNumberOfArguments
0x1800177f3  mov     options, ebx; dwExceptionFlags
0x1800177f5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800177fa  call    cs:__imp_RaiseException
0x180017800  xor     options, options; Val
0x180017802  mov     [rsp+180h+clientContext], r14
0x180017807  lea     this, [rbp+80h+urlComponents]; void *
0x18001780b  mov     [rsp+180h+status], r14d
0x180017810  mov     edi, r14d
0x180017813  mov     [rsp+180h+dwUri], r14d
0x180017818  lea     r8d, [rdx+68h]; Size
0x18001781c  call    memset_0
0x180017821  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017828  lea     rax, WPP_GLOBAL_Control
0x18001782f  cmp     this, rax
0x180017832  jz      short loc_180017866
0x180017834  test    byte ptr [this+44h], 8
0x180017838  jz      short loc_180017866
0x18001783a  cmp     byte ptr [this+41h], 5
0x18001783e  jb      short loc_180017866
0x180017840  mov     this, [this+38h]; Logger
0x180017844  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x18001784b  mov     options, 0Ch; id
0x180017850  mov     r9d, esi; _a1
0x180017853  call    WPP_SF_d
0x180017858  mov     this, cs:WPP_GLOBAL_Control
0x18001785f  lea     rax, WPP_GLOBAL_Control
0x180017866  test    r15, r15
0x180017869  jnz     short loc_1800178CB
0x18001786b  cmp     this, rax; __annotation("TMF:",
0x18001786e  jz      short loc_180017890
0x180017870  test    byte ptr [this+44h], 8
0x180017874  jz      short loc_180017890
0x180017876  cmp     byte ptr [this+41h], 2
0x18001787a  jb      short loc_180017890
0x18001787c  mov     this, [this+38h]; Logger
0x180017880  lea     options, [r15+0Dh]; id
0x180017884  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x18001788b  call    WPP_SF_
0x180017890  lea     callbackUri, [rbp+80h+string]; string
0x180017894  mov     options, 24h ; '$'; length
0x180017899  lea     requestUri, [rbp+80h+hstringHeader]; hstringHeader
0x18001789d  lea     this, aRequestUriPara; "Request URI parameter is not present"
0x1800178a4  call    cs:__imp_WindowsCreateStringReference
0x1800178aa  test    eax, eax
0x1800178ac  jns     short loc_1800178C1
0x1800178ae  mov     options, ebx; dwExceptionFlags
0x1800178b0  xor     r9d, r9d; lpArguments
0x1800178b3  xor     r8d, r8d; nNumberOfArguments
0x1800178b6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800178bb  call    cs:__imp_RaiseException
0x1800178c1  mov     ebx, 80070057h
0x1800178c6  jmp     loc_180017A49
0x1800178cb  test    r12, r12
0x1800178ce  jnz     short loc_180017900
0x1800178d0  cmp     this, rax; __annotation("TMF:",
0x1800178d3  jz      short loc_1800178F6
0x1800178d5  test    byte ptr [this+44h], 8
0x1800178d9  jz      short loc_1800178F6
0x1800178db  cmp     byte ptr [this+41h], 2
0x1800178df  jb      short loc_1800178F6
0x1800178e1  mov     this, [this+38h]; Logger
0x1800178e5  lea     options, [r12+0Eh]; id
0x1800178ea  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x1800178f1  call    WPP_SF_
0x1800178f6  mov     ebx, 80070057h
0x1800178fb  jmp     loc_180017D93
0x180017900  mov     [r12], r14
0x180017904  lea     rdx, [rsp+180h+request]
0x180017909  mov     rax, [r15]
0x18001790c  mov     this, r15
0x18001790f  mov     rax, [rax+30h]
0x180017913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017918  mov     [rsp+180h+hr], eax
0x18001791c  mov     ebx, eax
0x18001791e  test    eax, eax
0x180017920  jns     short loc_18001796A
0x180017922  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017929  lea     rdx, WPP_GLOBAL_Control
0x180017930  cmp     this, rdx
0x180017933  jz      loc_180017D93
0x180017939  test    byte ptr [this+44h], 8
0x18001793d  jz      loc_180017D93
0x180017943  cmp     byte ptr [this+41h], 2
0x180017947  jb      loc_180017D93
0x18001794d  mov     options, 0Fh; id
0x180017952  mov     this, [this+38h]; Logger
0x180017956  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x18001795d  mov     r9d, eax; _a1
0x180017960  call    WPP_SF_d
0x180017965  jmp     loc_180017D8F
0x18001796a  mov     rax, [r15]
0x18001796d  lea     rdx, [rsp+180h+scheme]
0x180017972  mov     this, r15
0x180017975  mov     rax, [rax+88h]
0x18001797c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017981  mov     [rsp+180h+hr], eax
0x180017985  mov     ebx, eax
0x180017987  test    eax, eax
0x180017989  jns     short loc_1800179BD
0x18001798b  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017992  lea     rdx, WPP_GLOBAL_Control
0x180017999  cmp     this, rdx
0x18001799c  jz      loc_180017D93
0x1800179a2  test    byte ptr [this+44h], 8
0x1800179a6  jz      loc_180017D93
0x1800179ac  cmp     byte ptr [this+41h], 2
0x1800179b0  jb      loc_180017D93
0x1800179b6  mov     options, 10h
0x1800179bb  jmp     short loc_180017952
0x1800179bd  mov     rdx, [rbp+80h+https._hstring]; string2
0x1800179c1  lea     requestUri, [rsp+180h+brokerFlags]; result
0x1800179c6  mov     this, [rsp+180h+scheme._hstring]; string1
0x1800179cb  mov     [rsp+180h+brokerFlags], r14d
0x1800179d0  call    cs:__imp_WindowsCompareStringOrdinal
0x1800179d6  cmp     [rsp+180h+brokerFlags], r14d
0x1800179db  jz      short loc_180017A5A
0x1800179dd  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800179e4  lea     rdx, WPP_GLOBAL_Control
0x1800179eb  cmp     this, rdx
0x1800179ee  jz      short loc_180017A11
0x1800179f0  test    byte ptr [this+44h], 8
0x1800179f4  jz      short loc_180017A11
0x1800179f6  cmp     byte ptr [this+41h], 2
0x1800179fa  jb      short loc_180017A11
0x1800179fc  mov     this, [this+38h]; Logger
0x180017a00  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x180017a07  mov     options, 11h; id
0x180017a0c  call    WPP_SF_
0x180017a11  lea     callbackUri, [rbp+80h+string]; string
0x180017a15  mov     options, 17h; length
0x180017a1a  lea     requestUri, [rbp+80h+hstringHeader]; hstringHeader
0x180017a1e  lea     this, aUriSchemeIsNot; "URI Scheme is not https"
0x180017a25  call    cs:__imp_WindowsCreateStringReference
0x180017a2b  test    eax, eax
0x180017a2d  jns     short loc_180017A44
0x180017a2f  xor     r9d, r9d; lpArguments
0x180017a32  xor     r8d, r8d; nNumberOfArguments
0x180017a35  mov     ecx, 0C000000Dh; dwExceptionCode
0x180017a3a  lea     options, [callbackUri+1]; dwExceptionFlags
0x180017a3e  call    cs:__imp_RaiseException
0x180017a44  mov     ebx, 80090365h
0x180017a49  mov     rdx, [rbp+80h+string]
0x180017a4d  mov     ecx, ebx
0x180017a4f  call    cs:__imp_RoOriginateError
0x180017a55  jmp     loc_180017D93
0x180017a5a  mov     this, [rsp+180h+request._hstring]; string
0x180017a5f  lea     rdx, [rsp+180h+dwUri]; length
0x180017a64  call    cs:__imp_WindowsGetStringRawBuffer
0x180017a6a  mov     options, [rsp+180h+dwUri]; dwUrlLength
0x180017a6e  lea     callbackUri, [rbp+80h+urlComponents]; lpUrlComponents
0x180017a72  mov     this, rax; pwszUrl
0x180017a75  mov     [rbp+80h+urlComponents.dwStructSize], 68h ; 'h'
0x180017a7c  xor     r8d, r8d; dwFlags
0x180017a7f  mov     r14, rax
0x180017a82  call    cs:__imp_WinHttpCrackUrl
0x180017a88  test    eax, eax
0x180017a8a  jnz     loc_180017B1F
0x180017a90  mov     ebx, 80070057h
0x180017a95  mov     [rsp+180h+hr], ebx
0x180017a99  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017aa0  lea     rdx, WPP_GLOBAL_Control
0x180017aa7  cmp     rax, rdx
0x180017aaa  jz      short loc_180017AD9
0x180017aac  test    byte ptr [rax+44h], 8
0x180017ab0  jz      short loc_180017AD9
0x180017ab2  cmp     byte ptr [rax+41h], 2
0x180017ab6  jb      short loc_180017AD9
0x180017ab8  call    cs:__imp_GetLastError
0x180017abe  mov     this, cs:WPP_GLOBAL_Control
0x180017ac5  mov     callbackUri, r14; _a3
0x180017ac8  mov     [rsp+180h+id], ebx; id
0x180017acc  mov     [rsp+180h+Logger], eax; Logger
0x180017ad0  mov     this, [this+38h]; Logger
0x180017ad4  call    WPP_SF_SDd
0x180017ad9  lea     callbackUri, [rbp+80h+string]; string
0x180017add  mov     options, 0Bh; length
0x180017ae2  lea     requestUri, [rbp+80h+hstringHeader]; hstringHeader
0x180017ae6  lea     this, aInvalidUrl; "Invalid Url"
0x180017aed  call    cs:__imp_WindowsCreateStringReference
0x180017af3  test    eax, eax
0x180017af5  jns     short loc_180017B0C
0x180017af7  xor     r9d, r9d; lpArguments
0x180017afa  xor     r8d, r8d; nNumberOfArguments
0x180017afd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180017b02  lea     options, [callbackUri+1]; dwExceptionFlags
0x180017b06  call    cs:__imp_RaiseException
0x180017b0c  mov     rdx, [rbp+80h+string]
0x180017b10  mov     ecx, [rsp+180h+hr]
0x180017b14  call    cs:__imp_RoOriginateError
0x180017b1a  jmp     loc_180017D8F
0x180017b1f  test    sil, 1
0x180017b23  mov     eax, 20000h
0x180017b28  cmovnz  edi, eax
0x180017b2b  mov     [rsp+180h+brokerFlags], edi
0x180017b2f  test    sil, 2
0x180017b33  jz      short loc_180017B3D
0x180017b35  bts     edi, 10h
0x180017b39  mov     [rsp+180h+brokerFlags], edi
0x180017b3d  test    sil, 4
0x180017b41  jz      short loc_180017B4B
0x180017b43  bts     edi, 13h
0x180017b47  mov     [rsp+180h+brokerFlags], edi
0x180017b4b  mov     r14b, 8
0x180017b4e  mov     ebx, 100000h
0x180017b53  test    r14b, sil
0x180017b56  jz      short loc_180017B5E
0x180017b58  or      edi, ebx
0x180017b5a  mov     [rsp+180h+brokerFlags], edi
0x180017b5e  lea     this, aEnabletestente; "EnableTestEnterprise"
0x180017b65  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180017b6a  test    eax, eax
0x180017b6c  jz      short loc_180017B74
0x180017b6e  or      edi, ebx
0x180017b70  mov     [rsp+180h+brokerFlags], edi
0x180017b74  bt      edi, 10h
0x180017b78  jnb     short loc_180017BAC
0x180017b7a  bt      edi, 13h
0x180017b7e  jnb     short loc_180017BAC
0x180017b80  lea     callbackUri, [rbp+80h+string]; string
0x180017b84  mov     options, 18h; length
0x180017b89  lea     requestUri, [rbp+80h+hstringHeader]; hstringHeader
0x180017b8d  lea     this, aInvalidMultipl; "Invalid multiple options"
0x180017b94  call    cs:__imp_WindowsCreateStringReference
0x180017b9a  test    eax, eax
0x180017b9c  jns     loc_1800178C1
0x180017ba2  mov     options, 1
0x180017ba7  jmp     loc_1800178B0
0x180017bac  call    ?GetAuthHostFeatureControlRegDWORDValue@@YAKPEBG@Z; GetAuthHostFeatureControlRegDWORDValue(ushort const *)
0x180017bb1  test    eax, eax
0x180017bb3  jz      short loc_180017BBD
0x180017bb5  bts     edi, 12h
0x180017bb9  mov     [rsp+180h+brokerFlags], edi
0x180017bbd  lea     rdx, [rsp+180h+clientContext]; clientContext
0x180017bc2  mov     ecx, edi; brokerFlags
0x180017bc4  call    ?GetAndVerifyAuthBrokerClientContext@@YAJIPEAPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; GetAndVerifyAuthBrokerClientContext(uint,_AUTH_BROKER_CLIENT_CONTEXT * *)
0x180017bc9  mov     [rsp+180h+hr], eax
0x180017bcd  mov     ebx, eax
0x180017bcf  test    eax, eax
0x180017bd1  js      loc_180017D93
0x180017bd7  mov     requestUri, [rsp+180h+clientContext]; clientContext
0x180017bdc  lea     rax, [rsp+180h+status]
0x180017be1  mov     qword ptr [rsp+180h+id], rax; useSsoAppContainer
0x180017be6  lea     callbackUri, [rbp+80h+callback]; callbackAbsoluteUri
0x180017bea  mov     rdx, r15; requestUri
0x180017bed  mov     [rsp+180h+Logger], edi; brokerFlags
0x180017bf1  mov     this, r13; callbackUri
0x180017bf4  call    ?VerifyAuthBrokerCallbackUri@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@0PEAU_AUTH_BROKER_CLIENT_CONTEXT@@PEAPEAUHSTRING__@@IPEAH@Z; VerifyAuthBrokerCallbackUri(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,_AUTH_BROKER_CLIENT_CONTEXT *,HSTRING__ * *,uint,int *)
0x180017bf9  mov     [rsp+180h+hr], eax
0x180017bfd  test    eax, eax
0x180017bff  jns     short loc_180017C49
0x180017c01  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017c08  lea     rdx, WPP_GLOBAL_Control
0x180017c0f  cmp     this, rdx
0x180017c12  jz      $Exit_17
0x180017c18  test    [this+44h], r14b
0x180017c1c  jz      $Exit_17
0x180017c22  cmp     byte ptr [this+41h], 2
0x180017c26  jb      $Exit_17
0x180017c2c  mov     this, [this+38h]; Logger
0x180017c30  lea     requestUri, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x180017c37  mov     options, 13h; id
0x180017c3c  mov     r9d, eax; _a1
0x180017c3f  call    WPP_SF_d
0x180017c44  jmp     $Exit_17
0x180017c49  lea     this, [rsp+180h+spAsyncWorker]; this
  ... truncated ...
```
