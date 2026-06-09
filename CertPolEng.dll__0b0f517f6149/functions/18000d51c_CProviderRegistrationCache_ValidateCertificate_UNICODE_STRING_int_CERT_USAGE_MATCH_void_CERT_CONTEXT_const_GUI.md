# CProviderRegistrationCache::ValidateCertificate(_UNICODE_STRING *,int,_CERT_USAGE_MATCH *,void * *,_CERT_CONTEXT const *,_GUID *)

- ea: `0x18000d51c`
- end: `0x18000db4b`
- name: `?ValidateCertificate@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@HPEAU_CERT_USAGE_MATCH@@PEAPEAXPEBU_CERT_CONTEXT@@PEAU_GUID@@@Z`
- size: `1583`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _UNICODE_STRING *, int *, struct _CERT_USAGE_MATCH *, void **hAdditionalStore, const struct _CERT_CONTEXT *, struct _GUID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013b50`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x180006fa0`
- `0x180007b70`
- `0x180007bc0`
- `0x180007da0`
- `0x180007ea0`
- `0x180009510`
- `0x18000c344`
- `0x18000d51c`
- `0x18000db54`
- `0x180014b54`
- `0x180016b9c`
- `0x180016f84`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db12`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d84f`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d84f`
- `CRYPT32!CertFreeCertificateChain` at `0x18000db04`
- `CRYPT32!CertFreeCertificateChain` at `0x18000db04`
- `CRYPT32!CertGetCertificateChain` at `0x18000d6c3`
- `CRYPT32!CertGetCertificateChain` at `0x18000d6c3`
- `CRYPT32!CertFindCertificateInStore` at `0x18000d81d`
- `CRYPT32!CertFindCertificateInStore` at `0x18000d81d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18000d997`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18000d997`
- `ntdll!RtlReleaseResource` at `0x18000d70f`
- `ntdll!RtlReleaseResource` at `0x18000d78d`
- `ntdll!RtlReleaseResource` at `0x18000d862`
- `ntdll!RtlReleaseResource` at `0x18000d8a1`
- `ntdll!RtlReleaseResource` at `0x18000d928`
- `ntdll!RtlReleaseResource` at `0x18000dae9`
- `ntdll!RtlReleaseResource` at `0x18000d70f`
- `ntdll!RtlReleaseResource` at `0x18000d78d`
- `ntdll!RtlReleaseResource` at `0x18000d862`
- `ntdll!RtlReleaseResource` at `0x18000d8a1`
- `ntdll!RtlReleaseResource` at `0x18000d928`
- `ntdll!RtlReleaseResource` at `0x18000dae9`

## string_xrefs

- `0x18000d5c7`: `CProviderRegistrationCache::ValidateCertificate`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ValidateCertificate(
        CProviderRegistrationCache *this,
        struct _UNICODE_STRING *a2,
        int *a3,
        struct _CERT_USAGE_MATCH *a4,
        void **hAdditionalStore,
        const struct _CERT_CONTEXT *a6,
        struct _GUID *a7)
{
  int v8; // edi
  int v10; // r14d
  CProviderRegistrationCache *v11; // r13
  unsigned __int16 *v12; // rsi
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // ebx
  int v16; // ecx
  int v17; // r8d
  int v18; // edi
  void *v19; // r9
  int v20; // r8d
  DWORD LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // ebx
  PCERT_SIMPLE_CHAIN v25; // rax
  PCERT_CHAIN_ELEMENT *rgpElement; // rax
  int v27; // r8d
  void *v28; // rcx
  const struct _CERT_CONTEXT *v29; // r12
  const CERT_CONTEXT *CertificateInStore; // r14
  DWORD v31; // eax
  int v32; // r14d
  __int64 v33; // rcx
  unsigned __int16 *v34; // r14
  int v35; // edx
  CProviderRegistrationCache *v36; // rcx
  DWORD dwError; // r8d
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  unsigned int ProvFromCertificate; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  unsigned int HostNameFromTargetName; // [rsp+40h] [rbp-C0h] BYREF
  PRTL_RESOURCE Resource; // [rsp+48h] [rbp-B8h] BYREF
  char v48; // [rsp+50h] [rbp-B0h]
  int v49; // [rsp+58h] [rbp-A8h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v51; // [rsp+68h] [rbp-98h] BYREF
  __int128 v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v53; // [rsp+80h] [rbp-80h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v55; // [rsp+A0h] [rbp-60h] BYREF
  struct CProviderEntry *v56; // [rsp+A8h] [rbp-58h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+B0h] [rbp-50h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v59[32]; // [rsp+E0h] [rbp-20h] BYREF
  PCCERT_CONTEXT pCertContext[2]; // [rsp+100h] [rbp+0h] BYREF
  PRTL_RESOURCE v61; // [rsp+110h] [rbp+10h] BYREF
  char v62; // [rsp+118h] [rbp+18h]
  struct _GUID *v63; // [rsp+120h] [rbp+20h] BYREF

