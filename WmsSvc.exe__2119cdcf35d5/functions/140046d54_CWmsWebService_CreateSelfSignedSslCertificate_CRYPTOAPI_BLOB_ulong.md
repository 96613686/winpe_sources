# CWmsWebService::CreateSelfSignedSslCertificate(_CRYPTOAPI_BLOB *,ulong)

- ea: `0x140046d54`
- end: `0x140047f0a`
- name: `?CreateSelfSignedSslCertificate@CWmsWebService@@AEAAJPEAU_CRYPTOAPI_BLOB@@K@Z`
- size: `4534`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this, struct _CRYPTOAPI_BLOB *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140046c2c`
- `0x140047f10`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x140046d54`
- `0x14005a300`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063fd4`
- `0x140064644`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140046e9f`
- `ADVAPI32!RegGetValueW` at `0x140046e9f`
- `ADVAPI32!CryptAcquireContextW` at `0x14004737a`
- `ADVAPI32!CryptAcquireContextW` at `0x14004739e`
- `ADVAPI32!CryptAcquireContextW` at `0x14004737a`
- `ADVAPI32!CryptAcquireContextW` at `0x14004739e`
- `ADVAPI32!CryptDestroyKey` at `0x14004722e`
- `ADVAPI32!CryptDestroyKey` at `0x14004722e`
- `ADVAPI32!CryptReleaseContext` at `0x14004723f`
- `ADVAPI32!CryptReleaseContext` at `0x140047250`
- `ADVAPI32!CryptReleaseContext` at `0x14004723f`
- `ADVAPI32!CryptReleaseContext` at `0x140047250`
- `ADVAPI32!CryptGenKey` at `0x140047450`
- `ADVAPI32!CryptGenKey` at `0x140047450`
- `KERNEL32!FileTimeToSystemTime` at `0x140047792`
- `KERNEL32!FileTimeToSystemTime` at `0x140047c6f`
- `KERNEL32!FileTimeToSystemTime` at `0x140047d15`
- `KERNEL32!FileTimeToSystemTime` at `0x140047792`
- `KERNEL32!FileTimeToSystemTime` at `0x140047c6f`
- `KERNEL32!FileTimeToSystemTime` at `0x140047d15`
- `KERNEL32!GetLastError` at `0x1400473ac`
- `KERNEL32!GetLastError` at `0x14004745e`
- `KERNEL32!GetLastError` at `0x140047524`
- `KERNEL32!GetLastError` at `0x140047663`
- `KERNEL32!GetLastError` at `0x1400477a0`
- `KERNEL32!GetLastError` at `0x140047879`
- `KERNEL32!GetLastError` at `0x140047982`
- `KERNEL32!GetLastError` at `0x140047a74`
- `KERNEL32!GetLastError` at `0x140047b0d`
- `KERNEL32!GetLastError` at `0x140047bc2`
- `KERNEL32!GetLastError` at `0x140047c7d`
- `KERNEL32!GetLastError` at `0x140047d23`
- `KERNEL32!GetLastError` at `0x1400473ac`
- `KERNEL32!GetLastError` at `0x14004745e`
- `KERNEL32!GetLastError` at `0x140047524`
- `KERNEL32!GetLastError` at `0x140047663`
- `KERNEL32!GetLastError` at `0x1400477a0`
- `KERNEL32!GetLastError` at `0x140047879`
- `KERNEL32!GetLastError` at `0x140047982`
- `KERNEL32!GetLastError` at `0x140047a74`
- `KERNEL32!GetLastError` at `0x140047b0d`
- `KERNEL32!GetLastError` at `0x140047bc2`
- `KERNEL32!GetLastError` at `0x140047c7d`
- `KERNEL32!GetLastError` at `0x140047d23`
- `KERNEL32!IsDebuggerPresent` at `0x140046efb`
- `KERNEL32!IsDebuggerPresent` at `0x14004704b`
- `KERNEL32!IsDebuggerPresent` at `0x140047113`
- `KERNEL32!IsDebuggerPresent` at `0x1400471b3`
- `KERNEL32!IsDebuggerPresent` at `0x140047330`
- `KERNEL32!IsDebuggerPresent` at `0x140047403`
- `KERNEL32!IsDebuggerPresent` at `0x1400474b5`
- `KERNEL32!IsDebuggerPresent` at `0x14004757b`
- `KERNEL32!IsDebuggerPresent` at `0x14004760d`
- `KERNEL32!IsDebuggerPresent` at `0x1400476ba`
- `KERNEL32!IsDebuggerPresent` at `0x1400477f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400478d0`
- `KERNEL32!IsDebuggerPresent` at `0x1400479dd`
- `KERNEL32!IsDebuggerPresent` at `0x140047acb`
- `KERNEL32!IsDebuggerPresent` at `0x140047b64`
- `KERNEL32!IsDebuggerPresent` at `0x140047c19`
- `KERNEL32!IsDebuggerPresent` at `0x140047cd4`
- `KERNEL32!IsDebuggerPresent` at `0x140047d7a`
- `KERNEL32!IsDebuggerPresent` at `0x140047ed8`
- `KERNEL32!IsDebuggerPresent` at `0x140046efb`
- `KERNEL32!IsDebuggerPresent` at `0x14004704b`
- `KERNEL32!IsDebuggerPresent` at `0x140047113`
- `KERNEL32!IsDebuggerPresent` at `0x1400471b3`
- `KERNEL32!IsDebuggerPresent` at `0x140047330`
- `KERNEL32!IsDebuggerPresent` at `0x140047403`
- `KERNEL32!IsDebuggerPresent` at `0x1400474b5`
- `KERNEL32!IsDebuggerPresent` at `0x14004757b`
- `KERNEL32!IsDebuggerPresent` at `0x14004760d`
- `KERNEL32!IsDebuggerPresent` at `0x1400476ba`
- `KERNEL32!IsDebuggerPresent` at `0x1400477f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400478d0`
- `KERNEL32!IsDebuggerPresent` at `0x1400479dd`
- `KERNEL32!IsDebuggerPresent` at `0x140047acb`
- `KERNEL32!IsDebuggerPresent` at `0x140047b64`
- `KERNEL32!IsDebuggerPresent` at `0x140047c19`
- `KERNEL32!IsDebuggerPresent` at `0x140047cd4`
- `KERNEL32!IsDebuggerPresent` at `0x140047d7a`
- `KERNEL32!IsDebuggerPresent` at `0x140047ed8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004773e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004773e`
- `CRYPT32!CertStrToNameW` at `0x140047516`
- `CRYPT32!CertStrToNameW` at `0x140047655`
- `CRYPT32!CertStrToNameW` at `0x140047516`
- `CRYPT32!CertStrToNameW` at `0x140047655`
- `CRYPT32!CryptEncodeObjectEx` at `0x14004786b`
- `CRYPT32!CryptEncodeObjectEx` at `0x14004786b`
- `CRYPT32!CertCloseStore` at `0x14004726e`
- `CRYPT32!CertCloseStore` at `0x14004726e`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x140047bb4`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x140047bb4`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140047aff`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140047aff`
- `CRYPT32!CertOpenStore` at `0x140047a62`
- `CRYPT32!CertOpenStore` at `0x140047a62`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x14004796c`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x14004796c`
- `CRYPT32!CertFreeCertificateContext` at `0x14004725e`
- `CRYPT32!CertFreeCertificateContext` at `0x14004725e`
- `OLEAUT32!__imp_SysFreeString` at `0x140047277`
- `OLEAUT32!__imp_SysFreeString` at `0x140047277`

