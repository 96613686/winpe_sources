# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x14001af94`
- end: `0x14001b0d4`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `320`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001d380`

## callees

- `0x140004c60`
- `0x140004c6c`
- `0x14001179c`
- `0x1400117bc`
- `0x14001af94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001affe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001affe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001afea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b067`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001afea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b067`

## string_xrefs

- `0x14001b030`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x14001b07c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x14001b0b2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
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
0x14001af94  mov     [rsp+arg_8], rbx
0x14001af99  mov     [rsp+arg_10], rsi
0x14001af9e  push    rdi
0x14001af9f  sub     rsp, 30h
0x14001afa3  mov     rbx, rcx
0x14001afa6  mov     rsi, rdx
0x14001afa9  mov     rcx, [rcx]; Block
0x14001afac  mov     qword ptr [rbx], 0
0x14001afb3  test    rcx, rcx
0x14001afb6  jz      short loc_14001AFBD
0x14001afb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001afbd  mov     rax, 0FFFFFFFFFFFFFFFAh
0x14001afc4  mov     [rsp+38h+TokenInformationLength], 0
0x14001afcc  test    rsi, rsi
0x14001afcf  cmovz   rsi, rax
0x14001afd3  xor     r9d, r9d; TokenInformationLength
0x14001afd6  lea     rax, [rsp+38h+TokenInformationLength]
0x14001afdb  xor     r8d, r8d; TokenInformation
0x14001afde  mov     rcx, rsi; TokenHandle
0x14001afe1  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x14001afe6  lea     edx, [r9+19h]; TokenInformationClass
0x14001afea  call    cs:__imp_GetTokenInformation
0x14001aff1  nop     dword ptr [rax+rax+00h]
0x14001aff6  test    eax, eax
0x14001aff8  jnz     loc_14001B0AD
0x14001affe  call    cs:__imp_GetLastError
0x14001b005  nop     dword ptr [rax+rax+00h]
0x14001b00a  cmp     eax, 7Ah ; 'z'
0x14001b00d  jnz     loc_14001B0AD
0x14001b013  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x14001b017  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b01e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001b023  mov     rdi, rax
0x14001b026  test    rax, rax
0x14001b029  jnz     short loc_14001B04D
0x14001b02b  mov     rcx, [rsp+38h]; this
0x14001b030  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001b037  mov     ebx, 8007000Eh
0x14001b03c  mov     edx, 119h; void *
0x14001b041  mov     r9d, ebx; char *
0x14001b044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b049  mov     eax, ebx
0x14001b04b  jmp     short loc_14001B0C3
0x14001b04d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14001b052  lea     rax, [rsp+38h+TokenInformationLength]
0x14001b057  mov     r8, rdi; TokenInformation
0x14001b05a  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x14001b05f  mov     edx, 19h; TokenInformationClass
0x14001b064  mov     rcx, rsi; TokenHandle
0x14001b067  call    cs:__imp_GetTokenInformation
0x14001b06e  nop     dword ptr [rax+rax+00h]
0x14001b073  test    eax, eax
0x14001b075  jnz     short loc_14001B099
0x14001b077  mov     rcx, [rsp+38h]; this
0x14001b07c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001b083  mov     edx, 11Ah; void *
0x14001b088  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001b08d  mov     rcx, rdi; Block
0x14001b090  mov     ebx, eax
0x14001b092  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001b097  jmp     short loc_14001B049
0x14001b099  mov     rcx, [rbx]; Block
0x14001b09c  mov     [rbx], rdi
0x14001b09f  test    rcx, rcx
0x14001b0a2  jz      short loc_14001B0A9
0x14001b0a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001b0a9  xor     eax, eax
0x14001b0ab  jmp     short loc_14001B0C3
0x14001b0ad  mov     rcx, [rsp+38h]; this
0x14001b0b2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001b0b9  mov     edx, 117h; void *
0x14001b0be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001b0c3  mov     rbx, [rsp+38h+arg_8]
0x14001b0c8  mov     rsi, [rsp+38h+arg_10]
0x14001b0cd  add     rsp, 30h
0x14001b0d1  pop     rdi
0x14001b0d2  retn
```
