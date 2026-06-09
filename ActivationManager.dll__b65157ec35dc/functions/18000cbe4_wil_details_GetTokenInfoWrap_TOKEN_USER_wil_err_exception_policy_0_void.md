# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x18000cbe4`
- end: `0x18000cd37`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `339`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b5f0`
- `0x18004531c`
- `0x180045770`
- `0x180050450`
- `0x180055aa4`
- `0x18008f044`

## callees

- `0x18000b5c0`
- `0x18000cbe4`
- `0x180044408`
- `0x180056208`
- `0x18005b37c`
- `0x18005b3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cc40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ccb2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cc40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ccb2`

## string_xrefs

- `0x18000cc82`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000ccc1`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000cd06`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000cd25`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  const char *v4; // r9
  void *v5; // rsi
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
  }
  else
  {
    v5 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v5 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
      goto LABEL_14;
    }
    if ( GetTokenInformation((HANDLE)v2, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = *a1;
      *a1 = v5;
      if ( v8 )
        operator delete(v8);
      return a1;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    operator delete(v5);
  }
  if ( LastError < 0 )
LABEL_14:
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
0x18000cbe4  mov     rax, rsp
0x18000cbe7  mov     [rax+18h], rbx
0x18000cbeb  mov     [rax+20h], rsi
0x18000cbef  mov     [rax+8], rcx
0x18000cbf3  push    rdi
0x18000cbf4  sub     rsp, 40h
0x18000cbf8  mov     rbx, rdx
0x18000cbfb  mov     rdi, rcx
0x18000cbfe  mov     dword ptr [rax-18h], 0
0x18000cc05  mov     dword ptr [rax-18h], 1
0x18000cc0c  mov     qword ptr [rcx], 0
0x18000cc13  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000cc1a  test    rdx, rdx
0x18000cc1d  cmovz   rbx, rax
0x18000cc21  mov     [rsp+48h+TokenInformationLength], 0
0x18000cc29  lea     rax, [rsp+48h+TokenInformationLength]
0x18000cc2e  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000cc33  xor     r9d, r9d; TokenInformationLength
0x18000cc36  xor     r8d, r8d; TokenInformation
0x18000cc39  lea     edx, [r9+1]; TokenInformationClass
0x18000cc3d  mov     rcx, rbx; TokenHandle
0x18000cc40  call    cs:__imp_GetTokenInformation
0x18000cc46  test    eax, eax
0x18000cc48  jnz     loc_18000CD01
0x18000cc4e  call    cs:__imp_GetLastError
0x18000cc54  cmp     eax, 7Ah ; 'z'
0x18000cc57  jnz     loc_18000CD01
0x18000cc5d  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000cc61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc68  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cc6d  mov     rsi, rax
0x18000cc70  test    rax, rax
0x18000cc73  jnz     short loc_18000CC98
0x18000cc75  mov     rcx, [rsp+48h]; this
0x18000cc7a  mov     ebx, 8007000Eh
0x18000cc7f  mov     r9d, ebx; char *
0x18000cc82  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cc89  mov     edx, 119h; void *
0x18000cc8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc93  jmp     loc_18000CD1D
0x18000cc98  lea     rax, [rsp+48h+TokenInformationLength]
0x18000cc9d  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x18000cca2  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000cca7  mov     r8, rsi; TokenInformation
0x18000ccaa  mov     edx, 1; TokenInformationClass
0x18000ccaf  mov     rcx, rbx; TokenHandle
0x18000ccb2  call    cs:__imp_GetTokenInformation
0x18000ccb8  test    eax, eax
0x18000ccba  jnz     short loc_18000CCDE
0x18000ccbc  mov     rcx, [rsp+48h]; this
0x18000ccc1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ccc8  mov     edx, 11Ah; void *
0x18000cccd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ccd2  mov     ebx, eax
0x18000ccd4  mov     rcx, rsi; Block
0x18000ccd7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ccdc  jmp     short loc_18000CD19
0x18000ccde  mov     rcx, [rdi]; Block
0x18000cce1  mov     [rdi], rsi
0x18000cce4  test    rcx, rcx
0x18000cce7  jz      short loc_18000CCEE
0x18000cce9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ccee  mov     rax, rdi
0x18000ccf1  mov     rbx, [rsp+48h+arg_10]
0x18000ccf6  mov     rsi, [rsp+48h+arg_18]
0x18000ccfb  add     rsp, 40h
0x18000ccff  pop     rdi
0x18000cd00  retn
0x18000cd01  mov     rcx, [rsp+48h]; this
0x18000cd06  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd0d  mov     edx, 117h; void *
0x18000cd12  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd17  mov     ebx, eax
0x18000cd19  test    ebx, ebx
0x18000cd1b  jns     short loc_18000CCEE
0x18000cd1d  mov     rcx, [rsp+48h]; this
0x18000cd22  mov     r9d, ebx; char *
0x18000cd25  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd2c  mov     edx, 1CBEh; void *
0x18000cd31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
