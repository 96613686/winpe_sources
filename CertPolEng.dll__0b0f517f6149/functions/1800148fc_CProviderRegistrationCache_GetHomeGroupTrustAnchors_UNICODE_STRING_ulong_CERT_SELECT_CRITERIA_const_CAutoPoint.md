# CProviderRegistrationCache::GetHomeGroupTrustAnchors(_UNICODE_STRING *,ulong,_CERT_SELECT_CRITERIA const *,CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>> &)

- ea: `0x1800148fc`
- end: `0x180014b4e`
- name: `?GetHomeGroupTrustAnchors@CProviderRegistrationCache@@QEAAKPEAU_UNICODE_STRING@@KPEBU_CERT_SELECT_CRITERIA@@AEAV?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, int *, struct _CERT_SELECT_CRITERIA *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014c2c`

## callees

- `0x180003dc0`
- `0x180007bc0`
- `0x180007ea0`
- `0x18000c344`
- `0x18000ddf0`
- `0x1800143c0`
- `0x1800148fc`
- `0x180014b54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b1e`
- `CRYPT32!CertSelectCertificateChains` at `0x180014ac7`
- `CRYPT32!CertSelectCertificateChains` at `0x180014ac7`

## string_xrefs

- `0x180014965`: `CProviderRegistrationCache::GetHomeGroupTrustAnchors`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetHomeGroupTrustAnchors(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        int *a3,
        struct _CERT_SELECT_CRITERIA *a4,
        _QWORD *a5)
{
  unsigned int v6; // esi
  struct _CERT_SELECT_CRITERIA *v9; // rdi
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  void *v13; // rbx
  CProviderRegistrationCache *i; // rcx
  DWORD LastError; // eax
  __int64 v16; // rcx
  unsigned int v17; // ebx
  unsigned __int16 *v19; // [rsp+40h] [rbp-61h] BYREF
  struct _CERT_SELECT_CRITERIA *v20; // [rsp+48h] [rbp-59h] BYREF
  struct _CERT_SELECT_CRITERIA hMem; // [rsp+50h] [rbp-51h] BYREF
  __int128 v22; // [rsp+60h] [rbp-41h] BYREF
  __int128 v23; // [rsp+70h] [rbp-31h]
  CERT_SELECT_CHAIN_PARA pChainParameters; // [rsp+80h] [rbp-21h] BYREF
  _BYTE v25[40]; // [rsp+A8h] [rbp+7h] BYREF
  unsigned int HostNameFromTargetName; // [rsp+110h] [rbp+6Fh] BYREF
  void *v27; // [rsp+118h] [rbp+77h] BYREF

  v6 = (unsigned int)a3;
  HostNameFromTargetName = 0;
  *(_QWORD *)&hMem.dwType = 0;
  v19 = 0;
  LODWORD(v27) = 0;
  v9 = 0;
  v20 = 0;
  memset(&pChainParameters, 0, sizeof(pChainParameters));
  v22 = 0;
  v23 = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v25,
    "CProviderRegistrationCache::GetHomeGroupTrustAnchors",
    a3,
    0,
    &HostNameFromTargetName);
  HostNameFromTargetName = GetHostNameFromTargetName(a2, (unsigned __int16 **)&hMem, &v19);
  v13 = *(void **)&hMem.dwType;
  if ( !HostNameFromTargetName )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v11, TargetNameAndHostName, *(_QWORD *)&hMem.dwType, v19);
    for ( i = 0; (unsigned int)i < v6; i = (CProviderRegistrationCache *)(unsigned int)((_DWORD)i + 1) )
    {
      if ( a4[(unsigned int)i].dwType == 6 )
      {
        HostNameFromTargetName = 0;
        goto LABEL_11;
      }
    }
    HostNameFromTargetName = 0;
    *(_QWORD *)&hMem.dwType = 0x100000006LL;
    hMem.ppPara = (void **)&v19;
    HostNameFromTargetName = CProviderRegistrationCache::ConstructNewSelectionCriteria(
                               i,
                               v6,
                               a4,
                               v12,
                               &hMem,
                               (unsigned int *)&v27,
                               (const struct _CERT_SELECT_CRITERIA **)&v20);
    v9 = v20;
    if ( HostNameFromTargetName )
      goto LABEL_18;
    v6 = (unsigned int)v27;
    a4 = v20;
