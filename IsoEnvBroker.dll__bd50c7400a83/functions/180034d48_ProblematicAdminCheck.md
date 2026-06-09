# _ProblematicAdminCheck

- ea: `0x180034d48`
- end: `0x180034f8e`
- name: `_ProblematicAdminCheck`
- size: `582`
- prototype: `char()`
- caller_count: `11`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032e60`
- `0x180053cf0`
- `0x180054d30`
- `0x1800555f0`
- `0x180055670`
- `0x180058110`
- `0x18005da50`
- `0x18005e6a0`
- `0x18005f190`
- `0x18005f240`
- `0x18005f2c0`

## callees

- `0x180002a54`
- `0x18000a444`
- `0x180011e18`
- `0x180013270`
- `0x180032568`
- `0x180034d48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034f3a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034f67`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034f3a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034f67`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180034d55`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180034d55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034e55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034e55`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034e2b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034e2b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034e1a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034e1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034d98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034e91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034eeb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034d98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034e91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034eeb`

## string_xrefs

- `0x180034f7c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180034da6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180034e9f`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180034ef9`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180034dbe`: `Caller validation failed. Failed to get token of the caller: %#x`
- `0x180034f47`: `Caller validation failed. Failed to get tokenMandatoryLabel: %#x`
- `0x180034eb7`: `Caller validation failed. Failed to get the elevation token: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char ProblematicAdminCheck()
{
  HRESULT v0; // eax
  const char *v1; // r9
  int LastError; // eax
  int token_information; // edi
  PSID *v4; // rbx
  UCHAR v5; // cl
  const char *v6; // r9
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  __int64 TokenInformation; // [rsp+30h] [rbp-18h] BYREF
  void *Block; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int v15; // [rsp+78h] [rbp+30h] BYREF
  DWORD v16; // [rsp+80h] [rbp+38h] BYREF
  DWORD v17; // [rsp+88h] [rbp+40h] BYREF

  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v0,
      ReturnLength);
  TokenInformation = 0;
  v16 = 8;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenOrigin, &TokenInformation, 8u, &v16) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v1);
    if ( LastError < 0 )
    {
      Log(2u, L"Caller validation failed. Failed to get token of the caller: %#x", (unsigned int)LastError);
LABEL_29:
      CoRevertToSelf();
      return 0;
    }
  }
  if ( !TokenInformation )
  {
    Log(2u, L"Caller validation failed. Caller is remote");
    goto LABEL_29;
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(&Block, -5);
  v4 = (PSID *)Block;
  if ( token_information < 0 || !IsValidSid(*(PSID *)Block) )
  {
    Log(2u, L"Caller validation failed. Failed to get tokenMandatoryLabel: %#x", (unsigned int)token_information);
    goto LABEL_27;
  }
  v5 = *GetSidSubAuthorityCount(*v4);
  if ( !v5 )
  {
    Log(2u, L"Caller validation failed. Integrity level index is 0");
LABEL_27:
    if ( v4 )
      operator delete(v4);
    goto LABEL_29;
  }
  if ( *GetSidSubAuthority(*v4, (unsigned __int8)(v5 - 1)) < 0x2000 )
  {
    Log(2u, L"Caller validation failed. Integrity level is low");
    goto LABEL_27;
  }
  v15 = 0;
  v16 = 4;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenElevation, &v15, 4u, &v16) )
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x128,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
           v6);
    if ( v7 < 0 )
    {
      Log(2u, L"Caller validation failed. Failed to get the elevation token: %#x", (unsigned int)v7);
      goto LABEL_27;
    }
  }
  if ( !v15 )
  {
    v16 = 0;
    v17 = 4;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenElevationType, &v16, 4u, &v17) )
    {
      v9 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x128,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v8);
      if ( v9 < 0 )
      {
        Log(2u, L"Caller validation failed. Failed to get the elevation type: %#x", (unsigned int)v9);
        goto LABEL_27;
      }
    }
    if ( v16 != 3 )
    {
      Log(2u, L"Caller validation failed. Caller is not able to elevate");
      goto LABEL_27;
    }
  }
  if ( v4 )
    operator delete(v4);
  CoRevertToSelf();
  return 1;
}

```

