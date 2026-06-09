# WinStoreAuth::AuthenticationInternal::GetTicketForAccount(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool,Windows::System::IUser *,HSTRING__ * *,WinStoreAuth::AccountProviderType *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x1800a6840`
- end: `0x1800a6b4e`
- name: `?GetTicketForAccount@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@22_NPEAUIUser@System@Windows@@PEAPEAU5@PEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z`
- size: `782`
- prototype: `int __high(HWND, enum WinStoreAuth::PromptType, HSTRING, HSTRING, HSTRING, bool, struct Windows::System::IUser *, HSTRING *, enum WinStoreAuth::AccountProviderType *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006a520`

## callees

- `0x180004738`
- `0x18002ca1c`
- `0x18002d188`
- `0x18002d928`
- `0x18002e07c`
- `0x180061c04`
- `0x180068f9c`
- `0x18006e9e0`
- `0x1800a3c58`
- `0x1800a6840`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a68ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a68d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a68ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a68d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a688b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a688b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetTicketForAccount(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HSTRING a4,
        HSTRING a5,
        UINT32 length,
        __int64 a7,
        _QWORD *a8,
        _DWORD *a9,
        __int64 (__fastcall ***a10)(_QWORD, GUID *, __int64 *))
{
  WinStoreAuth::AuthenticationInternal *v10; // rbx
  _QWORD *v12; // rsi
  _DWORD *v13; // r14
  const WCHAR *StringRawBuffer; // rdi
  HSTRING v15; // r8
  int AccountProvider; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **v19; // rdx
  int TokenBroker; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, _QWORD **); // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  int Tickets; // eax
  __int64 v29; // rax
  struct Windows::Security::Credentials::IWebAccountProvider **bIgnoreCase; // [rsp+20h] [rbp-50h]
  int bIgnoreCasea; // [rsp+20h] [rbp-50h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-50h]
  int bIgnoreCasec; // [rsp+20h] [rbp-50h]
  int v35; // [rsp+50h] [rbp-20h] BYREF
  __int128 v36; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v38; // [rsp+B0h] [rbp+40h] BYREF
  int v39; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v40; // [rsp+C8h] [rbp+58h] BYREF

  v38 = a1;
  v10 = (WinStoreAuth::AuthenticationInternal *)a4;
  v12 = a8;
  *a8 = 0;
  v13 = a9;
  *a9 = 0;
  *a10 = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, &length);
  if ( CompareStringOrdinal(StringRawBuffer, length, L"Msa", -1, 1) == 2
    || CompareStringOrdinal(StringRawBuffer, length, L"Aad", -1, 1) == 2 )
  {
    v10 = (WinStoreAuth::AuthenticationInternal *)qword_1800F2B88;
  }
  a10 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a10);
  AccountProvider = WinStoreAuth::AuthenticationInternal::GetAccountProvider(
                      v10,
                      a5,
                      v15,
                      (struct Windows::System::IUser *)&a10,
                      bIgnoreCase);
  v17 = AccountProvider;
  if ( AccountProvider < 0 )
  {
    v18 = 408;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)AccountProvider,
      bIgnoreCasea);
    goto LABEL_24;
  }
  AccountProvider = WinStoreAuth::AuthenticationInternal::ExtractProviderType(&a10, &v39);
  v17 = AccountProvider;
  if ( AccountProvider < 0 )
  {
    v18 = 412;
    goto LABEL_8;
  }
  v38 = 0;
  TokenBroker = WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
                  (WinStoreAuth::AuthenticationInternal *)&v38,
                  v19);
  v17 = TokenBroker;
  if ( TokenBroker >= 0 )
  {
    a8 = 0;
    v21 = v38;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, _QWORD **))(*(_QWORD *)v38 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a8);
    v23 = v22(v21, a10, a3, &a8);
    v17 = v23;
    if ( v23 >= 0 )
    {
      a9 = 0;
      v24 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
              a8,
              &a9);
      v17 = v24;
      if ( v24 >= 0 )
      {
        v40 = 0;
        v25 = WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(&a10, 0, 0, 0, &v40);
        v17 = v25;
        if ( v25 >= 0 )
        {
          v35 = 0;
          v36 = 0;
          a7 = 0;
          Tickets = WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(
                      (unsigned int)&v38,
                      (unsigned int)&v40,
                      v26,
                      v27,
                      (__int64)a9,
                      (__int64)&v35,
                      1,
                      (__int64)&a7);
          v17 = Tickets;
          if ( Tickets >= 0 )
          {
            v29 = v36;
            *(_QWORD *)&v36 = 0;
            *v12 = v29;
            *v13 = v35;
            WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v35);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a9);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a8);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
            v17 = 0;
            goto LABEL_24;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BD,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)Tickets,
            bIgnoreCasec);
          WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)&v35);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AF,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCaseb);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCasea);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a9);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCasea);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TokenBroker,
      bIgnoreCasea);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&a10);
  return v17;
}

