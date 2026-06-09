# DmGenerateAttestationClaims(_CERT_CONTEXT const *,int,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,int)

- ea: `0x180087b90`
- end: `0x180088322`
- name: `?DmGenerateAttestationClaims@@YAJPEBU_CERT_CONTEXT@@HPEAPEAEPEAK121212H@Z`
- size: `1938`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, int@<edx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180057c6c`
- `0x18005b914`
- `0x18005bd30`
- `0x1800605a8`
- `0x1800609dc`
- `0x180061a64`
- `0x180062704`
- `0x180062728`
- `0x180069ef0`
- `0x18008572c`
- `0x180085a08`
- `0x180087674`
- `0x180087b90`
- `0x1800940b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087e4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087fa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800880c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800881a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087e4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087fa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800880c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800881a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800880b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800880b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d61`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180087d23`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180087d23`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180087e20`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180087f79`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008804c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088205`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088286`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180087e20`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180087f79`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008804c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088205`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180088286`
- `ncrypt!NCryptCreateClaim` at `0x180087f2e`
- `ncrypt!NCryptCreateClaim` at `0x180088001`
- `ncrypt!NCryptCreateClaim` at `0x180087f2e`
- `ncrypt!NCryptCreateClaim` at `0x180088001`
- `ncrypt!NCryptExportKey` at `0x180087dce`
- `ncrypt!NCryptExportKey` at `0x180087eba`
- `ncrypt!NCryptExportKey` at `0x180088170`
- `ncrypt!NCryptExportKey` at `0x180088243`
- `ncrypt!NCryptExportKey` at `0x180087dce`
- `ncrypt!NCryptExportKey` at `0x180087eba`
- `ncrypt!NCryptExportKey` at `0x180088170`
- `ncrypt!NCryptExportKey` at `0x180088243`
- `ncrypt!NCryptFreeObject` at `0x180087e0d`
- `ncrypt!NCryptFreeObject` at `0x180087f69`
- `ncrypt!NCryptFreeObject` at `0x18008803c`
- `ncrypt!NCryptFreeObject` at `0x1800881f5`
- `ncrypt!NCryptFreeObject` at `0x180088276`
- `ncrypt!NCryptFreeObject` at `0x180087e0d`
- `ncrypt!NCryptFreeObject` at `0x180087f69`
- `ncrypt!NCryptFreeObject` at `0x18008803c`
- `ncrypt!NCryptFreeObject` at `0x1800881f5`
- `ncrypt!NCryptFreeObject` at `0x180088276`
- `ncrypt!NCryptGetProperty` at `0x180088098`
- `ncrypt!NCryptGetProperty` at `0x180088110`
- `ncrypt!NCryptGetProperty` at `0x180088098`
- `ncrypt!NCryptGetProperty` at `0x180088110`

## string_xrefs

- `0x180087cd9`: `DmGenerateAttestationClaims: DmGetActiveUserSid`
- `0x180088013`: `DmGenerateAttestationClaims: NCryptCreateClaim`
- `0x180087f40`: `DmGenerateAttestationClaims: NCryptCreateClaim(size)`
- `0x180087fca`: `DmGenerateAttestationClaims: NCryptCreateClaim(size allocation)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DmGenerateAttestationClaims(
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
  int ActiveUserSid; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  signed int v16; // eax
  SECURITY_STATUS v17; // eax
  const wchar_t *v18; // rdx
  DWORD v19; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v21; // rax
  __int64 v22; // rdx
  NCRYPT_HANDLE v23; // rbx
  SECURITY_STATUS Claim; // esi
  const wchar_t *v25; // rdx
  unsigned int v26; // edi
  HANDLE v27; // rax
  LPVOID v28; // rax
  const wchar_t *v29; // rdx
  SECURITY_STATUS Property; // edi
  const wchar_t *v31; // rdx
  unsigned int v32; // edi
  HANDLE v33; // rax
  LPVOID v34; // rax
  DWORD v35; // edi
  HANDLE v36; // rax
  LPVOID v37; // rax
  int pdwKeySpec; // [rsp+20h] [rbp-E0h]
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v41; // [rsp+48h] [rbp-B8h] BYREF
  int *v42; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbOutput; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pcbResult; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  PBYTE v48; // [rsp+78h] [rbp-88h] BYREF
  PBYTE v49; // [rsp+80h] [rbp-80h] BYREF
  PBYTE pbOutput; // [rsp+88h] [rbp-78h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v52[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v56[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v57; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int8 **v60; // [rsp+190h] [rbp+90h] BYREF
  unsigned int *v61; // [rsp+198h] [rbp+98h] BYREF

  v61 = a4;
  v60 = a3;
  v55 = 0;
  phCryptProvOrNCryptKey = 0;
  v41 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  hObject = 0;
  v54 = 0;
  v53 = 0;
  pbOutput = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  cbOutput = 0;
  pcbResult = 0;
  dwBytes = 0;
  v46 = 0;
  v56[0] = &v60;
  v56[1] = &v47;
  v56[2] = &v61;
  v56[3] = &dwBytes;
  v56[4] = &a5;
  v56[5] = &a6;
  v56[6] = &pbOutput;
  v56[7] = &cbOutput;
  v56[8] = &a7;
  v56[9] = &a8;
  v56[10] = &v48;
  v56[11] = &pcbResult;
  v56[12] = &a9;
  v56[13] = &a10;
  v56[14] = &v49;
  v56[15] = (char *)&dwBytes + 4;
  v57 = 1;
  v52[0] = 0;
  v52[2] = 0;
  v42 = &a11;
  if ( !a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v46,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v46);
    v14 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(
        &v42,
        L"DmGenerateAttestationClaims: DmGetActiveUserSid",
        (unsigned int)ActiveUserSid);
      goto LABEL_70;
    }
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)v52, v46);
  }
  if ( !CryptAcquireCertificatePrivateKey(
          pCert,
          0x40040u,
          0,
          &phCryptProvOrNCryptKey,
          &v41,
          &pfCallerFreeProvOrNCryptKey) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(
      &v42,
      L"DmGenerateAttestationClaims: CryptAcquireCertificatePrivateKey",
      (unsigned int)LastError);
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v14 = v16;
    goto LABEL_70;
  }
  if ( !a2 )
    AutoImpersonate::RevertToSelf((AutoImpersonate *)v52);
  if ( a5 && a6 )
  {
    v17 = NCryptExportKey(phCryptProvOrNCryptKey, 0, L"RSAPUBLICBLOB", 0, 0, 0, &cbOutput, 0);
    v14 = v17;
    if ( v17 < 0 )
    {
      v18 = L"DmGenerateAttestationClaims: NCryptExportKey(size)";
      goto LABEL_17;
    }
    v19 = cbOutput;
    ProcessHeap = GetProcessHeap();
    v21 = HeapAlloc(ProcessHeap, 8u, v19);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, v21);
    if ( !pbOutput )
    {
      v22 = 1237;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
        (const char *)0x8007000ELL,
        pdwKeySpec);
