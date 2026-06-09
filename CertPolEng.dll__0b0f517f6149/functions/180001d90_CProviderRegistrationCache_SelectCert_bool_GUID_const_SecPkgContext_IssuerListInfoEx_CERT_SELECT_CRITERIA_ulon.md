# CProviderRegistrationCache::SelectCert(bool,_GUID const *,_SecPkgContext_IssuerListInfoEx *,_CERT_SELECT_CRITERIA *,ulong,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180001d90`
- end: `0x18000254b`
- name: `?SelectCert@CProviderRegistrationCache@@QEAAJ_NPEBU_GUID@@PEAU_SecPkgContext_IssuerListInfoEx@@PEAU_CERT_SELECT_CRITERIA@@KPEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `1979`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, unsigned __int8, struct _GUID *, struct _SecPkgContext_IssuerListInfoEx *, struct _CERT_SELECT_CRITERIA *rgpCriteria, unsigned int, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002560`

## callees

- `0x180001d90`
- `0x180003e60`
- `0x180007d20`
- `0x18000c344`
- `0x18000db54`
- `0x18000ddf0`
- `0x18001374c`
- `0x180018db0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002460`
- `RPCRT4!UuidEqual` at `0x180001e76`
- `RPCRT4!UuidEqual` at `0x180001f45`
- `RPCRT4!UuidEqual` at `0x180001f62`
- `RPCRT4!UuidEqual` at `0x180001ff7`
- `RPCRT4!UuidEqual` at `0x18000201a`
- `RPCRT4!UuidEqual` at `0x180001e76`
- `RPCRT4!UuidEqual` at `0x180001f45`
- `RPCRT4!UuidEqual` at `0x180001f62`
- `RPCRT4!UuidEqual` at `0x180001ff7`
- `RPCRT4!UuidEqual` at `0x18000201a`
- `CRYPT32!CertCompareCertificateName` at `0x180001f1f`
- `CRYPT32!CertCompareCertificateName` at `0x180001f1f`
- `CRYPT32!CertOpenStore` at `0x180001fa0`
- `CRYPT32!CertOpenStore` at `0x180001fa0`
- `CRYPT32!CertControlStore` at `0x1800023da`
- `CRYPT32!CertControlStore` at `0x1800023da`
- `CRYPT32!CertCloseStore` at `0x180002458`
- `CRYPT32!CertCloseStore` at `0x180002458`
- `CRYPT32!CertDuplicateCertificateChain` at `0x180002411`
- `CRYPT32!CertDuplicateCertificateChain` at `0x180002411`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180002223`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180002223`
- `CRYPT32!CertSelectCertificateChains` at `0x180002129`
- `CRYPT32!CertSelectCertificateChains` at `0x180002129`
- `ncrypt!NCryptFreeObject` at `0x1800022f1`
- `ncrypt!NCryptFreeObject` at `0x1800022f1`
- `CRYPTSP!CryptReleaseContext` at `0x1800022fb`
- `CRYPTSP!CryptReleaseContext` at `0x1800022fb`
- `ntdll!RtlReleaseResource` at `0x1800024b9`
- `ntdll!RtlReleaseResource` at `0x1800024b9`
- `ntdll!RtlAcquireResourceShared` at `0x180001e2d`
- `ntdll!RtlAcquireResourceShared` at `0x180001e2d`

## string_xrefs