## string_xrefs

- `0x140047a4a`: `MultiPoint Services Certificates`
- `0x140046ee3`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004702e`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400470f0`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047196`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004730d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400473d6`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047488`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004754e`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400475f0`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004768d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400477ca`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400478a3`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400479b2`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047a9e`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047b37`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047bec`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047ca7`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047d4d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140047eb5`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140046ed6`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047022`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x1400470e6`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x14004718a`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047303`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x1400473cf`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047481`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047547`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x1400475e4`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047686`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x1400477c3`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x14004789c`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x1400479a5`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047a97`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047b30`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047be5`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047ca0`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047d46`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140047eab`: `CWmsWebService::CreateSelfSignedSslCertificate`
- `0x140046f6c`: `CWmsWebService::CreateSelfSignedSslCertificate - cCertLifetimeDays = %u\n`
- `0x140047751`: `CWmsWebService::CreateSelfSignedSslCertificate - WARNING, m_fCertTimesInMinutes == TRUE!\n`
- `0x140047e3a`: `CWmsWebService::CreateSelfSignedSslCertificate - Thumbprint = %s, Private Key Container = %s, valid from %u-%02u-%02u %02u:%02u:%02u.%03u to %u-%02u-%02u %02u:%02u:%02u.%03u.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::CreateSelfSignedSslCertificate(
        CWmsWebService *this,
        struct _CRYPTOAPI_BLOB *a2,
        unsigned int a3)
{
  unsigned __int16 *v6; // r13
  const CERT_CONTEXT *v7; // rdi
  LSTATUS ValueW; // eax
  signed int CertificateThumbprint; // ebx
  CERT_CONTEXT *v10; // rsi
  CERT_CONTEXT *v11; // r14
  int LocalHostName; // eax
  unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdi
  WCHAR *v16; // rax
  int v17; // eax
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  const WCHAR *v20; // rdi
  const unsigned __int16 *v21; // r15
  bool v22; // zf
  const unsigned __int16 *v23; // rax
  __int64 v24; // r9
  void *v25; // r15
  __int64 v27; // r8
  int v28; // eax
  signed int LastError; // eax
  signed int v30; // eax
  const WCHAR *v31; // rbx
  signed int v32; // eax
  BYTE *v33; // rdi
  signed int v34; // eax
  struct _FILETIME v35; // rbx
  __int64 v36; // rax
  signed int v37; // eax
  signed int v38; // eax
  signed int v39; // eax
  const unsigned __int16 *v40; // rax
  __int64 v41; // r9
  __int64 v42; // r8
  CERT_CONTEXT *v43; // rax
  signed int v44; // eax
  signed int v45; // eax
  signed int v46; // eax
  signed int v47; // eax
  signed int v48; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-F0h]
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-E8h]
  PVOID pvDataa; // [rsp+28h] [rbp-E8h]
  LPDWORD pcbData; // [rsp+30h] [rbp-E0h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-E0h]
  LPDWORD pcbDatab; // [rsp+30h] [rbp-E0h]
  LPDWORD pcbDatac; // [rsp+30h] [rbp-E0h]
  PCERT_EXTENSIONS pExtensions; // [rsp+38h] [rbp-D8h]
  unsigned __int16 *v57; // [rsp+90h] [rbp-80h]
  void *Block; // [rsp+98h] [rbp-78h] BYREF
  CERT_CONTEXT *v59; // [rsp+A0h] [rbp-70h]
  CERT_CONTEXT *v60; // [rsp+A8h] [rbp-68h]
  DWORD pcbEncoded; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int v62; // [rsp+B4h] [rbp-5Ch] BYREF
  DWORD v63; // [rsp+B8h] [rbp-58h] BYREF
  unsigned __int16 *v64; // [rsp+C0h] [rbp-50h] BYREF
  HCRYPTPROV hProv; // [rsp+C8h] [rbp-48h] BYREF
  DWORD v66; // [rsp+D0h] [rbp-40h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+D4h] [rbp-3Ch] BYREF
  DWORD pdwKeySpec; // [rsp+D8h] [rbp-38h] BYREF
  int v69; // [rsp+DCh] [rbp-34h]
  FILETIME FileTime; // [rsp+E0h] [rbp-30h] BYREF
  LPCWSTR pszX500; // [rsp+E8h] [rbp-28h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F0h] [rbp-20h] BYREF
  __int64 pvEncoded; // [rsp+F8h] [rbp-18h] BYREF
  void *v74; // [rsp+100h] [rbp-10h]
  HCRYPTKEY hKey; // [rsp+108h] [rbp-8h] BYREF
  HCRYPTPROV phCryptProvOrNCryptKey; // [rsp+110h] [rbp+0h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+118h] [rbp+8h] BYREF
  _CRYPT_KEY_PROV_INFO pKeyProvInfo; // [rsp+128h] [rbp+18h] BYREF
  const char *v79; // [rsp+158h] [rbp+48h] BYREF
  __int128 pvStructInfo; // [rsp+160h] [rbp+50h] BYREF
  struct _CERT_EXTENSIONS v81; // [rsp+170h] [rbp+60h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+180h] [rbp+70h] BYREF
  const CHAR *v83; // [rsp+198h] [rbp+88h] BYREF
  int v84; // [rsp+1A0h] [rbp+90h]
  DWORD v85; // [rsp+1A8h] [rbp+98h]
  __int64 v86; // [rsp+1B0h] [rbp+A0h]
  struct _SYSTEMTIME v87; // [rsp+1B8h] [rbp+A8h] BYREF
  struct _SYSTEMTIME v88; // [rsp+1C8h] [rbp+B8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1D8h] [rbp+C8h] BYREF
  unsigned __int16 v90[4]; // [rsp+1E8h] [rbp+D8h] BYREF
  int v91; // [rsp+1F0h] [rbp+E0h]
  unsigned __int16 v92[8]; // [rsp+1F8h] [rbp+E8h] BYREF
  __int128 v93; // [rsp+208h] [rbp+F8h]
  wchar_t v94; // [rsp+218h] [rbp+108h]

  v91 = *(_DWORD *)L"s";
  v94 = aMultipointXS[16];
  *(_QWORD *)v90 = *(_QWORD *)L"CN=%s";
  v79 = "1.3.6.1.5.5.7.3.1";
  v64 = 0;
  pszX500 = 0;
  v6 = 0;
  hProv = 0;
  v7 = 0;
  *(_OWORD *)v92 = *(_OWORD *)L"MultiPoint-%X-%s";
  hKey = 0;
  v93 = *(_OWORD *)L"nt-%X-%s";
  v60 = 0;
  v74 = 0;
  v59 = 0;
  phCryptProvOrNCryptKey = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  pcbEncoded = 0;
  pvEncoded = 0;
  v63 = 0;
  SystemTimeAsFileTime = 0;
  FileTime = 0;
  pdwKeySpec = 0;
  Block = 0;
  pvStructInfo = 0;
  v62 = 365;
  v81 = 0;
  v66 = 4;
  pSubjectIssuerBlob = 0;
  memset(&pKeyProvInfo, 0, sizeof(pKeyProvInfo));
  memset(&pSignatureAlgorithm, 0, sizeof(pSignatureAlgorithm));
  v88 = 0;
  v87 = 0;
  SystemTime = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
             L"SslCertificateLifetimeDays",
             0x10u,
             0,
             &v62,
             &v66);
  CertificateThumbprint = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      CertificateThumbprint = (unsigned __int16)ValueW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x89Du,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2205,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2205,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        pcbData);
    }
    v7 = 0;
    v10 = 0;
    v11 = 0;
    goto LABEL_30;
  }
  DEBUGMSG(L"CWmsWebService::CreateSelfSignedSslCertificate - cCertLifetimeDays = %u\n", v62);
  LocalHostName = GetLocalHostName(&v64);
  v6 = v64;
  CertificateThumbprint = LocalHostName;
  if ( LocalHostName < 0 )
    goto LABEL_18;
  if ( !v64 )
  {
    CertificateThumbprint = -2147024809;
LABEL_160:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8A7u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CHRA",
      L"hr",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2215,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CHRA",
        L"hr",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2215,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CHRA",
        L"hr",
        pcbData);
    }
    goto LABEL_17;
  }
  v13 = v64;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  CertificateThumbprint = v14 == 0 ? 0x80070057 : 0;
  v15 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
  if ( !v14 )
    goto LABEL_160;
  v16 = (WCHAR *)operator new(saturated_mul((unsigned int)(v15 + 6), 2u));
  pszX500 = v16;
  if ( !v16 )
  {
    CertificateThumbprint = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8ABu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CPR",
      L"pszX500",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2219,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CPR",
        L"pszX500",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2219,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CPR",
        L"pszX500",
        pcbData);
    }
LABEL_17:
    v7 = v60;
LABEL_18:
    v10 = (CERT_CONTEXT *)v7;
    v11 = (CERT_CONTEXT *)v7;
LABEL_30:
    v25 = Block;
    goto LABEL_31;
  }
  v17 = StringCchPrintfW(v16, (unsigned int)(v15 + 6), v90, v6);
  CertificateThumbprint = v17;
  if ( v17 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8AEu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CHRA",
      L"hr",
      v17);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2222,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CHRA",
        L"hr",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2222,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CHRA",
        L"hr",
        pcbData);
    }
    goto LABEL_17;
  }
  v18 = (unsigned int)(v15 + 17);
  v19 = (unsigned __int16 *)operator new(saturated_mul(v18, 2u));
  v57 = v19;
  v20 = v19;
  if ( !v19 )
  {
    v21 = L"CPR";
    CertificateThumbprint = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8B2u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CPR",
      L"pszContainer",
      -2147024882);
    v22 = !IsDebuggerPresent();
    v23 = L"pszContainer";
    if ( !v22 )
    {
      v24 = 2226;
LABEL_27:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v24,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CPR",
        v23,
        -2147024882);
LABEL_28:
      v7 = v60;
      v11 = v60;
LABEL_29:
      v10 = (CERT_CONTEXT *)v57;
      goto LABEL_30;
    }
    v27 = 2226;
LABEL_43:
    LODWORD(pcbData) = -2147024882;
    pvData = v23;
LABEL_44:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v27,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      v21,
      pvData,
      pcbData);
    goto LABEL_28;
  }
  v28 = StringCchPrintfW(v19, v18, v92, a3, v6);
  CertificateThumbprint = v28;
  if ( v28 < 0 )
  {
    v21 = L"CHRA";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8B5u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CHRA",
      L"hr",
      v28);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2229,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CHRA",
        L"hr",
        CertificateThumbprint);
      goto LABEL_28;
    }
    LODWORD(pcbData) = CertificateThumbprint;
    v27 = 2229;
    pvData = L"hr";
    goto LABEL_44;
  }
  if ( !CryptAcquireContextW(&hProv, v20, 0, 1u, 0x20u) && !CryptAcquireContextW(&hProv, v20, 0, 1u, 0x28u) )
  {
    LastError = GetLastError();
    CertificateThumbprint = LastError;
    if ( LastError > 0 )
      CertificateThumbprint = (unsigned __int16)LastError | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8BFu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2239,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2239,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbData);
    }
    goto LABEL_28;
  }
  if ( !CryptGenKey(hProv, 2u, 0x8000000u, &hKey) )
  {
    v30 = GetLastError();
    CertificateThumbprint = v30;
    if ( v30 > 0 )
      CertificateThumbprint = (unsigned __int16)v30 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8C4u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2244,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2244,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbData);
    }
    goto LABEL_28;
  }
  v31 = pszX500;
  if ( !CertStrToNameW(1u, pszX500, 3u, 0, 0, &pcbEncoded, 0) )
  {
    v32 = GetLastError();
    CertificateThumbprint = v32;
    if ( v32 > 0 )
      CertificateThumbprint = (unsigned __int16)v32 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8C9u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2249,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbData) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2249,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbData);
    }
    goto LABEL_28;
  }
  v74 = operator new(pcbEncoded);
  v33 = (BYTE *)v74;
  if ( !v74 )
  {
    v21 = L"CPR";
    CertificateThumbprint = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8CCu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CPR",
      L"pbEncoded",
      -2147024882);
    v22 = !IsDebuggerPresent();
    v23 = L"pbEncoded";
    if ( !v22 )
    {
      v24 = 2252;
      goto LABEL_27;
    }
    v27 = 2252;
    goto LABEL_43;
  }
  if ( !CertStrToNameW(1u, v31, 3u, 0, (BYTE *)v74, &pcbEncoded, 0) )
  {
    v34 = GetLastError();
    CertificateThumbprint = v34;
    if ( v34 > 0 )
      CertificateThumbprint = (unsigned __int16)v34 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8CFu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2255,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbDataa) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2255,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDataa);
    }
    goto LABEL_28;
  }
  pSubjectIssuerBlob.cbData = pcbEncoded;
  pSubjectIssuerBlob.pbData = v33;
  pSignatureAlgorithm.pszObjId = "1.2.840.113549.1.1.13";
  *(&pSubjectIssuerBlob.cbData + 1) = 0;
  *(_QWORD *)&pKeyProvInfo.cProvParam = 0;
  *(_QWORD *)&pKeyProvInfo.dwKeySpec = 2;
  pKeyProvInfo.pwszContainerName = v6;
  pKeyProvInfo.pwszProvName = 0;
  pKeyProvInfo.dwProvType = 1;
  pKeyProvInfo.dwFlags = 32;
  pKeyProvInfo.rgProvParam = 0;
  pSignatureAlgorithm.Parameters = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v35 = SystemTimeAsFileTime;
  if ( *((_DWORD *)this + 86) )
  {
    DEBUGMSG(L"CWmsWebService::CreateSelfSignedSslCertificate - WARNING, m_fCertTimesInMinutes == TRUE!\n");
    v36 = 600000000LL * v62;
  }
  else
  {
    v36 = 864000000000LL * v62;
  }
  FileTime = (FILETIME)(*(_QWORD *)&v35 + v36);
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    v37 = GetLastError();
    CertificateThumbprint = v37;
    if ( v37 > 0 )
      CertificateThumbprint = (unsigned __int16)v37 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8F7u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2295,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbDataa) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2295,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDataa);
    }
    goto LABEL_28;
  }
  LODWORD(pvStructInfo) = 1;
  *((_QWORD *)&pvStructInfo + 1) = &v79;
  if ( !CryptEncodeObjectEx(1u, "2.5.29.37", &pvStructInfo, 0x8000u, 0, &pvEncoded, &v63) )
  {
    v38 = GetLastError();
    CertificateThumbprint = v38;
    if ( v38 > 0 )
      CertificateThumbprint = (unsigned __int16)v38 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x8FEu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2302,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        CertificateThumbprint);
    }
    else
    {
      LODWORD(pcbDatab) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2302,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDatab);
    }
    goto LABEL_28;
  }
  v85 = v63;
  v86 = pvEncoded;
  v83 = "2.5.29.37";
  v81.rgExtension = (PCERT_EXTENSION)&v83;
  v84 = 0;
  v81.cExtension = 1;
  v60 = (CERT_CONTEXT *)CertCreateSelfSignCertificate(
                          0,
                          &pSubjectIssuerBlob,
                          0,
                          &pKeyProvInfo,
                          &pSignatureAlgorithm,
                          0,
                          &SystemTime,
                          &v81);
  v7 = v60;
  if ( !v60 )
  {
    v39 = GetLastError();
    CertificateThumbprint = v39;
    if ( v39 > 0 )
      CertificateThumbprint = (unsigned __int16)v39 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x90Au,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"pCertContext != 0",
      CertificateThumbprint);
    v22 = !IsDebuggerPresent();
    v40 = L"pCertContext != 0";
    if ( !v22 )
    {
      v41 = 2314;
LABEL_112:
      LODWORD(pExtensions) = CertificateThumbprint;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v41,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        v40,
        pExtensions);
LABEL_113:
      v7 = v60;
      v11 = v59;
      goto LABEL_29;
    }
    v42 = 2314;
    goto LABEL_115;
  }
  v43 = (CERT_CONTEXT *)CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"MultiPoint Services Certificates");
  v59 = v43;
  v11 = v43;
  if ( !v43 )
  {
    v44 = GetLastError();
    CertificateThumbprint = v44;
    if ( v44 > 0 )
      CertificateThumbprint = (unsigned __int16)v44 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x90Eu,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"hStore != 0",
      CertificateThumbprint);
    v22 = !IsDebuggerPresent();
    v40 = L"hStore != 0";
    if ( !v22 )
    {
      v41 = 2318;
      goto LABEL_112;
    }
    v42 = 2318;
LABEL_115:
    LODWORD(pcbDatac) = CertificateThumbprint;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v42,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      v40,
      pcbDatac);
    goto LABEL_113;
  }
  if ( !CertAddCertificateContextToStore(v43, v60, 3u, 0) )
  {
    v45 = GetLastError();
    CertificateThumbprint = v45;
    if ( v45 > 0 )
      CertificateThumbprint = (unsigned __int16)v45 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x912u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      LODWORD(pExtensions) = CertificateThumbprint;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2322,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pExtensions);
    }
    else
    {
      LODWORD(pcbDatac) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2322,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDatac);
    }
    goto LABEL_113;
  }
  if ( !CryptAcquireCertificatePrivateKey(v60, 0, 0, &phCryptProvOrNCryptKey, &pdwKeySpec, &pfCallerFreeProvOrNCryptKey) )
  {
    v46 = GetLastError();
    CertificateThumbprint = v46;
    if ( v46 > 0 )
      CertificateThumbprint = (unsigned __int16)v46 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x916u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      LODWORD(pExtensions) = CertificateThumbprint;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2326,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pExtensions);
    }
    else
    {
      LODWORD(pcbDatac) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2326,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDatac);
    }
    goto LABEL_113;
  }
  CertificateThumbprint = GetCertificateThumbprint(v60, &a2->cbData);
  if ( CertificateThumbprint < 0 )
    goto LABEL_29;
  if ( !FileTimeToSystemTime(&v60->pCertInfo->NotBefore, &v88) )
  {
    v47 = GetLastError();
    CertificateThumbprint = v47;
    if ( v47 > 0 )
      CertificateThumbprint = (unsigned __int16)v47 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x91Du,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      LODWORD(pExtensions) = CertificateThumbprint;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2333,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pExtensions);
    }
    else
    {
      LODWORD(pcbDatac) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2333,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDatac);
    }
    goto LABEL_113;
  }
  if ( !FileTimeToSystemTime(&v60->pCertInfo->NotAfter, &v87) )
  {
    v48 = GetLastError();
    CertificateThumbprint = v48;
    if ( v48 > 0 )
      CertificateThumbprint = (unsigned __int16)v48 | 0x80070000;
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x920u,
      L"CWmsWebService::CreateSelfSignedSslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateThumbprint);
    if ( IsDebuggerPresent() )
    {
      LODWORD(pExtensions) = CertificateThumbprint;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2336,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pExtensions);
    }
    else
    {
      LODWORD(pcbDatac) = CertificateThumbprint;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2336,
        L"CWmsWebService::CreateSelfSignedSslCertificate",
        L"CBRAEx",
        L"fSuccess",
        pcbDatac);
    }
    goto LABEL_113;
  }
  v69 = ConvertThumbprintBlobToString(a2, (unsigned __int16 **)&Block);
  CertificateThumbprint = v69;
  if ( v69 < 0 )
    goto LABEL_29;
  v10 = (CERT_CONTEXT *)v57;
  LODWORD(pExtensions) = v88.wMinute;
  LODWORD(pcbDatac) = v88.wHour;
  v25 = Block;
  LODWORD(pvDataa) = v88.wDay;
  LODWORD(pdwType) = v88.wMonth;
  DEBUGMSG(
    L"CWmsWebService::CreateSelfSignedSslCertificate - Thumbprint = %s, Private Key Container = %s, valid from %u-%02u-%02"
     "u %02u:%02u:%02u.%03u to %u-%02u-%02u %02u:%02u:%02u.%03u.\n",
    Block,
    v57,
    v88.wYear,
    pdwType,
    pvDataa,
    pcbDatac,
    pExtensions,
    v88.wSecond,
    v88.wMilliseconds,
    v87.wYear,
    v87.wMonth,
    v87.wDay,
    v87.wHour,
    v87.wMinute,
    v87.wSecond,
    v87.wMilliseconds);
  CertificateThumbprint = v69;
  v7 = v60;
  v6 = v64;
  v11 = v59;
LABEL_31:
  operator delete(v25);
  operator delete(v74);
  operator delete((void *)pszX500);
  operator delete(v10);
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  if ( phCryptProvOrNCryptKey )
    CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( v11 )
    CertCloseStore(v11, 0);
  SysFreeString(v6);
  return (unsigned int)CertificateThumbprint;
}

```

