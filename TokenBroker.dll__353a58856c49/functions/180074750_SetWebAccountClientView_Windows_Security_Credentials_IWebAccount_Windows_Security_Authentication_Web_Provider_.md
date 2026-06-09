# SetWebAccountClientView(Windows::Security::Credentials::IWebAccount *,Windows::Security::Authentication::Web::Provider::IWebAccountClientView *)

- ea: `0x180074750`
- end: `0x18007496f`
- name: `?SetWebAccountClientView@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUIWebAccountClientView@Provider@Web@Authentication@34@@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e33a0`
- `0x1800e3420`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180033600`
- `0x18004fdbc`
- `0x1800743a0`
- `0x180074750`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007486e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007486e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007489c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074942`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007489c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800748ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074942`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800748e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800748e4`

## string_xrefs

- `0x1800747af`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800747f9`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074831`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074881`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074918`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SetWebAccountClientView(
        struct Windows::Security::Credentials::IWebAccount *a1,
        struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *, struct Windows::Foundation::IUriRuntimeClass **); // rbx
  int v7; // eax
  int v8; // eax
  HSTRING v9; // rbx
  HRESULT v10; // eax
  HRESULT v11; // esi
  int v12; // edi
  __int64 v13; // rdx
  BOOL IsStringEmpty; // eax
  HSTRING v15; // r9
  struct Windows::Foundation::IUriRuntimeClass *v17; // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  int v20; // [rsp+68h] [rbp+38h] BYREF
  HSTRING v21; // [rsp+70h] [rbp+40h] BYREF
  HSTRING newString; // [rsp+78h] [rbp+48h] BYREF

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &word_180158106,
      0,
      0);
  v20 = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *, int *))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v20);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v17 = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    v7 = v6(a2, &v17);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBF,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v7,
        (int)v17);
LABEL_30:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      return v5;
    }
    string = 0;
    v8 = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromUri(
           (Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *)&string,
           v17);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC1,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v8,
        (int)v17);
      if ( string )
        WindowsDeleteString(string);
      goto LABEL_30;
    }
    newString = 0;
    v9 = string;
    v10 = WindowsDuplicateString(string, &newString);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC3,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v10,
        (int)v17);
      if ( newString )
        WindowsDeleteString(newString);
      if ( v9 )
        WindowsDeleteString(v9);
      v5 = v11;
      goto LABEL_30;
    }
    v21 = 0;
    v12 = (*(__int64 (__fastcall **)(struct Windows::Security::Authentication::Web::Provider::IWebAccountClientView *, HSTRING *))(*(_QWORD *)a2 + 64LL))(
            a2,
            &v21);
    if ( v12 >= 0 )
    {
      IsStringEmpty = WindowsIsStringEmpty(v21);
      v15 = v21;
      if ( IsStringEmpty )
        v15 = 0;
      v12 = SetWebAccountClientView(a1, newString, v20 == 1, v15);
      if ( v12 >= 0 )
        goto LABEL_23;
      v13 = 3276;
    }
    else
    {
      v13 = 3270;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v12,
      (int)v17);
LABEL_23:
    if ( v21 )
      WindowsDeleteString(v21);
    if ( newString )
      WindowsDeleteString(newString);
    if ( v9 )
      WindowsDeleteString(v9);
    v5 = v12;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCBB,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)v4,
    (int)v17);
  return v5;
}