```

## disassembly

```asm
0x1800a6840  mov     [rsp-38h+arg_10], rbx
0x1800a6845  mov     [rsp-38h+arg_0], rcx
0x1800a684a  push    rbp
0x1800a684b  push    rsi
0x1800a684c  push    rdi
0x1800a684d  push    r12
0x1800a684f  push    r13
0x1800a6851  push    r14
0x1800a6853  push    r15
0x1800a6855  mov     rbp, rsp
0x1800a6858  sub     rsp, 70h
0x1800a685c  mov     rbx, r9
0x1800a685f  mov     r12, r8
0x1800a6862  xor     r13d, r13d
0x1800a6865  mov     rsi, [rbp+arg_38]
0x1800a6869  mov     [rsi], r13
0x1800a686c  mov     r14, [rbp+arg_40]
0x1800a6873  mov     [r14], r13d
0x1800a6876  mov     r15, [rbp+arg_48]
0x1800a687d  mov     [r15], r13
0x1800a6880  mov     [rbp+length], r13d
0x1800a6884  lea     rdx, [rbp+length]; length
0x1800a6888  mov     rcx, r9; string
0x1800a688b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a6891  mov     rdi, rax
0x1800a6894  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1800a689c  or      r9d, 0FFFFFFFFh; cchCount2
0x1800a68a0  lea     r8, aMsa; "Msa"
0x1800a68a7  mov     edx, [rbp+length]; cchCount1
0x1800a68aa  mov     rcx, rax; lpString1
0x1800a68ad  call    cs:__imp_CompareStringOrdinal
0x1800a68b3  cmp     eax, 2
0x1800a68b6  jz      short loc_1800A68DC
0x1800a68b8  mov     [rsp+70h+bIgnoreCase], 1; int
0x1800a68c0  or      r9d, 0FFFFFFFFh; cchCount2
0x1800a68c4  lea     r8, aAad_0; "Aad"
0x1800a68cb  mov     edx, [rbp+length]; cchCount1
0x1800a68ce  mov     rcx, rdi; lpString1
0x1800a68d1  call    cs:__imp_CompareStringOrdinal
0x1800a68d7  cmp     eax, 2
0x1800a68da  jnz     short loc_1800A68E3
0x1800a68dc  mov     rbx, cs:qword_1800F2B88
0x1800a68e3  mov     [rbp+arg_48], r13
0x1800a68ea  lea     rcx, [rbp+arg_48]
0x1800a68f1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a68f6  lea     r9, [rbp+arg_48]; struct Windows::System::IUser *
0x1800a68fd  mov     rdx, [rbp+arg_20]; HSTRING
0x1800a6901  mov     rcx, rbx; this
0x1800a6904  call    ?GetAccountProvider@AuthenticationInternal@WinStoreAuth@@YAJPEAUHSTRING__@@0PEAUIUser@System@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z; WinStoreAuth::AuthenticationInternal::GetAccountProvider(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,Windows::Security::Credentials::IWebAccountProvider * *)
0x1800a6909  mov     ebx, eax
0x1800a690b  test    eax, eax
0x1800a690d  jns     short loc_1800A6916
0x1800a690f  mov     edx, 198h
0x1800a6914  jmp     short loc_1800A6931
0x1800a6916  lea     rdx, [rbp+arg_8]
0x1800a691a  lea     rcx, [rbp+arg_48]
0x1800a6921  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x1800a6926  mov     ebx, eax
0x1800a6928  test    eax, eax
0x1800a692a  jns     short loc_1800A6949
0x1800a692c  mov     edx, 19Ch; void *
0x1800a6931  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6938  mov     r9d, eax; char *
0x1800a693b  mov     rcx, [rbp+38h]; this
0x1800a693f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6944  jmp     loc_1800A6B28
0x1800a6949  mov     [rbp+arg_0], r13
0x1800a694d  lea     rcx, [rbp+arg_0]; this
0x1800a6951  call    ?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)
0x1800a6956  mov     ebx, eax
0x1800a6958  test    eax, eax
0x1800a695a  jns     short loc_1800A6983
0x1800a695c  mov     rcx, [rbp+38h]; this
0x1800a6960  mov     r9d, eax; char *
0x1800a6963  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a696a  mov     edx, 1A6h; void *
0x1800a696f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6974  nop
0x1800a6975  lea     rcx, [rbp+arg_0]
0x1800a6979  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a697e  jmp     loc_1800A6B28
0x1800a6983  mov     [rbp+arg_38], r13
0x1800a6987  mov     rdi, [rbp+arg_0]
0x1800a698b  mov     rax, [rdi]
0x1800a698e  mov     rbx, [rax+50h]
0x1800a6992  lea     rcx, [rbp+arg_38]
0x1800a6996  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a699b  lea     r9, [rbp+arg_38]
0x1800a699f  mov     r8, r12
0x1800a69a2  mov     rdx, [rbp+arg_48]
0x1800a69a9  mov     rcx, rdi
0x1800a69ac  mov     rax, rbx
0x1800a69af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a69b4  mov     ebx, eax
0x1800a69b6  test    eax, eax
0x1800a69b8  jns     short loc_1800A69DE
0x1800a69ba  mov     rcx, [rbp+38h]; this
0x1800a69be  mov     r9d, eax; char *
0x1800a69c1  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a69c8  mov     edx, 1A9h; void *
0x1800a69cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a69d2  nop
0x1800a69d3  lea     rcx, [rbp+arg_38]
0x1800a69d7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a69dc  jmp     short loc_1800A6975
0x1800a69de  mov     [rbp+arg_40], r13
0x1800a69e5  lea     rdx, [rbp+arg_40]
0x1800a69ec  mov     rcx, [rbp+arg_38]
0x1800a69f0  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccount@Credentials@Security@Windows@@UIWebAccount@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAXK@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>>,tagCOWAIT_FLAGS,void *,ulong)
0x1800a69f5  mov     ebx, eax
0x1800a69f7  test    eax, eax
0x1800a69f9  jns     short loc_1800A6A22
0x1800a69fb  mov     rcx, [rbp+38h]; this
0x1800a69ff  mov     r9d, eax; char *
0x1800a6a02  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6a09  mov     edx, 1ACh; void *
0x1800a6a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6a13  nop
0x1800a6a14  lea     rcx, [rbp+arg_40]
0x1800a6a1b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6a20  jmp     short loc_1800A69D3
0x1800a6a22  mov     [rbp+arg_18], r13
0x1800a6a26  lea     rax, [rbp+arg_18]
0x1800a6a2a  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x1800a6a2f  xor     r9d, r9d
0x1800a6a32  xor     r8d, r8d
0x1800a6a35  xor     edx, edx
0x1800a6a37  lea     rcx, [rbp+arg_48]
0x1800a6a3e  call    ?CreateTokenRequestHelper@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1800a6a43  mov     ebx, eax
0x1800a6a45  test    eax, eax
0x1800a6a47  jns     short loc_1800A6A6D
0x1800a6a49  mov     rcx, [rbp+38h]; this
0x1800a6a4d  mov     r9d, eax; char *
0x1800a6a50  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6a57  mov     edx, 1AFh; void *
0x1800a6a5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6a61  nop
0x1800a6a62  lea     rcx, [rbp+arg_18]
0x1800a6a66  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6a6b  jmp     short loc_1800A6A14
0x1800a6a6d  mov     [rbp+var_20], r13d
0x1800a6a71  xorps   xmm0, xmm0
0x1800a6a74  movdqu  [rbp+var_18], xmm0
0x1800a6a79  mov     [rbp+arg_30], r13
0x1800a6a7d  mov     [rsp+70h+var_28], r15
0x1800a6a82  lea     rax, [rbp+arg_30]
0x1800a6a86  mov     [rsp+70h+var_38], rax
0x1800a6a8b  mov     [rsp+70h+var_40], 1
0x1800a6a94  lea     rax, [rbp+var_20]
0x1800a6a98  mov     [rsp+70h+var_48], rax
0x1800a6a9d  mov     rax, [rbp+arg_40]
0x1800a6aa4  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x1800a6aa9  lea     rdx, [rbp+arg_18]
0x1800a6aad  lea     rcx, [rbp+arg_0]
0x1800a6ab1  call    ?SendTokenRequestAndGetTickets@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@W4PromptType@2@PEAUHWND__@@PEAUIWebAccount@Credentials@Security@Windows@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> const &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> const &,WinStoreAuth::PromptType,HWND__ *,Windows::Security::Credentials::IWebAccount *,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1800a6ab6  mov     ebx, eax
0x1800a6ab8  test    eax, eax
0x1800a6aba  jns     short loc_1800A6AE0
0x1800a6abc  mov     rcx, [rbp+38h]; this
0x1800a6ac0  mov     r9d, eax; char *
0x1800a6ac3  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6aca  mov     edx, 1BDh; void *
0x1800a6acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ad4  nop
0x1800a6ad5  lea     rcx, [rbp+var_20]; this
0x1800a6ad9  call    ??1TicketHolder@WinStoreAuth@@QEAA@XZ; WinStoreAuth::TicketHolder::~TicketHolder(void)
0x1800a6ade  jmp     short loc_1800A6A62
0x1800a6ae0  mov     rax, qword ptr [rbp+var_18]
0x1800a6ae4  mov     qword ptr [rbp+var_18], r13
0x1800a6ae8  mov     [rsi], rax
0x1800a6aeb  mov     eax, [rbp+var_20]
0x1800a6aee  mov     [r14], eax
0x1800a6af1  lea     rcx, [rbp+var_20]; this
0x1800a6af5  call    ??1TicketHolder@WinStoreAuth@@QEAA@XZ; WinStoreAuth::TicketHolder::~TicketHolder(void)
0x1800a6afa  nop
0x1800a6afb  lea     rcx, [rbp+arg_18]
0x1800a6aff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6b04  nop
0x1800a6b05  lea     rcx, [rbp+arg_40]
0x1800a6b0c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6b11  nop
0x1800a6b12  lea     rcx, [rbp+arg_38]
0x1800a6b16  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6b1b  nop
0x1800a6b1c  lea     rcx, [rbp+arg_0]
0x1800a6b20  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6b25  mov     ebx, r13d
0x1800a6b28  lea     rcx, [rbp+arg_48]
0x1800a6b2f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6b34  mov     eax, ebx
0x1800a6b36  mov     rbx, [rsp+70h+arg_10]
0x1800a6b3e  add     rsp, 70h
0x1800a6b42  pop     r15
0x1800a6b44  pop     r14
0x1800a6b46  pop     r13
0x1800a6b48  pop     r12
0x1800a6b4a  pop     rdi
0x1800a6b4b  pop     rsi
0x1800a6b4c  pop     rbp
0x1800a6b4d  retn
```
