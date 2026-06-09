# get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x18003c380`
- end: `0x18003c49f`
- name: `?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800375fc`

## callees

- `0x18000720c`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18001ef98`
- `0x18003c380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c3c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c439`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c3c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c439`

## string_xrefs

- `0x18003c402`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003c448`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003c47e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall get_token_information_nothrow(void **a1, void *a2)
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
  if ( GetTokenInformation(a2, TokenSecurityAttributes, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2F3,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation(a2, TokenSecurityAttributes, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2F7,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
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
0x18003c380  mov     [rsp+arg_8], rbx
0x18003c385  mov     [rsp+arg_10], rsi
0x18003c38a  push    rdi
0x18003c38b  sub     rsp, 30h
0x18003c38f  mov     rbx, rcx
0x18003c392  mov     rsi, rdx
0x18003c395  mov     rcx, [rcx]; Block
0x18003c398  mov     qword ptr [rbx], 0
0x18003c39f  test    rcx, rcx
0x18003c3a2  jz      short loc_18003C3A9
0x18003c3a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c3a9  xor     r9d, r9d; TokenInformationLength
0x18003c3ac  mov     [rsp+38h+TokenInformationLength], 0
0x18003c3b4  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c3b9  xor     r8d, r8d; TokenInformation
0x18003c3bc  mov     rcx, rsi; TokenHandle
0x18003c3bf  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003c3c4  lea     edx, [r9+27h]; TokenInformationClass
0x18003c3c8  call    cs:__imp_GetTokenInformation
0x18003c3ce  test    eax, eax
0x18003c3d0  jnz     loc_18003C479
0x18003c3d6  call    cs:__imp_GetLastError
0x18003c3dc  cmp     eax, 7Ah ; 'z'
0x18003c3df  jnz     loc_18003C479
0x18003c3e5  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003c3e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c3f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c3f5  mov     rdi, rax
0x18003c3f8  test    rax, rax
0x18003c3fb  jnz     short loc_18003C41F
0x18003c3fd  mov     rcx, [rsp+38h]; this
0x18003c402  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003c409  mov     ebx, 8007000Eh
0x18003c40e  mov     edx, 2F6h; void *
0x18003c413  mov     r9d, ebx; char *
0x18003c416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c41b  mov     eax, ebx
0x18003c41d  jmp     short loc_18003C48F
0x18003c41f  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003c424  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c429  mov     r8, rdi; TokenInformation
0x18003c42c  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003c431  mov     edx, 27h ; '''; TokenInformationClass
0x18003c436  mov     rcx, rsi; TokenHandle
0x18003c439  call    cs:__imp_GetTokenInformation
0x18003c43f  test    eax, eax
0x18003c441  jnz     short loc_18003C465
0x18003c443  mov     rcx, [rsp+38h]; this
0x18003c448  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003c44f  mov     edx, 2F7h; void *
0x18003c454  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c459  mov     rcx, rdi; Block
0x18003c45c  mov     ebx, eax
0x18003c45e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c463  jmp     short loc_18003C41B
0x18003c465  mov     rcx, [rbx]; Block
0x18003c468  mov     [rbx], rdi
0x18003c46b  test    rcx, rcx
0x18003c46e  jz      short loc_18003C475
0x18003c470  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c475  xor     eax, eax
0x18003c477  jmp     short loc_18003C48F
0x18003c479  mov     rcx, [rsp+38h]; this
0x18003c47e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003c485  mov     edx, 2F3h; void *
0x18003c48a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c48f  mov     rbx, [rsp+38h+arg_8]
0x18003c494  mov     rsi, [rsp+38h+arg_10]
0x18003c499  add     rsp, 30h
0x18003c49d  pop     rdi
0x18003c49e  retn
```
