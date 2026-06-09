# Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(Windows::Foundation::IUriRuntimeClass *,HSTRING__ * *)

- ea: `0x1800332f8`
- end: `0x180033560`
- name: `?GetApplicationPfnForLookup@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUriRuntimeClass@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, HSTRING *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002f450`
- `0x180033800`
- `0x180087800`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800332f8`
- `0x180033568`
- `0x180033600`
- `0x1800337b0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003343c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003351e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003352e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003353e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003343c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003351e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003352e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003353e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800333fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800333fb`

## string_xrefs

- `0x18003338c`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033421`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18003346f`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x1800334ab`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033504`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        HSTRING *a3)
{
  int MediumCallerUri; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  struct Windows::Foundation::IUriRuntimeClass *v9; // rcx
  HRESULT v11; // eax
  int v12; // eax
  unsigned int v13; // edi
  struct Windows::Foundation::IUriRuntimeClass *v14; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v15; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v16; // rcx
  HSTRING v17; // rbx
  HRESULT v18; // eax
  HSTRING newString; // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v22; // [rsp+60h] [rbp+30h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v23; // [rsp+68h] [rbp+38h] BYREF

  v23 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  MediumCallerUri = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetMediumCallerUri(&v23);
  v6 = MediumCallerUri;
  if ( MediumCallerUri < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)MediumCallerUri,
      (int)newString);
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v6;
  }
  v22 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, Windows::Internal::Security::Authentication::TokenBroker *, char *))(*(_QWORD *)v23 + 168LL))(
         v23,
         this,
         &v22);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)v7,
      (int)newString);
    v15 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v6;
  }
  newString = 0;
  string = 0;
  if ( v22 )
  {
    v11 = WindowsCreateString(L"NO_APPLICATION", 0xEu, &string);
    v12 = Windows::Internal::String::FreeAndAssignOnSuccess(v11, string, &newString);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)v12,
        (int)newString);
      if ( newString )
        WindowsDeleteString(newString);
      v14 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return v13;
    }
  }
  else
  {
    v8 = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromUri(
           (Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *)&string,
           this);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)v8,
        (int)newString);
      if ( string )
        WindowsDeleteString(string);
      if ( newString )
        WindowsDeleteString(newString);
      v9 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return v6;
    }
    v17 = string;
    v18 = WindowsDuplicateString(string, &newString);
    v13 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)v18,
        (int)newString);
      if ( v17 )
        WindowsDeleteString(v17);
      if ( newString )
        WindowsDeleteString(newString);
      goto LABEL_25;
    }
    if ( v17 )
      WindowsDeleteString(v17);
  }
  *(_QWORD *)a2 = newString;
  newString = 0;
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  return v13;
}

```

## disassembly

