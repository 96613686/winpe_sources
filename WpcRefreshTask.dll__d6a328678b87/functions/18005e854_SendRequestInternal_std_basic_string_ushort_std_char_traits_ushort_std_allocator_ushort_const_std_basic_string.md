# SendRequestInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::function<void (void *)>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,ushort)

- ea: `0x18005e854`
- end: `0x18005ee6f`
- name: `?SendRequestInternal@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@V?$function@$$A6AXPEAX@Z@2@0_NG@Z`
- size: `1563`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pswzServerName@<rcx>, LPCWSTR pwszObjectName@<rdx>, __int64, LPCWSTR pwszVerb, char, __int16)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x18005e360`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x18000947c`
- `0x180009a18`
- `0x180009a80`
- `0x18000bba8`
- `0x18000ec98`
- `0x18000ecc0`
- `0x18000fef0`
- `0x1800357c0`
- `0x180035e0c`
- `0x180037750`
- `0x18005b514`
- `0x18005b5b0`
- `0x18005b64c`
- `0x18005cef4`
- `0x18005e854`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005eba7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005eba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee3e`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005eb86`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005eb86`
- `WINHTTP!WinHttpOpen` at `0x18005e8d4`
- `WINHTTP!WinHttpOpen` at `0x18005e8d4`
- `WINHTTP!WinHttpSendRequest` at `0x18005eb71`
- `WINHTTP!WinHttpSendRequest` at `0x18005eb71`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18005ea9f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18005ea9f`
- `WINHTTP!WinHttpOpenRequest` at `0x18005e9c9`
- `WINHTTP!WinHttpOpenRequest` at `0x18005e9c9`
- `WINHTTP!WinHttpConnect` at `0x18005e95a`
- `WINHTTP!WinHttpConnect` at `0x18005e95a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SendRequestInternal(
        _QWORD *pswzServerName,
        const WCHAR *pwszObjectName,
        _QWORD *a3,
        __int64 ***a4,
        __int64 a5,
        LPCWSTR pwszVerb,
        unsigned __int8 a7,
        INTERNET_PORT a8)
{
  const WCHAR *v10; // rdi
  INTERNET_PORT v11; // r15
  _QWORD *v12; // r9
  __int64 *v13; // rbx
  Private::Format *v14; // rax
  Private::Format *v15; // rax
  Private::Format *v16; // rax
  __int64 v17; // rax
  BOOL v18; // edi
  __int64 **v19; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v22; // rax
  LPVOID *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rbx
  signed int v28; // eax
  signed int LastError; // eax
  unsigned int v30; // ebx
  signed int v31; // eax
  unsigned int v32; // ebx
  signed int v33; // eax
  unsigned int v34; // ebx
  signed int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rbx
  signed int v38; // eax
  HINTERNET hRequest; // [rsp+40h] [rbp-C0h] BYREF
  HINTERNET *p_hSession; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v41; // [rsp+50h] [rbp-B0h] BYREF
  HINTERNET hSession; // [rsp+58h] [rbp-A8h] BYREF
  HINTERNET hConnect; // [rsp+60h] [rbp-A0h] BYREF
  __int64 ***v44; // [rsp+68h] [rbp-98h]
  __int128 v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  char *v49[5]; // [rsp+98h] [rbp-68h] BYREF
  LPVOID lpOptional[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD dwOptionalLength[2]; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-28h]
  char *pExceptionObject[8]; // [rsp+E0h] [rbp-20h] BYREF
  char *v54[4]; // [rsp+120h] [rbp+20h] BYREF
  char *v55[4]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v56[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v57[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v58[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v44 = a4;
  v41 = a3;
  v10 = pwszVerb;
  v48 = a5;
  v11 = a8;
  if ( !a8 )
  {
    v11 = 443;
    if ( !a7 )
      v11 = 80;
  }
  hSession = WinHttpOpen(0, 4u, 0, 0, 0);
  if ( !hSession )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v30);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hSession;
  ScopeGuard::ScopeGuard__lambda_dff20fe531c161d312228c3011b1ee86___(v58, &p_hSession);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( pswzServerName[3] <= 7u )
      v12 = pswzServerName;
    else
      v12 = (_QWORD *)*pswzServerName;
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v12);
  }
  if ( pswzServerName[3] > 7u )
    pswzServerName = (_QWORD *)*pswzServerName;
  hConnect = WinHttpConnect(hSession, (LPCWSTR)pswzServerName, v11, 0);
  if ( !hConnect )
  {
    v31 = GetLastError();
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v32);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v32);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hConnect;
  ScopeGuard::ScopeGuard__lambda_a37f6ebc28d708e5d633bdd02f7a3cad___(v57, &p_hSession);
  if ( *((_QWORD *)pwszObjectName + 3) > 7u )
    pwszObjectName = *(const WCHAR **)pwszObjectName;
  if ( *((_QWORD *)pwszVerb + 3) > 7u )
    v10 = *(const WCHAR **)pwszVerb;
  hRequest = WinHttpOpenRequest(hConnect, v10, pwszObjectName, 0, 0, 0, a7 << 23);
  if ( !hRequest )
  {
    v33 = GetLastError();
    v34 = v33;
    if ( v33 > 0 )
      v34 = (unsigned __int16)v33 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v49, v34);
    throw (ErrorCodeException *)v49;
  }
  p_hSession = &hRequest;
  ScopeGuard::ScopeGuard__lambda_bf43a75a91dfa73a8e629cdbcec234d7___(v56, &p_hSession);
  v13 = **v44;
  while ( !*((_BYTE *)v13 + 25) )
  {
    std::wstring::wstring((__int64)v54, (__int64)(v13 + 4));
    std::wstring::wstring((__int64)v55, (__int64)(v13 + 8));
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v45, L"{0}: {1}", 8u);
    v14 = (Private::Format *)StringAlgo::FormatString(pExceptionObject, &v45);
    v15 = Private::Format::operator%<std::wstring>(v14, (__int64)v54);
    v16 = Private::Format::operator%<std::wstring>(v15, (__int64)v55);
    v17 = std::wstring::wstring((__int64)v49, (__int64)v16);
    if ( *(_QWORD *)(v17 + 24) > 7u )
      v17 = *(_QWORD *)v17;
    v18 = WinHttpAddRequestHeaders(hRequest, (LPCWSTR)v17, 0xFFFFFFFF, 0);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(pExceptionObject);
    if ( !v18 )
    {
      v35 = GetLastError();
      v36 = v35;
      if ( v35 > 0 )
        v36 = (unsigned __int16)v35 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v36);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v36);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v54);
    v19 = (__int64 **)v13[2];
    if ( *((_BYTE *)v19 + 25) )
    {
      for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v13 = i;
      v13 = i;
    }
    else
    {
      v13 = (__int64 *)v13[2];
      for ( j = *v19; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v13 = j;
    }
  }
  v22 = v41;
  if ( v41[3] > 7u )
    v22 = (_QWORD *)*v41;
  StringAlgo::ToUtf8(lpOptional, v22);
  if ( *(_QWORD *)dwOptionalLength > 0xFFFFFFFF )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147024809);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v23 = lpOptional;
  if ( v52 > 0xF )
    v23 = (LPVOID *)lpOptional[0];
  if ( !WinHttpSendRequest(hRequest, 0, 0, v23, dwOptionalLength[0], dwOptionalLength[0], 0) )
  {
    v37 = std::wstring::wstring(v49, L"SendRequest");
    v38 = GetLastError();
    if ( v38 > 0 )
      v38 = (unsigned __int16)v38 | 0x80070000;
    MessageException::MessageException(pExceptionObject, (unsigned int)v38, v37);
    throw (MessageException *)pExceptionObject;
  }
  if ( !WinHttpReceiveResponse(hRequest, 0) )
  {
    v27 = std::wstring::wstring(v49, L"ReceiveResponse");
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    MessageException::MessageException(pExceptionObject, (unsigned int)v28, v27);
    throw (MessageException *)pExceptionObject;
  }
  v41 = hRequest;
  v24 = *(_QWORD *)(a5 + 56);
  if ( !v24 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v24 + 16LL))(v24, &v41);
  std::string::~string((char **)lpOptional);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v56);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v57);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v58);
  v26 = *(_QWORD *)(a5 + 56);
  if ( v26 )
  {
    LOBYTE(v25) = v26 != a5;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 32LL))(v26, v25);
    *(_QWORD *)(a5 + 56) = 0;
  }
}

```

