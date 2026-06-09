# UserContextHelpers::GetSystemTypeFromUserContextToken(unsigned __int64 const &,Windows::System::Internal::UserTypeInternal *)

- ea: `0x18000dca0`
- end: `0x18000df41`
- name: `?GetSystemTypeFromUserContextToken@UserContextHelpers@@QEAAJAEB_KPEAW4UserTypeInternal@Internal@System@Windows@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(UserContextHelpers *__hidden this, const unsigned __int64 *, enum Windows::System::Internal::UserTypeInternal *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006b040`
- `0x18007ce74`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x18000dca0`
- `0x180044408`
- `0x180059df8`
- `0x18005b37c`
- `0x18005b3c4`
- `0x180067e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df36`
- `ntdll!RtlIsMultiSessionSku` at `0x18000dd86`
- `ntdll!RtlIsMultiSessionSku` at `0x18000dd86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dd15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dd62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dd15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000dd62`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000dd78`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000dd78`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ded0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000ded0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000dcd7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000dcd7`

## string_xrefs

- `0x18000dd28`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000ddf4`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000de80`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall UserContextHelpers::GetSystemTypeFromUserContextToken(
        UserContextHelpers *this,
        const unsigned __int64 *a2,
        enum Windows::System::Internal::UserTypeInternal *a3)
{
  __int64 v5; // rcx
  char *v6; // r9
  int v7; // eax
  __int64 v8; // rdi
  const char *v9; // r9
  int LastError; // edi
  PSID *v11; // rbx
  const char *v12; // r9
  HANDLE v14; // rcx
  const char *v15; // r9
  unsigned int v16; // edi
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)a3 = 0;
  v5 = *a2;
  v6 = 0;
  TokenHandle = 0;
  if ( !v5 )
    goto LABEL_14;
  v7 = UMgrQueryUserToken(v5, &TokenHandle);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
      (const char *)(unsigned int)v7,
      ReturnLength);
    goto LABEL_13;
  }
  v8 = -6;
  TokenInformationLength = 0;
  if ( TokenHandle )
    v8 = (__int64)TokenHandle;
  if ( GetTokenInformation((HANDLE)v8, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v9);
    goto LABEL_7;
  }
  v11 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLengtha);
    goto LABEL_19;
  }
  if ( !GetTokenInformation((HANDLE)v8, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v12);
    operator delete(v11);
LABEL_7:
    v11 = 0;
    if ( LastError < 0 )
    {
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)LastError,
        ReturnLengtha);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return (unsigned int)LastError;
    }
  }
  if ( IsWellKnownSid(*v11, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
  {
    *(_DWORD *)a3 = 1;
    operator delete(v11);
    v14 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 0;
    goto LABEL_31;
  }
  if ( (unsigned __int8)RtlIsMultiSessionSku()
    || !*(_BYTE *)this
    || (int)UserContextHelpers::GetResourceAccountSid(this) < 0 )
  {
    goto LABEL_12;
  }
  TokenInformationLength = 0;
  if ( (unsigned int)CheckTokenMembershipEx(TokenHandle, (char *)this + 4, 0, &TokenInformationLength) )
  {
    if ( TokenInformationLength )
    {
      *(_DWORD *)a3 = 2;
      operator delete(v11);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 0;
    }
LABEL_12:
    operator delete(v11);
LABEL_13:
    v6 = (char *)TokenHandle;
LABEL_14:
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    v14 = v6;
LABEL_31:
    CloseHandle(v14);
    return 0;
  }
  v16 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
          v15);
  operator delete(v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v16;
}

```

## disassembly

```asm
0x18000dca0  mov     [rsp+arg_0], rbx
0x18000dca5  mov     [rsp+arg_18], rbp
0x18000dcaa  push    rsi
0x18000dcab  push    rdi
0x18000dcac  push    r14
0x18000dcae  sub     rsp, 30h
0x18000dcb2  xor     r14d, r14d
0x18000dcb5  mov     rbp, rcx
0x18000dcb8  mov     [r8], r14d
0x18000dcbb  mov     rsi, r8
0x18000dcbe  mov     rcx, [rdx]
0x18000dcc1  mov     r9d, r14d
0x18000dcc4  mov     [rsp+48h+TokenHandle], r14
0x18000dcc9  test    rcx, rcx
0x18000dccc  jz      loc_18000DDA1
0x18000dcd2  lea     rdx, [rsp+48h+TokenHandle]
0x18000dcd7  call    cs:__imp_UMgrQueryUserToken
0x18000dcdd  test    eax, eax
0x18000dcdf  js      loc_18000DE5D
0x18000dce5  mov     rax, [rsp+48h+TokenHandle]
0x18000dcea  mov     rdi, 0FFFFFFFFFFFFFFFAh
0x18000dcf1  test    rax, rax
0x18000dcf4  mov     [rsp+48h+TokenInformationLength], r14d
0x18000dcf9  mov     edx, 1; TokenInformationClass
0x18000dcfe  cmovnz  rdi, rax
0x18000dd02  lea     rax, [rsp+48h+TokenInformationLength]
0x18000dd07  mov     rcx, rdi; TokenHandle
0x18000dd0a  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000dd0f  xor     r9d, r9d; TokenInformationLength
0x18000dd12  xor     r8d, r8d; TokenInformation
0x18000dd15  call    cs:__imp_GetTokenInformation
0x18000dd1b  test    eax, eax
0x18000dd1d  jz      loc_18000DDC4
0x18000dd23  mov     rcx, [rsp+48h]; this
0x18000dd28  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dd2f  mov     edx, 117h; void *
0x18000dd34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dd39  mov     edi, eax
0x18000dd3b  mov     rbx, r14
0x18000dd3e  test    edi, edi
0x18000dd40  js      loc_18000DE0D
0x18000dd46  jmp     short loc_18000DD70
0x18000dd48  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000dd4d  lea     rax, [rsp+48h+TokenInformationLength]
0x18000dd52  mov     r8, rbx; TokenInformation
0x18000dd55  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x18000dd5a  mov     edx, 1; TokenInformationClass
0x18000dd5f  mov     rcx, rdi; TokenHandle
0x18000dd62  call    cs:__imp_GetTokenInformation
0x18000dd68  test    eax, eax
0x18000dd6a  jz      loc_18000DE7B
0x18000dd70  mov     rcx, [rbx]; pSid
0x18000dd73  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18000dd78  call    cs:__imp_IsWellKnownSid
0x18000dd7e  test    eax, eax
0x18000dd80  jnz     loc_18000DE37
0x18000dd86  call    cs:__imp_RtlIsMultiSessionSku
0x18000dd8c  test    al, al
0x18000dd8e  jz      loc_18000DEA0
0x18000dd94  mov     rcx, rbx; Block
0x18000dd97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dd9c  mov     r9, [rsp+48h+TokenHandle]
0x18000dda1  lea     rax, [r9-1]
0x18000dda5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dda9  jbe     loc_18000DF33
0x18000ddaf  xor     eax, eax
0x18000ddb1  mov     rbx, [rsp+48h+arg_0]
0x18000ddb6  mov     rbp, [rsp+48h+arg_18]
0x18000ddbb  add     rsp, 30h
0x18000ddbf  pop     r14
0x18000ddc1  pop     rdi
0x18000ddc2  pop     rsi
0x18000ddc3  retn
0x18000ddc4  call    cs:__imp_GetLastError
0x18000ddca  cmp     eax, 7Ah ; 'z'
0x18000ddcd  jnz     loc_18000DD23
0x18000ddd3  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000ddd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ddde  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dde3  mov     rbx, rax
0x18000dde6  test    rax, rax
0x18000dde9  jnz     loc_18000DD48
0x18000ddef  mov     rcx, [rsp+48h]; this
0x18000ddf4  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ddfb  mov     edi, 8007000Eh
0x18000de00  mov     edx, 119h; void *
0x18000de05  mov     r9d, edi; char *
0x18000de08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de0d  mov     rcx, [rsp+48h]; this
0x18000de12  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000de19  mov     r9d, edi; char *
0x18000de1c  mov     edx, 56h ; 'V'; void *
0x18000de21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de26  lea     rcx, [rsp+48h+TokenHandle]
0x18000de2b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000de30  mov     eax, edi
0x18000de32  jmp     loc_18000DDB1
0x18000de37  mov     rcx, rbx; Block
0x18000de3a  mov     dword ptr [rsi], 1
0x18000de40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de45  mov     rcx, [rsp+48h+TokenHandle]
0x18000de4a  lea     rax, [rcx-1]
0x18000de4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000de52  ja      loc_18000DDAF
0x18000de58  jmp     loc_18000DF36
0x18000de5d  mov     rcx, [rsp+48h]; this
0x18000de62  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000de69  mov     r9d, eax; char *
0x18000de6c  mov     edx, 52h ; 'R'; void *
0x18000de71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000de76  jmp     loc_18000DD9C
0x18000de7b  mov     rcx, [rsp+48h]; this
0x18000de80  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000de87  mov     edx, 11Ah; void *
0x18000de8c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de91  mov     rcx, rbx; Block
0x18000de94  mov     edi, eax
0x18000de96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de9b  jmp     loc_18000DD3B
0x18000dea0  cmp     [rbp+0], r14b
0x18000dea4  jz      loc_18000DD94
0x18000deaa  mov     rcx, rbp; this
0x18000dead  call    ?GetResourceAccountSid@UserContextHelpers@@AEAAJXZ; UserContextHelpers::GetResourceAccountSid(void)
0x18000deb2  test    eax, eax
0x18000deb4  js      loc_18000DD94
0x18000deba  mov     rcx, [rsp+48h+TokenHandle]
0x18000debf  lea     rdx, [rbp+4]
0x18000dec3  lea     r9, [rsp+48h+TokenInformationLength]
0x18000dec8  mov     [rsp+48h+TokenInformationLength], r14d
0x18000decd  xor     r8d, r8d
0x18000ded0  call    cs:__imp_CheckTokenMembershipEx
0x18000ded6  test    eax, eax
0x18000ded8  jnz     short loc_18000DF0B
0x18000deda  mov     rcx, [rsp+48h]; this
0x18000dedf  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000dee6  mov     edx, 61h ; 'a'; void *
0x18000deeb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000def0  mov     rcx, rbx; Block
0x18000def3  mov     edi, eax
0x18000def5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000defa  lea     rcx, [rsp+48h+TokenHandle]
0x18000deff  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000df04  mov     eax, edi
0x18000df06  jmp     loc_18000DDB1
0x18000df0b  cmp     [rsp+48h+TokenInformationLength], r14d
0x18000df10  jz      loc_18000DD94
0x18000df16  mov     rcx, rbx; Block
0x18000df19  mov     dword ptr [rsi], 2
0x18000df1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df24  lea     rcx, [rsp+48h+TokenHandle]
0x18000df29  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000df2e  jmp     loc_18000DDAF
0x18000df33  mov     rcx, r9; hObject
0x18000df36  call    cs:__imp_CloseHandle
0x18000df3c  jmp     loc_18000DDAF
```
