# KdcMyStoreWaitHandler(void *,uchar)

- ea: `0x180053ec0`
- end: `0x18005458f`
- name: `?KdcMyStoreWaitHandler@@YAXPEAXE@Z`
- size: `1743`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031090`

## callees

- `0x180003908`
- `0x180004d34`
- `0x18000508c`
- `0x1800053d4`
- `0x180005c74`
- `0x1800101c4`
- `0x1800101ec`
- `0x180010718`
- `0x1800107dc`
- `0x18004d9f0`
- `0x18004ea74`
- `0x1800504e4`
- `0x1800509ac`
- `0x180052e6c`
- `0x180053ec0`
- `0x18005a060`
- `0x18005a090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800542f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800543d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800542f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800543d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180053f3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180053f3f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005414e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180054192`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005414e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180054192`
- `CRYPT32!CertCompareCertificateName` at `0x180054362`
- `CRYPT32!CertCompareCertificateName` at `0x180054418`
- `CRYPT32!CertCompareCertificateName` at `0x180054362`
- `CRYPT32!CertCompareCertificateName` at `0x180054418`
- `CRYPT32!CertCompareCertificate` at `0x180054062`
- `CRYPT32!CertCompareCertificate` at `0x180054062`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180054439`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180054439`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005403c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180054134`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180054174`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005403c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180054134`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180054174`
- `CRYPT32!CertControlStore` at `0x180053f6c`
- `CRYPT32!CertControlStore` at `0x180053ff7`
- `CRYPT32!CertControlStore` at `0x18005400c`
- `CRYPT32!CertControlStore` at `0x180053f6c`
- `CRYPT32!CertControlStore` at `0x180053ff7`
- `CRYPT32!CertControlStore` at `0x18005400c`
- `CRYPT32!CertGetCertificateChain` at `0x1800542db`
- `CRYPT32!CertGetCertificateChain` at `0x1800542db`
- `CRYPT32!CertCloseServerOcspResponse` at `0x18005411d`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180054257`
- `CRYPT32!CertCloseServerOcspResponse` at `0x18005411d`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180054257`
- `CRYPT32!CertOpenServerOcspResponse` at `0x1800544a7`
- `CRYPT32!CertOpenServerOcspResponse` at `0x1800544a7`
- `CRYPT32!CertFreeCertificateContext` at `0x18005406f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800540b4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800540e0`
- `CRYPT32!CertFreeCertificateContext` at `0x1800541ee`
- `CRYPT32!CertFreeCertificateContext` at `0x18005421a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005406f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800540b4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800540e0`
- `CRYPT32!CertFreeCertificateContext` at `0x1800541ee`
- `CRYPT32!CertFreeCertificateContext` at `0x18005421a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall KdcMyStoreWaitHandler(PVOID a1, char a2)
{
  __int64 v3; // rax
  const struct _CERT_CONTEXT *v4; // rbx
  CSecurityData *v5; // rcx
  DWORD LastError; // eax
  int v7; // eax
  int v8; // r14d
  PCCERT_CONTEXT v9; // rax
  int v10; // edx
  const struct _CERT_CONTEXT *v11; // rcx
  PCCERT_CONTEXT *v12; // rax
  unsigned int i; // r14d
  const CERT_CONTEXT *v14; // rax
  const CERT_CONTEXT *v15; // rax
  PCCERT_CONTEXT *v16; // rax
  unsigned int j; // r14d
  __int64 v18; // rdx
  __int64 v19; // r8
  const CERT_CONTEXT *v20; // rbx
  DWORD v21; // eax
  PCCERT_CHAIN_CONTEXT v22; // r9
  DWORD v23; // ebx
  PCCERT_CONTEXT pCertContext; // rcx
  BOOL v25; // eax
  unsigned int v26; // edx
  DWORD v27; // eax
  __int64 v28; // rdx
  DWORD k; // ebx
  PCERT_SIMPLE_CHAIN v30; // rax
  PCCERT_CONTEXT v31; // rcx
  PCCERT_CONTEXT v32; // rax
  DWORD v33; // eax
  struct _RTL_CRITICAL_SECTION *v34; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v36[16]; // [rsp+48h] [rbp-81h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS v37; // [rsp+58h] [rbp-71h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS v38; // [rsp+70h] [rbp-59h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+90h] [rbp-39h] BYREF
  unsigned int v40; // [rsp+C8h] [rbp-1h]
  DWORD pcbData; // [rsp+140h] [rbp+77h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+148h] [rbp+7Fh] BYREF

  pChainContext = 0;
  memset(&v37, 0, sizeof(v37));
  pcbData = 0;
  v3 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(
         &lpCriticalSection,
         &pChainContext);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v36, v3);
  _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningType, 0);
  _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningState, 1);
  if ( !KdcCertStoreWait )
    goto LABEL_86;
  v4 = 0;
  GetSystemTimeAsFileTime(&KdcLastChangeEventTime);
  if ( !a2 || CertControlStore(KdcCertStore, 0, 5u, &KdcCertStoreChangeEvent) )
    goto LABEL_7;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, LastError);
LABEL_7:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x1000) != 0 )
    WPP_SF_(*((_QWORD *)v5 + 2), 127, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
LABEL_11:
  wil::EnterCriticalSection(&lpCriticalSection, &KdcGlobalCertCritSect);
  CertControlStore(KdcCertStore, 0, 2u, &KdcCertStoreChangeEvent);
  CertControlStore(KdcCertStore, 0, 1u, 0);
  if ( !KdcGlobalCert )
    goto LABEL_26;
  v7 = KdcCheckKdcCertificate(KdcGlobalCert, &v37);
  v8 = v7;
  if ( !v7 )
  {
    do
    {
      v9 = CertEnumCertificatesInStore(KdcCertStore, v4);
      v4 = v9;
      if ( !v9 )
        goto LABEL_26;
    }
    while ( !CertCompareCertificate(0x10001u, KdcGlobalCert->pCertInfo, v9->pCertInfo) );
    CertFreeCertificateContext(v4);
    v10 = 1;
    v11 = KdcGlobalCert;
    goto LABEL_84;
  }
  if ( v7 == 77 || (KdcEventWriteKdcCertLog(KdcGlobalCert, 2, v7, &v37), v8 != 74) )
  {
    if ( KdcGlobalCert )
    {
      CertFreeCertificateContext(KdcGlobalCert);
      KdcGlobalCert = 0;
    }
    v12 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates;
    if ( KdcGlobalAdditionalCertificates )
    {
      for ( i = 0; i < KdcGlobalAdditionalCertificatesCount; v12 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates )
        CertFreeCertificateContext(v12[i++]);
      MIDL_user_free(v12);
      KdcGlobalAdditionalCertificates = 0;
    }
    KdcGlobalAdditionalCertificatesCount = 0;
    if ( KdcGlobalCertOcspResponse )
    {
      CertCloseServerOcspResponse(KdcGlobalCertOcspResponse, 0);
      KdcGlobalCertOcspResponse = 0;
    }
  }
  do
  {
LABEL_26:
    v14 = CertEnumCertificatesInStore(KdcCertStore, v4);
    v4 = v14;
    if ( !v14 )
    {
      while ( 1 )
      {
        v15 = CertEnumCertificatesInStore(KdcCertStore, v4);
        v4 = v15;
        if ( !v15 )
          break;
        if ( CertGetCertificateContextProperty(v15, 2u, 0, &pcbData)
          && !(unsigned int)KdcCheckLegacyKdcCertificate(v4, &v38) )
        {
          _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningType, 2);
          _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningState, 2);
          goto LABEL_34;
        }
      }
      KdcGlobalKdcCertChainStatus = v37;
      _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningType, 1);
      _InterlockedExchange((volatile __int32 *)&KdcGlobalKdcCertWarningState, 2);
      v10 = 3;
      v11 = 0;
LABEL_84:
      KdcEventWriteKdcCertLog(v11, v10, 0, 0);
      goto LABEL_85;
    }
  }
  while ( !CertGetCertificateContextProperty(v14, 2u, 0, &pcbData) || (unsigned int)KdcCheckKdcCertificate(v4, &v38) );
LABEL_34:
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
  if ( KdcGlobalCert )
  {
    CertFreeCertificateContext(KdcGlobalCert);
    KdcGlobalCert = 0;
  }
  v16 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates;
  if ( KdcGlobalAdditionalCertificates )
  {
    for ( j = 0; j < KdcGlobalAdditionalCertificatesCount; v16 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates )
      CertFreeCertificateContext(v16[j++]);
    MIDL_user_free(v16);
    KdcGlobalAdditionalCertificates = 0;
  }
  KdcGlobalAdditionalCertificatesCount = 0;
  if ( KdcGlobalCertOcspResponse )
  {
    CertCloseServerOcspResponse(KdcGlobalCertOcspResponse, 0);
    KdcGlobalCertOcspResponse = 0;
  }
  KdcGlobalCert = v4;
  KdcEventWriteKdcCertLog(v4, 1, 0, 0);
  v20 = KdcGlobalCert;
  if ( !KdcGlobalCert )
    goto LABEL_85;
  memset_0(&pChainPara, 0, 0x60u);
  pChainPara.cbSize = 96;
  v40 = 1000 * KdcGlobalCRLRetrievalTimeout;
  if ( CertGetCertificateChain((HCERTCHAINENGINE)1, v20, 0, 0, &pChainPara, 0xC0000000, 0, &pChainContext) )
  {
    v22 = pChainContext;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v21);
    }
    v22 = 0;
    pChainContext = 0;
  }
  if ( v22 && v22->cChain && (v23 = 0, (*v22->rgpChain)->cElement) )
  {
    do
    {
      pCertContext = (*v22->rgpChain)->rgpElement[v23]->pCertContext;
      v25 = CertCompareCertificateName(
              pCertContext->dwCertEncodingType,
              &pCertContext->pCertInfo->Issuer,
              &pCertContext->pCertInfo->Subject);
      v26 = KdcGlobalAdditionalCertificatesCount;
      if ( !v25 )
        v26 = ++KdcGlobalAdditionalCertificatesCount;
      ++v23;
      v22 = pChainContext;
    }
    while ( v23 < (*pChainContext->rgpChain)->cElement );
  }
  else
  {
    v26 = KdcGlobalAdditionalCertificatesCount;
  }
  if ( !v26 )
  {
LABEL_75:
    KdcGlobalCertOcspResponse = CertOpenServerOcspResponse(v22, 0, 0);
    if ( !KdcGlobalCertOcspResponse
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v33 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v33);
    }
    v34 = lpCriticalSection;
    if ( lpCriticalSection )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&lpCriticalSection);
      LeaveCriticalSection(v34);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&lpCriticalSection);
    }
    lpCriticalSection = 0;
    if ( !KdcGlobalDHParametersInitialized )
      KdcCacheDHParameters();
    goto LABEL_85;
  }
  KdcGlobalAdditionalCertificates = MIDL_user_allocate(8LL * v26);
  KdcGlobalAdditionalCertificatesCount = 0;
  if ( KdcGlobalAdditionalCertificates )
  {
    for ( k = 0; ; ++k )
    {
      v22 = pChainContext;
      v30 = *pChainContext->rgpChain;
      if ( k >= v30->cElement )
        break;
      v31 = v30->rgpElement[k]->pCertContext;
      if ( !CertCompareCertificateName(v31->dwCertEncodingType, &v31->pCertInfo->Issuer, &v31->pCertInfo->Subject) )
      {
        v32 = CertDuplicateCertificateContext((*pChainContext->rgpChain)->rgpElement[k]->pCertContext);
        v18 = KdcGlobalAdditionalCertificatesCount;
        *((_QWORD *)KdcGlobalAdditionalCertificates + KdcGlobalAdditionalCertificatesCount) = v32;
        if ( !v32 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v27 = GetLastError();
            v28 = 131;
            goto LABEL_74;
          }
          goto LABEL_85;
        }
        ++KdcGlobalAdditionalCertificatesCount;
      }
    }
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v27 = GetLastError();
    v28 = 130;
LABEL_74:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v27);
  }
LABEL_85:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
    &lpCriticalSection,
    v18,
    v19);
LABEL_86:
  wil::details::lambda_call__lambda_835b27bb30fb9948345708223005f6e0___::_lambda_call__lambda_835b27bb30fb9948345708223005f6e0___(v36);
}

```

