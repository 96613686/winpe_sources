# CSLSDownloader::GetUrlContent(void *,CSLSRequest const &,CCallerIdentity const *,CSLSResponse &,char const *)

- ea: `0x14003401c`
- end: `0x140034aef`
- name: `?GetUrlContent@CSLSDownloader@@QEAAJPEAXAEBVCSLSRequest@@PEBVCCallerIdentity@@AEAVCSLSResponse@@PEBD@Z`
- size: `2771`
- prototype: `__int64 __fastcall(CSLSDownloader *this, void *, GUID *, const struct CCallerIdentity *, struct CSLSResponse *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400254e8`

## callees

- `0x140003de4`
- `0x140007780`
- `0x140008de4`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14000e4d0`
- `0x140011444`
- `0x1400116a4`
- `0x1400154b4`
- `0x140017934`
- `0x140017bd0`
- `0x140022700`
- `0x1400309d8`
- `0x140030b54`
- `0x140032268`
- `0x1400326d0`
- `0x140032cc0`
- `0x140033f60`
- `0x14003401c`
- `0x140034af8`
- `0x140037020`
- `0x1400375dc`
- `0x140037798`
- `0x140037a14`
- `0x14003d038`
- `0x140045963`
- `0x140045a2c`
- `0x140045dc0`
- `0x14004cc90`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003471d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003475d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003471d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003475d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140034145`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003414f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400347f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140034953`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400349b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140034145`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003414f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400347f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140034953`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400349b3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003419a`
- `OLEAUT32!__imp_SysFreeString` at `0x140034a40`
- `OLEAUT32!__imp_SysFreeString` at `0x140034a96`
- `OLEAUT32!__imp_SysFreeString` at `0x14003419a`
- `OLEAUT32!__imp_SysFreeString` at `0x140034a40`
- `OLEAUT32!__imp_SysFreeString` at `0x140034a96`

## string_xrefs

