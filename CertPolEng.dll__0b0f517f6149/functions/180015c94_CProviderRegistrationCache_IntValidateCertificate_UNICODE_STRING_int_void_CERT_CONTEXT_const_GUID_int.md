# CProviderRegistrationCache::IntValidateCertificate(_UNICODE_STRING *,int,void * *,_CERT_CONTEXT const *,_GUID *,int *)

- ea: `0x180015c94`
- end: `0x180016326`
- name: `?IntValidateCertificate@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@HPEAPEAXPEBU_CERT_CONTEXT@@PEAU_GUID@@PEAH@Z`
- size: `1682`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _UNICODE_STRING *, int *, void **, const struct _CERT_CONTEXT *, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800136b0`

## callees

- `0x180003dc0`
- `0x180006fa0`
- `0x180007b70`
- `0x180007bc0`
- `0x180007da0`
- `0x180007ea0`
- `0x180009510`
- `0x18000c180`
- `0x18000c344`
- `0x180015c94`
- `0x180016f84`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f2f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161e4`
- `RPCRT4!UuidEqual` at `0x180015e6f`
- `RPCRT4!UuidEqual` at `0x180015e88`
- `RPCRT4!UuidEqual` at `0x180015e6f`
- `RPCRT4!UuidEqual` at `0x180015e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001626b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001627a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001626b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001627a`
- `CRYPT32!CertFreeCertificateChain` at `0x1800162b1`
- `CRYPT32!CertFreeCertificateChain` at `0x1800162b1`
- `CRYPT32!CertGetCertificateChain` at `0x180015f22`
- `CRYPT32!CertGetCertificateChain` at `0x180015f22`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180016036`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180016036`
- `CRYPT32!CertGetNameStringW` at `0x180016125`
- `CRYPT32!CertGetNameStringW` at `0x1800161a8`
- `CRYPT32!CertGetNameStringW` at `0x180016125`
- `CRYPT32!CertGetNameStringW` at `0x1800161a8`
- `ntdll!RtlAllocateHeap` at `0x18001615e`
- `ntdll!RtlAllocateHeap` at `0x18001615e`
- `ntdll!RtlReleaseResource` at `0x180015e4d`
- `ntdll!RtlReleaseResource` at `0x1800160d5`
- `ntdll!RtlReleaseResource` at `0x18001623b`
- `ntdll!RtlReleaseResource` at `0x18001625d`
- `ntdll!RtlReleaseResource` at `0x180015e4d`
- `ntdll!RtlReleaseResource` at `0x1800160d5`
- `ntdll!RtlReleaseResource` at `0x18001623b`
- `ntdll!RtlReleaseResource` at `0x18001625d`
- `ntdll!RtlFreeHeap` at `0x180016297`
- `ntdll!RtlFreeHeap` at `0x180016297`

## string_xrefs

