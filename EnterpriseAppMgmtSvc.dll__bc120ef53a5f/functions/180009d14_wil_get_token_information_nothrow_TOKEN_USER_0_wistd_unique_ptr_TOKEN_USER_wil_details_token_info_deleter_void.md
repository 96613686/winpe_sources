# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180009d14`
- end: `0x180009e6c`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b1ec`
- `0x180023d74`

## callees

- `0x180002398`
- `0x180009d14`
- `0x18000d3bc`
- `0x18000d3dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009d38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009d38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009df1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009df1`

## string_xrefs

- `0x180009db7`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009e06`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009e4a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x180009d14  mov     [rsp+arg_8], rbx
0x180009d19  mov     [rsp+arg_10], rsi
0x180009d1e  push    rdi
0x180009d1f  sub     rsp, 30h
0x180009d23  mov     rbx, rcx
0x180009d26  mov     rsi, rdx
0x180009d29  mov     rcx, [rcx]
0x180009d2c  mov     qword ptr [rbx], 0
0x180009d33  test    rcx, rcx
0x180009d36  jz      short loc_180009D44
0x180009d38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009d3f  nop     dword ptr [rax+rax+00h]
0x180009d44  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180009d4b  mov     [rsp+38h+TokenInformationLength], 0
0x180009d53  test    rsi, rsi
0x180009d56  cmovz   rsi, rax
0x180009d5a  xor     r9d, r9d; TokenInformationLength
0x180009d5d  lea     rax, [rsp+38h+TokenInformationLength]
0x180009d62  xor     r8d, r8d; TokenInformation
0x180009d65  mov     rcx, rsi; TokenHandle
0x180009d68  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180009d6d  lea     edx, [r9+1]; TokenInformationClass
0x180009d71  call    cs:__imp_GetTokenInformation
0x180009d78  nop     dword ptr [rax+rax+00h]
0x180009d7d  test    eax, eax
0x180009d7f  jnz     loc_180009E45
0x180009d85  call    cs:__imp_GetLastError
0x180009d8c  nop     dword ptr [rax+rax+00h]
0x180009d91  cmp     eax, 7Ah ; 'z'
0x180009d94  jnz     loc_180009E45
0x180009d9a  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180009d9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009da5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009daa  mov     rdi, rax
0x180009dad  test    rax, rax
0x180009db0  jnz     short loc_180009DD7
0x180009db2  mov     rcx, [rsp+38h]; this
0x180009db7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009dbe  mov     ebx, 8007000Eh
0x180009dc3  mov     edx, 119h; void *
0x180009dc8  mov     r9d, ebx; char *
0x180009dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dd0  mov     eax, ebx
0x180009dd2  jmp     loc_180009E5B
0x180009dd7  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180009ddc  lea     rax, [rsp+38h+TokenInformationLength]
0x180009de1  mov     r8, rdi; TokenInformation
0x180009de4  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180009de9  mov     edx, 1; TokenInformationClass
0x180009dee  mov     rcx, rsi; TokenHandle
0x180009df1  call    cs:__imp_GetTokenInformation
0x180009df8  nop     dword ptr [rax+rax+00h]
0x180009dfd  test    eax, eax
0x180009dff  jnz     short loc_180009E2A
0x180009e01  mov     rcx, [rsp+38h]; this
0x180009e06  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e0d  mov     edx, 11Ah; void *
0x180009e12  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009e17  mov     rcx, rdi
0x180009e1a  mov     ebx, eax
0x180009e1c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009e23  nop     dword ptr [rax+rax+00h]
0x180009e28  jmp     short loc_180009DD0
0x180009e2a  mov     rcx, [rbx]
0x180009e2d  mov     [rbx], rdi
0x180009e30  test    rcx, rcx
0x180009e33  jz      short loc_180009E41
0x180009e35  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009e3c  nop     dword ptr [rax+rax+00h]
0x180009e41  xor     eax, eax
0x180009e43  jmp     short loc_180009E5B
0x180009e45  mov     rcx, [rsp+38h]; this
0x180009e4a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e51  mov     edx, 117h; void *
0x180009e56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009e5b  mov     rbx, [rsp+38h+arg_8]
0x180009e60  mov     rsi, [rsp+38h+arg_10]
0x180009e65  add     rsp, 30h
0x180009e69  pop     rdi
0x180009e6a  retn
```
