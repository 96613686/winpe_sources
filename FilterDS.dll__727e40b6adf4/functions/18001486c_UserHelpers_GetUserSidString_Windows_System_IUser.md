# UserHelpers::GetUserSidString(Windows::System::IUser *)

- ea: `0x18001486c`
- end: `0x1800149fb`
- name: `?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `399`
- prototype: `LPWSTR *__fastcall(LPWSTR *StringSid, UserHelpers *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800136c0`

## callees

- `0x180002a70`
- `0x180005c84`
- `0x180005ca4`
- `0x18000cd18`
- `0x18001486c`
- `0x180014a04`
- `0x180015a30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001495f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800149c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001495f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800149c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800148d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001493b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800148d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001493b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800149b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800149b7`

## string_xrefs

- `0x1800149e9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180014910`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180014949`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180014976`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
LPWSTR *__fastcall UserHelpers::GetUserSidString(LPWSTR *StringSid, UserHelpers *a2)
{
  __int64 *UserTokenHandle; // rax
  PSID *v4; // rbx
  __int64 v5; // rdi
  const char *v6; // r9
  PSID *v7; // rsi
  int LastError; // edi
  const char *v9; // r9
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  int ReturnLength; // [rsp+20h] [rbp-20h]
  HANDLE hObject; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  PSID *v18; // [rsp+88h] [rbp+48h]

  *StringSid = 0;
  UserTokenHandle = (__int64 *)UserHelpers::GetUserTokenHandle(&hObject, a2);
  v4 = 0;
  v18 = 0;
  v5 = -6;
  if ( *UserTokenHandle )
    v5 = *UserTokenHandle;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v5, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v6);
  }
  else
  {
    v7 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v7 )
    {
      if ( GetTokenInformation((HANDLE)v5, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      {
        v4 = v7;
        v18 = v7;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                      v9);
        operator delete(v7);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( !ConvertSidToStringSidW(*v4, StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v10, v11, v12);
  if ( v4 )
    operator delete(v4);
  return StringSid;
}

```

## disassembly

```asm
0x18001486c  mov     [rsp-28h+arg_0], rcx
0x180014871  push    rbp
0x180014872  push    rbx
0x180014873  push    rsi
0x180014874  push    rdi
0x180014875  push    r14
0x180014877  mov     rbp, rsp
0x18001487a  sub     rsp, 40h
0x18001487e  mov     r14, rcx
0x180014881  mov     [rbp+var_10], 0
0x180014888  mov     [rbp+var_10], 1
0x18001488f  mov     qword ptr [rcx], 0
0x180014896  lea     rcx, [rbp+hObject]; TokenHandle
0x18001489a  call    ?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserTokenHandle(Windows::System::IUser *)
0x18001489f  nop
0x1800148a0  mov     [rbp+var_10], 9
0x1800148a7  xor     ebx, ebx
0x1800148a9  mov     [rbp+arg_18], rbx
0x1800148ad  lea     rdi, [rbx-6]
0x1800148b1  cmp     [rax], rbx
0x1800148b4  cmovnz  rdi, [rax]
0x1800148b8  mov     [rbp+TokenInformationLength], ebx
0x1800148bb  lea     rax, [rbp+TokenInformationLength]
0x1800148bf  mov     qword ptr [rsp+40h+ReturnLength], rax; int
0x1800148c4  xor     r9d, r9d; TokenInformationLength
0x1800148c7  xor     r8d, r8d; TokenInformation
0x1800148ca  lea     edx, [rbx+1]; TokenInformationClass
0x1800148cd  mov     rcx, rdi; TokenHandle
0x1800148d0  call    cs:__imp_GetTokenInformation
0x1800148d6  test    eax, eax
0x1800148d8  jnz     loc_180014972
0x1800148de  call    cs:__imp_GetLastError
0x1800148e4  cmp     eax, 7Ah ; 'z'
0x1800148e7  jnz     loc_180014972
0x1800148ed  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1800148f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800148f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800148fc  mov     rsi, rax
0x1800148ff  test    rax, rax
0x180014902  jnz     short loc_180014923
0x180014904  mov     rcx, [rbp+28h]; this
0x180014908  mov     edi, 8007000Eh
0x18001490d  mov     r9d, edi; char *
0x180014910  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014917  mov     edx, 119h; void *
0x18001491c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014921  jmp     short loc_180014989
0x180014923  lea     rax, [rbp+TokenInformationLength]
0x180014927  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x18001492c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180014930  mov     r8, rsi; TokenInformation
0x180014933  mov     edx, 1; TokenInformationClass
0x180014938  mov     rcx, rdi; TokenHandle
0x18001493b  call    cs:__imp_GetTokenInformation
0x180014941  test    eax, eax
0x180014943  jnz     short loc_180014967
0x180014945  mov     rcx, [rbp+28h]; this
0x180014949  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014950  mov     edx, 11Ah; void *
0x180014955  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001495a  mov     edi, eax
0x18001495c  mov     rcx, rsi
0x18001495f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014965  jmp     short loc_180014989
0x180014967  mov     rbx, rsi
0x18001496a  mov     [rbp+arg_18], rbx
0x18001496e  xor     edi, edi
0x180014970  jmp     short loc_180014989
0x180014972  mov     rcx, [rbp+28h]; this
0x180014976  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001497d  mov     edx, 117h; void *
0x180014982  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014987  mov     edi, eax
0x180014989  mov     rcx, [rbp+28h]; this
0x18001498d  test    edi, edi
0x18001498f  js      short loc_1800149E6
0x180014991  mov     [rbp+var_10], 7
0x180014998  mov     rcx, [rbp+hObject]; hObject
0x18001499c  lea     rax, [rcx-1]
0x1800149a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800149a4  ja      short loc_1800149AD
0x1800149a6  call    cs:__imp_CloseHandle
0x1800149ac  nop
0x1800149ad  mov     rdi, [rbp+28h]
0x1800149b1  mov     rdx, r14; StringSid
0x1800149b4  mov     rcx, [rbx]; Sid
0x1800149b7  call    cs:__imp_ConvertSidToStringSidW
0x1800149bd  test    eax, eax
0x1800149bf  jz      short loc_1800149DD
0x1800149c1  test    rbx, rbx
0x1800149c4  jz      short loc_1800149CF
0x1800149c6  mov     rcx, rbx
0x1800149c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800149cf  mov     rax, r14
0x1800149d2  add     rsp, 40h
0x1800149d6  pop     r14
0x1800149d8  pop     rdi
0x1800149d9  pop     rsi
0x1800149da  pop     rbx
0x1800149db  pop     rbp
0x1800149dc  retn
0x1800149dd  mov     rcx, rdi; this
0x1800149e0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800149e6  mov     r9d, edi; char *
0x1800149e9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800149f0  mov     edx, 1CBEh; void *
0x1800149f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