- `0x180001deb`: `CProviderRegistrationCache::SelectCert`
- `0x1800024dd`: `CProviderRegistrationCache::SelectCert`
- `0x180002502`: `CProviderRegistrationCache::SelectCert`
- `0x180001fc5`: `GetCertificates::CertOpenStore`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::SelectCert(
        CProviderRegistrationCache *this,
        unsigned __int8 a2,
        struct _GUID *a3,
        struct _SecPkgContext_IssuerListInfoEx *a4,
        struct _CERT_SELECT_CRITERIA *rgpCriteria,
        unsigned int a6,
        const struct _CERT_CHAIN_CONTEXT **a7)
{
  unsigned int v9; // edi
  __int64 v10; // r14
  char *v11; // rbx
  struct _RTL_RESOURCE *v12; // r13
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r12d
  __int64 v16; // r14
  struct _SecPkgContext_IssuerListInfoEx *v17; // rcx
  DWORD v18; // r12d
  unsigned int i; // edi
  __int64 v20; // rax
  HCERTSTORE v21; // rax
  DWORD LastError; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // r14d
  int v26; // ebx
  DWORD v27; // edi
  __int64 v28; // rax
  unsigned int v29; // r12d
  DWORD v30; // r15d
  __int64 v31; // r14
  PCCERT_CHAIN_CONTEXT **pprgpSelection; // rdi
  HCERTSTORE hStore; // r13
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  DWORD v37; // edi
  unsigned int v38; // r14d
  PCCERT_CHAIN_CONTEXT v39; // rax
  PCERT_CHAIN_ELEMENT v40; // rcx
  _DWORD *p_dwCertEncodingType; // rdi
  __int64 v42; // rdx
  __int64 v43; // rcx
  DWORD v44; // eax
  __int64 v45; // rcx
  NCRYPT_HANDLE v46; // r9
  const char *v47; // r10
  int v48; // edi
  __int64 v49; // rcx
  __int64 (__fastcall *v50)(__int64, _QWORD); // rax
  int v51; // eax
  __int64 v52; // rdx
  const struct _CERT_CHAIN_CONTEXT **v53; // rcx
  const struct _CERT_CHAIN_CONTEXT *v54; // rax
  __int64 v55; // r9
  const char *v56; // r8
  signed int v57; // eax
  unsigned int v58; // edi
  __int64 v59; // rdx
  __int64 v60; // rcx
  int v62; // [rsp+40h] [rbp-C0h] BYREF
  RPC_STATUS v63; // [rsp+44h] [rbp-BCh] BYREF
  int v64; // [rsp+48h] [rbp-B8h]
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pdwKeySpec; // [rsp+50h] [rbp-B0h] BYREF
  int v67; // [rsp+54h] [rbp-ACh]
  __int64 v68; // [rsp+58h] [rbp-A8h]
  struct _RTL_RESOURCE *v69; // [rsp+60h] [rbp-A0h]
  char v70; // [rsp+68h] [rbp-98h]
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+70h] [rbp-90h] BYREF
  RPC_STATUS Status; // [rsp+78h] [rbp-88h] BYREF
  DWORD v73; // [rsp+7Ch] [rbp-84h]
  HCERTSTORE hCertStore; // [rsp+80h] [rbp-80h]
  HCERTSTORE v75; // [rsp+88h] [rbp-78h]
  char *v76; // [rsp+90h] [rbp-70h]
  __int128 v77; // [rsp+98h] [rbp-68h] BYREF
  __int128 v78; // [rsp+A8h] [rbp-58h]
  CERT_SELECT_CHAIN_PARA pChainParameters; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v80[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v81[10]; // [rsp+100h] [rbp+0h] BYREF
  int v82; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int8 v83; // [rsp+168h] [rbp+68h]
  struct _SecPkgContext_IssuerListInfoEx *v84; // [rsp+178h] [rbp+78h]

  v84 = a4;
  v83 = a2;
  v9 = 0;
  v82 = 0;
  v63 = 0;
  v10 = 0;
  v68 = 0;
  v11 = 0;
  v76 = 0;
  memset(&pChainParameters, 0, sizeof(pChainParameters));
  v77 = 0;
  v78 = 0;
  v81[0] = "CProviderRegistrationCache::SelectCert";
  v81[1] = 0;
  v81[2] = &v82;
  v81[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(
      "CProviderRegistrationCache::SelectCert",
      Func_Start,
      "CProviderRegistrationCache::SelectCert");
  v12 = (struct _RTL_RESOURCE *)((char *)this + 16);
  v69 = (struct _RTL_RESOURCE *)((char *)this + 16);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
  v70 = 1;
  *a7 = 0;
  v15 = -1073741275;
  Status = 0;
  if ( *((_DWORD *)this + 38) )
  {
    do
    {
      v16 = 8LL * v9;
      if ( UuidEqual((UUID *)(*(_QWORD *)(v16 + *((_QWORD *)this + 18)) + 8LL), a3, &Status) )
      {
        v68 = *(_QWORD *)(v16 + *((_QWORD *)this + 18));
        v15 = 0;
      }
      ++v9;
    }
    while ( v9 < *((_DWORD *)this + 38) );
    v10 = v68;
  }
  v82 = v15;
  if ( v15 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v14, v13, "FindProvFromGUID", (unsigned int)v15);
    goto LABEL_102;
  }
  if ( !*(_DWORD *)(*(_QWORD *)(v10 + 2120) + 8LL) || (v17 = v84, !v84->cIssuers) )
  {
LABEL_101:
    v82 = 0;
    goto LABEL_102;
  }
  v18 = 0;
LABEL_14:
  if ( v18 >= v17->cIssuers )
    goto LABEL_101;
  for ( i = 0; ; ++i )
  {
    v20 = *(_QWORD *)(v10 + 2120);
    if ( i >= *(_DWORD *)(v20 + 8) )
    {
      ++v18;
      goto LABEL_14;
    }
    if ( CertCompareCertificateName(0x10001u, &v17->aIssuers[v18], (PCERT_NAME_BLOB)(*(_QWORD *)v20 + 16LL * i)) )
      break;
    v17 = v84;
  }
  if ( UuidEqual(a3, (UUID *)&Uuid2, &v63) || UuidEqual(a3, (UUID *)&stru_18001E1A0, &v63) )
  {
    v75 = 0;
    hCertStore = *(HCERTSTORE *)(v10 + 2104);
    v26 = 0;
    v25 = 9;
    v64 = 1;
  }
  else
  {
    v21 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, (((v83 ^ 1) + 1) << 16) | 0xC000u, L"My");
    v75 = v21;
    if ( !v21 )
    {
      LastError = GetLastError();
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v24, v23, "GetCertificates::CertOpenStore", LastError);
      goto LABEL_102;
    }
    v25 = 8;
    v64 = 0;
    hCertStore = v21;
    v26 = -16777281;
    if ( !UuidEqual(a3, (UUID *)&Uuid1, &v63) )
    {
      v27 = 0x10000000;
      if ( UuidEqual(a3, (UUID *)&stru_18001E1B0, &v63) )
        v64 = 1;
      goto LABEL_30;
    }
  }
  v27 = -2147483644;
