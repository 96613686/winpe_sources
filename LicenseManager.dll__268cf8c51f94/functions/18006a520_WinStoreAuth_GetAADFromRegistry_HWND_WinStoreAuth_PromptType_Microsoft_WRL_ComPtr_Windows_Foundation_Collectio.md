# WinStoreAuth::GetAADFromRegistry(HWND__ *,WinStoreAuth::PromptType,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>> const &,WinStoreAuth::TicketsHolder &)

- ea: `0x18006a520`
- end: `0x18006a92d`
- name: `?GetAADFromRegistry@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@1@AEBV?$ComPtr@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUTicketsHolder@1@@Z`
- size: `1037`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bf58`

## callees

- `0x180004738`
- `0x180037440`
- `0x18003aa0c`
- `0x18003c298`
- `0x180042090`
- `0x1800426bc`
- `0x180061c04`
- `0x180068944`
- `0x18006a520`
- `0x18006e9e0`
- `0x1800a4984`
- `0x1800a5228`
- `0x1800a5704`
- `0x1800a6840`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a5cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006a5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a87c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a8a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a87c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a8a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a914`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinStoreAuth::GetAADFromRegistry(HSTRING a1, UINT32 a2, _QWORD *a3, _QWORD *a4)
{
  const unsigned __int16 *v6; // rdx
  WinStoreAuth::AuthenticationInternal *v7; // rcx
  HSTRING *v8; // r9
  __int64 v9; // rcx
  const WCHAR *StringRawBuffer; // rsi
  unsigned int v11; // edi
  const WCHAR *v12; // rax
  int Account; // eax
  int v14; // edi
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rdi
  int v17; // eax
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rdi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rdi
  struct WinStoreAuth::TicketHolder **v24; // rsi
  void *v25; // rcx
  HSTRING *v26; // rsi
  _QWORD *v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rcx
  int TicketForAccount; // eax
  __int64 v31; // rdx
  unsigned __int64 v32; // r8
  struct WinStoreAuth::TicketHolder **v33; // rdx
  __int64 v34; // rax
  unsigned __int64 v35; // r8
  int v37; // [rsp+28h] [rbp-59h]
  int v38; // [rsp+28h] [rbp-59h]
  HSTRING v39; // [rsp+58h] [rbp-29h] BYREF
  __int64 v40; // [rsp+60h] [rbp-21h] BYREF
  __int64 v41; // [rsp+68h] [rbp-19h] BYREF
  __int64 v42; // [rsp+70h] [rbp-11h] BYREF
  __int64 v43; // [rsp+78h] [rbp-9h] BYREF
  HSTRING string; // [rsp+80h] [rbp-1h] BYREF
  void *v45; // [rsp+88h] [rbp+7h] BYREF
  struct WinStoreAuth::TicketHolder **v46; // [rsp+90h] [rbp+Fh]
  unsigned __int64 v47; // [rsp+98h] [rbp+17h] BYREF
  _BYTE v48[56]; // [rsp+A0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  HSTRING v50; // [rsp+E8h] [rbp+67h] BYREF
  UINT32 length; // [rsp+F0h] [rbp+6Fh] BYREF

  length = a2;
  v50 = a1;
  WindowsDeleteString(0);
  string = 0;
  if ( (int)WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(
              v7,
              v6,
              (struct Windows::System::IUser *)&string,
              v8) < 0
    || !string
    || a4[1] >= 0x20u )
  {
    goto LABEL_30;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v11 = 0;
  if ( a4[1] )
  {
    v9 = 0;
    do
    {
      LODWORD(v50) = 0;
      v12 = WindowsGetStringRawBuffer(*(HSTRING *)(*a4 + 24 * v9 + 16), (UINT32 *)&v50);
      if ( CompareStringOrdinal(v12, (int)v50, StringRawBuffer, length, 1) == 2 )
        break;
      v9 = ++v11;
    }
    while ( (unsigned __int64)v11 < a4[1] );
  }
  if ( v11 != a4[1] )
    goto LABEL_30;
  v43 = 0;
  Account = WinStoreAuth::AuthenticationInternal::FindAccount(v9, string, &v43);
  v14 = Account;
  if ( Account < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)Account,
      v37);
LABEL_37:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    goto LABEL_31;
  }
  v39 = 0;
  v50 = 0;
  v41 = 0;
  Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
    &v43,
    &v41);
  v15 = v41;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 48LL);
  WindowsDeleteString(0);
  v39 = 0;
  v17 = v16(v15, &v39);
  v14 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v17,
      v37);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    WindowsDeleteString(v50);
    v50 = 0;
    WindowsDeleteString(v39);
    v39 = 0;
    goto LABEL_37;
  }
  v40 = 0;
  v18 = v43;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  v20 = v19(v18, &v40);
  v14 = v20;
  if ( v20 < 0 )
  {
    v21 = 654;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v20,
      v37);
