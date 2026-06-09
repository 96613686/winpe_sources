# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x140007300`
- end: `0x14000742d`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001c3d4`

## callees

- `0x1400032f0`
- `0x140003644`
- `0x140007300`
- `0x1400136dc`
- `0x1400136fc`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140007356`
- `ADVAPI32!GetTokenInformation` at `0x1400073c7`
- `ADVAPI32!GetTokenInformation` at `0x140007356`
- `ADVAPI32!GetTokenInformation` at `0x1400073c7`
- `KERNEL32!GetLastError` at `0x140007364`
- `KERNEL32!GetLastError` at `0x140007364`

## string_xrefs

- `0x140007390`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400073d6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x14000740c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  if ( !GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
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
0x140007300  mov     [rsp+arg_8], rbx
0x140007305  mov     [rsp+arg_10], rsi
0x14000730a  push    rdi
0x14000730b  sub     rsp, 30h
0x14000730f  mov     rbx, rcx
0x140007312  mov     rsi, rdx
0x140007315  mov     rcx, [rcx]; Block
0x140007318  mov     qword ptr [rbx], 0
0x14000731f  test    rcx, rcx
0x140007322  jz      short loc_140007329
0x140007324  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007329  mov     rax, 0FFFFFFFFFFFFFFFAh
0x140007330  mov     [rsp+38h+TokenInformationLength], 0
0x140007338  test    rsi, rsi
0x14000733b  cmovz   rsi, rax
0x14000733f  xor     r9d, r9d; TokenInformationLength
0x140007342  lea     rax, [rsp+38h+TokenInformationLength]
0x140007347  xor     r8d, r8d; TokenInformation
0x14000734a  mov     rcx, rsi; TokenHandle
0x14000734d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140007352  lea     edx, [r9+19h]; TokenInformationClass
0x140007356  call    cs:__imp_GetTokenInformation
0x14000735c  test    eax, eax
0x14000735e  jnz     loc_140007407
0x140007364  call    cs:__imp_GetLastError
0x14000736a  cmp     eax, 7Ah ; 'z'
0x14000736d  jnz     loc_140007407
0x140007373  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140007377  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000737e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140007383  mov     rdi, rax
0x140007386  test    rax, rax
0x140007389  jnz     short loc_1400073AD
0x14000738b  mov     rcx, [rsp+38h]; this
0x140007390  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140007397  mov     ebx, 8007000Eh
0x14000739c  mov     edx, 119h; void *
0x1400073a1  mov     r9d, ebx; char *
0x1400073a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400073a9  mov     eax, ebx
0x1400073ab  jmp     short loc_14000741D
0x1400073ad  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1400073b2  lea     rax, [rsp+38h+TokenInformationLength]
0x1400073b7  mov     r8, rdi; TokenInformation
0x1400073ba  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1400073bf  mov     edx, 19h; TokenInformationClass
0x1400073c4  mov     rcx, rsi; TokenHandle
0x1400073c7  call    cs:__imp_GetTokenInformation
0x1400073cd  test    eax, eax
0x1400073cf  jnz     short loc_1400073F3
0x1400073d1  mov     rcx, [rsp+38h]; this
0x1400073d6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400073dd  mov     edx, 11Ah; void *
0x1400073e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400073e7  mov     rcx, rdi; Block
0x1400073ea  mov     ebx, eax
0x1400073ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400073f1  jmp     short loc_1400073A9
0x1400073f3  mov     rcx, [rbx]; Block
0x1400073f6  mov     [rbx], rdi
0x1400073f9  test    rcx, rcx
0x1400073fc  jz      short loc_140007403
0x1400073fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007403  xor     eax, eax
0x140007405  jmp     short loc_14000741D
0x140007407  mov     rcx, [rsp+38h]; this
0x14000740c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140007413  mov     edx, 117h; void *
0x140007418  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000741d  mov     rbx, [rsp+38h+arg_8]
0x140007422  mov     rsi, [rsp+38h+arg_10]
0x140007427  add     rsp, 30h
0x14000742b  pop     rdi
0x14000742c  retn
```
