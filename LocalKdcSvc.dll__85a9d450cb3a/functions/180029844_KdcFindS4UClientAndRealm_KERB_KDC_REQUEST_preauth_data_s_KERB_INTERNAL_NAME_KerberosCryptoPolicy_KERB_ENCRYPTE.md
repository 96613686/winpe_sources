# KdcFindS4UClientAndRealm(KERB_KDC_REQUEST_preauth_data_s *,_KERB_INTERNAL_NAME *,KerberosCryptoPolicy *,KERB_ENCRYPTED_TICKET *,_KERB_ENCRYPTION_KEY *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KDC_S4U_TICKET_INFO *,KERB_EXT_ERROR *,_KDC_S4U_TICKET_AUDIT_INFO *)

- ea: `0x180029844`
- end: `0x18002b340`
- name: `?KdcFindS4UClientAndRealm@@YAJPEAUKERB_KDC_REQUEST_preauth_data_s@@PEAU_KERB_INTERNAL_NAME@@PEAVKerberosCryptoPolicy@@PEAUKERB_ENCRYPTED_TICKET@@PEAU_KERB_ENCRYPTION_KEY@@1PEAU_UNICODE_STRING@@PEAU_KDC_S4U_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAU_KDC_S4U_TICKET_AUDIT_INFO@@@Z`
- size: `6908`
- prototype: `__int64 __fastcall(struct KERB_KDC_REQUEST_preauth_data_s *, struct _KERB_INTERNAL_NAME *, struct KerberosCryptoPolicy *, struct KERB_ENCRYPTED_TICKET *, struct _KERB_ENCRYPTION_KEY *, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME **, struct KERB_EXT_ERROR *)`
- caller_count: `1`
- callee_count: `49`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021eb4`

## callees

- `0x180002ad0`
- `0x1800038e4`
- `0x1800038f0`
- `0x180003908`
- `0x180005cc0`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180013f24`
- `0x18001e194`
- `0x18001ff94`
- `0x18002005c`
- `0x180020380`
- `0x180021250`
- `0x180029844`
- `0x180030b60`
- `0x180037b90`
- `0x18004843c`
- `0x18004e5f0`
- `0x18004ecb4`
- `0x180054598`
- `0x180055d28`
- `0x18005a060`
- `0x18005ad20`
- `0x18005c2a4`
- `0x18006349c`
- `0x180072338`
- `0x180074800`
- `0x180075a40`
- `0x180075f84`
- `0x180076848`
- `0x18007c054`
- `0x18007c274`
- `0x18007c340`
- `0x18007c4d4`
- `0x18007c5ec`
- `0x18007cad0`
- `0x18007d714`
- `0x18007dc20`
- `0x18007e35c`
- `0x18007ed58`
- `0x18007f55c`
- `0x18007f720`
- `0x18007fa48`
- `0x180080e48`
- `0x180082354`
- `0x1800831a0`
- `0x180099c58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a131`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a314`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a314`
- `CRYPT32!CertCreateCertificateContext` at `0x18002a10d`
- `CRYPT32!CertCreateCertificateContext` at `0x18002a10d`
- `ntdll!RtlEqualUnicodeString` at `0x18002ae57`
- `ntdll!RtlEqualUnicodeString` at `0x18002ae57`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002b28d`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002b28d`

## pseudocode

