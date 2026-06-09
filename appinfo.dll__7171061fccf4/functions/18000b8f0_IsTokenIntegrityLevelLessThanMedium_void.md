# IsTokenIntegrityLevelLessThanMedium(void *)

- ea: `0x18000b8f0`
- end: `0x18000ba0a`
- name: `?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z`
- size: `282`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b27c`
- `0x180035dbc`

## callees

- `0x18000720c`
- `0x18000b8f0`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18001ef98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b97c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b97c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b92b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b92b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b9d7`

## string_xrefs

- `0x18000b93a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b9a4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b9ea`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
char __fastcall IsTokenIntegrityLevelLessThanMedium(__int64 a1)
{
  __int64 v1; // rdi
  const char *v2; // r9
  int LastError; // edi
  void *v4; // rbx
  bool v6; // di
  const char *v7; // r9
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  v1 = a1;
  if ( !a1 )
    v1 = -6;
  if ( GetTokenInformation((HANDLE)v1, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v2);
    goto LABEL_5;
  }
  v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 1;
  }
  if ( !GetTokenInformation((HANDLE)v1, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
    operator delete(v4);
LABEL_5:
    v4 = 0;
    if ( LastError < 0 )
      return 1;
  }
  v6 = *(_DWORD *)(*(_QWORD *)v4 + 8LL) < 0x2000;
  operator delete(v4);
  return v6;
}

```

## disassembly

```asm
0x18000b8f0  mov     [rsp+arg_8], rbx
0x18000b8f5  push    rdi
0x18000b8f6  sub     rsp, 30h
0x18000b8fa  test    rcx, rcx
0x18000b8fd  mov     [rsp+38h+TokenInformationLength], 0
0x18000b905  mov     rdi, rcx
0x18000b908  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000b90f  cmovz   rdi, rax
0x18000b913  mov     edx, 19h; TokenInformationClass
0x18000b918  lea     rax, [rsp+38h+TokenInformationLength]
0x18000b91d  mov     rcx, rdi; TokenHandle
0x18000b920  xor     r9d, r9d; TokenInformationLength
0x18000b923  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000b928  xor     r8d, r8d; TokenInformation
0x18000b92b  call    cs:__imp_GetTokenInformation
0x18000b931  test    eax, eax
0x18000b933  jz      short loc_18000B97C
0x18000b935  mov     rcx, [rsp+38h]; this
0x18000b93a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b941  mov     edx, 117h; void *
0x18000b946  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b94b  mov     edi, eax
0x18000b94d  xor     ebx, ebx
0x18000b94f  test    edi, edi
0x18000b951  jns     short loc_18000B960
0x18000b953  mov     al, 1
0x18000b955  mov     rbx, [rsp+38h+arg_8]
0x18000b95a  add     rsp, 30h
0x18000b95e  pop     rdi
0x18000b95f  retn
0x18000b960  mov     rax, [rbx]
0x18000b963  mov     rcx, rbx; Block
0x18000b966  cmp     dword ptr [rax+8], 2000h
0x18000b96d  setl    dil
0x18000b971  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b976  movzx   eax, dil
0x18000b97a  jmp     short loc_18000B955
0x18000b97c  call    cs:__imp_GetLastError
0x18000b982  cmp     eax, 7Ah ; 'z'
0x18000b985  jnz     short loc_18000B935
0x18000b987  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18000b98b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b992  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b997  mov     rbx, rax
0x18000b99a  test    rax, rax
0x18000b99d  jnz     short loc_18000B9BD
0x18000b99f  mov     rcx, [rsp+38h]; this
0x18000b9a4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b9ab  mov     r9d, 8007000Eh; char *
0x18000b9b1  mov     edx, 119h; void *
0x18000b9b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9bb  jmp     short loc_18000B953
0x18000b9bd  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000b9c2  lea     rax, [rsp+38h+TokenInformationLength]
0x18000b9c7  mov     r8, rbx; TokenInformation
0x18000b9ca  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18000b9cf  mov     edx, 19h; TokenInformationClass
0x18000b9d4  mov     rcx, rdi; TokenHandle
0x18000b9d7  call    cs:__imp_GetTokenInformation
0x18000b9dd  test    eax, eax
0x18000b9df  jnz     loc_18000B960
0x18000b9e5  mov     rcx, [rsp+38h]; this
0x18000b9ea  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b9f1  mov     edx, 11Ah; void *
0x18000b9f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9fb  mov     rcx, rbx; Block
0x18000b9fe  mov     edi, eax
0x18000ba00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ba05  jmp     loc_18000B94D
```
