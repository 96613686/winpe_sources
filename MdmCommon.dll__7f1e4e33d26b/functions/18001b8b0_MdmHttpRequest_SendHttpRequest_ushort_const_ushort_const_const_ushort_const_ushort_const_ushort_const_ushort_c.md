# MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)

- ea: `0x18001b8b0`
- end: `0x18001c292`
- name: `?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z`
- size: `2530`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, const unsigned __int16 *, const unsigned __int16 *const, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, char *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001b394`
- `0x18001c298`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x180002de4`
- `0x180006548`
- `0x18001a8d4`
- `0x18001aa88`
- `0x18001ace4`
- `0x18001ad64`
- `0x18001ae20`
- `0x18001af58`
- `0x18001b8b0`
- `0x18001c6f4`
- `0x18001c850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001baba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001baba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c163`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bcf2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bcf2`
- `WINHTTP!WinHttpConnect` at `0x18001bb3c`
- `WINHTTP!WinHttpConnect` at `0x18001bb3c`
- `WINHTTP!WinHttpCloseHandle` at `0x18001bcd2`
- `WINHTTP!WinHttpCloseHandle` at `0x18001bcd2`
- `WINHTTP!WinHttpCrackUrl` at `0x18001b9d5`
- `WINHTTP!WinHttpCrackUrl` at `0x18001b9d5`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001bed7`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001bed7`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001bf09`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001bf09`
- `WINHTTP!WinHttpOpenRequest` at `0x18001bd3d`
- `WINHTTP!WinHttpOpenRequest` at `0x18001bd3d`
- `WINHTTP!WinHttpSetOption` at `0x18001bd96`
- `WINHTTP!WinHttpSetOption` at `0x18001bd96`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001bdbe`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001bdeb`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001be18`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001be3f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001bdbe`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001bdeb`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001be18`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001be3f`
- `WINHTTP!WinHttpSendRequest` at `0x18001be82`
- `WINHTTP!WinHttpSendRequest` at `0x18001be82`
- `WINHTTP!WinHttpOpen` at `0x18001baab`
- `WINHTTP!WinHttpOpen` at `0x18001baab`

## string_xrefs

