# cdp::GetCallerUserContextToken(unsigned __int64 &)

- ea: `0x1800429e0`
- end: `0x180042b44`
- name: `?GetCallerUserContextToken@cdp@@YAJAEA_K@Z`
- size: `356`
- prototype: `__int64 __fastcall(cdp *__hidden this, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800193d0`
- `0x1800363b0`
- `0x180036690`

## callees

- `0x1800257e0`
- `0x18004263c`
- `0x180042740`
- `0x1800427e4`
- `0x1800429e0`
- `0x180042b4c`
- `0x180042d08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180042a01`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180042a01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042a64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042a64`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042a7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a84`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall cdp::GetCallerUserContextToken(cdp *this, unsigned __int64 *a2)
{
  HRESULT CurrentUserContextToken; // eax
  int v4; // r9d
  unsigned int v5; // ecx
  unsigned __int64 *v6; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v10; // ecx
  int v11; // r9d
  signed int v12; // ebx
  unsigned __int64 *v13; // r8
  int UserManagerForUserContextToken; // eax
  int v15; // ecx
  int v16; // r9d
  _QWORD v17[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+18h] BYREF
  int v19; // [rsp+68h] [rbp+20h] BYREF
  int v20; // [rsp+70h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+30h] BYREF

  *(_QWORD *)this = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent(this, a2) )
  {
    CurrentUserContextToken = CoImpersonateClient();
    v5 = 0x80000000;
    v6 = (unsigned __int64 *)(CurrentUserContextToken + 0x80000000);
    if ( (int)v6 >= 0 && CurrentUserContextToken != -2147417833 )
    {
      v19 = 187;
LABEL_5:
      v18 = CurrentUserContextToken;
      Log<long &,char const (&)[20],int>(
        v5,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&v18,
        v4,
        (__int64)&v19);
      return v18;
    }
    if ( CurrentUserContextToken < 0 )
    {
      CurrentUserContextToken = cdp::GetCurrentUserContextToken(this, v6);
      if ( CurrentUserContextToken < 0 )
      {
        v19 = 212;
        goto LABEL_5;
      }
    }
    else
    {
      LOBYTE(v18) = 0;
      v17[0] = &v18;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v19 = v12;
        if ( v12 < 0 )
        {
          v20 = 204;
          Log<long &,char const (&)[20],int>(
            v10,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v19,
            v11,
            (__int64)&v20);
          v12 = v19;
        }
        ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___::_ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___(v17);
        goto LABEL_15;
      }
      ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___::_ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___(v17);
      UserManagerForUserContextToken = cdp::QueryUserManagerForUserContextToken((cdp *)TokenHandle, this, v13);
      if ( UserManagerForUserContextToken < 0 )
      {
        v19 = UserManagerForUserContextToken;
        v20 = 208;
        Log<long &,char const (&)[20],int>(
          v15,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
          (unsigned int)&v19,
          v16,
          (__int64)&v20);
        v12 = v19;
LABEL_15:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return (unsigned int)v12;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800429e0  push    rbp
0x1800429e2  push    rbx
0x1800429e3  mov     rbp, rsp
0x1800429e6  sub     rsp, 48h
0x1800429ea  mov     rbx, rcx
0x1800429ed  mov     qword ptr [rcx], 0
0x1800429f4  call    IsUMgrQueryUserContextPresent
0x1800429f9  test    al, al
0x1800429fb  jz      loc_180042B23
0x180042a01  call    cs:__imp_CoImpersonateClient
0x180042a07  mov     ecx, 80000000h
0x180042a0c  lea     edx, [rax+rcx]; unsigned __int64 *
0x180042a0f  test    ecx, edx
0x180042a11  jnz     short loc_180042A45
0x180042a13  cmp     eax, 80010117h
0x180042a18  jz      short loc_180042A45
0x180042a1a  mov     [rbp+arg_8], 0BBh
0x180042a21  mov     [rbp+arg_0], eax
0x180042a24  lea     rax, [rbp+arg_8]
0x180042a28  mov     [rsp+48h+var_28], rax
0x180042a2d  lea     r8, [rbp+arg_0]
0x180042a31  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042a38  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180042a3d  mov     eax, [rbp+arg_0]
0x180042a40  jmp     loc_180042B25
0x180042a45  shr     eax, 1Fh
0x180042a48  xor     al, 1
0x180042a4a  jz      loc_180042B2C
0x180042a50  mov     byte ptr [rbp+arg_0], 0
0x180042a54  lea     rax, [rbp+arg_0]
0x180042a58  mov     [rbp+var_18], rax
0x180042a5c  mov     [rbp+TokenHandle], 0
0x180042a64  call    cs:__imp_GetCurrentThread
0x180042a6a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180042a6e  mov     edx, 0Ch; DesiredAccess
0x180042a73  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180042a77  mov     rcx, rax; ThreadHandle
0x180042a7a  call    cs:__imp_OpenThreadToken
0x180042a80  test    eax, eax
0x180042a82  jnz     short loc_180042ACE
0x180042a84  call    cs:__imp_GetLastError
0x180042a8a  mov     ebx, eax
0x180042a8c  test    eax, eax
0x180042a8e  jle     short loc_180042A99
0x180042a90  movzx   ebx, ax
0x180042a93  or      ebx, 80070000h
0x180042a99  mov     [rbp+arg_8], ebx
0x180042a9c  test    ebx, ebx
0x180042a9e  jns     short loc_180042AC3
0x180042aa0  mov     [rbp+arg_10], 0CCh
0x180042aa7  lea     rax, [rbp+arg_10]
0x180042aab  mov     [rsp+48h+var_28], rax
0x180042ab0  lea     r8, [rbp+arg_8]
0x180042ab4  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042abb  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180042ac0  mov     ebx, [rbp+arg_8]
0x180042ac3  lea     rcx, [rbp+var_18]
0x180042ac7  call    ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680______ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___
0x180042acc  jmp     short loc_180042B0D
0x180042ace  lea     rcx, [rbp+var_18]
0x180042ad2  call    ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680______ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___
0x180042ad7  mov     rdx, rbx; void *
0x180042ada  mov     rcx, [rbp+TokenHandle]; this
0x180042ade  call    ?QueryUserManagerForUserContextToken@cdp@@YAJPEAXAEA_K@Z; cdp::QueryUserManagerForUserContextToken(void *,unsigned __int64 &)
0x180042ae3  test    eax, eax
0x180042ae5  jns     short loc_180042B1A
0x180042ae7  mov     [rbp+arg_8], eax
0x180042aea  mov     [rbp+arg_10], 0D0h
0x180042af1  lea     rax, [rbp+arg_10]
0x180042af5  mov     [rsp+48h+var_28], rax
0x180042afa  lea     r8, [rbp+arg_8]
0x180042afe  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042b05  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180042b0a  mov     ebx, [rbp+arg_8]
0x180042b0d  lea     rcx, [rbp+TokenHandle]
0x180042b11  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042b16  mov     eax, ebx
0x180042b18  jmp     short loc_180042B25
0x180042b1a  lea     rcx, [rbp+TokenHandle]
0x180042b1e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042b23  xor     eax, eax
0x180042b25  add     rsp, 48h
0x180042b29  pop     rbx
0x180042b2a  pop     rbp
0x180042b2b  retn
0x180042b2c  mov     rcx, rbx; this
0x180042b2f  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x180042b34  test    eax, eax
0x180042b36  jns     short loc_180042B23
0x180042b38  mov     [rbp+arg_8], 0D4h
0x180042b3f  jmp     loc_180042A21
```