LABEL_30:
  v28 = *(_QWORD *)(v68 + 2144) & 1LL;
  v29 = v26 & 0xFFFFFFFE;
  if ( !v28 )
    v29 = v26;
  v30 = v25 | 1;
  if ( !v28 )
    v30 = v25;
  v11 = (char *)operator new(0x18u);
  v76 = v11;
  if ( !v11 )
  {
    v11 = 0;
    goto LABEL_91;
  }
  *(_QWORD *)v11 = &CCertChainList::`vftable';
  *((_QWORD *)v11 + 2) = 0;
  *((_DWORD *)v11 + 2) = 0;
  v76 = v11;
  LODWORD(v77) = 32;
  DWORD2(v77) = 0;
  LODWORD(v78) = 0;
  *((_QWORD *)&v78 + 1) = 0;
  v31 = v68;
  pChainParameters.hChainEngine = *(HCERTCHAINENGINE *)(v68 + 2128);
  *(_OWORD *)&pChainParameters.pTime = 0;
  pChainParameters.pChainPara = (PCERT_CHAIN_PARA)&v77;
  pChainParameters.dwFlags = v27;
  v67 = 0;
  pprgpSelection = (PCCERT_CHAIN_CONTEXT **)(v11 + 16);
  hStore = hCertStore;
  while ( !CertSelectCertificateChains(
             0,
             v30,
             &pChainParameters,
             1u,
             rgpCriteria,
             hStore,
             (PDWORD)v11 + 2,
             pprgpSelection) )
  {
    v34 = GetLastError();
    v37 = v34;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v36, v35, "CertSelectCertificateChains", v34);
    if ( v37 == 14 )
    {
      v82 = -1073741801;
      goto LABEL_90;
    }
    pprgpSelection = (PCCERT_CHAIN_CONTEXT **)(v11 + 16);
LABEL_77:
    if ( v64 )
    {
      v82 = -2146762486;
      goto LABEL_90;
    }
    v49 = v31 + 8;
    v50 = (__int64 (__fastcall *)(__int64, _QWORD))*((_QWORD *)this + 32);
    if ( v50 )
      v51 = v50(v49, v83);
    else
      v51 = LsaRenewCertificate(v49, v83);
    v82 = v51;
    if ( v51 < 0 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
        goto LABEL_90;
      v55 = (unsigned int)v51;
      v56 = "RenewCertificate";
      goto LABEL_89;
    }
    if ( !CertControlStore(hStore, 0, 4u, 0) )
    {
      v57 = GetLastError();
      if ( v57 > 0 )
        v57 = (unsigned __int16)v57 | 0xC0070000;
      v82 = v57;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
        goto LABEL_90;
      v55 = (unsigned int)v57;
      v56 = "CertControlStore";
LABEL_89:
      McTemplateU0sq_EtwEventWriteTransfer(v53, v52, v56, v55);
      goto LABEL_90;
    }
    if ( (unsigned int)++v67 >= 2 )
      goto LABEL_84;
  }
  v38 = 0;
  while ( 2 )
  {
    if ( v38 >= *((_DWORD *)v11 + 2) )
    {
      v31 = v68;
      hStore = hCertStore;
      goto LABEL_77;
    }
    v39 = (*pprgpSelection)[v38];
    if ( (v29 & v39->TrustStatus.dwErrorStatus) != 0 )
    {
LABEL_75:
      ++v38;
      continue;
    }
    break;
  }
  v40 = *(*v39->rgpChain)->rgpElement;
  p_dwCertEncodingType = &v40->pCertContext->dwCertEncodingType;
  v62 = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  v80[0] = "PstAcquirePrivateKey";
  v80[1] = 0;
  v80[2] = &v62;
  v80[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v40, Func_Start, "PstAcquirePrivateKey");
  if ( p_dwCertEncodingType )
  {
    if ( CryptAcquireCertificatePrivateKey(
           (PCCERT_CONTEXT)p_dwCertEncodingType,
           0x20045u,
           0,
           &phCryptProvOrNCryptKey,
           &pdwKeySpec,
           &pfCallerFreeProvOrNCryptKey) )
    {
      goto LABEL_57;
    }
    v44 = GetLastError();
    v73 = v44;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v45, v42, "CryptAcquireCertificatePrivateKey", v44);
    v62 = -1073741715;
    v43 = *((_QWORD *)p_dwCertEncodingType + 1);
    if ( v43 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0qqbr1_EtwEventWriteTransfer(
          v43,
          v42,
          *p_dwCertEncodingType,
          p_dwCertEncodingType[4],
          *((_QWORD *)p_dwCertEncodingType + 1));
    }
    else
    {
      LOBYTE(a6) = 0;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0qqbr1_EtwEventWriteTransfer(0, v42, *p_dwCertEncodingType, 1, (__int64)&a6);
    }
    if ( !v73 )
    {
LABEL_57:
      v62 = 0;
      v46 = phCryptProvOrNCryptKey;
      v47 = "PstAcquirePrivateKey";
    }
    else
    {
      v46 = phCryptProvOrNCryptKey;
      v47 = "PstAcquirePrivateKey";
    }
  }
  else
  {
    v62 = NetpApiStatusToNtStatus(87);
  }
  if ( pfCallerFreeProvOrNCryptKey && v46 )
  {
    if ( pdwKeySpec == -1 )
      NCryptFreeObject(v46);
    else
      CryptReleaseContext(v46, 0);
    v47 = "PstAcquirePrivateKey";
  }
  v48 = v62;
  a6 = v62 | 0x10000000;
  if ( v62 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v43, v42, v47, v62 | 0x10000000u);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(v80, &a6);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v43, Func_Exit, "PstAcquirePrivateKey");
  v82 = v48;
  if ( v48 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v43, v42, "PstAcquirePrivateKey(Cert Selection)", (unsigned int)v48);
    pprgpSelection = (PCCERT_CHAIN_CONTEXT **)(v11 + 16);
    goto LABEL_75;
  }
  v54 = CertDuplicateCertificateChain(*(PCCERT_CHAIN_CONTEXT *)(*((_QWORD *)v11 + 2) + 8LL * v38));
  v53 = a7;
  *a7 = v54;
  if ( v54 )
  {
LABEL_84:
    v82 = 0;
    goto LABEL_90;
  }
  v82 = -1073741801;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
  {
    v55 = 3221225495LL;
    v56 = "CertDuplicateCertificateChain";
    goto LABEL_89;
  }
LABEL_90:
  v12 = v69;
LABEL_91:
  if ( v75 )
    CertCloseStore(v75, 0);
LABEL_102:
  v58 = v82;
  RtlReleaseResource(v12);
  a6 = v82 | 0x10000000;
  if ( v82 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v60, v59, "CProviderRegistrationCache::SelectCert", v82 | 0x10000000u);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(v81, &a6);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v60, Func_Exit, "CProviderRegistrationCache::SelectCert");
  if ( v11 )
    (**(void (__fastcall ***)(void *, __int64))v11)(v11, 1);
  return v58;
}

```

