# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x140017fb4`
- end: `0x1400180e1`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140018130`

## callees

- `0x14000e034`
- `0x14000ee38`
- `0x14000fc3c`
- `0x14000fc8c`
- `0x140017fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018018`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001800a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001807b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001800a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001807b`

## string_xrefs

- `0x140018044`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x14001808a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400180c0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x140017fb4  mov     [rsp+arg_8], rbx
0x140017fb9  mov     [rsp+arg_10], rsi
0x140017fbe  push    rdi
0x140017fbf  sub     rsp, 30h
0x140017fc3  mov     rbx, rcx
0x140017fc6  mov     rsi, rdx
0x140017fc9  mov     rcx, [rcx]; Block
0x140017fcc  mov     qword ptr [rbx], 0
0x140017fd3  test    rcx, rcx
0x140017fd6  jz      short loc_140017FDD
0x140017fd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140017fdd  mov     rax, 0FFFFFFFFFFFFFFFAh
0x140017fe4  mov     [rsp+38h+TokenInformationLength], 0
0x140017fec  test    rsi, rsi
0x140017fef  cmovz   rsi, rax
0x140017ff3  xor     r9d, r9d; TokenInformationLength
0x140017ff6  lea     rax, [rsp+38h+TokenInformationLength]
0x140017ffb  xor     r8d, r8d; TokenInformation
0x140017ffe  mov     rcx, rsi; TokenHandle
0x140018001  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140018006  lea     edx, [r9+1]; TokenInformationClass
0x14001800a  call    cs:__imp_GetTokenInformation
0x140018010  test    eax, eax
0x140018012  jnz     loc_1400180BB
0x140018018  call    cs:__imp_GetLastError
0x14001801e  cmp     eax, 7Ah ; 'z'
0x140018021  jnz     loc_1400180BB
0x140018027  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x14001802b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018032  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140018037  mov     rdi, rax
0x14001803a  test    rax, rax
0x14001803d  jnz     short loc_140018061
0x14001803f  mov     rcx, [rsp+38h]; this
0x140018044  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001804b  mov     ebx, 8007000Eh
0x140018050  mov     edx, 119h; void *
0x140018055  mov     r9d, ebx; char *
0x140018058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001805d  mov     eax, ebx
0x14001805f  jmp     short loc_1400180D1
0x140018061  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140018066  lea     rax, [rsp+38h+TokenInformationLength]
0x14001806b  mov     r8, rdi; TokenInformation
0x14001806e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140018073  mov     edx, 1; TokenInformationClass
0x140018078  mov     rcx, rsi; TokenHandle
0x14001807b  call    cs:__imp_GetTokenInformation
0x140018081  test    eax, eax
0x140018083  jnz     short loc_1400180A7
0x140018085  mov     rcx, [rsp+38h]; this
0x14001808a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140018091  mov     edx, 11Ah; void *
0x140018096  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001809b  mov     rcx, rdi; Block
0x14001809e  mov     ebx, eax
0x1400180a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400180a5  jmp     short loc_14001805D
0x1400180a7  mov     rcx, [rbx]; Block
0x1400180aa  mov     [rbx], rdi
0x1400180ad  test    rcx, rcx
0x1400180b0  jz      short loc_1400180B7
0x1400180b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400180b7  xor     eax, eax
0x1400180b9  jmp     short loc_1400180D1
0x1400180bb  mov     rcx, [rsp+38h]; this
0x1400180c0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400180c7  mov     edx, 117h; void *
0x1400180cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400180d1  mov     rbx, [rsp+38h+arg_8]
0x1400180d6  mov     rsi, [rsp+38h+arg_10]
0x1400180db  add     rsp, 30h
0x1400180df  pop     rdi
0x1400180e0  retn
```
