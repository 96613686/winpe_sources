# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18003f2f0`
- end: `0x18003f41d`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003f290`

## callees

- `0x18003f184`
- `0x18003f2f0`
- `0x18003f424`
- `0x180059db4`
- `0x18005a56c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x18003f346`
- `ADVAPI32!GetTokenInformation` at `0x18003f3b7`
- `ADVAPI32!GetTokenInformation` at `0x18003f346`
- `ADVAPI32!GetTokenInformation` at `0x18003f3b7`
- `KERNEL32!GetLastError` at `0x18003f354`
- `KERNEL32!GetLastError` at `0x18003f354`

## string_xrefs

- `0x18003f380`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18003f3c6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18003f3fc`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
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
0x18003f2f0  mov     [rsp+arg_8], rbx
0x18003f2f5  mov     [rsp+arg_10], rsi
0x18003f2fa  push    rdi
0x18003f2fb  sub     rsp, 30h
0x18003f2ff  mov     rbx, rcx
0x18003f302  mov     rsi, rdx
0x18003f305  mov     rcx, [rcx]; Block
0x18003f308  mov     qword ptr [rbx], 0
0x18003f30f  test    rcx, rcx
0x18003f312  jz      short loc_18003F319
0x18003f314  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f319  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003f320  mov     [rsp+38h+TokenInformationLength], 0
0x18003f328  test    rsi, rsi
0x18003f32b  cmovz   rsi, rax
0x18003f32f  xor     r9d, r9d; TokenInformationLength
0x18003f332  lea     rax, [rsp+38h+TokenInformationLength]
0x18003f337  xor     r8d, r8d; TokenInformation
0x18003f33a  mov     rcx, rsi; TokenHandle
0x18003f33d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003f342  lea     edx, [r9+1]; TokenInformationClass
0x18003f346  call    cs:__imp_GetTokenInformation
0x18003f34c  test    eax, eax
0x18003f34e  jnz     loc_18003F3F7
0x18003f354  call    cs:__imp_GetLastError
0x18003f35a  cmp     eax, 7Ah ; 'z'
0x18003f35d  jnz     loc_18003F3F7
0x18003f363  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003f367  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f36e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f373  mov     rdi, rax
0x18003f376  test    rax, rax
0x18003f379  jnz     short loc_18003F39D
0x18003f37b  mov     rcx, [rsp+38h]; this
0x18003f380  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f387  mov     ebx, 8007000Eh
0x18003f38c  mov     edx, 119h; void *
0x18003f391  mov     r9d, ebx; char *
0x18003f394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f399  mov     eax, ebx
0x18003f39b  jmp     short loc_18003F40D
0x18003f39d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003f3a2  lea     rax, [rsp+38h+TokenInformationLength]
0x18003f3a7  mov     r8, rdi; TokenInformation
0x18003f3aa  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003f3af  mov     edx, 1; TokenInformationClass
0x18003f3b4  mov     rcx, rsi; TokenHandle
0x18003f3b7  call    cs:__imp_GetTokenInformation
0x18003f3bd  test    eax, eax
0x18003f3bf  jnz     short loc_18003F3E3
0x18003f3c1  mov     rcx, [rsp+38h]; this
0x18003f3c6  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f3cd  mov     edx, 11Ah; void *
0x18003f3d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f3d7  mov     rcx, rdi; Block
0x18003f3da  mov     ebx, eax
0x18003f3dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f3e1  jmp     short loc_18003F399
0x18003f3e3  mov     rcx, [rbx]; Block
0x18003f3e6  mov     [rbx], rdi
0x18003f3e9  test    rcx, rcx
0x18003f3ec  jz      short loc_18003F3F3
0x18003f3ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f3f3  xor     eax, eax
0x18003f3f5  jmp     short loc_18003F40D
0x18003f3f7  mov     rcx, [rsp+38h]; this
0x18003f3fc  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f403  mov     edx, 117h; void *
0x18003f408  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f40d  mov     rbx, [rsp+38h+arg_8]
0x18003f412  mov     rsi, [rsp+38h+arg_10]
0x18003f417  add     rsp, 30h
0x18003f41b  pop     rdi
0x18003f41c  retn
```