```c
__int64 __fastcall KdcFindS4UClientAndRealm(
        struct KERB_KDC_REQUEST_preauth_data_s *a1,
        struct _KERB_INTERNAL_NAME *a2,
        struct KerberosCryptoPolicy *a3,
        struct KERB_ENCRYPTED_TICKET *a4,
        struct _KERB_ENCRYPTION_KEY *a5,
        struct _KERB_INTERNAL_NAME *a6,
        struct _UNICODE_STRING *a7,
        struct _KERB_INTERNAL_NAME **a8,
        struct KERB_EXT_ERROR *a9)
{
  __int64 v11; // rbx
  _BYTE *v12; // r12
  unsigned int v13; // r15d
  CSecurityData *v14; // rcx
  __int64 PreAuthDataEntry; // r13
  unsigned int CertificatePublicKey; // ebx
  unsigned int v17; // eax
  struct KerberosCryptoPolicy *v18; // rbx
  int v19; // eax
  struct _KERB_INTERNAL_NAME *v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // ebx
  struct _UNICODE_STRING *v23; // rbx
  unsigned __int8 IsOurRealm; // al
  unsigned int v25; // r12d
  struct KERB_EXT_ERROR *v26; // r13
  struct _CERT_CHAIN_CONTEXT *v27; // r8
  struct PA_S4U_X509_USER *v28; // rax
  struct _KERB_INTERNAL_NAME **v29; // r15
  struct _KERB_INTERNAL_NAME *CertificateContext; // rax
  DWORD LastError; // eax
  int PrincipalNameFromCertificate; // eax
  int v33; // r8d
  int v34; // r9d
  unsigned __int8 v35; // r8
  __int64 v36; // r9
  __int64 DnsNameArrayFromCertificate; // r9
  unsigned __int8 v38; // r8
  HLOCAL v39; // rax
  unsigned int v40; // eax
  CSecurityData *v41; // rcx
  char v42; // r13
  struct _UNICODE_STRING *v43; // rbx
  struct KERB_EXT_ERROR *v44; // rbx
  CSecurityData *v45; // rcx
  __int64 j; // rcx
  int v47; // r8d
  int v48; // r9d
  struct _KERB_INTERNAL_NAME *v49; // rax
  struct KERB_EXT_ERROR *v50; // r13
  __int64 v51; // rcx
  __int16 v52; // ax
  unsigned int v53; // r12d
  unsigned int v54; // r13d
  int v55; // eax
  struct KERB_EXT_ERROR *v56; // rbx
  CSecurityData *v57; // rcx
  int v58; // edx
  int v59; // r8d
  CSecurityData *v60; // rcx
  struct KERB_EXT_ERROR *v61; // rcx
  unsigned int i; // r12d
  unsigned int v63; // ebx
  int v64; // eax
  unsigned int v65; // r13d
  CSecurityData *v66; // rcx
  unsigned int v67; // eax
  unsigned int v68; // ebx
  const CERT_CONTEXT *v69; // rcx
  unsigned int v70; // eax
  struct PA_S4U_X509_USER *v71; // r8
  struct KERB_KDC_REQUEST_preauth_data_s *v72; // r12
  unsigned int v73; // eax
  unsigned int v74; // ebx
  struct KERB_PA_DATA *v75; // rax
  unsigned int v76; // ebx
  unsigned int v77; // eax
  struct KERB_EXT_ERROR *v79; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v80[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _KERB_INTERNAL_NAME *v81; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v82[8]; // [rsp+90h] [rbp-70h] BYREF
  struct PA_S4U_X509_USER *v83; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v84[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v85[10]; // [rsp+B0h] [rbp-50h] BYREF
  char v86; // [rsp+100h] [rbp+0h]
  HLOCAL hMem; // [rsp+110h] [rbp+10h] BYREF
  int v88; // [rsp+118h] [rbp+18h] BYREF
  int v89; // [rsp+11Ch] [rbp+1Ch]
  struct KERB_EXT_ERROR *v90; // [rsp+120h] [rbp+20h]
  unsigned int v91; // [rsp+128h] [rbp+28h] BYREF
  struct KERB_PA_FOR_USER *v92; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *String2[2]; // [rsp+138h] [rbp+38h] BYREF
  struct KerberosCryptoPolicy *v94; // [rsp+148h] [rbp+48h] BYREF
  const wchar_t *v95; // [rsp+150h] [rbp+50h]
  struct _UNICODE_STRING v96; // [rsp+158h] [rbp+58h] BYREF
  struct _CERT_CHAIN_CONTEXT *v97; // [rsp+168h] [rbp+68h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v98; // [rsp+170h] [rbp+70h]
  struct _UNICODE_STRING *v99; // [rsp+178h] [rbp+78h]
  struct _KERB_INTERNAL_NAME *v100; // [rsp+180h] [rbp+80h]
  struct KERB_ENCRYPTED_TICKET *v101; // [rsp+188h] [rbp+88h]
  size_t Size[2]; // [rsp+190h] [rbp+90h]
  void *Buf1[2]; // [rsp+1A0h] [rbp+A0h]
  struct _UNICODE_STRING v104; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v105[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v106; // [rsp+1E0h] [rbp+E0h]
  int v107; // [rsp+1ECh] [rbp+ECh]
  int v108; // [rsp+201h] [rbp+101h]
  __int16 v109; // [rsp+205h] [rbp+105h]
  char v110; // [rsp+207h] [rbp+107h]
  __int16 v111; // [rsp+219h] [rbp+119h]
  char v112; // [rsp+21Bh] [rbp+11Bh]
  int v113; // [rsp+220h] [rbp+120h]
  int v114; // [rsp+224h] [rbp+124h]
  CSecurityData *v115; // [rsp+228h] [rbp+128h]
  __int64 v116; // [rsp+248h] [rbp+148h] BYREF
  __int128 v117; // [rsp+250h] [rbp+150h]
  struct _KERB_ENCRYPTION_KEY *v118; // [rsp+260h] [rbp+160h]
  __int64 v119; // [rsp+268h] [rbp+168h]
  int v120; // [rsp+270h] [rbp+170h]
  int v121; // [rsp+274h] [rbp+174h]
  int v122; // [rsp+278h] [rbp+178h]
  int v123; // [rsp+27Ch] [rbp+17Ch]
  __int64 v124; // [rsp+280h] [rbp+180h]
  __int64 v125; // [rsp+288h] [rbp+188h]
  struct _UNICODE_STRING v126; // [rsp+290h] [rbp+190h] BYREF
  struct _UNICODE_STRING v127; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v128[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v129; // [rsp+2D0h] [rbp+1D0h]
  int v130; // [rsp+2DCh] [rbp+1DCh]
  int v131; // [rsp+2F1h] [rbp+1F1h]
  __int16 v132; // [rsp+2F5h] [rbp+1F5h]
  char v133; // [rsp+2F7h] [rbp+1F7h]
  __int16 v134; // [rsp+309h] [rbp+209h]
  char v135; // [rsp+30Bh] [rbp+20Bh]
  int v136; // [rsp+310h] [rbp+210h]
  int v137; // [rsp+314h] [rbp+214h]
  __int64 v138; // [rsp+338h] [rbp+238h] BYREF
  __int128 v139; // [rsp+340h] [rbp+240h]
  _BYTE Src[16]; // [rsp+350h] [rbp+250h] BYREF

  v101 = a4;
  v94 = a3;
  v98 = a1;
  v90 = a9;
  v118 = a5;
  v100 = a6;
  v99 = a7;
  v11 = 0;
  v92 = 0;
  v83 = 0;
  v81 = 0;
  v91 = 0;
  v97 = 0;
  v88 = 0;
  v89 = 60;
  Size[0] = 0;
  HIDWORD(Size[1]) = 0;
  v82[0] = 0;
  v126 = 0;
  *(_OWORD *)String2 = 0;
  v96 = 0;
  hMem = 0;
  *(_QWORD *)&v104.Length = 0;
  v104.Buffer = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v114 = 0;
  memset_0(v105, 0, 0x88u);
  v116 = 0;
  v117 = 0;
  *(_QWORD *)&v127.Length = 0;
  v127.Buffer = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v137 = 0;
  memset_0(v128, 0, 0x88u);
  v138 = 0;
  v139 = 0;
  v80[0] = 0;
  v84[0] = 0;
  v85[0] = &v92;
  v85[1] = &v83;
  v85[2] = String2;
  v85[3] = &hMem;
  v85[4] = &v104;
  v85[5] = &v127;
  v85[6] = &v96;
  v85[7] = &v81;
  v85[8] = &v97;
  v85[9] = &v88;
  v86 = 1;
  v12 = Src;
  Buf1[0] = Src;
  v13 = 16;
  LODWORD(Size[1]) = 16;
  PreAuthDataEntry = KerbFindPreAuthDataEntry(130, a1);
  if ( !PreAuthDataEntry )
  {
    v11 = KerbFindPreAuthDataEntry(129, a1);
    if ( !v11 )
    {
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 0;
      goto LABEL_352;
    }
  }
  if ( ((_DWORD)a8[37] & 0x2000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    v86 = 0;
    lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
    CertificatePublicKey = 13;
    goto LABEL_352;
  }
  if ( v11 )
  {
    v123 = 0;
    v125 = 0;
    v119 = 0;
    v120 = 1;
    v121 = *((_DWORD *)a4 + 6);
    v122 = *((_DWORD *)a4 + 8);
    v124 = *((_QWORD *)a4 + 5);
    CertificatePublicKey = KerbUnpackData(*(_QWORD *)(v11 + 16), *(unsigned int *)(v11 + 8), 33, &v92);
    if ( CertificatePublicKey )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_135;
    }
    if ( (int)KerbHashS4UPreauth(v92) < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
LABEL_19:
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 41;
      goto LABEL_352;
    }
    v13 = Size[1];
    if ( LODWORD(Size[1]) != *((_DWORD *)v92 + 10)
      || (v12 = Buf1[0], memcmp_0(Buf1[0], *((const void **)v92 + 6), LODWORD(Size[1]))) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_19;
    }
  }
  if ( PreAuthDataEntry )
  {
    v17 = KerbUnpackData(*(_QWORD *)(PreAuthDataEntry + 16), *(unsigned int *)(PreAuthDataEntry + 8), 67, &v83);
    CertificatePublicKey = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v17);
      goto LABEL_135;
    }
    v18 = v94;
    v19 = KerbVerifyS4UPreauthData(v94, v83);
    if ( v19 < 0 )
    {
      if ( v19 == -1073741823 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        goto LABEL_19;
      }
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_41;
    }
    *((_DWORD *)a8 + 75) = *((_DWORD *)v83 + 1);
    if ( (unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v18, 0x200000011LL) )
    {
      v20 = (struct _KERB_INTERNAL_NAME *)MIDL_user_allocate(v13);
      a8[42] = v20;
      if ( !v20 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        goto LABEL_41;
      }
      *((_DWORD *)a8 + 82) = v13;
      memcpy_0(v20, v12, v13);
    }
    v14 = v83;
    if ( (*(_BYTE *)v83 & 0x10) != 0 )
    {
      v22 = KerbConvertFlagsToUlong((struct PA_S4U_X509_USER *)((char *)v83 + 48));
      if ( (v22 & 0x10000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        *((_DWORD *)a8 + 74) |= 0x8000u;
      }
      LOBYTE(v21) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAKDC>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DMSAKDC>::GetImpl'::`2'::impl,
        v21);
      if ( (v22 & 0x8000000) != 0 )
        *((_DWORD *)a8 + 74) |= 0x200000u;
    }
  }
  v23 = v99;
  IsOurRealm = CSecurityData::IsOurRealm(v14, v99);
  v25 = 0;
  v26 = v90;
  if ( IsOurRealm )
  {
    if ( (unsigned int)KdcNormalize(
                         v100,
                         v23,
                         v23,
                         0,
                         1u,
                         2u,
                         0,
                         v82,
                         &v126,
                         (struct _KDC_TICKET_INFO *)(a8 + 3),
                         v90,
                         0,
                         0,
                         0,
                         0,
                         0)
      || v82[0] )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 68;
      goto LABEL_352;
    }
    *((_DWORD *)a8 + 74) |= 3u;
  }
  KdcGetRequestorIdFromTgtPac(v101, (void **)a8 + 25, (int *)&v94);
  LOBYTE(v27) = 6;
  v28 = v83;
  if ( v83 )
  {
    if ( (*(_BYTE *)v83 & 0x40) == 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_41;
    }
    CertificatePublicKey = KerbConvertRealmToUnicodeString(a8 + 29, (char *)v83 + 24);
    if ( CertificatePublicKey )
    {
LABEL_135:
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      goto LABEL_352;
    }
    v28 = v83;
    if ( *(char *)v83 >= 0 )
    {
      LOBYTE(v27) = 6;
    }
    else
    {
      CertificatePublicKey = KerbConvertPrincipalNameToKdcName(a8 + 28, (struct PA_S4U_X509_USER *)((char *)v83 + 8));
      if ( CertificatePublicKey )
        goto LABEL_135;
      LOBYTE(v27) = 6;
      if ( *(_WORD *)a8[28] == 6 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 6);
        }
        goto LABEL_41;
      }
      v28 = v83;
    }
  }
  if ( v92 )
  {
    CertificatePublicKey = KerbConvertRealmToUnicodeString(a8 + 29, (char *)v92 + 24);
    if ( CertificatePublicKey )
      goto LABEL_135;
    v29 = a8 + 28;
    CertificatePublicKey = KerbConvertPrincipalNameToKdcName(a8 + 28, (struct KERB_PA_FOR_USER *)((char *)v92 + 8));
    if ( CertificatePublicKey )
      goto LABEL_135;
    LOBYTE(v27) = 6;
    if ( *(_WORD *)*v29 == 6 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 6);
      goto LABEL_41;
    }
    v28 = v83;
  }
  else
  {
    v29 = a8 + 28;
  }
  if ( v28 && (*(_BYTE *)v28 & 0x20) != 0 )
  {
    CertificateContext = (struct _KERB_INTERNAL_NAME *)CertCreateCertificateContext(
                                                         0x10001u,
                                                         *((const BYTE **)v28 + 5),
                                                         *((_DWORD *)v28 + 8));
    a8[38] = CertificateContext;
    if ( !CertificateContext )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
      }
      goto LABEL_41;
    }
    PrincipalNameFromCertificate = KerbGetPrincipalNameFromCertificate(
                                     (const struct _CERT_CONTEXT *)CertificateContext,
                                     KdcGlobalUseSubjectAltName,
                                     (struct _UNICODE_STRING *)String2);
    if ( PrincipalNameFromCertificate >= 0 )
    {
      if ( String2[1] && !wcsncmp_0(L"@@@", String2[1], 3u) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        DnsNameArrayFromCertificate = (unsigned int)KerbGetDnsNameArrayFromCertificate(
                                                      (const struct _CERT_CONTEXT *)a8[38],
                                                      (struct _UNICODE_STRING **)&hMem,
                                                      v84);
        if ( (int)DnsNameArrayFromCertificate < 0 || !v84[0] )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              245,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              DnsNameArrayFromCertificate,
              v84[0]);
          }
          LocalFree(hMem);
          v39 = 0;
          hMem = 0;
          goto LABEL_130;
        }
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        KerbFreeString(String2);
        if ( (int)KerbDuplicateStringEx((struct _UNICODE_STRING *)String2, (const struct _UNICODE_STRING *)hMem, v38) < 0 )
          goto LABEL_41;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          241,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          (unsigned int)PrincipalNameFromCertificate);
      v36 = (unsigned int)KerbGetDnsNameArrayFromCertificate(
                            (const struct _CERT_CONTEXT *)a8[38],
                            (struct _UNICODE_STRING **)&hMem,
                            v84);
      if ( (int)v36 < 0 || !v84[0] )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            242,
            WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
            v36,
            v84[0]);
        }
        goto LABEL_41;
      }
      if ( (int)KerbDuplicateStringEx((struct _UNICODE_STRING *)String2, (const struct _UNICODE_STRING *)hMem, v35) < 0 )
      {
LABEL_41:
        v86 = 0;
        lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
        goto LABEL_42;
      }
    }
    v39 = hMem;
