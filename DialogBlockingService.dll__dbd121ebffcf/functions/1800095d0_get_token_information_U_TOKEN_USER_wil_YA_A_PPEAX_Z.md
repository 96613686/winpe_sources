# ??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z

- ea: `0x1800095d0`
- end: `0x180009724`
- name: `??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z`
- size: `340`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a65c`

## callees

- `0x180001c90`
- `0x18000213c`
- `0x1800067e4`
- `0x180006804`
- `0x180009568`
- `0x1800095d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000962c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000969b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000962c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000969b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000963a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000963a`

## string_xrefs

- `0x180009712`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18000966e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800096aa`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800096e0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
void **__fastcall wil::get_token_information<_TOKEN_USER>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  const char *v4; // r9
  void *v5; // rdi
  int LastError; // ebx
  const char *v7; // r9
  void *v8; // rcx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2;
  *a1 = 0;
  if ( !a2 )
    v2 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v4);
  }
  else
  {
    v5 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v5 )
    {
      if ( GetTokenInformation((HANDLE)v2, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        v8 = *a1;
        *a1 = v5;
        if ( v8 )
          operator delete(v8);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                      v7);
        operator delete(v5);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  return a1;
}

```

## disassembly

```asm
0x1800095d0  mov     rax, rsp
0x1800095d3  mov     [rax+18h], rbx
0x1800095d7  mov     [rax+20h], rsi
0x1800095db  mov     [rax+8], rcx
0x1800095df  push    rdi
0x1800095e0  sub     rsp, 40h
0x1800095e4  mov     rbx, rdx
0x1800095e7  mov     rsi, rcx
0x1800095ea  mov     dword ptr [rax-18h], 0
0x1800095f1  mov     dword ptr [rax-18h], 2
0x1800095f8  mov     qword ptr [rcx], 0
0x1800095ff  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180009606  test    rdx, rdx
0x180009609  cmovz   rbx, rax
0x18000960d  mov     [rsp+48h+TokenInformationLength], 0
0x180009615  lea     rax, [rsp+48h+TokenInformationLength]
0x18000961a  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000961f  xor     r9d, r9d; TokenInformationLength
0x180009622  xor     r8d, r8d; TokenInformation
0x180009625  lea     edx, [r9+1]; TokenInformationClass
0x180009629  mov     rcx, rbx; TokenHandle
0x18000962c  call    cs:__imp_GetTokenInformation
0x180009632  test    eax, eax
0x180009634  jnz     loc_1800096DB
0x18000963a  call    cs:__imp_GetLastError
0x180009640  cmp     eax, 7Ah ; 'z'
0x180009643  jnz     loc_1800096DB
0x180009649  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000964d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009654  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009659  mov     rdi, rax
0x18000965c  test    rax, rax
0x18000965f  jnz     short loc_180009681
0x180009661  mov     rcx, [rsp+48h]; this
0x180009666  mov     ebx, 8007000Eh
0x18000966b  mov     r9d, ebx; char *
0x18000966e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009675  mov     edx, 119h; void *
0x18000967a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000967f  jmp     short loc_1800096F3
0x180009681  lea     rax, [rsp+48h+TokenInformationLength]
0x180009686  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x18000968b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180009690  mov     r8, rdi; TokenInformation
0x180009693  mov     edx, 1; TokenInformationClass
0x180009698  mov     rcx, rbx; TokenHandle
0x18000969b  call    cs:__imp_GetTokenInformation
0x1800096a1  test    eax, eax
0x1800096a3  jnz     short loc_1800096C7
0x1800096a5  mov     rcx, [rsp+48h]; this
0x1800096aa  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800096b1  mov     edx, 11Ah; void *
0x1800096b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096bb  mov     ebx, eax
0x1800096bd  mov     rcx, rdi; Block
0x1800096c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096c5  jmp     short loc_1800096F3
0x1800096c7  mov     rcx, [rsi]; Block
0x1800096ca  mov     [rsi], rdi
0x1800096cd  test    rcx, rcx
0x1800096d0  jz      short loc_1800096D7
0x1800096d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096d7  xor     ebx, ebx
0x1800096d9  jmp     short loc_1800096F3
0x1800096db  mov     rcx, [rsp+48h]; this
0x1800096e0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800096e7  mov     edx, 117h; void *
0x1800096ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800096f1  mov     ebx, eax
0x1800096f3  mov     rcx, [rsp+48h]; this
0x1800096f8  test    ebx, ebx
0x1800096fa  js      short loc_18000970F
0x1800096fc  mov     rax, rsi
0x1800096ff  mov     rbx, [rsp+48h+arg_10]
0x180009704  mov     rsi, [rsp+48h+arg_18]
0x180009709  add     rsp, 40h
0x18000970d  pop     rdi
0x18000970e  retn
0x18000970f  mov     r9d, ebx; char *
0x180009712  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009719  mov     edx, 1CBEh; void *
0x18000971e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
