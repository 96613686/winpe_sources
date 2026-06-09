# LogGetTgsExtendedAudit(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,ulong *,long *,ulong *,sockaddr *,_GUID *,_LSA_ADT_STRING_LIST *,KERB_AP_REQUEST *,KERB_KDC_REQUEST_BODY *,KERB_TICKET *,KERB_ENCRYPTED_KDC_REPLY *,_UNICODE_STRING *,KERB_EXT_ERROR *,ulong *,ulong *,_KERB_ENCRYPTION_KEY *,_KDC_U2U_TICKET_INFO *,_KDC_S4U_TICKET_INFO *,_KDC_U2U_TICKET_AUDIT_INFO *,_KDC_S4U_TICKET_AUDIT_INFO *,_USER_INTERNAL6_INFORMATION *)

- ea: `0x18000d42c`
- end: `0x18000e30b`
- name: `?LogGetTgsExtendedAudit@@YAXPEAU_UNICODE_STRING@@00PEAXPEAKPEAJ2PEAUsockaddr@@PEAU_GUID@@PEAU_LSA_ADT_STRING_LIST@@PEAUKERB_AP_REQUEST@@PEAUKERB_KDC_REQUEST_BODY@@PEAUKERB_TICKET@@PEAUKERB_ENCRYPTED_KDC_REPLY@@0PEAUKERB_EXT_ERROR@@22PEAU_KERB_ENCRYPTION_KEY@@PEAU_KDC_U2U_TICKET_INFO@@PEAU_KDC_S4U_TICKET_INFO@@PEAU_KDC_U2U_TICKET_AUDIT_INFO@@PEAU_KDC_S4U_TICKET_AUDIT_INFO@@PEAU_USER_INTERNAL6_INFORMATION@@@Z`
- size: `3807`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, unsigned int *, int *, unsigned int *, struct sockaddr *, struct _GUID *, struct _LSA_ADT_STRING_LIST *, struct KERB_AP_REQUEST *, struct KERB_KDC_REQUEST_BODY *, struct KERB_TICKET *, struct KERB_ENCRYPTED_KDC_REPLY *, struct _UNICODE_STRING *, struct KERB_EXT_ERROR *, unsigned int *, unsigned int *, struct _KERB_ENCRYPTION_KEY *, struct _KDC_U2U_TICKET_INFO *, struct _KDC_S4U_TICKET_INFO *, struct _KDC_U2U_TICKET_AUDIT_INFO *, struct _KDC_S4U_TICKET_AUDIT_INFO *, struct _USER_INTERNAL6_INFORMATION *)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e930`
- `0x180021eb4`
- `0x180047850`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000a878`
- `0x18000a8d8`
- `0x18000abe4`
- `0x18000acec`
- `0x18000ae00`
- `0x18000b474`
- `0x18000d42c`
- `0x18000e874`
- `0x18000e9e8`
- `0x18000ea7c`
- `0x18000eae0`
- `0x18000f318`
- `0x180045bb0`
- `0x18004843c`
- `0x180063144`
- `0x18007bef4`
- `0x18007d4b0`
- `0x18007d714`
- `0x18007e35c`
- `0x18007f1a4`
- `0x180080280`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000d793`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000da9b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000dabf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000d793`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000da9b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000dabf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LogGetTgsExtendedAudit(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        unsigned int *a5,
        int *a6,
        unsigned int *a7,
        struct sockaddr *a8,
        struct _GUID *a9,
        struct _LSA_ADT_STRING_LIST *a10,
        struct KERB_AP_REQUEST *a11,
        struct KERB_KDC_REQUEST_BODY *a12,
        struct KERB_TICKET *a13,
        struct KERB_ENCRYPTED_KDC_REPLY *a14,
        struct _UNICODE_STRING *a15,
        struct KERB_EXT_ERROR *a16,
        unsigned int *a17,
        unsigned int *a18,
        struct _KERB_ENCRYPTION_KEY *a19,
        struct _KDC_U2U_TICKET_INFO *a20,
        struct _KDC_S4U_TICKET_INFO *a21,
        struct _KDC_U2U_TICKET_AUDIT_INFO *a22,
        const struct _UNICODE_STRING *a23,
        struct _USER_INTERNAL6_INFORMATION *a24)
{
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rbx
  ULONG v26; // ebx
  PLSA_ADT_STRING_LIST_ENTRY Strings; // rax
  PWSTR Buffer; // rdx
  unsigned __int64 Length; // r8
  __int64 *v30; // rax
  void *v31; // rcx
  const WCHAR *v32; // r11
  const unsigned __int16 *v33; // r11
  struct sockaddr *v34; // r11
  const struct _UNICODE_STRING *v35; // r8
  const struct _UNICODE_STRING *v36; // r8
  int *v37; // r8
  const struct _UNICODE_STRING *v38; // r8
  __int64 *v39; // rax
  const unsigned __int16 *v40; // rax
  struct KERB_ENCRYPTED_TICKET *v41; // [rsp+300h] [rbp-80h] BYREF
  int v42; // [rsp+308h] [rbp-78h]
  unsigned int v43; // [rsp+30Ch] [rbp-74h]
  int v44; // [rsp+310h] [rbp-70h] BYREF
  unsigned int v45; // [rsp+314h] [rbp-6Ch] BYREF
  int v46; // [rsp+318h] [rbp-68h]
  int v47; // [rsp+31Ch] [rbp-64h]
  int v48; // [rsp+320h] [rbp-60h]
  int v49; // [rsp+324h] [rbp-5Ch]
  int v50; // [rsp+328h] [rbp-58h]
  int v51; // [rsp+32Ch] [rbp-54h]
  int v52; // [rsp+330h] [rbp-50h]
  int v53; // [rsp+334h] [rbp-4Ch]
  int v54; // [rsp+338h] [rbp-48h]
  int v55; // [rsp+33Ch] [rbp-44h]
  int v56; // [rsp+340h] [rbp-40h] BYREF
  int v57; // [rsp+344h] [rbp-3Ch] BYREF
  int v58; // [rsp+348h] [rbp-38h] BYREF
  int v59; // [rsp+34Ch] [rbp-34h] BYREF
  int v60; // [rsp+350h] [rbp-30h]
  int v61; // [rsp+354h] [rbp-2Ch]
  unsigned int v62; // [rsp+358h] [rbp-28h]
  int v63; // [rsp+35Ch] [rbp-24h]
  unsigned int v64; // [rsp+360h] [rbp-20h]
  const struct _UNICODE_STRING *v65; // [rsp+368h] [rbp-18h]
  PSID v66; // [rsp+370h] [rbp-10h] BYREF
  const unsigned __int16 *v67; // [rsp+378h] [rbp-8h]
  struct sockaddr *v68; // [rsp+380h] [rbp+0h]
  const struct _UNICODE_STRING *v69; // [rsp+388h] [rbp+8h]
  const unsigned __int16 *v70; // [rsp+390h] [rbp+10h]
  struct _GUID *v71; // [rsp+398h] [rbp+18h]
  PSID pSid; // [rsp+3A0h] [rbp+20h]
  const unsigned __int16 *v73; // [rsp+3A8h] [rbp+28h]
  const unsigned __int16 *v74; // [rsp+3B0h] [rbp+30h]
  const unsigned __int16 *v75; // [rsp+3B8h] [rbp+38h]
  const unsigned __int16 *v76; // [rsp+3C0h] [rbp+40h]
  struct _UNICODE_STRING *v77; // [rsp+3C8h] [rbp+48h]
  __int64 v78; // [rsp+3D0h] [rbp+50h]
  const unsigned __int16 *v79; // [rsp+3D8h] [rbp+58h]
  const unsigned __int16 *v80; // [rsp+3E0h] [rbp+60h]
  const unsigned __int16 *p_sa_family; // [rsp+3E8h] [rbp+68h]
  const unsigned __int16 *v82; // [rsp+3F0h] [rbp+70h]
  __int64 v83; // [rsp+3F8h] [rbp+78h]
  __int64 v84; // [rsp+400h] [rbp+80h]
  __int64 v85; // [rsp+408h] [rbp+88h]
  __int64 v86; // [rsp+410h] [rbp+90h]
  __int64 v87; // [rsp+418h] [rbp+98h]
  __int64 v88; // [rsp+420h] [rbp+A0h]
  unsigned __int8 *v89; // [rsp+428h] [rbp+A8h] BYREF
  PSID v90; // [rsp+430h] [rbp+B0h]
  const WCHAR *v91; // [rsp+438h] [rbp+B8h]
  const WCHAR *v92; // [rsp+440h] [rbp+C0h]
  const unsigned __int16 *v93; // [rsp+448h] [rbp+C8h]
  _OWORD v94[2]; // [rsp+450h] [rbp+D0h] BYREF
  __int64 v95; // [rsp+470h] [rbp+F0h]
  void *v96[2]; // [rsp+478h] [rbp+F8h] BYREF
  _WORD v97[8]; // [rsp+488h] [rbp+108h] BYREF
  struct _UNICODE_STRING *v98; // [rsp+498h] [rbp+118h]
  struct _UNICODE_STRING *v99; // [rsp+4A0h] [rbp+120h]
  struct _UNICODE_STRING *v100; // [rsp+4A8h] [rbp+128h]
  const unsigned __int16 *v101; // [rsp+4B0h] [rbp+130h]
  const unsigned __int16 *v102; // [rsp+4B8h] [rbp+138h]
  const unsigned __int16 *v103; // [rsp+4C0h] [rbp+140h]
  const unsigned __int16 *v104; // [rsp+4C8h] [rbp+148h]
  const unsigned __int16 *v105; // [rsp+4D0h] [rbp+150h]
  const unsigned __int16 *v106; // [rsp+4D8h] [rbp+158h]
  const unsigned __int16 *v107; // [rsp+4E0h] [rbp+160h]
  const unsigned __int16 *v108; // [rsp+4E8h] [rbp+168h]
  const unsigned __int16 *v109; // [rsp+4F0h] [rbp+170h]
  const unsigned __int16 *v110; // [rsp+4F8h] [rbp+178h]
  const unsigned __int16 *v111; // [rsp+500h] [rbp+180h]
  const unsigned __int16 *v112; // [rsp+508h] [rbp+188h]
  const unsigned __int16 *v113; // [rsp+510h] [rbp+190h]
  struct _UNICODE_STRING v114; // [rsp+518h] [rbp+198h] BYREF
  struct _UNICODE_STRING v115; // [rsp+528h] [rbp+1A8h] BYREF
  struct _UNICODE_STRING v116; // [rsp+538h] [rbp+1B8h] BYREF
  struct _UNICODE_STRING v117; // [rsp+548h] [rbp+1C8h] BYREF
  struct _UNICODE_STRING v118; // [rsp+558h] [rbp+1D8h] BYREF
  struct _UNICODE_STRING v119; // [rsp+568h] [rbp+1E8h] BYREF
  struct _UNICODE_STRING v120; // [rsp+578h] [rbp+1F8h] BYREF
  struct _UNICODE_STRING v121; // [rsp+588h] [rbp+208h] BYREF
  struct _UNICODE_STRING v122; // [rsp+598h] [rbp+218h] BYREF
  struct _UNICODE_STRING v123; // [rsp+5A8h] [rbp+228h] BYREF
  struct _UNICODE_STRING v124; // [rsp+5B8h] [rbp+238h] BYREF
  struct _UNICODE_STRING v125; // [rsp+5C8h] [rbp+248h] BYREF
  int *v126; // [rsp+5D8h] [rbp+258h]
  unsigned int *v127; // [rsp+5E0h] [rbp+260h]
  struct _UNICODE_STRING v128; // [rsp+5F0h] [rbp+270h] BYREF
  struct _UNICODE_STRING v129; // [rsp+600h] [rbp+280h] BYREF
  struct _UNICODE_STRING v130; // [rsp+610h] [rbp+290h] BYREF
  struct _UNICODE_STRING v131; // [rsp+620h] [rbp+2A0h] BYREF
  struct _UNICODE_STRING v132; // [rsp+630h] [rbp+2B0h] BYREF
  _QWORD v133[15]; // [rsp+6B0h] [rbp+330h] BYREF
  char v134; // [rsp+728h] [rbp+3A8h]
  void *v135[4]; // [rsp+730h] [rbp+3B0h] BYREF
  __int128 v136; // [rsp+750h] [rbp+3D0h]