LABEL_130:
    v29 = a8 + 28;
    if ( !a8[28] )
    {
      if ( v39 )
      {
        v94 = (struct KerberosCryptoPolicy *)655368;
        v95 = L"host";
        v40 = KerbBuildFullServiceKdcNameWithSid(
                (unsigned int)String2,
                (unsigned int)&v94,
                v33,
                v34,
                (__int64)(a8 + 28));
      }
      else
      {
        v40 = KerbConvertStringToKdcName(a8 + 28, (struct _UNICODE_STRING *)String2);
      }
      CertificatePublicKey = v40;
      if ( v40 )
        goto LABEL_135;
    }
    LOBYTE(v27) = 6;
    v28 = v83;
  }
  v41 = *v29;
  if ( !*v29 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    goto LABEL_41;
  }
  if ( *(_WORD *)v41 != 6
    && v28
    && *(char *)v28 < 0
    && CSecurityData::IsOurRealm(v41, (struct _UNICODE_STRING *)(a8 + 29)) )
  {
    v79 = v26;
    v42 = 0;
    CertificatePublicKey = KdcNormalize(
                             *v29,
                             0,
                             0,
                             0,
                             0x55u,
                             2u,
                             0,
                             v80,
                             &v96,
                             (struct _KDC_TICKET_INFO *)&v104,
                             v79,
                             0,
                             0,
                             4 * (*(unsigned __int16 *)v83 & 0x20u),
                             0,
                             0);
    if ( CertificatePublicKey )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          247,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          *v29);
      goto LABEL_340;
    }
    if ( v80[0] )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v96);
