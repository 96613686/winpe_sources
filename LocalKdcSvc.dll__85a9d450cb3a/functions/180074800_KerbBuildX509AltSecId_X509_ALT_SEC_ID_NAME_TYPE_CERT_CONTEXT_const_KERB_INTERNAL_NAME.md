# KerbBuildX509AltSecId(_X509_ALT_SEC_ID_NAME_TYPE,_CERT_CONTEXT const *,_KERB_INTERNAL_NAME * *)

- ea: `0x180074800`
- end: `0x18007575c`
- name: `?KerbBuildX509AltSecId@@YAJW4_X509_ALT_SEC_ID_NAME_TYPE@@PEBU_CERT_CONTEXT@@PEAPEAU_KERB_INTERNAL_NAME@@@Z`
- size: `3932`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016148`
- `0x180029844`
- `0x18004ecb4`
- `0x18005508c`

## callees

- `0x180002ad0`
- `0x18000aab8`
- `0x18000e9e8`
- `0x18000eae0`
- `0x1800101c4`
- `0x1800101ec`
- `0x1800135b4`
- `0x18005654c`
- `0x18005a060`
- `0x18005a090`
- `0x18007473c`
- `0x1800747d8`
- `0x180074800`
- `0x180075764`
- `0x180075944`
- `0x1800761d4`
- `0x180076c30`
- `0x180077d78`
- `0x18007c274`
- `0x18007d760`
- `0x18007dc20`
- `0x180099c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007512d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800752d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800753b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007543f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007512d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800752d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800753b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007543f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756c0`
- `CRYPT32!CryptBinaryToStringW` at `0x180074eeb`
- `CRYPT32!CryptBinaryToStringW` at `0x180074fb9`
- `CRYPT32!CryptBinaryToStringW` at `0x180075102`
- `CRYPT32!CryptBinaryToStringW` at `0x1800751d9`
- `CRYPT32!CryptBinaryToStringW` at `0x1800752a5`
- `CRYPT32!CryptBinaryToStringW` at `0x180075414`
- `CRYPT32!CryptBinaryToStringW` at `0x180074eeb`
- `CRYPT32!CryptBinaryToStringW` at `0x180074fb9`
- `CRYPT32!CryptBinaryToStringW` at `0x180075102`
- `CRYPT32!CryptBinaryToStringW` at `0x1800751d9`
- `CRYPT32!CryptBinaryToStringW` at `0x1800752a5`
- `CRYPT32!CryptBinaryToStringW` at `0x180075414`
- `CRYPT32!CertNameToStrW` at `0x1800749d3`
- `CRYPT32!CertNameToStrW` at `0x180074a8b`
- `CRYPT32!CertNameToStrW` at `0x180074c0f`
- `CRYPT32!CertNameToStrW` at `0x180074cea`
- `CRYPT32!CertNameToStrW` at `0x180074d84`
- `CRYPT32!CertNameToStrW` at `0x180074e54`
- `CRYPT32!CertNameToStrW` at `0x180075245`
- `CRYPT32!CertNameToStrW` at `0x180075389`
- `CRYPT32!CertNameToStrW` at `0x1800754c8`
- `CRYPT32!CertNameToStrW` at `0x1800754e6`
- `CRYPT32!CertNameToStrW` at `0x1800755ac`
- `CRYPT32!CertNameToStrW` at `0x18007563e`
- `CRYPT32!CertNameToStrW` at `0x1800749d3`
- `CRYPT32!CertNameToStrW` at `0x180074a8b`
- `CRYPT32!CertNameToStrW` at `0x180074c0f`
- `CRYPT32!CertNameToStrW` at `0x180074cea`
- `CRYPT32!CertNameToStrW` at `0x180074d84`
- `CRYPT32!CertNameToStrW` at `0x180074e54`
- `CRYPT32!CertNameToStrW` at `0x180075245`
- `CRYPT32!CertNameToStrW` at `0x180075389`
- `CRYPT32!CertNameToStrW` at `0x1800754c8`
- `CRYPT32!CertNameToStrW` at `0x1800754e6`
- `CRYPT32!CertNameToStrW` at `0x1800755ac`
- `CRYPT32!CertNameToStrW` at `0x18007563e`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007507c`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007507c`

## string_xrefs

- `0x180074b07`: `<SID>`

## pseudocode

```c
__int64 __fastcall KerbBuildX509AltSecId(int a1, const struct _CERT_CONTEXT *a2, struct _KERB_INTERNAL_NAME **a3)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __m128i *ExtendedSanFromCert; // rax
  __int64 v11; // r9
  signed int CertificateHash; // ebx
  DWORD v13; // eax
  unsigned __int64 csz; // rdi
  DWORD v15; // eax
  __int64 v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  LPWSTR v18; // rbx
  DWORD v19; // eax
  __int16 v20; // di
  DWORD v21; // eax
  unsigned __int16 v22; // dx
  struct _CRYPTOAPI_BLOB *v23; // rcx
  CSecurityData *v24; // rcx
  __int64 v25; // rdx
  DWORD v26; // eax
  DWORD v27; // r15d
  WCHAR *v28; // rax
  WCHAR *v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rax
  WCHAR *v32; // rdx
  DWORD v33; // eax
  DWORD LastError; // eax
  __int64 v35; // rdx
  __int16 v36; // ax
  struct _CRYPTOAPI_BLOB *v37; // rcx
  DWORD v38; // eax
  DWORD v39; // r15d
  WCHAR *v40; // rax
  WCHAR *v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rax
  WCHAR *v44; // rdx
  DWORD v45; // eax
  WCHAR *v46; // rax
  WCHAR *v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rax
  WCHAR *v50; // r8
  __int16 v51; // ax
  PCERT_INFO pCertInfo; // rax
  DWORD cExtension; // r14d
  PCERT_EXTENSION rgExtension; // r15
  unsigned int v55; // ebx
  __int64 v56; // rdi
  DWORD v57; // esi
  const BYTE *v58; // r14
  WCHAR *v59; // rax
  WCHAR *v60; // rcx
  __int64 v61; // rbx
  __int64 v62; // rax
  WCHAR *v63; // rdx
  DWORD v64; // eax
  unsigned __int64 v65; // r12
  WCHAR *v66; // rax
  WCHAR *v67; // rcx
  __int64 v68; // rbx
  __int64 v69; // rax
  WCHAR *v70; // rdx
  __int64 v71; // rax
  WCHAR *v72; // r13
  DWORD v73; // eax
  __int16 v74; // di
  WCHAR *v75; // rdx
  struct _CRYPTOAPI_BLOB *v76; // rdx
  __int64 v77; // r15
  DWORD v78; // eax
  DWORD v79; // r12d
  WCHAR *v80; // rax
  WCHAR *v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rax
  WCHAR *v84; // rdx
  __int64 v85; // rax
  WCHAR *v86; // r13
  DWORD v87; // eax
  __int16 v88; // di
  WCHAR *v89; // rdx
  DWORD v90; // eax
  struct _UNICODE_STRING v92; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchString; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v94; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v95; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR psz; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbStructInfo; // [rsp+68h] [rbp-98h] BYREF
  void *pvStructInfo; // [rsp+70h] [rbp-90h] BYREF
  struct _KERB_INTERNAL_NAME **v99; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v100; // [rsp+80h] [rbp-80h] BYREF
  void *v101[2]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v102[8]; // [rsp+A0h] [rbp-60h] BYREF
  struct _CRYPT_DECODE_PARA pDecodePara; // [rsp+B0h] [rbp-50h] BYREF
  __m128i Sid[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h]
  char v106[72]; // [rsp+120h] [rbp+20h] BYREF
  BYTE pbBinary[24]; // [rsp+168h] [rbp+68h] BYREF

  v99 = a3;
  v95 = 0;
  v101[0] = v102;
  v101[1] = v102;
  pDecodePara.pfnAlloc = MIDL_user_allocate;
  pDecodePara.pfnFree = MIDL_user_free;
  v94 = 0;
  pcchString = 0;
  v102[0] = 0;
  *(_QWORD *)&pDecodePara.cbSize = 24;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v92 = 0;
  v100 = 0;
  if ( !a1 )
  {
    if ( IsCertNameBlobEmpty(&a2->pCertInfo->Subject) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_154;
      v25 = 30;
LABEL_153:
      WPP_SF_(*((_QWORD *)v24 + 2), v25, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
      goto LABEL_154;
    }
    v77 = CertNameToStrW(a2->dwCertEncodingType, v76 + 3, 0x28200003u, 0, 0);
    v78 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Subject, 0x28200003u, 0, 0);
    v79 = v78;
    if ( (unsigned int)v77 > 1 && v78 > 1 )
    {
      if ( (unsigned int)v77 > 0x7FF0 || v78 > (unsigned __int64)(32752 - v77) )
        goto LABEL_158;
      v92.Length = 2 * (v77 + v78 + 11);
      v92.MaximumLength = v92.Length + 2;
      v80 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
      v92.Buffer = v80;
      v81 = v80;
      if ( v80 )
      {
        v82 = -1;
        *(_QWORD *)v80 = *(_QWORD *)L"X509:";
        *((_DWORD *)v80 + 2) = *(_DWORD *)L":";
        v83 = -1;
        do
          ++v83;
        while ( v81[v83] );
        v84 = &v81[v83];
        *(_QWORD *)v84 = *(_QWORD *)L"<I>";
        v85 = -1;
        do
          ++v85;
        while ( v84[v85] );
        v86 = &v84[v85];
        v87 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Issuer, 0x28200003u, v86, v77);
        v88 = v87;
        if ( v87 <= 1 )
        {
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_170;
          }
          LastError = GetLastError();
          v35 = 32;
          goto LABEL_169;
        }
        v89 = &v86[v87 - 1];
        *(_QWORD *)v89 = 0x3E0053003CLL;
        do
          ++v82;
        while ( v89[v82] );
        v90 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Subject, 0x28200003u, &v89[v82], v79);
        if ( v90 <= 1 )
        {
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_170;
          }
          LastError = GetLastError();
          v35 = 33;
          goto LABEL_169;
        }
        v36 = v88 + v90 + 11;
        goto LABEL_178;
      }
      goto LABEL_185;
    }
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v15 = GetLastError();
    v16 = 31;