  pSid = a4;
  v98 = a3;
  v99 = a2;
  v100 = a1;
  v71 = a9;
  v76 = (const unsigned __int16 *)a16;
  v69 = (const struct _UNICODE_STRING *)a22;
  v126 = a6;
  v127 = a7;
  v68 = a8;
  v67 = (const unsigned __int16 *)a14;
  v77 = a15;
  v75 = (const unsigned __int16 *)a17;
  v74 = (const unsigned __int16 *)a18;
  v73 = (const unsigned __int16 *)a19;
  v65 = (const struct _UNICODE_STRING *)a20;
  v70 = (const unsigned __int16 *)a24;
  if ( (byte_1800B2901 & 1) != 0 )
  {
    memset(v94, 0, sizeof(v94));
    LOBYTE(v94[0]) = 0;
    v95 = 0;
    v125 = 0;
    v123 = 0;
    v122 = 0;
    v121 = 0;
    v120 = 0;
    v119 = 0;
    v118 = 0;
    v124 = 0;
    v117 = 0;
    v116 = 0;
    v114 = 0;
    v115 = 0;
    v41 = 0;
    v128.Length = 0;
    memset_0(&v128.MaximumLength, 0, 0xB2u);
    v66 = 0;
    v133[0] = &v125;
    v133[1] = &v123;
    v133[2] = &v122;
    v133[3] = &v121;
    v133[4] = &v120;
    v133[5] = &v119;
    v133[6] = &v118;
    v133[7] = &v124;
    v133[8] = &v117;
    v133[9] = &v116;
    v133[10] = &v114;
    v133[11] = &v115;
    v133[12] = &v41;
    v133[13] = &v128;
    v133[14] = &v66;
    v134 = 1;
    v61 = 0;
    v42 = 0;
    v59 = 0;
    v60 = 0;
    if ( a5 )
      v43 = *a5;
    else
      v43 = 0;
    if ( a12 )
    {
      if ( !a5 )
        v43 = KerbConvertFlagsToUlong((struct KERB_KDC_REQUEST_BODY *)((char *)a12 + 8));
      if ( (*(_BYTE *)a12 & 0x40) != 0 )
        KerbConvertPrincipalNameToString(&v123, &v59, (char *)a12 + 48);
      KerbConvertRealmToUnicodeString(&v122, (char *)a12 + 40);
      v24 = KerberosCryptoPolicy::EtypeListToCommaSeparatedString((__int64)v135, *((__int64 ***)a12 + 14));
      if ( (_BYTE)v95 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
          v94,
          v24);
      }
      else
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          v94,
          v24);
        LOBYTE(v95) = 1;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v135);
      v61 = *((_DWORD *)a12 + 36);
      if ( v61 )
        v42 = *((_DWORD *)a12 + 33);
      else
        v42 = 0;
      v60 = *((_DWORD *)a12 + 27);
    }
    if ( !pSid || !IsValidSid(pSid) )
      pSid = 0;
    v45 = 0;
    v89 = 0;
    GetClientAddressBuffer(v68, &v45, &v89);
    v58 = 0;
    v57 = 0;
    v62 = 0;
    v86 = 0;
    v85 = 0;
    v87 = 0;
    v88 = 0;
    if ( a11 )
    {
      v64 = *((_DWORD *)a11 + 18);
      v55 = *((_DWORD *)a11 + 16);
      v54 = *((_DWORD *)a11 + 15);
      KdcHashTicketEncryptedPart(*((unsigned __int8 **)a11 + 10), v64, &v125);
      KerbConvertPrincipalNameToString(&v121, &v58, (char *)a11 + 40);
      KerbConvertRealmToUnicodeString(&v120, (char *)a11 + 32);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties>::GetImpl'::`2'::impl)
        && !(unsigned int)DecryptTgt((struct KERB_AP_REQUEST *)((char *)a11 + 24), &v41)
        && v41 )
      {
        KerbConvertPrincipalNameToString(&v119, &v57, (char *)v41 + 56);
        KerbConvertRealmToUnicodeString(&v118, (char *)v41 + 48);
        v86 = KerbConvertGeneralizedTimeToFileTime((char *)v41 + 110);
        v85 = KerbConvertGeneralizedTimeToFileTime((char *)v41 + 124);
        v87 = KerbConvertGeneralizedTimeToFileTime((char *)v41 + 138);
        v88 = KerbConvertGeneralizedTimeToFileTime((char *)v41 + 96);
        v62 = KerbConvertFlagsToUlong((struct KERB_ENCRYPTED_TICKET *)((char *)v41 + 8));
        FillPacAuditInfo(v41, (struct _PAC_AUDIT_INFO *)&v128);
        KdcGetRequestorIdFromTgtPac(v41, &v66, &v44);
      }
    }
    else
    {
      v64 = 0;
      v54 = 0;
      v55 = 0;
    }
    v44 = 0;
    v56 = 0;
    if ( a13 )
    {
      v44 = *((_DWORD *)a13 + 12);
      KdcHashTicketEncryptedPart(*((unsigned __int8 **)a13 + 7), v44, &v124);
      KerbConvertPrincipalNameToString(&v117, &v56, (char *)a13 + 16);
      KerbConvertRealmToUnicodeString(&v116, (char *)a13 + 8);
    }
    v84 = 0;
    v83 = 0;
    v25 = v67;
    if ( v67 )
    {
      v84 = KerbConvertGeneralizedTimeToFileTime(v67 + 47);
      v83 = KerbConvertGeneralizedTimeToFileTime(v25 + 54);
    }
    v96[0] = v97;
    v96[1] = v97;
    v97[0] = 0;
    if ( a10 && a10->cStrings )
    {
      v26 = 0;
      do
      {
        Strings = a10->Strings;
        Buffer = Strings[v26].String.Buffer;
        if ( Buffer )
        {
          Length = Strings[v26].String.Length;
          if ( (_WORD)Length )
          {
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v96,
              Buffer,
              Length >> 1);
            if ( v26 < a10->cStrings - 1 )
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                v96,
                L", ",
                2);
          }
        }
        ++v26;
      }
      while ( v26 < a10->cStrings );
    }
    if ( a21 )
    {
      KerbConvertKdcNameToString(&v114, *(struct _KERB_INTERNAL_NAME **)a21, 0);
      KerbConvertKdcNameToString(&v115, *((struct _KERB_INTERNAL_NAME **)a21 + 28), 0);
    }
    if ( v70 )
      v30 = (__int64 *)(v70 + 376);
    else
      v30 = qword_1800A1970;
    v136 = *(_OWORD *)v30;
    if ( a21 && (v31 = (void *)*((_QWORD *)a21 + 25)) != 0 && IsValidSid(v31) )
      v78 = *((_QWORD *)a21 + 25);
    else
      v78 = 0;
    if ( v66 && IsValidSid(v66) )
      v90 = v66;
    else
      v90 = 0;
    if ( (byte_1800B2901 & 1) != 0 )
    {
      v101 = SafeGetBuffer(&v132);
      v102 = SafeGetBuffer(&v131);
      v103 = SafeGetBuffer(&v128);
      v104 = SafeGetBuffer(&v130);
      v105 = SafeGetBuffer(&v129);
      v32 = &Class;
      if ( a23 )
      {
        v91 = SafeGetBuffer(a23 + 2);
        v92 = SafeGetBuffer(a23 + 1);
        v48 = *(_DWORD *)(&a23->MaximumLength + 1);
        v47 = *(_DWORD *)&a23->Length;
        v46 = *(_DWORD *)&a23[3].Length;
      }
      else
      {
        v91 = &Class;
        v92 = &Class;
        v48 = 0;
        v47 = 0;
        v46 = 0;
      }
      if ( a21 )
        v93 = SafeGetBuffer((const struct _UNICODE_STRING *)((char *)a21 + 8));
      else
        v93 = v32;
      v106 = SafeGetBuffer(&v114);
      if ( a23 )
        v49 = (int)a23->Buffer;
      else
        v49 = 0;
      if ( a21 )
      {
        v79 = SafeGetBuffer((const struct _UNICODE_STRING *)a21 + 13);
        v80 = SafeGetBuffer((const struct _UNICODE_STRING *)((char *)a21 + 232));
        v50 = *((_DWORD *)a21 + 75);
      }
      else
      {
        v79 = v33;
        v80 = v33;
        v50 = 0;
      }
      v107 = SafeGetBuffer(&v115);
      if ( a21 )
        p_sa_family = SafeGetBuffer((const struct _UNICODE_STRING *)((char *)a21 + 312));
      else
        p_sa_family = &v34->sa_family;
      if ( v69 )
      {
        v82 = SafeGetBuffer(v69 + 3);
        v69 = (const struct _UNICODE_STRING *)SafeGetBuffer(v35 + 1);
        v70 = SafeGetBuffer(v36 + 2);
        v63 = v37[1];
        v53 = *v37;
        v52 = v37[2];
        v51 = v37[16];
      }
      else
      {
        v82 = &v34->sa_family;
        v69 = (const struct _UNICODE_STRING *)v34;
        v70 = &v34->sa_family;
        v63 = 0;
        v53 = 0;
        v52 = 0;
        v51 = 0;
      }
      if ( v65 )
      {
        v67 = SafeGetBuffer(v65 + 1);
        v68 = (struct sockaddr *)SafeGetBuffer(v38 + 2);
      }
      else
      {
        v67 = &v34->sa_family;
        v68 = v34;
      }
      if ( v73 )
        LODWORD(v65) = *((_DWORD *)v73 + 3);
      else
        LODWORD(v65) = 0;
      v74 = SafeGetBuffer(&v116);
      v73 = SafeGetBuffer(&v117);
      v108 = SafeGetBuffer(&v118);
      v109 = SafeGetBuffer(&v119);
      v110 = SafeGetBuffer(&v120);
      v111 = SafeGetBuffer(&v121);
      v112 = SafeGetBuffer(&v122);
      v113 = SafeGetBuffer(&v123);
      v77 = (struct _UNICODE_STRING *)SafeGetBuffer(v77);
      v76 = SafeGetBuffer(&v124);
      v75 = SafeGetBuffer(&v125);
      v39 = (__int64 *)v71;
      if ( !v71 )
        v39 = qword_1800A1970;
      v71 = (struct _GUID *)v39;
      SafeGetBuffer(v98);
      SafeGetBuffer(v99);
      v40 = SafeGetBuffer(v100);
      McTemplateU0zzzkqqqbr6qjzzzzqqqqmqmmmmmzqqqzqzzqzzqzzqzqqqqzzzqqzqzqzzzzqkqzzqqzzqjqbr69qbr71kzzzzzqqqqqqqmmmmmmq_EtwEventWriteTransfer(
        &S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context,
        KdcGetTgsExtendedAudit,
        v40);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v96);
    v134 = 0;
    lambda_5eeaea62fe84dd0bdee2f9784886869a_::operator()(v133);
    utl::_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>::~_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(v94);
  }
}