## disassembly

```asm
0x140046d54  mov     [rsp-8+arg_0], rbx
0x140046d59  push    rbp
0x140046d5a  push    rsi
0x140046d5b  push    rdi
0x140046d5c  push    r12
0x140046d5e  push    r13
0x140046d60  push    r14
0x140046d62  push    r15
0x140046d64  lea     rbp, [rsp-120h]
0x140046d6c  sub     rsp, 230h
0x140046d73  mov     rax, cs:__security_cookie
0x140046d7a  xor     rax, rsp
0x140046d7d  mov     [rbp+150h+var_40], rax
0x140046d84  mov     eax, dword ptr cs:aCnS+8; "s"
0x140046d8a  mov     r15, rcx
0x140046d8d  movsd   xmm0, qword ptr cs:aCnS; "CN=%s"
0x140046d95  xor     ecx, ecx
0x140046d97  movups  xmm1, xmmword ptr cs:aMultipointXS+10h; "nt-%X-%s"
0x140046d9e  mov     [rbp+150h+var_70], eax
0x140046da4  mov     r14d, r8d
0x140046da7  movzx   eax, word ptr cs:aMultipointXS+20h; ""
0x140046dae  lea     r8, aSslcertificate_2; "SslCertificateLifetimeDays"
0x140046db5  mov     [rbp+150h+var_48], ax
0x140046dbc  lea     r9d, [rcx+10h]; dwFlags
0x140046dc0  movsd   qword ptr [rbp+150h+var_78], xmm0
0x140046dc8  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x140046dcf  movups  xmm0, xmmword ptr cs:aMultipointXS; "MultiPoint-%X-%s"
0x140046dd6  mov     [rbp+150h+var_108], rax
0x140046dda  mov     rsi, rdx
0x140046ddd  xor     eax, eax
0x140046ddf  mov     [rbp+150h+var_1A0], rcx
0x140046de3  mov     [rbp+150h+pSignatureAlgorithm.Parameters.pbData], rax
0x140046dea  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140046df1  lea     rax, [rbp+150h+var_190]
0x140046df5  mov     [rbp+150h+pszX500], rcx
0x140046df9  mov     [rsp+260h+pcbData], rax; pcbData
0x140046dfe  mov     r13d, ecx
0x140046e01  lea     rax, [rbp+150h+var_1AC]
0x140046e05  mov     [rbp+150h+hProv], rcx
0x140046e09  mov     [rsp+260h+pvData], rax; pvData
0x140046e0e  mov     edi, ecx
0x140046e10  movups  xmmword ptr [rbp+150h+var_68], xmm0
0x140046e17  mov     [rsp+260h+pdwType], rcx; pdwType
0x140046e1c  xorps   xmm0, xmm0
0x140046e1f  mov     [rbp+150h+hKey], rcx
0x140046e23  movups  [rbp+150h+var_58], xmm1
0x140046e2a  mov     [rbp+150h+var_1B8], rcx
0x140046e2e  xorps   xmm1, xmm1
0x140046e31  mov     [rbp+150h+var_160], rcx
0x140046e35  mov     [rbp+150h+var_1C0], rcx
0x140046e39  mov     [rbp+150h+phCryptProvOrNCryptKey], rcx
0x140046e3d  mov     [rbp+150h+pfCallerFreeProvOrNCryptKey], ecx
0x140046e40  mov     [rbp+150h+pcbEncoded], ecx
0x140046e43  mov     [rbp+150h+pvEncoded], rcx
0x140046e47  mov     [rbp+150h+var_1A8], ecx
0x140046e4a  mov     qword ptr [rbp+150h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x140046e4e  mov     qword ptr [rbp+150h+FileTime.dwLowDateTime], rcx
0x140046e52  mov     [rbp+150h+pdwKeySpec], ecx
0x140046e55  mov     [rbp+150h+Block], rcx
0x140046e59  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140046e60  movups  [rbp+150h+pvStructInfo], xmm0
0x140046e64  mov     [rbp+150h+var_1AC], 16Dh
0x140046e6b  movups  xmmword ptr [rbp+150h+var_F0.cExtension], xmm1
0x140046e6f  mov     [rbp+150h+var_190], 4
0x140046e76  movups  xmmword ptr [rbp+150h+pSubjectIssuerBlob.cbData], xmm0
0x140046e7a  movups  xmmword ptr [rbp+150h+pKeyProvInfo.pwszContainerName], xmm1
0x140046e7e  movups  xmmword ptr [rbp+150h+pKeyProvInfo.dwProvType], xmm1
0x140046e82  movups  xmmword ptr [rbp+150h+pKeyProvInfo.rgProvParam], xmm1
0x140046e86  movups  xmmword ptr [rbp+150h+pSignatureAlgorithm.pszObjId], xmm0
0x140046e8a  movups  xmmword ptr [rbp+150h+var_98.wYear], xmm0
0x140046e91  movups  xmmword ptr [rbp+150h+var_A8.wYear], xmm1
0x140046e98  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x140046e9f  call    cs:__imp_RegGetValueW
0x140046ea5  mov     ebx, eax
0x140046ea7  test    eax, 0FFFFFFFDh
0x140046eac  jz      loc_140046F69
0x140046eb2  test    eax, eax
0x140046eb4  jle     short loc_140046EBF
0x140046eb6  movzx   ebx, ax
0x140046eb9  or      ebx, 80070000h
0x140046ebf  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140046ec6  mov     dword ptr [rsp+260h+pvData], ebx; int
0x140046eca  lea     r14, aCbraex; "CBRAEx"
0x140046ed1  mov     [rsp+260h+pdwType], rax; unsigned __int16 *
0x140046ed6  lea     rsi, aCwmswebservice_104; "CWmsWebService::CreateSelfSignedSslCert"...
0x140046edd  mov     r12d, 89Dh
0x140046ee3  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140046eea  mov     r9, r14; unsigned __int16 *
0x140046eed  mov     r8, rsi; unsigned __int16 *
0x140046ef0  mov     edx, r12d; unsigned int
0x140046ef3  mov     rcx, rdi; unsigned __int16 *
0x140046ef6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140046efb  call    cs:__imp_IsDebuggerPresent
0x140046f01  test    eax, eax
0x140046f03  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140046f0a  jz      short loc_140046F44
0x140046f0c  mov     dword ptr [rsp+260h+pExtensions], ebx
0x140046f10  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140046f17  mov     [rsp+260h+pcbData], rax
0x140046f1c  mov     r9d, r12d
0x140046f1f  mov     [rsp+260h+pvData], r14
0x140046f24  mov     r8, rdi
0x140046f27  mov     ecx, 2; unsigned __int8
0x140046f2c  mov     [rsp+260h+pdwType], rsi
0x140046f31  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140046f36  mov     rdi, r13
0x140046f39  mov     rsi, r13
0x140046f3c  mov     r14, r13
0x140046f3f  jmp     loc_1400471FF
0x140046f44  mov     dword ptr [rsp+260h+pcbData], ebx
0x140046f48  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140046f4f  mov     [rsp+260h+pvData], rax
0x140046f54  mov     r9, rsi
0x140046f57  mov     r8d, r12d
0x140046f5a  mov     [rsp+260h+pdwType], r14
0x140046f5f  mov     rdx, rdi
0x140046f62  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140046f67  jmp     short loc_140046F36
0x140046f69  mov     edx, [rbp+150h+var_1AC]
0x140046f6c  lea     rcx, aCwmswebservice_54; "CWmsWebService::CreateSelfSignedSslCert"...
0x140046f73  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140046f78  lea     rcx, [rbp+150h+var_1A0]; unsigned __int16 **
0x140046f7c  call    ?GetLocalHostName@@YAJPEAPEAG@Z; GetLocalHostName(ushort * *)
0x140046f81  mov     r13, [rbp+150h+var_1A0]
0x140046f85  xor     r8d, r8d
0x140046f88  mov     ebx, eax
0x140046f8a  test    eax, eax
0x140046f8c  js      loc_14004708C
0x140046f92  lea     r12d, [r8+2]
0x140046f96  test    r13, r13
0x140046f99  jz      loc_140047E9B
0x140046f9f  mov     edx, 7FFFFFFFh
0x140046fa4  mov     rax, r13
0x140046fa7  mov     ecx, edx
0x140046fa9  cmp     [rax], r8w
0x140046fad  jz      short loc_140046FB8
0x140046faf  add     rax, r12
0x140046fb2  sub     rcx, 1
0x140046fb6  jnz     short loc_140046FA9
0x140046fb8  mov     rax, rcx
0x140046fbb  neg     rax
0x140046fbe  mov     rax, rcx
0x140046fc1  sbb     ebx, ebx
0x140046fc3  sub     rdx, rcx
0x140046fc6  not     ebx
0x140046fc8  and     ebx, 80070057h
0x140046fce  neg     rax
0x140046fd1  sbb     rdi, rdi
0x140046fd4  and     rdi, rdx
0x140046fd7  test    rcx, rcx
0x140046fda  jz      loc_140047EA0
0x140046fe0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140046fe7  lea     ebx, [rdi+6]
0x140046fea  mov     rax, r12
0x140046fed  mul     rbx
0x140046ff0  cmovb   rax, rcx
0x140046ff4  mov     rcx, rax; Size
0x140046ff7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140046ffc  mov     [rbp+150h+pszX500], rax
0x140047000  test    rax, rax
0x140047003  jnz     loc_1400470C0
0x140047009  mov     r14d, 8007000Eh
0x14004700f  lea     rax, aPszx500; "pszX500"
0x140047016  lea     r15, aCpr; "CPR"
0x14004701d  mov     dword ptr [rsp+260h+pvData], r14d; int
0x140047022  lea     rsi, aCwmswebservice_104; "CWmsWebService::CreateSelfSignedSslCert"...
0x140047029  mov     [rsp+260h+pdwType], rax; unsigned __int16 *
0x14004702e  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140047035  mov     r9, r15; unsigned __int16 *
0x140047038  mov     r8, rsi; unsigned __int16 *
0x14004703b  mov     rcx, rdi; unsigned __int16 *
0x14004703e  mov     edx, 8ABh; unsigned int
0x140047043  mov     ebx, r14d
0x140047046  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004704b  call    cs:__imp_IsDebuggerPresent
0x140047051  test    eax, eax
0x140047053  lea     rax, aPszx500; "pszX500"
0x14004705a  jz      short loc_140047097
0x14004705c  mov     dword ptr [rsp+260h+pExtensions], r14d
0x140047061  mov     r9d, 8ABh
0x140047067  mov     [rsp+260h+pcbData], rax
0x14004706c  mov     [rsp+260h+pvData], r15
0x140047071  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140047078  mov     r8, rdi
0x14004707b  mov     [rsp+260h+pdwType], rsi
0x140047080  mov     ecx, r12d; unsigned __int8
0x140047083  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140047088  mov     rdi, [rbp+150h+var_1B8]
0x14004708c  mov     rsi, rdi
0x14004708f  mov     r14, rdi
0x140047092  jmp     loc_1400471FF
0x140047097  mov     dword ptr [rsp+260h+pcbData], r14d
0x14004709c  mov     r8d, 8ABh
0x1400470a2  mov     [rsp+260h+pvData], rax
0x1400470a7  mov     r9, rsi
0x1400470aa  mov     [rsp+260h+pdwType], r15
0x1400470af  mov     rdx, rdi
0x1400470b2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400470b9  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400470be  jmp     short loc_140047088
0x1400470c0  mov     r9, r13
0x1400470c3  lea     r8, [rbp+150h+var_78]; unsigned __int16 *
0x1400470ca  mov     rdx, rbx; unsigned __int64
0x1400470cd  mov     rcx, rax; unsigned __int16 *
0x1400470d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400470d5  mov     ebx, eax
0x1400470d7  test    eax, eax
0x1400470d9  jns     short loc_140047145
0x1400470db  mov     dword ptr [rsp+260h+pvData], eax; int
0x1400470df  lea     r15, aChra; "CHRA"
0x1400470e6  lea     rsi, aCwmswebservice_104; "CWmsWebService::CreateSelfSignedSslCert"...
0x1400470ed  mov     r9, r15; unsigned __int16 *
0x1400470f0  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400470f7  mov     r8, rsi; unsigned __int16 *
0x1400470fa  lea     r14, aHr; "hr"
0x140047101  mov     rcx, rdi; unsigned __int16 *
0x140047104  mov     edx, 8AEh; unsigned int
0x140047109  mov     [rsp+260h+pdwType], r14; unsigned __int16 *
0x14004710e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140047113  call    cs:__imp_IsDebuggerPresent
0x140047119  test    eax, eax
0x14004711b  jz      short loc_140047131
0x14004711d  mov     dword ptr [rsp+260h+pExtensions], ebx
0x140047121  mov     r9d, 8AEh
0x140047127  mov     [rsp+260h+pcbData], r14
0x14004712c  jmp     loc_14004706C
0x140047131  mov     dword ptr [rsp+260h+pcbData], ebx
0x140047135  mov     r8d, 8AEh
0x14004713b  mov     [rsp+260h+pvData], r14
0x140047140  jmp     loc_1400470A7
0x140047145  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004714c  lea     ebx, [rdi+11h]
0x14004714f  mov     rax, r12
0x140047152  mul     rbx
0x140047155  cmovb   rax, rcx
0x140047159  mov     rcx, rax; Size
0x14004715c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140047161  mov     [rbp+150h+var_1D0], rax
0x140047165  mov     rdi, rax
0x140047168  test    rax, rax
0x14004716b  jnz     loc_1400472D5
0x140047171  mov     r14d, 8007000Eh
0x140047177  lea     rax, aPszcontainer; "pszContainer"
0x14004717e  lea     r15, aCpr; "CPR"
0x140047185  mov     dword ptr [rsp+260h+pvData], r14d; int
0x14004718a  lea     rsi, aCwmswebservice_104; "CWmsWebService::CreateSelfSignedSslCert"...
0x140047191  mov     [rsp+260h+pdwType], rax; unsigned __int16 *
0x140047196  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004719d  mov     r9, r15; unsigned __int16 *
0x1400471a0  mov     r8, rsi; unsigned __int16 *
0x1400471a3  mov     rcx, rdi; unsigned __int16 *
0x1400471a6  mov     edx, 8B2h; unsigned int
0x1400471ab  mov     ebx, r14d
0x1400471ae  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400471b3  call    cs:__imp_IsDebuggerPresent
0x1400471b9  test    eax, eax
0x1400471bb  lea     rax, aPszcontainer; "pszContainer"
0x1400471c2  jz      loc_1400472A9
0x1400471c8  mov     r9d, 8B2h
0x1400471ce  mov     dword ptr [rsp+260h+pExtensions], r14d
0x1400471d3  mov     [rsp+260h+pcbData], rax
0x1400471d8  mov     [rsp+260h+pvData], r15
0x1400471dd  mov     r8, rdi
0x1400471e0  mov     [rsp+260h+pdwType], rsi
0x1400471e5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400471ec  mov     ecx, r12d; unsigned __int8
0x1400471ef  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400471f4  mov     rdi, [rbp+150h+var_1B8]
0x1400471f8  mov     r14, rdi
0x1400471fb  mov     rsi, [rbp+150h+var_1D0]
0x1400471ff  mov     r15, [rbp+150h+Block]
0x140047203  mov     rcx, r15; Block
0x140047206  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004720b  mov     rcx, [rbp+150h+var_160]; Block
0x14004720f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140047214  mov     rcx, [rbp+150h+pszX500]; Block
0x140047218  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004721d  mov     rcx, rsi; Block
0x140047220  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140047225  mov     rcx, [rbp+150h+hKey]; hKey
0x140047229  test    rcx, rcx
0x14004722c  jz      short loc_140047234
0x14004722e  call    cs:__imp_CryptDestroyKey
0x140047234  mov     rcx, [rbp+150h+hProv]; hProv
0x140047238  test    rcx, rcx
0x14004723b  jz      short loc_140047245
0x14004723d  xor     edx, edx; dwFlags
0x14004723f  call    cs:__imp_CryptReleaseContext
0x140047245  mov     rcx, [rbp+150h+phCryptProvOrNCryptKey]; hProv
0x140047249  test    rcx, rcx
0x14004724c  jz      short loc_140047256
0x14004724e  xor     edx, edx; dwFlags
0x140047250  call    cs:__imp_CryptReleaseContext
0x140047256  test    rdi, rdi
0x140047259  jz      short loc_140047264
0x14004725b  mov     rcx, rdi; pCertContext
0x14004725e  call    cs:__imp_CertFreeCertificateContext
0x140047264  test    r14, r14
0x140047267  jz      short loc_140047274
0x140047269  xor     edx, edx; dwFlags
  ... truncated ...
```
