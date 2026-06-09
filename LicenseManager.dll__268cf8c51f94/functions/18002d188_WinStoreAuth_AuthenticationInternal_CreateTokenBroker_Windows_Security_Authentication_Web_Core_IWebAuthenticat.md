# WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)

- ea: `0x18002d188`
- end: `0x18002d33d`
- name: `?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002b3f0`
- `0x18002ca1c`
- `0x1800a5704`
- `0x1800a6840`

## callees

- `0x180004738`
- `0x18002cce0`
- `0x18002d188`
- `0x18002d72c`
- `0x180061c04`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d1e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d1e6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d208`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d1d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d1d0`

## string_xrefs

- `0x18002d1c9`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **a2)
{
  HRESULT v3; // eax
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rcx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  *(_QWORD *)this = 0;
  v16 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v16);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v16);
    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v7)[2])(v7);
    }
    return v6;
  }
  v9 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v16);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v9,
      (int)v16);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
    return v6;
  }
  v17 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  v11 = **v16;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  v12 = v11(v10, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v17);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 1737;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      (int)v16);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    goto LABEL_14;
  }
  v12 = WinStoreAuth::SetProxyBlanket<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>(v17);
  v6 = v12;
  if ( v12 < 0 )
  {
    v13 = 1738;
    goto LABEL_13;
  }
  v14 = v17;
  v17 = 0;
  *(_QWORD *)this = v14;
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d188  push    rbp
0x18002d18a  push    rbx
0x18002d18b  push    rsi
0x18002d18c  push    rdi
0x18002d18d  mov     rbp, rsp
0x18002d190  sub     rsp, 68h
0x18002d194  mov     rax, cs:__security_cookie
0x18002d19b  xor     rax, rsp
0x18002d19e  mov     [rbp+var_18], rax
0x18002d1a2  mov     rsi, rcx
0x18002d1a5  mov     qword ptr [rcx], 0
0x18002d1ac  mov     [rbp+var_48], 0
0x18002d1b4  mov     [rbp+string], 0
0x18002d1bc  lea     r9, [rbp+string]; string
0x18002d1c0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002d1c4  mov     edx, 45h ; 'E'; length
0x18002d1c9  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18002d1d0  call    cs:__imp_WindowsCreateStringReference
0x18002d1d6  test    eax, eax
0x18002d1d8  jns     short loc_18002D1ED
0x18002d1da  xor     r9d, r9d; lpArguments
0x18002d1dd  xor     r8d, r8d; nNumberOfArguments
0x18002d1e0  lea     edx, [r9+1]; dwExceptionFlags
0x18002d1e4  mov     ecx, eax; dwExceptionCode
0x18002d1e6  call    cs:__imp_RaiseException
0x18002d1ec  int     3; Trap to Debugger
0x18002d1ed  mov     rbx, [rbp+string]
0x18002d1f1  lea     rcx, [rbp+var_48]
0x18002d1f5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002d1fa  lea     r8, [rbp+var_48]
0x18002d1fe  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18002d205  mov     rcx, rbx
0x18002d208  call    cs:__imp_RoGetActivationFactory
0x18002d20e  mov     ebx, eax
0x18002d210  test    eax, eax
0x18002d212  jns     short loc_18002D252
0x18002d214  mov     rcx, [rbp+20h]; this
0x18002d218  mov     r9d, eax; char *
0x18002d21b  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002d222  mov     edx, 6C5h; void *
0x18002d227  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d22c  nop
0x18002d22d  mov     rcx, [rbp+var_48]
0x18002d231  test    rcx, rcx
0x18002d234  jz      short loc_18002D24B
0x18002d236  mov     [rbp+var_48], 0
0x18002d23e  mov     rax, [rcx]
0x18002d241  mov     rax, [rax+10h]
0x18002d245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d24a  nop
0x18002d24b  mov     eax, ebx
0x18002d24d  jmp     loc_18002D328
0x18002d252  mov     rcx, [rbp+var_48]
0x18002d256  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18002d25b  mov     ebx, eax
0x18002d25d  test    eax, eax
0x18002d25f  jns     short loc_18002D27B
0x18002d261  mov     rcx, [rbp+20h]; this
0x18002d265  mov     r9d, eax; char *
0x18002d268  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002d26f  mov     edx, 6C6h; void *
0x18002d274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d279  jmp     short loc_18002D2EB
0x18002d27b  mov     [rbp+var_40], 0
0x18002d283  mov     rbx, [rbp+var_48]
0x18002d287  mov     rax, [rbx]
0x18002d28a  mov     rdi, [rax]
0x18002d28d  lea     rcx, [rbp+var_40]
0x18002d291  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002d296  lea     r8, [rbp+var_40]
0x18002d29a  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18002d2a1  mov     rcx, rbx
0x18002d2a4  mov     rax, rdi
0x18002d2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ac  mov     ebx, eax
0x18002d2ae  test    eax, eax
0x18002d2b0  jns     short loc_18002D2B9
0x18002d2b2  mov     edx, 6C9h
0x18002d2b7  jmp     short loc_18002D2CD
0x18002d2b9  mov     rcx, [rbp+var_40]
0x18002d2bd  call    ??$SetProxyBlanket@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WinStoreAuth@@YAJPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *)
0x18002d2c2  mov     ebx, eax
0x18002d2c4  test    eax, eax
0x18002d2c6  jns     short loc_18002D2F9
0x18002d2c8  mov     edx, 6CAh; void *
0x18002d2cd  mov     r9d, eax; char *
0x18002d2d0  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002d2d7  mov     rcx, [rbp+20h]; this
0x18002d2db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d2e0  nop
0x18002d2e1  lea     rcx, [rbp+var_40]
0x18002d2e5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002d2ea  nop
0x18002d2eb  lea     rcx, [rbp+var_48]
0x18002d2ef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002d2f4  jmp     loc_18002D24B
0x18002d2f9  mov     rax, [rbp+var_40]
0x18002d2fd  mov     [rbp+var_40], 0
0x18002d305  mov     [rsi], rax
0x18002d308  mov     rcx, [rbp+var_48]
0x18002d30c  test    rcx, rcx
0x18002d30f  jz      short loc_18002D326
0x18002d311  mov     [rbp+var_48], 0
0x18002d319  mov     rax, [rcx]
0x18002d31c  mov     rax, [rax+10h]
0x18002d320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d325  nop
0x18002d326  xor     eax, eax
0x18002d328  mov     rcx, [rbp+var_18]
0x18002d32c  xor     rcx, rsp; StackCookie
0x18002d32f  call    __security_check_cookie
0x18002d334  add     rsp, 68h
0x18002d338  pop     rdi
0x18002d339  pop     rsi
0x18002d33a  pop     rbx
0x18002d33b  pop     rbp
0x18002d33c  retn
```
