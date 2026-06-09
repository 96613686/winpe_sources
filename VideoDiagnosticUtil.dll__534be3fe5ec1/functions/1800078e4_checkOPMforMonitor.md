# checkOPMforMonitor

- ea: `0x1800078e4`
- end: `0x180007d7a`
- name: `checkOPMforMonitor`
- size: `1174`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005134`

## callees

- `0x1800078e4`
- `0x18000823c`
- `0x180008820`
- `0x1800089fc`
- `0x18000967e`
- `0x1800096b0`
- `0x180009740`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800079ea`
- `KERNEL32!GetLastError` at `0x180007a24`
- `KERNEL32!GetLastError` at `0x1800079ea`
- `KERNEL32!GetLastError` at `0x180007a24`
- `ole32!CoTaskMemAlloc` at `0x180007aea`
- `ole32!CoTaskMemAlloc` at `0x180007aea`
- `ole32!CoTaskMemFree` at `0x180007d21`
- `ole32!CoTaskMemFree` at `0x180007d30`
- `ole32!CoTaskMemFree` at `0x180007d41`
- `ole32!CoTaskMemFree` at `0x180007d21`
- `ole32!CoTaskMemFree` at `0x180007d30`
- `ole32!CoTaskMemFree` at `0x180007d41`
- `CRYPT32!CertFreeCertificateContext` at `0x180007cfa`
- `CRYPT32!CertFreeCertificateContext` at `0x180007cfa`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007a13`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007a51`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007a13`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007a51`
- `CRYPT32!CryptGetMessageCertificates` at `0x1800079d6`
- `CRYPT32!CryptGetMessageCertificates` at `0x1800079d6`
- `CRYPT32!CryptImportPublicKeyInfo` at `0x180007a9e`
- `CRYPT32!CryptImportPublicKeyInfo` at `0x180007a9e`
- `CRYPT32!CertCloseStore` at `0x180007ca0`
- `CRYPT32!CertCloseStore` at `0x180007ca0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180007a7a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180007a7a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptExportKey` at `0x180007ad2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptExportKey` at `0x180007b24`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptExportKey` at `0x180007ad2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptExportKey` at `0x180007b24`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b46`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b6b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b8b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b46`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b6b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007b8b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007d10`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007d10`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180007ce6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180007ce6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007bb5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180007bb5`
- `bcrypt!BCryptDestroyKey` at `0x180007cb6`
- `bcrypt!BCryptDestroyKey` at `0x180007cb6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007cce`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007cce`

## pseudocode

```c
__int64 __fastcall checkOPMforMonitor(__int64 a1, _DWORD *a2)
{
  BYTE *v4; // rsi
  const CERT_CONTEXT *v5; // r15
  int v6; // ebx
  HCERTSTORE MessageCertificates; // rax
  void *v8; // rdi
  signed int v9; // eax
  const CERT_CONTEXT *v10; // rax
  signed int LastError; // eax
  DWORD pdwDataLen; // [rsp+30h] [rbp-D0h] BYREF
  BYTE v14[4]; // [rsp+34h] [rbp-CCh] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbSignedBlob; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v17[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  HCRYPTKEY phKey; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *pbSignedBlob; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  BYTE pbBuffer[16]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-60h] BYREF
  UCHAR pbInput[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v29; // [rsp+C0h] [rbp-40h]
  int v30; // [rsp+D0h] [rbp-30h]
  int v31; // [rsp+D4h] [rbp-2Ch]
  _BYTE v32[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  GUID v33; // [rsp+1D0h] [rbp+D0h]
  int v34; // [rsp+1E0h] [rbp+E0h]

  pbSignedBlob = 0;
  cbSignedBlob = 0;
  phProv = 0;
  *(_DWORD *)v14 = 0;
  *(_DWORD *)v17 = 0;
  phKey = 0;
  v4 = 0;
  pdwDataLen = 0;
  v5 = 0;
  phAlgorithm = 0;
  hKey = 0;
  pv = 0;
  v18 = 0;
  v19 = 0;
  v27 = 0;
  *(_OWORD *)pbBuffer = 0;
  memset_0(pbInput, 0, 0x100u);
  memset_0(v32, 0, 0x1010u);
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, BYTE **, DWORD *))(*(_QWORD *)a1 + 24LL))(
         a1,
         &v27,
         &pbSignedBlob,
         &cbSignedBlob);
  if ( v6 < 0 )
    goto LABEL_26;
  MessageCertificates = CryptGetMessageCertificates(0x10001u, 0, 0, pbSignedBlob, cbSignedBlob);
  v8 = MessageCertificates;
  if ( MessageCertificates )
  {
    v10 = CertEnumCertificatesInStore(MessageCertificates, 0);
    if ( v10 )
    {
      do
      {
        v5 = v10;
        v10 = CertEnumCertificatesInStore(v8, v10);
      }
      while ( v10 );
      if ( CryptAcquireContextA(&phProv, 0, 0, 1u, 0xF0000040)
        && CryptImportPublicKeyInfo(phProv, 1u, &v5->pCertInfo->SubjectPublicKeyInfo, &phKey)
        && CryptExportKey(phKey, 0, 6u, 0, 0, &pdwDataLen) )
      {
        v4 = (BYTE *)CoTaskMemAlloc(pdwDataLen);
        if ( !v4 )
          goto LABEL_13;
        if ( CryptExportKey(phKey, 0, 6u, 0, v4, &pdwDataLen)
          && CryptGenRandom(phProv, 0x10u, pbBuffer)
          && CryptGenRandom(phProv, 4u, v14)
          && CryptGenRandom(phProv, 4u, v17) )
        {
          v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
          if ( v6 < 0 )
            goto LABEL_25;
          v6 = importRsaPublicKey(phAlgorithm);
          if ( v6 < 0 )
            goto LABEL_25;
          v30 = *(_DWORD *)v14;
          v31 = *(_DWORD *)v17;
          *(_OWORD *)pbInput = v27;
          v29 = *(_OWORD *)pbBuffer;
          v6 = encryptSignatureUsingRSAWithSHA2(pbInput, (__int64)&hKey);
          if ( v6 < 0 )
            goto LABEL_25;
          if ( v18 >= 0x100 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)a1 + 32LL))(a1, pv);
            if ( v6 >= 0 )
            {
              v34 = *(_DWORD *)v14;
              v33 = OPM_GET_CONNECTOR_TYPE;
              v25 = *(_OWORD *)pbBuffer;
              v6 = sendAndVerifyOPMRequest(v32, &v25, a1, &v19);
              if ( v6 >= 0 )
                *a2 = (unsigned __int16)v19;
            }
            goto LABEL_25;
          }
LABEL_13:
          v6 = -2147024882;
LABEL_25:
          CertCloseStore(v8, 0);
          goto LABEL_26;
        }
      }
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_25;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_26:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( v5 )
    CertFreeCertificateContext(v5);
  if ( phKey )
    CryptDestroyKey(phKey);
  CoTaskMemFree(pbSignedBlob);
  CoTaskMemFree(v4);
  CoTaskMemFree(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800078e4  mov     [rsp-8+arg_10], rbx
0x1800078e9  push    rbp
0x1800078ea  push    rsi
0x1800078eb  push    rdi
0x1800078ec  push    r12
0x1800078ee  push    r13
0x1800078f0  push    r14
0x1800078f2  push    r15
0x1800078f4  lea     rbp, [rsp-10D0h]
0x1800078fc  mov     eax, 11D0h
0x180007901  call    _alloca_probe
0x180007906  sub     rsp, rax
0x180007909  mov     rax, cs:__security_cookie
0x180007910  xor     rax, rsp
0x180007913  mov     [rbp+1100h+var_40], rax
0x18000791a  xor     r13d, r13d
0x18000791d  mov     r12, rdx
0x180007920  mov     r14, rcx
0x180007923  mov     [rsp+1200h+pbSignedBlob], r13
0x180007928  xorps   xmm0, xmm0
0x18000792b  mov     [rsp+1200h+var_11C0], r13d
0x180007930  xorps   xmm1, xmm1
0x180007933  mov     [rsp+1200h+phProv], r13
0x180007938  xor     edx, edx; Val
0x18000793a  mov     dword ptr [rsp+1200h+var_11CC], r13d
0x18000793f  lea     rcx, [rbp+1100h+pbInput]; void *
0x180007943  mov     dword ptr [rsp+1200h+var_11BC], r13d
0x180007948  mov     r8d, 100h; Size
0x18000794e  mov     [rsp+1200h+phKey], r13
0x180007953  mov     esi, r13d
0x180007956  mov     [rsp+1200h+var_11D0], r13d
0x18000795b  mov     r15d, r13d
0x18000795e  mov     [rsp+1200h+phAlgorithm], r13
0x180007963  mov     [rsp+1200h+hKey], r13
0x180007968  mov     [rsp+1200h+pv], r13
0x18000796d  mov     [rsp+1200h+var_11B8], r13d
0x180007972  mov     [rsp+1200h+var_11B4], r13d
0x180007977  movups  [rbp+1100h+var_1160], xmm0
0x18000797b  movups  xmmword ptr [rbp+1100h+pbBuffer], xmm1
0x18000797f  call    memset_0
0x180007984  xor     edx, edx; Val
0x180007986  lea     rcx, [rbp+1100h+var_1050]; void *
0x18000798d  mov     r8d, 1010h; Size
0x180007993  call    memset_0
0x180007998  mov     rax, [r14]
0x18000799b  lea     r9, [rsp+1200h+var_11C0]
0x1800079a0  lea     r8, [rsp+1200h+pbSignedBlob]
0x1800079a5  mov     rcx, r14
0x1800079a8  lea     rdx, [rbp+1100h+var_1160]
0x1800079ac  mov     rax, [rax+18h]
0x1800079b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b5  mov     ebx, eax
0x1800079b7  test    eax, eax
0x1800079b9  js      loc_180007CAC
0x1800079bf  mov     eax, [rsp+1200h+var_11C0]
0x1800079c3  xor     r8d, r8d; dwFlags
0x1800079c6  mov     r9, [rsp+1200h+pbSignedBlob]; pbSignedBlob
0x1800079cb  xor     edx, edx; hCryptProv
0x1800079cd  mov     ecx, 10001h; dwMsgAndCertEncodingType
0x1800079d2  mov     [rsp+1200h+cbSignedBlob], eax; cbSignedBlob
0x1800079d6  call    cs:__imp_CryptGetMessageCertificates
0x1800079dd  nop     dword ptr [rax+rax+00h]
0x1800079e2  mov     rdi, rax
0x1800079e5  test    rax, rax
0x1800079e8  jnz     short loc_180007A0E
0x1800079ea  call    cs:__imp_GetLastError
0x1800079f1  nop     dword ptr [rax+rax+00h]
0x1800079f6  mov     ebx, eax
0x1800079f8  test    eax, eax
0x1800079fa  jle     loc_180007CAC
0x180007a00  movzx   ebx, ax
0x180007a03  or      ebx, 80070000h
0x180007a09  jmp     loc_180007CAC
0x180007a0e  xor     edx, edx; pPrevCertContext
0x180007a10  mov     rcx, rdi; hCertStore
0x180007a13  call    cs:__imp_CertEnumCertificatesInStore
0x180007a1a  nop     dword ptr [rax+rax+00h]
0x180007a1f  test    rax, rax
0x180007a22  jnz     short loc_180007A48
0x180007a24  call    cs:__imp_GetLastError
0x180007a2b  nop     dword ptr [rax+rax+00h]
0x180007a30  mov     ebx, eax
0x180007a32  test    eax, eax
0x180007a34  jle     loc_180007C9B
0x180007a3a  movzx   ebx, ax
0x180007a3d  or      ebx, 80070000h
0x180007a43  jmp     loc_180007C9B
0x180007a48  mov     rdx, rax; pPrevCertContext
0x180007a4b  mov     rcx, rdi; hCertStore
0x180007a4e  mov     r15, rax
0x180007a51  call    cs:__imp_CertEnumCertificatesInStore
0x180007a58  nop     dword ptr [rax+rax+00h]
0x180007a5d  test    rax, rax
0x180007a60  jnz     short loc_180007A48
0x180007a62  lea     ebx, [rax+1]
0x180007a65  mov     [rsp+1200h+cbSignedBlob], 0F0000040h; dwFlags
0x180007a6d  mov     r9d, ebx; dwProvType
0x180007a70  lea     rcx, [rsp+1200h+phProv]; phProv
0x180007a75  xor     r8d, r8d; szProvider
0x180007a78  xor     edx, edx; szContainer
0x180007a7a  call    cs:__imp_CryptAcquireContextA
0x180007a81  nop     dword ptr [rax+rax+00h]
0x180007a86  test    eax, eax
0x180007a88  jz      short loc_180007A24
0x180007a8a  mov     r8, [r15+18h]
0x180007a8e  lea     r9, [rsp+1200h+phKey]; phKey
0x180007a93  mov     rcx, [rsp+1200h+phProv]; hCryptProv
0x180007a98  add     r8, 60h ; '`'; pInfo
0x180007a9c  mov     edx, ebx; dwCertEncodingType
0x180007a9e  call    cs:__imp_CryptImportPublicKeyInfo
0x180007aa5  nop     dword ptr [rax+rax+00h]
0x180007aaa  test    eax, eax
0x180007aac  jz      loc_180007A24
0x180007ab2  mov     rcx, [rsp+1200h+phKey]; hKey
0x180007ab7  lea     rax, [rsp+1200h+var_11D0]
0x180007abc  xor     r9d, r9d; dwFlags
0x180007abf  mov     [rsp+1200h+pdwDataLen], rax; pdwDataLen
0x180007ac4  xor     edx, edx; hExpKey
0x180007ac6  mov     qword ptr [rsp+1200h+cbSignedBlob], r13; pbData
0x180007acb  lea     ebx, [r9+6]
0x180007acf  mov     r8d, ebx; dwBlobType
0x180007ad2  call    cs:__imp_CryptExportKey
0x180007ad9  nop     dword ptr [rax+rax+00h]
0x180007ade  test    eax, eax
0x180007ae0  jz      loc_180007A24
0x180007ae6  mov     ecx, [rsp+1200h+var_11D0]; cb
0x180007aea  call    cs:__imp_CoTaskMemAlloc
0x180007af1  nop     dword ptr [rax+rax+00h]
0x180007af6  mov     rsi, rax
0x180007af9  test    rax, rax
0x180007afc  jnz     short loc_180007B08
0x180007afe  mov     ebx, 8007000Eh
0x180007b03  jmp     loc_180007C9B
0x180007b08  mov     rcx, [rsp+1200h+phKey]; hKey
0x180007b0d  lea     rax, [rsp+1200h+var_11D0]
0x180007b12  mov     [rsp+1200h+pdwDataLen], rax; pdwDataLen
0x180007b17  xor     r9d, r9d; dwFlags
0x180007b1a  mov     r8d, ebx; dwBlobType
0x180007b1d  mov     qword ptr [rsp+1200h+cbSignedBlob], rsi; pbData
0x180007b22  xor     edx, edx; hExpKey
0x180007b24  call    cs:__imp_CryptExportKey
0x180007b2b  nop     dword ptr [rax+rax+00h]
0x180007b30  test    eax, eax
0x180007b32  jz      loc_180007A24
0x180007b38  mov     rcx, [rsp+1200h+phProv]; hProv
0x180007b3d  lea     r8, [rbp+1100h+pbBuffer]; pbBuffer
0x180007b41  mov     edx, 10h; dwLen
0x180007b46  call    cs:__imp_CryptGenRandom
0x180007b4d  nop     dword ptr [rax+rax+00h]
0x180007b52  test    eax, eax
0x180007b54  jz      loc_180007A24
0x180007b5a  mov     rcx, [rsp+1200h+phProv]; hProv
0x180007b5f  lea     r8, [rsp+1200h+var_11CC]; pbBuffer
0x180007b64  mov     ebx, 4
0x180007b69  mov     edx, ebx; dwLen
0x180007b6b  call    cs:__imp_CryptGenRandom
0x180007b72  nop     dword ptr [rax+rax+00h]
0x180007b77  test    eax, eax
0x180007b79  jz      loc_180007A24
0x180007b7f  mov     rcx, [rsp+1200h+phProv]; hProv
0x180007b84  lea     r8, [rsp+1200h+var_11BC]; pbBuffer
0x180007b89  mov     edx, ebx; dwLen
0x180007b8b  call    cs:__imp_CryptGenRandom
0x180007b92  nop     dword ptr [rax+rax+00h]
0x180007b97  test    eax, eax
0x180007b99  jz      loc_180007A24
0x180007b9f  xor     r9d, r9d; dwFlags
0x180007ba2  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180007ba9  lea     rdx, pszAlgId; "RSA"
0x180007bb0  lea     rcx, [rsp+1200h+phAlgorithm]; phAlgorithm
0x180007bb5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180007bbc  nop     dword ptr [rax+rax+00h]
0x180007bc1  mov     ebx, eax
0x180007bc3  test    eax, eax
0x180007bc5  js      loc_180007C9B
0x180007bcb  mov     rcx, [rsp+1200h+phAlgorithm]; hAlgorithm
0x180007bd0  lea     r8, [rsp+1200h+hKey]
0x180007bd5  mov     rdx, rsi
0x180007bd8  call    importRsaPublicKey
0x180007bdd  mov     ebx, eax
0x180007bdf  test    eax, eax
0x180007be1  js      loc_180007C9B
0x180007be7  mov     eax, dword ptr [rsp+1200h+var_11CC]
0x180007beb  lea     r9, [rsp+1200h+pv]
0x180007bf0  movups  xmm0, [rbp+1100h+var_1160]
0x180007bf4  lea     r8, [rsp+1200h+var_11B8]
0x180007bf9  mov     [rbp+1100h+var_1130], eax
0x180007bfc  movaps  xmm1, xmmword ptr [rbp+1100h+pbBuffer]
0x180007c00  lea     rcx, [rbp+1100h+pbInput]; pbInput
0x180007c04  mov     eax, dword ptr [rsp+1200h+var_11BC]
0x180007c08  mov     [rbp+1100h+var_112C], eax
0x180007c0b  lea     rax, [rsp+1200h+hKey]
0x180007c10  mov     qword ptr [rsp+1200h+cbSignedBlob], rax; __int64
0x180007c15  movdqu  xmmword ptr [rbp+1100h+pbInput], xmm0
0x180007c1a  movdqu  [rbp+1100h+var_1140], xmm1
0x180007c1f  call    encryptSignatureUsingRSAWithSHA2
0x180007c24  mov     ebx, eax
0x180007c26  test    eax, eax
0x180007c28  js      short loc_180007C9B
0x180007c2a  cmp     [rsp+1200h+var_11B8], 100h
0x180007c32  jb      loc_180007AFE
0x180007c38  mov     rax, [r14]
0x180007c3b  mov     rcx, r14
0x180007c3e  mov     rdx, [rsp+1200h+pv]
0x180007c43  mov     rax, [rax+20h]
0x180007c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4c  mov     ebx, eax
0x180007c4e  test    eax, eax
0x180007c50  js      short loc_180007C9B
0x180007c52  movups  xmm0, xmmword ptr cs:OPM_GET_CONNECTOR_TYPE.Data1
0x180007c59  mov     eax, dword ptr [rsp+1200h+var_11CC]
0x180007c5d  lea     r9, [rsp+1200h+var_11B4]
0x180007c62  mov     r8, r14
0x180007c65  mov     [rbp+1100h+var_1020], eax
0x180007c6b  movdqu  [rbp+1100h+var_1030], xmm0
0x180007c73  lea     rdx, [rbp+1100h+var_1180]
0x180007c77  movaps  xmm0, xmmword ptr [rbp+1100h+pbBuffer]
0x180007c7b  lea     rcx, [rbp+1100h+var_1050]
0x180007c82  movdqa  [rbp+1100h+var_1180], xmm0
0x180007c87  call    sendAndVerifyOPMRequest
0x180007c8c  mov     ebx, eax
0x180007c8e  test    eax, eax
0x180007c90  js      short loc_180007C9B
0x180007c92  movzx   eax, word ptr [rsp+1200h+var_11B4]
0x180007c97  mov     [r12], eax
0x180007c9b  xor     edx, edx; dwFlags
0x180007c9d  mov     rcx, rdi; hCertStore
0x180007ca0  call    cs:__imp_CertCloseStore
0x180007ca7  nop     dword ptr [rax+rax+00h]
0x180007cac  mov     rcx, [rsp+1200h+hKey]; hKey
0x180007cb1  test    rcx, rcx
0x180007cb4  jz      short loc_180007CC2
0x180007cb6  call    cs:__imp_BCryptDestroyKey
0x180007cbd  nop     dword ptr [rax+rax+00h]
0x180007cc2  mov     rcx, [rsp+1200h+phAlgorithm]; hAlgorithm
0x180007cc7  test    rcx, rcx
0x180007cca  jz      short loc_180007CDA
0x180007ccc  xor     edx, edx; dwFlags
0x180007cce  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180007cd5  nop     dword ptr [rax+rax+00h]
0x180007cda  mov     rcx, [rsp+1200h+phProv]; hProv
0x180007cdf  test    rcx, rcx
0x180007ce2  jz      short loc_180007CF2
0x180007ce4  xor     edx, edx; dwFlags
0x180007ce6  call    cs:__imp_CryptReleaseContext
0x180007ced  nop     dword ptr [rax+rax+00h]
0x180007cf2  test    r15, r15
0x180007cf5  jz      short loc_180007D06
0x180007cf7  mov     rcx, r15; pCertContext
0x180007cfa  call    cs:__imp_CertFreeCertificateContext
0x180007d01  nop     dword ptr [rax+rax+00h]
0x180007d06  mov     rcx, [rsp+1200h+phKey]; hKey
0x180007d0b  test    rcx, rcx
0x180007d0e  jz      short loc_180007D1C
0x180007d10  call    cs:__imp_CryptDestroyKey
0x180007d17  nop     dword ptr [rax+rax+00h]
0x180007d1c  mov     rcx, [rsp+1200h+pbSignedBlob]; pv
0x180007d21  call    cs:__imp_CoTaskMemFree
0x180007d28  nop     dword ptr [rax+rax+00h]
0x180007d2d  mov     rcx, rsi; pv
0x180007d30  call    cs:__imp_CoTaskMemFree
0x180007d37  nop     dword ptr [rax+rax+00h]
0x180007d3c  mov     rcx, [rsp+1200h+pv]; pv
0x180007d41  call    cs:__imp_CoTaskMemFree
0x180007d48  nop     dword ptr [rax+rax+00h]
0x180007d4d  mov     eax, ebx
0x180007d4f  mov     rcx, [rbp+1100h+var_40]
0x180007d56  xor     rcx, rsp; StackCookie
0x180007d59  call    __security_check_cookie
0x180007d5e  mov     rbx, [rsp+1200h+arg_10]
0x180007d66  add     rsp, 11D0h
0x180007d6d  pop     r15
0x180007d6f  pop     r14
0x180007d71  pop     r13
0x180007d73  pop     r12
0x180007d75  pop     rdi
0x180007d76  pop     rsi
0x180007d77  pop     rbp
0x180007d78  retn
```
