# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800c5d90`
- end: `0x1800c5ec0`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c5d1c`

## callees

- `0x180004d38`
- `0x1800313ec`
- `0x18003140c`
- `0x1800c5d90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5db4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5e7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5e90`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5db4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5e7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800c5e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5df5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5de7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5e58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5de7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5e58`

## string_xrefs

- `0x1800c5e21`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800c5e67`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800c5e9f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
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
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
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
0x1800c5d90  mov     [rsp+arg_8], rbx
0x1800c5d95  mov     [rsp+arg_10], rsi
0x1800c5d9a  push    rdi
0x1800c5d9b  sub     rsp, 30h
0x1800c5d9f  mov     rbx, rcx
0x1800c5da2  mov     rsi, rdx
0x1800c5da5  mov     rcx, [rcx]
0x1800c5da8  mov     qword ptr [rbx], 0
0x1800c5daf  test    rcx, rcx
0x1800c5db2  jz      short loc_1800C5DBA
0x1800c5db4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800c5dba  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800c5dc1  mov     [rsp+38h+TokenInformationLength], 0
0x1800c5dc9  test    rsi, rsi
0x1800c5dcc  cmovz   rsi, rax
0x1800c5dd0  xor     r9d, r9d; TokenInformationLength
0x1800c5dd3  lea     rax, [rsp+38h+TokenInformationLength]
0x1800c5dd8  xor     r8d, r8d; TokenInformation
0x1800c5ddb  mov     rcx, rsi; TokenHandle
0x1800c5dde  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800c5de3  lea     edx, [r9+1]; TokenInformationClass
0x1800c5de7  call    cs:__imp_GetTokenInformation
0x1800c5ded  test    eax, eax
0x1800c5def  jnz     loc_1800C5E9A
0x1800c5df5  call    cs:__imp_GetLastError
0x1800c5dfb  cmp     eax, 7Ah ; 'z'
0x1800c5dfe  jnz     loc_1800C5E9A
0x1800c5e04  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800c5e08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c5e0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c5e14  mov     rdi, rax
0x1800c5e17  test    rax, rax
0x1800c5e1a  jnz     short loc_1800C5E3E
0x1800c5e1c  mov     rcx, [rsp+38h]; this
0x1800c5e21  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c5e28  mov     ebx, 8007000Eh
0x1800c5e2d  mov     edx, 119h; void *
0x1800c5e32  mov     r9d, ebx; char *
0x1800c5e35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5e3a  mov     eax, ebx
0x1800c5e3c  jmp     short loc_1800C5EB0
0x1800c5e3e  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800c5e43  lea     rax, [rsp+38h+TokenInformationLength]
0x1800c5e48  mov     r8, rdi; TokenInformation
0x1800c5e4b  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800c5e50  mov     edx, 1; TokenInformationClass
0x1800c5e55  mov     rcx, rsi; TokenHandle
0x1800c5e58  call    cs:__imp_GetTokenInformation
0x1800c5e5e  test    eax, eax
0x1800c5e60  jnz     short loc_1800C5E85
0x1800c5e62  mov     rcx, [rsp+38h]; this
0x1800c5e67  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c5e6e  mov     edx, 11Ah; void *
0x1800c5e73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5e78  mov     rcx, rdi
0x1800c5e7b  mov     ebx, eax
0x1800c5e7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800c5e83  jmp     short loc_1800C5E3A
0x1800c5e85  mov     rcx, [rbx]
0x1800c5e88  mov     [rbx], rdi
0x1800c5e8b  test    rcx, rcx
0x1800c5e8e  jz      short loc_1800C5E96
0x1800c5e90  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800c5e96  xor     eax, eax
0x1800c5e98  jmp     short loc_1800C5EB0
0x1800c5e9a  mov     rcx, [rsp+38h]; this
0x1800c5e9f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c5ea6  mov     edx, 117h; void *
0x1800c5eab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5eb0  mov     rbx, [rsp+38h+arg_8]
0x1800c5eb5  mov     rsi, [rsp+38h+arg_10]
0x1800c5eba  add     rsp, 30h
0x1800c5ebe  pop     rdi
0x1800c5ebf  retn
```
