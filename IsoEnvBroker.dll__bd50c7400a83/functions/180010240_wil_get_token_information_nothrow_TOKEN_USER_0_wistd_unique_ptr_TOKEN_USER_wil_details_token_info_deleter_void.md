# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180010240`
- end: `0x18001036d`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800116ac`
- `0x180034898`
- `0x180036178`
- `0x180038fc0`
- `0x180041b64`
- `0x1800507a8`
- `0x180056984`
- `0x180059200`
- `0x18005c4a8`

## callees

- `0x180002a30`
- `0x180002a54`
- `0x18000a444`
- `0x18000a464`
- `0x180010240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010296`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010307`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010296`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010307`

## string_xrefs

- `0x1800102d0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180010316`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001034c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x180010240  mov     [rsp+arg_8], rbx
0x180010245  mov     [rsp+arg_10], rsi
0x18001024a  push    rdi
0x18001024b  sub     rsp, 30h
0x18001024f  mov     rbx, rcx
0x180010252  mov     rsi, rdx
0x180010255  mov     rcx, [rcx]; Block
0x180010258  mov     qword ptr [rbx], 0
0x18001025f  test    rcx, rcx
0x180010262  jz      short loc_180010269
0x180010264  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010269  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180010270  mov     [rsp+38h+TokenInformationLength], 0
0x180010278  test    rsi, rsi
0x18001027b  cmovz   rsi, rax
0x18001027f  xor     r9d, r9d; TokenInformationLength
0x180010282  lea     rax, [rsp+38h+TokenInformationLength]
0x180010287  xor     r8d, r8d; TokenInformation
0x18001028a  mov     rcx, rsi; TokenHandle
0x18001028d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180010292  lea     edx, [r9+1]; TokenInformationClass
0x180010296  call    cs:__imp_GetTokenInformation
0x18001029c  test    eax, eax
0x18001029e  jnz     loc_180010347
0x1800102a4  call    cs:__imp_GetLastError
0x1800102aa  cmp     eax, 7Ah ; 'z'
0x1800102ad  jnz     loc_180010347
0x1800102b3  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800102b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800102be  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800102c3  mov     rdi, rax
0x1800102c6  test    rax, rax
0x1800102c9  jnz     short loc_1800102ED
0x1800102cb  mov     rcx, [rsp+38h]; this
0x1800102d0  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800102d7  mov     ebx, 8007000Eh
0x1800102dc  mov     edx, 119h; void *
0x1800102e1  mov     r9d, ebx; char *
0x1800102e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102e9  mov     eax, ebx
0x1800102eb  jmp     short loc_18001035D
0x1800102ed  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800102f2  lea     rax, [rsp+38h+TokenInformationLength]
0x1800102f7  mov     r8, rdi; TokenInformation
0x1800102fa  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800102ff  mov     edx, 1; TokenInformationClass
0x180010304  mov     rcx, rsi; TokenHandle
0x180010307  call    cs:__imp_GetTokenInformation
0x18001030d  test    eax, eax
0x18001030f  jnz     short loc_180010333
0x180010311  mov     rcx, [rsp+38h]; this
0x180010316  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001031d  mov     edx, 11Ah; void *
0x180010322  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010327  mov     rcx, rdi; Block
0x18001032a  mov     ebx, eax
0x18001032c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010331  jmp     short loc_1800102E9
0x180010333  mov     rcx, [rbx]; Block
0x180010336  mov     [rbx], rdi
0x180010339  test    rcx, rcx
0x18001033c  jz      short loc_180010343
0x18001033e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010343  xor     eax, eax
0x180010345  jmp     short loc_18001035D
0x180010347  mov     rcx, [rsp+38h]; this
0x18001034c  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010353  mov     edx, 117h; void *
0x180010358  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001035d  mov     rbx, [rsp+38h+arg_8]
0x180010362  mov     rsi, [rsp+38h+arg_10]
0x180010367  add     rsp, 30h
0x18001036b  pop     rdi
0x18001036c  retn
```
