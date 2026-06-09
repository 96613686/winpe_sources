# PrintCore::UserImpersonationHelpers::ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800454d4`
- end: `0x180045727`
- name: `?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180045194`

## callees

- `0x1800032e0`
- `0x180005f6c`
- `0x18000f590`
- `0x180044cf4`
- `0x1800454d4`
- `0x18004a5c8`
- `0x18004a650`
- `0x18004a688`
- `0x18004a6d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045629`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045629`
- `KERNEL32!CloseHandle` at `0x18004567d`
- `KERNEL32!CloseHandle` at `0x1800456a1`
- `KERNEL32!CloseHandle` at `0x18004567d`
- `KERNEL32!CloseHandle` at `0x1800456a1`
- `KERNEL32!GetLastError` at `0x18004559c`
- `KERNEL32!GetLastError` at `0x1800455ad`
- `KERNEL32!GetLastError` at `0x18004559c`
- `KERNEL32!GetLastError` at `0x1800455ad`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180045638`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180045638`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004552b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004552b`
- `WTSAPI32!WTSQueryUserToken` at `0x180045592`
- `WTSAPI32!WTSQueryUserToken` at `0x180045592`

## string_xrefs

- `0x180045646`: `Failed to impersonate the user!`
- `0x1800455ed`: `Failed to get the SID attached to the token!`
- `0x1800456e2`: `WTSQueryUserToken failed!`
- `0x180045548`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x18004570c`: `Failed to find the user to impersonate!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::UserImpersonationHelpers::ImpersonateUser(_QWORD *a1)
{
  unsigned int v2; // eax
  __m128i si128; // xmm6
  DWORD SessionId; // ecx
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int UserSidFromToken; // eax
  __int128 *v8; // rdx
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  const char *v11; // r9
  __int64 result; // rax
  __int64 v13; // rbx
  const char *v14; // r9
  char *v15; // [rsp+20h] [rbp-78h]
  const char *v16; // [rsp+28h] [rbp-70h]
  const char *v17; // [rsp+28h] [rbp-70h]
  DWORD v18; // [rsp+30h] [rbp-68h] BYREF
  HANDLE phToken; // [rsp+38h] [rbp-60h] BYREF
  PWTS_SESSION_INFOW v20[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v21; // [rsp+50h] [rbp-48h] BYREF
  __m128i v22; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v20[1] = (PWTS_SESSION_INFOW)-2LL;
  v20[0] = 0;
  v18 = 0;
  v2 = WTSEnumerateSessionsW(0, 0, 1u, v20, &v18);
  try
  {
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)v2,
      (__int64)"Enumerate sessions failed!",
      v16);
    v13 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( (unsigned int)v13 >= v18 )
      {
        v14 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL, v5, v6);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x50,
          (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          v14,
          (int)"Failed to find the user to impersonate!",
          v17);
      }
      SessionId = v20[0][v13].SessionId;
      if ( SessionId )
        break;