- `0x14003411f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140034221`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140034118`: `SLSResponseCabOverridePath`
- `0x1400341d5`: `strFilePath.Assign`
- `0x140034519`: `Complete the request URL %ws with [%08X] and http status code[%d] and send SLS events.`
- `0x140034703`: `text/xml`
- `0x14003472c`: `text/xml;`
- `0x14003480e`: `X-Microsoft-SLSClientCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSLSDownloader::GetUrlContent(
        CSLSDownloader *this,
        void *a2,
        GUID *a3,
        const struct CCallerIdentity *a4,
        struct CSLSResponse *a5)
{
  unsigned __int64 v6; // r12
  WCHAR *v7; // r14
  wchar_t *v8; // r15
  wchar_t *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // r8
  int LocalFilePath; // r12d
  wchar_t *v16; // rsi
  int v17; // ecx
  int v18; // eax
  wchar_t *v19; // rdi
  int v20; // eax
  __int64 v21; // rcx
  wchar_t *v22; // rax
  unsigned __int64 v23; // rdx
  wchar_t *v24; // rax
  void *v25; // rsi
  CSLSDownloader *v26; // rcx
  void *v27; // r9
  unsigned __int64 v28; // r8
  const char *v29; // r9
  const wchar_t *v30; // r8
  const WCHAR *v31; // r8
  __int64 v32; // rdx
  int StringHeaderValueWorker; // eax
  int v34; // eax
  int v35; // r12d
  unsigned __int64 v36; // r12
  int v37; // eax
  int v38; // edi
  __int64 v39; // rdi
  _DWORD *v40; // rax
  unsigned __int64 v41; // r12
  int SLSExpireSecsInADay; // edi
  int v43; // edi
  struct CSLSResponse *v44; // r13
  wchar_t *v45; // rdi
  void *v46; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  PCNZWCH lpString2b; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+48h] [rbp-B8h]
  char v52; // [rsp+60h] [rbp-A0h]
  bool v53; // [rsp+61h] [rbp-9Fh]
  char v54; // [rsp+62h] [rbp-9Eh]
  bool v55; // [rsp+63h] [rbp-9Dh] BYREF
  int NetworkLevel; // [rsp+64h] [rbp-9Ch]
  int v57; // [rsp+68h] [rbp-98h]
  unsigned int v58; // [rsp+6Ch] [rbp-94h]
  int v59; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  int v61; // [rsp+80h] [rbp-80h] BYREF
  GUID *rguid; // [rsp+88h] [rbp-78h]
  bool v63; // [rsp+90h] [rbp-70h]
  wchar_t *v64; // [rsp+98h] [rbp-68h] BYREF
  PCNZWCH lpString1; // [rsp+A0h] [rbp-60h] BYREF
  int v66; // [rsp+A8h] [rbp-58h]
  struct _GUID v67; // [rsp+B0h] [rbp-50h] BYREF
  void *lpMem; // [rsp+C0h] [rbp-40h]
  wchar_t *v69; // [rsp+C8h] [rbp-38h]
  wchar_t *v70; // [rsp+D0h] [rbp-30h]
  struct CSLSResponse *v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  struct _FILETIME v74; // [rsp+F0h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t *String[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v77[30]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t v78[2088]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1298h] [rbp+1198h]

  rguid = a3;
  v71 = a5;
  memset(v77, 0, sizeof(v77));
  CDownloadSession::CDownloadSession((CDownloadSession *)v77, a4);
  v6 = 0;
  v54 = 0;
  v57 = 0;
  v61 = 0;
  v59 = 2;
  v7 = 0;
  lpString1 = 0;
  v8 = 0;
  String[0] = 0;
  v58 = 0;
  v73 = 0;
  v74 = 0;
  SystemTimeAsFileTime = 0;
  bstrString = 0;
  v64 = 0;
  v9 = 0;
  v69 = 0;
  v55 = 0;
  v66 = AreTestKeysAllowed();
  LOBYTE(v10) = 0;
  v52 = 0;
  if ( v66 )
  {
    memset(v78, 0, 522);
    if ( (int)RegQueryStringValue(
                v10,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                L"SLSResponseCabOverridePath",
                v78,
                261) >= 0
      && v78[0] )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      GetSystemTimeAsFileTime(&v74);
      v12 = v74.dwLowDateTime + ((unsigned __int64)v74.dwHighDateTime << 32) + 864000000000LL;
      v74.dwLowDateTime += 711573504;
      v74.dwHighDateTime = HIDWORD(v12);
      v54 = 0;
      v59 = 2;
      v57 = 1;
      v58 = 200;
      SysFreeString(0);
      bstrString = 0;
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( v78[v14] );
      LocalFilePath = CSusBSTR::Append((CSusBSTR *)&bstrString, v78, v14);
      if ( LocalFilePath >= 0 )
      {
        v16 = bstrString;
        v17 = v57;
LABEL_99:
        v44 = v71;
        *((_BYTE *)v71 + 31) = v54;
        *((_DWORD *)v44 + 8) = v59;
        *((_BYTE *)v44 + 28) = v17 != 0;
        if ( v17 )
          *((_BYTE *)v44 + 29) = 0;
        *(struct _FILETIME *)v44 = v74;
        *((struct _FILETIME *)v44 + 1) = SystemTimeAsFileTime;
        *((_DWORD *)v44 + 6) = v58;
        if ( v16 != *((wchar_t **)v44 + 2) )
        {
          SysFreeString(*((BSTR *)v44 + 2));
          *((_QWORD *)v44 + 2) = 0;
          if ( v16 )
          {
            do
              ++v13;
            while ( v16[v13] );
          }
          else
          {
            LODWORD(v13) = 0;
          }
          CSusBSTR::Append((struct CSLSResponse *)((char *)v44 + 16), v16, v13);
        }
        v45 = v9;
        v9 = 0;
        v46 = (void *)*((_QWORD *)v44 + 5);
        if ( v46 )
          SusFree(v46);
        *((_QWORD *)v44 + 5) = v45;
        goto LABEL_110;
      }
      LODWORD(lpString2) = LocalFilePath;
      WUTrace(0, 0, 4, 3, lpString2, L"strFilePath.Assign");
      v16 = bstrString;
      goto LABEL_97;
    }
    v18 = RegQueryDwordValueWithDefaultAndRangeCheck(
            v11,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            L"SLSBlockNoneMatchHeader",
            0);
    LOBYTE(v10) = v18 != 0;
    v53 = v18 != 0;
    if ( v18 )
    {
      WUTrace(0, 0, 4, 4, 0, L"SLSBlockNoneMatchHeader override set.");
      LOBYTE(v10) = v53;
    }
  }
  *(_QWORD *)&v67.Data1 = 0;
  v19 = 0;
  v70 = 0;
  v20 = 0;
  if ( !(_BYTE)v10 )
  {
    if ( (int)DuplicateString<wchar_t *,wchar_t *>(*((_QWORD *)a5 + 5), &v64) >= 0 )
    {
      v9 = v64;
      v69 = v64;
      if ( !v64 )
        goto LABEL_32;
      v21 = 0x7FFFFFFF;
      v22 = v64;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v21;
      }
      while ( v21 );
      v23 = (0x7FFFFFFF - v21) & ((unsigned __int128)-(__int128)(unsigned __int64)v21 >> 64);
      if ( v21 )
      {
        v6 = v23 + 17;
        if ( v23 + 17 < v23 )
        {
          v6 = -1;
        }
        else
        {
          v24 = (wchar_t *)SafeSusAllocArray(v6, 2u);
          v19 = v24;
          v70 = v24;
          if ( v24 && (int)StringCchPrintfW(v24, v6, L"%s%s", L"If-None-Match: ", v9) >= 0 )
          {
            LODWORD(v77[28]) = 1;
            v52 = 1;
            v20 = v6;
            goto LABEL_24;
          }
        }
      }
      else
      {
LABEL_32:
        v6 = 0;
      }
    }
    v20 = 0;
  }