LABEL_155:
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 6;
      goto LABEL_352;
    }
    v25 = v106;
  }
  else
  {
    v42 = 0;
  }
  if ( !LOWORD(String2[0]) )
    goto LABEL_314;
  v43 = (struct _UNICODE_STRING *)(a8 + 29);
  if ( CSecurityData::IsOurRealm(v41, (struct _UNICODE_STRING *)(a8 + 29)) && a8[38] )
  {
    KerbFreeSid(&v81);
    CertificatePublicKey = KerbGetCertificatePublicKey((const struct _CERT_CONTEXT *)a8[38], &v81);
    if ( CertificatePublicKey )
      goto LABEL_340;
    KerbFreeString(&v96);
    v44 = v90;
    *(_QWORD *)v90 = 0;
    *((_DWORD *)v44 + 2) = 0;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v81);
    }
    if ( !(unsigned int)KdcNormalize(
                          v81,
                          0,
                          0,
                          0,
                          0x255u,
                          2u,
                          0,
                          v80,
                          &v96,
                          (struct _KDC_TICKET_INFO *)&v127,
                          v44,
                          0,
                          0,
                          0,
                          0,
                          0)
      && !v80[0] )
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            250,
            WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
            v81);
          v45 = WPP_GLOBAL_Control;
        }
        if ( v45 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v45 + 7) & 0x1000) != 0 )
          WPP_SF_Zd(
            *((_QWORD *)v45 + 2),
            251,
            (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
            (unsigned int)&v127,
            v136);
      }
      v113 |= 0x800u;
      KerbFreeSid(v29);
      CertificatePublicKey = KerbConvertStringToKdcName(v29, &v127);
      if ( CertificatePublicKey )
      {
LABEL_340:
        v86 = 0;
        lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
        goto LABEL_352;
      }
      v42 = 1;
      if ( v25 )
      {
        if ( v25 != v129 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              252,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              v25,
              v129);
          }
          FillExtendedError(-1073741198, 3, 1028, 7181, v90);
          v86 = 0;
          lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
LABEL_181:
          CertificatePublicKey = 75;
          goto LABEL_352;
        }
      }
    }
    v43 = (struct _UNICODE_STRING *)(a8 + 29);
  }
  if ( !LOWORD(String2[0]) )
    goto LABEL_314;
  if ( !CSecurityData::IsOurRealm(0, v43) || v42 )
    goto LABEL_291;
  KerbFreeSid(&v81);
  if ( hMem )
  {
    v94 = (struct KerberosCryptoPolicy *)655368;
    v95 = L"host";
    CertificatePublicKey = KerbBuildFullServiceKdcNameWithSid(
                             (unsigned int)String2,
                             (unsigned int)&v94,
                             v47,
                             v48,
                             (__int64)&v81);
    v49 = v81;
  }
  else
  {
    CertificatePublicKey = KerbConvertStringToKdcName(&v81, (struct _UNICODE_STRING *)String2);
    v49 = v81;
    if ( v81 )
    {
      j = 6;
      if ( *(_WORD *)v81 != 6 )
      {
        *(_WORD *)v81 = 10;
        v49 = v81;
      }
      goto LABEL_189;
    }
  }
  j = 6;
LABEL_189:
  if ( CertificatePublicKey )
    goto LABEL_340;
  if ( *(_WORD *)v49 == 6 )
  {
    v52 = v113;
    v50 = v90;
  }
  else
  {
    FreeTicketInfo((struct _KDC_TICKET_INFO *)&v104);
    memset_0(&v104, 0, 0xB0u);
    KerbFreeString(&v96);
    v50 = v90;
    *(_QWORD *)v90 = 0;
    *((_DWORD *)v50 + 2) = 0;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v81);
    }
    CertificatePublicKey = KdcNormalize(
                             v81,
                             0,
                             0,
                             0,
                             0x55u,
                             2u,
                             0,
                             v80,
                             &v96,
                             (struct _KDC_TICKET_INFO *)&v104,
                             v50,
                             0,
                             0,
                             0,
                             0,
                             0);
    if ( CertificatePublicKey )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          254,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          *v29);
      goto LABEL_340;
    }
    if ( v80[0] )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v96);
      goto LABEL_155;
    }
    KerbFreeSid(v29);
    CertificatePublicKey = KerbConvertStringToKdcName(v29, &v104);
    if ( CertificatePublicKey )
      goto LABEL_340;
    LODWORD(v27) = v106;
    if ( v25 && v25 != v106 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v25, v106);
      FillExtendedError(-1073741198, 3, 1028, 7287, v50);
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      goto LABEL_181;
    }
    if ( ((_DWORD)a8[37] & 0x8000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          257,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67378306,
          0);
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 12;
      goto LABEL_352;
    }
    v52 = v113 | 0x1000;
    v113 |= 0x1000u;
    if ( v25 && v25 != v106 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v51);
      v52 = v113;
      LODWORD(v27) = v106;
    }
    v25 = (unsigned int)v27;
    j = 6;
  }
  if ( (v52 & 0x800) != 0 || !a8[38] )
    goto LABEL_290;
  *(__m128i *)Size = _mm_load_si128((const __m128i *)&_xmm);
  *(__m128i *)Buf1 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v25 )
    goto LABEL_269;
  *(_QWORD *)v50 = 0;
  *((_DWORD *)v50 + 2) = 0;
  CertificatePublicKey = 6;
  v53 = 0;
  while ( 1 )
  {
    KerbFreeSid(&v81);
    v54 = *((_DWORD *)Size + v53);
    v55 = KerbBuildX509AltSecId(v54, a8[38], &v81);
    if ( v55 != -1073741275 )
    {
      if ( v55 < 0 )
      {
        if ( (KDCInfoLevel & 0x10000000) != 0 )
        {
          v61 = v90;
          *(_DWORD *)v90 = v55;
          *((_DWORD *)v61 + 1) = 67378362;
          *((_DWORD *)v61 + 2) = 2;
        }
        goto LABEL_316;
      }
      FreeTicketInfo((struct _KDC_TICKET_INFO *)&v104);
      memset_0(&v104, 0, 0xB0u);
      KerbFreeString(&v96);
      v56 = v90;
      *(_QWORD *)v90 = 0;
      *((_DWORD *)v56 + 2) = 0;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          259,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          v81);
      }
      CertificatePublicKey = KdcNormalize(
                               v81,
                               0,
                               0,
                               0,
                               0xD5u,
                               2u,
                               0,
                               v80,
                               &v96,
                               (struct _KDC_TICKET_INFO *)&v104,
                               v56,
                               0,
                               0,
                               0,
                               0,
                               0);
      if ( CertificatePublicKey )
      {
        if ( CertificatePublicKey != 6 )
          goto LABEL_340;
        goto LABEL_243;
      }
      if ( !v80[0] )
        break;
    }
