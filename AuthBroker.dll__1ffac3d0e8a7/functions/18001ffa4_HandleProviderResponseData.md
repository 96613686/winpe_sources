# _HandleProviderResponseData

- ea: `0x18001ffa4`
- end: `0x1800200d9`
- name: `_HandleProviderResponseData`
- size: `309`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *pWebAuthRequest, Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *pTokenResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f624`

## callees

- `0x180001150`
- `0x180006060`
- `0x180012b88`
- `0x18001ffa4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800200aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800200aa`

## pseudocode

```c
__int64 __fastcall HandleProviderResponseData(
        Windows::Security::Authentication::Web::CWebAuthOperation *pWebAuthRequest,
        Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *pTokenResult)
{
  Windows::Security::Authentication::Web::Core::IWebTokenRequestResult_vtbl *v2; // rax
  HRESULT (__fastcall *get_ResponseData)(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> **); // rbx
  const _tlgProvider_t *v6; // rcx
  int v7; // ebx
  const _GUID *v8; // r8
  const _GUID *v9; // r9
  Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> *ptr; // rdi
  HRESULT (__fastcall *GetAt)(Windows::Foundation::Collections::IVectorView_impl<Windows::Foundation::Internal::AggregateType<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Security::Authentication::Web::Core::IWebTokenResponse *>,1> *, unsigned int, Windows::Security::Authentication::Web::Core::IWebTokenResponse **); // rbx
  Windows::Security::Authentication::Web::Core::IWebTokenResponse *v12; // rdi
  HRESULT (__fastcall *get_Token)(Windows::Security::Authentication::Web::Core::IWebTokenResponse *, HSTRING__ **); // rbx
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> > tokenResponseVector; // [rsp+30h] [rbp-10h] BYREF
  HSTRING__ *other; // [rsp+68h] [rbp+28h] BYREF
  Microsoft::WRL::Wrappers::HString strToken; // [rsp+70h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> tokenResponse; // [rsp+78h] [rbp+38h] BYREF

  v2 = pTokenResult->lpVtbl;
  tokenResponseVector.ptr_ = 0;
  tokenResponse.ptr_ = 0;
  strToken.hstr_ = 0;
  get_ResponseData = v2->get_ResponseData;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenResponseVector);
  v7 = get_ResponseData(pTokenResult, &tokenResponseVector.ptr_);
  if ( v7 < 0 )
    goto LABEL_6;
  ptr = tokenResponseVector.ptr_;
  GetAt = tokenResponseVector.ptr_->GetAt;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenResponse);
  v7 = GetAt(ptr, 0, &tokenResponse.ptr_);
  if ( v7 < 0
    || (v12 = tokenResponse.ptr_,
        get_Token = tokenResponse.ptr_->get_Token,
        WindowsDeleteString(strToken.hstr_),
        strToken.hstr_ = 0,
        v7 = get_Token(v12, &strToken.hstr_),
        v7 < 0)
    || (other = strToken.hstr_,
        v7 = Windows::Internal::String::Initialize(&pWebAuthRequest->m_ResponseData, &other),
        v7 < 0) )
  {
LABEL_6:
    if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 2 )
    {
      LODWORD(other) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v6,
        &tlgEvent_9._tlgChannel,
        v8,
        v9,
        (const _tlgWrapperByVal<4> *)&other);
    }
  }
  else
  {
    pWebAuthRequest->m_ResponseStatus = WebAuthenticationStatus_Success;
    v7 = 0;
  }
  WindowsDeleteString(strToken.hstr_);
  strToken.hstr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenResponse);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&tokenResponseVector);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ffa4  mov     [rsp-18h+arg_0], rbx