LABEL_11:
    if ( !*(_QWORD *)(a1 + 320) )
      goto LABEL_17;
    v10 = operator new(0x18u);
    v27 = v10;
    if ( !v10 )
    {
      *a5 = 0;
      HostNameFromTargetName = 14;
      goto LABEL_18;
    }
    *v10 = &CCertChainList::`vftable';
    v10[2] = 0;
    *((_DWORD *)v10 + 2) = 0;
    *a5 = v10;
    LODWORD(v22) = 32;
    DWORD2(v22) = 0;
    LODWORD(v23) = 0;
    *((_QWORD *)&v23 + 1) = 0;
    memset(&pChainParameters, 0, 24);
    pChainParameters.pChainPara = (PCERT_CHAIN_PARA)&v22;
    pChainParameters.dwFlags = -2147483644;
    if ( CertSelectCertificateChains(
           0,
           0,
           &pChainParameters,
           v6,
           a4,
           *(HCERTSTORE *)(a1 + 320),
           (PDWORD)v10 + 2,
           (PCCERT_CHAIN_CONTEXT **)v10 + 2) )
    {
LABEL_17:
      HostNameFromTargetName = 0;
    }
    else
    {
      LastError = GetLastError();
      HostNameFromTargetName = LastError;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v16, v10, "HomeGroupCert::CertSelectCertificateChains", LastError);
    }
  }
LABEL_18:
  if ( v13 )
    LocalFree(v13);
  if ( v9 )
    LocalFree(v9);
  v17 = HostNameFromTargetName;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v25, (__int64)v10);
  return v17;
}

```

## disassembly

