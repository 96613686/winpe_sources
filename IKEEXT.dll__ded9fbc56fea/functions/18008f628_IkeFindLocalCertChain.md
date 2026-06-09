# IkeFindLocalCertChain

- ea: `0x18008f628`
- end: `0x18008fe90`
- name: `IkeFindLocalCertChain`
- size: `2152`
- prototype: ``
- caller_count: `6`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e3378`
- `0x1800e3d54`
- `0x1800e4224`
- `0x1800e5478`
- `0x1800e638c`
- `0x1800e66d8`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004a868`
- `0x18004aa3c`
- `0x18004d2a8`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`
- `0x180088aac`
- `0x180089f48`
- `0x18008a210`
- `0x18008b6e0`
- `0x18008c8cc`
- `0x18008d148`
- `0x18008f628`
- `0x1800900cc`
- `0x180090584`
- `0x180090700`
- `0x180090874`
- `0x180091058`
- `0x180091270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f714`
- `CRYPT32!CertFreeCertificateContext` at `0x18008f92c`
- `CRYPT32!CertFreeCertificateContext` at `0x18008f92c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fe74`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fe74`
- `CRYPT32!CertOpenStore` at `0x18008f701`
- `CRYPT32!CertOpenStore` at `0x18008f701`
- `CRYPT32!CertFreeCertificateChain` at `0x18008f90e`
- `CRYPT32!CertFreeCertificateChain` at `0x18008f90e`
- `CRYPT32!CertCloseStore` at `0x18008f91e`
- `CRYPT32!CertCloseStore` at `0x18008f91e`
- `ncrypt!NCryptFreeObject` at `0x18008f95c`
- `ncrypt!NCryptFreeObject` at `0x18008f95c`

## string_xrefs

