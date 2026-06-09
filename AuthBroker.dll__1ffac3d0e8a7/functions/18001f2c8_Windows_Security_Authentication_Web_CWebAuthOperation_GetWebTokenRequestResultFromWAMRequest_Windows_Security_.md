# Windows::Security::Authentication::Web::CWebAuthOperation::GetWebTokenRequestResultFromWAMRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x18001f2c8`
- end: `0x18001f46b`
- name: `?GetWebTokenRequestResultFromWAMRequest@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAAJPEAUIWebTokenRequest@Core@2345@PEAPEAUIWebTokenRequestResult@72345@@Z`
- size: `419`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, Windows::Security::Authentication::Web::Core::IWebTokenRequest *pWebTokenRequest, Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **ppTokenResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019484`

## callees

- `0x180001150`
- `0x180006060`
- `0x18001e9b0`
- `0x18001ecc8`
- `0x18001f2c8`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f33a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f33a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f321`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f35b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f35b`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001f371`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001f371`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::GetWebTokenRequestResultFromWAMRequest(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        Windows::Security::Authentication::Web::Core::IWebTokenRequest *pWebTokenRequest,
        Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **ppTokenResult)
{
  HSTRING v6; // rbx
  const _tlgProvider_t *v7; // rcx
  signed int ActivationFactory; // ebx
  const _GUID *v9; // r8
  const _GUID *v10; // r9
  Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *ptr; // rdi
  HRESULT (__fastcall *RequestTokenAsync)(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *, Windows::Security::Authentication::Web::Core::IWebTokenRequest *, Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *, unsigned int, Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> **); // rbx
  Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *v13; // rdi
  HRESULT v14; // edx
  void *v15; // r8
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> requestResult; // [rsp+30h] [rbp-50h] BYREF
  Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics> tbInternal; // [rsp+38h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> > tokenRequestResult; // [rsp+40h] [rbp-40h] BYREF
  _tlgWrapperByVal<4> v20; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  tbInternal.ptr_ = 0;
  tokenRequestResult.ptr_ = 0;
  requestResult.ptr_ = 0;
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal,
         0x40u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tbInternal);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &tbInternal);
  if ( ActivationFactory < 0 )
    goto $Cleanup_14;
  CoAllowSetForegroundWindow(tbInternal.ptr_, 0);
  ptr = tbInternal.ptr_;
  RequestTokenAsync = tbInternal.ptr_->RequestTokenAsync;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequestResult);
  ActivationFactory = RequestTokenAsync(
                        ptr,
                        pWebTokenRequest,
                        0,
                        (unsigned int)this->m_ClientContext->parentWindow,
                        &tokenRequestResult.ptr_);
  if ( ActivationFactory < 0
    || (v13 = tokenRequestResult.ptr_,
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestResult),
        ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
                              v13,
                              v14,
                              v15),
        ActivationFactory < 0)
    || (ActivationFactory = v13->GetResults(v13, &requestResult.ptr_), ActivationFactory < 0) )
  {
$Cleanup_14:
    if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 2 )
    {
      v20.Value = ActivationFactory;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v7,
        &tlgEvent_10._tlgChannel,
        v9,
        v10,
        &v20);
    }
  }
  else
  {
    ActivationFactory = 0;
    *ppTokenResult = requestResult.ptr_;
    requestResult.ptr_ = 0;
  }
  Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&requestResult);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenRequestResult);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tbInternal);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001f2c8  mov     [rsp-28h+arg_18], rbx
0x18001f2cd  push    rbp
0x18001f2ce  push    rsi
0x18001f2cf  push    rdi
0x18001f2d0  push    r14
0x18001f2d2  push    r15
0x18001f2d4  mov     rbp, rsp
0x18001f2d7  sub     rsp, 80h
0x18001f2de  mov     rax, cs:__security_cookie
0x18001f2e5  xor     rax, rsp
0x18001f2e8  mov     [rbp+var_10], rax
0x18001f2ec  mov     r14, ppTokenResult
0x18001f2ef  mov     [rbp+tbInternal.ptr_], 0
0x18001f2f7  mov     r15, pWebTokenRequest
0x18001f2fa  mov     [rbp+tokenRequestResult.ptr_], 0
0x18001f302  mov     rsi, this
0x18001f305  mov     [rbp+requestResult.ptr_], 0
0x18001f30d  lea     ppTokenResult, [rbp+hstringHeader]; hstringHeader
0x18001f311  mov     edx, 40h ; '@'; length
0x18001f316  lea     this, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; sourceString
0x18001f31d  lea     r9, [rbp+string]; string
0x18001f321  call    cs:__imp_WindowsCreateStringReference
0x18001f327  test    eax, eax
0x18001f329  jns     short loc_18001F340
0x18001f32b  xor     r9d, r9d; lpArguments
0x18001f32e  xor     r8d, r8d; nNumberOfArguments
0x18001f331  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001f336  lea     edx, [r9+1]; dwExceptionFlags
0x18001f33a  call    cs:__imp_RaiseException
0x18001f340  mov     rbx, [rbp+string]
0x18001f344  lea     this, [rbp+tbInternal]; this
0x18001f348  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f34d  lea     ppTokenResult, [rbp+tbInternal]
0x18001f351  mov     this, rbx
0x18001f354  lea     pWebTokenRequest, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18001f35b  call    cs:__imp_RoGetActivationFactory
0x18001f361  mov     ebx, eax
0x18001f363  test    eax, eax
0x18001f365  js      $Cleanup_14
0x18001f36b  mov     this, [rbp+tbInternal.ptr_]; pUnk
0x18001f36f  xor     edx, edx; lpvReserved
0x18001f371  call    cs:__imp_CoAllowSetForegroundWindow
0x18001f377  mov     rdi, [rbp+tbInternal.ptr_]
0x18001f37b  lea     this, [rbp+tokenRequestResult]; this
0x18001f37f  mov     rax, [rdi]
0x18001f382  mov     rbx, [rax+120h]
0x18001f389  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f38e  mov     r9, [rsi+0F0h]
0x18001f395  lea     rax, [rbp+tokenRequestResult]
0x18001f399  mov     [rsp+80h+var_60], rax
0x18001f39e  xor     r8d, r8d
0x18001f3a1  mov     pWebTokenRequest, r15
0x18001f3a4  mov     this, rdi
0x18001f3a7  mov     rax, rbx
0x18001f3aa  mov     r9d, [r9+8]
0x18001f3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b3  mov     ebx, eax
0x18001f3b5  test    eax, eax
0x18001f3b7  js      short $Cleanup_14
0x18001f3b9  mov     rdi, [rbp+tokenRequestResult.ptr_]
0x18001f3bd  lea     this, [rbp+requestResult]; this
0x18001f3c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f3c6  mov     this, rdi; pOperation
0x18001f3c9  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)
0x18001f3ce  mov     ebx, eax
0x18001f3d0  test    eax, eax
0x18001f3d2  js      short $Cleanup_14
0x18001f3d4  mov     rax, [rdi]
0x18001f3d7  lea     pWebTokenRequest, [rbp+requestResult]
0x18001f3db  mov     this, rdi
0x18001f3de  mov     rax, [rax+40h]
0x18001f3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3e7  mov     ebx, eax
0x18001f3e9  test    eax, eax
0x18001f3eb  js      short $Cleanup_14
0x18001f3ed  mov     rax, [rbp+requestResult.ptr_]
0x18001f3f1  xor     ebx, ebx
0x18001f3f3  mov     [r14], rax
0x18001f3f6  mov     [rbp+requestResult.ptr_], 0
0x18001f3fe  jmp     short loc_18001F423
0x18001f400  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x18001f406  cmp     eax, 2
0x18001f409  jbe     short loc_18001F423
0x18001f40b  lea     rax, [rbp+var_38]; __annotation("_TlgWrite:|443|g_hMyWABTraceLoggingProvider|"Requesting Token from WAM failed."=|"hr"=")
0x18001f40f  mov     [rbp+var_38.Value], ebx
0x18001f412  lea     pWebTokenRequest, _tlgEvent_10._tlgChannel; <wrappedArgs_0>
0x18001f419  mov     [rsp+80h+var_60], rax; <writerArgs_0>
0x18001f41e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f423  mov     this, rsi; this
0x18001f426  call    ?CleanupLocalMutex@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ; Windows::Security::Authentication::Web::CWebAuthOperation::CleanupLocalMutex(void)
0x18001f42b  lea     this, [rbp+requestResult]; this
0x18001f42f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f434  lea     this, [rbp+tokenRequestResult]; this
0x18001f438  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f43d  lea     this, [rbp+tbInternal]; this
0x18001f441  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f446  mov     eax, ebx
0x18001f448  mov     this, [rbp+var_10]
0x18001f44c  xor     this, rsp; StackCookie
0x18001f44f  call    __security_check_cookie
0x18001f454  mov     rbx, [rsp+80h+arg_18]
0x18001f45c  add     rsp, 80h
0x18001f463  pop     r15
0x18001f465  pop     r14
0x18001f467  pop     rdi
0x18001f468  pop     rsi
0x18001f469  pop     rbp
0x18001f46a  retn
```
