# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180023d44`
- end: `0x180023e71`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023f1c`

## callees

- `0x180003ae4`
- `0x180003eb4`
- `0x18000c4ac`
- `0x18000c4cc`
- `0x180023d44`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023d9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023d9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023da8`

## string_xrefs

- `0x180023dd4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180023e1a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180023e50`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180023d44  mov     [rsp+arg_8], rbx
0x180023d49  mov     [rsp+arg_10], rsi
0x180023d4e  push    rdi
0x180023d4f  sub     rsp, 30h
0x180023d53  mov     rbx, rcx
0x180023d56  mov     rsi, rdx
0x180023d59  mov     rcx, [rcx]; Block
0x180023d5c  mov     qword ptr [rbx], 0
0x180023d63  test    rcx, rcx
0x180023d66  jz      short loc_180023D6D
0x180023d68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d6d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180023d74  mov     [rsp+38h+TokenInformationLength], 0
0x180023d7c  test    rsi, rsi
0x180023d7f  cmovz   rsi, rax
0x180023d83  xor     r9d, r9d; TokenInformationLength
0x180023d86  lea     rax, [rsp+38h+TokenInformationLength]
0x180023d8b  xor     r8d, r8d; TokenInformation
0x180023d8e  mov     rcx, rsi; TokenHandle
0x180023d91  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180023d96  lea     edx, [r9+1]; TokenInformationClass
0x180023d9a  call    cs:__imp_GetTokenInformation
0x180023da0  test    eax, eax
0x180023da2  jnz     loc_180023E4B
0x180023da8  call    cs:__imp_GetLastError
0x180023dae  cmp     eax, 7Ah ; 'z'
0x180023db1  jnz     loc_180023E4B
0x180023db7  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180023dbb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023dc2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023dc7  mov     rdi, rax
0x180023dca  test    rax, rax
0x180023dcd  jnz     short loc_180023DF1
0x180023dcf  mov     rcx, [rsp+38h]; this
0x180023dd4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023ddb  mov     ebx, 8007000Eh
0x180023de0  mov     edx, 119h; void *
0x180023de5  mov     r9d, ebx; char *
0x180023de8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ded  mov     eax, ebx
0x180023def  jmp     short loc_180023E61
0x180023df1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180023df6  lea     rax, [rsp+38h+TokenInformationLength]
0x180023dfb  mov     r8, rdi; TokenInformation
0x180023dfe  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180023e03  mov     edx, 1; TokenInformationClass
0x180023e08  mov     rcx, rsi; TokenHandle
0x180023e0b  call    cs:__imp_GetTokenInformation
0x180023e11  test    eax, eax
0x180023e13  jnz     short loc_180023E37
0x180023e15  mov     rcx, [rsp+38h]; this
0x180023e1a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023e21  mov     edx, 11Ah; void *
0x180023e26  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e2b  mov     rcx, rdi; Block
0x180023e2e  mov     ebx, eax
0x180023e30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023e35  jmp     short loc_180023DED
0x180023e37  mov     rcx, [rbx]; Block
0x180023e3a  mov     [rbx], rdi
0x180023e3d  test    rcx, rcx
0x180023e40  jz      short loc_180023E47
0x180023e42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023e47  xor     eax, eax
0x180023e49  jmp     short loc_180023E61
0x180023e4b  mov     rcx, [rsp+38h]; this
0x180023e50  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023e57  mov     edx, 117h; void *
0x180023e5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e61  mov     rbx, [rsp+38h+arg_8]
0x180023e66  mov     rsi, [rsp+38h+arg_10]
0x180023e6b  add     rsp, 30h
0x180023e6f  pop     rdi
0x180023e70  retn
```
