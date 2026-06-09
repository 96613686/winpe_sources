# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180019fa0`
- end: `0x18001a0cd`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d974`
- `0x180018228`
- `0x18002ed98`
- `0x180035698`
- `0x1800432a0`

## callees

- `0x18000720c`
- `0x180019fa0`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18001ef98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a004`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019ff6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a067`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019ff6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a067`

## string_xrefs

- `0x18001a030`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18001a076`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18001a0ac`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
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
0x180019fa0  mov     [rsp+arg_8], rbx
0x180019fa5  mov     [rsp+arg_10], rsi
0x180019faa  push    rdi
0x180019fab  sub     rsp, 30h
0x180019faf  mov     rbx, rcx
0x180019fb2  mov     rsi, rdx
0x180019fb5  mov     rcx, [rcx]; Block
0x180019fb8  mov     qword ptr [rbx], 0
0x180019fbf  test    rcx, rcx
0x180019fc2  jz      short loc_180019FC9
0x180019fc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019fc9  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180019fd0  mov     [rsp+38h+TokenInformationLength], 0
0x180019fd8  test    rsi, rsi
0x180019fdb  cmovz   rsi, rax
0x180019fdf  xor     r9d, r9d; TokenInformationLength
0x180019fe2  lea     rax, [rsp+38h+TokenInformationLength]
0x180019fe7  xor     r8d, r8d; TokenInformation
0x180019fea  mov     rcx, rsi; TokenHandle
0x180019fed  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180019ff2  lea     edx, [r9+1]; TokenInformationClass
0x180019ff6  call    cs:__imp_GetTokenInformation
0x180019ffc  test    eax, eax
0x180019ffe  jnz     loc_18001A0A7
0x18001a004  call    cs:__imp_GetLastError
0x18001a00a  cmp     eax, 7Ah ; 'z'
0x18001a00d  jnz     loc_18001A0A7
0x18001a013  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18001a017  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a01e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a023  mov     rdi, rax
0x18001a026  test    rax, rax
0x18001a029  jnz     short loc_18001A04D
0x18001a02b  mov     rcx, [rsp+38h]; this
0x18001a030  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001a037  mov     ebx, 8007000Eh
0x18001a03c  mov     edx, 119h; void *
0x18001a041  mov     r9d, ebx; char *
0x18001a044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a049  mov     eax, ebx
0x18001a04b  jmp     short loc_18001A0BD
0x18001a04d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001a052  lea     rax, [rsp+38h+TokenInformationLength]
0x18001a057  mov     r8, rdi; TokenInformation
0x18001a05a  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18001a05f  mov     edx, 1; TokenInformationClass
0x18001a064  mov     rcx, rsi; TokenHandle
0x18001a067  call    cs:__imp_GetTokenInformation
0x18001a06d  test    eax, eax
0x18001a06f  jnz     short loc_18001A093
0x18001a071  mov     rcx, [rsp+38h]; this
0x18001a076  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001a07d  mov     edx, 11Ah; void *
0x18001a082  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a087  mov     rcx, rdi; Block
0x18001a08a  mov     ebx, eax
0x18001a08c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a091  jmp     short loc_18001A049
0x18001a093  mov     rcx, [rbx]; Block
0x18001a096  mov     [rbx], rdi
0x18001a099  test    rcx, rcx
0x18001a09c  jz      short loc_18001A0A3
0x18001a09e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a0a3  xor     eax, eax
0x18001a0a5  jmp     short loc_18001A0BD
0x18001a0a7  mov     rcx, [rsp+38h]; this
0x18001a0ac  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001a0b3  mov     edx, 117h; void *
0x18001a0b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a0bd  mov     rbx, [rsp+38h+arg_8]
0x18001a0c2  mov     rsi, [rsp+38h+arg_10]
0x18001a0c7  add     rsp, 30h
0x18001a0cb  pop     rdi
0x18001a0cc  retn
```