```

## disassembly

```asm
0x18000d42c  push    rbp
0x18000d42e  push    rbx
0x18000d42f  push    rsi
0x18000d430  push    rdi
0x18000d431  push    r12
0x18000d433  push    r13
0x18000d435  push    r14
0x18000d437  push    r15
0x18000d439  lea     rbp, [rsp-3F8h]
0x18000d441  sub     rsp, 778h
0x18000d448  mov     rax, cs:__security_cookie
0x18000d44f  xor     rax, rsp
0x18000d452  mov     [rbp+430h+var_50], rax
0x18000d459  mov     [rbp+430h+pSid], r9
0x18000d45d  mov     [rbp+430h+var_318], r8
0x18000d464  mov     [rbp+430h+var_310], rdx
0x18000d46b  mov     [rbp+430h+var_308], rcx
0x18000d472  mov     rax, [rbp+430h+arg_40]
0x18000d479  mov     [rbp+430h+var_418], rax
0x18000d47d  mov     rax, [rbp+430h+arg_78]
0x18000d484  mov     [rbp+430h+var_3F0], rax
0x18000d488  mov     rax, [rbp+430h+arg_A8]
0x18000d48f  mov     [rbp+430h+var_428], rax
0x18000d493  mov     r13, [rbp+430h+arg_B0]
0x18000d49a  mov     rdi, [rbp+430h+arg_A0]
0x18000d4a1  mov     r12, [rbp+430h+arg_48]
0x18000d4a8  mov     rbx, [rbp+430h+arg_58]
0x18000d4af  mov     r15, [rbp+430h+arg_20]
0x18000d4b6  mov     rax, [rbp+430h+arg_28]
0x18000d4bd  mov     [rbp+430h+var_1D8], rax
0x18000d4c4  mov     rcx, [rbp+430h+arg_30]
0x18000d4cb  mov     [rbp+430h+var_1D0], rcx
0x18000d4d2  mov     rax, [rbp+430h+arg_38]
0x18000d4d9  mov     [rbp+430h+var_430], rax
0x18000d4dd  mov     rsi, [rbp+430h+arg_50]
0x18000d4e4  mov     r14, [rbp+430h+arg_60]
0x18000d4eb  mov     rax, [rbp+430h+arg_68]
0x18000d4f2  mov     [rbp+430h+var_438], rax
0x18000d4f6  mov     rax, [rbp+430h+arg_70]
0x18000d4fd  mov     [rbp+430h+var_3E8], rax
0x18000d501  mov     rax, [rbp+430h+arg_80]
0x18000d508  mov     [rbp+430h+var_3F8], rax
0x18000d50c  mov     rax, [rbp+430h+arg_88]
0x18000d513  mov     [rbp+430h+var_400], rax
0x18000d517  mov     rax, [rbp+430h+arg_90]
0x18000d51e  mov     [rbp+430h+var_408], rax
0x18000d522  mov     rax, [rbp+430h+arg_98]
0x18000d529  mov     [rbp+430h+var_448], rax
0x18000d52d  mov     rax, [rbp+430h+arg_B8]
0x18000d534  mov     [rbp+430h+var_420], rax
0x18000d538  test    cs:byte_1800B2901, 1
0x18000d53f  jz      loc_18000E2E8
0x18000d545  xorps   xmm0, xmm0
0x18000d548  xor     eax, eax
0x18000d54a  movups  [rbp+430h+var_360], xmm0
0x18000d551  movups  [rbp+430h+var_350], xmm0
0x18000d558  mov     [rbp+430h+var_340], rax
0x18000d55f  xor     ecx, ecx
0x18000d561  mov     byte ptr [rbp+430h+var_360], cl
0x18000d567  mov     byte ptr [rbp+430h+var_340], cl
0x18000d56d  movups  xmmword ptr [rbp+430h+var_1E8.Length], xmm0
0x18000d574  xorps   xmm1, xmm1
0x18000d577  movups  xmmword ptr [rbp+430h+var_208.Length], xmm1
0x18000d57e  movups  xmmword ptr [rbp+430h+var_218.Length], xmm0
0x18000d585  movups  xmmword ptr [rbp+430h+var_228.Length], xmm1
0x18000d58c  movups  xmmword ptr [rbp+430h+var_238.Length], xmm0
0x18000d593  movups  xmmword ptr [rbp+430h+var_248.Length], xmm1
0x18000d59a  movups  xmmword ptr [rbp+430h+var_258.Length], xmm0
0x18000d5a1  movups  xmmword ptr [rbp+430h+var_1F8.Length], xmm1
0x18000d5a8  movups  xmmword ptr [rbp+430h+var_268.Length], xmm0
0x18000d5af  movups  xmmword ptr [rbp+430h+var_278.Length], xmm1
0x18000d5b6  movups  xmmword ptr [rbp+430h+var_298.Length], xmm0
0x18000d5bd  movups  xmmword ptr [rbp+430h+var_288.Length], xmm1
0x18000d5c4  mov     [rbp+430h+var_4B0], rcx
0x18000d5c8  mov     [rbp+430h+var_1C0.Length], cx
0x18000d5cf  xor     edx, edx; Val
0x18000d5d1  mov     r8d, 0B2h; Size
0x18000d5d7  lea     rcx, [rbp+430h+var_1C0.MaximumLength]; void *
0x18000d5de  call    memset_0
0x18000d5e3  xor     ecx, ecx
0x18000d5e5  mov     [rbp+430h+var_440], rcx
0x18000d5e9  lea     rax, [rbp+430h+var_1E8]
0x18000d5f0  mov     [rbp+430h+var_100], rax
0x18000d5f7  lea     rax, [rbp+430h+var_208]
0x18000d5fe  mov     [rbp+430h+var_F8], rax
0x18000d605  lea     rax, [rbp+430h+var_218]
0x18000d60c  mov     [rbp+430h+var_F0], rax
0x18000d613  lea     rax, [rbp+430h+var_228]
0x18000d61a  mov     [rbp+430h+var_E8], rax
0x18000d621  lea     rax, [rbp+430h+var_238]
0x18000d628  mov     [rbp+430h+var_E0], rax
0x18000d62f  lea     rax, [rbp+430h+var_248]
0x18000d636  mov     [rbp+430h+var_D8], rax
0x18000d63d  lea     rax, [rbp+430h+var_258]
0x18000d644  mov     [rbp+430h+var_D0], rax
0x18000d64b  lea     rax, [rbp+430h+var_1F8]
0x18000d652  mov     [rbp+430h+var_C8], rax
0x18000d659  lea     rax, [rbp+430h+var_268]
0x18000d660  mov     [rbp+430h+var_C0], rax
0x18000d667  lea     rax, [rbp+430h+var_278]
0x18000d66e  mov     [rbp+430h+var_B8], rax
0x18000d675  lea     rax, [rbp+430h+var_298]
0x18000d67c  mov     [rbp+430h+var_B0], rax
0x18000d683  lea     rax, [rbp+430h+var_288]
0x18000d68a  mov     [rbp+430h+var_A8], rax
0x18000d691  lea     rax, [rbp+430h+var_4B0]
0x18000d695  mov     [rbp+430h+var_A0], rax
0x18000d69c  lea     rax, [rbp+430h+var_1C0]
0x18000d6a3  mov     [rbp+430h+var_98], rax
0x18000d6aa  lea     rax, [rbp+430h+var_440]
0x18000d6ae  mov     [rbp+430h+var_90], rax
0x18000d6b5  mov     [rbp+430h+var_88], 1
0x18000d6bc  mov     [rbp+430h+var_45C], ecx
0x18000d6bf  mov     [rbp+430h+var_4A8], ecx
0x18000d6c2  mov     [rbp+430h+var_464], ecx
0x18000d6c5  mov     [rbp+430h+var_460], ecx
0x18000d6c8  test    r15, r15
0x18000d6cb  jz      short loc_18000D6D5
0x18000d6cd  mov     eax, [r15]
0x18000d6d0  mov     [rbp+430h+var_4A4], eax
0x18000d6d3  jmp     short loc_18000D6D8
0x18000d6d5  mov     [rbp+430h+var_4A4], ecx
0x18000d6d8  test    rbx, rbx
0x18000d6db  jz      loc_18000D784
0x18000d6e1  test    r15, r15
0x18000d6e4  jnz     short loc_18000D6F2
0x18000d6e6  lea     rcx, [rbx+8]; struct tagASN1bitstring_t *
0x18000d6ea  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18000d6ef  mov     [rbp+430h+var_4A4], eax
0x18000d6f2  test    byte ptr [rbx], 40h
0x18000d6f5  jz      short loc_18000D70B
0x18000d6f7  lea     r8, [rbx+30h]
0x18000d6fb  lea     rdx, [rbp+430h+var_464]
0x18000d6ff  lea     rcx, [rbp+430h+var_208]
0x18000d706  call    KerbConvertPrincipalNameToString
0x18000d70b  lea     rdx, [rbx+28h]
0x18000d70f  lea     rcx, [rbp+430h+var_218]
0x18000d716  call    KerbConvertRealmToUnicodeString
0x18000d71b  mov     rdx, [rbx+70h]
0x18000d71f  lea     rcx, [rbp+430h+var_80]
0x18000d726  call    ?EtypeListToCommaSeparatedString@KerberosCryptoPolicy@@SA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUKERB_KDC_REQUEST_BODY_encryption_type_s@@@Z; KerberosCryptoPolicy::EtypeListToCommaSeparatedString(KERB_KDC_REQUEST_BODY_encryption_type_s const *)
0x18000d72b  xor     r15d, r15d
0x18000d72e  mov     rdx, rax
0x18000d731  lea     rcx, [rbp+430h+var_360]
0x18000d738  cmp     byte ptr [rbp+430h+var_340], r15b
0x18000d73f  jz      short loc_18000D748
0x18000d741  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000d746  jmp     short loc_18000D754
0x18000d748  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000d74d  mov     byte ptr [rbp+430h+var_340], 1
0x18000d754  lea     rcx, [rbp+430h+var_80]
0x18000d75b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000d760  mov     ecx, [rbx+90h]
0x18000d766  mov     [rbp+430h+var_45C], ecx
0x18000d769  test    ecx, ecx
0x18000d76b  jz      short loc_18000D778
0x18000d76d  mov     eax, [rbx+84h]
0x18000d773  mov     [rbp+430h+var_4A8], eax
0x18000d776  jmp     short loc_18000D77C
0x18000d778  mov     [rbp+430h+var_4A8], r15d
0x18000d77c  mov     eax, [rbx+6Ch]
0x18000d77f  mov     [rbp+430h+var_460], eax
0x18000d782  jmp     short loc_18000D787
0x18000d784  xor     r15d, r15d
0x18000d787  mov     rbx, [rbp+430h+pSid]
0x18000d78b  test    rbx, rbx
0x18000d78e  jz      short loc_18000D79D
0x18000d790  mov     rcx, rbx; pSid
0x18000d793  call    cs:__imp_IsValidSid
0x18000d799  test    eax, eax
0x18000d79b  jnz     short loc_18000D7A1
0x18000d79d  mov     [rbp+430h+pSid], r15
0x18000d7a1  mov     [rbp+430h+var_49C], r15d
0x18000d7a5  mov     [rbp+430h+var_388], r15
0x18000d7ac  lea     r8, [rbp+430h+var_388]; unsigned __int8 **
0x18000d7b3  lea     rdx, [rbp+430h+var_49C]; unsigned int *
0x18000d7b7  mov     rcx, [rbp+430h+var_430]; struct sockaddr *
0x18000d7bb  call    ?GetClientAddressBuffer@@YAXQEAUsockaddr@@AEAKAEAPEAE@Z; GetClientAddressBuffer(sockaddr * const,ulong &,uchar * &)
0x18000d7c0  mov     [rbp+430h+var_468], r15d
0x18000d7c4  mov     [rbp+430h+var_46C], r15d
0x18000d7c8  mov     [rbp+430h+var_458], r15d
0x18000d7cc  mov     [rbp+430h+var_3A0], r15
0x18000d7d3  mov     [rbp+430h+var_3A8], r15
0x18000d7da  mov     [rbp+430h+var_398], r15
0x18000d7e1  mov     [rbp+430h+var_390], r15
0x18000d7e8  test    rsi, rsi
0x18000d7eb  jz      loc_18000D923
0x18000d7f1  mov     r15d, [rsi+48h]
0x18000d7f5  mov     [rbp+430h+var_450], r15d
0x18000d7f9  mov     eax, [rsi+40h]
0x18000d7fc  mov     [rbp+430h+var_474], eax
0x18000d7ff  mov     eax, [rsi+3Ch]
0x18000d802  mov     [rbp+430h+var_478], eax
0x18000d805  lea     r8, [rbp+430h+var_1E8]; struct _UNICODE_STRING *
0x18000d80c  mov     edx, r15d; unsigned int
0x18000d80f  mov     rcx, [rsi+50h]; unsigned __int8 *
0x18000d813  call    ?KdcHashTicketEncryptedPart@@YAXPEAEKPEAU_UNICODE_STRING@@@Z; KdcHashTicketEncryptedPart(uchar *,ulong,_UNICODE_STRING *)
0x18000d818  lea     r8, [rsi+28h]
0x18000d81c  lea     rdx, [rbp+430h+var_468]
0x18000d820  lea     rcx, [rbp+430h+var_228]
0x18000d827  call    KerbConvertPrincipalNameToString
0x18000d82c  lea     rdx, [rsi+20h]
0x18000d830  lea     rcx, [rbp+430h+var_238]
0x18000d837  call    KerbConvertRealmToUnicodeString
0x18000d83c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties> `wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties>::GetImpl(void)'::`2'::impl
0x18000d843  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberosAddTgtProperties>::__private_IsEnabled(void)
0x18000d848  xor     r15d, r15d
0x18000d84b  test    al, al
0x18000d84d  jz      loc_18000D92F
0x18000d853  lea     rdx, [rbp+430h+var_4B0]; struct KERB_ENCRYPTED_TICKET **
0x18000d857  lea     rcx, [rsi+18h]; struct KERB_TICKET *
0x18000d85b  call    ?DecryptTgt@@YAJPEAUKERB_TICKET@@PEAPEAUKERB_ENCRYPTED_TICKET@@@Z; DecryptTgt(KERB_TICKET *,KERB_ENCRYPTED_TICKET * *)
0x18000d860  test    eax, eax
0x18000d862  jnz     loc_18000D92F
0x18000d868  mov     r8, [rbp+430h+var_4B0]
0x18000d86c  test    r8, r8
0x18000d86f  jz      loc_18000D92F
0x18000d875  add     r8, 38h ; '8'
0x18000d879  lea     rdx, [rbp+430h+var_46C]
0x18000d87d  lea     rcx, [rbp+430h+var_248]
0x18000d884  call    KerbConvertPrincipalNameToString
0x18000d889  mov     rdx, [rbp+430h+var_4B0]
0x18000d88d  add     rdx, 30h ; '0'
0x18000d891  lea     rcx, [rbp+430h+var_258]
0x18000d898  call    KerbConvertRealmToUnicodeString
0x18000d89d  mov     rcx, [rbp+430h+var_4B0]
0x18000d8a1  add     rcx, 6Eh ; 'n'
0x18000d8a5  call    KerbConvertGeneralizedTimeToFileTime
0x18000d8aa  mov     [rbp+430h+var_3A0], rax
0x18000d8b1  mov     rcx, [rbp+430h+var_4B0]
0x18000d8b5  add     rcx, 7Ch ; '|'
0x18000d8b9  call    KerbConvertGeneralizedTimeToFileTime
0x18000d8be  mov     [rbp+430h+var_3A8], rax
0x18000d8c5  mov     rcx, [rbp+430h+var_4B0]
0x18000d8c9  add     rcx, 8Ah
0x18000d8d0  call    KerbConvertGeneralizedTimeToFileTime
0x18000d8d5  mov     [rbp+430h+var_398], rax
0x18000d8dc  mov     rcx, [rbp+430h+var_4B0]
0x18000d8e0  add     rcx, 60h ; '`'
0x18000d8e4  call    KerbConvertGeneralizedTimeToFileTime
0x18000d8e9  mov     [rbp+430h+var_390], rax
0x18000d8f0  mov     rcx, [rbp+430h+var_4B0]
0x18000d8f4  add     rcx, 8; struct tagASN1bitstring_t *
0x18000d8f8  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18000d8fd  mov     [rbp+430h+var_458], eax
0x18000d900  lea     rdx, [rbp+430h+var_1C0]; struct _PAC_AUDIT_INFO *
0x18000d907  mov     rcx, [rbp+430h+var_4B0]; struct KERB_ENCRYPTED_TICKET *
0x18000d90b  call    ?FillPacAuditInfo@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAU_PAC_AUDIT_INFO@@@Z; FillPacAuditInfo(KERB_ENCRYPTED_TICKET *,_PAC_AUDIT_INFO *)
0x18000d910  lea     r8, [rbp+430h+var_4A0]; int *
0x18000d914  lea     rdx, [rbp+430h+var_440]; void **
0x18000d918  mov     rcx, [rbp+430h+var_4B0]; struct KERB_ENCRYPTED_TICKET *
0x18000d91c  call    ?KdcGetRequestorIdFromTgtPac@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAPEAXPEAJ@Z; KdcGetRequestorIdFromTgtPac(KERB_ENCRYPTED_TICKET *,void * *,long *)
0x18000d921  jmp     short loc_18000D92F
0x18000d923  mov     [rbp+430h+var_450], r15d
0x18000d927  mov     [rbp+430h+var_478], r15d
0x18000d92b  mov     [rbp+430h+var_474], r15d
0x18000d92f  mov     [rbp+430h+var_4A0], r15d
0x18000d933  mov     [rbp+430h+var_470], r15d
0x18000d937  test    r14, r14
0x18000d93a  jz      short loc_18000D979
0x18000d93c  mov     esi, [r14+30h]
0x18000d940  mov     [rbp+430h+var_4A0], esi
0x18000d943  lea     r8, [rbp+430h+var_1F8]; struct _UNICODE_STRING *
0x18000d94a  mov     edx, esi; unsigned int
0x18000d94c  mov     rcx, [r14+38h]; unsigned __int8 *
0x18000d950  call    ?KdcHashTicketEncryptedPart@@YAXPEAEKPEAU_UNICODE_STRING@@@Z; KdcHashTicketEncryptedPart(uchar *,ulong,_UNICODE_STRING *)
0x18000d955  lea     r8, [r14+10h]
0x18000d959  lea     rdx, [rbp+430h+var_470]
0x18000d95d  lea     rcx, [rbp+430h+var_268]
0x18000d964  call    KerbConvertPrincipalNameToString
0x18000d969  lea     rdx, [r14+8]
0x18000d96d  lea     rcx, [rbp+430h+var_278]
0x18000d974  call    KerbConvertRealmToUnicodeString
0x18000d979  mov     [rbp+430h+var_3B0], r15
0x18000d980  mov     [rbp+430h+var_3B8], r15
0x18000d984  mov     rbx, [rbp+430h+var_438]
0x18000d988  test    rbx, rbx
0x18000d98b  jz      short loc_18000D9AA
0x18000d98d  lea     rcx, [rbx+5Eh]
0x18000d991  call    KerbConvertGeneralizedTimeToFileTime
0x18000d996  mov     [rbp+430h+var_3B0], rax
0x18000d99d  lea     rcx, [rbx+6Ch]
0x18000d9a1  call    KerbConvertGeneralizedTimeToFileTime
0x18000d9a6  mov     [rbp+430h+var_3B8], rax
0x18000d9aa  lea     rax, [rbp+430h+var_328]
0x18000d9b1  mov     [rbp+430h+var_338], rax
0x18000d9b8  lea     rax, [rbp+430h+var_328]
0x18000d9bf  mov     [rbp+430h+var_330], rax
0x18000d9c6  mov     [rbp+430h+var_328], r15w
0x18000d9ce  test    r12, r12
0x18000d9d1  jz      short loc_18000DA37
0x18000d9d3  cmp     [r12], r15d
0x18000d9d7  jbe     short loc_18000DA37
0x18000d9d9  mov     ebx, r15d
0x18000d9dc  mov     eax, ebx
0x18000d9de  lea     rcx, [rax+rax*2]
0x18000d9e2  mov     rax, [r12+8]
0x18000d9e7  mov     rdx, [rax+rcx*8+10h]
0x18000d9ec  test    rdx, rdx
0x18000d9ef  jz      short loc_18000DA2F
  ... truncated ...
```
