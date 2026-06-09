# I_GetTGSTicket(KERB_TICKET *,sockaddr *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,KERB_KDC_REQUEST_BODY *,_KDC_TICKET_INFO *,_KERB_ENCRYPTION_KEY *,_KDC_S4U_TICKET_INFO *,_KERB_ENCRYPTION_KEY *,uchar,_KDC_AP_REQUEST_INFO *,KERB_TICKET *,utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> *,KERB_KDC_REQUEST_preauth_data_s * *,KERB_EXT_ERROR *,_S4U_DELEGATION_INFO * *,_KDC_AUTH2_INFO *,_USER_INTERNAL6_INFORMATION * *,uchar *)

- ea: `0x180024ffc`
- end: `0x180026cfd`
- name: `?I_GetTGSTicket@@YAJPEAUKERB_TICKET@@PEAUsockaddr@@PEAU_UNICODE_STRING@@2PEAU_KERB_INTERNAL_NAME@@2PEAUKERB_KDC_REQUEST_BODY@@PEAU_KDC_TICKET_INFO@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_KDC_S4U_TICKET_INFO@@6EPEAU_KDC_AP_REQUEST_INFO@@0PEAV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAPEAUKERB_KDC_REQUEST_preauth_data_s@@PEAUKERB_EXT_ERROR@@PEAPEAU_S4U_DELEGATION_INFO@@PEAU_KDC_AUTH2_INFO@@PEAPEAU_USER_INTERNAL6_INFORMATION@@PEAE@Z`
- size: `7425`
- prototype: `__int64 __fastcall(KerberosCryptoPolicy *, __int64, __int64, __int64, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct KERB_KDC_REQUEST_BODY *, const UNICODE_STRING *, struct _KERB_ENCRYPTION_KEY *, struct _KDC_S4U_TICKET_INFO *, struct _KERB_ENCRYPTION_KEY *, char, struct _KDC_AP_REQUEST_INFO *, __int64, __int64 *, struct KERB_KDC_REQUEST_preauth_data_s **, struct KERB_EXT_ERROR *, struct _S4U_DELEGATION_INFO **, struct _KDC_AUTH2_INFO *, struct _USER_INTERNAL6_INFORMATION **, _BYTE *)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021eb4`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x180005cc0`
- `0x18000ab24`
- `0x18000ab40`
- `0x18000add0`
- `0x18000b6ac`
- `0x18000b6e0`
- `0x18000c25c`
- `0x18000e440`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180013d1c`
- `0x18001ab58`
- `0x18001fd80`
- `0x18001ff94`
- `0x180020380`
- `0x18002057c`
- `0x1800205bc`
- `0x180020fa8`
- `0x1800210a8`
- `0x180021400`
- `0x1800216cc`
- `0x180024ffc`
- `0x18002719c`
- `0x1800276cc`
- `0x180027a78`
- `0x180027b48`
- `0x180028d24`
- `0x18002b910`
- `0x18002bdf4`
- `0x18002d72c`
- `0x18002daac`
- `0x18002dc34`
- `0x1800306c8`
- `0x1800308ec`
- `0x180030e18`
- `0x180030ee0`
- `0x180047d28`
- `0x18005ad20`
- `0x18005c334`
- `0x18006349c`
- `0x180072338`
- `0x18007c574`
- `0x18007d714`
- `0x18007e35c`
- `0x180080a70`
- `0x180080b30`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18002653b`
- `ntdll!RtlEqualUnicodeString` at `0x1800265fc`
- `ntdll!RtlEqualUnicodeString` at `0x18002653b`
- `ntdll!RtlEqualUnicodeString` at `0x1800265fc`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x180025d96`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x180025d96`
- `AUTHZ!AuthzFreeContext` at `0x180025da3`
- `AUTHZ!AuthzFreeContext` at `0x180025dbe`
- `AUTHZ!AuthzFreeContext` at `0x180025da3`
- `AUTHZ!AuthzFreeContext` at `0x180025dbe`

## pseudocode

```c
__int64 __fastcall I_GetTGSTicket(
        KerberosCryptoPolicy *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct _KERB_INTERNAL_NAME *a5,
        struct _UNICODE_STRING *a6,
        struct KERB_KDC_REQUEST_BODY *a7,
        const UNICODE_STRING *a8,
        struct _KERB_ENCRYPTION_KEY *a9,
        struct _KDC_S4U_TICKET_INFO *a10,
        struct _KERB_ENCRYPTION_KEY *a11,
        char a12,
        struct _KDC_AP_REQUEST_INFO *a13,
        __int64 a14,
        __int64 *a15,
        struct KERB_KDC_REQUEST_preauth_data_s **a16,
        struct KERB_EXT_ERROR *a17,
        struct _S4U_DELEGATION_INFO **a18,
        struct _KDC_AUTH2_INFO *a19,
        struct _USER_INTERNAL6_INFORMATION **a20,
        _BYTE *a21)
{
  unsigned __int8 v21; // r12
  __int64 v22; // rdx
  __int64 v23; // r13
  unsigned int S4UTicketInfo; // ebx
  AUTHZ_CLIENT_CONTEXT_HANDLE v25; // r11
  unsigned int v26; // eax
  char v27; // r13
  unsigned int v28; // ebx
  bool IsAnyKrbtgt; // al
  __int64 v30; // r8
  const char *v31; // r9
  struct _USER_INTERNAL6_INFORMATION **v32; // r8
  void **v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // r8
  CSecurityData *v36; // rcx
  __int64 v37; // rdx
  UNICODE_STRING *v38; // rcx
  int v39; // edx
  char v40; // r10
  int v41; // edx
  CSecurityData *v42; // rcx
  __int64 v43; // rdx
  int v44; // edx
  CSecurityData *v45; // rcx
  unsigned __int8 IsOurRealm; // al
  int v47; // eax
  unsigned __int8 v48; // r8
  int v49; // edx
  int v50; // ecx
  int v51; // r9d
  int v52; // edx
  int v53; // r9d
  int v54; // ecx
  int v55; // edx
  char v56; // r12
  struct _USER_INTERNAL6_INFORMATION **v57; // rax
  struct _USER_INTERNAL6_INFORMATION *v58; // rdx
  KerberosCryptoPolicy *v59; // r9
  bool v60; // r14
  char v61; // r13
  struct _USER_INTERNAL6_INFORMATION *v62; // rax
  __int16 v63; // dx
  unsigned __int8 v64; // bl
  int v65; // r9d
  int v66; // ecx
  AUTHZ_CLIENT_CONTEXT_HANDLE v67; // r12
  AUTHZ_CLIENT_CONTEXT_HANDLE v68; // r13
  CSecurityData *v69; // rcx
  __int64 v70; // rdx
  unsigned int v71; // eax
  int v72; // edx
  int v73; // ecx
  AUTHZ_CLIENT_CONTEXT_HANDLE v74; // rcx
  unsigned __int8 v75; // al
  int v76; // edx
  struct _USER_INTERNAL6_INFORMATION **v77; // rdx
  unsigned int v78; // eax
  void *v79; // rdx
  CSecurityData *v80; // r9
  int v81; // eax
  int v82; // edx
  void *v83; // rdx
  int v84; // r13d
  KerberosCryptoPolicy *v85; // r12
  unsigned int v86; // eax
  struct _USER_INTERNAL6_INFORMATION **v87; // r14
  struct KERB_KDC_REQUEST_BODY *v88; // r13
  __int64 v89; // rcx
  KerberosCryptoPolicy *v90; // rdx
  _QWORD *v91; // rcx
  CSecurityData *v92; // rcx
  __int64 v93; // r13
  int v94; // edx
  __int64 v95; // rcx
  KerberosCryptoPolicy *v96; // rdx
  struct _USER_INTERNAL6_INFORMATION ***v97; // rax
  char v98; // bl
  CSecurityData *v99; // rcx
  __int64 v100; // rdx
  __int128 v101; // xmm0
  bool v102; // al
  struct _SAM_CLAIMS_BLOB *v103; // rdx
  struct _KDC_TICKET_INFO *v104; // rcx
  unsigned __int8 v105; // r8
  unsigned int inserted; // eax
  struct _KDC_AUTH2_INFO *v107; // rdi
  struct KERB_ENCRYPTED_DATA *v108; // r8
  __int64 v109; // rbx
  __m256i *v110; // rcx
  struct KERB_KDC_REQUEST_preauth_data_s **v112; // [rsp+30h] [rbp-D0h]
  char v113; // [rsp+80h] [rbp-80h]
  unsigned __int8 v114[15]; // [rsp+81h] [rbp-7Fh] BYREF
  PCUNICODE_STRING String2[2]; // [rsp+90h] [rbp-70h] BYREF
  char v116; // [rsp+A0h] [rbp-60h]
  char v117; // [rsp+A1h] [rbp-5Fh]
  int v118; // [rsp+A4h] [rbp-5Ch] BYREF
  KerberosCryptoPolicy *v119; // [rsp+A8h] [rbp-58h] BYREF
  char v120; // [rsp+B0h] [rbp-50h]
  struct _USER_INTERNAL6_INFORMATION **v121; // [rsp+B8h] [rbp-48h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+C0h] [rbp-40h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE v123; // [rsp+C8h] [rbp-38h] BYREF
  int v124[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v125; // [rsp+D8h] [rbp-28h]
  struct KERB_KDC_REQUEST_BODY *v126; // [rsp+E0h] [rbp-20h]
  struct _USER_INTERNAL6_INFORMATION *v127; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v128; // [rsp+F0h] [rbp-10h] BYREF
  int v129[2]; // [rsp+F8h] [rbp-8h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s **v130; // [rsp+100h] [rbp+0h] BYREF
  void *v131; // [rsp+108h] [rbp+8h] BYREF
  struct _KERB_ENCRYPTION_KEY *v132; // [rsp+110h] [rbp+10h]
  struct _KDC_AP_REQUEST_INFO *v133; // [rsp+118h] [rbp+18h]
  struct _UNICODE_STRING v134; // [rsp+120h] [rbp+20h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp+30h] BYREF
  struct _KDC_AUTH2_INFO *v136; // [rsp+140h] [rbp+40h]
  __int64 v137; // [rsp+148h] [rbp+48h]
  __int128 v138; // [rsp+150h] [rbp+50h] BYREF
  __int128 v139; // [rsp+160h] [rbp+60h] BYREF
  struct _KERB_ENCRYPTION_KEY *v140[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 *v141; // [rsp+180h] [rbp+80h]
  __m256i *v142; // [rsp+188h] [rbp+88h]
  struct _S4U_DELEGATION_INFO **v143; // [rsp+190h] [rbp+90h]
  struct _UNICODE_STRING v144; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v145; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v146; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v147; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v148; // [rsp+1D8h] [rbp+D8h]
  __int128 v149; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v150; // [rsp+1F0h] [rbp+F0h]
  __int128 v151; // [rsp+200h] [rbp+100h]
  __int128 v152; // [rsp+210h] [rbp+110h]
  __int64 v153; // [rsp+220h] [rbp+120h]
  __int128 v154; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v155[4]; // [rsp+240h] [rbp+140h] BYREF
  UNICODE_STRING v156; // [rsp+280h] [rbp+180h] BYREF
  char v157[24]; // [rsp+290h] [rbp+190h] BYREF
  int v158; // [rsp+2A8h] [rbp+1A8h]
  int v159; // [rsp+2B0h] [rbp+1B0h]
  int v160; // [rsp+2BCh] [rbp+1BCh]
  int v161; // [rsp+2D1h] [rbp+1D1h]
  __int16 v162; // [rsp+2D5h] [rbp+1D5h]
  char v163; // [rsp+2D7h] [rbp+1D7h]
  char v164; // [rsp+2E8h] [rbp+1E8h]
  __int16 v165; // [rsp+2E9h] [rbp+1E9h]
  char v166; // [rsp+2EBh] [rbp+1EBh]
  int v167; // [rsp+2F4h] [rbp+1F4h]
  __int64 v168; // [rsp+318h] [rbp+218h] BYREF
  __int128 v169; // [rsp+320h] [rbp+220h]
  _QWORD v170[15]; // [rsp+330h] [rbp+230h] BYREF
  char v171; // [rsp+3A8h] [rbp+2A8h]
  __int128 v172; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v173; // [rsp+3C0h] [rbp+2C0h]
  char v174[8]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v175; // [rsp+3D8h] [rbp+2D8h]
  int v176; // [rsp+40Ch] [rbp+30Ch]
  int v177; // [rsp+421h] [rbp+321h]
  __int16 v178; // [rsp+425h] [rbp+325h]
  char v179; // [rsp+427h] [rbp+327h]
  __int16 v180; // [rsp+439h] [rbp+339h]
  char v181; // [rsp+43Bh] [rbp+33Bh]
  int v182; // [rsp+444h] [rbp+344h]
  __int64 v183; // [rsp+468h] [rbp+368h] BYREF
  __int128 v184; // [rsp+470h] [rbp+370h]
  _OWORD v185[4]; // [rsp+480h] [rbp+380h] BYREF
  __int64 v186; // [rsp+4C0h] [rbp+3C0h]
  _BYTE v187[60]; // [rsp+4C8h] [rbp+3C8h] BYREF
  int v188; // [rsp+504h] [rbp+404h]
  int v189; // [rsp+519h] [rbp+419h]
  __int16 v190; // [rsp+51Dh] [rbp+41Dh]
  char v191; // [rsp+51Fh] [rbp+41Fh]
  __int16 v192; // [rsp+531h] [rbp+431h]
  char v193; // [rsp+533h] [rbp+433h]
  int v194; // [rsp+53Ch] [rbp+43Ch]
  __int128 v195; // [rsp+560h] [rbp+460h] BYREF
  __int64 v196; // [rsp+570h] [rbp+470h]
  _BYTE v197[56]; // [rsp+580h] [rbp+480h] BYREF
  __int64 v198; // [rsp+5B8h] [rbp+4B8h]
  _BYTE v199[80]; // [rsp+5D0h] [rbp+4D0h] BYREF
  __m256i v200; // [rsp+620h] [rbp+520h] BYREF
  __int128 v201; // [rsp+640h] [rbp+540h]
  __int128 v202; // [rsp+650h] [rbp+550h]
  __int128 v203; // [rsp+660h] [rbp+560h]
  __int128 v204; // [rsp+670h] [rbp+570h]
  __int128 v205; // [rsp+680h] [rbp+580h]
  __int128 v206; // [rsp+690h] [rbp+590h]
  __int128 v207; // [rsp+6A0h] [rbp+5A0h]
  __int128 v208; // [rsp+6B0h] [rbp+5B0h]
  __int64 v209; // [rsp+6C0h] [rbp+5C0h]

  *(_QWORD *)v124 = a4;
  *(_QWORD *)v129 = a3;
  v119 = a1;
  v121 = a20;
  v132 = a9;
  v136 = a19;
  v126 = a7;
  String2[0] = a8;
  v140[0] = a11;
  v133 = a13;
  v137 = a14;
  v141 = a15;
  v130 = a16;
  v143 = a18;
  v125 = 0;
  v154 = 0;
  v134 = 0;
  String1 = 0;
  v114[0] = 0;
  memset_0(&v200, 0, 0xA8u);
  memset_0(&v149, 0, 0x48u);
  *(_QWORD *)&v156.Length = 0;
  v156.Buffer = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  v165 = 0;
  v166 = 0;
  v167 = 0;
  memset_0(v157, 0, 0x88u);
  v168 = 0;
  v169 = 0;
  v139 = 0;
  v127 = 0;
  v128 = 0;
  v21 = KerbEqualKdcNames(a5, xmmword_1800B2E20);
  v146 = 0;
  LOBYTE(v22) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSubAuth>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_EnableSubAuth>::GetImpl'::`2'::impl,
    v22);
  v120 = IsSubAuthFilterPresent();
  hAuthzClientContext = 0;
  v147 = 0;
  v148 = 0;
  v172 = 0;
  v173 = 0;
  memset_0(v197, 0, 0x50u);
  v145 = 0;
  v144 = 0;
  memset(v155, 0, 56);
  v131 = 0;
  v176 = 0;
  v177 = 0;
  v178 = 0;
  v179 = 0;
  v180 = 0;
  v181 = 0;
  v182 = 0;
  memset_0(v174, 0, 0x98u);
  v183 = 0;
  v184 = 0;
  v138 = 0;
  v170[0] = &v156;
  v170[1] = &v139;
  v170[2] = &v127;
  v170[3] = &v149;
  v170[4] = &v134;
  v170[5] = &String1;
  v170[6] = &v128;
  v170[7] = &v146;
  v170[8] = &hAuthzClientContext;
  v170[9] = v197;
  v170[10] = &v131;
  v170[11] = &v145;
  v170[12] = &v144;
  v170[13] = v174;
  v170[14] = &v138;
  v171 = 1;
  *a20 = 0;
  *a21 = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v133);
  }
  v23 = *(_QWORD *)(v137 + 56);
  v142 = (__m256i *)v23;
  *((_QWORD *)&v152 + 1) = &v200;
  S4UTicketInfo = KerbConvertRealmToUnicodeString(&String1, *((_QWORD *)v119 + 7) + 48LL);
  LOBYTE(v25) = 0;
  if ( S4UTicketInfo )
    goto LABEL_376;
  *(_OWORD *)&v200.m256i_u64[1] = *(_OWORD *)(v23 + 8);
  *((_QWORD *)&v154 + 1) = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, a5);
  v26 = KerbConvertFlagsToUlong((struct KERB_KDC_REQUEST_BODY *)((char *)v126 + 8));
  v27 = v26;
  v125 = v26;
  if ( (v26 & 0x81400000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67375447,
        v26);
    S4UTicketInfo = 13;
    goto LABEL_13;
  }
  v28 = 52;
  if ( *(_WORD *)a5 != 10 )
    v28 = 22;
  IsAnyKrbtgt = _KDC_TICKET_INFO::IsAnyKrbtgt((_KDC_TICKET_INFO *)String2[0]);
  LOBYTE(v25) = 0;
  if ( !IsAnyKrbtgt )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v30);
      LOBYTE(v25) = 0;
    }
    S4UTicketInfo = 35;
    goto LABEL_376;
  }
  _KDC_TICKET_INFO::operator=(&v156, v30);
  v188 = 0;
  v189 = 0;
  v190 = 0;
  v191 = 0;
  v192 = 0;
  v193 = 0;
  v194 = 0;
  memset_0(v187, 0, 0x98u);
  v195 = 0;
  v196 = 0;
  _KDC_TICKET_INFO::operator=(String2[0], v187);
  std::vector<unsigned int>::_Tidy((__int64)&v195);
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
  {
    v31 = "TRUE";
    if ( (v27 & 8) == 0 )
      v31 = "FALSE";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v31);
  }
  v32 = 0;
  if ( !v21 )
    v32 = v121;
  v33 = (void **)&v128;
  if ( v21 )
    v33 = 0;
  v34 = KdcNormalize(
          a5,
          0,
          a6,
          &String1,
          v28,
          v132 == 0,
          0,
          v114,
          &v134,
          (struct _KDC_TICKET_INFO *)String2[0],
          a17,
          v33,
          0x10000000u,
          v132 != 0 ? 33556480 : 33556484,
          v32,
          0);
  S4UTicketInfo = v34;
  v25 = 0;
  if ( v34 )
  {
    if ( KdcGlobalCDC && v34 == -2147483642 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
        goto LABEL_13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          137,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67375519,
          -2147483642);
        v36 = WPP_GLOBAL_Control;
      }
      if ( v36 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v36 + 28) & 2) == 0 )
        goto LABEL_13;
      v37 = 138;
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
        goto LABEL_13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67375514,
          v34);
        v36 = WPP_GLOBAL_Control;
      }
      if ( v36 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v36 + 28) & 2) == 0 )
        goto LABEL_13;
      v37 = 136;
    }
    WPP_SF__KERB_NAME_(*((_QWORD *)v36 + 2), v37, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, a5);
    goto LABEL_13;
  }
  v38 = (UNICODE_STRING *)String2[0];
  if ( String2[0]
    && *(_DWORD *)&String2[0][3].Length != 502
    && !LOBYTE(String2[0][6].Buffer)
    && (BYTE4(String2[0][2].Buffer) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 67375541);
    FillExtendedError(-1073741710, 1, 1028, 4534, a17);
    S4UTicketInfo = v39 + 6;
    goto LABEL_376;
  }
  v40 = 0;
  v113 = 0;
  v41 = *((_DWORD *)a10 + 74);
  if ( (v41 & 0x1000) != 0 )
  {
    if ( v114[0] )
    {
      if ( (v41 & 2) != 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
          goto LABEL_98;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          v42 = WPP_GLOBAL_Control;
        }
        if ( v42 == (CSecurityData *)&WPP_GLOBAL_Control )
          goto LABEL_98;
        if ( (*((_BYTE *)v42 + 28) & 1) != 0 )
        {
          WPP_SF_Z(*((_QWORD *)v42 + 2), 141, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, (char *)a10 + 8);
          v42 = WPP_GLOBAL_Control;
        }
        if ( v42 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v42 + 28) & 1) == 0 )
          goto LABEL_98;
        v43 = 142;
