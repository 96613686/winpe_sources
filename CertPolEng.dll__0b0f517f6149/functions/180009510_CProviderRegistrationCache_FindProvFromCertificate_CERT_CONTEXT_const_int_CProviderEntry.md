# CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)

- ea: `0x180009510`
- end: `0x180009723`
- name: `?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, int, struct CProviderEntry **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800066f0`
- `0x18000bee0`
- `0x18000d51c`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`
- `0x1800167c8`

## callees

- `0x180009510`
- `0x18000c344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009649`
- `CRYPT32!CertFreeCertificateContext` at `0x180009580`
- `CRYPT32!CertFreeCertificateContext` at `0x1800096ce`
- `CRYPT32!CertFreeCertificateContext` at `0x180009580`
- `CRYPT32!CertFreeCertificateContext` at `0x1800096ce`
- `CRYPT32!CertFreeCertificateChain` at `0x1800095f0`
- `CRYPT32!CertFreeCertificateChain` at `0x180009710`
- `CRYPT32!CertFreeCertificateChain` at `0x1800095f0`
- `CRYPT32!CertFreeCertificateChain` at `0x180009710`
- `CRYPT32!CertGetCertificateChain` at `0x18000963f`
- `CRYPT32!CertGetCertificateChain` at `0x18000963f`
- `CRYPT32!CertFindCertificateInStore` at `0x1800095c4`
- `CRYPT32!CertFindCertificateInStore` at `0x1800096a7`
- `CRYPT32!CertFindCertificateInStore` at `0x1800095c4`
- `CRYPT32!CertFindCertificateInStore` at `0x1800096a7`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::FindProvFromCertificate(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        int a3,
        struct CProviderEntry **a4)
{
  unsigned int v4; // r15d
  const CERT_CONTEXT *CertificateInStore; // rbx
  const CERT_CHAIN_CONTEXT *v9; // r10
  unsigned int v10; // edi
  __int64 v12; // r14
  void *v13; // rcx
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-48h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+90h] [rbp+8h] BYREF

  v4 = 1168;
  *(_OWORD *)&pChainPara.cbSize = 0;
  CertificateInStore = 0;
  pChainContext = 0;
  v9 = 0;
  *a4 = 0;
  v10 = 0;
  pChainPara.cbSize = 32;
  pChainPara.RequestedUsage.Usage = 0;
  while ( v10 < *((_DWORD *)this + 38) )
  {
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
    v12 = 8LL * v10;
    v13 = *(void **)(*(_QWORD *)(*((_QWORD *)this + 18) + v12) + 2104LL);
    if ( !a3 )
    {
      CertificateInStore = CertFindCertificateInStore(v13, 0x10001u, 0, 0xD0000u, a2, 0);
      if ( CertificateInStore )
        goto LABEL_16;
      goto LABEL_18;
    }
    CertificateInStore = CertFindCertificateInStore(v13, 0x10001u, 0, 0xC0000u, a2, 0);
    if ( !CertificateInStore )
      goto LABEL_18;
    if ( !*((_DWORD *)this + 87) )
      goto LABEL_16;
    if ( pChainContext )
    {
      CertFreeCertificateChain(pChainContext);
      pChainContext = 0;
    }
    if ( !CertGetCertificateChain(
            *(HCERTCHAINENGINE *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8LL * v10) + 2128LL),
            a2,
            0,
            0,
            &pChainPara,
            0,
            0,
            &pChainContext) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v16, v15, "FindProvFromCertificate CertGetCertificateChain", LastError);
LABEL_18:
      v9 = pChainContext;
      goto LABEL_19;
    }
    v9 = pChainContext;
    if ( pChainContext && pChainContext->cChain && (*pChainContext->rgpChain)->cElement )
    {
LABEL_16:
      v4 = 0;
      *a4 = *(struct CProviderEntry **)(v12 + *((_QWORD *)this + 18));
      goto LABEL_21;
    }
LABEL_19:
    ++v10;
  }
  if ( !CertificateInStore )
    goto LABEL_22;
LABEL_21:
  CertFreeCertificateContext(CertificateInStore);
  v9 = pChainContext;
LABEL_22:
  if ( v9 )
    CertFreeCertificateChain(v9);
  return v4;
}

```

## disassembly

