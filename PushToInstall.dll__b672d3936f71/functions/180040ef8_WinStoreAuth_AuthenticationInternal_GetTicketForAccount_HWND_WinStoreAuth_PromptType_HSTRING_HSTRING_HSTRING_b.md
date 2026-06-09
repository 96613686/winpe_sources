# WinStoreAuth::AuthenticationInternal::GetTicketForAccount(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool,Windows::System::IUser *,HSTRING__ * *,WinStoreAuth::AccountProviderType *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x180040ef8`
- end: `0x180041491`
- name: `?GetTicketForAccount@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@22_NPEAUIUser@System@Windows@@PEAPEAU5@PEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z`
- size: `1433`
- prototype: `int __high(HWND, enum WinStoreAuth::PromptType, HSTRING, HSTRING, HSTRING, bool, struct Windows::System::IUser *, HSTRING *, enum WinStoreAuth::AccountProviderType *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003dcbc`

## callees

- `0x180010b84`
- `0x1800381c4`
- `0x18003a9a8`
- `0x18003b010`
- `0x18003bd7c`
- `0x18003e414`
- `0x180040ef8`
- `0x180043bb0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040f65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040f89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040f65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040f89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetTicketForAccount(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HSTRING a4,
        HSTRING a5,
        UINT32 length,
        __int64 a7,
        HSTRING *a8,
        _DWORD *a9,
        IUnknown *a10)
{
  WinStoreAuth::AuthenticationInternal *v10; // rbx
  HSTRING *v12; // rsi
  _DWORD *v13; // r14
  const WCHAR *StringRawBuffer; // rdi
  HSTRING v15; // r8
  int AccountProvider; // eax
  unsigned int v17; // ebx
  __int64 v18; // rcx
  int v20; // eax
  struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **v21; // rdx
  __int64 v22; // rcx
  int TokenBroker; // eax
  __int64 v24; // rcx
  __int64 v25; // rbx
  int v26; // eax
  unsigned int v27; // edi
  HSTRING *v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  _DWORD *v31; // rcx
  HSTRING *v32; // rcx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // r8d
  int v36; // r9d
  IUnknown *v37; // rcx
  _DWORD *v38; // rcx
  HSTRING *v39; // rcx
  __int64 v40; // rcx
  int Tickets; // eax
  IUnknown *v42; // rcx
  _DWORD *v43; // rcx
  HSTRING *v44; // rcx
  __int64 v45; // rcx
  HSTRING v46; // rax
  IUnknown *v47; // rcx
  _DWORD *v48; // rcx
  HSTRING *v49; // rcx
  __int64 v50; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider **bIgnoreCase; // [rsp+20h] [rbp-50h]
  int bIgnoreCasea; // [rsp+20h] [rbp-50h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-50h]
  int bIgnoreCasec; // [rsp+20h] [rbp-50h]
  int v55; // [rsp+50h] [rbp-20h] BYREF
  HSTRING string[3]; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v58; // [rsp+B0h] [rbp+40h] BYREF
  int v59; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v60; // [rsp+C8h] [rbp+58h] BYREF

  v58 = a1;
  v10 = (WinStoreAuth::AuthenticationInternal *)a4;
  v12 = a8;
  *a8 = 0;
  v13 = a9;
  *a9 = 0;
  a10->lpVtbl = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, &length);
  if ( CompareStringOrdinal(StringRawBuffer, length, L"Msa", -1, 1) == 2
    || CompareStringOrdinal(StringRawBuffer, length, L"Aad", -1, 1) == 2 )
  {
    v10 = (WinStoreAuth::AuthenticationInternal *)string2;
  }
  v58 = 0;
  AccountProvider = WinStoreAuth::AuthenticationInternal::GetAccountProvider(
                      v10,
                      a5,
                      v15,
                      (struct Windows::System::IUser *)&v58,
                      bIgnoreCase);
  v17 = AccountProvider;
  if ( AccountProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)AccountProvider,
      bIgnoreCasea);
    v18 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v17;
  }
  v20 = WinStoreAuth::AuthenticationInternal::ExtractProviderType(&v58, &v59);
  v17 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCasea);
    v22 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v17;
  }
  v60 = 0;
  TokenBroker = WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
                  (WinStoreAuth::AuthenticationInternal *)&v60,
                  v21);
  v17 = TokenBroker;
  if ( TokenBroker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TokenBroker,
      bIgnoreCasea);
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v24 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v17;
  }
  a8 = 0;
  v25 = v60;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING **))(*(_QWORD *)v60 + 80LL))(v60, v58, a3, &a8);
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v26,
      bIgnoreCasea);
    v28 = a8;
    if ( a8 )
    {
      a8 = 0;
      (*((void (__fastcall **)(HSTRING *))*v28 + 2))(v28);
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v29 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    return v27;
  }
  a9 = 0;
  v30 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
          (__int64)a8,
          (__int64 *)&a9);
  v27 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v30,
      bIgnoreCasea);
    v31 = a9;
    if ( a9 )
    {
      a9 = 0;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = a8;
    if ( a8 )
    {
      a8 = 0;
      (*((void (__fastcall **)(HSTRING *))*v32 + 2))(v32);
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v33 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return v27;
  }
  a10 = 0;
  v34 = WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(&v58, 0, 0, 0, &a10);
  v27 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v34,
      bIgnoreCaseb);
    v37 = a10;
    if ( a10 )
    {
      a10 = 0;
      ((void (__fastcall *)(IUnknown *))v37->lpVtbl->Release)(v37);
    }
    v38 = a9;
    if ( a9 )
    {
      a9 = 0;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = a8;
    if ( a8 )
    {
      a8 = 0;
      (*((void (__fastcall **)(HSTRING *))*v39 + 2))(v39);
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v40 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v27;
  }
  v55 = 0;
  *(_OWORD *)string = 0;
  a7 = 0;
  Tickets = WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(
              (unsigned int)&v60,
              (unsigned int)&a10,
              v35,
              v36,
              (__int64)a9,
              (unsigned int)&v55,
              1,
              (unsigned int)&a7);
  v17 = Tickets;
  if ( Tickets < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)Tickets,
      bIgnoreCasec);
    WindowsDeleteString(string[1]);
    string[1] = 0;
    WindowsDeleteString(string[0]);
    string[0] = 0;
    v42 = a10;
    if ( a10 )
    {
      a10 = 0;
      ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
    }
    v43 = a9;
    if ( a9 )
    {
      a9 = 0;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = a8;
    if ( a8 )
    {
      a8 = 0;
      (*((void (__fastcall **)(HSTRING *))*v44 + 2))(v44);
    }
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v45 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    return v17;
  }
  v46 = string[0];
  string[0] = 0;
  *v12 = v46;
  *v13 = v55;
  WindowsDeleteString(string[1]);
  string[1] = 0;
  WindowsDeleteString(string[0]);
  string[0] = 0;
  v47 = a10;
  if ( a10 )
  {
    a10 = 0;
    ((void (__fastcall *)(IUnknown *))v47->lpVtbl->Release)(v47);
  }
  v48 = a9;
  if ( a9 )
  {
    a9 = 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = a8;
  if ( a8 )
  {
    a8 = 0;
    (*((void (__fastcall **)(HSTRING *))*v49 + 2))(v49);
  }
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  v50 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  return 0;
}

```