LABEL_58:
      if ( pfCallerFreeProvOrNCryptKey )
      {
        if ( v41 == -1 )
          NCryptFreeObject(phCryptProvOrNCryptKey);
        else
          CryptReleaseContext(phCryptProvOrNCryptKey, 0);
      }
      v14 = -2147024882;
      goto LABEL_70;
    }
    v17 = NCryptExportKey(phCryptProvOrNCryptKey, 0, L"RSAPUBLICBLOB", 0, pbOutput, cbOutput, &cbOutput, 0);
    v14 = v17;
    if ( v17 < 0 )
    {
      v18 = L"DmGenerateAttestationClaims: NCryptExportKey";
      goto LABEL_17;
    }
  }
  hObject = 0;
  v17 = DMGetWindowsAIKKeyFromKeyHandle(phCryptProvOrNCryptKey, a11, &hObject);
  v14 = v17;
  if ( v17 < 0 )
  {
    v18 = L"DmGenerateAttestationClaims: DMGetWindowsAIKKeyFromKeyHandle";
    goto LABEL_17;
  }
  v23 = hObject;
  Claim = NCryptCreateClaim(phCryptProvOrNCryptKey, hObject, 2);
  if ( Claim < 0 )
  {
    v25 = L"DmGenerateAttestationClaims: NCryptCreateClaim(size)";
LABEL_30:
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v42, v25, (unsigned int)Claim);
    if ( pfCallerFreeProvOrNCryptKey )
    {
      if ( v41 == -1 )
        NCryptFreeObject(phCryptProvOrNCryptKey);
      else
        CryptReleaseContext(phCryptProvOrNCryptKey, 0);
    }
    v14 = Claim;
    goto LABEL_70;
  }
  v26 = dwBytes;
  v27 = GetProcessHeap();
  v28 = HeapAlloc(v27, 8u, v26);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v47, v28);
  if ( !v47 )
  {
    v29 = L"DmGenerateAttestationClaims: NCryptCreateClaim(size allocation)";
LABEL_57:
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v42, v29, (unsigned int)Claim);
    goto LABEL_58;
  }
  Property = NCryptCreateClaim(phCryptProvOrNCryptKey, v23, 2);
  if ( Property < 0 )
  {
    v31 = L"DmGenerateAttestationClaims: NCryptCreateClaim";
LABEL_39:
    lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v42, v31, (unsigned int)Property);
    if ( pfCallerFreeProvOrNCryptKey )
    {
      if ( v41 == -1 )
        NCryptFreeObject(phCryptProvOrNCryptKey);
      else
        CryptReleaseContext(phCryptProvOrNCryptKey, 0);
    }
    v14 = Property;
    goto LABEL_70;
  }
  if ( a9 && a10 && NCryptGetProperty(v23, L"SmartCardKeyCertificate", 0, 0, (DWORD *)&dwBytes + 1, 0) >= 0 )
  {
    v32 = HIDWORD(dwBytes);
    v33 = GetProcessHeap();
    v34 = HeapAlloc(v33, 8u, v32);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v49, v34);
    if ( !v49 )
    {
      v22 = 1303;
      goto LABEL_23;
    }
    Property = NCryptGetProperty(v23, L"SmartCardKeyCertificate", v49, HIDWORD(dwBytes), (DWORD *)&dwBytes + 1, 0);
    if ( Property < 0 )
    {
      v31 = L"DmGenerateAttestationClaims: NCryptGetProperty(hAIK Cert)";
      goto LABEL_39;
    }
  }
  if ( a7 && a8 )
  {
    Claim = NCryptExportKey(v23, 0, L"RSAPUBLICBLOB", 0, 0, 0, &pcbResult, 0);
    if ( Claim < 0 )
    {
      v25 = L"DmGenerateAttestationClaims: NCryptExportKey(hAIK size)";
      goto LABEL_30;
    }
    v35 = pcbResult;
    v36 = GetProcessHeap();
    v37 = HeapAlloc(v36, 8u, v35);
    wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v48, v37);
    if ( !v48 )
    {
      v29 = L"DmGenerateAttestationClaims: NCryptExportKey(hAIK size allocation)";
      goto LABEL_57;
    }
    v17 = NCryptExportKey(v23, 0, L"RSAPUBLICBLOB", 0, v48, pcbResult, &pcbResult, 0);
    v14 = v17;
    if ( v17 < 0 )
    {
      v18 = L"DmGenerateAttestationClaims: NCryptExportKey(hAIK)";
LABEL_17:
      lambda_a34be7e6fffcc5ac521306cfbd109a62_::operator()(&v42, v18, (unsigned int)v17);
      if ( pfCallerFreeProvOrNCryptKey )
      {
        if ( v41 == -1 )
          NCryptFreeObject(phCryptProvOrNCryptKey);
        else
          CryptReleaseContext(phCryptProvOrNCryptKey, 0);
      }
      goto LABEL_70;
    }
  }
  if ( pfCallerFreeProvOrNCryptKey )
  {
    if ( v41 == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  }
  v14 = 0;
LABEL_70:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v52);
  v57 = 0;
  lambda_d0cb7f3cccf3788457860c3f57d6f11f_::operator()(v56);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v47, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v48, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&v49, 0);
  wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::reset(&pbOutput, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v55);
  return v14;
}

