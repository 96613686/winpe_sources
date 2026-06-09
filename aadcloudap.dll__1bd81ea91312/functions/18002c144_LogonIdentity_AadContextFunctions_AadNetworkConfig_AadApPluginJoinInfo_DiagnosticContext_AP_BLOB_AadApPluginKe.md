# LogonIdentity(AadContextFunctions *,_AadNetworkConfig *,_AadApPluginJoinInfo *,DiagnosticContext &,_AP_BLOB *,_AadApPluginKeyInfo *,_AAD_LOGON_CRED *,_DECRYPTED_AUTH_DATA *,_AadApPluginUserRealmInfo *,_AadApPluginVsmBindingKeys *,ulong,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18002c144`
- end: `0x18002e61d`
- name: `?LogonIdentity@@YAJPEAVAadContextFunctions@@PEAU_AadNetworkConfig@@PEAU_AadApPluginJoinInfo@@AEAVDiagnosticContext@@PEAU_AP_BLOB@@PEAU_AadApPluginKeyInfo@@PEAU_AAD_LOGON_CRED@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_AadApPluginUserRealmInfo@@PEAU_AadApPluginVsmBindingKeys@@KPEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `9433`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, struct _AadNetworkConfig *@<rdx>, struct _AadApPluginJoinInfo *@<r8>, struct DiagnosticContext *@<r9>, struct _AP_BLOB *, struct _AadApPluginKeyInfo *, struct _AAD_LOGON_CRED *, struct _DECRYPTED_AUTH_DATA *, struct _AadApPluginUserRealmInfo *, struct _AadApPluginVsmBindingKeys *, unsigned int, struct _APPLUGIN_USER_INFO **, struct _AadApPluginTokenInfo *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `2`
- callee_count: `74`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e258`
- `0x18000f5cc`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180006380`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007ca4`
- `0x180007d7c`
- `0x180007df8`
- `0x1800090d0`
- `0x180009350`
- `0x18000943c`
- `0x180009fc4`
- `0x18000a06c`
- `0x18000a300`
- `0x18000c754`
- `0x18001a884`
- `0x18001ab40`
- `0x18001b87c`
- `0x18001c558`
- `0x18001ceb4`
- `0x18001cfdc`
- `0x18001d0ec`
- `0x18001d16c`
- `0x180020a40`
- `0x180020bb4`
- `0x180020c24`
- `0x180020c70`
- `0x180020ca4`
- `0x180020f40`
- `0x18002116c`
- `0x1800211ac`
- `0x1800211fc`
- `0x18002406c`
- `0x1800251b4`
- `0x18002865c`
- `0x180029ee4`
- `0x18002a1ec`
- `0x18002a588`
- `0x18002c144`
- `0x18002f4f0`
- `0x18002fde8`
- `0x1800315f8`
- `0x1800329d0`
- `0x1800331bc`
- `0x1800331f8`
- `0x180033290`
- `0x180039ae0`
- `0x180039c10`
- `0x18003ba44`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x18002cce3`
- `CRYPT32!CertCompareCertificateName` at `0x18002d011`
- `CRYPT32!CertCompareCertificateName` at `0x18002cce3`
- `CRYPT32!CertCompareCertificateName` at `0x18002d011`

## string_xrefs

- `0x18002d659`: `urn:aad:tb:update:prt`
- `0x18002e282`: `DoGetEnterpriseToken`
- `0x18002e406`: `EnterpriseAuthorityUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall LogonIdentity(
        struct AadContextFunctions *this,
        struct _AadNetworkConfig *a2,
        struct _AadApPluginJoinInfo *a3,
        struct DiagnosticContext *a4,
        struct _AP_BLOB *a5,
        struct _AadApPluginKeyInfo *a6,
        struct _AAD_LOGON_CRED *a7,
        struct _DECRYPTED_AUTH_DATA *a8,
        struct _AadApPluginUserRealmInfo *a9,
        struct _AadApPluginVsmBindingKeys *a10,
        unsigned int a11,
        struct _APPLUGIN_USER_INFO **a12,
        struct _AadApPluginTokenInfo *a13,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a14)
{
  struct _AadApPluginTokenInfo *v17; // rbx
  const WCHAR *v18; // rax
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rax
  int v21; // eax
  _QWORD *v22; // rcx
  bool v23; // zf
  int TokenEndPoint; // eax
  signed int v25; // ebx
  struct _AadApPluginVsmBindingKeys *v26; // r9
  int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  int v30; // edx
  int PasswordFromAuthBuffer; // eax
  int Nonce; // eax
  int v33; // eax
  signed int v34; // ebx
  __int64 v35; // r8
  int v36; // eax
  int v37; // r8d
  unsigned __int16 *v38; // rdx
  _QWORD *v39; // rax
  int v40; // eax
  __int64 v41; // r8
  int v42; // eax
  int v43; // eax
  char IsEnabled; // al
  const unsigned __int16 *v45; // r9
  const struct _CERT_CONTEXT *v46; // rcx
  int v47; // eax
  int v48; // eax
  unsigned int v49; // ebx
  rsize_t v50; // rcx
  _WORD *v51; // rbx
  int v52; // ebx
  unsigned __int16 *v53; // rbx
  int v54; // eax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rdx
  int v58; // eax
  int ResourceAccount; // ebx
  int v60; // eax
  unsigned __int16 *v61; // rbx
  int v62; // eax
  int v63; // eax
  _QWORD *v64; // rax
  int v65; // eax
  __int64 v66; // rax
  const char *v67; // rdx
  const char *v68; // rax
  signed int v69; // eax
  int v70; // eax
  __int64 v71; // rax
  const char *v72; // rdx
  const char *v73; // rax
  __int64 v74; // rax
  const char *v75; // rdx
  const char *v76; // rax
  __int64 v77; // r8
  int v78; // eax
  int v79; // eax
  const WCHAR *v80; // rcx
  struct _AAD_LOGON_CRED *v81; // r12
  int v82; // ebx
  char *v83; // rbx
  struct _AadApPluginTokenInfo *v84; // rsi
  struct _AadApPluginJoinInfo *v85; // rsi
  const unsigned __int16 *v86; // rdx
  const unsigned __int16 *v87; // rdx
  unsigned int v88; // ebx
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v89; // rbx
  struct _AadNetworkConfig *v91; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v92; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v93; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v94; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v95; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v96; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v97; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v98; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v99; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v100; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v101; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v102; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v103; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v104; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v105; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v106; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v107; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v108; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v109; // [rsp+20h] [rbp-E0h]
  struct _AadNetworkConfig *v110; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING *v111; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v112; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v113; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v114; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v115; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v116; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v117; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v118; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v119; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v120; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v121; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v122; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v123; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v124; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v125; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v126; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v127; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v128; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v129; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v130; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v131; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v132; // [rsp+30h] [rbp-D0h]
  struct _UNICODE_STRING *v133; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v134; // [rsp+38h] [rbp-C8h]
  struct _AadApPluginKeyInfo *v135; // [rsp+48h] [rbp-B8h]
  struct _AP_BLOB *v136; // [rsp+50h] [rbp-B0h]
  bool v137; // [rsp+80h] [rbp-80h]
  bool v138; // [rsp+80h] [rbp-80h]
  signed int v139; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 *v140; // [rsp+88h] [rbp-78h] BYREF
  struct _AP_BLOB *v141; // [rsp+90h] [rbp-70h] BYREF
  void *Destination; // [rsp+98h] [rbp-68h] BYREF
  signed int FederationProviderName; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v144; // [rsp+A8h] [rbp-58h] BYREF
  struct _APPLUGIN_USER_INFO **v145; // [rsp+B0h] [rbp-50h]
  struct _AadApPluginKeyInfo *v146; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v147; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v148; // [rsp+C8h] [rbp-38h]
  struct _AadApPluginVsmBindingKeys *v149; // [rsp+D0h] [rbp-30h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v150; // [rsp+D8h] [rbp-28h]
  struct _AadApPluginUserRealmInfo *v151; // [rsp+E0h] [rbp-20h]
  struct _AAD_LOGON_CRED *v152; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v153; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v154; // [rsp+F8h] [rbp-8h]
  struct _DECRYPTED_AUTH_DATA *v155; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING v156; // [rsp+108h] [rbp+8h] BYREF
  struct _CERT_CONTEXT *v157; // [rsp+118h] [rbp+18h] BYREF
  __int64 v158; // [rsp+120h] [rbp+20h]
  struct AadContextFunctions *v159; // [rsp+128h] [rbp+28h]
  char v160; // [rsp+130h] [rbp+30h]
  _BYTE v161[8]; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v162; // [rsp+140h] [rbp+40h] BYREF
  struct _AadApPluginJoinInfo *v163; // [rsp+148h] [rbp+48h]
  struct _AadApPluginTokenInfo *v164; // [rsp+150h] [rbp+50h]
  _BYTE v165[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v166[8]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v167; // [rsp+168h] [rbp+68h] BYREF
  __int64 v168[2]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v169[30]; // [rsp+180h] [rbp+80h] BYREF
  const char *v170[6]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v171[624]; // [rsp+2A0h] [rbp+1A0h] BYREF
  struct _GUID v172; // [rsp+510h] [rbp+410h] BYREF
  struct AadContextFunctions *v173; // [rsp+520h] [rbp+420h]

  v163 = a3;
  v151 = a9;
  v152 = a7;
  v141 = a5;
  v146 = a6;
  v155 = a8;
  v149 = a10;
  v145 = a12;
  v17 = a13;
  v164 = a13;
  v150 = a14;
  v139 = 0;
  v156 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v144);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v168);
  v137 = IsApBlobDefined(a5);
  memset_0(v171, 0, 0x268u);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v170,
    (int)"login.cpp",
    (int)"LogonIdentity",
    (int)&v139);
  if ( !this || !v155 || !v163 || !a9 || !a12 || !a13 || !v150 )
  {
    v139 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "login.cpp", 1008, "NTSTATUS", &base);
    if ( !this )
      goto LABEL_204;
    goto LABEL_203;
  }
  v147 = (unsigned __int16 *)*((_QWORD *)v163 + 1);
  v148 = (unsigned __int16 *)*((_QWORD *)v163 + 3);
  v154 = (unsigned __int16 *)*((_QWORD *)v163 + 11);
  v18 = &base;
  if ( *((_QWORD *)a4 + 3) )
    v18 = (const WCHAR *)*((_QWORD *)a4 + 3);
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "login.cpp", 1015, "correlation id", v18);
  v19 = (unsigned __int16 *)&base;
  if ( v147 )
    v19 = v147;
  LODWORD(v111) = 1016;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "login.cpp", v111, "authority", v19);
  v20 = (unsigned __int16 *)&base;
  if ( v148 )
    v20 = v148;
  LODWORD(v112) = 1017;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "login.cpp", v112, "tenant id", v20);
  LODWORD(v113) = 1018;
  WPPTraceLogA(
    4,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    4,
    0,
    "login.cpp",
    v113,
    "client id",
    L"38aa3b87-a06d-4817-b275-7a316988d93b");
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "login.cpp", 1019, "flags", a11);
  if ( *((_QWORD *)a7 + 7) )
  {
    LODWORD(v114) = 1023;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "login.cpp",
      v114,
      "credbuffer correlation id",
      *((_QWORD *)a7 + 7));
  }
  if ( !*((_QWORD *)a7 + 1) )
    goto LABEL_200;
  v21 = *((_DWORD *)a7 + 4);
  if ( !v21 )
    goto LABEL_200;
  v22 = (_QWORD *)((char *)a7 + 32);
  Destination = (char *)a7 + 32;
  if ( v21 == 1 )
  {
    if ( !*v22 )
    {
LABEL_200:
      v27 = -2146893042;
      v139 = -2146893042;
      LODWORD(v114) = 1034;
      goto LABEL_201;
    }
  }
  else if ( v21 == 4 )
  {
    Destination = (char *)a7 + 32;
    v23 = *((_QWORD *)a7 + 4) == 0;
    goto LABEL_22;
  }
  if ( v21 != 8 )
    goto LABEL_23;
  v23 = *v22 == 0;
