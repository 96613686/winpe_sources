# WinStoreAuth::AuthenticationInternal::CreateTokenBrokerInternal(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * *)

- ea: `0x18002c45c`
- end: `0x18002c68c`
- name: `?CreateTokenBrokerInternal@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002b3f0`

## callees

- `0x180004738`
- `0x18002bb00`
- `0x18002c45c`
- `0x18002cce0`
- `0x180061c04`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c4ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002c4ba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c4dc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c4a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c4a4`

## string_xrefs

- `0x18002c49d`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenBrokerInternal(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics **a2)
{
  HRESULT v3; // eax
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v18; // rax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  *(_QWORD *)this = 0;
  v19 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v19);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v19);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
    return v6;
  }
  v8 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v19);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v8,
      (int)v19);
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
    }
    return v6;
  }
  v20 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  v11 = **v19;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  v12 = v11(v10, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v20);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      (int)v19);
    v13 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
    }
    return v6;
  }
  v15 = WinStoreAuth::SetProxyBlanket<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(v20);
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v15,
      (int)v19);
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v17)[2])(v17);
    }
    return v6;
  }
  v18 = v20;
  v20 = 0;
  *(_QWORD *)this = v18;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  return 0;
}

```

## disassembly

```asm
0x18002c45c  push    rbp
0x18002c45e  push    rbx
0x18002c45f  push    rsi
0x18002c460  push    rdi
0x18002c461  mov     rbp, rsp
0x18002c464  sub     rsp, 68h
0x18002c468  mov     rax, cs:__security_cookie
0x18002c46f  xor     rax, rsp
0x18002c472  mov     [rbp+var_18], rax
0x18002c476  mov     rsi, rcx
0x18002c479  mov     qword ptr [rcx], 0
0x18002c480  mov     [rbp+var_48], 0
0x18002c488  mov     [rbp+string], 0
0x18002c490  lea     r9, [rbp+string]; string
0x18002c494  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002c498  mov     edx, 40h ; '@'; length
0x18002c49d  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18002c4a4  call    cs:__imp_WindowsCreateStringReference
0x18002c4aa  test    eax, eax
0x18002c4ac  jns     short loc_18002C4C1
0x18002c4ae  xor     r9d, r9d; lpArguments
0x18002c4b1  xor     r8d, r8d; nNumberOfArguments
0x18002c4b4  lea     edx, [r9+1]; dwExceptionFlags
0x18002c4b8  mov     ecx, eax; dwExceptionCode
0x18002c4ba  call    cs:__imp_RaiseException
0x18002c4c0  int     3; Trap to Debugger
0x18002c4c1  mov     rbx, [rbp+string]
0x18002c4c5  lea     rcx, [rbp+var_48]
0x18002c4c9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c4ce  lea     r8, [rbp+var_48]
0x18002c4d2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18002c4d9  mov     rcx, rbx
0x18002c4dc  call    cs:__imp_RoGetActivationFactory
0x18002c4e2  mov     ebx, eax
0x18002c4e4  test    eax, eax
0x18002c4e6  jns     short loc_18002C511
0x18002c4e8  mov     rcx, [rbp+20h]; this
0x18002c4ec  mov     r9d, eax; char *
0x18002c4ef  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002c4f6  mov     edx, 6D9h; void *
0x18002c4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c500  nop
0x18002c501  lea     rcx, [rbp+var_48]
0x18002c505  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c50a  mov     eax, ebx
0x18002c50c  jmp     loc_18002C677
0x18002c511  mov     rcx, [rbp+var_48]
0x18002c515  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18002c51a  mov     ebx, eax
0x18002c51c  test    eax, eax
0x18002c51e  jns     short loc_18002C559
0x18002c520  mov     rcx, [rbp+20h]; this
0x18002c524  mov     r9d, eax; char *
0x18002c527  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002c52e  mov     edx, 6DAh; void *
0x18002c533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c538  nop
0x18002c539  mov     rcx, [rbp+var_48]
0x18002c53d  test    rcx, rcx
0x18002c540  jz      short loc_18002C557
0x18002c542  mov     [rbp+var_48], 0
0x18002c54a  mov     rax, [rcx]
0x18002c54d  mov     rax, [rax+10h]
0x18002c551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c556  nop
0x18002c557  jmp     short loc_18002C50A
0x18002c559  mov     [rbp+var_40], 0
0x18002c561  mov     rbx, [rbp+var_48]
0x18002c565  mov     rax, [rbx]
0x18002c568  mov     rdi, [rax]
0x18002c56b  lea     rcx, [rbp+var_40]
0x18002c56f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c574  lea     r8, [rbp+var_40]
0x18002c578  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18002c57f  mov     rcx, rbx
0x18002c582  mov     rax, rdi
0x18002c585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c58a  mov     ebx, eax
0x18002c58c  test    eax, eax
0x18002c58e  jns     short loc_18002C5EA
0x18002c590  mov     rcx, [rbp+20h]; this
0x18002c594  mov     r9d, eax; char *
0x18002c597  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002c59e  mov     edx, 6DDh; void *
0x18002c5a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5a8  nop
0x18002c5a9  mov     rcx, [rbp+var_40]
0x18002c5ad  test    rcx, rcx
0x18002c5b0  jz      short loc_18002C5C7
0x18002c5b2  mov     [rbp+var_40], 0
0x18002c5ba  mov     rax, [rcx]
0x18002c5bd  mov     rax, [rax+10h]
0x18002c5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5c6  nop
0x18002c5c7  mov     rcx, [rbp+var_48]
0x18002c5cb  test    rcx, rcx
0x18002c5ce  jz      short loc_18002C5E5
0x18002c5d0  mov     [rbp+var_48], 0
0x18002c5d8  mov     rax, [rcx]
0x18002c5db  mov     rax, [rax+10h]
0x18002c5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5e4  nop
0x18002c5e5  jmp     loc_18002C50A
0x18002c5ea  mov     rcx, [rbp+var_40]
0x18002c5ee  call    ??$SetProxyBlanket@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WinStoreAuth@@YAJPEAUITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *)
0x18002c5f3  mov     ebx, eax
0x18002c5f5  test    eax, eax
0x18002c5f7  jns     short loc_18002C653
0x18002c5f9  mov     rcx, [rbp+20h]; this
0x18002c5fd  mov     r9d, eax; char *
0x18002c600  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002c607  mov     edx, 6DEh; void *
0x18002c60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c611  nop
0x18002c612  mov     rcx, [rbp+var_40]
0x18002c616  test    rcx, rcx
0x18002c619  jz      short loc_18002C630
0x18002c61b  mov     [rbp+var_40], 0
0x18002c623  mov     rax, [rcx]
0x18002c626  mov     rax, [rax+10h]
0x18002c62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c62f  nop
0x18002c630  mov     rcx, [rbp+var_48]
0x18002c634  test    rcx, rcx
0x18002c637  jz      short loc_18002C64E
0x18002c639  mov     [rbp+var_48], 0
0x18002c641  mov     rax, [rcx]
0x18002c644  mov     rax, [rax+10h]
0x18002c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c64d  nop
0x18002c64e  jmp     loc_18002C50A
0x18002c653  mov     rax, [rbp+var_40]
0x18002c657  mov     [rbp+var_40], 0
0x18002c65f  mov     [rsi], rax
0x18002c662  lea     rcx, [rbp+var_40]
0x18002c666  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c66b  nop
0x18002c66c  lea     rcx, [rbp+var_48]
0x18002c670  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c675  xor     eax, eax
0x18002c677  mov     rcx, [rbp+var_18]
0x18002c67b  xor     rcx, rsp; StackCookie
0x18002c67e  call    __security_check_cookie
0x18002c683  add     rsp, 68h
0x18002c687  pop     rdi
0x18002c688  pop     rsi
0x18002c689  pop     rbx
0x18002c68a  pop     rbp
0x18002c68b  retn
```