LABEL_97:
        WPP_SF_Z(*((_QWORD *)v42 + 2), v43, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v134);
LABEL_98:
        S4UTicketInfo = 36;
        goto LABEL_13;
      }
    }
    else
    {
      v44 = v41 | 4;
      *((_DWORD *)a10 + 74) = v44;
      if ( (v44 & 2) == 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
          goto LABEL_98;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          v42 = WPP_GLOBAL_Control;
        }
        if ( v42 == (CSecurityData *)&WPP_GLOBAL_Control )
          goto LABEL_98;
        if ( (*((_BYTE *)v42 + 28) & 1) != 0 )
        {
          WPP_SF_Z(*((_QWORD *)v42 + 2), 146, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, (char *)a10 + 8);
          v42 = WPP_GLOBAL_Control;
        }
        if ( v42 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v42 + 28) & 1) == 0 )
          goto LABEL_98;
        v43 = 147;
        goto LABEL_97;
      }
      if ( *((_DWORD *)a10 + 18) != *(_DWORD *)&v38[3].Length && (v44 & 0x200000) == 0 )
      {
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
            v45 = WPP_GLOBAL_Control;
          }
          if ( v45 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 1) != 0 )
            WPP_SF_qq(*((_QWORD *)v45 + 2), 144, v35, (char *)a10 + 24, String2);
        }
        goto LABEL_98;
      }
    }
    IsOurRealm = CSecurityData::IsOurRealm((CSecurityData *)v38, (struct _UNICODE_STRING *)((char *)a10 + 232));
    v25 = 0;
    if ( IsOurRealm )
    {
      v40 = 1;
      v113 = 1;
      v38 = (UNICODE_STRING *)String2[0];
    }
    else
    {
      if ( (*((_DWORD *)a10 + 74) & 0x200000) != 0 )
      {
        S4UTicketInfo = 6;
        goto LABEL_376;
      }
      v38 = (UNICODE_STRING *)String2[0];
      v40 = 0;
    }
  }
  v47 = *((_DWORD *)a10 + 74);
  v48 = v114[0];
  if ( (v47 & 0x2000) != 0 )
  {
    v49 = v47 & 0x10000;
    if ( v114[0] && !v49 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v134);
      v50 = -1073740789;
      v51 = 4618;
      goto LABEL_87;
    }
    if ( !KdcGlobalEnableA2DFCheck && v49 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      v53 = 4626;
LABEL_105:
      v54 = -1073741275;
LABEL_106:
      FillExtendedError(v54, 3, 1028, v53, a17);
      S4UTicketInfo = v55 + 10;
      goto LABEL_376;
    }
    if ( !v114[0] )
    {
      if ( v49 && (BYTE4(v38[2].Buffer) & 0x40) != 0 || v21 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        v53 = 4637;
        goto LABEL_105;
      }
      *((_DWORD *)a10 + 74) = v47 | 4;
      v56 = 0;
      v116 = 0;
      goto LABEL_118;
    }
    *((_DWORD *)a10 + 74) = v47 & 0xFFFFFDFF;
  }
  v56 = 0;
  v116 = 0;
  if ( v48 )
  {
    v59 = v119;
    goto LABEL_126;
  }