- `0x180015cee`: `CProviderRegistrationCache::IntValidateCertificate`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntValidateCertificate(
        CProviderRegistrationCache *this,
        struct _UNICODE_STRING *a2,
        int *a3,
        void **a4,
        const struct _CERT_CONTEXT *a5,
        struct _GUID *a6,
        int *a7)
{
  CProviderRegistrationCache *v7; // rbx
  WCHAR *v8; // rsi
  int v10; // edi
  PCERT_SIMPLE_CHAIN v11; // rdx
  int v12; // ecx
  int v13; // r8d
  int ProvFromCertificate; // eax
  __int64 v15; // rcx
  struct CProviderEntry *v16; // r13
  UUID *v17; // rbx
  DWORD dwFlags; // ecx
  unsigned int v19; // ebx
  void *v20; // r9
  DWORD LastError; // eax
  __int64 v22; // rcx
  PCCERT_CHAIN_CONTEXT v23; // rcx
  WCHAR *v24; // r14
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  DWORD v26; // edx
  int v27; // ebx
  int v28; // ecx
  DWORD dwError; // r8d
  unsigned int HostNameFromTargetName; // eax
  __int64 v31; // rcx
  signed int v32; // ebx
  const CERT_CONTEXT *v33; // r12
  DWORD NameStringW; // eax
  DWORD v35; // ebx
  WCHAR *Heap; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  const WCHAR *i; // rbx
  __int64 v40; // rax
  PCCERT_CHAIN_CONTEXT v41; // rcx
  unsigned int v42; // ebx
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  RPC_STATUS Status; // [rsp+44h] [rbp-BCh] BYREF
  PCNZWCH lpString2; // [rsp+48h] [rbp-B8h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  int v49; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h]
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+88h] [rbp-78h] BYREF
  struct CProviderEntry *v54; // [rsp+A0h] [rbp-60h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  void **v57; // [rsp+B8h] [rbp-48h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v59[32]; // [rsp+E0h] [rbp-20h] BYREF
  PRTL_RESOURCE Resource; // [rsp+100h] [rbp+0h] BYREF
  char v61; // [rsp+108h] [rbp+8h]

  v7 = g_pProvRegCache;
  v8 = 0;
  v44 = 0;
  Status = 0;
  v54 = 0;
  v49 = 0;
  v10 = (int)a3;
  pChainContext = 0;
  lpString2 = 0;
  hMem = 0;
  v57 = a4;
  v48 = (int)a3;
  pCertContext = a5;
  memset(&pChainPara, 0, sizeof(pChainPara));
  v52 = 0;
  pPolicyPara = 0;
  v51 = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v59, "CProviderRegistrationCache::IntValidateCertificate", a3, &v44, 0);
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( !*((_DWORD *)v7 + 2) )
  {
    v44 = -1073283051;
    goto LABEL_102;
  }
  if ( (unsigned int)CIdentityPolicy::IsPku2uDisabled((CProviderRegistrationCache *)((char *)v7 + 280)) )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v12, (unsigned int)Pku2uDisabled, v13, 1, (__int64)&Resource);
    v44 = -1073281812;
    goto LABEL_102;
  }
  if ( !a5 || !v10 && (!a2 || !a2->Buffer || !a2->Length) )
  {
    v44 = -1073741811;
    goto LABEL_102;
  }
  CAutoRtlLock::CAutoRtlLock(&Resource, (char *)v7 + 16, 0);
  ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(v7, a5, 1, &v54);
  if ( ProvFromCertificate )
  {
    if ( ProvFromCertificate > 0 )
      v15 = (unsigned __int16)ProvFromCertificate | 0xC0070000;
    else
      v15 = (unsigned int)ProvFromCertificate;
    v44 = v15;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v15, v11, "FindProvFromCertificate", (unsigned int)ProvFromCertificate);
    goto LABEL_22;
  }
  v16 = v54;
  v17 = (UUID *)((char *)v54 + 8);
  if ( UuidEqual((UUID *)((char *)v54 + 8), (UUID *)&Uuid2, &Status) || UuidEqual(v17, (UUID *)&Uuid1, &Status) )
  {
    dwFlags = -1073741820;
    v19 = 32;
    if ( a6 )
      *a6 = Uuid1;
  }
  else
  {
    dwFlags = 0x40000000;
    if ( a6 )
      *a6 = *v17;
    v19 = ((*((_BYTE *)v16 + 2144) & 1) == 0) | 0xFEFFFFBE;
  }
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  if ( v57 )
    v20 = *v57;
  else
    v20 = 0;
  if ( !CertGetCertificateChain(
          *((HCERTCHAINENGINE *)v16 + 266),
          pCertContext,
          0,
          v20,
          &pChainPara,
          dwFlags,
          0,
          &pChainContext) )
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v22, v11, "CertGetCertificateChain", LastError);
    goto LABEL_22;
  }
  v23 = pChainContext;
  v24 = 0;
  if ( !pChainContext
    || !pChainContext->cChain
    || (rgpChain = pChainContext->rgpChain, v11 = *rgpChain, !(*rgpChain)->cElement) )
  {
    v44 = -2146762486;
    if ( !v61 )
      goto LABEL_102;
    goto LABEL_94;
  }
  if ( (v19 & v11->TrustStatus.dwErrorStatus) != 0 )
  {
    v44 = -2146762486;
    goto LABEL_22;
  }
  if ( a7 && (v11->TrustStatus.dwErrorStatus & 0x1000000) != 0 )
    *a7 = 1;
  pPolicyPara.cbSize = 16;
  v26 = 3840;
  v52 = 0;
  pPolicyPara.dwFlags = 3840;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyStatus.cbSize = 24;
  v51 = 0;
  LODWORD(v51) = 24;
  pPolicyPara.pvExtraPolicyPara = &v51;
  if ( ((*v23->rgpChain)->TrustStatus.dwInfoStatus & 8) != 0 )
    v26 = 3856;
  pPolicyPara.dwFlags = v26;
  if ( (*((_BYTE *)v16 + 2144) & 1) != 0 )
    pPolicyPara.dwFlags = v26 | 1;
  v27 = v48;
  v52 = 0;
  *(_QWORD *)((char *)&v51 + 4) = 2;
  if ( v48 )
    *(_QWORD *)((char *)&v51 + 4) = 1;
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
    {
LABEL_56:
      v44 = -2146762477;
LABEL_22:
      if ( v61 )
        RtlReleaseResource(Resource);
      goto LABEL_102;
    }
    dwError = pPolicyStatus.dwError;
