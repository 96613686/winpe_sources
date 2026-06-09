# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1400253e4`
- end: `0x140025500`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400251a8`

## callees

- `0x140002d18`
- `0x140002d60`
- `0x14000e010`
- `0x14000e030`
- `0x1400253e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002542a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002549f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002542a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002549f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025438`

## string_xrefs

- `0x140025464`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400254ae`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400254e4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  void *v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = a2;
  v3 = *a1;
  *a1 = 0;
  if ( v3 )
    operator delete(v3);
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
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
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenUser,
          v5,
          TokenInformationLength,
          (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v8);
    operator delete(v5);
    return LastError;
  }
  v9 = *a1;
  *a1 = v5;
  if ( v9 )
    operator delete(v9);
  return 0;
}

```

## disassembly

```asm
0x1400253e4  mov     [rsp+arg_0], rbx
0x1400253e9  mov     [rsp+TokenInformationLength], rdx
0x1400253ee  push    rdi
0x1400253ef  sub     rsp, 30h
0x1400253f3  mov     rbx, rcx
0x1400253f6  mov     rcx, [rcx]; Block
0x1400253f9  mov     qword ptr [rbx], 0
0x140025400  test    rcx, rcx
0x140025403  jz      short loc_14002540A
0x140025405  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002540a  xor     r9d, r9d; TokenInformationLength
0x14002540d  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x140025415  lea     rax, [rsp+38h+TokenInformationLength]
0x14002541a  xor     r8d, r8d; TokenInformation
0x14002541d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140025422  lea     edx, [r9+1]; TokenInformationClass
0x140025426  lea     rcx, [r9-6]; TokenHandle
0x14002542a  call    cs:__imp_GetTokenInformation
0x140025430  test    eax, eax
0x140025432  jnz     loc_1400254DF
0x140025438  call    cs:__imp_GetLastError
0x14002543e  cmp     eax, 7Ah ; 'z'
0x140025441  jnz     loc_1400254DF
0x140025447  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x14002544b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140025452  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140025457  mov     rdi, rax
0x14002545a  test    rax, rax
0x14002545d  jnz     short loc_140025481
0x14002545f  mov     rcx, [rsp+38h]; this
0x140025464  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14002546b  mov     ebx, 8007000Eh
0x140025470  mov     edx, 119h; void *
0x140025475  mov     r9d, ebx; char *
0x140025478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002547d  mov     eax, ebx
0x14002547f  jmp     short loc_1400254F5
0x140025481  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140025486  lea     rax, [rsp+38h+TokenInformationLength]
0x14002548b  mov     r8, rdi; TokenInformation
0x14002548e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140025493  mov     edx, 1; TokenInformationClass
0x140025498  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x14002549f  call    cs:__imp_GetTokenInformation
0x1400254a5  test    eax, eax
0x1400254a7  jnz     short loc_1400254CB
0x1400254a9  mov     rcx, [rsp+38h]; this
0x1400254ae  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400254b5  mov     edx, 11Ah; void *
0x1400254ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400254bf  mov     rcx, rdi; Block
0x1400254c2  mov     ebx, eax
0x1400254c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400254c9  jmp     short loc_14002547D
0x1400254cb  mov     rcx, [rbx]; Block
0x1400254ce  mov     [rbx], rdi
0x1400254d1  test    rcx, rcx
0x1400254d4  jz      short loc_1400254DB
0x1400254d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400254db  xor     eax, eax
0x1400254dd  jmp     short loc_1400254F5
0x1400254df  mov     rcx, [rsp+38h]; this
0x1400254e4  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400254eb  mov     edx, 117h; void *
0x1400254f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400254f5  mov     rbx, [rsp+38h+arg_0]
0x1400254fa  add     rsp, 30h
0x1400254fe  pop     rdi
0x1400254ff  retn
```