LABEL_184:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, v15);
    goto LABEL_185;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v64 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Issuer, 0x28200003u, 0, 0);
    v65 = v64;
    if ( v64 > 1 )
    {
      if ( !CryptBinaryToStringW(
              a2->pCertInfo->SerialNumber.pbData,
              a2->pCertInfo->SerialNumber.cbData,
              0x4000000Cu,
              0,
              &v95) )
      {
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_170;
        }
        LastError = GetLastError();
        v35 = 41;
        goto LABEL_169;
      }
      if ( v95 > 0x7FEF || v65 > 32751 - (unsigned __int64)v95 )
        goto LABEL_158;
      v92.Length = 2 * (v95 + v65 + 12);
      v92.MaximumLength = v92.Length + 2;
      v66 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
      v92.Buffer = v66;
      v67 = v66;
      if ( v66 )
      {
        v68 = -1;
        *(_QWORD *)v66 = *(_QWORD *)L"X509:";
        *((_DWORD *)v66 + 2) = *(_DWORD *)L":";
        v69 = -1;
        do
          ++v69;
        while ( v67[v69] );
        v70 = &v67[v69];
        *(_QWORD *)v70 = *(_QWORD *)L"<I>";
        v71 = -1;
        do
          ++v71;
        while ( v70[v71] );
        v72 = &v70[v71];
        v73 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Issuer, 0x28200003u, v72, v65);
        v74 = v73;
        if ( v73 <= 1 )
        {
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_170;
          }
          LastError = GetLastError();
          v35 = 42;
          goto LABEL_169;
        }
        v75 = &v72[v73 - 1];
        *(_QWORD *)v75 = *(_QWORD *)L"<SR>";
        v75[4] = aSr[4];
        do
          ++v68;
        while ( v75[v68] );
        if ( !CryptBinaryToStringW(
                a2->pCertInfo->SerialNumber.pbData,
                a2->pCertInfo->SerialNumber.cbData,
                0x4000000Cu,
                &v75[v68],
                &v95) )
        {
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_170;
          }
          LastError = GetLastError();
          v35 = 43;
          goto LABEL_169;
        }
        v92.Length = 2 * (v95 + v74 + 12);