LABEL_35:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    goto LABEL_36;
  }
  v22 = v40;
  v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
  WindowsDeleteString(v50);
  v50 = 0;
  v20 = v23(v22, &v50);
  v14 = v20;
  if ( v20 < 0 )
  {
    v21 = 655;
    goto LABEL_15;
  }
  v24 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v14 = ULongLongMult(1u, 0x18u, &v47);
  if ( v14 < 0 )
  {
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v14,
      v37);
    v33 = v24;
    goto LABEL_34;
  }
  v14 = CTCoAllocPolicy::Alloc(v25, 1u, v47, &v45);
  if ( v14 < 0 )
  {
    v24 = v46;
    goto LABEL_33;
  }
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  v26 = (HSTRING *)v45;
  v27 = (char *)v45 + 8;
  WindowsDeleteString(*((HSTRING *)v45 + 1));
  *v27 = 0;
  v38 = (int)qword_1800F2BE8;
  TicketForAccount = WinStoreAuth::AuthenticationInternal::GetTicketForAccount(v29, v28, v39, v50);
  v14 = TicketForAccount;
  if ( TicketForAccount < 0 )
  {
    v31 = 671;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TicketForAccount,
      v38);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    v33 = v46;
LABEL_34:
    WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((WinStoreAuth::AuthenticationInternal *)&v45, v33, v32);
    goto LABEL_35;
  }
  WindowsDeleteString(v26[2]);
  v26[2] = 0;
  TicketForAccount = WinStoreAuth::AuthenticationInternal::ExtractAccountId(&v43, v26 + 2);
  v14 = TicketForAccount;
  if ( TicketForAccount < 0 )
  {
    v31 = 673;
    goto LABEL_22;
  }
  WinStoreAuth::TicketHolder::TicketHolder(
    (WinStoreAuth::TicketHolder *)v48,
    (const struct WinStoreAuth::TicketHolder *)*a4);
  WinStoreAuth::TicketHolder::operator=(*a4, v26);
  v34 = a4[1];
  if ( v34 )
    WinStoreAuth::TicketHolder::operator=(*a4 + 24 * v34, v48);
  ++a4[1];
  if ( v42 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 104LL))(*a3);
  WinStoreAuth::TicketHolder::~TicketHolder((WinStoreAuth::TicketHolder *)v48);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((WinStoreAuth::AuthenticationInternal *)&v45, v46, v35);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  WindowsDeleteString(v50);
  v50 = 0;
  WindowsDeleteString(v39);
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
LABEL_30:
  v14 = 0;
LABEL_31:
  WindowsDeleteString(string);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18006a520  mov     rax, rsp
