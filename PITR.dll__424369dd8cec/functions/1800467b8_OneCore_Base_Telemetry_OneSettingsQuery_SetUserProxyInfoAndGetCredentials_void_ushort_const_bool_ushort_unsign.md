# OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x1800467b8`
- end: `0x180046b4c`
- name: `?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z`
- size: `916`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044318`

## callees

- `0x18001c5bc`
- `0x180041980`
- `0x180041b50`
- `0x1800467b8`
- `0x180050300`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180046b06`
- `msvcrt!wcsrchr` at `0x180046b06`
- `msvcrt!_wcsnicmp` at `0x18004698a`
- `msvcrt!_wcsnicmp` at `0x18004698a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800468d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b3d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180046b45`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x180046b45`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046b2f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046b2f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004685e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004685e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046952`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004696b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a25`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a3f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a71`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a86`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046952`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004696b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a25`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a3f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a71`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180046a86`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800468be`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800468be`
- `WINHTTP!WinHttpSetOption` at `0x180046ad9`
- `WINHTTP!WinHttpSetOption` at `0x180046ad9`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800469d5`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800469d5`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180046a96`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180046a96`

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
0x1800467b8  mov     [rsp-8+arg_0], rbx
0x1800467bd  push    rbp
0x1800467be  push    rsi
0x1800467bf  push    rdi
0x1800467c0  push    r12
0x1800467c2  push    r13
0x1800467c4  push    r14
0x1800467c6  push    r15
0x1800467c8  lea     rbp, [rsp-1C0h]
0x1800467d0  sub     rsp, 2C0h
0x1800467d7  mov     rax, cs:__security_cookie
0x1800467de  xor     rax, rsp
0x1800467e1  mov     [rbp+1F0h+var_40], rax
0x1800467e8  mov     r12, [rbp+1F0h+arg_20]
0x1800467ef  xor     edi, edi
0x1800467f1  mov     r13, [rbp+1F0h+arg_30]
0x1800467f8  xorps   xmm0, xmm0
0x1800467fb  xor     eax, eax
0x1800467fd  mov     [rsp+2F0h+hToken], rdi
0x180046802  mov     [rsp+2F0h+var_2A8], edi
0x180046806  xorps   xmm1, xmm1
0x180046809  mov     [r12], di
0x18004680e  mov     rsi, r8
0x180046811  mov     [r13+0], di
0x180046816  mov     r15, rdx
0x180046819  mov     [rsp+2F0h+var_2B0], rax
0x18004681e  mov     r14b, dil
0x180046821  movups  xmmword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], xmm0
0x180046826  movups  xmmword ptr [rbp+1F0h+pAutoProxyOptions.lpvReserved], xmm0
0x18004682a  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm1
0x18004682f  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm1
0x180046834  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x180046839  test    r9b, r9b
0x18004683c  jnz     short loc_1800468AC
0x18004683e  lea     r8, [rsp+2F0h+var_2A8]; int *
0x180046843  lea     rdx, [rsp+2F0h+hToken]; void **
0x180046848  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x18004684d  mov     ebx, eax
0x18004684f  test    eax, eax
0x180046851  js      short loc_18004687D
0x180046853  cmp     [rsp+2F0h+var_2A8], edi
0x180046857  jz      short loc_1800468AC
0x180046859  mov     rcx, [rsp+2F0h+hToken]; hToken
0x18004685e  call    cs:__imp_ImpersonateLoggedOnUser
0x180046864  test    eax, eax
0x180046866  jnz     short loc_1800468A9
0x180046868  call    cs:__imp_GetLastError
0x18004686e  mov     ebx, eax
0x180046870  test    eax, eax
0x180046872  jle     short loc_18004687D
0x180046874  movzx   ebx, ax
0x180046877  or      ebx, 80070000h
0x18004687d  mov     eax, ebx
0x18004687f  mov     rcx, [rbp+1F0h+var_40]
0x180046886  xor     rcx, rsp; StackCookie
0x180046889  call    __security_check_cookie
0x18004688e  mov     rbx, [rsp+2F0h+arg_0]
0x180046896  add     rsp, 2C0h
0x18004689d  pop     r15
0x18004689f  pop     r14
0x1800468a1  pop     r13
0x1800468a3  pop     r12
0x1800468a5  pop     rdi
0x1800468a6  pop     rsi
0x1800468a7  pop     rbp
0x1800468a8  retn
0x1800468a9  mov     r14b, 1
0x1800468ac  xorps   xmm0, xmm0
0x1800468af  lea     rcx, [rsp+2F0h+pProxyConfig]; pProxyConfig
0x1800468b4  movups  xmmword ptr [rsp+2F0h+pProxyConfig.fAutoDetect], xmm0
0x1800468b9  movups  xmmword ptr [rsp+2F0h+pProxyConfig.lpszProxy], xmm0
0x1800468be  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800468c4  test    eax, eax
0x1800468c6  jnz     short loc_1800468F1
0x1800468c8  call    cs:__imp_GetLastError
0x1800468ce  cmp     eax, 2
0x1800468d1  jz      short loc_1800468F1
0x1800468d3  call    cs:__imp_GetLastError
0x1800468d9  mov     ebx, eax
0x1800468db  test    eax, eax
0x1800468dd  jle     loc_180046B26
0x1800468e3  movzx   ebx, ax
0x1800468e6  or      ebx, 80070000h
0x1800468ec  jmp     loc_180046B26
0x1800468f1  mov     bl, dil
0x1800468f4  xor     eax, eax
0x1800468f6  test    eax, eax
0x1800468f8  jnz     loc_180046AC0
0x1800468fe  test    rdi, rdi
0x180046901  jz      short loc_18004691B
0x180046903  call    cs:__imp_GetLastError
0x180046909  cmp     eax, 2EEFh
0x18004690e  jnz     loc_1800469F6
0x180046914  mov     [rbp+1F0h+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x18004691b  mov     rax, [rsp+2F0h+pProxyConfig.lpszAutoConfigUrl]
0x180046920  mov     [rbp+1F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x180046924  test    rax, rax
0x180046927  jnz     short loc_18004693B
0x180046929  mov     [rsp+2F0h+pAutoProxyOptions.dwFlags], 1
0x180046931  mov     [rsp+2F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180046939  jmp     short loc_180046944
0x18004693b  mov     qword ptr [rsp+2F0h+pAutoProxyOptions.dwFlags], 2
0x180046944  test    bl, bl
0x180046946  jz      short loc_18004697A
0x180046948  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18004694d  test    rcx, rcx
0x180046950  jz      short loc_180046961
0x180046952  call    cs:__imp_GlobalFree
0x180046958  mov     [rsp+2F0h+hMem+8], 0
0x180046961  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180046966  test    rcx, rcx
0x180046969  jz      short loc_18004697A
0x18004696b  call    cs:__imp_GlobalFree
0x180046971  mov     [rsp+2F0h+var_2B0], 0
0x18004697a  mov     r8d, 8; MaxCount
0x180046980  lea     rdx, aHttps; "https://"
0x180046987  mov     rcx, rsi; String1
0x18004698a  call    cs:__imp__wcsnicmp
0x180046990  test    eax, eax
0x180046992  jz      short loc_1800469C5
0x180046994  lea     r9, aHttps; "https://"
0x18004699b  mov     [rsp+2F0h+var_2D0], rsi
0x1800469a0  lea     r8, aLsLs; "%ls%ls"
0x1800469a7  mov     edx, 104h; unsigned __int64
0x1800469ac  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x1800469b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800469b5  mov     ebx, eax
0x1800469b7  test    eax, eax
0x1800469b9  js      loc_180046B26
0x1800469bf  lea     rdx, [rbp+1F0h+var_250]
0x1800469c3  jmp     short loc_1800469C8
0x1800469c5  mov     rdx, rsi; lpcwszUrl
0x1800469c8  mov     rcx, [r15]; hSession
0x1800469cb  lea     r9, [rsp+2F0h+hMem]; pProxyInfo
0x1800469d0  lea     r8, [rsp+2F0h+pAutoProxyOptions]; pAutoProxyOptions
0x1800469d5  call    cs:__imp_WinHttpGetProxyForUrl
0x1800469db  inc     rdi
0x1800469de  mov     bl, 1
0x1800469e0  cmp     rdi, 2
0x1800469e4  jb      loc_1800468F6
0x1800469ea  xor     edi, edi
0x1800469ec  test    eax, eax
0x1800469ee  jnz     loc_180046AC2
0x1800469f4  jmp     short loc_1800469F8
0x1800469f6  xor     edi, edi
0x1800469f8  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x1800469fd  mov     esi, 3Ah ; ':'
0x180046a02  test    rax, rax
0x180046a05  jz      short loc_180046A63
0x180046a07  cmp     [rax], di
0x180046a0a  jz      short loc_180046A63
0x180046a0c  cmp     [rax], si
0x180046a0f  jnz     short loc_180046A17
0x180046a11  cmp     [rax+2], di
0x180046a15  jz      short loc_180046A63
0x180046a17  test    bl, bl
0x180046a19  jz      short loc_180046A4A
0x180046a1b  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180046a20  test    rcx, rcx
0x180046a23  jz      short loc_180046A35
0x180046a25  call    cs:__imp_GlobalFree
0x180046a2b  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180046a30  mov     [rsp+2F0h+hMem+8], rdi
0x180046a35  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180046a3a  test    rcx, rcx
0x180046a3d  jz      short loc_180046A4A
0x180046a3f  call    cs:__imp_GlobalFree
0x180046a45  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxy]
0x180046a4a  mov     [rsp+2F0h+hMem+8], rax
0x180046a4f  mov     rax, [rsp+2F0h+pProxyConfig.lpszProxyBypass]
0x180046a54  mov     [rsp+2F0h+var_2B0], rax
0x180046a59  mov     dword ptr [rsp+2F0h+hMem], 3
0x180046a61  jmp     short loc_180046AC7
0x180046a63  test    bl, bl
0x180046a65  jz      short loc_180046A91
0x180046a67  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x180046a6c  test    rcx, rcx
0x180046a6f  jz      short loc_180046A7C
0x180046a71  call    cs:__imp_GlobalFree
0x180046a77  mov     [rsp+2F0h+hMem+8], rdi
0x180046a7c  mov     rcx, [rsp+2F0h+var_2B0]; hMem
0x180046a81  test    rcx, rcx
0x180046a84  jz      short loc_180046A91
0x180046a86  call    cs:__imp_GlobalFree
0x180046a8c  mov     [rsp+2F0h+var_2B0], rdi
0x180046a91  lea     rcx, [rsp+2F0h+hMem]; pProxyInfo
0x180046a96  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180046a9c  test    eax, eax
0x180046a9e  jz      loc_1800468D3
0x180046aa4  mov     rax, [rsp+2F0h+hMem+8]
0x180046aa9  test    rax, rax
0x180046aac  jz      short loc_180046B24
0x180046aae  cmp     [rax], di
0x180046ab1  jz      short loc_180046B24
0x180046ab3  cmp     [rax], si
0x180046ab6  jnz     short loc_180046AC7
0x180046ab8  cmp     [rax+2], di
0x180046abc  jz      short loc_180046B24
0x180046abe  jmp     short loc_180046AC7
0x180046ac0  xor     edi, edi
0x180046ac2  mov     esi, 3Ah ; ':'
0x180046ac7  mov     rcx, [r15]; hInternet
0x180046aca  lea     r8, [rsp+2F0h+hMem]; lpBuffer
0x180046acf  mov     r9d, 18h; dwBufferLength
0x180046ad5  lea     edx, [r9+0Eh]; dwOption
0x180046ad9  call    cs:__imp_WinHttpSetOption
0x180046adf  test    eax, eax
0x180046ae1  jz      loc_1800468D3
0x180046ae7  mov     rbx, [rsp+2F0h+hMem+8]
0x180046aec  test    rbx, rbx
0x180046aef  jz      short loc_180046B24
0x180046af1  cmp     [rbx], di
0x180046af4  jz      short loc_180046B24
0x180046af6  cmp     [rbx], si
0x180046af9  jnz     short loc_180046B01
0x180046afb  cmp     [rbx+2], di
0x180046aff  jz      short loc_180046B24
0x180046b01  mov     edx, esi; Ch
0x180046b03  mov     rcx, rbx; Str
0x180046b06  call    cs:__imp_wcsrchr
0x180046b0c  test    rax, rax
0x180046b0f  jz      short loc_180046B14
0x180046b11  mov     [rax], di
0x180046b14  mov     r8, r12; unsigned __int16 *
0x180046b17  mov     [rsp+2F0h+var_2D0], r13; unsigned __int16 *
0x180046b1c  mov     rdx, rbx; unsigned __int16 *
0x180046b1f  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180046b24  mov     ebx, edi
0x180046b26  test    r14b, r14b
0x180046b29  jz      loc_18004687D
0x180046b2f  call    cs:__imp_RevertToSelf
0x180046b35  test    eax, eax
0x180046b37  jnz     loc_18004687D
0x180046b3d  call    cs:__imp_GetLastError
0x180046b43  mov     ecx, eax; uExitCode
0x180046b45  call    cs:__imp_ExitProcess
```