## disassembly

```asm
0x180053ec0  mov     [rsp-8+arg_0], rbx
0x180053ec5  push    rbp
0x180053ec6  push    rsi
0x180053ec7  push    rdi
0x180053ec8  push    r12
0x180053eca  push    r13
0x180053ecc  push    r14
0x180053ece  push    r15
0x180053ed0  lea     rbp, [rsp-27h]
0x180053ed5  sub     rsp, 0F0h
0x180053edc  mov     sil, dl
0x180053edf  xor     r15d, r15d
0x180053ee2  mov     [rbp+57h+pChainContext], r15
0x180053ee6  xorps   xmm0, xmm0
0x180053ee9  xor     eax, eax
0x180053eeb  movups  xmmword ptr [rbp+57h+var_C8.cbSize], xmm0
0x180053eef  mov     [rbp+57h+var_C8.pvExtraPolicyStatus], rax
0x180053ef3  mov     [rbp+57h+pcbData], r15d
0x180053ef7  lea     rdx, [rbp+57h+pChainContext]
0x180053efb  lea     rcx, [rsp+120h+lpCriticalSection]
0x180053f00  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x180053f05  mov     rdx, rax
0x180053f08  lea     rcx, [rsp+120h+var_D8]
0x180053f0d  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x180053f12  nop
0x180053f13  mov     eax, r15d
0x180053f16  xchg    eax, cs:?KdcGlobalKdcCertWarningType@@3KA; ulong KdcGlobalKdcCertWarningType
0x180053f1c  lea     edi, [r15+1]
0x180053f20  mov     eax, edi
0x180053f22  xchg    eax, cs:?KdcGlobalKdcCertWarningState@@3KA; ulong KdcGlobalKdcCertWarningState
0x180053f28  cmp     cs:?KdcCertStoreWait@@3PEAXEA, r15; void * KdcCertStoreWait
0x180053f2f  jz      loc_18005456A
0x180053f35  mov     ebx, r15d
0x180053f38  lea     rcx, ?KdcLastChangeEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180053f3f  call    cs:__imp_GetSystemTimeAsFileTime
0x180053f45  lea     r13, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180053f4c  lea     r12, WPP_GLOBAL_Control
0x180053f53  test    sil, sil
0x180053f56  jz      short loc_180053FA7
0x180053f58  lea     r9, ?KdcCertStoreChangeEvent@@3PEAXEA; pvCtrlPara
0x180053f5f  xor     edx, edx; dwFlags
0x180053f61  lea     r8d, [r15+5]; dwCtrlType
0x180053f65  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180053f6c  call    cs:__imp_CertControlStore
0x180053f72  test    eax, eax
0x180053f74  jnz     short loc_180053FA7
0x180053f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f7d  cmp     rcx, r12
0x180053f80  jz      short loc_180053FCD
0x180053f82  test    [rcx+1Ch], dil
0x180053f86  jz      short loc_180053FAE
0x180053f88  call    cs:__imp_GetLastError
0x180053f8e  lea     edx, [rdi+7Dh]
0x180053f91  mov     r9d, eax
0x180053f94  mov     r8, r13
0x180053f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f9e  mov     rcx, [rcx+10h]
0x180053fa2  call    WPP_SF_d
0x180053fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fae  cmp     rcx, r12
0x180053fb1  jz      short loc_180053FCD
0x180053fb3  test    dword ptr [rcx+1Ch], 1000h
0x180053fba  jz      short loc_180053FCD
0x180053fbc  mov     edx, 7Fh
0x180053fc1  mov     r8, r13
0x180053fc4  mov     rcx, [rcx+10h]
0x180053fc8  call    WPP_SF_
0x180053fcd  lea     rdx, ?KdcGlobalCertCritSect@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION KdcGlobalCertCritSect
0x180053fd4  lea     rcx, [rsp+120h+lpCriticalSection]
0x180053fd9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180053fde  nop
0x180053fdf  lea     r9, ?KdcCertStoreChangeEvent@@3PEAXEA; pvCtrlPara
0x180053fe6  mov     esi, 2
0x180053feb  mov     r8d, esi; dwCtrlType
0x180053fee  xor     edx, edx; dwFlags
0x180053ff0  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180053ff7  call    cs:__imp_CertControlStore
0x180053ffd  xor     r9d, r9d; pvCtrlPara
0x180054000  mov     r8d, edi; dwCtrlType
0x180054003  xor     edx, edx; dwFlags
0x180054005  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x18005400c  call    cs:__imp_CertControlStore
0x180054012  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; struct _CERT_CONTEXT *
0x180054019  test    rcx, rcx
0x18005401c  jz      loc_18005412A
0x180054022  lea     rdx, [rbp+57h+var_C8]; struct _CERT_CHAIN_POLICY_STATUS *
0x180054026  call    ?KdcCheckKdcCertificate@@YAJPEBU_CERT_CONTEXT@@PEAU_CERT_CHAIN_POLICY_STATUS@@@Z; KdcCheckKdcCertificate(_CERT_CONTEXT const *,_CERT_CHAIN_POLICY_STATUS *)
0x18005402b  mov     r14d, eax
0x18005402e  test    eax, eax
0x180054030  jnz     short loc_180054083
0x180054032  mov     rdx, rbx; pPrevCertContext
0x180054035  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x18005403c  call    cs:__imp_CertEnumCertificatesInStore
0x180054042  mov     rbx, rax
0x180054045  test    rax, rax
0x180054048  jz      loc_18005412A
0x18005404e  mov     r8, [rax+18h]; pCertId2
0x180054052  mov     rdx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const KdcGlobalCert
0x180054059  mov     rdx, [rdx+18h]; pCertId1
0x18005405d  mov     ecx, 10001h; dwCertEncodingType
0x180054062  call    cs:__imp_CertCompareCertificate
0x180054068  test    eax, eax
0x18005406a  jz      short loc_180054032
0x18005406c  mov     rcx, rbx; pCertContext
0x18005406f  call    cs:__imp_CertFreeCertificateContext
0x180054075  mov     edx, edi
0x180054077  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const KdcGlobalCert
0x18005407e  jmp     loc_180054553
0x180054083  cmp     r14d, 4Dh ; 'M'
0x180054087  jz      short loc_1800540A8
0x180054089  lea     r9, [rbp+57h+var_C8]; struct _CERT_CHAIN_POLICY_STATUS *
0x18005408d  mov     r8d, r14d; int
0x180054090  mov     edx, esi; unsigned int
0x180054092  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; struct _CERT_CONTEXT *
0x180054099  call    ?KdcEventWriteKdcCertLog@@YAXPEBU_CERT_CONTEXT@@KJPEAU_CERT_CHAIN_POLICY_STATUS@@@Z; KdcEventWriteKdcCertLog(_CERT_CONTEXT const *,ulong,long,_CERT_CHAIN_POLICY_STATUS *)
0x18005409e  cmp     r14d, 4Ah ; 'J'
0x1800540a2  jz      loc_18005412A
0x1800540a8  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x1800540af  test    rcx, rcx
0x1800540b2  jz      short loc_1800540C1
0x1800540b4  call    cs:__imp_CertFreeCertificateContext
0x1800540ba  mov     cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB, r15; _CERT_CONTEXT const * const KdcGlobalCert
0x1800540c1  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x1800540c8  test    rax, rax
0x1800540cb  jz      short loc_180054108
0x1800540cd  mov     r14d, r15d
0x1800540d0  cmp     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, r15d; ulong KdcGlobalAdditionalCertificatesCount
0x1800540d7  jbe     short loc_1800540F9
0x1800540d9  mov     ecx, r14d
0x1800540dc  mov     rcx, [rax+rcx*8]; pCertContext
0x1800540e0  call    cs:__imp_CertFreeCertificateContext
0x1800540e6  add     r14d, edi
0x1800540e9  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x1800540f0  cmp     r14d, cs:?KdcGlobalAdditionalCertificatesCount@@3KA; ulong KdcGlobalAdditionalCertificatesCount
0x1800540f7  jb      short loc_1800540D9
0x1800540f9  mov     rcx, rax; void *
0x1800540fc  call    MIDL_user_free
0x180054101  mov     cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA, r15; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180054108  mov     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, r15d; ulong KdcGlobalAdditionalCertificatesCount
0x18005410f  mov     rcx, cs:?KdcGlobalCertOcspResponse@@3PEAXEA; hServerOcspResponse
0x180054116  test    rcx, rcx
0x180054119  jz      short loc_18005412A
0x18005411b  xor     edx, edx; dwFlags
0x18005411d  call    cs:__imp_CertCloseServerOcspResponse
0x180054123  mov     cs:?KdcGlobalCertOcspResponse@@3PEAXEA, r15; void * KdcGlobalCertOcspResponse
0x18005412a  mov     rdx, rbx; pPrevCertContext
0x18005412d  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180054134  call    cs:__imp_CertEnumCertificatesInStore
0x18005413a  mov     rbx, rax
0x18005413d  test    rax, rax
0x180054140  jz      short loc_18005416A
0x180054142  lea     r9, [rbp+57h+pcbData]; pcbData
0x180054146  xor     r8d, r8d; pvData
0x180054149  mov     edx, esi; dwPropId
0x18005414b  mov     rcx, rax; pCertContext
0x18005414e  call    cs:__imp_CertGetCertificateContextProperty
0x180054154  test    eax, eax
0x180054156  jz      short loc_18005412A
0x180054158  lea     rdx, [rbp+57h+var_B0]; struct _CERT_CHAIN_POLICY_STATUS *
0x18005415c  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18005415f  call    ?KdcCheckKdcCertificate@@YAJPEBU_CERT_CONTEXT@@PEAU_CERT_CHAIN_POLICY_STATUS@@@Z; KdcCheckKdcCertificate(_CERT_CONTEXT const *,_CERT_CHAIN_POLICY_STATUS *)
0x180054164  test    eax, eax
0x180054166  jnz     short loc_18005412A
0x180054168  jmp     short loc_1800541BC
0x18005416a  mov     rdx, rbx; pPrevCertContext
0x18005416d  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180054174  call    cs:__imp_CertEnumCertificatesInStore
0x18005417a  mov     rbx, rax
0x18005417d  test    rax, rax
0x180054180  jz      loc_180054528
0x180054186  lea     r9, [rbp+57h+pcbData]; pcbData
0x18005418a  xor     r8d, r8d; pvData
0x18005418d  mov     edx, esi; dwPropId
0x18005418f  mov     rcx, rax; pCertContext
0x180054192  call    cs:__imp_CertGetCertificateContextProperty
0x180054198  test    eax, eax
0x18005419a  jz      short loc_18005416A
0x18005419c  lea     rdx, [rbp+57h+var_B0]; struct _CERT_CHAIN_POLICY_STATUS *
0x1800541a0  mov     rcx, rbx; struct _CERT_CONTEXT *
0x1800541a3  call    ?KdcCheckLegacyKdcCertificate@@YAJPEBU_CERT_CONTEXT@@PEAU_CERT_CHAIN_POLICY_STATUS@@@Z; KdcCheckLegacyKdcCertificate(_CERT_CONTEXT const *,_CERT_CHAIN_POLICY_STATUS *)
0x1800541a8  test    eax, eax
0x1800541aa  jnz     short loc_18005416A
0x1800541ac  mov     eax, esi
0x1800541ae  xchg    eax, cs:?KdcGlobalKdcCertWarningType@@3KA; ulong KdcGlobalKdcCertWarningType
0x1800541b4  mov     ecx, esi
0x1800541b6  xchg    ecx, cs:?KdcGlobalKdcCertWarningState@@3KA; ulong KdcGlobalKdcCertWarningState
0x1800541bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541c3  cmp     rcx, r12
0x1800541c6  jz      short loc_1800541E2
0x1800541c8  test    dword ptr [rcx+1Ch], 1000h
0x1800541cf  jz      short loc_1800541E2
0x1800541d1  mov     edx, 80h
0x1800541d6  mov     r8, r13
0x1800541d9  mov     rcx, [rcx+10h]
0x1800541dd  call    WPP_SF_
0x1800541e2  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x1800541e9  test    rcx, rcx
0x1800541ec  jz      short loc_1800541FB
0x1800541ee  call    cs:__imp_CertFreeCertificateContext
0x1800541f4  mov     cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB, r15; _CERT_CONTEXT const * const KdcGlobalCert
0x1800541fb  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180054202  test    rax, rax
0x180054205  jz      short loc_180054242
0x180054207  mov     r14d, r15d
0x18005420a  cmp     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, r15d; ulong KdcGlobalAdditionalCertificatesCount
0x180054211  jbe     short loc_180054233
0x180054213  mov     ecx, r14d
0x180054216  mov     rcx, [rax+rcx*8]; pCertContext
0x18005421a  call    cs:__imp_CertFreeCertificateContext
0x180054220  add     r14d, edi
0x180054223  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x18005422a  cmp     r14d, cs:?KdcGlobalAdditionalCertificatesCount@@3KA; ulong KdcGlobalAdditionalCertificatesCount
0x180054231  jb      short loc_180054213
0x180054233  mov     rcx, rax; void *
0x180054236  call    MIDL_user_free
0x18005423b  mov     cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA, r15; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180054242  mov     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, r15d; ulong KdcGlobalAdditionalCertificatesCount
0x180054249  mov     rcx, cs:?KdcGlobalCertOcspResponse@@3PEAXEA; hServerOcspResponse
0x180054250  test    rcx, rcx
0x180054253  jz      short loc_180054264
0x180054255  xor     edx, edx; dwFlags
0x180054257  call    cs:__imp_CertCloseServerOcspResponse
0x18005425d  mov     cs:?KdcGlobalCertOcspResponse@@3PEAXEA, r15; void * KdcGlobalCertOcspResponse
0x180054264  mov     cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB, rbx; _CERT_CONTEXT const * const KdcGlobalCert
0x18005426b  xor     r9d, r9d; struct _CERT_CHAIN_POLICY_STATUS *
0x18005426e  xor     r8d, r8d; int
0x180054271  mov     edx, edi; unsigned int
0x180054273  mov     rcx, rbx; struct _CERT_CONTEXT *
0x180054276  call    ?KdcEventWriteKdcCertLog@@YAXPEBU_CERT_CONTEXT@@KJPEAU_CERT_CHAIN_POLICY_STATUS@@@Z; KdcEventWriteKdcCertLog(_CERT_CONTEXT const *,ulong,long,_CERT_CHAIN_POLICY_STATUS *)
0x18005427b  mov     rbx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const KdcGlobalCert
0x180054282  test    rbx, rbx
0x180054285  jz      loc_18005455F
0x18005428b  mov     r14d, 60h ; '`'
0x180054291  mov     r8d, r14d; Size
0x180054294  xor     edx, edx; Val
0x180054296  lea     rcx, [rbp+57h+var_90]; void *
0x18005429a  call    memset_0
0x18005429f  mov     [rbp+57h+var_90.cbSize], r14d
0x1800542a3  imul    eax, cs:?KdcGlobalCRLRetrievalTimeout@@3KA, 3E8h; ulong KdcGlobalCRLRetrievalTimeout
0x1800542ad  mov     [rbp+57h+var_58], eax
0x1800542b0  lea     rax, [rbp+57h+pChainContext]
0x1800542b4  mov     [rsp+120h+ppChainContext], rax; ppChainContext
0x1800542b9  mov     [rsp+120h+pvReserved], r15; pvReserved
0x1800542be  mov     [rsp+120h+dwFlags], 0C0000000h; dwFlags
0x1800542c6  lea     rax, [rbp+57h+var_90]
0x1800542ca  mov     [rsp+120h+pChainPara], rax; pChainPara
0x1800542cf  xor     r9d, r9d; hAdditionalStore
0x1800542d2  xor     r8d, r8d; pTime
0x1800542d5  mov     rdx, rbx; pCertContext
0x1800542d8  mov     rcx, rdi; hChainEngine
0x1800542db  call    cs:__imp_CertGetCertificateChain
0x1800542e1  test    eax, eax
0x1800542e3  jnz     short loc_180054320
0x1800542e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800542ec  cmp     rax, r12
0x1800542ef  jz      short loc_180054317
0x1800542f1  test    [rax+1Ch], sil
0x1800542f5  jz      short loc_180054317
0x1800542f7  call    cs:__imp_GetLastError
0x1800542fd  lea     edx, [r14+21h]
0x180054301  mov     r9d, eax
0x180054304  mov     r8, r13
0x180054307  mov     rcx, cs:WPP_GLOBAL_Control
0x18005430e  mov     rcx, [rcx+10h]
0x180054312  call    WPP_SF_d
0x180054317  mov     r9, r15
0x18005431a  mov     [rbp+57h+pChainContext], r15
0x18005431e  jmp     short loc_180054324
0x180054320  mov     r9, [rbp+57h+pChainContext]
0x180054324  test    r9, r9
0x180054327  jz      short loc_18005438E
0x180054329  cmp     [r9+0Ch], edi
0x18005432d  jb      short loc_18005438E
0x18005432f  mov     ebx, r15d
0x180054332  mov     rax, [r9+10h]
0x180054336  mov     rcx, [rax]
0x180054339  cmp     [rcx+0Ch], r15d
0x18005433d  jbe     short loc_18005438E
0x18005433f  mov     rax, [r9+10h]
0x180054343  mov     rax, [rax]
0x180054346  mov     ecx, ebx
0x180054348  mov     rax, [rax+10h]
0x18005434c  mov     rcx, [rax+rcx*8]
0x180054350  mov     rcx, [rcx+8]
0x180054354  mov     rdx, [rcx+18h]
0x180054358  lea     r8, [rdx+50h]; pCertName2
0x18005435c  add     rdx, 30h ; '0'; pCertName1
0x180054360  mov     ecx, [rcx]; dwCertEncodingType
0x180054362  call    cs:__imp_CertCompareCertificateName
0x180054368  mov     edx, cs:?KdcGlobalAdditionalCertificatesCount@@3KA; ulong KdcGlobalAdditionalCertificatesCount
0x18005436e  test    eax, eax
0x180054370  jnz     short loc_18005437A
0x180054372  add     edx, edi
0x180054374  mov     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, edx; ulong KdcGlobalAdditionalCertificatesCount
0x18005437a  add     ebx, edi
0x18005437c  mov     r9, [rbp+57h+pChainContext]
0x180054380  mov     rax, [r9+10h]
0x180054384  mov     rcx, [rax]
0x180054387  cmp     ebx, [rcx+0Ch]
0x18005438a  jb      short loc_18005433F
  ... truncated ...
```
