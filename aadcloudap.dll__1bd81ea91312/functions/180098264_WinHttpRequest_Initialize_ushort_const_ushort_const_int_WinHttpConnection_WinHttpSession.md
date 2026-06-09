# WinHttpRequest::Initialize(ushort const *,ushort const *,int,WinHttpConnection &,WinHttpSession &)

- ea: `0x180098264`
- end: `0x1800985dd`
- name: `?Initialize@WinHttpRequest@@QEAAJPEBG0HAEAVWinHttpConnection@@AEAVWinHttpSession@@@Z`
- size: `889`
- prototype: `int(WinHttpRequest *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, struct WinHttpConnection *, struct WinHttpSession *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180097cb8`

## callees

- `0x180005f24`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008aecc`
- `0x18008b32c`
- `0x18008c0ac`
- `0x180094c94`
- `0x180095cbc`
- `0x1800981c8`
- `0x180098264`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009833b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009833b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098573`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800983d4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180098527`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800983d4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180098527`
- `WINHTTP!WinHttpOpenRequest` at `0x1800983a6`
- `WINHTTP!WinHttpOpenRequest` at `0x1800983a6`
- `WINHTTP!WinHttpSetTimeouts` at `0x180098569`
- `WINHTTP!WinHttpSetTimeouts` at `0x180098569`

## string_xrefs

- `0x18009842d`: `EventWriteWinhttpOpenRequestFailureEvent`
- `0x180098434`: `Logger::WriteWinhttpOpenRequestFailureEvent`
- `0x18009828f`: `pcszPath`
- `0x1800982aa`: `pcszPath`
- `0x180098364`: `WinHttpConnection::CreateUrl`
- `0x18009830f`: `%s: Path: "%s". Verb: %s. bIsSecure: %s. UseAutoProxy: %s.`
- `0x18009844f`: `WinHttpOpenRequest`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::Initialize(
        WinHttpRequest *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        HINTERNET *a5,
        struct WinHttpSession *a6)
{
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rdx
  const wchar_t *v11; // rax
  int v12; // ecx
  void *v13; // rcx
  int Url; // eax
  HINTERNET v15; // rax
  int v16; // r15d
  DWORD v17; // edi
  const wchar_t *v18; // r8
  DWORD LastError; // eax
  int v20; // edx
  int v21; // ecx
  unsigned int v22; // eax
  _QWORD *v23; // rax
  __int64 (__fastcall ***v24)(_QWORD, __int64); // rdx
  int v25; // eax
  signed int v26; // eax

