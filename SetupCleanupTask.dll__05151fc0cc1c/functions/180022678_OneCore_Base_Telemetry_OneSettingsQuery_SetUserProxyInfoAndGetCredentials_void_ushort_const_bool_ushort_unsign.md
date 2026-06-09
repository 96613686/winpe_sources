# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180022678`
- end: `0x180022a0c`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `916`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001eac8`

## callees

- `0x180003850`
- `0x18001b524`
- `0x18001b8ec`
- `0x180022678`
- `0x180032310`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002284a`
- `msvcrt!_wcsnicmp` at `0x18002284a`
- `msvcrt!wcsrchr` at `0x1800229c6`
- `msvcrt!wcsrchr` at `0x1800229c6`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180022a05`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180022a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229fd`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180022956`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180022956`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180022895`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180022895`
- `WINHTTP!WinHttpSetOption` at `0x180022999`
- `WINHTTP!WinHttpSetOption` at `0x180022999`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18002277e`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18002277e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002271e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002271e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229ef`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800229ef`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022812`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002282b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800228e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800228ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022931`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022946`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022812`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002282b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800228e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800228ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022931`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022946`

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
  const unsigned __int16 *v19; // rbx
  wchar_t *v20; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v21; // rcx
  __int64 v22; // r9
  UINT v23; // eax
  WINHTTP_PROXY_INFO hMem; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+58h] [rbp-A8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v29[264]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = 0;
  hToken = 0;
  v25 = 0;
  *a5 = 0;
  *a7 = 0;
  v10 = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&hMem, 0, sizeof(hMem));
  if ( !a4 )
  {
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(this, &hToken, &v25);
    if ( UserSession < 0 )
      return (unsigned int)UserSession;
    if ( v25 )
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
        UserSession = StringCchPrintfW(v29, 0x104u, L"%ls%ls", L"https://", a3);
        if ( UserSession < 0 )
          goto LABEL_61;
        v17 = v29;
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
LABEL_60:
          UserSession = 0;
          goto LABEL_61;
        }
      }
    }
LABEL_52:
    if ( !WinHttpSetOption(*a2, 0x26u, &hMem, 0x18u) )
      goto LABEL_11;
    v19 = hMem.lpszProxy;
    if ( hMem.lpszProxy && *hMem.lpszProxy && (*hMem.lpszProxy != 58 || hMem.lpszProxy[1]) )
    {
      v20 = wcsrchr(hMem.lpszProxy, 0x3Au);
      if ( v20 )
        *v20 = 0;
      OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(v21, v19, a5, v22, a7);
    }
    goto LABEL_60;
  }
LABEL_11:
  v14 = GetLastError();
  UserSession = v14;
  if ( v14 > 0 )
    UserSession = (unsigned __int16)v14 | 0x80070000;
LABEL_61:
  if ( v10 && !RevertToSelf() )
  {
    v23 = GetLastError();
    ExitProcess(v23);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x180022678  mov     [rsp-8+arg_0], rbx
0x18002267d  push    rbp
0x18002267e  push    rsi
0x18002267f  push    rdi
0x180022680  push    r12
0x180022682  push    r13
0x180022684  push    r14
0x180022686  push    r15
0x180022688  lea     rbp, [rsp-1C0h]
0x180022690  sub     rsp, 2C0h
0x180022697  mov     rax, cs:__security_cookie
0x18002269e  xor     rax, rsp
0x1800226a1  mov     [rbp+1F0h+var_40], rax
0x1800226a8  mov     r12, [rbp+1F0h+arg_20]
0x1800226af  xor     edi, edi
0x1800226b1  mov     r13, [rbp+1F0h+arg_30]
0x1800226b8  xorps   xmm0, xmm0
0x1800226bb  xor     eax, eax
0x1800226bd  mov     [rsp+2F0h+hToken], rdi
0x1800226c2  mov     [rsp+2F0h+var_2A8], edi
0x1800226c6  xorps   xmm1, xmm1
0x1800226c9  mov     [r12], di
0x1800226ce  mov     rsi, r8
0x1800226d1  mov     [r13+0], di
0x1800226d6  mov     r15, rdx
0x1800226d9  mov     [rsp+2F0h+var_2B0], rax
0x1800226de  mov     r14b, dil
0x1800226e1  movups  xmmword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], xmm0
0x1800226e6  movups  xmmword ptr [rbp+1F0h+pAutoProxyOptions.lpvReserved], xmm0
0x1800226ea  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm1
0x1800226ef  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm1
0x1800226f4  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x1800226f9  test    r9b, r9b
0x1800226fc  jnz     short loc_18002276C
0x1800226fe  lea     r8, [rsp+2F0h+var_2A8]; int *
0x180022703  lea     rdx, [rsp+2F0h+hToken]; void **
0x180022708  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x18002270d  mov     ebx, eax
0x18002270f  test    eax, eax
0x180022711  js      short loc_18002273D
0x180022713  cmp     [rsp+2F0h+var_2A8], edi
0x180022717  jz      short loc_18002276C
0x180022719  mov     rcx, [rsp+2F0h+hToken]; hToken
0x18002271e  call    cs:__imp_ImpersonateLoggedOnUser
0x180022724  test    eax, eax
0x180022726  jnz     short loc_180022769
0x180022728  call    cs:__imp_GetLastError
0x18002272e  mov     ebx, eax
0x180022730  test    eax, eax
0x180022732  jle     short loc_18002273D
0x180022734  movzx   ebx, ax
0x180022737  or      ebx, 80070000h
0x18002273d  mov     eax, ebx
0x18002273f  mov     rcx, [rbp+1F0h+var_40]
0x180022746  xor     rcx, rsp; StackCookie
0x180022749  call    __security_check_cookie
0x18002274e  mov     rbx, [rsp+2F0h+arg_0]
0x180022756  add     rsp, 2C0h
0x18002275d  pop     r15
0x18002275f  pop     r14
0x180022761  pop     r13
0x180022763  pop     r12
0x180022765  pop     rdi
0x180022766  pop     rsi
0x180022767  pop     rbp
0x180022768  retn
0x180022769  mov     r14b, 1
0x18002276c  xorps   xmm0, xmm0
0x18002276f  lea     rcx, [rsp+2F0h+pProxyConfig]; pProxyConfig
0x180022774  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm0
0x180022779  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm0
0x18002277e  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180022784  test    eax, eax
0x180022786  jnz     short loc_1800227B1
0x180022788  call    cs:__imp_GetLastError
0x18002278e  cmp     eax, 2
0x180022791  jz      short loc_1800227B1
0x180022793  call    cs:__imp_GetLastError
0x180022799  mov     ebx, eax
0x18002279b  test    eax, eax
0x18002279d  jle     loc_1800229E6
0x1800227a3  movzx   ebx, ax
0x1800227a6  or      ebx, 80070000h
0x1800227ac  jmp     loc_1800229E6
0x1800227b1  mov     bl, dil
0x1800227b4  xor     eax, eax
0x1800227b6  test    eax, eax
0x1800227b8  jnz     loc_180022980
0x1800227be  test    rdi, rdi
0x1800227c1  jz      short loc_1800227DB
0x1800227c3  call    cs:__imp_GetLastError
0x1800227c9  cmp     eax, 2EEFh
0x1800227ce  jnz     loc_1800228B6
0x1800227d4  mov     [rbp+1F0h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x1800227db  mov     rax, [rsp+2F0h+pProxyConfig.lpszAutoConfigUrl]
0x1800227e0  mov     [rbp+1F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x1800227e4  test    rax, rax
0x1800227e7  jnz     short loc_1800227FB
0x1800227e9  mov     [rsp+2F0h+pAutoProxyOptions.dwFlags], 1
0x1800227f1  mov     [rsp+2F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800227f9  jmp     short loc_180022804
0x1800227fb  mov     qword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], 2
0x180022804  test    bl, bl
0x180022806  jz      short loc_18002283A
0x180022808  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18002280d  test    rcx, rcx
0x180022810  jz      short loc_180022821
0x180022812  call    cs:__imp_GlobalFree
0x180022818  mov     [rsp+2F0h+hMem+8], 0
0x180022821  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180022826  test    rcx, rcx
0x180022829  jz      short loc_18002283A
0x18002282b  call    cs:__imp_GlobalFree
0x180022831  mov     [rsp+2F0h+var_2B0], 0
0x18002283a  mov     r8d, 8; MaxCount
0x180022840  lea     rdx, aHttps; "https://"
0x180022847  mov     rcx, rsi; String1
0x18002284a  call    cs:__imp__wcsnicmp
0x180022850  test    eax, eax
0x180022852  jz      short loc_180022885
0x180022854  lea     r9, aHttps; "https://"
0x18002285b  mov     [rsp+2F0h+var_2D0], rsi
0x180022860  lea     r8, aLsLs; "%ls%ls"
0x180022867  mov     edx, 104h; unsigned __int64
0x18002286c  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x180022870  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022875  mov     ebx, eax
0x180022877  test    eax, eax
0x180022879  js      loc_1800229E6
0x18002287f  lea     rdx, [rbp+1F0h+var_250]
0x180022883  jmp     short loc_180022888
0x180022885  mov     rdx, rsi; lpcwszUrl
0x180022888  mov     rcx, [r15]; hSession
0x18002288b  lea     r9, [rsp+2F0h+hMem]; pProxyInfo
0x180022890  lea     r8, [rsp+2F0h+pAutoProxyOptions]; pAutoProxyOptions
0x180022895  call    cs:__imp_WinHttpGetProxyForUrl
0x18002289b  inc     rdi
0x18002289e  mov     bl, 1
0x1800228a0  cmp     rdi, 2
0x1800228a4  jb      loc_1800227B6
0x1800228aa  xor     edi, edi
0x1800228ac  test    eax, eax
0x1800228ae  jnz     loc_180022982
0x1800228b4  jmp     short loc_1800228B8
0x1800228b6  xor     edi, edi
0x1800228b8  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800228bd  mov     esi, 3Ah ; ':'
0x1800228c2  test    rax, rax
0x1800228c5  jz      short loc_180022923
0x1800228c7  cmp     [rax], di
0x1800228ca  jz      short loc_180022923
0x1800228cc  cmp     [rax], si
0x1800228cf  jnz     short loc_1800228D7
0x1800228d1  cmp     [rax+2], di
0x1800228d5  jz      short loc_180022923
0x1800228d7  test    bl, bl
0x1800228d9  jz      short loc_18002290A
0x1800228db  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x1800228e0  test    rcx, rcx
0x1800228e3  jz      short loc_1800228F5
0x1800228e5  call    cs:__imp_GlobalFree
0x1800228eb  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800228f0  mov     [rsp+2F0h+hMem+8], rdi
0x1800228f5  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x1800228fa  test    rcx, rcx
0x1800228fd  jz      short loc_18002290A
0x1800228ff  call    cs:__imp_GlobalFree
0x180022905  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x18002290a  mov     [rsp+2F0h+hMem+8], rax
0x18002290f  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxyBypass]
0x180022914  mov     [rsp+2F0h+var_2B0], rax
0x180022919  mov     dword ptr [rsp+2F0h+hMem], 3
0x180022921  jmp     short loc_180022987
0x180022923  test    bl, bl
0x180022925  jz      short loc_180022951
0x180022927  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18002292c  test    rcx, rcx
0x18002292f  jz      short loc_18002293C
0x180022931  call    cs:__imp_GlobalFree
0x180022937  mov     [rsp+2F0h+hMem+8], rdi
0x18002293c  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180022941  test    rcx, rcx
0x180022944  jz      short loc_180022951
0x180022946  call    cs:__imp_GlobalFree
0x18002294c  mov     [rsp+2F0h+var_2B0], rdi
0x180022951  lea     rcx, [rsp+2F0h+hMem]; pProxyInfo
0x180022956  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18002295c  test    eax, eax
0x18002295e  jz      loc_180022793
0x180022964  mov     rax, [rsp+2F0h+hMem+8]
0x180022969  test    rax, rax
0x18002296c  jz      short loc_1800229E4
0x18002296e  cmp     [rax], di
0x180022971  jz      short loc_1800229E4
0x180022973  cmp     [rax], si
0x180022976  jnz     short loc_180022987
0x180022978  cmp     [rax+2], di
0x18002297c  jz      short loc_1800229E4
0x18002297e  jmp     short loc_180022987
0x180022980  xor     edi, edi
0x180022982  mov     esi, 3Ah ; ':'
0x180022987  mov     rcx, [r15]; hInternet
0x18002298a  lea     r8, [rsp+2F0h+hMem]; lpBuffer
0x18002298f  mov     r9d, 18h; dwBufferLength
0x180022995  lea     edx, [r9+0Eh]; dwOption
0x180022999  call    cs:__imp_WinHttpSetOption
0x18002299f  test    eax, eax
0x1800229a1  jz      loc_180022793
0x1800229a7  mov     rbx, [rsp+2F0h+hMem+8]
0x1800229ac  test    rbx, rbx
0x1800229af  jz      short loc_1800229E4
0x1800229b1  cmp     [rbx], di
0x1800229b4  jz      short loc_1800229E4
0x1800229b6  cmp     [rbx], si
0x1800229b9  jnz     short loc_1800229C1
0x1800229bb  cmp     [rbx+2], di
0x1800229bf  jz      short loc_1800229E4
0x1800229c1  mov     edx, esi; Ch
0x1800229c3  mov     rcx, rbx; Str
0x1800229c6  call    cs:__imp_wcsrchr
0x1800229cc  test    rax, rax
0x1800229cf  jz      short loc_1800229D4
0x1800229d1  mov     [rax], di
0x1800229d4  mov     r8, r12; unsigned __int16 *
0x1800229d7  mov     [rsp+2F0h+var_2D0], r13; unsigned __int16 *
0x1800229dc  mov     rdx, rbx; unsigned __int16 *
0x1800229df  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800229e4  mov     ebx, edi
0x1800229e6  test    r14b, r14b
0x1800229e9  jz      loc_18002273D
0x1800229ef  call    cs:__imp_RevertToSelf
0x1800229f5  test    eax, eax
0x1800229f7  jnz     loc_18002273D
0x1800229fd  call    cs:__imp_GetLastError
0x180022a03  mov     ecx, eax; uExitCode
0x180022a05  call    cs:__imp_ExitProcess
```
