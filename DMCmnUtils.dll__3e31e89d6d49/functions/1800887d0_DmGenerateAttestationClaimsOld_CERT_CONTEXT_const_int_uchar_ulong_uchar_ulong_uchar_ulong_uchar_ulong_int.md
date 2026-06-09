# DmGenerateAttestationClaimsOld(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)

- ea: `0x1800887d0`
- end: `0x18008907d`
- name: `?DmGenerateAttestationClaimsOld@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z`
- size: `2221`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, int@<edx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x18005b914`
- `0x18005bd30`
- `0x18005cb4c`
- `0x1800605a8`
- `0x1800609dc`
- `0x180061a64`
- `0x180062704`
- `0x180062728`
- `0x180069ef0`
- `0x1800887d0`
- `0x18008b4d0`
- `0x1800940b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800889f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088c3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088d35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088e7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800889f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088c3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088d35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088e7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800889de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088c26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800889de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088c26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800888ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008892a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800888ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008892a`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800888d8`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800888d8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088ee0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088fe7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088ee0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088fe7`
- `ncrypt!NCryptCreateClaim` at `0x180088beb`
- `ncrypt!NCryptCreateClaim` at `0x180088c92`
- `ncrypt!NCryptCreateClaim` at `0x180088beb`
- `ncrypt!NCryptCreateClaim` at `0x180088c92`
- `ncrypt!NCryptExportKey` at `0x180088998`
- `ncrypt!NCryptExportKey` at `0x180088a62`
- `ncrypt!NCryptExportKey` at `0x180088e21`
- `ncrypt!NCryptExportKey` at `0x180088f23`
- `ncrypt!NCryptExportKey` at `0x180088998`
- `ncrypt!NCryptExportKey` at `0x180088a62`
- `ncrypt!NCryptExportKey` at `0x180088e21`
- `ncrypt!NCryptExportKey` at `0x180088f23`
- `ncrypt!NCryptFreeObject` at `0x180088aaf`
- `ncrypt!NCryptFreeObject` at `0x180088b58`
- `ncrypt!NCryptFreeObject` at `0x180088ed0`
- `ncrypt!NCryptFreeObject` at `0x180088fd7`
- `ncrypt!NCryptFreeObject` at `0x180088aaf`
- `ncrypt!NCryptFreeObject` at `0x180088b58`
- `ncrypt!NCryptFreeObject` at `0x180088ed0`
- `ncrypt!NCryptFreeObject` at `0x180088fd7`
- `ncrypt!NCryptOpenStorageProvider` at `0x180088ad6`
- `ncrypt!NCryptOpenStorageProvider` at `0x180088ad6`
- `ncrypt!NCryptGetProperty` at `0x180088d0a`
- `ncrypt!NCryptGetProperty` at `0x180088d9e`
- `ncrypt!NCryptGetProperty` at `0x180088d0a`
- `ncrypt!NCryptGetProperty` at `0x180088d9e`
- `ncrypt!NCryptOpenKey` at `0x180088b88`
- `ncrypt!NCryptOpenKey` at `0x180088b88`

## string_xrefs

- `0x180088890`: `DmGenerateAttestationClaims: DmGetActiveUserSid`
- `0x180088b02`: `DmGenerateAttestationClaims: NCryptOpenStorageProvider`
- `0x180088bb4`: `DmGenerateAttestationClaims: NCryptOpenKey(aik)`
- `0x180088cbe`: `DmGenerateAttestationClaims: NCryptCreateClaim`
- `0x180088c17`: `DmGenerateAttestationClaims: NCryptCreateClaim(size)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DmGenerateAttestationClaimsOld(
        PCCERT_CONTEXT pCert,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        unsigned int *a10,
        int a11)
{
  unsigned __int8 *v13; // r12
  int ActiveUserSid; // eax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  signed int LastError; // eax
  __int64 v18; // rcx
  signed int v19; // eax
  unsigned int *v20; // r13
  SECURITY_STATUS Claim; // eax
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  bool v24; // zf
  unsigned int v25; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v27; // rax
  __int64 v28; // rdx
  bool v29; // zf
  NCRYPT_HANDLE v30; // rbx
  NCRYPT_HANDLE v31; // rbx
  unsigned int v32; // ebx
  HANDLE v33; // rax
  LPVOID v34; // rax
  unsigned int *v35; // r14
  unsigned __int8 **v36; // r15
  DWORD v37; // ebx
  HANDLE v38; // rax
  LPVOID v39; // rax
  SECURITY_STATUS Property; // eax
  __int64 v41; // rcx
  unsigned int *v42; // rdi
  unsigned __int8 **v43; // rsi
  SECURITY_STATUS v44; // eax
  __int64 v45; // rcx
  const wchar_t *v46; // r8
  DWORD v47; // ebx
  HANDLE v48; // rax
  LPVOID v49; // rax
  int pdwKeySpec; // [rsp+28h] [rbp-A9h]
  int pdwKeySpeca; // [rsp+28h] [rbp-A9h]
  int pdwKeySpecb; // [rsp+28h] [rbp-A9h]
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+48h] [rbp-89h] BYREF
  DWORD v55; // [rsp+50h] [rbp-81h] BYREF
  SIZE_T dwBytes; // [rsp+54h] [rbp-7Dh] BYREF
  DWORD pcbResult; // [rsp+5Ch] [rbp-75h] BYREF
  DWORD cbOutput; // [rsp+60h] [rbp-71h] BYREF
  NCRYPT_HANDLE phKey; // [rsp+68h] [rbp-69h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp-61h] BYREF
  unsigned __int8 *v61; // [rsp+78h] [rbp-59h] BYREF
  unsigned __int16 *v62; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int8 *v63; // [rsp+88h] [rbp-49h] BYREF
  PBYTE v64; // [rsp+90h] [rbp-41h] BYREF
  PBYTE v65; // [rsp+98h] [rbp-39h] BYREF
  PBYTE pbOutput; // [rsp+A0h] [rbp-31h] BYREF
  PBYTE v67; // [rsp+A8h] [rbp-29h]
  PBYTE v68; // [rsp+B0h] [rbp-21h]
  _BYTE v69[16]; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v70; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v71[7]; // [rsp+D0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+3Fh]
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+120h] [rbp+4Fh] BYREF
  unsigned __int8 **v74; // [rsp+128h] [rbp+57h]
  unsigned int *v75; // [rsp+130h] [rbp+5Fh]

  v75 = a4;
  v74 = a3;
  hObject = 0;
  phCryptProvOrNCryptKey = 0;
  v55 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  phKey = 0;
  v71[0] = 0;
  v70 = 0;
  v13 = 0;
  pbOutput = 0;
  v68 = 0;
  v65 = 0;
  v67 = 0;
  v64 = 0;
  v63 = 0;
  cbOutput = 0;
  pcbResult = 0;
  dwBytes = 0;
  v62 = 0;
  v69[0] = 0;
  v69[2] = 0;
  if ( !a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v62,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v62);
    v16 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      if ( a11 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v15,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateAttestationClaims: DmGetActiveUserSid",
          (unsigned int)ActiveUserSid);
      goto LABEL_104;
    }
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)v69, v62);
  }
  if ( !CryptAcquireCertificatePrivateKey(
          pCert,
          0x40040u,
          0,
          &phCryptProvOrNCryptKey,
          &v55,
          &pfCallerFreeProvOrNCryptKey) )
  {
    if ( a11 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      McTemplateU0zd_EventWriteTransfer(
        v18,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateAttestationClaims: CryptAcquireCertificatePrivateKey",
        (unsigned int)LastError);
    }
    v19 = GetLastError();
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    v16 = v19;
    goto LABEL_104;
  }
  if ( !a2 )
    AutoImpersonate::RevertToSelf((AutoImpersonate *)v69);
  v20 = a6;
  if ( !a5 || !a6 )
    goto LABEL_33;
  Claim = NCryptExportKey(phCryptProvOrNCryptKey, 0, L"RSAPUBLICBLOB", 0, 0, 0, (DWORD *)&dwBytes + 1, 0);
  v16 = Claim;
  if ( Claim < 0 )
  {
    if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_25;
    v23 = L"DmGenerateAttestationClaims: NCryptExportKey(size)";
LABEL_24:
    McTemplateU0zd_EventWriteTransfer(v22, EnterpriseDiagnosticsTPMFunctionFailure, v23, (unsigned int)Claim);
LABEL_25:
    v24 = !pfCallerFreeProvOrNCryptKey;
    goto LABEL_100;
  }
  v25 = HIDWORD(dwBytes);
  ProcessHeap = GetProcessHeap();
  v27 = HeapAlloc(ProcessHeap, 8u, v25);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, v27);
  v13 = pbOutput;
  if ( pbOutput )
  {
    Claim = NCryptExportKey(
              phCryptProvOrNCryptKey,
              0,
              L"RSAPUBLICBLOB",
              0,
              pbOutput,
              HIDWORD(dwBytes),
              (DWORD *)&dwBytes + 1,
              0);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: NCryptExportKey";
      goto LABEL_24;
    }