LABEL_243:
    if ( ++v53 >= 8 )
    {
      if ( CertificatePublicKey )
      {
LABEL_245:
        v57 = WPP_GLOBAL_Control;
        goto LABEL_246;
      }
      goto LABEL_257;
    }
  }
  if ( ((_DWORD)a8[37] & 0x8000) != 0 && v54 - 4 <= 1 )
  {
    CertificatePublicKey = 12;
    v57 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
      goto LABEL_340;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 67378405, 12);
      goto LABEL_245;
    }
LABEL_246:
    if ( v57 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)v57 + 2), 263, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, *v29);
    goto LABEL_340;
  }
  CertificatePublicKey = KerbAddAltSecIdMapping(v54, v81, &v104, &v88);
  if ( CertificatePublicKey )
    goto LABEL_340;
  v60 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v81);
      v60 = WPP_GLOBAL_Control;
    }
    if ( v60 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v60 + 7) & 0x1000) != 0 )
    {
      WPP_SF_ZDd(*((_QWORD *)v60 + 2), v58, v59, (unsigned int)&v104, v113, v54);
LABEL_257:
      v60 = WPP_GLOBAL_Control;
    }
  }
  if ( v80[0] )
  {
    if ( v60 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v60 + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)v60 + 2), 264, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v96);
    goto LABEL_155;
  }
  KerbFreeSid(v29);
  CertificatePublicKey = KerbConvertStringToKdcName(v29, &v104);
  if ( CertificatePublicKey )
    goto LABEL_340;
  v52 = v113 | 1;
  v113 |= 1u;
LABEL_269:
  if ( (v52 & 0x800) == 0 && v115 && *((_DWORD *)v115 + 1) )
  {
    for ( i = 0; i < 8; ++i )
    {
      KerbFreeSid(&v81);
      v63 = *((_DWORD *)Size + i);
      v84[0] = v63;
      v64 = KerbBuildX509AltSecId(v63, a8[38], &v81);
      if ( v64 != -1073741275 )
      {
        if ( v64 < 0 )
          goto LABEL_316;
        v65 = 0;
        for ( j = (__int64)v115; v65 < *((_DWORD *)v115 + 1); j = (__int64)v115 )
        {
          if ( RtlEqualUnicodeString((PCUNICODE_STRING)(16LL * v65 + 8 + j), (PCUNICODE_STRING)((char *)v81 + 8), 1u)
            && (((_DWORD)a8[37] & 0x8000) == 0 || v63 - 4 > 1) )
          {
            if ( !(unsigned __int8)_KDC_TICKET_INFO::AddAltSecIdMapping(&v104, v63) )
              goto LABEL_316;
            v66 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              {
                WPP_SF__KERB_NAME_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  265,
                  WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
                  v81);
                v66 = WPP_GLOBAL_Control;
              }
              if ( v66 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v66 + 7) & 0x1000) != 0 )
                WPP_SF_Zd(
                  *((_QWORD *)v66 + 2),
                  266,
                  (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
                  (unsigned int)&v104,
                  i);
            }
            CertificatePublicKey = KerbAddAltSecIdMapping(v63, v81, &v104, &v88);
            if ( CertificatePublicKey )
              goto LABEL_340;
            v63 = v84[0];
          }
          ++v65;
        }
      }
    }
  }
LABEL_290:
  v43 = (struct _UNICODE_STRING *)(a8 + 29);
LABEL_291:
  if ( !LOWORD(String2[0]) || !CSecurityData::IsOurRealm((CSecurityData *)j, v43) )
    goto LABEL_314;
  if ( (v113 & 0x1800) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    v88 = 3;
    CertificatePublicKey = 75;
    v89 = 75;
    v86 = 0;
    lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
    goto LABEL_352;
  }
  v67 = KdcBuildClientAuthChain(
          (struct _KDC_TICKET_INFO *)&v104,
          (const struct _CERT_CONTEXT *)a8[38],
          0,
          (const struct _CERT_CHAIN_CONTEXT **)&v97);
  v68 = v67;
  if ( v67 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v67);
    v88 = 2;
    v89 = v68;
    v27 = 0;
    v97 = 0;
  }
  else
  {
    v27 = v97;
  }
  if ( KdcGlobalEnforceStrongCertificateMapping >= 1 )
  {
    v69 = (const CERT_CONTEXT *)a8[38];
    if ( v69 )
    {
      v70 = KdcSanityCheckCertMapping(v69, (struct _KDC_TICKET_INFO *)&v104, v27, (struct KERB_ERR_REASON *)&v88);
      CertificatePublicKey = v70;
      if ( v70 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v70);
        }
        goto LABEL_340;
      }
    }
  }
