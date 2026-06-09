# PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)

- ea: `0x180031d24`
- end: `0x180031e68`
- name: `?ImpersonateActiveUser@UserImpersonationHelpers@PrintCore@@SAJXZ`
- size: `324`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003170c`
- `0x180031a9c`
- `0x1800348e8`

## callees

- `0x180006b48`
- `0x18001255c`
- `0x18001cf80`
- `0x18001d020`
- `0x18001d0a0`
- `0x180023264`
- `0x180031d24`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180031dce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180031dce`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180031d50`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180031d50`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180031dbf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180031dbf`

## string_xrefs

- `0x180031e1e`: `WTSQueryUserToken failed!`
- `0x180031dd9`: `Failed to impersonate the user!`
- `0x180031e49`: `Failed to find an active user to impersonate!`
- `0x180031d6a`: `OneCoreUap\Internal\Printscan\inc\userimpersonationhelpers.h`
- `0x180031de8`: `OneCoreUap\Internal\Printscan\inc\userimpersonationhelpers.h`
- `0x180031e25`: `OneCoreUap\Internal\Printscan\inc\userimpersonationhelpers.h`
- `0x180031e55`: `OneCoreUap\Internal\Printscan\inc\userimpersonationhelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)
{
  unsigned int v0; // eax
  __int64 v1; // rbx
  unsigned int v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  __int64 i; // rcx
  unsigned int v6; // eax
  char *v7; // [rsp+20h] [rbp-18h]
  const char *v8; // [rsp+28h] [rbp-10h]
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD v11; // [rsp+40h] [rbp+8h] BYREF
  void *phToken; // [rsp+48h] [rbp+10h] BYREF
  PWTS_SESSION_INFOW v13; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  v11 = 0;
  v0 = WTSEnumerateSessionsW(0, 0, 1u, &v13, &v11);
  try
  {
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x83,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\userimpersonationhelpers.h",
      (const char *)v0,
      (int)"Enumerate sessions failed!",
      v8);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v11 )
      {
        v6 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x9D,
          (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\userimpersonationhelpers.h",
          (const char *)v6,
          (int)"Failed to find an active user to impersonate!",
          v9);
      }
      v1 = i;
      if ( v13[i].SessionId )
      {
        if ( v13[i].State == WTSActive )
          break;
      }
    }
    phToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phToken,
      0);
    if ( !WTSQueryUserToken(v13[v1].SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x96,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\userimpersonationhelpers.h",
        "WTSQueryUserToken failed!",
        v7);
    v2 = ImpersonateLoggedOnUser(phToken);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x91,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\userimpersonationhelpers.h",
      (const char *)v2,
      (int)"Failed to impersonate the user!",
      v9);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA2,
                           (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\userimpersonationhelpers.h",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180031d24  mov     r11, rsp
0x180031d27  push    rbx
0x180031d28  sub     rsp, 30h
0x180031d2c  mov     qword ptr [r11+18h], 0
0x180031d34  mov     [rsp+38h+arg_0], 0
0x180031d3c  lea     rax, [r11+8]
0x180031d40  mov     [r11-18h], rax
0x180031d44  lea     r9, [r11+18h]; ppSessionInfo
0x180031d48  xor     edx, edx; Reserved
0x180031d4a  xor     ecx, ecx; hServer
0x180031d4c  lea     r8d, [rdx+1]; Version
0x180031d50  call    cs:__imp_WTSEnumerateSessionsW
0x180031d56  mov     rcx, [rsp+38h]; this
0x180031d5b  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x180031d62  mov     [rsp+38h+var_18], rdx; char *
0x180031d67  mov     r9d, eax; char *
0x180031d6a  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180031d71  mov     edx, 83h; void *
0x180031d76  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180031d7b  xor     ecx, ecx
0x180031d7d  mov     rdx, [rsp+38h+arg_10]
0x180031d82  cmp     ecx, [rsp+38h+arg_0]
0x180031d86  jnb     loc_180031E37
0x180031d8c  lea     rbx, [rcx+rcx*2]
0x180031d90  cmp     dword ptr [rdx+rbx*8], 0
0x180031d94  jz      short loc_180031E08
0x180031d96  cmp     dword ptr [rdx+rbx*8+10h], 0
0x180031d9b  jnz     short loc_180031E08
0x180031d9d  mov     [rsp+38h+phToken], 0
0x180031da6  xor     edx, edx
0x180031da8  lea     rcx, [rsp+38h+phToken]
0x180031dad  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180031db2  lea     rdx, [rsp+38h+phToken]; phToken
0x180031db7  mov     rcx, [rsp+38h+arg_10]
0x180031dbc  mov     ecx, [rcx+rbx*8]; SessionId
0x180031dbf  call    cs:__imp_WTSQueryUserToken
0x180031dc5  test    eax, eax
0x180031dc7  jz      short loc_180031E19
0x180031dc9  mov     rcx, [rsp+38h+phToken]; hToken
0x180031dce  call    cs:__imp_ImpersonateLoggedOnUser
0x180031dd4  mov     rcx, [rsp+38h]; this
0x180031dd9  lea     rdx, aFailedToImpers; "Failed to impersonate the user!"
0x180031de0  mov     [rsp+38h+var_18], rdx; int
0x180031de5  mov     r9d, eax; char *
0x180031de8  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180031def  mov     edx, 91h; void *
0x180031df4  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180031df9  nop
0x180031dfa  lea     rcx, [rsp+38h+phToken]
0x180031dff  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031e04  xor     eax, eax
0x180031e06  jmp     short loc_180031E13
0x180031e08  inc     ecx
0x180031e0a  jmp     loc_180031D82
0x180031e0f  mov     eax, [rsp+38h+arg_0]
0x180031e13  add     rsp, 30h
0x180031e17  pop     rbx
0x180031e18  retn
0x180031e19  mov     rcx, [rsp+38h]; this
0x180031e1e  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x180031e25  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180031e2c  mov     edx, 96h; void *
0x180031e31  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180031e37  mov     ecx, 80070057h
0x180031e3c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180031e41  mov     r9d, eax; char *
0x180031e44  mov     rcx, [rsp+38h]; this
0x180031e49  lea     rax, aFailedToFindAn; "Failed to find an active user to impers"...
0x180031e50  mov     [rsp+38h+var_18], rax; int
0x180031e55  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Printscan\\inc\\u"...
0x180031e5c  mov     edx, 9Dh; void *
0x180031e61  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
