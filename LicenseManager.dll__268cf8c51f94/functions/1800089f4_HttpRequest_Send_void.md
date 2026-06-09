# HttpRequest::Send(void)

- ea: `0x1800089f4`
- end: `0x180008e60`
- name: `?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ`
- size: `1132`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000655c`

## callees

- `0x1800077c0`
- `0x180007bb0`
- `0x180007c78`
- `0x1800089f4`
- `0x18000a110`
- `0x18000a200`
- `0x180012dc0`
- `0x180017654`
- `0x180044780`
- `0x180054a54`
- `0x18006694c`
- `0x180075e60`
- `0x1800769f4`
- `0x18008a400`
- `0x1800a8984`
- `0x1800a8e2c`
- `0x1800a8e74`
- `0x1800aae3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008afb`
- `WINHTTP!WinHttpOpenRequest` at `0x180008aae`
- `WINHTTP!WinHttpOpenRequest` at `0x180008aae`
- `WINHTTP!WinHttpSendRequest` at `0x180008b4b`
- `WINHTTP!WinHttpSendRequest` at `0x180008b4b`
- `WINHTTP!WinHttpReceiveResponse` at `0x180008b77`
- `WINHTTP!WinHttpReceiveResponse` at `0x180008b77`
- `WINHTTP!WinHttpQueryOption` at `0x180008bd5`
- `WINHTTP!WinHttpQueryOption` at `0x180008bd5`

## string_xrefs

- `0x180008ae1`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180008b5d`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180008b89`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HttpRequest::Send(__int64 *a1, __int64 a2)
{
  __int64 *v4; // r12
  const WCHAR *v5; // r8
  const WCHAR *v6; // rdx
  HINTERNET v7; // rbx
  const char *v8; // r9
  const WCHAR *v9; // rdx
  const char *v10; // r9
  const char *v11; // r9
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 *v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // r8
  DWORD dwBufferLength; // [rsp+A0h] [rbp-3A8h] BYREF
  int v23; // [rsp+A4h] [rbp-3A4h]
  __int64 v24; // [rsp+A8h] [rbp-3A0h]
  unsigned __int64 v25; // [rsp+B0h] [rbp-398h]
  __int64 v26; // [rsp+C0h] [rbp-388h]
  const wil::ResultException *v27; // [rsp+D0h] [rbp-378h] BYREF
  const wil::ResultException *v28; // [rsp+D8h] [rbp-370h] BYREF
  _OWORD v29[2]; // [rsp+E0h] [rbp-368h] BYREF
  _BYTE v30[32]; // [rsp+100h] [rbp-348h] BYREF
  LPCWSTR lpszHeaders[2]; // [rsp+120h] [rbp-328h] BYREF
  DWORD dwHeadersLength; // [rsp+130h] [rbp-318h]
  unsigned __int64 v33; // [rsp+138h] [rbp-310h]
  _DWORD Buffer[180]; // [rsp+140h] [rbp-308h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]

  v26 = a2;
  v23 = 1;
  v4 = a1 + 31;
  FlattenHeaders(lpszHeaders);
  if ( (unsigned __int64)a1[7] <= 7 )
    v5 = (const WCHAR *)(a1 + 4);
  else
    v5 = (const WCHAR *)a1[4];
  if ( (unsigned __int64)a1[11] <= 7 )
    v6 = (const WCHAR *)(a1 + 8);
  else
    v6 = (const WCHAR *)a1[8];
  v7 = WinHttpOpenRequest((HINTERNET)a1[22], v6, v5, 0, 0, 0, *((_BYTE *)a1 + 160) != 0 ? 0x800000 : 0);
  if ( v7 == (HINTERNET)a1[26] )
  {
    v7 = (HINTERNET)a1[26];
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(a1 + 25);
    a1[26] = (__int64)v7;
  }
  if ( !v7 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v8);
  HttpRequest::SetOptions((HttpRequest *)a1);
  a1[29] = GetTickCount64();
  try
  {
    v9 = (const WCHAR *)lpszHeaders;
    if ( v33 > 7 )
      v9 = lpszHeaders[0];
    if ( !WinHttpSendRequest(
            (HINTERNET)a1[26],
            v9,
            dwHeadersLength,
            (LPVOID)a1[27],
            *((_DWORD *)a1 + 56),
            *((_DWORD *)a1 + 56),
            0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2A8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v10);
    if ( !WinHttpReceiveResponse((HINTERNET)a1[26], 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2A9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v11);
  }
  catch ( const wil::ResultException *v28 )
  {
    HttpRequest::WriteHttpFailure((HttpRequest *)a1, *((_DWORD *)v28 + 8), 0, a1[28]);
    throw;
  }
  memset_0(Buffer, 0, 0x2C4u);
  dwBufferLength = 708;
  if ( WinHttpQueryOption((HINTERNET)a1[26], 0x97u, Buffer, &dwBufferLength) )
    *((_DWORD *)a1 + 60) = Buffer[0];
  try
  {
    v13 = a1[26];
    a1[26] = 0;
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
    *(_DWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
    *(_QWORD *)(a2 + 48) = v13;
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    v23 = 1;
    v14 = HttpResponse::StatusCode((HttpResponse *)a2);
  }
  catch ( const wil::ResultException *v27 )
  {
    HttpRequest::WriteHttpFailure((HttpRequest *)a1, *((_DWORD *)v27 + 8), 0, a1[28]);
    throw;
  }
  if ( v14 - 100 > 0x18F )
  {
    if ( *((_BYTE *)a1 + 161) )
    {
      v24 = a1[28];
      v25 = HttpRequest::CalculateLatency((HttpRequest *)a1);
      v29[0] = 0;
      v29[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v29[0]) = 0;
      std::wstring::wstring(v30, L"MS-CV");
      v15 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::count(
              v4,
              v30);
      ContentIdString::~ContentIdString((ContentIdString *)v30);
      if ( v15 )
      {
        std::wstring::wstring(v30, L"MS-CV");
        v16 = std::map<std::wstring,std::wstring>::at(v4, v30);
        std::wstring::operator=(v29, v16);
        ContentIdString::~ContentIdString((ContentIdString *)v30);
      }
      if ( (unsigned __int64)a1[3] <= 7 )
        v17 = a1;
      else
        v17 = (__int64 *)*a1;
      v18 = (_QWORD *)std::operator+<unsigned short>(v30, a1 + 16, a1 + 4);
      if ( v18[3] > 7u )
        v18 = (_QWORD *)*v18;
      EventWriteHttpRequestFailure(v18, v17, v19, v25, 0);
      ContentIdString::~ContentIdString((ContentIdString *)v30);
      ContentIdString::~ContentIdString((ContentIdString *)v29);
    }
  }
  else
  {
    HttpRequest::WriteHttpSuccess((HttpRequest *)a1, v14);
  }
  if ( v33 > 7 )
    std::_Deallocate<16>(lpszHeaders[0], 2 * v33 + 2);
  return a2;
}

```

