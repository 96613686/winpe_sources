# CProviderRegistrationCache::GetCertificateChain(_CERT_CONTEXT const *,_SecPkgContext_IssuerListInfoEx *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180014750`
- end: `0x1800148f6`
- name: `?GetCertificateChain@CProviderRegistrationCache@@QEAAJPEBU_CERT_CONTEXT@@PEAU_SecPkgContext_IssuerListInfoEx@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, struct _SecPkgContext_IssuerListInfoEx *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800137d0`

## callees

- `0x180003dc0`
- `0x180007b70`
- `0x180007ea0`
- `0x18000c344`
- `0x18000db54`
- `0x180014750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014857`
- `CRYPT32!CertCompareCertificateName` at `0x1800147d8`
- `CRYPT32!CertCompareCertificateName` at `0x1800147d8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800148ce`
- `CRYPT32!CertFreeCertificateChain` at `0x1800148ce`
- `CRYPT32!CertGetCertificateChain` at `0x18001484d`
- `CRYPT32!CertGetCertificateChain` at `0x18001484d`
- `ntdll!RtlReleaseResource` at `0x18001489c`
- `ntdll!RtlReleaseResource` at `0x1800148ae`
- `ntdll!RtlReleaseResource` at `0x18001489c`
- `ntdll!RtlReleaseResource` at `0x1800148ae`

## string_xrefs

- `0x180014798`: `CProviderRegistrationCache::GetCertificateChain`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetCertificateChain(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        struct _SecPkgContext_IssuerListInfoEx *a3,
        const struct _CERT_CHAIN_CONTEXT **a4)
{
  CProviderRegistrationCache *v4; // r15
  __int64 v8; // rdx
  DWORD v9; // ebx
  bool v10; // zf
  unsigned int v11; // ebx
  DWORD LastError; // eax
  __int64 v13; // rcx
  PRTL_RESOURCE Resource; // [rsp+40h] [rbp-19h] BYREF
  char v16; // [rsp+48h] [rbp-11h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[64]; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v19; // [rsp+C0h] [rbp+67h] BYREF
  int v20; // [rsp+C4h] [rbp+6Bh]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+D0h] [rbp+77h] BYREF

  v20 = HIDWORD(this);
  v4 = g_pProvRegCache;
  v19 = 0;
  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v18, "CProviderRegistrationCache::GetCertificateChain", (int *)a3, 0, &v19);
  v9 = 0;
  *a4 = 0;
  v10 = a3->cIssuers == 0;
  if ( a3->cIssuers )
  {
    do
    {
      if ( CertCompareCertificateName(0x10001u, &a2->pCertInfo->Issuer, &a3->aIssuers[v9]) )
        break;
      ++v9;
    }
    while ( v9 < a3->cIssuers );
    v10 = a3->cIssuers == v9;
  }
  if ( v10 )
  {
    v11 = -2146893042;
  }
  else
  {
    memset(&pChainPara, 0, sizeof(pChainPara));
    pChainPara.cbSize = 32;
    CAutoRtlLock::CAutoRtlLock((__int64)&Resource, (struct _RTL_RESOURCE *)((char *)v4 + 16), 0);
    if ( CertGetCertificateChain(*((HCERTCHAINENGINE *)v4 + 17), a2, 0, 0, &pChainPara, 0xC0000004, 0, &pChainContext) )
    {
      if ( v16 )
        RtlReleaseResource(Resource);
      v11 = 0;
      *a4 = pChainContext;
      pChainContext = 0;
    }
    else
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      {
        McTemplateU0sq_EtwEventWriteTransfer(v13, v8, "CertGetCertificateChain", LastError);
        LastError = v19;
      }
      if ( LastError == 14 )
        v11 = NetpApiStatusToNtStatus(14);
      else
        v11 = -1073741715;
      if ( v16 )
        RtlReleaseResource(Resource);
    }
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v18, v8);
  return v11;
}

