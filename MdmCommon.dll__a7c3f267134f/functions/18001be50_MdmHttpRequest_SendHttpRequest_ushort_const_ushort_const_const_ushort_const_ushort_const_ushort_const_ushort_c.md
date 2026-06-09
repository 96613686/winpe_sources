# MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)

- ea: `0x18001be50`
- end: `0x18001c8c7`
- name: `?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z`
- size: `2679`
- prototype: `__int64 __usercall@<rax>(MdmHttpRequest *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *const@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, char *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001b924`
- `0x18001c8d0`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x180002de8`
- `0x1800065c0`
- `0x18001ae24`
- `0x18001afdc`
- `0x18001b244`
- `0x18001b2c4`
- `0x18001b394`
- `0x18001b4d8`
- `0x18001be50`
- `0x18001cd34`
- `0x18001ceb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c791`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c2bc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c2bc`
- `WINHTTP!WinHttpConnect` at `0x18001c0f4`
- `WINHTTP!WinHttpConnect` at `0x18001c0f4`
- `WINHTTP!WinHttpCloseHandle` at `0x18001c296`
- `WINHTTP!WinHttpCloseHandle` at `0x18001c296`
- `WINHTTP!WinHttpCrackUrl` at `0x18001bf75`
- `WINHTTP!WinHttpCrackUrl` at `0x18001bf75`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001c4dd`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001c4dd`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c515`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c515`
- `WINHTTP!WinHttpOpenRequest` at `0x18001c30d`
- `WINHTTP!WinHttpOpenRequest` at `0x18001c30d`
- `WINHTTP!WinHttpSetOption` at `0x18001c372`
- `WINHTTP!WinHttpSetOption` at `0x18001c372`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c3a0`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c3d3`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c406`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c433`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c3a0`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c3d3`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c406`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001c433`
- `WINHTTP!WinHttpSendRequest` at `0x18001c47c`
- `WINHTTP!WinHttpSendRequest` at `0x18001c47c`
- `WINHTTP!WinHttpOpen` at `0x18001c057`
- `WINHTTP!WinHttpOpen` at `0x18001c057`

## string_xrefs

