# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180026be4`
- end: `0x180026d11`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002afc8`
- `0x18002c454`

## callees

- `0x180002ba0`
- `0x180003a94`
- `0x18000aaf4`
- `0x18000ab14`
- `0x180026be4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c48`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026cab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026cab`

## string_xrefs

- `0x180026c74`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180026cba`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180026cf0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x180026be4  mov     [rsp+arg_8], rbx
0x180026be9  mov     [rsp+arg_10], rsi
0x180026bee  push    rdi
0x180026bef  sub     rsp, 30h
0x180026bf3  mov     rbx, rcx
0x180026bf6  mov     rsi, rdx
0x180026bf9  mov     rcx, [rcx]; Block
0x180026bfc  mov     qword ptr [rbx], 0
0x180026c03  test    rcx, rcx
0x180026c06  jz      short loc_180026C0D
0x180026c08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026c0d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180026c14  mov     [rsp+38h+TokenInformationLength], 0
0x180026c1c  test    rsi, rsi
0x180026c1f  cmovz   rsi, rax
0x180026c23  xor     r9d, r9d; TokenInformationLength
0x180026c26  lea     rax, [rsp+38h+TokenInformationLength]
0x180026c2b  xor     r8d, r8d; TokenInformation
0x180026c2e  mov     rcx, rsi; TokenHandle
0x180026c31  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180026c36  lea     edx, [r9+1]; TokenInformationClass
0x180026c3a  call    cs:__imp_GetTokenInformation
0x180026c40  test    eax, eax
0x180026c42  jnz     loc_180026CEB
0x180026c48  call    cs:__imp_GetLastError
0x180026c4e  cmp     eax, 7Ah ; 'z'
0x180026c51  jnz     loc_180026CEB
0x180026c57  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180026c5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026c62  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026c67  mov     rdi, rax
0x180026c6a  test    rax, rax
0x180026c6d  jnz     short loc_180026C91
0x180026c6f  mov     rcx, [rsp+38h]; this
0x180026c74  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026c7b  mov     ebx, 8007000Eh
0x180026c80  mov     edx, 119h; void *
0x180026c85  mov     r9d, ebx; char *
0x180026c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c8d  mov     eax, ebx
0x180026c8f  jmp     short loc_180026D01
0x180026c91  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180026c96  lea     rax, [rsp+38h+TokenInformationLength]
0x180026c9b  mov     r8, rdi; TokenInformation
0x180026c9e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180026ca3  mov     edx, 1; TokenInformationClass
0x180026ca8  mov     rcx, rsi; TokenHandle
0x180026cab  call    cs:__imp_GetTokenInformation
0x180026cb1  test    eax, eax
0x180026cb3  jnz     short loc_180026CD7
0x180026cb5  mov     rcx, [rsp+38h]; this
0x180026cba  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026cc1  mov     edx, 11Ah; void *
0x180026cc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026ccb  mov     rcx, rdi; Block
0x180026cce  mov     ebx, eax
0x180026cd0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026cd5  jmp     short loc_180026C8D
0x180026cd7  mov     rcx, [rbx]; Block
0x180026cda  mov     [rbx], rdi
0x180026cdd  test    rcx, rcx
0x180026ce0  jz      short loc_180026CE7
0x180026ce2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ce7  xor     eax, eax
0x180026ce9  jmp     short loc_180026D01
0x180026ceb  mov     rcx, [rsp+38h]; this
0x180026cf0  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026cf7  mov     edx, 117h; void *
0x180026cfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026d01  mov     rbx, [rsp+38h+arg_8]
0x180026d06  mov     rsi, [rsp+38h+arg_10]
0x180026d0b  add     rsp, 30h
0x180026d0f  pop     rdi
0x180026d10  retn
```
