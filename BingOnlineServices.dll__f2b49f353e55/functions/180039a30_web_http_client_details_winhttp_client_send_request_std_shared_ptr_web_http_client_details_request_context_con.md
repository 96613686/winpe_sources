# web::http::client::details::winhttp_client::send_request(std::shared_ptr<web::http::client::details::request_context> const &)

- ea: `0x180039a30`
- end: `0x18003a103`
- name: `?send_request@winhttp_client@details@client@http@web@@MEAAXAEBV?$shared_ptr@Vrequest_context@details@client@http@web@@@std@@@Z`
- size: `1747`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x18000529c`
- `0x1800086b0`
- `0x180009698`
- `0x18000e5a8`
- `0x18000eca4`
- `0x180014368`
- `0x18001a6ec`
- `0x18001adbc`
- `0x18001adf0`
- `0x18001df98`
- `0x180024718`
- `0x180025488`
- `0x18002560c`
- `0x18002b0a0`
- `0x180031968`
- `0x180032e30`
- `0x180032edc`
- `0x180033298`
- `0x180034034`
- `0x180036690`
- `0x180036bf0`
- `0x180038124`
- `0x1800395a0`
- `0x180039a30`
- `0x18003dfa0`
- `0x18004ee50`
- `0x180050640`
- `0x180050bd0`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003a006`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003a006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ebd`
- `WINHTTP!WinHttpSetOption` at `0x180039c86`
- `WINHTTP!WinHttpSetOption` at `0x180039d01`
- `WINHTTP!WinHttpSetOption` at `0x180039d82`
- `WINHTTP!WinHttpSetOption` at `0x180039c86`
- `WINHTTP!WinHttpSetOption` at `0x180039d01`
- `WINHTTP!WinHttpSetOption` at `0x180039d82`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180039aed`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180039aed`
- `WINHTTP!WinHttpOpenRequest` at `0x180039c03`
- `WINHTTP!WinHttpOpenRequest` at `0x180039c03`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180039eaf`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180039eaf`

## string_xrefs

- `0x180039c1d`: `WinHttpOpenRequest`
- `0x180039d16`: `Setting autologon policy to WINHTTP_AUTOLOGON_SECURITY_LEVEL_HIGH`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall web::http::client::details::winhttp_client::send_request(
        __int64 a1,
        struct web::http::client::details::winhttp_request_context **a2)
{
  struct web::http::client::details::winhttp_request_context *v4; // rdi
  bool v5; // r15
  __int64 v6; // rax
  const WCHAR *v7; // rax
  BOOL ProxyForUrl; // ebx
  char v9; // r12
  struct web::uri_builder *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rax
  DWORD dwFlags; // edx
  LPCWSTR v15; // r10
  void *v16; // rax
  DWORD LastError; // edi
  struct web::http::client::details::winhttp_request_context *v18; // rbx
  __int64 v19; // r8
  DWORD v20; // edi
  struct web::http::client::details::winhttp_request_context *v21; // rbx
  __int64 v22; // r8
  DWORD v23; // edi
  struct web::http::client::details::winhttp_request_context *v24; // rbx
  __int64 v25; // r8
  DWORD v26; // edi
  struct web::http::client::details::winhttp_request_context *v27; // rbx
  __int64 v28; // r8
  unsigned __int64 content_length; // r15
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r10
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r10
  __int64 v36; // rdx
  const WCHAR *v37; // rax
  DWORD v38; // edi
  struct web::http::client::details::winhttp_request_context *v39; // rbx
  __int64 v40; // rax
  struct web::http::client::details::winhttp_request_context *v41; // rbx
  __int64 v42; // rdx
  bool v43; // bl
  pplx::details::_CancellationTokenRegistration **v44; // rbx
  __int64 v45; // rcx
  web::http::client::details::winhttp_client *v46; // rcx
  __int64 v47; // rdx
  char v48; // bl
  __int64 v50; // rdi
  void (__fastcall *v51)(__int64, __int64); // rbx
  __int64 v52; // rax
  struct web::http::client::details::winhttp_request_context *Buffer; // [rsp+40h] [rbp-4D8h] BYREF
  pplx::details::_CancellationTokenRegistration *v54; // [rsp+48h] [rbp-4D0h] BYREF
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+50h] [rbp-4C8h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+68h] [rbp-4B0h] BYREF
  _BYTE v57[32]; // [rsp+88h] [rbp-490h] BYREF
  _QWORD v58[4]; // [rsp+A8h] [rbp-470h] BYREF
  _BYTE v59[40]; // [rsp+C8h] [rbp-450h] BYREF
  _BYTE v60[80]; // [rsp+F0h] [rbp-428h] BYREF
  _BYTE v61[208]; // [rsp+140h] [rbp-3D8h] BYREF
  _BYTE v62[240]; // [rsp+210h] [rbp-308h] BYREF
  _BYTE v63[240]; // [rsp+300h] [rbp-218h] BYREF
  _BYTE v64[240]; // [rsp+3F0h] [rbp-128h] BYREF

  v58[0] = a2;
  LODWORD(Buffer) = 0;
  v4 = *a2;
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  v5 = 0;
  if ( *(_DWORD *)(a1 + 504) == 1 )
  {
    memset(&pAutoProxyOptions.lpszAutoConfigUrl, 0, 20);
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    pAutoProxyOptions.dwFlags = 1;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
    pAutoProxyOptions.fAutoLogonIfChallenged = 1;
    v6 = web::uri::to_string(a1 + 8, v57);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    ProxyForUrl = WinHttpGetProxyForUrl(*(HINTERNET *)(a1 + 864), v7, &pAutoProxyOptions, &pProxyInfo);
    std::wstring::_Tidy_deallocate(v57);
    v5 = ProxyForUrl;
  }
  web::details::uri_components::uri_components(
    (web::details::uri_components *)v61,
    (const struct web::details::uri_components *)(a1 + 40));
  web::http::details::_http_request::relative_uri(*((_QWORD *)v4 + 3), v62);
  v9 = 2;
  v10 = web::uri_builder::append((web::uri_builder *)v61, (const struct web::uri *)v62);
  v11 = web::uri_builder::to_uri(v10, v64);
  v12 = web::uri::resource(v11, v63);
  web::uri::to_string(v12, v59);
  web::uri::~uri((web::uri *)v63);
  web::uri::~uri((web::uri *)v64);
  web::uri::~uri((web::uri *)v62);
  web::details::uri_components::~uri_components((web::details::uri_components *)v61);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v4 + 3) + 96LL);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
  v16 = WinHttpOpenRequest(*(HINTERNET *)(a1 + 872), v15, v13, 0, 0, 0, dwFlags);
  *((_QWORD *)v4 + 12) = v16;
  if ( !v16 )
  {
    LastError = GetLastError();
    v18 = *a2;
    std::string::string(&pAutoProxyOptions, "WinHttpOpenRequest");
    v19 = web::http::client::details::build_error_msg(v57, LastError, &pAutoProxyOptions);
    web::http::client::details::request_context::report_error(v18, LastError, v19);
    std::string::_Tidy_deallocate(v57);
LABEL_5:
    std::string::_Tidy_deallocate(&pAutoProxyOptions);
    return std::wstring::_Tidy_deallocate(v59);
  }
  if ( v5 && !WinHttpSetOption(v16, 0x26u, &pProxyInfo, 0x18u) )
  {
    v20 = GetLastError();
    v21 = *a2;
    std::string::string(&pAutoProxyOptions, "Setting proxy options");
    v22 = web::http::client::details::build_error_msg(v57, v20, &pAutoProxyOptions);
    web::http::client::details::request_context::report_error(v21, v20, v22);
    std::string::_Tidy_deallocate(v57);
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a1 + 592) )
  {
    LODWORD(Buffer) = 2;
    if ( !WinHttpSetOption(*((HINTERNET *)v4 + 12), 0x4Du, &Buffer, 4u) )
    {
      v23 = GetLastError();
      v24 = *a2;
      std::string::string(&pAutoProxyOptions, "Setting autologon policy to WINHTTP_AUTOLOGON_SECURITY_LEVEL_HIGH");
      v25 = web::http::client::details::build_error_msg(v57, v23, &pAutoProxyOptions);
      web::http::client::details::request_context::report_error(v24, v23, v25);
      std::string::_Tidy_deallocate(v57);
      goto LABEL_5;
    }
  }
  if ( !*(_BYTE *)(a1 + 665) )
  {
    LODWORD(Buffer) = 13056;
    if ( !WinHttpSetOption(*((HINTERNET *)v4 + 12), 0x1Fu, &Buffer, 4u) )
    {
      v26 = GetLastError();
      v27 = *a2;
      std::string::string(&pAutoProxyOptions, "Setting ignore server certificate verification");
      v28 = web::http::client::details::build_error_msg(v57, v26, &pAutoProxyOptions);
      web::http::client::details::request_context::report_error(v27, v26, v28);
      std::string::_Tidy_deallocate(v57);
      goto LABEL_5;
    }
  }
  content_length = web::http::details::http_msg_base::_get_content_length(*((web::http::details::http_msg_base **)v4 + 3));
  if ( content_length )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v4 + 3) + 96LL);
    v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(web::http::methods::GET);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                            v32,
                            *(_QWORD *)(v31 + 112),
                            v30,
                            qword_18009BA88)
      || (std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*((_QWORD *)v4 + 3) + 96LL),
          v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(web::http::methods::HEAD),
          (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                             v35,
                             *(_QWORD *)(v34 + 112),
                             v33,
                             qword_18009BB08)) )
    {
      v41 = *a2;
      std::wstring::wstring(&pAutoProxyOptions, L"A GET or HEAD request should not have an entity body.");
      v42 = web::http::http_exception::http_exception(v60, &pAutoProxyOptions);
      web::http::client::details::request_context::report_exception<web::http::http_exception>(v41, v42);
      web::http::http_exception::~http_exception((web::http::http_exception *)v60);
      goto LABEL_25;
    }
    if ( content_length == -1 )
    {
      *((_DWORD *)v4 + 27) = 2;
    }
    else
    {
      *((_DWORD *)v4 + 27) = 1;
      *((_QWORD *)v4 + 14) = content_length;
    }
  }
  v36 = *((_QWORD *)v4 + 3);
  if ( *(_QWORD *)(v36 + 48) )
  {
    web::http::client::details::flatten_http_headers(&pAutoProxyOptions, v36 + 40);
    v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&pAutoProxyOptions);
    if ( !WinHttpAddRequestHeaders(*((HINTERNET *)v4 + 12), v37, (DWORD)pAutoProxyOptions.lpvReserved, 0x20000000u) )
    {
      v38 = GetLastError();
      v39 = *a2;
      std::string::string(v58, "WinHttpAddRequestHeaders");
      v40 = web::http::client::details::build_error_msg(v57, v38, v58);
      web::http::client::details::request_context::report_error(v39, v38, v40);
      std::string::_Tidy_deallocate(v57);
      std::string::_Tidy_deallocate(v58);
LABEL_25:
      std::wstring::_Tidy_deallocate(&pAutoProxyOptions);
      return std::wstring::_Tidy_deallocate(v59);
    }
    std::wstring::_Tidy_deallocate(&pAutoProxyOptions);
  }
  Buffer = 0;
  v43 = *(_QWORD *)(*((_QWORD *)v4 + 3) + 144LL) != 0;
  pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)&Buffer);
  if ( v43 )
  {
    Buffer = v4;
    v44 = pplx::cancellation_token::register_callback<_lambda_1438ac20b176de53977512e8751d5d48_>(
            (pplx::details::_CancellationTokenState **)(*((_QWORD *)v4 + 3) + 144LL),
            &v54,
            &Buffer);
    if ( (pplx::details::_CancellationTokenRegistration **)((char *)v4 + 88) != v44 )
    {
      pplx::cancellation_token_registration::_Clear((struct web::http::client::details::winhttp_request_context *)((char *)v4 + 88));
      *((_QWORD *)v4 + 11) = *v44;
      *v44 = 0;
    }
    pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)&v54);
  }
  try
  {
    v54 = (pplx::details::_CancellationTokenRegistration *)*((_QWORD *)v4 + 12);
    v45 = *(_QWORD *)(a1 + 728);
    if ( !v45 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, pplx::details::_CancellationTokenRegistration **))(*(_QWORD *)v45 + 16LL))(
      v45,
      &v54);
  }
  catch ( ... )
  {
    v50 = *(_QWORD *)v58[0];
    v51 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)v58[0] + 8LL);
    v52 = std::current_exception(v58);
    v51(v50, v52);
    return std::wstring::_Tidy_deallocate(v59);
  }
  if ( !*((_DWORD *)v4 + 27)
    || !*(_BYTE *)(a1 + 736)
    || (v47 = (*(__int64 (__fastcall **)(struct web::http::client::details::winhttp_request_context *, _QWORD *))(*(_QWORD *)v4 + 16LL))(
                v4,
                v58),
        v9 = 3,
        LODWORD(Buffer) = 3,
        v48 = 1,
        (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47)) )
  {
    v48 = 0;
  }
  if ( (v9 & 1) != 0 )
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v58);
  if ( v48 )
  {
    v58[0] = operator new(0x18u);
    Buffer = (struct web::http::client::details::winhttp_request_context *)Concurrency::streams::container_buffer<std::vector<unsigned char>>::container_buffer<std::vector<unsigned char>>(v58[0]);
    std::unique_ptr<Concurrency::streams::container_buffer<std::vector<unsigned char>>>::operator=<std::default_delete<Concurrency::streams::container_buffer<std::vector<unsigned char>>>,0>(
      (__int64 *)v4 + 20,
      (__int64 *)&Buffer);
    std::unique_ptr<Concurrency::streams::container_buffer<std::vector<unsigned char>>>::~unique_ptr<Concurrency::streams::container_buffer<std::vector<unsigned char>>>(&Buffer);
  }
  web::http::client::details::winhttp_client::_start_request_send(v46, v4, content_length);
  return std::wstring::_Tidy_deallocate(v59);
}

```

