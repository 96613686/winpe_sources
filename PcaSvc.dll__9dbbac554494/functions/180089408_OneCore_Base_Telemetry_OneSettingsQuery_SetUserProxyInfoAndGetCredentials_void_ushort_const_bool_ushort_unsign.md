# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180089408`
- end: `0x180089798`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `912`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180086954`

## callees

- `0x18000dc08`
- `0x18002ac10`
- `0x1800868d4`
- `0x180089408`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800895eb`
- `msvcrt!_wcsnicmp` at `0x1800895eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008951e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008951e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089789`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180089791`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180089791`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008977b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008977b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800894b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800894b4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800895b3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800895cc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008968a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896da`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896f3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800895b3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800895cc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008968a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896da`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800896f3`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180089514`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180089514`
- `WINHTTP!WinHttpSetOption` at `0x180089750`
- `WINHTTP!WinHttpSetOption` at `0x180089750`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180089707`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180089707`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180089637`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180089637`

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
  char v7; // r14
  signed int UserSession; // ebx
  signed int LastError; // eax
  signed int v13; // eax
  char v14; // bl
  unsigned __int64 v15; // rdi
  BOOL ProxyForUrl; // eax
  unsigned __int16 *v17; // rdx
  WCHAR *lpszProxy; // r8
  int v19; // edx
  int v20; // ecx
  OneCore::Base::Telemetry::OneSettingsQuery *v21; // rcx
  unsigned __int64 v22; // r9
  UINT v23; // eax
  unsigned __int64 v24; // [rsp+28h] [rbp-D8h]
  WINHTTP_PROXY_INFO hMem; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+58h] [rbp-A8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v30[264]; // [rsp+A0h] [rbp-60h] BYREF

  hToken = 0;
  v7 = 0;
  v26 = 0;
  *a5 = 0;
  *a7 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&hMem, 0, sizeof(hMem));
  if ( !a4 )
  {
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(this, &hToken, &v26);
    if ( UserSession < 0 )
      return (unsigned int)UserSession;
    if ( v26 )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        UserSession = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)UserSession;
      }
      v7 = 1;
    }
  }
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) || GetLastError() == 2 )
  {
    v14 = 0;
    v15 = 0;
    ProxyForUrl = 0;
    while ( v15 < 2 )
    {
      if ( ProxyForUrl )
        goto LABEL_55;
      if ( v15 )
      {
        if ( GetLastError() != 12015 )
          goto LABEL_33;
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
      if ( v14 )
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
        UserSession = StringCchPrintfW(v30, 0x104u, L"%ls%ls", L"https://", a3);
        if ( UserSession < 0 )
          goto LABEL_58;
        v17 = v30;
      }
      else
      {
        v17 = a3;
      }
      ProxyForUrl = WinHttpGetProxyForUrl(*a2, v17, &pAutoProxyOptions, &hMem);
      ++v15;
      v14 = 1;
    }
    if ( !ProxyForUrl )
    {
LABEL_33:
      lpszProxy = pProxyConfig.lpszProxy;
      if ( !pProxyConfig.lpszProxy || !*pProxyConfig.lpszProxy )
        goto LABEL_44;
      v19 = *pProxyConfig.lpszProxy - 58;
      if ( *pProxyConfig.lpszProxy == 58 )
        v19 = pProxyConfig.lpszProxy[1];
      if ( v19 )
      {
        if ( v14 )
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
        hMem.lpszProxyBypass = pProxyConfig.lpszProxyBypass;
        hMem.lpszProxy = lpszProxy;
        hMem.dwAccessType = 3;
      }
      else
      {
LABEL_44:
        if ( v14 )
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
        if ( !hMem.lpszProxy || !*hMem.lpszProxy )
          goto LABEL_57;
        v20 = *hMem.lpszProxy - 58;
        if ( *hMem.lpszProxy == 58 )
          v20 = hMem.lpszProxy[1];
        if ( !v20 )
        {
LABEL_57:
          UserSession = 0;
          goto LABEL_58;
        }
      }
    }
LABEL_55:
    if ( !WinHttpSetOption(*a2, 0x26u, &hMem, 0x18u) )
      goto LABEL_11;
    OneCore::Base::Telemetry::OneSettingsQuery::GetFirstCredentialsForBasicProxyListIfPresent(
      v21,
      hMem.lpszProxy,
      a5,
      v22,
      a7,
      v24);
    goto LABEL_57;
  }
LABEL_11:
  v13 = GetLastError();
  UserSession = v13;
  if ( v13 > 0 )
    UserSession = (unsigned __int16)v13 | 0x80070000;
LABEL_58:
  if ( v7 && !RevertToSelf() )
  {
    v23 = GetLastError();
    ExitProcess(v23);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x180089408  mov     [rsp-8+arg_0], rbx
0x18008940d  push    rbp
0x18008940e  push    rsi
0x18008940f  push    rdi
0x180089410  push    r12
0x180089412  push    r13
0x180089414  push    r14
0x180089416  push    r15
0x180089418  lea     rbp, [rsp-1C0h]
0x180089420  sub     rsp, 2C0h
0x180089427  mov     rax, cs:__security_cookie
0x18008942e  xor     rax, rsp
0x180089431  mov     [rbp+1F0h+var_40], rax
0x180089438  mov     r15, [rbp+1F0h+arg_20]
0x18008943f  xor     eax, eax
0x180089441  mov     r12, [rbp+1F0h+arg_30]
0x180089448  xorps   xmm0, xmm0
0x18008944b  xorps   xmm1, xmm1
0x18008944e  mov     [rsp+2F0h+hToken], 0
0x180089457  xor     r14b, r14b
0x18008945a  mov     [rsp+2F0h+var_2A8], 0
0x180089462  mov     [r15], ax
0x180089466  mov     rsi, r8
0x180089469  mov     [r12], ax
0x18008946e  mov     r13, rdx
0x180089471  mov     [rsp+2F0h+var_2B0], rax
0x180089476  movups  xmmword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], xmm0
0x18008947b  movups  xmmword ptr [rbp+1F0h+pAutoProxyOptions.lpvReserved], xmm0
0x18008947f  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm1
0x180089484  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm1
0x180089489  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x18008948e  test    r9b, r9b
0x180089491  jnz     short loc_180089502
0x180089493  lea     r8, [rsp+2F0h+var_2A8]; int *
0x180089498  lea     rdx, [rsp+2F0h+hToken]; void **
0x18008949d  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x1800894a2  mov     ebx, eax
0x1800894a4  test    eax, eax
0x1800894a6  js      short loc_1800894D3
0x1800894a8  cmp     [rsp+2F0h+var_2A8], 0
0x1800894ad  jz      short loc_180089502
0x1800894af  mov     rcx, [rsp+2F0h+hToken]; hToken
0x1800894b4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800894ba  test    eax, eax
0x1800894bc  jnz     short loc_1800894FF
0x1800894be  call    cs:__imp_GetLastError
0x1800894c4  mov     ebx, eax
0x1800894c6  test    eax, eax
0x1800894c8  jle     short loc_1800894D3
0x1800894ca  movzx   ebx, ax
0x1800894cd  or      ebx, 80070000h
0x1800894d3  mov     eax, ebx
0x1800894d5  mov     rcx, [rbp+1F0h+var_40]
0x1800894dc  xor     rcx, rsp; StackCookie
0x1800894df  call    __security_check_cookie
0x1800894e4  mov     rbx, [rsp+2F0h+arg_0]
0x1800894ec  add     rsp, 2C0h
0x1800894f3  pop     r15
0x1800894f5  pop     r14
0x1800894f7  pop     r13
0x1800894f9  pop     r12
0x1800894fb  pop     rdi
0x1800894fc  pop     rsi
0x1800894fd  pop     rbp
0x1800894fe  retn
0x1800894ff  mov     r14b, 1
0x180089502  xorps   xmm0, xmm0
0x180089505  lea     rcx, [rsp+2F0h+pProxyConfig]; pProxyConfig
0x18008950a  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm0
0x18008950f  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm0
0x180089514  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18008951a  test    eax, eax
0x18008951c  jnz     short loc_180089547
0x18008951e  call    cs:__imp_GetLastError
0x180089524  cmp     eax, 2
0x180089527  jz      short loc_180089547
0x180089529  call    cs:__imp_GetLastError
0x18008952f  mov     ebx, eax
0x180089531  test    eax, eax
0x180089533  jle     loc_180089772
0x180089539  movzx   ebx, ax
0x18008953c  or      ebx, 80070000h
0x180089542  jmp     loc_180089772
0x180089547  xor     bl, bl
0x180089549  xor     edi, edi
0x18008954b  xor     eax, eax
0x18008954d  cmp     rdi, 2
0x180089551  jnb     loc_180089647
0x180089557  test    eax, eax
0x180089559  jnz     loc_18008973D
0x18008955f  test    rdi, rdi
0x180089562  jz      short loc_18008957C
0x180089564  call    cs:__imp_GetLastError
0x18008956a  cmp     eax, 2EEFh
0x18008956f  jnz     loc_18008964F
0x180089575  mov     [rbp+1F0h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x18008957c  mov     rax, [rsp+2F0h+pProxyConfig.lpszAutoConfigUrl]
0x180089581  mov     [rbp+1F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180089585  test    rax, rax
0x180089588  jnz     short loc_18008959C
0x18008958a  mov     [rsp+2F0h+pAutoProxyOptions.dwFlags], 1
0x180089592  mov     [rsp+2F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18008959a  jmp     short loc_1800895A5
0x18008959c  mov     qword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], 2
0x1800895a5  test    bl, bl
0x1800895a7  jz      short loc_1800895DB
0x1800895a9  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800895ae  test    rcx, rcx
0x1800895b1  jz      short loc_1800895C2
0x1800895b3  call    cs:__imp_GlobalFree
0x1800895b9  mov     [rsp+2F0h+hMem+8], 0
0x1800895c2  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800895c7  test    rcx, rcx
0x1800895ca  jz      short loc_1800895DB
0x1800895cc  call    cs:__imp_GlobalFree
0x1800895d2  mov     [rsp+2F0h+var_2B0], 0
0x1800895db  mov     r8d, 8; MaxCount
0x1800895e1  lea     rdx, aHttps; "https://"
0x1800895e8  mov     rcx, rsi; String1
0x1800895eb  call    cs:__imp__wcsnicmp
0x1800895f1  test    eax, eax
0x1800895f3  jz      short loc_180089626
0x1800895f5  lea     r9, aHttps; "https://"
0x1800895fc  mov     [rsp+2F0h+var_2D0], rsi
0x180089601  lea     r8, aLsLs_0; "%ls%ls"
0x180089608  mov     edx, 104h; unsigned __int64
0x18008960d  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180089611  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180089616  mov     ebx, eax
0x180089618  test    eax, eax
0x18008961a  js      loc_180089772
0x180089620  lea     rdx, [rbp+1F0h+var_250]
0x180089624  jmp     short loc_180089629
0x180089626  mov     rdx, rsi; lpcwszUrl
0x180089629  mov     rcx, [r13+0]; hSession
0x18008962d  lea     r9, [rsp+2F0h+hMem]; pProxyInfo
0x180089632  lea     r8, [rsp+2F0h+pAutoProxyOptions]; pAutoProxyOptions
0x180089637  call    cs:__imp_WinHttpGetProxyForUrl
0x18008963d  inc     rdi
0x180089640  mov     bl, 1
0x180089642  jmp     loc_18008954D
0x180089647  test    eax, eax
0x180089649  jnz     loc_18008973D
0x18008964f  mov     r8, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180089654  mov     edi, 3Ah ; ':'
0x180089659  test    r8, r8
0x18008965c  jz      short loc_1800896CC
0x18008965e  xor     eax, eax
0x180089660  cmp     [r8], ax
0x180089664  jz      short loc_1800896CC
0x180089666  movzx   edx, word ptr [r8]
0x18008966a  sub     edx, edi
0x18008966c  jnz     short loc_180089678
0x18008966e  movzx   edx, word ptr [r8+2]
0x180089673  movzx   ecx, ax
0x180089676  sub     edx, ecx
0x180089678  test    edx, edx
0x18008967a  jz      short loc_1800896CC
0x18008967c  test    bl, bl
0x18008967e  jz      short loc_1800896B3
0x180089680  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180089685  test    rcx, rcx
0x180089688  jz      short loc_18008969E
0x18008968a  call    cs:__imp_GlobalFree
0x180089690  mov     r8, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180089695  mov     [rsp+2F0h+hMem+8], 0
0x18008969e  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800896a3  test    rcx, rcx
0x1800896a6  jz      short loc_1800896B3
0x1800896a8  call    cs:__imp_GlobalFree
0x1800896ae  mov     r8, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800896b3  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxyBypass]
0x1800896b8  mov     [rsp+2F0h+var_2B0], rax
0x1800896bd  mov     [rsp+2F0h+hMem+8], r8
0x1800896c2  mov     dword ptr [rsp+2F0h+hMem], 3
0x1800896ca  jmp     short loc_18008973D
0x1800896cc  test    bl, bl
0x1800896ce  jz      short loc_180089702
0x1800896d0  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800896d5  test    rcx, rcx
0x1800896d8  jz      short loc_1800896E9
0x1800896da  call    cs:__imp_GlobalFree
0x1800896e0  mov     [rsp+2F0h+hMem+8], 0
0x1800896e9  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800896ee  test    rcx, rcx
0x1800896f1  jz      short loc_180089702
0x1800896f3  call    cs:__imp_GlobalFree
0x1800896f9  mov     [rsp+2F0h+var_2B0], 0
0x180089702  lea     rcx, [rsp+2F0h+hMem]; pProxyInfo
0x180089707  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18008970d  test    eax, eax
0x18008970f  jz      loc_180089529
0x180089715  mov     r8, [rsp+2F0h+hMem+8]
0x18008971a  test    r8, r8
0x18008971d  jz      short loc_180089770
0x18008971f  xor     eax, eax
0x180089721  cmp     [r8], ax
0x180089725  jz      short loc_180089770
0x180089727  movzx   ecx, word ptr [r8]
0x18008972b  sub     ecx, edi
0x18008972d  jnz     short loc_180089739
0x18008972f  movzx   ecx, word ptr [r8+2]
0x180089734  movzx   edx, ax
0x180089737  sub     ecx, edx
0x180089739  test    ecx, ecx
0x18008973b  jz      short loc_180089770
0x18008973d  mov     rcx, [r13+0]; hInternet
0x180089741  lea     r8, [rsp+2F0h+hMem]; lpBuffer
0x180089746  mov     r9d, 18h; dwBufferLength
0x18008974c  lea     edx, [r9+0Eh]; dwOption
0x180089750  call    cs:__imp_WinHttpSetOption
0x180089756  test    eax, eax
0x180089758  jz      loc_180089529
0x18008975e  mov     rdx, [rsp+2F0h+hMem+8]; unsigned __int16 *
0x180089763  mov     r8, r15; unsigned __int16 *
0x180089766  mov     [rsp+2F0h+var_2D0], r12; unsigned __int16 *
0x18008976b  call    ?GetFirstCredentialsForBasicProxyListIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAG0_K01@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetFirstCredentialsForBasicProxyListIfPresent(ushort *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180089770  xor     ebx, ebx
0x180089772  test    r14b, r14b
0x180089775  jz      loc_1800894D3
0x18008977b  call    cs:__imp_RevertToSelf
0x180089781  test    eax, eax
0x180089783  jnz     loc_1800894D3
0x180089789  call    cs:__imp_GetLastError
0x18008978f  mov     ecx, eax; uExitCode
0x180089791  call    cs:__imp_ExitProcess
```