  if ( !a2 )
  {
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::Initialize", L"pcszPath");
    v10 = L"pcszPath";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpRequest::Initialize", v10);
    return v9;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::Initialize", L"pcszVerb");
    v10 = L"pcszVerb";
    goto LABEL_3;
  }
  v11 = L"TRUE";
  v12 = *((_DWORD *)a6 + 4);
  *((_DWORD *)this + 41) = v12;
  if ( !v12 )
    v11 = L"FALSE";
  Logger::TraceVerbose(
    L"%s: Path: \"%s\". Verb: %s. bIsSecure: %s. UseAutoProxy: %s.",
    L"WinHttpRequest::Initialize",
    a2,
    a3,
    L"TRUE",
    v11);
  v13 = (void *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    free(v13);
    *((_QWORD *)this + 7) = 0;
  }
  Url = WinHttpConnection::CreateUrl((WinHttpConnection *)a5, (unsigned __int16 **)this + 7);
  v9 = Url;
  if ( Url < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpRequest::Initialize",
      L"WinHttpConnection::CreateUrl",
      (unsigned int)Url);
    return v9;
  }
  v15 = WinHttpOpenRequest(a5[1], a3, a2, 0, 0, 0, 0x800000u);
  *((_QWORD *)this + 1) = v15;
  v16 = 2;
  if ( !v15 )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v22 = McTemplateU0zqq_EventWriteTransfer(v21, v20, (_DWORD)a3, 0x800000, LastError);
      if ( v22 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpOpenRequestFailureEvent",
          L"EventWriteWinhttpOpenRequestFailureEvent",
          v22);
    }
    if ( v17 )
    {
      v18 = L"WinHttpOpenRequest";
LABEL_21:
      Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"WinHttpRequest::Initialize", v18, v17);
      if ( (int)v17 > 0 )
        return (unsigned __int16)v17 | 0x80070000;
      else
        return v17;
    }
  }
  if ( WinHttpSetStatusCallback(*((HINTERNET *)this + 1), WinHttpRequest::AsyncCallback, 0x6F4800u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    v17 = GetLastError();
    Logger::WriteWinhttpSetCallbackFailureEvent(0x6F4800u, v17);
    if ( v17 )
      goto LABEL_15;
  }
  if ( !*((_DWORD *)this + 41) )
  {
    v23 = operator new[](0x10u, (const struct std::nothrow_t *)std::nothrow);
    if ( !v23 )
    {
      v9 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::Initialize");
      return v9;
    }
    *(_OWORD *)v23 = 0;
    *v23 = &WinHttpHandle::`vftable';
    do
    {
      v23[1] = 0;
      --v16;
    }
    while ( v16 );
    *v23 = &WinHttpHandle::`vftable';
    v24 = (__int64 (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = v23;
    if ( v24 )
      std::default_delete<WinHttpProxyResolver>::operator()((__int64)&WinHttpHandle::`vftable', v24);
    v25 = WinHttpProxyResolver::Initialize(*((WinHttpProxyResolver **)this + 15), a6);
    v9 = v25;
    if ( v25 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"WinHttpRequest::Initialize",
        L"WinHttpProxyResolver::Intialize",
        (unsigned int)v25);
      return v9;
    }
    if ( WinHttpSetStatusCallback(
           *(HINTERNET *)(*((_QWORD *)this + 15) + 8LL),
           WinHttpRequest::AsyncCallback,
           0x1200000u,
           0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      v17 = GetLastError();
      Logger::WriteWinhttpSetCallbackFailureEvent(0x1200000u, v17);
      if ( v17 )
      {
LABEL_15:
        v18 = L"WinHttpSetStatusCallback";
        goto LABEL_21;
      }
    }
  }
  if ( !WinHttpSetTimeouts(*((HINTERNET *)this + 1), 0, 60000, 30000, *((_DWORD *)this + 42)) )
  {
    v26 = GetLastError();
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    Logger::TraceWarning(
      L"%s: WinHttpSetTimeouts failed with error code 0x%08X. Continuing with default timeouts.",
      L"WinHttpRequest::Initialize",
      (unsigned int)v26);
  }
  return v9;
}

```

## disassembly

```asm
0x180098264  mov     [rsp+arg_0], rbx
0x180098269  mov     [rsp+arg_10], rbp
0x18009826e  push    rsi
0x18009826f  push    rdi
0x180098270  push    r13
0x180098272  push    r14
0x180098274  push    r15
0x180098276  sub     rsp, 40h
0x18009827a  lea     rsi, aWinhttprequest_0; "WinHttpRequest::Initialize"
0x180098281  mov     r14, r8
0x180098284  mov     rdi, rdx
0x180098287  mov     rbp, rcx
0x18009828a  test    rdx, rdx
0x18009828d  jnz     short loc_1800982BE
0x18009828f  lea     r8, aPcszpath; "pcszPath"
0x180098296  mov     rdx, rsi
0x180098299  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800982a0  mov     ebx, 80070057h
0x1800982a5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800982aa  lea     rdx, aPcszpath; "pcszPath"
0x1800982b1  mov     rcx, rsi; unsigned __int16 *
0x1800982b4  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800982b9  jmp     loc_1800985C2
0x1800982be  test    r14, r14
0x1800982c1  jnz     short loc_1800982E7
0x1800982c3  lea     r8, aPcszverb; "pcszVerb"
0x1800982ca  mov     rdx, rsi
0x1800982cd  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800982d4  mov     ebx, 80070057h
0x1800982d9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800982de  lea     rdx, aPcszverb; "pcszVerb"
0x1800982e5  jmp     short loc_1800982B1
0x1800982e7  mov     r13, [rsp+68h+arg_28]
0x1800982ef  lea     r8, aTrue_0; "TRUE"
0x1800982f6  mov     rax, r8
0x1800982f9  lea     rdx, aFalse_0; "FALSE"
0x180098300  mov     r9, r14
0x180098303  mov     ecx, [r13+10h]
0x180098307  test    ecx, ecx
0x180098309  mov     [rbp+0A4h], ecx
0x18009830f  lea     rcx, aSPathSVerbSBis; "%s: Path: \"%s\". Verb: %s. bIsSecure: "...
0x180098316  cmovz   rax, rdx
0x18009831a  mov     rdx, rsi
0x18009831d  mov     [rsp+68h+ppwszAcceptTypes], rax
0x180098322  mov     [rsp+68h+pwszReferrer], r8
0x180098327  mov     r8, rdi
0x18009832a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009832f  lea     rbx, [rbp+38h]
0x180098333  mov     rcx, [rbx]; Block
0x180098336  test    rcx, rcx
0x180098339  jz      short loc_180098348
0x18009833b  call    cs:__imp_free
0x180098341  mov     qword ptr [rbx], 0
0x180098348  mov     r15, [rsp+68h+arg_20]
0x180098350  mov     rdx, rbx; unsigned __int16 **
0x180098353  mov     rcx, r15; this
0x180098356  call    ?CreateUrl@WinHttpConnection@@QEAAJPEAPEAG@Z; WinHttpConnection::CreateUrl(ushort * *)
0x18009835b  mov     ebx, eax
0x18009835d  test    eax, eax
0x18009835f  jns     short loc_18009837F
0x180098361  mov     r9d, eax
0x180098364  lea     r8, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x18009836b  mov     rdx, rsi
0x18009836e  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180098375  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009837a  jmp     loc_1800985C2
0x18009837f  mov     rcx, [r15+8]; hConnect
0x180098383  xor     r9d, r9d; pwszVersion
0x180098386  mov     [rsp+68h+dwFlags], 800000h; dwFlags
0x18009838e  mov     r8, rdi; pwszObjectName
0x180098391  mov     [rsp+68h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18009839a  mov     rdx, r14; pwszVerb
0x18009839d  mov     [rsp+68h+pwszReferrer], 0; pwszReferrer
0x1800983a6  call    cs:__imp_WinHttpOpenRequest
0x1800983ac  mov     [rbp+8], rax
0x1800983b0  mov     r15d, 2
0x1800983b6  test    rax, rax
0x1800983b9  jz      short loc_180098403
0x1800983bb  xor     edi, edi
0x1800983bd  mov     rcx, [rbp+8]; hInternet
0x1800983c1  lea     rdx, ?AsyncCallback@WinHttpRequest@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800983c8  mov     r14d, 6F4800h
0x1800983ce  xor     r9d, r9d; dwReserved
0x1800983d1  mov     r8d, r14d; dwNotificationFlags
0x1800983d4  call    cs:__imp_WinHttpSetStatusCallback
0x1800983da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800983de  jnz     loc_18009846D
0x1800983e4  call    cs:__imp_GetLastError
0x1800983ea  mov     edx, eax; unsigned int
0x1800983ec  mov     ecx, r14d; unsigned int
0x1800983ef  mov     edi, eax
0x1800983f1  call    ?WriteWinhttpSetCallbackFailureEvent@Logger@@SAJKK@Z; Logger::WriteWinhttpSetCallbackFailureEvent(ulong,ulong)
0x1800983f6  test    edi, edi
0x1800983f8  jz      short loc_18009846D
0x1800983fa  lea     r8, aWinhttpsetstat_0; "WinHttpSetStatusCallback"
0x180098401  jmp     short loc_180098456
0x180098403  call    cs:__imp_GetLastError
0x180098409  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, r15b
0x180098410  mov     edi, eax
0x180098412  jz      short loc_180098447
0x180098414  mov     r9d, 800000h
0x18009841a  mov     dword ptr [rsp+68h+pwszReferrer], eax
0x18009841e  mov     r8, r14
0x180098421  call    McTemplateU0zqq_EventWriteTransfer
0x180098426  test    eax, eax
0x180098428  jz      short loc_180098447
0x18009842a  mov     r9d, eax
0x18009842d  lea     r8, aEventwritewinh_12; "EventWriteWinhttpOpenRequestFailureEven"...
0x180098434  lea     rdx, aLoggerWritewin_7; "Logger::WriteWinhttpOpenRequestFailureE"...
0x18009843b  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180098442  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098447  test    edi, edi
0x180098449  jz      loc_1800983BD
0x18009844f  lea     r8, aWinhttpopenreq_0; "WinHttpOpenRequest"
0x180098456  mov     r9d, edi
0x180098459  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180098460  mov     rdx, rsi
0x180098463  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098468  jmp     loc_18009859B
0x18009846d  cmp     dword ptr [rbp+0A4h], 0
0x180098474  jnz     loc_18009854D
0x18009847a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180098481  mov     ecx, 10h; unsigned __int64
0x180098486  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009848b  mov     [rsp+68h+arg_8], rax
0x180098490  test    rax, rax
0x180098493  jz      loc_1800985A3
0x180098499  xorps   xmm0, xmm0
0x18009849c  lea     rcx, ??_7WinHttpHandle@@6B@; const WinHttpHandle::`vftable'
0x1800984a3  movups  xmmword ptr [rax], xmm0
0x1800984a6  mov     [rax], rcx
0x1800984a9  mov     qword ptr [rax+8], 0
0x1800984b1  sub     r15d, 1
0x1800984b5  jnz     short loc_1800984A9
0x1800984b7  lea     rcx, ??_7WinHttpHandle@@6B@; const WinHttpHandle::`vftable'
0x1800984be  mov     [rax], rcx
0x1800984c1  test    rax, rax
0x1800984c4  jz      loc_1800985A3
0x1800984ca  mov     rdx, [rbp+78h]
0x1800984ce  mov     [rbp+78h], rax
0x1800984d2  test    rdx, rdx
0x1800984d5  jz      short loc_1800984DC
0x1800984d7  call    ??R?$default_delete@VWinHttpProxyResolver@@@std@@QEBAXPEAVWinHttpProxyResolver@@@Z; std::default_delete<WinHttpProxyResolver>::operator()(WinHttpProxyResolver *)
0x1800984dc  mov     rcx, [rbp+78h]; this
0x1800984e0  mov     rdx, r13; struct WinHttpSession *
0x1800984e3  call    ?Initialize@WinHttpProxyResolver@@QEAAJAEAVWinHttpSession@@@Z; WinHttpProxyResolver::Initialize(WinHttpSession &)
0x1800984e8  mov     ebx, eax
0x1800984ea  test    eax, eax
0x1800984ec  jns     short loc_18009850C
0x1800984ee  mov     r9d, eax
0x1800984f1  lea     r8, aWinhttpproxyre_0; "WinHttpProxyResolver::Intialize"
0x1800984f8  mov     rdx, rsi
0x1800984fb  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180098502  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098507  jmp     loc_180098597
0x18009850c  mov     rcx, [rbp+78h]
0x180098510  lea     rdx, ?AsyncCallback@WinHttpRequest@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x180098517  mov     r14d, 1200000h
0x18009851d  xor     r9d, r9d; dwReserved
0x180098520  mov     r8d, r14d; dwNotificationFlags
0x180098523  mov     rcx, [rcx+8]; hInternet
0x180098527  call    cs:__imp_WinHttpSetStatusCallback
0x18009852d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180098531  jnz     short loc_18009854D
0x180098533  call    cs:__imp_GetLastError
0x180098539  mov     edx, eax; unsigned int
0x18009853b  mov     ecx, r14d; unsigned int
0x18009853e  mov     edi, eax
0x180098540  call    ?WriteWinhttpSetCallbackFailureEvent@Logger@@SAJKK@Z; Logger::WriteWinhttpSetCallbackFailureEvent(ulong,ulong)
0x180098545  test    edi, edi
0x180098547  jnz     loc_1800983FA
0x18009854d  mov     eax, [rbp+0A8h]
0x180098553  xor     edx, edx; nResolveTimeout
0x180098555  mov     rcx, [rbp+8]; hInternet
0x180098559  mov     r9d, 7530h; nSendTimeout
0x18009855f  mov     r8d, 0EA60h; nConnectTimeout
0x180098565  mov     dword ptr [rsp+68h+pwszReferrer], eax; nReceiveTimeout
0x180098569  call    cs:__imp_WinHttpSetTimeouts
0x18009856f  test    eax, eax
0x180098571  jnz     short loc_180098597
0x180098573  call    cs:__imp_GetLastError
0x180098579  test    eax, eax
0x18009857b  jle     short loc_180098585
0x18009857d  movzx   eax, ax
0x180098580  or      eax, 80070000h
0x180098585  mov     r8d, eax
0x180098588  lea     rcx, aSWinhttpsettim; "%s: WinHttpSetTimeouts failed with erro"...
0x18009858f  mov     rdx, rsi
0x180098592  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180098597  test    edi, edi
0x180098599  jz      short loc_1800985C2
0x18009859b  test    edi, edi
0x18009859d  jg      short loc_1800985B9
0x18009859f  mov     ebx, edi
0x1800985a1  jmp     short loc_1800985C2
0x1800985a3  mov     rdx, rsi
0x1800985a6  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800985ad  mov     ebx, 8007000Eh
0x1800985b2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800985b7  jmp     short loc_180098597
0x1800985b9  movzx   ebx, di
0x1800985bc  or      ebx, 80070000h
0x1800985c2  lea     r11, [rsp+68h+var_28]
0x1800985c7  mov     eax, ebx
0x1800985c9  mov     rbx, [r11+30h]
0x1800985cd  mov     rbp, [r11+40h]
0x1800985d1  mov     rsp, r11
0x1800985d4  pop     r15
0x1800985d6  pop     r14
0x1800985d8  pop     r13
0x1800985da  pop     rdi
0x1800985db  pop     rsi
0x1800985dc  retn
```
