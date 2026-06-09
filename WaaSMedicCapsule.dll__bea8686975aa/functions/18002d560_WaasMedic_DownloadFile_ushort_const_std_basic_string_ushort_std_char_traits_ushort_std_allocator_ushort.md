# WaasMedic::DownloadFile(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002d560`
- end: `0x18002da5b`
- name: `?DownloadFile@WaasMedic@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1275`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002d398`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x1800070cc`
- `0x180007590`
- `0x180009a34`
- `0x180009a54`
- `0x180026920`
- `0x18002d560`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d956`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d721`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d721`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d7d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d7d1`
- `WINHTTP!WinHttpOpen` at `0x18002d60e`
- `WINHTTP!WinHttpOpen` at `0x18002d60e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d808`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d811`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d81a`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d85b`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d864`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d86d`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8b6`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8bf`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8c8`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d907`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d910`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d919`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d95f`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d968`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d971`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9a0`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9c2`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9eb`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d808`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d811`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d81a`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d85b`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d864`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d86d`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8b6`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8bf`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d8c8`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d907`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d910`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d919`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d95f`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d968`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d971`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9a0`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9c2`
- `WINHTTP!WinHttpCloseHandle` at `0x18002d9eb`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002d636`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002d636`
- `WINHTTP!WinHttpConnect` at `0x18002d65e`
- `WINHTTP!WinHttpConnect` at `0x18002d65e`
- `WINHTTP!WinHttpSendRequest` at `0x18002d6d1`
- `WINHTTP!WinHttpSendRequest` at `0x18002d6d1`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002d6e4`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002d6e4`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002d748`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002d748`
- `WINHTTP!WinHttpReadData` at `0x18002d79b`
- `WINHTTP!WinHttpReadData` at `0x18002d79b`
- `WINHTTP!WinHttpCrackUrl` at `0x18002d5c4`
- `WINHTTP!WinHttpCrackUrl` at `0x18002d5c4`
- `WINHTTP!WinHttpOpenRequest` at `0x18002d69b`
- `WINHTTP!WinHttpOpenRequest` at `0x18002d69b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d89f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d89f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d76e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d76e`

## string_xrefs

- `0x18002d5ba`: `https://msedgesetup.microsoft.com/products/msedgeupdate-stable-win-x86/1.3.195.57/MicrosoftEdgeUpdateSetup_X86_1.3.195.57.exe`
- `0x18002d601`: `Edge-Update-Download/1.0`
- `0x18002d87d`: `Error in WinHttpReadData`
- `0x18002d833`: `Error in WriteFile`

## pseudocode