- `0x18001c23c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001bdb3`: `Content-Type: application/json\n`
- `0x18001c1d8`: `CBR(pwszUrlPath != nullptr)`
- `0x18001ba73`: `CHR(StringCchCopyNW( szServerName, (sizeof(*__countof_helper(szServerName)) + 0), urlComponents.lpszHostName, urlComponents.dwHostNameLength))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SendHttpRequest(
        MdmHttpRequest *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *const a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        const unsigned __int16 *a9,
        unsigned int a10,
        const unsigned __int16 *a11,
        char *a12,
        unsigned int a13,
        unsigned int *a14,
        unsigned int *a15,
        unsigned __int8 **a16)
{
  unsigned __int64 v18; // rdx
  WCHAR *v19; // rcx
  int v20; // r13d
  signed int LastError; // eax
  signed int ContentSize; // ebx
  __int64 dwHostNameLength; // rax
  LPSTR lpszHostName; // rcx
  WCHAR *v25; // r8
  WCHAR v26; // r9
  int v27; // r8d
  HINTERNET v28; // rax
  signed int v29; // eax
  HINTERNET v30; // rax
  signed int v31; // eax
  LPCWSTR *v32; // rax
  const WCHAR *v33; // r12
  int v34; // r9d
  const WCHAR *v35; // r15
  unsigned int *v36; // r14
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rax
  signed int v40; // eax
  const WCHAR *v41; // rdx
  const WCHAR *v42; // rdx
  const WCHAR *v43; // rdx
  signed int v44; // eax
  unsigned int *v45; // r15
  unsigned __int8 **v46; // r12
  unsigned __int8 *v47; // rax
  signed int v48; // eax
  signed int v49; // eax
  signed int v50; // eax
  signed int v51; // eax
  signed int v52; // eax
  char dwFlags; // [rsp+20h] [rbp-E0h]
  const char *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  DWORD dwBufferLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 **v58; // [rsp+48h] [rbp-B8h]
  LPCWSTR pwszVerb; // [rsp+50h] [rbp-B0h]
  unsigned int *v60; // [rsp+58h] [rbp-A8h]
  LPCWSTR pwszObjectName; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v62; // [rsp+68h] [rbp-98h]
  unsigned int *v63; // [rsp+70h] [rbp-90h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR Src[2]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD v66[4]; // [rsp+100h] [rbp+0h]
  LPCWSTR lpszHeaders[2]; // [rsp+110h] [rbp+10h] BYREF
  DWORD dwHeadersLength[4]; // [rsp+120h] [rbp+20h]
  LPCWSTR v69[2]; // [rsp+130h] [rbp+30h] BYREF
  DWORD v70[4]; // [rsp+140h] [rbp+40h]
  WCHAR pswzServerName[264]; // [rsp+150h] [rbp+50h] BYREF

  pwszVerb = a2;
  v62 = (unsigned __int64)a12;
  pwszObjectName = a5;
  v63 = a14;
  v60 = a15;
  v58 = a16;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  LODWORD(v19) = 0;
  Buffer = 0;
  dwBufferLength = 0;
  *(_OWORD *)lpszHeaders = 0;
  *(__m128i *)dwHeadersLength = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpszHeaders[0]) = 0;
  *(_OWORD *)v69 = 0;
  *(_OWORD *)v70 = *(_OWORD *)dwHeadersLength;
  LOWORD(v69[0]) = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v66 = *(_OWORD *)dwHeadersLength;
  LOWORD(Src[0]) = 0;
  if ( pwszVerb )
  {
    if ( !a4 )
    {
      ContentSize = -2147467261;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v18,
          -2147467261,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          39,
          (__int64)"CBR(pwszHost != nullptr)");
      goto LABEL_142;
    }
    if ( !a5 )
    {
      ContentSize = -2147467261;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v18,
          -2147467261,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          40,
          (__int64)"CBR(pwszUrlPath != nullptr)");
      goto LABEL_142;
    }
    v20 = 0;
    if ( !a14 )
    {
      ContentSize = -2147467261;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v18,
          -2147467261,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          41,
          (__int64)"CBR(pdwHttpStatus != nullptr)");
      goto LABEL_142;
    }
    *a14 = 0;
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwSchemeLength = -1;
    UrlComponents.dwHostNameLength = -1;
    UrlComponents.dwUrlPathLength = -1;
    if ( !WinHttpCrackUrl(a4, 0, 0x4000u, &UrlComponents) )
    {
      LastError = GetLastError();
      ContentSize = LastError;
      if ( LastError > 0 )
        ContentSize = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_142;
    }
    dwHostNameLength = UrlComponents.dwHostNameLength;
    if ( UrlComponents.dwHostNameLength > 0x7FFFFFFEuLL )
    {
      ContentSize = -2147024809;
      pswzServerName[0] = 0;
      goto LABEL_17;
    }
    lpszHostName = UrlComponents.lpszHostName;
    v18 = 260;
    v25 = pswzServerName;
    do
    {
      if ( !dwHostNameLength )
        break;
      v26 = *(_WORD *)lpszHostName;
      if ( !*(_WORD *)lpszHostName )
        break;
      lpszHostName += 2;
      *v25++ = v26;
      --dwHostNameLength;
      --v18;
    }
    while ( v18 );
    ContentSize = v18 == 0 ? 0x8007007A : 0;
    v19 = v25 - 1;
    if ( v18 )
      v19 = v25;
    *v19 = 0;
    if ( !v18 )
    {
LABEL_17:
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        ppwszAcceptTypes = "CHR(StringCchCopyNW( szServerName, (sizeof(*__countof_helper(szServerName)) + 0), urlComponen"
                           "ts.lpszHostName, urlComponents.dwHostNameLength))";
        dwFlags = 70;
        goto LABEL_19;
      }
      goto LABEL_142;
    }
    if ( !*((_QWORD *)this + 3) )
    {
      v28 = WinHttpOpen(L"Windows Device Management Platform", 4u, 0, 0, 0);
      *((_QWORD *)this + 3) = v28;
      if ( !v28 )
      {
        v29 = GetLastError();
        ContentSize = v29;
        if ( v29 > 0 )
          ContentSize = (unsigned __int16)v29 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CBR(m_hSession != nullptr)";
          dwFlags = 81;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
    }
    ContentSize = MdmHttpRequest::SetDefaultTimeoutOptions(this);
    if ( ContentSize < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        ppwszAcceptTypes = "CHR(SetDefaultTimeoutOptions())";
        dwFlags = 85;
        goto LABEL_19;
      }
      goto LABEL_142;
    }
    if ( !*((_QWORD *)this + 2) )
    {
      v30 = WinHttpConnect(*((HINTERNET *)this + 3), pswzServerName, UrlComponents.nPort, 0);
      *((_QWORD *)this + 2) = v30;
      if ( !v30 )
      {
        v31 = GetLastError();
        ContentSize = v31;
        if ( v31 > 0 )
          ContentSize = (unsigned __int16)v31 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CBR(nullptr != m_hConnection)";
          dwFlags = 95;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
    }
    if ( a8 )
    {
      ContentSize = MdmHttpRequest::AddDelegationTicketHeader(a6, a7, lpszHeaders);
      if ( ContentSize < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CHR(AddDelegationTicketHeader(pwszMainTicket, pwszSecondaryTicket, wstrMainTicketHeader))";
          dwFlags = 113;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
    }
    else
    {
      if ( a6 )
      {
        ContentSize = MdmHttpRequest::AddMainTicketHeader(a6, lpszHeaders);
        if ( ContentSize < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            ppwszAcceptTypes = "CHR(AddMainTicketHeader(pwszMainTicket, wstrMainTicketHeader))";
            dwFlags = 102;
            goto LABEL_19;
          }
          goto LABEL_142;
        }
      }
      if ( a7 )
      {
        ContentSize = MdmHttpRequest::AddSecondaryTicketHeader(a7, v69);
        if ( ContentSize < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            ppwszAcceptTypes = "CHR(AddSecondaryTicketHeader(pwszSecondaryTicket, wstrSecondaryTicketHeader))";
            dwFlags = 108;
            goto LABEL_19;
          }
          goto LABEL_142;
        }
      }
    }
    ContentSize = MdmHttpRequest::AddCorrelationVectorHeader(Src);
    if ( ContentSize < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        ppwszAcceptTypes = "CHR(AddCorrelationVectorHeader(wstrCorrelationVectorHeader))";
        dwFlags = 117;
        goto LABEL_19;
      }
      goto LABEL_142;
    }
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    {
      v32 = Src;
      if ( *(_QWORD *)&v66[2] > 7u )
        v32 = (LPCWSTR *)Src[0];
      v33 = pwszObjectName;
      v34 = (int)a4;
      v35 = pwszVerb;
      McTemplateU0zzzzz_EventWriteTransfer(
        (_DWORD)v19,
        v18,
        (_DWORD)pwszVerb,
        v34,
        (__int64)pwszObjectName,
        (__int64)v32,
        (__int64)a11);
    }
    else
    {
      v33 = pwszObjectName;
      v35 = pwszVerb;
    }
    v36 = (unsigned int *)((char *)this + 48);
    while ( 1 )
    {
      v37 = (void *)*((_QWORD *)this + 4);
      if ( v37 )
      {
        WinHttpCloseHandle(v37);
        *((_QWORD *)this + 4) = 0;
      }
      if ( v20 )
        Sleep(8000 << (v20 - 1));
      v38 = (void *)*((_QWORD *)this + 5);
      if ( v38 )
      {
        operator delete(v38, v18);
        *((_QWORD *)this + 5) = 0;
      }
      *v36 = 0;
      v39 = (void *)*((_QWORD *)this + 4);
      if ( !v39 )
      {
        v39 = WinHttpOpenRequest(*((HINTERNET *)this + 2), v35, v33, 0, 0, 0, 0x800100u);
        *((_QWORD *)this + 4) = v39;
        if ( !v39 )
        {
          v40 = GetLastError();
          ContentSize = v40;
          if ( v40 > 0 )
            ContentSize = (unsigned __int16)v40 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            ppwszAcceptTypes = "CBR(nullptr != m_hRequest)";
            dwFlags = -104;
            goto LABEL_19;
          }
          goto LABEL_142;
        }
      }
      if ( !WinHttpSetOption(v39, 0x2Fu, 0, 0) )
      {
        v52 = GetLastError();
        ContentSize = v52;
        if ( v52 > 0 )
          ContentSize = (unsigned __int16)v52 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CBR(::WinHttpSetOption( m_hRequest, 47, 0, 0))";
          dwFlags = -95;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
      if ( !WinHttpAddRequestHeaders(*((HINTERNET *)this + 4), L"Content-Type: application/json\r\n", 0x20u, 0xA0000000) )
      {
        v51 = GetLastError();
        ContentSize = v51;
        if ( v51 > 0 )
          ContentSize = (unsigned __int16)v51 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CBR(::WinHttpAddRequestHeaders( m_hRequest, pwszContentType, (DWORD)wcslen(pwszContentType)"
                             ", 0x80000000 | 0x20000000))";
          dwFlags = -87;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
      if ( *(_QWORD *)dwHeadersLength )
      {
        v41 = (const WCHAR *)lpszHeaders;
        if ( *(_QWORD *)&dwHeadersLength[2] > 7u )
          v41 = lpszHeaders[0];
        if ( !WinHttpAddRequestHeaders(*((HINTERNET *)this + 4), v41, dwHeadersLength[0], 0xA0000000) )
        {
          v48 = GetLastError();
          ContentSize = v48;
          if ( v48 > 0 )
            ContentSize = (unsigned __int16)v48 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            ppwszAcceptTypes = "CBR(::WinHttpAddRequestHeaders( m_hRequest, wstrMainTicketHeader.c_str(), (DWORD)wstrMain"
                               "TicketHeader.length(), 0x80000000 | 0x20000000))";
            dwFlags = -77;
            goto LABEL_19;
          }
          goto LABEL_142;
        }
      }
      if ( *(_QWORD *)v70 )
      {
        v42 = (const WCHAR *)v69;
        if ( *(_QWORD *)&v70[2] > 7u )
          v42 = v69[0];
        if ( !WinHttpAddRequestHeaders(*((HINTERNET *)this + 4), v42, v70[0], 0xA0000000) )
        {
          v49 = GetLastError();
          ContentSize = v49;
          if ( v49 > 0 )
            ContentSize = (unsigned __int16)v49 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            ppwszAcceptTypes = "CBR(::WinHttpAddRequestHeaders( m_hRequest, wstrSecondaryTicketHeader.c_str(), (DWORD)wst"
                               "rSecondaryTicketHeader.length(), 0x80000000 | 0x20000000))";
            dwFlags = -66;
            goto LABEL_19;
          }
          goto LABEL_142;
        }
      }
      v43 = (const WCHAR *)Src;
      if ( *(_QWORD *)&v66[2] > 7u )
        v43 = Src[0];
      if ( !WinHttpAddRequestHeaders(*((HINTERNET *)this + 4), v43, v66[0], 0xA0000000) )
      {
        v50 = GetLastError();
        ContentSize = v50;
        if ( v50 > 0 )
          ContentSize = (unsigned __int16)v50 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          ppwszAcceptTypes = "CBR(::WinHttpAddRequestHeaders( m_hRequest, wstrCorrelationVectorHeader.c_str(), (DWORD)wst"
                             "rCorrelationVectorHeader.length(), 0x80000000 | 0x20000000))";
          dwFlags = -57;
          goto LABEL_19;
        }
        goto LABEL_142;
      }
      if ( !WinHttpSendRequest(
              *((HINTERNET *)this + 4),
              0,
              0,
              (LPVOID)(v62 & -(__int64)(v62 != 0)),
              v62 != 0 ? a13 : 0,
              v62 != 0 ? a13 : 0,
              0)
        || !WinHttpReceiveResponse(*((HINTERNET *)this + 4), 0) )
      {
        break;
      }
      dwBufferLength = 4;
      if ( !WinHttpQueryHeaders(*((HINTERNET *)this + 4), 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
      {
        ContentSize = -2147467259;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_142;
        ppwszAcceptTypes = "CBR(::WinHttpQueryHeaders( m_hRequest, 19 | 0x20000000, nullptr, (LPVOID)&dwHttpStatus, &cbHt"
                           "tpStatus, nullptr))";
        dwFlags = -14;
        goto LABEL_19;
      }
      v45 = v60;
      if ( !v60 )
        goto LABEL_85;
      ContentSize = MdmHttpRequest::GetContentSize(this, (unsigned int *)this + 12);
      if ( ContentSize < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_142;
        ppwszAcceptTypes = "CHR(GetContentSize(&m_cbDataBufferSize))";
        dwFlags = -8;
        goto LABEL_19;
      }
      v46 = v58;
      if ( !v58 || !*v36 )
        goto LABEL_115;
      if ( *((_QWORD *)this + 5) )
      {
        ContentSize = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_142;
        ppwszAcceptTypes = "CBR(m_pbDataBuffer == nullptr)";
        dwFlags = 1;
        goto LABEL_19;
      }
      v47 = (unsigned __int8 *)operator new[](*v36, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 5) = v47;
      if ( !v47 )
      {
        ContentSize = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_142;
        ppwszAcceptTypes = "CBR(m_pbDataBuffer != nullptr)";
        dwFlags = 3;
        goto LABEL_19;
      }
      ContentSize = MdmHttpRequest::GetHttpData(this, *v36, v47);
LABEL_86:
      if ( ContentSize != -2147012894 )
      {
        if ( ContentSize >= 0 )
        {
LABEL_115:
          *v63 = Buffer;
          if ( v46 )
            *v46 = (unsigned __int8 *)*((_QWORD *)this + 5);
          if ( v45 )
            *v45 = *v36;
          goto LABEL_142;
        }
LABEL_113:
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_142;
        ppwszAcceptTypes = "CHR(hr)";
        dwFlags = 17;
LABEL_19:
        v27 = ContentSize;
LABEL_141:
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v19,
          v18,
          v27,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          dwFlags,
          (__int64)ppwszAcceptTypes);
        goto LABEL_142;
      }
      if ( (unsigned int)++v20 >= 2 )
        goto LABEL_113;
      v33 = pwszObjectName;
      v35 = pwszVerb;
    }
    v44 = GetLastError();
    ContentSize = v44;
    if ( v44 > 0 )
      ContentSize = (unsigned __int16)v44 | 0x80070000;
    v45 = v60;
LABEL_85:
    v46 = v58;
    goto LABEL_86;
  }
  v27 = -2147467261;
  ContentSize = -2147467261;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    ppwszAcceptTypes = "CBR(pwszMethod != nullptr)";
    dwFlags = 38;
    goto LABEL_141;
  }
LABEL_142:
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v69);
  std::wstring::~wstring(lpszHeaders);
  return (unsigned int)ContentSize;
}

```

