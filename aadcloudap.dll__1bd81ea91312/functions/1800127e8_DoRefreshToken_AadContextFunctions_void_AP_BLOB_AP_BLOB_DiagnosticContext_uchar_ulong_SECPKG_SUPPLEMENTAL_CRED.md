# DoRefreshToken(AadContextFunctions *,void *,_AP_BLOB *,_AP_BLOB *,DiagnosticContext &,uchar * *,ulong *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x1800127e8`
- end: `0x180013d33`
- name: `?DoRefreshToken@@YAJPEAVAadContextFunctions@@PEAXPEAU_AP_BLOB@@2AEAVDiagnosticContext@@PEAPEAEPEAKPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `5451`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, void *@<rdx>, struct _AP_BLOB *@<r8>, struct _AP_BLOB *@<r9>, struct DiagnosticContext *, unsigned __int8 **, unsigned int *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x1800011b4`
- `0x180001310`
- `0x180001954`
- `0x180001af4`
- `0x180001cfc`
- `0x180003c20`
- `0x18000424c`
- `0x1800042b4`
- `0x180004a24`
- `0x180006049`
- `0x180006380`
- `0x1800063f4`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x180009350`
- `0x180009380`
- `0x180009f78`
- `0x18000a300`
- `0x18000c884`
- `0x1800127e8`
- `0x1800192e8`
- `0x18001a8fc`
- `0x18001ce38`
- `0x18001ceb4`
- `0x18001d074`
- `0x18001d0ec`
- `0x18001f474`
- `0x180021cbc`
- `0x180028088`
- `0x18002865c`
- `0x18002f898`
- `0x18002fde8`
- `0x18002fec8`
- `0x180031a48`
- `0x180034590`
- `0x1800352a8`
- `0x180036bf4`
- `0x180039ae0`
- `0x18003c10c`
- `0x18003fd78`
- `0x180071e14`
- `0x180075584`
- `0x180078b18`
- `0x180078b98`
- `0x180078bfc`
- `0x180078da8`
- `0x1800792d8`
- `0x1800a2d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012d68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012d68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013bc9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013bc9`
- `ntdll!RtlLengthRequiredSid` at `0x180013d12`
- `ntdll!RtlLengthRequiredSid` at `0x180013d12`

## string_xrefs

- `0x180013220`: `Token is expired`
- `0x18001386d`: `Token is expired`
- `0x1800128dd`: `DoRefreshToken`
- `0x18001298e`: `DoRefreshToken`
- `0x180012c90`: `DoRefreshToken`
- `0x180012bcc`: `enterpriseSTSInfo authorityUri is not a valid url`
- `0x180012cea`: `tokenUpdateInfo authorityUri is not a valid url`
- `0x180012dae`: `token enterpriseSTSInfo authorityUri`
- `0x180012df9`: `tokenUpdateInfo authorityUri`
- `0x180012fa1`: `EnterpriseSTS Refresh token correlation ID`
- `0x180013027`: `Skipping unnecessary enterprise token refresh (the given token is the same as existing one).`
- `0x180012ef0`: `Skipping enterprise token refresh.`
- `0x18001351a`: `Refresh token correlation ID`
- `0x18001359a`: `Skipping unnecessary token refresh (the given token is the same as existing one).`
- `0x180013786`: `User SIDs don't match`
- `0x180013439`: `Skipping token refresh.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DoRefreshToken(
        struct AadContextFunctions *this,
        struct _AadApPluginJoinInfo **a2,
        struct _AP_BLOB *a3,
        struct _AP_BLOB *a4,
        const WCHAR **a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a8)
{
  bool v12; // bl
  unsigned __int8 v13; // dl
  char v14; // al
  GUID *v15; // rdx
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  unsigned int *v18; // rax
  __int64 v19; // rdx
  int v20; // r8d
  int updated; // eax
  char v22; // bl
  const WCHAR *v23; // rcx
  __int64 v24; // rcx
  BOOL v25; // esi
  char v26; // bl
  const WCHAR *v27; // rcx
  __int64 v28; // rbx
  _QWORD *v29; // rax
  BOOL v30; // ebx
  const WCHAR *v31; // rcx
  const WCHAR *v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  const WCHAR *v36; // rax
  __int64 v37; // r8
  struct _AadApPluginKeyInfo *v38; // rcx
  struct _AP_BLOB *p_Size; // rax
  int refreshed; // eax
  bool v41; // al
  int v42; // r8d
  __int64 v43; // r9
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  const WCHAR *v47; // rax
  __int64 v48; // r8
  struct _AadApPluginKeyInfo *v49; // rcx
  struct _AP_BLOB *v50; // rax
  int v51; // eax
  const void *v52; // rcx
  const void *v53; // rdx
  __int64 v54; // r9
  __int64 v55; // r9
  int v56; // eax
  int v57; // ecx
  __int64 v58; // rcx
  __int64 v59; // r9
  unsigned int v60; // ebx
  struct _AP_BLOB *v62; // [rsp+20h] [rbp-E0h]
  struct _AP_BLOB *v63; // [rsp+20h] [rbp-E0h]
  struct _AP_BLOB *v64; // [rsp+20h] [rbp-E0h]
  struct _AP_BLOB *v65; // [rsp+20h] [rbp-E0h]
  struct _AP_BLOB *v66; // [rsp+30h] [rbp-D0h]
  int v67; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v68; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v69; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v70; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v71; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v72; // [rsp+30h] [rbp-D0h]
  struct _AP_BLOB *v73; // [rsp+30h] [rbp-D0h]
  bool v74; // [rsp+60h] [rbp-A0h]
  int v75; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v76; // [rsp+68h] [rbp-98h]
  BOOL v77; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v78; // [rsp+70h] [rbp-90h] BYREF
  struct _AadApPluginJoinInfo **v79; // [rsp+78h] [rbp-88h] BYREF
  __int128 v80; // [rsp+80h] [rbp-80h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v81; // [rsp+90h] [rbp-70h] BYREF
  struct _APPLUGIN_USER_INFO *v82; // [rsp+98h] [rbp-68h] BYREF
  struct _APPLUGIN_USER_INFO *v83; // [rsp+A0h] [rbp-60h] BYREF
  char v84[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-50h]
  unsigned int *v86; // [rsp+C8h] [rbp-38h]
  unsigned __int8 **v87; // [rsp+D0h] [rbp-30h]
  _QWORD v88[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v89; // [rsp+F0h] [rbp-10h]
  __int64 v90; // [rsp+100h] [rbp+0h]
  char v91[8]; // [rsp+110h] [rbp+10h] BYREF
  size_t Size; // [rsp+118h] [rbp+18h] BYREF
  void *Buf1; // [rsp+120h] [rbp+20h]
  __int64 v94; // [rsp+128h] [rbp+28h]
  _BYTE v95[40]; // [rsp+130h] [rbp+30h] BYREF
  const WCHAR *v96; // [rsp+158h] [rbp+58h]
  unsigned __int16 *v97; // [rsp+160h] [rbp+60h]
  struct DiagnosticContext *v98; // [rsp+170h] [rbp+70h]
  _BYTE v99[144]; // [rsp+180h] [rbp+80h] BYREF
  int v100; // [rsp+210h] [rbp+110h] BYREF
  void *v101; // [rsp+218h] [rbp+118h]
  __int64 v102; // [rsp+220h] [rbp+120h]
  __int64 v103; // [rsp+228h] [rbp+128h]
  char v104; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 *v105; // [rsp+258h] [rbp+158h]
  unsigned __int16 *v106; // [rsp+260h] [rbp+160h]
  _OWORD v107[2]; // [rsp+288h] [rbp+188h] BYREF
  __int128 v108; // [rsp+2A8h] [rbp+1A8h]
  __int128 v109; // [rsp+2B8h] [rbp+1B8h]
  __int128 v110; // [rsp+2C8h] [rbp+1C8h] BYREF
  void *Buf2[2]; // [rsp+2D8h] [rbp+1D8h]
  _OWORD v112[3]; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v113; // [rsp+318h] [rbp+218h]
  __int64 v114; // [rsp+328h] [rbp+228h]
  int v115; // [rsp+338h] [rbp+238h]
  __int64 v116; // [rsp+340h] [rbp+240h]
  int v117; // [rsp+348h] [rbp+248h]
  int v118; // [rsp+34Ch] [rbp+24Ch]
  int v119; // [rsp+350h] [rbp+250h]
  int v120; // [rsp+360h] [rbp+260h]
  __int64 v121; // [rsp+364h] [rbp+264h]
  unsigned int v122; // [rsp+36Ch] [rbp+26Ch]
  __int128 v123; // [rsp+370h] [rbp+270h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 v124; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v125; // [rsp+458h] [rbp+358h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+460h] [rbp+360h] BYREF
  __int64 v127; // [rsp+4C8h] [rbp+3C8h]
  _BYTE v128[160]; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v129; // [rsp+570h] [rbp+470h]
  __int128 v130; // [rsp+5D8h] [rbp+4D8h]
  __int128 v131; // [rsp+5E8h] [rbp+4E8h]
  __int128 v132; // [rsp+5F8h] [rbp+4F8h]
  __int128 v133; // [rsp+608h] [rbp+508h]
  __int128 v134; // [rsp+618h] [rbp+518h]
  __int128 v135; // [rsp+628h] [rbp+528h]
  __int128 v136; // [rsp+638h] [rbp+538h]
  __int128 v137; // [rsp+648h] [rbp+548h]
  __int128 v138; // [rsp+658h] [rbp+558h]
  __int128 v139; // [rsp+668h] [rbp+568h]
  __int64 v140; // [rsp+678h] [rbp+578h]
  int v141; // [rsp+680h] [rbp+580h]
  int v142; // [rsp+688h] [rbp+588h]
  __int64 v143; // [rsp+690h] [rbp+590h]
  int v144; // [rsp+698h] [rbp+598h]
  int v145; // [rsp+69Ch] [rbp+59Ch]
  const char *v146[6]; // [rsp+740h] [rbp+640h] BYREF
  int v147; // [rsp+770h] [rbp+670h] BYREF
  char v148; // [rsp+774h] [rbp+674h]
  _BYTE v149[16]; // [rsp+778h] [rbp+678h] BYREF
  GUID ActivityId; // [rsp+788h] [rbp+688h] BYREF
  struct _AP_BLOB *v151[2]; // [rsp+798h] [rbp+698h] BYREF
  __int128 v152; // [rsp+7A8h] [rbp+6A8h] BYREF

  v151[0] = a4;
  v79 = a2;
  v87 = a6;
  v86 = a7;
  *(_QWORD *)&v152 = a8;
  v75 = 0;
  v78 = (__int64)a2;
  memset_0(v99, 0, 0x268u);
  memset_0(v128, 0, 0x268u);
  memset_0(v91, 0, 0x58u);
  v82 = 0;
  v83 = 0;
  v81 = 0;
  memset(v88, 0, sizeof(v88));
  v89 = 0;
  v90 = 0;
  v77 = 0;
  v12 = IsApBlobDefined(a4);
  v74 = v12;
  v76 = v13;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v146,
    (int)"aadcloudap.cpp",
    (int)"DoRefreshToken",
    (int)&v75);
  v147 = 0;
  v148 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v147);
  if ( (unsigned int)dword_1800E5050 > 5 )
  {
    v14 = tlgKeywordOn(&dword_1800E5050, 0x400000000000LL);
    v15 = 0;
    if ( v14 )
    {
      *(_QWORD *)&v80 = 0x1000000;
      if ( !v148 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
        p_ActivityId = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (__int64)&dword_1800E5050,
        (__int64)byte_1800D2729,
        (__int64)v149,
        (__int64)p_ActivityId,
        (__int64)&v80);
    }
  }
  v98 = (struct DiagnosticContext *)a5;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
    a5 + 8,
    L"DoRefreshToken");
  if ( !this || !a2 || !a3 || !a6 || (v18 = v86) == 0 )
  {
    updated = -1073741811;
    v75 = -1073741811;
    v67 = 1717;
    goto LABEL_18;
  }
  *a6 = 0;
  *v18 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !PluginState::IsCloudDomainJoined((PluginState *)&v78) )
  {
    LODWORD(v62) = -2147187631;
    WPPTraceLogA(2, v19, "%x 0x%08x %s:%u : %s:%ws", 2, v62, "aadcloudap.cpp", 1730, "HRESULT", &base);
    v20 = -1073445807;
    v75 = -1073445807;
LABEL_35:
    v25 = v77;
    DiagnosticContext::LogDiagnosticEvent((struct DiagnosticContext *)a5, L"DoRefreshToken", v20, v106, v117, v77, v12);
    goto LABEL_158;
  }
  updated = TokenInfoSerializeHelper::DeserializeTokenInfo(this, a3, &v82, (struct _AadApPluginTokenInfo *)v99);
  v75 = updated;
  if ( updated < 0 )
  {
    v67 = 1738;
LABEL_18:
    LODWORD(v62) = updated;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v62, "aadcloudap.cpp", v67, "NTSTATUS", &base);
    goto LABEL_34;
  }
  LODWORD(v88[0]) = v120;
  *(_QWORD *)((char *)v88 + 4) = v121;
  *(_QWORD *)((char *)&v88[1] + 4) = v122;
  v89 = v123;
  LODWORD(v90) = 0;
  if ( !v12 )
    goto LABEL_45;
  updated = TokenInfoSerializeHelper::DeserializeTokenUpdateInfo(
              this,
              v151[0],
              (struct _AadApPluginTokenUpdateInfo *)v91);
  v75 = updated;
  if ( updated < 0 )
  {
    v67 = 1752;
    goto LABEL_18;
  }
  if ( v97 && *v97 )
    DiagnosticContext::SetCorrelationId((DiagnosticContext *)a5, v97);
  if ( *((_QWORD *)&v107[0] + 1) && v96 )
  {
    Url::Url((Url *)&UrlComponents);
    Url::Url((Url *)&v124);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v80,
      *((__int64 *)&v107[0] + 1));
    v22 = Url::TryCreate(&UrlComponents);
    ATL::CStringData::Release((ATL::CStringData *)(v80 - 24));
    if ( !v22 )
    {
      v23 = &base;
      if ( *((_QWORD *)&v107[0] + 1) )
        v23 = (const WCHAR *)*((_QWORD *)&v107[0] + 1);
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        0,
        "aadcloudap.cpp",
        1767,
        "enterpriseSTSInfo authorityUri is not a valid url",
        v23);
      LODWORD(v68) = 1768;
LABEL_31:
      LODWORD(v63) = -2147187424;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v63, "aadcloudap.cpp", v68, "HRESULT", &base);
      v75 = -1073445600;
      ATL::CStringData::Release((ATL::CStringData *)(v125 - 24));
      v24 = v127;
LABEL_32:
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
LABEL_33:
      v12 = v74;
      goto LABEL_34;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v80,
      (__int64)v96);
    v26 = Url::TryCreate(&v124);
    ATL::CStringData::Release((ATL::CStringData *)(v80 - 24));
    if ( !v26 )
    {
      v27 = &base;
      if ( v96 )
        v27 = v96;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        0,
        "aadcloudap.cpp",
        1773,
        "tokenUpdateInfo authorityUri is not a valid url",
        v27);
      LODWORD(v68) = 1774;
      goto LABEL_31;
    }
    v28 = *(_QWORD *)Url::Host(&v124, &v78);
    v29 = (_QWORD *)Url::Host(&UrlComponents, v151);
    v30 = _o__wcsicmp(*v29, v28) == 0;
    v77 = v30;
    ATL::CStringData::Release((struct _AP_BLOB *)((char *)v151[0] - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v78 - 24));
    v31 = &base;
    if ( *((_QWORD *)&v107[0] + 1) )
      v31 = (const WCHAR *)*((_QWORD *)&v107[0] + 1);
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      0,
      "aadcloudap.cpp",
      1778,
      "token enterpriseSTSInfo authorityUri",
      v31);
    v32 = &base;
    if ( v96 )
      v32 = v96;
    LODWORD(v69) = 1779;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, 0, "aadcloudap.cpp", v69, "tokenUpdateInfo authorityUri", v32);
    ATL::CStringData::Release((ATL::CStringData *)(v125 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v127 - 24));
  }
  else
  {
LABEL_45:
    v30 = v77;
  }
  if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v151[0] = (struct _AP_BLOB *)a5[3];
    v78 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5050,
      (__int64)&byte_1800D26E7,
      (__int64)v149,
      v33,
      (__int64)&v78,
      (const WCHAR **)v151);
  }
  if ( v30 )
  {
    if ( v74 && IsTimeOlderThan(v94, 3, 1) )
    {
      LODWORD(v66) = 1870;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        4,
        0,
        "aadcloudap.cpp",
        v66,
        "Skipping enterprise token refresh.",
        &base);
      if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
        McTemplateU0xx_EventWriteTransfer(v35, v34, Buf2[1], v94);
      goto LABEL_97;
    }
    v152 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v80);
    AutoPasswordExpiryInfo::AutoPasswordExpiryInfo((AutoPasswordExpiryInfo *)v84, this);
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_EnterpriseSTS_RefreshToken_CorrelationID,
        a5[3]);
    v36 = &base;
    if ( a5[3] )
      v36 = a5[3];
    LODWORD(v66) = 1796;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "aadcloudap.cpp",
      v66,
      "EnterpriseSTS Refresh token correlation ID",
      v36);
    if ( v74 && (_DWORD)Size == DWORD2(v110) && (_DWORD)Size && !memcmp_0(Buf1, Buf2[0], (unsigned int)Size) )
    {
      v76 = 1;
      LODWORD(v70) = 1806;
      WPPTraceLogA(
        4,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        4,
        0,
        "aadcloudap.cpp",
        v70,
        "Skipping unnecessary enterprise token refresh (the given token is the same as existing one).",
        &base);
      if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_SameTokenIsNotRefreshed,
          v37,
          1,
          v151);
    }
    else
    {
      v76 = 0;
      if ( *((_QWORD *)&v108 + 1) )
      {
        CSecureString::operator=((__int64)&v80, *((__int64 *)&v108 + 1));
        (*(void (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)this + 32LL))(
          this,
          *((_QWORD *)&v108 + 1));
        *((_QWORD *)&v108 + 1) = 0;
      }
      ReleaseEnterpriseTokenInfo(this, (struct _AadApPluginEnterpriseTokenInfo *)&v110);
      if ( *((_QWORD *)&v113 + 1) )
      {
        (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)this + 32LL))(this);
        *((_QWORD *)&v113 + 1) = 0;
      }
      v38 = (struct _AadApPluginKeyInfo *)v112;
      if ( v74 )
        v38 = (struct _AadApPluginKeyInfo *)v95;
      p_Size = (struct _AP_BLOB *)((char *)&v110 + 8);
      if ( v74 )
        p_Size = (struct _AP_BLOB *)&Size;
      refreshed = EnterpriseSTSHelper::RefreshEnterpriseSTSTokenLogon(
                    this,
                    v105,
                    (struct DiagnosticContext *)a5,
                    *v79,
                    p_Size,
                    v38,
                    (struct _AadApPluginEnterpriseSTSInfo *)v107,
                    (struct AutoPasswordExpiryInfo *)v84);
      v75 = refreshed;
      if ( refreshed >= 0 )
      {
        v41 = IsTimeOlderThan((__int64)Buf2[1], 3, 1);
        v42 = 0;
        if ( !v41 )
          goto LABEL_170;
        v75 = -1073740964;
        if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_EnterpriseSTS_RefreshToken_TokenIsExpired,
            a5[3]);
          v42 = 0;
        }
        if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
        {
          v151[0] = (struct _AP_BLOB *)"Token is expired";
          LODWORD(v79) = v75;
          v78 = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (__int64)&dword_1800E5050,
            (__int64)&dword_1800D26A4,
            (__int64)v149,
            v43,
            (__int64)&v78,
            (__int64)&v79,
            (const unsigned __int16 **)v151);
          v42 = 0;
        }
        refreshed = v75;
        if ( v75 < 0 )
        {
          LODWORD(v71) = 1845;
        }
        else
        {
LABEL_170:
          if ( *((_QWORD *)&v108 + 1)
            && *(_DWORD *)(v80 - 16) != v42
            && !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                                &v80,
                                *((_QWORD *)&v108 + 1)) )
          {
            goto LABEL_94;
          }
          v75 = -1073741790;
          if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_RefreshToken_Mismatching_User_Subject,
              a5[3]);
          if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
          {
            v151[0] = (struct _AP_BLOB *)"Subject don't match";
            LODWORD(v79) = v75;
            v78 = 2048;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (__int64)&dword_1800E5050,
              (__int64)byte_1800D2661,
              (__int64)v149,
              v44,
              (__int64)&v78,
              (__int64)&v79,
              (const unsigned __int16 **)v151);
          }
          refreshed = v75;
          if ( v75 < 0 )
          {
            LODWORD(v71) = 1856;
          }
          else
          {
LABEL_94:
            refreshed = TokenInfoSerializeHelper::SerializeTokenInfo(this, v99, &v152, 3);
            v75 = refreshed;
            if ( refreshed >= 0 )
            {
              *v87 = (unsigned __int8 *)*((_QWORD *)&v152 + 1);
              *v86 = v152;
              ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
              CSecureString::~CSecureString((CSecureString *)&v80);
LABEL_97:
              v76 = 0;
              goto LABEL_33;
            }
            LODWORD(v71) = 1863;
          }
        }
      }
      else
      {
        LODWORD(v71) = 1837;
      }
      LODWORD(v64) = refreshed;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v64, "aadcloudap.cpp", v71, "NTSTATUS", &base);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
    CSecureString::~CSecureString((CSecureString *)&v80);
    goto LABEL_33;
  }
  if ( *((_DWORD *)a2 + 11) != 1 )
    goto LABEL_33;
  if ( v74 && IsTimeOlderThan(v94, 3, 1) )
  {
    LODWORD(v66) = 2003;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v66, "Skipping token refresh.", &base);
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McTemplateU0xx_EventWriteTransfer(v46, v45, v103, v94);
    goto LABEL_33;
  }
  if ( dword_1800E60F0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800E60F0);
    if ( dword_1800E60F0 == -1 )
    {
      ::Size = RtlLengthRequiredSid(5u);
      Init_thread_footer(&dword_1800E60F0);
    }
  }
  v80 = 0;
  AutoPasswordExpiryInfo::AutoPasswordExpiryInfo(
    (AutoPasswordExpiryInfo *)v84,
    this,
    (struct _APPLUGIN_USER_INFO *)((char *)v82 + 96),
    v119 != 0);
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(Microsoft_Windows_AAD_Context, Aad_CloudAPPlugin_RefreshToken_CorrelationID, a5[3]);
  v47 = &base;
  if ( a5[3] )
    v47 = a5[3];
  LODWORD(v66) = 1887;
  LODWORD(v62) = v74;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, v62, "aadcloudap.cpp", v66, "Refresh token correlation ID", v47);
  if ( v74 && (_DWORD)Size == v100 && (_DWORD)Size && !memcmp_0(Buf1, v101, (unsigned int)Size) )
  {
    v76 = 1;
    LODWORD(v72) = 1897;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "aadcloudap.cpp",
      v72,
      "Skipping unnecessary token refresh (the given token is the same as existing one).",
      &base);
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_SameTokenIsNotRefreshed,
        v48,
        1,
        &v152);
    v24 = v85;
    goto LABEL_32;
  }
  v76 = 0;
  v12 = v74;
  v49 = (struct _AadApPluginKeyInfo *)&v104;
  if ( v74 )
    v49 = (struct _AadApPluginKeyInfo *)v95;
  v50 = (struct _AP_BLOB *)&v100;
  if ( v74 )
    v50 = (struct _AP_BLOB *)&Size;
  v51 = RefreshTokenLogon(
          this,
          *v79,
          v79[1],
          (struct DiagnosticContext *)a5,
          v50,
          v49,
          (struct _AP_BLOB *)((unsigned __int64)&v100 & -(__int64)v74),
          ~(8 * (unsigned __int8)*((_DWORD *)v79 + 10)) & 0x20 | 0x48u,
          (struct _AadApPluginVsmBindingKeys *)v88,
          &v83,
          (struct _AadApPluginTokenInfo *)v128,
          &v81);
  v75 = v51;
  if ( v51 >= 0 )
  {
    if ( v82 && v83 )
    {
      DumpGroupSids(v83);
      v52 = (const void *)*((_QWORD *)v82 + 2);
      if ( v52 )
      {
        v53 = (const void *)*((_QWORD *)v83 + 2);
        if ( v53 )
        {
          if ( !memcmp_0(v52, v53, ::Size) )
            goto LABEL_171;
        }
      }
      v75 = -1073741790;
      if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_RefreshToken_Mismatching_User_Sids,
          a5[3]);
      if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
      {
        v151[0] = (struct _AP_BLOB *)"User SIDs don't match";
        LODWORD(v79) = v75;
        v78 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&dword_1800E5050,
          (__int64)&word_1800D261E,
          (__int64)v149,
          v54,
          (__int64)&v78,
          (__int64)&v79,
          (const unsigned __int16 **)v151);
      }
      v51 = v75;
      if ( v75 >= 0 )
      {
LABEL_171:
        if ( !IsTokenExpired((struct _AadApPluginTokenInfo *)v128) )
          goto LABEL_143;
        v75 = -1073740964;
        if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_RefreshToken_TokenIsExpired,
            a5[3]);
        if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
        {
          v151[0] = (struct _AP_BLOB *)"Token is expired";
          LODWORD(v79) = v75;
          v78 = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (__int64)&dword_1800E5050,
            (__int64)byte_1800D25DB,
            (__int64)v149,
            v55,
            (__int64)&v78,
            (__int64)&v79,
            (const unsigned __int16 **)v151);
        }
        v51 = v75;
        if ( v75 < 0 )
        {
          LODWORD(v73) = 1948;
        }
        else
        {
LABEL_143:
          v130 = v107[0];
          v131 = v107[1];
          v132 = v108;
          v133 = v109;
          v134 = v110;
          v135 = *(_OWORD *)Buf2;
          v136 = v112[0];
          v137 = v112[1];
          v138 = v112[2];
          v139 = v113;
          v140 = v114;
          memset_0(v107, 0, 0xA8u);
          v141 = 0;
          v56 = AutoPasswordExpiryInfo::ApplyPasswordChangeClaims(
                  (AutoPasswordExpiryInfo *)v84,
                  v83,
                  (struct _AadApPluginTokenInfo *)v128);
          v57 = v142;
          if ( !v56 )
            v57 = v115;
          v142 = v57;
          v129 = v102;
          v58 = v143;
          if ( !v143 )
          {
            if ( v116 > 0 )
              v58 = v116;
            v143 = v58;
          }
          v144 = v117;
          v145 = v118;
          v51 = SetVsmBindingKeys(this, (struct _AadApPluginVsmBindingKeys *)v88, (struct _AadApPluginTokenInfo *)v128);
          v75 = v51;
          if ( v51 >= 0 )
          {
            v51 = TokenInfoSerializeHelper::SerializeTokenInfo(this, v128, &v80, 3);
            v75 = v51;
            if ( v51 >= 0 )
            {
              *v87 = (unsigned __int8 *)*((_QWORD *)&v80 + 1);
              *v86 = v80;
              if ( (_QWORD)v152 )
              {
                *(_QWORD *)v152 = v81;
                v81 = 0;
              }
              goto LABEL_122;
            }
            LODWORD(v73) = 1990;
          }
          else
          {
            LODWORD(v73) = 1984;
          }
        }
      }
      else
      {
        LODWORD(v73) = 1939;
      }
    }
    else
    {
      LODWORD(v73) = 1926;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, 0, "aadcloudap.cpp", v73, "userInfo is not defined", &base);
      v51 = -1073741595;
      v75 = -1073741595;
      LODWORD(v73) = 1927;
    }
  }
  else
  {
    LODWORD(v73) = 1922;
  }
  LODWORD(v65) = v51;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v65, "aadcloudap.cpp", v73, "NTSTATUS", &base);
LABEL_122:
  ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
LABEL_34:
  v20 = v75;
  if ( v75 < 0 )
    goto LABEL_35;
  v25 = v77;
LABEL_158:
  ReleaseUserInfoData(this, &v82, (struct _AadApPluginTokenInfo *)v99);
  ReleaseUserInfoData(this, &v83, (struct _AadApPluginTokenInfo *)v128);
  ReleaseTokenUpdateInfo(this, (struct _AadApPluginTokenUpdateInfo *)v91);
  if ( v81 )
    FreeSupplementalCredentials(this, v81);
  ReleaseVsmBindingKeys(this, (struct _AadApPluginVsmBindingKeys *)v88);
  if ( v148 )
    EventActivityIdControl(4u, &ActivityId);
  v147 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    *(_QWORD *)&v152 = a5[3];
    LODWORD(v79) = v76;
    v77 = v12;
    LODWORD(v81) = v25;
    LODWORD(v80) = v75;
    v151[0] = (struct _AP_BLOB *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5050,
      (__int64)&word_1800D255E,
      (__int64)v149,
      v59,
      (__int64)v151,
      (__int64)&v80,
      (__int64)&v81,
      (__int64)&v77,
      (__int64)&v79,
      (const WCHAR **)&v152);
  }
  v60 = v75;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveHead(
    a5 + 8,
    &v152);
  ATL::CStringData::Release((ATL::CStringData *)(v152 - 24));
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v147);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v146);
  return v60;
}

```