0x18001ffa9  push    rbp
0x18001ffaa  push    rsi
0x18001ffab  push    rdi
0x18001ffac  mov     rbp, rsp
0x18001ffaf  sub     rsp, 40h
0x18001ffb3  mov     rax, [pTokenResult]
0x18001ffb6  mov     rsi, pWebAuthRequest
0x18001ffb9  lea     pWebAuthRequest, [rbp+tokenResponseVector]; this
0x18001ffbd  mov     [rbp+tokenResponseVector.ptr_], 0
0x18001ffc5  mov     rdi, pTokenResult
0x18001ffc8  mov     [rbp+tokenResponse.ptr_], 0
0x18001ffd0  mov     [rbp+strToken.hstr_], 0
0x18001ffd8  mov     rbx, [rax+30h]
0x18001ffdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ffe1  lea     pTokenResult, [rbp+tokenResponseVector]
0x18001ffe5  mov     pWebAuthRequest, rdi
0x18001ffe8  mov     rax, rbx
0x18001ffeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fff0  mov     ebx, eax
0x18001fff2  test    eax, eax
0x18001fff4  js      loc_180020083
0x18001fffa  mov     rdi, [rbp+tokenResponseVector.ptr_]
0x18001fffe  lea     pWebAuthRequest, [rbp+tokenResponse]; this
0x180020002  mov     rax, [rdi]
0x180020005  mov     rbx, [rax+30h]
0x180020009  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002000e  lea     r8, [rbp+tokenResponse]
0x180020012  xor     edx, edx
0x180020014  mov     pWebAuthRequest, rdi
0x180020017  mov     rax, rbx
0x18002001a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002001f  mov     ebx, eax
0x180020021  test    eax, eax
0x180020023  js      short loc_180020083
0x180020025  mov     rdi, [rbp+tokenResponse.ptr_]
0x180020029  mov     pWebAuthRequest, [rbp+strToken.hstr_]; string
0x18002002d  mov     rax, [rdi]
0x180020030  mov     rbx, [rax+30h]
0x180020034  call    cs:__imp_WindowsDeleteString
0x18002003a  lea     pTokenResult, [rbp+strToken]
0x18002003e  mov     [rbp+strToken.hstr_], 0
0x180020046  mov     pWebAuthRequest, rdi
0x180020049  mov     rax, rbx
0x18002004c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020051  mov     ebx, eax
0x180020053  test    eax, eax
0x180020055  js      short loc_180020083
0x180020057  mov     rax, [rbp+strToken.hstr_]
0x18002005b  lea     pWebAuthRequest, [rsi+0D8h]; this
0x180020062  lea     pTokenResult, [rbp+other]; other
0x180020066  mov     [rbp+other], rax
0x18002006a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18002006f  mov     ebx, eax
0x180020071  test    eax, eax
0x180020073  js      short loc_180020083
0x180020075  mov     dword ptr [rsi+0E4h], 0
0x18002007f  xor     ebx, ebx
0x180020081  jmp     short loc_1800200A6
0x180020083  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x180020089  cmp     eax, 2
0x18002008c  jbe     short loc_1800200A6
0x18002008e  lea     rax, [rbp+other]; __annotation("_TlgWrite:|480|g_hMyWABTraceLoggingProvider|"Handling provider response data failed."=|"hr"=")
0x180020092  mov     dword ptr [rbp+other], ebx
0x180020095  lea     pTokenResult, _tlgEvent_9._tlgChannel; <wrappedArgs_0>
0x18002009c  mov     [rsp+40h+var_20], rax; <writerArgs_0>
0x1800200a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800200a6  mov     pWebAuthRequest, [rbp+strToken.hstr_]; string
0x1800200aa  call    cs:__imp_WindowsDeleteString
0x1800200b0  lea     pWebAuthRequest, [rbp+tokenResponse]; this
0x1800200b4  mov     [rbp+strToken.hstr_], 0
0x1800200bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200c1  lea     pWebAuthRequest, [rbp+tokenResponseVector]; this
0x1800200c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800200ca  mov     eax, ebx
0x1800200cc  mov     rbx, [rsp+40h+arg_0]
0x1800200d1  add     rsp, 40h
0x1800200d5  pop     rdi
0x1800200d6  pop     rsi
0x1800200d7  pop     rbp
0x1800200d8  retn
```