## disassembly

```asm
0x180034d48  push    rbp
0x180034d4a  push    rbx
0x180034d4b  push    rdi
0x180034d4c  push    r14
0x180034d4e  mov     rbp, rsp
0x180034d51  sub     rsp, 48h
0x180034d55  call    cs:__imp_CoImpersonateClient
0x180034d5b  mov     rcx, [rbp+20h]; this
0x180034d5f  test    eax, eax
0x180034d61  js      loc_180034F79
0x180034d67  mov     [rbp+arg_0], 1
0x180034d6b  mov     [rbp+TokenInformation], 0
0x180034d73  mov     r9d, 8; TokenInformationLength
0x180034d79  mov     [rbp+arg_10], r9d
0x180034d7d  lea     rax, [rbp+arg_10]
0x180034d81  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180034d86  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180034d8a  lea     edx, [r9+9]; TokenInformationClass
0x180034d8e  mov     r14, 0FFFFFFFFFFFFFFFBh
0x180034d95  mov     rcx, r14; TokenHandle
0x180034d98  call    cs:__imp_GetTokenInformation
0x180034d9e  test    eax, eax
0x180034da0  jnz     short loc_180034DD3
0x180034da2  mov     rcx, [rbp+20h]; this
0x180034da6  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034dad  mov     edx, 128h; void *
0x180034db2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034db7  test    eax, eax
0x180034db9  jns     short loc_180034DD3
0x180034dbb  mov     r8d, eax
0x180034dbe  lea     rdx, aCallerValidati_1; "Caller validation failed. Failed to get"...
0x180034dc5  lea     ecx, [r14+7]; unsigned __int8
0x180034dc9  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034dce  jmp     loc_180034F67
0x180034dd3  cmp     dword ptr [rbp+TokenInformation+4], 0
0x180034dd7  jnz     short loc_180034DF5
0x180034dd9  cmp     dword ptr [rbp+TokenInformation], 0
0x180034ddd  jnz     short loc_180034DF5
0x180034ddf  lea     rdx, aCallerValidati_4; "Caller validation failed. Caller is rem"...
0x180034de6  mov     ecx, 2; unsigned __int8
0x180034deb  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034df0  jmp     loc_180034F67
0x180034df5  mov     [rbp+Block], 0
0x180034dfd  mov     rdx, r14
0x180034e00  lea     rcx, [rbp+Block]
0x180034e04  call    ??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)
0x180034e09  mov     edi, eax
0x180034e0b  mov     rbx, [rbp+Block]
0x180034e0f  test    eax, eax
0x180034e11  js      loc_180034F44
0x180034e17  mov     rcx, [rbx]; pSid
0x180034e1a  call    cs:__imp_IsValidSid
0x180034e20  test    eax, eax
0x180034e22  jz      loc_180034F44
0x180034e28  mov     rcx, [rbx]; pSid
0x180034e2b  call    cs:__imp_GetSidSubAuthorityCount
0x180034e31  mov     cl, [rax]
0x180034e33  test    cl, cl
0x180034e35  jnz     short loc_180034E4D
0x180034e37  lea     rdx, aCallerValidati_6; "Caller validation failed. Integrity lev"...
0x180034e3e  mov     ecx, 2; unsigned __int8
0x180034e43  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034e48  jmp     loc_180034F59
0x180034e4d  dec     cl
0x180034e4f  movzx   edx, cl; nSubAuthority
0x180034e52  mov     rcx, [rbx]; pSid
0x180034e55  call    cs:__imp_GetSidSubAuthority
0x180034e5b  cmp     dword ptr [rax], 2000h
0x180034e61  jnb     short loc_180034E6C
0x180034e63  lea     rdx, aCallerValidati_3; "Caller validation failed. Integrity lev"...
0x180034e6a  jmp     short loc_180034E3E
0x180034e6c  mov     [rbp+arg_8], 0
0x180034e73  mov     edi, 4
0x180034e78  mov     [rbp+arg_10], edi
0x180034e7b  lea     rax, [rbp+arg_10]
0x180034e7f  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180034e84  mov     r9d, edi; TokenInformationLength
0x180034e87  lea     r8, [rbp+arg_8]; TokenInformation
0x180034e8b  lea     edx, [rdi+10h]; TokenInformationClass
0x180034e8e  mov     rcx, r14; TokenHandle
0x180034e91  call    cs:__imp_GetTokenInformation
0x180034e97  test    eax, eax
0x180034e99  jnz     short loc_180034EC3
0x180034e9b  mov     rcx, [rbp+20h]; this
0x180034e9f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034ea6  mov     edx, 128h; void *
0x180034eab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034eb0  test    eax, eax
0x180034eb2  jns     short loc_180034EC3
0x180034eb4  mov     r8d, eax
0x180034eb7  lea     rdx, aCallerValidati_5; "Caller validation failed. Failed to get"...
0x180034ebe  jmp     loc_180034F4E
0x180034ec3  cmp     [rbp+arg_8], 0
0x180034ec7  jnz     short loc_180034F2C
0x180034ec9  mov     [rbp+arg_10], 0
0x180034ed0  mov     [rbp+arg_18], edi
0x180034ed3  lea     rax, [rbp+arg_18]
0x180034ed7  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180034edc  mov     r9d, edi; TokenInformationLength
0x180034edf  lea     r8, [rbp+arg_10]; TokenInformation
0x180034ee3  mov     edx, 12h; TokenInformationClass
0x180034ee8  mov     rcx, r14; TokenHandle
0x180034eeb  call    cs:__imp_GetTokenInformation
0x180034ef1  test    eax, eax
0x180034ef3  jnz     short loc_180034F1A
0x180034ef5  mov     rcx, [rbp+20h]; this
0x180034ef9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f00  mov     edx, 128h; void *
0x180034f05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034f0a  test    eax, eax
0x180034f0c  jns     short loc_180034F1A
0x180034f0e  mov     r8d, eax
0x180034f11  lea     rdx, aCallerValidati_0; "Caller validation failed. Failed to get"...
0x180034f18  jmp     short loc_180034F4E
0x180034f1a  cmp     [rbp+arg_10], 3
0x180034f1e  jz      short loc_180034F2C
0x180034f20  lea     rdx, aCallerValidati; "Caller validation failed. Caller is not"...
0x180034f27  jmp     loc_180034E3E
0x180034f2c  test    rbx, rbx
0x180034f2f  jz      short loc_180034F3A
0x180034f31  mov     rcx, rbx; Block
0x180034f34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034f39  nop
0x180034f3a  call    cs:__imp_CoRevertToSelf
0x180034f40  mov     al, 1
0x180034f42  jmp     short loc_180034F6F
0x180034f44  mov     r8d, edi
0x180034f47  lea     rdx, aCallerValidati_2; "Caller validation failed. Failed to get"...
0x180034f4e  mov     ecx, 2; unsigned __int8
0x180034f53  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034f58  nop
0x180034f59  test    rbx, rbx
0x180034f5c  jz      short loc_180034F67
0x180034f5e  mov     rcx, rbx; Block
0x180034f61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034f66  nop
0x180034f67  call    cs:__imp_CoRevertToSelf
0x180034f6d  xor     al, al
0x180034f6f  add     rsp, 48h
0x180034f73  pop     r14
0x180034f75  pop     rdi
0x180034f76  pop     rbx
0x180034f77  pop     rbp
0x180034f78  retn
0x180034f79  mov     r9d, eax; char *
0x180034f7c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f83  mov     edx, 14AAh; void *
0x180034f88  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