LABEL_24:
  v72 = 0;
  v25 = SafeSusAllocArray((unsigned int)(v20 + 1), 2u);
  lpMem = v25;
  v63 = v19 == 0;
  if ( v19 )
    StringCchPrintfW((wchar_t *)v25, v6, L"%ws", v19);
  WUTrace(0, 0, 4, 5, 0, L"SLS request headers: %ws");
  LocalFilePath = CSLSDownloader::GetLocalFilePath(v26, rguid, (struct CSusBSTR *)&bstrString, v27);
  if ( LocalFilePath < 0
    || (v78[0] = 0,
        LocalFilePath = CSLSRequest::GetUrl((CSLSRequest *)rguid, v78, v28, (unsigned __int64 *)&v67.Data1, &v55),
        LocalFilePath < 0) )
  {
    if ( v19 )
      SusFree(v19);
    if ( v25 )
      SusFree(v25);
    v16 = bstrString;
    v13 = -1;
    goto LABEL_97;
  }
  WUTrace(0, 0, 4, 4, 0, L"Making request with URL %ws and send SLS events, cV=%hs.");
  v30 = &OutputString;
  if ( v52 )
    v30 = v9;
  v67 = *rguid;
  sls::telemetry::DiscoveryEvent::SendRequestStartEvent(&v67, *(const wchar_t **)&rguid[2].Data1, v30, v29);
  v51 = (__int64)v25;
  v16 = bstrString;
  LocalFilePath = CDownloadSession::DoFileDownload(
                    (CDownloadSession *)v77,
                    lpString2a,
                    (__int64)bstrString,
                    (unsigned int)v78,
                    (__int64)&v61,
                    1,
                    v51,
                    2);
  if ( !v77[29] )
  {
    LocalFilePath = -2145120257;
    if ( !v63 )
      SusFree(v19);
    if ( lpMem )
      SusFree(lpMem);
    goto LABEL_110;
  }
  NetworkLevel = NetworkUtil::GetNetworkLevel();
  v58 = v77[24];
  WUTrace(0, 0, 4, 4, 0, L"Complete the request URL %ws with [%08X] and http status code[%d] and send SLS events.");
  v31 = &OutputString;
  v32 = *(_QWORD *)&rguid[2].Data1;
  v67 = *rguid;
  if ( LocalFilePath < 0 )
  {
    if ( v52 )
      v31 = v9;
    LODWORD(lpString2b) = LocalFilePath;
    sls::telemetry::DiscoveryEvent::SendRequestFailedEvent(&v67, v32, v31, v58);
  }
  else
  {
    if ( v52 )
      v31 = v9;
    sls::telemetry::DiscoveryEvent::SendRequestSucceededEvent(&v67, v32, v31, v58);
  }
  if ( !v63 )
    SusFree(v19);
  if ( lpMem )
    SusFree(lpMem);
  if ( HIDWORD(v77[27]) )
  {
    WUTrace(0, 0, 4, 3, 0, L"*** Potential Failover Scenario ***");
    v54 = 1;
  }
  if ( LocalFilePath < 0 )
  {
    LODWORD(lpString2b) = LocalFilePath;
    WUTrace(0, 0, 4, 1, lpString2b, L"GetDownloadedOnWeakSSLCert");
    v17 = v61;
    v13 = -1;
    goto LABEL_98;
  }
  v57 = v61;
  if ( !v61 )
    goto LABEL_77;
  if ( v9 )
    SusFree(v9);
  StringHeaderValueWorker = CDownloadSession::GetStringHeaderValueWorker((CDownloadSession *)v77, 0x36u, 0, &v64);
  v9 = v64;
  v69 = v64;
  if ( StringHeaderValueWorker >= 0 )
  {
    WUTrace(0, 0, 4, 5, 0, L"New ETAG value %ws");
    if ( v66 )
      LogETagValue(rguid);
  }
  else
  {
    LODWORD(lpString2b) = StringHeaderValueWorker;
    WUTrace(0, 0, 4, 5, lpString2b, L"Failed to get the ETAG value; ignoring...");
  }
  if ( SLODWORD(v77[27]) < 0 )
    v34 = CDownloadSession::GetStringHeaderValueWorker((CDownloadSession *)v77, 1u, 0, (wchar_t **)&lpString1);
  else
    v34 = DuplicateString<wchar_t *,wchar_t *>(v77[26], &lpString1);
  LocalFilePath = v34;
  v7 = (WCHAR *)lpString1;
  if ( v34 >= 0 )
  {
    v13 = -1;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"text/xml", -1) == 2
      || (unsigned int)WUStringStartsWithI(v7, L"text/xml;") )
    {
      v35 = 1;
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, v7, -1, L"application/octet-stream", -1) != 2
        && !(unsigned int)WUStringStartsWithI(v7, L"application/octet-stream;") )
      {
        LocalFilePath = -2145103867;
        WUTrace(0, 0, 4, 1, 0, L"Unsupported content type in response: %ws");
        goto LABEL_110;
      }
      v35 = 2;
    }
    v59 = v35;
    WUTrace(0, 0, 4, 5, 0, L"Content Type for Response: %ws");
    if ( v35 == 1 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
LABEL_96:
      v58 = v77[24];
      LocalFilePath = 0;
LABEL_97:
      v17 = v57;
LABEL_98:
      if ( LocalFilePath < 0 )
        goto LABEL_110;
      goto LABEL_99;
    }