LABEL_118:
  v57 = v121;
  v58 = *v121;
  v59 = v119;
  if ( !*v121 || !*((_QWORD *)v58 + 73) || (BYTE4(v38[2].Buffer) & 0x40) != 0 )
    goto LABEL_127;
  if ( (**((_BYTE **)v119 + 7) & 0x10) != 0 )
  {
    v56 = 1;
    v116 = 1;
  }
  else if ( *((_BYTE *)v58 + 568) )
  {
    v50 = -1073740781;
    v51 = 4665;
LABEL_87:
    FillExtendedError(v50, 3, 1028, v51, a17);
    S4UTicketInfo = v52 + 9;
    goto LABEL_376;
  }
LABEL_126:
  v57 = v121;
LABEL_127:
  v60 = 0;
  v61 = 0;
  v117 = 0;
  if ( !v48 )
  {
    v62 = *v57;
    if ( v62 )
    {
      if ( *((_QWORD *)v62 + 33) && (BYTE4(v38[2].Buffer) & 0x40) == 0 )
      {
        v63 = **((_WORD **)v59 + 7) & 0x10;
        if ( v63 && !_KDC_TICKET_INFO::IsLocalKrbtgt((_KDC_TICKET_INFO *)v38) )
          v60 = (*(_DWORD *)&v38[7].Length & 0x400) == 0;
        if ( (*((_DWORD *)a10 + 74) & 0x12000) == 0x12000 )
        {
          if ( !v63 )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
            v53 = 4726;
            goto LABEL_105;
          }
          v61 = 1;
          v117 = 1;
        }
      }
    }
  }
  if ( v40 || v60 || v56 || v61 || v120 != (_BYTE)v25 )
  {
    if ( (*((_DWORD *)a10 + 74) & 0x1000) == 0 || (v64 = 1, v40) )
      v64 = (unsigned __int8)v25;
    v118 = (int)v25;
    v123 = v25;
    memset_0(v199, 0, sizeof(v199));
    S4UTicketInfo = KdcBuildAuthzContext(
                      (struct _KDC_TICKET_INFO *)&v156,
                      *((struct KERB_ENCRYPTED_TICKET **)v119 + 7),
                      v64,
                      &hAuthzClientContext,
                      &v147,
                      (struct _KDC_AUTHZ_GROUP_BUFFERS *)v197,
                      &v118,
                      &v145,
                      &v144,
                      &v131);
    v25 = 0;
    if ( S4UTicketInfo )
    {
      if ( v113 || v60 || v56 || v61 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            152,
            WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
            (unsigned int)v118);
        }
        v65 = 4780;
LABEL_154:
        v66 = v118;
        goto LABEL_155;
      }