## disassembly

```asm
0x180039a30  mov     r11, rsp
0x180039a33  mov     [r11+18h], rbx
0x180039a37  mov     [r11+20h], rsi
0x180039a3b  push    rdi
0x180039a3c  push    r12
0x180039a3e  push    r13
0x180039a40  push    r14
0x180039a42  push    r15
0x180039a44  sub     rsp, 4F0h
0x180039a4b  mov     rax, cs:__security_cookie
0x180039a52  xor     rax, rsp
0x180039a55  mov     [rsp+518h+var_38], rax
0x180039a5d  mov     rsi, rdx
0x180039a60  mov     r14, rcx
0x180039a63  mov     [rsp+518h+var_470], rdx
0x180039a6b  xor     r13d, r13d
0x180039a6e  mov     dword ptr [rsp+518h+Buffer], r13d
0x180039a73  mov     rdi, [rdx]
0x180039a76  xorps   xmm0, xmm0
0x180039a79  xor     eax, eax
0x180039a7b  movups  xmmword ptr [rsp+518h+pProxyInfo.dwAccessType], xmm0
0x180039a80  mov     [rsp+518h+pProxyInfo.lpszProxyBypass], rax
0x180039a85  movzx   r15d, r13b
0x180039a89  lea     ebx, [rax+1]
0x180039a8c  cmp     [rcx+1F8h], ebx
0x180039a92  jnz     short loc_180039B0C
0x180039a94  movdqu  xmmword ptr [rsp+518h+pAutoProxyOptions.lpszAutoConfigUrl], xmm0
0x180039a9a  mov     [r11-498h], r13d
0x180039aa1  xorps   xmm1, xmm1
0x180039aa4  movups  xmmword ptr [rsp+518h+pProxyInfo.dwAccessType], xmm1
0x180039aa9  mov     [rsp+518h+pProxyInfo.lpszProxyBypass], rax
0x180039aae  mov     [rsp+518h+pAutoProxyOptions.dwFlags], ebx
0x180039ab2  mov     [rsp+518h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180039aba  mov     [rsp+518h+pAutoProxyOptions.fAutoLogonIfChallenged], ebx
0x180039ac1  add     rcx, 8
0x180039ac5  lea     rdx, [r11-490h]
0x180039acc  call    ?to_string@uri@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::uri::to_string(void)
0x180039ad1  mov     rcx, rax
0x180039ad4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039ad9  lea     r9, [rsp+518h+pProxyInfo]; pProxyInfo
0x180039ade  lea     r8, [rsp+518h+pAutoProxyOptions]; pAutoProxyOptions
0x180039ae3  mov     rdx, rax; lpcwszUrl
0x180039ae6  mov     rcx, [r14+360h]; hSession
0x180039aed  call    cs:__imp_WinHttpGetProxyForUrl
0x180039af3  mov     ebx, eax
0x180039af5  lea     rcx, [rsp+518h+var_490]
0x180039afd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039b02  test    ebx, ebx
0x180039b04  lea     ebx, [r13+1]
0x180039b08  cmovnz  r15d, ebx
0x180039b0c  lea     rdx, [r14+28h]; struct web::details::uri_components *
0x180039b10  lea     rcx, [rsp+518h+var_3D8]; this
0x180039b18  call    ??0uri_components@details@web@@QEAA@AEBU012@@Z; web::details::uri_components::uri_components(web::details::uri_components const &)
0x180039b1d  nop
0x180039b1e  lea     rdx, [rsp+518h+var_308]
0x180039b26  mov     rcx, [rdi+18h]
0x180039b2a  call    ?relative_uri@_http_request@details@http@web@@QEBA?AVuri@4@XZ; web::http::details::_http_request::relative_uri(void)
0x180039b2f  mov     r12d, 2
0x180039b35  lea     rdx, [rsp+518h+var_308]; struct web::uri *
0x180039b3d  lea     rcx, [rsp+518h+var_3D8]; this
0x180039b45  call    ?append@uri_builder@web@@QEAAAEAV12@AEBVuri@2@@Z; web::uri_builder::append(web::uri const &)
0x180039b4a  lea     rdx, [rsp+518h+var_128]
0x180039b52  mov     rcx, rax
0x180039b55  call    ?to_uri@uri_builder@web@@QEAA?AVuri@2@XZ; web::uri_builder::to_uri(void)
0x180039b5a  nop
0x180039b5b  lea     rdx, [rsp+518h+var_218]
0x180039b63  mov     rcx, rax
0x180039b66  call    ?resource@uri@web@@QEBA?AV12@XZ; web::uri::resource(void)
0x180039b6b  nop
0x180039b6c  lea     rdx, [rsp+518h+var_450]
0x180039b74  mov     rcx, rax
0x180039b77  call    ?to_string@uri@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::uri::to_string(void)
0x180039b7c  nop
0x180039b7d  lea     rcx, [rsp+518h+var_218]; this
0x180039b85  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180039b8a  nop
0x180039b8b  lea     rcx, [rsp+518h+var_128]; this
0x180039b93  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180039b98  nop
0x180039b99  lea     rcx, [rsp+518h+var_308]; this
0x180039ba1  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180039ba6  nop
0x180039ba7  lea     rcx, [rsp+518h+var_3D8]; this
0x180039baf  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x180039bb4  mov     rcx, [rdi+18h]
0x180039bb8  add     rcx, 60h ; '`'
0x180039bbc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039bc1  mov     r10, rax
0x180039bc4  mov     cl, [r14+370h]
0x180039bcb  neg     cl
0x180039bcd  sbb     edx, edx
0x180039bcf  and     edx, 800000h
0x180039bd5  add     edx, 40h ; '@'
0x180039bd8  lea     rcx, [rsp+518h+var_450]
0x180039be0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039be5  mov     r8, rax; pwszObjectName
0x180039be8  mov     [rsp+518h+dwFlags], edx; dwFlags
0x180039bec  mov     [rsp+518h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x180039bf1  mov     [rsp+518h+pwszReferrer], r13; pwszReferrer
0x180039bf6  xor     r9d, r9d; pwszVersion
0x180039bf9  mov     rdx, r10; pwszVerb
0x180039bfc  mov     rcx, [r14+368h]; hConnect
0x180039c03  call    cs:__imp_WinHttpOpenRequest
0x180039c09  mov     [rdi+60h], rax
0x180039c0d  test    rax, rax
0x180039c10  jnz     short loc_180039C6F
0x180039c12  call    cs:__imp_GetLastError
0x180039c18  mov     edi, eax
0x180039c1a  mov     rbx, [rsi]
0x180039c1d  lea     rdx, aWinhttpopenreq; "WinHttpOpenRequest"
0x180039c24  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039c29  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039c2e  nop
0x180039c2f  lea     r8, [rsp+518h+pAutoProxyOptions]
0x180039c34  mov     edx, edi
0x180039c36  lea     rcx, [rsp+518h+var_490]
0x180039c3e  call    web__http__client__details__build_error_msg
0x180039c43  nop
0x180039c44  mov     r8, rax
0x180039c47  mov     edx, edi
0x180039c49  mov     rcx, rbx
0x180039c4c  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039c51  nop
0x180039c52  lea     rcx, [rsp+518h+var_490]
0x180039c5a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039c5f  nop
0x180039c60  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039c65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039c6a  jmp     loc_18003A0C9
0x180039c6f  test    r15b, r15b
0x180039c72  jz      short loc_180039CE0
0x180039c74  mov     r9d, 18h; dwBufferLength
0x180039c7a  lea     r8, [rsp+518h+pProxyInfo]; lpBuffer
0x180039c7f  lea     edx, [r9+0Eh]; dwOption
0x180039c83  mov     rcx, rax; hInternet
0x180039c86  call    cs:__imp_WinHttpSetOption
0x180039c8c  test    eax, eax
0x180039c8e  jnz     short loc_180039CE0
0x180039c90  call    cs:__imp_GetLastError
0x180039c96  mov     edi, eax
0x180039c98  mov     rbx, [rsi]
0x180039c9b  lea     rdx, aSettingProxyOp; "Setting proxy options"
0x180039ca2  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039ca7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039cac  nop
0x180039cad  lea     r8, [rsp+518h+pAutoProxyOptions]
0x180039cb2  mov     edx, edi
0x180039cb4  lea     rcx, [rsp+518h+var_490]
0x180039cbc  call    web__http__client__details__build_error_msg
0x180039cc1  nop
0x180039cc2  mov     r8, rax
0x180039cc5  mov     edx, edi
0x180039cc7  mov     rcx, rbx
0x180039cca  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039ccf  nop
0x180039cd0  lea     rcx, [rsp+518h+var_490]
0x180039cd8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039cdd  nop
0x180039cde  jmp     short loc_180039C60
0x180039ce0  cmp     [r14+250h], r13
0x180039ce7  jz      short loc_180039D5E
0x180039ce9  mov     dword ptr [rsp+518h+Buffer], r12d
0x180039cee  mov     r9d, 4; dwBufferLength
0x180039cf4  lea     r8, [rsp+518h+Buffer]; lpBuffer
0x180039cf9  lea     edx, [r9+49h]; dwOption
0x180039cfd  mov     rcx, [rdi+60h]; hInternet
0x180039d01  call    cs:__imp_WinHttpSetOption
0x180039d07  test    eax, eax
0x180039d09  jnz     short loc_180039D5E
0x180039d0b  call    cs:__imp_GetLastError
0x180039d11  mov     edi, eax
0x180039d13  mov     rbx, [rsi]
0x180039d16  lea     rdx, aSettingAutolog; "Setting autologon policy to WINHTTP_AUT"...
0x180039d1d  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039d22  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039d27  nop
0x180039d28  lea     r8, [rsp+518h+pAutoProxyOptions]
0x180039d2d  mov     edx, edi
0x180039d2f  lea     rcx, [rsp+518h+var_490]
0x180039d37  call    web__http__client__details__build_error_msg
0x180039d3c  nop
0x180039d3d  mov     r8, rax
0x180039d40  mov     edx, edi
0x180039d42  mov     rcx, rbx
0x180039d45  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039d4a  nop
0x180039d4b  lea     rcx, [rsp+518h+var_490]
0x180039d53  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039d58  nop
0x180039d59  jmp     loc_180039C60
0x180039d5e  cmp     [r14+299h], r13b
0x180039d65  jnz     short loc_180039DDF
0x180039d67  mov     dword ptr [rsp+518h+Buffer], 3300h
0x180039d6f  mov     r9d, 4; dwBufferLength
0x180039d75  lea     r8, [rsp+518h+Buffer]; lpBuffer
0x180039d7a  lea     edx, [r9+1Bh]; dwOption
0x180039d7e  mov     rcx, [rdi+60h]; hInternet
0x180039d82  call    cs:__imp_WinHttpSetOption
0x180039d88  test    eax, eax
0x180039d8a  jnz     short loc_180039DDF
0x180039d8c  call    cs:__imp_GetLastError
0x180039d92  mov     edi, eax
0x180039d94  mov     rbx, [rsi]
0x180039d97  lea     rdx, aSettingIgnoreS; "Setting ignore server certificate verif"...
0x180039d9e  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039da3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039da8  nop
0x180039da9  lea     r8, [rsp+518h+pAutoProxyOptions]
0x180039dae  mov     edx, edi
0x180039db0  lea     rcx, [rsp+518h+var_490]
0x180039db8  call    web__http__client__details__build_error_msg
0x180039dbd  nop
0x180039dbe  mov     r8, rax
0x180039dc1  mov     edx, edi
0x180039dc3  mov     rcx, rbx
0x180039dc6  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039dcb  nop
0x180039dcc  lea     rcx, [rsp+518h+var_490]
0x180039dd4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039dd9  nop
0x180039dda  jmp     loc_180039C60
0x180039ddf  mov     rcx, [rdi+18h]; this
0x180039de3  call    ?_get_content_length@http_msg_base@details@http@web@@QEAA_KXZ; web::http::details::http_msg_base::_get_content_length(void)
0x180039de8  mov     r15, rax
0x180039deb  test    rax, rax
0x180039dee  jz      loc_180039E76
0x180039df4  mov     rdx, [rdi+18h]
0x180039df8  lea     rcx, [rdx+60h]
0x180039dfc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039e01  mov     r10, rax
0x180039e04  lea     rcx, ?GET@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::GET
0x180039e0b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039e10  mov     r8, rax
0x180039e13  mov     r9, cs:qword_18009BA88
0x180039e1a  mov     rdx, [rdx+70h]
0x180039e1e  mov     rcx, r10
0x180039e21  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180039e26  test    al, al
0x180039e28  jnz     loc_180039F2D
0x180039e2e  mov     rdx, [rdi+18h]
0x180039e32  lea     rcx, [rdx+60h]
0x180039e36  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039e3b  mov     r10, rax
0x180039e3e  lea     rcx, ?HEAD@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::HEAD
0x180039e45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039e4a  mov     r8, rax
0x180039e4d  mov     r9, cs:qword_18009BB08
0x180039e54  mov     rdx, [rdx+70h]
0x180039e58  mov     rcx, r10
0x180039e5b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180039e60  test    al, al
0x180039e62  jnz     loc_180039F2D
0x180039e68  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180039e6c  jnz     loc_180039F21
0x180039e72  mov     [rdi+6Ch], r12d
0x180039e76  mov     rdx, [rdi+18h]
0x180039e7a  cmp     [rdx+30h], r13
0x180039e7e  jz      loc_180039F88
0x180039e84  add     rdx, 28h ; '('
0x180039e88  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039e8d  call    web__http__client__details__flatten_http_headers
0x180039e92  nop
0x180039e93  lea     rcx, [rsp+518h+pAutoProxyOptions]
0x180039e98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039e9d  mov     rdx, rax; lpszHeaders
0x180039ea0  mov     r9d, 20000000h; dwModifiers
0x180039ea6  mov     r8d, dword ptr [rsp+518h+pAutoProxyOptions.lpvReserved]; dwHeadersLength
0x180039eab  mov     rcx, [rdi+60h]; hRequest
0x180039eaf  call    cs:__imp_WinHttpAddRequestHeaders
0x180039eb5  test    eax, eax
0x180039eb7  jnz     loc_180039F7E
0x180039ebd  call    cs:__imp_GetLastError
0x180039ec3  mov     edi, eax
0x180039ec5  mov     rbx, [rsi]
0x180039ec8  lea     rdx, aWinhttpaddrequ; "WinHttpAddRequestHeaders"
0x180039ecf  lea     rcx, [rsp+518h+var_470]
0x180039ed7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180039edc  nop
0x180039edd  lea     r8, [rsp+518h+var_470]
0x180039ee5  mov     edx, edi
0x180039ee7  lea     rcx, [rsp+518h+var_490]
0x180039eef  call    web__http__client__details__build_error_msg
0x180039ef4  nop
0x180039ef5  mov     r8, rax
0x180039ef8  mov     edx, edi
0x180039efa  mov     rcx, rbx
0x180039efd  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180039f02  nop
0x180039f03  lea     rcx, [rsp+518h+var_490]
0x180039f0b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039f10  nop
0x180039f11  lea     rcx, [rsp+518h+var_470]
0x180039f19  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180039f1e  nop
0x180039f1f  jmp     short loc_180039F6F
0x180039f21  mov     [rdi+6Ch], ebx
0x180039f24  mov     [rdi+70h], r15
0x180039f28  jmp     loc_180039E76
0x180039f2d  mov     rbx, [rsi]
0x180039f30  lea     rdx, aAGetOrHeadRequ; "A GET or HEAD request should not have a"...
  ... truncated ...
```
