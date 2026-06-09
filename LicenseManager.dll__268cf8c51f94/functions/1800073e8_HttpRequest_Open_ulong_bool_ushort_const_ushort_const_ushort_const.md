# HttpRequest::Open(ulong,bool,ushort const *,ushort const *,ushort const *)

- ea: `0x1800073e8`
- end: `0x1800076fd`
- name: `?Open@HttpRequest@@QEAAXK_NPEBG11@Z`
- size: `789`
- prototype: `void __usercall(LPCWSTR pswzServerName@<rcx>, unsigned int@<edx>, bool@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000655c`

## callees

- `0x1800073e8`
- `0x1800077c0`
- `0x180044760`
- `0x180075300`
- `0x180075e60`
- `0x1800769f4`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800076b7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800076c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800076b7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800076c7`
- `WINHTTP!WinHttpOpen` at `0x18000744d`
- `WINHTTP!WinHttpOpen` at `0x18000744d`
- `WINHTTP!WinHttpSetOption` at `0x18000768a`
- `WINHTTP!WinHttpSetOption` at `0x18000768a`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000766a`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000766a`
- `WINHTTP!WinHttpCreateUrl` at `0x1800075cf`
- `WINHTTP!WinHttpCreateUrl` at `0x18000761d`
- `WINHTTP!WinHttpCreateUrl` at `0x1800075cf`
- `WINHTTP!WinHttpCreateUrl` at `0x18000761d`
- `WINHTTP!WinHttpConnect` at `0x1800074b5`
- `WINHTTP!WinHttpConnect` at `0x1800074b5`

## string_xrefs

- `0x18000747f`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1800074e7`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180007627`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x18000769b`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  void *v11; // rsi
  const char *v12; // r9
  const WCHAR *v13; // rdx
  HINTERNET v14; // rsi
  const char *v15; // r9
  wchar_t *v16; // rax
  CHAR *v17; // rax
  CHAR *v18; // rax
  WCHAR *v19; // rbx
  __int64 v20; // rdx
  const char *v21; // r9
  WCHAR *v22; // rsi
  WCHAR *v23; // rdx
  const char *v24; // r9
  DWORD pdwUrlLength; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v26; // [rsp+38h] [rbp-C8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v28; // [rsp+60h] [rbp-A0h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+68h] [rbp-98h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pwszUrl[512]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v9 = pswzServerName + 92;
  v10 = pswzServerName + 48;
  if ( *((_QWORD *)v10 + 3) > 7u )
    v10 = *(LPCWSTR *)v10;
  v11 = WinHttpOpen(v10, a2, a4, pszProxyBypassW, 0);
  if ( v11 == *((void **)v9 + 1) )
  {
    v11 = (void *)*((_QWORD *)v9 + 1);
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(v9);
    *((_QWORD *)v9 + 1) = v11;
  }
  if ( !v11 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2EB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v12);
  if ( *((_QWORD *)pswzServerName + 3) <= 7u )
    v13 = pswzServerName;
  else
    v13 = *(const WCHAR **)pswzServerName;
  v14 = WinHttpConnect(v11, v13, pswzServerName[81], 0);
  if ( v14 == *((HINTERNET *)pswzServerName + 22) )
  {
    v14 = (HINTERNET)*((_QWORD *)pswzServerName + 22);
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(pswzServerName + 84);
    *((_QWORD *)pswzServerName + 22) = v14;
  }
  if ( !v14 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v15);
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
    v16 = L"https";
    if ( !*((_BYTE *)pswzServerName + 160) )
      v16 = L"http";
    UrlComponents.lpszScheme = (LPSTR)v16;
    if ( *((_QWORD *)pswzServerName + 3) <= 7u )
      v17 = (CHAR *)pswzServerName;
    else
      v17 = *(CHAR **)pswzServerName;
    UrlComponents.lpszHostName = v17;
    UrlComponents.nPort = pswzServerName[81];
    v18 = (CHAR *)(pswzServerName + 16);
    if ( *((_QWORD *)pswzServerName + 7) > 7u )
      v18 = *(CHAR **)v18;
    UrlComponents.lpszUrlPath = v18;
    v19 = 0;
    v28 = 0;
    pdwUrlLength = 512;
    if ( WinHttpCreateUrl(&UrlComponents, 0, pwszUrl, &pdwUrlLength) )
    {
      v22 = 0;
      v23 = pwszUrl;
    }
    else
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v26,
        v20,
        2LL * pdwUrlLength);
      v19 = v26;
      v28 = v26;
      v26 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      if ( !WinHttpCreateUrl(&UrlComponents, 0, v19, &pdwUrlLength) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x314,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          v21);
      v22 = v19;
      v23 = v19;
    }
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    if ( WinHttpGetProxyForUrl(*((HINTERNET *)pswzServerName + 24), v23, &pAutoProxyOptions, &pProxyInfo)
      && !WinHttpSetOption(*((HINTERNET *)pswzServerName + 24), 0x26u, &pProxyInfo, 0x18u) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x31A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v24);
    }
    if ( pProxyInfo.lpszProxy )
      GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      GlobalFree(pProxyInfo.lpszProxyBypass);
    if ( v22 )
      LocalFree(v19);
  }
}

