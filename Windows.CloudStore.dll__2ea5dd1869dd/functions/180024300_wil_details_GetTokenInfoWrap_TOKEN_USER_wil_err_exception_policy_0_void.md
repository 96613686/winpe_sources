# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x180024300`
- end: `0x18002444a`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180024020`
- `0x1800307d4`
- `0x1800320f0`
- `0x1800322f8`
- `0x18003be48`

## callees

- `0x180016cf4`
- `0x180024300`
- `0x1800c8458`
- `0x1800fc644`
- `0x180120850`
- `0x1801236bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024363`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024355`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800243a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024355`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800243a4`

## string_xrefs

- `0x1800243f7`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800243de`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002440e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002442c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1, __int64 a2)
{
  __int64 v2; // rsi
  const char *v4; // r9
  void *v5; // rbx
  const char *v6; // r9
  void *v7; // rcx
  int LastError; // esi
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
    goto LABEL_13;
  }
  v5 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    goto LABEL_11;
  }
  if ( !GetTokenInformation((HANDLE)v2, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v6);
    operator delete(v5);
LABEL_13:
    if ( LastError >= 0 )
      return a1;
LABEL_11:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  }
  v7 = *a1;
  *a1 = v5;
  if ( v7 )
    operator delete(v7);
  return a1;
}

```

## disassembly

```asm
0x180024300  mov     [rsp+arg_10], rbx
0x180024305  mov     [rsp+arg_18], rsi
0x18002430a  mov     [rsp+arg_0], rcx
0x18002430f  push    rdi
0x180024310  sub     rsp, 40h
0x180024314  mov     rsi, rdx
0x180024317  mov     rdi, rcx
0x18002431a  xor     ecx, ecx
0x18002431c  mov     [rsp+48h+var_18], ecx
0x180024320  mov     [rsp+48h+var_18], 1
0x180024328  mov     [rdi], rcx
0x18002432b  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180024332  test    rdx, rdx
0x180024335  cmovz   rsi, rax
0x180024339  mov     [rsp+48h+TokenInformationLength], ecx
0x18002433d  lea     rax, [rsp+48h+TokenInformationLength]
0x180024342  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x180024347  xor     r9d, r9d; TokenInformationLength
0x18002434a  xor     r8d, r8d; TokenInformation
0x18002434d  mov     edx, 1; TokenInformationClass
0x180024352  mov     rcx, rsi; TokenHandle
0x180024355  call    cs:__imp_GetTokenInformation
0x18002435b  test    eax, eax
0x18002435d  jnz     loc_180024409
0x180024363  call    cs:__imp_GetLastError
0x180024369  cmp     eax, 7Ah ; 'z'
0x18002436c  jnz     loc_180024409
0x180024372  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x180024376  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002437d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024382  mov     rbx, rax
0x180024385  test    rax, rax
0x180024388  jz      short loc_1800243D1
0x18002438a  lea     rax, [rsp+48h+TokenInformationLength]
0x18002438f  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180024394  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180024399  mov     r8, rbx; TokenInformation
0x18002439c  mov     edx, 1; TokenInformationClass
0x1800243a1  mov     rcx, rsi; TokenHandle
0x1800243a4  call    cs:__imp_GetTokenInformation
0x1800243aa  test    eax, eax
0x1800243ac  jz      short loc_180024427
0x1800243ae  mov     rcx, [rdi]; Block
0x1800243b1  mov     [rdi], rbx
0x1800243b4  test    rcx, rcx
0x1800243b7  jz      short loc_1800243BE
0x1800243b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800243be  mov     rax, rdi
0x1800243c1  mov     rbx, [rsp+48h+arg_10]
0x1800243c6  mov     rsi, [rsp+48h+arg_18]
0x1800243cb  add     rsp, 40h
0x1800243cf  pop     rdi
0x1800243d0  retn
0x1800243d1  mov     rcx, [rsp+48h]; this
0x1800243d6  mov     esi, 8007000Eh
0x1800243db  mov     r9d, esi; char *
0x1800243de  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800243e5  mov     edx, 119h; void *
0x1800243ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800243ef  mov     rcx, [rsp+48h]; this
0x1800243f4  mov     r9d, esi; char *
0x1800243f7  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800243fe  mov     edx, 1CBEh; void *
0x180024403  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024409  mov     rcx, [rsp+48h]; this
0x18002440e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024415  mov     edx, 117h; void *
0x18002441a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002441f  mov     esi, eax
0x180024421  test    esi, esi
0x180024423  js      short loc_1800243EF
0x180024425  jmp     short loc_1800243BE
0x180024427  mov     rcx, [rsp+48h]; this
0x18002442c  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024433  mov     edx, 11Ah; void *
0x180024438  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002443d  mov     esi, eax
0x18002443f  mov     rcx, rbx; Block
0x180024442  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024447  jmp     short loc_180024421
```
