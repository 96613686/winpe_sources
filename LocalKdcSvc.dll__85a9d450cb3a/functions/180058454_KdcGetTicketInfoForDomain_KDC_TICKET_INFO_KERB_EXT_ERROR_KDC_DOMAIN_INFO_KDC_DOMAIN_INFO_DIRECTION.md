# KdcGetTicketInfoForDomain(_KDC_TICKET_INFO *,KERB_EXT_ERROR *,_KDC_DOMAIN_INFO *,KDC_DOMAIN_INFO_DIRECTION)

- ea: `0x180058454`
- end: `0x180058f5c`
- name: `?KdcGetTicketInfoForDomain@@YAJPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAU_KDC_DOMAIN_INFO@@W4KDC_DOMAIN_INFO_DIRECTION@@@Z`
- size: `2824`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057fb4`

## callees

- `0x180003908`
- `0x18000508c`
- `0x180005c74`
- `0x18000ab40`
- `0x18000e9a4`
- `0x180020fa8`
- `0x1800210a8`
- `0x180057354`
- `0x180057df0`
- `0x180058454`
- `0x18005932c`
- `0x180059364`
- `0x1800597cc`
- `0x18005998c`
- `0x180059bcc`
- `0x18005a060`
- `0x18005a090`
- `0x18005c2a4`
- `0x18007aed4`
- `0x18007c4d4`
- `0x18007dc20`
- `0x1800811b4`
- `0x180081bec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800586b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800586b9`
- `ntdll!RtlEqualUnicodeString` at `0x18005884c`
- `ntdll!RtlEqualUnicodeString` at `0x180058a81`
- `ntdll!RtlEqualUnicodeString` at `0x18005884c`
- `ntdll!RtlEqualUnicodeString` at `0x180058a81`
- `ntdll!RtlLengthSid` at `0x180058c5c`
- `ntdll!RtlLengthSid` at `0x180058c5c`
- `ntdll!RtlCopySid` at `0x180058c81`
- `ntdll!RtlCopySid` at `0x180058c81`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180058562`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180058594`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180058562`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180058594`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058525`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18005868e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x1800586a5`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18005873d`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058750`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058cca`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058cdd`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058d85`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058d98`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058e1b`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058e2e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058ebb`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058ed0`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058525`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18005868e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x1800586a5`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18005873d`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058750`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058cca`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058cdd`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058d85`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058d98`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058e1b`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058e2e`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058ebb`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180058ed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall KdcGetTicketInfoForDomain(__int64 a1, int *a2, __int64 a3, int a4)
{
  __int64 *v6; // rbx
  unsigned int v7; // esi
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r14d
  int v12; // edx
  int v13; // r8d
  int v14; // r14d
  struct _LSAPR_AUTH_INFORMATION *v15; // r12
  struct _LSAPR_AUTH_INFORMATION *v16; // rdx
  unsigned int v17; // ecx
  unsigned int *v18; // r11
  struct _LSAPR_AUTH_INFORMATION *v19; // rdx
  struct _LSAPR_AUTH_INFORMATION *v20; // rdx
  unsigned int v21; // ecx
  struct _LSAPR_AUTH_INFORMATION *v22; // rdx
  unsigned int v23; // ecx
  int v24; // r8d
  __int64 v25; // r10
  void **v26; // rax
  const struct _UNICODE_STRING *v27; // r12
  int v28; // eax
  unsigned __int8 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r12
  struct _UNICODE_STRING *v33; // r12
  unsigned __int8 v34; // r8
  int v35; // r12d
  void **v36; // r12
  PCUNICODE_STRING v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned __int8 v43; // r8
  int v44; // eax
  void **v45; // rax
  struct _LSAPR_AUTH_INFORMATION *v46; // rcx
  int v47; // ebx
  int v48; // edx
  int v49; // eax
  unsigned __int8 v50; // r8
  int v51; // eax
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  void *v55; // rcx
  ULONG v56; // ebx
  void *v57; // rax
  unsigned int v58; // ebx
  unsigned int v60; // ebx
  int v61; // [rsp+48h] [rbp-C0h]
  __int64 v62; // [rsp+78h] [rbp-90h] BYREF
  unsigned int *v63; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v64; // [rsp+88h] [rbp-80h] BYREF
  void **v65; // [rsp+90h] [rbp-78h]
  PCUNICODE_STRING String2; // [rsp+98h] [rbp-70h]
  unsigned int v67; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v68; // [rsp+A4h] [rbp-64h]
  struct _LSAPR_AUTH_INFORMATION *v69; // [rsp+A8h] [rbp-60h]
  __int64 v70; // [rsp+B0h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+B8h] [rbp-50h] BYREF
  struct _UNICODE_STRING *v72; // [rsp+C8h] [rbp-40h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D0h] [rbp-38h] BYREF
  struct _UNICODE_STRING v74; // [rsp+D8h] [rbp-30h] BYREF
  struct _UNICODE_STRING v75; // [rsp+E8h] [rbp-20h] BYREF
  union _LARGE_INTEGER v76; // [rsp+F8h] [rbp-10h]
  unsigned int v77; // [rsp+100h] [rbp-8h]
  int v78; // [rsp+104h] [rbp-4h]
  int v79; // [rsp+10Ch] [rbp+4h]
  int v80; // [rsp+110h] [rbp+8h]
  int v81; // [rsp+114h] [rbp+Ch]
  struct _KERB_STORED_CREDENTIAL *v82; // [rsp+118h] [rbp+10h] BYREF
  struct _KERB_STORED_CREDENTIAL *v83; // [rsp+120h] [rbp+18h] BYREF
  int v84; // [rsp+129h] [rbp+21h]
  __int16 v85; // [rsp+12Dh] [rbp+25h]
  char v86; // [rsp+12Fh] [rbp+27h]
  void *v87; // [rsp+130h] [rbp+28h]
  unsigned int v88; // [rsp+138h] [rbp+30h]
  __int16 v89; // [rsp+141h] [rbp+39h]
  char v90; // [rsp+143h] [rbp+3Bh]
  int v91; // [rsp+144h] [rbp+3Ch]
  int v92; // [rsp+14Ch] [rbp+44h]
  __int64 v93; // [rsp+170h] [rbp+68h] BYREF
  __int128 v94; // [rsp+178h] [rbp+70h]
  __int64 *v95; // [rsp+188h] [rbp+80h]
  unsigned int **v96; // [rsp+190h] [rbp+88h]
  struct _UNICODE_STRING *v97; // [rsp+198h] [rbp+90h]
  char v98; // [rsp+1A0h] [rbp+98h]
  _BYTE v99[60]; // [rsp+1A8h] [rbp+A0h] BYREF
  int v100; // [rsp+1E4h] [rbp+DCh]
  int v101; // [rsp+1F9h] [rbp+F1h]
  __int16 v102; // [rsp+1FDh] [rbp+F5h]
  char v103; // [rsp+1FFh] [rbp+F7h]
  __int16 v104; // [rsp+211h] [rbp+109h]
  char v105; // [rsp+213h] [rbp+10Bh]
  int v106; // [rsp+21Ch] [rbp+114h]
  __int128 v107; // [rsp+240h] [rbp+138h] BYREF
  __int64 v108; // [rsp+250h] [rbp+148h]

  v62 = 0;
  v63 = 0;
  v81 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v89 = 0;
  v90 = 0;
  v92 = 0;
  memset_0(&v74, 0, 0x98u);
  v93 = 0;
  v94 = 0;
  String1 = 0;
  v67 = 0;
  SystemTimeAsFileTime = 0;
  v95 = &v62;
  v96 = &v63;
  v97 = &v74;
  v98 = 1;
  KerberosCryptoPolicy::Create(&v64);
  v6 = v64;
  if ( !v64 )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
    if ( v62 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
    if ( !v63 )
      goto LABEL_124;
    goto LABEL_123;
  }
  v70 = a3 + 16;
  v7 = 7;
  v8 = LsarQueryTrustedDomainInfoByName(GlobalPolicyHandle, a3 + 16, 7, &v62);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -1073741772 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v10, a3 + 16);
      v60 = 7;
      goto LABEL_131;
    }
    if ( v8 == -1073741058 )
    {
      v60 = 29;
LABEL_131:
      if ( (KDCInfoLevel & 0x10000000) != 0 )
      {
        *a2 = v11;
        a2[1] = 67831070;
        a2[2] = 2;
      }
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
      if ( v62 )
        LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
      if ( v63 )
        LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)&v74);
      std::vector<unsigned int>::_Tidy((__int64)&v93);
      return v60;
    }
LABEL_127:
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_ZDSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a3 + 16, v11);
    v60 = 60;
    goto LABEL_131;
  }
  if ( !v62 )
  {
    v11 = -1073741823;
    goto LABEL_127;
  }
  v14 = LsarQueryTrustedDomainInfoByName(GlobalPolicyHandle, a3 + 16, 13, &v63);
  if ( v14 < 0 )
    goto LABEL_115;
  if ( !v63 )
  {
    v14 = -1073741823;
LABEL_115:
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v14, a3 + 16);
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      *a2 = v14;
      a2[1] = 67831092;
      a2[2] = 2;
    }
    goto LABEL_120;
  }
  if ( a4 == 2 )
  {
    v15 = KdcPickAuthInfo(*(_DWORD *)v62, *(struct _LSAPR_AUTH_INFORMATION **)(v62 + 8));
    v68 = KdcPickAuthInfoKeyVersion(v17, v16);
    v18 = (unsigned int *)v62;
    v19 = *(struct _LSAPR_AUTH_INFORMATION **)(v62 + 16);
  }
  else
  {
    v15 = KdcPickAuthInfo(*(_DWORD *)(v62 + 24), *(struct _LSAPR_AUTH_INFORMATION **)(v62 + 32));
    v68 = KdcPickAuthInfoKeyVersion(v21, v20);
    v19 = *(struct _LSAPR_AUTH_INFORMATION **)(v62 + 40);
    v18 = (unsigned int *)(v62 + 24);
  }
  v65 = (void **)KdcPickAuthInfo(*v18, v19);
  LODWORD(v72) = KdcPickAuthInfoKeyVersion(v23, v22);
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_ZSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v24, v70);
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      *a2 = -1073741428;
      a2[1] = 67831150;
      a2[2] = 2;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
    if ( v62 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
    if ( v63 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
    goto LABEL_125;
  }
  if ( v25 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)v15 < 600000000LL * KdcGlobalDomainPasswordReplSkew )
    {
      v69 = v15;
      v15 = (struct _LSAPR_AUTH_INFORMATION *)v65;
      v68 = (unsigned int)v72;
      goto LABEL_29;
    }
    v26 = v65;
  }
  else
  {
    v26 = 0;
  }
  v69 = (struct _LSAPR_AUTH_INFORMATION *)v26;
LABEL_29:
  String1.MaximumLength = *((_WORD *)v15 + 6);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)*((_QWORD *)v15 + 2);
  if ( !(unsigned __int8)KerberosCryptoPolicy::SetPartnerAttributes(v6, *v63, 4) )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
    if ( v62 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
    if ( v63 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
    v7 = 14;
    goto LABEL_125;
  }
  if ( *((_DWORD *)v15 + 2) == 1 )
  {
    v27 = (const struct _UNICODE_STRING *)(a3 + 16);
    v28 = KdcBuildPasswordList(
            &String1,
            a3 + 16,
            &DomainName2,
            KdcGlobalIterationCount,
            2,
            v6,
            0,
            0,
            0,
            2,
            a4,
            &v82,
            &v67);
    if ( v28 < 0 )
    {
      if ( (KDCInfoLevel & 0x10000000) == 0 )
        goto LABEL_120;
      a2[1] = 67831214;
      goto LABEL_39;
    }
  }
  else
  {
    v30 = 104;
    if ( a4 != 1 )
      v30 = 136;
    String2 = (PCUNICODE_STRING)(a3 + v30);
    v31 = 96;
    if ( a4 != 1 )
      v31 = 128;
    v65 = (void **)(a3 + v31);
    v32 = 112;
    if ( a4 != 1 )
      v32 = 144;
    v33 = (struct _UNICODE_STRING *)(a3 + v32);
    v72 = v33;
    wil::EnterCriticalSection(&v70, a3 + 224);
    if ( RtlEqualUnicodeString(&String1, v33, 0) )
      goto LABEL_54;
    memset_0(v33->Buffer, 0, v33->Length);
    KerbFreeString(v33);
    v35 = KerbDuplicateStringEx(v33, &String1, v34);
    if ( v35 < 0 )
      goto LABEL_51;
    v36 = v65;
    if ( *v65 )
    {
      MIDL_user_free(*v65);
      *v36 = 0;
    }
    v37 = String2;
    *(_DWORD *)&String2->Length = 0;
    v35 = KdcBuildKeysForTrusts(&String1, a3, v6, &DomainName2, a4, v36, v37);
    if ( v35 >= 0 )
    {
LABEL_54:
      v35 = KdcExtractKeysForTrusts(*(_DWORD *)&String2->Length, (unsigned __int8 *)*v65, &v82, &v67);
    }
    else
    {
LABEL_51:
      memset_0(v72->Buffer, 0, v72->Length);
      KerbFreeString(v72);
      if ( *v65 )
      {
        MIDL_user_free(*v65);
        *v65 = 0;
      }
      *(_DWORD *)&String2->Length = 0;
    }
    if ( v35 < 0 )
    {
      if ( (KDCInfoLevel & 0x10000000) != 0 )
      {
        *a2 = v35;
        a2[1] = 67831291;
        a2[2] = 2;
      }
      goto LABEL_58;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
      &v70,
      v38,
      v39);
    v27 = (const struct _UNICODE_STRING *)(a3 + 16);
  }
  if ( !v69 )
    goto LABEL_86;
  String1.MaximumLength = *((_WORD *)v69 + 6);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)*((_QWORD *)v69 + 2);
  if ( *((_DWORD *)v69 + 2) != 1 )
  {
    v40 = 168;
    if ( a4 != 1 )
      v40 = 200;
    v69 = (struct _LSAPR_AUTH_INFORMATION *)(a3 + v40);
    v41 = 160;
    if ( a4 != 1 )
      v41 = 192;
    v65 = (void **)(a3 + v41);
    v42 = 176;
    if ( a4 != 1 )
      v42 = 208;
    String2 = (PCUNICODE_STRING)(a3 + v42);
    wil::EnterCriticalSection(&v70, a3 + 224);
    if ( RtlEqualUnicodeString(&String1, String2, 0) )
      goto LABEL_76;
    memset_0(String2->Buffer, 0, String2->Length);
    KerbFreeString(String2);
    v44 = KerbDuplicateStringEx((struct _UNICODE_STRING *)String2, &String1, v43);
    if ( v44 < 0 )
    {
      v47 = v44;
    }
    else
    {
      v45 = v65;
      if ( *v65 )
      {
        MIDL_user_free(*v65);
        v45 = v65;
        *v65 = 0;
      }
      v46 = v69;
      *(_DWORD *)v69 = 0;
      v47 = KdcBuildKeysForTrusts(&String1, a3, v6, &DomainName2, a4, v45, v46);
      if ( v47 >= 0 )
      {
LABEL_76:
        v47 = KdcExtractKeysForTrusts(*(_DWORD *)v69, (unsigned __int8 *)*v65, &v83, &v67);
LABEL_77:
        if ( v47 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
            &v70,
            v38,
            v39);
          goto LABEL_86;
        }
        if ( (KDCInfoLevel & 0x10000000) != 0 )
        {
          *a2 = v47;
          a2[1] = 67831406;
          a2[2] = 2;
        }
LABEL_58:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
          &v70,
          v38,
          v39);
        goto LABEL_120;
      }
    }
    memset_0(String2->Buffer, 0, String2->Length);
    KerbFreeString(String2);
    if ( *v65 )
    {
      MIDL_user_free(*v65);
      *v65 = 0;
    }
    *(_DWORD *)v69 = 0;
    goto LABEL_77;
  }
  LOBYTE(v61) = 0;
  v28 = KdcBuildPasswordList(&String1, v27, &DomainName2, KdcGlobalIterationCount, 2, v6, 0, 0, v61, 2, a4, &v83, &v67);
  if ( v28 < 0 )
  {
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      a2[1] = 67831327;
LABEL_39:
      *a2 = v28;
      a2[2] = 2;
    }
LABEL_120:
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
    if ( v62 )
      LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
    if ( !v63 )
      goto LABEL_124;
LABEL_123:
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
LABEL_124:
    v7 = 60;
LABEL_125:
    FreeTicketInfo((struct _KDC_TICKET_INFO *)&v74);
    std::vector<unsigned int>::_Tidy((__int64)&v93);
    return v7;
  }
LABEL_86:
  if ( (int)KerbDuplicateStringEx(&v74, v27, v29) < 0 )
    goto LABEL_120;
  v76 = tsInfinity;
  v78 = 64;
  v91 = *v63;
  v48 = *(_DWORD *)(a3 + 60);
  v49 = 383;
  v50 = 127;
  if ( *(_DWORD *)(a3 + 64) == 3 )
  {
    if ( (v48 & 1) == 0 )
      v49 = 1407;
    v77 = v49;
    v51 = (!(v48 & 1) << 10) + 383;
    v52 = !(v48 & 1) << 10;
  }
  else
  {
    v53 = v48 & 0x28;
    if ( (v48 & 0x28) != 0 )
      v49 = 1407;
    v77 = v49;
    v88 = v68;
    v50 = 0;
    v51 = v53 != 0 ? 1407 : 383;
    v52 = v53 != 0 ? 0x400 : 0;
  }
  v54 = v52 + 383;
  if ( (v48 & 0x204) != 0 )
  {
    v54 = v51;
  }
  else if ( (v48 & 0x820) != 0 )
  {
    goto LABEL_99;
  }
  v77 = v54 & 0xFFFFFEFF;
LABEL_99:
  v55 = *(void **)(a3 + 88);
  if ( v55 )
  {
    v56 = RtlLengthSid(v55);
    v57 = MIDL_user_allocate(v56);
    v87 = v57;
    if ( !v57 || RtlCopySid(v56, v57, *(PSID *)(a3 + 88)) < 0 )
      goto LABEL_120;
  }
  v80 = *(_DWORD *)(a3 + 60);
  v79 = *(_DWORD *)(a3 + 64);
  if ( (v80 & 8) != 0 )
  {
    v58 = KerbDuplicateStringEx(&v75, v27, v50);
    if ( v58 )
    {
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
      if ( v62 )
        LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
      if ( v63 )
        LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
      v7 = v58;
      goto LABEL_125;
    }
  }
  _KDC_TICKET_INFO::operator=(a1, &v74);
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  memset_0(v99, 0, 0x98u);
  v107 = 0;
  v108 = 0;
  _KDC_TICKET_INFO::operator=(&v74, v99);
  std::vector<unsigned int>::_Tidy((__int64)&v107);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v64);
  if ( v62 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(7);
  if ( v63 )
    LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(13);
  FreeTicketInfo((struct _KDC_TICKET_INFO *)&v74);
  std::vector<unsigned int>::_Tidy((__int64)&v93);
  return 0;
}

```

