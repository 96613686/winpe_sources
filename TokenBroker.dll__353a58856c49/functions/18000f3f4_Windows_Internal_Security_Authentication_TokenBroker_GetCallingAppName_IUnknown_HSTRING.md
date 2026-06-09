# Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)

- ea: `0x18000f3f4`
- end: `0x18000f8e2`
- name: `?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct IUnknown *, HSTRING *)`
- caller_count: `12`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e390`
- `0x180023910`
- `0x18008169c`
- `0x1800aff38`
- `0x1800b048c`
- `0x1800c3708`
- `0x1800c38d8`
- `0x1800c42c8`
- `0x1800cf4f0`
- `0x1800cf66c`
- `0x1800cf824`
- `0x1800cf9dc`

## callees

- `0x18000bd40`
- `0x18000d250`
- `0x18000f0b0`
- `0x18000f3f4`
- `0x18000f8e8`
- `0x180024000`
- `0x18007fa64`
- `0x18008e690`
- `0x18008f234`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f89c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f89c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f5c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f5c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f5b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f88a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f88a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8d6`
- `combase!__imp_CoGetCallLocality` at `0x18000f44e`
- `combase!__imp_CoGetCallLocality` at `0x18000f44e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f681`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f681`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000f620`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000f620`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000f4ca`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000f4ca`

## string_xrefs

- `0x18000f51b`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f53b`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f6de`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f756`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f7c7`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f7f6`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f868`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v7; // rbx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  int Error; // edi
  unsigned __int64 v10; // rsi
  HRESULT v11; // r14d
  LONG PackageFamilyNameFromToken; // eax
  __int64 v13; // rdx
  HSTRING v15; // rcx
  HRESULT v16; // eax
  HANDLE v17; // rcx
  HSTRING v18; // rcx
  HANDLE v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  UINT32 packageFamilyNameLength; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE token; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v28; // [rsp+38h] [rbp-C8h]
  WCHAR packageFamilyName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[524]; // [rsp+44h] [rbp-BCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !this )
  {
    v13 = 1985;
LABEL_56:
    v6 = -2147024809;
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v13 = 1986;
    goto LABEL_56;
  }
  packageFamilyNameLength = 1;
  v5 = CoGetCallLocality(this, &packageFamilyNameLength);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v5,
      packageFamilyNameLength);
    v13 = 1989;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v6,
      packageFamilyNameLength);
    return v6;
  }
  if ( packageFamilyNameLength == 2 )
  {
    string = 0;
    v22 = Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"VAIL_CALLER_IMAGE", 0x11u);
    v6 = v22;
    if ( v22 >= 0 )
    {
      a2->lpVtbl = (struct IUnknownVtbl *)string;
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v22,
      packageFamilyNameLength);
    if ( string )
      WindowsDeleteString(string);
    return v6;
  }
  v7 = 0;
  v28 = 0;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  token = 0;
  ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                  this,
                                                  131080,
                                                  &token);
  Error = ImpersonationTokenForClientOfObject_nothrow;
  v10 = -1;
  v11 = -2147024362;
  if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
  {
    v23 = (unsigned int)ImpersonationTokenForClientOfObject_nothrow;
    v24 = 1925;
LABEL_64:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v23,
      packageFamilyNameLength);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&token);
    goto LABEL_21;
  }
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(token, &packageFamilyNameLength, packageFamilyName);
  Error = PackageFamilyNameFromToken;
  if ( PackageFamilyNameFromToken > 0 )
    Error = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
  if ( Error < 0 )
  {
    if ( Error == -2147009196 )
    {
      if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(token);
      goto LABEL_22;
    }
    v23 = (unsigned int)Error;
    v24 = 1929;
    goto LABEL_64;
  }
  if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(token);
  string = 0;
  v21 = -1;
  do
    ++v21;
  while ( packageFamilyName[v21] );
  if ( v21 <= 0xFFFFFFFF )
  {
    Error = WindowsCreateString(packageFamilyName, v21, &string);
    if ( Error >= 0 )
    {
      v7 = string;
      WindowsDeleteString(0);
      v28 = v7;
      Error = 0;
      goto LABEL_21;
    }
  }
  else
  {
    Error = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x78C,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)(unsigned int)Error,
    packageFamilyNameLength);
LABEL_21:
  if ( Error != -2147009196 )
  {
    if ( Error >= 0 )
      goto LABEL_17;
    v20 = 2009;
    goto LABEL_45;
  }
LABEL_22:
  *(_DWORD *)packageFamilyName = 0;
  memset_0(v30, 0, 0x206u);
  packageFamilyNameLength = 261;
  string = 0;
  token = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&token);
  v16 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &token);
  Error = v16;
  if ( v16 >= 0 )
  {
    Error = (*(__int64 (__fastcall **)(HANDLE, __int64, HSTRING *))(*(_QWORD *)token + 24LL))(token, 4096, &string);
    if ( Error >= 0 )
      goto LABEL_24;
    v19 = token;
    if ( token )
    {
      token = 0;
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v19 + 16LL))(v19);
    }
LABEL_39:
    packageFamilyName[0] = 0;
    packageFamilyNameLength = 0;
    goto LABEL_28;
  }
  if ( v16 != -2147417833 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v16,
      packageFamilyNameLength);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&token);
    goto LABEL_39;
  }
  string = (HSTRING)GetCurrentProcess();
LABEL_24:
  v17 = token;
  if ( token )
  {
    token = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( QueryFullProcessImageNameW(string, 0, packageFamilyName, &packageFamilyNameLength) )
  {
    Error = 0;
    goto LABEL_28;
  }
  Error = ResultFromKnownLastError();
  if ( Error < 0 )
    goto LABEL_39;
LABEL_28:
  v18 = string;
  string = 0;
  if ( (unsigned __int64)v18 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v18);
  if ( Error < 0 )
  {
    v20 = 2004;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)Error,
      packageFamilyNameLength);
    if ( v7 )
      WindowsDeleteString(v7);
    return (unsigned int)Error;
  }
  string = 0;
  do
    ++v10;
  while ( packageFamilyName[v10] );
  if ( v10 <= 0xFFFFFFFF )
  {
    v11 = WindowsCreateString(packageFamilyName, v10, &string);
    if ( v11 >= 0 )
    {
      v15 = v7;
      v7 = string;
      WindowsDeleteString(v15);
LABEL_17:
      a2->lpVtbl = (struct IUnknownVtbl *)v7;
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7D5,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)(unsigned int)v11,
    packageFamilyNameLength);
  if ( v7 )
    WindowsDeleteString(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f3f4  mov     [rsp-8+arg_10], rbx
0x18000f3f9  mov     [rsp-8+arg_18], rsi
0x18000f3fe  push    rbp
0x18000f3ff  push    rdi
0x18000f400  push    r12
0x18000f402  push    r14
0x18000f404  push    r15
0x18000f406  lea     rbp, [rsp-160h]
0x18000f40e  sub     rsp, 260h
0x18000f415  mov     rax, cs:__security_cookie
0x18000f41c  xor     rax, rsp
0x18000f41f  mov     [rbp+180h+var_30], rax
0x18000f426  mov     r15, rdx
0x18000f429  mov     rdi, rcx
0x18000f42c  xor     r12d, r12d
0x18000f42f  test    rcx, rcx
0x18000f432  jz      loc_18000F7DD
0x18000f438  test    rdx, rdx
0x18000f43b  jz      loc_18000F820
0x18000f441  mov     [rsp+280h+packageFamilyNameLength], 1; int
0x18000f449  lea     rdx, [rsp+280h+packageFamilyNameLength]
0x18000f44e  call    cs:__imp_CoGetCallLocality
0x18000f454  mov     ebx, eax
0x18000f456  test    eax, eax
0x18000f458  js      loc_18000F511
0x18000f45e  cmp     [rsp+280h+packageFamilyNameLength], 2
0x18000f463  setz    al
0x18000f466  test    al, al
0x18000f468  jnz     loc_18000F827
0x18000f46e  mov     ebx, r12d
0x18000f471  mov     [rsp+280h+var_248], rbx
0x18000f476  xor     edx, edx; Val
0x18000f478  mov     r8d, 82h; Size
0x18000f47e  lea     rcx, [rsp+280h+packageFamilyName]; void *
0x18000f483  call    memset_0
0x18000f488  mov     [rsp+280h+packageFamilyNameLength], 41h ; 'A'; int
0x18000f490  mov     [rsp+280h+token], r12
0x18000f495  lea     r8, [rsp+280h+token]
0x18000f49a  mov     edx, 20008h
0x18000f49f  mov     rcx, rdi
0x18000f4a2  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18000f4a7  mov     edi, eax
0x18000f4a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f4ad  mov     r14d, 80070216h
0x18000f4b3  test    eax, eax
0x18000f4b5  js      loc_18000F856
0x18000f4bb  lea     r8, [rsp+280h+packageFamilyName]; packageFamilyName
0x18000f4c0  lea     rdx, [rsp+280h+packageFamilyNameLength]; packageFamilyNameLength
0x18000f4c5  mov     rcx, [rsp+280h+token]; token
0x18000f4ca  call    cs:__imp_GetPackageFamilyNameFromToken
0x18000f4d0  mov     edi, eax
0x18000f4d2  test    eax, eax
0x18000f4d4  jle     short loc_18000F4DF
0x18000f4d6  movzx   edi, ax
0x18000f4d9  or      edi, 80070000h
0x18000f4df  test    edi, edi
0x18000f4e1  jns     loc_18000F782
0x18000f4e7  cmp     edi, 80073D54h
0x18000f4ed  jnz     loc_18000F860
0x18000f4f3  mov     rcx, [rsp+280h+token]; hObject
0x18000f4f8  lea     rax, [rcx-1]
0x18000f4fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f500  ja      loc_18000F5E1
0x18000f506  call    cs:__imp_CloseHandle
0x18000f50c  jmp     loc_18000F5E1
0x18000f511  mov     rcx, [rbp+188h]; this
0x18000f518  mov     r9d, ebx; char *
0x18000f51b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f522  mov     edx, 748h; void *
0x18000f527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f52c  mov     edx, 7C5h; void *
0x18000f531  mov     rcx, [rbp+188h]; this
0x18000f538  mov     r9d, ebx; char *
0x18000f53b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f547  mov     eax, ebx
0x18000f549  jmp     short loc_18000F57B
0x18000f54b  mov     edx, esi; length
0x18000f54d  lea     r8, [rsp+280h+string]; string
0x18000f552  lea     rcx, [rsp+280h+packageFamilyName]; sourceString
0x18000f557  call    cs:__imp_WindowsCreateString
0x18000f55d  mov     r14d, eax
0x18000f560  test    eax, eax
0x18000f562  js      loc_18000F6D4
0x18000f568  mov     rcx, rbx; string
0x18000f56b  mov     rbx, [rsp+280h+string]
0x18000f570  call    cs:__imp_WindowsDeleteString
0x18000f576  mov     [r15], rbx
0x18000f579  xor     eax, eax
0x18000f57b  mov     rcx, [rbp+180h+var_30]
0x18000f582  xor     rcx, rsp; StackCookie
0x18000f585  call    __security_check_cookie
0x18000f58a  lea     r11, [rsp+280h+var_20]
0x18000f592  mov     rbx, [r11+40h]
0x18000f596  mov     rsi, [r11+48h]
0x18000f59a  mov     rsp, r11
0x18000f59d  pop     r15
0x18000f59f  pop     r14
0x18000f5a1  pop     r12
0x18000f5a3  pop     rdi
0x18000f5a4  pop     rbp
0x18000f5a5  retn
0x18000f5a6  lea     r8, [rsp+280h+string]; string
0x18000f5ab  lea     rcx, [rsp+280h+packageFamilyName]; sourceString
0x18000f5b0  call    cs:__imp_WindowsCreateString
0x18000f5b6  mov     edi, eax
0x18000f5b8  test    eax, eax
0x18000f5ba  js      loc_18000F7BD
0x18000f5c0  mov     rbx, [rsp+280h+string]
0x18000f5c5  xor     ecx, ecx; string
0x18000f5c7  call    cs:__imp_WindowsDeleteString
0x18000f5cd  mov     [rsp+280h+var_248], rbx
0x18000f5d2  mov     edi, r12d
0x18000f5d5  cmp     edi, 80073D54h
0x18000f5db  jnz     loc_18000F731
0x18000f5e1  mov     dword ptr [rsp+280h+packageFamilyName], r12d
0x18000f5e6  xor     edx, edx; Val
0x18000f5e8  mov     r8d, 206h; Size
0x18000f5ee  lea     rcx, [rsp+280h+var_23C]; void *
0x18000f5f3  call    memset_0
0x18000f5f8  mov     [rsp+280h+packageFamilyNameLength], 105h; int
0x18000f600  mov     [rsp+280h+string], r12
0x18000f605  mov     [rsp+280h+token], r12
0x18000f60a  lea     rcx, [rsp+280h+token]
0x18000f60f  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18000f614  lea     rdx, [rsp+280h+token]; ppInterface
0x18000f619  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18000f620  call    cs:__imp_CoGetCallContext
0x18000f626  mov     edi, eax
0x18000f628  test    eax, eax
0x18000f62a  js      loc_18000F895
0x18000f630  mov     rcx, [rsp+280h+token]
0x18000f635  mov     rax, [rcx]
0x18000f638  lea     r8, [rsp+280h+string]
0x18000f63d  mov     edx, 1000h
0x18000f642  mov     rax, [rax+18h]
0x18000f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64b  mov     edi, eax
0x18000f64d  test    eax, eax
0x18000f64f  js      loc_18000F706
0x18000f655  mov     rcx, [rsp+280h+token]
0x18000f65a  test    rcx, rcx
0x18000f65d  jz      short loc_18000F670
0x18000f65f  mov     [rsp+280h+token], r12
0x18000f664  mov     rax, [rcx]
0x18000f667  mov     rax, [rax+10h]
0x18000f66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f670  lea     r9, [rsp+280h+packageFamilyNameLength]; lpdwSize
0x18000f675  lea     r8, [rsp+280h+packageFamilyName]; lpExeName
0x18000f67a  xor     edx, edx; dwFlags
0x18000f67c  mov     rcx, [rsp+280h+string]; hProcess
0x18000f681  call    cs:__imp_QueryFullProcessImageNameW
0x18000f687  test    eax, eax
0x18000f689  jz      loc_18000F740
0x18000f68f  mov     edi, r12d
0x18000f692  mov     rcx, [rsp+280h+string]; hObject
0x18000f697  mov     [rsp+280h+string], r12
0x18000f69c  lea     rax, [rcx-1]
0x18000f6a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f6a4  jbe     loc_18000F8D6
0x18000f6aa  test    edi, edi
0x18000f6ac  js      loc_18000F751
0x18000f6b2  mov     [rsp+280h+string], r12
0x18000f6b7  lea     rax, [rsp+280h+packageFamilyName]
0x18000f6bc  inc     rsi
0x18000f6bf  cmp     [rax+rsi*2], r12w
0x18000f6c4  jnz     short loc_18000F6BC
0x18000f6c6  mov     eax, 0FFFFFFFFh
0x18000f6cb  cmp     rsi, rax
0x18000f6ce  jbe     loc_18000F54B
0x18000f6d4  mov     rcx, [rbp+188h]; this
0x18000f6db  mov     r9d, r14d; char *
0x18000f6de  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f6e5  mov     edx, 7D5h; void *
0x18000f6ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6ef  nop
0x18000f6f0  test    rbx, rbx
0x18000f6f3  jz      short loc_18000F6FE
0x18000f6f5  mov     rcx, rbx; string
0x18000f6f8  call    cs:__imp_WindowsDeleteString
0x18000f6fe  mov     eax, r14d
0x18000f701  jmp     loc_18000F57B
0x18000f706  mov     rcx, [rsp+280h+token]
0x18000f70b  test    rcx, rcx
0x18000f70e  jz      short loc_18000F721
0x18000f710  mov     [rsp+280h+token], r12
0x18000f715  mov     rax, [rcx]
0x18000f718  mov     rax, [rax+10h]
0x18000f71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f721  mov     [rsp+280h+packageFamilyName], r12w
0x18000f727  mov     [rsp+280h+packageFamilyNameLength], r12d
0x18000f72c  jmp     loc_18000F692
0x18000f731  test    edi, edi
0x18000f733  jns     loc_18000F576
0x18000f739  mov     edx, 7D9h
0x18000f73e  jmp     short loc_18000F756
0x18000f740  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f745  mov     edi, eax
0x18000f747  test    eax, eax
0x18000f749  jns     loc_18000F692
0x18000f74f  jmp     short loc_18000F721
0x18000f751  mov     edx, 7D4h; void *
0x18000f756  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f75d  mov     r9d, edi; char *
0x18000f760  mov     rcx, [rbp+188h]; this
0x18000f767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f76c  nop
0x18000f76d  test    rbx, rbx
0x18000f770  jz      short loc_18000F77B
0x18000f772  mov     rcx, rbx; string
0x18000f775  call    cs:__imp_WindowsDeleteString
0x18000f77b  mov     eax, edi
0x18000f77d  jmp     loc_18000F57B
0x18000f782  mov     rcx, [rsp+280h+token]; hObject
0x18000f787  lea     rax, [rcx-1]
0x18000f78b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f78f  jbe     loc_18000F88A
0x18000f795  mov     [rsp+280h+string], r12
0x18000f79a  lea     rax, [rsp+280h+packageFamilyName]
0x18000f79f  mov     rdx, rsi
0x18000f7a2  inc     rdx; length
0x18000f7a5  cmp     [rax+rdx*2], r12w
0x18000f7aa  jnz     short loc_18000F7A2
0x18000f7ac  mov     eax, 0FFFFFFFFh
0x18000f7b1  cmp     rdx, rax
0x18000f7b4  jbe     loc_18000F5A6
0x18000f7ba  mov     edi, r14d
0x18000f7bd  mov     rcx, [rbp+188h]; this
0x18000f7c4  mov     r9d, edi; char *
0x18000f7c7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f7ce  mov     edx, 78Ch; void *
0x18000f7d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7d8  jmp     loc_18000F5D5
0x18000f7dd  mov     edx, 7C1h
0x18000f7e2  mov     ebx, 80070057h
0x18000f7e7  jmp     loc_18000F531
0x18000f7ec  mov     rcx, [rbp+188h]; this
0x18000f7f3  mov     r9d, ebx; char *
0x18000f7f6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f7fd  mov     edx, 7C9h; void *
0x18000f802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f807  mov     rcx, [rsp+280h+string]; string
0x18000f80c  test    rcx, rcx
0x18000f80f  jz      loc_18000F547
0x18000f815  call    cs:__imp_WindowsDeleteString
0x18000f81b  jmp     loc_18000F547
0x18000f820  mov     edx, 7C2h
0x18000f825  jmp     short loc_18000F7E2
0x18000f827  mov     [rsp+280h+string], r12
0x18000f82c  mov     r8d, 11h; unsigned int
0x18000f832  lea     rdx, aVailCallerImag; "VAIL_CALLER_IMAGE"
0x18000f839  lea     rcx, [rsp+280h+string]; this
0x18000f83e  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18000f843  mov     ebx, eax
0x18000f845  test    eax, eax
0x18000f847  js      short loc_18000F7EC
0x18000f849  mov     rax, [rsp+280h+string]
0x18000f84e  mov     [r15], rax
0x18000f851  jmp     loc_18000F579
0x18000f856  mov     r9d, eax
0x18000f859  mov     edx, 785h
0x18000f85e  jmp     short loc_18000F868
0x18000f860  mov     r9d, edi; char *
0x18000f863  mov     edx, 789h; void *
0x18000f868  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f86f  mov     rcx, [rbp+188h]; this
0x18000f876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f87b  lea     rcx, [rsp+280h+token]; this
0x18000f880  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18000f885  jmp     loc_18000F5D5
0x18000f88a  call    cs:__imp_CloseHandle
0x18000f890  jmp     loc_18000F795
0x18000f895  cmp     eax, 80010117h
0x18000f89a  jnz     short loc_18000F8AC
0x18000f89c  call    cs:__imp_GetCurrentProcess
0x18000f8a2  mov     [rsp+280h+string], rax
0x18000f8a7  jmp     loc_18000F655
0x18000f8ac  mov     rcx, [rbp+188h]; this
0x18000f8b3  mov     r9d, eax; char *
0x18000f8b6  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18000f8bd  mov     edx, 58h ; 'X'; void *
0x18000f8c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8c7  lea     rcx, [rsp+280h+token]
0x18000f8cc  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18000f8d1  jmp     loc_18000F721
0x18000f8d6  call    cs:__imp_CloseHandle
0x18000f8dc  jmp     loc_18000F6AA
```