LABEL_179:
        KerbConvertNameString(&v92, v22);
        goto LABEL_180;
      }
      goto LABEL_185;
    }
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v15 = GetLastError();
    v16 = 40;
    goto LABEL_184;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    pCertInfo = a2->pCertInfo;
    cExtension = pCertInfo->cExtension;
    if ( !cExtension )
      goto LABEL_154;
    rgExtension = pCertInfo->rgExtension;
    v55 = 0;
    while ( 1 )
    {
      v56 = v55;
      if ( !strcmp_0(rgExtension[v56].pszObjId, "2.5.29.14") )
        break;
      if ( ++v55 >= cExtension )
        goto LABEL_154;
    }
    if ( !CryptDecodeObjectEx(
            a2->dwCertEncodingType,
            (LPCSTR)0x19,
            rgExtension[v56].Value.pbData,
            rgExtension[v56].Value.cbData,
            0x8000u,
            &pDecodePara,
            &pvStructInfo,
            &pcbStructInfo) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_170;
      LastError = GetLastError();
      v35 = 44;
      goto LABEL_169;
    }
    if ( pcbStructInfo < 0x10 )
      goto LABEL_170;
    v57 = *(_DWORD *)pvStructInfo;
    if ( *(_DWORD *)pvStructInfo > pcbStructInfo )
      goto LABEL_170;
    if ( !v57 )
    {
LABEL_154:
      CertificateHash = -1073741275;
      goto LABEL_186;
    }
    v58 = (const BYTE *)*((_QWORD *)pvStructInfo + 1);
    if ( !CryptBinaryToStringW(v58, v57, 0x4000000Cu, 0, &v94) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_170;
      LastError = GetLastError();
      v35 = 45;
      goto LABEL_169;
    }
    if ( v94 > 0x7FF2 )
      goto LABEL_158;
    v92.Length = 2 * (v94 + 10);
    v92.MaximumLength = v92.Length + 2;
    v59 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
    v92.Buffer = v59;
    v60 = v59;
    if ( !v59 )
      goto LABEL_185;
    v61 = -1;
    *(_QWORD *)v59 = *(_QWORD *)L"X509:";
    *((_DWORD *)v59 + 2) = *(_DWORD *)L":";
    v62 = -1;
    do
      ++v62;
    while ( v60[v62] );
    v63 = &v60[v62];
    *(_QWORD *)v63 = *(_QWORD *)L"<SKI>";
    *((_DWORD *)v63 + 2) = *(_DWORD *)L">";
    do
      ++v61;
    while ( v63[v61] );
    if ( !CryptBinaryToStringW(v58, v57, 0x4000000Cu, &v63[v61], &v94) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_170;
      LastError = GetLastError();
      v35 = 46;
      goto LABEL_169;
    }
    v51 = v94 + 10;