LABEL_182:
      v38 = (UNICODE_STRING *)String2[0];
      goto LABEL_183;
    }
    if ( v133 )
    {
      S4UTicketInfo = KdcBuildAuthzContext(
                        (struct _KDC_AP_REQUEST_INFO *)((char *)v133 + 144),
                        *((struct KERB_ENCRYPTED_TICKET **)v133 + 2),
                        0,
                        &v123,
                        &v172,
                        (struct _KDC_AUTHZ_GROUP_BUFFERS *)v199,
                        &v118,
                        0,
                        0,
                        0);
      v25 = 0;
      if ( S4UTicketInfo )
      {
        if ( v113 || v60 || v56 || v61 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              153,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              (unsigned int)v118);
          }
          v65 = 4822;
          goto LABEL_154;
        }
        goto LABEL_182;
      }
      v67 = hAuthzClientContext;
      v68 = v123;
      if ( v123 && (unsigned int)AuthzInitializeCompoundContext(hAuthzClientContext, v123, &hAuthzClientContext) )
        AuthzFreeContext(v67);
      else
        hAuthzClientContext = v67;
      KdcFreeAuthzInfo((struct _KDC_AUTHZ_GROUP_BUFFERS *)v199);
      AuthzFreeContext(v68);
      v56 = v116;
      v25 = 0;
    }
    if ( v113 )
    {
      S4UTicketInfo = KdcGetS4UTicketInfo(
                        a10,
                        hAuthzClientContext,
                        &v127,
                        (struct _SID_AND_ATTRIBUTES_LIST *)&v139,
                        a17,
                        (struct _SAM_CLAIMS_BLOB *)&v146,
                        (struct _KDC_TICKET_INFO *)v174);
      v25 = 0;
      if ( S4UTicketInfo )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_376;
        }
        v70 = 154;
        goto LABEL_172;
      }
    }
    v61 = v117;
    goto LABEL_182;
  }
LABEL_183:
  if ( (*((_DWORD *)a10 + 74) & 0x200000) != 0 )
  {
    if ( !v127 )
    {
      S4UTicketInfo = 60;
      goto LABEL_376;
    }
    v71 = KdcDmsaTgsReqWorker(
            (struct _KDC_TICKET_INFO *)v38,
            a10,
            v127,
            (struct _KDC_TICKET_INFO *)v174,
            (struct _SID_AND_ATTRIBUTES_LIST *)&v139,
            a17,
            v130,
            (struct _SID_AND_ATTRIBUTES_LIST *)&v138);
    S4UTicketInfo = v71;
    if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 2) != 0 )
      McTemplateU0zzd_EtwEventWriteTransfer(v73, v72, v175, *((_QWORD *)a10 + 4), v71);
    v25 = 0;
    if ( S4UTicketInfo )
    {
      v69 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_376;
      v70 = 155;
LABEL_172:
      WPP_SF_d(*((_QWORD *)v69 + 2), v70, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, S4UTicketInfo);
      goto LABEL_13;
    }
    v38 = (UNICODE_STRING *)String2[0];
  }
  if ( !v56 )
    goto LABEL_207;
  v118 = (int)v25;
  v74 = hAuthzClientContext;
  if ( hAuthzClientContext )
  {
    v75 = CSecurityData::IsOurRealm((CSecurityData *)hAuthzClientContext, (char **)(*((_QWORD *)v119 + 7) + 48LL));
    v25 = 0;
    if ( v75 )
    {
      v76 = *(_DWORD *)(v198 + 148);
      if ( v76 == 500 )
      {
LABEL_206:
        v38 = (UNICODE_STRING *)String2[0];
        goto LABEL_207;
      }
      v38 = (UNICODE_STRING *)String2[0];
      if ( v76 == *(_DWORD *)&String2[0][3].Length )
      {
LABEL_207:
        v77 = v121;
        goto LABEL_208;
      }
    }
    v74 = hAuthzClientContext;
  }
  S4UTicketInfo = KdcPerformA2DFAccessCheck(v74, *((PSECURITY_DESCRIPTOR *)*v121 + 73), &v118);
  v25 = 0;
  if ( !S4UTicketInfo )
    goto LABEL_206;
  v77 = v121;
  if ( *((_BYTE *)*v121 + 568) )
  {
    if ( S4UTicketInfo != 12 )
      goto LABEL_376;
    v66 = v118;
    if ( v118 != -1073740781 && v118 != -1073741413 )
      goto LABEL_376;
    v65 = 4915;
    goto LABEL_155;
  }
  S4UTicketInfo = 0;
  v38 = (UNICODE_STRING *)String2[0];
