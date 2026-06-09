# WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,WinStoreAuth::TicketHolder &)

- ea: `0x1800a52ec`
- end: `0x1800a54e3`
- name: `?ExtractTicketFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAUTicketHolder@2@@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800620e8`

## callees

- `0x180004738`
- `0x18002cce0`
- `0x180061c04`
- `0x180068f9c`
- `0x18006c124`
- `0x1800a5228`
- `0x1800a52ec`
- `0x1800a7508`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a545d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a545d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a536f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a542d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a536f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a542d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, __int64); // rdi
  enum WinStoreAuth::AccountProviderType *v16; // rdx
  const char *v17; // rax
  int v19; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF

  v22 = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 64LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  v6 = v5(v4, &v22);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v22);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 2081;
      goto LABEL_5;
    }
    WindowsDeleteString(*(HSTRING *)(a2 + 16));
    *(_QWORD *)(a2 + 16) = 0;
    v6 = WinStoreAuth::AuthenticationInternal::ExtractAccountId(&v22, a2 + 16);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 2083;
      goto LABEL_5;
    }
    v21 = 0;
    v9 = v22;
    v10 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v22 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    v11 = v10(v9, &v21);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v11 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v21);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v11 = WinStoreAuth::AuthenticationInternal::ExtractProviderType(&v21, (_DWORD *)a2);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v14 = *a1;
          v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 48LL);
          WindowsDeleteString(*(HSTRING *)(a2 + 8));
          *(_QWORD *)(a2 + 8) = 0;
          v11 = v15(v14, a2 + 8);
          v7 = v11;
          if ( v11 >= 0 )
          {
            WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 16), 0);
            v17 = (const char *)WinStoreAuth::ConvertProviderTypeToString((WinStoreAuth *)a2, v16);
            LOBYTE(v19) = 1;
            wil::details::in1diag3::Log_HrIfMsg(
              retaddr,
              (void *)0x82D,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)0x80004005LL,
              v19,
              (bool)"Account Ticket succesfully extracted. Ticket providerType: %ws web: %ws ",
              v17);
            if ( *(_DWORD *)a2 )
            {
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
              v7 = 0;
              goto LABEL_21;
            }
            v7 = -2147418113;
            v13 = 2147549183LL;
            v12 = 2095;
            goto LABEL_11;
          }
          v12 = 2090;
        }
        else
        {
          v12 = 2089;
        }
      }
      else
      {
        v12 = 2087;
      }
    }
    else
    {
      v12 = 2086;
    }
    v13 = (unsigned int)v11;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v13,
      v19);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    goto LABEL_21;
  }
  v8 = 2080;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)v6,
    v19);
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  return v7;
}

