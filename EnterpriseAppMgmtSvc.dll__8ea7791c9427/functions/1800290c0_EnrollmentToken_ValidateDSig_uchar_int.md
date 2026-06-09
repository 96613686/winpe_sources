# EnrollmentToken::ValidateDSig(uchar *,int)

- ea: `0x1800290c0`
- end: `0x1800294ef`
- name: `?ValidateDSig@EnrollmentToken@@AEAAJPEAEH@Z`
- size: `1071`
- prototype: `__int64 __fastcall(EnrollmentToken *__hidden this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028f54`

## callees

- `0x180006858`
- `0x180028d6c`
- `0x1800290c0`
- `0x1800641b4`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029306`
- `CRYPT32!CertFreeCertificateChain` at `0x1800294b5`
- `CRYPT32!CertFreeCertificateChain` at `0x1800294b5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800294a6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800294a6`
- `CRYPT32!CertCloseStore` at `0x180029482`
- `CRYPT32!CertCloseStore` at `0x180029482`
- `CRYPT32!CertGetCertificateChain` at `0x1800292fc`
- `CRYPT32!CertGetCertificateChain` at `0x1800292fc`
- `CRYPT32!CertCreateCertificateContext` at `0x180029230`
- `CRYPT32!CertCreateCertificateContext` at `0x180029230`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18002928e`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18002928e`
- `bcrypt!BCryptDestroyKey` at `0x180029498`
- `bcrypt!BCryptDestroyKey` at `0x180029498`
- `CRYPTXML!CryptXmlClose` at `0x1800294c4`
- `CRYPTXML!CryptXmlClose` at `0x1800294c4`
- `CRYPTXML!CryptXmlVerifySignature` at `0x180029381`
- `CRYPTXML!CryptXmlVerifySignature` at `0x180029381`
- `CRYPTXML!CryptXmlGetDocContext` at `0x180029162`
- `CRYPTXML!CryptXmlGetDocContext` at `0x180029162`
- `CRYPTXML!CryptXmlGetReference` at `0x1800293d1`
- `CRYPTXML!CryptXmlGetReference` at `0x1800293d1`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18002914a`
- `CRYPTXML!CryptXmlOpenToDecode` at `0x18002914a`
- `CRYPTXML!CryptXmlGetStatus` at `0x180029426`
- `CRYPTXML!CryptXmlGetStatus` at `0x180029426`
- `CRYPTXML!CryptXmlGetSignature` at `0x1800293a4`
- `CRYPTXML!CryptXmlGetSignature` at `0x1800293a4`

## string_xrefs