LABEL_208:
  if ( v60 )
  {
    v118 = (int)v25;
    v78 = KdcPerformA2AAccessCheck(
            hAuthzClientContext,
            (struct _KDC_AUTHZ_INFO *)&v147,
            *((unsigned __int8 **)*v77 + 33),
            &v118);
    S4UTicketInfo = v78;
    v25 = 0;
    if ( v78 )
    {
      if ( v78 != 12 )
        goto LABEL_376;
      v66 = v118;
      if ( v118 != -1073740781 && v118 != -1073741413 )
        goto LABEL_376;
      v65 = 4973;
LABEL_155:
      FillExtendedError(v66, 3, 1028, v65, a17);
      goto LABEL_376;
    }
    v38 = (UNICODE_STRING *)String2[0];
  }
  if ( v61 )
  {
    v118 = (int)v25;
    v79 = (void *)*((_QWORD *)*v121 + 65);
    if ( v79 )
    {
      S4UTicketInfo = KdcPerformA2DFAccessCheck(hAuthzClientContext, v79, &v118);
      v25 = 0;
      if ( !S4UTicketInfo )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          v25 = 0;
        }
        *((_DWORD *)a10 + 74) &= 0xFFFEFDFF;
        *((_DWORD *)a10 + 74) |= 0x40000u;
        v38 = (UNICODE_STRING *)String2[0];
        goto LABEL_237;
      }
      v80 = WPP_GLOBAL_Control;
      v81 = v118;
      v38 = (UNICODE_STRING *)String2[0];
    }
    else
    {
      v80 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        v80 = WPP_GLOBAL_Control;
        v38 = (UNICODE_STRING *)String2[0];
        v25 = 0;
      }
      S4UTicketInfo = 13;
      v81 = -1073741275;
    }
    v82 = *((_DWORD *)a10 + 74);
    if ( (v82 & 0x200) != 0 )
    {
      if ( v80 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v80 + 28) < 0 )
      {
        WPP_SF_(*((_QWORD *)v80 + 2), 158, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        v38 = (UNICODE_STRING *)String2[0];
        v25 = 0;
      }
      *((_DWORD *)a10 + 74) &= ~0x10000u;
    }
    else if ( (v82 & 0x10000) != 0 )
    {
      if ( v81 != -1073740781 && v81 != -1073741413 )
        v81 = -1073741275;
      v53 = 5022;
      v54 = v81;
      goto LABEL_106;
    }
  }
LABEL_237:
  if ( v120 == (_BYTE)v25 )
  {
    v85 = v119;
    v84 = v124[0];
  }
  else
  {
    if ( (_QWORD)v147 )
      v83 = *(void **)v147;
    else
      v83 = v25;
    LODWORD(v155[0]) = 2;
    *(UNICODE_STRING *)((char *)v155 + 8) = *v38;
    *(struct _UNICODE_STRING *)((char *)&v155[1] + 8) = stru_1800B2D60;
    v84 = v124[0];
    *(_OWORD *)((char *)&v155[2] + 8) = **(_OWORD **)v124;
    if ( v131 )
      v83 = v131;
    v85 = v119;
    v86 = KdcCallSubAuthRoutineEx(
            *((struct KERB_ENCRYPTED_TICKET **)v119 + 7),
            v83,
            &v145,
            &v144,
            (struct _KDC_TARGET_INFO *)v155,
            a17);
    S4UTicketInfo = v86;
    LOBYTE(v25) = 0;
    if ( v86 )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_376;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67376054,
        v86);
LABEL_13:
      LOBYTE(v25) = 0;
      goto LABEL_376;
    }
    v38 = (UNICODE_STRING *)String2[0];
  }
  KerberosCryptoPolicy::FromKdcTicketInfo((KerberosCryptoPolicy **)&v121, (const struct _KDC_TICKET_INFO *)v38);
  v87 = v121;
  if ( !v121 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v121);
    S4UTicketInfo = 60;
    goto LABEL_13;
  }
  if ( (BYTE4(String2[0][2].Buffer) & 0x40) == 0 )
  {
    if ( !(unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v121, 2) )
    {
      KerberosCryptoPolicy::GetEncryptionAlgorithms((KerberosCryptoPolicy *)v87, &v123);
      KdcReportKeyErrorETypes(v129[0], v84, 9, -1073741808, v123, (__int64)String2[0], (__int64)v112);
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 67376112);
      utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v123);
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v121);
      S4UTicketInfo = 14;
      goto LABEL_13;
    }
    KerberosCryptoPolicy::Create((__int64 **)&v119);
    v88 = v126;
    if ( (!v119
       || !KerberosCryptoPolicy::SetRequestCiphers(
             v119,
             *((struct KERB_KDC_REQUEST_BODY_encryption_type_s **)v126 + 14)))
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    }
    KerberosCryptoPolicy::ApplySecondPartnerHandle((__int64)v87, (__int64 *)&v119);
    S4UTicketInfo = BuildTicketTGS(
                      (struct _KDC_TICKET_INFO *)String2[0],
                      v88,
                      v85,
                      v114[0],
                      a10,
                      (struct KerberosCryptoPolicy *)v87,
                      (struct KERB_TICKET *)&v149,
                      a17);
    v90 = v87[6];
    v87[6] = 0;
    if ( v90 )
      utl::default_delete<KerberosCryptoPolicy>::operator()(v89, v90);
    if ( S4UTicketInfo )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67376146,
          (__int64)&v154,
          S4UTicketInfo);
LABEL_271:
      v91 = &v119;
LABEL_272:
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v91);
LABEL_273:
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v121);
      goto LABEL_13;
    }
    goto LABEL_338;
  }
  v92 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, String2[0]);
    v92 = WPP_GLOBAL_Control;
  }
  v93 = *((_QWORD *)v85 + 7);
  if ( *(_DWORD *)&String2[0][3].Length != 502
    && !LOBYTE(String2[0][6].Buffer)
    && ((__int64)String2[0][2].Buffer & 0x400) == 0 )
  {
    if ( !CSecurityData::IsOurRealm(v92, (char **)(v93 + 48)) )
    {
      if ( (*((_DWORD *)a10 + 74) & 0x1000) == 0 )
      {
        v92 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_288;
        }
        v94 = 166;
        goto LABEL_287;
      }
      if ( !RtlEqualUnicodeString(&String1, String2[0], 1u) )
      {
        v92 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_288;
        }
        v94 = 165;
LABEL_287:
        WPP_SF_sZ(
          *((_QWORD *)v92 + 2),
          v94,
          (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          *(_QWORD *)(v93 + 48),
          (__int64)String2[0]);
        v92 = WPP_GLOBAL_Control;
LABEL_288:
        S4UTicketInfo = 28;
LABEL_293:
        v85 = v119;
        goto LABEL_294;
      }
    }
    v92 = WPP_GLOBAL_Control;
    goto LABEL_293;
  }
LABEL_294:
  if ( (v158 & 0x400) == 0 && !v164 && v159 != 502 )
  {
    if ( (*((_DWORD *)a10 + 74) & 0x1000) == 0 )
    {
      if ( v92 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v92 + 28) & 2) != 0 )
        WPP_SF_sZ(
          *((_QWORD *)v92 + 2),
          168,
          (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          *(_QWORD *)(v93 + 48),
          (__int64)&v156);
      goto LABEL_304;
    }
    if ( !RtlEqualUnicodeString(&String1, &v156, 1u) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          167,
          (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          *(_QWORD *)(v93 + 48),
          (__int64)&v156);
      S4UTicketInfo = 28;
    }
  }
  if ( S4UTicketInfo == 28 )
  {
LABEL_304:
    if ( String1.Buffer )
      ReportServiceEvent(1u, 0x8000000C, 0, 0, 2u, String1.Buffer, String2[0]->Buffer);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v121);
    S4UTicketInfo = 28;
    goto LABEL_13;
  }
  if ( !(unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v87, 2) )
  {
    S4UTicketInfo = 14;
    goto LABEL_314;
  }
  if ( S4UTicketInfo )
  {
    if ( S4UTicketInfo != 14 )
    {
LABEL_315:
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67376289,
          S4UTicketInfo);
      goto LABEL_273;
    }
