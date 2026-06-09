# HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)

- ea: `0x180047d38`
- end: `0x1800480e4`
- name: `?Open@HttpRequest@@QEAAXK_NPEBG11@Z`
- size: `940`
- prototype: `void __usercall(LPCWSTR pswzServerName@<rcx>, unsigned int@<edx>, bool@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800484d0`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x180022810`
- `0x18002fbb4`
- `0x180030a68`
- `0x180047d38`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048094`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048010`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048020`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048010`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048020`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047f4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047f4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004802f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004802f`
- `WINHTTP!WinHttpConnect` at `0x180047e14`
- `WINHTTP!WinHttpConnect` at `0x180047e14`
- `WINHTTP!WinHttpCreateUrl` at `0x180047f36`
- `WINHTTP!WinHttpCreateUrl` at `0x180047f92`
- `WINHTTP!WinHttpCreateUrl` at `0x180047f36`
- `WINHTTP!WinHttpCreateUrl` at `0x180047f92`
- `WINHTTP!WinHttpOpen` at `0x180047da5`
- `WINHTTP!WinHttpOpen` at `0x180047da5`
- `WINHTTP!WinHttpSetOption` at `0x180047ff5`
- `WINHTTP!WinHttpSetOption` at `0x180047ff5`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180047fd5`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180047fd5`

## string_xrefs

- `0x1800480c0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180048056`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180048082`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1800480ae`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1800480d2`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HttpRequest::Open(
        WCHAR *pswzServerName,
        DWORD a2,
        char a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *pszProxyBypassW,
        const unsigned __int16 *a6)
{
  LPCWSTR v9; // r14
  LPCWSTR v10; // rcx
  void *v11; // rbx
  const char *v12; // r9
  void *v13; // rax
  const WCHAR *v14; // rdx
  HINTERNET v15; // rbx
  const char *v16; // r9
  HINTERNET v17; // rax
  wchar_t *v18; // rax
  CHAR *v19; // rax
  CHAR *v20; // rax
  WCHAR *v21; // rbx
  __int64 v22; // rsi
  const char *v23; // r9
  const char *v24; // r9
  WCHAR *v25; // rdx
  WCHAR *v26; // rsi
  const char *v27; // r9
  signed int LastError; // eax
  int v29; // edx
  unsigned int v30; // r8d
  signed int v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  DWORD pdwUrlLength; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh]
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v37; // [rsp+58h] [rbp-A8h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v39; // [rsp+78h] [rbp-88h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pwszUrl[512]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v35 = 0;
  v9 = pswzServerName + 92;
  v10 = pswzServerName + 48;
  if ( *((_QWORD *)v10 + 3) > 7u )
    v10 = *(LPCWSTR *)v10;
  v11 = WinHttpOpen(v10, a2, a4, pszProxyBypassW, 0);
  v13 = (void *)*((_QWORD *)v9 + 1);
  if ( v11 == v13 )
  {
    v11 = (void *)*((_QWORD *)v9 + 1);
  }
  else
  {
    if ( v13 && !(**(unsigned __int8 (__fastcall ***)(LPCWSTR))v9)(v9) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v29, v30);
      __debugbreak();
    }
    *((_QWORD *)v9 + 1) = v11;
  }
  if ( !v11 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2EB,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v12);
  if ( *((_QWORD *)pswzServerName + 3) <= 7u )
    v14 = pswzServerName;
  else
    v14 = *(const WCHAR **)pswzServerName;
  v15 = WinHttpConnect(v11, v14, pswzServerName[81], 0);
  v17 = (HINTERNET)*((_QWORD *)pswzServerName + 22);
  if ( v15 == v17 )
  {
    v15 = (HINTERNET)*((_QWORD *)pswzServerName + 22);
  }
  else
  {
    if ( v17 && !(**((unsigned __int8 (__fastcall ***)(LPCWSTR))pswzServerName + 21))(pswzServerName + 84) )
    {
      v31 = GetLastError();
      if ( v31 > 0 )
        v31 = (unsigned __int16)v31 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
      __debugbreak();
    }
    *((_QWORD *)pswzServerName + 22) = v15;
  }
  if ( !v15 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2EE,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v16);
  if ( !a2 || a6 )
  {
    memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
    if ( a6 )
    {
      pAutoProxyOptions.dwFlags = 2;
      pAutoProxyOptions.lpszAutoConfigUrl = a6;
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    }
    if ( a3 )
    {
      pAutoProxyOptions.dwFlags = a6 != 0 ? 3 : 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    }
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    v18 = L"https";
    if ( !*((_BYTE *)pswzServerName + 160) )
      v18 = L"http";
    UrlComponents.lpszScheme = (LPSTR)v18;
    if ( *((_QWORD *)pswzServerName + 3) <= 7u )
      v19 = (CHAR *)pswzServerName;
    else
      v19 = *(CHAR **)pswzServerName;
    UrlComponents.lpszHostName = v19;
    UrlComponents.nPort = pswzServerName[81];
    v20 = (CHAR *)(pswzServerName + 16);
    if ( *((_QWORD *)pswzServerName + 7) > 7u )
      v20 = *(CHAR **)v20;
    UrlComponents.lpszUrlPath = v20;
    v21 = 0;
    v37 = 0;
    pdwUrlLength = 512;
    if ( WinHttpCreateUrl(&UrlComponents, 0, pwszUrl, &pdwUrlLength) )
    {
      v26 = 0;
      v25 = pwszUrl;
    }
    else
    {
      v22 = pdwUrlLength;
      v21 = (WCHAR *)LocalAlloc(0, 4LL * pdwUrlLength + 2);
      if ( v21 )
      {
        *v21 = 0;
        v21[2 * v22] = 0;
      }
      v39 = v21;
      v35 = 2;
      if ( !v21 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v23);
      v37 = v21;
      if ( !WinHttpCreateUrl(&UrlComponents, 0, v21, &pdwUrlLength) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x314,
          (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          v24);
      v25 = v21;
      v26 = v21;
    }
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    if ( WinHttpGetProxyForUrl(*((HINTERNET *)pswzServerName + 24), v25, &pAutoProxyOptions, &pProxyInfo)
      && !WinHttpSetOption(*((HINTERNET *)pswzServerName + 24), 0x26u, &pProxyInfo, 0x18u) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x31A,
        (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v27);
    }
    if ( pProxyInfo.lpszProxy )
      GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      GlobalFree(pProxyInfo.lpszProxyBypass);
    if ( v26 )
      LocalFree(v21);
  }
}

