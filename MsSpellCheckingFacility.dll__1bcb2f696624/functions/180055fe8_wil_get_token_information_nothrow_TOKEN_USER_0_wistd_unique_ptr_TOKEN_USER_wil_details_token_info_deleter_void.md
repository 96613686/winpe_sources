# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180055fe8`
- end: `0x180056115`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180055f90`

## callees

- `0x18004aa2c`
- `0x18004aa50`
- `0x180055fe8`
- `0x180061304`
- `0x18006183c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005604c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005604c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005603e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800560af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005603e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800560af`

## string_xrefs

- `0x180056078`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800560be`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800560f4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180055fe8  mov     [rsp+arg_8], rbx
0x180055fed  mov     [rsp+arg_10], rsi
0x180055ff2  push    rdi
0x180055ff3  sub     rsp, 30h
0x180055ff7  mov     rbx, rcx
0x180055ffa  mov     rsi, rdx
0x180055ffd  mov     rcx, [rcx]; Block
0x180056000  mov     qword ptr [rbx], 0
0x180056007  test    rcx, rcx
0x18005600a  jz      short loc_180056011
0x18005600c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056011  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180056018  mov     [rsp+38h+TokenInformationLength], 0
0x180056020  test    rsi, rsi
0x180056023  cmovz   rsi, rax
0x180056027  xor     r9d, r9d; TokenInformationLength
0x18005602a  lea     rax, [rsp+38h+TokenInformationLength]
0x18005602f  xor     r8d, r8d; TokenInformation
0x180056032  mov     rcx, rsi; TokenHandle
0x180056035  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18005603a  lea     edx, [r9+1]; TokenInformationClass
0x18005603e  call    cs:__imp_GetTokenInformation
0x180056044  test    eax, eax
0x180056046  jnz     loc_1800560EF
0x18005604c  call    cs:__imp_GetLastError
0x180056052  cmp     eax, 7Ah ; 'z'
0x180056055  jnz     loc_1800560EF
0x18005605b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18005605f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180056066  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005606b  mov     rdi, rax
0x18005606e  test    rax, rax
0x180056071  jnz     short loc_180056095
0x180056073  mov     rcx, [rsp+38h]; this
0x180056078  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005607f  mov     ebx, 8007000Eh
0x180056084  mov     edx, 119h; void *
0x180056089  mov     r9d, ebx; char *
0x18005608c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056091  mov     eax, ebx
0x180056093  jmp     short loc_180056105
0x180056095  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18005609a  lea     rax, [rsp+38h+TokenInformationLength]
0x18005609f  mov     r8, rdi; TokenInformation
0x1800560a2  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800560a7  mov     edx, 1; TokenInformationClass
0x1800560ac  mov     rcx, rsi; TokenHandle
0x1800560af  call    cs:__imp_GetTokenInformation
0x1800560b5  test    eax, eax
0x1800560b7  jnz     short loc_1800560DB
0x1800560b9  mov     rcx, [rsp+38h]; this
0x1800560be  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800560c5  mov     edx, 11Ah; void *
0x1800560ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800560cf  mov     rcx, rdi; Block
0x1800560d2  mov     ebx, eax
0x1800560d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800560d9  jmp     short loc_180056091
0x1800560db  mov     rcx, [rbx]; Block
0x1800560de  mov     [rbx], rdi
0x1800560e1  test    rcx, rcx
0x1800560e4  jz      short loc_1800560EB
0x1800560e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800560eb  xor     eax, eax
0x1800560ed  jmp     short loc_180056105
0x1800560ef  mov     rcx, [rsp+38h]; this
0x1800560f4  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800560fb  mov     edx, 117h; void *
0x180056100  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180056105  mov     rbx, [rsp+38h+arg_8]
0x18005610a  mov     rsi, [rsp+38h+arg_10]
0x18005610f  add     rsp, 30h
0x180056113  pop     rdi
0x180056114  retn
```
