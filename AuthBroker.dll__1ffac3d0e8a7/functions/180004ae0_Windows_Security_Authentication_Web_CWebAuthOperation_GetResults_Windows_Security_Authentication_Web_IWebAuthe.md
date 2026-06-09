# Windows::Security::Authentication::Web::CWebAuthOperation::GetResults(Windows::Security::Authentication::Web::IWebAuthenticationResult * *)

- ea: `0x180004ae0`
- end: `0x180004cf6`
- name: `?GetResults@CWebAuthOperation@Web@Authentication@Security@Windows@@UEAAJPEAPEAUIWebAuthenticationResult@2345@@Z`
- size: `534`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, Windows::Security::Authentication::Web::IWebAuthenticationResult **ppResult)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004ae0`
- `0x180006060`
- `0x180006360`
- `0x180006f74`
- `0x180008068`
- `0x180012b88`
- `0x18001595c`
- `0x1800159a8`
- `0x180016d68`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004b48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004b48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004b2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004b2e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004b55`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004be8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004c99`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004b55`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004be8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004c99`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::GetResults(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        Windows::Security::Authentication::Web::IWebAuthenticationResult **ppResult)
{
  int m_ResponseHr; // ebx
  HSTRING__ *hstring; // rdx
  HSTRING__ **v7; // rax
  Windows::Security::Authentication::Web::CWebAuthResult *ptr; // rbx
  Windows::Security::Authentication::Web::CWebAuthResult *v9; // rax
  const wchar_t *v10; // rdx
  Windows::Security::Authentication::Web::CWebAuthResult *v11; // rax
  _QWORD *v12; // rax
  int v13; // edi
  Windows::Security::Authentication::Web::IWebAuthenticationResult *v14; // rcx
  const wchar_t *v15; // rdx
  _QWORD *v16; // rax
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::IWebAuthenticationResult> spIResult; // [rsp+20h] [rbp-58h] BYREF
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::CWebAuthResult> v18; // [rsp+28h] [rbp-50h] BYREF
  Windows::Internal::StringReference string; // [rsp+30h] [rbp-48h] BYREF

  spIResult.ptr_ = 0;
  m_ResponseHr = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForResultsCall(&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >);
  if ( m_ResponseHr < 0 )
  {
    if ( WindowsCreateStringReference(L"Invalid state for GetResults", 0x1Cu, &string._header, &string._hstring) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    hstring = string._hstring;
    goto LABEL_5;
  }
  m_ResponseHr = this->m_ResponseHr;
  if ( m_ResponseHr < 0 )
  {
    Windows::Internal::StringReference::StringReference(&string, (const wchar_t (*)[22])L"Authentication failed");
    hstring = *v7;
LABEL_5:
    RoOriginateError((unsigned int)m_ResponseHr, hstring);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spIResult);
    return (unsigned int)m_ResponseHr;
  }
  ptr = 0;
  v18.ptr_ = 0;
  v9 = (Windows::Security::Authentication::Web::CWebAuthResult *)operator new(0x38u, &std::nothrow);
  if ( v9 )
  {
    Windows::Security::Authentication::Web::CWebAuthResult::CWebAuthResult(
      v9,
      this->m_ResponseStatus,
      this->m_ResponseErrorDetail);
    Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::CWebAuthResult>::Attach(&v18, v11);
    ptr = v18.ptr_;
  }
  if ( ptr )
  {
    v13 = ptr->QueryInterface(ptr, &GUID_64002b4b_ede9_470a_a5cd_0323faf6e262, (void **)&spIResult.ptr_);
    if ( v13 >= 0 )
    {
      v13 = Windows::Internal::String::Initialize(&ptr->m_data, &this->m_ResponseData._hstring);
      if ( v13 >= 0 )
      {
        *ppResult = spIResult.ptr_;
        spIResult.ptr_ = 0;
      }
      else
      {
        Windows::Internal::StringReference::StringReference(&string, (const wchar_t (*)[26])v15);
        RoOriginateError((unsigned int)v13, *v16);
      }
      ptr->Release(ptr);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spIResult);
    }
    else
    {
      ptr->Release(ptr);
      v14 = spIResult.ptr_;
      if ( spIResult.ptr_ )
      {
        spIResult.ptr_ = 0;
        v14->Release(v14);
      }
    }
    return (unsigned int)v13;
  }
  else
  {
    Windows::Internal::StringReference::StringReference(&string, (const wchar_t (*)[26])v10);
    RoOriginateError(2147942414LL, *v12);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spIResult);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180004ae0  mov     [rsp+arg_18], rbx
0x180004ae5  push    rbp
0x180004ae6  push    rsi
0x180004ae7  push    r14
0x180004ae9  sub     rsp, 60h
0x180004aed  mov     rax, cs:__security_cookie
0x180004af4  xor     rax, rsp
0x180004af7  mov     [rsp+78h+var_28], rax
0x180004afc  mov     rsi, this
0x180004aff  xor     ebp, ebp
0x180004b01  add     this, 10h; this
0x180004b05  mov     [rsp+78h+spIResult.ptr_], rbp
0x180004b0a  mov     r14, ppResult
0x180004b0d  call    ?CheckValidStateForResultsCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForResultsCall(void)
0x180004b12  mov     ebx, eax
0x180004b14  test    eax, eax
0x180004b16  jns     short loc_180004B6C
0x180004b18  lea     r9, [rsp+78h+string]; string
0x180004b1d  mov     edx, 1Ch; length
0x180004b22  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x180004b27  lea     this, aInvalidStateFo; "Invalid state for GetResults"
0x180004b2e  call    cs:__imp_WindowsCreateStringReference
0x180004b34  test    eax, eax
0x180004b36  jns     short loc_180004B4E
0x180004b38  xor     r9d, r9d; lpArguments
0x180004b3b  xor     r8d, r8d; nNumberOfArguments
0x180004b3e  mov     edx, 1; dwExceptionFlags
0x180004b43  mov     ecx, 0C000000Dh; dwExceptionCode
0x180004b48  call    cs:__imp_RaiseException
0x180004b4e  mov     ppResult, [rsp+78h+string]
0x180004b53  mov     ecx, ebx
0x180004b55  call    cs:__imp_RoOriginateError
0x180004b5b  lea     this, [rsp+78h+spIResult]; this
0x180004b60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004b65  mov     eax, ebx
0x180004b67  jmp     loc_180004CD8
0x180004b6c  mov     ebx, [rsi+0E0h]
0x180004b72  test    ebx, ebx
0x180004b74  jns     short loc_180004B8C
0x180004b76  lea     ppResult, stringRef; "Authentication failed"
0x180004b7d  lea     this, [rsp+78h+string]; this
0x180004b82  call    ??$?0$0BG@@StringReference@Internal@Windows@@QEAA@AEAY0BG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[22])
0x180004b87  mov     ppResult, [rax]
0x180004b8a  jmp     short loc_180004B53
0x180004b8c  mov     rbx, rbp
0x180004b8f  lea     ppResult, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x180004b96  mov     ecx, 38h ; '8'; count
0x180004b9b  mov     [rsp+78h+var_50.ptr_], rbx
0x180004ba0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004ba5  test    rax, rax
0x180004ba8  jz      short loc_180004BD1
0x180004baa  mov     r8d, [rsi+0E8h]; errorDetail
0x180004bb1  mov     this, rax; this
0x180004bb4  mov     edx, [rsi+0E4h]; status
0x180004bba  call    ??0CWebAuthResult@Web@Authentication@Security@Windows@@QEAA@W4WebAuthenticationStatus@1234@I@Z; Windows::Security::Authentication::Web::CWebAuthResult::CWebAuthResult(Windows::Security::Authentication::Web::WebAuthenticationStatus,uint)
0x180004bbf  mov     ppResult, rax; other
0x180004bc2  lea     this, [rsp+78h+var_50]; this
0x180004bc7  call    ?Attach@?$ComPtr@VCWebAuthResult@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEAAXPEAVCWebAuthResult@Web@Authentication@Security@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::CWebAuthResult>::Attach(Windows::Security::Authentication::Web::CWebAuthResult *)
0x180004bcc  mov     rbx, [rsp+78h+var_50.ptr_]
0x180004bd1  test    rbx, rbx
0x180004bd4  jnz     short loc_180004C02
0x180004bd6  lea     this, [rsp+78h+string]; this
0x180004bdb  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x180004be0  mov     ecx, 8007000Eh
0x180004be5  mov     ppResult, [rax]
0x180004be8  call    cs:__imp_RoOriginateError
0x180004bee  lea     this, [rsp+78h+spIResult]; this
0x180004bf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004bf8  mov     eax, 8007000Eh
0x180004bfd  jmp     loc_180004CD8
0x180004c02  mov     rax, [rbx]
0x180004c05  mov     this, [rsp+78h+spIResult.ptr_]
0x180004c0a  mov     [rsp+78h+arg_10], rdi
0x180004c12  mov     rdi, [rax]
0x180004c15  test    this, this
0x180004c18  jz      short loc_180004C2B
0x180004c1a  mov     [rsp+78h+spIResult.ptr_], rbp
0x180004c1f  mov     ppResult, [this]
0x180004c22  mov     rax, [ppResult+10h]
0x180004c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2b  lea     r8, [rsp+78h+spIResult]
0x180004c30  mov     this, rbx
0x180004c33  lea     ppResult, _GUID_64002b4b_ede9_470a_a5cd_0323faf6e262
0x180004c3a  mov     rax, rdi
0x180004c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c42  mov     edi, eax
0x180004c44  test    eax, eax
0x180004c46  jns     short loc_180004C74
0x180004c48  mov     this, [rbx]
0x180004c4b  mov     rax, [this+10h]
0x180004c4f  mov     this, rbx
0x180004c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c57  mov     this, [rsp+78h+spIResult.ptr_]
0x180004c5c  test    this, this
0x180004c5f  jz      short loc_180004CCE
0x180004c61  mov     [rsp+78h+spIResult.ptr_], rbp
0x180004c66  mov     rax, [this]
0x180004c69  mov     rax, [rax+10h]
0x180004c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c72  jmp     short loc_180004CCE
0x180004c74  lea     ppResult, [rsi+0D8h]; other
0x180004c7b  lea     this, [rbx+28h]; this
0x180004c7f  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180004c84  mov     edi, eax
0x180004c86  test    eax, eax
0x180004c88  jns     short loc_180004CA8
0x180004c8a  lea     this, [rsp+78h+string]; this
0x180004c8f  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x180004c94  mov     ecx, edi
0x180004c96  mov     ppResult, [rax]
0x180004c99  call    cs:__imp_RoOriginateError
0x180004c9f  mov     this, [rbx]
0x180004ca2  mov     rax, [this+10h]
0x180004ca6  jmp     short loc_180004CBC
0x180004ca8  mov     rax, [rsp+78h+spIResult.ptr_]
0x180004cad  mov     [r14], rax
0x180004cb0  mov     [rsp+78h+spIResult.ptr_], rbp
0x180004cb5  mov     rax, [rbx]
0x180004cb8  mov     rax, [rax+10h]
0x180004cbc  mov     this, rbx
0x180004cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc4  lea     this, [rsp+78h+spIResult]; this
0x180004cc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004cce  mov     eax, edi
0x180004cd0  mov     rdi, [rsp+78h+arg_10]
0x180004cd8  mov     this, [rsp+78h+var_28]
0x180004cdd  xor     this, rsp; StackCookie
0x180004ce0  call    __security_check_cookie
0x180004ce5  mov     rbx, [rsp+78h+arg_18]
0x180004ced  add     rsp, 60h
0x180004cf1  pop     r14
0x180004cf3  pop     rsi
0x180004cf4  pop     rbp
0x180004cf5  retn
```