- `0x18008f71d`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeFindLocalCertChain(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int *a4,
        _BYTE *a5,
        NCRYPT_HANDLE *a6,
        __int64 a7,
        PCCERT_CONTEXT *a8)
{
  __int64 v9; // r12
  unsigned int v10; // edi
  const CERT_CONTEXT *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  void *v15; // r14
  DWORD LastError; // eax
  __int64 v17; // rcx
  __int64 SigKeyProv; // rbx
  int *v19; // rbx
  unsigned int AuthType; // r14d
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  int TlsMmLuid; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // r8d
  int v35; // r9d
  __int64 CertInfo; // r13
  __int64 v37; // r15
  __int64 OptionalLocalCertHashFromAcquire; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  const CERT_CONTEXT *v47; // rbx
  __int64 v49; // rdi
  __int64 v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rdi
  __int64 v65; // rbx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rax
  int v73; // r8d
  __int64 v74; // rdi
  __int64 v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  int v80; // eax
  __int64 v81; // rcx
  __int64 v82; // rax
  int v83; // r8d
  int v84; // r9d
  __int64 v85; // rdi
  __int64 v86; // rbx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  int v91; // eax
  __int64 v92; // rcx
  __int64 v93; // rax
  int v94; // r8d
  int v95; // r9d
  const CERT_CONTEXT *v96; // rdi
  unsigned int *v97; // rcx
  PCCERT_CONTEXT v98; // rax
  unsigned int v99; // [rsp+28h] [rbp-D8h]
  unsigned int v100; // [rsp+28h] [rbp-D8h]
  char v101[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v102; // [rsp+54h] [rbp-ACh] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v104; // [rsp+60h] [rbp-A0h]
  __int64 v105; // [rsp+68h] [rbp-98h] BYREF
  __int64 v106; // [rsp+70h] [rbp-90h] BYREF
  __int64 v107; // [rsp+78h] [rbp-88h]
  __int64 v108; // [rsp+80h] [rbp-80h]
  _QWORD *v109; // [rsp+88h] [rbp-78h]
  unsigned int *v110; // [rsp+90h] [rbp-70h]
  _BYTE *v111; // [rsp+98h] [rbp-68h]
  NCRYPT_HANDLE *v112; // [rsp+A0h] [rbp-60h]
  PCCERT_CONTEXT *v113; // [rsp+A8h] [rbp-58h]
  _DWORD v114[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v115; // [rsp+B8h] [rbp-48h]
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v117[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v118; // [rsp+D8h] [rbp-28h]
  int v119; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v120; // [rsp+F8h] [rbp-8h] BYREF
  char v121[24]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v122; // [rsp+120h] [rbp+20h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+128h] [rbp+28h]
  __int128 v124; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v125[32]; // [rsp+140h] [rbp+40h] BYREF
  __int64 *v126; // [rsp+160h] [rbp+60h]
  __int64 v127; // [rsp+168h] [rbp+68h]
  _BYTE v128[16]; // [rsp+170h] [rbp+70h] BYREF
  const char *v129; // [rsp+180h] [rbp+80h]
  __int64 v130; // [rsp+188h] [rbp+88h]

  v111 = a5;
  v112 = a6;
  v9 = 0;
  v10 = 0;
  v108 = a7;
  v109 = a3;
  v107 = a2;
  v113 = a8;
  v110 = a4;
  v106 = 0;
  pChainContext[0] = 0;
  v105 = 0;
  v102 = 0;
  v101[0] = 0;
  hObject = 0;
  memset_0(v117, 0, 0x50u);
  pCertContext = 0;
  v114[1] = 0;
  v124 = 0;
  v11 = 0;
  TraceLogHelper("IkeFindLocalCertChain", 1);
  v104 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20001u, L"My");
  v15 = v104;
  if ( !v104 )
  {
    LastError = GetLastError();
    SigKeyProv = WfpReportSysErrorAsWinError(v17, "CertOpenStore", LastError, 1);
    goto LABEL_23;
  }
  v19 = (int *)(a1 + 584);
  if ( *(_DWORD *)(a1 + 584) == 2 )
    AuthType = *(_DWORD *)(*(_QWORD *)(a1 + 1104) + 500LL);
  else
    AuthType = IkeGetAuthType(*(_QWORD *)(a1 + 744), v12, v13, v14);
  IkeGetCertAuthFromPolicy(*(_QWORD *)(a1 + 736), AuthType, &v106);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v22);
    TlsMmLuid = IkeGetTlsMmLuid(v28, v27, v29, v30);
    WPP_SF_iS(v25, 115, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr);
    v19 = (int *)(a1 + 584);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v122 = IkeGetTlsMmLuid(v22, v21, v23, v24);
    v126 = &v122;
    v127 = 8;
    v33 = IkeGetTlsPeerAddr(v32);
    tlgCreate1Sz_wchar_t(v128, v33);
    v130 = 30;
    v129 = "Constructing local cert chain";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180156BAB,
      v34,
      v35,
      5,
      (__int64)v125);
  }
  CertInfo = IkeGetCertInfo(a1);
  v37 = v106;
  v118 = *v19;
  if ( v118 == 2 && *(_DWORD *)(v106 + 56) && (*(_DWORD *)(a1 + 592) & 0x80000) != 0 )
    OptionalLocalCertHashFromAcquire = IkeDownloadCertInfoFromUrl(
                                         (int)v106 + 56,
                                         *(_DWORD *)(v106 + 48) & 0x20,
                                         (unsigned int)&v124,
                                         (unsigned int)&v119,
                                         0,
                                         0,
                                         0,
                                         0);
  else
    OptionalLocalCertHashFromAcquire = IkeGetOptionalLocalCertHashFromAcquire(a1, 0, &v119);
  SigKeyProv = OptionalLocalCertHashFromAcquire;
  if ( OptionalLocalCertHashFromAcquire )
    goto LABEL_21;
  if ( !v119 )
  {
    if ( *(_QWORD *)(CertInfo + 8) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v74 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v75 = IkeGetTlsPeerAddr(v40);
        v80 = IkeGetTlsMmLuid(v77, v76, v78, v79);
        WPP_SF_iS(v74, 118, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v80, v75);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v122 = IkeGetTlsMmLuid(v40, v39, v41, v42);
        v126 = &v122;
        v127 = 8;
        v82 = IkeGetTlsPeerAddr(v81);
        tlgCreate1Sz_wchar_t(v128, v82);
        v130 = 25;
        v129 = "Taking into account CRPs";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_180156AE2,
          v83,
          v84,
          5,
          (__int64)v125);
      }
      SigKeyProv = IkeChainSelect(
                     (_DWORD)v104,
                     0,
                     *(_QWORD *)(CertInfo + 8),
                     *(_DWORD *)(CertInfo + 16),
                     v37,
                     AuthType,
                     (__int64)v117,
                     0,
                     (__int64)pChainContext);
    }
    if ( !SigKeyProv && *(_QWORD *)(CertInfo + 8) )
    {
      v15 = v104;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v85 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v86 = IkeGetTlsPeerAddr(v40);
        v91 = IkeGetTlsMmLuid(v88, v87, v89, v90);
        WPP_SF_iS(v85, 119, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v91, v86);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v122 = IkeGetTlsMmLuid(v40, v39, v41, v42);
        v126 = &v122;
        v127 = 8;
        v93 = IkeGetTlsPeerAddr(v92);
        tlgCreate1Sz_wchar_t(v128, v93);
        v130 = 40;
        v129 = "Trying WITHOUT taking into account CRPs";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&dword_180156AA4,
          v94,
          v95,
          5,
          (__int64)v125);
      }
      v100 = AuthType;
      v15 = v104;
      SigKeyProv = IkeChainSelect((_DWORD)v104, 0, 0, 0, v37, v100, (__int64)v117, v107, (__int64)pChainContext);
      if ( SigKeyProv )
        goto LABEL_22;
    }
