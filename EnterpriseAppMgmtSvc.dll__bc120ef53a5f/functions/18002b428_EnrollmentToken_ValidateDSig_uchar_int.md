# EnrollmentToken::ValidateDSig(uchar *,int)

- ea: `0x18002b428`
- end: `0x18002b8b8`
- name: `?ValidateDSig@EnrollmentToken@@AEAAJPEAEH@Z`
- size: `1168`
- prototype: `__int64 __fastcall(EnrollmentToken *__hidden this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b2a4`

## callees

- `0x180006ac0`
- `0x18002b088`
- `0x18002b428`
- `0x180069a30`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b692`
- `CRYPT32!CertFreeCertificateChain` at `0x18002b871`
- `CRYPT32!CertFreeCertificateChain` at `0x18002b871`
- `CRYPT32!CertFreeCertificateContext` at `0x18002b85c`
- `CRYPT32!CertFreeCertificateContext` at `0x18002b85c`
- `CRYPT32!CertCloseStore` at `0x18002b82c`
- `CRYPT32!CertCloseStore` at `0x18002b82c`
- `CRYPT32!CertGetCertificateChain` at `0x18002b682`
- `CRYPT32!CertGetCertificateChain` at `0x18002b682`
- `CRYPT32!CertCreateCertificateContext` at `0x18002b5a4`
- `CRYPT32!CertCreateCertificateContext` at `0x18002b5a4`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18002b608`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18002b608`
- `bcrypt!BCryptDestroyKey` at `0x18002b848`
- `bcrypt!BCryptDestroyKey` at `0x18002b848`
- `CRYPTXML!CryptXmlClose` at `0x18002b886`
- `CRYPTXML!CryptXmlClose` at `0x18002b886`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18002b713`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18002b713`
- `CRYPTXML!CryptXmlGetDocContext` at `0x18002b4d0`
- `CRYPTXML!CryptXmlGetDocContext` at `0x18002b4d0`
- `CRYPTXML!CryptXmlGetReference` at `0x18002b76f`
- `CRYPTXML!CryptXmlGetReference` at `0x18002b76f`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18002b4b2`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18002b4b2`
- `CRYPTXML!CryptXmlGetStatus` at `0x18002b7ca`
- `CRYPTXML!CryptXmlGetStatus` at `0x18002b7ca`
- `CRYPTXML!CryptXmlGetSignature` at `0x18002b73c`
- `CRYPTXML!CryptXmlGetSignature` at `0x18002b73c`

## string_xrefs

- `0x18002b6ba`: `EnrollmentToken::ValidateDSig CertGetCertificateChain failed`
- `0x18002b804`: `EnrollmentToken::ValidateDSig CryptXmlGetStatus not resolved`
- `0x18002b7ed`: `EnrollmentToken::ValidateDSig CryptXmlGetStatus is invalid`
- `0x18002b7ae`: `EnrollmentToken::ValidateDSig Reference URI was not an empty string`

## pseudocode

```c
__int64 __fastcall EnrollmentToken::ValidateDSig(EnrollmentToken *this, unsigned __int8 *a2, ULONG a3)
{
  const CERT_CONTEXT *v4; // rdi
  int DocContext; // ebx
  CRYPT_XML_KEY_INFO *pKeyInfo; // rcx
  CRYPT_XML_KEY_INFO_ITEM *rgKeyInfo; // rcx
  CRYPT_XML_KEY_INFO_ITEM *v8; // rdx
  LPCWSTR wszNamedCurve; // r9
  const WCHAR *v10; // r11
  const WCHAR *v11; // rsi
  unsigned int i; // ecx
  LPCWSTR v13; // rdx
  PCCERT_CONTEXT CertificateContext; // rax
  unsigned __int16 **v15; // r8
  EnrollmentToken *v16; // rcx
  signed int LastError; // eax
  HCERTSTORE v18; // rsi
  signed int v19; // eax
  LPCWSTR wszUri; // rcx
  __int64 v21; // r9
  const wchar_t *v22; // r8
  PCERT_SIMPLE_CHAIN v23; // rcx
  PCERT_CHAIN_ELEMENT *rgpElement; // rcx
  __int64 v25; // rax
  CRYPT_XML_DOC_CTXT *ppStruct; // [rsp+40h] [rbp-49h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-41h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+50h] [rbp-39h] BYREF
  HCRYPTXML hCryptXml; // [rsp+58h] [rbp-31h] BYREF
  HCERTSTORE hAdditionalStore; // [rsp+60h] [rbp-29h] BYREF
  CRYPT_XML_SIGNATURE *v32; // [rsp+68h] [rbp-21h] BYREF
  CRYPT_XML_REFERENCE *v33; // [rsp+70h] [rbp-19h] BYREF
  CRYPT_XML_BLOB pEncoded; // [rsp+78h] [rbp-11h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+88h] [rbp-1h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+A8h] [rbp+1Fh] BYREF

  hCryptXml = 0;
  ppStruct = 0;
  v4 = 0;
  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  hAdditionalStore = 0;
  v32 = 0;
  v33 = 0;
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  phKey = 0;
  pEncoded.dwCharset = CRYPT_XML_CHARSET_AUTO;
  pEncoded.cbData = a3;
  pEncoded.pbData = a2;
  DocContext = CryptXmlOpenToDecode(0, 0x10000000u, 0, 0, &pEncoded, &hCryptXml);
  if ( DocContext < 0 )
    goto LABEL_55;
  DocContext = CryptXmlGetDocContext(hCryptXml, (const CRYPT_XML_DOC_CTXT **)&ppStruct);
  if ( DocContext < 0 )
    goto LABEL_55;
  if ( ppStruct->cSignature != 1 )
    goto LABEL_54;
  pKeyInfo = (*ppStruct->rgpSignature)->pKeyInfo;
  if ( !pKeyInfo || pKeyInfo->cKeyInfo != 2 )
    goto LABEL_54;
  rgKeyInfo = pKeyInfo->rgKeyInfo;
  v8 = rgKeyInfo + 1;
  if ( rgKeyInfo->KeyValue.dwType != 2 )
    v8 = rgKeyInfo++;
  if ( rgKeyInfo->dwType != 4 || v8->dwType != 4 || v8->KeyValue.dwType != 1 || rgKeyInfo->KeyValue.dwType != 2 )
    goto LABEL_54;
  wszNamedCurve = rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve;
  v10 = wszNamedCurve;
  v11 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( *(_DWORD *)&wszNamedCurve[12 * i] == 4 )
    {
      v11 = &v10[12 * i];
      wszNamedCurve = v10;
    }
  }
  if ( !v11
    || (v13 = v8->KeyValue.ECDSAKeyValue.wszNamedCurve, *(_DWORD *)v13 != 4)
    || (CertificateContext = CertCreateCertificateContext(1u, *((const BYTE **)v13 + 2), *((_DWORD *)v13 + 2)),
        (v4 = CertificateContext) == 0) )
  {
LABEL_54:
    DocContext = -2147467259;
    goto LABEL_55;
  }
  *(FILETIME *)((char *)this + 20) = CertificateContext->pCertInfo->NotBefore;
  *(FILETIME *)((char *)this + 28) = CertificateContext->pCertInfo->NotAfter;
  DocContext = DevPlat::Shared::GetEnterpriseNameFromCertificate(
                 CertificateContext,
                 (const struct _CERT_CONTEXT *)this + 1,
                 v15);
  if ( DocContext < 0 )
    goto LABEL_55;
  if ( !CryptImportPublicKeyInfoEx2(1u, &v4->pCertInfo->SubjectPublicKeyInfo, 0x80000000, 0, &phKey) )
  {
    LastError = GetLastError();
    DocContext = LastError;
    if ( LastError > 0 )
      DocContext = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_55;
  }
  DocContext = EnrollmentToken::GenerateAETCertsStore(
                 v16,
                 &hAdditionalStore,
                 *((const unsigned __int8 **)v11 + 2),
                 *((_DWORD *)v11 + 2));
  v18 = hAdditionalStore;
  if ( DocContext >= 0 )
  {
    if ( !CertGetCertificateChain(0, v4, 0, hAdditionalStore, &pChainPara, 0, 0, &pChainContext) )
    {
      v19 = GetLastError();
      if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
      {
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        v21 = (unsigned int)v19;
        v22 = L"EnrollmentToken::ValidateDSig CertGetCertificateChain failed";
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    v23 = *pChainContext->rgpChain;
    if ( v23->cElement != 3 )
      goto LABEL_51;
    rgpElement = v23->rgpElement;
    if ( (*rgpElement)->TrustStatus.dwErrorStatus || rgpElement[1]->TrustStatus.dwErrorStatus )
      goto LABEL_51;
    DocContext = CryptXmlVerifySignature((*ppStruct->rgpSignature)->hSignature, phKey, 0x10000000u);
    if ( DocContext >= 0 )
    {
      DocContext = CryptXmlGetSignature((*ppStruct->rgpSignature)->hSignature, (const CRYPT_XML_SIGNATURE **)&v32);
      if ( DocContext >= 0 )
      {
        if ( v32->SignedInfo.cReference == 1 )
        {
          DocContext = CryptXmlGetReference(
                         (*v32->SignedInfo.rgpReference)->hReference,
                         (const CRYPT_XML_REFERENCE **)&v33);
          if ( DocContext < 0 )
            goto LABEL_52;
          wszUri = v33->wszUri;
          if ( !wszUri )
            goto LABEL_42;
          v25 = -1;
          do
            ++v25;
          while ( wszUri[v25] );
          if ( v25 )
          {
            if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
              goto LABEL_51;
            v22 = L"EnrollmentToken::ValidateDSig Reference URI was not an empty string";
          }
          else
          {
LABEL_42:
            DocContext = CryptXmlGetStatus((*ppStruct->rgpSignature)->hSignature, &pStatus);
            if ( DocContext < 0 )
              goto LABEL_52;
            wszUri = (LPCWSTR)pStatus.dwErrorStatus;
            if ( (pStatus.dwErrorStatus & 2) != 0 )
            {
              if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
                goto LABEL_51;
              v22 = L"EnrollmentToken::ValidateDSig CryptXmlGetStatus is invalid";
            }
            else
            {
              if ( (pStatus.dwErrorStatus & 1) == 0 )
                goto LABEL_52;
              if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
                goto LABEL_51;
              v22 = L"EnrollmentToken::ValidateDSig CryptXmlGetStatus not resolved";
            }
          }
          v21 = 2147500037LL;
LABEL_50:
          McTemplateU0zq_EventWriteTransfer(wszUri, EnterpriseAppMgmtSvcError, v22, v21);
        }
LABEL_51:
        DocContext = -2147467259;
      }
    }
  }
LABEL_52:
  if ( v18 )
    CertCloseStore(v18, 0);
LABEL_55:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( hCryptXml )
    CryptXmlClose(hCryptXml);
  return (unsigned int)DocContext;
}

```

## disassembly

```asm
0x18002b428  mov     [rsp-8+arg_18], rbx
0x18002b42d  push    rbp
0x18002b42e  push    rsi
0x18002b42f  push    rdi
0x18002b430  push    r14
0x18002b432  push    r15
0x18002b434  lea     rbp, [rsp-37h]
0x18002b439  sub     rsp, 0C0h
0x18002b440  mov     rax, cs:__security_cookie
0x18002b447  xor     rax, rsp
0x18002b44a  mov     [rbp+57h+var_28], rax
0x18002b44e  mov     r14, rcx
0x18002b451  xor     r15d, r15d
0x18002b454  mov     [rbp+57h+hCryptXml], r15
0x18002b458  mov     [rbp+57h+ppStruct], r15
0x18002b45c  mov     edi, r15d
0x18002b45f  mov     [rbp+57h+pChainContext], r15
0x18002b463  xorps   xmm0, xmm0
0x18002b466  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x18002b46a  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18002b46e  mov     [rbp+57h+hAdditionalStore], r15
0x18002b472  mov     [rbp+57h+var_78], r15
0x18002b476  mov     [rbp+57h+var_70], r15
0x18002b47a  xor     eax, eax
0x18002b47c  mov     qword ptr [rbp+57h+pStatus.cbSize], rax
0x18002b480  mov     [rbp+57h+pStatus.dwInfoStatus], eax
0x18002b483  mov     [rbp+57h+phKey], r15
0x18002b487  mov     [rbp+57h+var_68.dwCharset], r15d
0x18002b48b  mov     [rbp+57h+var_68.cbData], r8d
0x18002b48f  mov     [rbp+57h+var_68.pbData], rdx
0x18002b493  lea     rax, [rbp+57h+hCryptXml]
0x18002b497  mov     [rsp+0E0h+phCryptXml], rax; phCryptXml
0x18002b49c  lea     rax, [rbp+57h+var_68]
0x18002b4a0  mov     [rsp+0E0h+pEncoded], rax; pEncoded
0x18002b4a5  xor     r9d, r9d; cProperty
0x18002b4a8  xor     r8d, r8d; rgProperty
0x18002b4ab  mov     edx, 10000000h; dwFlags
0x18002b4b0  xor     ecx, ecx; pConfig
0x18002b4b2  call    cs:__imp_CryptXmlOpenToDecode
0x18002b4b9  nop     dword ptr [rax+rax+00h]
0x18002b4be  mov     ebx, eax
0x18002b4c0  test    eax, eax
0x18002b4c2  js      loc_18002B83F
0x18002b4c8  lea     rdx, [rbp+57h+ppStruct]; ppStruct
0x18002b4cc  mov     rcx, [rbp+57h+hCryptXml]; hCryptXml
0x18002b4d0  call    cs:__imp_CryptXmlGetDocContext
0x18002b4d7  nop     dword ptr [rax+rax+00h]
0x18002b4dc  mov     ebx, eax
0x18002b4de  test    eax, eax
0x18002b4e0  js      loc_18002B83F
0x18002b4e6  mov     rax, [rbp+57h+ppStruct]
0x18002b4ea  cmp     dword ptr [rax+18h], 1
0x18002b4ee  jnz     loc_18002B83A
0x18002b4f4  mov     rax, [rax+20h]
0x18002b4f8  mov     rcx, [rax]
0x18002b4fb  mov     rcx, [rcx+98h]
0x18002b502  test    rcx, rcx
0x18002b505  jz      loc_18002B83A
0x18002b50b  cmp     dword ptr [rcx+10h], 2
0x18002b50f  jnz     loc_18002B83A
0x18002b515  mov     rcx, [rcx+18h]
0x18002b519  lea     rax, [rcx+80h]
0x18002b520  mov     rdx, rax
0x18002b523  cmp     dword ptr [rcx+8], 2
0x18002b527  cmovnz  rdx, rcx
0x18002b52b  cmovnz  rcx, rax
0x18002b52f  cmp     dword ptr [rcx], 4
0x18002b532  jnz     loc_18002B83A
0x18002b538  cmp     dword ptr [rdx], 4
0x18002b53b  jnz     loc_18002B83A
0x18002b541  cmp     dword ptr [rdx+8], 1
0x18002b545  jnz     loc_18002B83A
0x18002b54b  mov     r8d, [rcx+8]
0x18002b54f  cmp     r8d, 2
0x18002b553  jnz     loc_18002B83A
0x18002b559  mov     r9, [rcx+10h]
0x18002b55d  mov     r11, r9
0x18002b560  mov     esi, r15d
0x18002b563  mov     ecx, r15d
0x18002b566  mov     eax, ecx
0x18002b568  lea     r10, [rax+rax*2]
0x18002b56c  cmp     dword ptr [r9+r10*8], 4
0x18002b571  jnz     short loc_18002B57A
0x18002b573  lea     rsi, [r11+r10*8]
0x18002b577  mov     r9, r11
0x18002b57a  inc     ecx
0x18002b57c  cmp     ecx, r8d
0x18002b57f  jb      short loc_18002B566
0x18002b581  test    rsi, rsi
0x18002b584  jz      loc_18002B83A
0x18002b58a  mov     rdx, [rdx+10h]
0x18002b58e  cmp     dword ptr [rdx], 4
0x18002b591  jnz     loc_18002B83A
0x18002b597  mov     r8d, [rdx+8]; cbCertEncoded
0x18002b59b  mov     rdx, [rdx+10h]; pbCertEncoded
0x18002b59f  mov     ecx, 1; dwCertEncodingType
0x18002b5a4  call    cs:__imp_CertCreateCertificateContext
0x18002b5ab  nop     dword ptr [rax+rax+00h]
0x18002b5b0  mov     rdi, rax
0x18002b5b3  test    rax, rax
0x18002b5b6  jz      loc_18002B83A
0x18002b5bc  mov     rax, [rax+18h]
0x18002b5c0  mov     rcx, [rax+40h]
0x18002b5c4  mov     [r14+14h], rcx
0x18002b5c8  mov     rax, [rdi+18h]
0x18002b5cc  mov     rcx, [rax+48h]
0x18002b5d0  mov     [r14+1Ch], rcx
0x18002b5d4  lea     rdx, [r14+28h]; struct _CERT_CONTEXT *
0x18002b5d8  mov     rcx, rdi; pCertContext
0x18002b5db  call    ?GetEnterpriseNameFromCertificate@Shared@DevPlat@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; DevPlat::Shared::GetEnterpriseNameFromCertificate(_CERT_CONTEXT const *,ushort * *)
0x18002b5e0  mov     ebx, eax
0x18002b5e2  test    eax, eax
0x18002b5e4  js      loc_18002B83F
0x18002b5ea  mov     rdx, [rdi+18h]
0x18002b5ee  add     rdx, 60h ; '`'; pInfo
0x18002b5f2  lea     rax, [rbp+57h+phKey]
0x18002b5f6  mov     [rsp+0E0h+pEncoded], rax; phKey
0x18002b5fb  xor     r9d, r9d; pvAuxInfo
0x18002b5fe  lea     ecx, [r9+1]; dwCertEncodingType
0x18002b602  mov     r8d, 80000000h; dwFlags
0x18002b608  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18002b60f  nop     dword ptr [rax+rax+00h]
0x18002b614  test    eax, eax
0x18002b616  jnz     short loc_18002B63C
0x18002b618  call    cs:__imp_GetLastError
0x18002b61f  nop     dword ptr [rax+rax+00h]
0x18002b624  mov     ebx, eax
0x18002b626  test    eax, eax
0x18002b628  jle     loc_18002B83F
0x18002b62e  movzx   ebx, ax
0x18002b631  or      ebx, 80070000h
0x18002b637  jmp     loc_18002B83F
0x18002b63c  mov     r9d, [rsi+8]; unsigned int
0x18002b640  mov     r8, [rsi+10h]; unsigned __int8 *
0x18002b644  lea     rdx, [rbp+57h+hAdditionalStore]; void **
0x18002b648  call    ?GenerateAETCertsStore@EnrollmentToken@@AEAAJPEAPEAXPEBEK@Z; EnrollmentToken::GenerateAETCertsStore(void * *,uchar const *,ulong)
0x18002b64d  mov     ebx, eax
0x18002b64f  mov     rsi, [rbp+57h+hAdditionalStore]
0x18002b653  test    eax, eax
0x18002b655  js      loc_18002B822
0x18002b65b  lea     rax, [rbp+57h+pChainContext]
0x18002b65f  mov     [rsp+0E0h+ppChainContext], rax; ppChainContext
0x18002b664  mov     [rsp+0E0h+pvReserved], r15; pvReserved
0x18002b669  mov     dword ptr [rsp+0E0h+phCryptXml], r15d; dwFlags
0x18002b66e  lea     rax, [rbp+57h+pChainPara]
0x18002b672  mov     [rsp+0E0h+pEncoded], rax; pChainPara
0x18002b677  mov     r9, rsi; hAdditionalStore
0x18002b67a  xor     r8d, r8d; pTime
0x18002b67d  mov     rdx, rdi; pCertContext
0x18002b680  xor     ecx, ecx; hChainEngine
0x18002b682  call    cs:__imp_CertGetCertificateChain
0x18002b689  nop     dword ptr [rax+rax+00h]
0x18002b68e  test    eax, eax
0x18002b690  jnz     short loc_18002B6C6
0x18002b692  call    cs:__imp_GetLastError
0x18002b699  nop     dword ptr [rax+rax+00h]
0x18002b69e  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b6a5  jz      loc_18002B81D
0x18002b6ab  test    eax, eax
0x18002b6ad  jle     short loc_18002B6B7
0x18002b6af  movzx   eax, ax
0x18002b6b2  or      eax, 80070000h
0x18002b6b7  mov     r9d, eax
0x18002b6ba  lea     r8, aEnrollmenttoke_6; "EnrollmentToken::ValidateDSig CertGetCe"...
0x18002b6c1  jmp     loc_18002B811
0x18002b6c6  mov     rax, [rbp+57h+pChainContext]
0x18002b6ca  mov     rcx, [rax+10h]
0x18002b6ce  mov     rcx, [rcx]
0x18002b6d1  cmp     dword ptr [rcx+0Ch], 3
0x18002b6d5  jnz     loc_18002B81D
0x18002b6db  mov     rcx, [rcx+10h]
0x18002b6df  mov     rax, [rcx]
0x18002b6e2  cmp     [rax+10h], r15d
0x18002b6e6  jnz     loc_18002B81D
0x18002b6ec  mov     rax, [rcx+8]
0x18002b6f0  cmp     [rax+10h], r15d
0x18002b6f4  jnz     loc_18002B81D
0x18002b6fa  mov     rax, [rbp+57h+ppStruct]
0x18002b6fe  mov     rcx, [rax+20h]
0x18002b702  mov     rcx, [rcx]
0x18002b705  mov     r8d, 10000000h; dwFlags
0x18002b70b  mov     rdx, [rbp+57h+phKey]; hKey
0x18002b70f  mov     rcx, [rcx+8]; hSignature
0x18002b713  call    cs:__imp_CryptXmlVerifySignature
0x18002b71a  nop     dword ptr [rax+rax+00h]
0x18002b71f  mov     ebx, eax
0x18002b721  test    eax, eax
0x18002b723  js      loc_18002B822
0x18002b729  mov     rax, [rbp+57h+ppStruct]
0x18002b72d  mov     rcx, [rax+20h]
0x18002b731  mov     rcx, [rcx]
0x18002b734  lea     rdx, [rbp+57h+var_78]; ppStruct
0x18002b738  mov     rcx, [rcx+8]; hCryptXml
0x18002b73c  call    cs:__imp_CryptXmlGetSignature
0x18002b743  nop     dword ptr [rax+rax+00h]
0x18002b748  mov     ebx, eax
0x18002b74a  test    eax, eax
0x18002b74c  js      loc_18002B822
0x18002b752  mov     rax, [rbp+57h+var_78]
0x18002b756  cmp     dword ptr [rax+68h], 1
0x18002b75a  jnz     loc_18002B81D
0x18002b760  mov     rax, [rax+70h]
0x18002b764  mov     rcx, [rax]
0x18002b767  lea     rdx, [rbp+57h+var_70]; ppStruct
0x18002b76b  mov     rcx, [rcx+8]; hCryptXml
0x18002b76f  call    cs:__imp_CryptXmlGetReference
0x18002b776  nop     dword ptr [rax+rax+00h]
0x18002b77b  mov     ebx, eax
0x18002b77d  test    eax, eax
0x18002b77f  js      loc_18002B822
0x18002b785  mov     rax, [rbp+57h+var_70]
0x18002b789  mov     rcx, [rax+18h]
0x18002b78d  test    rcx, rcx
0x18002b790  jz      short loc_18002B7B7
0x18002b792  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b796  inc     rax
0x18002b799  cmp     [rcx+rax*2], r15w
0x18002b79e  jnz     short loc_18002B796
0x18002b7a0  test    rax, rax
0x18002b7a3  jz      short loc_18002B7B7
0x18002b7a5  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b7ac  jz      short loc_18002B81D
0x18002b7ae  lea     r8, aEnrollmenttoke_7; "EnrollmentToken::ValidateDSig Reference"...
0x18002b7b5  jmp     short loc_18002B80B
0x18002b7b7  mov     rax, [rbp+57h+ppStruct]
0x18002b7bb  mov     rcx, [rax+20h]
0x18002b7bf  mov     rcx, [rcx]
0x18002b7c2  lea     rdx, [rbp+57h+pStatus]; pStatus
0x18002b7c6  mov     rcx, [rcx+8]; hCryptXml
0x18002b7ca  call    cs:__imp_CryptXmlGetStatus
0x18002b7d1  nop     dword ptr [rax+rax+00h]
0x18002b7d6  mov     ebx, eax
0x18002b7d8  test    eax, eax
0x18002b7da  js      short loc_18002B822
0x18002b7dc  mov     ecx, [rbp+57h+pStatus.dwErrorStatus]
0x18002b7df  test    cl, 2
0x18002b7e2  jz      short loc_18002B7F6
0x18002b7e4  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b7eb  jz      short loc_18002B81D
0x18002b7ed  lea     r8, aEnrollmenttoke_2; "EnrollmentToken::ValidateDSig CryptXmlG"...
0x18002b7f4  jmp     short loc_18002B80B
0x18002b7f6  test    cl, 1
0x18002b7f9  jz      short loc_18002B822
0x18002b7fb  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b802  jz      short loc_18002B81D
0x18002b804  lea     r8, aEnrollmenttoke_1; "EnrollmentToken::ValidateDSig CryptXmlG"...
0x18002b80b  mov     r9d, 80004005h
0x18002b811  lea     rdx, EnterpriseAppMgmtSvcError
0x18002b818  call    McTemplateU0zq_EventWriteTransfer
0x18002b81d  mov     ebx, 80004005h
0x18002b822  test    rsi, rsi
0x18002b825  jz      short loc_18002B83F
0x18002b827  xor     edx, edx; dwFlags
0x18002b829  mov     rcx, rsi; hCertStore
0x18002b82c  call    cs:__imp_CertCloseStore
0x18002b833  nop     dword ptr [rax+rax+00h]
0x18002b838  jmp     short loc_18002B83F
0x18002b83a  mov     ebx, 80004005h
0x18002b83f  mov     rcx, [rbp+57h+phKey]; hKey
0x18002b843  test    rcx, rcx
0x18002b846  jz      short loc_18002B854
0x18002b848  call    cs:__imp_BCryptDestroyKey
0x18002b84f  nop     dword ptr [rax+rax+00h]
0x18002b854  test    rdi, rdi
0x18002b857  jz      short loc_18002B868
0x18002b859  mov     rcx, rdi; pCertContext
0x18002b85c  call    cs:__imp_CertFreeCertificateContext
0x18002b863  nop     dword ptr [rax+rax+00h]
0x18002b868  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x18002b86c  test    rcx, rcx
0x18002b86f  jz      short loc_18002B87D
0x18002b871  call    cs:__imp_CertFreeCertificateChain
0x18002b878  nop     dword ptr [rax+rax+00h]
0x18002b87d  mov     rcx, [rbp+57h+hCryptXml]; hCryptXml
0x18002b881  test    rcx, rcx
0x18002b884  jz      short loc_18002B892
0x18002b886  call    cs:__imp_CryptXmlClose
0x18002b88d  nop     dword ptr [rax+rax+00h]
0x18002b892  mov     eax, ebx
0x18002b894  mov     rcx, [rbp+57h+var_28]
0x18002b898  xor     rcx, rsp; StackCookie
0x18002b89b  call    __security_check_cookie
0x18002b8a0  mov     rbx, [rsp+0E0h+arg_18]
0x18002b8a8  add     rsp, 0C0h
0x18002b8af  pop     r15
0x18002b8b1  pop     r14
0x18002b8b3  pop     rdi
0x18002b8b4  pop     rsi
0x18002b8b5  pop     rbp
0x18002b8b6  retn
```