LABEL_122:
    v92.Length = 2 * v51;
LABEL_180:
    CertificateHash = (unsigned int)KerbConvertStringToKdcName(v99, &v92) != 0 ? 0xC000009A : 0;
    goto LABEL_186;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    CertificateHash = KerbGetCertificateHash(pbBinary, (unsigned int)a2, a2);
    if ( CertificateHash < 0 )
      goto LABEL_186;
    if ( !CryptBinaryToStringW(pbBinary, 0x14u, 0x4000000Cu, 0, &pcchString) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_170;
      LastError = GetLastError();
      v35 = 47;
      goto LABEL_169;
    }
    v92.Length = 2 * (pcchString + 17);
    v92.MaximumLength = v92.Length + 2;
    v46 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
    v92.Buffer = v46;
    v47 = v46;
    if ( !v46 )
      goto LABEL_185;
    v48 = -1;
    *(_QWORD *)v46 = *(_QWORD *)L"X509:";
    *((_DWORD *)v46 + 2) = *(_DWORD *)L":";
    v49 = -1;
    do
      ++v49;
    while ( v47[v49] );
    v50 = &v47[v49];
    *(_OWORD *)v50 = *(_OWORD *)L"<SHA1-PUKEY>";
    *(_OWORD *)(v50 + 5) = *(_OWORD *)L"-PUKEY>";
    do
      ++v48;
    while ( v50[v48] );
    if ( !CryptBinaryToStringW(pbBinary, 0x14u, 0x4000000Cu, &v50[v48], &pcchString) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_170;
      LastError = GetLastError();
      v35 = 48;
      goto LABEL_169;
    }
    v51 = pcchString + 17;
    goto LABEL_122;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    CertificateHash = KerbGetRFC822NameAltSecIDFromCertificate(a2, &v92);
    if ( CertificateHash < 0 )
      goto LABEL_186;
    goto LABEL_180;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( IsCertNameBlobEmpty(&a2->pCertInfo->Subject) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_154;
      v25 = 34;
      goto LABEL_153;
    }
    v38 = CertNameToStrW(a2->dwCertEncodingType, v37, 0x28200003u, 0, 0);
    v39 = v38;
    if ( v38 > 1 )
    {
      if ( v38 > 0x7FF4 )
        goto LABEL_158;
      v92.Length = 2 * (v38 + 8);
      v92.MaximumLength = v92.Length + 2;
      v40 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
      v92.Buffer = v40;
      v41 = v40;
      if ( v40 )
      {
        v42 = -1;
        *(_QWORD *)v40 = *(_QWORD *)L"X509:";
        *((_DWORD *)v40 + 2) = *(_DWORD *)L":";
        v43 = -1;
        do
          ++v43;
        while ( v41[v43] );
        v44 = &v41[v43];
        *(_QWORD *)v44 = 0x3E0053003CLL;
        do
          ++v42;
        while ( v44[v42] );
        v45 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Subject, 0x28200003u, &v44[v42], v39);
        if ( v45 <= 1 )
        {
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_170;
          }
          LastError = GetLastError();
          v35 = 36;
          goto LABEL_169;
        }
        v36 = v45 + 8;
LABEL_178:
        v92.Length = 2 * v36;
        goto LABEL_179;
      }
LABEL_185:
      CertificateHash = -1073741801;
      goto LABEL_186;
    }
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v15 = GetLastError();
    v16 = 35;
    goto LABEL_184;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( IsCertNameBlobEmpty(&a2->pCertInfo->Subject) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_154;
      v25 = 37;
      goto LABEL_153;
    }
    v26 = CertNameToStrW(a2->dwCertEncodingType, v23, 0x28200003u, 0, 0);
    v27 = v26;
    if ( v26 <= 1 )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_185;
      v15 = GetLastError();
      v16 = 38;
      goto LABEL_184;
    }
    if ( v26 > 0x7FF3 )
      goto LABEL_158;
    v92.Length = 2 * (v26 + 9);
    v92.MaximumLength = v92.Length + 2;
    v28 = (WCHAR *)MIDL_user_allocate((unsigned __int16)(v92.Length + 2));
    v92.Buffer = v28;
    v29 = v28;
    if ( v28 )
    {
      v30 = -1;
      *(_QWORD *)v28 = *(_QWORD *)L"X509N:";
      *((_DWORD *)v28 + 2) = *(_DWORD *)L"N:";
      v28[6] = aX509n[6];
      v31 = -1;
      do
        ++v31;
      while ( v29[v31] );
      v32 = &v29[v31];
      *(_QWORD *)v32 = 0x3E0053003CLL;
      do
        ++v30;
      while ( v32[v30] );
      v33 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Subject, 0x28200003u, &v32[v30], v27);
      if ( v33 <= 1 )
      {
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_170;
        }
        LastError = GetLastError();
        v35 = 39;
