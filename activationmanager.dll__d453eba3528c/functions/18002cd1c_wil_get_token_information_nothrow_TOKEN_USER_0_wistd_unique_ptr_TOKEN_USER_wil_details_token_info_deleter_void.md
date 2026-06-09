# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18002cd1c`
- end: `0x18002ce49`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c930`
- `0x18002cc58`
- `0x18007e900`
- `0x18008e300`
- `0x18008e804`

## callees

- `0x18000b5c0`
- `0x18002cd1c`
- `0x180044408`
- `0x18005b37c`
- `0x18005b3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd80`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cd72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cde3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cd72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cde3`

## string_xrefs

- `0x18002cdac`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002cdf2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002ce28`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
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
0x18002cd1c  mov     [rsp+arg_8], rbx
0x18002cd21  mov     [rsp+arg_10], rsi
0x18002cd26  push    rdi
0x18002cd27  sub     rsp, 30h
0x18002cd2b  mov     rbx, rcx
0x18002cd2e  mov     rsi, rdx
0x18002cd31  mov     rcx, [rcx]; Block
0x18002cd34  mov     qword ptr [rbx], 0
0x18002cd3b  test    rcx, rcx
0x18002cd3e  jz      short loc_18002CD45
0x18002cd40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cd45  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18002cd4c  mov     [rsp+38h+TokenInformationLength], 0
0x18002cd54  test    rsi, rsi
0x18002cd57  cmovz   rsi, rax
0x18002cd5b  xor     r9d, r9d; TokenInformationLength
0x18002cd5e  lea     rax, [rsp+38h+TokenInformationLength]
0x18002cd63  xor     r8d, r8d; TokenInformation
0x18002cd66  mov     rcx, rsi; TokenHandle
0x18002cd69  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18002cd6e  lea     edx, [r9+1]; TokenInformationClass
0x18002cd72  call    cs:__imp_GetTokenInformation
0x18002cd78  test    eax, eax
0x18002cd7a  jnz     loc_18002CE23
0x18002cd80  call    cs:__imp_GetLastError
0x18002cd86  cmp     eax, 7Ah ; 'z'
0x18002cd89  jnz     loc_18002CE23
0x18002cd8f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18002cd93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cd9a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cd9f  mov     rdi, rax
0x18002cda2  test    rax, rax
0x18002cda5  jnz     short loc_18002CDC9
0x18002cda7  mov     rcx, [rsp+38h]; this
0x18002cdac  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cdb3  mov     ebx, 8007000Eh
0x18002cdb8  mov     edx, 119h; void *
0x18002cdbd  mov     r9d, ebx; char *
0x18002cdc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdc5  mov     eax, ebx
0x18002cdc7  jmp     short loc_18002CE39
0x18002cdc9  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002cdce  lea     rax, [rsp+38h+TokenInformationLength]
0x18002cdd3  mov     r8, rdi; TokenInformation
0x18002cdd6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18002cddb  mov     edx, 1; TokenInformationClass
0x18002cde0  mov     rcx, rsi; TokenHandle
0x18002cde3  call    cs:__imp_GetTokenInformation
0x18002cde9  test    eax, eax
0x18002cdeb  jnz     short loc_18002CE0F
0x18002cded  mov     rcx, [rsp+38h]; this
0x18002cdf2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cdf9  mov     edx, 11Ah; void *
0x18002cdfe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ce03  mov     rcx, rdi; Block
0x18002ce06  mov     ebx, eax
0x18002ce08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ce0d  jmp     short loc_18002CDC5
0x18002ce0f  mov     rcx, [rbx]; Block
0x18002ce12  mov     [rbx], rdi
0x18002ce15  test    rcx, rcx
0x18002ce18  jz      short loc_18002CE1F
0x18002ce1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ce1f  xor     eax, eax
0x18002ce21  jmp     short loc_18002CE39
0x18002ce23  mov     rcx, [rsp+38h]; this
0x18002ce28  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ce2f  mov     edx, 117h; void *
0x18002ce34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ce39  mov     rbx, [rsp+38h+arg_8]
0x18002ce3e  mov     rsi, [rsp+38h+arg_10]
0x18002ce43  add     rsp, 30h
0x18002ce47  pop     rdi
0x18002ce48  retn
```
