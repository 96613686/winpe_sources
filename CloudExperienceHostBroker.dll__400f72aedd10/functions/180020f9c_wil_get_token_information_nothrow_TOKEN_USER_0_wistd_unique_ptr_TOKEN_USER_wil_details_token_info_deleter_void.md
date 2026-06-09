# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180020f9c`
- end: `0x1800210c9`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022d30`

## callees

- `0x180008344`
- `0x18000a7a0`
- `0x18000ba24`
- `0x18000e6f4`
- `0x180020f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021000`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ff2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021063`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ff2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021063`

## string_xrefs

- `0x18002102c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180021072`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800210a8`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x180020f9c  mov     [rsp+arg_8], rbx
0x180020fa1  mov     [rsp+arg_10], rsi
0x180020fa6  push    rdi
0x180020fa7  sub     rsp, 30h
0x180020fab  mov     rbx, rcx
0x180020fae  mov     rsi, rdx
0x180020fb1  mov     rcx, [rcx]; Block
0x180020fb4  mov     qword ptr [rbx], 0
0x180020fbb  test    rcx, rcx
0x180020fbe  jz      short loc_180020FC5
0x180020fc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020fc5  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180020fcc  mov     [rsp+38h+TokenInformationLength], 0
0x180020fd4  test    rsi, rsi
0x180020fd7  cmovz   rsi, rax
0x180020fdb  xor     r9d, r9d; TokenInformationLength
0x180020fde  lea     rax, [rsp+38h+TokenInformationLength]
0x180020fe3  xor     r8d, r8d; TokenInformation
0x180020fe6  mov     rcx, rsi; TokenHandle
0x180020fe9  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180020fee  lea     edx, [r9+1]; TokenInformationClass
0x180020ff2  call    cs:__imp_GetTokenInformation
0x180020ff8  test    eax, eax
0x180020ffa  jnz     loc_1800210A3
0x180021000  call    cs:__imp_GetLastError
0x180021006  cmp     eax, 7Ah ; 'z'
0x180021009  jnz     loc_1800210A3
0x18002100f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180021013  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002101a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002101f  mov     rdi, rax
0x180021022  test    rax, rax
0x180021025  jnz     short loc_180021049
0x180021027  mov     rcx, [rsp+38h]; this
0x18002102c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021033  mov     ebx, 8007000Eh
0x180021038  mov     edx, 119h; void *
0x18002103d  mov     r9d, ebx; char *
0x180021040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021045  mov     eax, ebx
0x180021047  jmp     short loc_1800210B9
0x180021049  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002104e  lea     rax, [rsp+38h+TokenInformationLength]
0x180021053  mov     r8, rdi; TokenInformation
0x180021056  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18002105b  mov     edx, 1; TokenInformationClass
0x180021060  mov     rcx, rsi; TokenHandle
0x180021063  call    cs:__imp_GetTokenInformation
0x180021069  test    eax, eax
0x18002106b  jnz     short loc_18002108F
0x18002106d  mov     rcx, [rsp+38h]; this
0x180021072  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021079  mov     edx, 11Ah; void *
0x18002107e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021083  mov     rcx, rdi; Block
0x180021086  mov     ebx, eax
0x180021088  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002108d  jmp     short loc_180021045
0x18002108f  mov     rcx, [rbx]; Block
0x180021092  mov     [rbx], rdi
0x180021095  test    rcx, rcx
0x180021098  jz      short loc_18002109F
0x18002109a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002109f  xor     eax, eax
0x1800210a1  jmp     short loc_1800210B9
0x1800210a3  mov     rcx, [rsp+38h]; this
0x1800210a8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800210af  mov     edx, 117h; void *
0x1800210b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800210b9  mov     rbx, [rsp+38h+arg_8]
0x1800210be  mov     rsi, [rsp+38h+arg_10]
0x1800210c3  add     rsp, 30h
0x1800210c7  pop     rdi
0x1800210c8  retn
```