LABEL_77:
    v36 = 0;
    v37 = CDownloadSession::GetStringHeaderValueWorker(
            (CDownloadSession *)v77,
            0xFFFFu,
            L"X-Microsoft-SLSClientCache",
            String);
    if ( v37 < 0 )
    {
      LODWORD(lpString2b) = v37;
      WUTrace(0, 0, 4, 1, lpString2b, L"GetStringHeaderValue");
    }
    v8 = String[0];
    if ( String[0] )
    {
      *(_DWORD *)o__errno_0() = 0;
      v39 = o__wtoi64_0(v8);
      v40 = (_DWORD *)o__errno_0();
      if ( !*v40 )
      {
        v36 = v39;
LABEL_87:
        if ( v36 > 0xFFFFFFFF )
        {
          LODWORD(v36) = -1;
          LODWORD(lpString2b) = -2147024362;
          WUTrace(0, 0, 4, 1, lpString2b, L"Int64ToDWord");
        }
        goto LABEL_89;
      }
      if ( *v40 == 34 )
      {
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x31,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safemisc.cpp",
                (const char *)0x216,
                (unsigned int)lpString2b);
        v36 = 0;
        if ( v38 >= 0 )
        {
LABEL_89:
          v41 = 60LL * (unsigned int)v36;
          if ( v41 > 0xFFFFFFFF )
          {
            LODWORD(v41) = -1;
            LODWORD(lpString2b) = -2147024362;
            WUTrace(0, 0, 4, 1, lpString2b, L"DWordMult");
          }
          SLSExpireSecsInADay = GetSLSExpireSecsInADay();
          String[0] = 0;
          GetSystemTimeAsFileTime((LPFILETIME)String);
          v74 = (struct _FILETIME)&String[0][5000000 * (int)((double)(int)v41 / 86400.0 * (double)SLSExpireSecsInADay)];
          v43 = HIDWORD(v77[25]);
          if ( v77[25] < 0 )
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            LODWORD(lpString2b) = v43;
            WUTrace(0, 0, 4, 1, lpString2b, L"GetLastModified");
          }
          else
          {
            SystemTimeAsFileTime = *(struct _FILETIME *)((char *)&v77[24] + 4);
          }
          v13 = -1;
          goto LABEL_96;
        }
      }
      else
      {
        v38 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safemisc.cpp",
          (const char *)0x80070057LL,
          (int)lpString2b);
      }
    }
    else
    {
      v38 = -2147024809;
    }
    LODWORD(lpString2b) = v38;
    WUTrace(0, 0, 4, 1, lpString2b, L"Safe_wtoi64");
    goto LABEL_87;
  }