```asm
0x1800332f8  mov     [rsp-18h+arg_0], rbx
0x1800332fd  push    rbp
0x1800332fe  push    rsi
0x1800332ff  push    rdi
0x180033300  mov     rbp, rsp
0x180033303  sub     rsp, 30h
0x180033307  mov     rsi, rdx
0x18003330a  mov     rdi, rcx
0x18003330d  mov     [rbp+arg_18], 0
0x180033315  lea     rcx, [rbp+arg_18]
0x180033319  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003331e  lea     rcx, [rbp+arg_18]; struct Windows::Foundation::IUriRuntimeClass **
0x180033322  call    ?GetMediumCallerUri@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@SAJPEAPEAUIUriRuntimeClass@Foundation@6@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetMediumCallerUri(Windows::Foundation::IUriRuntimeClass * *)
0x180033327  mov     ebx, eax
0x180033329  test    eax, eax
0x18003332b  js      loc_1800334A4
0x180033331  mov     [rbp+arg_10], 0
0x180033335  mov     rcx, [rbp+arg_18]
0x180033339  mov     rax, [rcx]
0x18003333c  lea     r8, [rbp+arg_10]
0x180033340  mov     rdx, rdi
0x180033343  mov     rax, [rax+0A8h]
0x18003334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003334f  mov     ebx, eax
0x180033351  test    eax, eax
0x180033353  js      loc_180033468
0x180033359  mov     [rbp+newString], 0
0x180033361  mov     [rbp+string], 0
0x180033369  cmp     [rbp+arg_10], 0
0x18003336d  jnz     short loc_1800333EB
0x18003336f  mov     rdx, rdi; struct Windows::Foundation::IUriRuntimeClass *
0x180033372  lea     rcx, [rbp+string]; this
0x180033376  call    ?InitializeFromUri@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUriRuntimeClass@Foundation@6@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromUri(Windows::Foundation::IUriRuntimeClass *)
0x18003337b  mov     ebx, eax
0x18003337d  test    eax, eax
0x18003337f  jns     loc_180033546
0x180033385  mov     rcx, [rbp+18h]; this
0x180033389  mov     r9d, eax; char *
0x18003338c  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033393  mov     edx, 114h; void *
0x180033398  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003339d  nop
0x18003339e  mov     rcx, [rbp+string]; string
0x1800333a2  test    rcx, rcx
0x1800333a5  jz      short loc_1800333AE
0x1800333a7  call    cs:__imp_WindowsDeleteString
0x1800333ad  nop
0x1800333ae  mov     rcx, [rbp+newString]; string
0x1800333b2  test    rcx, rcx
0x1800333b5  jz      short loc_1800333BE
0x1800333b7  call    cs:__imp_WindowsDeleteString
0x1800333bd  nop
0x1800333be  mov     rcx, [rbp+arg_18]
0x1800333c2  test    rcx, rcx
0x1800333c5  jz      short loc_1800333DC
0x1800333c7  mov     [rbp+arg_18], 0
0x1800333cf  mov     rax, [rcx]
0x1800333d2  mov     rax, [rax+10h]
0x1800333d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333db  nop
0x1800333dc  mov     eax, ebx
0x1800333de  mov     rbx, [rsp+30h+arg_0]
0x1800333e3  add     rsp, 30h
0x1800333e7  pop     rdi
0x1800333e8  pop     rsi
0x1800333e9  pop     rbp
0x1800333ea  retn
0x1800333eb  lea     r8, [rbp+string]; string
0x1800333ef  mov     edx, 0Eh; length
0x1800333f4  lea     rcx, aNoApplication; "NO_APPLICATION"
0x1800333fb  call    cs:__imp_WindowsCreateString
0x180033401  lea     r8, [rbp+newString]; HSTRING *
0x180033405  mov     rdx, [rbp+string]; HSTRING
0x180033409  mov     ecx, eax; int
0x18003340b  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180033410  mov     edi, eax
0x180033412  test    eax, eax
0x180033414  jns     loc_1800334E0
0x18003341a  mov     rcx, [rbp+18h]; this
0x18003341e  mov     r9d, eax; char *
0x180033421  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033428  mov     edx, 10Fh; void *
0x18003342d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033432  nop
0x180033433  mov     rcx, [rbp+newString]; string
0x180033437  test    rcx, rcx
0x18003343a  jz      short loc_180033443
0x18003343c  call    cs:__imp_WindowsDeleteString
0x180033442  nop
0x180033443  mov     rcx, [rbp+arg_18]
0x180033447  test    rcx, rcx
0x18003344a  jz      short loc_180033461
0x18003344c  mov     [rbp+arg_18], 0
0x180033454  mov     rax, [rcx]
0x180033457  mov     rax, [rax+10h]
0x18003345b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033460  nop
0x180033461  mov     eax, edi
0x180033463  jmp     loc_1800333DE
0x180033468  mov     rcx, [rbp+18h]; this
0x18003346c  mov     r9d, ebx; char *
0x18003346f  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033476  mov     edx, 109h; void *
0x18003347b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033480  nop
0x180033481  mov     rcx, [rbp+arg_18]
0x180033485  test    rcx, rcx
0x180033488  jz      short loc_18003349F
0x18003348a  mov     [rbp+arg_18], 0
0x180033492  mov     rax, [rcx]
0x180033495  mov     rax, [rax+10h]
0x180033499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003349e  nop
0x18003349f  jmp     loc_1800333DC
0x1800334a4  mov     rcx, [rbp+18h]; this
0x1800334a8  mov     r9d, ebx; char *
0x1800334ab  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800334b2  mov     edx, 106h; void *
0x1800334b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334bc  nop
0x1800334bd  mov     rcx, [rbp+arg_18]
0x1800334c1  test    rcx, rcx
0x1800334c4  jz      short loc_1800334DB
0x1800334c6  mov     [rbp+arg_18], 0
0x1800334ce  mov     rax, [rcx]
0x1800334d1  mov     rax, [rax+10h]
0x1800334d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334da  nop
0x1800334db  jmp     loc_1800333DC
0x1800334e0  mov     rax, [rbp+newString]
0x1800334e4  mov     [rsi], rax
0x1800334e7  mov     [rbp+newString], 0
0x1800334ef  lea     rcx, [rbp+arg_18]
0x1800334f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800334f8  jmp     loc_180033461
0x1800334fd  mov     rcx, [rbp+18h]; this
0x180033501  mov     r9d, eax; char *
0x180033504  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18003350b  mov     edx, 115h; void *
0x180033510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033515  nop
0x180033516  test    rbx, rbx
0x180033519  jz      short loc_180033525
0x18003351b  mov     rcx, rbx; string
0x18003351e  call    cs:__imp_WindowsDeleteString
0x180033524  nop
0x180033525  mov     rcx, [rbp+newString]; string
0x180033529  test    rcx, rcx
0x18003352c  jz      short loc_1800334EF
0x18003352e  call    cs:__imp_WindowsDeleteString
0x180033534  jmp     short loc_1800334EF
0x180033536  test    rbx, rbx
0x180033539  jz      short loc_1800334E0
0x18003353b  mov     rcx, rbx; string
0x18003353e  call    cs:__imp_WindowsDeleteString
0x180033544  jmp     short loc_1800334E0
0x180033546  lea     rdx, [rbp+newString]; newString
0x18003354a  mov     rbx, [rbp+string]
0x18003354e  mov     rcx, rbx; string
0x180033551  call    cs:__imp_WindowsDuplicateString
0x180033557  mov     edi, eax
0x180033559  test    eax, eax
0x18003355b  jns     short loc_180033536
0x18003355d  jmp     short loc_1800334FD
```
