# PrintCore::UserImpersonationHelpers::ImpersonateUser(ulong)

- ea: `0x18001c60c`
- end: `0x18001c6d1`
- name: `?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJK@Z`
- size: `197`
- prototype: `__int64 __fastcall(ULONG SessionId)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022b44`
- `0x180031a9c`

## callees

- `0x18001255c`
- `0x18001c60c`
- `0x18001cf80`
- `0x18001cfd4`
- `0x18001d0a0`
- `0x180023264`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c670`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c670`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001c661`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001c661`

## string_xrefs

- `0x18001c634`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x18001c68a`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x18001c6c0`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x18001c6b9`: `WTSQueryUserToken failed!`
- `0x18001c67b`: `Failed to impersonate the user!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintCore::UserImpersonationHelpers::ImpersonateUser(ULONG SessionId)
{
  unsigned int v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  char *v5; // [rsp+20h] [rbp-18h]
  char *v6; // [rsp+28h] [rbp-10h]
  const char *v7; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *phToken; // [rsp+48h] [rbp+10h] BYREF

  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x64,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
      (const char *)0x80070057LL,
      SessionId == 0,
      (bool)"Invalid session ID!",
      v7);
    phToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phToken,
      0);
    if ( !WTSQueryUserToken(SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x69,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
        "WTSQueryUserToken failed!",
        v5);
    v2 = ImpersonateLoggedOnUser(phToken);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x6D,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
      (const char *)v2,
      (int)"Failed to impersonate the user!",
      v6);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x71,
                           (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001c60c  push    rbx; char *
0x18001c60e  sub     rsp, 30h
0x18001c612  mov     ebx, ecx
0x18001c614  test    ecx, ecx
0x18001c616  setz    al
0x18001c619  mov     rcx, [rsp+38h]; this
0x18001c61e  lea     rdx, aInvalidSession; "Invalid session ID!"
0x18001c625  mov     [rsp+38h+var_10], rdx; char *
0x18001c62a  mov     byte ptr [rsp+38h+var_18], al; char *
0x18001c62e  mov     r9d, 80070057h; char *
0x18001c634  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x18001c63b  mov     edx, 64h ; 'd'; void *
0x18001c640  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001c645  mov     [rsp+38h+phToken], 0
0x18001c64e  xor     edx, edx
0x18001c650  lea     rcx, [rsp+38h+phToken]
0x18001c655  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001c65a  lea     rdx, [rsp+38h+phToken]; phToken
0x18001c65f  mov     ecx, ebx; SessionId
0x18001c661  call    cs:__imp_WTSQueryUserToken
0x18001c667  test    eax, eax
0x18001c669  jz      short loc_18001C6B4
0x18001c66b  mov     rcx, [rsp+38h+phToken]; hToken
0x18001c670  call    cs:__imp_ImpersonateLoggedOnUser
0x18001c676  mov     rcx, [rsp+38h]; this
0x18001c67b  lea     rdx, aFailedToImpers; "Failed to impersonate the user!"
0x18001c682  mov     [rsp+38h+var_18], rdx; int
0x18001c687  mov     r9d, eax; char *
0x18001c68a  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x18001c691  mov     edx, 6Dh ; 'm'; void *
0x18001c696  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001c69b  nop
0x18001c69c  lea     rcx, [rsp+38h+phToken]
0x18001c6a1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c6a6  xor     eax, eax
0x18001c6a8  jmp     short loc_18001C6AE
0x18001c6aa  mov     eax, [rsp+38h+arg_0]
0x18001c6ae  add     rsp, 30h
0x18001c6b2  pop     rbx
0x18001c6b3  retn
0x18001c6b4  mov     rcx, [rsp+38h]; this
0x18001c6b9  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x18001c6c0  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x18001c6c7  lea     edx, [rax+69h]; void *
0x18001c6ca  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