## disassembly

```asm
0x180001d90  mov     [rsp-8+arg_10], rbx
0x180001d95  mov     [rsp-8+arg_18], r9
0x180001d9a  mov     [rsp-8+arg_8], dl
0x180001d9e  push    rbp
0x180001d9f  push    rsi
0x180001da0  push    rdi
0x180001da1  push    r12
0x180001da3  push    r13
0x180001da5  push    r14
0x180001da7  push    r15
0x180001da9  lea     rbp, [rsp-20h]
0x180001dae  sub     rsp, 120h
0x180001db5  mov     r15, r8
0x180001db8  mov     rsi, rcx
0x180001dbb  xor     edi, edi
0x180001dbd  mov     [rbp+50h+arg_0], edi
0x180001dc0  mov     [rsp+150h+var_10C], edi
0x180001dc4  mov     r14d, edi
0x180001dc7  mov     [rsp+150h+var_F8], rdi
0x180001dcc  mov     ebx, edi
0x180001dce  mov     [rbp+50h+var_C0], rbx
0x180001dd2  xorps   xmm0, xmm0
0x180001dd5  xor     eax, eax
0x180001dd7  movups  xmmword ptr [rbp+50h+pChainParameters.hChainEngine], xmm0
0x180001ddb  movups  xmmword ptr [rbp+50h+pChainParameters.hAdditionalStore], xmm0
0x180001ddf  mov     qword ptr [rbp+50h+pChainParameters.dwFlags], rax
0x180001de3  movups  [rbp+50h+var_B8], xmm0
0x180001de7  movups  [rbp+50h+var_A8], xmm0
0x180001deb  lea     rcx, aCproviderregis_2; "CProviderRegistrationCache::SelectCert"
0x180001df2  mov     [rbp+50h+var_50], rcx
0x180001df6  mov     [rbp+50h+var_48], rdi
0x180001dfa  lea     rax, [rbp+50h+arg_0]
0x180001dfe  mov     [rbp+50h+var_40], rax
0x180001e02  mov     [rbp+50h+var_38], rdi
0x180001e06  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180001e0d  jz      short loc_180001E1F
0x180001e0f  mov     r8, rcx
0x180001e12  lea     rdx, Func_Start
0x180001e19  call    McTemplateU0s_EtwEventWriteTransfer
0x180001e1e  nop
0x180001e1f  lea     r13, [rsi+10h]
0x180001e23  mov     [rsp+150h+var_F0], r13
0x180001e28  mov     dl, 1; Wait
0x180001e2a  mov     rcx, r13; Resource
0x180001e2d  call    cs:__imp_RtlAcquireResourceShared
0x180001e33  mov     [rsp+150h+var_E8], 1
0x180001e38  mov     rax, [rbp+50h+arg_30]
0x180001e3f  mov     [rax], rdi
0x180001e42  mov     r12d, 0C0000225h
0x180001e48  mov     [rsp+150h+Status], edi
0x180001e4c  cmp     dword ptr [rsi+98h], 0
0x180001e53  jbe     short loc_180001EA2
0x180001e55  mov     eax, edi
0x180001e57  lea     r14, ds:0[rax*8]
0x180001e5f  mov     rax, [rsi+90h]
0x180001e66  mov     rcx, [r14+rax]
0x180001e6a  add     rcx, 8; Uuid1
0x180001e6e  lea     r8, [rsp+150h+Status]; Status
0x180001e73  mov     rdx, r15; Uuid2
0x180001e76  call    cs:__imp_UuidEqual
0x180001e7c  test    eax, eax
0x180001e7e  jz      short loc_180001E93
0x180001e80  mov     rax, [rsi+90h]
0x180001e87  mov     rax, [r14+rax]
0x180001e8b  mov     [rsp+150h+var_F8], rax
0x180001e90  xor     r12d, r12d
0x180001e93  inc     edi
0x180001e95  cmp     edi, [rsi+98h]
0x180001e9b  jb      short loc_180001E55
0x180001e9d  mov     r14, [rsp+150h+var_F8]
0x180001ea2  mov     [rbp+50h+arg_0], r12d
0x180001ea6  test    r12d, r12d
0x180001ea9  jns     short loc_180001ECC
0x180001eab  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180001eb2  jz      loc_1800024B3
0x180001eb8  mov     r9d, r12d
0x180001ebb  lea     r8, aFindprovfromgu; "FindProvFromGUID"
0x180001ec2  call    McTemplateU0sq_EtwEventWriteTransfer
0x180001ec7  jmp     loc_1800024B3
0x180001ecc  mov     rax, [r14+848h]
0x180001ed3  cmp     dword ptr [rax+8], 0
0x180001ed7  jz      loc_1800024AC
0x180001edd  mov     rcx, [rbp+50h+arg_18]
0x180001ee1  cmp     dword ptr [rcx+8], 0
0x180001ee5  jz      loc_1800024AC
0x180001eeb  xor     r12d, r12d
0x180001eee  cmp     r12d, [rcx+8]
0x180001ef2  jnb     loc_1800024AC
0x180001ef8  xor     edi, edi
0x180001efa  mov     rax, [r14+848h]
0x180001f01  cmp     edi, [rax+8]
0x180001f04  jnb     short loc_180001F31
0x180001f06  mov     r8d, edi
0x180001f09  shl     r8, 4
0x180001f0d  add     r8, [rax]; pCertName2
0x180001f10  mov     edx, r12d
0x180001f13  shl     rdx, 4
0x180001f17  add     rdx, [rcx]; pCertName1
0x180001f1a  mov     ecx, 10001h; dwCertEncodingType
0x180001f1f  call    cs:__imp_CertCompareCertificateName
0x180001f25  test    eax, eax
0x180001f27  jnz     short loc_180001F36
0x180001f29  inc     edi
0x180001f2b  mov     rcx, [rbp+50h+arg_18]
0x180001f2f  jmp     short loc_180001EFA
0x180001f31  inc     r12d
0x180001f34  jmp     short loc_180001EEE
0x180001f36  lea     r8, [rsp+150h+var_10C]; Status
0x180001f3b  lea     rdx, Uuid2; Uuid2
0x180001f42  mov     rcx, r15; Uuid1
0x180001f45  call    cs:__imp_UuidEqual
0x180001f4b  test    eax, eax
0x180001f4d  jnz     loc_18000202E
0x180001f53  lea     r8, [rsp+150h+var_10C]; Status
0x180001f58  lea     rdx, stru_18001E1A0; Uuid2
0x180001f5f  mov     rcx, r15; Uuid1
0x180001f62  call    cs:__imp_UuidEqual
0x180001f68  test    eax, eax
0x180001f6a  jnz     loc_18000202E
0x180001f70  movzx   r9d, [rbp+50h+arg_8]
0x180001f75  xor     r9d, 1
0x180001f79  inc     r9d
0x180001f7c  shl     r9d, 10h
0x180001f80  or      r9d, 0C000h; dwFlags
0x180001f87  lea     rax, aMy; "My"
0x180001f8e  mov     [rsp+150h+pvPara], rax; pvPara
0x180001f93  xor     r8d, r8d; hCryptProv
0x180001f96  mov     edx, 10001h; dwEncodingType
0x180001f9b  mov     ecx, 0Ah; lpszStoreProvider
0x180001fa0  call    cs:__imp_CertOpenStore
0x180001fa6  mov     [rbp+50h+var_C8], rax
0x180001faa  test    rax, rax
0x180001fad  jnz     short loc_180001FD6
0x180001faf  call    cs:__imp_GetLastError
0x180001fb5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180001fbc  jz      loc_1800024B3
0x180001fc2  mov     r9d, eax
0x180001fc5  lea     r8, aGetcertificate_1; "GetCertificates::CertOpenStore"
0x180001fcc  call    McTemplateU0sq_EtwEventWriteTransfer
0x180001fd1  jmp     loc_1800024B3
0x180001fd6  mov     r14d, 8
0x180001fdc  mov     [rsp+150h+var_108], 0
0x180001fe4  mov     [rbp+50h+hCertStore], rax
0x180001fe8  lea     r8, [rsp+150h+var_10C]; Status
0x180001fed  lea     rdx, Uuid1; Uuid2
0x180001ff4  mov     rcx, r15; Uuid1
0x180001ff7  call    cs:__imp_UuidEqual
0x180001ffd  mov     ebx, 0FEFFFFBFh
0x180002002  test    eax, eax
0x180002004  jnz     short loc_180002051
0x180002006  mov     edi, 10000000h
0x18000200b  lea     r8, [rsp+150h+var_10C]; Status
0x180002010  lea     rdx, stru_18001E1B0; Uuid2
0x180002017  mov     rcx, r15; Uuid1
0x18000201a  call    cs:__imp_UuidEqual
0x180002020  test    eax, eax
0x180002022  jz      short loc_180002056
0x180002024  mov     [rsp+150h+var_108], 1
0x18000202c  jmp     short loc_180002056
0x18000202e  mov     [rbp+50h+var_C8], 0
0x180002036  mov     rax, [r14+838h]
0x18000203d  mov     [rbp+50h+hCertStore], rax
0x180002041  xor     ebx, ebx
0x180002043  mov     r14d, 9
0x180002049  mov     [rsp+150h+var_108], 1
0x180002051  mov     edi, 80000004h
0x180002056  mov     rax, [rsp+150h+var_F8]
0x18000205b  mov     rax, [rax+860h]
0x180002062  and     eax, 1
0x180002065  mov     r12d, ebx
0x180002068  and     r12d, 0FFFFFFFEh
0x18000206c  test    rax, rax
0x18000206f  cmovz   r12d, ebx
0x180002073  mov     r15d, r14d
0x180002076  or      r15d, 1
0x18000207a  test    rax, rax
0x18000207d  cmovz   r15d, r14d
0x180002081  mov     ecx, 18h; Size
0x180002086  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000208b  mov     rbx, rax
0x18000208e  mov     [rbp+50h+var_C0], rax
0x180002092  test    rax, rax
0x180002095  jz      loc_1800024A8
0x18000209b  lea     rax, ??_7CCertChainList@@6B@; const CCertChainList::`vftable'
0x1800020a2  mov     [rbx], rax
0x1800020a5  xor     ecx, ecx
0x1800020a7  mov     [rbx+10h], rcx
0x1800020ab  mov     [rbx+8], ecx
0x1800020ae  mov     [rbp+50h+var_C0], rbx
0x1800020b2  test    rbx, rbx
0x1800020b5  jz      loc_18000244D
0x1800020bb  mov     dword ptr [rbp+50h+var_B8], 20h ; ' '
0x1800020c2  mov     dword ptr [rbp+50h+var_B8+8], ecx
0x1800020c5  mov     dword ptr [rbp+50h+var_A8], ecx
0x1800020c8  mov     qword ptr [rbp+50h+var_A8+8], rcx
0x1800020cc  mov     r14, [rsp+150h+var_F8]
0x1800020d1  mov     rax, [r14+850h]
0x1800020d8  mov     [rbp+50h+pChainParameters.hChainEngine], rax
0x1800020dc  xorps   xmm0, xmm0
0x1800020df  movdqu  xmmword ptr [rbp+50h+pChainParameters.pTime], xmm0
0x1800020e4  lea     rax, [rbp+50h+var_B8]
0x1800020e8  mov     [rbp+50h+pChainParameters.pChainPara], rax
0x1800020ec  mov     [rbp+50h+pChainParameters.dwFlags], edi
0x1800020ef  mov     [rsp+150h+var_FC], ecx
0x1800020f3  lea     rdi, [rbx+10h]
0x1800020f7  mov     r13, [rbp+50h+hCertStore]
0x1800020fb  lea     rax, [rbx+8]
0x1800020ff  mov     [rsp+150h+pprgpSelection], rdi; pprgpSelection
0x180002104  mov     [rsp+150h+pcSelection], rax; pcSelection
0x180002109  mov     [rsp+150h+hStore], r13; hStore
0x18000210e  mov     rax, [rbp+50h+rgpCriteria]
0x180002115  mov     [rsp+150h+pvPara], rax; rgpCriteria
0x18000211a  mov     r9d, 1; cCriteria
0x180002120  lea     r8, [rbp+50h+pChainParameters]; pChainParameters
0x180002124  mov     edx, r15d; dwFlags
0x180002127  xor     ecx, ecx; pSelectionContext
0x180002129  call    cs:__imp_CertSelectCertificateChains
0x18000212f  test    eax, eax
0x180002131  jnz     short loc_180002165
0x180002133  call    cs:__imp_GetLastError
0x180002139  mov     edi, eax
0x18000213b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180002142  jz      short loc_180002153
0x180002144  mov     r9d, eax
0x180002147  lea     r8, aCertselectcert; "CertSelectCertificateChains"
0x18000214e  call    McTemplateU0sq_EtwEventWriteTransfer
0x180002153  cmp     edi, 0Eh
0x180002156  jz      loc_180002400
0x18000215c  lea     rdi, [rbx+10h]
0x180002160  jmp     loc_180002396
0x180002165  xor     edx, edx
0x180002167  mov     r14d, edx
0x18000216a  cmp     r14d, [rbx+8]
0x18000216e  jnb     loc_18000238D
0x180002174  mov     eax, r14d
0x180002177  lea     r13, ds:0[rax*8]
0x18000217f  mov     rax, [rdi]
0x180002182  mov     rax, [rax+r13]
0x180002186  test    [rax+4], r12d
0x18000218a  jnz     loc_180002385
0x180002190  mov     rax, [rax+10h]
0x180002194  mov     rcx, [rax]
0x180002197  mov     rax, [rcx+10h]
0x18000219b  mov     rcx, [rax]
0x18000219e  mov     rdi, [rcx+8]
0x1800021a2  mov     [rsp+150h+var_110], edx
0x1800021a6  mov     r9, rdx
0x1800021a9  mov     [rsp+150h+phCryptProvOrNCryptKey], rdx
0x1800021ae  mov     [rsp+150h+pdwKeySpec], edx
0x1800021b2  mov     [rsp+150h+pfCallerFreeProvOrNCryptKey], edx
0x1800021b6  lea     r10, aPstacquirepriv_0; "PstAcquirePrivateKey"
0x1800021bd  mov     [rbp+50h+var_70], r10
0x1800021c1  mov     [rbp+50h+var_68], rdx
0x1800021c5  lea     rax, [rsp+150h+var_110]
0x1800021ca  mov     [rbp+50h+var_60], rax
0x1800021ce  mov     [rbp+50h+var_58], rdx
0x1800021d2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800021d9  jz      short loc_1800021F6
0x1800021db  mov     r8, r10
0x1800021de  lea     rdx, Func_Start
0x1800021e5  call    McTemplateU0s_EtwEventWriteTransfer
0x1800021ea  mov     r9, [rsp+150h+phCryptProvOrNCryptKey]
0x1800021ef  lea     r10, aPstacquirepriv_0; "PstAcquirePrivateKey"
0x1800021f6  test    rdi, rdi
0x1800021f9  jz      loc_1800022CD
0x1800021ff  lea     rax, [rsp+150h+pfCallerFreeProvOrNCryptKey]
0x180002204  mov     [rsp+150h+hStore], rax; pfCallerFreeProvOrNCryptKey
0x180002209  lea     rax, [rsp+150h+pdwKeySpec]
0x18000220e  mov     [rsp+150h+pvPara], rax; pdwKeySpec
0x180002213  lea     r9, [rsp+150h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180002218  xor     r8d, r8d; pvParameters
0x18000221b  mov     edx, 20045h; dwFlags
0x180002220  mov     rcx, rdi; pCert
0x180002223  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180002229  test    eax, eax
0x18000222b  jnz     loc_1800022B7
0x180002231  call    cs:__imp_GetLastError
0x180002237  mov     [rsp+150h+var_D4], eax
0x18000223b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180002242  jz      short loc_180002253
0x180002244  mov     r9d, eax
0x180002247  lea     r8, aCryptacquirece; "CryptAcquireCertificatePrivateKey"
0x18000224e  call    McTemplateU0sq_EtwEventWriteTransfer
0x180002253  mov     [rsp+150h+var_110], 0C000006Dh
0x18000225b  mov     rcx, [rdi+8]
0x18000225f  test    rcx, rcx
0x180002262  jz      short loc_180002278
0x180002264  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000226b  jz      short loc_1800022A2
0x18000226d  mov     [rsp+150h+pvPara], rcx
0x180002272  mov     r9d, [rdi+10h]
0x180002276  jmp     short loc_18000229A
0x180002278  mov     byte ptr [rbp+50h+arg_28], 0
0x18000227f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180002286  jz      short loc_1800022A2
0x180002288  lea     rax, [rbp+50h+arg_28]
0x18000228f  mov     [rsp+150h+pvPara], rax
0x180002294  mov     r9d, 1
0x18000229a  mov     r8d, [rdi]
0x18000229d  call    McTemplateU0qqbr1_EtwEventWriteTransfer
  ... truncated ...
```