```

## disassembly

```asm
0x180047d38  push    rbp
0x180047d3a  push    rbx
0x180047d3b  push    rsi
0x180047d3c  push    rdi
0x180047d3d  push    r12
0x180047d3f  push    r14
0x180047d41  push    r15
0x180047d43  lea     rbp, [rsp-400h]
0x180047d4b  sub     rsp, 500h
0x180047d52  mov     rax, cs:__security_cookie
0x180047d59  xor     rax, rsp
0x180047d5c  mov     [rbp+430h+var_40], rax
0x180047d63  mov     rax, r9
0x180047d66  mov     r12b, r8b
0x180047d69  mov     r15d, edx
0x180047d6c  mov     rdi, rcx
0x180047d6f  mov     r9, [rbp+430h+pszProxyBypassW]; pszProxyBypassW
0x180047d76  mov     rsi, [rbp+430h+arg_28]
0x180047d7d  mov     [rsp+530h+var_4FC], 0
0x180047d85  lea     r14, [rcx+0B8h]
0x180047d8c  add     rcx, 60h ; '`'
0x180047d90  cmp     qword ptr [rcx+18h], 7
0x180047d95  jbe     short loc_180047D9A
0x180047d97  mov     rcx, [rcx]; pszAgentW
0x180047d9a  mov     [rsp+530h+dwFlags], 0; dwFlags
0x180047da2  mov     r8, rax; pszProxyW
0x180047da5  call    cs:__imp_WinHttpOpen
0x180047dab  mov     rbx, rax
0x180047dae  mov     rax, [r14+8]
0x180047db2  cmp     rbx, rax
0x180047db5  jz      short loc_180047DD8
0x180047db7  test    rax, rax
0x180047dba  jz      short loc_180047DD2
0x180047dbc  mov     rax, [r14]
0x180047dbf  mov     rcx, r14
0x180047dc2  mov     rax, [rax]
0x180047dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dca  test    al, al
0x180047dcc  jz      loc_180048068
0x180047dd2  mov     [r14+8], rbx
0x180047dd6  jmp     short loc_180047DDB
0x180047dd8  mov     rbx, rax
0x180047ddb  test    rbx, rbx
0x180047dde  setz    al
0x180047de1  mov     rcx, [rbp+438h]; this
0x180047de8  test    al, al
0x180047dea  jnz     loc_180048082
0x180047df0  lea     r14, [rdi+0A8h]
0x180047df7  cmp     qword ptr [rdi+18h], 7
0x180047dfc  jbe     short loc_180047E03
0x180047dfe  mov     rdx, [rdi]
0x180047e01  jmp     short loc_180047E06
0x180047e03  mov     rdx, rdi; pswzServerName
0x180047e06  xor     r9d, r9d; dwReserved
0x180047e09  movzx   r8d, word ptr [rdi+0A2h]; nServerPort
0x180047e11  mov     rcx, rbx; hSession
0x180047e14  call    cs:__imp_WinHttpConnect
0x180047e1a  mov     rbx, rax
0x180047e1d  mov     rax, [r14+8]
0x180047e21  cmp     rbx, rax
0x180047e24  jz      short loc_180047E47
0x180047e26  test    rax, rax
0x180047e29  jz      short loc_180047E41
0x180047e2b  mov     rcx, [r14]
0x180047e2e  mov     rax, [rcx]
0x180047e31  mov     rcx, r14
0x180047e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e39  test    al, al
0x180047e3b  jz      loc_180048094
0x180047e41  mov     [r14+8], rbx
0x180047e45  jmp     short loc_180047E4A
0x180047e47  mov     rbx, rax
0x180047e4a  test    rbx, rbx
0x180047e4d  setz    al
0x180047e50  mov     rcx, [rbp+438h]; this
0x180047e57  test    al, al
0x180047e59  jnz     loc_1800480AE
0x180047e5f  test    r15d, r15d
0x180047e62  jz      short loc_180047E6D
0x180047e64  test    rsi, rsi
0x180047e67  jz      loc_180048035
0x180047e6d  xorps   xmm0, xmm0
0x180047e70  movups  xmmword ptr [rsp+530h+pAutoProxyOptions.dwFlags], xmm0
0x180047e75  movups  xmmword ptr [rsp+530h+pAutoProxyOptions.lpvReserved], xmm0
0x180047e7a  mov     ecx, 1
0x180047e7f  lea     r14d, [rcx+1]
0x180047e83  test    rsi, rsi
0x180047e86  jz      short loc_180047E96
0x180047e88  mov     [rsp+530h+pAutoProxyOptions.dwFlags], r14d
0x180047e8d  mov     [rsp+530h+pAutoProxyOptions.lpszAutoConfigUrl], rsi
0x180047e92  mov     [rsp+530h+pAutoProxyOptions.fAutoLogonIfChallenged], ecx
0x180047e96  test    r12b, r12b
0x180047e99  jz      short loc_180047EB5
0x180047e9b  neg     rsi
0x180047e9e  sbb     eax, eax
0x180047ea0  and     eax, r14d
0x180047ea3  add     eax, ecx
0x180047ea5  mov     [rsp+530h+pAutoProxyOptions.dwFlags], eax
0x180047ea9  mov     [rsp+530h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180047eb1  mov     [rsp+530h+pAutoProxyOptions.fAutoLogonIfChallenged], ecx
0x180047eb5  mov     ebx, 68h ; 'h'
0x180047eba  mov     r8d, ebx; Size
0x180047ebd  xor     edx, edx; Val
0x180047ebf  lea     rcx, [rbp+430h+UrlComponents]; void *
0x180047ec3  call    memset_0
0x180047ec8  mov     [rbp+430h+UrlComponents.dwStructSize], ebx
0x180047ecb  lea     rcx, aHttp_0; "http"
0x180047ed2  lea     rax, aHttps_1; "https"
0x180047ed9  cmp     byte ptr [rdi+0A0h], 0
0x180047ee0  cmovz   rax, rcx
0x180047ee4  mov     [rbp+430h+UrlComponents.lpszScheme], rax
0x180047ee8  cmp     qword ptr [rdi+18h], 7
0x180047eed  jbe     short loc_180047EF4
0x180047eef  mov     rax, [rdi]
0x180047ef2  jmp     short loc_180047EF7
0x180047ef4  mov     rax, rdi
0x180047ef7  mov     [rbp+430h+UrlComponents.lpszHostName], rax
0x180047efb  movzx   eax, word ptr [rdi+0A2h]
0x180047f02  mov     [rbp+430h+UrlComponents.nPort], ax
0x180047f06  lea     rax, [rdi+20h]
0x180047f0a  cmp     qword ptr [rax+18h], 7
0x180047f0f  jbe     short loc_180047F14
0x180047f11  mov     rax, [rax]
0x180047f14  mov     [rbp+430h+UrlComponents.lpszUrlPath], rax
0x180047f18  xor     ebx, ebx
0x180047f1a  mov     [rsp+530h+var_4D8], rbx
0x180047f1f  mov     [rsp+530h+pdwUrlLength], 200h
0x180047f27  lea     r9, [rsp+530h+pdwUrlLength]; pdwUrlLength
0x180047f2c  lea     r8, [rbp+430h+pwszUrl]; pwszUrl
0x180047f30  xor     edx, edx; dwFlags
0x180047f32  lea     rcx, [rbp+430h+UrlComponents]; lpUrlComponents
0x180047f36  call    cs:__imp_WinHttpCreateUrl
0x180047f3c  test    eax, eax
0x180047f3e  jnz     short loc_180047FAF
0x180047f40  mov     esi, [rsp+530h+pdwUrlLength]
0x180047f44  lea     rdx, ds:2[rsi*4]; uBytes
0x180047f4c  xor     ecx, ecx; uFlags
0x180047f4e  call    cs:__imp_LocalAlloc
0x180047f54  mov     rbx, rax
0x180047f57  test    rax, rax
0x180047f5a  jz      short loc_180047F65
0x180047f5c  xor     eax, eax
0x180047f5e  mov     [rbx], ax
0x180047f61  mov     [rbx+rsi*4], ax
0x180047f65  mov     [rsp+530h+var_4B8], rbx
0x180047f6a  mov     [rsp+530h+var_4FC], r14d
0x180047f6f  mov     rcx, [rbp+438h]; this
0x180047f76  test    rbx, rbx
0x180047f79  jz      loc_1800480C0
0x180047f7f  mov     [rsp+530h+var_4D8], rbx
0x180047f84  lea     r9, [rsp+530h+pdwUrlLength]; pdwUrlLength
0x180047f89  mov     r8, rbx; pwszUrl
0x180047f8c  xor     edx, edx; dwFlags
0x180047f8e  lea     rcx, [rbp+430h+UrlComponents]; lpUrlComponents
0x180047f92  call    cs:__imp_WinHttpCreateUrl
0x180047f98  mov     rcx, [rbp+438h]; this
0x180047f9f  test    eax, eax
0x180047fa1  jz      loc_1800480D2
0x180047fa7  mov     rdx, rbx
0x180047faa  mov     rsi, rbx
0x180047fad  jmp     short loc_180047FB5
0x180047faf  xor     esi, esi
0x180047fb1  lea     rdx, [rbp+430h+pwszUrl]; lpcwszUrl
0x180047fb5  xorps   xmm0, xmm0
0x180047fb8  xor     eax, eax
0x180047fba  movups  xmmword ptr [rsp+530h+pProxyInfo.dwAccessType], xmm0
0x180047fbf  mov     [rsp+530h+pProxyInfo.lpszProxyBypass], rax
0x180047fc4  lea     r9, [rsp+530h+pProxyInfo]; pProxyInfo
0x180047fc9  lea     r8, [rsp+530h+pAutoProxyOptions]; pAutoProxyOptions
0x180047fce  mov     rcx, [rdi+0C0h]; hSession
0x180047fd5  call    cs:__imp_WinHttpGetProxyForUrl
0x180047fdb  test    eax, eax
0x180047fdd  jz      short loc_180048006
0x180047fdf  mov     r9d, 18h; dwBufferLength
0x180047fe5  lea     r8, [rsp+530h+pProxyInfo]; lpBuffer
0x180047fea  lea     edx, [r9+0Eh]; dwOption
0x180047fee  mov     rcx, [rdi+0C0h]; hInternet
0x180047ff5  call    cs:__imp_WinHttpSetOption
0x180047ffb  mov     rcx, [rbp+438h]; this
0x180048002  test    eax, eax
0x180048004  jz      short loc_180048056
0x180048006  mov     rcx, [rsp+530h+pProxyInfo.lpszProxy]; hMem
0x18004800b  test    rcx, rcx
0x18004800e  jz      short loc_180048016
0x180048010  call    cs:__imp_GlobalFree
0x180048016  mov     rcx, [rsp+530h+pProxyInfo.lpszProxyBypass]; hMem
0x18004801b  test    rcx, rcx
0x18004801e  jz      short loc_180048027
0x180048020  call    cs:__imp_GlobalFree
0x180048026  nop
0x180048027  test    rsi, rsi
0x18004802a  jz      short loc_180048035
0x18004802c  mov     rcx, rbx; hMem
0x18004802f  call    cs:__imp_LocalFree
0x180048035  mov     rcx, [rbp+430h+var_40]
0x18004803c  xor     rcx, rsp; StackCookie
0x18004803f  call    __security_check_cookie
0x180048044  add     rsp, 500h
0x18004804b  pop     r15
0x18004804d  pop     r14
0x18004804f  pop     r12
0x180048051  pop     rdi
0x180048052  pop     rsi
0x180048053  pop     rbx
0x180048054  pop     rbp
0x180048055  retn
0x180048056  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004805d  mov     edx, 31Ah; void *
0x180048062  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180048068  call    cs:__imp_GetLastError
0x18004806e  test    eax, eax
0x180048070  jle     short loc_18004807A
0x180048072  movzx   eax, ax
0x180048075  or      eax, 80070000h
0x18004807a  mov     ecx, eax; this
0x18004807c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180048081  int     3; Trap to Debugger
0x180048082  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048089  mov     edx, 2EBh; void *
0x18004808e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180048094  call    cs:__imp_GetLastError
0x18004809a  test    eax, eax
0x18004809c  jle     short loc_1800480A6
0x18004809e  movzx   eax, ax
0x1800480a1  or      eax, 80070000h
0x1800480a6  mov     ecx, eax; this
0x1800480a8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800480ad  int     3; Trap to Debugger
0x1800480ae  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800480b5  mov     edx, 2EEh; void *
0x1800480ba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800480c0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800480c7  mov     edx, 0FF8h; void *
0x1800480cc  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800480d2  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800480d9  mov     edx, 314h; void *
0x1800480de  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