LABEL_22:
  if ( v23 )
    goto LABEL_200;
LABEL_23:
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws");
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0dz_EventWriteTransfer(
      Microsoft_Windows_AAD_Context,
      Aad_CloudAPPlugin_CredType,
      *((unsigned int *)a7 + 4),
      *((_QWORD *)a4 + 3));
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "login.cpp", 1041, "credential type", *((_DWORD *)a7 + 4));
  TokenEndPoint = EndpointHelper::GetTokenEndPoint(v147, v148, &v144);
  if ( TokenEndPoint >= 0 )
  {
    v26 = v149;
    if ( v149 )
    {
      LODWORD(v140) = 0;
      v27 = CheckVsmBindingKeys(this, v149, (int *)&v140);
      v139 = v27;
      if ( v27 < 0 )
      {
        LODWORD(v114) = 1050;
LABEL_201:
        LODWORD(v91) = v27;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "NTSTATUS", &base);
        goto LABEL_203;
      }
      if ( (_DWORD)v140 )
      {
        v134 = "VSM key roll";
        LODWORD(v114) = 1055;
        LODWORD(v91) = (_DWORD)v140;
        WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::GetImpl'::`2'::impl) )
        {
          a11 |= 0x100u;
          DiagnosticContext::AddDiagnosticMessage(a4, L"SkRolloverReason", L"VSM key rollover");
        }
        else
        {
          v146 = 0;
        }
        if ( (Microsoft_Windows_AADEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_DoGetToken_SessionKey_Needs_Roll,
            L"VSM key rollover");
      }
      v26 = v149;
    }
    v138 = !v137;
    v28 = a11 | 2;
    if ( *((_DWORD *)v163 + 29) != 3 )
      v28 = a11;
    v29 = v28 | 0x18;
    LODWORD(v140) = v29;
    v30 = *((_DWORD *)v152 + 4);
    switch ( v30 )
    {
      case 1:
        *(_QWORD *)&v172.Data1 = 0;
        v173 = this;
        *(_QWORD *)v172.Data4 = 0;
        PasswordFromAuthBuffer = GetPasswordFromAuthBuffer(this, v152, &v172);
        v139 = PasswordFromAuthBuffer;
        if ( PasswordFromAuthBuffer < 0 )
        {
          LODWORD(v114) = 1083;
          LODWORD(v91) = PasswordFromAuthBuffer;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "NTSTATUS", &base);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        if ( !*(_QWORD *)&v172.Data1 || !**(_WORD **)&v172.Data1 )
        {
          v139 = -1073741718;
          LODWORD(v114) = 1088;
          LODWORD(v91) = -1073741718;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "NTSTATUS", &base);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        Nonce = GetNonce(this, v144, v148, a4, a2, 0, &v156);
        v139 = Nonce;
        if ( Nonce < 0 )
        {
          LODWORD(v115) = 1094;
          LODWORD(v92) = Nonce;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v92, "login.cpp", v115, "NTSTATUS", &base);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        if ( *(_DWORD *)v151 == 1 )
        {
          PasswordGrantTokenRequest::PasswordGrantTokenRequest(
            (PasswordGrantTokenRequest *)v169,
            v144,
            v148,
            v154,
            (const unsigned __int16 *)v92,
            a4,
            &v115->Length,
            v156.Buffer,
            *((const unsigned __int16 **)v152 + 1),
            *(const unsigned __int16 **)&v172.Data1,
            v141,
            v146,
            v149,
            (unsigned int)v140);
          v33 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
          v139 = v33;
          if ( v33 < 0 )
          {
            LODWORD(v116) = 1123;
            LODWORD(v93) = v33;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v93, "login.cpp", v116, "NTSTATUS", &base);
            PasswordGrantTokenRequest::~PasswordGrantTokenRequest((PasswordGrantTokenRequest *)v169);
            Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
            goto LABEL_203;
          }
          PasswordGrantTokenRequest::~PasswordGrantTokenRequest((PasswordGrantTokenRequest *)v169);
          goto LABEL_64;
        }
        if ( *(_DWORD *)v151 || *((_DWORD *)v151 + 1) )
        {
          v139 = -1073741729;
          LODWORD(v115) = 1171;
          LODWORD(v92) = -1073741729;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v92, "login.cpp", v115, "NTSTATUS", &base);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        FederationProviderName = GetFederationProviderName(v147, a2, v168);
        if ( FederationProviderName < 0 )
        {
          LODWORD(v115) = 1128;
          v34 = FederationProviderName;
          LODWORD(v92) = FederationProviderName;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v92, "login.cpp", v115, "HRESULT", &base);
          v139 = v34 & 0xAFFFFFFF | 0x40000000;
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        v35 = *((_QWORD *)v151 + 6);
        if ( !v35 || !*((_WORD *)v151 + 20) )
        {
          LODWORD(v115) = 1132;
          LODWORD(v92) = -2147187573;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v92, "login.cpp", v115, "HRESULT", &base);
          v139 = -1073445749;
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_203;
        }
        WsTrustPasswordTokenRequest::WsTrustPasswordTokenRequest(
          v169,
          *((unsigned int *)v151 + 22),
          v35,
          *((_QWORD *)v152 + 1),
          *(__int64 *)&v172.Data1);
        v36 = SendWsTrustRequest(
                this,
                a2,
                v163,
                (struct WSTrustTokenRequest *)v169,
                v144,
                L"38aa3b87-a06d-4817-b275-7a316988d93b",
                v156.Buffer,
                v138,
                1,
                (unsigned int)v140,
                v141,
                v146,
                v149,
                v145,
                a13,
                v150);
        v139 = v36;
        if ( v36 == -1073741715 )
        {
          v36 = -1073741718;
          v139 = -1073741718;
        }
        else if ( v36 >= 0 )
        {
          WsTrustPasswordTokenRequest::~WsTrustPasswordTokenRequest((WsTrustPasswordTokenRequest *)v169);
LABEL_64:
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
          goto LABEL_176;
        }
        LODWORD(v117) = 1167;
        LODWORD(v94) = v36;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v94, "login.cpp", v117, "NTSTATUS", &base);
        WsTrustPasswordTokenRequest::~WsTrustPasswordTokenRequest((WsTrustPasswordTokenRequest *)v169);
        Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v172);
        goto LABEL_203;
      case 2:
      case 9:
        v27 = GetNonce(this, v144, v148, a4, a2, 0, &v156);
        v139 = v27;
        if ( v27 < 0 )
        {
          LODWORD(v114) = 1179;
          goto LABEL_201;
        }
        if ( !*(_DWORD *)v151 && (Microsoft_Windows_AADEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_ManagedLogonForFederatedNGCUser,
            v77,
            1,
            &v172);
        NgcGrantTokenRequest::NgcGrantTokenRequest(
          (NgcGrantTokenRequest *)v169,
          v144,
          v148,
          v154,
          (const unsigned __int16 *)v91,
          v148,
          a4,
          v134,
          v156.Buffer,
          *((const unsigned __int16 **)v152 + 1),
          v155,
          0,
          v141,
          v146,
          v149,
          (unsigned int)v140);
        v78 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
        v139 = v78;
        if ( v78 < 0 )
        {
          LODWORD(v130) = 1217;
          LODWORD(v108) = v78;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v108, "login.cpp", v130, "NTSTATUS", &base);
          goto LABEL_173;
        }
