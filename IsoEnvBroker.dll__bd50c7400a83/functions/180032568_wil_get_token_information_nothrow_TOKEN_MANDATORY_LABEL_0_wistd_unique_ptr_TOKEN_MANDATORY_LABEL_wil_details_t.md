# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x180032568`
- end: `0x180032695`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180034d48`

## callees

- `0x180002a30`
- `0x180002a54`
- `0x18000a444`
- `0x18000a464`
- `0x180032568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800325be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003262f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800325be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003262f`

## string_xrefs

- `0x1800325f8`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18003263e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180032674`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
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
0x180032568  mov     [rsp+arg_8], rbx
0x18003256d  mov     [rsp+arg_10], rsi
0x180032572  push    rdi
0x180032573  sub     rsp, 30h
0x180032577  mov     rbx, rcx
0x18003257a  mov     rsi, rdx
0x18003257d  mov     rcx, [rcx]; Block
0x180032580  mov     qword ptr [rbx], 0
0x180032587  test    rcx, rcx
0x18003258a  jz      short loc_180032591
0x18003258c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032591  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180032598  mov     [rsp+38h+TokenInformationLength], 0
0x1800325a0  test    rsi, rsi
0x1800325a3  cmovz   rsi, rax
0x1800325a7  xor     r9d, r9d; TokenInformationLength
0x1800325aa  lea     rax, [rsp+38h+TokenInformationLength]
0x1800325af  xor     r8d, r8d; TokenInformation
0x1800325b2  mov     rcx, rsi; TokenHandle
0x1800325b5  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800325ba  lea     edx, [r9+19h]; TokenInformationClass
0x1800325be  call    cs:__imp_GetTokenInformation
0x1800325c4  test    eax, eax
0x1800325c6  jnz     loc_18003266F
0x1800325cc  call    cs:__imp_GetLastError
0x1800325d2  cmp     eax, 7Ah ; 'z'
0x1800325d5  jnz     loc_18003266F
0x1800325db  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800325df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800325e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800325eb  mov     rdi, rax
0x1800325ee  test    rax, rax
0x1800325f1  jnz     short loc_180032615
0x1800325f3  mov     rcx, [rsp+38h]; this
0x1800325f8  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800325ff  mov     ebx, 8007000Eh
0x180032604  mov     edx, 119h; void *
0x180032609  mov     r9d, ebx; char *
0x18003260c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032611  mov     eax, ebx
0x180032613  jmp     short loc_180032685
0x180032615  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003261a  lea     rax, [rsp+38h+TokenInformationLength]
0x18003261f  mov     r8, rdi; TokenInformation
0x180032622  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180032627  mov     edx, 19h; TokenInformationClass
0x18003262c  mov     rcx, rsi; TokenHandle
0x18003262f  call    cs:__imp_GetTokenInformation
0x180032635  test    eax, eax
0x180032637  jnz     short loc_18003265B
0x180032639  mov     rcx, [rsp+38h]; this
0x18003263e  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180032645  mov     edx, 11Ah; void *
0x18003264a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003264f  mov     rcx, rdi; Block
0x180032652  mov     ebx, eax
0x180032654  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032659  jmp     short loc_180032611
0x18003265b  mov     rcx, [rbx]; Block
0x18003265e  mov     [rbx], rdi
0x180032661  test    rcx, rcx
0x180032664  jz      short loc_18003266B
0x180032666  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003266b  xor     eax, eax
0x18003266d  jmp     short loc_180032685
0x18003266f  mov     rcx, [rsp+38h]; this
0x180032674  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003267b  mov     edx, 117h; void *
0x180032680  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032685  mov     rbx, [rsp+38h+arg_8]
0x18003268a  mov     rsi, [rsp+38h+arg_10]
0x18003268f  add     rsp, 30h
0x180032693  pop     rdi
0x180032694  retn
```
