# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x1800a3ab8`
- end: `0x1800a3e1a`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `866`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a182c`

## callees

- `0x180008570`
- `0x180011d94`
- `0x18009cc74`
- `0x18009d0d0`
- `0x1800a3ab8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a3c89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a3c89`
- `KERNEL32!GlobalFree` at `0x1800a3c51`
- `KERNEL32!GlobalFree` at `0x1800a3c6a`
- `KERNEL32!GlobalFree` at `0x1800a3d21`
- `KERNEL32!GlobalFree` at `0x1800a3d3b`
- `KERNEL32!GlobalFree` at `0x1800a3d6d`
- `KERNEL32!GlobalFree` at `0x1800a3d82`
- `KERNEL32!GlobalFree` at `0x1800a3c51`
- `KERNEL32!GlobalFree` at `0x1800a3c6a`
- `KERNEL32!GlobalFree` at `0x1800a3d21`
- `KERNEL32!GlobalFree` at `0x1800a3d3b`
- `KERNEL32!GlobalFree` at `0x1800a3d6d`
- `KERNEL32!GlobalFree` at `0x1800a3d82`
- `KERNEL32!ExitProcess` at `0x1800a3e13`
- `KERNEL32!ExitProcess` at `0x1800a3e13`
- `KERNEL32!GetLastError` at `0x1800a3b67`
- `KERNEL32!GetLastError` at `0x1800a3bc7`
- `KERNEL32!GetLastError` at `0x1800a3bd2`
- `KERNEL32!GetLastError` at `0x1800a3c02`
- `KERNEL32!GetLastError` at `0x1800a3e0b`
- `KERNEL32!GetLastError` at `0x1800a3b67`
- `KERNEL32!GetLastError` at `0x1800a3bc7`
- `KERNEL32!GetLastError` at `0x1800a3bd2`
- `KERNEL32!GetLastError` at `0x1800a3c02`
- `KERNEL32!GetLastError` at `0x1800a3e0b`
- `ADVAPI32!RevertToSelf` at `0x1800a3dfd`
- `ADVAPI32!RevertToSelf` at `0x1800a3dfd`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800a3b5d`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800a3b5d`
- `WINHTTP!WinHttpSetOption` at `0x1800a3dd2`
- `WINHTTP!WinHttpSetOption` at `0x1800a3dd2`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800a3bbd`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800a3bbd`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800a3cd5`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800a3cd5`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800a3d92`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800a3d92`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        void **a2,
        unsigned __int16 *a3,
        char a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        unsigned __int16 *a7)
{
  unsigned __int64 v7; // rdi
  char v10; // r14
  signed int UserSession; // ebx
  signed int LastError; // eax
  signed int v14; // eax
  char v15; // bl
  BOOL ProxyForUrl; // eax
  unsigned __int16 *v17; // rdx
  WCHAR *lpszProxy; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v19; // rcx
  unsigned __int64 v20; // r9
  UINT v21; // eax
  unsigned __int64 v22; // [rsp+28h] [rbp-D8h]
  WINHTTP_PROXY_INFO hMem; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+58h] [rbp-A8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v28[264]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = 0;
  hToken = 0;
  v24 = 0;
  *a5 = 0;
  *a7 = 0;
  v10 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&hMem, 0, sizeof(hMem));
  if ( !a4 )
  {
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(this, &hToken, &v24);
    if ( UserSession < 0 )
      return (unsigned int)UserSession;
    if ( v24 )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        UserSession = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)UserSession;
      }
      v10 = 1;
    }
  }
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) || GetLastError() == 2 )
  {
    v15 = 0;
    ProxyForUrl = 0;
    do
    {
      if ( ProxyForUrl )
        goto LABEL_52;
      if ( v7 )
      {
        if ( GetLastError() != 12015 )
          goto LABEL_32;
        pAutoProxyOptions.fAutoLogonIfChallenged = 1;
      }
      pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      if ( pProxyConfig.lpszAutoConfigUrl )
      {
        *(_QWORD *)&pAutoProxyOptions.dwFlags = 2;
      }
      else
      {
        pAutoProxyOptions.dwFlags = 1;
        pAutoProxyOptions.dwAutoDetectFlags = 3;
      }
      if ( v15 )
      {
        if ( hMem.lpszProxy )
        {
          GlobalFree(hMem.lpszProxy);
          hMem.lpszProxy = 0;
        }
        if ( hMem.lpszProxyBypass )
        {
          GlobalFree(hMem.lpszProxyBypass);
          hMem.lpszProxyBypass = 0;
        }
      }
      if ( (unsigned int)_o__wcsnicmp(a3, L"https://", 8) )
      {
        UserSession = StringCchPrintfW(v28, 0x104u, L"%ls%ls", L"https://", a3);
        if ( UserSession < 0 )
          goto LABEL_55;
        v17 = v28;
      }
      else
      {
        v17 = a3;
      }
      ProxyForUrl = WinHttpGetProxyForUrl(*a2, v17, &pAutoProxyOptions, &hMem);
      ++v7;
      v15 = 1;
    }
    while ( v7 < 2 );
    if ( !ProxyForUrl )
    {
LABEL_32:
      lpszProxy = pProxyConfig.lpszProxy;
      if ( pProxyConfig.lpszProxy
        && *pProxyConfig.lpszProxy
        && (*pProxyConfig.lpszProxy != 58 || pProxyConfig.lpszProxy[1]) )
      {
        if ( v15 )
        {
          if ( hMem.lpszProxy )
          {
            GlobalFree(hMem.lpszProxy);
            lpszProxy = pProxyConfig.lpszProxy;
            hMem.lpszProxy = 0;
          }
          if ( hMem.lpszProxyBypass )
          {
            GlobalFree(hMem.lpszProxyBypass);
            lpszProxy = pProxyConfig.lpszProxy;
          }
        }
        hMem.lpszProxy = lpszProxy;
        hMem.lpszProxyBypass = pProxyConfig.lpszProxyBypass;
        hMem.dwAccessType = 3;
      }
      else
      {
        if ( v15 )
        {
          if ( hMem.lpszProxy )
          {
            GlobalFree(hMem.lpszProxy);
            hMem.lpszProxy = 0;
          }
          if ( hMem.lpszProxyBypass )
          {
            GlobalFree(hMem.lpszProxyBypass);
            hMem.lpszProxyBypass = 0;
          }
        }
        if ( !WinHttpGetDefaultProxyConfiguration(&hMem) )
          goto LABEL_11;
        if ( !hMem.lpszProxy || !*hMem.lpszProxy || *hMem.lpszProxy == 58 && !hMem.lpszProxy[1] )
        {
LABEL_54:
          UserSession = 0;
          goto LABEL_55;
        }
      }
    }
LABEL_52:
    if ( !WinHttpSetOption(*a2, 0x26u, &hMem, 0x18u) )
      goto LABEL_11;
    OneCore::Base::Telemetry::OneSettingsQuery::GetFirstCredentialsForBasicProxyListIfPresent(
      v19,
      hMem.lpszProxy,
      a5,
      v20,
      a7,
      v22);
    goto LABEL_54;
  }
LABEL_11:
  v14 = GetLastError();
  UserSession = v14;
  if ( v14 > 0 )
    UserSession = (unsigned __int16)v14 | 0x80070000;
LABEL_55:
  if ( v10 && !RevertToSelf() )
  {
    v21 = GetLastError();
    ExitProcess(v21);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x1800a3ab8  mov     [rsp-8+arg_0], rbx
0x1800a3abd  push    rbp
0x1800a3abe  push    rsi
0x1800a3abf  push    rdi
0x1800a3ac0  push    r12
0x1800a3ac2  push    r13
0x1800a3ac4  push    r14
0x1800a3ac6  push    r15
0x1800a3ac8  lea     rbp, [rsp-1C0h]
0x1800a3ad0  sub     rsp, 2C0h
0x1800a3ad7  mov     rax, cs:__security_cookie
0x1800a3ade  xor     rax, rsp
0x1800a3ae1  mov     [rbp+1F0h+var_40], rax
0x1800a3ae8  mov     r15, [rbp+1F0h+arg_20]
0x1800a3aef  xor     edi, edi
0x1800a3af1  mov     r12, [rbp+1F0h+arg_30]
0x1800a3af8  xorps   xmm0, xmm0
0x1800a3afb  xor     eax, eax
0x1800a3afd  mov     [rsp+2F0h+hToken], rdi
0x1800a3b02  mov     [rsp+2F0h+var_2A8], edi
0x1800a3b06  xorps   xmm1, xmm1
0x1800a3b09  mov     [r15], di
0x1800a3b0d  mov     rsi, r8
0x1800a3b10  mov     [r12], di
0x1800a3b15  mov     r13, rdx
0x1800a3b18  mov     [rsp+2F0h+var_2B0], rax
0x1800a3b1d  mov     r14b, dil
0x1800a3b20  movups  xmmword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], xmm0
0x1800a3b25  movups  xmmword ptr [rbp+1F0h+pAutoProxyOptions.lpvReserved], xmm0
0x1800a3b29  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm1
0x1800a3b2e  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm1
0x1800a3b33  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x1800a3b38  test    r9b, r9b
0x1800a3b3b  jnz     short loc_1800A3BAB
0x1800a3b3d  lea     r8, [rsp+2F0h+var_2A8]; int *
0x1800a3b42  lea     rdx, [rsp+2F0h+hToken]; void **
0x1800a3b47  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x1800a3b4c  mov     ebx, eax
0x1800a3b4e  test    eax, eax
0x1800a3b50  js      short loc_1800A3B7C
0x1800a3b52  cmp     [rsp+2F0h+var_2A8], edi
0x1800a3b56  jz      short loc_1800A3BAB
0x1800a3b58  mov     rcx, [rsp+2F0h+hToken]; hToken
0x1800a3b5d  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a3b63  test    eax, eax
0x1800a3b65  jnz     short loc_1800A3BA8
0x1800a3b67  call    cs:__imp_GetLastError
0x1800a3b6d  mov     ebx, eax
0x1800a3b6f  test    eax, eax
0x1800a3b71  jle     short loc_1800A3B7C
0x1800a3b73  movzx   ebx, ax
0x1800a3b76  or      ebx, 80070000h
0x1800a3b7c  mov     eax, ebx
0x1800a3b7e  mov     rcx, [rbp+1F0h+var_40]
0x1800a3b85  xor     rcx, rsp; StackCookie
0x1800a3b88  call    __security_check_cookie
0x1800a3b8d  mov     rbx, [rsp+2F0h+arg_0]
0x1800a3b95  add     rsp, 2C0h
0x1800a3b9c  pop     r15
0x1800a3b9e  pop     r14
0x1800a3ba0  pop     r13
0x1800a3ba2  pop     r12
0x1800a3ba4  pop     rdi
0x1800a3ba5  pop     rsi
0x1800a3ba6  pop     rbp
0x1800a3ba7  retn
0x1800a3ba8  mov     r14b, 1
0x1800a3bab  xorps   xmm0, xmm0
0x1800a3bae  lea     rcx, [rsp+2F0h+pProxyConfig]; pProxyConfig
0x1800a3bb3  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm0
0x1800a3bb8  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm0
0x1800a3bbd  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800a3bc3  test    eax, eax
0x1800a3bc5  jnz     short loc_1800A3BF0
0x1800a3bc7  call    cs:__imp_GetLastError
0x1800a3bcd  cmp     eax, 2
0x1800a3bd0  jz      short loc_1800A3BF0
0x1800a3bd2  call    cs:__imp_GetLastError
0x1800a3bd8  mov     ebx, eax
0x1800a3bda  test    eax, eax
0x1800a3bdc  jle     loc_1800A3DF4
0x1800a3be2  movzx   ebx, ax
0x1800a3be5  or      ebx, 80070000h
0x1800a3beb  jmp     loc_1800A3DF4
0x1800a3bf0  mov     bl, dil
0x1800a3bf3  xor     eax, eax
0x1800a3bf5  test    eax, eax
0x1800a3bf7  jnz     loc_1800A3DBD
0x1800a3bfd  test    rdi, rdi
0x1800a3c00  jz      short loc_1800A3C1A
0x1800a3c02  call    cs:__imp_GetLastError
0x1800a3c08  cmp     eax, 2EEFh
0x1800a3c0d  jnz     loc_1800A3CF6
0x1800a3c13  mov     [rbp+1F0h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x1800a3c1a  mov     rax, [rsp+2F0h+pProxyConfig.lpszAutoConfigUrl]
0x1800a3c1f  mov     [rbp+1F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x1800a3c23  test    rax, rax
0x1800a3c26  jnz     short loc_1800A3C3A
0x1800a3c28  mov     [rsp+2F0h+pAutoProxyOptions.dwFlags], 1
0x1800a3c30  mov     [rsp+2F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800a3c38  jmp     short loc_1800A3C43
0x1800a3c3a  mov     qword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], 2
0x1800a3c43  test    bl, bl
0x1800a3c45  jz      short loc_1800A3C79
0x1800a3c47  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800a3c4c  test    rcx, rcx
0x1800a3c4f  jz      short loc_1800A3C60
0x1800a3c51  call    cs:__imp_GlobalFree
0x1800a3c57  mov     [rsp+2F0h+hMem+8], 0
0x1800a3c60  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800a3c65  test    rcx, rcx
0x1800a3c68  jz      short loc_1800A3C79
0x1800a3c6a  call    cs:__imp_GlobalFree
0x1800a3c70  mov     [rsp+2F0h+var_2B0], 0
0x1800a3c79  mov     r8d, 8
0x1800a3c7f  lea     rdx, aHttps; "https://"
0x1800a3c86  mov     rcx, rsi
0x1800a3c89  call    cs:__imp__o__wcsnicmp
0x1800a3c8f  test    eax, eax
0x1800a3c91  jz      short loc_1800A3CC4
0x1800a3c93  lea     r9, aHttps; "https://"
0x1800a3c9a  mov     [rsp+2F0h+var_2D0], rsi
0x1800a3c9f  lea     r8, aLsLs_3; "%ls%ls"
0x1800a3ca6  mov     edx, 104h; unsigned __int64
0x1800a3cab  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x1800a3caf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3cb4  mov     ebx, eax
0x1800a3cb6  test    eax, eax
0x1800a3cb8  js      loc_1800A3DF4
0x1800a3cbe  lea     rdx, [rbp+1F0h+var_250]
0x1800a3cc2  jmp     short loc_1800A3CC7
0x1800a3cc4  mov     rdx, rsi; lpcwszUrl
0x1800a3cc7  mov     rcx, [r13+0]; hSession
0x1800a3ccb  lea     r9, [rsp+2F0h+hMem]; pProxyInfo
0x1800a3cd0  lea     r8, [rsp+2F0h+pAutoProxyOptions]; pAutoProxyOptions
0x1800a3cd5  call    cs:__imp_WinHttpGetProxyForUrl
0x1800a3cdb  inc     rdi
0x1800a3cde  mov     bl, 1
0x1800a3ce0  cmp     rdi, 2
0x1800a3ce4  jb      loc_1800A3BF5
0x1800a3cea  xor     edi, edi
0x1800a3cec  test    eax, eax
0x1800a3cee  jnz     loc_1800A3DBF
0x1800a3cf4  jmp     short loc_1800A3CF8
0x1800a3cf6  xor     edi, edi
0x1800a3cf8  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800a3cfd  test    rax, rax
0x1800a3d00  jz      short loc_1800A3D5F
0x1800a3d02  cmp     [rax], di
0x1800a3d05  jz      short loc_1800A3D5F
0x1800a3d07  cmp     word ptr [rax], 3Ah ; ':'
0x1800a3d0b  jnz     short loc_1800A3D13
0x1800a3d0d  cmp     [rax+2], di
0x1800a3d11  jz      short loc_1800A3D5F
0x1800a3d13  test    bl, bl
0x1800a3d15  jz      short loc_1800A3D46
0x1800a3d17  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800a3d1c  test    rcx, rcx
0x1800a3d1f  jz      short loc_1800A3D31
0x1800a3d21  call    cs:__imp_GlobalFree
0x1800a3d27  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800a3d2c  mov     [rsp+2F0h+hMem+8], rdi
0x1800a3d31  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800a3d36  test    rcx, rcx
0x1800a3d39  jz      short loc_1800A3D46
0x1800a3d3b  call    cs:__imp_GlobalFree
0x1800a3d41  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800a3d46  mov     [rsp+2F0h+hMem+8], rax
0x1800a3d4b  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxyBypass]
0x1800a3d50  mov     [rsp+2F0h+var_2B0], rax
0x1800a3d55  mov     dword ptr [rsp+2F0h+hMem], 3
0x1800a3d5d  jmp     short loc_1800A3DBF
0x1800a3d5f  test    bl, bl
0x1800a3d61  jz      short loc_1800A3D8D
0x1800a3d63  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800a3d68  test    rcx, rcx
0x1800a3d6b  jz      short loc_1800A3D78
0x1800a3d6d  call    cs:__imp_GlobalFree
0x1800a3d73  mov     [rsp+2F0h+hMem+8], rdi
0x1800a3d78  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800a3d7d  test    rcx, rcx
0x1800a3d80  jz      short loc_1800A3D8D
0x1800a3d82  call    cs:__imp_GlobalFree
0x1800a3d88  mov     [rsp+2F0h+var_2B0], rdi
0x1800a3d8d  lea     rcx, [rsp+2F0h+hMem]; pProxyInfo
0x1800a3d92  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800a3d98  test    eax, eax
0x1800a3d9a  jz      loc_1800A3BD2
0x1800a3da0  mov     rax, [rsp+2F0h+hMem+8]
0x1800a3da5  test    rax, rax
0x1800a3da8  jz      short loc_1800A3DF2
0x1800a3daa  cmp     [rax], di
0x1800a3dad  jz      short loc_1800A3DF2
0x1800a3daf  cmp     word ptr [rax], 3Ah ; ':'
0x1800a3db3  jnz     short loc_1800A3DBF
0x1800a3db5  cmp     [rax+2], di
0x1800a3db9  jz      short loc_1800A3DF2
0x1800a3dbb  jmp     short loc_1800A3DBF
0x1800a3dbd  xor     edi, edi
0x1800a3dbf  mov     rcx, [r13+0]; hInternet
0x1800a3dc3  lea     r8, [rsp+2F0h+hMem]; lpBuffer
0x1800a3dc8  mov     r9d, 18h; dwBufferLength
0x1800a3dce  lea     edx, [r9+0Eh]; dwOption
0x1800a3dd2  call    cs:__imp_WinHttpSetOption
0x1800a3dd8  test    eax, eax
0x1800a3dda  jz      loc_1800A3BD2
0x1800a3de0  mov     rdx, [rsp+2F0h+hMem+8]; unsigned __int16 *
0x1800a3de5  mov     r8, r15; unsigned __int16 *
0x1800a3de8  mov     [rsp+2F0h+var_2D0], r12; unsigned __int16 *
0x1800a3ded  call    ?GetFirstCredentialsForBasicProxyListIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAG0_K01@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetFirstCredentialsForBasicProxyListIfPresent(ushort *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800a3df2  mov     ebx, edi
0x1800a3df4  test    r14b, r14b
0x1800a3df7  jz      loc_1800A3B7C
0x1800a3dfd  call    cs:__imp_RevertToSelf
0x1800a3e03  test    eax, eax
0x1800a3e05  jnz     loc_1800A3B7C
0x1800a3e0b  call    cs:__imp_GetLastError
0x1800a3e11  mov     ecx, eax; uExitCode
0x1800a3e13  call    cs:__imp_ExitProcess
```