  v8 = (int)a3;
  v49 = (int)a3;
  v10 = (int)hAdditionalStore;
  pCertContext[0] = a6;
  v63 = a7;
  v11 = g_pProvRegCache;
  HostNameFromTargetName = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pPolicyPara = 0;
  v52 = 0;
  v53 = 0;
  pChainContext = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  v56 = 0;
  v12 = 0;
  v51 = 0;
  v55 = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v59,
    "CProviderRegistrationCache::ValidateCertificate",
    a3,
    0,
    &HostNameFromTargetName);
  if ( v8 && (unsigned int)CIdentityPolicy::IsPku2uDisabled((CProviderRegistrationCache *)((char *)v11 + 280)) )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v13, (unsigned int)Pku2uDisabled, v14, 1, (__int64)&v61);
    v15 = -1073741715;
    goto LABEL_85;
  }
  CProviderRegistrationCache::RefreshProvCache(v11);
  CAutoRtlLock::CAutoRtlLock(&Resource, (char *)v11 + 16, 0);
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  v18 = 1;
  if ( a4 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v16, (unsigned int)RIPolicySpecified, v17, 1, (__int64)&v61);
    pChainPara.RequestedUsage.dwType = a4->dwType;
    pChainPara.RequestedUsage.Usage.cUsageIdentifier = a4->Usage.cUsageIdentifier;
    pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = a4->Usage.rgpszUsageIdentifier;
  }
  if ( hAdditionalStore )
  {
    v19 = *hAdditionalStore;
    v10 = 0;
  }
  else
  {
    v19 = 0;
  }
  if ( CertGetCertificateChain(
         *((HCERTCHAINENGINE *)v11 + 17),
         pCertContext[0],
         0,
         v19,
         &pChainPara,
         0xC0000004,
         0,
         &pChainContext) )
  {
    v24 = 0;
    if ( !pChainContext )
      goto LABEL_47;
    if ( !pChainContext->cChain )
      goto LABEL_47;
    v25 = *pChainContext->rgpChain;
    if ( !v25->cElement )
      goto LABEL_47;
    if ( (v25->TrustStatus.dwErrorStatus & 0x20) != 0 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          (_DWORD)pChainContext,
          (unsigned int)CertRootIsNotTrusted,
          v20,
          1,
          (__int64)&v61);
      goto LABEL_29;
    }
    rgpElement = v25->rgpElement;
    v24 = (*rgpElement)->TrustStatus.dwInfoStatus & 8;
    if ( !v49 && v24 && a2 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)*rgpElement,
          (unsigned int)CertIsSelfSigned,
          v20,
          1,
          (__int64)&v61);
      CAutoRtlLock::CAutoRtlLock(&v61, (char *)v11 + 16, 0);
      v28 = (void *)*((_QWORD *)v11 + 40);
      if ( !v28
        || (v29 = pCertContext[0],
            (CertificateInStore = CertFindCertificateInStore(v28, 0x10001u, 0, 0xD0000u, pCertContext[0], 0)) == 0) )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            (_DWORD)v28,
            (unsigned int)CertNotFoundInHGContainer,
            v27,
            1,
            (__int64)&v63);
        v15 = -1073741715;
        if ( v62 )
          RtlReleaseResource(v61);
        goto LABEL_30;
      }
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          (_DWORD)v28,
          (unsigned int)CertFoundInContainer,
          v27,
          1,
          (__int64)pCertContext);
      CertFreeCertificateContext(CertificateInStore);
      v10 = 1;
      if ( v62 )
        RtlReleaseResource(v61);
    }
    else
    {
LABEL_47:
      v29 = pCertContext[0];
    }
    memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
    v52 = 0;
    v53 = 0;
    pPolicyPara.cbSize = 16;
    pPolicyStatus.cbSize = 24;
    LODWORD(v52) = 24;
    pPolicyPara.pvExtraPolicyPara = &v52;
    v31 = 3840;
    if ( v10 )
      v31 = 3856;
    pPolicyPara.dwFlags = v31;
    v32 = v49;
    if ( v49 )
    {
      *(_QWORD *)((char *)&v52 + 4) = 1;
      v53 = 0;
    }
    else
    {
      HostNameFromTargetName = GetHostNameFromTargetName(a2, &v51, &v55);
      if ( HostNameFromTargetName )
      {
        if ( v48 )
          RtlReleaseResource(Resource);
        v12 = v51;
        goto LABEL_84;
      }
      v12 = v51;
      v34 = v55;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McTemplateU0zz_EtwEventWriteTransfer(v33, TargetNameAndHostName, v51, v55);
      LODWORD(v52) = 24;
      *(_QWORD *)((char *)&v52 + 4) = 2;
      v53 = v34;
      v32 = v49;
    }
    if ( CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
    {
      dwError = pPolicyStatus.dwError;
      if ( !pPolicyStatus.dwError )
      {
        if ( v32
          && a2
          && a2->Length
          && (v38 = CProviderRegistrationCache::ValidateClientNameBinding(v36, v29, a2),
              (HostNameFromTargetName = v38) != 0) )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v40, v39, "ValidateClientNameBinding", v38);
        }
        else if ( !v24 )
        {
          if ( pChainContext->cChain )
          {
            rgpChain = pChainContext->rgpChain;
            if ( (*rgpChain)->cElement )
            {
              if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
                McGenEventWrite_EtwEventWriteTransfer(
                  (unsigned int)*rgpChain,
                  (unsigned int)CheckProvFromCert,
                  dwError,
                  1,
                  (__int64)&v61);
              ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(
                                      v11,
                                      (*pChainContext->rgpChain)->rgpElement[(*pChainContext->rgpChain)->cElement - 1]->pCertContext,
                                      0,
                                      &v56);
              HostNameFromTargetName = ProvFromCertificate;
              if ( ProvFromCertificate )
              {
                if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                  McTemplateU0sq_EtwEventWriteTransfer(v44, v43, "FindProvFromCertificate", ProvFromCertificate);
                goto LABEL_29;
              }
              if ( v63 )
                *v63 = *(struct _GUID *)((char *)v56 + 8);
            }
          }
        }
        if ( v48 )
          RtlReleaseResource(Resource);
        goto LABEL_84;
      }
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        goto LABEL_62;
    }
    else if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    {
      dwError = pPolicyStatus.dwError;
LABEL_62:
      McTemplateU0qqq_EtwEventWriteTransfer(
        (_DWORD)v36,
        v35,
        dwError,
        pPolicyStatus.lChainIndex,
        pPolicyStatus.lElementIndex);
    }
