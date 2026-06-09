# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180090524`
- end: `0x180090640`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180090648`

## callees

- `0x1800062d0`
- `0x180006770`
- `0x18001330c`
- `0x18001332c`
- `0x180090524`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090578`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009056a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800905df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009056a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800905df`

## string_xrefs

- `0x1800905a4`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800905ee`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180090624`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x180090524  mov     [rsp+arg_0], rbx
0x180090529  mov     [rsp+TokenInformationLength], rdx
0x18009052e  push    rdi
0x18009052f  sub     rsp, 30h
0x180090533  mov     rbx, rcx
0x180090536  mov     rcx, [rcx]; Block
0x180090539  mov     qword ptr [rbx], 0
0x180090540  test    rcx, rcx
0x180090543  jz      short loc_18009054A
0x180090545  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009054a  xor     r9d, r9d; TokenInformationLength
0x18009054d  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x180090555  lea     rax, [rsp+38h+TokenInformationLength]
0x18009055a  xor     r8d, r8d; TokenInformation
0x18009055d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180090562  lea     edx, [r9+1]; TokenInformationClass
0x180090566  lea     rcx, [r9-6]; TokenHandle
0x18009056a  call    cs:__imp_GetTokenInformation
0x180090570  test    eax, eax
0x180090572  jnz     loc_18009061F
0x180090578  call    cs:__imp_GetLastError
0x18009057e  cmp     eax, 7Ah ; 'z'
0x180090581  jnz     loc_18009061F
0x180090587  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18009058b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180090592  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180090597  mov     rdi, rax
0x18009059a  test    rax, rax
0x18009059d  jnz     short loc_1800905C1
0x18009059f  mov     rcx, [rsp+38h]; this
0x1800905a4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800905ab  mov     ebx, 8007000Eh
0x1800905b0  mov     edx, 119h; void *
0x1800905b5  mov     r9d, ebx; char *
0x1800905b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800905bd  mov     eax, ebx
0x1800905bf  jmp     short loc_180090635
0x1800905c1  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800905c6  lea     rax, [rsp+38h+TokenInformationLength]
0x1800905cb  mov     r8, rdi; TokenInformation
0x1800905ce  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800905d3  mov     edx, 1; TokenInformationClass
0x1800905d8  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800905df  call    cs:__imp_GetTokenInformation
0x1800905e5  test    eax, eax
0x1800905e7  jnz     short loc_18009060B
0x1800905e9  mov     rcx, [rsp+38h]; this
0x1800905ee  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800905f5  mov     edx, 11Ah; void *
0x1800905fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800905ff  mov     rcx, rdi; Block
0x180090602  mov     ebx, eax
0x180090604  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180090609  jmp     short loc_1800905BD
0x18009060b  mov     rcx, [rbx]; Block
0x18009060e  mov     [rbx], rdi
0x180090611  test    rcx, rcx
0x180090614  jz      short loc_18009061B
0x180090616  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009061b  xor     eax, eax
0x18009061d  jmp     short loc_180090635
0x18009061f  mov     rcx, [rsp+38h]; this
0x180090624  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009062b  mov     edx, 117h; void *
0x180090630  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180090635  mov     rbx, [rsp+38h+arg_0]
0x18009063a  add     rsp, 30h
0x18009063e  pop     rdi
0x18009063f  retn
```