```

## disassembly

```asm
0x180014750  mov     [rsp-8+arg_8], rbx
0x180014755  mov     qword ptr [rsp-8+arg_0], rcx
0x18001475a  push    rbp
0x18001475b  push    rsi
0x18001475c  push    rdi
0x18001475d  push    r14
0x18001475f  push    r15
0x180014761  lea     rbp, [rsp-37h]
0x180014766  sub     rsp, 90h
0x18001476d  mov     r15, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180014774  lea     rax, [rbp+57h+arg_0]
0x180014778  xorps   xmm0, xmm0
0x18001477b  mov     [rsp+0B0h+pChainPara], rax; unsigned int *
0x180014780  mov     rsi, r9
0x180014783  mov     [rbp+57h+arg_0], 0
0x18001478a  mov     r14, rdx
0x18001478d  mov     [rbp+57h+pChainContext], 0
0x180014795  xor     r9d, r9d; int *
0x180014798  lea     rdx, aCproviderregis_15; "CProviderRegistrationCache::GetCertific"...
0x18001479f  lea     rcx, [rbp+57h+var_40]; this
0x1800147a3  mov     rdi, r8
0x1800147a6  movups  xmmword ptr [rbp+57h+var_60.cbSize], xmm0
0x1800147aa  movups  xmmword ptr [rbp+57h+var_60.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800147ae  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x1800147b3  xor     ebx, ebx
0x1800147b5  mov     qword ptr [rsi], 0
0x1800147bc  cmp     [rdi+8], ebx
0x1800147bf  jbe     short loc_1800147EC
0x1800147c1  mov     rdx, [r14+18h]
0x1800147c5  mov     ecx, 10001h; dwCertEncodingType
0x1800147ca  mov     r8d, ebx
0x1800147cd  add     rdx, 30h ; '0'; pCertName1
0x1800147d1  shl     r8, 4
0x1800147d5  add     r8, [rdi]; pCertName2
0x1800147d8  call    cs:__imp_CertCompareCertificateName
0x1800147de  test    eax, eax
0x1800147e0  jnz     short loc_1800147E9
0x1800147e2  inc     ebx
0x1800147e4  cmp     ebx, [rdi+8]
0x1800147e7  jb      short loc_1800147C1
0x1800147e9  cmp     [rdi+8], ebx
0x1800147ec  jnz     short loc_1800147F8
0x1800147ee  mov     ebx, 8009030Eh
0x1800147f3  jmp     loc_1800148C5
0x1800147f8  xorps   xmm0, xmm0
0x1800147fb  lea     rdx, [r15+10h]
0x1800147ff  movups  xmmword ptr [rbp+57h+var_60.cbSize], xmm0
0x180014803  xor     r8d, r8d
0x180014806  mov     [rbp+57h+var_60.cbSize], 20h ; ' '
0x18001480d  lea     rcx, [rbp+57h+Resource]
0x180014811  movups  xmmword ptr [rbp+57h+var_60.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180014815  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x18001481a  mov     rcx, [r15+88h]; hChainEngine
0x180014821  lea     rax, [rbp+57h+pChainContext]
0x180014825  mov     [rsp+0B0h+ppChainContext], rax; ppChainContext
0x18001482a  xor     r9d, r9d; hAdditionalStore
0x18001482d  mov     [rsp+0B0h+pvReserved], 0; pvReserved
0x180014836  lea     rax, [rbp+57h+var_60]
0x18001483a  mov     [rsp+0B0h+dwFlags], 0C0000004h; dwFlags
0x180014842  xor     r8d, r8d; pTime
0x180014845  mov     rdx, r14; pCertContext
0x180014848  mov     [rsp+0B0h+pChainPara], rax; pChainPara
0x18001484d  call    cs:__imp_CertGetCertificateChain
0x180014853  test    eax, eax
0x180014855  jnz     short loc_1800148A4
0x180014857  call    cs:__imp_GetLastError
0x18001485d  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180014864  mov     [rbp+57h+arg_0], eax
0x180014867  jz      short loc_18001487B
0x180014869  mov     r9d, eax
0x18001486c  lea     r8, aCertgetcertifi; "CertGetCertificateChain"
0x180014873  call    McTemplateU0sq_EtwEventWriteTransfer
0x180014878  mov     eax, [rbp+57h+arg_0]
0x18001487b  mov     ecx, 0Eh
0x180014880  cmp     eax, ecx
0x180014882  jz      short loc_18001488B
0x180014884  mov     ebx, 0C000006Dh
0x180014889  jmp     short loc_180014892
0x18001488b  call    NetpApiStatusToNtStatus
0x180014890  mov     ebx, eax
0x180014892  cmp     [rbp+57h+var_68], 0
0x180014896  jz      short loc_1800148C5
0x180014898  mov     rcx, [rbp+57h+Resource]; Resource
0x18001489c  call    cs:__imp_RtlReleaseResource
0x1800148a2  jmp     short loc_1800148C5
0x1800148a4  cmp     [rbp+57h+var_68], 0
0x1800148a8  jz      short loc_1800148B4
0x1800148aa  mov     rcx, [rbp+57h+Resource]; Resource
0x1800148ae  call    cs:__imp_RtlReleaseResource
0x1800148b4  mov     rax, [rbp+57h+pChainContext]
0x1800148b8  xor     ebx, ebx
0x1800148ba  mov     [rsi], rax
0x1800148bd  mov     [rbp+57h+pChainContext], 0
0x1800148c5  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x1800148c9  test    rcx, rcx
0x1800148cc  jz      short loc_1800148D4
0x1800148ce  call    cs:__imp_CertFreeCertificateChain
0x1800148d4  lea     rcx, [rbp+57h+var_40]; this
0x1800148d8  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x1800148dd  mov     eax, ebx
0x1800148df  mov     rbx, [rsp+0B0h+arg_8]
0x1800148e7  add     rsp, 90h
0x1800148ee  pop     r15
0x1800148f0  pop     r14
0x1800148f2  pop     rdi
0x1800148f3  pop     rsi
0x1800148f4  pop     rbp
0x1800148f5  retn
```