## disassembly

```asm
0x1800127e8  mov     [rsp-8+arg_8], rbx
0x1800127ed  push    rbp
0x1800127ee  push    rsi
0x1800127ef  push    rdi
0x1800127f0  push    r12
0x1800127f2  push    r13
0x1800127f4  push    r14
0x1800127f6  push    r15
0x1800127f8  lea     rbp, [rsp-6C0h]
0x180012800  sub     rsp, 7C0h
0x180012807  mov     rax, cs:__security_cookie
0x18001280e  xor     rax, rsp
0x180012811  mov     [rbp+6F0h+var_38], rax
0x180012818  mov     rbx, r9
0x18001281b  mov     [rbp+6F0h+var_58], rbx
0x180012822  mov     rdi, r8
0x180012825  mov     r12, rdx
0x180012828  mov     [rsp+7F0h+var_778], rdx
0x18001282d  mov     r15, rcx
0x180012830  mov     r13, [rbp+6F0h+arg_20]
0x180012837  mov     r14, [rbp+6F0h+arg_28]
0x18001283e  mov     [rbp+6F0h+var_720], r14
0x180012842  mov     rcx, [rbp+6F0h+arg_30]
0x180012849  mov     [rbp+6F0h+var_728], rcx
0x18001284d  mov     rsi, [rbp+6F0h+arg_38]
0x180012854  mov     qword ptr [rbp+6F0h+var_48], rsi
0x18001285b  mov     [rsp+7F0h+var_78C], 0
0x180012863  mov     [rsp+7F0h+var_780], rdx
0x180012868  xor     edx, edx; Val
0x18001286a  mov     r8d, 268h; Size
0x180012870  lea     rcx, [rbp+6F0h+var_670]; void *
0x180012877  call    memset_0
0x18001287c  xor     edx, edx; Val
0x18001287e  mov     r8d, 268h; Size
0x180012884  lea     rcx, [rbp+6F0h+var_320]; void *
0x18001288b  call    memset_0
0x180012890  xor     edx, edx; Val
0x180012892  lea     r8d, [rdx+58h]; Size
0x180012896  lea     rcx, [rbp+6F0h+var_6E0]; void *
0x18001289a  call    memset_0
0x18001289f  xor     edx, edx
0x1800128a1  mov     [rbp+6F0h+var_758], rdx
0x1800128a5  mov     [rbp+6F0h+var_750], rdx
0x1800128a9  mov     [rbp+6F0h+var_760], rdx
0x1800128ad  mov     [rbp+6F0h+var_718], rdx
0x1800128b1  xorps   xmm0, xmm0
0x1800128b4  xor     eax, eax
0x1800128b6  movups  [rbp+6F0h+var_710], xmm0
0x1800128ba  movups  [rbp+6F0h+var_700], xmm0
0x1800128be  mov     [rbp+6F0h+var_6F0], rax
0x1800128c2  mov     [rsp+7F0h+var_784], edx
0x1800128c6  mov     rcx, rbx; struct _AP_BLOB *
0x1800128c9  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x1800128ce  mov     bl, al
0x1800128d0  mov     [rsp+7F0h+var_790], al
0x1800128d4  mov     [rsp+7F0h+var_788], dl
0x1800128d8  lea     r9, [rsp+7F0h+var_78C]
0x1800128dd  lea     r8, aDorefreshtoken; "DoRefreshToken"
0x1800128e4  lea     rdx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x1800128eb  lea     rcx, [rbp+6F0h+var_B0]
0x1800128f2  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800128f7  nop
0x1800128f8  xor     eax, eax
0x1800128fa  mov     [rbp+6F0h+var_80], eax
0x180012900  mov     [rbp+6F0h+var_7C], al
0x180012906  lea     rcx, [rbp+6F0h+var_80]
0x18001290d  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180012912  mov     eax, cs:dword_1800E5050
0x180012918  cmp     eax, 5
0x18001291b  jbe     short loc_180012986
0x18001291d  mov     rdx, 400000000000h
0x180012927  lea     rcx, dword_1800E5050
0x18001292e  call    _tlgKeywordOn
0x180012933  xor     edx, edx
0x180012935  test    al, al
0x180012937  jz      short loc_180012986
0x180012939  mov     qword ptr [rbp+6F0h+var_770], 1000000h
0x180012941  cmp     [rbp+6F0h+var_7C], dl
0x180012947  jz      short loc_180012960
0x180012949  lea     rcx, [rbp+6F0h+ActivityId]; struct _GUID *
0x180012950  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180012955  test    al, al
0x180012957  lea     r9, [rbp+6F0h+ActivityId]
0x18001295e  jz      short loc_180012963
0x180012960  mov     r9, rdx
0x180012963  lea     rax, [rbp+6F0h+var_770]
0x180012967  mov     [rsp+7F0h+var_7D0], rax
0x18001296c  lea     r8, [rbp+6F0h+var_78]
0x180012973  lea     rdx, byte_1800D2729
0x18001297a  lea     rcx, dword_1800E5050
0x180012981  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180012986  mov     [rbp+6F0h+var_680], r13
0x18001298a  lea     rcx, [r13+40h]
0x18001298e  lea     rdx, aDorefreshtoken_0; "DoRefreshToken"
0x180012995  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x18001299a  nop
0x18001299b  xor     edx, edx
0x18001299d  test    r15, r15
0x1800129a0  jz      loc_180013B27
0x1800129a6  test    r12, r12
0x1800129a9  jz      loc_180013B27
0x1800129af  test    rdi, rdi
0x1800129b2  jz      loc_180013B27
0x1800129b8  test    r14, r14
0x1800129bb  jz      loc_180013B27
0x1800129c1  mov     rax, [rbp+6F0h+var_728]
0x1800129c5  test    rax, rax
0x1800129c8  jz      loc_180013B27
0x1800129ce  mov     [r14], rdx
0x1800129d1  mov     [rax], edx
0x1800129d3  test    rsi, rsi
0x1800129d6  jz      short loc_1800129DB
0x1800129d8  mov     [rsi], rdx
0x1800129db  lea     rcx, [rsp+7F0h+var_780]; this
0x1800129e0  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x1800129e5  test    al, al
0x1800129e7  jnz     short loc_180012A43
0x1800129e9  lea     r14, base
0x1800129f0  mov     [rsp+7F0h+var_7B0], r14
0x1800129f5  lea     rax, aHresult; "HRESULT"
0x1800129fc  mov     [rsp+7F0h+var_7B8], rax
0x180012a01  mov     dword ptr [rsp+7F0h+var_7C0], 6C2h
0x180012a09  lea     rcx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180012a10  mov     [rsp+7F0h+var_7C8], rcx
0x180012a15  mov     dword ptr [rsp+7F0h+var_7D0], 80048451h
0x180012a1d  mov     edi, 2
0x180012a22  mov     r9d, edi
0x180012a25  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180012a2c  mov     ecx, edi
0x180012a2e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180012a33  mov     r8d, 0C0048451h
0x180012a39  mov     [rsp+7F0h+var_78C], r8d
0x180012a3e  jmp     loc_180012C6E
0x180012a43  lea     r9, [rbp+6F0h+var_670]; struct _AadApPluginTokenInfo *
0x180012a4a  lea     r8, [rbp+6F0h+var_758]; struct _APPLUGIN_USER_INFO **
0x180012a4e  mov     rdx, rdi; struct _AP_BLOB *
0x180012a51  mov     rcx, r15; struct AadContextFunctions *
0x180012a54  call    ?DeserializeTokenInfo@TokenInfoSerializeHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@PEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@@Z; TokenInfoSerializeHelper::DeserializeTokenInfo(AadContextFunctions *,_AP_BLOB *,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *)
0x180012a59  mov     [rsp+7F0h+var_78C], eax
0x180012a5d  xor     r8d, r8d
0x180012a60  lea     r14, base
0x180012a67  lea     edi, [r8+2]
0x180012a6b  test    eax, eax
0x180012a6d  jns     short loc_180012AB0
0x180012a6f  mov     [rsp+7F0h+var_7B0], r14
0x180012a74  lea     rcx, aNtstatus; "NTSTATUS"
0x180012a7b  mov     [rsp+7F0h+var_7B8], rcx
0x180012a80  mov     dword ptr [rsp+7F0h+var_7C0], 6CAh
0x180012a88  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180012a8f  xor     edx, edx
0x180012a91  lea     rcx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180012a98  mov     [rsp+7F0h+var_7C8], rcx
0x180012a9d  mov     dword ptr [rsp+7F0h+var_7D0], eax
0x180012aa1  mov     r9d, edi
0x180012aa4  mov     ecx, edi
0x180012aa6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180012aab  jmp     loc_180012C60
0x180012ab0  mov     eax, [rbp+6F0h+var_490]
0x180012ab6  mov     dword ptr [rbp+6F0h+var_718], eax
0x180012ab9  movsd   xmm0, [rbp+6F0h+var_48C]
0x180012ac1  movsd   [rbp+6F0h+var_718+4], xmm0
0x180012ac6  mov     eax, [rbp+6F0h+var_484]
0x180012acc  mov     dword ptr [rbp+6F0h+var_710+4], eax
0x180012acf  mov     dword ptr [rbp+6F0h+var_710+8], r8d
0x180012ad3  movaps  xmm0, [rbp+6F0h+var_480]
0x180012ada  movdqu  [rbp+6F0h+var_700], xmm0
0x180012adf  mov     dword ptr [rbp+6F0h+var_6F0], r8d
0x180012ae3  lea     rsi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180012aea  test    bl, bl
0x180012aec  jz      loc_180012E55
0x180012af2  lea     r8, [rbp+6F0h+var_6E0]; struct _AadApPluginTokenUpdateInfo *
0x180012af6  mov     rdx, [rbp+6F0h+var_58]; struct _AP_BLOB *
0x180012afd  mov     rcx, r15; struct AadContextFunctions *
0x180012b00  call    ?DeserializeTokenUpdateInfo@TokenInfoSerializeHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@PEAU_AadApPluginTokenUpdateInfo@@@Z; TokenInfoSerializeHelper::DeserializeTokenUpdateInfo(AadContextFunctions *,_AP_BLOB *,_AadApPluginTokenUpdateInfo *)
0x180012b05  mov     [rsp+7F0h+var_78C], eax
0x180012b09  xor     r8d, r8d
0x180012b0c  test    eax, eax
0x180012b0e  jns     short loc_180012B31
0x180012b10  mov     [rsp+7F0h+var_7B0], r14
0x180012b15  lea     rcx, aNtstatus; "NTSTATUS"
0x180012b1c  mov     [rsp+7F0h+var_7B8], rcx
0x180012b21  mov     dword ptr [rsp+7F0h+var_7C0], 6D8h
0x180012b29  mov     r8, rsi
0x180012b2c  jmp     loc_180012A8F
0x180012b31  mov     rdx, [rbp+6F0h+var_690]; unsigned __int16 *
0x180012b35  test    rdx, rdx
0x180012b38  jz      short loc_180012B4B
0x180012b3a  cmp     [rdx], r8w
0x180012b3e  jz      short loc_180012B4B
0x180012b40  mov     rcx, r13; this
0x180012b43  call    ?SetCorrelationId@DiagnosticContext@@QEAAXPEBG@Z; DiagnosticContext::SetCorrelationId(ushort const *)
0x180012b48  xor     r8d, r8d
0x180012b4b  cmp     qword ptr [rbp+6F0h+var_568+8], r8
0x180012b52  jz      loc_180012E55
0x180012b58  cmp     [rbp+6F0h+var_698], r8
0x180012b5c  jz      loc_180012E55
0x180012b62  lea     rcx, [rbp+6F0h+UrlComponents]; this
0x180012b69  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x180012b6e  nop
0x180012b6f  lea     rcx, [rbp+6F0h+var_400]; this
0x180012b76  call    ??0Url@@QEAA@XZ; Url::Url(void)
0x180012b7b  nop
0x180012b7c  mov     rdx, qword ptr [rbp+6F0h+var_568+8]
0x180012b83  lea     rcx, [rbp+6F0h+var_770]
0x180012b87  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180012b8c  nop
0x180012b8d  lea     rdx, [rbp+6F0h+var_770]
0x180012b91  lea     rcx, [rbp+6F0h+UrlComponents]; lpUrlComponents
0x180012b98  call    ?TryCreate@Url@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::TryCreate(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180012b9d  mov     bl, al
0x180012b9f  mov     rcx, qword ptr [rbp+6F0h+var_770]
0x180012ba3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012ba7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012bac  xor     edx, edx
0x180012bae  test    bl, bl
0x180012bb0  jnz     loc_180012CA4
0x180012bb6  mov     rcx, r14
0x180012bb9  mov     rax, qword ptr [rbp+6F0h+var_568+8]
0x180012bc0  test    rax, rax
0x180012bc3  cmovnz  rcx, rax
0x180012bc7  mov     [rsp+7F0h+var_7B0], rcx
0x180012bcc  lea     rax, aEnterprisestsi_0; "enterpriseSTSInfo authorityUri is not a"...
0x180012bd3  mov     [rsp+7F0h+var_7B8], rax
0x180012bd8  mov     dword ptr [rsp+7F0h+var_7C0], 6E7h
0x180012be0  lea     rbx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180012be7  mov     [rsp+7F0h+var_7C8], rbx
0x180012bec  mov     [rsp+7F0h+var_7D0], rdx
0x180012bf1  mov     r9d, edi
0x180012bf4  mov     r8, rsi
0x180012bf7  mov     ecx, edi
0x180012bf9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180012bfe  mov     [rsp+7F0h+var_7B0], r14
0x180012c03  lea     rax, aHresult; "HRESULT"
0x180012c0a  mov     [rsp+7F0h+var_7B8], rax
0x180012c0f  mov     dword ptr [rsp+7F0h+var_7C0], 6E8h
0x180012c17  mov     [rsp+7F0h+var_7C8], rbx
0x180012c1c  mov     dword ptr [rsp+7F0h+var_7D0], 80048520h
0x180012c24  mov     r9d, edi
0x180012c27  mov     r8, rsi
0x180012c2a  xor     edx, edx
0x180012c2c  mov     ecx, edi
0x180012c2e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180012c33  mov     [rsp+7F0h+var_78C], 0C0048520h
0x180012c3b  mov     rcx, [rbp+6F0h+var_398]
0x180012c42  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012c46  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012c4b  nop
0x180012c4c  mov     rcx, [rbp+6F0h+var_328]
0x180012c53  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012c57  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012c5c  mov     bl, [rsp+7F0h+var_790]
0x180012c60  mov     r8d, [rsp+7F0h+var_78C]; int
0x180012c65  test    r8d, r8d
0x180012c68  jns     loc_180013B61
0x180012c6e  mov     esi, [rsp+7F0h+var_784]
0x180012c72  test    esi, esi
0x180012c74  setnz   al
0x180012c77  mov     byte ptr [rsp+7F0h+var_7C0], bl; bool
0x180012c7b  mov     byte ptr [rsp+7F0h+var_7C8], al; bool
0x180012c7f  mov     eax, [rbp+6F0h+var_4A8]
0x180012c85  mov     dword ptr [rsp+7F0h+var_7D0], eax; int
0x180012c89  mov     r9, [rbp+6F0h+var_590]; unsigned __int16 *
0x180012c90  lea     rdx, aDorefreshtoken_0; "DoRefreshToken"
0x180012c97  mov     rcx, r13; struct DiagnosticContext *
0x180012c9a  call    ?LogDiagnosticEvent@DiagnosticContext@@SAXAEAV1@PEBGJ1H_N2@Z; DiagnosticContext::LogDiagnosticEvent(DiagnosticContext &,ushort const *,long,ushort const *,int,bool,bool)
0x180012c9f  jmp     loc_180013B65
0x180012ca4  mov     rdx, [rbp+6F0h+var_698]
0x180012ca8  lea     rcx, [rbp+6F0h+var_770]
0x180012cac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180012cb1  nop
0x180012cb2  lea     rdx, [rbp+6F0h+var_770]
0x180012cb6  lea     rcx, [rbp+6F0h+var_400]; lpUrlComponents
0x180012cbd  call    ?TryCreate@Url@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::TryCreate(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180012cc2  mov     bl, al
0x180012cc4  mov     rcx, qword ptr [rbp+6F0h+var_770]
0x180012cc8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012ccc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012cd1  xor     edx, edx
0x180012cd3  test    bl, bl
0x180012cd5  jnz     short loc_180012D3A
0x180012cd7  mov     rcx, r14
0x180012cda  mov     rax, [rbp+6F0h+var_698]
0x180012cde  test    rax, rax
0x180012ce1  cmovnz  rcx, rax
0x180012ce5  mov     [rsp+7F0h+var_7B0], rcx
0x180012cea  lea     rax, aTokenupdateinf_0; "tokenUpdateInfo authorityUri is not a v"...
0x180012cf1  mov     [rsp+7F0h+var_7B8], rax
0x180012cf6  mov     dword ptr [rsp+7F0h+var_7C0], 6EDh
0x180012cfe  lea     rbx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x180012d05  mov     [rsp+7F0h+var_7C8], rbx
0x180012d0a  mov     [rsp+7F0h+var_7D0], rdx
0x180012d0f  mov     r9d, edi
0x180012d12  mov     r8, rsi
0x180012d15  mov     ecx, edi
0x180012d17  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180012d1c  mov     [rsp+7F0h+var_7B0], r14
0x180012d21  lea     rax, aHresult; "HRESULT"
0x180012d28  mov     [rsp+7F0h+var_7B8], rax
0x180012d2d  mov     dword ptr [rsp+7F0h+var_7C0], 6EEh
0x180012d35  jmp     loc_180012C17
  ... truncated ...
```