- `0x18002945a`: `EnrollmentToken::ValidateDSig CryptXmlGetStatus not resolved`
- `0x180029443`: `EnrollmentToken::ValidateDSig CryptXmlGetStatus is invalid`
- `0x18002940a`: `EnrollmentToken::ValidateDSig Reference URI was not an empty string`
- `0x180029328`: `EnrollmentToken::ValidateDSig CertGetCertificateChain failed`

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
0x1800290c0  mov     [rsp-8+arg_18], rbx
0x1800290c5  push    rbp
0x1800290c6  push    rsi
0x1800290c7  push    rdi
0x1800290c8  push    r14
0x1800290ca  push    r15
0x1800290cc  lea     rbp, [rsp-37h]
0x1800290d1  sub     rsp, 0C0h
0x1800290d8  mov     rax, cs:__security_cookie
0x1800290df  xor     rax, rsp
0x1800290e2  mov     [rbp+57h+var_28], rax
0x1800290e6  mov     r14, rcx
0x1800290e9  xor     r15d, r15d
0x1800290ec  mov     [rbp+57h+hCryptXml], r15
0x1800290f0  mov     [rbp+57h+ppStruct], r15
0x1800290f4  mov     edi, r15d
0x1800290f7  mov     [rbp+57h+pChainContext], r15
0x1800290fb  xorps   xmm0, xmm0
0x1800290fe  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x180029102  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180029106  mov     [rbp+57h+hAdditionalStore], r15
0x18002910a  mov     [rbp+57h+var_78], r15
0x18002910e  mov     [rbp+57h+var_70], r15
0x180029112  xor     eax, eax
0x180029114  mov     qword ptr [rbp+57h+pStatus.cbSize], rax
0x180029118  mov     [rbp+57h+pStatus.dwInfoStatus], eax
0x18002911b  mov     [rbp+57h+phKey], r15
0x18002911f  mov     [rbp+57h+var_68.dwCharset], r15d
0x180029123  mov     [rbp+57h+var_68.cbData], r8d
0x180029127  mov     [rbp+57h+var_68.pbData], rdx
0x18002912b  lea     rax, [rbp+57h+hCryptXml]
0x18002912f  mov     [rsp+0E0h+phCryptXml], rax; phCryptXml
0x180029134  lea     rax, [rbp+57h+var_68]
0x180029138  mov     [rsp+0E0h+pEncoded], rax; pEncoded
0x18002913d  xor     r9d, r9d; cProperty
0x180029140  xor     r8d, r8d; rgProperty
0x180029143  mov     edx, 10000000h; dwFlags
0x180029148  xor     ecx, ecx; pConfig
0x18002914a  call    cs:__imp_CryptXmlOpenToDecode
0x180029150  mov     ebx, eax
0x180029152  test    eax, eax
0x180029154  js      loc_18002948F
0x18002915a  lea     rdx, [rbp+57h+ppStruct]; ppStruct
0x18002915e  mov     rcx, [rbp+57h+hCryptXml]; hCryptXml
0x180029162  call    cs:__imp_CryptXmlGetDocContext
0x180029168  mov     ebx, eax
0x18002916a  test    eax, eax
0x18002916c  js      loc_18002948F
0x180029172  mov     rax, [rbp+57h+ppStruct]
0x180029176  cmp     dword ptr [rax+18h], 1
0x18002917a  jnz     loc_18002948A
0x180029180  mov     rax, [rax+20h]
0x180029184  mov     rcx, [rax]
0x180029187  mov     rcx, [rcx+98h]
0x18002918e  test    rcx, rcx
0x180029191  jz      loc_18002948A
0x180029197  cmp     dword ptr [rcx+10h], 2
0x18002919b  jnz     loc_18002948A
0x1800291a1  mov     rcx, [rcx+18h]
0x1800291a5  lea     rax, [rcx+80h]
0x1800291ac  mov     rdx, rax
0x1800291af  cmp     dword ptr [rcx+8], 2
0x1800291b3  cmovnz  rdx, rcx
0x1800291b7  cmovnz  rcx, rax
0x1800291bb  cmp     dword ptr [rcx], 4
0x1800291be  jnz     loc_18002948A
0x1800291c4  cmp     dword ptr [rdx], 4
0x1800291c7  jnz     loc_18002948A
0x1800291cd  cmp     dword ptr [rdx+8], 1
0x1800291d1  jnz     loc_18002948A
0x1800291d7  mov     r8d, [rcx+8]
0x1800291db  cmp     r8d, 2
0x1800291df  jnz     loc_18002948A
0x1800291e5  mov     r9, [rcx+10h]
0x1800291e9  mov     r11, r9
0x1800291ec  mov     esi, r15d
0x1800291ef  mov     ecx, r15d
0x1800291f2  mov     eax, ecx
0x1800291f4  lea     r10, [rax+rax*2]
0x1800291f8  cmp     dword ptr [r9+r10*8], 4
0x1800291fd  jnz     short loc_180029206
0x1800291ff  lea     rsi, [r11+r10*8]
0x180029203  mov     r9, r11
0x180029206  inc     ecx
0x180029208  cmp     ecx, r8d
0x18002920b  jb      short loc_1800291F2
0x18002920d  test    rsi, rsi
0x180029210  jz      loc_18002948A
0x180029216  mov     rdx, [rdx+10h]
0x18002921a  cmp     dword ptr [rdx], 4
0x18002921d  jnz     loc_18002948A
0x180029223  mov     r8d, [rdx+8]; cbCertEncoded
0x180029227  mov     rdx, [rdx+10h]; pbCertEncoded
0x18002922b  mov     ecx, 1; dwCertEncodingType
0x180029230  call    cs:__imp_CertCreateCertificateContext
0x180029236  mov     rdi, rax
0x180029239  test    rax, rax
0x18002923c  jz      loc_18002948A
0x180029242  mov     rax, [rax+18h]
0x180029246  mov     rcx, [rax+40h]
0x18002924a  mov     [r14+14h], rcx
0x18002924e  mov     rax, [rdi+18h]
0x180029252  mov     rcx, [rax+48h]
0x180029256  mov     [r14+1Ch], rcx
0x18002925a  lea     rdx, [r14+28h]; struct _CERT_CONTEXT *
0x18002925e  mov     rcx, rdi; pCertContext
0x180029261  call    ?GetEnterpriseNameFromCertificate@Shared@DevPlat@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; DevPlat::Shared::GetEnterpriseNameFromCertificate(_CERT_CONTEXT const *,ushort * *)
0x180029266  mov     ebx, eax
0x180029268  test    eax, eax
0x18002926a  js      loc_18002948F
0x180029270  mov     rdx, [rdi+18h]
0x180029274  add     rdx, 60h ; '`'; pInfo
0x180029278  lea     rax, [rbp+57h+phKey]
0x18002927c  mov     [rsp+0E0h+pEncoded], rax; phKey
0x180029281  xor     r9d, r9d; pvAuxInfo
0x180029284  lea     ecx, [r9+1]; dwCertEncodingType
0x180029288  mov     r8d, 80000000h; dwFlags
0x18002928e  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x180029294  test    eax, eax
0x180029296  jnz     short loc_1800292B6
0x180029298  call    cs:__imp_GetLastError
0x18002929e  mov     ebx, eax
0x1800292a0  test    eax, eax
0x1800292a2  jle     loc_18002948F
0x1800292a8  movzx   ebx, ax
0x1800292ab  or      ebx, 80070000h
0x1800292b1  jmp     loc_18002948F
0x1800292b6  mov     r9d, [rsi+8]; unsigned int
0x1800292ba  mov     r8, [rsi+10h]; unsigned __int8 *
0x1800292be  lea     rdx, [rbp+57h+hAdditionalStore]; void **
0x1800292c2  call    ?GenerateAETCertsStore@EnrollmentToken@@AEAAJPEAPEAXPEBEK@Z; EnrollmentToken::GenerateAETCertsStore(void * *,uchar const *,ulong)
0x1800292c7  mov     ebx, eax
0x1800292c9  mov     rsi, [rbp+57h+hAdditionalStore]
0x1800292cd  test    eax, eax
0x1800292cf  js      loc_180029478
0x1800292d5  lea     rax, [rbp+57h+pChainContext]
0x1800292d9  mov     [rsp+0E0h+ppChainContext], rax; ppChainContext
0x1800292de  mov     [rsp+0E0h+pvReserved], r15; pvReserved
0x1800292e3  mov     dword ptr [rsp+0E0h+phCryptXml], r15d; dwFlags
0x1800292e8  lea     rax, [rbp+57h+pChainPara]
0x1800292ec  mov     [rsp+0E0h+pEncoded], rax; pChainPara
0x1800292f1  mov     r9, rsi; hAdditionalStore
0x1800292f4  xor     r8d, r8d; pTime
0x1800292f7  mov     rdx, rdi; pCertContext
0x1800292fa  xor     ecx, ecx; hChainEngine
0x1800292fc  call    cs:__imp_CertGetCertificateChain
0x180029302  test    eax, eax
0x180029304  jnz     short loc_180029334
0x180029306  call    cs:__imp_GetLastError
0x18002930c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180029313  jz      loc_180029473
0x180029319  test    eax, eax
0x18002931b  jle     short loc_180029325
0x18002931d  movzx   eax, ax
0x180029320  or      eax, 80070000h
0x180029325  mov     r9d, eax
0x180029328  lea     r8, aEnrollmenttoke_6; "EnrollmentToken::ValidateDSig CertGetCe"...
0x18002932f  jmp     loc_180029467
0x180029334  mov     rax, [rbp+57h+pChainContext]
0x180029338  mov     rcx, [rax+10h]
0x18002933c  mov     rcx, [rcx]
0x18002933f  cmp     dword ptr [rcx+0Ch], 3
0x180029343  jnz     loc_180029473
0x180029349  mov     rcx, [rcx+10h]
0x18002934d  mov     rax, [rcx]
0x180029350  cmp     [rax+10h], r15d
0x180029354  jnz     loc_180029473
0x18002935a  mov     rax, [rcx+8]
0x18002935e  cmp     [rax+10h], r15d
0x180029362  jnz     loc_180029473
0x180029368  mov     rax, [rbp+57h+ppStruct]
0x18002936c  mov     rcx, [rax+20h]
0x180029370  mov     rcx, [rcx]
0x180029373  mov     r8d, 10000000h; dwFlags
0x180029379  mov     rdx, [rbp+57h+phKey]; hKey
0x18002937d  mov     rcx, [rcx+8]; hSignature
0x180029381  call    cs:__imp_CryptXmlVerifySignature
0x180029387  mov     ebx, eax
0x180029389  test    eax, eax
0x18002938b  js      loc_180029478
0x180029391  mov     rax, [rbp+57h+ppStruct]
0x180029395  mov     rcx, [rax+20h]
0x180029399  mov     rcx, [rcx]
0x18002939c  lea     rdx, [rbp+57h+var_78]; ppStruct
0x1800293a0  mov     rcx, [rcx+8]; hCryptXml
0x1800293a4  call    cs:__imp_CryptXmlGetSignature
0x1800293aa  mov     ebx, eax
0x1800293ac  test    eax, eax
0x1800293ae  js      loc_180029478
0x1800293b4  mov     rax, [rbp+57h+var_78]
0x1800293b8  cmp     dword ptr [rax+68h], 1
0x1800293bc  jnz     loc_180029473
0x1800293c2  mov     rax, [rax+70h]
0x1800293c6  mov     rcx, [rax]
0x1800293c9  lea     rdx, [rbp+57h+var_70]; ppStruct
0x1800293cd  mov     rcx, [rcx+8]; hCryptXml
0x1800293d1  call    cs:__imp_CryptXmlGetReference
0x1800293d7  mov     ebx, eax
0x1800293d9  test    eax, eax
0x1800293db  js      loc_180029478
0x1800293e1  mov     rax, [rbp+57h+var_70]
0x1800293e5  mov     rcx, [rax+18h]
0x1800293e9  test    rcx, rcx
0x1800293ec  jz      short loc_180029413
0x1800293ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800293f2  inc     rax
0x1800293f5  cmp     [rcx+rax*2], r15w
0x1800293fa  jnz     short loc_1800293F2
0x1800293fc  test    rax, rax
0x1800293ff  jz      short loc_180029413
0x180029401  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180029408  jz      short loc_180029473
0x18002940a  lea     r8, aEnrollmenttoke_7; "EnrollmentToken::ValidateDSig Reference"...
0x180029411  jmp     short loc_180029461
0x180029413  mov     rax, [rbp+57h+ppStruct]
0x180029417  mov     rcx, [rax+20h]
0x18002941b  mov     rcx, [rcx]
0x18002941e  lea     rdx, [rbp+57h+pStatus]; pStatus
0x180029422  mov     rcx, [rcx+8]; hCryptXml
0x180029426  call    cs:__imp_CryptXmlGetStatus
0x18002942c  mov     ebx, eax
0x18002942e  test    eax, eax
0x180029430  js      short loc_180029478
0x180029432  mov     ecx, [rbp+57h+pStatus.dwErrorStatus]
0x180029435  test    cl, 2
0x180029438  jz      short loc_18002944C
0x18002943a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180029441  jz      short loc_180029473
0x180029443  lea     r8, aEnrollmenttoke_2; "EnrollmentToken::ValidateDSig CryptXmlG"...
0x18002944a  jmp     short loc_180029461
0x18002944c  test    cl, 1
0x18002944f  jz      short loc_180029478
0x180029451  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180029458  jz      short loc_180029473
0x18002945a  lea     r8, aEnrollmenttoke_1; "EnrollmentToken::ValidateDSig CryptXmlG"...
0x180029461  mov     r9d, 80004005h
0x180029467  lea     rdx, EnterpriseAppMgmtSvcError
0x18002946e  call    McTemplateU0zq_EventWriteTransfer
0x180029473  mov     ebx, 80004005h
0x180029478  test    rsi, rsi
0x18002947b  jz      short loc_18002948F
0x18002947d  xor     edx, edx; dwFlags
0x18002947f  mov     rcx, rsi; hCertStore
0x180029482  call    cs:__imp_CertCloseStore
0x180029488  jmp     short loc_18002948F
0x18002948a  mov     ebx, 80004005h
0x18002948f  mov     rcx, [rbp+57h+phKey]; hKey
0x180029493  test    rcx, rcx
0x180029496  jz      short loc_18002949E
0x180029498  call    cs:__imp_BCryptDestroyKey
0x18002949e  test    rdi, rdi
0x1800294a1  jz      short loc_1800294AC
0x1800294a3  mov     rcx, rdi; pCertContext
0x1800294a6  call    cs:__imp_CertFreeCertificateContext
0x1800294ac  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x1800294b0  test    rcx, rcx
0x1800294b3  jz      short loc_1800294BB
0x1800294b5  call    cs:__imp_CertFreeCertificateChain
0x1800294bb  mov     rcx, [rbp+57h+hCryptXml]; hCryptXml
0x1800294bf  test    rcx, rcx
0x1800294c2  jz      short loc_1800294CA
0x1800294c4  call    cs:__imp_CryptXmlClose
0x1800294ca  mov     eax, ebx
0x1800294cc  mov     rcx, [rbp+57h+var_28]
0x1800294d0  xor     rcx, rsp; StackCookie
0x1800294d3  call    __security_check_cookie
0x1800294d8  mov     rbx, [rsp+0E0h+arg_18]
0x1800294e0  add     rsp, 0C0h
0x1800294e7  pop     r15
0x1800294e9  pop     r14
0x1800294eb  pop     rdi
0x1800294ec  pop     rsi
0x1800294ed  pop     rbp
0x1800294ee  retn
```