LABEL_174:
        UpdatePasswordExpiryClaims(this, v147, a2, v155, v151, a4, *v145, a13);
LABEL_175:
        NgcGrantTokenRequest::~NgcGrantTokenRequest((NgcGrantTokenRequest *)v169);
        goto LABEL_176;
      case 3:
        v38 = (unsigned __int16 *)*((_QWORD *)v155 + 2);
        if ( !v38 || v38[1] - (unsigned __int64)*v38 < 0x18 )
        {
          LODWORD(v114) = 1229;
          LODWORD(v91) = -2147187570;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
          v139 = -1073445746;
          goto LABEL_203;
        }
        v153 = (unsigned __int64)(v38 + 14);
        if ( v38 == (unsigned __int16 *)-28LL || (v39 = *(_QWORD **)(v38 + 14), (Destination = v39) == 0) )
        {
          LODWORD(v114) = 1235;
          goto LABEL_110;
        }
        if ( !v39[3] )
        {
          LODWORD(v114) = 1241;
LABEL_110:
          LODWORD(v91) = -2147187571;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
          v139 = -1073445747;
          goto LABEL_203;
        }
        v27 = GetNonce(this, v144, v148, a4, a2, 0, &v156);
        v139 = v27;
        if ( v27 < 0 )
        {
          LODWORD(v114) = 1246;
          goto LABEL_201;
        }
        if ( !*(_DWORD *)v151 )
        {
          if ( CertCompareCertificateName(
                 1u,
                 (PCERT_NAME_BLOB)(*((_QWORD *)Destination + 3) + 48LL),
                 (PCERT_NAME_BLOB)(*((_QWORD *)Destination + 3) + 80LL)) )
          {
            NgcGrantTokenRequest::NgcGrantTokenRequest(
              (NgcGrantTokenRequest *)v169,
              v144,
              v148,
              v154,
              (const unsigned __int16 *)v91,
              v148,
              a4,
              v134,
              v156.Buffer,
              *((const unsigned __int16 **)v152 + 1),
              0,
              (const struct _CERT_CONTEXT *)Destination,
              v141,
              v146,
              v149,
              (unsigned int)v140);
            v40 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
            v139 = v40;
            if ( v40 < 0 )
            {
              LODWORD(v118) = 1286;
              LODWORD(v95) = v40;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v95, "login.cpp", v118, "NTSTATUS", &base);
LABEL_173:
              NgcGrantTokenRequest::~NgcGrantTokenRequest((NgcGrantTokenRequest *)v169);
              goto LABEL_203;
            }
            goto LABEL_174;
          }
          if ( !*((_DWORD *)v151 + 1) )
          {
            FederationProviderName = GetFederationProviderName(v147, a2, v168);
            if ( FederationProviderName < 0 )
            {
              LODWORD(v114) = 1294;
              v25 = FederationProviderName;
              goto LABEL_27;
            }
            v41 = *((_QWORD *)v151 + 8);
            if ( !v41 || !*((_WORD *)v151 + 28) )
            {
              LODWORD(v114) = 1298;
              LODWORD(v91) = -2147187572;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
              v139 = -1073445748;
              goto LABEL_203;
            }
            WSTrustCertificateTokenRequest::WSTrustCertificateTokenRequest(
              v169,
              *((unsigned int *)v151 + 23),
              v41,
              v168[0],
              *(_QWORD *)v153);
            v42 = SendWsTrustRequest(
                    this,
                    a2,
                    v163,
                    (struct WSTrustTokenRequest *)v169,
                    v144,
                    L"38aa3b87-a06d-4817-b275-7a316988d93b",
                    v156.Buffer,
                    v138,
                    1,
                    (unsigned int)v140,
                    v141,
                    v146,
                    v149,
                    v145,
                    a13,
                    v150);
            v139 = v42;
            if ( v42 < 0 )
            {
              LODWORD(v119) = 1323;
              LODWORD(v96) = v42;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v96, "login.cpp", v119, "NTSTATUS", &base);
              WSTrustCertificateTokenRequest::~WSTrustCertificateTokenRequest((WSTrustCertificateTokenRequest *)v169);
              goto LABEL_203;
            }
            WSTrustCertificateTokenRequest::~WSTrustCertificateTokenRequest((WSTrustCertificateTokenRequest *)v169);