LABEL_110:
  if ( v9 )
    SusFree(v9);
  SysFreeString(v16);
  if ( v8 )
    SusFree(v8);
  if ( v7 )
    SusFree(v7);
  CDownloadSession::~CDownloadSession((CDownloadSession *)v77);
  return (unsigned int)LocalFilePath;
}

```

## disassembly

```asm
0x14003401c  mov     [rsp-8+arg_0], rbx
0x140034021  push    rbp
0x140034022  push    rsi
0x140034023  push    rdi
0x140034024  push    r12
0x140034026  push    r13
0x140034028  push    r14
0x14003402a  push    r15
0x14003402c  lea     rbp, [rsp-1160h]
0x140034034  mov     eax, 1260h
0x140034039  call    _alloca_probe
0x14003403e  sub     rsp, rax
0x140034041  mov     rax, cs:__security_cookie
0x140034048  xor     rax, rsp
0x14003404b  mov     [rbp+1190h+var_40], rax
0x140034052  mov     rbx, r9
0x140034055  mov     [rbp+1190h+rguid], r8
0x140034059  mov     rsi, [rbp+1190h+arg_20]
0x140034060  mov     [rbp+1190h+var_11B8], rsi
0x140034064  xor     edx, edx; Val
0x140034066  mov     r8d, 0F0h; Size
0x14003406c  lea     rcx, [rbp+1190h+var_1180]; void *
0x140034070  call    memset
0x140034075  mov     rdx, rbx; struct CCallerIdentity *
0x140034078  lea     rcx, [rbp+1190h+var_1180]; this
0x14003407c  call    ??0CDownloadSession@@QEAA@PEBVCCallerIdentity@@@Z; CDownloadSession::CDownloadSession(CCallerIdentity const *)
0x140034081  nop
0x140034082  xor     r12d, r12d
0x140034085  mov     [rsp+1290h+var_122E], r12b
0x14003408a  mov     eax, r12d
0x14003408d  mov     [rsp+1290h+var_1228], eax
0x140034091  mov     [rbp+1190h+var_1210], eax
0x140034094  mov     [rsp+1290h+var_1220], 2
0x14003409c  mov     r14d, r12d
0x14003409f  mov     [rbp+1190h+lpString1], r12
0x1400340a3  mov     r15d, r12d
0x1400340a6  mov     [rbp+1190h+String], r12
0x1400340aa  mov     [rsp+1290h+var_1224], r12d
0x1400340af  mov     [rbp+1190h+var_11A8], r12
0x1400340b3  mov     qword ptr [rbp+1190h+var_11A0.dwLowDateTime], r12
0x1400340b7  mov     qword ptr [rbp+1190h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1400340bb  mov     [rsp+1290h+bstrString], r12
0x1400340c0  mov     [rbp+1190h+var_11F8], r12
0x1400340c4  mov     ebx, r12d
0x1400340c7  mov     [rbp+1190h+var_11C8], rbx
0x1400340cb  mov     [rsp+1290h+var_122D], r12b
0x1400340d0  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1400340d5  mov     [rbp+1190h+var_11E8], eax
0x1400340d8  mov     cl, r12b
0x1400340db  mov     [rsp+1290h+var_1230], r12b
0x1400340e0  lea     edi, [r12+4]
0x1400340e5  test    eax, eax
0x1400340e7  jz      loc_14003425E
0x1400340ed  mov     [rbp+1190h+var_1090], r12w
0x1400340f5  xor     edx, edx; Val
0x1400340f7  mov     r8d, 208h; Size
0x1400340fd  lea     rcx, [rbp+1190h+var_108E]; void *
0x140034104  call    memset
0x140034109  mov     dword ptr [rsp+1290h+lpString2], 105h
0x140034111  lea     r9, [rbp+1190h+var_1090]
0x140034118  lea     r8, ?c_szRegSLSResponseCabOverridePath@@3QB_WB; "SLSResponseCabOverridePath"
0x14003411f  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140034126  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x14003412b  test    eax, eax
0x14003412d  js      loc_14003420F
0x140034133  cmp     [rbp+1190h+var_1090], r12w
0x14003413b  jz      loc_14003420F
0x140034141  lea     rcx, [rbp+1190h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140034145  call    cs:__imp_GetSystemTimeAsFileTime
0x14003414b  lea     rcx, [rbp+1190h+var_11A0]; lpSystemTimeAsFileTime
0x14003414f  call    cs:__imp_GetSystemTimeAsFileTime
0x140034155  mov     eax, [rbp+1190h+var_11A0.dwHighDateTime]
0x140034158  shl     rax, 20h
0x14003415c  mov     ecx, [rbp+1190h+var_11A0.dwLowDateTime]
0x14003415f  mov     rdx, 0C92A69C000h
0x140034169  add     rdx, rax
0x14003416c  add     rdx, rcx
0x14003416f  mov     [rbp+1190h+var_11A0.dwLowDateTime], edx
0x140034172  shr     rdx, 20h
0x140034176  mov     [rbp+1190h+var_11A0.dwHighDateTime], edx
0x140034179  mov     [rsp+1290h+var_122E], r12b
0x14003417e  mov     [rsp+1290h+var_1220], 2
0x140034186  lea     r13d, [r12+1]
0x14003418b  mov     [rsp+1290h+var_1228], r13d
0x140034190  mov     [rsp+1290h+var_1224], 0C8h
0x140034198  xor     ecx, ecx; bstrString
0x14003419a  call    cs:__imp_SysFreeString
0x1400341a0  mov     [rsp+1290h+bstrString], r12
0x1400341a5  lea     rax, [rbp+1190h+var_1090]
0x1400341ac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400341b0  mov     r8, rdi
0x1400341b3  inc     r8; unsigned int
0x1400341b6  cmp     [rax+r8*2], r12w
0x1400341bb  jnz     short loc_1400341B3
0x1400341bd  lea     rdx, [rbp+1190h+var_1090]; wchar_t *
0x1400341c4  lea     rcx, [rsp+1290h+bstrString]; this
0x1400341c9  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x1400341ce  mov     r12d, eax
0x1400341d1  test    eax, eax
0x1400341d3  jns     short loc_140034201
0x1400341d5  lea     rax, aStrfilepathAss; "strFilePath.Assign"
0x1400341dc  mov     qword ptr [rsp+1290h+cchCount2], rax
0x1400341e1  mov     dword ptr [rsp+1290h+lpString2], r12d
0x1400341e6  xor     edx, edx
0x1400341e8  xor     ecx, ecx
0x1400341ea  lea     r9d, [rdx+3]
0x1400341ee  lea     r8d, [rdx+4]
0x1400341f2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400341f7  mov     rsi, [rsp+1290h+bstrString]
0x1400341fc  jmp     loc_1400349EA
0x140034201  mov     rsi, [rsp+1290h+bstrString]
0x140034206  mov     ecx, [rsp+1290h+var_1228]
0x14003420a  jmp     loc_1400349F7
0x14003420f  mov     [rsp+1290h+cchCount2], 0FFFFFFFFh
0x140034217  xor     r9d, r9d
0x14003421a  lea     r8, ?c_szRegSLSBlockNoneMatchHeader@@3QB_WB; "SLSBlockNoneMatchHeader"
0x140034221  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140034228  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x14003422d  test    eax, eax
0x14003422f  setnz   cl
0x140034232  mov     [rsp+1290h+var_122F], cl
0x140034236  test    eax, eax
0x140034238  jz      short loc_14003425E
0x14003423a  lea     rax, aSlsblocknonema; "SLSBlockNoneMatchHeader override set."
0x140034241  mov     qword ptr [rsp+1290h+cchCount2], rax
0x140034246  mov     [rsp+1290h+lpString2], r12
0x14003424b  mov     r9d, edi
0x14003424e  mov     r8d, edi
0x140034251  xor     edx, edx
0x140034253  xor     ecx, ecx
0x140034255  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003425a  mov     cl, [rsp+1290h+var_122F]
0x14003425e  mov     qword ptr [rbp+1190h+var_11E0.Data1], r12
0x140034262  mov     rdi, r12
0x140034265  mov     [rbp+1190h+var_11C0], r12
0x140034269  xor     eax, eax
0x14003426b  lea     r13d, [rax+1]
0x14003426f  test    cl, cl
0x140034271  jnz     loc_1400343DF
0x140034277  lea     rdx, [rbp+1190h+var_11F8]
0x14003427b  mov     rcx, [rsi+28h]
0x14003427f  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140034284  xor     esi, esi
0x140034286  test    eax, eax
0x140034288  js      loc_14003432A
0x14003428e  mov     rbx, [rbp+1190h+var_11F8]
0x140034292  mov     [rbp+1190h+var_11C8], rbx
0x140034296  test    rbx, rbx
0x140034299  jz      loc_1400343D7
0x14003429f  mov     r8d, 7FFFFFFFh
0x1400342a5  mov     ecx, r8d
0x1400342a8  mov     rax, rbx
0x1400342ab  cmp     [rax], si
0x1400342ae  jz      short loc_1400342B9
0x1400342b0  add     rax, 2
0x1400342b4  sub     rcx, r13
0x1400342b7  jnz     short loc_1400342AB
0x1400342b9  mov     rax, rcx
0x1400342bc  sub     r8, rcx
0x1400342bf  neg     rax
0x1400342c2  sbb     rdx, rdx
0x1400342c5  and     rdx, r8
0x1400342c8  test    rcx, rcx
0x1400342cb  jz      loc_1400343D7
0x1400342d1  lea     r12, [rdx+11h]
0x1400342d5  cmp     r12, rdx
0x1400342d8  jb      short loc_140034326
0x1400342da  mov     edx, 2; unsigned __int64
0x1400342df  mov     rcx, r12; unsigned __int64
0x1400342e2  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1400342e7  mov     rdi, rax
0x1400342ea  mov     [rbp+1190h+var_11C0], rax
0x1400342ee  test    rax, rax
0x1400342f1  jz      short loc_14003432A
0x1400342f3  mov     [rsp+1290h+lpString2], rbx
0x1400342f8  lea     r9, aIfNoneMatch; "If-None-Match: "
0x1400342ff  lea     r8, aSS_0; "%s%s"
0x140034306  mov     rdx, r12; unsigned __int64
0x140034309  mov     rcx, rax; Buffer
0x14003430c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140034311  test    eax, eax
0x140034313  js      short loc_14003432A
0x140034315  mov     [rbp+1190h+var_10A0], r13d
0x14003431c  mov     [rsp+1290h+var_1230], r13b
0x140034321  mov     eax, r12d
0x140034324  jmp     short loc_14003432C
0x140034326  or      r12, 0FFFFFFFFFFFFFFFFh
0x14003432a  mov     eax, esi
0x14003432c  mov     [rbp+1190h+var_11B0], rsi
0x140034330  lea     ecx, [rax+1]; unsigned __int64
0x140034333  mov     edx, 2; unsigned __int64
0x140034338  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003433d  mov     rsi, rax
0x140034340  mov     [rbp+1190h+lpMem], rax
0x140034344  xor     ecx, ecx
0x140034346  test    rdi, rdi
0x140034349  setz    al
0x14003434c  mov     [rsp+1290h+var_122F], al
0x140034350  mov     [rbp+1190h+var_1200], al
0x140034353  test    rdi, rdi
0x140034356  jz      short loc_14003436F
0x140034358  mov     r9, rdi
0x14003435b  lea     r8, aWs; "%ws"
0x140034362  mov     rdx, r12; unsigned __int64
0x140034365  mov     rcx, rsi; Buffer
0x140034368  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14003436d  xor     ecx, ecx
0x14003436f  mov     [rsp+1290h+var_1260], rsi
0x140034374  lea     rax, aSlsRequestHead; "SLS request headers: %ws"
0x14003437b  mov     qword ptr [rsp+1290h+cchCount2], rax
0x140034380  mov     [rsp+1290h+lpString2], rcx
0x140034385  xor     edx, edx
0x140034387  xor     ecx, ecx
0x140034389  lea     r9d, [rdx+5]
0x14003438d  lea     r8d, [rdx+4]
0x140034391  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140034396  lea     r8, [rsp+1290h+bstrString]; struct CSusBSTR *
0x14003439b  mov     rdx, [rbp+1190h+rguid]; struct _GUID *
0x14003439f  call    ?GetLocalFilePath@CSLSDownloader@@AEAAJAEBU_GUID@@AEAVCSusBSTR@@PEAX@Z; CSLSDownloader::GetLocalFilePath(_GUID const &,CSusBSTR &,void *)
0x1400343a4  mov     r12d, eax
0x1400343a7  xor     ecx, ecx
0x1400343a9  test    eax, eax
0x1400343ab  jns     short loc_1400343E6
0x1400343ad  cmp     [rsp+1290h+var_122F], cl
0x1400343b1  jnz     short loc_1400343BC
0x1400343b3  mov     rcx, rdi; lpMem
0x1400343b6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400343bb  nop
0x1400343bc  test    rsi, rsi
0x1400343bf  jz      short loc_1400343C9
0x1400343c1  mov     rcx, rsi; lpMem
0x1400343c4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400343c9  mov     rsi, [rsp+1290h+bstrString]
0x1400343ce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400343d2  jmp     loc_1400349EA
0x1400343d7  mov     r12, rsi
0x1400343da  jmp     loc_14003432A
0x1400343df  xor     esi, esi
0x1400343e1  jmp     loc_14003432C
0x1400343e6  mov     [rbp+1190h+var_1090], cx
0x1400343ed  lea     rax, [rsp+1290h+var_122D]
0x1400343f2  mov     [rsp+1290h+lpString2], rax; bool *
0x1400343f7  lea     r9, [rbp+1190h+var_11E0]; unsigned __int64 *
0x1400343fb  lea     rdx, [rbp+1190h+var_1090]; wchar_t *
0x140034402  mov     rcx, [rbp+1190h+rguid]; this
0x140034406  call    ?GetUrl@CSLSRequest@@QEBAJPEA_W_KPEA_KPEA_N@Z; CSLSRequest::GetUrl(wchar_t *,unsigned __int64,unsigned __int64 *,bool *)
0x14003440b  mov     r12d, eax
0x14003440e  xor     ecx, ecx
0x140034410  test    eax, eax
0x140034412  js      short loc_1400343AD
0x140034414  mov     [rsp+1290h+var_1258], rcx
0x140034419  lea     rax, [rbp+1190h+var_1090]
0x140034420  mov     [rsp+1290h+var_1260], rax
0x140034425  lea     rax, aMakingRequestW; "Making request with URL %ws and send SL"...
0x14003442c  mov     qword ptr [rsp+1290h+cchCount2], rax
0x140034431  mov     [rsp+1290h+lpString2], rcx
0x140034436  lea     eax, [rcx+4]
0x140034439  mov     r9d, eax
0x14003443c  mov     r8d, eax
0x14003443f  xor     edx, edx
0x140034441  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140034446  lea     r8, OutputString
0x14003444d  xor     r12d, r12d
0x140034450  cmp     [rsp+1290h+var_1230], r12b
0x140034455  cmovnz  r8, rbx; wchar_t *
0x140034459  mov     rax, [rbp+1190h+rguid]
0x14003445d  movups  xmm0, xmmword ptr [rax]
0x140034460  movdqu  xmmword ptr [rbp+1190h+var_11E0.Data1], xmm0
0x140034465  mov     rdx, [rax+20h]; wchar_t *
0x140034469  lea     rcx, [rbp+1190h+var_11E0]; struct _GUID
0x14003446d  call    ?SendRequestStartEvent@DiscoveryEvent@telemetry@sls@@SAXU_GUID@@PEB_W1PEBD@Z; sls::telemetry::DiscoveryEvent::SendRequestStartEvent(_GUID,wchar_t const *,wchar_t const *,char const *)
0x140034472  mov     r9d, r12d
0x140034475  lea     eax, [r12+7]
0x14003447a  cmp     [rsp+1290h+var_122D], r12b
0x14003447f  cmovz   r9d, eax
0x140034483  mov     [rsp+1290h+var_1240], 2
0x14003448b  mov     [rsp+1290h+var_1248], rsi
0x140034490  mov     byte ptr [rsp+1290h+var_1250], r13b
0x140034495  lea     rax, [rbp+1190h+var_1210]
0x140034499  mov     [rsp+1290h+var_1258], rax
0x14003449e  mov     rsi, [rsp+1290h+bstrString]
0x1400344a3  mov     qword ptr [rsp+1290h+cchCount2], rsi
0x1400344a8  lea     rdx, [rbp+1190h+var_1090]
0x1400344af  lea     rcx, [rbp+1190h+var_1180]
0x1400344b3  call    ?DoFileDownload@CDownloadSession@@QEAAJPEB_WKKPEAX0PEAV?$CSafeBuffer@E@@PEAH_N0K@Z; CDownloadSession::DoFileDownload(wchar_t const *,ulong,ulong,void *,wchar_t const *,CSafeBuffer<uchar> *,int *,bool,wchar_t const *,ulong)
0x1400344b8  mov     r12d, eax
0x1400344bb  xor     eax, eax
0x1400344bd  cmp     [rbp+1190h+var_1098], rax
0x1400344c4  jnz     short loc_1400344F1
0x1400344c6  mov     r12d, 80240FFFh
0x1400344cc  cmp     [rbp+1190h+var_1200], al
0x1400344cf  jnz     short loc_1400344DA
0x1400344d1  mov     rcx, rdi; lpMem
0x1400344d4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400344d9  nop
0x1400344da  mov     rcx, [rbp+1190h+lpMem]; lpMem
0x1400344de  test    rcx, rcx
0x1400344e1  jz      loc_140034A85
0x1400344e7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400344ec  jmp     loc_140034A85
  ... truncated ...
```