## disassembly

```asm
0x1800089f4  mov     r11, rsp
0x1800089f7  mov     [r11+18h], rbx
0x1800089fb  mov     [r11+20h], rsi
0x1800089ff  push    rdi
0x180008a00  push    r12
0x180008a02  push    r13
0x180008a04  push    r14
0x180008a06  push    r15
0x180008a08  sub     rsp, 420h
0x180008a0f  mov     rax, cs:__security_cookie
0x180008a16  xor     rax, rsp
0x180008a19  mov     [rsp+448h+var_38], rax
0x180008a21  mov     rsi, rdx
0x180008a24  mov     rdi, rcx
0x180008a27  mov     [rsp+448h+var_3B8], rcx
0x180008a2f  mov     [r11-388h], rdx
0x180008a36  mov     [rsp+448h+var_3A4], 1
0x180008a41  lea     r12, [rcx+0F8h]
0x180008a48  mov     rdx, r12
0x180008a4b  lea     rcx, [r11-328h]; Src
0x180008a52  call    ?FlattenHeaders@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@Z; FlattenHeaders(std::map<std::wstring,std::wstring> const &)
0x180008a57  nop
0x180008a58  lea     r15, [rdi+0C8h]
0x180008a5f  mov     al, [rdi+0A0h]
0x180008a65  neg     al
0x180008a67  sbb     ecx, ecx
0x180008a69  and     ecx, 800000h
0x180008a6f  cmp     qword ptr [rdi+38h], 7
0x180008a74  jbe     short loc_180008A7C
0x180008a76  mov     r8, [rdi+20h]
0x180008a7a  jmp     short loc_180008A80
0x180008a7c  lea     r8, [rdi+20h]; pwszObjectName
0x180008a80  lea     r14, [rdi+40h]
0x180008a84  cmp     qword ptr [r14+18h], 7
0x180008a89  jbe     short loc_180008A90
0x180008a8b  mov     rdx, [r14]
0x180008a8e  jmp     short loc_180008A93
0x180008a90  mov     rdx, r14; pwszVerb
0x180008a93  mov     [rsp+448h+dwFlags], ecx; dwFlags
0x180008a97  xor     r13d, r13d
0x180008a9a  mov     [rsp+448h+ppwszAcceptTypes], r13; ppwszAcceptTypes
0x180008a9f  mov     [rsp+448h+pwszReferrer], r13; pwszReferrer
0x180008aa4  xor     r9d, r9d; pwszVersion
0x180008aa7  mov     rcx, [rdi+0B0h]; hConnect
0x180008aae  call    cs:__imp_WinHttpOpenRequest
0x180008ab4  mov     rbx, rax
0x180008ab7  cmp     rax, [r15+8]
0x180008abb  jz      short loc_180008ACB
0x180008abd  mov     rcx, r15
0x180008ac0  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x180008ac5  mov     [r15+8], rbx
0x180008ac9  jmp     short loc_180008ACF
0x180008acb  mov     rbx, [r15+8]
0x180008acf  test    rbx, rbx
0x180008ad2  setz    al
0x180008ad5  mov     rcx, [rsp+448h]; this
0x180008add  test    al, al
0x180008adf  jz      short loc_180008AF3
0x180008ae1  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x180008ae8  mov     edx, 29Dh; void *
0x180008aed  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008af3  mov     rcx, rdi; this
0x180008af6  call    ?SetOptions@HttpRequest@@AEAAXXZ; HttpRequest::SetOptions(void)
0x180008afb  call    cs:__imp_GetTickCount64
0x180008b01  mov     [rdi+0E8h], rax
0x180008b08  mov     eax, [rdi+0E0h]
0x180008b0e  lea     rdx, [rsp+448h+lpszHeaders]
0x180008b16  cmp     [rsp+448h+var_310], 7
0x180008b1f  cmova   rdx, [rsp+448h+lpszHeaders]; lpszHeaders
0x180008b28  mov     qword ptr [rsp+448h+dwFlags], r13; dwContext
0x180008b2d  mov     dword ptr [rsp+448h+ppwszAcceptTypes], eax; dwTotalLength
0x180008b31  mov     dword ptr [rsp+448h+pwszReferrer], eax; dwOptionalLength
0x180008b35  mov     r9, [rdi+0D8h]; lpOptional
0x180008b3c  mov     r8d, [rsp+448h+dwHeadersLength]; dwHeadersLength
0x180008b44  mov     rcx, [rdi+0D0h]; hRequest
0x180008b4b  call    cs:__imp_WinHttpSendRequest
0x180008b51  mov     rcx, [rsp+448h]; this
0x180008b59  test    eax, eax
0x180008b5b  jnz     short loc_180008B6E
0x180008b5d  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x180008b64  mov     edx, 2A8h; void *
0x180008b69  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008b6e  xor     edx, edx; lpReserved
0x180008b70  mov     rcx, [rdi+0D0h]; hRequest
0x180008b77  call    cs:__imp_WinHttpReceiveResponse
0x180008b7d  mov     rcx, [rsp+448h]; this
0x180008b85  test    eax, eax
0x180008b87  jnz     short loc_180008B9B
0x180008b89  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x180008b90  mov     edx, 2A9h; void *
0x180008b95  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008b9b  mov     ebx, 2C4h
0x180008ba0  mov     r8d, ebx; Size
0x180008ba3  xor     edx, edx; Val
0x180008ba5  lea     rcx, [rsp+448h+Buffer]; void *
0x180008bad  call    memset_0
0x180008bb2  mov     [rsp+448h+dwBufferLength], ebx
0x180008bb9  lea     r9, [rsp+448h+dwBufferLength]; lpdwBufferLength
0x180008bc1  lea     r8, [rsp+448h+Buffer]; lpBuffer
0x180008bc9  mov     edx, 97h; dwOption
0x180008bce  mov     rcx, [rdi+0D0h]; hInternet
0x180008bd5  call    cs:__imp_WinHttpQueryOption
0x180008bdb  test    eax, eax
0x180008bdd  jz      short loc_180008BEC
0x180008bdf  mov     eax, [rsp+448h+Buffer]
0x180008be6  mov     [rdi+0F0h], eax
0x180008bec  mov     rcx, [rdi+0D0h]
0x180008bf3  mov     [rdi+0D0h], r13
0x180008bfa  xorps   xmm0, xmm0
0x180008bfd  movups  xmmword ptr [rsi], xmm0
0x180008c00  mov     [rsi+10h], r13
0x180008c04  mov     qword ptr [rsi+18h], 7
0x180008c0c  mov     [rsi], r13w
0x180008c10  mov     [rsi+20h], r13d
0x180008c14  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x180008c1b  mov     [rsi+28h], rax
0x180008c1f  mov     [rsi+30h], rcx
0x180008c23  mov     [rsi+38h], r13
0x180008c27  mov     [rsi+40h], r13
0x180008c2b  mov     [rsp+448h+var_3A4], 1
0x180008c36  mov     rcx, rsi; this
0x180008c39  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x180008c3e  mov     r15d, eax
0x180008c41  add     eax, 0FFFFFF9Ch
0x180008c44  cmp     eax, 18Fh
0x180008c49  ja      short loc_180008C5C
0x180008c4b  movzx   edx, r15w; unsigned __int16
0x180008c4f  mov     rcx, rdi; this
0x180008c52  call    ?WriteHttpSuccess@HttpRequest@@AEAAXG@Z; HttpRequest::WriteHttpSuccess(ushort)
0x180008c57  jmp     loc_180008E0D
0x180008c5c  cmp     [rdi+0A1h], r13b
0x180008c63  jz      loc_180008E0D
0x180008c69  mov     rax, [rdi+0E0h]
0x180008c70  mov     [rsp+448h+var_3A0], rax
0x180008c78  mov     rcx, rdi; this
0x180008c7b  call    ?CalculateLatency@HttpRequest@@AEAA_KXZ; HttpRequest::CalculateLatency(void)
0x180008c80  mov     [rsp+448h+var_398], rax
0x180008c88  xorps   xmm0, xmm0
0x180008c8b  movups  [rsp+448h+var_368], xmm0
0x180008c93  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180008c9b  movdqu  [rsp+448h+var_358], xmm1
0x180008ca4  mov     word ptr [rsp+448h+var_368], r13w
0x180008cad  lea     rdx, aMsCv; "MS-CV"
0x180008cb4  lea     rcx, [rsp+448h+var_348]
0x180008cbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008cc1  lea     rdx, [rsp+448h+var_348]
0x180008cc9  mov     rcx, r12
0x180008ccc  call    ?count@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::count(std::wstring const &)
0x180008cd1  mov     rbx, rax
0x180008cd4  lea     rcx, [rsp+448h+var_348]; this
0x180008cdc  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180008ce1  test    rbx, rbx
0x180008ce4  jz      short loc_180008D29
0x180008ce6  lea     rdx, aMsCv; "MS-CV"
0x180008ced  lea     rcx, [rsp+448h+var_348]
0x180008cf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008cfa  nop
0x180008cfb  lea     rdx, [rsp+448h+var_348]
0x180008d03  mov     rcx, r12
0x180008d06  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::map<std::wstring,std::wstring>::at(std::wstring const &)
0x180008d0b  mov     rdx, rax
0x180008d0e  lea     rcx, [rsp+448h+var_368]
0x180008d16  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180008d1b  nop
0x180008d1c  lea     rcx, [rsp+448h+var_348]; this
0x180008d24  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180008d29  mov     eax, [rdi+0F0h]
0x180008d2f  mov     dword ptr [rsp+448h+var_3B8], eax
0x180008d36  lea     r12, [rsp+448h+var_368]
0x180008d3e  cmp     qword ptr [rsp+448h+var_358+8], 7
0x180008d47  cmova   r12, qword ptr [rsp+448h+var_368]
0x180008d50  lea     rax, aHttp; "HTTP"
0x180008d57  lea     r13, aHttps_0; "HTTPS"
0x180008d5e  cmp     byte ptr [rdi+0A0h], 0
0x180008d65  cmovz   r13, rax
0x180008d69  cmp     qword ptr [r14+18h], 7
0x180008d6e  jbe     short loc_180008D73
0x180008d70  mov     r14, [r14]
0x180008d73  cmp     qword ptr [rdi+18h], 7
0x180008d78  jbe     short loc_180008D7F
0x180008d7a  mov     rbx, [rdi]
0x180008d7d  jmp     short loc_180008D82
0x180008d7f  mov     rbx, rdi
0x180008d82  lea     rdx, [rdi+80h]
0x180008d89  lea     r8, [rdi+20h]
0x180008d8d  lea     rcx, [rsp+448h+var_348]
0x180008d95  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180008d9a  nop
0x180008d9b  cmp     qword ptr [rax+18h], 7
0x180008da0  jbe     short loc_180008DA5
0x180008da2  mov     rax, [rax]
0x180008da5  mov     ecx, dword ptr [rsp+448h+var_3B8]
0x180008dac  mov     [rsp+448h+var_3C0], ecx
0x180008db3  mov     [rsp+448h+var_3D0], r12
0x180008db8  mov     rcx, [rsp+448h+var_3A0]
0x180008dc0  mov     [rsp+448h+var_3D8], rcx
0x180008dc5  mov     [rsp+448h+var_400], r15w
0x180008dcb  mov     [rsp+448h+var_408], r13
0x180008dd0  mov     qword ptr [rsp+448h+dwFlags], r14
0x180008dd5  mov     dword ptr [rsp+448h+pwszReferrer], 0
0x180008ddd  mov     r9, [rsp+448h+var_398]
0x180008de5  mov     rdx, rbx
0x180008de8  mov     rcx, rax
0x180008deb  call    EventWriteHttpRequestFailure
0x180008df0  nop
0x180008df1  lea     rcx, [rsp+448h+var_348]; this
0x180008df9  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180008dfe  nop
0x180008dff  lea     rcx, [rsp+448h+var_368]; this
0x180008e07  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180008e0c  nop
0x180008e0d  mov     rdx, [rsp+448h+var_310]
0x180008e15  cmp     rdx, 7
0x180008e19  jbe     short loc_180008E30
0x180008e1b  lea     rdx, ds:2[rdx*2]
0x180008e23  mov     rcx, [rsp+448h+lpszHeaders]
0x180008e2b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008e30  mov     rax, rsi
0x180008e33  mov     rcx, [rsp+448h+var_38]
0x180008e3b  xor     rcx, rsp; StackCookie
0x180008e3e  call    __security_check_cookie
0x180008e43  lea     r11, [rsp+448h+var_28]
0x180008e4b  mov     rbx, [r11+40h]
0x180008e4f  mov     rsi, [r11+48h]
0x180008e53  mov     rsp, r11
0x180008e56  pop     r15
0x180008e58  pop     r14
0x180008e5a  pop     r13
0x180008e5c  pop     r12
0x180008e5e  pop     rdi
0x180008e5f  retn
```