LABEL_20:
      v13 = (unsigned int)(v13 + 1);
    }
    phToken = 0;
    if ( !WTSQueryUserToken(SessionId, &phToken) )
    {
      if ( GetLastError() != 1008 && GetLastError() != 2 )
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x3A,
          (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          "WTSQueryUserToken failed!",
          v15);
      goto LABEL_18;
    }
    v21 = 0;
    v22 = si128;
    LOWORD(v21) = 0;
    UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(phToken, &v21);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x40,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)UserSidFromToken,
      (int)"Failed to get the SID attached to the token!",
      v17);
    v8 = &v21;
    if ( v22.m128i_i64[1] > 7uLL )
      v8 = (__int128 *)v21;
    if ( a1[3] <= 7u )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    if ( (unsigned int)_o__wcsicmp(v9, v8) )
    {
      std::wstring::~wstring(&v21);
LABEL_18:
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      goto LABEL_20;
    }
    v10 = ImpersonateLoggedOnUser(phToken);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x48,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)v10,
      (__int64)"Failed to impersonate the user!",
      v17);
    std::wstring::~wstring(&v21);
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800454d4  mov     r11, rsp
0x1800454d7  push    r14
0x1800454d9  sub     rsp, 90h
0x1800454e0  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x1800454e8  mov     [r11+10h], rbx
0x1800454ec  mov     [r11+18h], rdi
0x1800454f0  movaps  xmmword ptr [r11-18h], xmm6
0x1800454f5  mov     rax, cs:__security_cookie
0x1800454fc  xor     rax, rsp
0x1800454ff  mov     [rsp+98h+var_28], rax
0x180045504  mov     rdi, rcx
0x180045507  mov     qword ptr [r11-58h], 0
0x18004550f  mov     [rsp+98h+var_68], 0
0x180045517  lea     rax, [r11-68h]
0x18004551b  mov     [r11-78h], rax
0x18004551f  lea     r9, [r11-58h]; ppSessionInfo
0x180045523  xor     edx, edx; Reserved
0x180045525  xor     ecx, ecx; hServer
0x180045527  lea     r8d, [rdx+1]; Version
0x18004552b  call    cs:__imp_WTSEnumerateSessionsW
0x180045531  mov     rcx, [rsp+98h]; this
0x180045539  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x180045540  mov     [rsp+98h+var_78], rdx; char *
0x180045545  mov     r9d, eax; char *
0x180045548  lea     r14, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x18004554f  mov     r8, r14; unsigned int
0x180045552  mov     edx, 27h ; '''; void *
0x180045557  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18004555c  xor     ebx, ebx
0x18004555e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180045566  cmp     ebx, [rsp+98h+var_68]
0x18004556a  jnb     loc_1800456F7
0x180045570  lea     rcx, [rbx+rbx*2]
0x180045574  mov     rax, [rsp+98h+var_58]
0x180045579  mov     ecx, [rax+rcx*8]; SessionId
0x18004557c  test    ecx, ecx
0x18004557e  jz      loc_1800456A7
0x180045584  mov     [rsp+98h+phToken], 0
0x18004558d  lea     rdx, [rsp+98h+phToken]; phToken
0x180045592  call    cs:__imp_WTSQueryUserToken
0x180045598  test    eax, eax
0x18004559a  jnz     short loc_1800455C1
0x18004559c  call    cs:__imp_GetLastError
0x1800455a2  cmp     eax, 3F0h
0x1800455a7  jz      loc_180045692
0x1800455ad  call    cs:__imp_GetLastError
0x1800455b3  cmp     eax, 2
0x1800455b6  jnz     loc_1800456DA
0x1800455bc  jmp     loc_180045692
0x1800455c1  xorps   xmm0, xmm0
0x1800455c4  movups  [rsp+98h+var_48], xmm0
0x1800455c9  movdqu  [rsp+98h+var_38], xmm6
0x1800455cf  xor     eax, eax
0x1800455d1  mov     word ptr [rsp+98h+var_48], ax
0x1800455d6  lea     rdx, [rsp+98h+var_48]; void *
0x1800455db  mov     rcx, [rsp+98h+phToken]; TokenHandle
0x1800455e0  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x1800455e5  mov     rcx, [rsp+98h]; this
0x1800455ed  lea     rdx, aFailedToGetThe; "Failed to get the SID attached to the t"...
0x1800455f4  mov     [rsp+98h+var_78], rdx; int
0x1800455f9  mov     r9d, eax; char *
0x1800455fc  mov     r8, r14; unsigned int
0x1800455ff  mov     edx, 40h ; '@'; void *
0x180045604  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180045609  lea     rdx, [rsp+98h+var_48]
0x18004560e  cmp     qword ptr [rsp+98h+var_38+8], 7
0x180045614  cmova   rdx, qword ptr [rsp+98h+var_48]
0x18004561a  cmp     qword ptr [rdi+18h], 7
0x18004561f  jbe     short loc_180045626
0x180045621  mov     rcx, [rdi]
0x180045624  jmp     short loc_180045629
0x180045626  mov     rcx, rdi
0x180045629  call    cs:__imp__o__wcsicmp
0x18004562f  test    eax, eax
0x180045631  jnz     short loc_180045687
0x180045633  mov     rcx, [rsp+98h+phToken]; hToken
0x180045638  call    cs:__imp_ImpersonateLoggedOnUser
0x18004563e  mov     rcx, [rsp+98h]; this
0x180045646  lea     rdx, aFailedToImpers; "Failed to impersonate the user!"
0x18004564d  mov     [rsp+98h+var_78], rdx; __int64
0x180045652  mov     r9d, eax; char *
0x180045655  mov     r8, r14; unsigned int
0x180045658  mov     edx, 48h ; 'H'; void *
0x18004565d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180045662  nop
0x180045663  lea     rcx, [rsp+98h+var_48]
0x180045668  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004566d  nop
0x18004566e  mov     rcx, [rsp+98h+phToken]; hObject
0x180045673  lea     rax, [rcx-1]
0x180045677  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004567b  ja      short loc_180045683
0x18004567d  call    cs:__imp_CloseHandle
0x180045683  xor     eax, eax
0x180045685  jmp     short loc_1800456B2
0x180045687  lea     rcx, [rsp+98h+var_48]
0x18004568c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045691  nop
0x180045692  mov     rcx, [rsp+98h+phToken]; hObject
0x180045697  lea     rax, [rcx-1]
0x18004569b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004569f  ja      short loc_1800456A7
0x1800456a1  call    cs:__imp_CloseHandle
0x1800456a7  inc     ebx
0x1800456a9  jmp     loc_180045566
0x1800456ae  mov     eax, [rsp+98h+var_68]
0x1800456b2  mov     rcx, [rsp+98h+var_28]
0x1800456b7  xor     rcx, rsp; StackCookie
0x1800456ba  call    __security_check_cookie
0x1800456bf  lea     r11, [rsp+98h+var_8]
0x1800456c7  mov     rbx, [r11+18h]
0x1800456cb  mov     rdi, [r11+20h]
0x1800456cf  movaps  xmm6, xmmword ptr [r11-10h]
0x1800456d4  mov     rsp, r11
0x1800456d7  pop     r14
0x1800456d9  retn
0x1800456da  mov     rcx, [rsp+98h]; this
0x1800456e2  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x1800456e9  mov     r8, r14; unsigned int
0x1800456ec  mov     edx, 3Ah ; ':'; void *
0x1800456f1  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800456f7  mov     ecx, 80070057h
0x1800456fc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180045701  mov     r9d, eax; char *
0x180045704  mov     rcx, [rsp+98h]; this
0x18004570c  lea     rax, aFailedToFindTh; "Failed to find the user to impersonate!"
0x180045713  mov     [rsp+98h+var_78], rax; int
0x180045718  mov     r8, r14; unsigned int
0x18004571b  mov     edx, 50h ; 'P'; void *
0x180045720  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