LABEL_169:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, LastError);
LABEL_170:
        CertificateHash = -1073741670;
        goto LABEL_186;
      }
      v36 = v33 + 9;
      goto LABEL_178;
    }
    goto LABEL_185;
  }
  if ( v9 != 2 )
    goto LABEL_158;
  ExtendedSanFromCert = (__m128i *)KerbGetExtendedSanFromCert((__int64)v106, (__int64)a2);
  Sid[0] = *ExtendedSanFromCert;
  v11 = (unsigned int)_mm_cvtsi128_si32(Sid[0]);
  Sid[1] = ExtendedSanFromCert[1];
  Sid[2] = ExtendedSanFromCert[2];
  Sid[3] = ExtendedSanFromCert[3];
  v105 = ExtendedSanFromCert[4].m128i_i64[0];
  if ( (int)v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, v11);
    goto LABEL_154;
  }
  CertificateHash = KerbConvertSidToString((char *)Sid[0].m128i_i64 + 4, &v100, 1);
  if ( CertificateHash >= 0 )
  {
    if ( v100.Length <= 0x7FEEu )
    {
      v13 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Issuer, 0x28200003u, 0, 0);
      csz = v13;
      if ( v13 <= 1 )
      {
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_185;
        }
        v15 = GetLastError();
        v16 = 51;
        goto LABEL_184;
      }
      if ( v13 <= 32750 - (unsigned int)v100.Length )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v101,
                                 L"X509:",
                                 5)
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v101,
                                 L"<I>",
                                 3) )
        {
          goto LABEL_185;
        }
        utl::make_unique<unsigned short [0],0>(&psz, csz);
        v18 = psz;
        if ( !psz )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids);
          }
          goto LABEL_39;
        }
        v19 = CertNameToStrW(a2->dwCertEncodingType, &a2->pCertInfo->Issuer, 0x28200003u, psz, csz);
        v20 = v19;
        if ( v19 <= 1 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v21 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids, v21);
          }
          goto LABEL_39;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v101,
                                 v18,
                                 v19 - 1) )
        {
LABEL_39:
          CertificateHash = -1073741801;
          utl::unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>::~unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>(
            (void **)&psz,
            v17);
          goto LABEL_186;
        }
        utl::unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>::~unique_ptr<unsigned long [0],utl::default_delete<unsigned long [0]>>(
          (void **)&psz,
          v17);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v101,
                                 L"<SID>",
                                 5)
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v101,
                                 v100.Buffer,
                                 (unsigned __int64)v100.Length >> 1)
          || !(unsigned int)WStringToUnicodeString(v101, &v92) )
        {
          goto LABEL_185;
        }
        if ( v92.Length > 2 * (unsigned __int64)(unsigned __int16)(v100.Length + v20 + 13) )
        {
          CertificateHash = -1073741595;
          goto LABEL_186;
        }
        goto LABEL_179;
      }
    }
LABEL_158:
    CertificateHash = -1073741637;
    goto LABEL_186;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids,
      (unsigned int)CertificateHash);
LABEL_186:
  KerbFreeString(&v92);
  if ( pvStructInfo )
    MIDL_user_free(pvStructInfo);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v101);
  v99 = (struct _KERB_INTERNAL_NAME **)&v100;
  psz = (LPWSTR)KerbFreeString;
  wistd::invoke<void (*)(_UNICODE_STRING *),_UNICODE_STRING * &>(&psz, &v99);
  return (unsigned int)CertificateHash;
}