LABEL_314:
  if ( (int)KerbDuplicateStringEx((struct _UNICODE_STRING *)(a8 + 1), v99, (unsigned __int8)v27) >= 0
    && (int)KerbDuplicateKdcName(a8, v100) >= 0 )
  {
    a8[31] = v101;
    CertificatePublicKey = KerbDuplicateKey(a8 + 32, v118);
    if ( CertificatePublicKey )
      goto LABEL_340;
    *((_DWORD *)a8 + 74) |= 0x1010u;
    v71 = v83;
    v72 = v98;
    if ( v83 )
    {
      if ( (*(_BYTE *)v83 & 0x20) != 0 && KerbFindPreAuthDataEntry(131, v98) && (v113 & 1) != 0 )
      {
        CertificatePublicKey = KdcCheckAccountMappingDuplicates((const struct _CERT_CONTEXT *)a8[38], v90);
        if ( CertificatePublicKey )
          goto LABEL_340;
        v71 = v83;
      }
      if ( v71 && (*(_BYTE *)v71 & 0x10) != 0 )
      {
        v73 = KerbConvertFlagsToUlong((struct PA_S4U_X509_USER *)((char *)v71 + 48));
        v74 = v73;
        if ( ((_BYTE)a8[37] & 2) != 0 && (v73 & 0x40000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              270,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              *v29);
          }
          *((_DWORD *)a8 + 74) |= 0x400u;
        }
        if ( (v74 & 0x20000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              271,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              *v29);
          }
          *((_DWORD *)a8 + 74) |= 0x4000u;
        }
      }
    }
    v75 = (struct KERB_PA_DATA *)KerbFindPreAuthDataEntry(167, v72);
    if ( !v75 )
      goto LABEL_351;
    CertificatePublicKey = KerbCheckPacOptionsPreAuthData(v75, &v91);
    if ( CertificatePublicKey )
      goto LABEL_340;
    v76 = v91 & 0x80000000;
    if ( (v91 & 0x80000000) != 0 )
      LsaIModifyPerformanceCounter(15, 0, 0);
    v77 = KdcGlobalDomainClaimsLevel;
    if ( KdcGlobalDomainClaimsLevel == 2 )
    {
      if ( (unsigned int)KdcIsWin8FunctionalLevel() )
        goto LABEL_348;
      v77 = KdcGlobalDomainClaimsLevel;
    }
    if ( !v77 || !v76 )
    {
LABEL_351:
      v86 = 0;
      lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
      CertificatePublicKey = 0;
      goto LABEL_352;
    }
LABEL_348:
    *((_DWORD *)a8 + 74) |= 0x20000u;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 272, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v91);
    }
    goto LABEL_351;
  }
LABEL_316:
  v86 = 0;
  lambda_71632b6ee5adea9884f1dbfa3944b52d_::operator()(v85);
LABEL_42:
  CertificatePublicKey = 60;
LABEL_352:
  std::vector<unsigned int>::_Tidy((__int64)&v138);
  std::vector<unsigned int>::_Tidy((__int64)&v116);
  return CertificatePublicKey;
}