```

## disassembly

```asm
0x1800073e8  push    rbp
0x1800073ea  push    rbx
0x1800073eb  push    rsi
0x1800073ec  push    rdi
0x1800073ed  push    r12
0x1800073ef  push    r14
0x1800073f1  push    r15
0x1800073f3  lea     rbp, [rsp-400h]
0x1800073fb  sub     rsp, 500h
0x180007402  mov     rax, cs:__security_cookie
0x180007409  xor     rax, rsp
0x18000740c  mov     [rbp+430h+var_40], rax
0x180007413  mov     rax, r9
0x180007416  mov     r12b, r8b
0x180007419  mov     r15d, edx
0x18000741c  mov     rdi, rcx
0x18000741f  mov     r9, [rbp+430h+pszProxyBypassW]; pszProxyBypassW
0x180007426  mov     rbx, [rbp+430h+arg_28]
0x18000742d  lea     r14, [rcx+0B8h]
0x180007434  add     rcx, 60h ; '`'
0x180007438  cmp     qword ptr [rcx+18h], 7
0x18000743d  jbe     short loc_180007442
0x18000743f  mov     rcx, [rcx]; pszAgentW
0x180007442  mov     [rsp+530h+dwFlags], 0; dwFlags
0x18000744a  mov     r8, rax; pszProxyW
0x18000744d  call    cs:__imp_WinHttpOpen
0x180007453  mov     rsi, rax
0x180007456  cmp     rax, [r14+8]
0x18000745a  jz      short loc_18000746A
0x18000745c  mov     rcx, r14
0x18000745f  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x180007464  mov     [r14+8], rsi
0x180007468  jmp     short loc_18000746E
0x18000746a  mov     rsi, [r14+8]
0x18000746e  test    rsi, rsi
0x180007471  setz    al
0x180007474  mov     rcx, [rbp+438h]; this
0x18000747b  test    al, al
0x18000747d  jz      short loc_180007491
0x18000747f  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x180007486  mov     edx, 2EBh; void *
0x18000748b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180007491  lea     r14, [rdi+0A8h]
0x180007498  cmp     qword ptr [rdi+18h], 7
0x18000749d  jbe     short loc_1800074A4
0x18000749f  mov     rdx, [rdi]
0x1800074a2  jmp     short loc_1800074A7
0x1800074a4  mov     rdx, rdi; pswzServerName
0x1800074a7  xor     r9d, r9d; dwReserved
0x1800074aa  movzx   r8d, word ptr [rdi+0A2h]; nServerPort
0x1800074b2  mov     rcx, rsi; hSession
0x1800074b5  call    cs:__imp_WinHttpConnect
0x1800074bb  mov     rsi, rax
0x1800074be  cmp     rax, [r14+8]
0x1800074c2  jz      short loc_1800074D2
0x1800074c4  mov     rcx, r14
0x1800074c7  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x1800074cc  mov     [r14+8], rsi
0x1800074d0  jmp     short loc_1800074D6
0x1800074d2  mov     rsi, [r14+8]
0x1800074d6  test    rsi, rsi
0x1800074d9  setz    al
0x1800074dc  mov     rcx, [rbp+438h]; this
0x1800074e3  test    al, al
0x1800074e5  jz      short loc_1800074F9
0x1800074e7  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x1800074ee  mov     edx, 2EEh; void *
0x1800074f3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800074f9  test    r15d, r15d
0x1800074fc  jz      short loc_180007507
0x1800074fe  test    rbx, rbx
0x180007501  jz      loc_1800076DC
0x180007507  xorps   xmm0, xmm0
0x18000750a  movups  xmmword ptr [rsp+530h+pAutoProxyOptions.dwFlags], xmm0
0x18000750f  movups  xmmword ptr [rsp+530h+pAutoProxyOptions.lpvReserved], xmm0
0x180007514  mov     ecx, 1
0x180007519  test    rbx, rbx
0x18000751c  jz      short loc_18000752F
0x18000751e  mov     [rsp+530h+pAutoProxyOptions.dwFlags], 2
0x180007526  mov     [rsp+530h+pAutoProxyOptions.lpszAutoConfigUrl], rbx
0x18000752b  mov     [rsp+530h+pAutoProxyOptions.fAutoLogonIfChallenged], ecx
0x18000752f  test    r12b, r12b
0x180007532  jz      short loc_18000754E
0x180007534  neg     rbx
0x180007537  sbb     eax, eax
0x180007539  and     eax, 2
0x18000753c  add     eax, ecx
0x18000753e  mov     [rsp+530h+pAutoProxyOptions.dwFlags], eax
0x180007542  mov     [rsp+530h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18000754a  mov     [rsp+530h+pAutoProxyOptions.fAutoLogonIfChallenged], ecx
0x18000754e  mov     ebx, 68h ; 'h'
0x180007553  mov     r8d, ebx; Size
0x180007556  xor     edx, edx; Val
0x180007558  lea     rcx, [rbp+430h+UrlComponents]; void *
0x18000755c  call    memset_0
0x180007561  mov     [rbp+430h+UrlComponents.dwStructSize], ebx
0x180007564  lea     rcx, aHttp_0; "http"
0x18000756b  lea     rax, aHttps_1; "https"
0x180007572  cmp     byte ptr [rdi+0A0h], 0
0x180007579  cmovz   rax, rcx
0x18000757d  mov     [rbp+430h+UrlComponents.lpszScheme], rax
0x180007581  cmp     qword ptr [rdi+18h], 7
0x180007586  jbe     short loc_18000758D
0x180007588  mov     rax, [rdi]
0x18000758b  jmp     short loc_180007590
0x18000758d  mov     rax, rdi
0x180007590  mov     [rbp+430h+UrlComponents.lpszHostName], rax
0x180007594  movzx   eax, word ptr [rdi+0A2h]
0x18000759b  mov     [rbp+430h+UrlComponents.nPort], ax
0x18000759f  lea     rax, [rdi+20h]
0x1800075a3  cmp     qword ptr [rax+18h], 7
0x1800075a8  jbe     short loc_1800075AD
0x1800075aa  mov     rax, [rax]
0x1800075ad  mov     [rbp+430h+UrlComponents.lpszUrlPath], rax
0x1800075b1  xor     ebx, ebx
0x1800075b3  mov     [rsp+530h+var_4D0], rbx
0x1800075b8  mov     [rsp+530h+pdwUrlLength], 200h
0x1800075c0  lea     r9, [rsp+530h+pdwUrlLength]; pdwUrlLength
0x1800075c5  lea     r8, [rbp+430h+pwszUrl]; pwszUrl
0x1800075c9  xor     edx, edx; dwFlags
0x1800075cb  lea     rcx, [rbp+430h+UrlComponents]; lpUrlComponents
0x1800075cf  call    cs:__imp_WinHttpCreateUrl
0x1800075d5  test    eax, eax
0x1800075d7  jnz     short loc_180007644
0x1800075d9  mov     r8d, [rsp+530h+pdwUrlLength]
0x1800075de  add     r8, r8
0x1800075e1  lea     rcx, [rsp+530h+var_4F8]
0x1800075e6  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800075eb  mov     rbx, [rsp+530h+var_4F8]
0x1800075f0  mov     [rsp+530h+var_4D0], rbx
0x1800075f5  mov     [rsp+530h+var_4F8], 0
0x1800075fe  lea     rcx, [rsp+530h+var_4F8]
0x180007603  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180007608  mov     rsi, [rbp+438h]
0x18000760f  lea     r9, [rsp+530h+pdwUrlLength]; pdwUrlLength
0x180007614  mov     r8, rbx; pwszUrl
0x180007617  xor     edx, edx; dwFlags
0x180007619  lea     rcx, [rbp+430h+UrlComponents]; lpUrlComponents
0x18000761d  call    cs:__imp_WinHttpCreateUrl
0x180007623  test    eax, eax
0x180007625  jnz     short loc_18000763C
0x180007627  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x18000762e  mov     edx, 314h; void *
0x180007633  mov     rcx, rsi; this
0x180007636  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000763c  mov     rsi, rbx
0x18000763f  mov     rdx, rbx
0x180007642  jmp     short loc_18000764A
0x180007644  xor     esi, esi
0x180007646  lea     rdx, [rbp+430h+pwszUrl]; lpcwszUrl
0x18000764a  xorps   xmm0, xmm0
0x18000764d  xor     eax, eax
0x18000764f  movups  xmmword ptr [rsp+530h+pProxyInfo.dwAccessType], xmm0
0x180007654  mov     [rsp+530h+pProxyInfo.lpszProxyBypass], rax
0x180007659  lea     r9, [rsp+530h+pProxyInfo]; pProxyInfo
0x18000765e  lea     r8, [rsp+530h+pAutoProxyOptions]; pAutoProxyOptions
0x180007663  mov     rcx, [rdi+0C0h]; hSession
0x18000766a  call    cs:__imp_WinHttpGetProxyForUrl
0x180007670  test    eax, eax
0x180007672  jz      short loc_1800076AD
0x180007674  mov     r9d, 18h; dwBufferLength
0x18000767a  lea     r8, [rsp+530h+pProxyInfo]; lpBuffer
0x18000767f  lea     edx, [r9+0Eh]; dwOption
0x180007683  mov     rcx, [rdi+0C0h]; hInternet
0x18000768a  call    cs:__imp_WinHttpSetOption
0x180007690  mov     rcx, [rbp+438h]; this
0x180007697  test    eax, eax
0x180007699  jnz     short loc_1800076AD
0x18000769b  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x1800076a2  mov     edx, 31Ah; void *
0x1800076a7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800076ad  mov     rcx, [rsp+530h+pProxyInfo.lpszProxy]; hMem
0x1800076b2  test    rcx, rcx
0x1800076b5  jz      short loc_1800076BD
0x1800076b7  call    cs:__imp_GlobalFree
0x1800076bd  mov     rcx, [rsp+530h+pProxyInfo.lpszProxyBypass]; hMem
0x1800076c2  test    rcx, rcx
0x1800076c5  jz      short loc_1800076CE
0x1800076c7  call    cs:__imp_GlobalFree
0x1800076cd  nop
0x1800076ce  test    rsi, rsi
0x1800076d1  jz      short loc_1800076DC
0x1800076d3  mov     rcx, rbx; hMem
0x1800076d6  call    cs:__imp_LocalFree
0x1800076dc  mov     rcx, [rbp+430h+var_40]
0x1800076e3  xor     rcx, rsp; StackCookie
0x1800076e6  call    __security_check_cookie
0x1800076eb  add     rsp, 500h
0x1800076f2  pop     r15
0x1800076f4  pop     r14
0x1800076f6  pop     r12
0x1800076f8  pop     rdi
0x1800076f9  pop     rsi
0x1800076fa  pop     rbx
0x1800076fb  pop     rbp
0x1800076fc  retn
```
