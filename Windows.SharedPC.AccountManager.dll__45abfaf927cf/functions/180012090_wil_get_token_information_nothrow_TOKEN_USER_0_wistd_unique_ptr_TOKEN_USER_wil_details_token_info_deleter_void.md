# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180012090`
- end: `0x1800121bd`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011a14`

## callees

- `0x180003b20`
- `0x1800044c4`
- `0x180008a18`
- `0x180008a38`
- `0x180012090`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800120e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012157`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800120e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120f4`

## string_xrefs

- `0x180012120`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180012166`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18001219c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180012090  mov     [rsp+arg_8], rbx
0x180012095  mov     [rsp+arg_10], rsi
0x18001209a  push    rdi
0x18001209b  sub     rsp, 30h
0x18001209f  mov     rbx, rcx
0x1800120a2  mov     rsi, rdx
0x1800120a5  mov     rcx, [rcx]; Block
0x1800120a8  mov     qword ptr [rbx], 0
0x1800120af  test    rcx, rcx
0x1800120b2  jz      short loc_1800120B9
0x1800120b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800120b9  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800120c0  mov     [rsp+38h+TokenInformationLength], 0
0x1800120c8  test    rsi, rsi
0x1800120cb  cmovz   rsi, rax
0x1800120cf  xor     r9d, r9d; TokenInformationLength
0x1800120d2  lea     rax, [rsp+38h+TokenInformationLength]
0x1800120d7  xor     r8d, r8d; TokenInformation
0x1800120da  mov     rcx, rsi; TokenHandle
0x1800120dd  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800120e2  lea     edx, [r9+1]; TokenInformationClass
0x1800120e6  call    cs:__imp_GetTokenInformation
0x1800120ec  test    eax, eax
0x1800120ee  jnz     loc_180012197
0x1800120f4  call    cs:__imp_GetLastError
0x1800120fa  cmp     eax, 7Ah ; 'z'
0x1800120fd  jnz     loc_180012197
0x180012103  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180012107  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001210e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012113  mov     rdi, rax
0x180012116  test    rax, rax
0x180012119  jnz     short loc_18001213D
0x18001211b  mov     rcx, [rsp+38h]; this
0x180012120  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012127  mov     ebx, 8007000Eh
0x18001212c  mov     edx, 119h; void *
0x180012131  mov     r9d, ebx; char *
0x180012134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012139  mov     eax, ebx
0x18001213b  jmp     short loc_1800121AD
0x18001213d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180012142  lea     rax, [rsp+38h+TokenInformationLength]
0x180012147  mov     r8, rdi; TokenInformation
0x18001214a  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18001214f  mov     edx, 1; TokenInformationClass
0x180012154  mov     rcx, rsi; TokenHandle
0x180012157  call    cs:__imp_GetTokenInformation
0x18001215d  test    eax, eax
0x18001215f  jnz     short loc_180012183
0x180012161  mov     rcx, [rsp+38h]; this
0x180012166  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001216d  mov     edx, 11Ah; void *
0x180012172  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012177  mov     rcx, rdi; Block
0x18001217a  mov     ebx, eax
0x18001217c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012181  jmp     short loc_180012139
0x180012183  mov     rcx, [rbx]; Block
0x180012186  mov     [rbx], rdi
0x180012189  test    rcx, rcx
0x18001218c  jz      short loc_180012193
0x18001218e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012193  xor     eax, eax
0x180012195  jmp     short loc_1800121AD
0x180012197  mov     rcx, [rsp+38h]; this
0x18001219c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800121a3  mov     edx, 117h; void *
0x1800121a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800121ad  mov     rbx, [rsp+38h+arg_8]
0x1800121b2  mov     rsi, [rsp+38h+arg_10]
0x1800121b7  add     rsp, 30h
0x1800121bb  pop     rdi
0x1800121bc  retn
```
