# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18002f4f4`
- end: `0x18002f621`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ee20`

## callees

- `0x180003cc4`
- `0x18000534c`
- `0x18000aa5c`
- `0x18000aa7c`
- `0x18002f4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f558`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f54a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f5bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f54a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f5bb`

## string_xrefs

- `0x18002f584`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002f5ca`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002f600`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18002f4f4  mov     [rsp+arg_8], rbx
0x18002f4f9  mov     [rsp+arg_10], rsi
0x18002f4fe  push    rdi
0x18002f4ff  sub     rsp, 30h
0x18002f503  mov     rbx, rcx
0x18002f506  mov     rsi, rdx
0x18002f509  mov     rcx, [rcx]; Block
0x18002f50c  mov     qword ptr [rbx], 0
0x18002f513  test    rcx, rcx
0x18002f516  jz      short loc_18002F51D
0x18002f518  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f51d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18002f524  mov     [rsp+38h+TokenInformationLength], 0
0x18002f52c  test    rsi, rsi
0x18002f52f  cmovz   rsi, rax
0x18002f533  xor     r9d, r9d; TokenInformationLength
0x18002f536  lea     rax, [rsp+38h+TokenInformationLength]
0x18002f53b  xor     r8d, r8d; TokenInformation
0x18002f53e  mov     rcx, rsi; TokenHandle
0x18002f541  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18002f546  lea     edx, [r9+1]; TokenInformationClass
0x18002f54a  call    cs:__imp_GetTokenInformation
0x18002f550  test    eax, eax
0x18002f552  jnz     loc_18002F5FB
0x18002f558  call    cs:__imp_GetLastError
0x18002f55e  cmp     eax, 7Ah ; 'z'
0x18002f561  jnz     loc_18002F5FB
0x18002f567  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18002f56b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f572  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f577  mov     rdi, rax
0x18002f57a  test    rax, rax
0x18002f57d  jnz     short loc_18002F5A1
0x18002f57f  mov     rcx, [rsp+38h]; this
0x18002f584  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f58b  mov     ebx, 8007000Eh
0x18002f590  mov     edx, 119h; void *
0x18002f595  mov     r9d, ebx; char *
0x18002f598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f59d  mov     eax, ebx
0x18002f59f  jmp     short loc_18002F611
0x18002f5a1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002f5a6  lea     rax, [rsp+38h+TokenInformationLength]
0x18002f5ab  mov     r8, rdi; TokenInformation
0x18002f5ae  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18002f5b3  mov     edx, 1; TokenInformationClass
0x18002f5b8  mov     rcx, rsi; TokenHandle
0x18002f5bb  call    cs:__imp_GetTokenInformation
0x18002f5c1  test    eax, eax
0x18002f5c3  jnz     short loc_18002F5E7
0x18002f5c5  mov     rcx, [rsp+38h]; this
0x18002f5ca  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f5d1  mov     edx, 11Ah; void *
0x18002f5d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f5db  mov     rcx, rdi; Block
0x18002f5de  mov     ebx, eax
0x18002f5e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f5e5  jmp     short loc_18002F59D
0x18002f5e7  mov     rcx, [rbx]; Block
0x18002f5ea  mov     [rbx], rdi
0x18002f5ed  test    rcx, rcx
0x18002f5f0  jz      short loc_18002F5F7
0x18002f5f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f5f7  xor     eax, eax
0x18002f5f9  jmp     short loc_18002F611
0x18002f5fb  mov     rcx, [rsp+38h]; this
0x18002f600  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f607  mov     edx, 117h; void *
0x18002f60c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f611  mov     rbx, [rsp+38h+arg_8]
0x18002f616  mov     rsi, [rsp+38h+arg_10]
0x18002f61b  add     rsp, 30h
0x18002f61f  pop     rdi
0x18002f620  retn
```
