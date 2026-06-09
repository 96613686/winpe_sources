# wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x180120e34`
- end: `0x180120f61`
- name: `??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180121730`

## callees

- `0x180036da4`
- `0x180036dc8`
- `0x180052df0`
- `0x180052e80`
- `0x180120e34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120e98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180120e8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180120efb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180120e8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180120efb`

## string_xrefs

- `0x180120ec4`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180120f0a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180120f40`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x180120e34  mov     [rsp+arg_8], rbx
0x180120e39  mov     [rsp+arg_10], rsi
0x180120e3e  push    rdi
0x180120e3f  sub     rsp, 30h
0x180120e43  mov     rbx, rcx
0x180120e46  mov     rsi, rdx
0x180120e49  mov     rcx, [rcx]; Block
0x180120e4c  mov     qword ptr [rbx], 0
0x180120e53  test    rcx, rcx
0x180120e56  jz      short loc_180120E5D
0x180120e58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180120e5d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180120e64  mov     [rsp+38h+TokenInformationLength], 0
0x180120e6c  test    rsi, rsi
0x180120e6f  cmovz   rsi, rax
0x180120e73  xor     r9d, r9d; TokenInformationLength
0x180120e76  lea     rax, [rsp+38h+TokenInformationLength]
0x180120e7b  xor     r8d, r8d; TokenInformation
0x180120e7e  mov     rcx, rsi; TokenHandle
0x180120e81  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180120e86  lea     edx, [r9+1Fh]; TokenInformationClass
0x180120e8a  call    cs:__imp_GetTokenInformation
0x180120e90  test    eax, eax
0x180120e92  jnz     loc_180120F3B
0x180120e98  call    cs:__imp_GetLastError
0x180120e9e  cmp     eax, 7Ah ; 'z'
0x180120ea1  jnz     loc_180120F3B
0x180120ea7  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180120eab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180120eb2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180120eb7  mov     rdi, rax
0x180120eba  test    rax, rax
0x180120ebd  jnz     short loc_180120EE1
0x180120ebf  mov     rcx, [rsp+38h]; this
0x180120ec4  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180120ecb  mov     ebx, 8007000Eh
0x180120ed0  mov     edx, 119h; void *
0x180120ed5  mov     r9d, ebx; char *
0x180120ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120edd  mov     eax, ebx
0x180120edf  jmp     short loc_180120F51
0x180120ee1  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180120ee6  lea     rax, [rsp+38h+TokenInformationLength]
0x180120eeb  mov     r8, rdi; TokenInformation
0x180120eee  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180120ef3  mov     edx, 1Fh; TokenInformationClass
0x180120ef8  mov     rcx, rsi; TokenHandle
0x180120efb  call    cs:__imp_GetTokenInformation
0x180120f01  test    eax, eax
0x180120f03  jnz     short loc_180120F27
0x180120f05  mov     rcx, [rsp+38h]; this
0x180120f0a  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180120f11  mov     edx, 11Ah; void *
0x180120f16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180120f1b  mov     rcx, rdi; Block
0x180120f1e  mov     ebx, eax
0x180120f20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180120f25  jmp     short loc_180120EDD
0x180120f27  mov     rcx, [rbx]; Block
0x180120f2a  mov     [rbx], rdi
0x180120f2d  test    rcx, rcx
0x180120f30  jz      short loc_180120F37
0x180120f32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180120f37  xor     eax, eax
0x180120f39  jmp     short loc_180120F51
0x180120f3b  mov     rcx, [rsp+38h]; this
0x180120f40  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180120f47  mov     edx, 117h; void *
0x180120f4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180120f51  mov     rbx, [rsp+38h+arg_8]
0x180120f56  mov     rsi, [rsp+38h+arg_10]
0x180120f5b  add     rsp, 30h
0x180120f5f  pop     rdi
0x180120f60  retn
```
