# Windows::Security::Authentication::Web::Core::CWebTokenRequestResult::InvalidateCacheAsync(Windows::Foundation::IAsyncAction * *)

- ea: `0x1800f9760`
- end: `0x1800f9c0d`
- name: `?InvalidateCacheAsync@CWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@UEAAJPEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1197`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::Core::CWebTokenRequestResult *__hidden this, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000ee40`
- `0x180010a70`
- `0x180024000`
- `0x180024118`
- `0x180056174`
- `0x18008e690`
- `0x1800afb68`
- `0x1800f0ad4`
- `0x1800f3cc8`
- `0x1800f42d0`
- `0x1800f498c`
- `0x1800f4be8`
- `0x1800f580c`
- `0x1800f60e8`
- `0x1800f9760`
- `0x1800fc0f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f98ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f990e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f98ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f990e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f9bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f992a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f992a`

## string_xrefs

- `0x1800f97d1`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f981a`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f987c`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f98d6`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f9941`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f99f2`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f9b04`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800f9788`: `WebTokenRequestResultInvalidateCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenRequestResult::InvalidateCacheAsync(
        HSTRING *this,
        struct Windows::Foundation::IAsyncAction **a2)
{
  bool *v4; // r8
  int IsCallingProcessAppContainer; // eax
  void *v7; // r9
  unsigned int v8; // edi
  int CallingAppPackageFamilyName; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  HRESULT v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r8d
  int v20; // r9d
  int v21; // ebx
  int v22; // [rsp+20h] [rbp-398h]
  int v23; // [rsp+20h] [rbp-398h]
  struct IUnknown v24; // [rsp+40h] [rbp-378h] BYREF
  HSTRING string; // [rsp+48h] [rbp-370h] BYREF
  __int16 v26; // [rsp+50h] [rbp-368h]
  HSTRING v27; // [rsp+58h] [rbp-360h] BYREF
  HSTRING *v28; // [rsp+60h] [rbp-358h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-350h] BYREF
  HSTRING newString; // [rsp+70h] [rbp-348h] BYREF
  __int16 v31; // [rsp+78h] [rbp-340h]
  _BYTE v32[12]; // [rsp+80h] [rbp-338h] BYREF
  void *TokenHandle[2]; // [rsp+90h] [rbp-328h] BYREF
  _QWORD v34[42]; // [rsp+A0h] [rbp-318h] BYREF
  _BYTE v35[416]; // [rsp+1F0h] [rbp-1C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v34);
  v34[0] = &WamClientLogProvider::WebTokenRequestResultInvalidateCache::`vftable';
  WamClientLogProvider::WebTokenRequestResultInvalidateCache::StartActivity((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x690,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)0x80070057LL,
      v22);
    WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
    return 2147942487LL;
  }
  LOBYTE(v24.lpVtbl) = 1;
  IsCallingProcessAppContainer = Windows::Internal::Security::Authentication::TokenBroker::IsCallingProcessAppContainer(
                                   (Windows::Internal::Security::Authentication::TokenBroker *)this,
                                   &v24,
                                   v4);
  v8 = IsCallingProcessAppContainer;
  if ( IsCallingProcessAppContainer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x693,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)IsCallingProcessAppContainer,
      v22);
    WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
    return v8;
  }
  string = 0;
  v26 = 0;
  if ( LOBYTE(v24.lpVtbl) )
  {
    v27 = 0;
    CallingAppPackageFamilyName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(
                                    (Windows::Internal::Security::Authentication::TokenBroker *)this,
                                    (struct IUnknown *)&v27,
                                    0,
                                    v7);
    v10 = CallingAppPackageFamilyName;
    if ( CallingAppPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x699,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)CallingAppPackageFamilyName,
        v22);
      WindowsDeleteString(string);
      string = 0;
      WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
      return v10;
    }
    v11 = Microsoft::WRL::Wrappers::HString::Set(&string, &v27);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v11,
        v22);
      WindowsDeleteString(string);
      string = 0;
      WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
      return v12;
    }
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    v13 = WindowsCreateString(L"NO_APPLICATION", 0xEu, &string);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v13,
        v22);
      WindowsDeleteString(string);
      string = 0;
      WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
      return v14;
    }
  }
  v27 = this[20];
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v27);
  v29 = this[16];
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v29);
  v28 = this;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v28);
  newString = 0;
  v31 = 0;
  *(_QWORD *)v32 = this[18];
  v15 = Microsoft::WRL::Wrappers::HString::Set(&newString, (HSTRING *)v32);
  v16 = v15;
  if ( v15 >= 0 )
  {
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(TokenHandle);
    v17 = lambda_18715b9e1567a78c6f93fc4fc2e75538_::_lambda_18715b9e1567a78c6f93fc4fc2e75538__0(
            (unsigned int)v35,
            (unsigned int)v34,
            (unsigned int)&string,
            (unsigned int)&v29,
            (__int64)&newString,
            (__int64)TokenHandle,
            (__int64)&v27,
            (__int64)&v28);
    *(_DWORD *)v32 = 3;
    *(_QWORD *)&v32[4] = 128;
    v18 = Windows::Internal::MakeOpLambda_0_Windows::Internal::CNoResult__lambda_18715b9e1567a78c6f93fc4fc2e75538___(v17);
    v21 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Security::Authentication::Web::InvalidateCachedEntryAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
            (_DWORD)a2,
            (unsigned int)v32,
            v19,
            v20,
            v18);
    lambda_18715b9e1567a78c6f93fc4fc2e75538_::__lambda_18715b9e1567a78c6f93fc4fc2e75538_((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v35);
    if ( v21 >= 0 )
    {
      wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v34);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)TokenHandle);
      WindowsDeleteString(newString);
      newString = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      WindowsDeleteString(string);
      string = 0;
      WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v21,
        v23);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)TokenHandle);
      WindowsDeleteString(newString);
      newString = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      WindowsDeleteString(string);
      string = 0;
      WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
      return (unsigned int)v21;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)v15,
      v22);
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    WindowsDeleteString(string);
    string = 0;
    WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache((WamClientLogProvider::WebTokenRequestResultInvalidateCache *)v34);
    return v16;
  }
}

