# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18017c0b0`
- end: `0x18017c1dd`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18017c058`

## callees

- `0x180078410`
- `0x180147170`
- `0x18017c0b0`
- `0x180188d74`
- `0x18018e800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017c114`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017c106`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017c177`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017c106`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18017c177`

## string_xrefs

- `0x18017c140`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18017c186`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18017c1bc`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18017c0b0  mov     [rsp+arg_8], rbx
0x18017c0b5  mov     [rsp+arg_10], rsi
0x18017c0ba  push    rdi
0x18017c0bb  sub     rsp, 30h
0x18017c0bf  mov     rbx, rcx
0x18017c0c2  mov     rsi, rdx
0x18017c0c5  mov     rcx, [rcx]; Block
0x18017c0c8  mov     qword ptr [rbx], 0
0x18017c0cf  test    rcx, rcx
0x18017c0d2  jz      short loc_18017C0D9
0x18017c0d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017c0d9  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18017c0e0  mov     [rsp+38h+TokenInformationLength], 0
0x18017c0e8  test    rsi, rsi
0x18017c0eb  cmovz   rsi, rax
0x18017c0ef  xor     r9d, r9d; TokenInformationLength
0x18017c0f2  lea     rax, [rsp+38h+TokenInformationLength]
0x18017c0f7  xor     r8d, r8d; TokenInformation
0x18017c0fa  mov     rcx, rsi; TokenHandle
0x18017c0fd  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18017c102  lea     edx, [r9+1]; TokenInformationClass
0x18017c106  call    cs:__imp_GetTokenInformation
0x18017c10c  test    eax, eax
0x18017c10e  jnz     loc_18017C1B7
0x18017c114  call    cs:__imp_GetLastError
0x18017c11a  cmp     eax, 7Ah ; 'z'
0x18017c11d  jnz     loc_18017C1B7
0x18017c123  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18017c127  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18017c12e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18017c133  mov     rdi, rax
0x18017c136  test    rax, rax
0x18017c139  jnz     short loc_18017C15D
0x18017c13b  mov     rcx, [rsp+38h]; this
0x18017c140  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18017c147  mov     ebx, 8007000Eh
0x18017c14c  mov     edx, 119h; void *
0x18017c151  mov     r9d, ebx; char *
0x18017c154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017c159  mov     eax, ebx
0x18017c15b  jmp     short loc_18017C1CD
0x18017c15d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18017c162  lea     rax, [rsp+38h+TokenInformationLength]
0x18017c167  mov     r8, rdi; TokenInformation
0x18017c16a  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18017c16f  mov     edx, 1; TokenInformationClass
0x18017c174  mov     rcx, rsi; TokenHandle
0x18017c177  call    cs:__imp_GetTokenInformation
0x18017c17d  test    eax, eax
0x18017c17f  jnz     short loc_18017C1A3
0x18017c181  mov     rcx, [rsp+38h]; this
0x18017c186  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18017c18d  mov     edx, 11Ah; void *
0x18017c192  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18017c197  mov     rcx, rdi; Block
0x18017c19a  mov     ebx, eax
0x18017c19c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017c1a1  jmp     short loc_18017C159
0x18017c1a3  mov     rcx, [rbx]; Block
0x18017c1a6  mov     [rbx], rdi
0x18017c1a9  test    rcx, rcx
0x18017c1ac  jz      short loc_18017C1B3
0x18017c1ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017c1b3  xor     eax, eax
0x18017c1b5  jmp     short loc_18017C1CD
0x18017c1b7  mov     rcx, [rsp+38h]; this
0x18017c1bc  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18017c1c3  mov     edx, 117h; void *
0x18017c1c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18017c1cd  mov     rbx, [rsp+38h+arg_8]
0x18017c1d2  mov     rsi, [rsp+38h+arg_10]
0x18017c1d7  add     rsp, 30h
0x18017c1db  pop     rdi
0x18017c1dc  retn
```
