# sih::network::HttpRequest::SendRequest(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,sockaddr * const)

- ea: `0x14001a790`
- end: `0x14001abb2`
- name: `?SendRequest@HttpRequest@network@sih@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00QEAUsockaddr@@@Z`
- size: `1058`
- prototype: `__int64 __fastcall(int, int, int, int, SOCKADDR *pSockaddr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001abb8`

## callees

- `0x1400154b4`
- `0x14001a790`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a82c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a82c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a973`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab66`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab79`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab87`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab66`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab79`
- `WINHTTP!WinHttpCloseHandle` at `0x14001ab87`
- `WINHTTP!WinHttpQueryHeaders` at `0x14001aaab`
- `WINHTTP!WinHttpQueryHeaders` at `0x14001aaab`
- `WINHTTP!WinHttpReceiveResponse` at `0x14001aa79`
- `WINHTTP!WinHttpReceiveResponse` at `0x14001aa79`
- `WINHTTP!WinHttpSendRequest` at `0x14001aa66`
- `WINHTTP!WinHttpSendRequest` at `0x14001aa66`
- `WINHTTP!WinHttpOpenRequest` at `0x14001aa3c`
- `WINHTTP!WinHttpOpenRequest` at `0x14001aa3c`
- `WINHTTP!WinHttpOpen` at `0x14001a803`
- `WINHTTP!WinHttpOpen` at `0x14001a803`
- `WINHTTP!WinHttpSetOption` at `0x14001a969`
- `WINHTTP!WinHttpSetOption` at `0x14001a969`
- `WINHTTP!WinHttpConnect` at `0x14001a864`
- `WINHTTP!WinHttpConnect` at `0x14001a864`
- `WS2_32!getnameinfo` at `0x14001a91e`
- `WS2_32!getnameinfo` at `0x14001a91e`

## string_xrefs

- `0x14001a9ae`: `WinHttpSetOption - Failed to associate the URL cache entry with an address info.host: %s, IP: %hs`
- `0x14001a9e9`: `WinHttpSetOption - WINHTTP_OPTION_STATIC_RESOLVER_CACHE_ENTRY for [%s][%hs]`

## pseudocode

