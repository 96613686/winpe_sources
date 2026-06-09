# I_ReaderListReadContainerDataPerKeyType

- ea: `0x180019250`
- end: `0x180019c7b`
- name: `I_ReaderListReadContainerDataPerKeyType`
- size: `2603`
- prototype: `__int64 __fastcall(__int64, __int64, HCRYPTPROV, const wchar_t *, DWORD dwKeySpec)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180018edc`
- `0x180019c84`

## callees

- `0x1800011e4`
- `0x180007178`
- `0x1800071d4`
- `0x180014018`
- `0x1800157fc`
- `0x1800160c8`
- `0x180019250`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001975b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001975b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a2b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019326`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019338`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019c0e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019326`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019338`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180019c0e`
- `CRYPT32!CertCreateCertificateContext` at `0x1800195ca`
- `CRYPT32!CertCreateCertificateContext` at `0x1800195ca`
- `CRYPT32!CertFreeCertificateContext` at `0x180019b36`
- `CRYPT32!CertFreeCertificateContext` at `0x180019b36`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180019aad`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180019aad`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019751`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019927`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019a8e`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019751`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019927`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180019a8e`
- `CRYPTSP!CryptDestroyKey` at `0x180019b45`
- `CRYPTSP!CryptDestroyKey` at `0x180019b45`
- `CRYPTSP!CryptGetKeyParam` at `0x18001941b`
- `CRYPTSP!CryptGetKeyParam` at `0x18001956c`
- `CRYPTSP!CryptGetKeyParam` at `0x18001977f`
- `CRYPTSP!CryptGetKeyParam` at `0x18001979e`
- `CRYPTSP!CryptGetKeyParam` at `0x1800198b9`
- `CRYPTSP!CryptGetKeyParam` at `0x180019a20`
- `CRYPTSP!CryptGetKeyParam` at `0x18001941b`
- `CRYPTSP!CryptGetKeyParam` at `0x18001956c`
- `CRYPTSP!CryptGetKeyParam` at `0x18001977f`
- `CRYPTSP!CryptGetKeyParam` at `0x18001979e`
- `CRYPTSP!CryptGetKeyParam` at `0x1800198b9`
- `CRYPTSP!CryptGetKeyParam` at `0x180019a20`
- `CRYPTSP!CryptGetUserKey` at `0x18001939a`
- `CRYPTSP!CryptGetUserKey` at `0x18001939a`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadContainerDataPerKeyType(
        __int64 a1,
        __int64 a2,
        HCRYPTPROV a3,
        const wchar_t *a4,
        DWORD dwKeySpec)
{
  DWORD *p_pdwDataLen; // rdi
  DWORD *v7; // r14
  DWORD *v8; // rsi
  __int64 v10; // rcx
  unsigned int LastError; // ebx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  DWORD *v23; // rax
  __int64 v24; // rcx
  PCCERT_CONTEXT CertificateContext; // r15
  _DWORD *p_dwVersion; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  int v29; // edx
  BOOL KeyParam; // ebx
  BOOL v31; // eax
  __int64 v32; // rdx
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  void *v37; // rsp
  void *v38; // rsp
  DWORD *v39; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rdx
  unsigned __int64 v44; // rbx
  unsigned __int64 v45; // rcx
  __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  void *v48; // rsp
  void *v49; // rsp
  DWORD *v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rcx
  LPVOID v53; // rcx
  __int64 v54; // rcx
  _BYTE v56[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v58; // [rsp+34h] [rbp+4h] BYREF
  DWORD v59; // [rsp+38h] [rbp+8h] BYREF
  HCRYPTKEY phUserKey; // [rsp+40h] [rbp+10h] BYREF
  unsigned int v61; // [rsp+48h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp+20h] BYREF
  DWORD dwCertEncodingType; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbCertEncoded; // [rsp+5Ch] [rbp+2Ch] BYREF
  const wchar_t *v65; // [rsp+60h] [rbp+30h]
  __int64 v66; // [rsp+68h] [rbp+38h]
  __int128 v67; // [rsp+70h] [rbp+40h] BYREF
  __int128 v68; // [rsp+80h] [rbp+50h] BYREF
  __int128 pvData; // [rsp+90h] [rbp+60h] BYREF
  __int128 v70; // [rsp+A0h] [rbp+70h]
  __int128 v71; // [rsp+B0h] [rbp+80h]
  GUID ActivityId; // [rsp+C0h] [rbp+90h] BYREF
  GUID v73; // [rsp+D0h] [rbp+A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+E0h] [rbp+B0h] BYREF
  DWORD *p_dwCertEncodingType; // [rsp+100h] [rbp+D0h]
  __int64 v76; // [rsp+108h] [rbp+D8h]
  DWORD *p_cbCertEncoded; // [rsp+110h] [rbp+E0h]
  __int64 v78; // [rsp+118h] [rbp+E8h]
  unsigned int *v79; // [rsp+120h] [rbp+F0h]
  __int64 v80; // [rsp+128h] [rbp+F8h]
  _DWORD *v81; // [rsp+130h] [rbp+100h]
  __int64 v82; // [rsp+138h] [rbp+108h]
  _DWORD *v83; // [rsp+140h] [rbp+110h]
  __int64 v84; // [rsp+148h] [rbp+118h]
  struct _EVENT_DATA_DESCRIPTOR v85[2]; // [rsp+150h] [rbp+120h] BYREF
  unsigned int *v86; // [rsp+170h] [rbp+140h]
  __int64 v87; // [rsp+178h] [rbp+148h]

  v65 = a4;
  phUserKey = 0;
  lpMem = 0;
  pdwDataLen = 0;
  v58 = 0;
  p_pdwDataLen = 0;
  v59 = 0;
  v7 = 0;
  v66 = a1;
  v8 = 0;
  pvData = 0;
  v70 = 0;
  v71 = 0;
  v67 = 0;
  v68 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v73 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v73);
  if ( (unsigned int)dword_18002B008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)byte_180024FFB, &v73, &ActivityId, 2u, v85);
  pvData = 0;
  v70 = 0;
  v71 = 0;
  if ( !CryptGetUserKey(a3, dwKeySpec, &phUserKey) )
  {
    LastError = GetLastError();
    WppTraceIndent(v12, 2);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 70;
LABEL_12:
      WPP_SF_sd(v13[2], v14, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, LastError);
      goto LABEL_106;
    }
    goto LABEL_106;
  }
  if ( CryptGetKeyParam(phUserKey, 0x1Au, 0, &pdwDataLen, 0) )
  {
    v17 = pdwDataLen;
    if ( !pdwDataLen )
      goto LABEL_26;
    if ( pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_26;
    v18 = pdwDataLen + g_ulAdditionalProbeSize + 8;
    if ( v18 < pdwDataLen || !(unsigned int)VerifyStackAvailable(v18, v15) )
      goto LABEL_26;
    v19 = v17 + 23;
    if ( v17 + 23 <= v17 + 8 )
      v19 = 0xFFFFFFFFFFFFFF0LL;
    v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
    v21 = alloca(v20);
    v22 = alloca(v20);
    p_pdwDataLen = &pdwDataLen;
    if ( v56 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = &v59) == 0) )
    {
LABEL_26:
      v20 = v17 + 8;
      if ( v17 + 8 >= v17 )
      {
        v23 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pdwDataLen = v23;
        if ( v23 )
        {
          *v23 = 1885431112;
          p_pdwDataLen = v23 + 2;
        }
      }
    }
    if ( !p_pdwDataLen )
    {
      WppTraceIndent(v20, 2);
      LastError = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_106;
    }
    if ( !CryptGetKeyParam(phUserKey, 0x1Au, (BYTE *)p_pdwDataLen, &pdwDataLen, 0) )
    {
      LastError = GetLastError();
      WppTraceIndent(v24, 2);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 73;
        goto LABEL_12;
      }
      goto LABEL_106;
    }
    CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)p_pdwDataLen, pdwDataLen);
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      goto LABEL_106;
    }
    if ( (unsigned int)dword_18002B008 > 5 )
    {
      p_dwVersion = &CertificateContext->pCertInfo->dwVersion;
      dwCertEncodingType = CertificateContext->dwCertEncodingType;
      v76 = 4;
      p_dwCertEncodingType = &dwCertEncodingType;
      cbCertEncoded = CertificateContext->cbCertEncoded;
      p_cbCertEncoded = &cbCertEncoded;
      v78 = 4;
      v61 = *p_dwVersion;
      v79 = &v61;
      v81 = p_dwVersion + 16;
      v83 = p_dwVersion + 18;
      v80 = 4;
      v82 = 8;
      v84 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)p_dwVersion,
        (unsigned __int8 *)byte_180024F09,
        &v73,
        &ActivityId,
        7u,
        &v74);
    }
    LastError = I_ReaderListBuildCredFromCertContext(v66, CertificateContext, v65, dwKeySpec, &lpMem);
    if ( LastError )
    {
      WppTraceIndent(v27, 2);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v29 = 74;
      goto LABEL_48;
    }
    *((_QWORD *)&pvData + 1) = *(_QWORD *)(a2 + 80);
    LODWORD(v70) = *(_DWORD *)(a2 + 120);
    *(_QWORD *)&pvData = v65;
    DWORD2(v71) = dwKeySpec;
    if ( !CertSetCertificateContextProperty(CertificateContext, 2u, 0, &pvData) )
    {
LABEL_50:
      LastError = GetLastError();
      goto LABEL_105;
    }
    KeyParam = CryptGetKeyParam(phUserKey, 0x2Bu, 0, &v58, 0x40u);
    v31 = CryptGetKeyParam(phUserKey, 0x2Cu, 0, &v59, 0x40u);
    if ( KeyParam && v31 )
    {
      v33 = v58;
      if ( !v58 )
        goto LABEL_61;
      if ( v58 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_61;
      v34 = v58 + g_ulAdditionalProbeSize + 8;
      if ( v34 < v58 || !(unsigned int)VerifyStackAvailable(v34, v32) )
        goto LABEL_61;
      v35 = v33 + 23;
      if ( v33 + 23 <= v33 + 8 )
        v35 = 0xFFFFFFFFFFFFFF0LL;
      v36 = v35 & 0xFFFFFFFFFFFFFFF0uLL;
      v37 = alloca(v36);
      v38 = alloca(v36);
      v7 = &pdwDataLen;
      if ( v56 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (v7 = &v59) == 0) )
      {
LABEL_61:
        v36 = v33 + 8;
        if ( v33 + 8 >= v33 )
        {
          v39 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v7 = v39;
          if ( v39 )
          {
            *v39 = 1885431112;
            v7 = v39 + 2;
          }
        }
      }
      if ( !v7 )
      {
        WppTraceIndent(v36, 2);
        LastError = 8;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v41 = 75;
        goto LABEL_69;
      }
      if ( !CryptGetKeyParam(phUserKey, 0x2Bu, (BYTE *)v7, &v58, 0x40u) )
      {
        LastError = GetLastError();
        WppTraceIndent(v42, 2);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v29 = 76;
        goto LABEL_48;
      }
      LODWORD(v67) = v58;
      *((_QWORD *)&v67 + 1) = v7;
      if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Au, 0x40000000u, &v67) )
        goto LABEL_50;
      v44 = v59;
      if ( !v59 )
        goto LABEL_84;
      if ( v59 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_84;
      v45 = v59 + g_ulAdditionalProbeSize + 8;
      if ( v45 < v59 || !(unsigned int)VerifyStackAvailable(v45, v43) )
        goto LABEL_84;
      v46 = v44 + 23;
      if ( v44 + 23 <= v44 + 8 )
        v46 = 0xFFFFFFFFFFFFFF0LL;
      v47 = v46 & 0xFFFFFFFFFFFFFFF0uLL;
      v48 = alloca(v47);
      v49 = alloca(v47);
      v8 = &pdwDataLen;
      if ( v56 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (v8 = &v59) == 0) )
      {
LABEL_84:
        v47 = v44 + 8;
        if ( v44 + 8 >= v44 )
        {
          v50 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v8 = v50;
          if ( v50 )
          {
            *v50 = 1885431112;
            v8 = v50 + 2;
          }
        }
      }
      if ( !v8 )
      {
        WppTraceIndent(v47, 2);
        LastError = 8;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v41 = 77;
LABEL_69:
        WPP_SF_s(v40[2], v41, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_105;
      }
      if ( !CryptGetKeyParam(phUserKey, 0x2Cu, (BYTE *)v8, &v59, 0x40u) )
      {
        LastError = GetLastError();
        WppTraceIndent(v51, 2);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_105;
        }
        v29 = 78;
LABEL_48:
        WPP_SF_sd(v28[2], v29, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, LastError);
LABEL_105:
        CertFreeCertificateContext(CertificateContext);
        goto LABEL_106;
      }
      LODWORD(v68) = v59;
      *((_QWORD *)&v68 + 1) = v8;
      if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Bu, 0x40000000u, &v68) )
        goto LABEL_50;
    }
    if ( CertAddCertificateContextToStore(*(HCERTSTORE *)(a2 + 168), CertificateContext, 4u, 0) )
    {
      LastError = I_ReaderListBuildCredFromCertContext(v66, CertificateContext, v65, dwKeySpec, &lpMem);
      if ( !LastError )
      {
        I_ReaderListAddCredToList(lpMem, *(unsigned __int16 **)(a2 + 96), (__int64 *)(a2 + 232));
        lpMem = 0;
        goto LABEL_105;
      }
      WppTraceIndent(v52, 2);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v29 = 79;
      goto LABEL_48;
    }
    goto LABEL_50;
  }
  LastError = GetLastError();
  WppTraceIndent(v16, 2);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 71;
    goto LABEL_12;
  }
LABEL_106:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v7 && *(v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v8 && *(v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  v53 = lpMem;
  if ( lpMem )
    I_FreeCredListItem((LPVOID *)lpMem);
  if ( (unsigned int)dword_18002B008 > 5 )
  {
    v61 = LastError;
    v86 = &v61;
    v87 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)v53, (unsigned __int8 *)byte_18002551F, &v73, &ActivityId, 3u, v85);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v54, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180019250  push    rbp
0x180019252  push    rbx
0x180019253  push    rsi
0x180019254  push    rdi
0x180019255  push    r12
0x180019257  push    r13
0x180019259  push    r14
0x18001925b  push    r15
0x18001925d  sub     rsp, 198h
0x180019264  lea     rbp, [rsp+30h]
0x180019269  mov     rax, cs:__security_cookie
0x180019270  xor     rax, rbp
0x180019273  mov     [rbp+1A0h+var_50], rax
0x18001927a  xor     r15d, r15d
0x18001927d  mov     [rbp+1A0h+var_170], r9
0x180019281  xorps   xmm0, xmm0
0x180019284  mov     [rbp+1A0h+phUserKey], r15
0x180019288  mov     r13, rdx
0x18001928b  mov     [rbp+1A0h+lpMem], r15
0x18001928f  xorps   xmm1, xmm1
0x180019292  mov     [rbp+1A0h+pdwDataLen], r15d
0x180019296  xor     edx, edx
0x180019298  mov     [rbp+1A0h+var_19C], r15d
0x18001929c  mov     edi, r15d
0x18001929f  mov     [rbp+1A0h+var_198], r15d
0x1800192a3  mov     r14d, r15d
0x1800192a6  mov     [rbp+1A0h+var_168], rcx
0x1800192aa  mov     esi, r15d
0x1800192ad  mov     rbx, r8
0x1800192b0  movups  [rbp+1A0h+pvData], xmm0
0x1800192b4  movups  [rbp+1A0h+var_130], xmm0
0x1800192b8  movups  [rbp+1A0h+var_120], xmm0
0x1800192bf  movups  [rbp+1A0h+var_160], xmm0
0x1800192c3  movups  [rbp+1A0h+var_150], xmm1
0x1800192c7  call    WppTraceIndent
0x1800192cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192d3  lea     rax, WPP_GLOBAL_Control
0x1800192da  cmp     rcx, rax
0x1800192dd  jz      short loc_180019306
0x1800192df  test    byte ptr [rcx+1Ch], 2
0x1800192e3  jz      short loc_180019306
0x1800192e5  cmp     byte ptr [rcx+19h], 5
0x1800192e9  jb      short loc_180019306
0x1800192eb  mov     r9, cs:WPP_pszIndent
0x1800192f2  lea     edx, [r15+45h]
0x1800192f6  mov     rcx, [rcx+10h]
0x1800192fa  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019301  call    WPP_SF_s
0x180019306  xorps   xmm0, xmm0
0x180019309  lea     rdx, [rbp+1A0h+ActivityId]; ActivityId
0x180019310  xorps   xmm1, xmm1
0x180019313  mov     ecx, 5; ControlCode
0x180019318  movups  xmmword ptr [rbp+1A0h+ActivityId.Data1], xmm0
0x18001931f  movups  xmmword ptr [rbp+1A0h+var_100.Data1], xmm1
0x180019326  call    cs:__imp_EventActivityIdControl
0x18001932c  lea     rdx, [rbp+1A0h+var_100]; ActivityId
0x180019333  mov     ecx, 1; ControlCode
0x180019338  call    cs:__imp_EventActivityIdControl
0x18001933e  mov     eax, cs:dword_18002B008
0x180019344  cmp     eax, 5
0x180019347  jbe     short loc_180019377
0x180019349  lea     rax, [rbp+1A0h+var_80]
0x180019350  mov     [rsp+1D0h+var_1A8], rax
0x180019355  lea     r9, [rbp+1A0h+ActivityId]
0x18001935c  lea     r8, [rbp+1A0h+var_100]
0x180019363  mov     [rsp+1D0h+dwFlags], 2
0x18001936b  lea     rdx, byte_180024FFB
0x180019372  call    _tlgWriteTransfer_EventWriteTransfer
0x180019377  mov     r12d, [rbp+1A0h+dwKeySpec]
0x18001937e  lea     r8, [rbp+1A0h+phUserKey]; phUserKey
0x180019382  xorps   xmm0, xmm0
0x180019385  mov     edx, r12d; dwKeySpec
0x180019388  mov     rcx, rbx; hProv
0x18001938b  movups  [rbp+1A0h+pvData], xmm0
0x18001938f  movups  [rbp+1A0h+var_130], xmm0
0x180019393  movups  [rbp+1A0h+var_120], xmm0
0x18001939a  call    cs:__imp_CryptGetUserKey
0x1800193a0  cmp     eax, 1
0x1800193a3  jz      short loc_180019407
0x1800193a5  call    cs:__imp_GetLastError
0x1800193ab  mov     edx, 2
0x1800193b0  mov     ebx, eax
0x1800193b2  call    WppTraceIndent
0x1800193b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193be  lea     r12, WPP_GLOBAL_Control
0x1800193c5  cmp     rcx, r12
0x1800193c8  jz      loc_180019B3C
0x1800193ce  test    byte ptr [rcx+1Ch], 1
0x1800193d2  jz      loc_180019B3C
0x1800193d8  cmp     byte ptr [rcx+19h], 2
0x1800193dc  jb      loc_180019B3C
0x1800193e2  mov     edx, 46h ; 'F'
0x1800193e7  mov     r9, cs:WPP_pszIndent
0x1800193ee  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800193f5  mov     rcx, [rcx+10h]
0x1800193f9  mov     [rsp+1D0h+dwFlags], ebx
0x1800193fd  call    WPP_SF_sd
0x180019402  jmp     loc_180019B3C
0x180019407  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x18001940b  lea     r9, [rbp+1A0h+pdwDataLen]; pdwDataLen
0x18001940f  xor     r8d, r8d; pbData
0x180019412  mov     [rsp+1D0h+dwFlags], r15d; dwFlags
0x180019417  lea     edx, [r8+1Ah]; dwParam
0x18001941b  call    cs:__imp_CryptGetKeyParam
0x180019421  cmp     eax, 1
0x180019424  jz      short loc_18001946D
0x180019426  call    cs:__imp_GetLastError
0x18001942c  mov     edx, 2
0x180019431  mov     ebx, eax
0x180019433  call    WppTraceIndent
0x180019438  mov     rcx, cs:WPP_GLOBAL_Control
0x18001943f  lea     r12, WPP_GLOBAL_Control
0x180019446  cmp     rcx, r12
0x180019449  jz      loc_180019B3C
0x18001944f  test    byte ptr [rcx+1Ch], 1
0x180019453  jz      loc_180019B3C
0x180019459  cmp     byte ptr [rcx+19h], 2
0x18001945d  jb      loc_180019B3C
0x180019463  mov     edx, 47h ; 'G'
0x180019468  jmp     loc_1800193E7
0x18001946d  mov     ebx, [rbp+1A0h+pdwDataLen]
0x180019470  test    rbx, rbx
0x180019473  jz      short loc_1800194D6
0x180019475  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001947c  ja      short loc_1800194D6
0x18001947e  mov     rcx, cs:g_ulAdditionalProbeSize
0x180019485  add     rcx, 8
0x180019489  add     rcx, rbx
0x18001948c  cmp     rcx, rbx
0x18001948f  jb      short loc_1800194D6
0x180019491  call    VerifyStackAvailable
0x180019496  test    eax, eax
0x180019498  jz      short loc_1800194D6
0x18001949a  lea     rax, [rbx+8]
0x18001949e  lea     rcx, [rax+0Fh]
0x1800194a2  cmp     rcx, rax
0x1800194a5  ja      short loc_1800194B1
0x1800194a7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800194b1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800194b5  mov     rax, rcx
0x1800194b8  call    _alloca_probe
0x1800194bd  sub     rsp, rcx
0x1800194c0  lea     rdi, [rsp+1D0h+pdwDataLen]
0x1800194c5  test    rdi, rdi
0x1800194c8  jz      short loc_1800194D6
0x1800194ca  mov     dword ptr [rdi], 6B637453h
0x1800194d0  add     rdi, 8
0x1800194d4  jnz     short loc_1800194FD
0x1800194d6  lea     rcx, [rbx+8]
0x1800194da  cmp     rcx, rbx
0x1800194dd  jb      short loc_1800194FD
0x1800194df  mov     rax, cs:g_pfnAllocate
0x1800194e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194eb  mov     rdi, rax
0x1800194ee  test    rax, rax
0x1800194f1  jz      short loc_1800194FD
0x1800194f3  mov     dword ptr [rax], 70616548h
0x1800194f9  add     rdi, 8
0x1800194fd  test    rdi, rdi
0x180019500  jnz     short loc_180019557
0x180019502  lea     edx, [rdi+2]
0x180019505  call    WppTraceIndent
0x18001950a  lea     ebx, [rdi+8]
0x18001950d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019514  lea     r12, WPP_GLOBAL_Control
0x18001951b  cmp     rcx, r12
0x18001951e  jz      loc_180019B3C
0x180019524  test    byte ptr [rcx+1Ch], 1
0x180019528  jz      loc_180019B3C
0x18001952e  cmp     byte ptr [rcx+19h], 2
0x180019532  jb      loc_180019B3C
0x180019538  mov     r9, cs:WPP_pszIndent
0x18001953f  lea     edx, [rdi+48h]
0x180019542  mov     rcx, [rcx+10h]
0x180019546  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001954d  call    WPP_SF_s
0x180019552  jmp     loc_180019B3C
0x180019557  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x18001955b  lea     r9, [rbp+1A0h+pdwDataLen]; pdwDataLen
0x18001955f  mov     r8, rdi; pbData
0x180019562  mov     [rsp+1D0h+dwFlags], r15d; dwFlags
0x180019567  mov     edx, 1Ah; dwParam
0x18001956c  call    cs:__imp_CryptGetKeyParam
0x180019572  cmp     eax, 1
0x180019575  jz      short loc_1800195BE
0x180019577  call    cs:__imp_GetLastError
0x18001957d  mov     edx, 2
0x180019582  mov     ebx, eax
0x180019584  call    WppTraceIndent
0x180019589  mov     rcx, cs:WPP_GLOBAL_Control
0x180019590  lea     r12, WPP_GLOBAL_Control
0x180019597  cmp     rcx, r12
0x18001959a  jz      loc_180019B3C
0x1800195a0  test    byte ptr [rcx+1Ch], 1
0x1800195a4  jz      loc_180019B3C
0x1800195aa  cmp     byte ptr [rcx+19h], 2
0x1800195ae  jb      loc_180019B3C
0x1800195b4  mov     edx, 49h ; 'I'
0x1800195b9  jmp     loc_1800193E7
0x1800195be  mov     r8d, [rbp+1A0h+pdwDataLen]; cbCertEncoded
0x1800195c2  mov     rdx, rdi; pbCertEncoded
0x1800195c5  mov     ecx, 10001h; dwCertEncodingType
0x1800195ca  call    cs:__imp_CertCreateCertificateContext
0x1800195d0  mov     r15, rax
0x1800195d3  test    rax, rax
0x1800195d6  jnz     short loc_1800195EC
0x1800195d8  call    cs:__imp_GetLastError
0x1800195de  mov     ebx, eax
0x1800195e0  lea     r12, WPP_GLOBAL_Control
0x1800195e7  jmp     loc_180019B3C
0x1800195ec  mov     eax, cs:dword_18002B008
0x1800195f2  cmp     eax, 5
0x1800195f5  jbe     loc_1800196AD
0x1800195fb  mov     rcx, [r15+18h]
0x1800195ff  lea     r9, [rbp+1A0h+ActivityId]
0x180019606  mov     eax, [r15]
0x180019609  lea     r8, [rbp+1A0h+var_100]
0x180019610  mov     [rbp+1A0h+var_178], eax
0x180019613  lea     rdx, byte_180024F09
0x18001961a  lea     rax, [rbp+1A0h+var_178]
0x18001961e  mov     [rbp+1A0h+var_C8], 4
0x180019629  mov     [rbp+1A0h+var_D0], rax
0x180019630  mov     eax, [r15+10h]
0x180019634  mov     [rbp+1A0h+var_174], eax
0x180019637  lea     rax, [rbp+1A0h+var_174]
0x18001963b  mov     [rbp+1A0h+var_C0], rax
0x180019642  mov     [rbp+1A0h+var_B8], 4
0x18001964d  mov     eax, [rcx]
0x18001964f  mov     [rbp+1A0h+var_188], eax
0x180019652  lea     rax, [rbp+1A0h+var_188]
0x180019656  mov     [rbp+1A0h+var_B0], rax
0x18001965d  lea     rax, [rcx+40h]
0x180019661  mov     [rbp+1A0h+var_A0], rax
0x180019668  lea     rax, [rcx+48h]
0x18001966c  mov     [rbp+1A0h+var_90], rax
0x180019673  lea     rax, [rbp+1A0h+var_F0]
0x18001967a  mov     [rsp+1D0h+var_1A8], rax
0x18001967f  mov     [rsp+1D0h+dwFlags], 7
0x180019687  mov     [rbp+1A0h+var_A8], 4
0x180019692  mov     [rbp+1A0h+var_98], 8
0x18001969d  mov     [rbp+1A0h+var_88], 8
0x1800196a8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800196ad  mov     r8, [rbp+1A0h+var_170]
0x1800196b1  lea     rax, [rbp+1A0h+lpMem]
0x1800196b5  mov     rcx, [rbp+1A0h+var_168]
0x1800196b9  mov     r9d, r12d
0x1800196bc  mov     rdx, r15
0x1800196bf  mov     qword ptr [rsp+1D0h+dwFlags], rax
0x1800196c4  call    I_ReaderListBuildCredFromCertContext
0x1800196c9  mov     ebx, eax
0x1800196cb  mov     edx, 2; dwPropId
0x1800196d0  test    eax, eax
0x1800196d2  jz      short loc_180019729
0x1800196d4  call    WppTraceIndent
0x1800196d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196e0  lea     r12, WPP_GLOBAL_Control
0x1800196e7  cmp     rcx, r12
0x1800196ea  jz      loc_180019B33
0x1800196f0  test    byte ptr [rcx+1Ch], 1
0x1800196f4  jz      loc_180019B33
0x1800196fa  cmp     byte ptr [rcx+19h], 2
0x1800196fe  jb      loc_180019B33
0x180019704  mov     edx, 4Ah ; 'J'
0x180019709  mov     r9, cs:WPP_pszIndent
0x180019710  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019717  mov     rcx, [rcx+10h]
0x18001971b  mov     [rsp+1D0h+dwFlags], ebx
0x18001971f  call    WPP_SF_sd
0x180019724  jmp     loc_180019B33
0x180019729  mov     rax, [r13+50h]
0x18001972d  lea     r9, [rbp+1A0h+pvData]; pvData
0x180019731  mov     qword ptr [rbp+1A0h+pvData+8], rax
0x180019735  xor     r8d, r8d; dwFlags
0x180019738  mov     eax, [r13+78h]
0x18001973c  mov     rcx, r15; pCertContext
0x18001973f  mov     dword ptr [rbp+1A0h+var_130], eax
0x180019742  mov     rax, [rbp+1A0h+var_170]
0x180019746  mov     qword ptr [rbp+1A0h+pvData], rax
0x18001974a  mov     dword ptr [rbp+1A0h+var_120+8], r12d
0x180019751  call    cs:__imp_CertSetCertificateContextProperty
0x180019757  test    eax, eax
0x180019759  jnz     short loc_180019768
0x18001975b  call    cs:__imp_GetLastError
0x180019761  mov     ebx, eax
0x180019763  jmp     loc_180019B2C
0x180019768  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x18001976c  lea     r9, [rbp+1A0h+var_19C]; pdwDataLen
0x180019770  xor     r8d, r8d; pbData
0x180019773  mov     [rsp+1D0h+dwFlags], 40h ; '@'; dwFlags
0x18001977b  lea     edx, [r8+2Bh]; dwParam
0x18001977f  call    cs:__imp_CryptGetKeyParam
0x180019785  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x180019789  lea     r9, [rbp+1A0h+var_198]; pdwDataLen
0x18001978d  xor     r8d, r8d; pbData
0x180019790  mov     [rsp+1D0h+dwFlags], 40h ; '@'; dwFlags
0x180019798  mov     ebx, eax
0x18001979a  lea     edx, [r8+2Ch]; dwParam
0x18001979e  call    cs:__imp_CryptGetKeyParam
0x1800197a4  test    ebx, ebx
0x1800197a6  jz      loc_180019A9C
  ... truncated ...
```
