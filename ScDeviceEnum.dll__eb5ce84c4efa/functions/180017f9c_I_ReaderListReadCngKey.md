# I_ReaderListReadCngKey

- ea: `0x180017f9c`
- end: `0x180018ed5`
- name: `I_ReaderListReadCngKey`
- size: `3897`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const wchar_t **, unsigned __int16 *, DWORD, _DWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180016958`

## callees

- `0x180001178`
- `0x1800011b4`
- `0x1800011e4`
- `0x180007178`
- `0x1800071d4`
- `0x180014018`
- `0x1800157fc`
- `0x1800160c8`
- `0x180017f9c`
- `0x18001c6e4`
- `0x18001cb0c`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001dffa`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bb8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018e59`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800180bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018e59`
- `CRYPT32!CertCreateCertificateContext` at `0x1800184dd`
- `CRYPT32!CertCreateCertificateContext` at `0x1800184dd`
- `CRYPT32!CertFreeCertificateContext` at `0x180018d18`
- `CRYPT32!CertFreeCertificateContext` at `0x180018d18`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180018bdb`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180018bdb`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018814`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018a2b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018bae`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018814`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018a2b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018bae`
- `ncrypt!NCryptGetProperty` at `0x18001833f`
- `ncrypt!NCryptGetProperty` at `0x180018486`
- `ncrypt!NCryptGetProperty` at `0x18001860e`
- `ncrypt!NCryptGetProperty` at `0x180018752`
- `ncrypt!NCryptGetProperty` at `0x180018844`
- `ncrypt!NCryptGetProperty` at `0x18001886e`
- `ncrypt!NCryptGetProperty` at `0x1800189a7`
- `ncrypt!NCryptGetProperty` at `0x180018b3d`
- `ncrypt!NCryptGetProperty` at `0x18001833f`
- `ncrypt!NCryptGetProperty` at `0x180018486`
- `ncrypt!NCryptGetProperty` at `0x18001860e`
- `ncrypt!NCryptGetProperty` at `0x180018752`
- `ncrypt!NCryptGetProperty` at `0x180018844`
- `ncrypt!NCryptGetProperty` at `0x18001886e`
- `ncrypt!NCryptGetProperty` at `0x1800189a7`
- `ncrypt!NCryptGetProperty` at `0x180018b3d`
- `ncrypt!NCryptOpenKey` at `0x1800182c2`
- `ncrypt!NCryptOpenKey` at `0x1800182c2`
- `ncrypt!NCryptFreeObject` at `0x180018d06`
- `ncrypt!NCryptFreeObject` at `0x180018d06`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadCngKey(
        __int64 a1,
        _QWORD *a2,
        const wchar_t **a3,
        unsigned __int16 *a4,
        DWORD a5,
        _DWORD *a6)
{
  LPVOID *p_lpMem; // rsi
  LPVOID *v9; // r13
  LPVOID *v10; // r14
  LPVOID *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // rdx
  size_t v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  unsigned __int64 v23; // rcx
  _DWORD *v24; // rax
  unsigned int LastError; // edi
  LPVOID *v26; // rbx
  LPVOID *v27; // r12
  _QWORD *v28; // rbx
  SECURITY_STATUS v29; // eax
  __int64 v30; // rcx
  char v31; // bl
  _QWORD *v32; // rcx
  int v33; // edx
  SECURITY_STATUS Property; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned __int64 v40; // rcx
  void *v41; // rsp
  void *v42; // rsp
  _DWORD *v43; // rax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  SECURITY_STATUS v46; // eax
  __int64 v47; // rcx
  PCERT_INFO pCertInfo; // rcx
  _QWORD *v49; // rbx
  const wchar_t *v50; // rax
  SECURITY_STATUS v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned __int64 v54; // rbx
  unsigned __int64 v55; // rcx
  __int64 v56; // rcx
  unsigned __int64 v57; // rcx
  void *v58; // rsp
  void *v59; // rsp
  _DWORD *v60; // rax
  SECURITY_STATUS v61; // eax
  __int64 v62; // rcx
  SECURITY_STATUS v63; // ebx
  SECURITY_STATUS v64; // eax
  __int64 v65; // rdx
  unsigned __int64 v66; // rbx
  LPVOID *v67; // rax
  unsigned __int64 v68; // rcx
  __int64 v69; // rcx
  unsigned __int64 v70; // rcx
  void *v71; // rsp
  void *v72; // rsp
  _DWORD *v73; // rax
  _QWORD *v74; // rcx
  __int64 v75; // rdx
  SECURITY_STATUS v76; // eax
  __int64 v77; // rcx
  char v78; // bl
  _QWORD *v79; // rcx
  int v80; // edx
  __int64 v81; // rdx
  unsigned __int64 v82; // rbx
  unsigned __int64 v83; // rcx
  __int64 v84; // rcx
  unsigned __int64 v85; // rcx
  void *v86; // rsp
  void *v87; // rsp
  _DWORD *v88; // rax
  SECURITY_STATUS v89; // eax
  __int64 v90; // rcx
  _QWORD *v91; // rbx
  const wchar_t *v92; // r8
  __int64 v93; // rcx
  NCRYPT_KEY_HANDLE v94; // rcx
  __int64 v95; // rcx
  _BYTE v97[32]; // [rsp+0h] [rbp-30h] BYREF
  LPVOID *v98; // [rsp+30h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp+8h] BYREF
  DWORD cbOutput; // [rsp+40h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+18h] BYREF
  DWORD pcbResult; // [rsp+50h] [rbp+20h] BYREF
  DWORD v103; // [rsp+54h] [rbp+24h] BYREF
  DWORD v104; // [rsp+58h] [rbp+28h] BYREF
  DWORD dwVersion; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbCertEncoded; // [rsp+68h] [rbp+38h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp+40h]
  DWORD v108; // [rsp+78h] [rbp+48h] BYREF
  DWORD v109; // [rsp+7Ch] [rbp+4Ch]
  _QWORD *v110; // [rsp+80h] [rbp+50h] BYREF
  _QWORD *v111; // [rsp+88h] [rbp+58h]
  DWORD v112; // [rsp+90h] [rbp+60h] BYREF
  DWORD v113; // [rsp+94h] [rbp+64h] BYREF
  __int128 pvData; // [rsp+98h] [rbp+68h] BYREF
  __int128 v115; // [rsp+A8h] [rbp+78h]
  __int128 v116; // [rsp+B8h] [rbp+88h]
  __int64 v117; // [rsp+C8h] [rbp+98h]
  unsigned __int16 *v118; // [rsp+D0h] [rbp+A0h]
  _DWORD *v119; // [rsp+D8h] [rbp+A8h]
  __int128 v120; // [rsp+E0h] [rbp+B0h] BYREF
  __int128 v121; // [rsp+F0h] [rbp+C0h] BYREF
  GUID ActivityId; // [rsp+100h] [rbp+D0h] BYREF
  GUID v123; // [rsp+110h] [rbp+E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v124[2]; // [rsp+120h] [rbp+F0h] BYREF
  DWORD *p_cbOutput; // [rsp+140h] [rbp+110h]
  __int64 v126; // [rsp+148h] [rbp+118h]
  DWORD *p_cbCertEncoded; // [rsp+150h] [rbp+120h]
  __int64 v128; // [rsp+158h] [rbp+128h]
  _QWORD v129[2]; // [rsp+160h] [rbp+130h] BYREF
  DWORD *p_NotBefore; // [rsp+170h] [rbp+140h]
  __int64 v131; // [rsp+178h] [rbp+148h]
  LPVOID **p_NotAfter; // [rsp+180h] [rbp+150h]
  __int64 v133; // [rsp+188h] [rbp+158h]
  struct _EVENT_DATA_DESCRIPTOR v134[2]; // [rsp+190h] [rbp+160h] BYREF
  LPVOID **v135; // [rsp+1B0h] [rbp+180h]
  __int64 v136; // [rsp+1B8h] [rbp+188h]

  p_lpMem = 0;
  v111 = a2;
  v118 = a4;
  lpMem = 0;
  v110 = 0;
  v117 = a1;
  v119 = a6;
  phKey = 0;
  v9 = 0;
  v98 = 0;
  v10 = 0;
  pcbResult = 0;
  v11 = 0;
  v103 = 0;
  v104 = 0;
  v108 = 0;
  v112 = 0;
  v113 = 0;
  pCertContext = 0;
  pvData = 0;
  v109 = 0;
  v115 = 0;
  v116 = 0;
  v120 = 0;
  v121 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v123 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v123);
  if ( (unsigned int)dword_18002B008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&unk_180025B30, &v123, &ActivityId, 2u, v134);
  v13 = -1;
  *a6 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*a2 + 2 * v14) );
  v15 = *a3;
  do
    ++v13;
  while ( v15[v13] );
  v16 = v13 + v14 + 6;
  pvData = 0;
  v115 = 0;
  v17 = 2 * v16;
  v116 = 0;
  if ( !(2 * v16) )
    goto LABEL_19;
  if ( v17 > g_ulMaxStackAllocSize )
    goto LABEL_19;
  v18 = v17 + g_ulAdditionalProbeSize + 8;
  if ( v18 < v17 || !(unsigned int)VerifyStackAvailable(v18, v15) )
    goto LABEL_19;
  v19 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  p_lpMem = (LPVOID *)&v98;
  if ( v97 == (_BYTE *)-48LL || (LODWORD(v98) = 1801679955, (p_lpMem = &lpMem) == 0) )
  {
LABEL_19:
    v23 = v17 + 8;
    if ( v17 + 8 >= v17 )
    {
      v24 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_lpMem = (LPVOID *)v24;
      if ( !v24 )
      {
LABEL_23:
        WppTraceIndent(v23, 2);
        LastError = 8;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
          v27 = (LPVOID *)lpMem;
          goto LABEL_185;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        goto LABEL_27;
      }
      *v24 = 1885431112;
      p_lpMem = (LPVOID *)(v24 + 2);
    }
    if ( !p_lpMem )
      goto LABEL_23;
  }
  v28 = v111;
  if ( StringCchPrintfW((STRSAFE_LPWSTR)p_lpMem, v16, L"\\\\.\\%s\\%s", *v111, *a3) < 0 )
  {
    LastError = 122;
LABEL_27:
    v26 = 0;
LABEL_28:
    v27 = (LPVOID *)lpMem;
    goto LABEL_29;
  }
  LastError = 0;
  v29 = NCryptOpenKey(v28[17], &phKey, (LPCWSTR)p_lpMem, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5) | 0x40);
  v31 = v29;
  if ( v29 )
  {
    WppTraceIndent(v30, 2);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v33 = 130;
LABEL_42:
    WPP_SF_sd(v32[2], v33, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v31);
LABEL_43:
    v26 = 0;
    goto LABEL_28;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0x40u);
  v31 = Property;
  if ( Property )
  {
    WppTraceIndent(v36, 2);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v33 = 131;
    goto LABEL_42;
  }
  v37 = pcbResult;
  if ( !pcbResult )
    goto LABEL_57;
  if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_57;
  v38 = pcbResult + g_ulAdditionalProbeSize + 8;
  if ( v38 < pcbResult || !(unsigned int)VerifyStackAvailable(v38, v35) )
    goto LABEL_57;
  v39 = v37 + 23;
  if ( v37 + 23 <= v37 + 8 )
    v39 = 0xFFFFFFFFFFFFFF0LL;
  v40 = v39 & 0xFFFFFFFFFFFFFFF0uLL;
  v41 = alloca(v40);
  v42 = alloca(v40);
  v9 = (LPVOID *)&v98;
  if ( v97 == (_BYTE *)-48LL || (LODWORD(v98) = 1801679955, (v9 = &lpMem) == 0) )
  {
LABEL_57:
    v40 = v37 + 8;
    if ( v37 + 8 >= v37 )
    {
      v43 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v9 = (LPVOID *)v43;
      if ( v43 )
      {
        *v43 = 1885431112;
        v9 = (LPVOID *)(v43 + 2);
      }
    }
  }
  if ( !v9 )
  {
    WppTraceIndent(v40, 2);
    LastError = 8;
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v45 = 132;
    goto LABEL_65;
  }
  v46 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", (PBYTE)v9, pcbResult, &v108, 0x40u);
  v31 = v46;
  if ( v46 )
  {
    WppTraceIndent(v47, 2);
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v33 = 133;
    goto LABEL_42;
  }
  pCertContext = CertCreateCertificateContext(0x10001u, (const BYTE *)v9, pcbResult);
  if ( !pCertContext )
  {
LABEL_73:
    LastError = GetLastError();
    goto LABEL_66;
  }
  if ( (unsigned int)dword_18002B008 > 5 )
  {
    cbOutput = pCertContext->dwCertEncodingType;
    v126 = 4;
    p_cbOutput = &cbOutput;
    pCertInfo = pCertContext->pCertInfo;
    cbCertEncoded = pCertContext->cbCertEncoded;
    p_cbCertEncoded = &cbCertEncoded;
    v128 = 4;
    dwVersion = pCertInfo->dwVersion;
    v129[0] = &dwVersion;
    p_NotBefore = (DWORD *)&pCertInfo->NotBefore;
    p_NotAfter = (LPVOID **)&pCertInfo->NotAfter;
    v129[1] = 4;
    v131 = 8;
    v133 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)pCertInfo,
      (unsigned __int8 *)byte_180025021,
      &v123,
      &ActivityId,
      7u,
      v124);
  }
  v49 = v111;
  *(_QWORD *)&pvData = *a3;
  if ( *((_DWORD *)v111 + 3) == 1024 )
  {
    if ( a5 )
    {
      v50 = (const wchar_t *)v111[11];
    }
    else
    {
      cbOutput = 0;
      v51 = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", 0, 0, &cbOutput, 0x40u);
      v31 = v51;
      if ( v51 )
      {
        WppTraceIndent(v53, 2);
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v33 = 134;
        goto LABEL_42;
      }
      v54 = cbOutput;
      if ( !cbOutput )
        goto LABEL_92;
      if ( cbOutput > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_92;
      v55 = cbOutput + g_ulAdditionalProbeSize + 8;
      if ( v55 < cbOutput || !(unsigned int)VerifyStackAvailable(v55, v52) )
        goto LABEL_92;
      v56 = v54 + 23;
      if ( v54 + 23 <= v54 + 8 )
        v56 = 0xFFFFFFFFFFFFFF0LL;
      v57 = v56 & 0xFFFFFFFFFFFFFFF0uLL;
      v58 = alloca(v57);
      v59 = alloca(v57);
      v11 = (LPVOID *)&v98;
      if ( v97 == (_BYTE *)-48LL || (LODWORD(v98) = 1801679955, (v11 = &lpMem) == 0) )
      {
LABEL_92:
        v57 = v54 + 8;
        if ( v54 + 8 >= v54 )
        {
          v60 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v11 = (LPVOID *)v60;
          if ( v60 )
          {
            *v60 = 1885431112;
            v11 = (LPVOID *)(v60 + 2);
          }
        }
      }
      if ( !v11 )
      {
        WppTraceIndent(v57, 2);
        LastError = 8;
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_66;
        }
        v45 = 135;
LABEL_65:
        WPP_SF_s(v44[2], v45, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_66:
        v26 = 0;
        goto LABEL_28;
      }
      v61 = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", (PBYTE)v11, cbOutput, &v108, 0x40u);
      v31 = v61;
      if ( v61 )
      {
        WppTraceIndent(v62, 2);
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v33 = 136;
        goto LABEL_42;
      }
      *(_QWORD *)&pvData = v11;
      v50 = L"Microsoft Passport Key Storage Provider";
    }
    LODWORD(v115) = 0;
    DWORD2(v116) = 0;
  }
  else
  {
    if ( IsCAPIOverrideForRSAEnabled() && !wcscmp_0(a3[1], L"RSA") && v49[10] )
    {
      *((_QWORD *)&pvData + 1) = v49[10];
      DWORD2(v116) = *((_DWORD *)a3 + 4);
      LODWORD(v115) = 1;
      goto LABEL_113;
    }
    v50 = (const wchar_t *)v49[11];
    DWORD2(v116) = 0;
    LODWORD(v115) = 0;
  }
  *((_QWORD *)&pvData + 1) = v50;
LABEL_113:
  if ( !CertSetCertificateContextProperty(pCertContext, 2u, 0, &pvData) )
    goto LABEL_73;
  v63 = NCryptGetProperty(phKey, L"SmartCardPinId", 0, 0, &v103, 0x40u);
  v64 = NCryptGetProperty(phKey, L"SmartCardPinInfo", 0, 0, &v104, 0x40u);
  if ( v63 || v64 )
    goto LABEL_167;
  v66 = v103;
  v67 = 0;
  v98 = 0;
  if ( v103 )
  {
    if ( v103 <= (unsigned __int64)g_ulMaxStackAllocSize )
    {
      v68 = v103 + g_ulAdditionalProbeSize + 8;
      if ( v68 >= v103 )
      {
        if ( (unsigned int)VerifyStackAvailable(v68, v65) )
        {
          v69 = v66 + 23;
          if ( v66 + 23 <= v66 + 8 )
            v69 = 0xFFFFFFFFFFFFFF0LL;
          v70 = v69 & 0xFFFFFFFFFFFFFFF0uLL;
          v71 = alloca(v70);
          v72 = alloca(v70);
          v67 = (LPVOID *)&v98;
          v98 = (LPVOID *)&v98;
          if ( v97 != (_BYTE *)-48LL )
          {
            v67 = &lpMem;
            v98 = &lpMem;
            if ( &lpMem )
              goto LABEL_129;
          }
        }
        else
        {
          v67 = 0;
        }
      }
    }
  }
  v70 = v66 + 8;
  if ( v66 + 8 >= v66 )
  {
    v73 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
    v98 = (LPVOID *)v73;
    if ( !v73 )
      goto LABEL_130;
    *v73 = 1885431112;
    v67 = (LPVOID *)(v73 + 2);
    v98 = v67;
  }
LABEL_129:
  if ( !v67 )
  {
LABEL_130:
    WppTraceIndent(v70, 2);
    LastError = 8;
    v74 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_135;
    }
    v75 = 137;
    goto LABEL_134;
  }
  v76 = NCryptGetProperty(phKey, L"SmartCardPinId", (PBYTE)v67, v103, &v112, 0x40u);
  v78 = v76;
  if ( v76 )
  {
    WppTraceIndent(v77, 2);
    v79 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_135;
    }
    v80 = 138;
    goto LABEL_141;
  }
  v26 = v98;
  *((_QWORD *)&v120 + 1) = v98;
  LODWORD(v120) = v103;
  if ( !CertSetCertificateContextProperty(pCertContext, 0x5Au, 0x40000000u, &v120) )
  {
    LastError = GetLastError();
    goto LABEL_28;
  }
  v82 = v104;
  if ( !v104 )
    goto LABEL_152;
  if ( v104 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_152;
  v83 = v104 + g_ulAdditionalProbeSize + 8;
  if ( v83 < v104 || !(unsigned int)VerifyStackAvailable(v83, v81) )
    goto LABEL_152;
  v84 = v82 + 23;
  if ( v82 + 23 <= v82 + 8 )
    v84 = 0xFFFFFFFFFFFFFF0LL;
  v85 = v84 & 0xFFFFFFFFFFFFFFF0uLL;
  v86 = alloca(v85);
  v87 = alloca(v85);
  v10 = (LPVOID *)&v98;
  if ( v97 == (_BYTE *)-48LL || (LODWORD(v98) = 1801679955, (v10 = &lpMem) == 0) )
  {
LABEL_152:
    v85 = v82 + 8;
    if ( v82 + 8 >= v82 )
    {
      v88 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v10 = (LPVOID *)v88;
      if ( v88 )
      {
        *v88 = 1885431112;
        v10 = (LPVOID *)(v88 + 2);
      }
    }
  }
  if ( !v10 )
  {
    WppTraceIndent(v85, 2);
    LastError = 8;
    v74 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_135;
    }
    v75 = 139;
LABEL_134:
    WPP_SF_s(v74[2], v75, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_135:
    v26 = v98;
    goto LABEL_28;
  }
  v89 = NCryptGetProperty(phKey, L"SmartCardPinInfo", (PBYTE)v10, v104, &v113, 0x40u);
  v78 = v89;
  if ( v89 )
  {
    WppTraceIndent(v90, 2);
    v79 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_135;
    }
    v80 = 140;
LABEL_141:
    WPP_SF_sd(v79[2], v80, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v78);
    goto LABEL_135;
  }
  LODWORD(v121) = v104;
  *((_QWORD *)&v121 + 1) = v10;
  if ( !CertSetCertificateContextProperty(pCertContext, 0x5Bu, 0x40000000u, &v121) )
  {
LABEL_166:
    LastError = GetLastError();
    goto LABEL_135;
  }