```

## disassembly

```asm
0x180074750  push    rbp
0x180074752  push    rbx
0x180074753  push    rsi
0x180074754  push    rdi
0x180074755  push    r14
0x180074757  mov     rbp, rsp
0x18007475a  sub     rsp, 30h
0x18007475e  mov     rdi, rdx
0x180074761  mov     r14, rcx
0x180074764  mov     eax, cs:dword_180175000
0x18007476a  cmp     eax, 4
0x18007476d  jbe     short loc_180074788
0x18007476f  xor     r9d, r9d
0x180074772  xor     r8d, r8d
0x180074775  lea     rdx, word_180158106
0x18007477c  lea     rcx, dword_180175000
0x180074783  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180074788  mov     [rbp+arg_8], 0
0x18007478f  mov     rax, [rdi]
0x180074792  lea     rdx, [rbp+arg_8]
0x180074796  mov     rcx, rdi
0x180074799  mov     rax, [rax+38h]
0x18007479d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747a2  mov     ebx, eax
0x1800747a4  test    eax, eax
0x1800747a6  jns     short loc_1800747C5
0x1800747a8  mov     rcx, [rbp+28h]; this
0x1800747ac  mov     r9d, eax; char *
0x1800747af  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800747b6  mov     edx, 0CBBh; void *
0x1800747bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800747c0  jmp     loc_180074962
0x1800747c5  mov     [rbp+var_10], 0
0x1800747cd  mov     rax, [rdi]
0x1800747d0  mov     rbx, [rax+30h]
0x1800747d4  lea     rcx, [rbp+var_10]
0x1800747d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800747dd  lea     rdx, [rbp+var_10]
0x1800747e1  mov     rcx, rdi
0x1800747e4  mov     rax, rbx
0x1800747e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747ec  mov     ebx, eax
0x1800747ee  test    eax, eax
0x1800747f0  jns     short loc_18007480F
0x1800747f2  mov     rcx, [rbp+28h]; this
0x1800747f6  mov     r9d, eax; char *
0x1800747f9  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074800  mov     edx, 0CBFh; void *
0x180074805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007480a  jmp     loc_180074959
0x18007480f  mov     [rbp+string], 0
0x180074817  mov     rdx, [rbp+var_10]; struct Windows::Foundation::IUriRuntimeClass *
0x18007481b  lea     rcx, [rbp+string]; this
0x18007481f  call    ?InitializeFromUri@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUriRuntimeClass@Foundation@6@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromUri(Windows::Foundation::IUriRuntimeClass *)
0x180074824  mov     ebx, eax
0x180074826  test    eax, eax
0x180074828  jns     short loc_18007485B
0x18007482a  mov     rcx, [rbp+28h]; this
0x18007482e  mov     r9d, eax; char *
0x180074831  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074838  mov     edx, 0CC1h; void *
0x18007483d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074842  nop
0x180074843  mov     rcx, [rbp+string]; string
0x180074847  test    rcx, rcx
0x18007484a  jz      loc_180074959
0x180074850  call    cs:__imp_WindowsDeleteString
0x180074856  jmp     loc_180074959
0x18007485b  mov     [rbp+newString], 0
0x180074863  lea     rdx, [rbp+newString]; newString
0x180074867  mov     rbx, [rbp+string]
0x18007486b  mov     rcx, rbx; string
0x18007486e  call    cs:__imp_WindowsDuplicateString
0x180074874  mov     esi, eax
0x180074876  test    eax, eax
0x180074878  jns     short loc_1800748B8
0x18007487a  mov     rcx, [rbp+28h]; this
0x18007487e  mov     r9d, eax; char *
0x180074881  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074888  mov     edx, 0CC3h; void *
0x18007488d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074892  nop
0x180074893  mov     rcx, [rbp+newString]; string
0x180074897  test    rcx, rcx
0x18007489a  jz      short loc_1800748A3
0x18007489c  call    cs:__imp_WindowsDeleteString
0x1800748a2  nop
0x1800748a3  test    rbx, rbx
0x1800748a6  jz      short loc_1800748B1
0x1800748a8  mov     rcx, rbx; string
0x1800748ab  call    cs:__imp_WindowsDeleteString
0x1800748b1  mov     ebx, esi
0x1800748b3  jmp     loc_180074959
0x1800748b8  mov     [rbp+arg_10], 0
0x1800748c0  mov     rax, [rdi]
0x1800748c3  lea     rdx, [rbp+arg_10]
0x1800748c7  mov     rcx, rdi
0x1800748ca  mov     rax, [rax+40h]
0x1800748ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800748d3  mov     edi, eax
0x1800748d5  test    eax, eax
0x1800748d7  jns     short loc_1800748E0
0x1800748d9  mov     edx, 0CC6h
0x1800748de  jmp     short loc_180074915
0x1800748e0  mov     rcx, [rbp+arg_10]; string
0x1800748e4  call    cs:__imp_WindowsIsStringEmpty
0x1800748ea  mov     r9, [rbp+arg_10]
0x1800748ee  xor     ecx, ecx
0x1800748f0  test    eax, eax
0x1800748f2  cmovnz  r9, rcx; HSTRING
0x1800748f6  cmp     [rbp+arg_8], 1
0x1800748fa  setz    r8b; bool
0x1800748fe  mov     rdx, [rbp+newString]; string
0x180074902  mov     rcx, r14; struct Windows::Security::Credentials::IWebAccount *
0x180074905  call    ?SetWebAccountClientView@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUHSTRING__@@_N1@Z; SetWebAccountClientView(Windows::Security::Credentials::IWebAccount *,HSTRING__ *,bool,HSTRING__ *)
0x18007490a  mov     edi, eax
0x18007490c  test    eax, eax
0x18007490e  jns     short loc_180074929
0x180074910  mov     edx, 0CCCh; void *
0x180074915  mov     r9d, edi; char *
0x180074918  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007491f  mov     rcx, [rbp+28h]; this
0x180074923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074928  nop
0x180074929  mov     rcx, [rbp+arg_10]; string
0x18007492d  test    rcx, rcx
0x180074930  jz      short loc_180074939
0x180074932  call    cs:__imp_WindowsDeleteString
0x180074938  nop
0x180074939  mov     rcx, [rbp+newString]; string
0x18007493d  test    rcx, rcx
0x180074940  jz      short loc_180074949
0x180074942  call    cs:__imp_WindowsDeleteString
0x180074948  nop
0x180074949  test    rbx, rbx
0x18007494c  jz      short loc_180074957
0x18007494e  mov     rcx, rbx; string
0x180074951  call    cs:__imp_WindowsDeleteString
0x180074957  mov     ebx, edi
0x180074959  lea     rcx, [rbp+var_10]
0x18007495d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074962  mov     eax, ebx
0x180074964  add     rsp, 30h
0x180074968  pop     r14
0x18007496a  pop     rdi
0x18007496b  pop     rsi
0x18007496c  pop     rbx
0x18007496d  pop     rbp
0x18007496e  retn
```