## disassembly

```asm
0x180058454  mov     rax, rsp
0x180058457  mov     [rax+10h], rbx
0x18005845b  mov     [rax+20h], r9d
0x18005845f  mov     [rax+8], rcx
0x180058463  push    rbp
0x180058464  push    rsi
0x180058465  push    rdi
0x180058466  push    r12
0x180058468  push    r13
0x18005846a  push    r14
0x18005846c  push    r15
0x18005846e  lea     rbp, [rax-188h]
0x180058475  sub     rsp, 250h
0x18005847c  mov     r13, r8
0x18005847f  mov     rdi, rdx
0x180058482  xor     r15d, r15d
0x180058485  mov     [rsp+280h+var_210], r15
0x18005848a  mov     [rsp+280h+var_208], r15
0x18005848f  xor     eax, eax
0x180058491  mov     [rbp+180h+var_174], eax
0x180058494  mov     [rbp+180h+var_15F], eax
0x180058497  mov     [rbp+180h+var_15B], ax
0x18005849b  mov     [rbp+180h+var_159], al
0x18005849e  mov     [rbp+180h+var_147], ax
0x1800584a2  mov     [rbp+180h+var_145], al
0x1800584a5  mov     [rbp+180h+var_13C], eax
0x1800584a8  xor     edx, edx; Val
0x1800584aa  mov     r8d, 98h; Size
0x1800584b0  lea     rcx, [rbp+180h+var_1B0]; void *
0x1800584b4  call    memset_0
0x1800584b9  mov     [rbp+180h+var_118], r15
0x1800584bd  xorps   xmm0, xmm0
0x1800584c0  movdqa  [rbp+180h+var_110], xmm0
0x1800584c5  movups  xmmword ptr [rbp+180h+String1.Length], xmm0
0x1800584c9  mov     [rbp+180h+var_1E8], r15d
0x1800584cd  mov     qword ptr [rbp+180h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800584d1  lea     rax, [rsp+280h+var_210]
0x1800584d6  mov     [rbp+180h+var_100], rax
0x1800584dd  lea     rax, [rsp+280h+var_208]
0x1800584e2  mov     [rbp+180h+var_F8], rax
0x1800584e9  lea     rax, [rbp+180h+var_1B0]
0x1800584ed  mov     [rbp+180h+var_F0], rax
0x1800584f4  mov     [rbp+180h+var_E8], 1
0x1800584fb  lea     rcx, [rbp+180h+var_200]
0x1800584ff  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x180058504  nop
0x180058505  mov     rbx, [rbp+180h+var_200]
0x180058509  test    rbx, rbx
0x18005850c  jnz     short loc_180058543
0x18005850e  lea     rcx, [rbp+180h+var_200]
0x180058512  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180058517  nop
0x180058518  mov     rdx, [rsp+280h+var_210]
0x18005851d  test    rdx, rdx
0x180058520  jz      short loc_18005852B
0x180058522  lea     ecx, [rbx+7]
0x180058525  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x18005852b  mov     rdx, [rsp+280h+var_208]
0x180058530  test    rdx, rdx
0x180058533  jz      loc_180058E34
0x180058539  mov     ecx, 0Dh
0x18005853e  jmp     loc_180058E2E
0x180058543  lea     r12, [r13+10h]
0x180058547  mov     [rbp+180h+var_1D8], r12
0x18005854b  lea     r9, [rsp+280h+var_210]
0x180058550  mov     esi, 7
0x180058555  mov     r8d, esi
0x180058558  mov     rdx, r12
0x18005855b  mov     rcx, cs:?GlobalPolicyHandle@@3PEAXEA; void * GlobalPolicyHandle
0x180058562  call    cs:__imp_LsarQueryTrustedDomainInfoByName
0x180058568  mov     r14d, eax
0x18005856b  test    eax, eax
0x18005856d  js      loc_180058F06
0x180058573  cmp     [rsp+280h+var_210], r15
0x180058578  jz      loc_180058E53
0x18005857e  lea     r9, [rsp+280h+var_208]
0x180058583  lea     r15d, [rsi+6]
0x180058587  mov     r8d, r15d
0x18005858a  mov     rdx, r12
0x18005858d  mov     rcx, cs:?GlobalPolicyHandle@@3PEAXEA; void * GlobalPolicyHandle
0x180058594  call    cs:__imp_LsarQueryTrustedDomainInfoByName
0x18005859a  mov     r14d, eax
0x18005859d  test    eax, eax
0x18005859f  js      loc_180058DBE
0x1800585a5  cmp     [rsp+280h+var_208], 0
0x1800585ab  jz      loc_180058DB8
0x1800585b1  lea     r14d, [rsi-5]
0x1800585b5  mov     rax, [rsp+280h+var_210]
0x1800585ba  cmp     [rbp+180h+arg_18], r14d
0x1800585c1  jnz     short loc_1800585E4
0x1800585c3  mov     rdx, [rax+8]; struct _LSAPR_AUTH_INFORMATION *
0x1800585c7  mov     ecx, [rax]; unsigned int
0x1800585c9  call    ?KdcPickAuthInfo@@YAPEAU_LSAPR_AUTH_INFORMATION@@KPEAU1@@Z; KdcPickAuthInfo(ulong,_LSAPR_AUTH_INFORMATION *)
0x1800585ce  mov     r12, rax
0x1800585d1  call    ?KdcPickAuthInfoKeyVersion@@YAKKPEAU_LSAPR_AUTH_INFORMATION@@@Z; KdcPickAuthInfoKeyVersion(ulong,_LSAPR_AUTH_INFORMATION *)
0x1800585d6  mov     [rbp+180h+var_1E4], eax
0x1800585d9  mov     r11, [rsp+280h+var_210]
0x1800585de  mov     rdx, [r11+10h]
0x1800585e2  jmp     short loc_180058608
0x1800585e4  mov     rdx, [rax+20h]; struct _LSAPR_AUTH_INFORMATION *
0x1800585e8  mov     ecx, [rax+18h]; unsigned int
0x1800585eb  call    ?KdcPickAuthInfo@@YAPEAU_LSAPR_AUTH_INFORMATION@@KPEAU1@@Z; KdcPickAuthInfo(ulong,_LSAPR_AUTH_INFORMATION *)
0x1800585f0  mov     r12, rax
0x1800585f3  call    ?KdcPickAuthInfoKeyVersion@@YAKKPEAU_LSAPR_AUTH_INFORMATION@@@Z; KdcPickAuthInfoKeyVersion(ulong,_LSAPR_AUTH_INFORMATION *)
0x1800585f8  mov     [rbp+180h+var_1E4], eax
0x1800585fb  mov     rax, [rsp+280h+var_210]
0x180058600  mov     rdx, [rax+28h]; struct _LSAPR_AUTH_INFORMATION *
0x180058604  lea     r11, [rax+18h]
0x180058608  mov     ecx, [r11]; unsigned int
0x18005860b  call    ?KdcPickAuthInfo@@YAPEAU_LSAPR_AUTH_INFORMATION@@KPEAU1@@Z; KdcPickAuthInfo(ulong,_LSAPR_AUTH_INFORMATION *)
0x180058610  mov     r10, rax
0x180058613  mov     [rbp+180h+var_1F8], rax
0x180058617  call    ?KdcPickAuthInfoKeyVersion@@YAKKPEAU_LSAPR_AUTH_INFORMATION@@@Z; KdcPickAuthInfoKeyVersion(ulong,_LSAPR_AUTH_INFORMATION *)
0x18005861c  mov     dword ptr [rbp+180h+var_1C0], eax
0x18005861f  test    r12, r12
0x180058622  jnz     loc_1800586B0
0x180058628  lea     rax, WPP_GLOBAL_Control
0x18005862f  mov     rcx, cs:WPP_GLOBAL_Control
0x180058636  cmp     rcx, rax
0x180058639  jz      short loc_18005865B
0x18005863b  test    byte ptr [rcx+1Ch], 1
0x18005863f  jz      short loc_18005865B
0x180058641  lea     edx, [r12+1Ch]
0x180058646  mov     dword ptr [rsp+280h+var_258], 56Ch
0x18005864e  mov     r9, [rbp+180h+var_1D8]
0x180058652  mov     rcx, [rcx+10h]
0x180058656  call    WPP_SF_ZSd
0x18005865b  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x180058665  jz      short loc_180058678
0x180058667  mov     dword ptr [rdi], 0C000018Ch
0x18005866d  mov     dword ptr [rdi+4], 40B056Eh
0x180058674  mov     [rdi+8], r14d
0x180058678  lea     rcx, [rbp+180h+var_200]
0x18005867c  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180058681  nop
0x180058682  mov     rdx, [rsp+280h+var_210]
0x180058687  test    rdx, rdx
0x18005868a  jz      short loc_180058694
0x18005868c  mov     ecx, esi
0x18005868e  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x180058694  mov     rdx, [rsp+280h+var_208]
0x180058699  test    rdx, rdx
0x18005869c  jz      loc_180058E39
0x1800586a2  mov     ecx, r15d
0x1800586a5  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x1800586ab  jmp     loc_180058E39
0x1800586b0  test    r10, r10
0x1800586b3  jz      short loc_1800586EF
0x1800586b5  lea     rcx, [rbp+180h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800586b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800586bf  mov     eax, cs:?KdcGlobalDomainPasswordReplSkew@@3KA; ulong KdcGlobalDomainPasswordReplSkew
0x1800586c5  imul    rcx, rax, 23C34600h
0x1800586cc  mov     rax, qword ptr [rbp+180h+SystemTimeAsFileTime.dwLowDateTime]
0x1800586d0  sub     rax, [r12]
0x1800586d4  cmp     rax, rcx
0x1800586d7  jge     short loc_1800586E9
0x1800586d9  mov     [rbp+180h+var_1E0], r12
0x1800586dd  mov     r12, [rbp+180h+var_1F8]
0x1800586e1  mov     eax, dword ptr [rbp+180h+var_1C0]
0x1800586e4  mov     [rbp+180h+var_1E4], eax
0x1800586e7  jmp     short loc_1800586F5
0x1800586e9  mov     rax, [rbp+180h+var_1F8]
0x1800586ed  jmp     short loc_1800586F1
0x1800586ef  xor     eax, eax
0x1800586f1  mov     [rbp+180h+var_1E0], rax
0x1800586f5  movzx   eax, word ptr [r12+0Ch]
0x1800586fb  mov     [rbp+180h+String1.MaximumLength], ax
0x1800586ff  mov     [rbp+180h+String1.Length], ax
0x180058703  mov     rax, [r12+10h]
0x180058708  mov     [rbp+180h+String1.Buffer], rax
0x18005870c  mov     r8d, 4
0x180058712  mov     rdx, [rsp+280h+var_208]
0x180058717  mov     edx, [rdx]
0x180058719  mov     rcx, rbx
0x18005871c  call    ?SetPartnerAttributes@KerberosCryptoPolicy@@QEAA_NKW4UserPolicyAttributes@Kerb3961@@@Z; KerberosCryptoPolicy::SetPartnerAttributes(ulong,Kerb3961::UserPolicyAttributes)
0x180058721  xor     ecx, ecx
0x180058723  test    al, al
0x180058725  jnz     short loc_180058760
0x180058727  lea     rcx, [rbp+180h+var_200]
0x18005872b  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180058730  nop
0x180058731  mov     rdx, [rsp+280h+var_210]
0x180058736  test    rdx, rdx
0x180058739  jz      short loc_180058743
0x18005873b  mov     ecx, esi
0x18005873d  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x180058743  mov     rdx, [rsp+280h+var_208]
0x180058748  test    rdx, rdx
0x18005874b  jz      short loc_180058756
0x18005874d  mov     ecx, r15d
0x180058750  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x180058756  mov     esi, 0Eh
0x18005875b  jmp     loc_180058E39
0x180058760  cmp     dword ptr [r12+8], 1
0x180058766  jnz     loc_1800587EC
0x18005876c  lea     rax, [rbp+180h+var_1E8]
0x180058770  mov     [rsp+60h], rax
0x180058775  lea     rax, [rbp+180h+var_170]
0x180058779  mov     [rsp+280h+var_228], rax
0x18005877e  mov     eax, [rbp+180h+arg_18]
0x180058784  mov     dword ptr [rsp+280h+var_230], eax
0x180058788  mov     [rsp+280h+var_238], r14d
0x18005878d  mov     byte ptr [rsp+280h+var_240], cl
0x180058791  mov     dword ptr [rsp+280h+var_248], ecx
0x180058795  mov     qword ptr [rsp+280h+var_250], rcx
0x18005879a  mov     [rsp+280h+var_258], rbx
0x18005879f  mov     dword ptr [rsp+280h+var_260], r14d
0x1800587a4  mov     r9d, cs:?KdcGlobalIterationCount@@3KA; ulong KdcGlobalIterationCount
0x1800587ab  lea     r8, DomainName2
0x1800587b2  lea     r12, [r13+10h]
0x1800587b6  mov     rdx, r12
0x1800587b9  lea     rcx, [rbp+180h+String1]
0x1800587bd  call    ?KdcBuildPasswordList@@YAJPEAU_UNICODE_STRING@@00KW4_KERB_ACCOUNT_TYPE@@PEAVKerberosCryptoPolicy@@PEAU_KERB_STORED_CREDENTIAL@@KEKW4KDC_DOMAIN_INFO_DIRECTION@@PEAPEAU4@PEAK@Z; KdcBuildPasswordList(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_KERB_ACCOUNT_TYPE,KerberosCryptoPolicy *,_KERB_STORED_CREDENTIAL *,ulong,uchar,ulong,KDC_DOMAIN_INFO_DIRECTION,_KERB_STORED_CREDENTIAL * *,ulong *)
0x1800587c2  test    eax, eax
0x1800587c4  jns     loc_180058976
0x1800587ca  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x1800587d4  jz      loc_180058E05
0x1800587da  mov     dword ptr [rdi+4], 40B05AEh
0x1800587e1  mov     [rdi], eax
0x1800587e3  mov     [rdi+8], r14d
0x1800587e7  jmp     loc_180058E05
0x1800587ec  mov     eax, 68h ; 'h'
0x1800587f1  lea     edx, [rax+20h]
0x1800587f4  mov     ecx, [rbp+180h+arg_18]
0x1800587fa  cmp     ecx, 1
0x1800587fd  cmovnz  eax, edx
0x180058800  add     rax, r13
0x180058803  mov     [rbp+180h+String2], rax
0x180058807  lea     eax, [rdx-28h]
0x18005880a  lea     edx, [rax+20h]
0x18005880d  cmp     ecx, 1
0x180058810  cmovnz  eax, edx
0x180058813  add     rax, r13
0x180058816  mov     [rbp+180h+var_1F8], rax
0x18005881a  mov     edx, 90h
0x18005881f  lea     r12d, [rdx-20h]
0x180058823  cmp     ecx, 1
0x180058826  cmovnz  r12d, edx
0x18005882a  add     r12, r13
0x18005882d  mov     [rbp+180h+var_1C0], r12
0x180058831  lea     rdx, [r13+0E0h]
0x180058838  lea     rcx, [rbp+180h+var_1D8]
0x18005883c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180058841  nop
0x180058842  xor     r8d, r8d; CaseInsensitive
0x180058845  mov     rdx, r12; String2
0x180058848  lea     rcx, [rbp+180h+String1]; String1
0x18005884c  call    cs:__imp_RtlEqualUnicodeString
0x180058852  test    al, al
0x180058854  jnz     loc_18005891F
0x18005885a  movzx   r8d, word ptr [r12]; Size
0x18005885f  xor     edx, edx; Val
0x180058861  mov     rcx, [r12+8]; void *
0x180058866  call    memset_0
0x18005886b  mov     rcx, r12
0x18005886e  call    KerbFreeString
0x180058873  lea     rdx, [rbp+180h+String1]; struct _UNICODE_STRING *
0x180058877  mov     rcx, r12; struct _UNICODE_STRING *
0x18005887a  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005887f  mov     r12d, eax
0x180058882  test    eax, eax
0x180058884  js      short loc_1800588DB
0x180058886  mov     r12, [rbp+180h+var_1F8]
0x18005888a  mov     rcx, [r12]; void *
0x18005888e  test    rcx, rcx
0x180058891  jz      short loc_1800588A0
0x180058893  call    MIDL_user_free
0x180058898  mov     qword ptr [r12], 0
0x1800588a0  mov     rax, [rbp+180h+String2]
0x1800588a4  mov     dword ptr [rax], 0
0x1800588aa  mov     qword ptr [rsp+280h+var_250], rax
0x1800588af  mov     [rsp+280h+var_258], r12
0x1800588b4  mov     eax, [rbp+180h+arg_18]
0x1800588ba  mov     dword ptr [rsp+280h+var_260], eax
0x1800588be  lea     r9, DomainName2
0x1800588c5  mov     r8, rbx
0x1800588c8  mov     rdx, r13
0x1800588cb  lea     rcx, [rbp+180h+String1]
0x1800588cf  call    ?KdcBuildKeysForTrusts@@YAJPEAU_UNICODE_STRING@@PEAU_KDC_DOMAIN_INFO@@PEAVKerberosCryptoPolicy@@0W4KDC_DOMAIN_INFO_DIRECTION@@PEAPEAEPEAK@Z; KdcBuildKeysForTrusts(_UNICODE_STRING *,_KDC_DOMAIN_INFO *,KerberosCryptoPolicy *,_UNICODE_STRING *,KDC_DOMAIN_INFO_DIRECTION,uchar * *,ulong *)
0x1800588d4  mov     r12d, eax
0x1800588d7  test    eax, eax
0x1800588d9  jns     short loc_18005891F
0x1800588db  mov     rax, [rbp+180h+var_1C0]
0x1800588df  movzx   r8d, word ptr [rax]; Size
0x1800588e3  xor     edx, edx; Val
0x1800588e5  mov     rcx, [rax+8]; void *
0x1800588e9  call    memset_0
0x1800588ee  mov     rcx, [rbp+180h+var_1C0]
0x1800588f2  call    KerbFreeString
0x1800588f7  mov     rax, [rbp+180h+var_1F8]
0x1800588fb  mov     rcx, [rax]; void *
0x1800588fe  test    rcx, rcx
0x180058901  jz      short loc_180058913
0x180058903  call    MIDL_user_free
0x180058908  mov     rax, [rbp+180h+var_1F8]
0x18005890c  mov     qword ptr [rax], 0
0x180058913  mov     rcx, [rbp+180h+String2]
0x180058917  mov     dword ptr [rcx], 0
0x18005891d  jmp     short loc_18005893C
0x18005891f  lea     r9, [rbp+180h+var_1E8]; unsigned int *
  ... truncated ...
```
