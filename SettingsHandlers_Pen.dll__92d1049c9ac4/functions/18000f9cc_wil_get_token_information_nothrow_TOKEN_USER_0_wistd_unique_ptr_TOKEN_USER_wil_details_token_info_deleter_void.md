# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18000f9cc`
- end: `0x18000fae8`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013554`

## callees

- `0x180003110`
- `0x1800035b0`
- `0x18000a29c`
- `0x18000a2bc`
- `0x18000f9cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fa12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fa87`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fa12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fa87`

## string_xrefs

- `0x18000fa4c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000fa96`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000facc`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  void *v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = a2;
  v3 = *a1;
  *a1 = 0;
  if ( v3 )
    operator delete(v3);
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenUser,
          v5,
          TokenInformationLength,
          (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v8);
    operator delete(v5);
    return LastError;
  }
  v9 = *a1;
  *a1 = v5;
  if ( v9 )
    operator delete(v9);
  return 0;
}

```

## disassembly

```asm
0x18000f9cc  mov     [rsp+arg_0], rbx
0x18000f9d1  mov     [rsp+TokenInformationLength], rdx
0x18000f9d6  push    rdi
0x18000f9d7  sub     rsp, 30h
0x18000f9db  mov     rbx, rcx
0x18000f9de  mov     rcx, [rcx]; Block
0x18000f9e1  mov     qword ptr [rbx], 0
0x18000f9e8  test    rcx, rcx
0x18000f9eb  jz      short loc_18000F9F2
0x18000f9ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f9f2  xor     r9d, r9d; TokenInformationLength
0x18000f9f5  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x18000f9fd  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fa02  xor     r8d, r8d; TokenInformation
0x18000fa05  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000fa0a  lea     edx, [r9+1]; TokenInformationClass
0x18000fa0e  lea     rcx, [r9-6]; TokenHandle
0x18000fa12  call    cs:__imp_GetTokenInformation
0x18000fa18  test    eax, eax
0x18000fa1a  jnz     loc_18000FAC7
0x18000fa20  call    cs:__imp_GetLastError
0x18000fa26  cmp     eax, 7Ah ; 'z'
0x18000fa29  jnz     loc_18000FAC7
0x18000fa2f  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18000fa33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fa3a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fa3f  mov     rdi, rax
0x18000fa42  test    rax, rax
0x18000fa45  jnz     short loc_18000FA69
0x18000fa47  mov     rcx, [rsp+38h]; this
0x18000fa4c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fa53  mov     ebx, 8007000Eh
0x18000fa58  mov     edx, 119h; void *
0x18000fa5d  mov     r9d, ebx; char *
0x18000fa60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa65  mov     eax, ebx
0x18000fa67  jmp     short loc_18000FADD
0x18000fa69  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000fa6e  lea     rax, [rsp+38h+TokenInformationLength]
0x18000fa73  mov     r8, rdi; TokenInformation
0x18000fa76  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18000fa7b  mov     edx, 1; TokenInformationClass
0x18000fa80  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18000fa87  call    cs:__imp_GetTokenInformation
0x18000fa8d  test    eax, eax
0x18000fa8f  jnz     short loc_18000FAB3
0x18000fa91  mov     rcx, [rsp+38h]; this
0x18000fa96  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fa9d  mov     edx, 11Ah; void *
0x18000faa2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000faa7  mov     rcx, rdi; Block
0x18000faaa  mov     ebx, eax
0x18000faac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fab1  jmp     short loc_18000FA65
0x18000fab3  mov     rcx, [rbx]; Block
0x18000fab6  mov     [rbx], rdi
0x18000fab9  test    rcx, rcx
0x18000fabc  jz      short loc_18000FAC3
0x18000fabe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fac3  xor     eax, eax
0x18000fac5  jmp     short loc_18000FADD
0x18000fac7  mov     rcx, [rsp+38h]; this
0x18000facc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fad3  mov     edx, 117h; void *
0x18000fad8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fadd  mov     rbx, [rsp+38h+arg_0]
0x18000fae2  add     rsp, 30h
0x18000fae6  pop     rdi
0x18000fae7  retn
```
