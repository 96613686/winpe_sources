# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800182bc`
- end: `0x1800183f8`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `316`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001107c`
- `0x18002a1d8`
- `0x180032118`
- `0x180038de0`
- `0x180040730`

## callees

- `0x180007c78`
- `0x1800182bc`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001830c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018389`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001830c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018320`

## string_xrefs

- `0x180018352`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18001839e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800183d6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  if ( !a2 )
    a2 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    if ( GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = *a1;
      *a1 = v6;
      if ( v10 )
        operator delete(v10);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v8);
      operator delete(v6);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800182bc  mov     [rsp+arg_8], rbx
0x1800182c1  mov     [rsp+arg_10], rsi
0x1800182c6  push    rdi
0x1800182c7  sub     rsp, 30h
0x1800182cb  mov     rdi, rcx
0x1800182ce  mov     rsi, rdx
0x1800182d1  mov     rcx, [rcx]; Block
0x1800182d4  and     qword ptr [rdi], 0
0x1800182d8  test    rcx, rcx
0x1800182db  jz      short loc_1800182E2
0x1800182dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800182e2  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800182e9  test    rsi, rsi
0x1800182ec  cmovz   rsi, rax
0x1800182f0  and     [rsp+38h+TokenInformationLength], 0
0x1800182f5  xor     r9d, r9d; TokenInformationLength
0x1800182f8  lea     rax, [rsp+38h+TokenInformationLength]
0x1800182fd  xor     r8d, r8d; TokenInformation
0x180018300  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180018305  mov     rcx, rsi; TokenHandle
0x180018308  lea     edx, [r9+1]; TokenInformationClass
0x18001830c  call    cs:__imp_GetTokenInformation
0x180018313  nop     dword ptr [rax+rax+00h]
0x180018318  test    eax, eax
0x18001831a  jnz     loc_1800183D1
0x180018320  call    cs:__imp_GetLastError
0x180018327  nop     dword ptr [rax+rax+00h]
0x18001832c  cmp     eax, 7Ah ; 'z'
0x18001832f  jnz     loc_1800183D1
0x180018335  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180018339  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018340  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018345  mov     rbx, rax
0x180018348  test    rax, rax
0x18001834b  jnz     short loc_18001836F
0x18001834d  mov     rcx, [rsp+38h]; this
0x180018352  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018359  mov     ebx, 8007000Eh
0x18001835e  mov     edx, 119h; void *
0x180018363  mov     r9d, ebx; char *
0x180018366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001836b  mov     eax, ebx
0x18001836d  jmp     short loc_1800183E7
0x18001836f  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180018374  lea     rax, [rsp+38h+TokenInformationLength]
0x180018379  mov     r8, rbx; TokenInformation
0x18001837c  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180018381  mov     edx, 1; TokenInformationClass
0x180018386  mov     rcx, rsi; TokenHandle
0x180018389  call    cs:__imp_GetTokenInformation
0x180018390  nop     dword ptr [rax+rax+00h]
0x180018395  test    eax, eax
0x180018397  jnz     short loc_1800183BD
0x180018399  mov     rcx, [rsp+38h]; this
0x18001839e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183a5  mov     edx, 11Ah; void *
0x1800183aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800183af  mov     rcx, rbx; Block
0x1800183b2  mov     edi, eax
0x1800183b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800183b9  mov     eax, edi
0x1800183bb  jmp     short loc_1800183E7
0x1800183bd  mov     rcx, [rdi]; Block
0x1800183c0  mov     [rdi], rbx
0x1800183c3  test    rcx, rcx
0x1800183c6  jz      short loc_1800183CD
0x1800183c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800183cd  xor     eax, eax
0x1800183cf  jmp     short loc_1800183E7
0x1800183d1  mov     rcx, [rsp+38h]; this
0x1800183d6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183dd  mov     edx, 117h; void *
0x1800183e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800183e7  mov     rbx, [rsp+38h+arg_8]
0x1800183ec  mov     rsi, [rsp+38h+arg_10]
0x1800183f1  add     rsp, 30h
0x1800183f5  pop     rdi
0x1800183f6  retn
```