```

## disassembly

```asm
0x1800a52ec  mov     [rsp-28h+arg_8], rbx
0x1800a52f1  push    rbp
0x1800a52f2  push    rsi
0x1800a52f3  push    rdi
0x1800a52f4  push    r14
0x1800a52f6  push    r15
0x1800a52f8  mov     rbp, rsp
0x1800a52fb  sub     rsp, 40h
0x1800a52ff  mov     r15, rdx
0x1800a5302  mov     rsi, rcx
0x1800a5305  mov     [rbp+arg_10], 0
0x1800a530d  mov     rdi, [rcx]
0x1800a5310  mov     rax, [rdi]
0x1800a5313  mov     rbx, [rax+40h]
0x1800a5317  lea     rcx, [rbp+arg_10]
0x1800a531b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5320  lea     rdx, [rbp+arg_10]
0x1800a5324  mov     rcx, rdi
0x1800a5327  mov     rax, rbx
0x1800a532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a532f  mov     ebx, eax
0x1800a5331  test    eax, eax
0x1800a5333  jns     short loc_1800A533C
0x1800a5335  mov     edx, 820h
0x1800a533a  jmp     short loc_1800A5350
0x1800a533c  mov     rcx, [rbp+arg_10]
0x1800a5340  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x1800a5345  mov     ebx, eax
0x1800a5347  test    eax, eax
0x1800a5349  jns     short loc_1800A5368
0x1800a534b  mov     edx, 821h; void *
0x1800a5350  mov     rcx, [rbp+28h]; this
0x1800a5354  mov     r9d, eax; char *
0x1800a5357  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a535e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5363  jmp     loc_1800A54C7
0x1800a5368  lea     r14, [r15+10h]
0x1800a536c  mov     rcx, [r14]; string
0x1800a536f  call    cs:__imp_WindowsDeleteString
0x1800a5375  mov     qword ptr [r14], 0
0x1800a537c  mov     rdx, r14
0x1800a537f  lea     rcx, [rbp+arg_10]
0x1800a5383  call    ?ExtractAccountId@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@PEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::ExtractAccountId(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> const &,HSTRING__ * *)
0x1800a5388  mov     ebx, eax
0x1800a538a  test    eax, eax
0x1800a538c  jns     short loc_1800A5395
0x1800a538e  mov     edx, 823h
0x1800a5393  jmp     short loc_1800A5350
0x1800a5395  mov     [rbp+arg_0], 0
0x1800a539d  mov     rdi, [rbp+arg_10]
0x1800a53a1  mov     rax, [rdi]
0x1800a53a4  mov     rbx, [rax+30h]
0x1800a53a8  lea     rcx, [rbp+arg_0]
0x1800a53ac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a53b1  lea     rdx, [rbp+arg_0]
0x1800a53b5  mov     rcx, rdi
0x1800a53b8  mov     rax, rbx
0x1800a53bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a53c0  mov     ebx, eax
0x1800a53c2  test    eax, eax
0x1800a53c4  jns     short loc_1800A53ED
0x1800a53c6  mov     edx, 826h; void *
0x1800a53cb  mov     r9d, eax; char *
0x1800a53ce  mov     rcx, [rbp+28h]; this
0x1800a53d2  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a53d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a53de  nop
0x1800a53df  lea     rcx, [rbp+arg_0]
0x1800a53e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a53e8  jmp     loc_1800A54C7
0x1800a53ed  mov     rcx, [rbp+arg_0]
0x1800a53f1  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x1800a53f6  mov     ebx, eax
0x1800a53f8  test    eax, eax
0x1800a53fa  jns     short loc_1800A5403
0x1800a53fc  mov     edx, 827h
0x1800a5401  jmp     short loc_1800A53CB
0x1800a5403  mov     rdx, r15
0x1800a5406  lea     rcx, [rbp+arg_0]
0x1800a540a  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x1800a540f  mov     ebx, eax
0x1800a5411  test    eax, eax
0x1800a5413  jns     short loc_1800A541C
0x1800a5415  mov     edx, 829h
0x1800a541a  jmp     short loc_1800A53CB
0x1800a541c  mov     rsi, [rsi]
0x1800a541f  mov     rax, [rsi]
0x1800a5422  mov     rdi, [rax+30h]
0x1800a5426  lea     rbx, [r15+8]
0x1800a542a  mov     rcx, [rbx]; string
0x1800a542d  call    cs:__imp_WindowsDeleteString
0x1800a5433  mov     qword ptr [rbx], 0
0x1800a543a  mov     rdx, rbx
0x1800a543d  mov     rcx, rsi
0x1800a5440  mov     rax, rdi
0x1800a5443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5448  mov     ebx, eax
0x1800a544a  test    eax, eax
0x1800a544c  jns     short loc_1800A5458
0x1800a544e  mov     edx, 82Ah
0x1800a5453  jmp     loc_1800A53CB
0x1800a5458  xor     edx, edx; length
0x1800a545a  mov     rcx, [r14]; string
0x1800a545d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a5463  mov     r8, rax
0x1800a5466  mov     rcx, r15; this
0x1800a5469  call    ?ConvertProviderTypeToString@WinStoreAuth@@YAPEBGAEAW4AccountProviderType@1@@Z; WinStoreAuth::ConvertProviderTypeToString(WinStoreAuth::AccountProviderType &)
0x1800a546e  mov     rcx, [rbp+28h]; this
0x1800a5472  mov     [rsp+40h+var_8], r8
0x1800a5477  mov     [rsp+40h+var_10], rax; char *
0x1800a547c  lea     rax, aAccountTicketS; "Account Ticket succesfully extracted. T"...
0x1800a5483  mov     qword ptr [rsp+40h+var_18], rax; bool
0x1800a5488  mov     byte ptr [rsp+40h+var_20], 1; int
0x1800a548d  mov     r9d, 80004005h; char *
0x1800a5493  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a549a  mov     edx, 82Dh; void *
0x1800a549f  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800a54a4  cmp     dword ptr [r15], 0
0x1800a54a8  jnz     short loc_1800A54BC
0x1800a54aa  mov     ebx, 8000FFFFh
0x1800a54af  mov     r9d, ebx
0x1800a54b2  mov     edx, 82Fh
0x1800a54b7  jmp     loc_1800A53CE
0x1800a54bc  lea     rcx, [rbp+arg_0]
0x1800a54c0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a54c5  xor     ebx, ebx
0x1800a54c7  lea     rcx, [rbp+arg_10]
0x1800a54cb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a54d0  mov     eax, ebx
0x1800a54d2  mov     rbx, [rsp+40h+arg_8]
0x1800a54d7  add     rsp, 40h
0x1800a54db  pop     r15
0x1800a54dd  pop     r14
0x1800a54df  pop     rdi
0x1800a54e0  pop     rsi
0x1800a54e1  pop     rbp
0x1800a54e2  retn
```
