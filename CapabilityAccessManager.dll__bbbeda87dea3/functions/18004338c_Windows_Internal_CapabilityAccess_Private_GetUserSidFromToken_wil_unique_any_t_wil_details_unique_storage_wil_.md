# Windows::Internal::CapabilityAccess::Private::GetUserSidFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x18004338c`
- end: `0x1800434f0`
- name: `?GetUserSidFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@6@@Z`
- size: `356`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040398`
- `0x180043538`
- `0x180043610`

## callees

- `0x18002392c`
- `0x1800299c4`
- `0x180039e9c`
- `0x18003f274`
- `0x18003f43c`
- `0x18003f47c`
- `0x18004338c`
- `0x18004624c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043467`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043467`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004345b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004345b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800433c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043439`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800433c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043439`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004349e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004349e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetUserSidFromToken(_QWORD *a1, HANDLE *a2)
{
  DWORD LastError; // eax
  PSID **v5; // rax
  PSID *v6; // rdi
  const char *v7; // r9
  SIZE_T LengthSid; // rsi
  HLOCAL v9; // rax
  const char *v10; // r9
  const char *v11; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+38h] BYREF
  char v16; // [rsp+80h] [rbp+40h] BYREF
  PSID *v17; // [rsp+88h] [rbp+48h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(*a2, TokenUser, 0, 0, &TokenInformationLength) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  LastError = GetLastError();
  if ( LastError != 122 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)LastError,
      ReturnLength);
  v5 = (PSID **)std::make_unique<unsigned char [0],0>(&v16, TokenInformationLength);
  v6 = *v5;
  *v5 = 0;
  v17 = v6;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v16);
  if ( !GetTokenInformation(*a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x333,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v7);
  LengthSid = GetLengthSid(*v6);
  v9 = LocalAlloc(0, LengthSid);
  *a1 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x337,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v10);
  if ( !CopySid(LengthSid, v9, *v6) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x338,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v11);
  std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(&v17);
  return a1;
}

```

## disassembly

```asm
0x18004338c  mov     [rsp-28h+arg_0], rcx
0x180043391  push    rbp
0x180043392  push    rbx
0x180043393  push    rsi
0x180043394  push    rdi
0x180043395  push    r14
0x180043397  mov     rbp, rsp
0x18004339a  sub     rsp, 40h
0x18004339e  mov     rsi, rdx
0x1800433a1  mov     rbx, rcx
0x1800433a4  mov     [rbp+var_10], 0
0x1800433ab  mov     [rbp+TokenInformationLength], 0
0x1800433b2  lea     rax, [rbp+TokenInformationLength]
0x1800433b6  mov     qword ptr [rsp+40h+ReturnLength], rax; int
0x1800433bb  xor     r9d, r9d; TokenInformationLength
0x1800433be  xor     r8d, r8d; TokenInformation
0x1800433c1  lea     edx, [r9+1]; TokenInformationClass
0x1800433c5  mov     rcx, [rsi]; TokenHandle
0x1800433c8  call    cs:__imp_GetTokenInformation
0x1800433ce  test    eax, eax
0x1800433d0  jnz     loc_1800434D4
0x1800433d6  call    cs:__imp_GetLastError
0x1800433dc  cmp     eax, 7Ah ; 'z'
0x1800433df  jz      short loc_1800433FA
0x1800433e1  mov     rcx, [rbp+28h]; this
0x1800433e5  mov     r9d, eax; char *
0x1800433e8  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800433ef  mov     edx, 320h; void *
0x1800433f4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800433fa  mov     edx, [rbp+TokenInformationLength]
0x1800433fd  lea     rcx, [rbp+arg_10]
0x180043401  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180043406  mov     rdi, [rax]
0x180043409  mov     qword ptr [rax], 0
0x180043410  mov     [rbp+arg_18], rdi
0x180043414  lea     rcx, [rbp+arg_10]
0x180043418  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18004341d  mov     r14, [rbp+28h]
0x180043421  lea     rax, [rbp+TokenInformationLength]
0x180043425  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x18004342a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004342e  mov     r8, rdi; TokenInformation
0x180043431  mov     edx, 1; TokenInformationClass
0x180043436  mov     rcx, [rsi]; TokenHandle
0x180043439  call    cs:__imp_GetTokenInformation
0x18004343f  test    eax, eax
0x180043441  jnz     short loc_180043458
0x180043443  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004344a  mov     edx, 333h; void *
0x18004344f  mov     rcx, r14; this
0x180043452  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180043458  mov     rcx, [rdi]; pSid
0x18004345b  call    cs:__imp_GetLengthSid
0x180043461  mov     esi, eax
0x180043463  mov     edx, eax; uBytes
0x180043465  xor     ecx, ecx; uFlags
0x180043467  call    cs:__imp_LocalAlloc
0x18004346d  mov     [rbx], rax
0x180043470  mov     [rbp+var_10], 1
0x180043477  mov     rcx, [rbp+28h]; this
0x18004347b  test    rax, rax
0x18004347e  jnz     short loc_180043492
0x180043480  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180043487  mov     edx, 337h; void *
0x18004348c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180043492  mov     r14, [rbp+28h]
0x180043496  mov     r8, [rdi]; pSourceSid
0x180043499  mov     rdx, rax; pDestinationSid
0x18004349c  mov     ecx, esi; nDestinationSidLength
0x18004349e  call    cs:__imp_CopySid
0x1800434a4  test    eax, eax
0x1800434a6  jnz     short loc_1800434BD
0x1800434a8  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800434af  mov     edx, 338h; void *
0x1800434b4  mov     rcx, r14; this
0x1800434b7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800434bd  lea     rcx, [rbp+arg_18]
0x1800434c1  call    ??1?$unique_ptr@U_TOKEN_USER@@U?$default_delete@U_TOKEN_USER@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(void)
0x1800434c6  mov     rax, rbx
0x1800434c9  add     rsp, 40h
0x1800434cd  pop     r14
0x1800434cf  pop     rdi
0x1800434d0  pop     rsi
0x1800434d1  pop     rbx
0x1800434d2  pop     rbp
0x1800434d3  retn
0x1800434d4  mov     rcx, [rbp+28h]; this
0x1800434d8  mov     r9d, 8000FFFFh; char *
0x1800434de  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800434e5  mov     edx, 326h; void *
0x1800434ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