```

## disassembly

```asm
0x180029844  mov     [rsp-8+arg_8], rbx
0x180029849  push    rbp
0x18002984a  push    rsi
0x18002984b  push    rdi
0x18002984c  push    r12
0x18002984e  push    r13
0x180029850  push    r14
0x180029852  push    r15
0x180029854  lea     rbp, [rsp-270h]
0x18002985c  sub     rsp, 370h
0x180029863  mov     rax, cs:__security_cookie
0x18002986a  xor     rax, rsp
0x18002986d  mov     [rbp+2A0h+var_40], rax
0x180029874  mov     rdi, r9
0x180029877  mov     [rbp+2A0h+var_218], r9
0x18002987e  mov     [rbp+2A0h+var_258], r8
0x180029882  mov     rsi, rcx
0x180029885  mov     [rbp+2A0h+var_230], rcx
0x180029889  mov     rax, [rbp+2A0h+arg_40]
0x180029890  mov     [rbp+2A0h+var_280], rax
0x180029894  mov     rax, [rbp+2A0h+arg_20]
0x18002989b  mov     [rbp+2A0h+var_140], rax
0x1800298a2  mov     rax, [rbp+2A0h+arg_28]
0x1800298a9  mov     [rbp+2A0h+var_220], rax
0x1800298b0  mov     rdx, [rbp+2A0h+arg_30]
0x1800298b7  mov     [rbp+2A0h+var_228], rdx
0x1800298bb  mov     r14, [rbp+2A0h+arg_38]
0x1800298c2  xor     r12d, r12d
0x1800298c5  mov     ebx, r12d
0x1800298c8  mov     [rbp+2A0h+var_270], r12
0x1800298cc  mov     [rbp+2A0h+var_308], r12
0x1800298d0  mov     [rbp+2A0h+var_318], r12
0x1800298d4  mov     [rbp+2A0h+var_278], r12d
0x1800298d8  mov     [rbp+2A0h+var_238], r12
0x1800298dc  mov     [rbp+2A0h+var_288], r12d
0x1800298e0  mov     [rbp+2A0h+var_284], 3Ch ; '<'
0x1800298e7  mov     [rbp+2A0h+Size], r12
0x1800298ee  mov     dword ptr [rbp+2A0h+Size+0Ch], r12d
0x1800298f5  mov     [rbp+2A0h+var_310], r12b
0x1800298f9  xorps   xmm0, xmm0
0x1800298fc  movups  xmmword ptr [rbp+2A0h+var_110.Length], xmm0
0x180029903  xorps   xmm1, xmm1
0x180029906  movups  xmmword ptr [rbp+2A0h+String2], xmm1
0x18002990a  movups  xmmword ptr [rbp+2A0h+var_248.Length], xmm0
0x18002990e  mov     [rbp+2A0h+hMem], r12
0x180029912  mov     qword ptr [rbp+2A0h+var_1F0.Length], r12
0x180029919  mov     [rbp+2A0h+var_1F0.Buffer], r12
0x180029920  xor     eax, eax
0x180029922  mov     [rbp+2A0h+var_1B4], eax
0x180029928  mov     [rbp+2A0h+var_19F], eax
0x18002992e  mov     [rbp+2A0h+var_19B], ax
0x180029935  mov     [rbp+2A0h+var_199], al
0x18002993b  mov     [rbp+2A0h+var_187], ax
0x180029942  mov     [rbp+2A0h+var_185], al
0x180029948  mov     [rbp+2A0h+var_17C], eax
0x18002994e  mov     r15d, 88h
0x180029954  mov     r8d, r15d; Size
0x180029957  xor     edx, edx; Val
0x180029959  lea     rcx, [rbp+2A0h+var_1E0]; void *
0x180029960  call    memset_0
0x180029965  mov     [rbp+2A0h+var_158], r12
0x18002996c  xorps   xmm0, xmm0
0x18002996f  movdqa  [rbp+2A0h+var_150], xmm0
0x180029977  mov     qword ptr [rbp+2A0h+var_100.Length], r12
0x18002997e  mov     [rbp+2A0h+var_100.Buffer], r12
0x180029985  xor     eax, eax
0x180029987  mov     [rbp+2A0h+var_C4], eax
0x18002998d  mov     [rbp+2A0h+var_AF], eax
0x180029993  mov     [rbp+2A0h+var_AB], ax
0x18002999a  mov     [rbp+2A0h+var_A9], al
0x1800299a0  mov     [rbp+2A0h+var_97], ax
0x1800299a7  mov     [rbp+2A0h+var_95], al
0x1800299ad  mov     [rbp+2A0h+var_8C], eax
0x1800299b3  mov     r8d, r15d; Size
0x1800299b6  xor     edx, edx; Val
0x1800299b8  lea     rcx, [rbp+2A0h+var_F0]; void *
0x1800299bf  call    memset_0
0x1800299c4  mov     [rbp+2A0h+var_68], r12
0x1800299cb  xorps   xmm0, xmm0
0x1800299ce  movdqa  [rbp+2A0h+var_60], xmm0
0x1800299d6  mov     [rbp+2A0h+var_320], r12b
0x1800299da  mov     [rbp+2A0h+var_300], r12d
0x1800299de  lea     rax, [rbp+2A0h+var_270]
0x1800299e2  mov     [rbp+2A0h+var_2F0], rax
0x1800299e6  lea     rax, [rbp+2A0h+var_308]
0x1800299ea  mov     [rbp+2A0h+var_2E8], rax
0x1800299ee  lea     rax, [rbp+2A0h+String2]
0x1800299f2  mov     [rbp+2A0h+var_2E0], rax
0x1800299f6  lea     rax, [rbp+2A0h+hMem]
0x1800299fa  mov     [rbp+2A0h+var_2D8], rax
0x1800299fe  lea     rax, [rbp+2A0h+var_1F0]
0x180029a05  mov     [rbp+2A0h+var_2D0], rax
0x180029a09  lea     rax, [rbp+2A0h+var_100]
0x180029a10  mov     [rbp+2A0h+var_2C8], rax
0x180029a14  lea     rax, [rbp+2A0h+var_248]
0x180029a18  mov     [rbp+2A0h+var_2C0], rax
0x180029a1c  lea     rax, [rbp+2A0h+var_318]
0x180029a20  mov     [rbp+2A0h+var_2B8], rax
0x180029a24  lea     rax, [rbp+2A0h+var_238]
0x180029a28  mov     [rbp+2A0h+var_2B0], rax
0x180029a2c  lea     rax, [rbp+2A0h+var_288]
0x180029a30  mov     [rbp+2A0h+var_2A8], rax
0x180029a34  mov     [rbp+2A0h+var_2A0], 1
0x180029a38  lea     r12, [rbp+2A0h+Src]
0x180029a3f  mov     [rbp+2A0h+Buf1], r12
0x180029a46  lea     r15d, [rbx+10h]
0x180029a4a  mov     dword ptr [rbp+2A0h+Size+8], r15d
0x180029a51  mov     rdx, rsi
0x180029a54  lea     ecx, [r15+72h]
0x180029a58  call    KerbFindPreAuthDataEntry
0x180029a5d  mov     r13, rax
0x180029a60  test    rax, rax
0x180029a63  jnz     short loc_180029A90
0x180029a65  mov     rdx, rsi
0x180029a68  lea     ecx, [r15+71h]
0x180029a6c  call    KerbFindPreAuthDataEntry
0x180029a71  mov     rbx, rax
0x180029a74  xor     esi, esi
0x180029a76  test    rax, rax
0x180029a79  jnz     short loc_180029A92
0x180029a7b  mov     [rbp+2A0h+var_2A0], sil
0x180029a7f  lea     rcx, [rbp+2A0h+var_2F0]
0x180029a83  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029a88  nop
0x180029a89  mov     ebx, esi
0x180029a8b  jmp     loc_18002B2FB
0x180029a90  xor     esi, esi
0x180029a92  test    dword ptr [r14+128h], 2000h
0x180029a9d  jz      short loc_180029AE6
0x180029a9f  lea     rdi, WPP_GLOBAL_Control
0x180029aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180029aad  cmp     rcx, rdi
0x180029ab0  jz      short loc_180029ACE
0x180029ab2  test    byte ptr [rcx+1Ch], 1
0x180029ab6  jz      short loc_180029ACE
0x180029ab8  mov     edx, 0E3h
0x180029abd  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029ac4  mov     rcx, [rcx+10h]
0x180029ac8  call    WPP_SF_
0x180029acd  nop
0x180029ace  mov     [rbp+2A0h+var_2A0], 0
0x180029ad2  lea     rcx, [rbp+2A0h+var_2F0]
0x180029ad6  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029adb  nop
0x180029adc  mov     ebx, 0Dh
0x180029ae1  jmp     loc_18002B2FB
0x180029ae6  test    rbx, rbx
0x180029ae9  jz      loc_180029C5F
0x180029aef  mov     [rbp+2A0h+var_124], esi
0x180029af5  mov     [rbp+2A0h+var_118], 0
0x180029b00  mov     [rbp+2A0h+var_138], rsi
0x180029b07  mov     [rbp+2A0h+var_130], 1
0x180029b11  mov     eax, [rdi+18h]
0x180029b14  mov     [rbp+2A0h+var_12C], eax
0x180029b1a  mov     eax, [rdi+20h]
0x180029b1d  mov     [rbp+2A0h+var_128], eax
0x180029b23  mov     rax, [rdi+28h]
0x180029b27  mov     [rbp+2A0h+var_120], rax
0x180029b2e  lea     r9, [rbp+2A0h+var_270]
0x180029b32  mov     r8d, 21h ; '!'
0x180029b38  mov     edx, [rbx+8]
0x180029b3b  mov     rcx, [rbx+10h]
0x180029b3f  call    KerbUnpackData
0x180029b44  mov     ebx, eax
0x180029b46  test    eax, eax
0x180029b48  jz      short loc_180029B8D
0x180029b4a  lea     rdi, WPP_GLOBAL_Control
0x180029b51  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b58  cmp     rcx, rdi
0x180029b5b  jz      short loc_180029B7A
0x180029b5d  test    byte ptr [rcx+1Ch], 1
0x180029b61  jz      short loc_180029B7A
0x180029b63  mov     edx, 0E4h
0x180029b68  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029b6f  mov     rcx, [rcx+10h]
0x180029b73  call    WPP_SF_
0x180029b78  xor     esi, esi
0x180029b7a  mov     [rbp+2A0h+var_2A0], sil
0x180029b7e  lea     rcx, [rbp+2A0h+var_2F0]
0x180029b82  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029b87  nop
0x180029b88  jmp     loc_18002B2FB
0x180029b8d  lea     r9, [rbp+2A0h+Size]
0x180029b94  mov     rcx, [rbp+2A0h+var_270]; struct KERB_PA_FOR_USER *
0x180029b98  mov     r8d, [rcx+20h]
0x180029b9c  lea     rdx, [rbp+2A0h+var_138]
0x180029ba3  call    KerbHashS4UPreauth
0x180029ba8  test    eax, eax
0x180029baa  jns     short loc_180029BF4
0x180029bac  lea     rdi, WPP_GLOBAL_Control
0x180029bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bba  cmp     rcx, rdi
0x180029bbd  jz      short loc_180029BDC
0x180029bbf  test    byte ptr [rcx+1Ch], 1
0x180029bc3  jz      short loc_180029BDC
0x180029bc5  mov     edx, 0E5h
0x180029bca  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029bd1  mov     rcx, [rcx+10h]
0x180029bd5  call    WPP_SF_
0x180029bda  xor     esi, esi
0x180029bdc  mov     [rbp+2A0h+var_2A0], sil
0x180029be0  lea     rcx, [rbp+2A0h+var_2F0]
0x180029be4  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029be9  nop
0x180029bea  mov     ebx, 29h ; ')'
0x180029bef  jmp     loc_18002B2FB
0x180029bf4  mov     r15d, dword ptr [rbp+2A0h+Size+8]
0x180029bfb  mov     rdx, [rbp+2A0h+var_270]
0x180029bff  cmp     r15d, [rdx+28h]
0x180029c03  jnz     short loc_180029C1F
0x180029c05  mov     r8d, r15d; Size
0x180029c08  mov     rdx, [rdx+30h]; Buf2
0x180029c0c  mov     r12, [rbp+2A0h+Buf1]
0x180029c13  mov     rcx, r12; Buf1
0x180029c16  call    memcmp_0
0x180029c1b  test    eax, eax
0x180029c1d  jz      short loc_180029C5F
0x180029c1f  lea     rdi, WPP_GLOBAL_Control
0x180029c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c2d  cmp     rcx, rdi
0x180029c30  jz      short loc_180029C4F
0x180029c32  test    byte ptr [rcx+1Ch], 1
0x180029c36  jz      short loc_180029C4F
0x180029c38  mov     edx, 0E6h
0x180029c3d  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029c44  mov     rcx, [rcx+10h]
0x180029c48  call    WPP_SF_
0x180029c4d  xor     esi, esi
0x180029c4f  mov     [rbp+2A0h+var_2A0], sil
0x180029c53  lea     rcx, [rbp+2A0h+var_2F0]
0x180029c57  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029c5c  nop
0x180029c5d  jmp     short loc_180029BEA
0x180029c5f  lea     rdi, WPP_GLOBAL_Control
0x180029c66  lea     rsi, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029c6d  test    r13, r13
0x180029c70  jz      loc_180029E4E
0x180029c76  lea     r9, [rbp+2A0h+var_308]
0x180029c7a  mov     r8d, 43h ; 'C'
0x180029c80  mov     edx, [r13+8]
0x180029c84  mov     rcx, [r13+10h]
0x180029c88  call    KerbUnpackData
0x180029c8d  mov     ebx, eax
0x180029c8f  xor     r13d, r13d
0x180029c92  test    eax, eax
0x180029c94  jz      short loc_180029CD0
0x180029c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c9d  cmp     rcx, rdi
0x180029ca0  jz      short loc_180029CBD
0x180029ca2  test    byte ptr [rcx+1Ch], 1
0x180029ca6  jz      short loc_180029CBD
0x180029ca8  mov     edx, 0E7h
0x180029cad  mov     r9d, eax
0x180029cb0  mov     r8, rsi
0x180029cb3  mov     rcx, [rcx+10h]
0x180029cb7  call    WPP_SF_d
0x180029cbc  nop
0x180029cbd  mov     [rbp+2A0h+var_2A0], r13b
0x180029cc1  lea     rcx, [rbp+2A0h+var_2F0]
0x180029cc5  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029cca  nop
0x180029ccb  jmp     loc_18002B2FB
0x180029cd0  mov     rdx, [rbp+2A0h+var_308]; struct PA_S4U_X509_USER *
0x180029cd4  mov     rbx, [rbp+2A0h+var_258]
0x180029cd8  mov     rcx, rbx; struct KerberosCryptoPolicy *
0x180029cdb  call    ?KerbVerifyS4UPreauthData@@YAJPEAVKerberosCryptoPolicy@@PEAUPA_S4U_X509_USER@@@Z; KerbVerifyS4UPreauthData(KerberosCryptoPolicy *,PA_S4U_X509_USER *)
0x180029ce0  test    eax, eax
0x180029ce2  jns     short loc_180029D5E
0x180029ce4  cmp     eax, 0C0000001h
0x180029ce9  jnz     short loc_180029D22
0x180029ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cf2  cmp     rcx, rdi
0x180029cf5  jz      short loc_180029D0F
0x180029cf7  test    byte ptr [rcx+1Ch], 1
0x180029cfb  jz      short loc_180029D0F
0x180029cfd  mov     edx, 0E8h
0x180029d02  mov     r8, rsi
0x180029d05  mov     rcx, [rcx+10h]
0x180029d09  call    WPP_SF_
0x180029d0e  nop
0x180029d0f  mov     [rbp+2A0h+var_2A0], r13b
0x180029d13  lea     rcx, [rbp+2A0h+var_2F0]
0x180029d17  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029d1c  nop
0x180029d1d  jmp     loc_180029BEA
0x180029d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d29  cmp     rcx, rdi
0x180029d2c  jz      short loc_180029D46
0x180029d2e  test    byte ptr [rcx+1Ch], 1
0x180029d32  jz      short loc_180029D46
0x180029d34  mov     edx, 0E9h
0x180029d39  mov     r8, rsi
0x180029d3c  mov     rcx, [rcx+10h]
0x180029d40  call    WPP_SF_
0x180029d45  nop
0x180029d46  mov     [rbp+2A0h+var_2A0], r13b
0x180029d4a  lea     rcx, [rbp+2A0h+var_2F0]
0x180029d4e  call    _lambda_71632b6ee5adea9884f1dbfa3944b52d___operator__
0x180029d53  nop
0x180029d54  mov     ebx, 3Ch ; '<'
  ... truncated ...
```
