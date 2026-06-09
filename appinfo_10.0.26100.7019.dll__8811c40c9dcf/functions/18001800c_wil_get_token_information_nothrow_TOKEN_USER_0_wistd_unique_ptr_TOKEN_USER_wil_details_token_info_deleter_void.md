# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18001800c`
- end: `0x180018148`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `316`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010f3c`
- `0x18002b828`
- `0x1800320a8`
- `0x180038740`
- `0x18003eb60`

## callees

- `0x180007c78`
- `0x18001800c`
- `0x180018150`
- `0x18001b0c4`
- `0x18001b8a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001805c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800180d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001805c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800180d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018070`

## string_xrefs

- `0x1800180a2`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800180ee`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180018126`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  if ( !a2 )
    a2 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    if ( GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = *a1;
      *a1 = v6;
      if ( v10 )
        operator delete(v10);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v8);
      operator delete(v6);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001800c  mov     [rsp+arg_8], rbx
0x180018011  mov     [rsp+arg_10], rsi
0x180018016  push    rdi
0x180018017  sub     rsp, 30h
0x18001801b  mov     rdi, rcx
0x18001801e  mov     rsi, rdx
0x180018021  mov     rcx, [rcx]; Block
0x180018024  and     qword ptr [rdi], 0
0x180018028  test    rcx, rcx
0x18001802b  jz      short loc_180018032
0x18001802d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018032  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180018039  test    rsi, rsi
0x18001803c  cmovz   rsi, rax
0x180018040  and     [rsp+38h+TokenInformationLength], 0
0x180018045  xor     r9d, r9d; TokenInformationLength
0x180018048  lea     rax, [rsp+38h+TokenInformationLength]
0x18001804d  xor     r8d, r8d; TokenInformation
0x180018050  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180018055  mov     rcx, rsi; TokenHandle
0x180018058  lea     edx, [r9+1]; TokenInformationClass
0x18001805c  call    cs:__imp_GetTokenInformation
0x180018063  nop     dword ptr [rax+rax+00h]
0x180018068  test    eax, eax
0x18001806a  jnz     loc_180018121
0x180018070  call    cs:__imp_GetLastError
0x180018077  nop     dword ptr [rax+rax+00h]
0x18001807c  cmp     eax, 7Ah ; 'z'
0x18001807f  jnz     loc_180018121
0x180018085  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180018089  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018090  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018095  mov     rbx, rax
0x180018098  test    rax, rax
0x18001809b  jnz     short loc_1800180BF
0x18001809d  mov     rcx, [rsp+38h]; this
0x1800180a2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800180a9  mov     ebx, 8007000Eh
0x1800180ae  mov     edx, 119h; void *
0x1800180b3  mov     r9d, ebx; char *
0x1800180b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180bb  mov     eax, ebx
0x1800180bd  jmp     short loc_180018137
0x1800180bf  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800180c4  lea     rax, [rsp+38h+TokenInformationLength]
0x1800180c9  mov     r8, rbx; TokenInformation
0x1800180cc  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800180d1  mov     edx, 1; TokenInformationClass
0x1800180d6  mov     rcx, rsi; TokenHandle
0x1800180d9  call    cs:__imp_GetTokenInformation
0x1800180e0  nop     dword ptr [rax+rax+00h]
0x1800180e5  test    eax, eax
0x1800180e7  jnz     short loc_18001810D
0x1800180e9  mov     rcx, [rsp+38h]; this
0x1800180ee  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800180f5  mov     edx, 11Ah; void *
0x1800180fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800180ff  mov     rcx, rbx; Block
0x180018102  mov     edi, eax
0x180018104  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018109  mov     eax, edi
0x18001810b  jmp     short loc_180018137
0x18001810d  mov     rcx, [rdi]; Block
0x180018110  mov     [rdi], rbx
0x180018113  test    rcx, rcx
0x180018116  jz      short loc_18001811D
0x180018118  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001811d  xor     eax, eax
0x18001811f  jmp     short loc_180018137
0x180018121  mov     rcx, [rsp+38h]; this
0x180018126  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001812d  mov     edx, 117h; void *
0x180018132  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018137  mov     rbx, [rsp+38h+arg_8]
0x18001813c  mov     rsi, [rsp+38h+arg_10]
0x180018141  add     rsp, 30h
0x180018145  pop     rdi
0x180018146  retn
```
