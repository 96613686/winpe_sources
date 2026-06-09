# IsTokenIntegrityLevelLessThanMedium(void *)

- ea: `0x18000be90`
- end: `0x18000bfc5`
- name: `?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z`
- size: `309`
- prototype: `bool __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027d78`
- `0x180032810`

## callees

- `0x180007c78`
- `0x18000be90`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000becc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bf88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000becc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bf88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf27`

## string_xrefs

- `0x18000bee1`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bf55`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bf9d`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
char __fastcall IsTokenIntegrityLevelLessThanMedium(__int64 a1)
{
  void *v1; // rbx
  __int64 v2; // rsi
  const char *v3; // r9
  int LastError; // esi
  bool v6; // di
  void *v7; // rdi
  const char *v8; // r9
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  v2 = a1;
  TokenInformationLength = 0;
  if ( !a1 )
    v2 = -6;
  if ( GetTokenInformation((HANDLE)v2, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v3);
  }
  else
  {
    v7 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
      return 1;
    }
    if ( GetTokenInformation((HANDLE)v2, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v1 = v7;
      goto LABEL_7;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v8);
    operator delete(v7);
  }
  if ( LastError < 0 )
    return 1;
LABEL_7:
  v6 = *(_DWORD *)(*(_QWORD *)v1 + 8LL) < 0x2000;
  operator delete(v1);
  return v6;
}

```

## disassembly

```asm
0x18000be90  mov     [rsp+arg_8], rbx
0x18000be95  mov     [rsp+arg_10], rsi
0x18000be9a  push    rdi
0x18000be9b  sub     rsp, 30h
0x18000be9f  xor     ebx, ebx
0x18000bea1  mov     rsi, rcx
0x18000bea4  test    rcx, rcx
0x18000bea7  mov     [rsp+38h+TokenInformationLength], ebx
0x18000beab  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000beb2  cmovz   rsi, rax
0x18000beb6  lea     rax, [rsp+38h+TokenInformationLength]
0x18000bebb  mov     rcx, rsi; TokenHandle
0x18000bebe  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000bec3  xor     r9d, r9d; TokenInformationLength
0x18000bec6  lea     edx, [rbx+19h]; TokenInformationClass
0x18000bec9  xor     r8d, r8d; TokenInformation
0x18000becc  call    cs:__imp_GetTokenInformation
0x18000bed3  nop     dword ptr [rax+rax+00h]
0x18000bed8  test    eax, eax
0x18000beda  jz      short loc_18000BF27
0x18000bedc  mov     rcx, [rsp+38h]; this
0x18000bee1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bee8  mov     edx, 117h; void *
0x18000beed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bef2  mov     esi, eax
0x18000bef4  test    esi, esi
0x18000bef6  jns     short loc_18000BF0B
0x18000bef8  mov     al, 1
0x18000befa  mov     rbx, [rsp+38h+arg_8]
0x18000beff  mov     rsi, [rsp+38h+arg_10]
0x18000bf04  add     rsp, 30h
0x18000bf08  pop     rdi
0x18000bf09  retn
0x18000bf0b  mov     rax, [rbx]
0x18000bf0e  mov     rcx, rbx; Block
0x18000bf11  cmp     dword ptr [rax+8], 2000h
0x18000bf18  setl    dil
0x18000bf1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bf21  movzx   eax, dil
0x18000bf25  jmp     short loc_18000BEFA
0x18000bf27  call    cs:__imp_GetLastError
0x18000bf2e  nop     dword ptr [rax+rax+00h]
0x18000bf33  cmp     eax, 7Ah ; 'z'
0x18000bf36  jnz     short loc_18000BEDC
0x18000bf38  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18000bf3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bf48  mov     rdi, rax
0x18000bf4b  test    rax, rax
0x18000bf4e  jnz     short loc_18000BF6E
0x18000bf50  mov     rcx, [rsp+38h]; this
0x18000bf55  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bf5c  mov     r9d, 8007000Eh; char *
0x18000bf62  mov     edx, 119h; void *
0x18000bf67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf6c  jmp     short loc_18000BEF8
0x18000bf6e  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000bf73  lea     rax, [rsp+38h+TokenInformationLength]
0x18000bf78  mov     r8, rdi; TokenInformation
0x18000bf7b  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18000bf80  mov     edx, 19h; TokenInformationClass
0x18000bf85  mov     rcx, rsi; TokenHandle
0x18000bf88  call    cs:__imp_GetTokenInformation
0x18000bf8f  nop     dword ptr [rax+rax+00h]
0x18000bf94  test    eax, eax
0x18000bf96  jnz     short loc_18000BFBD
0x18000bf98  mov     rcx, [rsp+38h]; this
0x18000bf9d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bfa4  mov     edx, 11Ah; void *
0x18000bfa9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bfae  mov     rcx, rdi; Block
0x18000bfb1  mov     esi, eax
0x18000bfb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bfb8  jmp     loc_18000BEF4
0x18000bfbd  mov     rbx, rdi
0x18000bfc0  jmp     loc_18000BF0B
```
