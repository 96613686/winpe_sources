# Http::PrepareRequest

- ea: `0x1800d846c`
- end: `0x1800d85bf`
- name: `Http::PrepareRequest`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d83a4`

## callees

- `0x180022790`
- `0x1800d8384`
- `0x1800d846c`

## import_xrefs

- `WINHTTP!WinHttpOpenRequest` at `0x1800d8530`
- `WINHTTP!WinHttpOpenRequest` at `0x1800d8530`
- `WINHTTP!WinHttpConnect` at `0x1800d84db`
- `WINHTTP!WinHttpConnect` at `0x1800d84db`
- `WINHTTP!WinHttpOpen` at `0x1800d84a0`
- `WINHTTP!WinHttpOpen` at `0x1800d84a0`

## string_xrefs

- `0x1800d84d1`: `endpoints.office.com`
- `0x1800d84b8`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`
- `0x1800d84f3`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`
- `0x1800d8548`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Http::PrepareRequest(void *a1, const WCHAR *a2, void *a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  void *v8; // rax
  const char *v9; // r9
  void *v10; // rdi
  void *v11; // rbx
  const char *v12; // r9
  HINTERNET v13; // rax
  const char *v14; // r9
  void *v16; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *v18; // [rsp+70h] [rbp+8h] BYREF
  HINTERNET v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = a3;
  v18 = a1;
  v8 = WinHttpOpen(L"Windows Web Sign-in Client", 4u, 0, 0, 0);
  v10 = v8;
  v16 = v8;
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
      v9);
  v11 = WinHttpConnect(v8, L"endpoints.office.com", 0x1BBu, 0);
  v18 = v11;
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
      v12);
  v13 = WinHttpOpenRequest(v11, L"GET", a2, 0, 0, (LPCWSTR *)&ppwszAcceptTypes, 0x800100u);
  v19 = v13;
  if ( !v13 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
      v14);
  v19 = 0;
  *a4 = v13;
  v16 = 0;
  *a5 = v10;
  v18 = 0;
  *a6 = v11;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  return wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
}

```

## disassembly

```asm
0x1800d846c  mov     rax, rsp
0x1800d846f  mov     [rax+10h], rbx
0x1800d8473  mov     [rax+18h], r8
0x1800d8477  mov     [rax+8], rcx
0x1800d847b  push    rbp
0x1800d847c  push    rsi
0x1800d847d  push    rdi
0x1800d847e  sub     rsp, 50h
0x1800d8482  mov     rsi, r9
0x1800d8485  mov     rbp, rdx
0x1800d8488  mov     dword ptr [rax-48h], 0
0x1800d848f  xor     r9d, r9d; pszProxyBypassW
0x1800d8492  xor     r8d, r8d; pszProxyW
0x1800d8495  lea     edx, [r9+4]; dwAccessType
0x1800d8499  lea     rcx, pszAgentW; "Windows Web Sign-in Client"
0x1800d84a0  call    cs:__imp_WinHttpOpen
0x1800d84a6  mov     rdi, rax
0x1800d84a9  mov     [rsp+68h+var_28], rax
0x1800d84ae  mov     rcx, [rsp+68h]; this
0x1800d84b3  test    rax, rax
0x1800d84b6  jnz     short loc_1800D84C8
0x1800d84b8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d84bf  lea     edx, [rax+11h]; void *
0x1800d84c2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d84c8  mov     r8d, 1BBh; nServerPort
0x1800d84ce  xor     r9d, r9d; dwReserved
0x1800d84d1  lea     rdx, pswzServerName; "endpoints.office.com"
0x1800d84d8  mov     rcx, rdi; hSession
0x1800d84db  call    cs:__imp_WinHttpConnect
0x1800d84e1  mov     rbx, rax
0x1800d84e4  mov     [rsp+68h+arg_0], rax
0x1800d84e9  mov     rcx, [rsp+68h]; this
0x1800d84ee  test    rax, rax
0x1800d84f1  jnz     short loc_1800D8503
0x1800d84f3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d84fa  lea     edx, [rax+15h]; void *
0x1800d84fd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d8503  mov     [rsp+68h+dwFlags], 800100h; dwFlags
0x1800d850b  lea     rax, ppwszAcceptTypes
0x1800d8512  mov     [rsp+68h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800d8517  mov     [rsp+68h+pwszReferrer], 0; pwszReferrer
0x1800d8520  xor     r9d, r9d; pwszVersion
0x1800d8523  mov     r8, rbp; pwszObjectName
0x1800d8526  lea     rdx, pwszVerb; "GET"
0x1800d852d  mov     rcx, rbx; hConnect
0x1800d8530  call    cs:__imp_WinHttpOpenRequest
0x1800d8536  mov     [rsp+68h+arg_10], rax
0x1800d853e  mov     rcx, [rsp+68h]; this
0x1800d8543  test    rax, rax
0x1800d8546  jnz     short loc_1800D8558
0x1800d8548  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d854f  lea     edx, [rax+1Ah]; void *
0x1800d8552  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d8558  mov     [rsp+68h+arg_10], 0
0x1800d8564  mov     [rsi], rax
0x1800d8567  mov     [rsp+68h+var_28], 0
0x1800d8570  mov     rax, [rsp+68h+arg_20]
0x1800d8578  mov     [rax], rdi
0x1800d857b  mov     [rsp+68h+arg_0], 0
0x1800d8584  mov     rax, [rsp+68h+arg_28]
0x1800d858c  mov     [rax], rbx
0x1800d858f  lea     rcx, [rsp+68h+arg_10]
0x1800d8597  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d859c  nop
0x1800d859d  lea     rcx, [rsp+68h+arg_0]
0x1800d85a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d85a7  nop
0x1800d85a8  lea     rcx, [rsp+68h+var_28]
0x1800d85ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d85b2  mov     rbx, [rsp+68h+arg_8]
0x1800d85b7  add     rsp, 50h
0x1800d85bb  pop     rdi
0x1800d85bc  pop     rsi
0x1800d85bd  pop     rbp
0x1800d85be  retn
```