LABEL_33:
    v30 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
      NCryptFreeObject(v30);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
    }
    hObject = 0;
    Claim = NCryptOpenStorageProvider(&hObject, L"Microsoft Platform Crypto Provider", 0);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: NCryptOpenStorageProvider";
      goto LABEL_24;
    }
    Claim = DmSetWindowsAIKPlatformStorageLocation(hObject);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: SetWindowsAIKStorageLocation";
      goto LABEL_24;
    }
    v31 = phKey;
    if ( phKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v61);
      NCryptFreeObject(v31);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v61);
    }
    phKey = 0;
    Claim = NCryptOpenKey(hObject, &phKey, L"Windows AIK", 0, 0);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: NCryptOpenKey(aik)";
      goto LABEL_24;
    }
    pdwKeySpec = 0;
    Claim = NCryptCreateClaim(phCryptProvOrNCryptKey, phKey, 2);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: NCryptCreateClaim(size)";
      goto LABEL_24;
    }
    v32 = dwBytes;
    v33 = GetProcessHeap();
    v34 = HeapAlloc(v33, 8u, v32);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v63, v34);
    v61 = v63;
    if ( !v63 )
    {
      v28 = 1002;
      goto LABEL_28;
    }
    Claim = NCryptCreateClaim(phCryptProvOrNCryptKey, phKey, 2);
    v16 = Claim;
    if ( Claim < 0 )
    {
      if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_25;
      v23 = L"DmGenerateAttestationClaims: NCryptCreateClaim";
      goto LABEL_24;
    }
    v35 = a10;
    v36 = a9;
    v16 = 0;
    if ( a9 && a10 && NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &cbOutput, 0) >= 0 )
    {
      v37 = cbOutput;
      v38 = GetProcessHeap();
      v39 = HeapAlloc(v38, 8u, v37);
      wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v65, v39);
      v68 = v65;
      if ( !v65 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x404,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
          (const char *)0x8007000ELL,
          pdwKeySpeca);
        v29 = !pfCallerFreeProvOrNCryptKey;
        goto LABEL_80;
      }
      Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", v65, cbOutput, &cbOutput, 0);
      v16 = Property;
      if ( Property < 0 )
      {
        if ( a11 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(
            v41,
            EnterpriseDiagnosticsTPMFunctionFailure,
            L"DmGenerateAttestationClaims: NCryptGetProperty(hAIK Cert)",
            (unsigned int)Property);
        v24 = !pfCallerFreeProvOrNCryptKey;
        goto LABEL_100;
      }
      v16 = 0;
    }
    v42 = a8;
    v43 = a7;
    if ( a7 && a8 )
    {
      v44 = NCryptExportKey(phKey, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
      v16 = v44;
      if ( v44 < 0 )
      {
        if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
          goto LABEL_77;
        v46 = L"DmGenerateAttestationClaims: NCryptExportKey(hAIK size)";
LABEL_76:
        McTemplateU0zd_EventWriteTransfer(v45, EnterpriseDiagnosticsTPMFunctionFailure, v46, (unsigned int)v44);
LABEL_77:
        v24 = !pfCallerFreeProvOrNCryptKey;
LABEL_100:
        if ( !v24 )
        {
          if ( v55 == -1 )
            NCryptFreeObject(phCryptProvOrNCryptKey);
          else
            CryptReleaseContext(phCryptProvOrNCryptKey, 0);
        }
        goto LABEL_104;
      }
      v47 = pcbResult;
      v48 = GetProcessHeap();
      v49 = HeapAlloc(v48, 8u, v47);
      wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v64, v49);
      v67 = v64;
      if ( !v64 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42C,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
          (const char *)0x8007000ELL,
          pdwKeySpecb);
        v29 = !pfCallerFreeProvOrNCryptKey;
        goto LABEL_80;
      }
      v44 = NCryptExportKey(phKey, 0, L"RSAPUBLICBLOB", 0, v64, pcbResult, &pcbResult, 0);
      v16 = v44;
      if ( v44 < 0 )
      {
        if ( !a11 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
          goto LABEL_77;
        v46 = L"DmGenerateAttestationClaims: NCryptExportKey(hAIK)";
        goto LABEL_76;
      }
      v16 = 0;
    }
    v63 = 0;
    *v74 = v61;
    *v75 = dwBytes;
    if ( a5 && v20 )
    {
      pbOutput = 0;
      *a5 = v13;
      *v20 = HIDWORD(dwBytes);
    }
    if ( v43 && v42 )
    {
      v64 = 0;
      *v43 = v67;
      *v42 = pcbResult;
    }
    if ( v36 && v35 )
    {
      v65 = 0;
      *v36 = v68;
      *v35 = cbOutput;
    }
    v24 = !pfCallerFreeProvOrNCryptKey;
    goto LABEL_100;
  }
  v28 = 936;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v28,
    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
    (const char *)0x8007000ELL,
    pdwKeySpec);
  v29 = !pfCallerFreeProvOrNCryptKey;
