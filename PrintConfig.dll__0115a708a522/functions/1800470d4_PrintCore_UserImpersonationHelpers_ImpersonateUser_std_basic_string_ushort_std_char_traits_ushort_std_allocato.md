# PrintCore::UserImpersonationHelpers::ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800470d4`
- end: `0x180047358`
- name: `?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180046d80`

## callees

- `0x180003400`
- `0x1800060e8`
- `0x18000fa4c`
- `0x18004686c`
- `0x1800470d4`
- `0x18004c4b4`
- `0x18004c53c`
- `0x18004c574`
- `0x18004c5c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047241`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047241`
- `KERNEL32!CloseHandle` at `0x1800472a1`
- `KERNEL32!CloseHandle` at `0x1800472cb`
- `KERNEL32!CloseHandle` at `0x1800472a1`
- `KERNEL32!CloseHandle` at `0x1800472cb`
- `KERNEL32!GetLastError` at `0x1800471a8`
- `KERNEL32!GetLastError` at `0x1800471bf`
- `KERNEL32!GetLastError` at `0x1800471a8`
- `KERNEL32!GetLastError` at `0x1800471bf`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180047256`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180047256`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004712b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004712b`
- `WTSAPI32!WTSQueryUserToken` at `0x180047198`
- `WTSAPI32!WTSQueryUserToken` at `0x180047198`

## string_xrefs