## disassembly

```asm
0x18005e854  push    rbp
0x18005e856  push    rbx
0x18005e857  push    rsi
0x18005e858  push    rdi
0x18005e859  push    r12
0x18005e85b  push    r13
0x18005e85d  push    r15
0x18005e85f  lea     rbp, [rsp-130h]
0x18005e867  sub     rsp, 230h
0x18005e86e  mov     rax, cs:__security_cookie
0x18005e875  xor     rax, rsp
0x18005e878  mov     [rbp+160h+var_40], rax
0x18005e87f  mov     [rsp+260h+var_1F8], r9
0x18005e884  mov     [rsp+260h+var_210], r8
0x18005e889  mov     r12, rdx
0x18005e88c  mov     rbx, rcx
0x18005e88f  mov     rdi, [rbp+160h+pwszVerb]
0x18005e896  mov     r13, [rbp+160h+arg_20]
0x18005e89d  mov     [rbp+160h+var_1D0], r13
0x18005e8a1  movzx   r15d, [rbp+160h+arg_38]
0x18005e8a9  xor     esi, esi
0x18005e8ab  test    r15w, r15w
0x18005e8af  jnz     short loc_18005E8C4
0x18005e8b1  cmp     [rbp+160h+arg_30], sil
0x18005e8b8  mov     r15d, 1BBh
0x18005e8be  jnz     short loc_18005E8C4
0x18005e8c0  lea     r15d, [rsi+50h]
0x18005e8c4  mov     [rsp+260h+dwFlags], esi; dwFlags
0x18005e8c8  xor     r9d, r9d; pszProxyBypassW
0x18005e8cb  xor     r8d, r8d; pszProxyW
0x18005e8ce  lea     edx, [r9+4]; dwAccessType
0x18005e8d2  xor     ecx, ecx; pszAgentW
0x18005e8d4  call    cs:__imp_WinHttpOpen
0x18005e8da  mov     [rsp+260h+hSession], rax
0x18005e8df  test    rax, rax
0x18005e8e2  jz      loc_18005EC72
0x18005e8e8  lea     rax, [rsp+260h+hSession]
0x18005e8ed  mov     [rsp+260h+var_218], rax
0x18005e8f2  lea     rdx, [rsp+260h+var_218]
0x18005e8f7  lea     rcx, [rbp+160h+var_80]
0x18005e8fe  call    ScopeGuard__ScopeGuard__lambda_dff20fe531c161d312228c3011b1ee86___
0x18005e903  nop
0x18005e904  lea     rsi, WPP_GLOBAL_Control
0x18005e90b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e912  cmp     rcx, rsi
0x18005e915  jz      short loc_18005E941
0x18005e917  test    byte ptr [rcx+1Ch], 4
0x18005e91b  jz      short loc_18005E941
0x18005e91d  cmp     qword ptr [rbx+18h], 7
0x18005e922  jbe     short loc_18005E929
0x18005e924  mov     r9, [rbx]
0x18005e927  jmp     short loc_18005E92C
0x18005e929  mov     r9, rbx
0x18005e92c  mov     edx, 0Ch
0x18005e931  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005e938  mov     rcx, [rcx+10h]
0x18005e93c  call    WPP_SF_S
0x18005e941  cmp     qword ptr [rbx+18h], 7
0x18005e946  jbe     short loc_18005E94B
0x18005e948  mov     rbx, [rbx]
0x18005e94b  xor     r9d, r9d; dwReserved
0x18005e94e  movzx   r8d, r15w; nServerPort
0x18005e952  mov     rdx, rbx; pswzServerName
0x18005e955  mov     rcx, [rsp+260h+hSession]; hSession
0x18005e95a  call    cs:__imp_WinHttpConnect
0x18005e960  mov     [rsp+260h+hConnect], rax
0x18005e965  xor     r15d, r15d
0x18005e968  test    rax, rax
0x18005e96b  jz      loc_18005ECD4
0x18005e971  lea     rax, [rsp+260h+hConnect]
0x18005e976  mov     [rsp+260h+var_218], rax
0x18005e97b  lea     rdx, [rsp+260h+var_218]
0x18005e980  lea     rcx, [rbp+160h+var_C0]
0x18005e987  call    ScopeGuard__ScopeGuard__lambda_a37f6ebc28d708e5d633bdd02f7a3cad___
0x18005e98c  nop
0x18005e98d  movzx   eax, [rbp+160h+arg_30]
0x18005e994  shl     eax, 17h
0x18005e997  cmp     qword ptr [r12+18h], 7
0x18005e99d  jbe     short loc_18005E9A3
0x18005e99f  mov     r12, [r12]
0x18005e9a3  cmp     qword ptr [rdi+18h], 7
0x18005e9a8  jbe     short loc_18005E9AD
0x18005e9aa  mov     rdi, [rdi]
0x18005e9ad  mov     [rsp+260h+var_230], eax; dwFlags
0x18005e9b1  mov     [rsp+260h+ppwszAcceptTypes], r15; ppwszAcceptTypes
0x18005e9b6  mov     qword ptr [rsp+260h+dwFlags], r15; pwszReferrer
0x18005e9bb  xor     r9d, r9d; pwszVersion
0x18005e9be  mov     r8, r12; pwszObjectName
0x18005e9c1  mov     rdx, rdi; pwszVerb
0x18005e9c4  mov     rcx, [rsp+260h+hConnect]; hConnect
0x18005e9c9  call    cs:__imp_WinHttpOpenRequest
0x18005e9cf  mov     [rsp+260h+hRequest], rax
0x18005e9d4  test    rax, rax
0x18005e9d7  jz      loc_18005ED2F
0x18005e9dd  lea     rax, [rsp+260h+hRequest]
0x18005e9e2  mov     [rsp+260h+var_218], rax
0x18005e9e7  lea     rdx, [rsp+260h+var_218]
0x18005e9ec  lea     rcx, [rbp+160h+var_100]
0x18005e9f0  call    ScopeGuard__ScopeGuard__lambda_bf43a75a91dfa73a8e629cdbcec234d7___
0x18005e9f5  nop
0x18005e9f6  mov     rbx, [rsp+260h+var_1F8]
0x18005e9fb  mov     rbx, [rbx]
0x18005e9fe  mov     rbx, [rbx]
0x18005ea01  mov     r12d, 0FFFFFFFFh
0x18005ea07  cmp     [rbx+19h], r15b
0x18005ea0b  jnz     loc_18005EB23
0x18005ea11  lea     rdx, [rbx+20h]
0x18005ea15  lea     rcx, [rbp+160h+var_140]
0x18005ea19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005ea1e  nop
0x18005ea1f  lea     rdx, [rbx+40h]
0x18005ea23  lea     rcx, [rbp+160h+var_120]
0x18005ea27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005ea2c  nop
0x18005ea2d  xorps   xmm0, xmm0
0x18005ea30  movups  [rsp+260h+var_1F0], xmm0
0x18005ea35  mov     [rbp+160h+var_1E0], r15
0x18005ea39  mov     [rbp+160h+var_1D8], r15
0x18005ea3d  mov     r8d, 8
0x18005ea43  lea     rdx, a01; "{0}: {1}"
0x18005ea4a  lea     rcx, [rsp+260h+var_1F0]
0x18005ea4f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005ea54  lea     rdx, [rsp+260h+var_1F0]
0x18005ea59  lea     rcx, [rbp+160h+pExceptionObject]
0x18005ea5d  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18005ea62  nop
0x18005ea63  lea     rdx, [rbp+160h+var_140]
0x18005ea67  mov     rcx, rax; this
0x18005ea6a  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18005ea6f  lea     rdx, [rbp+160h+var_120]
0x18005ea73  mov     rcx, rax; this
0x18005ea76  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18005ea7b  mov     rdx, rax
0x18005ea7e  lea     rcx, [rbp+160h+var_1C8]
0x18005ea82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005ea87  cmp     qword ptr [rax+18h], 7
0x18005ea8c  jbe     short loc_18005EA91
0x18005ea8e  mov     rax, [rax]
0x18005ea91  xor     r9d, r9d; dwModifiers
0x18005ea94  mov     r8d, r12d; dwHeadersLength
0x18005ea97  mov     rdx, rax; lpszHeaders
0x18005ea9a  mov     rcx, [rsp+260h+hRequest]; hRequest
0x18005ea9f  call    cs:__imp_WinHttpAddRequestHeaders
0x18005eaa5  mov     edi, eax
0x18005eaa7  lea     rcx, [rbp+160h+var_1C8]
0x18005eaab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005eab0  nop
0x18005eab1  lea     rcx, [rbp+160h+pExceptionObject]
0x18005eab5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005eaba  test    edi, edi
0x18005eabc  jz      loc_18005ED8A
0x18005eac2  lea     rcx, [rbp+160h+var_120]
0x18005eac6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005eacb  lea     rcx, [rbp+160h+var_140]
0x18005eacf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ead4  mov     rcx, [rbx+10h]
0x18005ead8  cmp     [rcx+19h], r15b
0x18005eadc  jz      short loc_18005EAFF
0x18005eade  mov     rax, [rbx+8]
0x18005eae2  jmp     short loc_18005EAF1
0x18005eae4  cmp     rbx, [rax+10h]
0x18005eae8  jnz     short loc_18005EAF7
0x18005eaea  mov     rbx, rax
0x18005eaed  mov     rax, [rax+8]
0x18005eaf1  cmp     [rax+19h], r15b
0x18005eaf5  jz      short loc_18005EAE4
0x18005eaf7  mov     rbx, rax
0x18005eafa  jmp     loc_18005EA07
0x18005eaff  mov     rbx, rcx
0x18005eb02  mov     rcx, [rcx]
0x18005eb05  cmp     [rcx+19h], r15b
0x18005eb09  jnz     loc_18005EA07
0x18005eb0f  mov     rbx, rcx
0x18005eb12  mov     rax, [rcx]
0x18005eb15  mov     rcx, rax
0x18005eb18  cmp     [rax+19h], r15b
0x18005eb1c  jz      short loc_18005EB0F
0x18005eb1e  jmp     loc_18005EA07
0x18005eb23  mov     rax, [rsp+260h+var_210]
0x18005eb28  cmp     qword ptr [rax+18h], 7
0x18005eb2d  jbe     short loc_18005EB32
0x18005eb2f  mov     rax, [rax]
0x18005eb32  mov     rdx, rax
0x18005eb35  lea     rcx, [rbp+160h+lpOptional]
0x18005eb39  call    ?ToUtf8@StringAlgo@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; StringAlgo::ToUtf8(ushort const *)
0x18005eb3e  nop
0x18005eb3f  mov     rax, qword ptr [rbp+160h+dwOptionalLength]
0x18005eb43  cmp     rax, r12
0x18005eb46  ja      loc_18005EDE5
0x18005eb4c  lea     r9, [rbp+160h+lpOptional]
0x18005eb50  cmp     [rbp+160h+var_188], 0Fh
0x18005eb55  cmova   r9, [rbp+160h+lpOptional]; lpOptional
0x18005eb5a  mov     qword ptr [rsp+260h+var_230], r15; dwContext
0x18005eb5f  mov     dword ptr [rsp+260h+ppwszAcceptTypes], eax; dwTotalLength
0x18005eb63  mov     [rsp+260h+dwFlags], eax; dwOptionalLength
0x18005eb67  xor     r8d, r8d; dwHeadersLength
0x18005eb6a  xor     edx, edx; lpszHeaders
0x18005eb6c  mov     rcx, [rsp+260h+hRequest]; hRequest
0x18005eb71  call    cs:__imp_WinHttpSendRequest
0x18005eb77  test    eax, eax
0x18005eb79  jz      loc_18005EE2B
0x18005eb7f  xor     edx, edx; lpReserved
0x18005eb81  mov     rcx, [rsp+260h+hRequest]; hRequest
0x18005eb86  call    cs:__imp_WinHttpReceiveResponse
0x18005eb8c  test    eax, eax
0x18005eb8e  jz      loc_18005EC2E
0x18005eb94  mov     rax, [rsp+260h+hRequest]
0x18005eb99  mov     [rsp+260h+var_210], rax
0x18005eb9e  mov     rcx, [r13+38h]
0x18005eba2  test    rcx, rcx
0x18005eba5  jnz     short loc_18005EBAE
0x18005eba7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005ebad  int     3; Trap to Debugger
0x18005ebae  mov     rax, [rcx]
0x18005ebb1  lea     rdx, [rsp+260h+var_210]
0x18005ebb6  mov     rax, [rax+10h]
0x18005ebba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebbf  nop
0x18005ebc0  lea     rcx, [rbp+160h+lpOptional]
0x18005ebc4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005ebc9  nop
0x18005ebca  lea     rcx, [rbp+160h+var_100]; this
0x18005ebce  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18005ebd3  nop
0x18005ebd4  lea     rcx, [rbp+160h+var_C0]; this
0x18005ebdb  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18005ebe0  nop
0x18005ebe1  lea     rcx, [rbp+160h+var_80]; this
0x18005ebe8  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18005ebed  nop
0x18005ebee  mov     rcx, [r13+38h]
0x18005ebf2  test    rcx, rcx
0x18005ebf5  jz      short loc_18005EC0D
0x18005ebf7  mov     rax, [rcx]
0x18005ebfa  cmp     rcx, r13
0x18005ebfd  setnz   dl
0x18005ec00  mov     rax, [rax+20h]
0x18005ec04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec09  mov     [r13+38h], r15
0x18005ec0d  mov     rcx, [rbp+160h+var_40]
0x18005ec14  xor     rcx, rsp; StackCookie
0x18005ec17  call    __security_check_cookie
0x18005ec1c  add     rsp, 230h
0x18005ec23  pop     r15
0x18005ec25  pop     r13
0x18005ec27  pop     r12
0x18005ec29  pop     rdi
0x18005ec2a  pop     rsi
0x18005ec2b  pop     rbx
0x18005ec2c  pop     rbp
0x18005ec2d  retn
0x18005ec2e  lea     rdx, aReceiverespons; "ReceiveResponse"
0x18005ec35  lea     rcx, [rbp+160h+var_1C8]
0x18005ec39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ec3e  mov     rbx, rax
0x18005ec41  call    cs:__imp_GetLastError
0x18005ec47  test    eax, eax
0x18005ec49  jle     short loc_18005EC53
0x18005ec4b  movzx   eax, ax
0x18005ec4e  or      eax, 80070000h
0x18005ec53  mov     r8, rbx
0x18005ec56  mov     edx, eax
0x18005ec58  lea     rcx, [rbp+160h+pExceptionObject]
0x18005ec5c  call    ??0MessageException@@QEAA@JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MessageException::MessageException(long,std::wstring)
0x18005ec61  lea     rdx, _TI3?AVMessageException@@; pThrowInfo
0x18005ec68  lea     rcx, [rbp+160h+pExceptionObject]; pExceptionObject
0x18005ec6c  call    _CxxThrowException_0
0x18005ec72  call    cs:__imp_GetLastError
0x18005ec78  mov     ebx, eax
0x18005ec7a  test    eax, eax
0x18005ec7c  jle     short loc_18005EC87
0x18005ec7e  movzx   ebx, ax
0x18005ec81  or      ebx, 80070000h
0x18005ec87  lea     rsi, WPP_GLOBAL_Control
0x18005ec8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec95  cmp     rcx, rsi
0x18005ec98  jz      short loc_18005ECB8
0x18005ec9a  test    byte ptr [rcx+1Ch], 1
0x18005ec9e  jz      short loc_18005ECB8
0x18005eca0  mov     edx, 0Bh
0x18005eca5  mov     r9d, ebx
0x18005eca8  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x18005ecaf  mov     rcx, [rcx+10h]
0x18005ecb3  call    WPP_SF_d
0x18005ecb8  mov     edx, ebx; int
0x18005ecba  lea     rcx, [rbp+160h+var_1C8]; this
0x18005ecbe  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005ecc3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005ecca  lea     rcx, [rbp+160h+var_1C8]; pExceptionObject
0x18005ecce  call    _CxxThrowException_0
0x18005ecd4  call    cs:__imp_GetLastError
0x18005ecda  mov     ebx, eax
0x18005ecdc  test    eax, eax
0x18005ecde  jle     short loc_18005ECE9
0x18005ece0  movzx   ebx, ax
0x18005ece3  or      ebx, 80070000h
0x18005ece9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ecf0  cmp     rcx, rsi
0x18005ecf3  jz      short loc_18005ED13
0x18005ecf5  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
