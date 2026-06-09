# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800129f4`
- end: `0x180012b21`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012f64`

## callees

- `0x180003100`
- `0x180003124`
- `0x180007f8c`
- `0x180007fac`
- `0x1800129f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012a4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012abb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012a4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012abb`

## string_xrefs

- `0x180012a84`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180012aca`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180012b00`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x1800129f4  mov     [rsp+arg_8], rbx
0x1800129f9  mov     [rsp+arg_10], rsi
0x1800129fe  push    rdi
0x1800129ff  sub     rsp, 30h
0x180012a03  mov     rbx, rcx
0x180012a06  mov     rsi, rdx
0x180012a09  mov     rcx, [rcx]; Block
0x180012a0c  mov     qword ptr [rbx], 0
0x180012a13  test    rcx, rcx
0x180012a16  jz      short loc_180012A1D
0x180012a18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012a1d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180012a24  mov     [rsp+38h+TokenInformationLength], 0
0x180012a2c  test    rsi, rsi
0x180012a2f  cmovz   rsi, rax
0x180012a33  xor     r9d, r9d; TokenInformationLength
0x180012a36  lea     rax, [rsp+38h+TokenInformationLength]
0x180012a3b  xor     r8d, r8d; TokenInformation
0x180012a3e  mov     rcx, rsi; TokenHandle
0x180012a41  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180012a46  lea     edx, [r9+1]; TokenInformationClass
0x180012a4a  call    cs:__imp_GetTokenInformation
0x180012a50  test    eax, eax
0x180012a52  jnz     loc_180012AFB
0x180012a58  call    cs:__imp_GetLastError
0x180012a5e  cmp     eax, 7Ah ; 'z'
0x180012a61  jnz     loc_180012AFB
0x180012a67  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180012a6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012a72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012a77  mov     rdi, rax
0x180012a7a  test    rax, rax
0x180012a7d  jnz     short loc_180012AA1
0x180012a7f  mov     rcx, [rsp+38h]; this
0x180012a84  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012a8b  mov     ebx, 8007000Eh
0x180012a90  mov     edx, 119h; void *
0x180012a95  mov     r9d, ebx; char *
0x180012a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a9d  mov     eax, ebx
0x180012a9f  jmp     short loc_180012B11
0x180012aa1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180012aa6  lea     rax, [rsp+38h+TokenInformationLength]
0x180012aab  mov     r8, rdi; TokenInformation
0x180012aae  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180012ab3  mov     edx, 1; TokenInformationClass
0x180012ab8  mov     rcx, rsi; TokenHandle
0x180012abb  call    cs:__imp_GetTokenInformation
0x180012ac1  test    eax, eax
0x180012ac3  jnz     short loc_180012AE7
0x180012ac5  mov     rcx, [rsp+38h]; this
0x180012aca  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012ad1  mov     edx, 11Ah; void *
0x180012ad6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012adb  mov     rcx, rdi; Block
0x180012ade  mov     ebx, eax
0x180012ae0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012ae5  jmp     short loc_180012A9D
0x180012ae7  mov     rcx, [rbx]; Block
0x180012aea  mov     [rbx], rdi
0x180012aed  test    rcx, rcx
0x180012af0  jz      short loc_180012AF7
0x180012af2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012af7  xor     eax, eax
0x180012af9  jmp     short loc_180012B11
0x180012afb  mov     rcx, [rsp+38h]; this
0x180012b00  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012b07  mov     edx, 117h; void *
0x180012b0c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012b11  mov     rbx, [rsp+38h+arg_8]
0x180012b16  mov     rsi, [rsp+38h+arg_10]
0x180012b1b  add     rsp, 30h
0x180012b1f  pop     rdi
0x180012b20  retn
```