LABEL_29:
    v15 = -1073741715;
LABEL_30:
    if ( v48 )
      RtlReleaseResource(Resource);
    goto LABEL_85;
  }
  LastError = GetLastError();
  HostNameFromTargetName = LastError;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v23, v22, "CertGetCertificateChain", LastError);
  if ( HostNameFromTargetName == 14 )
  {
    v15 = 0;
  }
  else
  {
    v15 = -1073741715;
    v18 = 0;
  }
  if ( v48 )
    RtlReleaseResource(Resource);
  if ( v18 )
LABEL_84:
    v15 = NetpApiStatusToNtStatus(HostNameFromTargetName);
LABEL_85:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v12 )
    LocalFree(v12);
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v59);
  return v15;
}

```

## disassembly

```asm
0x18000d51c  mov     [rsp-8+arg_0], rbx
0x18000d521  push    rbp
0x18000d522  push    rsi
0x18000d523  push    rdi
0x18000d524  push    r12
0x18000d526  push    r13
0x18000d528  push    r14
0x18000d52a  push    r15
0x18000d52c  lea     rbp, [rsp-40h]
0x18000d531  sub     rsp, 140h
0x18000d538  mov     rax, cs:__security_cookie
0x18000d53f  xor     rax, rsp
0x18000d542  mov     [rbp+70h+var_40], rax
0x18000d546  mov     rbx, r9
0x18000d549  mov     edi, r8d
0x18000d54c  mov     [rsp+170h+var_118], r8d
0x18000d551  mov     r15, rdx
0x18000d554  mov     r14, [rbp+70h+hAdditionalStore]
0x18000d55b  mov     rax, [rbp+70h+arg_28]
0x18000d562  mov     [rbp+70h+pCertContext], rax
0x18000d566  mov     rax, [rbp+70h+arg_30]
0x18000d56d  mov     [rbp+70h+var_50], rax
0x18000d571  mov     r13, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x18000d578  xor     r12d, r12d
0x18000d57b  mov     [rsp+170h+var_130], r12d
0x18000d580  xorps   xmm0, xmm0
0x18000d583  movups  xmmword ptr [rbp+70h+var_B0.cbSize], xmm0
0x18000d587  movups  xmmword ptr [rbp+70h+var_B0.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18000d58b  movups  xmmword ptr [rbp+70h+pPolicyPara.cbSize], xmm0
0x18000d58f  xorps   xmm1, xmm1
0x18000d592  xor     eax, eax
0x18000d594  movups  [rsp+170h+var_100], xmm1
0x18000d599  mov     [rbp+70h+var_F0], rax
0x18000d59d  mov     [rsp+170h+pChainContext], r12
0x18000d5a2  movups  xmmword ptr [rbp+70h+pPolicyStatus.cbSize], xmm0
0x18000d5a6  mov     [rbp+70h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18000d5aa  mov     [rbp+70h+var_C8], r12
0x18000d5ae  mov     esi, r12d
0x18000d5b1  mov     [rsp+170h+var_108], r12
0x18000d5b6  mov     [rbp+70h+var_D0], r12
0x18000d5ba  lea     rax, [rsp+170h+var_130]
0x18000d5bf  mov     [rsp+170h+pChainPara], rax; unsigned int *
0x18000d5c4  xor     r9d, r9d; int *
0x18000d5c7  lea     rdx, aCproviderregis_5; "CProviderRegistrationCache::ValidateCer"...
0x18000d5ce  lea     rcx, [rbp+70h+var_90]; this
0x18000d5d2  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x18000d5d7  nop
0x18000d5d8  test    edi, edi
0x18000d5da  jz      short loc_18000D61C
0x18000d5dc  lea     rcx, [r13+118h]; this
0x18000d5e3  call    ?IsPku2uDisabled@CIdentityPolicy@@QEAAHXZ; CIdentityPolicy::IsPku2uDisabled(void)
0x18000d5e8  test    eax, eax
0x18000d5ea  jz      short loc_18000D61C
0x18000d5ec  lea     edi, [r12+1]
0x18000d5f1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x18000d5f8  jz      short loc_18000D612
0x18000d5fa  lea     rax, [rbp+70h+var_60]
0x18000d5fe  mov     [rsp+170h+pChainPara], rax
0x18000d603  mov     r9d, edi
0x18000d606  lea     rdx, Pku2uDisabled
0x18000d60d  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d612  mov     ebx, 0C000006Dh
0x18000d617  jmp     loc_18000DAFA
0x18000d61c  mov     rcx, r13; this
0x18000d61f  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x18000d624  xor     r8d, r8d
0x18000d627  lea     rdx, [r13+10h]
0x18000d62b  lea     rcx, [rsp+170h+Resource]
0x18000d630  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x18000d635  xorps   xmm0, xmm0
0x18000d638  movups  xmmword ptr [rbp+70h+var_B0.cbSize], xmm0
0x18000d63c  movups  xmmword ptr [rbp+70h+var_B0.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18000d640  mov     [rbp+70h+var_B0.cbSize], 20h ; ' '
0x18000d647  mov     edi, 1
0x18000d64c  test    rbx, rbx
0x18000d64f  jz      short loc_18000D685
0x18000d651  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x18000d658  jz      short loc_18000D672
0x18000d65a  lea     rax, [rbp+70h+var_60]
0x18000d65e  mov     [rsp+170h+pChainPara], rax
0x18000d663  mov     r9d, edi
0x18000d666  lea     rdx, RIPolicySpecified
0x18000d66d  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d672  mov     eax, [rbx]
0x18000d674  mov     [rbp+70h+var_B0.RequestedUsage.dwType], eax
0x18000d677  mov     eax, [rbx+8]
0x18000d67a  mov     [rbp+70h+var_B0.RequestedUsage.Usage.cUsageIdentifier], eax
0x18000d67d  mov     rax, [rbx+10h]
0x18000d681  mov     [rbp+70h+var_B0.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18000d685  test    r14, r14
0x18000d688  jz      short loc_18000D692
0x18000d68a  mov     r9, [r14]
0x18000d68d  xor     r14d, r14d
0x18000d690  jmp     short loc_18000D695
0x18000d692  mov     r9, r14; hAdditionalStore
0x18000d695  lea     rax, [rsp+170h+pChainContext]
0x18000d69a  mov     [rsp+170h+ppChainContext], rax; ppChainContext
0x18000d69f  mov     [rsp+170h+pvReserved], r14; pvReserved
0x18000d6a4  mov     [rsp+170h+dwFlags], 0C0000004h; dwFlags
0x18000d6ac  lea     rax, [rbp+70h+var_B0]
0x18000d6b0  mov     [rsp+170h+pChainPara], rax; pChainPara
0x18000d6b5  xor     r8d, r8d; pTime
0x18000d6b8  mov     rdx, [rbp+70h+pCertContext]; pCertContext
0x18000d6bc  mov     rcx, [r13+88h]; hChainEngine
0x18000d6c3  call    cs:__imp_CertGetCertificateChain
0x18000d6c9  test    eax, eax
0x18000d6cb  jnz     short loc_18000D722
0x18000d6cd  call    cs:__imp_GetLastError
0x18000d6d3  mov     [rsp+170h+var_130], eax
0x18000d6d7  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000d6de  jz      short loc_18000D6EF
0x18000d6e0  mov     r9d, eax
0x18000d6e3  lea     r8, aCertgetcertifi; "CertGetCertificateChain"
0x18000d6ea  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000d6ef  cmp     [rsp+170h+var_130], 0Eh
0x18000d6f4  jz      short loc_18000D700
0x18000d6f6  mov     ebx, 0C000006Dh
0x18000d6fb  mov     edi, r14d
0x18000d6fe  jmp     short loc_18000D703
0x18000d700  mov     ebx, r14d
0x18000d703  cmp     [rsp+170h+var_120], r14b
0x18000d708  jz      short loc_18000D715
0x18000d70a  mov     rcx, [rsp+170h+Resource]; Resource
0x18000d70f  call    cs:__imp_RtlReleaseResource
0x18000d715  test    edi, edi
0x18000d717  jz      loc_18000DAFA
0x18000d71d  jmp     loc_18000DAEF
0x18000d722  mov     ebx, r14d
0x18000d725  mov     rcx, [rsp+170h+pChainContext]
0x18000d72a  test    rcx, rcx
0x18000d72d  jz      loc_18000D8AC
0x18000d733  cmp     dword ptr [rcx+0Ch], 0
0x18000d737  jbe     loc_18000D8AC
0x18000d73d  mov     rax, [rcx+10h]
0x18000d741  mov     rax, [rax]
0x18000d744  cmp     dword ptr [rax+0Ch], 0
0x18000d748  jbe     loc_18000D8AC
0x18000d74e  test    byte ptr [rax+4], 20h
0x18000d752  jz      short loc_18000D798
0x18000d754  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000d75b  jz      short loc_18000D775
0x18000d75d  lea     rax, [rbp+70h+var_60]
0x18000d761  mov     [rsp+170h+pChainPara], rax
0x18000d766  mov     r9d, edi
0x18000d769  lea     rdx, CertRootIsNotTrusted
0x18000d770  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d775  xor     r14d, r14d
0x18000d778  mov     ebx, 0C000006Dh
0x18000d77d  cmp     [rsp+170h+var_120], r14b
0x18000d782  jz      loc_18000DAFA
0x18000d788  mov     rcx, [rsp+170h+Resource]; Resource
0x18000d78d  call    cs:__imp_RtlReleaseResource
0x18000d793  jmp     loc_18000DAFA
0x18000d798  mov     rax, [rax+10h]
0x18000d79c  mov     rcx, [rax]
0x18000d79f  mov     ebx, [rcx+14h]
0x18000d7a2  and     ebx, 8
0x18000d7a5  cmp     [rsp+170h+var_118], 0
0x18000d7aa  jnz     loc_18000D8AC
0x18000d7b0  test    ebx, ebx
0x18000d7b2  jz      loc_18000D8AC
0x18000d7b8  test    r15, r15
0x18000d7bb  jz      loc_18000D8AC
0x18000d7c1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x18000d7c8  jz      short loc_18000D7E2
0x18000d7ca  lea     rax, [rbp+70h+var_60]
0x18000d7ce  mov     [rsp+170h+pChainPara], rax
0x18000d7d3  mov     r9d, edi
0x18000d7d6  lea     rdx, CertIsSelfSigned
0x18000d7dd  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d7e2  xor     r8d, r8d
0x18000d7e5  lea     rdx, [r13+10h]
0x18000d7e9  lea     rcx, [rbp+70h+var_60]
0x18000d7ed  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x18000d7f2  mov     rcx, [r13+140h]; hCertStore
0x18000d7f9  xor     r14d, r14d
0x18000d7fc  test    rcx, rcx
0x18000d7ff  jz      short loc_18000D86D
0x18000d801  mov     qword ptr [rsp+170h+dwFlags], r14; pPrevCertContext
0x18000d806  mov     r12, [rbp+70h+pCertContext]
0x18000d80a  mov     [rsp+170h+pChainPara], r12; pvFindPara
0x18000d80f  mov     r9d, 0D0000h; dwFindType
0x18000d815  xor     r8d, r8d; dwFindFlags
0x18000d818  mov     edx, 10001h; dwCertEncodingType
0x18000d81d  call    cs:__imp_CertFindCertificateInStore
0x18000d823  mov     r14, rax
0x18000d826  test    rax, rax
0x18000d829  jz      short loc_18000D86A
0x18000d82b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x18000d832  jz      short loc_18000D84C
0x18000d834  lea     rax, [rbp+70h+pCertContext]
0x18000d838  mov     [rsp+170h+pChainPara], rax
0x18000d83d  mov     r9d, edi
0x18000d840  lea     rdx, CertFoundInContainer
0x18000d847  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d84c  mov     rcx, r14; pCertContext
0x18000d84f  call    cs:__imp_CertFreeCertificateContext
0x18000d855  mov     r14d, edi
0x18000d858  cmp     [rbp+70h+var_58], 0
0x18000d85c  jz      short loc_18000D8B0
0x18000d85e  mov     rcx, [rbp+70h+var_60]; Resource
0x18000d862  call    cs:__imp_RtlReleaseResource
0x18000d868  jmp     short loc_18000D8B0
0x18000d86a  xor     r14d, r14d
0x18000d86d  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000d874  jz      short loc_18000D88E
0x18000d876  lea     rax, [rbp+70h+var_50]
0x18000d87a  mov     [rsp+170h+pChainPara], rax
0x18000d87f  mov     r9d, edi
0x18000d882  lea     rdx, CertNotFoundInHGContainer
0x18000d889  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d88e  mov     ebx, 0C000006Dh
0x18000d893  cmp     [rbp+70h+var_58], r14b
0x18000d897  jz      loc_18000D77D
0x18000d89d  mov     rcx, [rbp+70h+var_60]; Resource
0x18000d8a1  call    cs:__imp_RtlReleaseResource
0x18000d8a7  jmp     loc_18000D77D
0x18000d8ac  mov     r12, [rbp+70h+pCertContext]
0x18000d8b0  xorps   xmm0, xmm0
0x18000d8b3  xor     eax, eax
0x18000d8b5  movups  xmmword ptr [rbp+70h+pPolicyStatus.cbSize], xmm0
0x18000d8b9  mov     [rbp+70h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18000d8bd  xorps   xmm1, xmm1
0x18000d8c0  movups  [rsp+170h+var_100], xmm1
0x18000d8c5  mov     [rbp+70h+var_F0], rax
0x18000d8c9  mov     [rbp+70h+pPolicyPara.cbSize], 10h
0x18000d8d0  mov     eax, 18h
0x18000d8d5  mov     [rbp+70h+pPolicyStatus.cbSize], eax
0x18000d8d8  mov     dword ptr [rsp+170h+var_100], eax
0x18000d8dc  lea     rax, [rsp+170h+var_100]
0x18000d8e1  mov     [rbp+70h+pPolicyPara.pvExtraPolicyPara], rax
0x18000d8e5  mov     eax, 0F00h
0x18000d8ea  lea     ecx, [rax+10h]
0x18000d8ed  test    r14d, r14d
0x18000d8f0  cmovnz  eax, ecx
0x18000d8f3  mov     [rbp+70h+pPolicyPara.dwFlags], eax
0x18000d8f6  mov     r14d, [rsp+170h+var_118]
0x18000d8fb  test    r14d, r14d
0x18000d8fe  jnz     short loc_18000D978
0x18000d900  lea     r8, [rbp+70h+var_D0]; unsigned __int16 **
0x18000d904  lea     rdx, [rsp+170h+var_108]; unsigned __int16 **
0x18000d909  mov     rcx, r15; struct _UNICODE_STRING *
0x18000d90c  call    ?GetHostNameFromTargetName@@YAKPEAU_UNICODE_STRING@@PEAPEAG1@Z; GetHostNameFromTargetName(_UNICODE_STRING *,ushort * *,ushort * *)
0x18000d911  mov     [rsp+170h+var_130], eax
0x18000d915  xor     r14d, r14d
0x18000d918  test    eax, eax
0x18000d91a  jz      short loc_18000D938
0x18000d91c  cmp     [rsp+170h+var_120], r14b
0x18000d921  jz      short loc_18000D92E
0x18000d923  mov     rcx, [rsp+170h+Resource]; Resource
0x18000d928  call    cs:__imp_RtlReleaseResource
0x18000d92e  mov     rsi, [rsp+170h+var_108]
0x18000d933  jmp     loc_18000DAEF
0x18000d938  mov     rsi, [rsp+170h+var_108]
0x18000d93d  mov     r14, [rbp+70h+var_D0]
0x18000d941  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x18000d948  jz      short loc_18000D95C
0x18000d94a  mov     r9, r14
0x18000d94d  mov     r8, rsi
0x18000d950  lea     rdx, TargetNameAndHostName
0x18000d957  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000d95c  mov     dword ptr [rsp+170h+var_100], 18h
0x18000d964  mov     qword ptr [rsp+170h+var_100+4], 2
0x18000d96d  mov     [rbp+70h+var_F0], r14
0x18000d971  mov     r14d, [rsp+170h+var_118]
0x18000d976  jmp     short loc_18000D985
0x18000d978  mov     qword ptr [rsp+170h+var_100+4], rdi
0x18000d97d  mov     [rbp+70h+var_F0], 0
0x18000d985  lea     r9, [rbp+70h+pPolicyStatus]; pPolicyStatus
0x18000d989  lea     r8, [rbp+70h+pPolicyPara]; pPolicyPara
0x18000d98d  mov     rdx, [rsp+170h+pChainContext]; pChainContext
0x18000d992  mov     ecx, 4; pszPolicyOID
0x18000d997  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18000d99d  test    eax, eax
0x18000d99f  jnz     short loc_18000D9C7
0x18000d9a1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000d9a8  jz      loc_18000D775
0x18000d9ae  mov     r8d, [rbp+70h+pPolicyStatus.dwError]
0x18000d9b2  mov     eax, [rbp+70h+pPolicyStatus.lElementIndex]
0x18000d9b5  mov     r9d, [rbp+70h+pPolicyStatus.lChainIndex]
0x18000d9b9  mov     dword ptr [rsp+170h+pChainPara], eax
0x18000d9bd  call    McTemplateU0qqq_EtwEventWriteTransfer
0x18000d9c2  jmp     loc_18000D775
0x18000d9c7  mov     r8d, [rbp+70h+pPolicyStatus.dwError]
0x18000d9cb  test    r8d, r8d
0x18000d9ce  jz      short loc_18000D9DF
0x18000d9d0  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000d9d7  jz      loc_18000D775
0x18000d9dd  jmp     short loc_18000D9B2
0x18000d9df  test    r14d, r14d
0x18000d9e2  jz      short loc_18000DA26
0x18000d9e4  xor     r14d, r14d
0x18000d9e7  test    r15, r15
0x18000d9ea  jz      short loc_18000DA29
0x18000d9ec  cmp     [r15], r14w
0x18000d9f0  jz      short loc_18000DA29
0x18000d9f2  mov     r8, r15; struct _UNICODE_STRING *
0x18000d9f5  mov     rdx, r12; struct _CERT_CONTEXT *
0x18000d9f8  call    ?ValidateClientNameBinding@CProviderRegistrationCache@@AEAAKPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z; CProviderRegistrationCache::ValidateClientNameBinding(_CERT_CONTEXT const *,_UNICODE_STRING *)
0x18000d9fd  mov     [rsp+170h+var_130], eax
  ... truncated ...
```