- `0x18004726a`: `Failed to impersonate the user!`
- `0x180047205`: `Failed to get the SID attached to the token!`
- `0x180047313`: `WTSQueryUserToken failed!`
- `0x18004714e`: `OneCoreUap\Internal\PrintScan\inc\UserImpersonationHelpers.h`
- `0x18004733d`: `Failed to find the user to impersonate!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::UserImpersonationHelpers::ImpersonateUser(_QWORD *a1)
{
  unsigned int v2; // eax
  __m128i si128; // xmm6
  DWORD SessionId; // ecx
  unsigned int UserSidFromToken; // eax
  __int128 *v6; // rdx
  _QWORD *v7; // rcx
  unsigned int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  __int64 v11; // rbx
  const char *v12; // r9
  char *v13; // [rsp+20h] [rbp-78h]
  const char *v14; // [rsp+28h] [rbp-70h]
  const char *v15; // [rsp+28h] [rbp-70h]
  DWORD v16; // [rsp+30h] [rbp-68h] BYREF
  HANDLE phToken; // [rsp+38h] [rbp-60h] BYREF
  PWTS_SESSION_INFOW v18[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v19; // [rsp+50h] [rbp-48h] BYREF
  __m128i v20; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v18[1] = (PWTS_SESSION_INFOW)-2LL;
  v18[0] = 0;
  v16 = 0;
  v2 = WTSEnumerateSessionsW(0, 0, 1u, v18, &v16);
  try
  {
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)v2,
      (void *)"Enumerate sessions failed!",
      v14);
    v11 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( (unsigned int)v11 >= v16 )
      {
        v12 = (const char *)(unsigned int)wil::verify_hresult<long>(0x80070057);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          80,
          (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          v12,
          (unsigned __int64)"Failed to find the user to impersonate!",
          v15);
      }
      SessionId = v18[0][v11].SessionId;
      if ( SessionId )
        break;
LABEL_20:
      v11 = (unsigned int)(v11 + 1);
    }
    phToken = 0;
    if ( !WTSQueryUserToken(SessionId, &phToken) )
    {
      if ( GetLastError() != 1008 && GetLastError() != 2 )
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x3A,
          (__int64)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
          "WTSQueryUserToken failed!",
          v13);
      goto LABEL_18;
    }
    v19 = 0;
    v20 = si128;
    LOWORD(v19) = 0;
    UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(phToken, &v19);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x40,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)UserSidFromToken,
      (int)"Failed to get the SID attached to the token!",
      v15);
    v6 = &v19;
    if ( v20.m128i_i64[1] > 7uLL )
      v6 = (__int128 *)v19;
    if ( a1[3] <= 7u )
      v7 = a1;
    else
      v7 = (_QWORD *)*a1;
    if ( (unsigned int)_o__wcsicmp(v7, v6) )
    {
      std::wstring::~wstring((char **)&v19);
LABEL_18:
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      goto LABEL_20;
    }
    v8 = ImpersonateLoggedOnUser(phToken);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x48,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
      (const char *)v8,
      (void *)"Failed to impersonate the user!",
      v15);
    std::wstring::~wstring((char **)&v19);
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (int)"OneCoreUap\\Internal\\PrintScan\\inc\\UserImpersonationHelpers.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800470d4  mov     r11, rsp
0x1800470d7  push    r14
0x1800470d9  sub     rsp, 90h
0x1800470e0  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x1800470e8  mov     [r11+10h], rbx
0x1800470ec  mov     [r11+18h], rdi
0x1800470f0  movaps  xmmword ptr [r11-18h], xmm6
0x1800470f5  mov     rax, cs:__security_cookie
0x1800470fc  xor     rax, rsp
0x1800470ff  mov     [rsp+98h+var_28], rax
0x180047104  mov     rdi, rcx
0x180047107  mov     qword ptr [r11-58h], 0
0x18004710f  mov     [rsp+98h+var_68], 0
0x180047117  lea     rax, [r11-68h]
0x18004711b  mov     [r11-78h], rax
0x18004711f  lea     r9, [r11-58h]; ppSessionInfo
0x180047123  xor     edx, edx; Reserved
0x180047125  xor     ecx, ecx; hServer
0x180047127  lea     r8d, [rdx+1]; Version
0x18004712b  call    cs:__imp_WTSEnumerateSessionsW
0x180047132  nop     dword ptr [rax+rax+00h]
0x180047137  mov     rcx, [rsp+98h]; this
0x18004713f  lea     rdx, aEnumerateSessi; "Enumerate sessions failed!"
0x180047146  mov     [rsp+98h+var_78], rdx; char *
0x18004714b  mov     r9d, eax; char *
0x18004714e  lea     r14, aOnecoreuapInte_0; "OneCoreUap\\Internal\\PrintScan\\inc\\U"...
0x180047155  mov     r8, r14; unsigned int
0x180047158  mov     edx, 27h ; '''; void *
0x18004715d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180047162  xor     ebx, ebx
0x180047164  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004716c  cmp     ebx, [rsp+98h+var_68]
0x180047170  jnb     loc_180047328
0x180047176  lea     rcx, [rbx+rbx*2]
0x18004717a  mov     rax, [rsp+98h+var_58]
0x18004717f  mov     ecx, [rax+rcx*8]; SessionId
0x180047182  test    ecx, ecx
0x180047184  jz      loc_1800472D7
0x18004718a  mov     [rsp+98h+phToken], 0
0x180047193  lea     rdx, [rsp+98h+phToken]; phToken
0x180047198  call    cs:__imp_WTSQueryUserToken
0x18004719f  nop     dword ptr [rax+rax+00h]
0x1800471a4  test    eax, eax
0x1800471a6  jnz     short loc_1800471D9
0x1800471a8  call    cs:__imp_GetLastError
0x1800471af  nop     dword ptr [rax+rax+00h]
0x1800471b4  cmp     eax, 3F0h
0x1800471b9  jz      loc_1800472BC
0x1800471bf  call    cs:__imp_GetLastError
0x1800471c6  nop     dword ptr [rax+rax+00h]
0x1800471cb  cmp     eax, 2
0x1800471ce  jnz     loc_18004730B
0x1800471d4  jmp     loc_1800472BC
0x1800471d9  xorps   xmm0, xmm0
0x1800471dc  movups  [rsp+98h+var_48], xmm0
0x1800471e1  movdqu  [rsp+98h+var_38], xmm6
0x1800471e7  xor     eax, eax
0x1800471e9  mov     word ptr [rsp+98h+var_48], ax
0x1800471ee  lea     rdx, [rsp+98h+var_48]; void *
0x1800471f3  mov     rcx, [rsp+98h+phToken]; TokenHandle
0x1800471f8  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x1800471fd  mov     rcx, [rsp+98h]; this
0x180047205  lea     rdx, aFailedToGetThe; "Failed to get the SID attached to the t"...
0x18004720c  mov     [rsp+98h+var_78], rdx; int
0x180047211  mov     r9d, eax; char *
0x180047214  mov     r8, r14; unsigned int
0x180047217  mov     edx, 40h ; '@'; void *
0x18004721c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180047221  lea     rdx, [rsp+98h+var_48]
0x180047226  cmp     qword ptr [rsp+98h+var_38+8], 7
0x18004722c  cmova   rdx, qword ptr [rsp+98h+var_48]
0x180047232  cmp     qword ptr [rdi+18h], 7
0x180047237  jbe     short loc_18004723E
0x180047239  mov     rcx, [rdi]
0x18004723c  jmp     short loc_180047241
0x18004723e  mov     rcx, rdi
0x180047241  call    cs:__imp__o__wcsicmp
0x180047248  nop     dword ptr [rax+rax+00h]
0x18004724d  test    eax, eax
0x18004724f  jnz     short loc_1800472B1
0x180047251  mov     rcx, [rsp+98h+phToken]; hToken
0x180047256  call    cs:__imp_ImpersonateLoggedOnUser
0x18004725d  nop     dword ptr [rax+rax+00h]
0x180047262  mov     rcx, [rsp+98h]; this
0x18004726a  lea     rdx, aFailedToImpers; "Failed to impersonate the user!"
0x180047271  mov     [rsp+98h+var_78], rdx; __int64
0x180047276  mov     r9d, eax; char *
0x180047279  mov     r8, r14; unsigned int
0x18004727c  mov     edx, 48h ; 'H'; void *
0x180047281  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180047286  nop
0x180047287  lea     rcx, [rsp+98h+var_48]
0x18004728c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047291  nop
0x180047292  mov     rcx, [rsp+98h+phToken]; hObject
0x180047297  lea     rax, [rcx-1]
0x18004729b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004729f  ja      short loc_1800472AD
0x1800472a1  call    cs:__imp_CloseHandle
0x1800472a8  nop     dword ptr [rax+rax+00h]
0x1800472ad  xor     eax, eax
0x1800472af  jmp     short loc_1800472E2
0x1800472b1  lea     rcx, [rsp+98h+var_48]
0x1800472b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800472bb  nop
0x1800472bc  mov     rcx, [rsp+98h+phToken]; hObject
0x1800472c1  lea     rax, [rcx-1]
0x1800472c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800472c9  ja      short loc_1800472D7
0x1800472cb  call    cs:__imp_CloseHandle
0x1800472d2  nop     dword ptr [rax+rax+00h]
0x1800472d7  inc     ebx
0x1800472d9  jmp     loc_18004716C
0x1800472de  mov     eax, [rsp+98h+var_68]
0x1800472e2  mov     rcx, [rsp+98h+var_28]
0x1800472e7  xor     rcx, rsp; StackCookie
0x1800472ea  call    __security_check_cookie
0x1800472ef  lea     r11, [rsp+98h+var_8]
0x1800472f7  mov     rbx, [r11+18h]
0x1800472fb  mov     rdi, [r11+20h]
0x1800472ff  movaps  xmm6, xmmword ptr [r11-10h]
0x180047304  mov     rsp, r11
0x180047307  pop     r14
0x180047309  retn
0x18004730b  mov     rcx, [rsp+98h]; this
0x180047313  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x18004731a  mov     r8, r14; unsigned int
0x18004731d  mov     edx, 3Ah ; ':'; void *
0x180047322  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180047328  mov     ecx, 80070057h
0x18004732d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180047332  mov     r9d, eax; char *
0x180047335  mov     rcx, [rsp+98h]; this
0x18004733d  lea     rax, aFailedToFindTh; "Failed to find the user to impersonate!"
0x180047344  mov     [rsp+98h+var_78], rax; int
0x180047349  mov     r8, r14; unsigned int
0x18004734c  mov     edx, 50h ; 'P'; void *
0x180047351  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