LABEL_55:
    McTemplateU0qqq_EtwEventWriteTransfer(
      v28,
      (_DWORD)v11,
      dwError,
      pPolicyStatus.lChainIndex,
      pPolicyStatus.lElementIndex);
    goto LABEL_56;
  }
  dwError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_56;
    goto LABEL_55;
  }
  if ( v27 )
    goto LABEL_90;
  HostNameFromTargetName = IntGetHostNameFromTargetName(
                             a2,
                             &v49,
                             (unsigned __int16 **)&lpString2,
                             (unsigned __int16 **)&hMem);
  v32 = HostNameFromTargetName;
  if ( HostNameFromTargetName )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v31, v11, "IntGetHostNameFromTargetName", HostNameFromTargetName);
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0xC0070000;
    v44 = v32;
    if ( v61 )
      RtlReleaseResource(Resource);
    v8 = (WCHAR *)lpString2;
    goto LABEL_95;
  }
  v8 = (WCHAR *)lpString2;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0zz_EtwEventWriteTransfer(v31, TargetNameAndHostName, &qword_180020CC0, lpString2);
  v33 = pCertContext;
  NameStringW = CertGetNameStringW(pCertContext, 6u, 2u, 0, 0, 0);
  v35 = NameStringW;
  if ( NameStringW < 2 )
  {
    v44 = -2146762476;
    goto LABEL_73;
  }
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * NameStringW);
  v24 = Heap;
  if ( Heap )
  {
    if ( CertGetNameStringW(v33, 6u, 2u, 0, Heap, v35) < 2 )
    {
      v44 = -1073281713;
      goto LABEL_73;
    }
    for ( i = v24; *i; i += v40 + 1 )
    {
      if ( CompareStringW(0x400u, 1u, i, -1, v8, -1) == 2 )
        goto LABEL_90;
      v40 = -1;
      do
        ++v40;
      while ( i[v40] );
    }
    v44 = -2146762476;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v38, v11, "Cert_Name_Checking", 2148204820LL);
    if ( a7 )
      *a7 = 1;
LABEL_90:
    if ( v61 )
      RtlReleaseResource(Resource);
    v44 = 0;
    goto LABEL_95;
  }
  v44 = -1073741801;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v37, v11, "RtlAllocateHeap", 3221225495LL);
LABEL_73:
  if ( v61 )
LABEL_94:
    RtlReleaseResource(Resource);
LABEL_95:
  if ( v8 )
    LocalFree(v8);
  if ( hMem )
    LocalFree(hMem);
  if ( v24 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
LABEL_102:
  v41 = pChainContext;
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v44 < 0 && v44 != -1073741801 && v44 != -1073741670 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v41, v11, "IntValidateCertificate(actual error)", (unsigned int)v44);
    v44 = -1073741715;
  }
  v42 = v44;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v59);
  return v42;
}

