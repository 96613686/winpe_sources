# Windows::Internal::CapabilityAccess::Private::GetUserSidFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x180022b88`
- end: `0x180022ce5`
- name: `?GetUserSidFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@6@@Z`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022d2c`
- `0x180022d88`

## callees

- `0x18001b5ac`
- `0x1800211b8`
- `0x1800214f0`
- `0x18002150c`
- `0x180022b88`
- `0x180023690`
- `0x1800236ac`
- `0x180023900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022c63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022c63`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022c93`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022c93`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022c57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022bc4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022c35`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022bc4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022c35`

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
  unsigned int v10; // r8d
  const char *v11; // r9
  const char *v12; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+38h] BYREF
  __int64 v17; // [rsp+80h] [rbp+40h] BYREF
  PSID *v18; // [rsp+88h] [rbp+48h] BYREF

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
  v5 = (PSID **)std::make_unique<unsigned char [0],0>(&v17, TokenInformationLength);
  v6 = *v5;
  *v5 = 0;
  v18 = v6;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v17);
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
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x337, v10, v11);
  if ( !CopySid(LengthSid, v9, *v6) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x338,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v12);
  std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(&v18);
  return a1;
}

```

## disassembly

```asm
0x180022b88  mov     [rsp-28h+arg_0], rcx
0x180022b8d  push    rbp
0x180022b8e  push    rbx
0x180022b8f  push    rsi
0x180022b90  push    rdi
0x180022b91  push    r14
0x180022b93  mov     rbp, rsp
0x180022b96  sub     rsp, 40h
0x180022b9a  mov     rsi, rdx
0x180022b9d  mov     rbx, rcx
0x180022ba0  mov     [rbp+var_10], 0
0x180022ba7  mov     [rbp+TokenInformationLength], 0
0x180022bae  lea     rax, [rbp+TokenInformationLength]
0x180022bb2  mov     qword ptr [rsp+40h+ReturnLength], rax; int
0x180022bb7  xor     r9d, r9d; TokenInformationLength
0x180022bba  xor     r8d, r8d; TokenInformation
0x180022bbd  lea     edx, [r9+1]; TokenInformationClass
0x180022bc1  mov     rcx, [rsi]; TokenHandle
0x180022bc4  call    cs:__imp_GetTokenInformation
0x180022bca  test    eax, eax
0x180022bcc  jnz     loc_180022CC9
0x180022bd2  call    cs:__imp_GetLastError
0x180022bd8  cmp     eax, 7Ah ; 'z'
0x180022bdb  jz      short loc_180022BF6
0x180022bdd  mov     rcx, [rbp+28h]; this
0x180022be1  mov     r9d, eax; char *
0x180022be4  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022beb  mov     edx, 320h; void *
0x180022bf0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022bf6  mov     edx, [rbp+TokenInformationLength]
0x180022bf9  lea     rcx, [rbp+arg_10]
0x180022bfd  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180022c02  mov     rdi, [rax]
0x180022c05  mov     qword ptr [rax], 0
0x180022c0c  mov     [rbp+arg_18], rdi
0x180022c10  lea     rcx, [rbp+arg_10]
0x180022c14  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180022c19  mov     r14, [rbp+28h]
0x180022c1d  lea     rax, [rbp+TokenInformationLength]
0x180022c21  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x180022c26  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180022c2a  mov     r8, rdi; TokenInformation
0x180022c2d  mov     edx, 1; TokenInformationClass
0x180022c32  mov     rcx, [rsi]; TokenHandle
0x180022c35  call    cs:__imp_GetTokenInformation
0x180022c3b  test    eax, eax
0x180022c3d  jnz     short loc_180022C54
0x180022c3f  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022c46  mov     edx, 333h; void *
0x180022c4b  mov     rcx, r14; this
0x180022c4e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022c54  mov     rcx, [rdi]; pSid
0x180022c57  call    cs:__imp_GetLengthSid
0x180022c5d  mov     esi, eax
0x180022c5f  mov     edx, eax; uBytes
0x180022c61  xor     ecx, ecx; uFlags
0x180022c63  call    cs:__imp_LocalAlloc
0x180022c69  mov     [rbx], rax
0x180022c6c  mov     [rbp+var_10], 1
0x180022c73  mov     rcx, [rbp+28h]; this
0x180022c77  test    rax, rax
0x180022c7a  jnz     short loc_180022C87
0x180022c7c  mov     edx, 337h; void *
0x180022c81  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180022c87  mov     r14, [rbp+28h]
0x180022c8b  mov     r8, [rdi]; pSourceSid
0x180022c8e  mov     rdx, rax; pDestinationSid
0x180022c91  mov     ecx, esi; nDestinationSidLength
0x180022c93  call    cs:__imp_CopySid
0x180022c99  test    eax, eax
0x180022c9b  jnz     short loc_180022CB2
0x180022c9d  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022ca4  mov     edx, 338h; void *
0x180022ca9  mov     rcx, r14; this
0x180022cac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022cb2  lea     rcx, [rbp+arg_18]
0x180022cb6  call    ??1?$unique_ptr@U_TOKEN_USER@@U?$default_delete@U_TOKEN_USER@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(void)
0x180022cbb  mov     rax, rbx
0x180022cbe  add     rsp, 40h
0x180022cc2  pop     r14
0x180022cc4  pop     rdi
0x180022cc5  pop     rsi
0x180022cc6  pop     rbx
0x180022cc7  pop     rbp
0x180022cc8  retn
0x180022cc9  mov     rcx, [rbp+28h]; this
0x180022ccd  mov     r9d, 8000FFFFh; char *
0x180022cd3  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022cda  mov     edx, 326h; void *
0x180022cdf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
