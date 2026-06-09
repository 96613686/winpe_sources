# HttpRequest::Send(void)

- ea: `0x180048138`
- end: `0x1800484ca`
- name: `?Send@HttpRequest@@QEAA?AVHttpResponse@@XZ`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800484d0`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18002fbb4`
- `0x180030a68`
- `0x180030aac`
- `0x180047448`
- `0x180048138`
- `0x180048cc0`
- `0x180048d5c`
- `0x180048fe0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048443`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800482b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800482b2`
- `WINHTTP!WinHttpSetOption` at `0x180048240`
- `WINHTTP!WinHttpSetOption` at `0x18004829c`
- `WINHTTP!WinHttpSetOption` at `0x180048240`
- `WINHTTP!WinHttpSetOption` at `0x18004829c`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004826c`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004826c`
- `WINHTTP!WinHttpQueryOption` at `0x18004836f`
- `WINHTTP!WinHttpQueryOption` at `0x18004836f`
- `WINHTTP!WinHttpOpenRequest` at `0x1800481da`
- `WINHTTP!WinHttpOpenRequest` at `0x1800481da`
- `WINHTTP!WinHttpSendRequest` at `0x180048306`
- `WINHTTP!WinHttpSendRequest` at `0x180048306`
- `WINHTTP!WinHttpReceiveResponse` at `0x180048325`
- `WINHTTP!WinHttpReceiveResponse` at `0x180048325`

## string_xrefs

- `0x18004845e`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180048470`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180048482`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x180048494`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1800484a6`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1800484b7`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HttpRequest::Send(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // r8
  const WCHAR *v5; // rdx
  void *v6; // rsi
  const char *v7; // r9
  void *v8; // rax
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  const WCHAR *v12; // rdx
  const char *v13; // r9
  const char *v14; // r9
  __int64 v16; // rcx
  unsigned int v17; // eax
  signed int LastError; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  __int64 *v23; // rbp
  int ErrorCode; // eax
  __int64 *v25; // rdx
  __int64 v26; // [rsp+0h] [rbp-398h] BYREF
  int Buffer; // [rsp+40h] [rbp-358h] BYREF
  DWORD dwBufferLength[3]; // [rsp+44h] [rbp-354h] BYREF
  HttpRequest *v29; // [rsp+50h] [rbp-348h]
  __int64 v30; // [rsp+60h] [rbp-338h]
  const wil::ResultException *v31; // [rsp+70h] [rbp-328h] BYREF
  const wil::ResultException *v32; // [rsp+78h] [rbp-320h] BYREF
  LPCWSTR lpszHeaders[2]; // [rsp+80h] [rbp-318h] BYREF
  DWORD dwHeadersLength; // [rsp+90h] [rbp-308h]
  unsigned __int64 v35; // [rsp+98h] [rbp-300h]
  _DWORD v36[180]; // [rsp+A0h] [rbp-2F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  v29 = (HttpRequest *)a1;
  v30 = a2;
  Buffer = 1;
  FlattenHeaders(lpszHeaders);
  v4 = (const WCHAR *)(a1 + 32);
  if ( *(_QWORD *)(a1 + 56) > 7u )
    v4 = *(const WCHAR **)v4;
  v5 = (const WCHAR *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 88) > 7u )
    v5 = *(const WCHAR **)v5;
  v6 = WinHttpOpenRequest(*(HINTERNET *)(a1 + 176), v5, v4, 0, 0, 0, *(_BYTE *)(a1 + 160) != 0 ? 0x800000 : 0);
  v8 = *(void **)(a1 + 208);
  if ( v6 == v8 )
  {
    v6 = *(void **)(a1 + 208);
  }
  else
  {
    if ( v8 && !(**(unsigned __int8 (__fastcall ***)(__int64))(a1 + 200))(a1 + 200) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v20, v21);
      __debugbreak();
    }
    *(_QWORD *)(a1 + 208) = v6;
  }
  if ( !v6 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x29D,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v7);
  Buffer = 0;
  if ( !WinHttpSetOption(v6, 0x4Du, &Buffer, 4u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x323,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v9);
  if ( !WinHttpSetTimeouts(*(HINTERNET *)(a1 + 208), 60000, 60000, 60000, 60000) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x325,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v10);
  if ( *(_BYTE *)(a1 + 160) && !WinHttpSetOption(*(HINTERNET *)(a1 + 208), 0x2Fu, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x329,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v11);
  *(_QWORD *)(a1 + 232) = GetTickCount64();
  v12 = (const WCHAR *)lpszHeaders;
  if ( v35 > 7 )
    v12 = lpszHeaders[0];
  if ( !WinHttpSendRequest(
          *(HINTERNET *)(a1 + 208),
          v12,
          dwHeadersLength,
          *(LPVOID *)(a1 + 216),
          *(_DWORD *)(a1 + 224),
          *(_DWORD *)(a1 + 224),
          0) )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2A8,
        (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v13);
    }
    catch ( const wil::ResultException *v32 )
    {
      v25 = &v26;
      v23 = v25;
      ErrorCode = wil::ResultException::GetErrorCode((wil::ResultException *)v25[15]);
      HttpRequest::WriteHttpFailure((HttpRequest *)v23[10], ErrorCode, 0, *(_QWORD *)(v23[10] + 224));
      throw;
    }
  }
  if ( !WinHttpReceiveResponse(*(HINTERNET *)(a1 + 208), 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2A9,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v14);
  memset_0(v36, 0, 0x2C4u);
  dwBufferLength[0] = 708;
  if ( WinHttpQueryOption(*(HINTERNET *)(a1 + 208), 0x97u, v36, dwBufferLength) )
    *(_DWORD *)(a1 + 240) = v36[0];
  try
  {
    v16 = *(_QWORD *)(a1 + 208);
    *(_QWORD *)(a1 + 208) = 0;
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
    *(_DWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
    *(_QWORD *)(a2 + 48) = v16;
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    Buffer = 1;
    v17 = HttpResponse::StatusCode((HttpResponse *)a2);
  }
  catch ( const wil::ResultException *v31 )
  {
    v22 = wil::ResultException::GetErrorCode(v31);
    HttpRequest::WriteHttpFailure(v29, v22, 0, *((_QWORD *)v29 + 28));
    throw;
  }
  if ( v17 - 100 > 0x18F )
    HttpRequest::WriteHttpFailure((HttpRequest *)a1, 0, v17, *(_QWORD *)(a1 + 224));
  else
    HttpRequest::WriteHttpSuccess((HttpRequest *)a1, v17);
  std::wstring::_Tidy_deallocate((char **)lpszHeaders);
  return a2;
}

```

## disassembly

```asm
0x180048138  mov     [rsp+arg_10], rbx
0x18004813d  push    rsi
0x18004813e  push    rdi
0x18004813f  push    r14
0x180048141  sub     rsp, 380h
0x180048148  mov     rax, cs:__security_cookie
0x18004814f  xor     rax, rsp
0x180048152  mov     [rsp+398h+var_28], rax
0x18004815a  mov     rdi, rdx
0x18004815d  mov     rbx, rcx
0x180048160  mov     [rsp+398h+var_348], rcx
0x180048165  mov     [rsp+398h+var_338], rdx
0x18004816a  mov     [rsp+398h+Buffer], 1
0x180048172  lea     rdx, [rcx+0F8h]
0x180048179  lea     rcx, [rsp+398h+lpszHeaders]; Src
0x180048181  call    ?FlattenHeaders@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@Z; FlattenHeaders(std::map<std::wstring,std::wstring> const &)
0x180048186  nop
0x180048187  lea     r14, [rbx+0C8h]
0x18004818e  mov     al, [rbx+0A0h]
0x180048194  neg     al
0x180048196  sbb     ecx, ecx
0x180048198  and     ecx, 800000h
0x18004819e  lea     r8, [rbx+20h]
0x1800481a2  cmp     qword ptr [r8+18h], 7
0x1800481a7  jbe     short loc_1800481AC
0x1800481a9  mov     r8, [r8]; pwszObjectName
0x1800481ac  lea     rdx, [rbx+40h]
0x1800481b0  cmp     qword ptr [rdx+18h], 7
0x1800481b5  jbe     short loc_1800481BA
0x1800481b7  mov     rdx, [rdx]; pwszVerb
0x1800481ba  mov     [rsp+398h+dwFlags], ecx; dwFlags
0x1800481be  mov     [rsp+398h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1800481c7  mov     [rsp+398h+pwszReferrer], 0; pwszReferrer
0x1800481d0  xor     r9d, r9d; pwszVersion
0x1800481d3  mov     rcx, [rbx+0B0h]; hConnect
0x1800481da  call    cs:__imp_WinHttpOpenRequest
0x1800481e0  mov     rsi, rax
0x1800481e3  mov     rax, [r14+8]
0x1800481e7  cmp     rsi, rax
0x1800481ea  jz      short loc_18004820D
0x1800481ec  test    rax, rax
0x1800481ef  jz      short loc_180048207
0x1800481f1  mov     rax, [r14]
0x1800481f4  mov     rcx, r14
0x1800481f7  mov     rax, [rax]
0x1800481fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481ff  test    al, al
0x180048201  jz      loc_180048443
0x180048207  mov     [r14+8], rsi
0x18004820b  jmp     short loc_180048210
0x18004820d  mov     rsi, rax
0x180048210  test    rsi, rsi
0x180048213  setz    al
0x180048216  mov     rcx, [rsp+398h]; this
0x18004821e  test    al, al
0x180048220  jnz     loc_18004845E
0x180048226  mov     [rsp+398h+Buffer], 0
0x18004822e  mov     r9d, 4; dwBufferLength
0x180048234  lea     r8, [rsp+398h+Buffer]; lpBuffer
0x180048239  lea     edx, [r9+49h]; dwOption
0x18004823d  mov     rcx, rsi; hInternet
0x180048240  call    cs:__imp_WinHttpSetOption
0x180048246  mov     rcx, [rsp+398h]; this
0x18004824e  test    eax, eax
0x180048250  jz      loc_180048470
0x180048256  mov     edx, 0EA60h; nResolveTimeout
0x18004825b  mov     dword ptr [rsp+398h+pwszReferrer], edx; nReceiveTimeout
0x18004825f  mov     r9d, edx; nSendTimeout
0x180048262  mov     r8d, edx; nConnectTimeout
0x180048265  mov     rcx, [rbx+0D0h]; hInternet
0x18004826c  call    cs:__imp_WinHttpSetTimeouts
0x180048272  mov     rcx, [rsp+398h]; this
0x18004827a  test    eax, eax
0x18004827c  jz      loc_180048482
0x180048282  cmp     byte ptr [rbx+0A0h], 0
0x180048289  jz      short loc_1800482B2
0x18004828b  xor     r9d, r9d; dwBufferLength
0x18004828e  xor     r8d, r8d; lpBuffer
0x180048291  lea     edx, [r9+2Fh]; dwOption
0x180048295  mov     rcx, [rbx+0D0h]; hInternet
0x18004829c  call    cs:__imp_WinHttpSetOption
0x1800482a2  mov     rcx, [rsp+398h]; this
0x1800482aa  test    eax, eax
0x1800482ac  jz      loc_180048494
0x1800482b2  call    cs:__imp_GetTickCount64
0x1800482b8  mov     [rbx+0E8h], rax
0x1800482bf  mov     eax, [rbx+0E0h]
0x1800482c5  lea     rdx, [rsp+398h+lpszHeaders]
0x1800482cd  cmp     [rsp+398h+var_300], 7
0x1800482d6  cmova   rdx, [rsp+398h+lpszHeaders]; lpszHeaders
0x1800482df  mov     qword ptr [rsp+398h+dwFlags], 0; dwContext
0x1800482e8  mov     dword ptr [rsp+398h+ppwszAcceptTypes], eax; dwTotalLength
0x1800482ec  mov     dword ptr [rsp+398h+pwszReferrer], eax; dwOptionalLength
0x1800482f0  mov     r9, [rbx+0D8h]; lpOptional
0x1800482f7  mov     r8d, [rsp+398h+dwHeadersLength]; dwHeadersLength
0x1800482ff  mov     rcx, [rbx+0D0h]; hRequest
0x180048306  call    cs:__imp_WinHttpSendRequest
0x18004830c  mov     rcx, [rsp+398h]; this
0x180048314  test    eax, eax
0x180048316  jz      loc_1800484A6
0x18004831c  xor     edx, edx; lpReserved
0x18004831e  mov     rcx, [rbx+0D0h]; hRequest
0x180048325  call    cs:__imp_WinHttpReceiveResponse
0x18004832b  mov     rcx, [rsp+398h]; this
0x180048333  test    eax, eax
0x180048335  jz      loc_1800484B7
0x18004833b  mov     esi, 2C4h
0x180048340  mov     r8d, esi; Size
0x180048343  xor     edx, edx; Val
0x180048345  lea     rcx, [rsp+398h+var_2F8]; void *
0x18004834d  call    memset_0
0x180048352  mov     [rsp+398h+dwBufferLength], esi
0x180048356  lea     r9, [rsp+398h+dwBufferLength]; lpdwBufferLength
0x18004835b  lea     r8, [rsp+398h+var_2F8]; lpBuffer
0x180048363  mov     edx, 97h; dwOption
0x180048368  mov     rcx, [rbx+0D0h]; hInternet
0x18004836f  call    cs:__imp_WinHttpQueryOption
0x180048375  test    eax, eax
0x180048377  jz      short loc_180048386
0x180048379  mov     eax, [rsp+398h+var_2F8]
0x180048380  mov     [rbx+0F0h], eax
0x180048386  mov     rcx, [rbx+0D0h]
0x18004838d  mov     qword ptr [rbx+0D0h], 0
0x180048398  xorps   xmm0, xmm0
0x18004839b  movups  xmmword ptr [rdi], xmm0
0x18004839e  mov     qword ptr [rdi+10h], 0
0x1800483a6  mov     qword ptr [rdi+18h], 7
0x1800483ae  xor     eax, eax
0x1800483b0  mov     [rdi], ax
0x1800483b3  mov     [rdi+20h], eax
0x1800483b6  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x1800483bd  mov     [rdi+28h], rax
0x1800483c1  mov     [rdi+30h], rcx
0x1800483c5  mov     qword ptr [rdi+38h], 0
0x1800483cd  mov     qword ptr [rdi+40h], 0
0x1800483d5  mov     [rsp+398h+Buffer], 1
0x1800483dd  mov     rcx, rdi; this
0x1800483e0  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x1800483e5  mov     r8d, eax; unsigned __int16
0x1800483e8  add     eax, 0FFFFFF9Ch
0x1800483eb  mov     rcx, rbx; this
0x1800483ee  cmp     eax, 18Fh
0x1800483f3  ja      short loc_180048400
0x1800483f5  movzx   edx, r8w; unsigned __int16
0x1800483f9  call    ?WriteHttpSuccess@HttpRequest@@AEAAXG@Z; HttpRequest::WriteHttpSuccess(ushort)
0x1800483fe  jmp     short loc_18004840F
0x180048400  mov     r9, [rbx+0E0h]; unsigned __int64
0x180048407  xor     edx, edx; int
0x180048409  call    ?WriteHttpFailure@HttpRequest@@AEAAXJG_K@Z; HttpRequest::WriteHttpFailure(long,ushort,unsigned __int64)
0x18004840e  nop
0x18004840f  lea     rcx, [rsp+398h+lpszHeaders]
0x180048417  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004841c  mov     rax, rdi
0x18004841f  mov     rcx, [rsp+398h+var_28]
0x180048427  xor     rcx, rsp; StackCookie
0x18004842a  call    __security_check_cookie
0x18004842f  mov     rbx, [rsp+398h+arg_10]
0x180048437  add     rsp, 380h
0x18004843e  pop     r14
0x180048440  pop     rdi
0x180048441  pop     rsi
0x180048442  retn
0x180048443  call    cs:__imp_GetLastError
0x180048449  nop
0x18004844a  test    eax, eax
0x18004844c  jle     short loc_180048456
0x18004844e  movzx   eax, ax
0x180048451  or      eax, 80070000h
0x180048456  mov     ecx, eax; this
0x180048458  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004845d  int     3; Trap to Debugger
0x18004845e  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048465  mov     edx, 29Dh; void *
0x18004846a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180048470  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048477  mov     edx, 323h; void *
0x18004847c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180048482  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048489  mov     edx, 325h; void *
0x18004848e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180048494  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004849b  mov     edx, 329h; void *
0x1800484a0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800484a6  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800484ad  mov     edx, 2A8h; void *
0x1800484b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800484b7  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800484be  mov     edx, 2A9h; void *
0x1800484c3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