```

## disassembly

```asm
0x1800f9760  mov     [rsp+arg_10], rbx
0x1800f9765  push    rsi
0x1800f9766  push    rdi
0x1800f9767  push    r14
0x1800f9769  sub     rsp, 3A0h
0x1800f9770  mov     rax, cs:__security_cookie
0x1800f9777  xor     rax, rsp
0x1800f977a  mov     [rsp+3B8h+var_28], rax
0x1800f9782  mov     rsi, rdx
0x1800f9785  mov     rbx, rcx
0x1800f9788  lea     rdx, aWebtokenreques; "WebTokenRequestResultInvalidateCache"
0x1800f978f  lea     rcx, [rsp+3B8h+var_318]; struct wil::details::IFailureCallback *
0x1800f9797  call    ??0?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f979c  lea     rax, ??_7WebTokenRequestResultInvalidateCache@WamClientLogProvider@@6B@; const WamClientLogProvider::WebTokenRequestResultInvalidateCache::`vftable'
0x1800f97a3  mov     [rsp+3B8h+var_318], rax
0x1800f97ab  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f97b3  call    ?StartActivity@WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAAXXZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::StartActivity(void)
0x1800f97b8  nop
0x1800f97b9  xor     r14d, r14d
0x1800f97bc  test    rsi, rsi
0x1800f97bf  jnz     short loc_1800F97F7
0x1800f97c1  mov     rcx, [rsp+3B8h]; this
0x1800f97c9  mov     ebx, 80070057h
0x1800f97ce  mov     r9d, ebx; char *
0x1800f97d1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f97d8  mov     edx, 690h; void *
0x1800f97dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f97e2  nop
0x1800f97e3  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f97eb  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f97f0  mov     eax, ebx
0x1800f97f2  jmp     loc_1800F9BE8
0x1800f97f7  mov     byte ptr [rsp+3B8h+var_378.lpVtbl], 1
0x1800f97fc  lea     rdx, [rsp+3B8h+var_378]; struct IUnknown *
0x1800f9801  mov     rcx, rbx; this
0x1800f9804  call    ?IsCallingProcessAppContainer@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::IsCallingProcessAppContainer(IUnknown *,bool *)
0x1800f9809  mov     edi, eax
0x1800f980b  test    eax, eax
0x1800f980d  jns     short loc_1800F9840
0x1800f980f  mov     rcx, [rsp+3B8h]; this
0x1800f9817  mov     r9d, eax; char *
0x1800f981a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f9821  mov     edx, 693h; void *
0x1800f9826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f982b  nop
0x1800f982c  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f9834  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9839  mov     eax, edi
0x1800f983b  jmp     loc_1800F9BE8
0x1800f9840  mov     [rsp+3B8h+string], r14
0x1800f9845  mov     [rsp+3B8h+var_368], r14w
0x1800f984b  cmp     byte ptr [rsp+3B8h+var_378.lpVtbl], r14b
0x1800f9850  jz      loc_1800F990C
0x1800f9856  mov     [rsp+3B8h+var_360], r14
0x1800f985b  xor     r8d, r8d; HSTRING *
0x1800f985e  lea     rdx, [rsp+3B8h+var_360]; struct IUnknown *
0x1800f9863  mov     rcx, rbx; this
0x1800f9866  call    ?GetCallingAppPackageFamilyName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@PEAX@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(IUnknown *,HSTRING__ * *,void *)
0x1800f986b  mov     edi, eax
0x1800f986d  test    eax, eax
0x1800f986f  jns     short loc_1800F98B2
0x1800f9871  mov     rcx, [rsp+3B8h]; this
0x1800f9879  mov     r9d, eax; char *
0x1800f987c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f9883  mov     edx, 699h; void *
0x1800f9888  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f988d  nop
0x1800f988e  mov     rcx, [rsp+3B8h+string]; string
0x1800f9893  call    cs:__imp_WindowsDeleteString
0x1800f9899  mov     [rsp+3B8h+string], r14
0x1800f989e  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f98a6  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f98ab  mov     eax, edi
0x1800f98ad  jmp     loc_1800F9BE8
0x1800f98b2  lea     rdx, [rsp+3B8h+var_360]; HSTRING *
0x1800f98b7  lea     rcx, [rsp+3B8h+string]; newString
0x1800f98bc  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800f98c1  mov     edi, eax
0x1800f98c3  test    eax, eax
0x1800f98c5  jns     loc_1800F9977
0x1800f98cb  mov     rcx, [rsp+3B8h]; this
0x1800f98d3  mov     r9d, eax; char *
0x1800f98d6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f98dd  mov     edx, 69Ah; void *
0x1800f98e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f98e7  nop
0x1800f98e8  mov     rcx, [rsp+3B8h+string]; string
0x1800f98ed  call    cs:__imp_WindowsDeleteString
0x1800f98f3  mov     [rsp+3B8h+string], r14
0x1800f98f8  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f9900  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9905  mov     eax, edi
0x1800f9907  jmp     loc_1800F9BE8
0x1800f990c  xor     ecx, ecx; string
0x1800f990e  call    cs:__imp_WindowsDeleteString
0x1800f9914  mov     [rsp+3B8h+string], r14
0x1800f9919  lea     r8, [rsp+3B8h+string]; string
0x1800f991e  mov     edx, 0Eh; length
0x1800f9923  lea     rcx, aNoApplication; "NO_APPLICATION"
0x1800f992a  call    cs:__imp_WindowsCreateString
0x1800f9930  mov     edi, eax
0x1800f9932  test    eax, eax
0x1800f9934  jns     short loc_1800F9977
0x1800f9936  mov     rcx, [rsp+3B8h]; this
0x1800f993e  mov     r9d, eax; char *
0x1800f9941  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f9948  mov     edx, 69Eh; void *
0x1800f994d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9952  nop
0x1800f9953  mov     rcx, [rsp+3B8h+string]; string
0x1800f9958  call    cs:__imp_WindowsDeleteString
0x1800f995e  mov     [rsp+3B8h+string], r14
0x1800f9963  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f996b  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9970  mov     eax, edi
0x1800f9972  jmp     loc_1800F9BE8
0x1800f9977  mov     rax, [rbx+0A0h]
0x1800f997e  mov     [rsp+3B8h+var_360], rax
0x1800f9983  lea     rcx, [rsp+3B8h+var_360]
0x1800f9988  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f998d  nop
0x1800f998e  mov     rax, [rbx+80h]
0x1800f9995  mov     [rsp+3B8h+var_350], rax
0x1800f999a  lea     rcx, [rsp+3B8h+var_350]
0x1800f999f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f99a4  nop
0x1800f99a5  mov     [rsp+3B8h+var_358], rbx
0x1800f99aa  lea     rcx, [rsp+3B8h+var_358]
0x1800f99af  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f99b4  nop
0x1800f99b5  mov     [rsp+3B8h+newString], r14
0x1800f99ba  mov     [rsp+3B8h+var_340], r14w
0x1800f99c0  mov     rax, [rbx+90h]
0x1800f99c7  mov     [rsp+3B8h+var_338], rax
0x1800f99cf  lea     rdx, [rsp+3B8h+var_338]; HSTRING *
0x1800f99d7  lea     rcx, [rsp+3B8h+newString]; newString
0x1800f99dc  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800f99e1  mov     ebx, eax
0x1800f99e3  test    eax, eax
0x1800f99e5  jns     short loc_1800F9A59
0x1800f99e7  mov     rcx, [rsp+3B8h]; this
0x1800f99ef  mov     r9d, eax; char *
0x1800f99f2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f99f9  mov     edx, 6A5h; void *
0x1800f99fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9a03  nop
0x1800f9a04  mov     rcx, [rsp+3B8h+newString]; string
0x1800f9a09  call    cs:__imp_WindowsDeleteString
0x1800f9a0f  mov     [rsp+3B8h+newString], r14
0x1800f9a14  lea     rcx, [rsp+3B8h+var_358]
0x1800f9a19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9a1e  nop
0x1800f9a1f  lea     rcx, [rsp+3B8h+var_350]
0x1800f9a24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9a29  nop
0x1800f9a2a  lea     rcx, [rsp+3B8h+var_360]
0x1800f9a2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9a34  nop
0x1800f9a35  mov     rcx, [rsp+3B8h+string]; string
0x1800f9a3a  call    cs:__imp_WindowsDeleteString
0x1800f9a40  mov     [rsp+3B8h+string], r14
0x1800f9a45  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f9a4d  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9a52  mov     eax, ebx
0x1800f9a54  jmp     loc_1800F9BE8
0x1800f9a59  lea     rcx, [rsp+3B8h+TokenHandle]; TokenHandle
0x1800f9a61  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x1800f9a66  nop
0x1800f9a67  lea     rax, [rsp+3B8h+var_358]
0x1800f9a6c  mov     [rsp+3B8h+var_380], rax
0x1800f9a71  lea     rax, [rsp+3B8h+var_360]
0x1800f9a76  mov     [rsp+3B8h+var_388], rax
0x1800f9a7b  lea     rax, [rsp+3B8h+TokenHandle]
0x1800f9a83  mov     [rsp+3B8h+var_390], rax
0x1800f9a88  lea     rax, [rsp+3B8h+newString]
0x1800f9a8d  mov     qword ptr [rsp+3B8h+var_398], rax
0x1800f9a92  lea     r9, [rsp+3B8h+var_350]
0x1800f9a97  lea     r8, [rsp+3B8h+string]
0x1800f9a9c  lea     rdx, [rsp+3B8h+var_318]
0x1800f9aa4  lea     rcx, [rsp+3B8h+var_1C8]
0x1800f9aac  call    _lambda_18715b9e1567a78c6f93fc4fc2e75538____lambda_18715b9e1567a78c6f93fc4fc2e75538__0
0x1800f9ab1  nop
0x1800f9ab2  mov     dword ptr [rsp+3B8h+var_338], 3
0x1800f9abd  mov     [rsp+3B8h+var_338+4], 80h
0x1800f9ac9  mov     rcx, rax
0x1800f9acc  call    Windows__Internal__MakeOpLambda_0_Windows__Internal__CNoResult__lambda_18715b9e1567a78c6f93fc4fc2e75538___
0x1800f9ad1  mov     qword ptr [rsp+3B8h+var_398], rax; int
0x1800f9ad6  lea     rdx, [rsp+3B8h+var_338]
0x1800f9ade  mov     rcx, rsi
0x1800f9ae1  call    ??$MakeAsyncHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UINilDelegate@Internal@3@VCNoResult@63@VComTaskPoolHandler@63@U?$AsyncCausalityOptions@$1?InvalidateCachedEntryAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAUIAsyncAction@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Security::Authentication::Web::InvalidateCachedEntryAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncAction * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x1800f9ae6  mov     ebx, eax
0x1800f9ae8  lea     rcx, [rsp+3B8h+var_1C8]; this
0x1800f9af0  call    _lambda_18715b9e1567a78c6f93fc4fc2e75538_____lambda_18715b9e1567a78c6f93fc4fc2e75538_
0x1800f9af5  test    ebx, ebx
0x1800f9af7  jns     short loc_1800F9B76
0x1800f9af9  mov     rcx, [rsp+3B8h]; this
0x1800f9b01  mov     r9d, ebx; char *
0x1800f9b04  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f9b0b  mov     edx, 6D0h; void *
0x1800f9b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9b15  nop
0x1800f9b16  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x1800f9b1e  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f9b23  nop
0x1800f9b24  mov     rcx, [rsp+3B8h+newString]; string
0x1800f9b29  call    cs:__imp_WindowsDeleteString
0x1800f9b2f  mov     [rsp+3B8h+newString], r14
0x1800f9b34  lea     rcx, [rsp+3B8h+var_358]
0x1800f9b39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9b3e  nop
0x1800f9b3f  lea     rcx, [rsp+3B8h+var_350]
0x1800f9b44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9b49  nop
0x1800f9b4a  lea     rcx, [rsp+3B8h+var_360]
0x1800f9b4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9b54  nop
0x1800f9b55  mov     rcx, [rsp+3B8h+string]; string
0x1800f9b5a  call    cs:__imp_WindowsDeleteString
0x1800f9b60  mov     [rsp+3B8h+string], r14
0x1800f9b65  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f9b6d  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9b72  mov     eax, ebx
0x1800f9b74  jmp     short loc_1800F9BE8
0x1800f9b76  lea     rcx, [rsp+3B8h+var_318]
0x1800f9b7e  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800f9b83  nop
0x1800f9b84  lea     rcx, [rsp+3B8h+TokenHandle]; this
0x1800f9b8c  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f9b91  nop
0x1800f9b92  mov     rcx, [rsp+3B8h+newString]; string
0x1800f9b97  call    cs:__imp_WindowsDeleteString
0x1800f9b9d  mov     [rsp+3B8h+newString], r14
0x1800f9ba2  lea     rcx, [rsp+3B8h+var_358]
0x1800f9ba7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9bac  nop
0x1800f9bad  lea     rcx, [rsp+3B8h+var_350]
0x1800f9bb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9bb7  nop
0x1800f9bb8  lea     rcx, [rsp+3B8h+var_360]
0x1800f9bbd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f9bc2  nop
0x1800f9bc3  mov     rcx, [rsp+3B8h+string]; string
0x1800f9bc8  call    cs:__imp_WindowsDeleteString
0x1800f9bce  mov     [rsp+3B8h+string], r14
0x1800f9bd3  lea     rcx, [rsp+3B8h+var_318]; this
0x1800f9bdb  call    ??1WebTokenRequestResultInvalidateCache@WamClientLogProvider@@QEAA@XZ; WamClientLogProvider::WebTokenRequestResultInvalidateCache::~WebTokenRequestResultInvalidateCache(void)
0x1800f9be0  xor     eax, eax
0x1800f9be2  jmp     short loc_1800F9BE8
0x1800f9be4  mov     eax, dword ptr [rsp+3B8h+var_358]
0x1800f9be8  mov     rcx, [rsp+3B8h+var_28]
0x1800f9bf0  xor     rcx, rsp; StackCookie
0x1800f9bf3  call    __security_check_cookie
0x1800f9bf8  mov     rbx, [rsp+3B8h+arg_10]
0x1800f9c00  add     rsp, 3A0h
0x1800f9c07  pop     r14
0x1800f9c09  pop     rdi
0x1800f9c0a  pop     rsi
0x1800f9c0b  retn
```