```asm
0x180009510  mov     rax, rsp
0x180009513  push    r15
0x180009515  sub     rsp, 80h
0x18000951c  mov     [rax+10h], rbx
0x180009520  xorps   xmm0, xmm0
0x180009523  mov     [rax+18h], rbp
0x180009527  mov     r15d, 490h
0x18000952d  mov     [rax+20h], rsi
0x180009531  mov     ebp, r8d
0x180009534  mov     [rax-10h], rdi
0x180009538  mov     rsi, rcx
0x18000953b  mov     [rax-18h], r12
0x18000953f  mov     r12, rdx
0x180009542  xor     edx, edx
0x180009544  mov     [rax-20h], r13
0x180009548  movups  xmmword ptr [rax-48h], xmm0
0x18000954c  mov     ebx, edx
0x18000954e  mov     [rax+8], rdx
0x180009552  mov     r10d, edx
0x180009555  mov     [r9], rdx
0x180009558  mov     edi, edx
0x18000955a  mov     dword ptr [rax-48h], 20h ; ' '
0x180009561  mov     r13, r9
0x180009564  mov     [rax-28h], r14
0x180009568  movups  xmmword ptr [rax-38h], xmm0
0x18000956c  cmp     edi, [rsi+98h]
0x180009572  jnb     loc_1800096C6
0x180009578  test    rbx, rbx
0x18000957b  jz      short loc_180009588
0x18000957d  mov     rcx, rbx; pCertContext
0x180009580  call    cs:__imp_CertFreeCertificateContext
0x180009586  xor     edx, edx
0x180009588  mov     eax, edi
0x18000958a  xor     r8d, r8d; dwFindFlags
0x18000958d  mov     [rsp+88h+pPrevCertContext], rdx; pPrevCertContext
0x180009592  lea     r14, ds:0[rax*8]
0x18000959a  mov     rax, [rsi+90h]
0x1800095a1  mov     edx, 10001h; dwCertEncodingType
0x1800095a6  mov     [rsp+88h+pvFindPara], r12; pvFindPara
0x1800095ab  mov     rcx, [rax+r14]
0x1800095af  mov     rcx, [rcx+838h]; hCertStore
0x1800095b6  test    ebp, ebp
0x1800095b8  jz      loc_1800096A1
0x1800095be  mov     r9d, 0C0000h; dwFindType
0x1800095c4  call    cs:__imp_CertFindCertificateInStore
0x1800095ca  mov     rbx, rax
0x1800095cd  test    rax, rax
0x1800095d0  jz      loc_1800096B5
0x1800095d6  cmp     dword ptr [rsi+15Ch], 0
0x1800095dd  jz      loc_18000968D
0x1800095e3  mov     rcx, [rsp+88h+pChainContext]; pChainContext
0x1800095eb  test    rcx, rcx
0x1800095ee  jz      short loc_180009602
0x1800095f0  call    cs:__imp_CertFreeCertificateChain
0x1800095f6  mov     [rsp+88h+pChainContext], 0
0x180009602  mov     rax, [rsi+90h]
0x180009609  xor     r9d, r9d; hAdditionalStore
0x18000960c  xor     r8d, r8d; pTime
0x18000960f  mov     rdx, r12; pCertContext
0x180009612  mov     rcx, [rax+r14]
0x180009616  lea     rax, [rsp+88h+pChainContext]
0x18000961e  mov     [rsp+88h+ppChainContext], rax; ppChainContext
0x180009623  xor     eax, eax
0x180009625  mov     [rsp+88h+pvReserved], rax; pvReserved
0x18000962a  mov     dword ptr [rsp+88h+pPrevCertContext], eax; dwFlags
0x18000962e  lea     rax, [rsp+88h+pChainPara]
0x180009633  mov     rcx, [rcx+850h]; hChainEngine
0x18000963a  mov     [rsp+88h+pvFindPara], rax; pChainPara
0x18000963f  call    cs:__imp_CertGetCertificateChain
0x180009645  test    eax, eax
0x180009647  jnz     short loc_18000966C
0x180009649  call    cs:__imp_GetLastError
0x18000964f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180009656  mov     r15d, eax
0x180009659  jz      short loc_1800096B5
0x18000965b  mov     r9d, eax
0x18000965e  lea     r8, aFindprovfromce; "FindProvFromCertificate CertGetCertific"...
0x180009665  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000966a  jmp     short loc_1800096B5
0x18000966c  mov     r10, [rsp+88h+pChainContext]
0x180009674  test    r10, r10
0x180009677  jz      short loc_1800096BD
0x180009679  cmp     dword ptr [r10+0Ch], 0
0x18000967e  jz      short loc_1800096BD
0x180009680  mov     rax, [r10+10h]
0x180009684  mov     rcx, [rax]
0x180009687  cmp     dword ptr [rcx+0Ch], 0
0x18000968b  jz      short loc_1800096BD
0x18000968d  mov     rax, [rsi+90h]
0x180009694  xor     r15d, r15d
0x180009697  mov     rcx, [r14+rax]
0x18000969b  mov     [r13+0], rcx
0x18000969f  jmp     short loc_1800096CB
0x1800096a1  mov     r9d, 0D0000h; dwFindType
0x1800096a7  call    cs:__imp_CertFindCertificateInStore
0x1800096ad  mov     rbx, rax
0x1800096b0  test    rax, rax
0x1800096b3  jnz     short loc_18000968D
0x1800096b5  mov     r10, [rsp+88h+pChainContext]
0x1800096bd  inc     edi
0x1800096bf  xor     edx, edx
0x1800096c1  jmp     loc_18000956C
0x1800096c6  test    rbx, rbx
0x1800096c9  jz      short loc_1800096DC
0x1800096cb  mov     rcx, rbx; pCertContext
0x1800096ce  call    cs:__imp_CertFreeCertificateContext
0x1800096d4  mov     r10, [rsp+88h+pChainContext]
0x1800096dc  mov     r14, [rsp+88h+var_28]
0x1800096e1  mov     r13, [rsp+88h+var_20]
0x1800096e6  mov     r12, [rsp+88h+var_18]
0x1800096eb  mov     rdi, [rsp+88h+var_10]
0x1800096f0  mov     rsi, [rsp+88h+arg_18]
0x1800096f8  mov     rbp, [rsp+88h+arg_10]
0x180009700  mov     rbx, [rsp+88h+arg_8]
0x180009708  test    r10, r10
0x18000970b  jz      short loc_180009716
0x18000970d  mov     rcx, r10; pChainContext
0x180009710  call    cs:__imp_CertFreeCertificateChain
0x180009716  mov     eax, r15d
0x180009719  add     rsp, 80h
0x180009720  pop     r15
0x180009722  retn
```