LABEL_167:
  v91 = v111;
  if ( !CertAddCertificateContextToStore((HCERTSTORE)v111[21], pCertContext, 4u, 0) )
    goto LABEL_166;
  v92 = *a3;
  v109 = 1;
  LastError = I_ReaderListBuildCredFromCertContext(v117, pCertContext, v92, SDWORD2(v116), &v110);
  if ( LastError )
  {
    WppTraceIndent(v93, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
      lpMem = v110;
      goto LABEL_135;
    }
    v27 = (LPVOID *)v110;
  }
  else
  {
    I_ReaderListAddCredToList(v110, v118, v91 + 29);
    v27 = 0;
    *v119 = 1;
  }
  v26 = v98;
LABEL_29:
  if ( p_lpMem && *((_DWORD *)p_lpMem - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v11 && *((_DWORD *)v11 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v26 && *((_DWORD *)v26 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v10 && *((_DWORD *)v10 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_185:
  v94 = phKey;
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v27 )
    I_FreeCredListItem(v27);
  if ( (unsigned int)dword_18002B008 > 5 && (unsigned __int8)tlgKeywordOn(v94, 0x400000000000LL) )
  {
    dwVersion = a5;
    p_cbOutput = &dwVersion;
    v126 = 4;
    v128 = 4;
    cbCertEncoded = *((_DWORD *)v111 + 3);
    p_cbCertEncoded = &cbCertEncoded;
    tlgCreate1Sz_wchar_t((__int64)v129, *((__int64 **)&pvData + 1));
    p_NotBefore = &cbOutput;
    cbOutput = v109;
    p_NotAfter = &v98;
    v131 = 4;
    LODWORD(v98) = LastError;
    v133 = 4;
    tlgWriteTransfer_EventWriteTransfer(v109, (unsigned __int8 *)byte_18002519F, 0, 0, 7u, v124);
  }
  if ( (unsigned int)dword_18002B008 > 5 )
  {
    LODWORD(v98) = LastError;
    v135 = &v98;
    v136 = 4;
    tlgWriteTransfer_EventWriteTransfer(v94, (unsigned __int8 *)&word_180024FCE, &v123, &ActivityId, 3u, v134);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v95, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      142,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180017f9c  push    rbp
0x180017f9e  push    rsi
0x180017f9f  push    rdi
0x180017fa0  push    r12
0x180017fa2  push    r13
0x180017fa4  push    r14
0x180017fa6  push    r15
0x180017fa8  sub     rsp, 1D0h
0x180017faf  lea     rbp, [rsp+30h]
0x180017fb4  mov     [rbp+1D0h+arg_18], rbx
0x180017fbb  mov     rax, cs:__security_cookie
0x180017fc2  xor     rax, rbp
0x180017fc5  mov     [rbp+1D0h+var_40], rax
0x180017fcc  mov     rbx, [rbp+1D0h+arg_28]
0x180017fd3  xor     esi, esi
0x180017fd5  xorps   xmm0, xmm0
0x180017fd8  mov     [rbp+1D0h+var_178], rdx
0x180017fdc  mov     eax, esi
0x180017fde  mov     [rbp+1D0h+var_130], r9
0x180017fe5  mov     rdi, rdx
0x180017fe8  mov     [rbp+1D0h+lpMem], rax
0x180017fec  xorps   xmm1, xmm1
0x180017fef  mov     [rbp+1D0h+var_180], rax
0x180017ff3  xor     edx, edx
0x180017ff5  mov     [rbp+1D0h+var_138], rcx
0x180017ffc  mov     r12, r8
0x180017fff  mov     [rbp+1D0h+var_128], rbx
0x180018006  mov     [rbp+1D0h+phKey], rsi
0x18001800a  mov     r13d, esi
0x18001800d  mov     [rbp+1D0h+var_1D0], rsi
0x180018011  mov     r14d, esi
0x180018014  mov     [rbp+1D0h+pcbResult], esi
0x180018017  mov     r15d, esi
0x18001801a  mov     [rbp+1D0h+var_1AC], esi
0x18001801d  mov     [rbp+1D0h+var_1A8], esi
0x180018020  mov     [rbp+1D0h+var_188], esi
0x180018023  mov     [rbp+1D0h+var_170], esi
0x180018026  mov     [rbp+1D0h+var_16C], esi
0x180018029  mov     [rbp+1D0h+pCertContext], rsi
0x18001802d  movups  [rbp+1D0h+pvData], xmm0
0x180018031  mov     [rbp+1D0h+var_184], esi
0x180018034  movups  [rbp+1D0h+var_158], xmm0
0x180018038  movups  [rbp+1D0h+var_148], xmm0
0x18001803f  movups  [rbp+1D0h+var_120], xmm0
0x180018046  movups  [rbp+1D0h+var_110], xmm1
0x18001804d  call    WppTraceIndent
0x180018052  mov     rcx, cs:WPP_GLOBAL_Control
0x180018059  lea     rax, WPP_GLOBAL_Control
0x180018060  cmp     rcx, rax
0x180018063  jz      short loc_18001808D
0x180018065  test    byte ptr [rcx+1Ch], 2
0x180018069  jz      short loc_18001808D
0x18001806b  cmp     byte ptr [rcx+19h], 5
0x18001806f  jb      short loc_18001808D
0x180018071  mov     r9, cs:WPP_pszIndent
0x180018078  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001807f  mov     rcx, [rcx+10h]
0x180018083  mov     edx, 80h
0x180018088  call    WPP_SF_s
0x18001808d  xorps   xmm0, xmm0
0x180018090  lea     rdx, [rbp+1D0h+ActivityId]; ActivityId
0x180018097  xorps   xmm1, xmm1
0x18001809a  mov     ecx, 5; ControlCode
0x18001809f  movups  xmmword ptr [rbp+1D0h+ActivityId.Data1], xmm0
0x1800180a6  movups  xmmword ptr [rbp+1D0h+var_F0.Data1], xmm1
0x1800180ad  call    cs:__imp_EventActivityIdControl
0x1800180b3  lea     rdx, [rbp+1D0h+var_F0]; ActivityId
0x1800180ba  mov     ecx, 1; ControlCode
0x1800180bf  call    cs:__imp_EventActivityIdControl
0x1800180c5  mov     eax, cs:dword_18002B008
0x1800180cb  cmp     eax, 5
0x1800180ce  jbe     short loc_1800180FE
0x1800180d0  lea     rax, [rbp+1D0h+var_70]
0x1800180d7  mov     qword ptr [rsp+200h+var_1D8], rax
0x1800180dc  lea     r9, [rbp+1D0h+ActivityId]
0x1800180e3  lea     r8, [rbp+1D0h+var_F0]
0x1800180ea  mov     [rsp+200h+dwFlags], 2
0x1800180f2  lea     rdx, unk_180025B30
0x1800180f9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800180fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018102  mov     [rbx], esi
0x180018104  mov     rdx, [rdi]
0x180018107  mov     rcx, rax
0x18001810a  inc     rcx
0x18001810d  cmp     [rdx+rcx*2], si
0x180018111  jnz     short loc_18001810A
0x180018113  mov     rdx, [r12]
0x180018117  inc     rax
0x18001811a  cmp     [rdx+rax*2], si
0x18001811e  jnz     short loc_180018117
0x180018120  xorps   xmm0, xmm0
0x180018123  lea     rdi, [rcx+6]
0x180018127  add     rdi, rax
0x18001812a  movups  [rbp+1D0h+pvData], xmm0
0x18001812e  movups  [rbp+1D0h+var_158], xmm0
0x180018132  lea     rbx, [rdi+rdi]
0x180018136  movups  [rbp+1D0h+var_148], xmm0
0x18001813d  test    rbx, rbx
0x180018140  jz      short loc_1800181A7
0x180018142  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180018149  ja      short loc_1800181A7
0x18001814b  mov     rcx, cs:g_ulAdditionalProbeSize
0x180018152  add     rcx, 8
0x180018156  add     rcx, rbx
0x180018159  cmp     rcx, rbx
0x18001815c  jb      short loc_1800181A7
0x18001815e  call    VerifyStackAvailable
0x180018163  test    eax, eax
0x180018165  jz      short loc_1800181A7
0x180018167  lea     rax, [rbx+8]
0x18001816b  lea     rcx, [rax+0Fh]
0x18001816f  cmp     rcx, rax
0x180018172  ja      short loc_18001817E
0x180018174  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001817e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180018182  mov     rax, rcx
0x180018185  call    _alloca_probe
0x18001818a  sub     rsp, rcx
0x18001818d  lea     rsi, [rsp+200h+var_1D0]
0x180018192  test    rsi, rsi
0x180018195  jz      short loc_1800181A7
0x180018197  mov     dword ptr [rsi], 6B637453h
0x18001819d  add     rsi, 8
0x1800181a1  jnz     loc_180018274
0x1800181a7  lea     rcx, [rbx+8]
0x1800181ab  cmp     rcx, rbx
0x1800181ae  jb      short loc_1800181CE
0x1800181b0  mov     rax, cs:g_pfnAllocate
0x1800181b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181bc  mov     rsi, rax
0x1800181bf  test    rax, rax
0x1800181c2  jz      short loc_1800181D7
0x1800181c4  mov     dword ptr [rax], 70616548h
0x1800181ca  add     rsi, 8
0x1800181ce  test    rsi, rsi
0x1800181d1  jnz     loc_180018274
0x1800181d7  mov     edx, 2
0x1800181dc  call    WppTraceIndent
0x1800181e1  mov     edi, 8
0x1800181e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181ed  lea     rbx, WPP_GLOBAL_Control
0x1800181f4  cmp     rcx, rbx
0x1800181f7  jz      loc_180018ECC
0x1800181fd  test    byte ptr [rcx+1Ch], 1
0x180018201  jz      short loc_180018223
0x180018203  cmp     byte ptr [rcx+19h], 2
0x180018207  jb      short loc_180018223
0x180018209  mov     r9, cs:WPP_pszIndent
0x180018210  lea     edx, [rdi+79h]
0x180018213  mov     rcx, [rcx+10h]
0x180018217  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001821e  call    WPP_SF_s
0x180018223  mov     rbx, r13
0x180018226  mov     r12, [rbp+1D0h+lpMem]
0x18001822a  test    rsi, rsi
0x18001822d  jz      short loc_180018247
0x18001822f  lea     rcx, [rsi-8]
0x180018233  cmp     dword ptr [rcx], 70616548h
0x180018239  jnz     short loc_180018247
0x18001823b  mov     rax, cs:g_pfnFree
0x180018242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018247  test    r15, r15
0x18001824a  jz      loc_180018CA2
0x180018250  lea     rcx, [r15-8]
0x180018254  mov     r15d, 70616548h
0x18001825a  cmp     [rcx], r15d
0x18001825d  jnz     loc_180018CA8
0x180018263  mov     rax, cs:g_pfnFree
0x18001826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001826f  jmp     loc_180018CA8
0x180018274  mov     rax, [r12]
0x180018278  lea     r8, aSS; "\\\\.\\%s\\%s"
0x18001827f  mov     rbx, [rbp+1D0h+var_178]
0x180018283  mov     rdx, rdi; cchDest
0x180018286  mov     rcx, rsi; pszDest
0x180018289  mov     qword ptr [rsp+200h+dwFlags], rax
0x18001828e  mov     r9, [rbx]
0x180018291  call    StringCchPrintfW
0x180018296  test    eax, eax
0x180018298  jns     short loc_1800182A1
0x18001829a  mov     edi, 7Ah ; 'z'
0x18001829f  jmp     short loc_180018223
0x1800182a1  mov     eax, [r12+14h]
0x1800182a6  lea     rdx, [rbp+1D0h+phKey]; phKey
0x1800182aa  mov     r9d, [r12+10h]; dwLegacyKeySpec
0x1800182af  or      eax, 40h
0x1800182b2  mov     rcx, [rbx+88h]; hProvider
0x1800182b9  mov     r8, rsi; pszKeyName
0x1800182bc  mov     [rsp+200h+dwFlags], eax; dwFlags
0x1800182c0  xor     edi, edi
0x1800182c2  call    cs:__imp_NCryptOpenKey
0x1800182c8  mov     ebx, eax
0x1800182ca  test    eax, eax
0x1800182cc  jz      short loc_18001831D
0x1800182ce  lea     edx, [rdi+2]
0x1800182d1  call    WppTraceIndent
0x1800182d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182dd  lea     rax, WPP_GLOBAL_Control
0x1800182e4  cmp     rcx, rax
0x1800182e7  jz      short loc_180018315
0x1800182e9  test    byte ptr [rcx+1Ch], 1
0x1800182ed  jz      short loc_180018315
0x1800182ef  cmp     byte ptr [rcx+19h], 2
0x1800182f3  jb      short loc_180018315
0x1800182f5  mov     edx, 82h
0x1800182fa  mov     r9, cs:WPP_pszIndent
0x180018301  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180018308  mov     rcx, [rcx+10h]
0x18001830c  mov     [rsp+200h+dwFlags], ebx
0x180018310  call    WPP_SF_sd
0x180018315  mov     rbx, rdi
0x180018318  jmp     loc_180018226
0x18001831d  mov     rcx, [rbp+1D0h+phKey]; hObject
0x180018321  lea     rax, [rbp+1D0h+pcbResult]
0x180018325  mov     [rsp+200h+var_1D8], 40h ; '@'; dwFlags
0x18001832d  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180018334  xor     r9d, r9d; cbOutput
0x180018337  mov     qword ptr [rsp+200h+dwFlags], rax; pcbResult
0x18001833c  xor     r8d, r8d; pbOutput
0x18001833f  call    cs:__imp_NCryptGetProperty
0x180018345  mov     ebx, eax
0x180018347  test    eax, eax
0x180018349  jz      short loc_18001837E
0x18001834b  mov     edx, 2
0x180018350  call    WppTraceIndent
0x180018355  mov     rcx, cs:WPP_GLOBAL_Control
0x18001835c  lea     rax, WPP_GLOBAL_Control
0x180018363  cmp     rcx, rax
0x180018366  jz      short loc_180018315
0x180018368  test    byte ptr [rcx+1Ch], 1
0x18001836c  jz      short loc_180018315
0x18001836e  cmp     byte ptr [rcx+19h], 2
0x180018372  jb      short loc_180018315
0x180018374  mov     edx, 83h
0x180018379  jmp     loc_1800182FA
0x18001837e  mov     ebx, [rbp+1D0h+pcbResult]
0x180018381  test    rbx, rbx
0x180018384  jz      short loc_1800183E9
0x180018386  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001838d  ja      short loc_1800183E9
0x18001838f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180018396  add     rcx, 8
0x18001839a  add     rcx, rbx
0x18001839d  cmp     rcx, rbx
0x1800183a0  jb      short loc_1800183E9
0x1800183a2  call    VerifyStackAvailable
0x1800183a7  test    eax, eax
0x1800183a9  jz      short loc_1800183E9
0x1800183ab  lea     rax, [rbx+8]
0x1800183af  lea     rcx, [rax+0Fh]
0x1800183b3  cmp     rcx, rax
0x1800183b6  ja      short loc_1800183C2
0x1800183b8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800183c2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800183c6  mov     rax, rcx
0x1800183c9  call    _alloca_probe
0x1800183ce  sub     rsp, rcx
0x1800183d1  lea     r13, [rsp+200h+var_1D0]
0x1800183d6  test    r13, r13
0x1800183d9  jz      short loc_1800183E9
0x1800183db  mov     dword ptr [r13+0], 6B637453h
0x1800183e3  add     r13, 8
0x1800183e7  jnz     short loc_180018410
0x1800183e9  lea     rcx, [rbx+8]
0x1800183ed  cmp     rcx, rbx
0x1800183f0  jb      short loc_180018410
0x1800183f2  mov     rax, cs:g_pfnAllocate
0x1800183f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183fe  mov     r13, rax
0x180018401  test    rax, rax
0x180018404  jz      short loc_180018410
0x180018406  mov     dword ptr [rax], 70616548h
0x18001840c  add     r13, 8
0x180018410  test    r13, r13
0x180018413  jnz     short loc_180018463
0x180018415  lea     edx, [r13+2]
0x180018419  call    WppTraceIndent
0x18001841e  lea     edi, [r13+8]
0x180018422  mov     rcx, cs:WPP_GLOBAL_Control
0x180018429  lea     rax, WPP_GLOBAL_Control
0x180018430  cmp     rcx, rax
0x180018433  jz      short loc_18001845B
0x180018435  test    byte ptr [rcx+1Ch], 1
0x180018439  jz      short loc_18001845B
0x18001843b  cmp     byte ptr [rcx+19h], 2
0x18001843f  jb      short loc_18001845B
0x180018441  lea     edx, [rdi+7Ch]
0x180018444  mov     r9, cs:WPP_pszIndent
0x18001844b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180018452  mov     rcx, [rcx+10h]
0x180018456  call    WPP_SF_s
0x18001845b  mov     rbx, r14
0x18001845e  jmp     loc_180018226
0x180018463  mov     r9d, [rbp+1D0h+pcbResult]; cbOutput
0x180018467  lea     rax, [rbp+1D0h+var_188]
0x18001846b  mov     rcx, [rbp+1D0h+phKey]; hObject
0x18001846f  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180018476  mov     [rsp+200h+var_1D8], 40h ; '@'; dwFlags
0x18001847e  mov     r8, r13; pbOutput
0x180018481  mov     qword ptr [rsp+200h+dwFlags], rax; pcbResult
  ... truncated ...
```