- `0x18001c870`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001c395`: `Content-Type: application/json\n`
- `0x18001c80c`: `CBR(pwszUrlPath != nullptr)`
- `0x18001c01f`: `CHR(StringCchCopyNW( szServerName, (sizeof(*__countof_helper(szServerName)) + 0), urlComponents.lpszHostName, urlComponents.dwHostNameLength))`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
          "CBR(pwszHost != nullptr)");
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
          "CBR(pwszUrlPath != nullptr)");
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
          "CBR(pdwHttpStatus != nullptr)");
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
          ppwszAcceptTypes);
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
0x18001be50  mov     [rsp-8+arg_10], rbx
0x18001be55  push    rbp
0x18001be56  push    rsi
0x18001be57  push    rdi
0x18001be58  push    r12
0x18001be5a  push    r13
0x18001be5c  push    r14
0x18001be5e  push    r15
0x18001be60  lea     rbp, [rsp-270h]
0x18001be68  sub     rsp, 370h
0x18001be6f  mov     rax, cs:__security_cookie
0x18001be76  xor     rax, rsp
0x18001be79  mov     [rbp+2A0h+var_40], rax
0x18001be80  mov     r15, r9
0x18001be83  mov     [rsp+3A0h+pwszVerb], rdx
0x18001be88  mov     rsi, rcx
0x18001be8b  mov     rax, [rbp+2A0h+arg_58]
0x18001be92  mov     [rsp+3A0h+var_338], rax
0x18001be97  mov     r13, [rbp+2A0h+arg_20]
0x18001be9e  mov     [rsp+3A0h+pwszObjectName], r13
0x18001bea3  mov     rdi, [rbp+2A0h+arg_28]
0x18001beaa  mov     r14, [rbp+2A0h+arg_30]
0x18001beb1  mov     r12, [rbp+2A0h+arg_50]
0x18001beb8  mov     rbx, [rbp+2A0h+arg_68]
0x18001bebf  mov     [rsp+3A0h+var_330], rbx
0x18001bec4  mov     rax, [rbp+2A0h+arg_70]
0x18001becb  mov     [rsp+3A0h+var_348], rax
0x18001bed0  mov     rcx, [rbp+2A0h+arg_78]
0x18001bed7  mov     [rsp+3A0h+var_358], rcx
0x18001bedc  xor     edx, edx; Val
0x18001bede  lea     r8d, [rdx+68h]; Size
0x18001bee2  lea     rcx, [rbp+2A0h+UrlComponents]; void *
0x18001bee6  call    memset_0
0x18001beeb  xor     ecx, ecx
0x18001beed  mov     [rsp+3A0h+Buffer], ecx
0x18001bef1  mov     [rsp+3A0h+dwBufferLength], ecx
0x18001bef5  xorps   xmm0, xmm0
0x18001bef8  movups  xmmword ptr [rbp+2A0h+lpszHeaders], xmm0
0x18001befc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bf04  movdqu  xmmword ptr [rbp+2A0h+dwHeadersLength], xmm1
0x18001bf09  mov     word ptr [rbp+2A0h+lpszHeaders], cx
0x18001bf0d  movups  xmmword ptr [rbp+2A0h+var_270], xmm0
0x18001bf11  movdqu  xmmword ptr [rbp+2A0h+var_260], xmm1
0x18001bf16  mov     word ptr [rbp+2A0h+var_270], cx
0x18001bf1a  movups  xmmword ptr [rbp+2A0h+Src], xmm0
0x18001bf1e  movdqu  xmmword ptr [rbp+2A0h+var_2A0], xmm1
0x18001bf23  mov     word ptr [rbp+2A0h+Src], cx
0x18001bf27  cmp     [rsp+3A0h+pwszVerb], rcx
0x18001bf2c  jz      loc_18001C84A
0x18001bf32  test    r15, r15
0x18001bf35  jz      loc_18001C822
0x18001bf3b  test    r13, r13
0x18001bf3e  jz      loc_18001C7FA
0x18001bf44  xor     r13d, r13d
0x18001bf47  test    rbx, rbx
0x18001bf4a  jz      loc_18001C7CE
0x18001bf50  mov     [rbx], r13d
0x18001bf53  mov     [rbp+2A0h+UrlComponents.dwStructSize], 68h ; 'h'
0x18001bf5a  or      eax, 0FFFFFFFFh
0x18001bf5d  mov     [rbp+2A0h+UrlComponents.dwSchemeLength], eax
0x18001bf60  mov     [rbp+2A0h+UrlComponents.dwHostNameLength], eax
0x18001bf63  mov     [rbp+2A0h+UrlComponents.dwUrlPathLength], eax
0x18001bf66  lea     r9, [rbp+2A0h+UrlComponents]; lpUrlComponents
0x18001bf6a  xor     edx, edx; dwUrlLength
0x18001bf6c  mov     r8d, 4000h; dwFlags
0x18001bf72  mov     rcx, r15; pwszUrl
0x18001bf75  call    cs:__imp_WinHttpCrackUrl
0x18001bf7c  nop     dword ptr [rax+rax+00h]
0x18001bf81  test    eax, eax
0x18001bf83  jnz     short loc_18001BFA9
0x18001bf85  call    cs:__imp_GetLastError
0x18001bf8c  nop     dword ptr [rax+rax+00h]
0x18001bf91  mov     ebx, eax
0x18001bf93  test    eax, eax
0x18001bf95  jle     loc_18001C87D
0x18001bf9b  movzx   ebx, ax
0x18001bf9e  or      ebx, 80070000h
0x18001bfa4  jmp     loc_18001C87D
0x18001bfa9  mov     eax, [rbp+2A0h+UrlComponents.dwHostNameLength]
0x18001bfac  cmp     rax, 7FFFFFFEh
0x18001bfb2  jbe     short loc_18001BFC0
0x18001bfb4  mov     ebx, 80070057h
0x18001bfb9  mov     [rbp+2A0h+pswzServerName], r13w
0x18001bfbe  jmp     short loc_18001C012
0x18001bfc0  mov     rcx, [rbp+2A0h+UrlComponents.lpszHostName]
0x18001bfc4  mov     edx, 104h
0x18001bfc9  lea     r8, [rbp+2A0h+pswzServerName]
0x18001bfcd  test    rax, rax
0x18001bfd0  jz      short loc_18001BFF1
0x18001bfd2  movzx   r9d, word ptr [rcx]
0x18001bfd6  test    r9w, r9w
0x18001bfda  jz      short loc_18001BFF1
0x18001bfdc  add     rcx, 2
0x18001bfe0  mov     [r8], r9w
0x18001bfe4  add     r8, 2
0x18001bfe8  dec     rax
0x18001bfeb  sub     rdx, 1
0x18001bfef  jnz     short loc_18001BFCD
0x18001bff1  mov     rax, rdx
0x18001bff4  neg     rax
0x18001bff7  sbb     ebx, ebx
0x18001bff9  not     ebx
0x18001bffb  and     ebx, 8007007Ah
0x18001c001  lea     rcx, [r8-2]
0x18001c005  test    rdx, rdx
0x18001c008  cmovnz  rcx, r8
0x18001c00c  mov     [rcx], r13w
0x18001c010  jnz     short loc_18001C03B
0x18001c012  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c019  jz      loc_18001C87D
0x18001c01f  lea     rax, aChrStringcchco; "CHR(StringCchCopyNW( szServerName, (siz"...
0x18001c026  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c02b  mov     [rsp+3A0h+dwFlags], 146h
0x18001c033  mov     r8d, ebx
0x18001c036  jmp     loc_18001C870
0x18001c03b  cmp     [rsi+18h], r13
0x18001c03f  jnz     short loc_18001C0AA
0x18001c041  mov     [rsp+3A0h+dwFlags], r13d; dwFlags
0x18001c046  xor     r9d, r9d; pszProxyBypassW
0x18001c049  xor     r8d, r8d; pszProxyW
0x18001c04c  lea     edx, [r9+4]; dwAccessType
0x18001c050  lea     rcx, pszAgentW; "Windows Device Management Platform"
0x18001c057  call    cs:__imp_WinHttpOpen
0x18001c05e  nop     dword ptr [rax+rax+00h]
0x18001c063  mov     [rsi+18h], rax
0x18001c067  test    rax, rax
0x18001c06a  jnz     short loc_18001C0AA
0x18001c06c  call    cs:__imp_GetLastError
0x18001c073  nop     dword ptr [rax+rax+00h]
0x18001c078  mov     ebx, eax
0x18001c07a  test    eax, eax
0x18001c07c  jle     short loc_18001C087
0x18001c07e  movzx   ebx, ax
0x18001c081  or      ebx, 80070000h
0x18001c087  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c08e  jz      loc_18001C87D
0x18001c094  lea     rax, aCbrMHsessionNu; "CBR(m_hSession != nullptr)"
0x18001c09b  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c0a0  mov     [rsp+3A0h+dwFlags], 151h
0x18001c0a8  jmp     short loc_18001C033
0x18001c0aa  mov     rcx, rsi; this
0x18001c0ad  call    ?SetDefaultTimeoutOptions@MdmHttpRequest@@AEAAJXZ; MdmHttpRequest::SetDefaultTimeoutOptions(void)
0x18001c0b2  mov     ebx, eax
0x18001c0b4  test    eax, eax
0x18001c0b6  jns     short loc_18001C0DE
0x18001c0b8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c0bf  jz      loc_18001C87D
0x18001c0c5  lea     rax, aChrSetdefaultt; "CHR(SetDefaultTimeoutOptions())"
0x18001c0cc  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c0d1  mov     [rsp+3A0h+dwFlags], 155h
0x18001c0d9  jmp     loc_18001C033
0x18001c0de  cmp     [rsi+10h], r13
0x18001c0e2  jnz     short loc_18001C14A
0x18001c0e4  xor     r9d, r9d; dwReserved
0x18001c0e7  movzx   r8d, [rbp+2A0h+UrlComponents.nPort]; nServerPort
0x18001c0ec  lea     rdx, [rbp+2A0h+pswzServerName]; pswzServerName
0x18001c0f0  mov     rcx, [rsi+18h]; hSession
0x18001c0f4  call    cs:__imp_WinHttpConnect
0x18001c0fb  nop     dword ptr [rax+rax+00h]
0x18001c100  mov     [rsi+10h], rax
0x18001c104  test    rax, rax
0x18001c107  jnz     short loc_18001C14A
0x18001c109  call    cs:__imp_GetLastError
0x18001c110  nop     dword ptr [rax+rax+00h]
0x18001c115  mov     ebx, eax
0x18001c117  test    eax, eax
0x18001c119  jle     short loc_18001C124
0x18001c11b  movzx   ebx, ax
0x18001c11e  or      ebx, 80070000h
0x18001c124  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c12b  jz      loc_18001C87D
0x18001c131  lea     rax, aCbrNullptrMHco; "CBR(nullptr != m_hConnection)"
0x18001c138  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c13d  mov     [rsp+3A0h+dwFlags], 15Fh
0x18001c145  jmp     loc_18001C033
0x18001c14a  cmp     [rbp+2A0h+arg_38], r13d
0x18001c151  jnz     short loc_18001C1CD
0x18001c153  test    rdi, rdi
0x18001c156  jz      short loc_18001C190
0x18001c158  lea     rdx, [rbp+2A0h+lpszHeaders]; Src
0x18001c15c  mov     rcx, rdi; void *
0x18001c15f  call    ?AddMainTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddMainTicketHeader(ushort const *,std::wstring &)
0x18001c164  mov     ebx, eax
0x18001c166  test    eax, eax
0x18001c168  jns     short loc_18001C190
0x18001c16a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c171  jz      loc_18001C87D
0x18001c177  lea     rax, aChrAddmaintick; "CHR(AddMainTicketHeader(pwszMainTicket,"...
0x18001c17e  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c183  mov     [rsp+3A0h+dwFlags], 166h
0x18001c18b  jmp     loc_18001C033
0x18001c190  test    r14, r14
0x18001c193  jz      short loc_18001C208
0x18001c195  lea     rdx, [rbp+2A0h+var_270]; Src
0x18001c199  mov     rcx, r14; void *
0x18001c19c  call    ?AddSecondaryTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddSecondaryTicketHeader(ushort const *,std::wstring &)
0x18001c1a1  mov     ebx, eax
0x18001c1a3  test    eax, eax
0x18001c1a5  jns     short loc_18001C208
0x18001c1a7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c1ae  jz      loc_18001C87D
0x18001c1b4  lea     rax, aChrAddsecondar; "CHR(AddSecondaryTicketHeader(pwszSecond"...
0x18001c1bb  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c1c0  mov     [rsp+3A0h+dwFlags], 16Ch
0x18001c1c8  jmp     loc_18001C033
0x18001c1cd  lea     r8, [rbp+2A0h+lpszHeaders]
0x18001c1d1  mov     rdx, r14
0x18001c1d4  mov     rcx, rdi
0x18001c1d7  call    ?AddDelegationTicketHeader@MdmHttpRequest@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddDelegationTicketHeader(ushort const *,ushort const *,std::wstring &)
0x18001c1dc  mov     ebx, eax
0x18001c1de  test    eax, eax
0x18001c1e0  jns     short loc_18001C208
0x18001c1e2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c1e9  jz      loc_18001C87D
0x18001c1ef  lea     rax, aChrAdddelegati; "CHR(AddDelegationTicketHeader(pwszMainT"...
0x18001c1f6  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c1fb  mov     [rsp+3A0h+dwFlags], 171h
0x18001c203  jmp     loc_18001C033
0x18001c208  lea     rcx, [rbp+2A0h+Src]; Src
0x18001c20c  call    ?AddCorrelationVectorHeader@MdmHttpRequest@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpRequest::AddCorrelationVectorHeader(std::wstring &)
0x18001c211  mov     ebx, eax
0x18001c213  test    eax, eax
0x18001c215  jns     short loc_18001C23D
0x18001c217  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c21e  jz      loc_18001C87D
0x18001c224  lea     rax, aChrAddcorrelat; "CHR(AddCorrelationVectorHeader(wstrCorr"...
0x18001c22b  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c230  mov     [rsp+3A0h+dwFlags], 175h
0x18001c238  jmp     loc_18001C033
0x18001c23d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001c244  jz      short loc_18001C27A
0x18001c246  lea     rax, [rbp+2A0h+Src]
0x18001c24a  cmp     qword ptr [rbp+2A0h+var_2A0+8], 7
0x18001c24f  cmova   rax, [rbp+2A0h+Src]
0x18001c254  mov     qword ptr [rsp+3A0h+var_370], r12
0x18001c259  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c25e  mov     r12, [rsp+3A0h+pwszObjectName]
0x18001c263  mov     qword ptr [rsp+3A0h+dwFlags], r12
0x18001c268  mov     r9, r15
0x18001c26b  mov     r15, [rsp+3A0h+pwszVerb]
0x18001c270  mov     r8, r15
0x18001c273  call    McTemplateU0zzzzz_EventWriteTransfer
0x18001c278  jmp     short loc_18001C284
0x18001c27a  mov     r12, [rsp+3A0h+pwszObjectName]
0x18001c27f  mov     r15, [rsp+3A0h+pwszVerb]
0x18001c284  lea     r14, [rsi+30h]
0x18001c288  mov     edi, 80070000h
0x18001c28d  mov     rcx, [rsi+20h]; hInternet
0x18001c291  test    rcx, rcx
0x18001c294  jz      short loc_18001C2AA
0x18001c296  call    cs:__imp_WinHttpCloseHandle
0x18001c29d  nop     dword ptr [rax+rax+00h]
0x18001c2a2  mov     qword ptr [rsi+20h], 0
0x18001c2aa  test    r13d, r13d
0x18001c2ad  jz      short loc_18001C2C8
0x18001c2af  lea     ecx, [r13-1]
0x18001c2b3  mov     eax, 1F40h
0x18001c2b8  shl     eax, cl
0x18001c2ba  mov     ecx, eax; dwMilliseconds
0x18001c2bc  call    cs:__imp_Sleep
0x18001c2c3  nop     dword ptr [rax+rax+00h]
0x18001c2c8  mov     rcx, [rsi+28h]; void *
0x18001c2cc  test    rcx, rcx
0x18001c2cf  jz      short loc_18001C2DE
0x18001c2d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c2d6  mov     qword ptr [rsi+28h], 0
0x18001c2de  mov     dword ptr [r14], 0
0x18001c2e5  mov     rax, [rsi+20h]
0x18001c2e9  test    rax, rax
0x18001c2ec  jnz     short loc_18001C362
0x18001c2ee  mov     [rsp+3A0h+var_370], 800100h; dwFlags
0x18001c2f6  mov     [rsp+3A0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18001c2fb  mov     qword ptr [rsp+3A0h+dwFlags], rax; pwszReferrer
0x18001c300  xor     r9d, r9d; pwszVersion
0x18001c303  mov     r8, r12; pwszObjectName
0x18001c306  mov     rdx, r15; pwszVerb
0x18001c309  mov     rcx, [rsi+10h]; hConnect
0x18001c30d  call    cs:__imp_WinHttpOpenRequest
0x18001c314  nop     dword ptr [rax+rax+00h]
0x18001c319  mov     [rsi+20h], rax
0x18001c31d  xor     r12d, r12d
0x18001c320  test    rax, rax
0x18001c323  jnz     short loc_18001C365
0x18001c325  call    cs:__imp_GetLastError
0x18001c32c  nop     dword ptr [rax+rax+00h]
0x18001c331  mov     ebx, eax
0x18001c333  test    eax, eax
0x18001c335  jle     short loc_18001C33C
0x18001c337  movzx   ebx, ax
0x18001c33a  or      ebx, edi
0x18001c33c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c343  jz      loc_18001C87D
0x18001c349  lea     rax, aCbrNullptrMHre; "CBR(nullptr != m_hRequest)"
0x18001c350  mov     [rsp+3A0h+ppwszAcceptTypes], rax
0x18001c355  mov     [rsp+3A0h+dwFlags], 198h
0x18001c35d  jmp     loc_18001C033
0x18001c362  xor     r12d, r12d
0x18001c365  xor     r9d, r9d; dwBufferLength
0x18001c368  xor     r8d, r8d; lpBuffer
0x18001c36b  lea     edx, [r9+2Fh]; dwOption
  ... truncated ...
```
