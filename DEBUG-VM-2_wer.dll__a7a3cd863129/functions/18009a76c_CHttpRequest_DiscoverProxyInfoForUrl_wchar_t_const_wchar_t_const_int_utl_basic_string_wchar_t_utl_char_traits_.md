# CHttpRequest::DiscoverProxyInfoForUrl(wchar_t const *,wchar_t const *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ulong *)

- ea: `0x18009a76c`
- end: `0x18009ad42`
- name: `?DiscoverProxyInfoForUrl@CHttpRequest@@IEAAJPEB_W0HPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1PEAK@Z`
- size: `1494`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009ad48`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001fe24`
- `0x18003bf14`
- `0x180065d04`
- `0x18009a76c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009aac1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009aae3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009aac1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009aae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ab8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ab8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009acfb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009acfb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a811`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a811`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a87d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a88c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a89b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8bf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a87d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a88c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a89b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009a8bf`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009a9bf`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18009a9bf`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009aadb`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009aadb`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009a8fd`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18009a8fd`

## pseudocode

```c
__int64 __fastcall CHttpRequest::DiscoverProxyInfoForUrl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 v9; // rcx
  _DWORD *v10; // r15
  void *v11; // rcx
  DWORD v12; // eax
  unsigned int v13; // eax
  int v14; // ebx
  wchar_t *v15; // rcx
  _WORD *v17; // rcx
  _WORD *v18; // rcx
  LPWSTR lpszProxyBypass; // rdx
  wchar_t *v20; // rcx
  __int64 v21; // rdx
  int v22; // edx
  DWORD dwFlags; // eax
  const wchar_t *v24; // r8
  int v25; // eax
  wchar_t *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  BOOL ProxyForUrl; // ebx
  DWORD LastError; // eax
  unsigned int v31; // eax
  LPWSTR lpszProxy; // rdx
  DWORD v33; // eax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+30h] [rbp-89h] BYREF
  HGLOBAL v35; // [rsp+48h] [rbp-71h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG v36; // [rsp+50h] [rbp-69h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR lpcwszUrl[13]; // [rsp+90h] [rbp-29h] BYREF
  int v41; // [rsp+118h] [rbp+5Fh]

  v41 = 0;
  v9 = 0;
  v35 = 0;
  *(_OWORD *)&pProxyInfo.lpszProxy = 0;
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  memset(&v36, 0, sizeof(v36));
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, 0, a3);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  v10 = a7;
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, a2, a3);
  v11 = *(void **)(a1 + 224);
  if ( !v11 )
    goto LABEL_29;
  if ( ImpersonateLoggedOnUser(v11) )
  {
    v41 = 1;
LABEL_29:
    v17 = *(_WORD **)a5;
    *(_QWORD *)(a5 + 8) = *(_QWORD *)a5;
    *v17 = 0;
    v18 = (_WORD *)*a6;
    a6[1] = *a6;
    *v18 = 0;
    *a7 = 0;
    if ( WinHttpGetDefaultProxyConfiguration((WINHTTP_PROXY_INFO *)&pProxyInfo.lpszProxy) )
    {
      lpszProxyBypass = pProxyInfo.lpszProxyBypass;
      if ( pProxyInfo.lpszProxyBypass )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
          lpszProxyBypass = pProxyInfo.lpszProxyBypass;
        }
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a5,
                                lpszProxyBypass)
          && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a6,
                                v35) )
        {
          v14 = 0;
          *a7 = pProxyInfo.lpszProxy;
          v15 = WPP_GLOBAL_Control;
LABEL_100:
          if ( a5 && a6 && v10 && v15 != (wchar_t *)&WPP_GLOBAL_Control && (v15[14] & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)v15 + 2),
              32,
              (unsigned int)WPP_158c1c2611d1379e0dd259997317728c_Traceguids,
              *(_QWORD *)a5,
              *a6,
              *v10);
          goto LABEL_106;
        }
        v14 = -2147024882;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v21 = 23;
LABEL_40:
          WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, 2147942414LL);
          goto LABEL_106;
        }
        goto LABEL_106;
      }
    }
    if ( !WinHttpGetIEProxyConfigForCurrentUser(&v36) )
      goto LABEL_50;
    v22 = 0;
    if ( v36.fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
      v22 = 1;
    }
    else
    {
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( v36.lpszAutoConfigUrl )
    {
      pAutoProxyOptions.lpszAutoConfigUrl = v36.lpszAutoConfigUrl;
      pAutoProxyOptions.dwFlags = dwFlags | 2;
      v22 = 1;
    }
    if ( !v36.fAutoDetect && !v36.lpszAutoConfigUrl && !v36.lpszProxy )
    {
LABEL_50:
      v22 = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
    }
    pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    if ( !v22 )
      goto LABEL_77;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpcwszUrl);
    v24 = L"s";
    if ( !a4 )
      v24 = (const wchar_t *)&Src;
    v25 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpcwszUrl,
            L"http%ls://%ls/%ls",
            v24,
            a2,
            a3);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_72;
      v27 = 24;
      v28 = (unsigned int)v25;
LABEL_71:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v28);
LABEL_72:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpcwszUrl);
      goto LABEL_106;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
    GetTickCount();
    ProxyForUrl = WinHttpGetProxyForUrl(
                    *(HINTERNET *)a1,
                    lpcwszUrl[0],
                    &pAutoProxyOptions,
                    (WINHTTP_PROXY_INFO *)&pProxyInfo.lpszProxy);
    GetTickCount();
    if ( ProxyForUrl )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a5,
                               pProxyInfo.lpszProxyBypass)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a6,
                               v35) )
      {
        v14 = -2147024882;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_72;
        v27 = 27;
        v28 = 2147942414LL;
        goto LABEL_71;
      }
      *a7 = pProxyInfo.lpszProxy;
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      v31 = ERROR_HR_FROM_WIN32(LastError);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v31);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpcwszUrl);
    if ( ProxyForUrl )
    {
      v14 = 0;
    }
    else
    {
LABEL_77:
      v14 = 0;
      if ( v36.lpszProxy )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
          v15 = WPP_GLOBAL_Control;
        }
        if ( *v36.lpszProxy && (*v36.lpszProxy != 58 || v36.lpszProxy[1]) )
        {
          lpszProxy = v36.lpszProxy;
          *a7 = 3;
          if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                   a5,
                                   lpszProxy) )
          {
            v14 = -2147024882;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v21 = 30;
              goto LABEL_40;
            }
LABEL_106:
            if ( v41 && !RevertToSelf() )
            {
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v33 = GetLastError();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v33);
              }
              __fastfail(7u);
            }
            goto LABEL_17;
          }
          v15 = WPP_GLOBAL_Control;
        }
        if ( !v36.lpszProxyBypass || !*v36.lpszProxyBypass || *v36.lpszProxyBypass == 58 && !v36.lpszProxyBypass[1] )
        {
LABEL_99:
          v10 = a7;
          goto LABEL_100;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 a6,
                                 v36.lpszProxyBypass) )
        {
          v14 = -2147024882;
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v21 = 31;
            goto LABEL_40;
          }
          goto LABEL_106;
        }
      }
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_99;
  }
  v12 = GetLastError();
  v13 = ERROR_HR_FROM_WIN32(v12);
  v14 = v13;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v13);
    v15 = WPP_GLOBAL_Control;
  }
  v41 = 0;
  if ( v14 >= 0 )
    goto LABEL_100;
LABEL_17:
  if ( pProxyInfo.lpszProxyBypass )
    GlobalFree(pProxyInfo.lpszProxyBypass);
  if ( v35 )
    GlobalFree(v35);
  if ( v36.lpszAutoConfigUrl )
    GlobalFree(v36.lpszAutoConfigUrl);
  if ( v36.lpszProxy )
    GlobalFree(v36.lpszProxy);
  if ( v36.lpszProxyBypass )
    GlobalFree(v36.lpszProxyBypass);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009a76c  mov     rax, rsp
0x18009a76f  mov     [rax+20h], r9d
0x18009a773  mov     [rax+10h], rdx
0x18009a777  mov     [rax+8], rcx
0x18009a77b  push    rbp
0x18009a77c  push    rbx
0x18009a77d  push    rsi
0x18009a77e  push    rdi
0x18009a77f  push    r12
0x18009a781  push    r13
0x18009a783  push    r14
0x18009a785  push    r15
0x18009a787  lea     rbp, [rax-47h]
0x18009a78b  sub     rsp, 0B8h
0x18009a792  xorps   xmm0, xmm0
0x18009a795  xor     esi, esi
0x18009a797  xorps   xmm1, xmm1
0x18009a79a  mov     [rbp+3Fh+arg_10], esi
0x18009a79d  mov     rdi, rcx
0x18009a7a0  mov     rbx, r8
0x18009a7a3  xor     ecx, ecx
0x18009a7a5  mov     [rbp+3Fh+var_B0], rcx
0x18009a7a9  movups  xmmword ptr [rsp+0F0h+pProxyInfo.lpszProxy], xmm0
0x18009a7ae  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.dwFlags], xmm1
0x18009a7b2  movups  xmmword ptr [rbp+3Fh+pAutoProxyOptions.lpvReserved], xmm1
0x18009a7b6  movups  xmmword ptr [rbp+3Fh+var_A8], xmm0
0x18009a7ba  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x18009a7be  test    rdx, rdx
0x18009a7c1  jnz     short loc_18009A7C8
0x18009a7c3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a7c8  test    rbx, rbx
0x18009a7cb  jnz     short loc_18009A7D2
0x18009a7cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a7d2  mov     r13, [rbp+3Fh+arg_20]
0x18009a7d6  test    r13, r13
0x18009a7d9  jnz     short loc_18009A7E0
0x18009a7db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a7e0  mov     r12, [rbp+3Fh+arg_28]
0x18009a7e4  test    r12, r12
0x18009a7e7  jnz     short loc_18009A7EE
0x18009a7e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a7ee  mov     r15, [rbp+3Fh+arg_30]
0x18009a7f2  test    r15, r15
0x18009a7f5  jnz     short loc_18009A7FC
0x18009a7f7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009a7fc  mov     rcx, [rdi+0E0h]; hToken
0x18009a803  mov     edi, 1
0x18009a808  test    rcx, rcx
0x18009a80b  jz      loc_18009A8DE
0x18009a811  call    cs:__imp_ImpersonateLoggedOnUser
0x18009a817  test    eax, eax
0x18009a819  jnz     loc_18009A8DB
0x18009a81f  call    cs:__imp_GetLastError
0x18009a825  mov     ecx, eax; unsigned int
0x18009a827  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009a82c  mov     ebx, eax
0x18009a82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a835  lea     rsi, WPP_GLOBAL_Control
0x18009a83c  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009a843  cmp     rcx, rsi
0x18009a846  jz      short loc_18009A867
0x18009a848  test    [rcx+1Ch], dil
0x18009a84c  jz      short loc_18009A867
0x18009a84e  mov     rcx, [rcx+10h]
0x18009a852  lea     edx, [rdi+14h]
0x18009a855  mov     r9d, eax
0x18009a858  mov     r8, r14
0x18009a85b  call    WPP_SF_d
0x18009a860  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a867  xor     edx, edx
0x18009a869  mov     [rbp+3Fh+arg_10], edx
0x18009a86c  test    ebx, ebx
0x18009a86e  jns     loc_18009ACAF
0x18009a874  mov     rcx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]; hMem
0x18009a878  test    rcx, rcx
0x18009a87b  jz      short loc_18009A883
0x18009a87d  call    cs:__imp_GlobalFree
0x18009a883  mov     rcx, [rbp+3Fh+var_B0]; hMem
0x18009a887  test    rcx, rcx
0x18009a88a  jz      short loc_18009A892
0x18009a88c  call    cs:__imp_GlobalFree
0x18009a892  mov     rcx, [rbp+3Fh+var_A8+8]; hMem
0x18009a896  test    rcx, rcx
0x18009a899  jz      short loc_18009A8A1
0x18009a89b  call    cs:__imp_GlobalFree
0x18009a8a1  mov     rax, [rbp+3Fh+var_98]
0x18009a8a5  test    rax, rax
0x18009a8a8  jz      short loc_18009A8B3
0x18009a8aa  mov     rcx, rax; hMem
0x18009a8ad  call    cs:__imp_GlobalFree
0x18009a8b3  mov     rax, [rbp+3Fh+var_98+8]
0x18009a8b7  test    rax, rax
0x18009a8ba  jz      short loc_18009A8C5
0x18009a8bc  mov     rcx, rax; hMem
0x18009a8bf  call    cs:__imp_GlobalFree
0x18009a8c5  mov     eax, ebx
0x18009a8c7  add     rsp, 0B8h
0x18009a8ce  pop     r15
0x18009a8d0  pop     r14
0x18009a8d2  pop     r13
0x18009a8d4  pop     r12
0x18009a8d6  pop     rdi
0x18009a8d7  pop     rsi
0x18009a8d8  pop     rbx
0x18009a8d9  pop     rbp
0x18009a8da  retn
0x18009a8db  mov     [rbp+3Fh+arg_10], edi
0x18009a8de  mov     rcx, [r13+0]
0x18009a8e2  mov     [r13+8], rcx
0x18009a8e6  mov     [rcx], si
0x18009a8e9  mov     rcx, [r12]
0x18009a8ed  mov     [r12+8], rcx
0x18009a8f2  mov     [rcx], si
0x18009a8f5  lea     rcx, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009a8fa  mov     [r15], esi
0x18009a8fd  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18009a903  test    eax, eax
0x18009a905  jz      loc_18009A9BB
0x18009a90b  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009a90f  test    rdx, rdx
0x18009a912  jz      loc_18009A9BB
0x18009a918  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a91f  lea     rsi, WPP_GLOBAL_Control
0x18009a926  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009a92d  cmp     rcx, rsi
0x18009a930  jz      short loc_18009A94D
0x18009a932  test    byte ptr [rcx+1Ch], 4
0x18009a936  jz      short loc_18009A94D
0x18009a938  mov     rcx, [rcx+10h]
0x18009a93c  mov     edx, 16h
0x18009a941  mov     r8, r14
0x18009a944  call    WPP_SF_
0x18009a949  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009a94d  mov     rcx, r13
0x18009a950  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009a955  test    al, al
0x18009a957  jz      short loc_18009A980
0x18009a959  mov     rdx, [rbp+3Fh+var_B0]
0x18009a95d  mov     rcx, r12
0x18009a960  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009a965  xor     edx, edx
0x18009a967  test    al, al
0x18009a969  jz      short loc_18009A980
0x18009a96b  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009a96f  mov     ebx, edx
0x18009a971  mov     [r15], eax
0x18009a974  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a97b  jmp     loc_18009ACAF
0x18009a980  mov     ebx, 8007000Eh
0x18009a985  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a98c  cmp     rcx, rsi
0x18009a98f  jz      loc_18009ACEE
0x18009a995  test    [rcx+1Ch], dil
0x18009a999  jz      loc_18009ACEE
0x18009a99f  mov     edx, 17h
0x18009a9a4  mov     rcx, [rcx+10h]
0x18009a9a8  mov     r9d, 8007000Eh
0x18009a9ae  mov     r8, r14
0x18009a9b1  call    WPP_SF_d
0x18009a9b6  jmp     loc_18009ACEE
0x18009a9bb  lea     rcx, [rbp+3Fh+var_A8]; pProxyConfig
0x18009a9bf  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18009a9c5  mov     r15d, 3
0x18009a9cb  test    eax, eax
0x18009a9cd  jz      short loc_18009AA10
0x18009a9cf  mov     r8d, dword ptr [rbp+3Fh+var_A8]
0x18009a9d3  mov     edx, esi
0x18009a9d5  test    r8d, r8d
0x18009a9d8  jz      short loc_18009A9E7
0x18009a9da  mov     eax, edi
0x18009a9dc  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009a9e0  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009a9e3  mov     edx, edi
0x18009a9e5  jmp     short loc_18009A9EA
0x18009a9e7  mov     eax, [rbp+3Fh+pAutoProxyOptions.dwFlags]
0x18009a9ea  mov     rcx, [rbp+3Fh+var_A8+8]
0x18009a9ee  test    rcx, rcx
0x18009a9f1  jz      short loc_18009A9FF
0x18009a9f3  or      eax, 2
0x18009a9f6  mov     [rbp+3Fh+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x18009a9fa  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], eax
0x18009a9fd  mov     edx, edi
0x18009a9ff  test    r8d, r8d
0x18009aa02  jnz     short loc_18009AA19
0x18009aa04  cmp     [rbp+3Fh+var_A8+8], rsi
0x18009aa08  jnz     short loc_18009AA19
0x18009aa0a  cmp     [rbp+3Fh+var_98], rsi
0x18009aa0e  jnz     short loc_18009AA19
0x18009aa10  mov     edx, edi
0x18009aa12  mov     [rbp+3Fh+pAutoProxyOptions.dwAutoDetectFlags], r15d
0x18009aa16  mov     [rbp+3Fh+pAutoProxyOptions.dwFlags], edi
0x18009aa19  mov     [rbp+3Fh+pAutoProxyOptions.fAutoLogonIfChallenged], edi
0x18009aa1c  lea     rsi, WPP_GLOBAL_Control
0x18009aa23  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009aa2a  test    edx, edx
0x18009aa2c  jz      loc_18009ABC7
0x18009aa32  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009aa36  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009aa3b  cmp     [rbp+3Fh+arg_18], 0
0x18009aa3f  lea     rax, Src
0x18009aa46  mov     r9, [rbp+3Fh+arg_8]
0x18009aa4a  lea     r8, aS_1; "s"
0x18009aa51  cmovz   r8, rax
0x18009aa55  mov     qword ptr [rsp+0F0h+var_D0], rbx
0x18009aa5a  lea     rdx, aHttpLsLsLs; "http%ls://%ls/%ls"
0x18009aa61  lea     rcx, [rbp+3Fh+lpcwszUrl]
0x18009aa65  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18009aa6a  mov     ebx, eax
0x18009aa6c  test    eax, eax
0x18009aa6e  jns     short loc_18009AA9E
0x18009aa70  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aa77  lea     r14, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009aa7e  cmp     rcx, rsi
0x18009aa81  jz      loc_18009AB6E
0x18009aa87  test    [rcx+1Ch], dil
0x18009aa8b  jz      loc_18009AB6E
0x18009aa91  mov     edx, 18h
0x18009aa96  mov     r9d, eax
0x18009aa99  jmp     loc_18009AB62
0x18009aa9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aaa5  cmp     rcx, rsi
0x18009aaa8  jz      short loc_18009AAC1
0x18009aaaa  test    byte ptr [rcx+1Ch], 4
0x18009aaae  jz      short loc_18009AAC1
0x18009aab0  mov     rcx, [rcx+10h]
0x18009aab4  mov     edx, 19h
0x18009aab9  mov     r8, r14
0x18009aabc  call    WPP_SF_
0x18009aac1  call    cs:__imp_GetTickCount
0x18009aac7  mov     rcx, [rbp+3Fh+arg_0]
0x18009aacb  lea     r9, [rsp+0F0h+pProxyInfo.lpszProxy]; pProxyInfo
0x18009aad0  mov     rdx, [rbp+3Fh+lpcwszUrl]; lpcwszUrl
0x18009aad4  lea     r8, [rbp+3Fh+pAutoProxyOptions]; pAutoProxyOptions
0x18009aad8  mov     rcx, [rcx]; hSession
0x18009aadb  call    cs:__imp_WinHttpGetProxyForUrl
0x18009aae1  mov     ebx, eax
0x18009aae3  call    cs:__imp_GetTickCount
0x18009aae9  test    ebx, ebx
0x18009aaeb  jz      loc_18009AB7C
0x18009aaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aaf8  cmp     rcx, rsi
0x18009aafb  jz      short loc_18009AB14
0x18009aafd  test    byte ptr [rcx+1Ch], 4
0x18009ab01  jz      short loc_18009AB14
0x18009ab03  mov     rcx, [rcx+10h]
0x18009ab07  mov     edx, 1Ah
0x18009ab0c  mov     r8, r14
0x18009ab0f  call    WPP_SF_
0x18009ab14  mov     rdx, [rbp+3Fh+pProxyInfo.lpszProxyBypass]
0x18009ab18  mov     rcx, r13
0x18009ab1b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009ab20  test    al, al
0x18009ab22  jz      short loc_18009AB40
0x18009ab24  mov     rdx, [rbp+3Fh+var_B0]
0x18009ab28  mov     rcx, r12
0x18009ab2b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009ab30  test    al, al
0x18009ab32  jz      short loc_18009AB40
0x18009ab34  mov     rcx, [rbp+3Fh+arg_30]
0x18009ab38  mov     eax, dword ptr [rsp+0F0h+pProxyInfo.lpszProxy]
0x18009ab3c  mov     [rcx], eax
0x18009ab3e  jmp     short loc_18009ABB6
0x18009ab40  mov     ebx, 8007000Eh
0x18009ab45  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ab4c  cmp     rcx, rsi
0x18009ab4f  jz      short loc_18009AB6E
0x18009ab51  test    [rcx+1Ch], dil
0x18009ab55  jz      short loc_18009AB6E
0x18009ab57  mov     edx, 1Bh
0x18009ab5c  mov     r9d, 8007000Eh
0x18009ab62  mov     rcx, [rcx+10h]
0x18009ab66  mov     r8, r14
0x18009ab69  call    WPP_SF_d
0x18009ab6e  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009ab72  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009ab77  jmp     loc_18009ACEE
0x18009ab7c  mov     rax, cs:WPP_GLOBAL_Control
0x18009ab83  cmp     rax, rsi
0x18009ab86  jz      short loc_18009ABB6
0x18009ab88  test    [rax+1Ch], dil
0x18009ab8c  jz      short loc_18009ABB6
0x18009ab8e  call    cs:__imp_GetLastError
0x18009ab94  mov     ecx, eax; unsigned int
0x18009ab96  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009ab9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aba2  mov     edx, 1Ch
0x18009aba7  mov     r9d, eax
0x18009abaa  mov     r8, r14
0x18009abad  mov     rcx, [rcx+10h]
0x18009abb1  call    WPP_SF_d
0x18009abb6  lea     rcx, [rbp+3Fh+lpcwszUrl]; void *
0x18009abba  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009abbf  test    ebx, ebx
0x18009abc1  jnz     loc_18009ACA2
0x18009abc7  xor     ebx, ebx
0x18009abc9  cmp     [rbp+3Fh+var_98], rbx
0x18009abcd  jz      loc_18009ACA4
0x18009abd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009abda  cmp     rcx, rsi
0x18009abdd  jz      short loc_18009ABFB
  ... truncated ...
```
