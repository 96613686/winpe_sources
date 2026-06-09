# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18006189c`
- end: `0x180061bfe`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `866`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005f5cc`

## callees

- `0x180012864`
- `0x18005cd64`
- `0x18005d23c`
- `0x18006189c`
- `0x18006c690`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180061a6d`
- `msvcrt!_wcsnicmp` at `0x180061a6d`
- `ADVAPI32!RevertToSelf` at `0x180061be1`
- `ADVAPI32!RevertToSelf` at `0x180061be1`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180061941`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180061941`
- `KERNEL32!GetLastError` at `0x18006194b`
- `KERNEL32!GetLastError` at `0x1800619ab`
- `KERNEL32!GetLastError` at `0x1800619b6`
- `KERNEL32!GetLastError` at `0x1800619e6`
- `KERNEL32!GetLastError` at `0x180061bef`
- `KERNEL32!GetLastError` at `0x18006194b`
- `KERNEL32!GetLastError` at `0x1800619ab`
- `KERNEL32!GetLastError` at `0x1800619b6`
- `KERNEL32!GetLastError` at `0x1800619e6`
- `KERNEL32!GetLastError` at `0x180061bef`
- `KERNEL32!GlobalFree` at `0x180061a35`
- `KERNEL32!GlobalFree` at `0x180061a4e`
- `KERNEL32!GlobalFree` at `0x180061b05`
- `KERNEL32!GlobalFree` at `0x180061b1f`
- `KERNEL32!GlobalFree` at `0x180061b51`
- `KERNEL32!GlobalFree` at `0x180061b66`
- `KERNEL32!GlobalFree` at `0x180061a35`
- `KERNEL32!GlobalFree` at `0x180061a4e`
- `KERNEL32!GlobalFree` at `0x180061b05`
- `KERNEL32!GlobalFree` at `0x180061b1f`
- `KERNEL32!GlobalFree` at `0x180061b51`
- `KERNEL32!GlobalFree` at `0x180061b66`
- `KERNEL32!ExitProcess` at `0x180061bf7`
- `KERNEL32!ExitProcess` at `0x180061bf7`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180061ab9`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180061ab9`
- `WINHTTP!WinHttpSetOption` at `0x180061bb6`
- `WINHTTP!WinHttpSetOption` at `0x180061bb6`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800619a1`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800619a1`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180061b76`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180061b76`

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
      if ( _wcsnicmp(a3, L"https://", 8u) )
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
0x18006189c  mov     [rsp-8+arg_0], rbx
0x1800618a1  push    rbp
0x1800618a2  push    rsi
0x1800618a3  push    rdi
0x1800618a4  push    r12
0x1800618a6  push    r13
0x1800618a8  push    r14
0x1800618aa  push    r15
0x1800618ac  lea     rbp, [rsp-1C0h]
0x1800618b4  sub     rsp, 2C0h
0x1800618bb  mov     rax, cs:__security_cookie
0x1800618c2  xor     rax, rsp
0x1800618c5  mov     [rbp+1F0h+var_40], rax
0x1800618cc  mov     r15, [rbp+1F0h+arg_20]
0x1800618d3  xor     edi, edi
0x1800618d5  mov     r12, [rbp+1F0h+arg_30]
0x1800618dc  xorps   xmm0, xmm0
0x1800618df  xor     eax, eax
0x1800618e1  mov     [rsp+2F0h+hToken], rdi
0x1800618e6  mov     [rsp+2F0h+var_2A8], edi
0x1800618ea  xorps   xmm1, xmm1
0x1800618ed  mov     [r15], di
0x1800618f1  mov     rsi, r8
0x1800618f4  mov     [r12], di
0x1800618f9  mov     r13, rdx
0x1800618fc  mov     [rsp+2F0h+var_2B0], rax
0x180061901  mov     r14b, dil
0x180061904  movups  xmmword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], xmm0
0x180061909  movups  xmmword ptr [rbp+1F0h+pAutoProxyOptions.lpvReserved], xmm0
0x18006190d  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm1
0x180061912  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm1
0x180061917  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x18006191c  test    r9b, r9b
0x18006191f  jnz     short loc_18006198F
0x180061921  lea     r8, [rsp+2F0h+var_2A8]; int *
0x180061926  lea     rdx, [rsp+2F0h+hToken]; void **
0x18006192b  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x180061930  mov     ebx, eax
0x180061932  test    eax, eax
0x180061934  js      short loc_180061960
0x180061936  cmp     [rsp+2F0h+var_2A8], edi
0x18006193a  jz      short loc_18006198F
0x18006193c  mov     rcx, [rsp+2F0h+hToken]; hToken
0x180061941  call    cs:__imp_ImpersonateLoggedOnUser
0x180061947  test    eax, eax
0x180061949  jnz     short loc_18006198C
0x18006194b  call    cs:__imp_GetLastError
0x180061951  mov     ebx, eax
0x180061953  test    eax, eax
0x180061955  jle     short loc_180061960
0x180061957  movzx   ebx, ax
0x18006195a  or      ebx, 80070000h
0x180061960  mov     eax, ebx
0x180061962  mov     rcx, [rbp+1F0h+var_40]
0x180061969  xor     rcx, rsp; StackCookie
0x18006196c  call    __security_check_cookie
0x180061971  mov     rbx, [rsp+2F0h+arg_0]
0x180061979  add     rsp, 2C0h
0x180061980  pop     r15
0x180061982  pop     r14
0x180061984  pop     r13
0x180061986  pop     r12
0x180061988  pop     rdi
0x180061989  pop     rsi
0x18006198a  pop     rbp
0x18006198b  retn
0x18006198c  mov     r14b, 1
0x18006198f  xorps   xmm0, xmm0
0x180061992  lea     rcx, [rsp+2F0h+pProxyConfig]; pProxyConfig
0x180061997  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm0
0x18006199c  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm0
0x1800619a1  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800619a7  test    eax, eax
0x1800619a9  jnz     short loc_1800619D4
0x1800619ab  call    cs:__imp_GetLastError
0x1800619b1  cmp     eax, 2
0x1800619b4  jz      short loc_1800619D4
0x1800619b6  call    cs:__imp_GetLastError
0x1800619bc  mov     ebx, eax
0x1800619be  test    eax, eax
0x1800619c0  jle     loc_180061BD8
0x1800619c6  movzx   ebx, ax
0x1800619c9  or      ebx, 80070000h
0x1800619cf  jmp     loc_180061BD8
0x1800619d4  mov     bl, dil
0x1800619d7  xor     eax, eax
0x1800619d9  test    eax, eax
0x1800619db  jnz     loc_180061BA1
0x1800619e1  test    rdi, rdi
0x1800619e4  jz      short loc_1800619FE
0x1800619e6  call    cs:__imp_GetLastError
0x1800619ec  cmp     eax, 2EEFh
0x1800619f1  jnz     loc_180061ADA
0x1800619f7  mov     [rbp+1F0h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x1800619fe  mov     rax, [rsp+2F0h+pProxyConfig.lpszAutoConfigUrl]
0x180061a03  mov     [rbp+1F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180061a07  test    rax, rax
0x180061a0a  jnz     short loc_180061A1E
0x180061a0c  mov     [rsp+2F0h+pAutoProxyOptions.dwFlags], 1
0x180061a14  mov     [rsp+2F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180061a1c  jmp     short loc_180061A27
0x180061a1e  mov     qword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], 2
0x180061a27  test    bl, bl
0x180061a29  jz      short loc_180061A5D
0x180061a2b  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180061a30  test    rcx, rcx
0x180061a33  jz      short loc_180061A44
0x180061a35  call    cs:__imp_GlobalFree
0x180061a3b  mov     [rsp+2F0h+hMem+8], 0
0x180061a44  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180061a49  test    rcx, rcx
0x180061a4c  jz      short loc_180061A5D
0x180061a4e  call    cs:__imp_GlobalFree
0x180061a54  mov     [rsp+2F0h+var_2B0], 0
0x180061a5d  mov     r8d, 8; MaxCount
0x180061a63  lea     rdx, aHttps; "https://"
0x180061a6a  mov     rcx, rsi; String1
0x180061a6d  call    cs:__imp__wcsnicmp
0x180061a73  test    eax, eax
0x180061a75  jz      short loc_180061AA8
0x180061a77  lea     r9, aHttps; "https://"
0x180061a7e  mov     [rsp+2F0h+var_2D0], rsi
0x180061a83  lea     r8, aLsLs; "%ls%ls"
0x180061a8a  mov     edx, 104h; unsigned __int64
0x180061a8f  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180061a93  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061a98  mov     ebx, eax
0x180061a9a  test    eax, eax
0x180061a9c  js      loc_180061BD8
0x180061aa2  lea     rdx, [rbp+1F0h+var_250]
0x180061aa6  jmp     short loc_180061AAB
0x180061aa8  mov     rdx, rsi; lpcwszUrl
0x180061aab  mov     rcx, [r13+0]; hSession
0x180061aaf  lea     r9, [rsp+2F0h+hMem]; pProxyInfo
0x180061ab4  lea     r8, [rsp+2F0h+pAutoProxyOptions]; pAutoProxyOptions
0x180061ab9  call    cs:__imp_WinHttpGetProxyForUrl
0x180061abf  inc     rdi
0x180061ac2  mov     bl, 1
0x180061ac4  cmp     rdi, 2
0x180061ac8  jb      loc_1800619D9
0x180061ace  xor     edi, edi
0x180061ad0  test    eax, eax
0x180061ad2  jnz     loc_180061BA3
0x180061ad8  jmp     short loc_180061ADC
0x180061ada  xor     edi, edi
0x180061adc  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180061ae1  test    rax, rax
0x180061ae4  jz      short loc_180061B43
0x180061ae6  cmp     [rax], di
0x180061ae9  jz      short loc_180061B43
0x180061aeb  cmp     word ptr [rax], 3Ah ; ':'
0x180061aef  jnz     short loc_180061AF7
0x180061af1  cmp     [rax+2], di
0x180061af5  jz      short loc_180061B43
0x180061af7  test    bl, bl
0x180061af9  jz      short loc_180061B2A
0x180061afb  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180061b00  test    rcx, rcx
0x180061b03  jz      short loc_180061B15
0x180061b05  call    cs:__imp_GlobalFree
0x180061b0b  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180061b10  mov     [rsp+2F0h+hMem+8], rdi
0x180061b15  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180061b1a  test    rcx, rcx
0x180061b1d  jz      short loc_180061B2A
0x180061b1f  call    cs:__imp_GlobalFree
0x180061b25  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180061b2a  mov     [rsp+2F0h+hMem+8], rax
0x180061b2f  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxyBypass]
0x180061b34  mov     [rsp+2F0h+var_2B0], rax
0x180061b39  mov     dword ptr [rsp+2F0h+hMem], 3
0x180061b41  jmp     short loc_180061BA3
0x180061b43  test    bl, bl
0x180061b45  jz      short loc_180061B71
0x180061b47  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180061b4c  test    rcx, rcx
0x180061b4f  jz      short loc_180061B5C
0x180061b51  call    cs:__imp_GlobalFree
0x180061b57  mov     [rsp+2F0h+hMem+8], rdi
0x180061b5c  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180061b61  test    rcx, rcx
0x180061b64  jz      short loc_180061B71
0x180061b66  call    cs:__imp_GlobalFree
0x180061b6c  mov     [rsp+2F0h+var_2B0], rdi
0x180061b71  lea     rcx, [rsp+2F0h+hMem]; pProxyInfo
0x180061b76  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180061b7c  test    eax, eax
0x180061b7e  jz      loc_1800619B6
0x180061b84  mov     rax, [rsp+2F0h+hMem+8]
0x180061b89  test    rax, rax
0x180061b8c  jz      short loc_180061BD6
0x180061b8e  cmp     [rax], di
0x180061b91  jz      short loc_180061BD6
0x180061b93  cmp     word ptr [rax], 3Ah ; ':'
0x180061b97  jnz     short loc_180061BA3
0x180061b99  cmp     [rax+2], di
0x180061b9d  jz      short loc_180061BD6
0x180061b9f  jmp     short loc_180061BA3
0x180061ba1  xor     edi, edi
0x180061ba3  mov     rcx, [r13+0]; hInternet
0x180061ba7  lea     r8, [rsp+2F0h+hMem]; lpBuffer
0x180061bac  mov     r9d, 18h; dwBufferLength
0x180061bb2  lea     edx, [r9+0Eh]; dwOption
0x180061bb6  call    cs:__imp_WinHttpSetOption
0x180061bbc  test    eax, eax
0x180061bbe  jz      loc_1800619B6
0x180061bc4  mov     rdx, [rsp+2F0h+hMem+8]; unsigned __int16 *
0x180061bc9  mov     r8, r15; unsigned __int16 *
0x180061bcc  mov     [rsp+2F0h+var_2D0], r12; unsigned __int16 *
0x180061bd1  call    ?GetFirstCredentialsForBasicProxyListIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAG0_K01@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetFirstCredentialsForBasicProxyListIfPresent(ushort *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180061bd6  mov     ebx, edi
0x180061bd8  test    r14b, r14b
0x180061bdb  jz      loc_180061960
0x180061be1  call    cs:__imp_RevertToSelf
0x180061be7  test    eax, eax
0x180061be9  jnz     loc_180061960
0x180061bef  call    cs:__imp_GetLastError
0x180061bf5  mov     ecx, eax; uExitCode
0x180061bf7  call    cs:__imp_ExitProcess
```