LABEL_65:
    SigKeyProv = IkeCopyRootPolicyToSA(v121, CertInfo + 64);
    if ( !SigKeyProv )
    {
      SigKeyProv = IkeEncodeCertChain(
                     (int)a1 + 584,
                     v37,
                     pChainContext[0],
                     (unsigned int)&v124,
                     (__int64)&v105,
                     (__int64)&v102,
                     (__int64)v101);
      if ( SigKeyProv
        || (v96 = (*(*pChainContext[0]->rgpChain)->rgpElement)->pCertContext, (SigKeyProv = IkeGetSigKeyProv(v96)) != 0)
        || (SigKeyProv = IkeAdjustMMLifetimeFromCert(a1, v96)) != 0
        || (SigKeyProv = IkeGetIDPayloadFromCert(v96, v108)) != 0 )
      {
        v9 = v105;
      }
      else
      {
        v97 = v110;
        v9 = v105;
        *v109 = v105;
        *v97 = v102;
        *v111 = v101[0];
        *v112 = hObject;
        v98 = CertDuplicateCertificateContext(v96);
        *v113 = v98;
      }
    }
    goto LABEL_22;
  }
  v114[0] = v119;
  v115 = v120;
  IkeCertFindByHash(v104, v114, &pCertContext);
  v47 = pCertContext;
  if ( pCertContext )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v49 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v50 = IkeGetTlsPeerAddr(v44);
      v55 = IkeGetTlsMmLuid(v52, v51, v53, v54);
      WPP_SF_iS(v49, 116, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v55, v50);
      v47 = pCertContext;
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v122 = IkeGetTlsMmLuid(v44, v43, v45, v46);
      v126 = &v122;
      v127 = 8;
      v57 = IkeGetTlsPeerAddr(v56);
      tlgCreate1Sz_wchar_t(v128, v57);
      v130 = 47;
      v129 = "Found cert using certificate hash from acquire";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&word_180156A66,
        v58,
        v59,
        5,
        (__int64)v125);
    }
    IkeDumpCert(v47);
    v99 = AuthType;
    v15 = v104;
    SigKeyProv = IkeChainSelect((_DWORD)v104, (_DWORD)v47, 0, 0, v37, v99, (__int64)v117, v107, (__int64)pChainContext);
    if ( SigKeyProv )
      goto LABEL_22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v64 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v65 = IkeGetTlsPeerAddr(v61);
      v70 = IkeGetTlsMmLuid(v67, v66, v68, v69);
      WPP_SF_iS(v64, 117, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v70, v65);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v122 = IkeGetTlsMmLuid(v61, v60, v62, v63);
      v126 = &v122;
      v127 = 8;
      v72 = IkeGetTlsPeerAddr(v71);
      tlgCreate1Sz_wchar_t(v128, v72);
      v130 = 53;
      v129 = "Found cert chain using certificate hash from acquire";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)qword_180156A28,
        v73,
        (unsigned int)"Found cert chain using certificate hash from acquire",
        5,
        (__int64)v125);
    }
    goto LABEL_65;
  }
  SigKeyProv = WfpReportSysErrorAsWinError(v44, "IkeFindLocalCertChain", 13806, 1);
