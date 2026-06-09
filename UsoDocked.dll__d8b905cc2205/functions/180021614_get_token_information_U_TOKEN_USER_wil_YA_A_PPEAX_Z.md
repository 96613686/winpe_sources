# ??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z

- ea: `0x180021614`
- end: `0x180021784`
- name: `??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021e80`

## callees

- `0x180007644`
- `0x180007660`
- `0x180007920`
- `0x1800183d4`
- `0x1800183f4`
- `0x1800209fc`
- `0x180021614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002168d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002168d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002167f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800216ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002167f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800216ee`

## string_xrefs

- `0x1800216c1`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800216fd`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180021733`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180021772`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall wil::get_token_information<_TOKEN_USER>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  const char *v4; // r9
  void *v5; // rdi
  int LastError; // ebx
  const char *v7; // r9
  void *v8; // rcx
  int ReturnLength; // [rsp+20h] [rbp-38h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

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
    v5 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
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
    wil::details::in1diag3::Throw_Hr(
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
0x180021614  mov     r11, rsp
0x180021617  mov     [r11+18h], rbx
0x18002161b  mov     [r11+20h], rsi
0x18002161f  push    rdi
0x180021620  sub     rsp, 50h
0x180021624  mov     rax, cs:__security_cookie
0x18002162b  xor     rax, rsp
0x18002162e  mov     [rsp+58h+var_10], rax
0x180021633  mov     rbx, rdx
0x180021636  mov     rsi, rcx
0x180021639  mov     [r11-20h], rcx
0x18002163d  mov     [rsp+58h+var_28], 0
0x180021645  mov     [rsp+58h+var_28], 2
0x18002164d  mov     qword ptr [rcx], 0
0x180021654  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18002165b  test    rdx, rdx
0x18002165e  cmovz   rbx, rax
0x180021662  mov     [rsp+58h+TokenInformationLength], 0
0x18002166a  lea     rax, [r11-18h]
0x18002166e  mov     [r11-38h], rax
0x180021672  xor     r9d, r9d; TokenInformationLength
0x180021675  xor     r8d, r8d; TokenInformation
0x180021678  lea     edx, [r9+1]; TokenInformationClass
0x18002167c  mov     rcx, rbx; TokenHandle
0x18002167f  call    cs:__imp_GetTokenInformation
0x180021685  test    eax, eax
0x180021687  jnz     loc_18002172E
0x18002168d  call    cs:__imp_GetLastError
0x180021693  cmp     eax, 7Ah ; 'z'
0x180021696  jnz     loc_18002172E
0x18002169c  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1800216a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800216a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800216ac  mov     rdi, rax
0x1800216af  test    rax, rax
0x1800216b2  jnz     short loc_1800216D4
0x1800216b4  mov     rcx, [rsp+58h]; this
0x1800216b9  mov     ebx, 8007000Eh
0x1800216be  mov     r9d, ebx; char *
0x1800216c1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800216c8  mov     edx, 119h; void *
0x1800216cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216d2  jmp     short loc_180021746
0x1800216d4  lea     rax, [rsp+58h+TokenInformationLength]
0x1800216d9  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x1800216de  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800216e3  mov     r8, rdi; TokenInformation
0x1800216e6  mov     edx, 1; TokenInformationClass
0x1800216eb  mov     rcx, rbx; TokenHandle
0x1800216ee  call    cs:__imp_GetTokenInformation
0x1800216f4  test    eax, eax
0x1800216f6  jnz     short loc_18002171A
0x1800216f8  mov     rcx, [rsp+58h]; this
0x1800216fd  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021704  mov     edx, 11Ah; void *
0x180021709  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002170e  mov     ebx, eax
0x180021710  mov     rcx, rdi; Block
0x180021713  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021718  jmp     short loc_180021746
0x18002171a  mov     rcx, [rsi]; Block
0x18002171d  mov     [rsi], rdi
0x180021720  test    rcx, rcx
0x180021723  jz      short loc_18002172A
0x180021725  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002172a  xor     ebx, ebx
0x18002172c  jmp     short loc_180021746
0x18002172e  mov     rcx, [rsp+58h]; this
0x180021733  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002173a  mov     edx, 117h; void *
0x18002173f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021744  mov     ebx, eax
0x180021746  mov     rcx, [rsp+58h]; this
0x18002174b  test    ebx, ebx
0x18002174d  js      short loc_18002176F
0x18002174f  mov     rax, rsi
0x180021752  mov     rcx, [rsp+58h+var_10]
0x180021757  xor     rcx, rsp; StackCookie
0x18002175a  call    __security_check_cookie
0x18002175f  mov     rbx, [rsp+58h+arg_10]
0x180021764  mov     rsi, [rsp+58h+arg_18]
0x180021769  add     rsp, 50h
0x18002176d  pop     rdi
0x18002176e  retn
0x18002176f  mov     r9d, ebx; char *
0x180021772  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021779  mov     edx, 1CBEh; void *
0x18002177e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
