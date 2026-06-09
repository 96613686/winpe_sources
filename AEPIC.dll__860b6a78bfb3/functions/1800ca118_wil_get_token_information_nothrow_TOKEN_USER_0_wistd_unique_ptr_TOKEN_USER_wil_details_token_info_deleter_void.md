# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800ca118`
- end: `0x1800ca245`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c9b28`

## callees

- `0x180005d6c`
- `0x1800060e8`
- `0x18000c35c`
- `0x18000c37c`
- `0x1800ca118`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca17c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca16e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca1df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca16e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca1df`

## string_xrefs

- `0x1800ca1a8`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800ca1ee`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800ca224`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x1800ca118  mov     [rsp+arg_8], rbx
0x1800ca11d  mov     [rsp+arg_10], rsi
0x1800ca122  push    rdi
0x1800ca123  sub     rsp, 30h
0x1800ca127  mov     rbx, rcx
0x1800ca12a  mov     rsi, rdx
0x1800ca12d  mov     rcx, [rcx]; Block
0x1800ca130  mov     qword ptr [rbx], 0
0x1800ca137  test    rcx, rcx
0x1800ca13a  jz      short loc_1800CA141
0x1800ca13c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ca141  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800ca148  mov     [rsp+38h+TokenInformationLength], 0
0x1800ca150  test    rsi, rsi
0x1800ca153  cmovz   rsi, rax
0x1800ca157  xor     r9d, r9d; TokenInformationLength
0x1800ca15a  lea     rax, [rsp+38h+TokenInformationLength]
0x1800ca15f  xor     r8d, r8d; TokenInformation
0x1800ca162  mov     rcx, rsi; TokenHandle
0x1800ca165  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800ca16a  lea     edx, [r9+1]; TokenInformationClass
0x1800ca16e  call    cs:__imp_GetTokenInformation
0x1800ca174  test    eax, eax
0x1800ca176  jnz     loc_1800CA21F
0x1800ca17c  call    cs:__imp_GetLastError
0x1800ca182  cmp     eax, 7Ah ; 'z'
0x1800ca185  jnz     loc_1800CA21F
0x1800ca18b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800ca18f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ca196  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ca19b  mov     rdi, rax
0x1800ca19e  test    rax, rax
0x1800ca1a1  jnz     short loc_1800CA1C5
0x1800ca1a3  mov     rcx, [rsp+38h]; this
0x1800ca1a8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800ca1af  mov     ebx, 8007000Eh
0x1800ca1b4  mov     edx, 119h; void *
0x1800ca1b9  mov     r9d, ebx; char *
0x1800ca1bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca1c1  mov     eax, ebx
0x1800ca1c3  jmp     short loc_1800CA235
0x1800ca1c5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800ca1ca  lea     rax, [rsp+38h+TokenInformationLength]
0x1800ca1cf  mov     r8, rdi; TokenInformation
0x1800ca1d2  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800ca1d7  mov     edx, 1; TokenInformationClass
0x1800ca1dc  mov     rcx, rsi; TokenHandle
0x1800ca1df  call    cs:__imp_GetTokenInformation
0x1800ca1e5  test    eax, eax
0x1800ca1e7  jnz     short loc_1800CA20B
0x1800ca1e9  mov     rcx, [rsp+38h]; this
0x1800ca1ee  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800ca1f5  mov     edx, 11Ah; void *
0x1800ca1fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ca1ff  mov     rcx, rdi; Block
0x1800ca202  mov     ebx, eax
0x1800ca204  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ca209  jmp     short loc_1800CA1C1
0x1800ca20b  mov     rcx, [rbx]; Block
0x1800ca20e  mov     [rbx], rdi
0x1800ca211  test    rcx, rcx
0x1800ca214  jz      short loc_1800CA21B
0x1800ca216  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ca21b  xor     eax, eax
0x1800ca21d  jmp     short loc_1800CA235
0x1800ca21f  mov     rcx, [rsp+38h]; this
0x1800ca224  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800ca22b  mov     edx, 117h; void *
0x1800ca230  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ca235  mov     rbx, [rsp+38h+arg_8]
0x1800ca23a  mov     rsi, [rsp+38h+arg_10]
0x1800ca23f  add     rsp, 30h
0x1800ca243  pop     rdi
0x1800ca244  retn
```