LABEL_21:
  v15 = v104;
LABEL_22:
  v11 = pCertContext;
  v10 = v102;
LABEL_23:
  if ( pChainContext[0] )
    CertFreeCertificateChain(pChainContext[0]);
  if ( v15 )
    CertCloseStore(v15, 0);
  if ( v11 )
    CertFreeCertificateContext(v11);
  WfpMemFree(&v120);
  WfpMemFree((char *)&v124 + 8);
  if ( SigKeyProv )
  {
    IkeFreeEncodedCertArray(v9, v10);
    if ( hObject )
      NCryptFreeObject(hObject);
  }
  TraceLogHelper("IkeFindLocalCertChain", 0);
  return IkeReturnError(SigKeyProv, "IkeFindLocalCertChain");
}

```

## disassembly

```asm
0x18008f628  push    rbp
0x18008f62a  push    rbx
0x18008f62b  push    rsi
0x18008f62c  push    rdi
0x18008f62d  push    r12
0x18008f62f  push    r13
0x18008f631  push    r14
0x18008f633  push    r15
0x18008f635  lea     rbp, [rsp-0A8h]
0x18008f63d  sub     rsp, 1A8h
0x18008f644  mov     rax, cs:__security_cookie
0x18008f64b  xor     rax, rsp
0x18008f64e  mov     [rbp+0E0h+var_50], rax
0x18008f655  mov     rax, [rbp+0E0h+arg_20]
0x18008f65c  xor     ebx, ebx
0x18008f65e  mov     [rbp+0E0h+var_148], rax
0x18008f662  mov     rsi, rcx
0x18008f665  mov     rax, [rbp+0E0h+arg_28]
0x18008f66c  lea     rcx, [rbp+0E0h+var_110]; void *
0x18008f670  mov     [rbp+0E0h+var_140], rax
0x18008f674  mov     r12d, ebx
0x18008f677  mov     rax, [rbp+0E0h+arg_30]
0x18008f67e  mov     edi, ebx
0x18008f680  mov     [rbp+0E0h+var_160], rax
0x18008f684  mov     rax, [rbp+0E0h+arg_38]
0x18008f68b  mov     [rbp+0E0h+var_158], r8
0x18008f68f  lea     r8d, [rbx+50h]; Size
0x18008f693  mov     [rsp+1E0h+var_168], rdx
0x18008f698  xor     edx, edx; Val
0x18008f69a  mov     [rbp+0E0h+var_138], rax
0x18008f69e  mov     [rbp+0E0h+var_150], r9
0x18008f6a2  mov     [rsp+1E0h+var_170], rbx
0x18008f6a7  mov     [rbp+0E0h+pChainContext], rbx
0x18008f6ab  mov     [rsp+1E0h+var_178], rbx
0x18008f6b0  mov     [rsp+1E0h+var_18C], ebx
0x18008f6b4  mov     [rsp+1E0h+var_190], bl
0x18008f6b8  mov     [rbp+0E0h+hObject], rbx
0x18008f6bc  call    memset_0
0x18008f6c1  xorps   xmm0, xmm0
0x18008f6c4  mov     [rsp+1E0h+pCertContext], rbx
0x18008f6c9  lea     r13d, [rbx+1]
0x18008f6cd  mov     [rbp+0E0h+var_12C], ebx
0x18008f6d0  mov     edx, r13d
0x18008f6d3  lea     rcx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f6da  movups  [rbp+0E0h+var_B0], xmm0
0x18008f6de  mov     r15d, ebx
0x18008f6e1  call    TraceLogHelper
0x18008f6e6  lea     rax, aMy; "My"
0x18008f6ed  mov     r9d, 20001h; dwFlags
0x18008f6f3  xor     r8d, r8d; hCryptProv
0x18008f6f6  mov     [rsp+1E0h+pvPara], rax; pvPara
0x18008f6fb  mov     edx, r13d; dwEncodingType
0x18008f6fe  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18008f701  call    cs:__imp_CertOpenStore
0x18008f707  mov     [rsp+1E0h+var_180], rax
0x18008f70c  mov     r14, rax
0x18008f70f  test    rax, rax
0x18008f712  jnz     short loc_18008F734
0x18008f714  call    cs:__imp_GetLastError
0x18008f71a  mov     r9d, r13d
0x18008f71d  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x18008f724  mov     r8d, eax
0x18008f727  call    WfpReportSysErrorAsWinError
0x18008f72c  mov     rbx, rax
0x18008f72f  jmp     loc_18008F905
0x18008f734  lea     rbx, [rsi+248h]
0x18008f73b  cmp     dword ptr [rbx], 2
0x18008f73e  jnz     short loc_18008F750
0x18008f740  mov     rax, [rsi+450h]
0x18008f747  mov     r14d, [rax+1F4h]
0x18008f74e  jmp     short loc_18008F75F
0x18008f750  mov     rcx, [rsi+2E8h]
0x18008f757  call    IkeGetAuthType
0x18008f75c  mov     r14d, eax
0x18008f75f  mov     rcx, [rsi+2E0h]
0x18008f766  lea     r8, [rsp+1E0h+var_170]
0x18008f76b  mov     edx, r14d
0x18008f76e  call    IkeGetCertAuthFromPolicy
0x18008f773  mov     rdi, cs:WPP_GLOBAL_Control
0x18008f77a  lea     rax, WPP_GLOBAL_Control
0x18008f781  cmp     rdi, rax
0x18008f784  jz      short loc_18008F7C6
0x18008f786  cmp     byte ptr [rdi+19h], 4
0x18008f78a  jb      short loc_18008F7C6
0x18008f78c  test    byte ptr [rdi+1Ch], 10h
0x18008f790  jz      short loc_18008F7C6
0x18008f792  mov     rdi, [rdi+10h]
0x18008f796  call    IkeGetTlsPeerAddr
0x18008f79b  mov     rbx, rax
0x18008f79e  call    IkeGetTlsMmLuid
0x18008f7a3  mov     r9, rax
0x18008f7a6  mov     [rsp+1E0h+pvPara], rbx
0x18008f7ab  mov     edx, 73h ; 's'
0x18008f7b0  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008f7b7  mov     rcx, rdi
0x18008f7ba  call    WPP_SF_iS
0x18008f7bf  lea     rbx, [rsi+248h]
0x18008f7c6  mov     eax, cs:dword_180173278
0x18008f7cc  cmp     eax, 4
0x18008f7cf  jbe     short loc_18008F838
0x18008f7d1  call    IkeGetTlsMmLuid
0x18008f7d6  mov     [rbp+0E0h+var_C0], rax
0x18008f7da  lea     rax, [rbp+0E0h+var_C0]
0x18008f7de  mov     [rbp+0E0h+var_80], rax
0x18008f7e2  mov     [rbp+0E0h+var_78], 8
0x18008f7ea  call    IkeGetTlsPeerAddr
0x18008f7ef  mov     rdx, rax
0x18008f7f2  lea     rcx, [rbp+0E0h+var_70]
0x18008f7f6  call    _tlgCreate1Sz_wchar_t
0x18008f7fb  lea     rcx, aConstructingLo; "Constructing local cert chain"
0x18008f802  mov     [rbp+0E0h+var_58], 1Eh
0x18008f80d  lea     rax, [rbp+0E0h+var_A0]
0x18008f811  mov     [rbp+0E0h+var_60], rcx
0x18008f818  mov     [rsp+1E0h+var_1B8], rax
0x18008f81d  lea     rcx, dword_180173278
0x18008f824  lea     rdx, byte_180156BAB
0x18008f82b  mov     dword ptr [rsp+1E0h+pvPara], 5
0x18008f833  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008f838  mov     rcx, rsi
0x18008f83b  call    IkeGetCertInfo
0x18008f840  mov     ecx, [rbx]
0x18008f842  mov     r13, rax
0x18008f845  mov     r15, [rsp+1E0h+var_170]
0x18008f84a  mov     [rbp+0E0h+var_108], ecx
0x18008f84d  cmp     ecx, 2
0x18008f850  jnz     short loc_18008F891
0x18008f852  lea     rcx, [r15+38h]
0x18008f856  cmp     [rcx], r12d
0x18008f859  jbe     short loc_18008F891
0x18008f85b  test    dword ptr [rsi+250h], 80000h
0x18008f865  jz      short loc_18008F891
0x18008f867  mov     edx, [r15+30h]
0x18008f86b  lea     r9, [rbp+0E0h+var_F0]
0x18008f86f  mov     [rsp+1E0h+var_1A8], r12
0x18008f874  lea     r8, [rbp+0E0h+var_B0]
0x18008f878  mov     [rsp+1E0h+var_1B0], r12
0x18008f87d  and     edx, 20h
0x18008f880  mov     [rsp+1E0h+var_1B8], r12
0x18008f885  mov     [rsp+1E0h+pvPara], r12
0x18008f88a  call    IkeDownloadCertInfoFromUrl
0x18008f88f  jmp     short loc_18008F89F
0x18008f891  lea     r8, [rbp+0E0h+var_F0]
0x18008f895  xor     edx, edx
0x18008f897  mov     rcx, rsi
0x18008f89a  call    IkeGetOptionalLocalCertHashFromAcquire
0x18008f89f  mov     rbx, rax
0x18008f8a2  test    rax, rax
0x18008f8a5  jnz     short loc_18008F8F7
0x18008f8a7  mov     eax, [rbp+0E0h+var_F0]
0x18008f8aa  test    eax, eax
0x18008f8ac  jz      loc_18008FB7C
0x18008f8b2  mov     rcx, [rsp+1E0h+var_180]
0x18008f8b7  lea     r8, [rsp+1E0h+pCertContext]
0x18008f8bc  mov     [rbp+0E0h+var_130], eax
0x18008f8bf  lea     rdx, [rbp+0E0h+var_130]
0x18008f8c3  mov     rax, [rbp+0E0h+var_E8]
0x18008f8c7  mov     [rbp+0E0h+var_128], rax
0x18008f8cb  call    IkeCertFindByHash
0x18008f8d0  mov     rbx, [rsp+1E0h+pCertContext]
0x18008f8d5  test    rbx, rbx
0x18008f8d8  jnz     loc_18008F9A2
0x18008f8de  lea     r9d, [rbx+1]
0x18008f8e2  mov     r8d, 35EEh
0x18008f8e8  lea     rdx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f8ef  call    WfpReportSysErrorAsWinError
0x18008f8f4  mov     rbx, rax
0x18008f8f7  mov     r14, [rsp+1E0h+var_180]
0x18008f8fc  mov     r15, [rsp+1E0h+pCertContext]
0x18008f901  mov     edi, [rsp+1E0h+var_18C]
0x18008f905  mov     rcx, [rbp+0E0h+pChainContext]; pChainContext
0x18008f909  test    rcx, rcx
0x18008f90c  jz      short loc_18008F914
0x18008f90e  call    cs:__imp_CertFreeCertificateChain
0x18008f914  test    r14, r14
0x18008f917  jz      short loc_18008F924
0x18008f919  xor     edx, edx; dwFlags
0x18008f91b  mov     rcx, r14; hCertStore
0x18008f91e  call    cs:__imp_CertCloseStore
0x18008f924  test    r15, r15
0x18008f927  jz      short loc_18008F932
0x18008f929  mov     rcx, r15; pCertContext
0x18008f92c  call    cs:__imp_CertFreeCertificateContext
0x18008f932  lea     rcx, [rbp+0E0h+var_E8]
0x18008f936  call    WfpMemFree
0x18008f93b  lea     rcx, [rbp+0E0h+var_B0+8]
0x18008f93f  call    WfpMemFree
0x18008f944  test    rbx, rbx
0x18008f947  jz      short loc_18008F962
0x18008f949  mov     edx, edi
0x18008f94b  mov     rcx, r12
0x18008f94e  call    IkeFreeEncodedCertArray
0x18008f953  mov     rcx, [rbp+0E0h+hObject]; hObject
0x18008f957  test    rcx, rcx
0x18008f95a  jz      short loc_18008F962
0x18008f95c  call    cs:__imp_NCryptFreeObject
0x18008f962  xor     edx, edx
0x18008f964  lea     rcx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f96b  call    TraceLogHelper
0x18008f970  lea     rdx, aIkefindlocalce; "IkeFindLocalCertChain"
0x18008f977  mov     rcx, rbx
0x18008f97a  call    IkeReturnError
0x18008f97f  mov     rcx, [rbp+0E0h+var_50]
0x18008f986  xor     rcx, rsp; StackCookie
0x18008f989  call    __security_check_cookie
0x18008f98e  add     rsp, 1A8h
0x18008f995  pop     r15
0x18008f997  pop     r14
0x18008f999  pop     r13
0x18008f99b  pop     r12
0x18008f99d  pop     rdi
0x18008f99e  pop     rsi
0x18008f99f  pop     rbx
0x18008f9a0  pop     rbp
0x18008f9a1  retn
0x18008f9a2  mov     rdi, cs:WPP_GLOBAL_Control
0x18008f9a9  lea     rax, WPP_GLOBAL_Control
0x18008f9b0  cmp     rdi, rax
0x18008f9b3  jz      short loc_18008F9F3
0x18008f9b5  cmp     byte ptr [rdi+19h], 4
0x18008f9b9  jb      short loc_18008F9F3
0x18008f9bb  test    byte ptr [rdi+1Ch], 10h
0x18008f9bf  jz      short loc_18008F9F3
0x18008f9c1  mov     rdi, [rdi+10h]
0x18008f9c5  call    IkeGetTlsPeerAddr
0x18008f9ca  mov     rbx, rax
0x18008f9cd  call    IkeGetTlsMmLuid
0x18008f9d2  mov     r9, rax
0x18008f9d5  mov     [rsp+1E0h+pvPara], rbx
0x18008f9da  mov     edx, 74h ; 't'
0x18008f9df  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008f9e6  mov     rcx, rdi
0x18008f9e9  call    WPP_SF_iS
0x18008f9ee  mov     rbx, [rsp+1E0h+pCertContext]
0x18008f9f3  mov     eax, cs:dword_180173278
0x18008f9f9  cmp     eax, 4
0x18008f9fc  jbe     short loc_18008FA65
0x18008f9fe  call    IkeGetTlsMmLuid
0x18008fa03  mov     [rbp+0E0h+var_C0], rax
0x18008fa07  lea     rax, [rbp+0E0h+var_C0]
0x18008fa0b  mov     [rbp+0E0h+var_80], rax
0x18008fa0f  mov     [rbp+0E0h+var_78], 8
0x18008fa17  call    IkeGetTlsPeerAddr
0x18008fa1c  mov     rdx, rax
0x18008fa1f  lea     rcx, [rbp+0E0h+var_70]
0x18008fa23  call    _tlgCreate1Sz_wchar_t
0x18008fa28  lea     rcx, aFoundCertUsing; "Found cert using certificate hash from "...
0x18008fa2f  mov     [rbp+0E0h+var_58], 2Fh ; '/'
0x18008fa3a  lea     rax, [rbp+0E0h+var_A0]
0x18008fa3e  mov     [rbp+0E0h+var_60], rcx
0x18008fa45  mov     [rsp+1E0h+var_1B8], rax
0x18008fa4a  lea     rcx, dword_180173278
0x18008fa51  lea     rdx, word_180156A66
0x18008fa58  mov     dword ptr [rsp+1E0h+pvPara], 5
0x18008fa60  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008fa65  mov     rcx, rbx; pCertContext
0x18008fa68  call    IkeDumpCert
0x18008fa6d  lea     rax, [rbp+0E0h+pChainContext]
0x18008fa71  xor     r9d, r9d
0x18008fa74  mov     [rsp+1E0h+var_1A0], rax
0x18008fa79  xor     r8d, r8d
0x18008fa7c  mov     rax, [rsp+1E0h+var_168]
0x18008fa81  mov     rdx, rbx
0x18008fa84  mov     [rsp+1E0h+var_1A8], rax
0x18008fa89  lea     rax, [rbp+0E0h+var_110]
0x18008fa8d  mov     [rsp+1E0h+var_1B0], rax
0x18008fa92  mov     dword ptr [rsp+1E0h+var_1B8], r14d
0x18008fa97  mov     r14, [rsp+1E0h+var_180]
0x18008fa9c  mov     rcx, r14
0x18008fa9f  mov     [rsp+1E0h+pvPara], r15
0x18008faa4  call    IkeChainSelect
0x18008faa9  mov     rbx, rax
0x18008faac  test    rax, rax
0x18008faaf  jnz     loc_18008F8FC
0x18008fab5  mov     rdi, cs:WPP_GLOBAL_Control
0x18008fabc  lea     rax, WPP_GLOBAL_Control
0x18008fac3  cmp     rdi, rax
0x18008fac6  jz      short loc_18008FB01
0x18008fac8  cmp     byte ptr [rdi+19h], 4
0x18008facc  jb      short loc_18008FB01
0x18008face  test    byte ptr [rdi+1Ch], 10h
0x18008fad2  jz      short loc_18008FB01
0x18008fad4  mov     rdi, [rdi+10h]
0x18008fad8  call    IkeGetTlsPeerAddr
0x18008fadd  mov     rbx, rax
0x18008fae0  call    IkeGetTlsMmLuid
0x18008fae5  mov     r9, rax
0x18008fae8  mov     [rsp+1E0h+pvPara], rbx
0x18008faed  mov     edx, 75h ; 'u'
0x18008faf2  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008faf9  mov     rcx, rdi
0x18008fafc  call    WPP_SF_iS
0x18008fb01  mov     eax, cs:dword_180173278
0x18008fb07  cmp     eax, 4
0x18008fb0a  jbe     loc_18008FD97
0x18008fb10  call    IkeGetTlsMmLuid
0x18008fb15  mov     [rbp+0E0h+var_C0], rax
0x18008fb19  lea     rax, [rbp+0E0h+var_C0]
0x18008fb1d  mov     [rbp+0E0h+var_80], rax
0x18008fb21  mov     [rbp+0E0h+var_78], 8
0x18008fb29  call    IkeGetTlsPeerAddr
  ... truncated ...
```
