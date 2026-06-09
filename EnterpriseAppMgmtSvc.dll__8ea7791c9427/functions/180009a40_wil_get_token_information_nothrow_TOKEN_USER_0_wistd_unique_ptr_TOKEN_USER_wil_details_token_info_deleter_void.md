# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180009a40`
- end: `0x180009b70`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000afdc`
- `0x180022510`

## callees

- `0x180002368`
- `0x180009a40`
- `0x18000cfc8`
- `0x18000cfe8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009a64`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b40`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009a64`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009a97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009b08`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009a97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009b08`

## string_xrefs

- `0x180009ad1`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009b17`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009b4f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x180009a40  mov     [rsp+arg_8], rbx
0x180009a45  mov     [rsp+arg_10], rsi
0x180009a4a  push    rdi
0x180009a4b  sub     rsp, 30h
0x180009a4f  mov     rbx, rcx
0x180009a52  mov     rsi, rdx
0x180009a55  mov     rcx, [rcx]
0x180009a58  mov     qword ptr [rbx], 0
0x180009a5f  test    rcx, rcx
0x180009a62  jz      short loc_180009A6A
0x180009a64  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009a6a  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180009a71  mov     [rsp+38h+TokenInformationLength], 0
0x180009a79  test    rsi, rsi
0x180009a7c  cmovz   rsi, rax
0x180009a80  xor     r9d, r9d; TokenInformationLength
0x180009a83  lea     rax, [rsp+38h+TokenInformationLength]
0x180009a88  xor     r8d, r8d; TokenInformation
0x180009a8b  mov     rcx, rsi; TokenHandle
0x180009a8e  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180009a93  lea     edx, [r9+1]; TokenInformationClass
0x180009a97  call    cs:__imp_GetTokenInformation
0x180009a9d  test    eax, eax
0x180009a9f  jnz     loc_180009B4A
0x180009aa5  call    cs:__imp_GetLastError
0x180009aab  cmp     eax, 7Ah ; 'z'
0x180009aae  jnz     loc_180009B4A
0x180009ab4  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180009ab8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009abf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009ac4  mov     rdi, rax
0x180009ac7  test    rax, rax
0x180009aca  jnz     short loc_180009AEE
0x180009acc  mov     rcx, [rsp+38h]; this
0x180009ad1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009ad8  mov     ebx, 8007000Eh
0x180009add  mov     edx, 119h; void *
0x180009ae2  mov     r9d, ebx; char *
0x180009ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009aea  mov     eax, ebx
0x180009aec  jmp     short loc_180009B60
0x180009aee  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180009af3  lea     rax, [rsp+38h+TokenInformationLength]
0x180009af8  mov     r8, rdi; TokenInformation
0x180009afb  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180009b00  mov     edx, 1; TokenInformationClass
0x180009b05  mov     rcx, rsi; TokenHandle
0x180009b08  call    cs:__imp_GetTokenInformation
0x180009b0e  test    eax, eax
0x180009b10  jnz     short loc_180009B35
0x180009b12  mov     rcx, [rsp+38h]; this
0x180009b17  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009b1e  mov     edx, 11Ah; void *
0x180009b23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b28  mov     rcx, rdi
0x180009b2b  mov     ebx, eax
0x180009b2d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b33  jmp     short loc_180009AEA
0x180009b35  mov     rcx, [rbx]
0x180009b38  mov     [rbx], rdi
0x180009b3b  test    rcx, rcx
0x180009b3e  jz      short loc_180009B46
0x180009b40  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b46  xor     eax, eax
0x180009b48  jmp     short loc_180009B60
0x180009b4a  mov     rcx, [rsp+38h]; this
0x180009b4f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009b56  mov     edx, 117h; void *
0x180009b5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b60  mov     rbx, [rsp+38h+arg_8]
0x180009b65  mov     rsi, [rsp+38h+arg_10]
0x180009b6a  add     rsp, 30h
0x180009b6e  pop     rdi
0x180009b6f  retn
```
