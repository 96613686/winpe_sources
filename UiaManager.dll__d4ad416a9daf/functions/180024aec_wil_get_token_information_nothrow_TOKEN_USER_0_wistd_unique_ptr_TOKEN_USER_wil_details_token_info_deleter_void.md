# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180024aec`
- end: `0x180024c08`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024a94`

## callees

- `0x180006edc`
- `0x180024aec`
- `0x180024f38`
- `0x180043ad0`
- `0x180043af4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024b32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024ba7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024b32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024ba7`

## string_xrefs

- `0x180024b6c`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180024bb6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180024bec`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
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
0x180024aec  mov     [rsp+arg_0], rbx
0x180024af1  mov     [rsp+TokenInformationLength], rdx
0x180024af6  push    rdi
0x180024af7  sub     rsp, 30h
0x180024afb  mov     rbx, rcx
0x180024afe  mov     rcx, [rcx]; Block
0x180024b01  mov     qword ptr [rbx], 0
0x180024b08  test    rcx, rcx
0x180024b0b  jz      short loc_180024B12
0x180024b0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024b12  xor     r9d, r9d; TokenInformationLength
0x180024b15  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x180024b1d  lea     rax, [rsp+38h+TokenInformationLength]
0x180024b22  xor     r8d, r8d; TokenInformation
0x180024b25  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180024b2a  lea     edx, [r9+1]; TokenInformationClass
0x180024b2e  lea     rcx, [r9-6]; TokenHandle
0x180024b32  call    cs:__imp_GetTokenInformation
0x180024b38  test    eax, eax
0x180024b3a  jnz     loc_180024BE7
0x180024b40  call    cs:__imp_GetLastError
0x180024b46  cmp     eax, 7Ah ; 'z'
0x180024b49  jnz     loc_180024BE7
0x180024b4f  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x180024b53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024b5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024b5f  mov     rdi, rax
0x180024b62  test    rax, rax
0x180024b65  jnz     short loc_180024B89
0x180024b67  mov     rcx, [rsp+38h]; this
0x180024b6c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b73  mov     ebx, 8007000Eh
0x180024b78  mov     edx, 119h; void *
0x180024b7d  mov     r9d, ebx; char *
0x180024b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b85  mov     eax, ebx
0x180024b87  jmp     short loc_180024BFD
0x180024b89  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180024b8e  lea     rax, [rsp+38h+TokenInformationLength]
0x180024b93  mov     r8, rdi; TokenInformation
0x180024b96  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180024b9b  mov     edx, 1; TokenInformationClass
0x180024ba0  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180024ba7  call    cs:__imp_GetTokenInformation
0x180024bad  test    eax, eax
0x180024baf  jnz     short loc_180024BD3
0x180024bb1  mov     rcx, [rsp+38h]; this
0x180024bb6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024bbd  mov     edx, 11Ah; void *
0x180024bc2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024bc7  mov     rcx, rdi; Block
0x180024bca  mov     ebx, eax
0x180024bcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024bd1  jmp     short loc_180024B85
0x180024bd3  mov     rcx, [rbx]; Block
0x180024bd6  mov     [rbx], rdi
0x180024bd9  test    rcx, rcx
0x180024bdc  jz      short loc_180024BE3
0x180024bde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024be3  xor     eax, eax
0x180024be5  jmp     short loc_180024BFD
0x180024be7  mov     rcx, [rsp+38h]; this
0x180024bec  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024bf3  mov     edx, 117h; void *
0x180024bf8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024bfd  mov     rbx, [rsp+38h+arg_0]
0x180024c02  add     rsp, 30h
0x180024c06  pop     rdi
0x180024c07  retn
```