LABEL_176:
            if ( !*(_DWORD *)v151 )
            {
              AutoPasswordExpiryInfo::AutoPasswordExpiryInfo((AutoPasswordExpiryInfo *)&v157, this);
              v79 = EnterpriseSTSHelper::LogonAsSecondary(
                      this,
                      v148,
                      a4,
                      a2,
                      v152,
                      v155,
                      v151,
                      (unsigned __int8)v140 & 1,
                      (struct _AadApPluginTokenInfo *)((char *)v17 + 264),
                      (struct AutoPasswordExpiryInfo *)&v157);
              LODWORD(v140) = v79;
              if ( v79 >= 0 )
              {
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Destination);
                v82 = CloudDomainHelper::SetLoginUri(&Destination, *((_QWORD *)v151 + 2));
                if ( v82 < 0 )
                {
                  LODWORD(v131) = 1689;
                  LODWORD(v109) = v82;
                  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v109, "login.cpp", v131, "HRESULT", &base);
                  v139 = v82 & 0xAFFFFFFF | 0x40000000;
                  ATL::CStringData::Release((ATL::CStringData *)((char *)Destination - 24));
LABEL_187:
                  ATL::CStringData::Release((ATL::CStringData *)(v158 - 24));
                  goto LABEL_203;
                }
                v172 = *(struct _GUID *)((char *)a2 + 36);
                v83 = (char *)Destination;
                RegistryHelper::SetStringValue(
                  this,
                  &v172,
                  L"EnterpriseAuthorityUri",
                  (const unsigned __int16 *)Destination,
                  (bool)v109);
                v84 = v164;
                if ( !(unsigned int)AutoPasswordExpiryInfo::ApplyPasswordChangeClaims(
                                      (AutoPasswordExpiryInfo *)&v157,
                                      *v145,
                                      v164) )
                  *((_DWORD *)v84 + 110) = 1;
                ATL::CStringData::Release((ATL::CStringData *)(v83 - 24));
                v17 = v164;
              }
              else
              {
                v80 = &base;
                if ( *((_QWORD *)a4 + 3) )
                  v80 = (const WCHAR *)*((_QWORD *)a4 + 3);
                LODWORD(v131) = 1660;
                LODWORD(v109) = v79;
                WPPTraceLogA(
                  3,
                  0,
                  "%x 0x%08x %s:%u : %s:%ws",
                  3,
                  v109,
                  "login.cpp",
                  v131,
                  "Logon to Enterprise STS failed. Correlation ID",
                  v80);
                v81 = v152;
                DiagnosticContext::LogDiagnosticEvent(
                  a4,
                  L"DoGetEnterpriseToken",
                  (int)v140,
                  *((const unsigned __int16 **)v152 + 1),
                  *((_DWORD *)v152 + 4),
                  1,
                  0);
                if ( (_DWORD)v140 == -1073741711 && (unsigned int)(*((_DWORD *)v81 + 4) - 2) <= 1 )
                {
                  if ( !v160 )
                    AutoPasswordExpiryInfo::ApplyPasswordChangeUri((AutoPasswordExpiryInfo *)&v157, *v145, v17);
                  if ( (Microsoft_Windows_AADEnableBits & 4) != 0 )
                    McTemplateU0dz_EventWriteTransfer(
                      Microsoft_Windows_AAD_Context,
                      Aad_CloudAPPlugin_EnterpriseLogonPasswordExpired,
                      3221225585LL,
                      *((_QWORD *)a4 + 3));
                  LODWORD(v132) = 1679;
                  WPPTraceLogA(
                    3,
                    0,
                    "%x 0x%08x %s:%u : %s:%ws",
                    3,
                    0,
                    "login.cpp",
                    v132,
                    "Enterprise Password expired.",
                    &base);
                  v139 = -1073741711;
                  LODWORD(v133) = 1681;
                  LODWORD(v110) = -1073741711;
                  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v110, "login.cpp", v133, "NTSTATUS", &base);
                  goto LABEL_187;
                }
              }
              ATL::CStringData::Release((ATL::CStringData *)(v158 - 24));
            }
            v85 = v163;
            v86 = (const unsigned __int16 *)*((_QWORD *)v163 + 5);
            if ( v86 && !*((_QWORD *)v17 + 31) )
              DuplicateString(this, v86, v37, (unsigned __int16 **)v17 + 31);
            v87 = (const unsigned __int16 *)*((_QWORD *)v85 + 9);
            if ( v87 && !*((_QWORD *)v17 + 32) )
              DuplicateString(this, v87, v37, (unsigned __int16 **)v17 + 32);
            goto LABEL_203;
          }
          v27 = -1073741729;
          LODWORD(v114) = 1328;