## disassembly

```asm
0x18001b8b0  mov     [rsp-8+arg_10], rbx
0x18001b8b5  push    rbp
0x18001b8b6  push    rsi
0x18001b8b7  push    rdi
0x18001b8b8  push    r12
0x18001b8ba  push    r13
0x18001b8bc  push    r14
0x18001b8be  push    r15
0x18001b8c0  lea     rbp, [rsp-270h]
0x18001b8c8  sub     rsp, 370h
0x18001b8cf  mov     rax, cs:__security_cookie
0x18001b8d6  xor     rax, rsp
0x18001b8d9  mov     [rbp+2A0h+var_40], rax
0x18001b8e0  mov     r15, r9
0x18001b8e3  mov     [rsp+3A0h+pwszVerb], rdx
0x18001b8e8  mov     rsi, rcx
0x18001b8eb  mov     rax, [rbp+2A0h+arg_58]
0x18001b8f2  mov     [rsp+3A0h+var_338], rax
0x18001b8f7  mov     r13, [rbp+2A0h+arg_20]
0x18001b8fe  mov     [rsp+3A0h+pwszObjectName], r13
0x18001b903  mov     rdi, [rbp+2A0h+arg_28]
0x18001b90a  mov     r14, [rbp+2A0h+arg_30]
0x18001b911  mov     r12, [rbp+2A0h+arg_50]
0x18001b918  mov     rbx, [rbp+2A0h+arg_68]
0x18001b91f  mov     [rsp+3A0h+var_330], rbx
0x18001b924  mov     rax, [rbp+2A0h+arg_70]
0x18001b92b  mov     [rsp+3A0h+var_348], rax
0x18001b930  mov     rcx, [rbp+2A0h+arg_78]
0x18001b937  mov     [rsp+3A0h+var_358], rcx
0x18001b93c  xor     edx, edx; Val
0x18001b93e  lea     r8d, [rdx+68h]; Size
0x18001b942  lea     rcx, [rbp+2A0h+UrlComponents]; void *
0x18001b946  call    memset_0
0x18001b94b  xor     ecx, ecx
0x18001b94d  mov     [rsp+3A0h+Buffer], ecx
0x18001b951  mov     [rsp+3A0h+dwBufferLength], ecx
0x18001b955  xorps   xmm0, xmm0
0x18001b958  movups  xmmword ptr [rbp+2A0h+lpszHeaders], xmm0
0x18001b95c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b964  movdqu  xmmword ptr [rbp+2A0h+dwHeadersLength], xmm1
0x18001b969  mov     word ptr [rbp+2A0h+lpszHeaders], cx
0x18001b96d  movups  xmmword ptr [rbp+2A0h+var_270], xmm0
0x18001b971  movdqu  xmmword ptr [rbp+2A0h+var_260], xmm1
0x18001b976  mov     word ptr [rbp+2A0h+var_270], cx
0x18001b97a  movups  xmmword ptr [rbp+2A0h+Src], xmm0
0x18001b97e  movdqu  xmmword ptr [rbp+2A0h+var_2A0], xmm1
0x18001b983  mov     word ptr [rbp+2A0h+Src], cx
0x18001b987  cmp     [rsp+3A0h+pwszVerb], rcx
0x18001b98c  jz      loc_18001C216
0x18001b992  test    r15, r15
0x18001b995  jz      loc_18001C1EE
0x18001b99b  test    r13, r13
0x18001b99e  jz      loc_18001C1C6
0x18001b9a4  xor     r13d, r13d
0x18001b9a7  test    rbx, rbx
0x18001b9aa  jz      loc_18001C19A
0x18001b9b0  mov     [rbx], r13d
0x18001b9b3  mov     [rbp+2A0h+UrlComponents.dwStructSize], 68h ; 'h'
0x18001b9ba  or      eax, 0FFFFFFFFh
0x18001b9bd  mov     [rbp+2A0h+UrlComponents.dwSchemeLength], eax
0x18001b9c0  mov     [rbp+2A0h+UrlComponents.dwHostNameLength], eax
0x18001b9c3  mov     [rbp+2A0h+UrlComponents.dwUrlPathLength], eax
0x18001b9c6  lea     r9, [rbp+2A0h+UrlComponents]; lpUrlComponents
0x18001b9ca  xor     edx, edx; dwUrlLength
0x18001b9cc  mov     r8d, 4000h; dwFlags
0x18001b9d2  mov     rcx, r15; pwszUrl
0x18001b9d5  call    cs:__imp_WinHttpCrackUrl
0x18001b9db  test    eax, eax
0x18001b9dd  jnz     short loc_18001B9FD
0x18001b9df  call    cs:__imp_GetLastError
0x18001b9e5  mov     ebx, eax
0x18001b9e7  test    eax, eax
0x18001b9e9  jle     loc_18001C249
0x18001b9ef  movzx   ebx, ax
0x18001b9f2  or      ebx, 80070000h
0x18001b9f8  jmp     loc_18001C249
0x18001b9fd  mov     eax, [rbp+2A0h+UrlComponents.dwHostNameLength]
0x18001ba00  cmp     rax, 7FFFFFFEh
0x18001ba06  jbe     short loc_18001BA14
0x18001ba08  mov     ebx, 80070057h
0x18001ba0d  mov     [rbp+2A0h+pswzServerName], r13w
0x18001ba12  jmp     short loc_18001BA66
0x18001ba14  mov     rcx, [rbp+2A0h+UrlComponents.lpszHostName]
0x18001ba18  mov     edx, 104h
0x18001ba1d  lea     r8, [rbp+2A0h+pswzServerName]
0x18001ba21  test    rax, rax
0x18001ba24  jz      short loc_18001BA45
0x18001ba26  movzx   r9d, word ptr [rcx]
0x18001ba2a  test    r9w, r9w
0x18001ba2e  jz      short loc_18001BA45
0x18001ba30  add     rcx, 2
0x18001ba34  mov     [r8], r9w
0x18001ba38  add     r8, 2
0x18001ba3c  dec     rax
0x18001ba3f  sub     rdx, 1
0x18001ba43  jnz     short loc_18001BA21
0x18001ba45  mov     rax, rdx
0x18001ba48  neg     rax
0x18001ba4b  sbb     ebx, ebx
0x18001ba4d  not     ebx
0x18001ba4f  and     ebx, 8007007Ah
0x18001ba55  lea     rcx, [r8-2]
0x18001ba59  test    rdx, rdx
0x18001ba5c  cmovnz  rcx, r8
0x18001ba60  mov     [rcx], r13w
0x18001ba64  jnz     short loc_18001BA8F
0x18001ba66  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ba6d  jz      loc_18001C249
0x18001ba73  lea     rax, aChrStringcchco; "CHR(StringCchCopyNW( szServerName, (siz"...
0x18001ba7a  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001ba7f  mov     [rsp+3A0h+dwFlags], 146h
0x18001ba87  mov     r8d, ebx
0x18001ba8a  jmp     loc_18001C23C
0x18001ba8f  cmp     [rsi+18h], r13
0x18001ba93  jnz     short loc_18001BAF2
0x18001ba95  mov     [rsp+3A0h+dwFlags], r13d; dwFlags
0x18001ba9a  xor     r9d, r9d; pszProxyBypassW
0x18001ba9d  xor     r8d, r8d; pszProxyW
0x18001baa0  lea     edx, [r9+4]; dwAccessType
0x18001baa4  lea     rcx, pszAgentW; "Windows Device Management Platform"
0x18001baab  call    cs:__imp_WinHttpOpen
0x18001bab1  mov     [rsi+18h], rax
0x18001bab5  test    rax, rax
0x18001bab8  jnz     short loc_18001BAF2
0x18001baba  call    cs:__imp_GetLastError
0x18001bac0  mov     ebx, eax
0x18001bac2  test    eax, eax
0x18001bac4  jle     short loc_18001BACF
0x18001bac6  movzx   ebx, ax
0x18001bac9  or      ebx, 80070000h
0x18001bacf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bad6  jz      loc_18001C249
0x18001badc  lea     rax, aCbrMHsessionNu; "CBR(m_hSession != nullptr)"
0x18001bae3  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bae8  mov     [rsp+3A0h+dwFlags], 151h
0x18001baf0  jmp     short loc_18001BA87
0x18001baf2  mov     rcx, rsi; this
0x18001baf5  call    ?SetDefaultTimeoutOptions@MdmHttpRequest@@AEAAJXZ; MdmHttpRequest::SetDefaultTimeoutOptions(void)
0x18001bafa  mov     ebx, eax
0x18001bafc  test    eax, eax
0x18001bafe  jns     short loc_18001BB26
0x18001bb00  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bb07  jz      loc_18001C249
0x18001bb0d  lea     rax, aChrSetdefaultt; "CHR(SetDefaultTimeoutOptions())"
0x18001bb14  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bb19  mov     [rsp+3A0h+dwFlags], 155h
0x18001bb21  jmp     loc_18001BA87
0x18001bb26  cmp     [rsi+10h], r13
0x18001bb2a  jnz     short loc_18001BB86
0x18001bb2c  xor     r9d, r9d; dwReserved
0x18001bb2f  movzx   r8d, [rbp+2A0h+UrlComponents.nPort]; nServerPort
0x18001bb34  lea     rdx, [rbp+2A0h+pswzServerName]; pswzServerName
0x18001bb38  mov     rcx, [rsi+18h]; hSession
0x18001bb3c  call    cs:__imp_WinHttpConnect
0x18001bb42  mov     [rsi+10h], rax
0x18001bb46  test    rax, rax
0x18001bb49  jnz     short loc_18001BB86
0x18001bb4b  call    cs:__imp_GetLastError
0x18001bb51  mov     ebx, eax
0x18001bb53  test    eax, eax
0x18001bb55  jle     short loc_18001BB60
0x18001bb57  movzx   ebx, ax
0x18001bb5a  or      ebx, 80070000h
0x18001bb60  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bb67  jz      loc_18001C249
0x18001bb6d  lea     rax, aCbrNullptrMHco; "CBR(nullptr != m_hConnection)"
0x18001bb74  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bb79  mov     [rsp+3A0h+dwFlags], 15Fh
0x18001bb81  jmp     loc_18001BA87
0x18001bb86  cmp     [rbp+2A0h+arg_38], r13d
0x18001bb8d  jnz     short loc_18001BC09
0x18001bb8f  test    rdi, rdi
0x18001bb92  jz      short loc_18001BBCC
0x18001bb94  lea     rdx, [rbp+2A0h+lpszHeaders]; Src
0x18001bb98  mov     rcx, rdi; void *
0x18001bb9b  call    ?AddMainTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddMainTicketHeader(ushort const *,std::wstring &)
0x18001bba0  mov     ebx, eax
0x18001bba2  test    eax, eax
0x18001bba4  jns     short loc_18001BBCC
0x18001bba6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bbad  jz      loc_18001C249
0x18001bbb3  lea     rax, aChrAddmaintick; "CHR(AddMainTicketHeader(pwszMainTicket,"...
0x18001bbba  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bbbf  mov     [rsp+3A0h+dwFlags], 166h
0x18001bbc7  jmp     loc_18001BA87
0x18001bbcc  test    r14, r14
0x18001bbcf  jz      short loc_18001BC44
0x18001bbd1  lea     rdx, [rbp+2A0h+var_270]; Src
0x18001bbd5  mov     rcx, r14; void *
0x18001bbd8  call    ?AddSecondaryTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddSecondaryTicketHeader(ushort const *,std::wstring &)
0x18001bbdd  mov     ebx, eax
0x18001bbdf  test    eax, eax
0x18001bbe1  jns     short loc_18001BC44
0x18001bbe3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bbea  jz      loc_18001C249
0x18001bbf0  lea     rax, aChrAddsecondar; "CHR(AddSecondaryTicketHeader(pwszSecond"...
0x18001bbf7  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bbfc  mov     [rsp+3A0h+dwFlags], 16Ch
0x18001bc04  jmp     loc_18001BA87
0x18001bc09  lea     r8, [rbp+2A0h+lpszHeaders]
0x18001bc0d  mov     rdx, r14
0x18001bc10  mov     rcx, rdi
0x18001bc13  call    ?AddDelegationTicketHeader@MdmHttpRequest@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddDelegationTicketHeader(ushort const *,ushort const *,std::wstring &)
0x18001bc18  mov     ebx, eax
0x18001bc1a  test    eax, eax
0x18001bc1c  jns     short loc_18001BC44
0x18001bc1e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bc25  jz      loc_18001C249
0x18001bc2b  lea     rax, aChrAdddelegati; "CHR(AddDelegationTicketHeader(pwszMainT"...
0x18001bc32  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bc37  mov     [rsp+3A0h+dwFlags], 171h
0x18001bc3f  jmp     loc_18001BA87
0x18001bc44  lea     rcx, [rbp+2A0h+Src]; Src
0x18001bc48  call    ?AddCorrelationVectorHeader@MdmHttpRequest@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddCorrelationVectorHeader(std::wstring &)
0x18001bc4d  mov     ebx, eax
0x18001bc4f  test    eax, eax
0x18001bc51  jns     short loc_18001BC79
0x18001bc53  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bc5a  jz      loc_18001C249
0x18001bc60  lea     rax, aChrAddcorrelat; "CHR(AddCorrelationVectorHeader(wstrCorr"...
0x18001bc67  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bc6c  mov     [rsp+3A0h+dwFlags], 175h
0x18001bc74  jmp     loc_18001BA87
0x18001bc79  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001bc80  jz      short loc_18001BCB6
0x18001bc82  lea     rax, [rbp+2A0h+Src]
0x18001bc86  cmp     qword ptr [rbp+2A0h+var_2A0+8], 7
0x18001bc8b  cmova   rax, [rbp+2A0h+Src]
0x18001bc90  mov     qword ptr [rsp+3A0h+var_370], r12
0x18001bc95  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bc9a  mov     r12, [rsp+3A0h+pwszObjectName]
0x18001bc9f  mov     qword ptr [rsp+3A0h+dwFlags], r12
0x18001bca4  mov     r9, r15
0x18001bca7  mov     r15, [rsp+3A0h+pwszVerb]
0x18001bcac  mov     r8, r15
0x18001bcaf  call    McTemplateU0zzzzz_EventWriteTransfer
0x18001bcb4  jmp     short loc_18001BCC0
0x18001bcb6  mov     r12, [rsp+3A0h+pwszObjectName]
0x18001bcbb  mov     r15, [rsp+3A0h+pwszVerb]
0x18001bcc0  lea     r14, [rsi+30h]
0x18001bcc4  mov     edi, 80070000h
0x18001bcc9  mov     rcx, [rsi+20h]; hInternet
0x18001bccd  test    rcx, rcx
0x18001bcd0  jz      short loc_18001BCE0
0x18001bcd2  call    cs:__imp_WinHttpCloseHandle
0x18001bcd8  mov     qword ptr [rsi+20h], 0
0x18001bce0  test    r13d, r13d
0x18001bce3  jz      short loc_18001BCF8
0x18001bce5  lea     ecx, [r13-1]
0x18001bce9  mov     eax, 1F40h
0x18001bcee  shl     eax, cl
0x18001bcf0  mov     ecx, eax; dwMilliseconds
0x18001bcf2  call    cs:__imp_Sleep
0x18001bcf8  mov     rcx, [rsi+28h]; void *
0x18001bcfc  test    rcx, rcx
0x18001bcff  jz      short loc_18001BD0E
0x18001bd01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bd06  mov     qword ptr [rsi+28h], 0
0x18001bd0e  mov     dword ptr [r14], 0
0x18001bd15  mov     rax, [rsi+20h]
0x18001bd19  test    rax, rax
0x18001bd1c  jnz     short loc_18001BD86
0x18001bd1e  mov     [rsp+3A0h+var_370], 800100h; dwFlags
0x18001bd26  mov     [rsp+3A0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18001bd2b  mov     qword ptr [rsp+3A0h+dwFlags], rax; pwszReferrer
0x18001bd30  xor     r9d, r9d; pwszVersion
0x18001bd33  mov     r8, r12; pwszObjectName
0x18001bd36  mov     rdx, r15; pwszVerb
0x18001bd39  mov     rcx, [rsi+10h]; hConnect
0x18001bd3d  call    cs:__imp_WinHttpOpenRequest
0x18001bd43  mov     [rsi+20h], rax
0x18001bd47  xor     r12d, r12d
0x18001bd4a  test    rax, rax
0x18001bd4d  jnz     short loc_18001BD89
0x18001bd4f  call    cs:__imp_GetLastError
0x18001bd55  mov     ebx, eax
0x18001bd57  test    eax, eax
0x18001bd59  jle     short loc_18001BD60
0x18001bd5b  movzx   ebx, ax
0x18001bd5e  or      ebx, edi
0x18001bd60  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bd67  jz      loc_18001C249
0x18001bd6d  lea     rax, aCbrNullptrMHre; "CBR(nullptr != m_hRequest)"
0x18001bd74  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001bd79  mov     [rsp+3A0h+dwFlags], 198h
0x18001bd81  jmp     loc_18001BA87
0x18001bd86  xor     r12d, r12d
0x18001bd89  xor     r9d, r9d; dwBufferLength
0x18001bd8c  xor     r8d, r8d; lpBuffer
0x18001bd8f  lea     edx, [r9+2Fh]; dwOption
0x18001bd93  mov     rcx, rax; hInternet
0x18001bd96  call    cs:__imp_WinHttpSetOption
0x18001bd9c  test    eax, eax
0x18001bd9e  jz      loc_18001C163
0x18001bda4  mov     r15d, 0A0000000h
0x18001bdaa  mov     r9d, r15d; dwModifiers
0x18001bdad  mov     r8d, 20h ; ' '; dwHeadersLength
0x18001bdb3  lea     rdx, szHeaders; "Content-Type: application/json\r\n"
0x18001bdba  mov     rcx, [rsi+20h]; hRequest
0x18001bdbe  call    cs:__imp_WinHttpAddRequestHeaders
  ... truncated ...
```