```

## disassembly

```asm
0x180015c94  mov     [rsp-8+arg_0], rbx
0x180015c99  push    rbp
0x180015c9a  push    rsi
0x180015c9b  push    rdi
0x180015c9c  push    r12
0x180015c9e  push    r13
0x180015ca0  push    r14
0x180015ca2  push    r15
0x180015ca4  lea     rbp, [rsp-20h]
0x180015ca9  sub     rsp, 120h
0x180015cb0  mov     rax, cs:__security_cookie
0x180015cb7  xor     rax, rsp
0x180015cba  mov     [rbp+50h+var_40], rax
0x180015cbe  mov     r13, [rbp+50h+arg_20]
0x180015cc5  xor     ecx, ecx
0x180015cc7  mov     r14, [rbp+50h+arg_28]
0x180015cce  xorps   xmm0, xmm0
0x180015cd1  mov     r15, [rbp+50h+arg_30]
0x180015cd8  xor     eax, eax
0x180015cda  mov     rbx, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180015ce1  mov     esi, ecx
0x180015ce3  mov     [rsp+150h+var_110], ecx
0x180015ce7  mov     r12, rdx
0x180015cea  mov     [rsp+150h+Status], ecx
0x180015cee  lea     rdx, aCproviderregis_17; "CProviderRegistrationCache::IntValidate"...
0x180015cf5  mov     [rbp+50h+var_B0], rcx
0x180015cf9  xorps   xmm1, xmm1
0x180015cfc  mov     [rsp+150h+var_F4], ecx
0x180015d00  mov     edi, r8d
0x180015d03  mov     [rsp+150h+pChainContext], rcx
0x180015d08  mov     [rsp+150h+lpString2], rcx
0x180015d0d  mov     [rbp+50h+hMem], rcx
0x180015d11  mov     [rsp+150h+pChainPara], rcx; unsigned int *
0x180015d16  lea     rcx, [rbp+50h+var_70]; this
0x180015d1a  mov     [rbp+50h+var_98], r9
0x180015d1e  lea     r9, [rsp+150h+var_110]; int *
0x180015d23  mov     [rsp+150h+var_F8], r8d
0x180015d28  mov     [rbp+50h+pCertContext], r13
0x180015d2c  movups  xmmword ptr [rbp+50h+var_90.cbSize], xmm0
0x180015d30  mov     [rbp+50h+var_D0], rax
0x180015d34  movups  xmmword ptr [rbp+50h+var_90.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180015d38  mov     [rbp+50h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180015d3c  movups  xmmword ptr [rsp+150h+pPolicyPara.cbSize], xmm0
0x180015d41  movups  [rsp+150h+var_E0], xmm1
0x180015d46  movups  xmmword ptr [rbp+50h+pPolicyStatus.cbSize], xmm0
0x180015d4a  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180015d4f  test    r14, r14
0x180015d52  jz      short loc_180015D5B
0x180015d54  xorps   xmm0, xmm0
0x180015d57  movups  xmmword ptr [r14], xmm0
0x180015d5b  test    r15, r15
0x180015d5e  jz      short loc_180015D63
0x180015d60  mov     [r15], esi
0x180015d63  cmp     [rbx+8], esi
0x180015d66  jnz     short loc_180015D75
0x180015d68  mov     [rsp+150h+var_110], 0C0070015h
0x180015d70  jmp     loc_1800162A7
0x180015d75  lea     rcx, [rbx+118h]; this
0x180015d7c  call    ?IsPku2uDisabled@CIdentityPolicy@@QEAAHXZ; CIdentityPolicy::IsPku2uDisabled(void)
0x180015d81  test    eax, eax
0x180015d83  jz      short loc_180015DB8
0x180015d85  mov     edi, 1
0x180015d8a  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x180015d91  jz      short loc_180015DAB
0x180015d93  lea     rax, [rbp+50h+Resource]
0x180015d97  mov     r9d, edi
0x180015d9a  lea     rdx, Pku2uDisabled
0x180015da1  mov     [rsp+150h+pChainPara], rax
0x180015da6  call    McGenEventWrite_EtwEventWriteTransfer
0x180015dab  mov     [rsp+150h+var_110], 0C00704ECh
0x180015db3  jmp     loc_1800162A7
0x180015db8  test    r13, r13
0x180015dbb  jz      loc_18001629F
0x180015dc1  test    edi, edi
0x180015dc3  jnz     short loc_180015DE6
0x180015dc5  test    r12, r12
0x180015dc8  jz      loc_18001629F
0x180015dce  cmp     [r12+8], rsi
0x180015dd3  jz      loc_18001629F
0x180015dd9  xor     eax, eax
0x180015ddb  cmp     ax, [r12]
0x180015de0  jz      loc_18001629F
0x180015de6  lea     rdx, [rbx+10h]
0x180015dea  xor     r8d, r8d
0x180015ded  lea     rcx, [rbp+50h+Resource]
0x180015df1  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x180015df6  mov     edi, 1
0x180015dfb  lea     r9, [rbp+50h+var_B0]; struct CProviderEntry **
0x180015dff  mov     r8d, edi; int
0x180015e02  mov     rdx, r13; struct _CERT_CONTEXT *
0x180015e05  mov     rcx, rbx; this
0x180015e08  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x180015e0d  xor     r13d, r13d
0x180015e10  test    eax, eax
0x180015e12  jz      short loc_180015E58
0x180015e14  jg      short loc_180015E1A
0x180015e16  mov     ecx, eax
0x180015e18  jmp     short loc_180015E23
0x180015e1a  movzx   ecx, ax
0x180015e1d  or      ecx, 0C0070000h
0x180015e23  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180015e2a  mov     [rsp+150h+var_110], ecx
0x180015e2e  jz      short loc_180015E3F
0x180015e30  mov     r9d, eax
0x180015e33  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x180015e3a  call    McTemplateU0sq_EtwEventWriteTransfer
0x180015e3f  cmp     [rbp+50h+var_48], r13b
0x180015e43  jz      loc_1800162A7
0x180015e49  mov     rcx, [rbp+50h+Resource]; Resource
0x180015e4d  call    cs:__imp_RtlReleaseResource
0x180015e53  jmp     loc_1800162A7
0x180015e58  mov     r13, [rbp+50h+var_B0]
0x180015e5c  lea     r8, [rsp+150h+Status]; Status
0x180015e61  lea     rdx, Uuid2; Uuid2
0x180015e68  lea     rbx, [r13+8]
0x180015e6c  mov     rcx, rbx; Uuid1
0x180015e6f  call    cs:__imp_UuidEqual
0x180015e75  test    eax, eax
0x180015e77  jnz     short loc_180015EBA
0x180015e79  lea     r8, [rsp+150h+Status]; Status
0x180015e7e  mov     rcx, rbx; Uuid1
0x180015e81  lea     rdx, Uuid1; Uuid2
0x180015e88  call    cs:__imp_UuidEqual
0x180015e8e  test    eax, eax
0x180015e90  jnz     short loc_180015EBA
0x180015e92  mov     ecx, 40000000h
0x180015e97  test    r14, r14
0x180015e9a  jz      short loc_180015EA4
0x180015e9c  movups  xmm0, xmmword ptr [rbx]
0x180015e9f  movdqu  xmmword ptr [r14], xmm0
0x180015ea4  mov     al, [r13+860h]
0x180015eab  not     al
0x180015ead  movzx   ebx, al
0x180015eb0  and     ebx, edi
0x180015eb2  or      ebx, 0FEFFFFBEh
0x180015eb8  jmp     short loc_180015ED5
0x180015eba  mov     ecx, 0C0000004h
0x180015ebf  mov     ebx, 20h ; ' '
0x180015ec4  test    r14, r14
0x180015ec7  jz      short loc_180015ED5
0x180015ec9  movups  xmm0, xmmword ptr cs:Uuid1.Data1
0x180015ed0  movdqu  xmmword ptr [r14], xmm0
0x180015ed5  mov     rax, [rbp+50h+var_98]
0x180015ed9  xorps   xmm0, xmm0
0x180015edc  movups  xmmword ptr [rbp+50h+var_90.cbSize], xmm0
0x180015ee0  mov     [rbp+50h+var_90.cbSize], 20h ; ' '
0x180015ee7  movups  xmmword ptr [rbp+50h+var_90.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180015eeb  test    rax, rax
0x180015eee  jz      short loc_180015EF5
0x180015ef0  mov     r9, [rax]
0x180015ef3  jmp     short loc_180015EF8
0x180015ef5  xor     r9d, r9d; hAdditionalStore
0x180015ef8  mov     rdx, [rbp+50h+pCertContext]; pCertContext
0x180015efc  lea     rax, [rsp+150h+pChainContext]
0x180015f01  mov     [rsp+150h+ppChainContext], rax; ppChainContext
0x180015f06  xor     r8d, r8d; pTime
0x180015f09  mov     [rsp+150h+pvReserved], rsi; pvReserved
0x180015f0e  lea     rax, [rbp+50h+var_90]
0x180015f12  mov     [rsp+150h+dwFlags], ecx; dwFlags
0x180015f16  mov     rcx, [r13+850h]; hChainEngine
0x180015f1d  mov     [rsp+150h+pChainPara], rax; pChainPara
0x180015f22  call    cs:__imp_CertGetCertificateChain
0x180015f28  xor     r8d, r8d
0x180015f2b  test    eax, eax
0x180015f2d  jnz     short loc_180015F55
0x180015f2f  call    cs:__imp_GetLastError
0x180015f35  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180015f3c  jz      short loc_180015F4D
0x180015f3e  mov     r9d, eax
0x180015f41  lea     r8, aCertgetcertifi; "CertGetCertificateChain"
0x180015f48  call    McTemplateU0sq_EtwEventWriteTransfer
0x180015f4d  xor     r13d, r13d
0x180015f50  jmp     loc_180015E3F
0x180015f55  mov     rcx, [rsp+150h+pChainContext]
0x180015f5a  mov     r14, r8
0x180015f5d  test    rcx, rcx
0x180015f60  jz      loc_180016248
0x180015f66  cmp     [rcx+0Ch], r8d
0x180015f6a  jbe     loc_180016248
0x180015f70  mov     rax, [rcx+10h]
0x180015f74  mov     rdx, [rax]
0x180015f77  cmp     [rdx+0Ch], r8d
0x180015f7b  jbe     loc_180016248
0x180015f81  test    [rdx+4], ebx
0x180015f84  jz      short loc_180015F90
0x180015f86  mov     [rsp+150h+var_110], 800B010Ah
0x180015f8e  jmp     short loc_180015F4D
0x180015f90  test    r15, r15
0x180015f93  jz      short loc_180015FA1
0x180015f95  test    dword ptr [rdx+4], 1000000h
0x180015f9c  jz      short loc_180015FA1
0x180015f9e  mov     [r15], edi
0x180015fa1  xor     eax, eax
0x180015fa3  mov     qword ptr [rsp+150h+pPolicyPara.cbSize], 10h
0x180015fac  mov     [rbp+50h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180015fb0  mov     edx, 0F00h
0x180015fb5  mov     [rbp+50h+var_D0], rax
0x180015fb9  xorps   xmm0, xmm0
0x180015fbc  mov     [rsp+150h+pPolicyPara.dwFlags], edx
0x180015fc0  mov     eax, 18h
0x180015fc5  movups  xmmword ptr [rbp+50h+pPolicyStatus.cbSize], xmm0
0x180015fc9  mov     [rbp+50h+pPolicyStatus.cbSize], eax
0x180015fcc  xorps   xmm1, xmm1
0x180015fcf  movups  [rsp+150h+var_E0], xmm1
0x180015fd4  mov     dword ptr [rsp+150h+var_E0], eax
0x180015fd8  lea     rax, [rsp+150h+var_E0]
0x180015fdd  mov     [rsp+150h+pPolicyPara.pvExtraPolicyPara], rax
0x180015fe2  mov     rax, [rcx+10h]
0x180015fe6  mov     rcx, [rax]
0x180015fe9  lea     eax, [rdx+10h]
0x180015fec  test    byte ptr [rcx+8], 8
0x180015ff0  cmovnz  edx, eax
0x180015ff3  mov     [rsp+150h+pPolicyPara.dwFlags], edx
0x180015ff7  test    [r13+860h], dil
0x180015ffe  jz      short loc_180016006
0x180016000  or      edx, edi
0x180016002  mov     [rsp+150h+pPolicyPara.dwFlags], edx
0x180016006  mov     ebx, [rsp+150h+var_F8]
0x18001600a  xor     r13d, r13d
0x18001600d  mov     [rbp+50h+var_D0], r13
0x180016011  mov     qword ptr [rsp+150h+var_E0+4], 2
0x18001601a  test    ebx, ebx
0x18001601c  jz      short loc_180016023
0x18001601e  mov     qword ptr [rsp+150h+var_E0+4], rdi
0x180016023  mov     rdx, [rsp+150h+pChainContext]; pChainContext
0x180016028  lea     r9, [rbp+50h+pPolicyStatus]; pPolicyStatus
0x18001602c  lea     r8, [rsp+150h+pPolicyPara]; pPolicyPara
0x180016031  mov     ecx, 4; pszPolicyOID
0x180016036  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18001603c  test    eax, eax
0x18001603e  jnz     short loc_18001606A
0x180016040  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016047  jz      short loc_18001605D
0x180016049  mov     r8d, [rbp+50h+pPolicyStatus.dwError]
0x18001604d  mov     eax, [rbp+50h+pPolicyStatus.lElementIndex]
0x180016050  mov     r9d, [rbp+50h+pPolicyStatus.lChainIndex]
0x180016054  mov     dword ptr [rsp+150h+pChainPara], eax
0x180016058  call    McTemplateU0qqq_EtwEventWriteTransfer
0x18001605d  mov     [rsp+150h+var_110], 800B0113h
0x180016065  jmp     loc_180015E3F
0x18001606a  mov     r8d, [rbp+50h+pPolicyStatus.dwError]
0x18001606e  test    r8d, r8d
0x180016071  jz      short loc_18001607E
0x180016073  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18001607a  jz      short loc_18001605D
0x18001607c  jmp     short loc_18001604D
0x18001607e  test    ebx, ebx
0x180016080  jnz     loc_180016231
0x180016086  lea     r9, [rbp+50h+hMem]; unsigned __int16 **
0x18001608a  mov     rcx, r12; struct _UNICODE_STRING *
0x18001608d  lea     r8, [rsp+150h+lpString2]; unsigned __int16 **
0x180016092  lea     rdx, [rsp+150h+var_F4]; int *
0x180016097  call    ?IntGetHostNameFromTargetName@@YAKPEAU_UNICODE_STRING@@PEAHPEAPEAG2@Z; IntGetHostNameFromTargetName(_UNICODE_STRING *,int *,ushort * *,ushort * *)
0x18001609c  mov     ebx, eax
0x18001609e  test    eax, eax
0x1800160a0  jz      short loc_1800160E5
0x1800160a2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800160a9  jz      short loc_1800160BA
0x1800160ab  mov     r9d, eax
0x1800160ae  lea     r8, aIntgethostname; "IntGetHostNameFromTargetName"
0x1800160b5  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800160ba  test    ebx, ebx
0x1800160bc  jle     short loc_1800160C7
0x1800160be  movzx   ebx, bx
0x1800160c1  or      ebx, 0C0070000h
0x1800160c7  mov     [rsp+150h+var_110], ebx
0x1800160cb  cmp     [rbp+50h+var_48], r13b
0x1800160cf  jz      short loc_1800160DB
0x1800160d1  mov     rcx, [rbp+50h+Resource]; Resource
0x1800160d5  call    cs:__imp_RtlReleaseResource
0x1800160db  mov     rsi, [rsp+150h+lpString2]
0x1800160e0  jmp     loc_180016263
0x1800160e5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, dil
0x1800160ec  mov     rsi, [rsp+150h+lpString2]
0x1800160f1  jz      short loc_180016109
0x1800160f3  mov     r9, rsi
0x1800160f6  lea     r8, qword_180020CC0
0x1800160fd  lea     rdx, TargetNameAndHostName
0x180016104  call    McTemplateU0zz_EtwEventWriteTransfer
0x180016109  mov     r12, [rbp+50h+pCertContext]
0x18001610d  xor     r9d, r9d; pvTypePara
0x180016110  mov     [rsp+150h+dwFlags], r13d; cchNameString
0x180016115  mov     rcx, r12; pCertContext
0x180016118  mov     [rsp+150h+pChainPara], r13; pszNameString
0x18001611d  lea     edx, [r9+6]; dwType
0x180016121  lea     r8d, [r9+2]; dwFlags
0x180016125  call    cs:__imp_CertGetNameStringW
0x18001612b  mov     ebx, eax
0x18001612d  cmp     eax, 2
0x180016130  jnb     short loc_180016149
0x180016132  mov     [rsp+150h+var_110], 800B0114h
0x18001613a  cmp     [rbp+50h+var_48], r13b
0x18001613e  jz      loc_180016263
0x180016144  jmp     loc_180016259
0x180016149  mov     rcx, gs:60h
0x180016152  mov     r8, rbx
0x180016155  add     r8, r8; Size
0x180016158  xor     edx, edx; Flags
0x18001615a  mov     rcx, [rcx+30h]; HeapHandle
0x18001615e  call    cs:__imp_RtlAllocateHeap
  ... truncated ...
```