```c
__int64 __fastcall WaasMedic::DownloadFile(__int64 a1, const WCHAR *a2)
{
  void *v3; // rax
  const char *v4; // r9
  void *v5; // rdi
  const char *v6; // r9
  const WCHAR *v7; // rdx
  void *v8; // rax
  void *v9; // r14
  void *v10; // rax
  const char *v11; // r9
  void *v12; // rsi
  const char *v13; // r9
  HANDLE FileW; // rbx
  __int64 v15; // rdx
  __int64 v16; // r12
  _WORD *v17; // rax
  void *v18; // r15
  const char *v20; // r9
  __int64 v21; // rdx
  unsigned int LastError; // ebx
  unsigned int v23; // r12d
  int LastErrorMsg; // r15d
  __int64 v25; // rdx
  const char *dwFlags; // [rsp+20h] [rbp-99h]
  const char *dwFlagsa; // [rsp+20h] [rbp-99h]
  DWORD dwNumberOfBytesAvailable; // [rsp+40h] [rbp-79h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+44h] [rbp-75h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-71h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-69h] BYREF
  LPCWSTR pswzServerName[2]; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v33; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = -1;
  UrlComponents.dwHostNameLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  UrlComponents.dwExtraInfoLength = -1;
  if ( !WinHttpCrackUrl(
          L"https://msedgesetup.microsoft.com/products/msedgeupdate-stable-win-x86/1.3.195.57/MicrosoftEdgeUpdateSetup_X86_1.3.195.57.exe",
          0,
          0,
          &UrlComponents) )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0xFF,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
             "Error in WinHttpCrackUrl",
             dwFlags);
  *(_OWORD *)pswzServerName = 0;
  v33 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    pswzServerName,
    UrlComponents.lpszHostName,
    UrlComponents.dwHostNameLength);
  v3 = WinHttpOpen(L"Edge-Update-Download/1.0", 4u, 0, 0, 0);
  v5 = v3;
  if ( !v3 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x108,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                  v4);
    goto LABEL_51;
  }
  if ( !WinHttpSetTimeouts(v3, 5000, 5000, 10000, 10000) )
  {
    v25 = 267;
    goto LABEL_48;
  }
  v7 = (const WCHAR *)pswzServerName;
  if ( *((_QWORD *)&v33 + 1) > 7u )
    v7 = pswzServerName[0];
  v8 = WinHttpConnect(v5, v7, 0x1BBu, 0);
  v9 = v8;
  if ( !v8 )
  {
    v25 = 274;
LABEL_48:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v25,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                  v6);
    goto LABEL_49;
  }
  v10 = WinHttpOpenRequest(v8, L"GET", (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, 0x800000u);
  v12 = v10;
  if ( !v10 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                  v11);
    goto LABEL_45;
  }
  if ( !WinHttpSendRequest(v10, 0, 0, 0, 0, 0, 0) )
  {
    v15 = 286;
    goto LABEL_43;
  }
  if ( !WinHttpReceiveResponse(v12, 0) )
  {
    v15 = 289;
    goto LABEL_43;
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 4u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v15 = 294;
LABEL_43:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                  v13);
    WinHttpCloseHandle(v12);
LABEL_45:
    WinHttpCloseHandle(v9);
LABEL_49:
    WinHttpCloseHandle(v5);
LABEL_51:
    std::wstring::~wstring(pswzServerName);
    return LastError;
  }
  while ( 1 )
  {
    dwNumberOfBytesAvailable = 0;
    if ( !WinHttpQueryDataAvailable(v12, &dwNumberOfBytesAvailable) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x12F,
                       (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                       "Error in WinHttpQueryDataAvailable",
                       dwFlagsa);
      goto LABEL_38;
    }
    if ( !dwNumberOfBytesAvailable )
      break;
    v16 = dwNumberOfBytesAvailable;
    v17 = LocalAlloc(0, 2LL * dwNumberOfBytesAvailable + 2);
    v18 = v17;
    if ( !v17 )
    {
      LastErrorMsg = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
        (const char *)0x8007000ELL,
        (int)dwFlagsa);
LABEL_38:
      if ( FileW )
        CloseHandle(FileW);
      WinHttpCloseHandle(v12);
      WinHttpCloseHandle(v9);
      WinHttpCloseHandle(v5);
      LastError = LastErrorMsg;
      goto LABEL_51;
    }
    *v17 = 0;
    v17[v16] = 0;
    dwNumberOfBytesRead = 0;
    if ( !WinHttpReadData(v12, v17, dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
    {
      v20 = "Error in WinHttpReadData";
      v21 = 326;
      goto LABEL_30;
    }
    if ( dwNumberOfBytesRead > dwNumberOfBytesAvailable )
    {
      LocalFree(v18);
      if ( FileW )
        CloseHandle(FileW);
      WinHttpCloseHandle(v12);
      WinHttpCloseHandle(v9);
      WinHttpCloseHandle(v5);
      LastError = -2147418113;
      goto LABEL_51;
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, v18, dwNumberOfBytesRead, &NumberOfBytesWritten, 0) )
    {
      v20 = "Error in WriteFile";
      v21 = 343;
LABEL_30:
      v23 = wil::details::in1diag3::Return_GetLastErrorMsg(
              retaddr,
              (void *)v21,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
              v20,
              dwFlagsa);
      LocalFree(v18);
      if ( FileW )
        CloseHandle(FileW);
      WinHttpCloseHandle(v12);
      WinHttpCloseHandle(v9);
      WinHttpCloseHandle(v5);
      LastError = v23;
      goto LABEL_51;
    }
    if ( dwNumberOfBytesRead != NumberOfBytesWritten )
    {
      LocalFree(v18);
      if ( FileW )
        CloseHandle(FileW);
      WinHttpCloseHandle(v12);
      WinHttpCloseHandle(v9);
      WinHttpCloseHandle(v5);
      std::wstring::~wstring(pswzServerName);
      return 2147500037LL;
    }
    LocalFree(v18);
  }
  if ( FileW )
    CloseHandle(FileW);
  WinHttpCloseHandle(v12);
  WinHttpCloseHandle(v9);
  WinHttpCloseHandle(v5);
  std::wstring::~wstring(pswzServerName);
  return 0;
}

```