```

## disassembly

```asm
0x180074800  mov     [rsp-8+arg_0], rbx
0x180074805  push    rbp
0x180074806  push    rsi
0x180074807  push    rdi
0x180074808  push    r12
0x18007480a  push    r13
0x18007480c  push    r14
0x18007480e  push    r15
0x180074810  lea     rbp, [rsp-90h]
0x180074818  sub     rsp, 190h
0x18007481f  mov     rax, cs:__security_cookie
0x180074826  xor     rax, rsp
0x180074829  mov     [rbp+0C0h+var_40], rax
0x180074830  xor     r13d, r13d
0x180074833  mov     [rsp+1C0h+var_148], r8
0x180074838  mov     [rsp+1C0h+var_168], r13d
0x18007483d  lea     rax, [rbp+0C0h+var_120]
0x180074841  mov     [rbp+0C0h+var_130], rax
0x180074845  lea     rax, [rbp+0C0h+var_120]
0x180074849  mov     [rbp+0C0h+var_128], rax
0x18007484d  lea     rax, MIDL_user_allocate
0x180074854  mov     [rbp+0C0h+var_110.pfnAlloc], rax
0x180074858  lea     rax, MIDL_user_free
0x18007485f  mov     [rbp+0C0h+var_110.pfnFree], rax
0x180074863  xorps   xmm0, xmm0
0x180074866  mov     [rsp+1C0h+var_16C], r13d
0x18007486b  xorps   xmm1, xmm1
0x18007486e  mov     [rsp+1C0h+pcchString], r13d
0x180074873  mov     rsi, rdx
0x180074876  mov     [rbp+0C0h+var_120], r13w
0x18007487b  mov     qword ptr [rbp+0C0h+var_110.cbSize], 18h
0x180074883  mov     [rsp+1C0h+var_150], r13
0x180074888  mov     [rsp+1C0h+var_158], r13d
0x18007488d  movups  xmmword ptr [rsp+1C0h+var_180.Length], xmm0
0x180074892  movups  [rbp+0C0h+var_140], xmm1
0x180074896  test    ecx, ecx
0x180074898  jz      loc_180075465
0x18007489e  sub     ecx, 1
0x1800748a1  jz      loc_18007522A
0x1800748a7  sub     ecx, 1
0x1800748aa  jz      loc_180075002
0x1800748b0  sub     ecx, 1
0x1800748b3  jz      loc_180074EB5
0x1800748b9  sub     ecx, 1
0x1800748bc  jz      loc_180074E99
0x1800748c2  sub     ecx, 1
0x1800748c5  jz      loc_180074D2F
0x1800748cb  sub     ecx, 1
0x1800748ce  jz      loc_180074BBA
0x1800748d4  lea     edi, [r13+2]
0x1800748d8  cmp     ecx, edi
0x1800748da  jnz     loc_18007550D
0x1800748e0  lea     rcx, [rbp+0C0h+var_A0]
0x1800748e4  call    ?KerbGetExtendedSanFromCert@@YA?AUKerbExtendedSanLookupResult@@PEBU_CERT_CONTEXT@@@Z; KerbGetExtendedSanFromCert(_CERT_CONTEXT const *)
0x1800748e9  movups  xmm2, xmmword ptr [rax]
0x1800748ec  movaps  [rbp+0C0h+Sid], xmm2
0x1800748f0  movups  xmm0, xmmword ptr [rax+10h]
0x1800748f4  movd    r9d, xmm2
0x1800748f9  movaps  [rbp+0C0h+var_E0], xmm0
0x1800748fd  movups  xmm1, xmmword ptr [rax+20h]
0x180074901  movaps  [rbp+0C0h+var_D0], xmm1
0x180074905  movups  xmm0, xmmword ptr [rax+30h]
0x180074909  movaps  [rbp+0C0h+var_C0], xmm0
0x18007490d  movsd   xmm1, qword ptr [rax+40h]
0x180074912  movsd   [rbp+0C0h+var_B0], xmm1
0x180074917  test    r9d, r9d
0x18007491a  jns     short loc_180074955
0x18007491c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074923  lea     rax, WPP_GLOBAL_Control
0x18007492a  cmp     rcx, rax
0x18007492d  jz      loc_1800754A7
0x180074933  test    byte ptr [rcx+1Ch], 1
0x180074937  jz      loc_1800754A7
0x18007493d  mov     rcx, [rcx+10h]
0x180074941  lea     edx, [rdi+2Fh]
0x180074944  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x18007494b  call    WPP_SF_d
0x180074950  jmp     loc_1800754A7
0x180074955  mov     r8b, 1
0x180074958  lea     rdx, [rbp+0C0h+var_140]
0x18007495c  lea     rcx, [rbp+0C0h+Sid+4]; Sid
0x180074960  call    KerbConvertSidToString
0x180074965  mov     ebx, eax
0x180074967  test    eax, eax
0x180074969  jns     short loc_1800749A9
0x18007496b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074972  lea     rax, WPP_GLOBAL_Control
0x180074979  cmp     rcx, rax
0x18007497c  jz      loc_1800756EA
0x180074982  test    [rcx+1Ch], dil
0x180074986  jz      loc_1800756EA
0x18007498c  mov     rcx, [rcx+10h]
0x180074990  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x180074997  mov     edx, 32h ; '2'
0x18007499c  mov     r9d, ebx
0x18007499f  call    WPP_SF_d
0x1800749a4  jmp     loc_1800756EA
0x1800749a9  mov     ebx, 7FEEh
0x1800749ae  cmp     word ptr [rbp+0C0h+var_140], bx
0x1800749b2  ja      loc_18007550D
0x1800749b8  mov     rdx, [rsi+18h]
0x1800749bc  mov     r14d, 28200003h
0x1800749c2  mov     ecx, [rsi]; dwCertEncodingType
0x1800749c4  add     rdx, 30h ; '0'; pName
0x1800749c8  mov     r8d, r14d; dwStrType
0x1800749cb  mov     [rsp+1C0h+csz], r13d; csz
0x1800749d0  xor     r9d, r9d; psz
0x1800749d3  call    cs:__imp_CertNameToStrW
0x1800749d9  mov     edi, eax
0x1800749db  cmp     eax, 1
0x1800749de  ja      short loc_180074A11
0x1800749e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800749e7  lea     rax, WPP_GLOBAL_Control
0x1800749ee  cmp     rcx, rax
0x1800749f1  jz      loc_1800756E5
0x1800749f7  test    byte ptr [rcx+1Ch], 1
0x1800749fb  jz      loc_1800756E5
0x180074a01  call    cs:__imp_GetLastError
0x180074a07  mov     edx, 33h ; '3'
0x180074a0c  jmp     loc_1800756CB
0x180074a11  movzx   eax, word ptr [rbp+0C0h+var_140]
0x180074a15  sub     ebx, eax
0x180074a17  cmp     edi, ebx
0x180074a19  ja      loc_18007550D
0x180074a1f  mov     r15d, 5
0x180074a25  lea     rdx, aX509; "X509:"
0x180074a2c  mov     r8d, r15d
0x180074a2f  lea     rcx, [rbp+0C0h+var_130]
0x180074a33  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180074a38  test    al, al
0x180074a3a  jz      loc_1800756E5
0x180074a40  lea     r8d, [r15-2]
0x180074a44  lea     rdx, aI; "<I>"
0x180074a4b  lea     rcx, [rbp+0C0h+var_130]
0x180074a4f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180074a54  test    al, al
0x180074a56  jz      loc_1800756E5
0x180074a5c  mov     rdx, rdi
0x180074a5f  lea     rcx, [rsp+1C0h+psz]
0x180074a64  call    ??$make_unique@$$BY0A@G$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@0@_K@Z; utl::make_unique<ushort [0],0>(unsigned __int64)
0x180074a69  mov     rbx, [rsp+1C0h+psz]
0x180074a6e  test    rbx, rbx
0x180074a71  jz      loc_180074B78
0x180074a77  mov     rdx, [rsi+18h]
0x180074a7b  mov     r9, rbx; psz
0x180074a7e  mov     ecx, [rsi]; dwCertEncodingType
0x180074a80  add     rdx, 30h ; '0'; pName
0x180074a84  mov     r8d, r14d; dwStrType
0x180074a87  mov     [rsp+1C0h+csz], edi; csz
0x180074a8b  call    cs:__imp_CertNameToStrW
0x180074a91  mov     edi, eax
0x180074a93  cmp     eax, 1
0x180074a96  ja      short loc_180074AE2
0x180074a98  mov     rcx, cs:WPP_GLOBAL_Control
0x180074a9f  lea     rax, WPP_GLOBAL_Control
0x180074aa6  cmp     rcx, rax
0x180074aa9  jz      loc_180074BA6
0x180074aaf  test    byte ptr [rcx+1Ch], 1
0x180074ab3  jz      loc_180074BA6
0x180074ab9  call    cs:__imp_GetLastError
0x180074abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ac6  lea     edx, [r15+30h]
0x180074aca  mov     r9d, eax
0x180074acd  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x180074ad4  mov     rcx, [rcx+10h]
0x180074ad8  call    WPP_SF_d
0x180074add  jmp     loc_180074BA6
0x180074ae2  lea     r8d, [rax-1]
0x180074ae6  mov     rdx, rbx
0x180074ae9  lea     rcx, [rbp+0C0h+var_130]
0x180074aed  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180074af2  lea     rcx, [rsp+1C0h+psz]
0x180074af7  test    al, al
0x180074af9  jz      loc_180074BAB
0x180074aff  call    ??1?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ulong [0],utl::default_delete<ulong [0]>>::~unique_ptr<ulong [0],utl::default_delete<ulong [0]>>(void)
0x180074b04  mov     r8, r15
0x180074b07  lea     rdx, aSid; "<SID>"
0x180074b0e  lea     rcx, [rbp+0C0h+var_130]
0x180074b12  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180074b17  test    al, al
0x180074b19  jz      loc_1800756E5
0x180074b1f  movzx   r8d, word ptr [rbp+0C0h+var_140]
0x180074b24  lea     rcx, [rbp+0C0h+var_130]
0x180074b28  mov     rdx, qword ptr [rbp+0C0h+var_140+8]
0x180074b2c  shr     r8, 1
0x180074b2f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180074b34  test    al, al
0x180074b36  jz      loc_1800756E5
0x180074b3c  lea     rdx, [rsp+1C0h+var_180]
0x180074b41  lea     rcx, [rbp+0C0h+var_130]
0x180074b45  call    ?WStringToUnicodeString@@YAHAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAU_UNICODE_STRING@@@Z; WStringToUnicodeString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,_UNICODE_STRING *)
0x180074b4a  test    eax, eax
0x180074b4c  jz      loc_1800756E5
0x180074b52  movzx   eax, [rsp+1C0h+var_180.Length]
0x180074b57  add     di, 0Dh
0x180074b5b  add     di, word ptr [rbp+0C0h+var_140]
0x180074b5f  movzx   ecx, di
0x180074b62  add     rcx, rcx
0x180074b65  cmp     rax, rcx
0x180074b68  jbe     loc_180075681
0x180074b6e  mov     ebx, 0C00000E5h
0x180074b73  jmp     loc_1800756EA
0x180074b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b7f  lea     rax, WPP_GLOBAL_Control
0x180074b86  cmp     rcx, rax
0x180074b89  jz      short loc_180074BA6
0x180074b8b  test    byte ptr [rcx+1Ch], 1
0x180074b8f  jz      short loc_180074BA6
0x180074b91  mov     rcx, [rcx+10h]
0x180074b95  lea     r8, WPP_e63059d634053a80dba2ba0f43b284a5_Traceguids
0x180074b9c  mov     edx, 34h ; '4'
0x180074ba1  call    WPP_SF_
0x180074ba6  lea     rcx, [rsp+1C0h+psz]
0x180074bab  mov     ebx, 0C0000017h
0x180074bb0  call    ??1?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ulong [0],utl::default_delete<ulong [0]>>::~unique_ptr<ulong [0],utl::default_delete<ulong [0]>>(void)
0x180074bb5  jmp     loc_1800756EA
0x180074bba  mov     rcx, [rdx+18h]
0x180074bbe  add     rcx, 50h ; 'P'; struct _CRYPTOAPI_BLOB *
0x180074bc2  call    ?IsCertNameBlobEmpty@@YA_NAEBU_CRYPTOAPI_BLOB@@@Z; IsCertNameBlobEmpty(_CRYPTOAPI_BLOB const &)
0x180074bc7  test    al, al
0x180074bc9  jz      short loc_180074BF9
0x180074bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074bd2  lea     rax, WPP_GLOBAL_Control
0x180074bd9  cmp     rcx, rax
0x180074bdc  jz      loc_1800754A7
0x180074be2  mov     edi, 2
0x180074be7  test    [rcx+1Ch], dil
0x180074beb  jz      loc_1800754A7
0x180074bf1  lea     edx, [rdi+23h]
0x180074bf4  jmp     loc_180075497
0x180074bf9  mov     rdx, rcx; pName
0x180074bfc  mov     [rsp+1C0h+csz], r13d; csz
0x180074c01  mov     ecx, [rsi]; dwCertEncodingType
0x180074c03  mov     r14d, 28200003h
0x180074c09  mov     r8d, r14d; dwStrType
0x180074c0c  xor     r9d, r9d; psz
0x180074c0f  call    cs:__imp_CertNameToStrW
0x180074c15  mov     r15d, eax
0x180074c18  cmp     eax, 1
0x180074c1b  ja      short loc_180074C4E
0x180074c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074c24  lea     rax, WPP_GLOBAL_Control
0x180074c2b  cmp     rcx, rax
0x180074c2e  jz      loc_1800756E5
0x180074c34  test    byte ptr [rcx+1Ch], 1
0x180074c38  jz      loc_1800756E5
0x180074c3e  call    cs:__imp_GetLastError
0x180074c44  mov     edx, 26h ; '&'
0x180074c49  jmp     loc_1800756CB
0x180074c4e  cmp     r15d, 7FF3h
0x180074c55  ja      loc_18007550D
0x180074c5b  add     eax, 9
0x180074c5e  add     ax, ax
0x180074c61  mov     [rsp+1C0h+var_180.Length], ax
0x180074c66  add     ax, 2
0x180074c6a  movzx   ecx, ax; size
0x180074c6d  mov     [rsp+1C0h+var_180.MaximumLength], cx
0x180074c72  call    MIDL_user_allocate
0x180074c77  mov     [rsp+1C0h+var_180.Buffer], rax
0x180074c7c  mov     rcx, rax
0x180074c7f  test    rax, rax
0x180074c82  jz      loc_1800756E5
0x180074c88  movsd   xmm0, qword ptr cs:aX509n; "X509N:"
0x180074c90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180074c94  movsd   qword ptr [rax], xmm0
0x180074c98  mov     eax, dword ptr cs:aX509n+8; "N:"
0x180074c9e  mov     [rcx+8], eax
0x180074ca1  movzx   eax, word ptr cs:aX509n+0Ch; ""
0x180074ca8  mov     [rcx+0Ch], ax
0x180074cac  mov     rax, rbx
0x180074caf  inc     rax
0x180074cb2  cmp     [rcx+rax*2], r13w
0x180074cb7  jnz     short loc_180074CAF
0x180074cb9  lea     rdx, [rcx+rax*2]
0x180074cbd  mov     rax, 3E0053003Ch
0x180074cc7  mov     [rdx], rax
0x180074cca  inc     rbx
0x180074ccd  cmp     [rdx+rbx*2], r13w
0x180074cd2  jnz     short loc_180074CCA
0x180074cd4  mov     ecx, [rsi]; dwCertEncodingType
0x180074cd6  lea     r9, [rdx+rbx*2]; psz
0x180074cda  mov     rdx, [rsi+18h]
0x180074cde  mov     r8d, r14d; dwStrType
0x180074ce1  add     rdx, 50h ; 'P'; pName
0x180074ce5  mov     [rsp+1C0h+csz], r15d; csz
0x180074cea  call    cs:__imp_CertNameToStrW
0x180074cf0  cmp     eax, 1
0x180074cf3  ja      short loc_180074D26
0x180074cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180074cfc  lea     rax, WPP_GLOBAL_Control
0x180074d03  cmp     rcx, rax
0x180074d06  jz      loc_1800755F7
0x180074d0c  test    byte ptr [rcx+1Ch], 1
0x180074d10  jz      loc_1800755F7
0x180074d16  call    cs:__imp_GetLastError
0x180074d1c  mov     edx, 27h ; '''
0x180074d21  jmp     loc_1800755DD
0x180074d26  add     ax, 9
0x180074d2a  jmp     loc_180075679
0x180074d2f  mov     rcx, [rdx+18h]
  ... truncated ...
```