```asm
0x1800148fc  mov     [rsp-8+arg_0], rbx
0x180014901  mov     [rsp-8+arg_8], rsi
0x180014906  push    rbp
0x180014907  push    rdi
0x180014908  push    r12
0x18001490a  push    r14
0x18001490c  push    r15
0x18001490e  lea     rbp, [rsp-2Fh]
0x180014913  sub     rsp, 0D0h
0x18001491a  mov     r14, r9
0x18001491d  mov     esi, r8d
0x180014920  mov     rbx, rdx
0x180014923  mov     r15, rcx
0x180014926  xor     r12d, r12d
0x180014929  mov     [rbp+4Fh+arg_10], r12d
0x18001492d  mov     [rbp+4Fh+hMem], r12
0x180014931  mov     [rbp+4Fh+var_B0], r12
0x180014935  mov     dword ptr [rbp+4Fh+arg_18], r12d
0x180014939  mov     edi, r12d
0x18001493c  mov     [rbp+4Fh+var_A8], r12
0x180014940  xorps   xmm0, xmm0
0x180014943  xor     eax, eax
0x180014945  movups  xmmword ptr [rbp+4Fh+pChainParameters.hChainEngine], xmm0
0x180014949  movups  xmmword ptr [rbp+4Fh+pChainParameters.hAdditionalStore], xmm0
0x18001494d  mov     qword ptr [rbp+4Fh+pChainParameters.dwFlags], rax
0x180014951  movups  [rbp+4Fh+var_90], xmm0
0x180014955  movups  [rbp+4Fh+var_80], xmm0
0x180014959  lea     rax, [rbp+4Fh+arg_10]
0x18001495d  mov     [rsp+0F0h+rgpCriteria], rax; unsigned int *
0x180014962  xor     r9d, r9d; int *
0x180014965  lea     rdx, aCproviderregis_6; "CProviderRegistrationCache::GetHomeGrou"...
0x18001496c  lea     rcx, [rbp+4Fh+var_48]; this
0x180014970  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180014975  nop
0x180014976  lea     r8, [rbp+4Fh+var_B0]; unsigned __int16 **
0x18001497a  lea     rdx, [rbp+4Fh+hMem]; unsigned __int16 **
0x18001497e  mov     rcx, rbx; struct _UNICODE_STRING *
0x180014981  call    ?GetHostNameFromTargetName@@YAKPEAU_UNICODE_STRING@@PEAPEAG1@Z; GetHostNameFromTargetName(_UNICODE_STRING *,ushort * *,ushort * *)
0x180014986  mov     [rbp+4Fh+arg_10], eax
0x180014989  mov     rbx, [rbp+4Fh+hMem]
0x18001498d  test    eax, eax
0x18001498f  jnz     loc_180014B08
0x180014995  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18001499c  jz      short loc_1800149B1
0x18001499e  mov     r9, [rbp+4Fh+var_B0]
0x1800149a2  mov     r8, rbx
0x1800149a5  lea     rdx, TargetNameAndHostName
0x1800149ac  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800149b1  mov     ecx, r12d; this
0x1800149b4  cmp     ecx, esi
0x1800149b6  jnb     short loc_1800149CE
0x1800149b8  mov     eax, ecx
0x1800149ba  add     rax, rax
0x1800149bd  cmp     dword ptr [r14+rax*8], 6
0x1800149c2  jz      short loc_1800149C8
0x1800149c4  inc     ecx
0x1800149c6  jmp     short loc_1800149B4
0x1800149c8  mov     [rbp+4Fh+arg_10], r12d
0x1800149cc  jmp     short loc_180014A22
0x1800149ce  mov     [rbp+4Fh+arg_10], r12d
0x1800149d2  mov     dword ptr [rbp+4Fh+hMem], 6
0x1800149d9  mov     dword ptr [rbp+4Fh+hMem+4], 1
0x1800149e0  lea     rax, [rbp+4Fh+var_B0]
0x1800149e4  mov     [rbp+4Fh+var_98], rax
0x1800149e8  lea     rax, [rbp+4Fh+var_A8]
0x1800149ec  mov     [rsp+0F0h+pcSelection], rax; struct _CERT_SELECT_CRITERIA **
0x1800149f1  lea     rax, [rbp+4Fh+arg_18]
0x1800149f5  mov     [rsp+0F0h+hStore], rax; unsigned int *
0x1800149fa  lea     rax, [rbp+4Fh+hMem]
0x1800149fe  mov     [rsp+0F0h+rgpCriteria], rax; struct _CERT_SELECT_CRITERIA *
0x180014a03  mov     r8, r14; struct _CERT_SELECT_CRITERIA *
0x180014a06  mov     edx, esi; unsigned int
0x180014a08  call    ?ConstructNewSelectionCriteria@CProviderRegistrationCache@@QEAAKKPEBU_CERT_SELECT_CRITERIA@@K0PEAKPEAPEBU2@@Z; CProviderRegistrationCache::ConstructNewSelectionCriteria(ulong,_CERT_SELECT_CRITERIA const *,ulong,_CERT_SELECT_CRITERIA const *,ulong *,_CERT_SELECT_CRITERIA const * *)
0x180014a0d  mov     [rbp+4Fh+arg_10], eax
0x180014a10  mov     rdi, [rbp+4Fh+var_A8]
0x180014a14  test    eax, eax
0x180014a16  jnz     loc_180014B08
0x180014a1c  mov     esi, dword ptr [rbp+4Fh+arg_18]
0x180014a1f  mov     r14, rdi
0x180014a22  cmp     [r15+140h], r12
0x180014a29  jz      loc_180014B04
0x180014a2f  mov     ecx, 18h; Size
0x180014a34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014a39  mov     rdx, rax
0x180014a3c  mov     [rbp+4Fh+arg_18], rax
0x180014a40  test    rax, rax
0x180014a43  jz      loc_180014AF4
0x180014a49  lea     rax, ??_7CCertChainList@@6B@; const CCertChainList::`vftable'
0x180014a50  mov     [rdx], rax
0x180014a53  mov     [rdx+10h], r12
0x180014a57  mov     [rdx+8], r12d
0x180014a5b  mov     rcx, [rbp+4Fh+arg_20]
0x180014a5f  mov     [rcx], rdx
0x180014a62  test    rdx, rdx
0x180014a65  jz      loc_180014AFB
0x180014a6b  mov     dword ptr [rbp+4Fh+var_90], 20h ; ' '
0x180014a72  mov     dword ptr [rbp+4Fh+var_90+8], r12d
0x180014a76  mov     dword ptr [rbp+4Fh+var_80], r12d
0x180014a7a  mov     qword ptr [rbp+4Fh+var_80+8], r12
0x180014a7e  xorps   xmm0, xmm0
0x180014a81  movdqu  xmmword ptr [rbp+4Fh+pChainParameters.hChainEngine], xmm0
0x180014a86  mov     [rbp+4Fh+pChainParameters.hAdditionalStore], r12
0x180014a8a  lea     rax, [rbp+4Fh+var_90]
0x180014a8e  mov     [rbp+4Fh+pChainParameters.pChainPara], rax
0x180014a92  mov     [rbp+4Fh+pChainParameters.dwFlags], 80000004h
0x180014a99  lea     rax, [rdx+10h]
0x180014a9d  lea     rcx, [rdx+8]
0x180014aa1  mov     [rsp+0F0h+pprgpSelection], rax; pprgpSelection
0x180014aa6  mov     [rsp+0F0h+pcSelection], rcx; pcSelection
0x180014aab  mov     rax, [r15+140h]
0x180014ab2  mov     [rsp+0F0h+hStore], rax; hStore
0x180014ab7  mov     [rsp+0F0h+rgpCriteria], r14; rgpCriteria
0x180014abc  mov     r9d, esi; cCriteria
0x180014abf  lea     r8, [rbp+4Fh+pChainParameters]; pChainParameters
0x180014ac3  xor     edx, edx; dwFlags
0x180014ac5  xor     ecx, ecx; pSelectionContext
0x180014ac7  call    cs:__imp_CertSelectCertificateChains
0x180014acd  test    eax, eax
0x180014acf  jnz     short loc_180014B04
0x180014ad1  call    cs:__imp_GetLastError
0x180014ad7  mov     [rbp+4Fh+arg_10], eax
0x180014ada  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180014ae1  jz      short loc_180014B08
0x180014ae3  mov     r9d, eax
0x180014ae6  lea     r8, aHomegroupcertC; "HomeGroupCert::CertSelectCertificateCha"...
0x180014aed  call    McTemplateU0sq_EtwEventWriteTransfer
0x180014af2  jmp     short loc_180014B08
0x180014af4  mov     rax, [rbp+4Fh+arg_20]
0x180014af8  mov     [rax], r12
0x180014afb  mov     [rbp+4Fh+arg_10], 0Eh
0x180014b02  jmp     short loc_180014B08
0x180014b04  mov     [rbp+4Fh+arg_10], r12d
0x180014b08  test    rbx, rbx
0x180014b0b  jz      short loc_180014B16
0x180014b0d  mov     rcx, rbx; hMem
0x180014b10  call    cs:__imp_LocalFree
0x180014b16  test    rdi, rdi
0x180014b19  jz      short loc_180014B24
0x180014b1b  mov     rcx, rdi; hMem
0x180014b1e  call    cs:__imp_LocalFree
0x180014b24  mov     ebx, [rbp+4Fh+arg_10]
0x180014b27  lea     rcx, [rbp+4Fh+var_48]; this
0x180014b2b  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180014b30  mov     eax, ebx
0x180014b32  lea     r11, [rsp+0F0h+var_20]
0x180014b3a  mov     rbx, [r11+30h]
0x180014b3e  mov     rsi, [r11+38h]
0x180014b42  mov     rsp, r11
0x180014b45  pop     r15
0x180014b47  pop     r14
0x180014b49  pop     r12
0x180014b4b  pop     rdi
0x180014b4c  pop     rbp
0x180014b4d  retn
```
