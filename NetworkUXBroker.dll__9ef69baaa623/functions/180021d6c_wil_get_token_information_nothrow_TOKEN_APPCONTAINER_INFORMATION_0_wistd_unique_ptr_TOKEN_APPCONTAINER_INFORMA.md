# wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x180021d6c`
- end: `0x180021e99`
- name: `??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022194`

## callees

- `0x180002a04`
- `0x180002a28`
- `0x18000e768`
- `0x18001916c`
- `0x180021d6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021dd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021dc2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021e33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021dc2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021e33`

## string_xrefs

- `0x180021dfc`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180021e42`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180021e78`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenAppContainerSid, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenAppContainerSid, v6, TokenInformationLength, &TokenInformationLength) )
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
0x180021d6c  mov     [rsp+arg_8], rbx
0x180021d71  mov     [rsp+arg_10], rsi
0x180021d76  push    rdi
0x180021d77  sub     rsp, 30h
0x180021d7b  mov     rbx, rcx
0x180021d7e  mov     rsi, rdx
0x180021d81  mov     rcx, [rcx]; Block
0x180021d84  mov     qword ptr [rbx], 0
0x180021d8b  test    rcx, rcx
0x180021d8e  jz      short loc_180021D95
0x180021d90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d95  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180021d9c  mov     [rsp+38h+TokenInformationLength], 0
0x180021da4  test    rsi, rsi
0x180021da7  cmovz   rsi, rax
0x180021dab  xor     r9d, r9d; TokenInformationLength
0x180021dae  lea     rax, [rsp+38h+TokenInformationLength]
0x180021db3  xor     r8d, r8d; TokenInformation
0x180021db6  mov     rcx, rsi; TokenHandle
0x180021db9  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180021dbe  lea     edx, [r9+1Fh]; TokenInformationClass
0x180021dc2  call    cs:__imp_GetTokenInformation
0x180021dc8  test    eax, eax
0x180021dca  jnz     loc_180021E73
0x180021dd0  call    cs:__imp_GetLastError
0x180021dd6  cmp     eax, 7Ah ; 'z'
0x180021dd9  jnz     loc_180021E73
0x180021ddf  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180021de3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021dea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021def  mov     rdi, rax
0x180021df2  test    rax, rax
0x180021df5  jnz     short loc_180021E19
0x180021df7  mov     rcx, [rsp+38h]; this
0x180021dfc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021e03  mov     ebx, 8007000Eh
0x180021e08  mov     edx, 119h; void *
0x180021e0d  mov     r9d, ebx; char *
0x180021e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e15  mov     eax, ebx
0x180021e17  jmp     short loc_180021E89
0x180021e19  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180021e1e  lea     rax, [rsp+38h+TokenInformationLength]
0x180021e23  mov     r8, rdi; TokenInformation
0x180021e26  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180021e2b  mov     edx, 1Fh; TokenInformationClass
0x180021e30  mov     rcx, rsi; TokenHandle
0x180021e33  call    cs:__imp_GetTokenInformation
0x180021e39  test    eax, eax
0x180021e3b  jnz     short loc_180021E5F
0x180021e3d  mov     rcx, [rsp+38h]; this
0x180021e42  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021e49  mov     edx, 11Ah; void *
0x180021e4e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021e53  mov     rcx, rdi; Block
0x180021e56  mov     ebx, eax
0x180021e58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021e5d  jmp     short loc_180021E15
0x180021e5f  mov     rcx, [rbx]; Block
0x180021e62  mov     [rbx], rdi
0x180021e65  test    rcx, rcx
0x180021e68  jz      short loc_180021E6F
0x180021e6a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021e6f  xor     eax, eax
0x180021e71  jmp     short loc_180021E89
0x180021e73  mov     rcx, [rsp+38h]; this
0x180021e78  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021e7f  mov     edx, 117h; void *
0x180021e84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021e89  mov     rbx, [rsp+38h+arg_8]
0x180021e8e  mov     rsi, [rsp+38h+arg_10]
0x180021e93  add     rsp, 30h
0x180021e97  pop     rdi
0x180021e98  retn
```