```

## disassembly

```asm
0x180087b90  mov     [rsp-8+arg_18], r9
0x180087b95  mov     [rsp-8+arg_10], r8
0x180087b9a  push    rbp
0x180087b9b  push    rbx
0x180087b9c  push    rsi
0x180087b9d  push    rdi
0x180087b9e  push    r14
0x180087ba0  lea     rbp, [rsp-50h]
0x180087ba5  sub     rsp, 150h
0x180087bac  mov     edi, edx
0x180087bae  mov     rsi, rcx
0x180087bb1  xor     r14d, r14d
0x180087bb4  mov     [rbp+70h+var_B8], r14
0x180087bb8  mov     [rsp+170h+phCryptProvOrNCryptKey], r14
0x180087bbd  mov     [rsp+170h+var_128], r14d
0x180087bc2  mov     [rbp+70h+arg_8], r14d
0x180087bc9  mov     [rbp+70h+hObject], r14
0x180087bcd  mov     [rbp+70h+var_C0], r14
0x180087bd1  mov     [rbp+70h+var_C8], r14
0x180087bd5  mov     [rbp+70h+pbOutput], r14
0x180087bd9  mov     [rbp+70h+var_F0], r14
0x180087bdd  mov     [rsp+170h+var_F8], r14
0x180087be2  mov     [rsp+170h+var_100], r14
0x180087be7  mov     [rsp+170h+cbOutput], r14d
0x180087bec  mov     dword ptr [rsp+170h+dwBytes+4], r14d
0x180087bf1  mov     [rsp+170h+var_10C], r14d
0x180087bf6  mov     dword ptr [rsp+170h+dwBytes], r14d
0x180087bfb  mov     [rsp+170h+var_108], r14
0x180087c00  lea     rax, [rbp+70h+arg_10]
0x180087c07  mov     [rbp+70h+var_B0], rax
0x180087c0b  lea     rax, [rsp+170h+var_100]
0x180087c10  mov     [rbp+70h+var_A8], rax
0x180087c14  lea     rax, [rbp+70h+arg_18]
0x180087c1b  mov     [rbp+70h+var_A0], rax
0x180087c1f  lea     rax, [rsp+170h+dwBytes]
0x180087c24  mov     [rbp+70h+var_98], rax
0x180087c28  lea     rax, [rbp+70h+arg_20]
0x180087c2f  mov     [rbp+70h+var_90], rax
0x180087c33  lea     rax, [rbp+70h+arg_28]
0x180087c3a  mov     [rbp+70h+var_88], rax
0x180087c3e  lea     rax, [rbp+70h+pbOutput]
0x180087c42  mov     [rbp+70h+var_80], rax
0x180087c46  lea     rax, [rsp+170h+cbOutput]
0x180087c4b  mov     [rbp+70h+var_78], rax
0x180087c4f  lea     rax, [rbp+70h+arg_30]
0x180087c56  mov     [rbp+70h+var_70], rax
0x180087c5a  lea     rax, [rbp+70h+arg_38]
0x180087c61  mov     [rbp+70h+var_68], rax
0x180087c65  lea     rax, [rsp+170h+var_F8]
0x180087c6a  mov     [rbp+70h+var_60], rax
0x180087c6e  lea     rax, [rsp+170h+var_10C]
0x180087c73  mov     [rbp+70h+var_58], rax
0x180087c77  lea     rax, [rbp+70h+arg_40]
0x180087c7e  mov     [rbp+70h+var_50], rax
0x180087c82  lea     rax, [rbp+70h+arg_48]
0x180087c89  mov     [rbp+70h+var_48], rax
0x180087c8d  lea     rax, [rbp+70h+var_F0]
0x180087c91  mov     [rbp+70h+var_40], rax
0x180087c95  lea     rax, [rsp+170h+dwBytes+4]
0x180087c9a  mov     [rbp+70h+var_38], rax
0x180087c9e  mov     [rbp+70h+var_30], 1
0x180087ca2  mov     [rbp+70h+var_D8], r14b
0x180087ca6  mov     [rbp+70h+var_D6], r14b
0x180087caa  lea     rax, [rbp+70h+arg_50]
0x180087cb1  mov     [rsp+170h+var_120], rax
0x180087cb6  test    edx, edx
0x180087cb8  jnz     short loc_180087CFD
0x180087cba  xor     edx, edx
0x180087cbc  lea     rcx, [rsp+170h+var_108]
0x180087cc1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180087cc6  lea     rcx, [rsp+170h+var_108]; unsigned __int16 **
0x180087ccb  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180087cd0  mov     ebx, eax
0x180087cd2  test    eax, eax
0x180087cd4  jns     short loc_180087CEF
0x180087cd6  mov     r8d, eax
0x180087cd9  lea     rdx, aDmgenerateatte_14; "DmGenerateAttestationClaims: DmGetActiv"...
0x180087ce0  lea     rcx, [rsp+170h+var_120]
0x180087ce5  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x180087cea  jmp     loc_180088295
0x180087cef  mov     rdx, [rsp+170h+var_108]; unsigned __int16 *
0x180087cf4  lea     rcx, [rbp+70h+var_D8]; this
0x180087cf8  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x180087cfd  lea     rax, [rbp+70h+arg_8]
0x180087d04  mov     [rsp+170h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x180087d09  lea     rax, [rsp+170h+var_128]
0x180087d0e  mov     [rsp+170h+pdwKeySpec], rax; pdwKeySpec
0x180087d13  lea     r9, [rsp+170h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180087d18  xor     r8d, r8d; pvParameters
0x180087d1b  mov     edx, 40040h; dwFlags
0x180087d20  mov     rcx, rsi; pCert
0x180087d23  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180087d2a  nop     dword ptr [rax+rax+00h]
0x180087d2f  test    eax, eax
0x180087d31  jnz     short loc_180087D7D
0x180087d33  call    cs:__imp_GetLastError
0x180087d3a  nop     dword ptr [rax+rax+00h]
0x180087d3f  mov     ebx, 80070000h
0x180087d44  test    eax, eax
0x180087d46  jle     short loc_180087D4D
0x180087d48  movzx   eax, ax
0x180087d4b  or      eax, ebx
0x180087d4d  mov     r8d, eax
0x180087d50  lea     rdx, aDmgenerateatte_5; "DmGenerateAttestationClaims: CryptAcqui"...
0x180087d57  lea     rcx, [rsp+170h+var_120]
0x180087d5c  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x180087d61  call    cs:__imp_GetLastError
0x180087d68  nop     dword ptr [rax+rax+00h]
0x180087d6d  test    eax, eax
0x180087d6f  jle     short loc_180087D76
0x180087d71  movzx   eax, ax
0x180087d74  or      eax, ebx
0x180087d76  mov     ebx, eax
0x180087d78  jmp     loc_180088295
0x180087d7d  test    edi, edi
0x180087d7f  jnz     short loc_180087D8A
0x180087d81  lea     rcx, [rbp+70h+var_D8]; this
0x180087d85  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x180087d8a  cmp     [rbp+70h+arg_20], r14
0x180087d91  jz      loc_180087ED8
0x180087d97  cmp     [rbp+70h+arg_28], r14
0x180087d9e  jz      loc_180087ED8
0x180087da4  mov     [rsp+170h+dwFlags], r14d; dwFlags
0x180087da9  lea     rax, [rsp+170h+cbOutput]
0x180087dae  mov     [rsp+170h+pcbResult], rax; pcbResult
0x180087db3  mov     dword ptr [rsp+170h+pfCallerFreeProvOrNCryptKey], r14d; cbOutput
0x180087db8  mov     [rsp+170h+pdwKeySpec], r14; int
0x180087dbd  xor     r9d, r9d; pParameterList
0x180087dc0  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180087dc7  xor     edx, edx; hExportKey
0x180087dc9  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hKey
0x180087dce  call    cs:__imp_NCryptExportKey
0x180087dd5  nop     dword ptr [rax+rax+00h]
0x180087dda  mov     ebx, eax
0x180087ddc  test    eax, eax
0x180087dde  jns     short loc_180087E31
0x180087de0  lea     rdx, aDmgenerateatte_13; "DmGenerateAttestationClaims: NCryptExpo"...
0x180087de7  mov     r8d, eax
0x180087dea  lea     rcx, [rsp+170h+var_120]
0x180087def  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x180087df4  cmp     [rbp+70h+arg_8], r14d
0x180087dfb  jz      loc_180088295
0x180087e01  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hProv
0x180087e06  cmp     [rsp+170h+var_128], 0FFFFFFFFh
0x180087e0b  jnz     short loc_180087E1E
0x180087e0d  call    cs:__imp_NCryptFreeObject
0x180087e14  nop     dword ptr [rax+rax+00h]
0x180087e19  jmp     loc_180088295
0x180087e1e  xor     edx, edx; dwFlags
0x180087e20  call    cs:__imp_CryptReleaseContext
0x180087e27  nop     dword ptr [rax+rax+00h]
0x180087e2c  jmp     loc_180088295
0x180087e31  mov     ebx, [rsp+170h+cbOutput]
0x180087e35  call    cs:__imp_GetProcessHeap
0x180087e3c  nop     dword ptr [rax+rax+00h]
0x180087e41  mov     r8d, ebx; dwBytes
0x180087e44  mov     edx, 8; dwFlags
0x180087e49  mov     rcx, rax; hHeap
0x180087e4c  call    cs:__imp_HeapAlloc
0x180087e53  nop     dword ptr [rax+rax+00h]
0x180087e58  mov     rdx, rax
0x180087e5b  lea     rcx, [rbp+70h+pbOutput]
0x180087e5f  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x180087e64  mov     rax, [rbp+70h+pbOutput]
0x180087e68  test    rax, rax
0x180087e6b  jnz     short loc_180087E8D
0x180087e6d  mov     edx, 4D5h; void *
0x180087e72  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\dm\\dmcmnutils\\atte"...
0x180087e79  mov     r9d, 8007000Eh; char *
0x180087e7f  mov     rcx, [rbp+78h]; this
0x180087e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087e88  jmp     loc_1800881E0
0x180087e8d  mov     edx, [rsp+170h+cbOutput]
0x180087e91  mov     [rsp+170h+dwFlags], r14d; dwFlags
0x180087e96  lea     rcx, [rsp+170h+cbOutput]
0x180087e9b  mov     [rsp+170h+pcbResult], rcx; pcbResult
0x180087ea0  mov     dword ptr [rsp+170h+pfCallerFreeProvOrNCryptKey], edx; cbOutput
0x180087ea4  mov     [rsp+170h+pdwKeySpec], rax; pbOutput
0x180087ea9  xor     r9d, r9d; pParameterList
0x180087eac  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180087eb3  xor     edx, edx; hExportKey
0x180087eb5  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hKey
0x180087eba  call    cs:__imp_NCryptExportKey
0x180087ec1  nop     dword ptr [rax+rax+00h]
0x180087ec6  mov     ebx, eax
0x180087ec8  test    eax, eax
0x180087eca  jns     short loc_180087ED8
0x180087ecc  lea     rdx, aDmgenerateatte_8; "DmGenerateAttestationClaims: NCryptExpo"...
0x180087ed3  jmp     loc_180087DE7
0x180087ed8  mov     [rbp+70h+hObject], r14
0x180087edc  lea     r8, [rbp+70h+hObject]; unsigned __int64 *
0x180087ee0  mov     edx, [rbp+70h+arg_50]; int
0x180087ee6  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hObject
0x180087eeb  call    ?DMGetWindowsAIKKeyFromKeyHandle@@YAJ_KHPEA_K@Z; DMGetWindowsAIKKeyFromKeyHandle(unsigned __int64,int,unsigned __int64 *)
0x180087ef0  mov     ebx, eax
0x180087ef2  test    eax, eax
0x180087ef4  jns     short loc_180087F02
0x180087ef6  lea     rdx, aDmgenerateatte_15; "DmGenerateAttestationClaims: DMGetWindo"...
0x180087efd  jmp     loc_180087DE7
0x180087f02  mov     [rsp+170h+dwFlags], r14d
0x180087f07  lea     rax, [rsp+170h+dwBytes]
0x180087f0c  mov     [rsp+170h+pcbResult], rax
0x180087f11  mov     dword ptr [rsp+170h+pfCallerFreeProvOrNCryptKey], r14d
0x180087f16  mov     [rsp+170h+pdwKeySpec], r14
0x180087f1b  xor     r9d, r9d
0x180087f1e  lea     r8d, [r9+2]
0x180087f22  mov     rbx, [rbp+70h+hObject]
0x180087f26  mov     rdx, rbx
0x180087f29  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]
0x180087f2e  call    cs:__imp_NCryptCreateClaim
0x180087f35  nop     dword ptr [rax+rax+00h]
0x180087f3a  mov     esi, eax
0x180087f3c  test    eax, eax
0x180087f3e  jns     short loc_180087F8C
0x180087f40  lea     rdx, aDmgenerateatte_12; "DmGenerateAttestationClaims: NCryptCrea"...
0x180087f47  mov     r8d, esi
0x180087f4a  lea     rcx, [rsp+170h+var_120]
0x180087f4f  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x180087f54  cmp     [rbp+70h+arg_8], r14d
0x180087f5b  jz      short loc_180087F85
0x180087f5d  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hProv
0x180087f62  cmp     [rsp+170h+var_128], 0FFFFFFFFh
0x180087f67  jnz     short loc_180087F77
0x180087f69  call    cs:__imp_NCryptFreeObject
0x180087f70  nop     dword ptr [rax+rax+00h]
0x180087f75  jmp     short loc_180087F85
0x180087f77  xor     edx, edx; dwFlags
0x180087f79  call    cs:__imp_CryptReleaseContext
0x180087f80  nop     dword ptr [rax+rax+00h]
0x180087f85  mov     ebx, esi
0x180087f87  jmp     loc_180088295
0x180087f8c  mov     edi, dword ptr [rsp+170h+dwBytes]
0x180087f90  call    cs:__imp_GetProcessHeap
0x180087f97  nop     dword ptr [rax+rax+00h]
0x180087f9c  mov     r8d, edi; dwBytes
0x180087f9f  mov     edx, 8; dwFlags
0x180087fa4  mov     rcx, rax; hHeap
0x180087fa7  call    cs:__imp_HeapAlloc
0x180087fae  nop     dword ptr [rax+rax+00h]
0x180087fb3  mov     rdx, rax
0x180087fb6  lea     rcx, [rsp+170h+var_100]
0x180087fbb  call    ?reset@?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::process_heap_deleter>::reset(uchar *)
0x180087fc0  mov     rax, [rsp+170h+var_100]
0x180087fc5  test    rax, rax
0x180087fc8  jnz     short loc_180087FD6
0x180087fca  lea     rdx, aDmgenerateatte_7; "DmGenerateAttestationClaims: NCryptCrea"...
0x180087fd1  jmp     loc_1800881D3
0x180087fd6  mov     edx, dword ptr [rsp+170h+dwBytes]
0x180087fda  mov     [rsp+170h+dwFlags], r14d
0x180087fdf  lea     rcx, [rsp+170h+dwBytes]
0x180087fe4  mov     [rsp+170h+pcbResult], rcx
0x180087fe9  mov     dword ptr [rsp+170h+pfCallerFreeProvOrNCryptKey], edx
0x180087fed  mov     [rsp+170h+pdwKeySpec], rax
0x180087ff2  xor     r9d, r9d
0x180087ff5  lea     r8d, [r9+2]
0x180087ff9  mov     rdx, rbx
0x180087ffc  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]
0x180088001  call    cs:__imp_NCryptCreateClaim
0x180088008  nop     dword ptr [rax+rax+00h]
0x18008800d  mov     edi, eax
0x18008800f  test    eax, eax
0x180088011  jns     short loc_18008805F
0x180088013  lea     rdx, aDmgenerateatte_16; "DmGenerateAttestationClaims: NCryptCrea"...
0x18008801a  mov     r8d, edi
0x18008801d  lea     rcx, [rsp+170h+var_120]
0x180088022  call    _lambda_a34be7e6fffcc5ac521306cfbd109a62___operator__
0x180088027  cmp     [rbp+70h+arg_8], r14d
0x18008802e  jz      short loc_180088058
0x180088030  mov     rcx, [rsp+170h+phCryptProvOrNCryptKey]; hProv
0x180088035  cmp     [rsp+170h+var_128], 0FFFFFFFFh
0x18008803a  jnz     short loc_18008804A
0x18008803c  call    cs:__imp_NCryptFreeObject
0x180088043  nop     dword ptr [rax+rax+00h]
0x180088048  jmp     short loc_180088058
0x18008804a  xor     edx, edx; dwFlags
0x18008804c  call    cs:__imp_CryptReleaseContext
0x180088053  nop     dword ptr [rax+rax+00h]
0x180088058  mov     ebx, edi
0x18008805a  jmp     loc_180088295
0x18008805f  cmp     [rbp+70h+arg_40], r14
0x180088066  jz      loc_18008812E
0x18008806c  cmp     [rbp+70h+arg_48], r14
0x180088073  jz      loc_18008812E
0x180088079  mov     dword ptr [rsp+170h+pfCallerFreeProvOrNCryptKey], r14d; dwFlags
0x18008807e  lea     rax, [rsp+170h+dwBytes+4]
0x180088083  mov     [rsp+170h+pdwKeySpec], rax; pcbResult
0x180088088  xor     r9d, r9d; cbOutput
0x18008808b  xor     r8d, r8d; pbOutput
0x18008808e  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180088095  mov     rcx, rbx; hObject
0x180088098  call    cs:__imp_NCryptGetProperty
0x18008809f  nop     dword ptr [rax+rax+00h]
0x1800880a4  test    eax, eax
0x1800880a6  js      loc_18008812E
0x1800880ac  mov     edi, dword ptr [rsp+170h+dwBytes+4]
0x1800880b0  call    cs:__imp_GetProcessHeap
0x1800880b7  nop     dword ptr [rax+rax+00h]
0x1800880bc  mov     r8d, edi; dwBytes
0x1800880bf  mov     edx, 8; dwFlags
0x1800880c4  mov     rcx, rax; hHeap
  ... truncated ...
```