LABEL_80:
  if ( !v29 )
  {
    if ( v55 == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  }
  v16 = -2147024882;
LABEL_104:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v69);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v63, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v64, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v65, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v71);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return v16;
}

```

## disassembly

```asm
0x1800887d0  mov     rax, rsp
0x1800887d3  mov     [rax+8], rbx
0x1800887d7  mov     [rax+20h], r9
0x1800887db  mov     [rax+18h], r8
0x1800887df  push    rbp
0x1800887e0  push    rsi
0x1800887e1  push    rdi
0x1800887e2  push    r12
0x1800887e4  push    r13
0x1800887e6  push    r14
0x1800887e8  push    r15
0x1800887ea  lea     rbp, [rax-3Fh]
0x1800887ee  sub     rsp, 0D0h
0x1800887f5  mov     edi, edx
0x1800887f7  mov     rsi, rcx
0x1800887fa  xor     r14d, r14d
0x1800887fd  mov     [rbp+37h+hObject], r14
0x180088801  mov     [rsp+100h+phCryptProvOrNCryptKey], r14
0x180088806  mov     [rsp+100h+var_B8], r14d
0x18008880b  mov     [rbp+37h+arg_8], r14d
0x18008880f  mov     [rbp+37h+phKey], r14
0x180088813  mov     [rbp+37h+var_38], r14
0x180088817  mov     [rbp+37h+var_40], r14
0x18008881b  mov     r12d, r14d
0x18008881e  mov     [rbp+37h+pbOutput], r14
0x180088822  mov     eax, r14d
0x180088825  mov     [rbp+37h+var_58], rax
0x180088829  mov     [rbp+37h+var_70], rax
0x18008882d  mov     [rbp+37h+var_60], rax
0x180088831  mov     [rbp+37h+var_78], rax
0x180088835  mov     [rbp+37h+var_80], r14
0x180088839  mov     dword ptr [rbp+37h+dwBytes+4], r14d
0x18008883d  mov     [rbp+37h+cbOutput], r14d
0x180088841  mov     [rbp+37h+var_AC], r14d
0x180088845  mov     dword ptr [rbp+37h+dwBytes], r14d
0x180088849  mov     [rbp+37h+var_88], r14
0x18008884d  mov     [rbp+37h+var_50], r14b
0x180088851  mov     [rbp+37h+var_4E], r14b
0x180088855  test    edx, edx
0x180088857  jnz     short loc_1800888B5
0x180088859  xor     edx, edx
0x18008885b  lea     rcx, [rbp+37h+var_88]
0x18008885f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180088864  lea     rcx, [rbp+37h+var_88]; unsigned __int16 **
0x180088868  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18008886d  mov     ebx, eax
0x18008886f  test    eax, eax
0x180088871  jns     short loc_1800888A8
0x180088873  cmp     [rbp+37h+arg_50], r14d
0x18008887a  jz      loc_180088FF4
0x180088880  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088887  jz      loc_180088FF4
0x18008888d  mov     r9d, eax
0x180088890  lea     r8, aDmgenerateatte_14; "DmGenerateAttestationClaims: DmGetActiv"...
0x180088897  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18008889e  call    McTemplateU0zd_EventWriteTransfer
0x1800888a3  jmp     loc_180088FF4
0x1800888a8  mov     rdx, [rbp+37h+var_88]; unsigned __int16 *
0x1800888ac  lea     rcx, [rbp+37h+var_50]; this
0x1800888b0  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800888b5  lea     rax, [rbp+37h+arg_8]
0x1800888b9  mov     [rsp+100h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x1800888be  lea     rax, [rsp+100h+var_B8]
0x1800888c3  mov     [rsp+100h+pdwKeySpec], rax; pdwKeySpec
0x1800888c8  lea     r9, [rsp+100h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800888cd  xor     r8d, r8d; pvParameters
0x1800888d0  mov     edx, 40040h; dwFlags
0x1800888d5  mov     rcx, rsi; pCert
0x1800888d8  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800888df  nop     dword ptr [rax+rax+00h]
0x1800888e4  test    eax, eax
0x1800888e6  jnz     short loc_180088946
0x1800888e8  mov     ebx, 80070000h
0x1800888ed  cmp     [rbp+37h+arg_50], r14d
0x1800888f4  jz      short loc_18008892A
0x1800888f6  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800888fd  jz      short loc_18008892A
0x1800888ff  call    cs:__imp_GetLastError
0x180088906  nop     dword ptr [rax+rax+00h]
0x18008890b  test    eax, eax
0x18008890d  jle     short loc_180088914
0x18008890f  movzx   eax, ax
0x180088912  or      eax, ebx
0x180088914  mov     r9d, eax
0x180088917  lea     r8, aDmgenerateatte_5; "DmGenerateAttestationClaims: CryptAcqui"...
0x18008891e  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180088925  call    McTemplateU0zd_EventWriteTransfer
0x18008892a  call    cs:__imp_GetLastError
0x180088931  nop     dword ptr [rax+rax+00h]
0x180088936  test    eax, eax
0x180088938  jle     short loc_18008893F
0x18008893a  movzx   eax, ax
0x18008893d  or      eax, ebx
0x18008893f  mov     ebx, eax
0x180088941  jmp     loc_180088FF4
0x180088946  test    edi, edi
0x180088948  jnz     short loc_180088953
0x18008894a  lea     rcx, [rbp+37h+var_50]; this
0x18008894e  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x180088953  mov     esi, 8
0x180088958  mov     r13, [rbp+37h+arg_28]
0x18008895c  cmp     [rbp+37h+arg_20], r14
0x180088960  jz      loc_180088A9A
0x180088966  test    r13, r13
0x180088969  jz      loc_180088A9A
0x18008896f  mov     [rsp+100h+dwFlags], r14d; dwFlags
0x180088974  lea     rax, [rbp+37h+dwBytes+4]
0x180088978  mov     [rsp+100h+pcbResult], rax; pcbResult
0x18008897d  mov     dword ptr [rsp+100h+pfCallerFreeProvOrNCryptKey], r14d; cbOutput
0x180088982  mov     [rsp+100h+pdwKeySpec], r14; int
0x180088987  xor     r9d, r9d; pParameterList
0x18008898a  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180088991  xor     edx, edx; hExportKey
0x180088993  mov     rcx, [rsp+100h+phCryptProvOrNCryptKey]; hKey
0x180088998  call    cs:__imp_NCryptExportKey
0x18008899f  nop     dword ptr [rax+rax+00h]
0x1800889a4  mov     ebx, eax
0x1800889a6  test    eax, eax
0x1800889a8  jns     short loc_1800889DB
0x1800889aa  cmp     [rbp+37h+arg_50], r14d
0x1800889b1  jz      short loc_1800889D2
0x1800889b3  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800889ba  jz      short loc_1800889D2
0x1800889bc  lea     r8, aDmgenerateatte_13; "DmGenerateAttestationClaims: NCryptExpo"...
0x1800889c3  mov     r9d, eax
0x1800889c6  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x1800889cd  call    McTemplateU0zd_EventWriteTransfer
0x1800889d2  cmp     [rbp+37h+arg_8], r14d
0x1800889d6  jmp     loc_180088FC9
0x1800889db  mov     ebx, dword ptr [rbp+37h+dwBytes+4]
0x1800889de  call    cs:__imp_GetProcessHeap
0x1800889e5  nop     dword ptr [rax+rax+00h]
0x1800889ea  mov     r8d, ebx; dwBytes
0x1800889ed  mov     edx, esi; dwFlags
0x1800889ef  mov     rcx, rax; hHeap
0x1800889f2  call    cs:__imp_HeapAlloc
0x1800889f9  nop     dword ptr [rax+rax+00h]
0x1800889fe  mov     rdx, rax
0x180088a01  lea     rcx, [rbp+37h+pbOutput]
0x180088a05  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x180088a0a  mov     r12, [rbp+37h+pbOutput]
0x180088a0e  test    r12, r12
0x180088a11  jnz     short loc_180088A37
0x180088a13  mov     edx, 3A8h; void *
0x180088a18  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\dm\\dmcmnutils\\atte"...
0x180088a1f  mov     r9d, 8007000Eh; char *
0x180088a25  mov     rcx, [rbp+3Fh]; this
0x180088a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088a2e  cmp     [rbp+37h+arg_8], r14d
0x180088a32  jmp     loc_180088EC2
0x180088a37  mov     eax, dword ptr [rbp+37h+dwBytes+4]
0x180088a3a  mov     [rsp+100h+dwFlags], r14d; dwFlags
0x180088a3f  lea     rcx, [rbp+37h+dwBytes+4]
0x180088a43  mov     [rsp+100h+pcbResult], rcx; pcbResult
0x180088a48  mov     dword ptr [rsp+100h+pfCallerFreeProvOrNCryptKey], eax; cbOutput
0x180088a4c  mov     [rsp+100h+pdwKeySpec], r12; pbOutput
0x180088a51  xor     r9d, r9d; pParameterList
0x180088a54  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180088a5b  xor     edx, edx; hExportKey
0x180088a5d  mov     rcx, [rsp+100h+phCryptProvOrNCryptKey]; hKey
0x180088a62  call    cs:__imp_NCryptExportKey
0x180088a69  nop     dword ptr [rax+rax+00h]
0x180088a6e  mov     ebx, eax
0x180088a70  test    eax, eax
0x180088a72  jns     short loc_180088A9A
0x180088a74  cmp     [rbp+37h+arg_50], r14d
0x180088a7b  jz      loc_1800889D2
0x180088a81  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088a88  jz      loc_1800889D2
0x180088a8e  lea     r8, aDmgenerateatte_8; "DmGenerateAttestationClaims: NCryptExpo"...
0x180088a95  jmp     loc_1800889C3
0x180088a9a  mov     rbx, [rbp+37h+hObject]
0x180088a9e  test    rbx, rbx
0x180088aa1  jz      short loc_180088AC4
0x180088aa3  lea     rcx, [rbp+37h+var_90]; this
0x180088aa7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180088aac  mov     rcx, rbx; hObject
0x180088aaf  call    cs:__imp_NCryptFreeObject
0x180088ab6  nop     dword ptr [rax+rax+00h]
0x180088abb  lea     rcx, [rbp+37h+var_90]; this
0x180088abf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180088ac4  mov     [rbp+37h+hObject], r14
0x180088ac8  xor     r8d, r8d; dwFlags
0x180088acb  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180088ad2  lea     rcx, [rbp+37h+hObject]; phProvider
0x180088ad6  call    cs:__imp_NCryptOpenStorageProvider
0x180088add  nop     dword ptr [rax+rax+00h]
0x180088ae2  mov     ebx, eax
0x180088ae4  test    eax, eax
0x180088ae6  jns     short loc_180088B0E
0x180088ae8  cmp     [rbp+37h+arg_50], r14d
0x180088aef  jz      loc_1800889D2
0x180088af5  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088afc  jz      loc_1800889D2
0x180088b02  lea     r8, aDmgenerateatte_2; "DmGenerateAttestationClaims: NCryptOpen"...
0x180088b09  jmp     loc_1800889C3
0x180088b0e  mov     rcx, [rbp+37h+hObject]; hObject
0x180088b12  call    ?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z; DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)
0x180088b17  mov     ebx, eax
0x180088b19  test    eax, eax
0x180088b1b  jns     short loc_180088B43
0x180088b1d  cmp     [rbp+37h+arg_50], r14d
0x180088b24  jz      loc_1800889D2
0x180088b2a  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088b31  jz      loc_1800889D2
0x180088b37  lea     r8, aDmgenerateatte_4; "DmGenerateAttestationClaims: SetWindows"...
0x180088b3e  jmp     loc_1800889C3
0x180088b43  mov     rbx, [rbp+37h+phKey]
0x180088b47  test    rbx, rbx
0x180088b4a  jz      short loc_180088B6D
0x180088b4c  lea     rcx, [rbp+37h+var_90]; this
0x180088b50  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180088b55  mov     rcx, rbx; hObject
0x180088b58  call    cs:__imp_NCryptFreeObject
0x180088b5f  nop     dword ptr [rax+rax+00h]
0x180088b64  lea     rcx, [rbp+37h+var_90]; this
0x180088b68  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180088b6d  mov     [rbp+37h+phKey], r14
0x180088b71  mov     dword ptr [rsp+100h+pdwKeySpec], r14d; dwFlags
0x180088b76  xor     r9d, r9d; dwLegacyKeySpec
0x180088b79  lea     r8, pszKeyName; "Windows AIK"
0x180088b80  lea     rdx, [rbp+37h+phKey]; phKey
0x180088b84  mov     rcx, [rbp+37h+hObject]; hProvider
0x180088b88  call    cs:__imp_NCryptOpenKey
0x180088b8f  nop     dword ptr [rax+rax+00h]
0x180088b94  mov     ebx, eax
0x180088b96  test    eax, eax
0x180088b98  jns     short loc_180088BC0
0x180088b9a  cmp     [rbp+37h+arg_50], r14d
0x180088ba1  jz      loc_1800889D2
0x180088ba7  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088bae  jz      loc_1800889D2
0x180088bb4  lea     r8, aDmgenerateatte_3; "DmGenerateAttestationClaims: NCryptOpen"...
0x180088bbb  jmp     loc_1800889C3
0x180088bc0  mov     [rsp+100h+dwFlags], r14d
0x180088bc5  lea     rax, [rbp+37h+dwBytes]
0x180088bc9  mov     [rsp+100h+pcbResult], rax
0x180088bce  mov     dword ptr [rsp+100h+pfCallerFreeProvOrNCryptKey], r14d
0x180088bd3  mov     [rsp+100h+pdwKeySpec], r14
0x180088bd8  xor     r9d, r9d
0x180088bdb  lea     edi, [r9+2]
0x180088bdf  mov     r8d, edi
0x180088be2  mov     rdx, [rbp+37h+phKey]
0x180088be6  mov     rcx, [rsp+100h+phCryptProvOrNCryptKey]
0x180088beb  call    cs:__imp_NCryptCreateClaim
0x180088bf2  nop     dword ptr [rax+rax+00h]
0x180088bf7  mov     ebx, eax
0x180088bf9  test    eax, eax
0x180088bfb  jns     short loc_180088C23
0x180088bfd  cmp     [rbp+37h+arg_50], r14d
0x180088c04  jz      loc_1800889D2
0x180088c0a  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088c11  jz      loc_1800889D2
0x180088c17  lea     r8, aDmgenerateatte_12; "DmGenerateAttestationClaims: NCryptCrea"...
0x180088c1e  jmp     loc_1800889C3
0x180088c23  mov     ebx, dword ptr [rbp+37h+dwBytes]
0x180088c26  call    cs:__imp_GetProcessHeap
0x180088c2d  nop     dword ptr [rax+rax+00h]
0x180088c32  mov     r8d, ebx; dwBytes
0x180088c35  mov     edx, esi; dwFlags
0x180088c37  mov     rcx, rax; hHeap
0x180088c3a  call    cs:__imp_HeapAlloc
0x180088c41  nop     dword ptr [rax+rax+00h]
0x180088c46  mov     rdx, rax
0x180088c49  lea     rcx, [rbp+37h+var_80]
0x180088c4d  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x180088c52  mov     rcx, [rbp+37h+var_80]
0x180088c56  mov     [rbp+37h+var_90], rcx
0x180088c5a  test    rcx, rcx
0x180088c5d  jnz     short loc_180088C69
0x180088c5f  mov     edx, 3EAh
0x180088c64  jmp     loc_180088A18
0x180088c69  mov     eax, dword ptr [rbp+37h+dwBytes]
0x180088c6c  mov     [rsp+100h+dwFlags], r14d
0x180088c71  lea     rdx, [rbp+37h+dwBytes]
0x180088c75  mov     [rsp+100h+pcbResult], rdx
0x180088c7a  mov     dword ptr [rsp+100h+pfCallerFreeProvOrNCryptKey], eax
0x180088c7e  mov     [rsp+100h+pdwKeySpec], rcx
0x180088c83  xor     r9d, r9d
0x180088c86  mov     r8d, edi
0x180088c89  mov     rdx, [rbp+37h+phKey]
0x180088c8d  mov     rcx, [rsp+100h+phCryptProvOrNCryptKey]
0x180088c92  call    cs:__imp_NCryptCreateClaim
0x180088c99  nop     dword ptr [rax+rax+00h]
0x180088c9e  mov     ebx, eax
0x180088ca0  test    eax, eax
0x180088ca2  jns     short loc_180088CCA
0x180088ca4  cmp     [rbp+37h+arg_50], r14d
0x180088cab  jz      loc_1800889D2
0x180088cb1  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180088cb8  jz      loc_1800889D2
0x180088cbe  lea     r8, aDmgenerateatte_16; "DmGenerateAttestationClaims: NCryptCrea"...
0x180088cc5  jmp     loc_1800889C3
0x180088cca  mov     r14, [rbp+37h+arg_48]
0x180088cd1  mov     r15, [rbp+37h+arg_40]
0x180088cd8  xor     ebx, ebx
0x180088cda  test    r15, r15
0x180088cdd  jz      loc_180088DE1
0x180088ce3  test    r14, r14
0x180088ce6  jz      loc_180088DE1
  ... truncated ...
```
