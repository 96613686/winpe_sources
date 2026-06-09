# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180063800`
- end: `0x180063922`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006323c`

## callees

- `0x18002c8d0`
- `0x180063800`
- `0x180083aa8`
- `0x1800867dc`
- `0x180086800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006384f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006384f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063845`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800638ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063845`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800638ec`

## string_xrefs

- `0x180063877`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800638a2`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800638fb`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rdi
  unsigned int LastError; // ebx
  void *v8; // rcx
  const char *v9; // r9
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
                  v9);
    operator delete(v5);
    return LastError;
  }
  v8 = *a1;
  *a1 = v5;
  if ( v8 )
    operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x180063800  mov     [rsp+arg_0], rbx
0x180063805  mov     [rsp+TokenInformationLength], rdx
0x18006380a  push    rdi
0x18006380b  sub     rsp, 30h
0x18006380f  mov     rbx, rcx
0x180063812  mov     rcx, [rcx]; Block
0x180063815  mov     qword ptr [rbx], 0
0x18006381c  test    rcx, rcx
0x18006381f  jnz     loc_1800638C4
0x180063825  xor     r9d, r9d; TokenInformationLength
0x180063828  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x180063830  lea     rax, [rsp+38h+TokenInformationLength]
0x180063835  xor     r8d, r8d; TokenInformation
0x180063838  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18006383d  lea     edx, [r9+1]; TokenInformationClass
0x180063841  lea     rcx, [r9-6]; TokenHandle
0x180063845  call    cs:__imp_GetTokenInformation
0x18006384b  test    eax, eax
0x18006384d  jnz     short loc_18006389D
0x18006384f  call    cs:__imp_GetLastError
0x180063855  cmp     eax, 7Ah ; 'z'
0x180063858  jnz     short loc_18006389D
0x18006385a  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18006385e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063865  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006386a  mov     rdi, rax
0x18006386d  test    rax, rax
0x180063870  jnz     short loc_1800638CE
0x180063872  mov     rcx, [rsp+38h]; this
0x180063877  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006387e  mov     ebx, 8007000Eh
0x180063883  mov     edx, 119h; void *
0x180063888  mov     r9d, ebx; char *
0x18006388b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063890  mov     eax, ebx
0x180063892  mov     rbx, [rsp+38h+arg_0]
0x180063897  add     rsp, 30h
0x18006389b  pop     rdi
0x18006389c  retn
0x18006389d  mov     rcx, [rsp+38h]; this
0x1800638a2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800638a9  mov     edx, 117h; void *
0x1800638ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800638b3  jmp     short loc_180063892
0x1800638b5  mov     rcx, [rbx]; Block
0x1800638b8  mov     [rbx], rdi
0x1800638bb  test    rcx, rcx
0x1800638be  jnz     short loc_18006391B
0x1800638c0  xor     eax, eax
0x1800638c2  jmp     short loc_180063892
0x1800638c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800638c9  jmp     loc_180063825
0x1800638ce  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800638d3  lea     rax, [rsp+38h+TokenInformationLength]
0x1800638d8  mov     r8, rdi; TokenInformation
0x1800638db  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800638e0  mov     edx, 1; TokenInformationClass
0x1800638e5  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800638ec  call    cs:__imp_GetTokenInformation
0x1800638f2  test    eax, eax
0x1800638f4  jnz     short loc_1800638B5
0x1800638f6  mov     rcx, [rsp+38h]; this
0x1800638fb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180063902  mov     edx, 11Ah; void *
0x180063907  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006390c  mov     rcx, rdi; Block
0x18006390f  mov     ebx, eax
0x180063911  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063916  jmp     loc_180063890
0x18006391b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180063920  jmp     short loc_1800638C0
```