LABEL_314:
    KerberosCryptoPolicy::GetEncryptionAlgorithms((KerberosCryptoPolicy *)v87, &v123);
    KdcReportKeyErrorETypes(v129[0], v124[0], 10, -1073741808, v123, (__int64)String2[0], (__int64)v112);
    utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v123);
    goto LABEL_315;
  }
  if ( (*(_DWORD *)&String2[0][7].Length & 0x400) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  KerberosCryptoPolicy::Create((__int64 **)&v119);
  v88 = v126;
  if ( (!v119
     || !KerberosCryptoPolicy::SetRequestCiphers(v119, *((struct KERB_KDC_REQUEST_BODY_encryption_type_s **)v126 + 14)))
    && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
  }
  KerberosCryptoPolicy::ApplySecondPartnerHandle((__int64)v87, (__int64 *)&v119);
  S4UTicketInfo = BuildTicketTGS(
                    (struct _KDC_TICKET_INFO *)String2[0],
                    v88,
                    v85,
                    1u,
                    a10,
                    (struct KerberosCryptoPolicy *)v87,
                    (struct KERB_TICKET *)&v149,
                    a17);
  v96 = v87[6];
  v87[6] = 0;
  if ( v96 )
    utl::default_delete<KerberosCryptoPolicy>::operator()(v95, v96);
  if ( S4UTicketInfo )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        171,
        (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67376320,
        (__int64)String2[0],
        S4UTicketInfo);
    goto LABEL_271;
  }
  if ( v114[0] && (v125 & 0x10000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v134);
    S4UTicketInfo = KdcBuildReferralInfo(&v134, v130);
    if ( S4UTicketInfo )
      goto LABEL_271;
  }
LABEL_338:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v119);
  if ( v132 )
  {
    v97 = (struct _USER_INTERNAL6_INFORMATION ***)KerberosCryptoPolicy::FromKerberosKey(
                                                    (KerberosCryptoPolicy **)v129,
                                                    v132,
                                                    0,
                                                    0);
    v98 = 1;
    v87 = *v97;
  }
  else
  {
    v121 = 0;
    v97 = &v130;
    v98 = 2;
  }
  *v97 = 0;
  *(_QWORD *)v124 = v87;
  if ( (v98 & 2) != 0 )
  {
    v98 &= ~2u;
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v130);
  }
  if ( (v98 & 1) != 0 )
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v129);
  if ( v132 )
  {
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0 )
    {
      goto LABEL_353;
    }
    v100 = 173;
  }
  else
  {
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
    {
      goto LABEL_353;
    }
    v100 = 174;
  }
  WPP_SF_(*((_QWORD *)v99 + 2), v100, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
LABEL_353:
  if ( v113 )
  {
    if ( (_DWORD)v138 && *((_QWORD *)&v138 + 1) )
      v101 = v138;
    else
      v101 = v139;
    *(_OWORD *)v140 = v101;
    v102 = _KDC_TICKET_INFO::IsAnyKrbtgt((_KDC_TICKET_INFO *)String2[0]);
    inserted = KdcInsertInitialS4UAuthorizationData(
                 (struct KERB_ENCRYPTED_TICKET *)&v200,
                 a17,
                 a10,
                 v127,
                 (struct _SID_AND_ATTRIBUTES_LIST *)v140,
                 v104,
                 !v102,
                 v105,
                 (struct KerberosCryptoPolicy *)v87,
                 v103);
    v107 = v136;
  }
  else
  {
    v108 = (struct KERB_KDC_REQUEST_BODY *)((char *)v88 + 128);
    if ( (*(_BYTE *)v88 & 4) == 0 )
      v108 = 0;
    v107 = v136;
    inserted = KdcInsertAuthorizationData(
                 (struct KERB_ENCRYPTED_TICKET *)&v200,
                 a17,
                 v108,
                 *((struct KERB_ENCRYPTED_TICKET **)v85 + 7),
                 (struct _KDC_TICKET_INFO *)String2[0],
                 a12,
                 a10,
                 (struct _KDC_TICKET_INFO *)&v156,
                 (struct KerberosCryptoPolicy *)v87,
                 v140[0],
                 v133,
                 v143,
                 v136);
  }
  S4UTicketInfo = inserted;
  if ( inserted )
  {
    if ( (!KdcGlobalCDC || inserted != -2147483641)
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        175,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67376421,
        inserted);
    }
    v91 = v124;
    goto LABEL_272;
  }
  if ( v128 && (*(_DWORD *)v107 & 1) != 0 )
  {
    *((_QWORD *)v107 + 2) = v128;
    v128 = 0;
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::operator=(v141, (__int64 *)v124);
  v109 = v137;
  *(_OWORD *)v137 = v149;
  *(_OWORD *)(v109 + 16) = v150;
  *(_OWORD *)(v109 + 32) = v151;
  *(_OWORD *)(v109 + 48) = v152;
  *(_QWORD *)(v109 + 64) = v153;
  memset_0(v185, 0, 0x48u);
  v149 = v185[0];
  v150 = v185[1];
  v151 = v185[2];
  v152 = v185[3];
  v153 = v186;
  v110 = v142;
  *v142 = v200;
  *(_OWORD *)v110[1].m256i_i8 = v201;
  *(_OWORD *)&v110[1].m256i_u64[2] = v202;
  *(_OWORD *)v110[2].m256i_i8 = v203;
  *(_OWORD *)&v110[2].m256i_u64[2] = v204;
  *(_OWORD *)v110[3].m256i_i8 = v205;
  *(_OWORD *)&v110[3].m256i_u64[2] = v206;
  *(_OWORD *)v110[4].m256i_i8 = v207;
  *(_OWORD *)&v110[4].m256i_u64[2] = v208;
  v110[5].m256i_i64[0] = v209;
  *(_QWORD *)(v109 + 56) = v110;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 0);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v124);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v121);
  LOBYTE(v25) = 0;
  S4UTicketInfo = 0;
LABEL_376:
  v171 = (char)v25;
  lambda_92d3b94e6458b28ec369bd54fc5a80ae_::operator()(v170);
  std::vector<unsigned int>::_Tidy((__int64)&v183);
  std::vector<unsigned int>::_Tidy((__int64)&v168);
  return S4UTicketInfo;
}