## disassembly

```asm
0x180040ef8  mov     [rsp-38h+arg_10], rbx
0x180040efd  mov     [rsp-38h+arg_0], rcx
0x180040f02  push    rbp
0x180040f03  push    rsi
0x180040f04  push    rdi
0x180040f05  push    r12
0x180040f07  push    r13
0x180040f09  push    r14
0x180040f0b  push    r15
0x180040f0d  mov     rbp, rsp
0x180040f10  sub     rsp, 70h
0x180040f14  mov     rbx, r9
0x180040f17  mov     r12, r8
0x180040f1a  xor     r13d, r13d
0x180040f1d  mov     rsi, [rbp+arg_38]
0x180040f21  mov     [rsi], r13
0x180040f24  mov     r14, [rbp+arg_40]
0x180040f2b  mov     [r14], r13d
0x180040f2e  mov     r15, [rbp+arg_48]
0x180040f35  mov     [r15], r13
0x180040f38  mov     [rbp+length], r13d
0x180040f3c  lea     rdx, [rbp+length]; length
0x180040f40  mov     rcx, r9; string
0x180040f43  call    cs:__imp_WindowsGetStringRawBuffer
0x180040f49  mov     rdi, rax
0x180040f4c  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180040f54  or      r9d, 0FFFFFFFFh; cchCount2
0x180040f58  lea     r8, aMsa; "Msa"
0x180040f5f  mov     edx, [rbp+length]; cchCount1
0x180040f62  mov     rcx, rax; lpString1
0x180040f65  call    cs:__imp_CompareStringOrdinal
0x180040f6b  cmp     eax, 2
0x180040f6e  jz      short loc_180040F94
0x180040f70  mov     [rsp+70h+bIgnoreCase], 1; int
0x180040f78  or      r9d, 0FFFFFFFFh; cchCount2
0x180040f7c  lea     r8, aAad_0; "Aad"
0x180040f83  mov     edx, [rbp+length]; cchCount1
0x180040f86  mov     rcx, rdi; lpString1
0x180040f89  call    cs:__imp_CompareStringOrdinal
0x180040f8f  cmp     eax, 2
0x180040f92  jnz     short loc_180040F9B
0x180040f94  mov     rbx, cs:string2
0x180040f9b  mov     [rbp+arg_0], r13
0x180040f9f  lea     r9, [rbp+arg_0]; struct Windows::System::IUser *
0x180040fa3  mov     rdx, [rbp+arg_20]; HSTRING
0x180040fa7  mov     rcx, rbx; this
0x180040faa  call    ?GetAccountProvider@AuthenticationInternal@WinStoreAuth@@YAJPEAUHSTRING__@@0PEAUIUser@System@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z; WinStoreAuth::AuthenticationInternal::GetAccountProvider(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180040faf  mov     ebx, eax
0x180040fb1  test    eax, eax
0x180040fb3  jns     short loc_180040FEF
0x180040fb5  mov     rcx, [rbp+38h]; this
0x180040fb9  mov     r9d, eax; char *
0x180040fbc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040fc3  mov     edx, 198h; void *
0x180040fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040fcd  nop
0x180040fce  mov     rcx, [rbp+arg_0]
0x180040fd2  test    rcx, rcx
0x180040fd5  jz      short loc_180040FE8
0x180040fd7  mov     [rbp+arg_0], r13
0x180040fdb  mov     rax, [rcx]
0x180040fde  mov     rax, [rax+10h]
0x180040fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fe7  nop
0x180040fe8  mov     eax, ebx
0x180040fea  jmp     loc_180041479
0x180040fef  lea     rdx, [rbp+arg_8]
0x180040ff3  lea     rcx, [rbp+arg_0]
0x180040ff7  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x180040ffc  mov     ebx, eax
0x180040ffe  test    eax, eax
0x180041000  jns     short loc_180041037
0x180041002  mov     rcx, [rbp+38h]; this
0x180041006  mov     r9d, eax; char *
0x180041009  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041010  mov     edx, 19Ch; void *
0x180041015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004101a  nop
0x18004101b  mov     rcx, [rbp+arg_0]
0x18004101f  test    rcx, rcx
0x180041022  jz      short loc_180041035
0x180041024  mov     [rbp+arg_0], r13
0x180041028  mov     rax, [rcx]
0x18004102b  mov     rax, [rax+10h]
0x18004102f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041034  nop
0x180041035  jmp     short loc_180040FE8
0x180041037  mov     [rbp+arg_18], r13
0x18004103b  lea     rcx, [rbp+arg_18]; this
0x18004103f  call    ?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)
0x180041044  mov     ebx, eax
0x180041046  test    eax, eax
0x180041048  jns     short loc_180041098
0x18004104a  mov     rcx, [rbp+38h]; this
0x18004104e  mov     r9d, eax; char *
0x180041051  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041058  mov     edx, 1A6h; void *
0x18004105d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041062  nop
0x180041063  mov     rcx, [rbp+arg_18]
0x180041067  test    rcx, rcx
0x18004106a  jz      short loc_180041079
0x18004106c  mov     rax, [rcx]
0x18004106f  mov     rax, [rax+10h]
0x180041073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041078  nop
0x180041079  mov     rcx, [rbp+arg_0]
0x18004107d  test    rcx, rcx
0x180041080  jz      short loc_180041093
0x180041082  mov     [rbp+arg_0], r13
0x180041086  mov     rax, [rcx]
0x180041089  mov     rax, [rax+10h]
0x18004108d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041092  nop
0x180041093  jmp     loc_180040FE8
0x180041098  mov     [rbp+arg_38], r13
0x18004109c  mov     rbx, [rbp+arg_18]
0x1800410a0  mov     rax, [rbx]
0x1800410a3  lea     r9, [rbp+arg_38]
0x1800410a7  mov     r8, r12
0x1800410aa  mov     rdx, [rbp+arg_0]
0x1800410ae  mov     rcx, rbx
0x1800410b1  mov     rax, [rax+50h]
0x1800410b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410ba  mov     edi, eax
0x1800410bc  test    eax, eax
0x1800410be  jns     short loc_180041129
0x1800410c0  mov     rcx, [rbp+38h]; this
0x1800410c4  mov     r9d, eax; char *
0x1800410c7  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800410ce  mov     edx, 1A9h; void *
0x1800410d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410d8  nop
0x1800410d9  mov     rcx, [rbp+arg_38]
0x1800410dd  test    rcx, rcx
0x1800410e0  jz      short loc_1800410F3
0x1800410e2  mov     [rbp+arg_38], r13
0x1800410e6  mov     rax, [rcx]
0x1800410e9  mov     rax, [rax+10h]
0x1800410ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410f2  nop
0x1800410f3  test    rbx, rbx
0x1800410f6  jz      short loc_180041108
0x1800410f8  mov     rax, [rbx]
0x1800410fb  mov     rcx, rbx
0x1800410fe  mov     rax, [rax+10h]
0x180041102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041107  nop
0x180041108  mov     rcx, [rbp+arg_0]
0x18004110c  test    rcx, rcx
0x18004110f  jz      short loc_180041122
0x180041111  mov     [rbp+arg_0], r13
0x180041115  mov     rax, [rcx]
0x180041118  mov     rax, [rax+10h]
0x18004111c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041121  nop
0x180041122  mov     eax, edi
0x180041124  jmp     loc_180041479
0x180041129  mov     [rbp+arg_40], r13
0x180041130  lea     rdx, [rbp+arg_40]
0x180041137  mov     rcx, [rbp+arg_38]
0x18004113b  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccount@Credentials@Security@Windows@@UIWebAccount@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAXK@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>>,tagCOWAIT_FLAGS,void *,ulong)
0x180041140  mov     edi, eax
0x180041142  test    eax, eax
0x180041144  jns     loc_1800411D1
0x18004114a  mov     rcx, [rbp+38h]; this
0x18004114e  mov     r9d, eax; char *
0x180041151  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041158  mov     edx, 1ACh; void *
0x18004115d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041162  nop
0x180041163  mov     rcx, [rbp+arg_40]
0x18004116a  test    rcx, rcx
0x18004116d  jz      short loc_180041183
0x18004116f  mov     [rbp+arg_40], r13
0x180041176  mov     rax, [rcx]
0x180041179  mov     rax, [rax+10h]
0x18004117d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041182  nop
0x180041183  mov     rcx, [rbp+arg_38]
0x180041187  test    rcx, rcx
0x18004118a  jz      short loc_18004119D
0x18004118c  mov     [rbp+arg_38], r13
0x180041190  mov     rax, [rcx]
0x180041193  mov     rax, [rax+10h]
0x180041197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004119c  nop
0x18004119d  test    rbx, rbx
0x1800411a0  jz      short loc_1800411B2
0x1800411a2  mov     rax, [rbx]
0x1800411a5  mov     rcx, rbx
0x1800411a8  mov     rax, [rax+10h]
0x1800411ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411b1  nop
0x1800411b2  mov     rcx, [rbp+arg_0]
0x1800411b6  test    rcx, rcx
0x1800411b9  jz      short loc_1800411CC
0x1800411bb  mov     [rbp+arg_0], r13
0x1800411bf  mov     rax, [rcx]
0x1800411c2  mov     rax, [rax+10h]
0x1800411c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411cb  nop
0x1800411cc  jmp     loc_180041122
0x1800411d1  mov     [rbp+arg_48], r13
0x1800411d8  lea     rax, [rbp+arg_48]
0x1800411df  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x1800411e4  xor     r9d, r9d
0x1800411e7  xor     r8d, r8d
0x1800411ea  xor     edx, edx
0x1800411ec  lea     rcx, [rbp+arg_0]
0x1800411f0  call    ?CreateTokenRequestHelper@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1800411f5  mov     edi, eax
0x1800411f7  test    eax, eax
0x1800411f9  jns     loc_1800412A6
0x1800411ff  mov     rcx, [rbp+38h]; this
0x180041203  mov     r9d, eax; char *
0x180041206  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18004120d  mov     edx, 1AFh; void *
0x180041212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041217  nop
0x180041218  mov     rcx, [rbp+arg_48]
0x18004121f  test    rcx, rcx
0x180041222  jz      short loc_180041238
0x180041224  mov     [rbp+arg_48], r13
0x18004122b  mov     rax, [rcx]
0x18004122e  mov     rax, [rax+10h]
0x180041232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041237  nop
0x180041238  mov     rcx, [rbp+arg_40]
0x18004123f  test    rcx, rcx
0x180041242  jz      short loc_180041258
0x180041244  mov     [rbp+arg_40], r13
0x18004124b  mov     rax, [rcx]
0x18004124e  mov     rax, [rax+10h]
0x180041252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041257  nop
0x180041258  mov     rcx, [rbp+arg_38]
0x18004125c  test    rcx, rcx
0x18004125f  jz      short loc_180041272
0x180041261  mov     [rbp+arg_38], r13
0x180041265  mov     rax, [rcx]
0x180041268  mov     rax, [rax+10h]
0x18004126c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041271  nop
0x180041272  test    rbx, rbx
0x180041275  jz      short loc_180041287
0x180041277  mov     rax, [rbx]
0x18004127a  mov     rcx, rbx
0x18004127d  mov     rax, [rax+10h]
0x180041281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041286  nop
0x180041287  mov     rcx, [rbp+arg_0]
0x18004128b  test    rcx, rcx
0x18004128e  jz      short loc_1800412A1
0x180041290  mov     [rbp+arg_0], r13
0x180041294  mov     rax, [rcx]
0x180041297  mov     rax, [rax+10h]
0x18004129b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412a0  nop
0x1800412a1  jmp     loc_180041122
0x1800412a6  mov     [rbp+var_20], r13d
0x1800412aa  xorps   xmm0, xmm0
0x1800412ad  movdqu  xmmword ptr [rbp+string], xmm0
0x1800412b2  mov     [rbp+arg_30], r13
0x1800412b6  mov     [rsp+70h+var_28], r15
0x1800412bb  lea     rax, [rbp+arg_30]
0x1800412bf  mov     [rsp+70h+var_38], rax
0x1800412c4  mov     [rsp+70h+var_40], 1
0x1800412cd  lea     rax, [rbp+var_20]
0x1800412d1  mov     [rsp+70h+var_48], rax
0x1800412d6  mov     rax, [rbp+arg_40]
0x1800412dd  mov     qword ptr [rsp+70h+bIgnoreCase], rax; int
0x1800412e2  lea     rdx, [rbp+arg_48]
0x1800412e9  lea     rcx, [rbp+arg_18]
0x1800412ed  call    ?SendTokenRequestAndGetTickets@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@W4PromptType@2@PEAUHWND__@@PEAUIWebAccount@Credentials@Security@Windows@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> const &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> const &,WinStoreAuth::PromptType,HWND__ *,Windows::Security::Credentials::IWebAccount *,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1800412f2  mov     ebx, eax
0x1800412f4  test    eax, eax
0x1800412f6  jns     loc_1800413C0
0x1800412fc  mov     rcx, [rbp+38h]; this
0x180041300  mov     r9d, eax; char *
0x180041303  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18004130a  mov     edx, 1BDh; void *
0x18004130f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041314  nop
0x180041315  mov     rcx, [rbp+string+8]; string
0x180041319  call    cs:__imp_WindowsDeleteString
0x18004131f  mov     [rbp+string+8], r13
0x180041323  mov     rcx, [rbp+string]; string
0x180041327  call    cs:__imp_WindowsDeleteString
0x18004132d  mov     [rbp+string], r13
0x180041331  mov     rcx, [rbp+arg_48]
0x180041338  test    rcx, rcx
0x18004133b  jz      short loc_180041351
0x18004133d  mov     [rbp+arg_48], r13
0x180041344  mov     rax, [rcx]
0x180041347  mov     rax, [rax+10h]
0x18004134b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041350  nop
0x180041351  mov     rcx, [rbp+arg_40]
0x180041358  test    rcx, rcx
  ... truncated ...
```
