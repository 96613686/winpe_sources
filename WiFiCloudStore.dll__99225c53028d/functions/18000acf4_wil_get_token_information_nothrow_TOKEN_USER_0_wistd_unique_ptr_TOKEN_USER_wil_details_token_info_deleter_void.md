# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18000acf4`
- end: `0x18000ae16`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `290`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ac9c`

## callees

- `0x18000acf4`
- `0x18002477c`
- `0x180028a70`
- `0x18002a43c`
- `0x18002a448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad43`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ad39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000adbe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ad39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000adbe`

## string_xrefs

- `0x18000ad6b`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000ad8d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000adf6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x18000acf4  mov     [rsp+arg_0], rbx
0x18000acf9  mov     [rsp+TokenInformationLength], rdx
0x18000acfe  push    rdi
0x18000acff  sub     rsp, 30h
0x18000ad03  mov     rbx, rcx
0x18000ad06  mov     rcx, [rcx]; Block
0x18000ad09  mov     qword ptr [rbx], 0
0x18000ad10  test    rcx, rcx
0x18000ad13  jnz     loc_18000ADE0
0x18000ad19  xor     r9d, r9d; TokenInformationLength
0x18000ad1c  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x18000ad24  lea     rax, [rsp+38h+TokenInformationLength]
0x18000ad29  xor     r8d, r8d; TokenInformation
0x18000ad2c  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000ad31  lea     edx, [r9+1]; TokenInformationClass
0x18000ad35  lea     rcx, [r9-6]; TokenHandle
0x18000ad39  call    cs:__imp_GetTokenInformation
0x18000ad3f  test    eax, eax
0x18000ad41  jnz     short loc_18000AD88
0x18000ad43  call    cs:__imp_GetLastError
0x18000ad49  cmp     eax, 7Ah ; 'z'
0x18000ad4c  jnz     short loc_18000AD88
0x18000ad4e  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18000ad52  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad59  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad5e  mov     rdi, rax
0x18000ad61  test    rax, rax
0x18000ad64  jnz     short loc_18000ADA0
0x18000ad66  mov     rcx, [rsp+38h]; this
0x18000ad6b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ad72  mov     ebx, 8007000Eh
0x18000ad77  mov     edx, 119h; void *
0x18000ad7c  mov     r9d, ebx; char *
0x18000ad7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad84  mov     eax, ebx
0x18000ad86  jmp     short loc_18000ADD5
0x18000ad88  mov     rcx, [rsp+38h]; this
0x18000ad8d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ad94  mov     edx, 117h; void *
0x18000ad99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad9e  jmp     short loc_18000ADD5
0x18000ada0  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18000ada5  lea     rax, [rsp+38h+TokenInformationLength]
0x18000adaa  mov     r8, rdi; TokenInformation
0x18000adad  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18000adb2  mov     edx, 1; TokenInformationClass
0x18000adb7  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18000adbe  call    cs:__imp_GetTokenInformation
0x18000adc4  test    eax, eax
0x18000adc6  jz      short loc_18000ADF1
0x18000adc8  mov     rcx, [rbx]; Block
0x18000adcb  mov     [rbx], rdi
0x18000adce  test    rcx, rcx
0x18000add1  jnz     short loc_18000ADEA
0x18000add3  xor     eax, eax
0x18000add5  mov     rbx, [rsp+38h+arg_0]
0x18000adda  add     rsp, 30h
0x18000adde  pop     rdi
0x18000addf  retn
0x18000ade0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ade5  jmp     loc_18000AD19
0x18000adea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000adef  jmp     short loc_18000ADD3
0x18000adf1  mov     rcx, [rsp+38h]; this
0x18000adf6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000adfd  mov     edx, 11Ah; void *
0x18000ae02  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae07  mov     rcx, rdi; Block
0x18000ae0a  mov     ebx, eax
0x18000ae0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ae11  jmp     loc_18000AD84
```