```

## disassembly

```asm
0x180024ffc  mov     [rsp-8+arg_8], rbx
0x180025001  push    rbp
0x180025002  push    rsi
0x180025003  push    rdi
0x180025004  push    r12
0x180025006  push    r13
0x180025008  push    r14
0x18002500a  push    r15
0x18002500c  lea     rbp, [rsp-5E0h]
0x180025014  sub     rsp, 6E0h
0x18002501b  mov     rax, cs:__security_cookie
0x180025022  xor     rax, rsp
0x180025025  mov     [rbp+610h+var_40], rax
0x18002502c  mov     qword ptr [rbp+610h+var_640], r9
0x180025030  mov     qword ptr [rbp+610h+var_618], r8
0x180025034  mov     [rbp+610h+var_668], rcx
0x180025038  mov     r13, [rbp+610h+arg_98]
0x18002503f  mov     [rbp+610h+var_658], r13
0x180025043  mov     rax, [rbp+610h+arg_40]
0x18002504a  mov     [rbp+610h+var_600], rax
0x18002504e  mov     rax, [rbp+610h+arg_90]
0x180025055  mov     [rbp+610h+var_5D0], rax
0x180025059  mov     rax, [rbp+610h+arg_30]
0x180025060  mov     [rbp+610h+var_630], rax
0x180025064  mov     r14, [rbp+610h+arg_20]
0x18002506b  mov     rdi, [rbp+610h+arg_28]
0x180025072  mov     rax, [rbp+610h+arg_38]
0x180025079  mov     [rbp+610h+String2], rax
0x18002507d  mov     rsi, [rbp+610h+arg_48]
0x180025084  mov     rax, [rbp+610h+arg_50]
0x18002508b  mov     [rbp+610h+var_5A0], rax
0x18002508f  mov     rax, [rbp+610h+arg_60]
0x180025096  mov     [rbp+610h+var_5F8], rax
0x18002509a  mov     rax, [rbp+610h+arg_68]
0x1800250a1  mov     [rbp+610h+var_5C8], rax
0x1800250a5  mov     rax, [rbp+610h+arg_70]
0x1800250ac  mov     [rbp+610h+var_590], rax
0x1800250b3  mov     rax, [rbp+610h+arg_78]
0x1800250ba  mov     [rbp+610h+var_610], rax
0x1800250be  mov     r15, [rbp+610h+arg_80]
0x1800250c5  mov     rax, [rbp+610h+arg_88]
0x1800250cc  mov     [rbp+610h+var_580], rax
0x1800250d3  mov     rbx, [rbp+610h+arg_A0]
0x1800250da  xor     r12d, r12d
0x1800250dd  mov     [rbp+610h+var_638], r12d
0x1800250e1  xorps   xmm0, xmm0
0x1800250e4  movups  [rbp+610h+var_4E0], xmm0
0x1800250eb  xorps   xmm1, xmm1
0x1800250ee  movups  xmmword ptr [rbp+610h+var_5F0.Length], xmm1
0x1800250f2  movups  xmmword ptr [rbp+610h+String1.Length], xmm0
0x1800250f6  mov     [rbp+610h+var_68F], r12b
0x1800250fa  xor     edx, edx; Val
0x1800250fc  mov     r8d, 0A8h; Size
0x180025102  lea     rcx, [rbp+610h+var_F0]; void *
0x180025109  call    memset_0
0x18002510e  xor     edx, edx; Val
0x180025110  lea     r8d, [r12+48h]; Size
0x180025115  lea     rcx, [rbp+610h+var_530]; void *
0x18002511c  call    memset_0
0x180025121  mov     qword ptr [rbp+610h+var_490.Length], r12
0x180025128  mov     [rbp+610h+var_490.Buffer], r12
0x18002512f  xor     eax, eax
0x180025131  mov     [rbp+610h+var_454], eax
0x180025137  mov     [rbp+610h+var_43F], eax
0x18002513d  mov     [rbp+610h+var_43B], ax
0x180025144  mov     [rbp+610h+var_439], al
0x18002514a  mov     [rbp+610h+var_427], ax
0x180025151  mov     [rbp+610h+var_425], al
0x180025157  mov     [rbp+610h+var_41C], eax
0x18002515d  xor     edx, edx; Val
0x18002515f  mov     r8d, 88h; Size
0x180025165  lea     rcx, [rbp+610h+var_480]; void *
0x18002516c  call    memset_0
0x180025171  mov     [rbp+610h+var_3F8], r12
0x180025178  xorps   xmm0, xmm0
0x18002517b  movdqa  [rbp+610h+var_3F0], xmm0
0x180025183  movups  [rbp+610h+var_5B0], xmm0
0x180025187  mov     [rbp+610h+var_628], r12
0x18002518b  mov     [rbp+610h+var_620], r12
0x18002518f  mov     rdx, qword ptr cs:xmmword_1800B2E20; struct _KERB_INTERNAL_NAME *
0x180025196  mov     rcx, r14; struct _KERB_INTERNAL_NAME *
0x180025199  call    ?KerbEqualKdcNames@@YAEPEAU_KERB_INTERNAL_NAME@@0@Z; KerbEqualKdcNames(_KERB_INTERNAL_NAME *,_KERB_INTERNAL_NAME *)
0x18002519e  mov     r12b, al
0x1800251a1  xorps   xmm0, xmm0
0x1800251a4  movups  [rbp+610h+var_558], xmm0
0x1800251ab  mov     dl, 1
0x1800251ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableSubAuth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSubAuth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSubAuth> `wil::Feature<__WilFeatureTraits_Feature_EnableSubAuth>::GetImpl(void)'::`2'::impl
0x1800251b4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSubAuth@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSubAuth>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800251b9  call    ?IsSubAuthFilterPresent@@YA_NXZ; IsSubAuthFilterPresent(void)
0x1800251be  mov     [rbp+610h+var_660], al
0x1800251c1  mov     [rbp+610h+hAuthzClientContext], 0
0x1800251c9  xorps   xmm0, xmm0
0x1800251cc  xor     eax, eax
0x1800251ce  movups  [rbp+610h+var_548], xmm0
0x1800251d5  mov     [rbp+610h+var_538], rax
0x1800251dc  xorps   xmm1, xmm1
0x1800251df  movups  [rbp+610h+var_360], xmm1
0x1800251e6  mov     [rbp+610h+var_350], rax
0x1800251ed  xor     edx, edx; Val
0x1800251ef  lea     r8d, [rax+50h]; Size
0x1800251f3  lea     rcx, [rbp+610h+var_190]; void *
0x1800251fa  call    memset_0
0x1800251ff  xorps   xmm0, xmm0
0x180025202  movups  xmmword ptr [rbp+610h+var_568.Length], xmm0
0x180025209  xorps   xmm1, xmm1
0x18002520c  movups  xmmword ptr [rbp+610h+var_578.Length], xmm1
0x180025213  xor     eax, eax
0x180025215  movups  [rbp+610h+var_4D0], xmm0
0x18002521c  movups  [rbp+610h+var_4C0], xmm0
0x180025223  movups  [rbp+610h+var_4B0], xmm0
0x18002522a  mov     [rbp+610h+var_4A0], rax
0x180025231  mov     [rbp+610h+var_608], rax
0x180025235  mov     [rbp+610h+var_304], eax
0x18002523b  mov     [rbp+610h+var_2EF], eax
0x180025241  mov     [rbp+610h+var_2EB], ax
0x180025248  mov     [rbp+610h+var_2E9], al
0x18002524e  mov     [rbp+610h+var_2D7], ax
0x180025255  mov     [rbp+610h+var_2D5], al
0x18002525b  mov     [rbp+610h+var_2CC], eax
0x180025261  xor     edx, edx; Val
0x180025263  mov     r8d, 98h; Size
0x180025269  lea     rcx, [rbp+610h+var_340]; void *
0x180025270  call    memset_0
0x180025275  xor     ecx, ecx
0x180025277  mov     [rbp+610h+var_2A8], rcx
0x18002527e  xorps   xmm0, xmm0
0x180025281  movdqa  [rbp+610h+var_2A0], xmm0
0x180025289  movups  [rbp+610h+var_5C0], xmm0
0x18002528d  lea     rax, [rbp+610h+var_490]
0x180025294  mov     [rbp+610h+var_3E0], rax
0x18002529b  lea     rax, [rbp+610h+var_5B0]
0x18002529f  mov     [rbp+610h+var_3D8], rax
0x1800252a6  lea     rax, [rbp+610h+var_628]
0x1800252aa  mov     [rbp+610h+var_3D0], rax
0x1800252b1  lea     rax, [rbp+610h+var_530]
0x1800252b8  mov     [rbp+610h+var_3C8], rax
0x1800252bf  lea     rax, [rbp+610h+var_5F0]
0x1800252c3  mov     [rbp+610h+var_3C0], rax
0x1800252ca  lea     rax, [rbp+610h+String1]
0x1800252ce  mov     [rbp+610h+var_3B8], rax
0x1800252d5  lea     rax, [rbp+610h+var_620]
0x1800252d9  mov     [rbp+610h+var_3B0], rax
0x1800252e0  lea     rax, [rbp+610h+var_558]
0x1800252e7  mov     [rbp+610h+var_3A8], rax
0x1800252ee  lea     rax, [rbp+610h+hAuthzClientContext]
0x1800252f2  mov     [rbp+610h+var_3A0], rax
0x1800252f9  lea     rax, [rbp+610h+var_190]
0x180025300  mov     [rbp+610h+var_398], rax
0x180025307  lea     rax, [rbp+610h+var_608]
0x18002530b  mov     [rbp+610h+var_390], rax
0x180025312  lea     rax, [rbp+610h+var_568]
0x180025319  mov     [rbp+610h+var_388], rax
0x180025320  lea     rax, [rbp+610h+var_578]
0x180025327  mov     [rbp+610h+var_380], rax
0x18002532e  lea     rax, [rbp+610h+var_340]
0x180025335  mov     [rbp+610h+var_378], rax
0x18002533c  lea     rax, [rbp+610h+var_5C0]
0x180025340  mov     [rbp+610h+var_370], rax
0x180025347  mov     [rbp+610h+var_368], 1
0x18002534e  mov     [r13+0], rcx
0x180025352  mov     [rbx], cl
0x180025354  lea     rax, WPP_GLOBAL_Control
0x18002535b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025362  cmp     rcx, rax
0x180025365  jz      short loc_180025389
0x180025367  test    dword ptr [rcx+1Ch], 200000h
0x18002536e  jz      short loc_180025389
0x180025370  mov     edx, 82h
0x180025375  mov     r9, [rbp+610h+var_5F8]
0x180025379  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180025380  mov     rcx, [rcx+10h]
0x180025384  call    WPP_SF_q
0x180025389  mov     r13, [rbp+610h+var_5C8]
0x18002538d  mov     r13, [r13+38h]
0x180025391  mov     [rbp+610h+var_588], r13
0x180025398  lea     rax, [rbp+610h+var_F0]
0x18002539f  mov     [rbp+610h+var_4F8], rax
0x1800253a6  mov     rdx, [rbp+610h+var_668]
0x1800253aa  mov     rdx, [rdx+38h]
0x1800253ae  add     rdx, 30h ; '0'
0x1800253b2  lea     rcx, [rbp+610h+String1]
0x1800253b6  call    KerbConvertRealmToUnicodeString
0x1800253bb  mov     ebx, eax
0x1800253bd  xor     r11d, r11d
0x1800253c0  test    eax, eax
0x1800253c2  jnz     loc_180026CA4
0x1800253c8  movups  xmm0, xmmword ptr [r13+8]
0x1800253cd  movdqu  [rbp+610h+var_F0+8], xmm0
0x1800253d5  mov     qword ptr [rbp+610h+var_4E0+8], r11
0x1800253dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253e3  lea     rbx, WPP_GLOBAL_Control
0x1800253ea  cmp     rcx, rbx
0x1800253ed  jz      short loc_180025410
0x1800253ef  test    dword ptr [rcx+1Ch], 2000h
0x1800253f6  jz      short loc_180025410
0x1800253f8  mov     edx, 83h
0x1800253fd  mov     r9, r14
0x180025400  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180025407  mov     rcx, [rcx+10h]
0x18002540b  call    WPP_SF__KERB_NAME_
0x180025410  mov     rcx, [rbp+610h+var_630]
0x180025414  add     rcx, 8; struct tagASN1bitstring_t *
0x180025418  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18002541d  mov     r13d, eax
0x180025420  mov     [rbp+610h+var_638], eax
0x180025423  test    eax, 81400000h
0x180025428  jz      short loc_180025468
0x18002542a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025431  cmp     rcx, rbx
0x180025434  jz      short loc_18002545B
0x180025436  test    byte ptr [rcx+1Ch], 1
0x18002543a  jz      short loc_18002545B
0x18002543c  mov     edx, 84h
0x180025441  mov     dword ptr [rsp+710h+var_6F0], eax
0x180025445  mov     r9d, 4041157h
0x18002544b  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180025452  mov     rcx, [rcx+10h]
0x180025456  call    WPP_SF_Dd
0x18002545b  mov     ebx, 0Dh
0x180025460  xor     r11d, r11d
0x180025463  jmp     loc_180026CA4
0x180025468  mov     ebx, 34h ; '4'
0x18002546d  lea     eax, [rbx-1Eh]
0x180025470  lea     ecx, [rbx-2Ah]
0x180025473  cmp     [r14], cx
0x180025477  cmovnz  ebx, eax
0x18002547a  mov     r8, [rbp+610h+String2]
0x18002547e  mov     rcx, r8; this
0x180025481  call    ?IsAnyKrbtgt@_KDC_TICKET_INFO@@QEBA_NXZ; _KDC_TICKET_INFO::IsAnyKrbtgt(void)
0x180025486  xor     r11d, r11d
0x180025489  test    al, al
0x18002548b  jnz     short loc_1800254CB
0x18002548d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025494  lea     rax, WPP_GLOBAL_Control
0x18002549b  cmp     rcx, rax
0x18002549e  jz      short loc_1800254C1
0x1800254a0  test    byte ptr [rcx+1Ch], 1
0x1800254a4  jz      short loc_1800254C1
0x1800254a6  mov     edx, 85h
0x1800254ab  mov     r9, r8
0x1800254ae  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x1800254b5  mov     rcx, [rcx+10h]
0x1800254b9  call    WPP_SF_Z
0x1800254be  xor     r11d, r11d
0x1800254c1  mov     ebx, 23h ; '#'
0x1800254c6  jmp     loc_180026CA4
0x1800254cb  mov     rdx, r8
0x1800254ce  lea     rcx, [rbp+610h+var_490]
0x1800254d5  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@AEBU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO const &)
0x1800254da  xor     eax, eax
0x1800254dc  mov     [rbp+610h+var_20C], eax
0x1800254e2  mov     [rbp+610h+var_1F7], eax
0x1800254e8  mov     [rbp+610h+var_1F3], ax
0x1800254ef  mov     [rbp+610h+var_1F1], al
0x1800254f5  mov     [rbp+610h+var_1DF], ax
0x1800254fc  mov     [rbp+610h+var_1DD], al
0x180025502  mov     [rbp+610h+var_1D4], eax
0x180025508  xor     edx, edx; Val
0x18002550a  mov     r8d, 98h; Size
0x180025510  lea     rcx, [rbp+610h+var_248]; void *
0x180025517  call    memset_0
0x18002551c  xorps   xmm0, xmm0
0x18002551f  movdqu  [rbp+610h+var_1B0], xmm0
0x180025527  mov     [rbp+610h+var_1A0], 0
0x180025532  lea     rdx, [rbp+610h+var_248]
0x180025539  mov     rcx, [rbp+610h+String2]
0x18002553d  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@$$QEAU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO &&)
0x180025542  lea     rcx, [rbp+610h+var_1B0]
0x180025549  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18002554e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025555  lea     rax, WPP_GLOBAL_Control
0x18002555c  cmp     rcx, rax
0x18002555f  jz      short loc_18002559A
0x180025561  test    dword ptr [rcx+1Ch], 4000h
0x180025568  jz      short loc_18002559A
0x18002556a  test    r13b, 8
0x18002556e  lea     rax, aFalse_0; "FALSE"
0x180025575  lea     r9, aTrue_0; "TRUE"
0x18002557c  cmovz   r9, rax
0x180025580  mov     edx, 86h
0x180025585  lea     r13, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002558c  mov     r8, r13
0x18002558f  mov     rcx, [rcx+10h]
0x180025593  call    WPP_SF_s
0x180025598  jmp     short loc_1800255A1
0x18002559a  lea     r13, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x1800255a1  xor     r11d, r11d
0x1800255a4  mov     r8d, r11d
0x1800255a7  test    r12b, r12b
0x1800255aa  cmovz   r8, [rbp+610h+var_658]
0x1800255af  mov     r10, [rbp+610h+var_600]
0x1800255b3  mov     rax, r10
0x1800255b6  neg     rax
0x1800255b9  sbb     edx, edx
0x1800255bb  and     edx, 0FFFFFFFCh
0x1800255be  add     edx, 2000804h
0x1800255c4  lea     rcx, [rbp+610h+var_620]
0x1800255c8  test    r12b, r12b
0x1800255cb  cmovnz  rcx, r11
0x1800255cf  mov     r9d, r11d
  ... truncated ...
```