LABEL_94:
          v139 = v27;
          goto LABEL_201;
        }
        if ( *(_DWORD *)v151 != 1 )
        {
          v27 = -1073741729;
          v139 = -1073741729;
          LODWORD(v114) = 1424;
          goto LABEL_201;
        }
        if ( CertCompareCertificateName(
               1u,
               (PCERT_NAME_BLOB)(*((_QWORD *)Destination + 3) + 48LL),
               (PCERT_NAME_BLOB)(*((_QWORD *)Destination + 3) + 80LL)) )
        {
          NgcGrantTokenRequest::NgcGrantTokenRequest(
            (NgcGrantTokenRequest *)v169,
            v144,
            v148,
            v154,
            (const unsigned __int16 *)v91,
            v148,
            a4,
            v134,
            v156.Buffer,
            *((const unsigned __int16 **)v152 + 1),
            0,
            (const struct _CERT_CONTEXT *)Destination,
            v141,
            v146,
            v149,
            (unsigned int)v140);
          v43 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
          v139 = v43;
          if ( v43 < 0 )
          {
            LODWORD(v120) = 1362;
            LODWORD(v97) = v43;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v97, "login.cpp", v120, "NTSTATUS", &base);
            goto LABEL_173;
          }
          goto LABEL_175;
        }
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CBA_SendOldPRTOnNetworkLogon>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CBA_SendOldPRTOnNetworkLogon>::GetImpl'::`2'::impl);
        v46 = *(const struct _CERT_CONTEXT **)v153;
        if ( IsEnabled )
        {
          X509GrantTokenRequest::X509GrantTokenRequest(
            (X509GrantTokenRequest *)v169,
            v144,
            v148,
            v45,
            v148,
            a4,
            &v114->Length,
            v156.Buffer,
            *((const unsigned __int16 **)v152 + 1),
            v46,
            v141,
            v146,
            v149,
            (unsigned int)v140);
          v47 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
          v139 = v47;
          if ( v47 < 0 )
          {
            LODWORD(v121) = 1391;
            LODWORD(v98) = v47;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v98, "login.cpp", v121, "NTSTATUS", &base);
LABEL_103:
            X509GrantTokenRequest::~X509GrantTokenRequest((X509GrantTokenRequest *)v169);
            goto LABEL_203;
          }
        }
        else
        {
          X509GrantTokenRequest::X509GrantTokenRequest(
            (X509GrantTokenRequest *)v169,
            v144,
            v148,
            v45,
            v148,
            a4,
            &v114->Length,
            v156.Buffer,
            *((const unsigned __int16 **)v155 + 1),
            v46,
            0,
            0,
            0,
            (unsigned int)v140);
          v48 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
          v139 = v48;
          if ( v48 < 0 )
          {
            LODWORD(v122) = 1418;
            LODWORD(v99) = v48;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v99, "login.cpp", v122, "NTSTATUS", &base);
            goto LABEL_103;
          }
        }
        X509GrantTokenRequest::~X509GrantTokenRequest((X509GrantTokenRequest *)v169);
        goto LABEL_176;
      case 4:
        v157 = 0;
        v159 = this;
        v158 = 0;
        v49 = *((unsigned __int16 *)v152 + 12) + 2;
        *(_QWORD *)v172.Data4 = 0;
        v172.Data1 = 0;
        Destination = (void *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)this + 24LL))(
                                this,
                                v49);
        Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
        v157 = (struct _CERT_CONTEXT *)Destination;
        v50 = v49;
        v153 = v49;
        v158 = v49;
        v51 = Destination;
        if ( !Destination )
        {
          v139 = -1073741801;
          LODWORD(v114) = 1437;
          LODWORD(v91) = -1073741801;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "NTSTATUS", &base);
          PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
          goto LABEL_203;
        }
        if ( memcpy_s_0(Destination, v50, *((const void *const *)v152 + 4), *((unsigned __int16 *)v152 + 12)) )
        {
          v139 = -1073741595;
          LODWORD(v114) = 1442;
          LODWORD(v91) = -1073741595;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "NTSTATUS", &base);
          PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
          goto LABEL_203;
        }
        v51[(v153 >> 1) - 1] = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&Destination,
          (__int64)v51);
        LOBYTE(v91) = 1;
        v52 = StringUtility::EncodeString(this, &Destination, &v172, 65001, (_DWORD)v91);
        ATL::CStringData::Release((ATL::CStringData *)((char *)Destination - 24));
        if ( v52 < 0 )
        {
          LODWORD(v114) = 1446;
          LODWORD(v100) = v52;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v100, "login.cpp", v114, "HRESULT", &base);
          v139 = v52 & 0xAFFFFFFF | 0x40000000;
          PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
          goto LABEL_203;
        }
        v53 = v148;
        v54 = GetNonce(this, v144, v148, a4, a2, 0, &v156);
        v139 = v54;
        if ( v54 < 0 )
        {
          LODWORD(v123) = 1451;
          LODWORD(v101) = v54;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v101, "login.cpp", v123, "NTSTATUS", &base);
          PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
          goto LABEL_203;
        }
        RefreshTokenRequest::RefreshTokenRequest(
          (RefreshTokenRequest *)v169,
          v144,
          v53,
          v154,
          L"urn:aad:tb:update:prt",
          a4,
          L"29d9ed98-a469-4536-ade2-f981bc1d605e",
          v156.Buffer,
          (struct _AP_BLOB *)&v172,
          0,
          v141,
          v149,
          0,
          (unsigned int)v140 | 4);
        v17 = v164;
        v55 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, v164, v150);
        v139 = v55;
        if ( v55 < 0 )
        {
          LODWORD(v124) = 1478;
          LODWORD(v102) = v55;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v102, "login.cpp", v124, "NTSTATUS", &base);
          RefreshTokenRequest::~RefreshTokenRequest((RefreshTokenRequest *)v169);
          PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
          Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
          goto LABEL_203;
        }
        RefreshTokenRequest::~RefreshTokenRequest((RefreshTokenRequest *)v169);
        PluginLocalFreeApBlob((struct _AP_BLOB *)&v172);
        Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,AadContextFunctions>::Clear(&v157);
        goto LABEL_176;
      case 6:
        v56 = *((_QWORD *)v155 + 2);
        if ( !v56 )
        {
          LODWORD(v114) = 1486;
          LODWORD(v91) = -2147187325;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
          v139 = -1073445501;
          goto LABEL_203;
        }
        v57 = v56 + 28;
        if ( !v57 )
        {
          LODWORD(v114) = 1492;
          LODWORD(v91) = -2147187332;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
          v139 = -1073445508;
          goto LABEL_203;
        }
        if ( !*(_WORD *)(v57 + 32) )
        {
          LODWORD(v114) = 1499;
          LODWORD(v91) = -2147187323;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
          v139 = -1073445499;
          goto LABEL_203;
        }
        v172.Data1 = *(unsigned __int16 *)(v57 + 32);
        *(_DWORD *)&v172.Data2 = 0;
        *(_QWORD *)v172.Data4 = v57 + *(unsigned int *)(v57 + 28);
        FidoGrantTokenRequest::FidoGrantTokenRequest(
          (FidoGrantTokenRequest *)v169,
          v144,
          v148,
          v154,
          (const unsigned __int16 *)v91,
          a4,
          &v114->Length,
          (struct _AP_BLOB *)&v172,
          v141,
          v146,
          v26,
          v29);
        v58 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, a13, v150);
        v139 = v58;
        if ( v58 < 0 )
        {
          LODWORD(v125) = 1524;
          LODWORD(v103) = v58;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v103, "login.cpp", v125, "NTSTATUS", &base);
          v169[0] = &FidoGrantTokenRequest::`vftable';
          OAuthTokenRequest::~OAuthTokenRequest((OAuthTokenRequest *)v169);
          goto LABEL_203;
        }
        v169[0] = &FidoGrantTokenRequest::`vftable';
        OAuthTokenRequest::~OAuthTokenRequest((OAuthTokenRequest *)v169);
        goto LABEL_176;
      case 7:
        CertificateContext::CertificateContext((CertificateContext *)&v157);
        ResourceAccount = DsrGetResourceAccount(&v157);
        if ( ResourceAccount >= 0 )
        {
          if ( !v157 )
          {
            LODWORD(v114) = 1534;
            LODWORD(v91) = -2147187295;
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
            v139 = -1073445471;
            goto LABEL_138;
          }
          v60 = CheckCertificatePrivateKey(this, 1);
          ResourceAccount = v60;
          if ( v60 >= 0 )
          {
            v61 = v148;
            v62 = GetNonce(this, v144, v148, a4, a2, 0, &v156);
            v139 = v62;
            if ( v62 >= 0 )
            {
              ResourceAccountRequest::ResourceAccountRequest(
                (ResourceAccountRequest *)v169,
                v144,
                v61,
                v154,
                (const unsigned __int16 *)v104,
                a4,
                &v126->Length,
                v156.Buffer,
                v157,
                v141,
                v146,
                v149,
                (unsigned int)v140);
              v17 = v164;
              v63 = ProcessOAuthRequest(this, (struct OAuthTokenRequest *)v169, a2, v138, v147, v145, v164, v150);
              v139 = v63;
              if ( v63 >= 0 )
              {
                v169[0] = &ResourceAccountRequest::`vftable';
                OAuthTokenRequest::~OAuthTokenRequest((OAuthTokenRequest *)v169);
                CertificateContext::~CertificateContext((CertificateContext *)&v157);
                goto LABEL_176;
              }
              LODWORD(v127) = 1572;
              LODWORD(v105) = v63;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v105, "login.cpp", v127, "NTSTATUS", &base);
              v169[0] = &ResourceAccountRequest::`vftable';
              OAuthTokenRequest::~OAuthTokenRequest((OAuthTokenRequest *)v169);
            }
            else
            {
              LODWORD(v126) = 1548;
              LODWORD(v104) = v62;
              WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v104, "login.cpp", v126, "NTSTATUS", &base);
            }
LABEL_138:
            CertificateContext::~CertificateContext((CertificateContext *)&v157);
            goto LABEL_203;
          }
          if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_Error,
              L"Resource account certificate private key check",
              (unsigned int)v60);
          LODWORD(v114) = 1542;
        }
        else
        {
          LODWORD(v114) = 1530;
        }
        LODWORD(v91) = ResourceAccount;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
        v139 = ResourceAccount & 0xAFFFFFFF | 0x40000000;
        goto LABEL_138;
    }
    if ( v30 != 8 )
    {
      v27 = -2146893043;
      LODWORD(v114) = 1637;
      goto LABEL_94;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v162,
      *(_QWORD *)Destination);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v161);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v146);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Destination);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v153);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v167);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v166);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v165);
    v141 = 0;
    v64 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::ensure_data(&v141);
    tip2::details::shared_data<0,0,0>::start(*v64 + 8LL, &v172);
    v65 = DelegationTokenHelper::ParseRdpAssertion(
            this,
            (const struct CSecureString *)&v162,
            (struct CSecureString *)v161,
            (struct CSecureString *)&v146,
            (struct CSecureString *)&Destination,
            (struct CSecureString *)&v153,
            (struct CSecureString *)&v167,
            (struct CSecureString *)v166,
            (struct CSecureString *)v165);
    if ( v65 >= 0 )
      goto LABEL_156;
    FederationProviderName = v65 & 0xAFFFFFFF | 0x40000000;
    v139 = FederationProviderName;
    v66 = tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::operator->(
            &v141,
            &v172);
    *(_DWORD *)(*(_QWORD *)v66 + 272LL) = FederationProviderName;
    tip2::test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>::~test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>(&v172);
    v68 = tip2::details::reason_string(
            (tip2::details *)"RDPAssertionLogonTip::reason::parsing_rdp_assertion_failed",
            v67);
    tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::complete_and_fail(
      &v141,
      0,
      v68);
    v69 = v139;
    if ( v139 >= 0 )
    {
LABEL_156:
      v70 = DelegationTokenHelper::ValidateNonce(this, v163, (const struct CSecureString *)v161);
      if ( v70 >= 0 )
        goto LABEL_159;
      FederationProviderName = v70 & 0xAFFFFFFF | 0x40000000;
      v139 = FederationProviderName;
      v71 = tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::operator->(
              &v141,
              &v172);
      *(_DWORD *)(*(_QWORD *)v71 + 272LL) = FederationProviderName;
      tip2::test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>::~test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>(&v172);
      v73 = tip2::details::reason_string((tip2::details *)"RDPAssertionLogonTip::reason::nonce_validation_failed", v72);
      tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::complete_and_fail(
        &v141,
        1,
        v73);
      v69 = v139;
      if ( v139 >= 0 )
      {
LABEL_159:
        RdpAssertionRequest::RdpAssertionRequest(
          (RdpAssertionRequest *)v169,
          v144,
          v148,
          v154,
          (const unsigned __int16 *)v106,
          a4,
          &v128->Length,
          (const unsigned __int16 *)v146,
          v162,
          v135,
          v136,
          v149,
          (unsigned int)v140);
        FederationProviderName = ProcessOAuthRequest(
                                   this,
                                   (struct OAuthTokenRequest *)v169,
                                   a2,
                                   v138,
                                   v147,
                                   v145,
                                   a13,
                                   v150);
        v139 = FederationProviderName;
        if ( FederationProviderName >= 0
          || (v74 = tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::operator->(
                      &v141,
                      &v172),
              *(_DWORD *)(*(_QWORD *)v74 + 272LL) = FederationProviderName,
              tip2::test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>::~test_data_control<tip2::details::merged_data<TipTest::_tip_GetKeysTip,TipTest::_tip_GetKeysTip>>(&v172),
              v76 = tip2::details::reason_string(
                      (tip2::details *)"RDPAssertionLogonTip::reason::rdp_assertion_authentication_failed",
                      v75),
              tip2::tip_test<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>>::complete_and_fail(
                &v141,
                2,
                v76),
              v139 >= 0) )
        {
          RdpAssertionRequest::~RdpAssertionRequest((RdpAssertionRequest *)v169);
          if ( v141 )
            tip2::details::shared_data<0,0,0>::complete_without_lock((char *)v141 + 8);
          wil::com_ptr_t<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>,wil::err_returncode_policy>((void **)&v141);
          CSecureString::~CSecureString((CSecureString *)v165);
          CSecureString::~CSecureString((CSecureString *)v166);
          CSecureString::~CSecureString((CSecureString *)&v167);
          CSecureString::~CSecureString((CSecureString *)&v153);
          CSecureString::~CSecureString((CSecureString *)&Destination);
          CSecureString::~CSecureString((CSecureString *)&v146);
          CSecureString::~CSecureString((CSecureString *)v161);
          CSecureString::~CSecureString((CSecureString *)&v162);
          goto LABEL_176;
        }
        LODWORD(v129) = 1629;
        LODWORD(v107) = v139;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v107, "login.cpp", v129, "NTSTATUS", &base);
        RdpAssertionRequest::~RdpAssertionRequest((RdpAssertionRequest *)v169);
LABEL_155:
        wil::com_ptr_t<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTest::_tip_RDPAssertionLogonTip,TipTest::_tip_RDPAssertionLogonTip>,wil::err_returncode_policy>((void **)&v141);
        CSecureString::~CSecureString((CSecureString *)v165);
        CSecureString::~CSecureString((CSecureString *)v166);
        CSecureString::~CSecureString((CSecureString *)&v167);
        CSecureString::~CSecureString((CSecureString *)&v153);
        CSecureString::~CSecureString((CSecureString *)&Destination);
        CSecureString::~CSecureString((CSecureString *)&v146);
        CSecureString::~CSecureString((CSecureString *)v161);
        CSecureString::~CSecureString((CSecureString *)&v162);
        goto LABEL_203;
      }
      LODWORD(v128) = 1597;
    }
    else
    {
      LODWORD(v128) = 1588;
    }
    LODWORD(v106) = v69;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v106, "login.cpp", v128, "NTSTATUS", &base);
    goto LABEL_155;
  }
  LODWORD(v114) = 1043;
  v25 = TokenEndPoint;