```c
__int64 __fastcall sih::network::HttpRequest::SendRequest(
        const WCHAR *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        SOCKADDR *pSockaddr)
{
  bool v7; // cc
  void *v9; // r15
  signed int v10; // ebx
  void *v11; // rax
  void *v12; // r13
  signed int LastError; // ecx
  signed int v14; // eax
  bool v15; // sf
  signed int v16; // eax
  const WCHAR *v17; // rdx
  void *v18; // rax
  signed int v19; // eax
  signed int v20; // ecx
  int sa_family; // ecx
  unsigned int v22; // eax
  __int64 v23; // rdx
  const WCHAR *v24; // rax
  signed int v25; // eax
  const WCHAR *v26; // r8
  const WCHAR *v27; // rdx
  void *v28; // rax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsa[2]; // [rsp+20h] [rbp-E0h]
  void *hInternet; // [rsp+50h] [rbp-B0h]
  _QWORD Buffer[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v34[12]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+D0h] [rbp-30h] BYREF
  DWORD dwBufferLength[3]; // [rsp+D4h] [rbp-2Ch] BYREF
  CHAR pNodeBuffer[1040]; // [rsp+E0h] [rbp-20h] BYREF

  v7 = *((_QWORD *)a1 + 3) <= 7u;
  v35 = 0;
  v9 = 0;
  dwBufferLength[0] = 0;
  v10 = 0;
  hInternet = 0;
  if ( !v7 )
    a1 = *(const WCHAR **)a1;
  v11 = WinHttpOpen(a1, pSockaddr != 0 ? 1 : 4, 0, 0, 0);
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v14 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v14 = LastError;
    v15 = v14 < 0;
LABEL_7:
    if ( v15 )
    {
      v16 = GetLastError();
      v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        v10 = v16;
    }
    else
    {
      v10 = -2147467259;
    }
    goto LABEL_42;
  }
  v17 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v17 = *(const WCHAR **)a2;
  v18 = WinHttpConnect(v11, v17, 0x1BBu, 0);
  hInternet = v18;
  if ( !v18 )
  {
LABEL_15:
    v19 = GetLastError();
    v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      v20 = v19;
    v15 = v20 < 0;
    goto LABEL_7;
  }
  if ( !pSockaddr )
  {
LABEL_32:
    v26 = (const WCHAR *)a3;
    if ( *(_QWORD *)(a3 + 24) > 7u )
      v26 = *(const WCHAR **)a3;
    v27 = (const WCHAR *)a4;
    if ( *(_QWORD *)(a4 + 24) > 7u )
      v27 = *(const WCHAR **)a4;
    v28 = WinHttpOpenRequest(v18, v27, v26, 0, 0, 0, 0x800000u);
    v9 = v28;
    if ( v28 )
    {
      if ( WinHttpSendRequest(v28, 0, 0, 0, 0, 0, 0) )
      {
        if ( WinHttpReceiveResponse(v9, 0) )
        {
          dwBufferLength[0] = 4;
          if ( WinHttpQueryHeaders(v9, 0x20000013u, 0, &v35, dwBufferLength, 0) )
          {
            if ( v35 != 200 )
            {
              v10 = v35 | 0x80190000;
              WUTrace(0, 0, 0x400000, 5, 0, L"WinHttp: got failed status code from server %d\n");
            }
LABEL_42:
            if ( v10 >= 0 )
              goto LABEL_44;
            goto LABEL_43;
          }
        }
      }
    }
    goto LABEL_15;
  }
  memset(v34, 0, 0x58u);
  sa_family = pSockaddr->sa_family;
  v22 = 28;
  v34[4] = pSockaddr;
  LODWORD(v34[0]) = 0x80000000;
  HIDWORD(v34[0]) = sa_family;
  LODWORD(v34[1]) = 1;
  if ( sa_family == 2 )
    v22 = 16;
  HIDWORD(v34[1]) = 6;
  v7 = *((_QWORD *)a2 + 3) <= 7u;
  v23 = v22;
  v24 = a2;
  v34[2] = v23;
  LODWORD(v34[9]) = 2;
  if ( !v7 )
    v24 = *(const WCHAR **)a2;
  Buffer[0] = v24;
  Buffer[1] = v34;
  if ( getnameinfo(pSockaddr, v23, pNodeBuffer, 0x401u, 0, 0, 8) )
    WUTrace(0, 0, 0x400000, 3, 0, L"getnameinfo - Failed to convert to address[AF=%d] with [%d]");
  if ( WinHttpSetOption(v12, 0x7Fu, Buffer, 0x10u) )
  {
    WUTrace(0, 0, 0x400000, 5, 0, L"WinHttpSetOption - WINHTTP_OPTION_STATIC_RESOLVER_CACHE_ENTRY for [%s][%hs]");
    v18 = hInternet;
    goto LABEL_32;
  }
  v25 = GetLastError();
  v10 = (unsigned __int16)v25 | 0x80070000;
  if ( v25 <= 0 )
    v10 = v25;
  if ( v10 >= 0 )
    v10 = -2147418113;
  dwFlagsa[0] = v10;
  WUTrace(
    0,
    0,
    0x400000,
    3,
    *(_QWORD *)dwFlagsa,
    L"WinHttpSetOption - Failed to associate the URL cache entry with an address info.host: %s, IP: %hs");
LABEL_43:
  dwFlags[0] = v10;
  WUTrace("sih::network::HttpRequest::SendRequest", 181, 0x400000, 3, *(_QWORD *)dwFlags, L"%ls, %ls, %ls, %lu");
LABEL_44:
  if ( v9 )
    WinHttpCloseHandle(v9);
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v12 )
    WinHttpCloseHandle(v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001a790  push    rbp
0x14001a792  push    rbx
0x14001a793  push    rsi
0x14001a794  push    rdi
0x14001a795  push    r12
0x14001a797  push    r13
0x14001a799  push    r14
0x14001a79b  push    r15
0x14001a79d  lea     rbp, [rsp-408h]
0x14001a7a5  sub     rsp, 508h
0x14001a7ac  mov     rax, cs:__security_cookie
0x14001a7b3  xor     rax, rsp
0x14001a7b6  mov     [rbp+440h+var_50], rax
0x14001a7bd  mov     rdi, [rbp+440h+pSockaddr]
0x14001a7c4  mov     r14, r8
0x14001a7c7  xor     r8d, r8d; pszProxyW
0x14001a7ca  mov     r12, r9
0x14001a7cd  cmp     qword ptr [rcx+18h], 7
0x14001a7d2  mov     rsi, rdx
0x14001a7d5  mov     [rbp+440h+var_470], r8d
0x14001a7d9  mov     r15d, r8d
0x14001a7dc  mov     [rbp+440h+dwBufferLength], r8d
0x14001a7e0  mov     ebx, r8d
0x14001a7e3  mov     [rsp+540h+hInternet], r8
0x14001a7e8  jbe     short loc_14001A7ED
0x14001a7ea  mov     rcx, [rcx]; pszAgentW
0x14001a7ed  mov     rax, rdi
0x14001a7f0  mov     [rsp+540h+dwFlags], r8d; dwFlags
0x14001a7f5  neg     rax
0x14001a7f8  sbb     edx, edx
0x14001a7fa  xor     r9d, r9d; pszProxyBypassW
0x14001a7fd  and     edx, 0FFFFFFFDh
0x14001a800  add     edx, 4; dwAccessType
0x14001a803  call    cs:__imp_WinHttpOpen
0x14001a809  mov     r13, rax
0x14001a80c  test    rax, rax
0x14001a80f  jnz     short loc_14001A84B
0x14001a811  call    cs:__imp_GetLastError
0x14001a817  mov     ecx, eax
0x14001a819  mov     edi, 80070000h
0x14001a81e  movzx   eax, ax
0x14001a821  or      eax, edi
0x14001a823  test    ecx, ecx
0x14001a825  cmovle  eax, ecx
0x14001a828  test    eax, eax
0x14001a82a  jns     short loc_14001A841
0x14001a82c  call    cs:__imp_GetLastError
0x14001a832  movzx   ebx, ax
0x14001a835  or      ebx, edi
0x14001a837  test    eax, eax
0x14001a839  cmovle  ebx, eax
0x14001a83c  jmp     loc_14001AAF7
0x14001a841  mov     ebx, 80004005h
0x14001a846  jmp     loc_14001AAF7
0x14001a84b  cmp     qword ptr [rsi+18h], 7
0x14001a850  mov     rdx, rsi
0x14001a853  jbe     short loc_14001A858
0x14001a855  mov     rdx, [rsi]; pswzServerName
0x14001a858  mov     r8d, 1BBh; nServerPort
0x14001a85e  xor     r9d, r9d; dwReserved
0x14001a861  mov     rcx, r13; hSession
0x14001a864  call    cs:__imp_WinHttpConnect
0x14001a86a  mov     [rsp+540h+hInternet], rax
0x14001a86f  test    rax, rax
0x14001a872  jnz     short loc_14001A88D
0x14001a874  call    cs:__imp_GetLastError
0x14001a87a  movzx   ecx, ax
0x14001a87d  mov     edi, 80070000h
0x14001a882  or      ecx, edi
0x14001a884  test    eax, eax
0x14001a886  cmovle  ecx, eax
0x14001a889  test    ecx, ecx
0x14001a88b  jmp     short loc_14001A82A
0x14001a88d  test    rdi, rdi
0x14001a890  jz      loc_14001AA08
0x14001a896  xor     edx, edx; Val
0x14001a898  lea     rcx, [rsp+540h+var_4D0]; void *
0x14001a89d  lea     r8d, [rdx+58h]; Size
0x14001a8a1  call    memset
0x14001a8a6  movzx   ecx, word ptr [rdi]
0x14001a8a9  mov     eax, 1Ch
0x14001a8ae  cmp     ecx, 2
0x14001a8b1  mov     [rbp+440h+var_4B0], rdi
0x14001a8b5  mov     [rsp+540h+var_4D0], 80000000h
0x14001a8bd  mov     [rsp+540h+var_4CC], ecx
0x14001a8c1  lea     edx, [rax-0Ch]
0x14001a8c4  mov     [rsp+540h+var_4C8], 1
0x14001a8cc  cmovz   eax, edx
0x14001a8cf  mov     [rsp+540h+var_4C4], 6
0x14001a8d7  cmp     qword ptr [rsi+18h], 7
0x14001a8dc  mov     edx, eax; SockaddrLength
0x14001a8de  mov     rax, rsi
0x14001a8e1  mov     [rbp+440h+var_4C0], rdx
0x14001a8e5  mov     [rbp+440h+var_488], 2
0x14001a8ec  jbe     short loc_14001A8F1
0x14001a8ee  mov     rax, [rsi]
0x14001a8f1  mov     [rsp+540h+Buffer], rax
0x14001a8f6  lea     r8, [rbp+440h+pNodeBuffer]; pNodeBuffer
0x14001a8fa  lea     rax, [rsp+540h+var_4D0]
0x14001a8ff  mov     [rsp+540h+Flags], 8; Flags
0x14001a907  mov     [rsp+540h+ServiceBufferSize], ebx; ServiceBufferSize
0x14001a90b  mov     r9d, 401h; NodeBufferSize
0x14001a911  mov     rcx, rdi; pSockaddr
0x14001a914  mov     [rsp+540h+var_4E0], rax
0x14001a919  mov     qword ptr [rsp+540h+dwFlags], rbx; pServiceBuffer
0x14001a91e  call    cs:__imp_getnameinfo
0x14001a924  test    eax, eax
0x14001a926  jz      short loc_14001A957
0x14001a928  movzx   ecx, word ptr [rdi]
0x14001a92b  xor     edx, edx
0x14001a92d  mov     dword ptr [rsp+540h+var_508], eax
0x14001a931  mov     r8d, 400000h
0x14001a937  mov     [rsp+540h+Flags], ecx
0x14001a93b  lea     rax, aGetnameinfoFai; "getnameinfo - Failed to convert to addr"...
0x14001a942  mov     qword ptr [rsp+540h+ServiceBufferSize], rax
0x14001a947  xor     ecx, ecx
0x14001a949  lea     r9d, [rdx+3]
0x14001a94d  mov     qword ptr [rsp+540h+dwFlags], rbx
0x14001a952  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001a957  mov     r9d, 10h; dwBufferLength
0x14001a95d  lea     r8, [rsp+540h+Buffer]; lpBuffer
0x14001a962  mov     rcx, r13; hInternet
0x14001a965  lea     edx, [r9+6Fh]; dwOption
0x14001a969  call    cs:__imp_WinHttpSetOption
0x14001a96f  test    eax, eax
0x14001a971  jnz     short loc_14001A9CC
0x14001a973  call    cs:__imp_GetLastError
0x14001a979  movzx   ebx, ax
0x14001a97c  mov     r8d, 400000h
0x14001a982  or      ebx, 80070000h
0x14001a988  test    eax, eax
0x14001a98a  cmovle  ebx, eax
0x14001a98d  mov     eax, 8000FFFFh
0x14001a992  test    ebx, ebx
0x14001a994  cmovns  ebx, eax
0x14001a997  lea     rax, [rbp+440h+pNodeBuffer]
0x14001a99b  mov     [rsp+540h+var_508], rax
0x14001a9a0  xor     edx, edx
0x14001a9a2  mov     rax, [rsp+540h+Buffer]
0x14001a9a7  xor     ecx, ecx
0x14001a9a9  mov     qword ptr [rsp+540h+Flags], rax
0x14001a9ae  lea     rax, aWinhttpsetopti_1; "WinHttpSetOption - Failed to associate "...
0x14001a9b5  mov     qword ptr [rsp+540h+ServiceBufferSize], rax
0x14001a9ba  lea     r9d, [rdx+3]
0x14001a9be  mov     [rsp+540h+dwFlags], ebx
0x14001a9c2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001a9c7  jmp     loc_14001AAFB
0x14001a9cc  lea     rax, [rbp+440h+pNodeBuffer]
0x14001a9d0  xor     edx, edx
0x14001a9d2  mov     [rsp+540h+var_508], rax
0x14001a9d7  xor     ecx, ecx
0x14001a9d9  mov     rax, [rsp+540h+Buffer]
0x14001a9de  mov     r8d, 400000h
0x14001a9e4  mov     qword ptr [rsp+540h+Flags], rax
0x14001a9e9  lea     rax, aWinhttpsetopti_0; "WinHttpSetOption - WINHTTP_OPTION_STATI"...
0x14001a9f0  mov     qword ptr [rsp+540h+ServiceBufferSize], rax
0x14001a9f5  lea     r9d, [rdx+5]
0x14001a9f9  mov     qword ptr [rsp+540h+dwFlags], rbx
0x14001a9fe  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001aa03  mov     rax, [rsp+540h+hInternet]
0x14001aa08  cmp     qword ptr [r14+18h], 7
0x14001aa0d  mov     r8, r14
0x14001aa10  jbe     short loc_14001AA15
0x14001aa12  mov     r8, [r14]; pwszObjectName
0x14001aa15  cmp     qword ptr [r12+18h], 7
0x14001aa1b  mov     rdx, r12
0x14001aa1e  jbe     short loc_14001AA24
0x14001aa20  mov     rdx, [r12]; pwszVerb
0x14001aa24  mov     [rsp+540h+Flags], 800000h; dwFlags
0x14001aa2c  xor     r9d, r9d; pwszVersion
0x14001aa2f  mov     qword ptr [rsp+540h+ServiceBufferSize], rbx; ppwszAcceptTypes
0x14001aa34  mov     rcx, rax; hConnect
0x14001aa37  mov     qword ptr [rsp+540h+dwFlags], rbx; pwszReferrer
0x14001aa3c  call    cs:__imp_WinHttpOpenRequest
0x14001aa42  mov     r15, rax
0x14001aa45  test    rax, rax
0x14001aa48  jz      loc_14001A874
0x14001aa4e  mov     qword ptr [rsp+540h+Flags], rbx; dwContext
0x14001aa53  xor     r9d, r9d; lpOptional
0x14001aa56  mov     [rsp+540h+ServiceBufferSize], ebx; dwTotalLength
0x14001aa5a  xor     r8d, r8d; dwHeadersLength
0x14001aa5d  xor     edx, edx; lpszHeaders
0x14001aa5f  mov     [rsp+540h+dwFlags], ebx; dwOptionalLength
0x14001aa63  mov     rcx, rax; hRequest
0x14001aa66  call    cs:__imp_WinHttpSendRequest
0x14001aa6c  test    eax, eax
0x14001aa6e  jz      loc_14001A874
0x14001aa74  xor     edx, edx; lpReserved
0x14001aa76  mov     rcx, r15; hRequest
0x14001aa79  call    cs:__imp_WinHttpReceiveResponse
0x14001aa7f  test    eax, eax
0x14001aa81  jz      loc_14001A874
0x14001aa87  lea     rax, [rbp+440h+dwBufferLength]
0x14001aa8b  mov     qword ptr [rsp+540h+ServiceBufferSize], rbx; lpdwIndex
0x14001aa90  lea     r9, [rbp+440h+var_470]; lpBuffer
0x14001aa94  mov     qword ptr [rsp+540h+dwFlags], rax; lpdwBufferLength
0x14001aa99  xor     r8d, r8d; pwszName
0x14001aa9c  mov     [rbp+440h+dwBufferLength], 4
0x14001aaa3  mov     edx, 20000013h; dwInfoLevel
0x14001aaa8  mov     rcx, r15; hRequest
0x14001aaab  call    cs:__imp_WinHttpQueryHeaders
0x14001aab1  test    eax, eax
0x14001aab3  jz      loc_14001A874
0x14001aab9  mov     eax, [rbp+440h+var_470]
0x14001aabc  cmp     eax, 0C8h
0x14001aac1  jz      short loc_14001AAF7
0x14001aac3  mov     [rsp+540h+Flags], eax
0x14001aac7  mov     ebx, eax
0x14001aac9  xor     edx, edx
0x14001aacb  lea     rax, aWinhttpGotFail; "WinHttp: got failed status code from se"...
0x14001aad2  mov     qword ptr [rsp+540h+ServiceBufferSize], rax
0x14001aad7  or      ebx, 80190000h
0x14001aadd  xor     ecx, ecx
0x14001aadf  mov     qword ptr [rsp+540h+dwFlags], 0
0x14001aae8  mov     r8d, 400000h
0x14001aaee  lea     r9d, [rdx+5]
0x14001aaf2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001aaf7  test    ebx, ebx
0x14001aaf9  jns     short loc_14001AB5E
0x14001aafb  cmp     qword ptr [r12+18h], 7
0x14001ab01  jbe     short loc_14001AB07
0x14001ab03  mov     r12, [r12]
0x14001ab07  cmp     qword ptr [r14+18h], 7
0x14001ab0c  jbe     short loc_14001AB11
0x14001ab0e  mov     r14, [r14]
0x14001ab11  cmp     qword ptr [rsi+18h], 7
0x14001ab16  jbe     short loc_14001AB1B
0x14001ab18  mov     rsi, [rsi]
0x14001ab1b  mov     eax, [rbp+440h+var_470]
0x14001ab1e  lea     rcx, aSihNetworkHttp; "sih::network::HttpRequest::SendRequest"
0x14001ab25  mov     [rsp+540h+var_4F8], eax
0x14001ab29  mov     edx, 0B5h
0x14001ab2e  mov     [rsp+540h+var_500], r12
0x14001ab33  lea     rax, aLsLsLsLu; "%ls, %ls, %ls, %lu"
0x14001ab3a  mov     [rsp+540h+var_508], r14
0x14001ab3f  mov     r9d, 3
0x14001ab45  mov     qword ptr [rsp+540h+Flags], rsi
0x14001ab4a  mov     r8d, 400000h
0x14001ab50  mov     qword ptr [rsp+540h+ServiceBufferSize], rax
0x14001ab55  mov     [rsp+540h+dwFlags], ebx
0x14001ab59  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14001ab5e  test    r15, r15
0x14001ab61  jz      short loc_14001AB6C
0x14001ab63  mov     rcx, r15; hInternet
0x14001ab66  call    cs:__imp_WinHttpCloseHandle
0x14001ab6c  mov     rax, [rsp+540h+hInternet]
0x14001ab71  test    rax, rax
0x14001ab74  jz      short loc_14001AB7F
0x14001ab76  mov     rcx, rax; hInternet
0x14001ab79  call    cs:__imp_WinHttpCloseHandle
0x14001ab7f  test    r13, r13
0x14001ab82  jz      short loc_14001AB8D
0x14001ab84  mov     rcx, r13; hInternet
0x14001ab87  call    cs:__imp_WinHttpCloseHandle
0x14001ab8d  mov     eax, ebx
0x14001ab8f  mov     rcx, [rbp+440h+var_50]
0x14001ab96  xor     rcx, rsp; StackCookie
0x14001ab99  call    __security_check_cookie
0x14001ab9e  add     rsp, 508h
0x14001aba5  pop     r15
0x14001aba7  pop     r14
0x14001aba9  pop     r13
0x14001abab  pop     r12
0x14001abad  pop     rdi
0x14001abae  pop     rsi
0x14001abaf  pop     rbx
0x14001abb0  pop     rbp
0x14001abb1  retn
```
