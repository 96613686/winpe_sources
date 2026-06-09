# PrintCore::UserImpersonationHelpers::ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800291d0`
- end: `0x1800293f3`
- name: `?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027f60`
- `0x180030cb0`
- `0x180030df0`
- `0x180031a9c`
- `0x1800348e8`
- `0x180036834`

## callees

- `0x180002d40`
- `0x180006b48`
- `0x18000f8a8`
- `0x18001255c`
- `0x18001c5dc`
- `0x18001cf80`
- `0x18001d020`
- `0x18001d058`
- `0x18001d0a0`
- `0x180023264`
- `0x180028758`
- `0x1800291d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292b1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029323`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029323`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002921c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18002921c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180029296`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180029296`

## string_xrefs

- `0x180029239`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x1800293ae`: `WTSQueryUserToken failed!`
- `0x180029331`: `Failed to impersonate the user!`
- `0x1800293d8`: `Failed to find the user to impersonate!`
- `0x1800292f1`: `Failed to get the SID attached to the token!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::UserImpersonationHelpers::ImpersonateUser(__int64 a1)
{
  unsigned int v2; // eax
  __m128i si128; // xmm6
  unsigned int UserSidFromToken; // eax
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rbx
  const char *v9; // r9
  DWORD *pCount; // [rsp+20h] [rbp-88h]
  const char *v11; // [rsp+28h] [rbp-80h]
  const char *v12; // [rsp+28h] [rbp-80h]
  DWORD v13; // [rsp+30h] [rbp-78h] BYREF
  void *phToken; // [rsp+38h] [rbp-70h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-68h] BYREF
  _OWORD v16[2]; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  ppSessionInfo = 0;
  v13 = 0;
  v2 = WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v13);
  try
  {
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
      (const char *)v2,
      (int)"Enumerate sessions failed!",
      v11);
    v8 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( (unsigned int)v8 >= v13 )
      {
        v9 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x50,
          (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
          v9,
          (int)"Failed to find the user to impersonate!",
          v12);
      }
      if ( ppSessionInfo[v8].SessionId )
      {
        phToken = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &phToken,
          0);
        if ( WTSQueryUserToken(ppSessionInfo[v8].SessionId, &phToken) )
        {
          v16[0] = 0;
          v16[1] = si128;
          LOWORD(v16[0]) = 0;
          UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(phToken);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x40,
            (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
            (const char *)UserSidFromToken,
            (int)"Failed to get the SID attached to the token!",
            v12);
          if ( (unsigned __int8)PrintCore::StringHelpers::IEquals(a1, v16) )
          {
            v5 = ImpersonateLoggedOnUser(phToken);
            wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
              retaddr,
              (void *)0x48,
              (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
              (const char *)v5,
              (int)"Failed to impersonate the user!",
              v12);
            std::wstring::_Tidy_deallocate(v16);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
            return 0;
          }
          std::wstring::_Tidy_deallocate(v16);
        }
        else if ( GetLastError() != 1008 && GetLastError() != 2 )
        {
          wil::details::in1diag3::Throw_GetLastErrorMsg(
            retaddr,
            (void *)0x3A,
            (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
            "WTSQueryUserToken failed!",
            (const char *)pCount);
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
      }
      v8 = (unsigned int)(v8 + 1);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800291d0  push    rbx
0x1800291d2  push    rsi
0x1800291d3  push    rdi
0x1800291d4  push    r15
0x1800291d6  sub     rsp, 88h
0x1800291dd  movaps  [rsp+0A8h+var_38], xmm6
0x1800291e2  mov     rax, cs:__security_cookie
0x1800291e9  xor     rax, rsp
0x1800291ec  mov     [rsp+0A8h+var_40], rax
0x1800291f1  mov     rsi, rcx
0x1800291f4  mov     [rsp+0A8h+ppSessionInfo], 0
0x1800291fd  mov     [rsp+0A8h+var_78], 0
0x180029205  lea     rax, [rsp+0A8h+var_78]
0x18002920a  mov     [rsp+0A8h+pCount], rax; pCount
0x18002920f  lea     r9, [rsp+0A8h+ppSessionInfo]; ppSessionInfo
0x180029214  xor     edx, edx; Reserved
0x180029216  xor     ecx, ecx; hServer
0x180029218  lea     r8d, [rdx+1]; Version
0x18002921c  call    cs:__imp_WTSEnumerateSessionsW
0x180029222  mov     rcx, [rsp+0A8h]; this
0x18002922a  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x180029231  mov     [rsp+0A8h+pCount], rdx; char *
0x180029236  mov     r9d, eax; char *
0x180029239  lea     r15, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x180029240  mov     r8, r15; unsigned int
0x180029243  mov     edx, 27h ; '''; void *
0x180029248  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002924d  xor     ebx, ebx
0x18002924f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180029257  cmp     ebx, [rsp+0A8h+var_78]
0x18002925b  jnb     loc_1800293C3
0x180029261  lea     rdi, [rbx+rbx*2]
0x180029265  mov     rax, [rsp+0A8h+ppSessionInfo]
0x18002926a  cmp     dword ptr [rax+rdi*8], 0
0x18002926e  jz      loc_18002937C
0x180029274  mov     [rsp+0A8h+phToken], 0
0x18002927d  xor     edx, edx
0x18002927f  lea     rcx, [rsp+0A8h+phToken]
0x180029284  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180029289  lea     rdx, [rsp+0A8h+phToken]; phToken
0x18002928e  mov     rcx, [rsp+0A8h+ppSessionInfo]
0x180029293  mov     ecx, [rcx+rdi*8]; SessionId
0x180029296  call    cs:__imp_WTSQueryUserToken
0x18002929c  test    eax, eax
0x18002929e  jnz     short loc_1800292C5
0x1800292a0  call    cs:__imp_GetLastError
0x1800292a6  cmp     eax, 3F0h
0x1800292ab  jz      loc_180029372
0x1800292b1  call    cs:__imp_GetLastError
0x1800292b7  cmp     eax, 2
0x1800292ba  jnz     loc_1800293A6
0x1800292c0  jmp     loc_180029372
0x1800292c5  xorps   xmm0, xmm0
0x1800292c8  movups  [rsp+0A8h+var_60], xmm0
0x1800292cd  movdqu  [rsp+0A8h+var_50], xmm6
0x1800292d3  xor     eax, eax
0x1800292d5  mov     word ptr [rsp+0A8h+var_60], ax
0x1800292da  lea     rdx, [rsp+0A8h+var_60]
0x1800292df  mov     rcx, [rsp+0A8h+phToken]; TokenHandle
0x1800292e4  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x1800292e9  mov     rcx, [rsp+0A8h]; this
0x1800292f1  lea     rdx, aFailedToGetThe_3; "Failed to get the SID attached to the t"...
0x1800292f8  mov     [rsp+0A8h+pCount], rdx; int
0x1800292fd  mov     r9d, eax; char *
0x180029300  mov     r8, r15; unsigned int
0x180029303  mov     edx, 40h ; '@'; void *
0x180029308  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002930d  lea     rdx, [rsp+0A8h+var_60]
0x180029312  mov     rcx, rsi
0x180029315  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x18002931a  test    al, al
0x18002931c  jz      short loc_180029367
0x18002931e  mov     rcx, [rsp+0A8h+phToken]; hToken
0x180029323  call    cs:__imp_ImpersonateLoggedOnUser
0x180029329  mov     rcx, [rsp+0A8h]; this
0x180029331  lea     rdx, aFailedToImpers; "Failed to impersonate the user!"
0x180029338  mov     [rsp+0A8h+pCount], rdx; int
0x18002933d  mov     r9d, eax; char *
0x180029340  mov     r8, r15; unsigned int
0x180029343  mov     edx, 48h ; 'H'; void *
0x180029348  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002934d  nop
0x18002934e  lea     rcx, [rsp+0A8h+var_60]
0x180029353  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029358  nop
0x180029359  lea     rcx, [rsp+0A8h+phToken]
0x18002935e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029363  xor     eax, eax
0x180029365  jmp     short loc_180029387
0x180029367  lea     rcx, [rsp+0A8h+var_60]
0x18002936c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029371  nop
0x180029372  lea     rcx, [rsp+0A8h+phToken]
0x180029377  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002937c  inc     ebx
0x18002937e  jmp     loc_180029257
0x180029383  mov     eax, [rsp+0A8h+var_78]
0x180029387  mov     rcx, [rsp+0A8h+var_40]
0x18002938c  xor     rcx, rsp; StackCookie
0x18002938f  call    __security_check_cookie
0x180029394  movaps  xmm6, [rsp+0A8h+var_38]
0x180029399  add     rsp, 88h
0x1800293a0  pop     r15
0x1800293a2  pop     rdi
0x1800293a3  pop     rsi
0x1800293a4  pop     rbx
0x1800293a5  retn
0x1800293a6  mov     rcx, [rsp+0A8h]; this
0x1800293ae  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x1800293b5  mov     r8, r15; unsigned int
0x1800293b8  mov     edx, 3Ah ; ':'; void *
0x1800293bd  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800293c3  mov     ecx, 80070057h
0x1800293c8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800293cd  mov     r9d, eax; char *
0x1800293d0  mov     rcx, [rsp+0A8h]; this
0x1800293d8  lea     rax, aFailedToFindTh_0; "Failed to find the user to impersonate!"
0x1800293df  mov     [rsp+0A8h+pCount], rax; int
0x1800293e4  mov     r8, r15; unsigned int
0x1800293e7  mov     edx, 50h ; 'P'; void *
0x1800293ec  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