LABEL_27:
  LODWORD(v91) = v25;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v91, "login.cpp", v114, "HRESULT", &base);
  v139 = v25 & 0xAFFFFFFF | 0x40000000;
LABEL_203:
  AadContextFunctions::LsaFreeString(this, &v156);
  ReleaseTokenInfo(this, (struct _AadApPluginTokenInfo *)v171);
LABEL_204:
  v88 = v139;
  if ( v139 < 0 )
  {
    if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
    {
      McTemplateU0dz_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_Logon_Failure,
        (unsigned int)v139,
        *((_QWORD *)a4 + 3));
      v88 = v139;
    }
    if ( v88 == -1073741711 )
      ReleaseTokenInfo(this, v164);
    else
      ReleaseUserInfoData(this, v145, v164);
    v89 = v150;
    if ( v150 && *v150 )
    {
      FreeSupplementalCredentials(this, *v150);
      *v89 = 0;
    }
    v88 = v139;
  }
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v170);
  ATL::CStringData::Release((ATL::CStringData *)(v168[0] - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v144 - 12));
  return v88;
}

```

## disassembly

```asm
0x18002c144  push    rbp
0x18002c146  push    rbx
0x18002c147  push    rsi
0x18002c148  push    rdi
0x18002c149  push    r12
0x18002c14b  push    r13
0x18002c14d  push    r14
0x18002c14f  push    r15
0x18002c151  lea     rbp, [rsp-448h]
0x18002c159  sub     rsp, 548h
0x18002c160  mov     rax, cs:__security_cookie
0x18002c167  xor     rax, rsp
0x18002c16a  mov     [rbp+480h+var_50], rax
0x18002c171  mov     r13, r9
0x18002c174  mov     [rbp+480h+var_438], r8
0x18002c178  mov     r12, rdx
0x18002c17b  mov     r15, rcx
0x18002c17e  mov     rsi, [rbp+480h+arg_40]
0x18002c185  mov     [rbp+480h+var_4A0], rsi
0x18002c189  mov     rdi, [rbp+480h+arg_30]
0x18002c190  mov     [rbp+480h+var_498], rdi
0x18002c194  mov     rax, [rbp+480h+arg_20]
0x18002c19b  mov     [rbp+480h+var_4F0], rax
0x18002c19f  mov     rax, [rbp+480h+arg_28]
0x18002c1a6  mov     [rbp+480h+var_4C8], rax
0x18002c1aa  mov     rax, [rbp+480h+arg_38]
0x18002c1b1  mov     [rbp+480h+var_480], rax
0x18002c1b5  mov     rax, [rbp+480h+arg_48]
0x18002c1bc  mov     [rbp+480h+var_4B0], rax
0x18002c1c0  mov     r14, [rbp+480h+arg_58]
0x18002c1c7  mov     [rbp+480h+var_4D0], r14
0x18002c1cb  mov     rbx, [rbp+480h+arg_60]
0x18002c1d2  mov     [rbp+480h+var_430], rbx
0x18002c1d6  mov     rax, [rbp+480h+arg_68]
0x18002c1dd  mov     [rbp+480h+var_4A8], rax
0x18002c1e1  mov     [rbp+480h+var_4FC], 0
0x18002c1e8  xorps   xmm0, xmm0
0x18002c1eb  movups  xmmword ptr [rbp+480h+var_478.Length], xmm0
0x18002c1ef  lea     rcx, [rbp+480h+var_4D8]; void *
0x18002c1f3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002c1f8  nop
0x18002c1f9  lea     rcx, [rbp+480h+var_410]; void *
0x18002c1fd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002c202  nop
0x18002c203  mov     rcx, [rbp+480h+var_4F0]; struct _AP_BLOB *
0x18002c207  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18002c20c  mov     [rbp+480h+var_500], al
0x18002c20f  xor     edx, edx; Val
0x18002c211  mov     r8d, 268h; Size
0x18002c217  lea     rcx, [rbp+480h+var_2E0]; void *
0x18002c21e  call    memset_0
0x18002c223  lea     r9, [rbp+480h+var_4FC]
0x18002c227  lea     r8, aLogonidentity; "LogonIdentity"
0x18002c22e  lea     rdx, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c235  lea     rcx, [rbp+480h+var_310]
0x18002c23c  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18002c241  nop
0x18002c242  xor     edx, edx
0x18002c244  test    r15, r15
0x18002c247  jz      loc_18002E4EF
0x18002c24d  cmp     [rbp+480h+var_480], rdx
0x18002c251  jz      loc_18002E4EF
0x18002c257  mov     rcx, [rbp+480h+var_438]
0x18002c25b  test    rcx, rcx
0x18002c25e  jz      loc_18002E4EF
0x18002c264  test    rsi, rsi
0x18002c267  jz      loc_18002E4EF
0x18002c26d  test    r14, r14
0x18002c270  jz      loc_18002E4EF
0x18002c276  test    rbx, rbx
0x18002c279  jz      loc_18002E4EF
0x18002c27f  cmp     [rbp+480h+var_4A8], rdx
0x18002c283  jz      loc_18002E4EF
0x18002c289  mov     rax, [rcx+8]
0x18002c28d  mov     [rbp+480h+var_4C0], rax
0x18002c291  mov     rax, [rcx+18h]
0x18002c295  mov     [rbp+480h+var_4B8], rax
0x18002c299  mov     rax, [rcx+58h]
0x18002c29d  mov     [rbp+480h+var_488], rax
0x18002c2a1  lea     r14, base
0x18002c2a8  mov     rax, r14
0x18002c2ab  cmp     [r13+18h], rdx
0x18002c2af  cmovnz  rax, [r13+18h]
0x18002c2b4  mov     [rsp+580h+var_540], rax
0x18002c2b9  lea     rax, aCorrelationId_0; "correlation id"
0x18002c2c0  mov     [rsp+580h+var_548], rax
0x18002c2c5  mov     dword ptr [rsp+580h+var_550], 3F7h
0x18002c2cd  lea     rcx, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c2d4  mov     [rsp+580h+var_558], rcx
0x18002c2d9  mov     [rsp+580h+var_560], rdx
0x18002c2de  lea     eax, [rdx+4]
0x18002c2e1  mov     r9d, eax
0x18002c2e4  lea     rsi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002c2eb  mov     r8, rsi
0x18002c2ee  mov     ecx, eax
0x18002c2f0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c2f5  mov     rax, r14
0x18002c2f8  mov     rcx, [rbp+480h+var_4C0]
0x18002c2fc  xor     edx, edx
0x18002c2fe  test    rcx, rcx
0x18002c301  cmovnz  rax, rcx
0x18002c305  mov     [rsp+580h+var_540], rax
0x18002c30a  lea     rax, aAuthority; "authority"
0x18002c311  mov     [rsp+580h+var_548], rax
0x18002c316  mov     dword ptr [rsp+580h+var_550], 3F8h
0x18002c31e  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c325  mov     [rsp+580h+var_558], rax
0x18002c32a  mov     [rsp+580h+var_560], rdx
0x18002c32f  lea     eax, [rdx+4]
0x18002c332  mov     r9d, eax
0x18002c335  mov     r8, rsi
0x18002c338  mov     ecx, eax
0x18002c33a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c33f  mov     rax, r14
0x18002c342  mov     rcx, [rbp+480h+var_4B8]
0x18002c346  xor     edx, edx
0x18002c348  test    rcx, rcx
0x18002c34b  cmovnz  rax, rcx
0x18002c34f  mov     [rsp+580h+var_540], rax
0x18002c354  lea     rax, aTenantId_0; "tenant id"
0x18002c35b  mov     [rsp+580h+var_548], rax
0x18002c360  mov     dword ptr [rsp+580h+var_550], 3F9h
0x18002c368  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c36f  mov     [rsp+580h+var_558], rax
0x18002c374  mov     [rsp+580h+var_560], rdx
0x18002c379  lea     eax, [rdx+4]
0x18002c37c  mov     r9d, eax
0x18002c37f  mov     r8, rsi
0x18002c382  mov     ecx, eax
0x18002c384  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c389  lea     rax, a38aa3b87A06d48; "38aa3b87-a06d-4817-b275-7a316988d93b"
0x18002c390  mov     [rsp+580h+var_540], rax
0x18002c395  lea     rax, aClientId_0; "client id"
0x18002c39c  mov     [rsp+580h+var_548], rax
0x18002c3a1  mov     dword ptr [rsp+580h+var_550], 3FAh
0x18002c3a9  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c3b0  mov     [rsp+580h+var_558], rax
0x18002c3b5  mov     [rsp+580h+var_560], 0
0x18002c3be  mov     eax, 4
0x18002c3c3  mov     r9d, eax
0x18002c3c6  mov     r8, rsi
0x18002c3c9  xor     edx, edx
0x18002c3cb  mov     ecx, eax
0x18002c3cd  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c3d2  mov     eax, [rbp+480h+arg_50]
0x18002c3d8  mov     dword ptr [rsp+580h+var_540], eax
0x18002c3dc  lea     rax, aFlags_0; "flags"
0x18002c3e3  mov     [rsp+580h+var_548], rax
0x18002c3e8  mov     dword ptr [rsp+580h+var_550], 3FBh
0x18002c3f0  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c3f7  mov     [rsp+580h+var_558], rax
0x18002c3fc  mov     [rsp+580h+var_560], 0
0x18002c405  mov     eax, 4
0x18002c40a  mov     r9d, eax
0x18002c40d  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18002c414  xor     edx, edx
0x18002c416  mov     ecx, eax
0x18002c418  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c41d  mov     rax, [rdi+38h]
0x18002c421  xor     r8d, r8d
0x18002c424  test    rax, rax
0x18002c427  jz      short loc_18002C469
0x18002c429  mov     [rsp+580h+var_540], rax
0x18002c42e  lea     rax, aCredbufferCorr_0; "credbuffer correlation id"
0x18002c435  mov     [rsp+580h+var_548], rax
0x18002c43a  mov     dword ptr [rsp+580h+var_550], 3FFh
0x18002c442  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c449  mov     [rsp+580h+var_558], rax
0x18002c44e  mov     [rsp+580h+var_560], r8
0x18002c453  lea     eax, [r8+4]
0x18002c457  mov     r9d, eax
0x18002c45a  mov     r8, rsi
0x18002c45d  xor     edx, edx
0x18002c45f  mov     ecx, eax
0x18002c461  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c466  xor     r8d, r8d
0x18002c469  mov     rdx, [rdi+8]
0x18002c46d  test    rdx, rdx
0x18002c470  jz      loc_18002E4A8
0x18002c476  mov     eax, [rdi+10h]
0x18002c479  test    eax, eax
0x18002c47b  jz      loc_18002E4A8
0x18002c481  lea     rcx, [rdi+20h]
0x18002c485  mov     [rbp+480h+Destination], rcx
0x18002c489  cmp     eax, 1
0x18002c48c  jnz     loc_18002C5B1
0x18002c492  cmp     [rcx], r8
0x18002c495  jz      loc_18002E4A8
0x18002c49b  cmp     eax, 8
0x18002c49e  jnz     short loc_18002C4A9
0x18002c4a0  cmp     [rcx], r8
0x18002c4a3  jz      loc_18002E4A8
0x18002c4a9  mov     [rsp+580h+var_540], rdx
0x18002c4ae  lea     rax, aUserName; "user name"
0x18002c4b5  mov     [rsp+580h+var_548], rax
0x18002c4ba  mov     dword ptr [rsp+580h+var_550], 40Dh
0x18002c4c2  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c4c9  mov     [rsp+580h+var_558], rax
0x18002c4ce  mov     [rsp+580h+var_560], r8
0x18002c4d3  mov     r9d, 4
0x18002c4d9  mov     r8, rsi
0x18002c4dc  xor     edx, edx
0x18002c4de  mov     ecx, r9d
0x18002c4e1  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c4e6  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18002c4ed  jz      short loc_18002C50A
0x18002c4ef  mov     r9, [r13+18h]
0x18002c4f3  mov     r8d, [rdi+10h]
0x18002c4f7  lea     rdx, Aad_CloudAPPlugin_CredType
0x18002c4fe  lea     rcx, Microsoft_Windows_AAD_Context
0x18002c505  call    McTemplateU0dz_EventWriteTransfer
0x18002c50a  mov     eax, [rdi+10h]
0x18002c50d  mov     dword ptr [rsp+580h+var_540], eax
0x18002c511  lea     rax, aCredentialType; "credential type"
0x18002c518  mov     [rsp+580h+var_548], rax
0x18002c51d  mov     dword ptr [rsp+580h+var_550], 411h
0x18002c525  lea     rdi, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002c52c  mov     [rsp+580h+var_558], rdi
0x18002c531  mov     [rsp+580h+var_560], 0
0x18002c53a  mov     eax, 4
0x18002c53f  mov     r9d, eax
0x18002c542  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18002c549  xor     edx, edx
0x18002c54b  mov     ecx, eax
0x18002c54d  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c552  lea     r8, [rbp+480h+var_4D8]
0x18002c556  mov     rdx, [rbp+480h+var_4B8]
0x18002c55a  mov     rcx, [rbp+480h+var_4C0]
0x18002c55e  call    ?GetTokenEndPoint@EndpointHelper@@SAJPEBG0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; EndpointHelper::GetTokenEndPoint(ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002c563  xor     r8d, r8d
0x18002c566  test    eax, eax
0x18002c568  jns     short loc_18002C5CA
0x18002c56a  mov     [rsp+580h+var_540], r14
0x18002c56f  lea     rcx, aHresult; "HRESULT"
0x18002c576  mov     [rsp+580h+var_548], rcx
0x18002c57b  mov     dword ptr [rsp+580h+var_550], 413h
0x18002c583  mov     [rsp+580h+var_558], rdi
0x18002c588  mov     ebx, eax
0x18002c58a  lea     edi, [r8+2]
0x18002c58e  xor     edx, edx
0x18002c590  mov     r8, rsi
0x18002c593  mov     r9d, edi
0x18002c596  mov     dword ptr [rsp+580h+var_560], ebx
0x18002c59a  mov     ecx, edi
0x18002c59c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c5a1  btr     ebx, 1Ch
0x18002c5a5  bts     ebx, 1Eh
0x18002c5a9  mov     [rbp+480h+var_4FC], ebx
0x18002c5ac  jmp     loc_18002E542
0x18002c5b1  cmp     eax, 4
0x18002c5b4  jnz     loc_18002C49B
0x18002c5ba  lea     rax, [rdi+20h]
0x18002c5be  mov     [rbp+480h+Destination], rax
0x18002c5c2  cmp     [rax], r8
0x18002c5c5  jmp     loc_18002C4A3
0x18002c5ca  mov     r9, [rbp+480h+var_4B0]
0x18002c5ce  test    r9, r9
0x18002c5d1  jz      loc_18002C6BC
0x18002c5d7  mov     dword ptr [rbp+480h+var_4F8], r8d
0x18002c5db  lea     r8, [rbp+480h+var_4F8]; int *
0x18002c5df  mov     rdx, r9; struct _AadApPluginVsmBindingKeys *
0x18002c5e2  mov     rcx, r15; this
0x18002c5e5  call    ?CheckVsmBindingKeys@@YAJPEAVAadContextFunctions@@PEAU_AadApPluginVsmBindingKeys@@PEAH@Z; CheckVsmBindingKeys(AadContextFunctions *,_AadApPluginVsmBindingKeys *,int *)
0x18002c5ea  mov     [rbp+480h+var_4FC], eax
0x18002c5ed  xor     r8d, r8d
0x18002c5f0  test    eax, eax
0x18002c5f2  jns     short loc_18002C617
0x18002c5f4  mov     [rsp+580h+var_540], r14
0x18002c5f9  lea     rcx, aNtstatus; "NTSTATUS"
0x18002c600  mov     [rsp+580h+var_548], rcx
0x18002c605  mov     dword ptr [rsp+580h+var_550], 41Ah
0x18002c60d  mov     [rsp+580h+var_558], rdi
0x18002c612  jmp     loc_18002E4D5
0x18002c617  mov     eax, dword ptr [rbp+480h+var_4F8]
0x18002c61a  test    eax, eax
0x18002c61c  jz      loc_18002C6B8
0x18002c622  mov     [rsp+580h+var_540], r14
0x18002c627  lea     rcx, aVsmKeyRoll; "VSM key roll"
0x18002c62e  mov     [rsp+580h+var_548], rcx; unsigned __int16 *
0x18002c633  mov     dword ptr [rsp+580h+var_550], 41Fh; unsigned __int16 *
0x18002c63b  mov     [rsp+580h+var_558], rdi
0x18002c640  mov     dword ptr [rsp+580h+var_560], eax; unsigned __int16 *
0x18002c644  mov     eax, 4
0x18002c649  mov     r9d, eax
0x18002c64c  mov     r8, rsi
0x18002c64f  xor     edx, edx
0x18002c651  mov     ecx, eax
0x18002c653  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002c658  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2> `wil::Feature<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::GetImpl(void)'::`2'::impl
0x18002c65f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::__private_IsEnabled(void)
0x18002c664  xor     r8d, r8d
0x18002c667  test    al, al
0x18002c669  jz      short loc_18002C68E
0x18002c66b  bts     [rbp+480h+arg_50], 8
0x18002c673  lea     r8, aVsmKeyRollover; "VSM key rollover"
0x18002c67a  lea     rdx, aSkrolloverreas; "SkRolloverReason"
0x18002c681  mov     rcx, r13; this
0x18002c684  call    ?AddDiagnosticMessage@DiagnosticContext@@QEAAJPEBG0@Z; DiagnosticContext::AddDiagnosticMessage(ushort const *,ushort const *)
0x18002c689  xor     r8d, r8d
0x18002c68c  jmp     short loc_18002C692
  ... truncated ...
```
