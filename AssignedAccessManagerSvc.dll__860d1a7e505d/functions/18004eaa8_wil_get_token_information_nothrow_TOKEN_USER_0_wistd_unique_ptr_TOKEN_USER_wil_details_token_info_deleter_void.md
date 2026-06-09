# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18004eaa8`
- end: `0x18004ebd5`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004f79c`

## callees

- `0x180006f2c`
- `0x1800088bc`
- `0x18000b694`
- `0x18000b6b4`
- `0x18004eaa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004eafe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004eb6f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004eafe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004eb6f`

## string_xrefs

- `0x18004eb38`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18004eb7e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18004ebb4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18004eaa8  mov     [rsp+arg_8], rbx
0x18004eaad  mov     [rsp+arg_10], rsi
0x18004eab2  push    rdi
0x18004eab3  sub     rsp, 30h
0x18004eab7  mov     rbx, rcx
0x18004eaba  mov     rsi, rdx
0x18004eabd  mov     rcx, [rcx]; Block
0x18004eac0  mov     qword ptr [rbx], 0
0x18004eac7  test    rcx, rcx
0x18004eaca  jz      short loc_18004EAD1
0x18004eacc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004ead1  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18004ead8  mov     [rsp+38h+TokenInformationLength], 0
0x18004eae0  test    rsi, rsi
0x18004eae3  cmovz   rsi, rax
0x18004eae7  xor     r9d, r9d; TokenInformationLength
0x18004eaea  lea     rax, [rsp+38h+TokenInformationLength]
0x18004eaef  xor     r8d, r8d; TokenInformation
0x18004eaf2  mov     rcx, rsi; TokenHandle
0x18004eaf5  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18004eafa  lea     edx, [r9+1]; TokenInformationClass
0x18004eafe  call    cs:__imp_GetTokenInformation
0x18004eb04  test    eax, eax
0x18004eb06  jnz     loc_18004EBAF
0x18004eb0c  call    cs:__imp_GetLastError
0x18004eb12  cmp     eax, 7Ah ; 'z'
0x18004eb15  jnz     loc_18004EBAF
0x18004eb1b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18004eb1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004eb26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004eb2b  mov     rdi, rax
0x18004eb2e  test    rax, rax
0x18004eb31  jnz     short loc_18004EB55
0x18004eb33  mov     rcx, [rsp+38h]; this
0x18004eb38  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004eb3f  mov     ebx, 8007000Eh
0x18004eb44  mov     edx, 119h; void *
0x18004eb49  mov     r9d, ebx; char *
0x18004eb4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb51  mov     eax, ebx
0x18004eb53  jmp     short loc_18004EBC5
0x18004eb55  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18004eb5a  lea     rax, [rsp+38h+TokenInformationLength]
0x18004eb5f  mov     r8, rdi; TokenInformation
0x18004eb62  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18004eb67  mov     edx, 1; TokenInformationClass
0x18004eb6c  mov     rcx, rsi; TokenHandle
0x18004eb6f  call    cs:__imp_GetTokenInformation
0x18004eb75  test    eax, eax
0x18004eb77  jnz     short loc_18004EB9B
0x18004eb79  mov     rcx, [rsp+38h]; this
0x18004eb7e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004eb85  mov     edx, 11Ah; void *
0x18004eb8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004eb8f  mov     rcx, rdi; Block
0x18004eb92  mov     ebx, eax
0x18004eb94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004eb99  jmp     short loc_18004EB51
0x18004eb9b  mov     rcx, [rbx]; Block
0x18004eb9e  mov     [rbx], rdi
0x18004eba1  test    rcx, rcx
0x18004eba4  jz      short loc_18004EBAB
0x18004eba6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004ebab  xor     eax, eax
0x18004ebad  jmp     short loc_18004EBC5
0x18004ebaf  mov     rcx, [rsp+38h]; this
0x18004ebb4  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004ebbb  mov     edx, 117h; void *
0x18004ebc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ebc5  mov     rbx, [rsp+38h+arg_8]
0x18004ebca  mov     rsi, [rsp+38h+arg_10]
0x18004ebcf  add     rsp, 30h
0x18004ebd3  pop     rdi
0x18004ebd4  retn
```