## disassembly

```asm
0x18002d560  mov     [rsp-8+arg_0], rbx
0x18002d565  mov     [rsp-8+arg_10], rsi
0x18002d56a  push    rbp
0x18002d56b  push    rdi
0x18002d56c  push    r12
0x18002d56e  push    r14
0x18002d570  push    r15
0x18002d572  lea     rbp, [rsp-37h]
0x18002d577  sub     rsp, 0F0h
0x18002d57e  mov     rax, cs:__security_cookie
0x18002d585  xor     rax, rsp
0x18002d588  mov     [rbp+57h+var_30], rax
0x18002d58c  mov     rbx, rdx
0x18002d58f  lea     rcx, [rbp+57h+UrlComponents]; void *
0x18002d593  mov     edi, 68h ; 'h'
0x18002d598  xor     edx, edx; Val
0x18002d59a  mov     r8d, edi; Size
0x18002d59d  call    memset_0
0x18002d5a2  or      eax, 0FFFFFFFFh
0x18002d5a5  mov     [rbp+57h+UrlComponents.dwStructSize], edi
0x18002d5a8  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x18002d5ac  mov     [rbp+57h+UrlComponents.dwSchemeLength], eax
0x18002d5af  xor     r8d, r8d; dwFlags
0x18002d5b2  mov     [rbp+57h+UrlComponents.dwHostNameLength], eax
0x18002d5b5  xor     edx, edx; dwUrlLength
0x18002d5b7  mov     [rbp+57h+UrlComponents.dwUrlPathLength], eax
0x18002d5ba  lea     rcx, pwszUrl; "https://msedgesetup.microsoft.com/produ"...
0x18002d5c1  mov     [rbp+57h+UrlComponents.dwExtraInfoLength], eax
0x18002d5c4  call    cs:__imp_WinHttpCrackUrl
0x18002d5ca  test    eax, eax
0x18002d5cc  jz      loc_18002DA17
0x18002d5d2  mov     r8d, [rbp+57h+UrlComponents.dwHostNameLength]
0x18002d5d6  lea     rcx, [rbp+57h+pswzServerName]
0x18002d5da  mov     rdx, [rbp+57h+UrlComponents.lpszHostName]
0x18002d5de  xorps   xmm0, xmm0
0x18002d5e1  xorps   xmm1, xmm1
0x18002d5e4  movups  xmmword ptr [rbp+57h+pswzServerName], xmm0
0x18002d5e8  movdqu  [rbp+57h+var_40], xmm1
0x18002d5ed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d5f2  lea     r15d, [rdi-64h]
0x18002d5f6  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18002d5fe  mov     edx, r15d; dwAccessType
0x18002d601  lea     rcx, pszAgentW; "Edge-Update-Download/1.0"
0x18002d608  xor     r9d, r9d; pszProxyBypassW
0x18002d60b  xor     r8d, r8d; pszProxyW
0x18002d60e  call    cs:__imp_WinHttpOpen
0x18002d614  mov     rdi, rax
0x18002d617  test    rax, rax
0x18002d61a  jz      loc_18002D9F3
0x18002d620  mov     edx, 1388h; nResolveTimeout
0x18002d625  mov     r9d, 2710h; nSendTimeout
0x18002d62b  mov     r8d, edx; nConnectTimeout
0x18002d62e  mov     [rsp+110h+dwFlags], r9d; nReceiveTimeout
0x18002d633  mov     rcx, rax; hInternet
0x18002d636  call    cs:__imp_WinHttpSetTimeouts
0x18002d63c  test    eax, eax
0x18002d63e  jz      loc_18002D9D1
0x18002d644  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18002d649  lea     rdx, [rbp+57h+pswzServerName]
0x18002d64d  mov     r8d, 1BBh; nServerPort
0x18002d653  mov     rcx, rdi; hSession
0x18002d656  cmova   rdx, [rbp+57h+pswzServerName]; pswzServerName
0x18002d65b  xor     r9d, r9d; dwReserved
0x18002d65e  call    cs:__imp_WinHttpConnect
0x18002d664  mov     r14, rax
0x18002d667  test    rax, rax
0x18002d66a  jz      loc_18002D9CA
0x18002d670  mov     r8, [rbp+57h+UrlComponents.lpszUrlPath]; pwszObjectName
0x18002d674  lea     rdx, pwszVerb; "GET"
0x18002d67b  mov     [rsp+110h+var_E0], 800000h; dwFlags
0x18002d683  xor     r9d, r9d; pwszVersion
0x18002d686  mov     [rsp+110h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18002d68f  mov     rcx, rax; hConnect
0x18002d692  mov     qword ptr [rsp+110h+dwFlags], 0; pwszReferrer
0x18002d69b  call    cs:__imp_WinHttpOpenRequest
0x18002d6a1  mov     rsi, rax
0x18002d6a4  test    rax, rax
0x18002d6a7  jz      loc_18002D9A8
0x18002d6ad  mov     qword ptr [rsp+110h+var_E0], 0; dwContext
0x18002d6b6  xor     r9d, r9d; lpOptional
0x18002d6b9  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 0; dwTotalLength
0x18002d6c1  xor     r8d, r8d; dwHeadersLength
0x18002d6c4  xor     edx, edx; lpszHeaders
0x18002d6c6  mov     [rsp+110h+dwFlags], 0; dwOptionalLength
0x18002d6ce  mov     rcx, rax; hRequest
0x18002d6d1  call    cs:__imp_WinHttpSendRequest
0x18002d6d7  test    eax, eax
0x18002d6d9  jz      loc_18002D986
0x18002d6df  xor     edx, edx; lpReserved
0x18002d6e1  mov     rcx, rsi; hRequest
0x18002d6e4  call    cs:__imp_WinHttpReceiveResponse
0x18002d6ea  test    eax, eax
0x18002d6ec  jz      loc_18002D97F
0x18002d6f2  cmp     qword ptr [rbx+18h], 7
0x18002d6f7  jbe     short loc_18002D6FC
0x18002d6f9  mov     rbx, [rbx]
0x18002d6fc  xor     r9d, r9d; lpSecurityAttributes
0x18002d6ff  mov     qword ptr [rsp+110h+var_E0], 0; hTemplateFile
0x18002d708  mov     dword ptr [rsp+110h+ppwszAcceptTypes], 80h; dwFlagsAndAttributes
0x18002d710  mov     edx, 0C0000000h; dwDesiredAccess
0x18002d715  mov     rcx, rbx; lpFileName
0x18002d718  mov     [rsp+110h+dwFlags], r15d; char *
0x18002d71d  lea     r8d, [r9+1]; dwShareMode
0x18002d721  call    cs:__imp_CreateFileW
0x18002d727  mov     rbx, rax
0x18002d72a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d72e  jnz     short loc_18002D73A
0x18002d730  mov     edx, 126h
0x18002d735  jmp     loc_18002D98B
0x18002d73a  lea     rdx, [rbp+57h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18002d73e  mov     [rbp+57h+dwNumberOfBytesAvailable], 0
0x18002d745  mov     rcx, rsi; hRequest
0x18002d748  call    cs:__imp_WinHttpQueryDataAvailable
0x18002d74e  test    eax, eax
0x18002d750  jz      loc_18002D92F
0x18002d756  mov     eax, [rbp+57h+dwNumberOfBytesAvailable]
0x18002d759  test    eax, eax
0x18002d75b  jz      loc_18002D8F6
0x18002d761  lea     rdx, ds:2[rax*2]; uBytes
0x18002d769  xor     ecx, ecx; uFlags
0x18002d76b  mov     r12d, eax
0x18002d76e  call    cs:__imp_LocalAlloc
0x18002d774  mov     r15, rax
0x18002d777  test    rax, rax
0x18002d77a  jz      loc_18002D8D6
0x18002d780  xor     ecx, ecx
0x18002d782  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18002d786  mov     [rax], cx
0x18002d789  mov     rdx, rax; lpBuffer
0x18002d78c  mov     [rax+r12*2], cx
0x18002d791  mov     r8d, [rbp+57h+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x18002d795  mov     [rbp+57h+dwNumberOfBytesRead], ecx
0x18002d798  mov     rcx, rsi; hRequest
0x18002d79b  call    cs:__imp_WinHttpReadData
0x18002d7a1  test    eax, eax
0x18002d7a3  jz      loc_18002D87D
0x18002d7a9  mov     r8d, [rbp+57h+dwNumberOfBytesRead]; nNumberOfBytesToWrite
0x18002d7ad  cmp     r8d, [rbp+57h+dwNumberOfBytesAvailable]
0x18002d7b1  ja      loc_18002D841
0x18002d7b7  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d7bb  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18002d7c2  mov     rdx, r15; lpBuffer
0x18002d7c5  mov     qword ptr [rsp+110h+dwFlags], 0; lpOverlapped
0x18002d7ce  mov     rcx, rbx; hFile
0x18002d7d1  call    cs:__imp_WriteFile
0x18002d7d7  test    eax, eax
0x18002d7d9  jz      short loc_18002D833
0x18002d7db  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x18002d7de  mov     rcx, r15; hMem
0x18002d7e1  cmp     [rbp+57h+dwNumberOfBytesRead], eax
0x18002d7e4  jnz     short loc_18002D7F1
0x18002d7e6  call    cs:__imp_LocalFree
0x18002d7ec  jmp     loc_18002D73A
0x18002d7f1  call    cs:__imp_LocalFree
0x18002d7f7  test    rbx, rbx
0x18002d7fa  jz      short loc_18002D805
0x18002d7fc  mov     rcx, rbx; hObject
0x18002d7ff  call    cs:__imp_CloseHandle
0x18002d805  mov     rcx, rsi; hInternet
0x18002d808  call    cs:__imp_WinHttpCloseHandle
0x18002d80e  mov     rcx, r14; hInternet
0x18002d811  call    cs:__imp_WinHttpCloseHandle
0x18002d817  mov     rcx, rdi; hInternet
0x18002d81a  call    cs:__imp_WinHttpCloseHandle
0x18002d820  lea     rcx, [rbp+57h+pswzServerName]; void *
0x18002d824  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d829  mov     eax, 80004005h
0x18002d82e  jmp     loc_18002DA33
0x18002d833  lea     r9, aErrorInWritefi; "Error in WriteFile"
0x18002d83a  mov     edx, 157h
0x18002d83f  jmp     short loc_18002D889
0x18002d841  mov     rcx, r15; hMem
0x18002d844  call    cs:__imp_LocalFree
0x18002d84a  test    rbx, rbx
0x18002d84d  jz      short loc_18002D858
0x18002d84f  mov     rcx, rbx; hObject
0x18002d852  call    cs:__imp_CloseHandle
0x18002d858  mov     rcx, rsi; hInternet
0x18002d85b  call    cs:__imp_WinHttpCloseHandle
0x18002d861  mov     rcx, r14; hInternet
0x18002d864  call    cs:__imp_WinHttpCloseHandle
0x18002d86a  mov     rcx, rdi; hInternet
0x18002d86d  call    cs:__imp_WinHttpCloseHandle
0x18002d873  mov     ebx, 8000FFFFh
0x18002d878  jmp     loc_18002DA0A
0x18002d87d  lea     r9, aErrorInWinhttp_1; "Error in WinHttpReadData"
0x18002d884  mov     edx, 146h; void *
0x18002d889  mov     rcx, [rbp+5Fh]; this
0x18002d88d  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d894  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002d899  mov     rcx, r15; hMem
0x18002d89c  mov     r12d, eax
0x18002d89f  call    cs:__imp_LocalFree
0x18002d8a5  test    rbx, rbx
0x18002d8a8  jz      short loc_18002D8B3
0x18002d8aa  mov     rcx, rbx; hObject
0x18002d8ad  call    cs:__imp_CloseHandle
0x18002d8b3  mov     rcx, rsi; hInternet
0x18002d8b6  call    cs:__imp_WinHttpCloseHandle
0x18002d8bc  mov     rcx, r14; hInternet
0x18002d8bf  call    cs:__imp_WinHttpCloseHandle
0x18002d8c5  mov     rcx, rdi; hInternet
0x18002d8c8  call    cs:__imp_WinHttpCloseHandle
0x18002d8ce  mov     ebx, r12d
0x18002d8d1  jmp     loc_18002DA0A
0x18002d8d6  mov     rcx, [rbp+5Fh]; this
0x18002d8da  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d8e1  mov     r15d, 8007000Eh
0x18002d8e7  mov     edx, 13Ah; void *
0x18002d8ec  mov     r9d, r15d; char *
0x18002d8ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d8f4  jmp     short loc_18002D94E
0x18002d8f6  test    rbx, rbx
0x18002d8f9  jz      short loc_18002D904
0x18002d8fb  mov     rcx, rbx; hObject
0x18002d8fe  call    cs:__imp_CloseHandle
0x18002d904  mov     rcx, rsi; hInternet
0x18002d907  call    cs:__imp_WinHttpCloseHandle
0x18002d90d  mov     rcx, r14; hInternet
0x18002d910  call    cs:__imp_WinHttpCloseHandle
0x18002d916  mov     rcx, rdi; hInternet
0x18002d919  call    cs:__imp_WinHttpCloseHandle
0x18002d91f  lea     rcx, [rbp+57h+pswzServerName]; void *
0x18002d923  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d928  xor     eax, eax
0x18002d92a  jmp     loc_18002DA33
0x18002d92f  mov     rcx, [rbp+5Fh]; this
0x18002d933  lea     r9, aErrorInWinhttp; "Error in WinHttpQueryDataAvailable"
0x18002d93a  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d941  mov     edx, 12Fh; void *
0x18002d946  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002d94b  mov     r15d, eax
0x18002d94e  test    rbx, rbx
0x18002d951  jz      short loc_18002D95C
0x18002d953  mov     rcx, rbx; hObject
0x18002d956  call    cs:__imp_CloseHandle
0x18002d95c  mov     rcx, rsi; hInternet
0x18002d95f  call    cs:__imp_WinHttpCloseHandle
0x18002d965  mov     rcx, r14; hInternet
0x18002d968  call    cs:__imp_WinHttpCloseHandle
0x18002d96e  mov     rcx, rdi; hInternet
0x18002d971  call    cs:__imp_WinHttpCloseHandle
0x18002d977  mov     ebx, r15d
0x18002d97a  jmp     loc_18002DA0A
0x18002d97f  mov     edx, 121h
0x18002d984  jmp     short loc_18002D98B
0x18002d986  mov     edx, 11Eh; void *
0x18002d98b  mov     rcx, [rbp+5Fh]; this
0x18002d98f  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d996  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d99b  mov     rcx, rsi; hInternet
0x18002d99e  mov     ebx, eax
0x18002d9a0  call    cs:__imp_WinHttpCloseHandle
0x18002d9a6  jmp     short loc_18002D9BF
0x18002d9a8  mov     rcx, [rbp+5Fh]; this
0x18002d9ac  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d9b3  mov     edx, 11Ah; void *
0x18002d9b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d9bd  mov     ebx, eax
0x18002d9bf  mov     rcx, r14; hInternet
0x18002d9c2  call    cs:__imp_WinHttpCloseHandle
0x18002d9c8  jmp     short loc_18002D9E8
0x18002d9ca  mov     edx, 112h
0x18002d9cf  jmp     short loc_18002D9D6
0x18002d9d1  mov     edx, 10Bh; void *
0x18002d9d6  mov     rcx, [rbp+5Fh]; this
0x18002d9da  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d9e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d9e6  mov     ebx, eax
0x18002d9e8  mov     rcx, rdi; hInternet
0x18002d9eb  call    cs:__imp_WinHttpCloseHandle
0x18002d9f1  jmp     short loc_18002DA0A
0x18002d9f3  mov     rcx, [rbp+5Fh]; this
0x18002d9f7  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d9fe  mov     edx, 108h; void *
0x18002da03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002da08  mov     ebx, eax
0x18002da0a  lea     rcx, [rbp+57h+pswzServerName]; void *
0x18002da0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002da13  mov     eax, ebx
0x18002da15  jmp     short loc_18002DA33
0x18002da17  mov     rcx, [rbp+5Fh]; this
0x18002da1b  lea     r9, aErrorInWinhttp_0; "Error in WinHttpCrackUrl"
0x18002da22  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002da29  mov     edx, 0FFh; void *
0x18002da2e  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002da33  mov     rcx, [rbp+57h+var_30]
0x18002da37  xor     rcx, rsp; StackCookie
0x18002da3a  call    __security_check_cookie
0x18002da3f  lea     r11, [rsp+110h+var_20]
0x18002da47  mov     rbx, [r11+30h]
0x18002da4b  mov     rsi, [r11+40h]
0x18002da4f  mov     rsp, r11
0x18002da52  pop     r15
0x18002da54  pop     r14
0x18002da56  pop     r12
0x18002da58  pop     rdi
0x18002da59  pop     rbp
0x18002da5a  retn
```
