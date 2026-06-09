# CProviderRegistrationCache::IntGetNameIdentifierForCertificate(_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x180005c20`
- end: `0x1800061d8`
- name: `?IntGetNameIdentifierForCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `1464`
- prototype: `__int64 __fastcall(__int64 this, __int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180003e60`
- `0x180005c20`
- `0x1800062a0`
- `0x180007c90`
- `0x180007d20`
- `0x180009190`
- `0x18000c344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000610b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000610b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006119`
- `CRYPT32!CertFreeCertificateContext` at `0x180005dd2`
- `CRYPT32!CertFreeCertificateContext` at `0x180005f9d`
- `CRYPT32!CertFreeCertificateContext` at `0x180005dd2`
- `CRYPT32!CertFreeCertificateContext` at `0x180005f9d`
- `CRYPT32!CertFreeCertificateChain` at `0x180005e3a`
- `CRYPT32!CertFreeCertificateChain` at `0x180005faf`
- `CRYPT32!CertFreeCertificateChain` at `0x180005e3a`
- `CRYPT32!CertFreeCertificateChain` at `0x180005faf`
- `CRYPT32!CertGetCertificateChain` at `0x180005e8a`
- `CRYPT32!CertGetCertificateChain` at `0x180005e8a`
- `CRYPT32!CertFindCertificateInStore` at `0x180005e12`
- `CRYPT32!CertFindCertificateInStore` at `0x180005e12`
- `ntdll!RtlAllocateHeap` at `0x180006067`
- `ntdll!RtlAllocateHeap` at `0x180006067`
- `ntdll!RtlReleaseResource` at `0x180005fdb`
- `ntdll!RtlReleaseResource` at `0x1800060b3`
- `ntdll!RtlReleaseResource` at `0x1800060f9`
- `ntdll!RtlReleaseResource` at `0x180005fdb`
- `ntdll!RtlReleaseResource` at `0x1800060b3`
- `ntdll!RtlReleaseResource` at `0x1800060f9`
- `ntdll!RtlAcquireResourceShared` at `0x180005d94`
- `ntdll!RtlAcquireResourceShared` at `0x180005d94`
- `ntdll!RtlFreeHeap` at `0x180006136`
- `ntdll!RtlFreeHeap` at `0x180006136`
- `ntdll!RtlCreateUnicodeString` at `0x1800060d7`
- `ntdll!RtlCreateUnicodeString` at `0x1800060d7`

## string_xrefs

- `0x180005c3a`: `CProviderRegistrationCache::IntGetNameIdentifierForCertificate`
- `0x180006144`: `CProviderRegistrationCache::IntGetNameIdentifierForCertificate`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntGetNameIdentifierForCertificate(
        __int64 this,
        __int64 a2,
        struct _UNICODE_STRING *a3)
{
  CProviderRegistrationCache *v3; // rsi
  const struct _CERT_CONTEXT *pvFindPara; // rdi
  HLOCAL v5; // r13
  unsigned int CertName; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  unsigned __int16 *Heap; // r12
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  const CERT_CONTEXT *CertificateInStore; // rbx
  DWORD LastError; // eax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  PCCERT_CHAIN_CONTEXT v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // edx
  __int64 v26; // rax
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rax
  int v29; // eax
  struct _RTL_RESOURCE *v30; // rcx
  __int64 v31; // rcx
  BOOLEAN UnicodeString; // al
  unsigned int v33; // ebx
  __int64 v34; // r9
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-31h] BYREF
  HLOCAL v38; // [rsp+58h] [rbp-29h]
  __int64 v39; // [rsp+60h] [rbp-21h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+68h] [rbp-19h] BYREF
  const char *v41; // [rsp+88h] [rbp+7h] BYREF
  __int128 v42; // [rsp+90h] [rbp+Fh]
  int *v43; // [rsp+A0h] [rbp+1Fh]
  int v44; // [rsp+E8h] [rbp+67h] BYREF
  int v45; // [rsp+ECh] [rbp+6Bh]
  unsigned int v46; // [rsp+F0h] [rbp+6Fh] BYREF
  unsigned int v47; // [rsp+100h] [rbp+7Fh] BYREF

  v45 = HIDWORD(this);
  v3 = g_pProvRegCache;
  pvFindPara = (const struct _CERT_CONTEXT *)a2;
  v5 = 0;
  v44 = 0;
  v43 = &v44;
  v41 = "CProviderRegistrationCache::IntGetNameIdentifierForCertificate";
  v42 = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(
      this,
      Func_Start,
      "CProviderRegistrationCache::IntGetNameIdentifierForCertificate");
  if ( !pvFindPara || !a3 )
  {
    v44 = 87;
    goto LABEL_78;
  }
  *a3 = 0;
  if ( !*((_DWORD *)v3 + 2) )
  {
    v44 = 21;
    goto LABEL_78;
  }
  hMem = 0;
  v46 = 0;
  v47 = 0;
  CertName = GetCertName(pvFindPara, 0, "2.5.4.3", (unsigned __int8 **)&hMem, &v46, &v47);
  v8 = CertName;
  if ( CertName != 14 )
  {
    if ( !CertName && v46 > 2 )
    {
      v9 = v46 >> 1;
      v38 = hMem;
      v5 = 0;
      v44 = 0;
      goto LABEL_11;
    }
    v8 = 87;
  }
  this = (__int64)hMem;
  v9 = 0;
  v38 = 0;
  if ( hMem )
    LocalFree(hMem);
  v44 = v8;
  if ( v8 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(this, a2, "GetNameFromCert(Issuer)", v8);
    goto LABEL_78;
  }
LABEL_11:
  pChainContext = 0;
  v46 = 0;
  v47 = 0;
  Heap = 0;
  v11 = GetCertName(pvFindPara, 1, "2.5.4.3", (unsigned __int8 **)&pChainContext, &v46, &v47);
  v12 = v11;
  if ( v11 == 14 )
    goto LABEL_33;
  if ( v11 || v46 <= 2 )
  {
    v12 = 87;
LABEL_33:
    this = (__int64)pChainContext;
    hMem = 0;
    v47 = 0;
    if ( pChainContext )
      LocalFree((HLOCAL)pChainContext);
    v44 = v12;
    if ( v12 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(this, a2, "GetNameFromCert(Subject)", v12);
      goto LABEL_72;
    }
    goto LABEL_15;
  }
  hMem = (HLOCAL)pChainContext;
  v47 = v46 >> 1;
  v44 = v11;
LABEL_15:
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v3 + 16), 1u);
  CertificateInStore = 0;
  LastError = 1168;
  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  v16 = 0;
  v46 = 1168;
  while ( (unsigned int)v16 < *((_DWORD *)v3 + 38) )
  {
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
    v17 = *((_QWORD *)v3 + 18);
    v39 = 8 * v16;
    CertificateInStore = CertFindCertificateInStore(
                           *(HCERTSTORE *)(*(_QWORD *)(8 * v16 + v17) + 2104LL),
                           0x10001u,
                           0,
                           0xC0000u,
                           pvFindPara,
                           0);
    if ( CertificateInStore )
    {
      if ( !*((_DWORD *)v3 + 87) )
        goto LABEL_43;
      if ( pChainContext )
      {
        CertFreeCertificateChain(pChainContext);
        pChainContext = 0;
      }
      if ( CertGetCertificateChain(
             *(HCERTCHAINENGINE *)(*(_QWORD *)(v39 + *((_QWORD *)v3 + 18)) + 2128LL),
             pvFindPara,
             0,
             0,
             &pChainPara,
             0,
             0,
             &pChainContext) )
      {
        if ( pChainContext && pChainContext->cChain && (*pChainContext->rgpChain)->cElement )
        {
LABEL_43:
          v19 = *((_QWORD *)v3 + 18);
          v46 = 0;
          v20 = *(_QWORD *)(v39 + v19);
          goto LABEL_45;
        }
      }
      else
      {
        LastError = GetLastError();
        v46 = LastError;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
          goto LABEL_42;
        McTemplateU0sq_EtwEventWriteTransfer(v18, v13, "FindProvFromCertificate CertGetCertificateChain", LastError);
      }
    }
    LastError = v46;
LABEL_42:
    v16 = (unsigned int)(v16 + 1);
  }
  v20 = 0;
  if ( !CertificateInStore )
    goto LABEL_46;
LABEL_45:
  CertFreeCertificateContext(CertificateInStore);
  LastError = v46;
LABEL_46:
  v21 = pChainContext;
  if ( pChainContext )
  {
    CertFreeCertificateChain(pChainContext);
    LastError = v46;
  }
  v44 = LastError;
  if ( LastError )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v21, v13, "FindProvFromCertificate", LastError);
    RtlReleaseResource((PRTL_RESOURCE)((char *)v3 + 16));
    v5 = hMem;
    goto LABEL_72;
  }
  v5 = hMem;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v21, CertSubjectName, hMem);
  v22 = v20 + 1584;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(v22 + 2 * v23) );
  v24 = v23 + v9;
  if ( (unsigned int)v23 + v9 < (unsigned int)v23
    || (v25 = v24 + v47, v24 + v47 < v24)
    || (v26 = v25 + 3, (unsigned int)v26 < v25)
    || (v27 = (unsigned int)v26, v28 = 2 * v26, v28 > 0xFFFFFFFF) )
  {
    v44 = 111;
LABEL_70:
    v30 = (struct _RTL_RESOURCE *)((char *)v3 + 16);
LABEL_71:
    RtlReleaseResource(v30);
    goto LABEL_72;
  }
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v28);
  if ( !Heap )
  {
    v44 = 14;
    goto LABEL_70;
  }
  v29 = StringCchPrintfW(Heap, v27, L"%ws\\%ws\\%ws", v22, v38, v5);
  v30 = (struct _RTL_RESOURCE *)((char *)v3 + 16);
  if ( v29 < 0 )
  {
    v44 = 534;
    goto LABEL_71;
  }
  RtlReleaseResource(v30);
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v31, UserName, Heap);
  UnicodeString = RtlCreateUnicodeString(a3, Heap);
  this = 0;
  a2 = 14;
  if ( !UnicodeString )
    this = 14;
  v44 = this;
LABEL_72:
  if ( v38 )
    LocalFree(v38);
  if ( v5 )
    LocalFree(v5);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_78:
  v33 = v44;
  if ( v44 > 0 )
    v34 = (unsigned __int16)v44 | 0x80070000;
  else
    v34 = (unsigned int)v44;
  v46 = v34;
  if ( (int)v34 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(
        this,
        a2,
        "CProviderRegistrationCache::IntGetNameIdentifierForCertificate",
        v34);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(&v41, &v46);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(
      this,
      Func_Exit,
      "CProviderRegistrationCache::IntGetNameIdentifierForCertificate");
  return v33;
}

```

## disassembly

```asm
0x180005c20  mov     rax, rsp
0x180005c23  mov     [rax+8], rcx
0x180005c27  push    rbp
0x180005c28  push    rbx
0x180005c29  push    r15
0x180005c2b  lea     rbp, [rax-5Fh]
0x180005c2f  sub     rsp, 0C0h
0x180005c36  mov     [rax+18h], rsi
0x180005c3a  lea     r15, aCproviderregis_18; "CProviderRegistrationCache::IntGetNameI"...
0x180005c41  mov     rsi, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180005c48  xorps   xmm0, xmm0
0x180005c4b  mov     [rax-20h], rdi
0x180005c4f  mov     rdi, rdx
0x180005c52  mov     [rax-30h], r13
0x180005c56  xor     r13d, r13d
0x180005c59  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180005c60  mov     [rax-38h], r14
0x180005c64  mov     r14, r8
0x180005c67  lea     rax, [rbp+57h+arg_0]
0x180005c6b  mov     [rbp+57h+arg_0], r13d
0x180005c6f  mov     [rbp+57h+var_38], rax
0x180005c73  mov     [rbp+57h+var_50], r15
0x180005c77  movdqu  [rbp+57h+var_48], xmm0
0x180005c7c  jz      short loc_180005C8D
0x180005c7e  mov     r8, r15
0x180005c81  lea     rdx, Func_Start
0x180005c88  call    McTemplateU0s_EtwEventWriteTransfer
0x180005c8d  test    rdi, rdi
0x180005c90  jz      loc_180006177
0x180005c96  test    r14, r14
0x180005c99  jz      loc_180006177
0x180005c9f  xorps   xmm0, xmm0
0x180005ca2  movups  xmmword ptr [r14], xmm0
0x180005ca6  cmp     [rsi+8], r13d
0x180005caa  jnz     short loc_180005CB8
0x180005cac  mov     [rbp+57h+arg_0], 15h
0x180005cb3  jmp     loc_18000614B
0x180005cb8  lea     rax, [rbp+57h+arg_18]
0x180005cbc  mov     [rbp+57h+hMem], r13
0x180005cc0  mov     [rsp+0D0h+pPrevCertContext], rax; unsigned int *
0x180005cc5  lea     r9, [rbp+57h+hMem]; unsigned __int8 **
0x180005cc9  lea     rax, [rbp+57h+arg_8]
0x180005ccd  mov     [rbp+57h+arg_8], r13d
0x180005cd1  lea     r8, a2543; "2.5.4.3"
0x180005cd8  mov     [rsp+0D0h+pvFindPara], rax; unsigned int *
0x180005cdd  xor     edx, edx; int
0x180005cdf  mov     [rbp+57h+arg_18], r13d
0x180005ce3  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180005ce6  call    ?GetCertName@@YAKPEBU_CERT_CONTEXT@@HPEADPEAPEAEPEAK3@Z; GetCertName(_CERT_CONTEXT const *,int,char *,uchar * *,ulong *,ulong *)
0x180005ceb  mov     ebx, eax
0x180005ced  cmp     eax, 0Eh
0x180005cf0  jz      loc_180005EC7
0x180005cf6  test    eax, eax
0x180005cf8  jnz     loc_180005EC2
0x180005cfe  mov     r15d, [rbp+57h+arg_8]
0x180005d02  cmp     r15d, 2
0x180005d06  jbe     loc_180005EC2
0x180005d0c  mov     r13, [rbp+57h+hMem]
0x180005d10  shr     r15d, 1
0x180005d13  mov     [rbp+57h+var_80], r13
0x180005d17  xor     r13d, r13d
0x180005d1a  mov     [rbp+57h+arg_0], r13d
0x180005d1e  lea     rax, [rbp+57h+arg_18]
0x180005d22  mov     [rsp+0D0h+var_20], r12
0x180005d2a  mov     [rsp+0D0h+pPrevCertContext], rax; unsigned int *
0x180005d2f  lea     r9, [rbp+57h+pChainContext]; unsigned __int8 **
0x180005d33  lea     rax, [rbp+57h+arg_8]
0x180005d37  mov     [rbp+57h+pChainContext], r13
0x180005d3b  lea     r8, a2543; "2.5.4.3"
0x180005d42  mov     [rsp+0D0h+pvFindPara], rax; unsigned int *
0x180005d47  mov     edx, 1; int
0x180005d4c  mov     [rbp+57h+arg_8], r13d
0x180005d50  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180005d53  mov     [rbp+57h+arg_18], r13d
0x180005d57  mov     r12, r13
0x180005d5a  call    ?GetCertName@@YAKPEBU_CERT_CONTEXT@@HPEADPEAPEAEPEAK3@Z; GetCertName(_CERT_CONTEXT const *,int,char *,uchar * *,ulong *,ulong *)
0x180005d5f  mov     ebx, eax
0x180005d61  cmp     eax, 0Eh
0x180005d64  jz      loc_180005F0E
0x180005d6a  test    eax, eax
0x180005d6c  jnz     loc_180005F09
0x180005d72  mov     eax, [rbp+57h+arg_8]
0x180005d75  cmp     eax, 2
0x180005d78  jbe     loc_180005F09
0x180005d7e  mov     r13, [rbp+57h+pChainContext]
0x180005d82  shr     eax, 1
0x180005d84  mov     [rbp+57h+hMem], r13
0x180005d88  mov     [rbp+57h+arg_18], eax
0x180005d8b  mov     [rbp+57h+arg_0], ebx
0x180005d8e  lea     rcx, [rsi+10h]; Resource
0x180005d92  mov     dl, 1; Wait
0x180005d94  call    cs:__imp_RtlAcquireResourceShared
0x180005d9a  xorps   xmm0, xmm0
0x180005d9d  xor     ebx, ebx
0x180005d9f  mov     eax, 490h
0x180005da4  mov     [rbp+57h+pChainContext], rbx
0x180005da8  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x180005dac  mov     [rbp+57h+pChainPara.cbSize], 20h ; ' '
0x180005db3  xor     r13d, r13d
0x180005db6  mov     [rbp+57h+arg_8], eax
0x180005db9  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180005dbd  cmp     r13d, [rsi+98h]
0x180005dc4  jnb     loc_180005F93
0x180005dca  test    rbx, rbx
0x180005dcd  jz      short loc_180005DD8
0x180005dcf  mov     rcx, rbx; pCertContext
0x180005dd2  call    cs:__imp_CertFreeCertificateContext
0x180005dd8  mov     rax, [rsi+90h]
0x180005ddf  lea     rcx, ds:0[r13*8]
0x180005de7  mov     [rbp+57h+var_78], rcx
0x180005deb  mov     r9d, 0C0000h; dwFindType
0x180005df1  mov     [rsp+0D0h+pPrevCertContext], 0; pPrevCertContext
0x180005dfa  xor     r8d, r8d; dwFindFlags
0x180005dfd  mov     edx, 10001h; dwCertEncodingType
0x180005e02  mov     [rsp+0D0h+pvFindPara], rdi; pvFindPara
0x180005e07  mov     rcx, [rcx+rax]
0x180005e0b  mov     rcx, [rcx+838h]; hCertStore
0x180005e12  call    cs:__imp_CertFindCertificateInStore
0x180005e18  mov     rbx, rax
0x180005e1b  test    rax, rax
0x180005e1e  jz      loc_180005F70
0x180005e24  cmp     dword ptr [rsi+15Ch], 0
0x180005e2b  jz      loc_180005F7B
0x180005e31  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x180005e35  test    rcx, rcx
0x180005e38  jz      short loc_180005E48
0x180005e3a  call    cs:__imp_CertFreeCertificateChain
0x180005e40  mov     [rbp+57h+pChainContext], 0
0x180005e48  mov     rax, [rsi+90h]
0x180005e4f  xor     r9d, r9d; hAdditionalStore
0x180005e52  mov     rcx, [rbp+57h+var_78]
0x180005e56  xor     r8d, r8d; pTime
0x180005e59  mov     rdx, rdi; pCertContext
0x180005e5c  mov     rcx, [rcx+rax]
0x180005e60  lea     rax, [rbp+57h+pChainContext]
0x180005e64  mov     [rsp+38h], rax; ppChainContext
0x180005e69  lea     rax, [rbp+57h+pChainPara]
0x180005e6d  mov     [rsp+0D0h+pvReserved], 0; pvReserved
0x180005e76  mov     dword ptr [rsp+0D0h+pPrevCertContext], 0; dwFlags
0x180005e7e  mov     rcx, [rcx+850h]; hChainEngine
0x180005e85  mov     [rsp+0D0h+pvFindPara], rax; pChainPara
0x180005e8a  call    cs:__imp_CertGetCertificateChain
0x180005e90  test    eax, eax
0x180005e92  jnz     loc_180005F54
0x180005e98  call    cs:__imp_GetLastError
0x180005e9e  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180005ea5  mov     [rbp+57h+arg_8], eax
0x180005ea8  jz      loc_180005F73
0x180005eae  mov     r9d, eax
0x180005eb1  lea     r8, aFindprovfromce; "FindProvFromCertificate CertGetCertific"...
0x180005eb8  call    McTemplateU0sq_EtwEventWriteTransfer
0x180005ebd  jmp     loc_180005F70
0x180005ec2  mov     ebx, 57h ; 'W'
0x180005ec7  mov     rcx, [rbp+57h+hMem]; hMem
0x180005ecb  mov     r15d, r13d
0x180005ece  mov     [rbp+57h+var_80], r13
0x180005ed2  test    rcx, rcx
0x180005ed5  jz      short loc_180005EDD
0x180005ed7  call    cs:__imp_LocalFree
0x180005edd  mov     [rbp+57h+arg_0], ebx
0x180005ee0  test    ebx, ebx
0x180005ee2  jz      loc_180005D1E
0x180005ee8  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180005eef  jz      loc_180006144
0x180005ef5  mov     r9d, ebx
0x180005ef8  lea     r8, aGetnamefromcer; "GetNameFromCert(Issuer)"
0x180005eff  call    McTemplateU0sq_EtwEventWriteTransfer
0x180005f04  jmp     loc_180006144
0x180005f09  mov     ebx, 57h ; 'W'
0x180005f0e  mov     rcx, [rbp+57h+pChainContext]; hMem
0x180005f12  mov     [rbp+57h+hMem], r13
0x180005f16  mov     [rbp+57h+arg_18], 0
0x180005f1d  test    rcx, rcx
0x180005f20  jz      short loc_180005F28
0x180005f22  call    cs:__imp_LocalFree
0x180005f28  mov     [rbp+57h+arg_0], ebx
0x180005f2b  test    ebx, ebx
0x180005f2d  jz      loc_180005D8E
0x180005f33  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180005f3a  jz      loc_1800060FF
0x180005f40  mov     r9d, ebx
0x180005f43  lea     r8, aGetnamefromcer_0; "GetNameFromCert(Subject)"
0x180005f4a  call    McTemplateU0sq_EtwEventWriteTransfer
0x180005f4f  jmp     loc_1800060FF
0x180005f54  mov     rcx, [rbp+57h+pChainContext]
0x180005f58  test    rcx, rcx
0x180005f5b  jz      short loc_180005F70
0x180005f5d  cmp     dword ptr [rcx+0Ch], 0
0x180005f61  jz      short loc_180005F70
0x180005f63  mov     rax, [rcx+10h]
0x180005f67  mov     rcx, [rax]
0x180005f6a  cmp     dword ptr [rcx+0Ch], 0
0x180005f6e  jnz     short loc_180005F7B
0x180005f70  mov     eax, [rbp+57h+arg_8]
0x180005f73  inc     r13d
0x180005f76  jmp     loc_180005DBD
0x180005f7b  mov     rax, [rsi+90h]
0x180005f82  mov     rcx, [rbp+57h+var_78]
0x180005f86  mov     [rbp+57h+arg_8], 0
0x180005f8d  mov     rdi, [rcx+rax]
0x180005f91  jmp     short loc_180005F9A
0x180005f93  xor     edi, edi
0x180005f95  test    rbx, rbx
0x180005f98  jz      short loc_180005FA6
0x180005f9a  mov     rcx, rbx; pCertContext
0x180005f9d  call    cs:__imp_CertFreeCertificateContext
0x180005fa3  mov     eax, [rbp+57h+arg_8]
0x180005fa6  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x180005faa  test    rcx, rcx
0x180005fad  jz      short loc_180005FB8
0x180005faf  call    cs:__imp_CertFreeCertificateChain
0x180005fb5  mov     eax, [rbp+57h+arg_8]
0x180005fb8  mov     [rbp+57h+arg_0], eax
0x180005fbb  test    eax, eax
0x180005fbd  jz      short loc_180005FEA
0x180005fbf  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180005fc6  jz      short loc_180005FD7
0x180005fc8  mov     r9d, eax
0x180005fcb  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x180005fd2  call    McTemplateU0sq_EtwEventWriteTransfer
0x180005fd7  lea     rcx, [rsi+10h]; Resource
0x180005fdb  call    cs:__imp_RtlReleaseResource
0x180005fe1  mov     r13, [rbp+57h+hMem]
0x180005fe5  jmp     loc_1800060FF
0x180005fea  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180005ff1  mov     r13, [rbp+57h+hMem]
0x180005ff5  jz      short loc_180006006
0x180005ff7  mov     r8, r13
0x180005ffa  lea     rdx, CertSubjectName
0x180006001  call    McTemplateU0z_EtwEventWriteTransfer
0x180006006  lea     rbx, [rdi+630h]
0x18000600d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006014  inc     rax
0x180006017  cmp     word ptr [rbx+rax*2], 0
0x18000601c  jnz     short loc_180006014
0x18000601e  lea     ecx, [rax+r15]
0x180006022  cmp     ecx, eax
0x180006024  jb      loc_1800060EE
0x18000602a  mov     edx, [rbp+57h+arg_18]
0x18000602d  add     edx, ecx
0x18000602f  cmp     edx, ecx
0x180006031  jb      loc_1800060EE
0x180006037  lea     eax, [rdx+3]
0x18000603a  cmp     eax, edx
0x18000603c  jb      loc_1800060EE
0x180006042  mov     edi, eax
0x180006044  mov     ecx, 0FFFFFFFFh
0x180006049  add     rax, rax
0x18000604c  cmp     rax, rcx
0x18000604f  ja      loc_1800060EE
0x180006055  mov     rcx, gs:60h
0x18000605e  xor     edx, edx; Flags
0x180006060  mov     r8d, eax; Size
0x180006063  mov     rcx, [rcx+30h]; HeapHandle
0x180006067  call    cs:__imp_RtlAllocateHeap
0x18000606d  mov     r12, rax
0x180006070  test    rax, rax
0x180006073  jnz     short loc_18000607F
0x180006075  mov     edx, 0Eh
0x18000607a  mov     [rbp+57h+arg_0], edx
0x18000607d  jmp     short loc_1800060F5
0x18000607f  mov     rax, [rbp+57h+var_80]
0x180006083  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x18000608a  mov     [rsp+0D0h+pPrevCertContext], r13
0x18000608f  mov     r9, rbx
0x180006092  mov     rdx, rdi; unsigned __int64
0x180006095  mov     [rsp+0D0h+pvFindPara], rax
0x18000609a  mov     rcx, r12; unsigned __int16 *
0x18000609d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800060a2  lea     rcx, [rsi+10h]; Resource
0x1800060a6  test    eax, eax
0x1800060a8  jns     short loc_1800060B3
0x1800060aa  mov     [rbp+57h+arg_0], 216h
0x1800060b1  jmp     short loc_1800060F9
0x1800060b3  call    cs:__imp_RtlReleaseResource
0x1800060b9  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800060c0  jz      short loc_1800060D1
0x1800060c2  mov     r8, r12
0x1800060c5  lea     rdx, UserName
0x1800060cc  call    McTemplateU0z_EtwEventWriteTransfer
0x1800060d1  mov     rdx, r12; SourceString
0x1800060d4  mov     rcx, r14; DestinationString
0x1800060d7  call    cs:__imp_RtlCreateUnicodeString
0x1800060dd  xor     ecx, ecx
0x1800060df  mov     edx, 0Eh
0x1800060e4  test    al, al
0x1800060e6  cmovz   ecx, edx
0x1800060e9  mov     [rbp+57h+arg_0], ecx
0x1800060ec  jmp     short loc_1800060FF
0x1800060ee  mov     [rbp+57h+arg_0], 6Fh ; 'o'
0x1800060f5  lea     rcx, [rsi+10h]; Resource
0x1800060f9  call    cs:__imp_RtlReleaseResource
0x1800060ff  mov     rax, [rbp+57h+var_80]
0x180006103  test    rax, rax
0x180006106  jz      short loc_180006111
0x180006108  mov     rcx, rax; hMem
0x18000610b  call    cs:__imp_LocalFree
0x180006111  test    r13, r13
0x180006114  jz      short loc_18000611F
0x180006116  mov     rcx, r13; hMem
  ... truncated ...
```