0x18006a523  mov     [rax+18h], rsi
0x18006a527  mov     [rax+10h], edx
0x18006a52a  mov     [rax+8], rcx
0x18006a52e  push    rbp
0x18006a52f  push    rdi
0x18006a530  push    r12
0x18006a532  push    r14
0x18006a534  push    r15
0x18006a536  lea     rbp, [rax-5Fh]
0x18006a53a  sub     rsp, 0B0h
0x18006a541  mov     r14, r9
0x18006a544  mov     r15, r8
0x18006a547  xor     ecx, ecx; string
0x18006a549  call    cs:__imp_WindowsDeleteString
0x18006a54f  xor     r12d, r12d
0x18006a552  mov     [rbp+57h+string], r12
0x18006a556  lea     r8, [rbp+57h+string]; struct Windows::System::IUser *
0x18006a55a  call    ?FetchStoreAccountIdFromRegistry@AuthenticationInternal@WinStoreAuth@@YAJPEBGPEAUIUser@System@Windows@@PEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(ushort const *,Windows::System::IUser *,HSTRING__ * *)
0x18006a55f  test    eax, eax
0x18006a561  js      loc_18006A89D
0x18006a567  cmp     [rbp+57h+string], r12
0x18006a56b  jz      loc_18006A89D
0x18006a571  cmp     qword ptr [r14+8], 20h ; ' '
0x18006a576  jnb     loc_18006A89D
0x18006a57c  mov     [rbp+57h+length], r12d
0x18006a580  lea     rdx, [rbp+57h+length]; length
0x18006a584  mov     rcx, [rbp+57h+string]; string
0x18006a588  call    cs:__imp_WindowsGetStringRawBuffer
0x18006a58e  mov     rsi, rax
0x18006a591  mov     edi, r12d
0x18006a594  cmp     [r14+8], r12
0x18006a598  jbe     short loc_18006A5E1
0x18006a59a  mov     ecx, r12d
0x18006a59d  mov     dword ptr [rbp+57h+arg_0], r12d
0x18006a5a1  lea     r8, [rcx+rcx*2]
0x18006a5a5  mov     rcx, [r14]
0x18006a5a8  lea     rdx, [rbp+57h+arg_0]; length
0x18006a5ac  mov     rcx, [rcx+r8*8+10h]; string
0x18006a5b1  call    cs:__imp_WindowsGetStringRawBuffer
0x18006a5b7  mov     dword ptr [rsp+20h], 1; int
0x18006a5bf  mov     r9d, [rbp+57h+length]; cchCount2
0x18006a5c3  mov     r8, rsi; lpString2
0x18006a5c6  mov     edx, dword ptr [rbp+57h+arg_0]; cchCount1
0x18006a5c9  mov     rcx, rax; lpString1
0x18006a5cc  call    cs:__imp_CompareStringOrdinal
0x18006a5d2  cmp     eax, 2
0x18006a5d5  jz      short loc_18006A5E1
0x18006a5d7  inc     edi
0x18006a5d9  mov     ecx, edi
0x18006a5db  cmp     rcx, [r14+8]
0x18006a5df  jb      short loc_18006A59D
0x18006a5e1  mov     eax, edi
0x18006a5e3  cmp     rax, [r14+8]
0x18006a5e7  jnz     loc_18006A89D
0x18006a5ed  mov     [rbp+57h+var_60], r12
0x18006a5f1  lea     r8, [rbp+57h+var_60]
0x18006a5f5  mov     rdx, [rbp+57h+string]
0x18006a5f9  call    ?FindAccount@AuthenticationInternal@WinStoreAuth@@YAJW4AccountProviderType@2@PEAUHSTRING__@@PEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::FindAccount(WinStoreAuth::AccountProviderType,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)
0x18006a5fe  mov     edi, eax
0x18006a600  test    eax, eax
0x18006a602  jns     short loc_18006A621
0x18006a604  mov     rcx, [rbp+5Fh]; this
0x18006a608  mov     r9d, eax; char *
0x18006a60b  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006a612  mov     edx, 286h; void *
0x18006a617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a61c  jmp     loc_18006A91E
0x18006a621  mov     [rbp+57h+var_80], r12
0x18006a625  mov     [rbp+57h+arg_0], r12
0x18006a629  mov     [rbp+57h+var_70], r12
0x18006a62d  lea     rdx, [rbp+57h+var_70]
0x18006a631  lea     rcx, [rbp+57h+var_60]
0x18006a635  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18006a63a  mov     rsi, [rbp+57h+var_70]
0x18006a63e  mov     rax, [rsi]
0x18006a641  mov     rdi, [rax+30h]
0x18006a645  mov     rcx, [rbp+57h+var_80]; string
0x18006a649  call    cs:__imp_WindowsDeleteString
0x18006a64f  mov     [rbp+57h+var_80], r12
0x18006a653  lea     rdx, [rbp+57h+var_80]
0x18006a657  mov     rcx, rsi
0x18006a65a  mov     rax, rdi
0x18006a65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a662  mov     edi, eax
0x18006a664  test    eax, eax
0x18006a666  jns     short loc_18006A685
0x18006a668  mov     rcx, [rbp+5Fh]; this
0x18006a66c  mov     r9d, eax; char *
0x18006a66f  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006a676  mov     edx, 28Ch; void *
0x18006a67b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a680  jmp     loc_18006A8F8
0x18006a685  mov     [rbp+57h+var_78], r12
0x18006a689  mov     rsi, [rbp+57h+var_60]
0x18006a68d  mov     rax, [rsi]
0x18006a690  mov     rdi, [rax+30h]
0x18006a694  lea     rcx, [rbp+57h+var_78]
0x18006a698  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a69d  lea     rdx, [rbp+57h+var_78]
0x18006a6a1  mov     rcx, rsi
0x18006a6a4  mov     rax, rdi
0x18006a6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6ac  mov     edi, eax
0x18006a6ae  test    eax, eax
0x18006a6b0  jns     short loc_18006A6CF
0x18006a6b2  mov     edx, 28Eh; void *
0x18006a6b7  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006a6be  mov     r9d, eax; char *
0x18006a6c1  mov     rcx, [rbp+5Fh]; this
0x18006a6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a6ca  jmp     loc_18006A8EE
0x18006a6cf  mov     rsi, [rbp+57h+var_78]
0x18006a6d3  mov     rax, [rsi]
0x18006a6d6  mov     rdi, [rax+30h]
0x18006a6da  mov     rcx, [rbp+57h+arg_0]; string
0x18006a6de  call    cs:__imp_WindowsDeleteString
0x18006a6e4  mov     [rbp+57h+arg_0], r12
0x18006a6e8  lea     rdx, [rbp+57h+arg_0]
0x18006a6ec  mov     rcx, rsi
0x18006a6ef  mov     rax, rdi
0x18006a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6f7  mov     edi, eax
0x18006a6f9  test    eax, eax
0x18006a6fb  jns     short loc_18006A704
0x18006a6fd  mov     edx, 28Fh
0x18006a702  jmp     short loc_18006A6B7
0x18006a704  mov     rsi, r12
0x18006a707  mov     [rbp+57h+var_48], r12
0x18006a70b  mov     [rbp+57h+var_50], r12
0x18006a70f  mov     [rbp+57h+var_40], r12
0x18006a713  lea     r8, [rbp+57h+var_40]; unsigned __int64 *
0x18006a717  mov     edx, 18h; unsigned __int64
0x18006a71c  lea     ecx, [rdx-17h]; unsigned __int64
0x18006a71f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006a724  mov     edi, eax
0x18006a726  test    eax, eax
0x18006a728  js      loc_18006A8C8
0x18006a72e  lea     r9, [rbp+57h+var_50]; void **
0x18006a732  mov     r8, [rbp+57h+var_40]; unsigned __int64
0x18006a736  mov     edx, 1; unsigned int
0x18006a73b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18006a740  mov     edi, eax
0x18006a742  test    eax, eax
0x18006a744  js      loc_18006A8C4
0x18006a74a  mov     [rbp+57h+var_68], r12
0x18006a74e  lea     rcx, [rbp+57h+var_68]
0x18006a752  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a757  mov     rsi, [rbp+57h+var_50]
0x18006a75b  lea     rdi, [rsi+8]
0x18006a75f  mov     rcx, [rdi]; string
0x18006a762  call    cs:__imp_WindowsDeleteString
0x18006a768  mov     [rdi], r12
0x18006a76b  lea     rax, [rbp+57h+var_68]
0x18006a76f  mov     [rsp+48h], rax
0x18006a774  mov     [rsp+0D0h+var_90], rsi
0x18006a779  mov     [rsp+0D0h+var_98], rdi
0x18006a77e  mov     rax, cs:qword_1800F2BE8
0x18006a785  mov     [rsp+20h], rax; int
0x18006a78a  mov     r9, [rbp+57h+arg_0]
0x18006a78e  mov     r8, [rbp+57h+var_80]
0x18006a792  call    ?GetTicketForAccount@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@22_NPEAUIUser@System@Windows@@PEAPEAU5@PEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z; WinStoreAuth::AuthenticationInternal::GetTicketForAccount(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool,Windows::System::IUser *,HSTRING__ * *,WinStoreAuth::AccountProviderType *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x18006a797  mov     edi, eax
0x18006a799  test    eax, eax
0x18006a79b  jns     short loc_18006A7C9
0x18006a79d  mov     edx, 29Fh; void *
0x18006a7a2  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006a7a9  mov     r9d, eax; char *
0x18006a7ac  mov     rcx, [rbp+5Fh]; this
0x18006a7b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a7b5  nop
0x18006a7b6  lea     rcx, [rbp+57h+var_68]
0x18006a7ba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a7bf  nop
0x18006a7c0  mov     rdx, [rbp+57h+var_48]
0x18006a7c4  jmp     loc_18006A8E4
0x18006a7c9  lea     rdi, [rsi+10h]
0x18006a7cd  mov     rcx, [rdi]; string
0x18006a7d0  call    cs:__imp_WindowsDeleteString
0x18006a7d6  mov     [rdi], r12
0x18006a7d9  mov     rdx, rdi
0x18006a7dc  lea     rcx, [rbp+57h+var_60]
0x18006a7e0  call    ?ExtractAccountId@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@PEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::ExtractAccountId(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> const &,HSTRING__ * *)
0x18006a7e5  mov     edi, eax
0x18006a7e7  test    eax, eax
0x18006a7e9  jns     short loc_18006A7F2
0x18006a7eb  mov     edx, 2A1h
0x18006a7f0  jmp     short loc_18006A7A2
0x18006a7f2  mov     rdx, [r14]; struct WinStoreAuth::TicketHolder *
0x18006a7f5  lea     rcx, [rbp+57h+var_38]; this
0x18006a7f9  call    ??0TicketHolder@WinStoreAuth@@QEAA@AEBU01@@Z; WinStoreAuth::TicketHolder::TicketHolder(WinStoreAuth::TicketHolder const &)
0x18006a7fe  mov     rdx, rsi
0x18006a801  mov     rcx, [r14]
0x18006a804  call    ??4TicketHolder@WinStoreAuth@@QEAAAEAU01@AEBU01@@Z; WinStoreAuth::TicketHolder::operator=(WinStoreAuth::TicketHolder const &)
0x18006a809  mov     rax, [r14+8]
0x18006a80d  test    rax, rax
0x18006a810  jz      short loc_18006A826
0x18006a812  lea     rcx, [rax+rax*2]
0x18006a816  mov     rax, [r14]
0x18006a819  lea     rcx, [rax+rcx*8]
0x18006a81d  lea     rdx, [rbp+57h+var_38]
0x18006a821  call    ??4TicketHolder@WinStoreAuth@@QEAAAEAU01@AEBU01@@Z; WinStoreAuth::TicketHolder::operator=(WinStoreAuth::TicketHolder const &)
0x18006a826  inc     qword ptr [r14+8]
0x18006a82a  mov     rdx, [rbp+57h+var_68]
0x18006a82e  test    rdx, rdx
0x18006a831  jz      short loc_18006A842
0x18006a833  mov     rcx, [r15]
0x18006a836  mov     rax, [rcx]
0x18006a839  mov     rax, [rax+68h]
0x18006a83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a842  lea     rcx, [rbp+57h+var_38]; this
0x18006a846  call    ??1TicketHolder@WinStoreAuth@@QEAA@XZ; WinStoreAuth::TicketHolder::~TicketHolder(void)
0x18006a84b  nop
0x18006a84c  lea     rcx, [rbp+57h+var_68]
0x18006a850  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a855  nop
0x18006a856  mov     rdx, [rbp+57h+var_48]; struct WinStoreAuth::TicketHolder **
0x18006a85a  lea     rcx, [rbp+57h+var_50]; this
0x18006a85e  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x18006a863  nop
0x18006a864  lea     rcx, [rbp+57h+var_78]
0x18006a868  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a86d  nop
0x18006a86e  lea     rcx, [rbp+57h+var_70]
0x18006a872  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a877  nop
0x18006a878  mov     rcx, [rbp+57h+arg_0]; string
0x18006a87c  call    cs:__imp_WindowsDeleteString
0x18006a882  mov     [rbp+57h+arg_0], r12
0x18006a886  mov     rcx, [rbp+57h+var_80]; string
0x18006a88a  call    cs:__imp_WindowsDeleteString
0x18006a890  mov     [rbp+57h+var_80], r12
0x18006a894  lea     rcx, [rbp+57h+var_60]
0x18006a898  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a89d  mov     edi, r12d
0x18006a8a0  mov     rcx, [rbp+57h+string]; string
0x18006a8a4  call    cs:__imp_WindowsDeleteString
0x18006a8aa  mov     eax, edi
0x18006a8ac  mov     rsi, [rsp+0D0h+arg_10]
0x18006a8b4  add     rsp, 0B0h
0x18006a8bb  pop     r15
0x18006a8bd  pop     r14
0x18006a8bf  pop     r12
0x18006a8c1  pop     rdi
0x18006a8c2  pop     rbp
0x18006a8c3  retn
0x18006a8c4  mov     rsi, [rbp+57h+var_48]
0x18006a8c8  mov     rcx, [rbp+5Fh]; this
0x18006a8cc  mov     r9d, edi; char *
0x18006a8cf  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006a8d6  mov     edx, 292h; void *
0x18006a8db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a8e0  nop
0x18006a8e1  mov     rdx, rsi; struct WinStoreAuth::TicketHolder **
0x18006a8e4  lea     rcx, [rbp+57h+var_50]; this
0x18006a8e8  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x18006a8ed  nop
0x18006a8ee  lea     rcx, [rbp+57h+var_78]
0x18006a8f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a8f7  nop
0x18006a8f8  lea     rcx, [rbp+57h+var_70]
0x18006a8fc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a901  nop
0x18006a902  mov     rcx, [rbp+57h+arg_0]; string
0x18006a906  call    cs:__imp_WindowsDeleteString
0x18006a90c  mov     [rbp+57h+arg_0], r12
0x18006a910  mov     rcx, [rbp+57h+var_80]; string
0x18006a914  call    cs:__imp_WindowsDeleteString
0x18006a91a  mov     [rbp+57h+var_80], r12
0x18006a91e  lea     rcx, [rbp+57h+var_60]
0x18006a922  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006a927  jmp     loc_18006A8A0
```
