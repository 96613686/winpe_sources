# CLocationUserInfoHelper::HasFlightingAccount(bool)

- ea: `0x1800116f0`
- end: `0x180011bb1`
- name: `?HasFlightingAccount@CLocationUserInfoHelper@@UEAAJ_N@Z`
- size: `1217`
- prototype: `__int64 __fastcall(CLocationUserInfoHelper *__hidden this, bool)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800116f0`
- `0x180011fa0`
- `0x1800122a8`
- `0x180012310`
- `0x1800142c4`
- `0x180014340`
- `0x18001e170`
- `0x18005c478`
- `0x180098a2c`
- `0x1800a98c0`
- `0x1800c4058`
- `0x1800c420c`
- `0x1800c5180`
- `0x1800c51d0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011792`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011792`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011813`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001177e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001177e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001187b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001187b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800117b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800117b5`

## string_xrefs

- `0x180011777`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800118db`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CLocationUserInfoHelper::HasFlightingAccount(CLocationUserInfoHelper *this, bool a2)
{
  HRESULT active; // ebx
  HRESULT v3; // eax
  HSTRING v4; // rbx
  void *v5; // rdx
  __int64 v6; // rcx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, PCNZWCH *); // rbx
  HSTRING *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING, __int64 *); // rdi
  HSTRING v13; // rbx
  __int64 v14; // rdi
  void *v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  void *v20; // rdx
  void *v21; // rdx
  void *v23; // rdx
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  PCNZWCH v25; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v28; // [rsp+68h] [rbp-98h]
  HSTRING_HEADER v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  PCNZWCH sourceString; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h] BYREF
  void **v39; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E8h] [rbp-18h]

  v39 = &ATL::CAccessToken::`vftable';
  v40 = 0;
  v41 = 0;
  v24 = 0;
  active = CLocationUserInfoHelper::ImpersonateActiveUser(this, a2, (struct ATL::CAccessToken *)&v39);
  if ( active < 0 )
    goto LABEL_29;
  string[1] = (HSTRING)&v39;
  v28 = 1;
  v31 = 0;
  string[0] = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = string[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  active = RoGetActivationFactory(v4, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v31);
  if ( active < 0 )
  {
    v6 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v39, v5);
    goto LABEL_29;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  active = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
  if ( active < 0 )
    goto LABEL_28;
  sourceString = 0;
  v7 = ppv;
  v8 = *(__int64 (__fastcall **)(LPVOID, PCNZWCH *))(*(_QWORD *)ppv + 176LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &sourceString,
    0);
  active = v8(v7, &sourceString);
  if ( active < 0 )
  {
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v39, v23);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    goto LABEL_29;
  }
  v36 = 0;
  v9 = (HSTRING *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&v36);
  v10 = -1;
  do
    ++v10;
  while ( sourceString[v10] );
  active = WindowsCreateString(sourceString, v10, v9);
  if ( active < 0 )
  {
LABEL_26:
    Windows::Internal::String::~String((Windows::Internal::String *)&v36);
    goto LABEL_27;
  }
  v34 = 0;
  v35 = 0;
  v11 = v31;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v31 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  string[0] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"consumers", 0xAu, 9u);
  v13 = string[0];
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, L"https://login.microsoft.com", 0x1Cu, 0x1Bu);
  active = v12(v11, v30, v13, &v35);
  if ( active < 0
    || (v14 = v35,
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34),
        active = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v14),
        active < 0)
    || (active = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 64LL))(v14, &v34), active < 0) )
  {
LABEL_25:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    goto LABEL_26;
  }
  if ( !v34 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Windows::Internal::String::~String((Windows::Internal::String *)&v36);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v39, v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    active = -2147023692;
    goto LABEL_29;
  }
  v38 = 0;
  v37 = 0;
  v16 = v31;
  v17 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v25 = sourceString;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v29, &v25);
  active = v17(v16, v34, *(_QWORD *)(v18 + 24), &v37);
  if ( active < 0
    || (v19 = v37,
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38),
        active = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(v19),
        active < 0)
    || (active = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 64LL))(v19, &v38), active < 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    goto LABEL_25;
  }
  if ( v38 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Windows::Internal::String::~String((Windows::Internal::String *)&v36);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v39, v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v39 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v39);
    return 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  ATL::CAccessToken::Revert((ATL::CAccessToken *)&v39, v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  active = -2147023579;
LABEL_29:
  v39 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v39);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x1800116f0  push    rbp
0x1800116f2  push    rbx
0x1800116f3  push    rsi
0x1800116f4  push    rdi
0x1800116f5  push    r14
0x1800116f7  push    r15
0x1800116f9  lea     rbp, [rsp-8]
0x1800116fe  sub     rsp, 108h
0x180011705  mov     rax, cs:__security_cookie
0x18001170c  xor     rax, rsp
0x18001170f  mov     [rbp+30h+var_40], rax
0x180011713  xorps   xmm0, xmm0
0x180011716  movups  [rbp+30h+var_60], xmm0
0x18001171a  movups  [rbp+30h+var_50], xmm0
0x18001171e  lea     r15, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180011725  mov     qword ptr [rbp+30h+var_60], r15
0x180011729  movdqu  [rbp+30h+var_60+8], xmm0
0x18001172e  xor     r14d, r14d
0x180011731  mov     qword ptr [rbp+30h+var_50+8], r14
0x180011735  mov     [rsp+130h+var_100], r14
0x18001173a  lea     r8, [rbp+30h+var_60]; struct ATL::CAccessToken *
0x18001173e  call    ?ImpersonateActiveUser@CLocationUserInfoHelper@@UEAAJ_NAEAVCAccessToken@ATL@@@Z; CLocationUserInfoHelper::ImpersonateActiveUser(bool,ATL::CAccessToken &)
0x180011743  mov     ebx, eax
0x180011745  test    eax, eax
0x180011747  jns     short loc_18001174E
0x180011749  jmp     loc_180011B86
0x18001174e  lea     rax, [rbp+30h+var_60]
0x180011752  mov     [rsp+130h+var_D0], rax
0x180011757  mov     edi, 1
0x18001175c  mov     [rsp+130h+var_C8], dil
0x180011761  mov     [rbp+30h+var_A0], r14
0x180011765  mov     [rsp+130h+string], r14
0x18001176a  lea     r9, [rsp+130h+string]; string
0x18001176f  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x180011774  lea     edx, [rdi+44h]; length
0x180011777  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18001177e  call    cs:__imp_WindowsCreateStringReference
0x180011784  test    eax, eax
0x180011786  jns     short loc_180011799
0x180011788  xor     r9d, r9d; lpArguments
0x18001178b  xor     r8d, r8d; nNumberOfArguments
0x18001178e  mov     edx, edi; dwExceptionFlags
0x180011790  mov     ecx, eax; dwExceptionCode
0x180011792  call    cs:__imp_RaiseException
0x180011798  int     3; Trap to Debugger
0x180011799  mov     rbx, [rsp+130h+string]
0x18001179e  lea     rcx, [rbp+30h+var_A0]
0x1800117a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800117a7  lea     r8, [rbp+30h+var_A0]
0x1800117ab  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800117b2  mov     rcx, rbx
0x1800117b5  call    cs:__imp_RoGetActivationFactory
0x1800117bb  mov     ebx, eax
0x1800117bd  test    eax, eax
0x1800117bf  jns     short loc_1800117EA
0x1800117c1  mov     rcx, [rbp+30h+var_A0]
0x1800117c5  test    rcx, rcx
0x1800117c8  jz      short loc_1800117DB
0x1800117ca  mov     [rbp+30h+var_A0], r14
0x1800117ce  mov     rdx, [rcx]
0x1800117d1  mov     rax, [rdx+10h]
0x1800117d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117da  nop
0x1800117db  lea     rcx, [rbp+30h+var_60]; this
0x1800117df  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x1800117e4  nop
0x1800117e5  jmp     loc_180011B86
0x1800117ea  mov     [rbp+30h+var_90], r14
0x1800117ee  lea     rcx, [rbp+30h+var_90]
0x1800117f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800117f7  lea     rax, [rbp+30h+var_90]
0x1800117fb  mov     [rsp+130h+ppv], rax; ppv
0x180011800  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180011807  mov     r8d, edi; dwClsContext
0x18001180a  xor     edx, edx; pUnkOuter
0x18001180c  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180011813  call    cs:__imp_CoCreateInstance
0x180011819  mov     ebx, eax
0x18001181b  test    eax, eax
0x18001181d  js      loc_180011B5D
0x180011823  mov     [rbp+30h+sourceString], r14
0x180011827  mov     rdi, [rbp+30h+var_90]
0x18001182b  mov     rax, [rdi]
0x18001182e  mov     rbx, [rax+0B0h]
0x180011835  xor     edx, edx
0x180011837  lea     rcx, [rbp+30h+sourceString]
0x18001183b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180011840  lea     rdx, [rbp+30h+sourceString]
0x180011844  mov     rcx, rdi
0x180011847  mov     rax, rbx
0x18001184a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001184f  mov     ebx, eax
0x180011851  test    eax, eax
0x180011853  js      loc_180011B53
0x180011859  mov     [rbp+30h+var_78], r14
0x18001185d  lea     rcx, [rbp+30h+var_78]
0x180011861  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x180011866  mov     rcx, [rbp+30h+sourceString]; sourceString
0x18001186a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001186e  inc     rdx; length
0x180011871  cmp     [rcx+rdx*2], r14w
0x180011876  jnz     short loc_18001186E
0x180011878  mov     r8, rax; string
0x18001187b  call    cs:__imp_WindowsCreateString
0x180011881  mov     ebx, eax
0x180011883  test    eax, eax
0x180011885  js      loc_180011B49
0x18001188b  mov     [rbp+30h+var_88], r14
0x18001188f  mov     [rbp+30h+var_80], r14
0x180011893  mov     rsi, [rbp+30h+var_A0]
0x180011897  mov     rax, [rsi]
0x18001189a  mov     rdi, [rax+60h]
0x18001189e  lea     rcx, [rbp+30h+var_80]
0x1800118a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800118a7  mov     [rsp+130h+string], r14
0x1800118ac  mov     r9d, 9; unsigned int
0x1800118b2  lea     r8d, [r9+1]; unsigned int
0x1800118b6  lea     rdx, sourceString; "consumers"
0x1800118bd  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x1800118c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800118c7  nop
0x1800118c8  mov     rbx, [rsp+130h+string]
0x1800118cd  mov     [rbp+30h+var_A8], r14
0x1800118d1  mov     r9d, 1Bh; unsigned int
0x1800118d7  lea     r8d, [r9+1]; unsigned int
0x1800118db  lea     rdx, aHttpsLoginMicr; "https://login.microsoft.com"
0x1800118e2  lea     rcx, [rsp+130h+var_C0]; hstringHeader
0x1800118e7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800118ec  nop
0x1800118ed  lea     r9, [rbp+30h+var_80]
0x1800118f1  mov     r8, rbx
0x1800118f4  mov     rdx, [rbp+30h+var_A8]
0x1800118f8  mov     rcx, rsi
0x1800118fb  mov     rax, rdi
0x1800118fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011903  mov     ebx, eax
0x180011905  test    eax, eax
0x180011907  js      loc_180011B35
0x18001190d  mov     rdi, [rbp+30h+var_80]
0x180011911  lea     rcx, [rbp+30h+var_88]
0x180011915  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001191a  mov     rcx, rdi
0x18001191d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180011922  mov     ebx, eax
0x180011924  test    eax, eax
0x180011926  js      loc_180011B35
0x18001192c  mov     rax, [rdi]
0x18001192f  lea     rdx, [rbp+30h+var_88]
0x180011933  mov     rcx, rdi
0x180011936  mov     rax, [rax+40h]
0x18001193a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001193f  mov     ebx, eax
0x180011941  test    eax, eax
0x180011943  js      loc_180011B35
0x180011949  cmp     [rbp+30h+var_88], r14
0x18001194d  jnz     short loc_1800119A9
0x18001194f  lea     rcx, [rbp+30h+var_80]
0x180011953  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011958  nop
0x180011959  lea     rcx, [rbp+30h+var_88]
0x18001195d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011962  nop
0x180011963  lea     rcx, [rbp+30h+var_78]; this
0x180011967  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001196c  nop
0x18001196d  lea     rcx, [rbp+30h+sourceString]
0x180011971  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011976  nop
0x180011977  lea     rcx, [rbp+30h+var_90]
0x18001197b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011980  nop
0x180011981  lea     rcx, [rbp+30h+var_A0]
0x180011985  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001198a  nop
0x18001198b  lea     rcx, [rbp+30h+var_60]; this
0x18001198f  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011994  nop
0x180011995  lea     rcx, [rsp+130h+var_100]
0x18001199a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001199f  mov     ebx, 800704B4h
0x1800119a4  jmp     loc_180011B86
0x1800119a9  mov     [rbp+30h+var_68], r14
0x1800119ad  mov     [rbp+30h+var_70], r14
0x1800119b1  mov     rdi, [rbp+30h+var_A0]
0x1800119b5  mov     rax, [rdi]
0x1800119b8  mov     rbx, [rax+50h]
0x1800119bc  lea     rcx, [rbp+30h+var_70]
0x1800119c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800119c5  mov     rdx, [rbp+30h+sourceString]
0x1800119c9  mov     [rsp+130h+var_F8], rdx
0x1800119ce  lea     rdx, [rsp+130h+var_F8]
0x1800119d3  lea     rcx, [rsp+130h+var_C0]
0x1800119d8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800119dd  nop
0x1800119de  lea     r9, [rbp+30h+var_70]
0x1800119e2  mov     r8, [rax+18h]
0x1800119e6  mov     rdx, [rbp+30h+var_88]
0x1800119ea  mov     rcx, rdi
0x1800119ed  mov     rax, rbx
0x1800119f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f5  mov     ebx, eax
0x1800119f7  test    eax, eax
0x1800119f9  js      loc_180011B21
0x1800119ff  mov     rdi, [rbp+30h+var_70]
0x180011a03  lea     rcx, [rbp+30h+var_68]
0x180011a07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a0c  mov     rcx, rdi
0x180011a0f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)
0x180011a14  mov     ebx, eax
0x180011a16  test    eax, eax
0x180011a18  js      loc_180011B21
0x180011a1e  mov     rax, [rdi]
0x180011a21  lea     rdx, [rbp+30h+var_68]
0x180011a25  mov     rcx, rdi
0x180011a28  mov     rax, [rax+40h]
0x180011a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a31  mov     ebx, eax
0x180011a33  test    eax, eax
0x180011a35  js      loc_180011B21
0x180011a3b  lea     rcx, [rbp+30h+var_70]
0x180011a3f  cmp     [rbp+30h+var_68], r14
0x180011a43  jnz     short loc_180011AAF
0x180011a45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a4a  nop
0x180011a4b  lea     rcx, [rbp+30h+var_68]
0x180011a4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a54  nop
0x180011a55  lea     rcx, [rbp+30h+var_80]
0x180011a59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a5e  nop
0x180011a5f  lea     rcx, [rbp+30h+var_88]
0x180011a63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a68  nop
0x180011a69  lea     rcx, [rbp+30h+var_78]; this
0x180011a6d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180011a72  nop
0x180011a73  lea     rcx, [rbp+30h+sourceString]
0x180011a77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011a7c  nop
0x180011a7d  lea     rcx, [rbp+30h+var_90]
0x180011a81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a86  nop
0x180011a87  lea     rcx, [rbp+30h+var_A0]
0x180011a8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a90  nop
0x180011a91  lea     rcx, [rbp+30h+var_60]; this
0x180011a95  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011a9a  nop
0x180011a9b  lea     rcx, [rsp+130h+var_100]
0x180011aa0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011aa5  mov     ebx, 80070525h
0x180011aaa  jmp     loc_180011B86
0x180011aaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ab4  nop
0x180011ab5  lea     rcx, [rbp+30h+var_68]
0x180011ab9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011abe  nop
0x180011abf  lea     rcx, [rbp+30h+var_80]
0x180011ac3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ac8  nop
0x180011ac9  lea     rcx, [rbp+30h+var_88]
0x180011acd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ad2  nop
0x180011ad3  lea     rcx, [rbp+30h+var_78]; this
0x180011ad7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180011adc  nop
0x180011add  lea     rcx, [rbp+30h+sourceString]
0x180011ae1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011ae6  nop
0x180011ae7  lea     rcx, [rbp+30h+var_90]
0x180011aeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011af0  nop
0x180011af1  lea     rcx, [rbp+30h+var_A0]
0x180011af5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011afa  nop
0x180011afb  lea     rcx, [rbp+30h+var_60]; this
0x180011aff  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011b04  nop
0x180011b05  lea     rcx, [rsp+130h+var_100]
0x180011b0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b0f  nop
0x180011b10  mov     qword ptr [rbp+30h+var_60], r15
0x180011b14  lea     rcx, [rbp+30h+var_60]; this
0x180011b18  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180011b1d  xor     eax, eax
0x180011b1f  jmp     short loc_180011B95
0x180011b21  lea     rcx, [rbp+30h+var_70]
0x180011b25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b2a  nop
0x180011b2b  lea     rcx, [rbp+30h+var_68]
0x180011b2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b34  nop
0x180011b35  lea     rcx, [rbp+30h+var_80]
0x180011b39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b3e  nop
0x180011b3f  lea     rcx, [rbp+30h+var_88]
0x180011b43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011b48  nop
0x180011b49  lea     rcx, [rbp+30h+var_78]; this
0x180011b4d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
  ... truncated ...
```
