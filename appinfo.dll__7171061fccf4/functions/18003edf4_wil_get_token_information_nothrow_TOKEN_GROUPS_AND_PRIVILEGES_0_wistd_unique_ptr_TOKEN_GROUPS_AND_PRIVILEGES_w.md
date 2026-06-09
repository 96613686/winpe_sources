# wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_GROUPS_AND_PRIVILEGES,wil::details::token_info_deleter> &,void *)

- ea: `0x18003edf4`
- end: `0x18003ef21`
- name: `??$get_token_information_nothrow@U_TOKEN_GROUPS_AND_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_GROUPS_AND_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003ef28`

## callees

- `0x18000720c`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18001ef98`
- `0x18003edf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ee4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003eebb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ee4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003eebb`

## string_xrefs

- `0x18003ee84`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003eeca`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003ef00`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rdi
  unsigned int LastError; // ebx
  const char *v9; // r9
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( !a2 )
    a2 = -6;
  if ( GetTokenInformation((HANDLE)a2, TokenGroupsAndPrivileges, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenGroupsAndPrivileges, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
    operator delete(v6);
    return LastError;
  }
  v10 = *a1;
  *a1 = v6;
  if ( v10 )
    operator delete(v10);
  return 0;
}

```

## disassembly

```asm
0x18003edf4  mov     [rsp+arg_8], rbx
0x18003edf9  mov     [rsp+arg_10], rsi
0x18003edfe  push    rdi
0x18003edff  sub     rsp, 30h
0x18003ee03  mov     rbx, rcx
0x18003ee06  mov     rsi, rdx
0x18003ee09  mov     rcx, [rcx]; Block
0x18003ee0c  mov     qword ptr [rbx], 0
0x18003ee13  test    rcx, rcx
0x18003ee16  jz      short loc_18003EE1D
0x18003ee18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ee1d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003ee24  mov     [rsp+38h+TokenInformationLength], 0
0x18003ee2c  test    rsi, rsi
0x18003ee2f  cmovz   rsi, rax
0x18003ee33  xor     r9d, r9d; TokenInformationLength
0x18003ee36  lea     rax, [rsp+38h+TokenInformationLength]
0x18003ee3b  xor     r8d, r8d; TokenInformation
0x18003ee3e  mov     rcx, rsi; TokenHandle
0x18003ee41  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003ee46  lea     edx, [r9+0Dh]; TokenInformationClass
0x18003ee4a  call    cs:__imp_GetTokenInformation
0x18003ee50  test    eax, eax
0x18003ee52  jnz     loc_18003EEFB
0x18003ee58  call    cs:__imp_GetLastError
0x18003ee5e  cmp     eax, 7Ah ; 'z'
0x18003ee61  jnz     loc_18003EEFB
0x18003ee67  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003ee6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ee72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ee77  mov     rdi, rax
0x18003ee7a  test    rax, rax
0x18003ee7d  jnz     short loc_18003EEA1
0x18003ee7f  mov     rcx, [rsp+38h]; this
0x18003ee84  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003ee8b  mov     ebx, 8007000Eh
0x18003ee90  mov     edx, 119h; void *
0x18003ee95  mov     r9d, ebx; char *
0x18003ee98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee9d  mov     eax, ebx
0x18003ee9f  jmp     short loc_18003EF11
0x18003eea1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003eea6  lea     rax, [rsp+38h+TokenInformationLength]
0x18003eeab  mov     r8, rdi; TokenInformation
0x18003eeae  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003eeb3  mov     edx, 0Dh; TokenInformationClass
0x18003eeb8  mov     rcx, rsi; TokenHandle
0x18003eebb  call    cs:__imp_GetTokenInformation
0x18003eec1  test    eax, eax
0x18003eec3  jnz     short loc_18003EEE7
0x18003eec5  mov     rcx, [rsp+38h]; this
0x18003eeca  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003eed1  mov     edx, 11Ah; void *
0x18003eed6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003eedb  mov     rcx, rdi; Block
0x18003eede  mov     ebx, eax
0x18003eee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003eee5  jmp     short loc_18003EE9D
0x18003eee7  mov     rcx, [rbx]; Block
0x18003eeea  mov     [rbx], rdi
0x18003eeed  test    rcx, rcx
0x18003eef0  jz      short loc_18003EEF7
0x18003eef2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003eef7  xor     eax, eax
0x18003eef9  jmp     short loc_18003EF11
0x18003eefb  mov     rcx, [rsp+38h]; this
0x18003ef00  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003ef07  mov     edx, 117h; void *
0x18003ef0c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ef11  mov     rbx, [rsp+38h+arg_8]
0x18003ef16  mov     rsi, [rsp+38h+arg_10]
0x18003ef1b  add     rsp, 30h
0x18003ef1f  pop     rdi
0x18003ef20  retn
```
