# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18002cb68`
- end: `0x18002cc95`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c8cc`

## callees

- `0x180003f50`
- `0x180004cd0`
- `0x18000bdfc`
- `0x18000be1c`
- `0x18002cb68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbcc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cbbe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cc2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cbbe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cc2f`

## string_xrefs

- `0x18002cbf8`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002cc3e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002cc74`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18002cb68  mov     [rsp+arg_8], rbx
0x18002cb6d  mov     [rsp+arg_10], rsi
0x18002cb72  push    rdi
0x18002cb73  sub     rsp, 30h
0x18002cb77  mov     rbx, rcx
0x18002cb7a  mov     rsi, rdx
0x18002cb7d  mov     rcx, [rcx]; Block
0x18002cb80  mov     qword ptr [rbx], 0
0x18002cb87  test    rcx, rcx
0x18002cb8a  jz      short loc_18002CB91
0x18002cb8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cb91  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18002cb98  mov     [rsp+38h+TokenInformationLength], 0
0x18002cba0  test    rsi, rsi
0x18002cba3  cmovz   rsi, rax
0x18002cba7  xor     r9d, r9d; TokenInformationLength
0x18002cbaa  lea     rax, [rsp+38h+TokenInformationLength]
0x18002cbaf  xor     r8d, r8d; TokenInformation
0x18002cbb2  mov     rcx, rsi; TokenHandle
0x18002cbb5  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18002cbba  lea     edx, [r9+1]; TokenInformationClass
0x18002cbbe  call    cs:__imp_GetTokenInformation
0x18002cbc4  test    eax, eax
0x18002cbc6  jnz     loc_18002CC6F
0x18002cbcc  call    cs:__imp_GetLastError
0x18002cbd2  cmp     eax, 7Ah ; 'z'
0x18002cbd5  jnz     loc_18002CC6F
0x18002cbdb  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18002cbdf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cbe6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cbeb  mov     rdi, rax
0x18002cbee  test    rax, rax
0x18002cbf1  jnz     short loc_18002CC15
0x18002cbf3  mov     rcx, [rsp+38h]; this
0x18002cbf8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cbff  mov     ebx, 8007000Eh
0x18002cc04  mov     edx, 119h; void *
0x18002cc09  mov     r9d, ebx; char *
0x18002cc0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc11  mov     eax, ebx
0x18002cc13  jmp     short loc_18002CC85
0x18002cc15  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002cc1a  lea     rax, [rsp+38h+TokenInformationLength]
0x18002cc1f  mov     r8, rdi; TokenInformation
0x18002cc22  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18002cc27  mov     edx, 1; TokenInformationClass
0x18002cc2c  mov     rcx, rsi; TokenHandle
0x18002cc2f  call    cs:__imp_GetTokenInformation
0x18002cc35  test    eax, eax
0x18002cc37  jnz     short loc_18002CC5B
0x18002cc39  mov     rcx, [rsp+38h]; this
0x18002cc3e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cc45  mov     edx, 11Ah; void *
0x18002cc4a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cc4f  mov     rcx, rdi; Block
0x18002cc52  mov     ebx, eax
0x18002cc54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cc59  jmp     short loc_18002CC11
0x18002cc5b  mov     rcx, [rbx]; Block
0x18002cc5e  mov     [rbx], rdi
0x18002cc61  test    rcx, rcx
0x18002cc64  jz      short loc_18002CC6B
0x18002cc66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cc6b  xor     eax, eax
0x18002cc6d  jmp     short loc_18002CC85
0x18002cc6f  mov     rcx, [rsp+38h]; this
0x18002cc74  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cc7b  mov     edx, 117h; void *
0x18002cc80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cc85  mov     rbx, [rsp+38h+arg_8]
0x18002cc8a  mov     rsi, [rsp+38h+arg_10]
0x18002cc8f  add     rsp, 30h
0x18002cc93  pop     rdi
0x18002cc94  retn
```
