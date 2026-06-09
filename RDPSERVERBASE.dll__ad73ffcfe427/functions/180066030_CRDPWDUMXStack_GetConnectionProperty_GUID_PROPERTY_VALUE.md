# CRDPWDUMXStack::GetConnectionProperty(_GUID,__PROPERTY_VALUE *)

- ea: `0x180066030`
- end: `0x180067728`
- name: `?GetConnectionProperty@CRDPWDUMXStack@@UEAAJU_GUID@@PEAU__PROPERTY_VALUE@@@Z`
- size: `5880`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *this, struct _GUID *, struct __PROPERTY_VALUE *)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x18000ce04`
- `0x180053d20`
- `0x180066030`
- `0x18007e9e0`
- `0x18007f42c`
- `0x1800d4788`
- `0x18010fdc0`
- `0x180120a20`
- `0x180120a80`
- `0x18012aeac`
- `0x180176f1c`
- `0x180177608`
- `0x1801776b4`
- `0x180177704`
- `0x180177884`
- `0x180178988`
- `0x180179480`
- `0x180179780`
- `0x18017aac8`
- `0x18017fe64`
- `0x18019b310`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006607e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800676f6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006607e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800676f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006650b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066589`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066623`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066a0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006650b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066589`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066623`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066a0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800665e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800665e8`
- `OLEAUT32!__imp_VariantInit` at `0x180066a41`
- `OLEAUT32!__imp_VariantInit` at `0x180066a41`
- `OLEAUT32!__imp_VariantClear` at `0x180066af4`
- `OLEAUT32!__imp_VariantClear` at `0x180066af4`

## string_xrefs

- `0x180066a52`: `MonitorConfig`
- `0x180067035`: `WDLIB_ExchangeConfigDataEx`
- `0x180067659`: `WDLIB_ExchangeConfigDataEx`
- `0x180066a8d`: `GetProperty for CONN_PROPERTY_MONITOR_CONFIG failed`
- `0x180066ddd`: `ActiveTransportLinkType`
- `0x180066e69`: `GetConnectionProperty(PROPERTY_TYPE_GET_ACTIVE_TRANSPORT_TYPE) - unrecognized current side transport link type.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRDPWDUMXStack::GetConnectionProperty(
        CRDPWDUMXStack *this,
        struct _GUID *a2,
        struct __PROPERTY_VALUE *a3)
{
  __int64 v6; // r15
  __int128 v7; // xmm0
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // r8d
  int v18; // r9d
  _OWORD *v19; // rax
  HLOCAL v20; // rax
  int TSWindowCapabilitySet; // eax
  char *v22; // rcx
  int v23; // eax
  _BYTE *v24; // rax
  int v25; // eax
  struct _WRDS_DYNAMIC_TIME_ZONE_INFORMATION *v26; // rax
  struct _WRDS_DYNAMIC_TIME_ZONE_INFORMATION *v27; // rbx
  _OWORD *v28; // rax
  __int64 v29; // rdx
  __int128 v30; // xmm1
  char *v31; // rcx
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  int v48; // eax
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // r14d
  unsigned int v53; // edx
  __int64 *v54; // rcx
  __int64 v55; // rax
  void (*v56)(void); // rax
  __int64 (__fastcall ***v57)(_QWORD, GUID *, const char **); // rcx
  int v58; // ebx
  int v59; // edx
  int v60; // r8d
  int v61; // r9d
  HLOCAL v62; // rax
  int v63; // ecx
  int v64; // r8d
  int v65; // r9d
  int v66; // ecx
  int v67; // r8d
  int v68; // r9d
  LONGLONG llVal; // rax
  __int64 v70; // rcx
  int v71; // eax
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  char *v75; // rcx
  int v76; // eax
  __int64 v77; // rax
  __int64 (__fastcall ***v78)(_QWORD, GUID *, const char **); // r9
  const char *v79; // rcx
  int v80; // edx
  int v81; // r8d
  int v82; // r9d
  unsigned int v83; // edx
  unsigned int v84; // edx
  unsigned int v85; // r9d
  int v86; // r8d
  int v87; // r9d
  int v88; // eax
  int v89; // ecx
  int v90; // r8d
  int v91; // r9d
  char *v92; // rcx
  int v93; // eax
  __int64 v94; // rax
  int v95; // eax
  int v96; // ecx
  int v97; // r8d
  int v98; // r9d
  int v99; // ebx
  __int64 (__fastcall ***v100)(_QWORD, GUID *, const char **); // rcx
  int v101; // edx
  int v102; // r8d
  int v103; // r9d
  int RailClientCapabilities; // eax
  int v105; // ecx
  int v106; // r8d
  int v107; // r9d
  char *v108; // rdx
  const char **v109; // rax
  int v110; // eax
  int v111; // ecx
  int v112; // r8d
  int v113; // r9d
  int ClientVideoPlaybackMode; // eax
  int v115; // ecx
  int v116; // r8d
  int v117; // r9d
  int ClientAllowsAudioCapture; // eax
  int v119; // ecx
  int v120; // r8d
  int v121; // r9d
  int v122; // eax
  __int64 *v123; // rdx
  int v124; // eax
  const char **v126; // [rsp+30h] [rbp-D0h]
  const char **v127; // [rsp+40h] [rbp-C0h]
  const char **v128; // [rsp+48h] [rbp-B8h]
  _BYTE v129[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v130; // [rsp+54h] [rbp-ACh] BYREF
  RdpNanoTransportLinkTypeHelpers *v131; // [rsp+58h] [rbp-A8h] BYREF
  const char *v132; // [rsp+60h] [rbp-A0h] BYREF
  const char *v133; // [rsp+68h] [rbp-98h] BYREF
  const char *v134; // [rsp+70h] [rbp-90h] BYREF
  const char *v135; // [rsp+78h] [rbp-88h] BYREF
  const char *v136; // [rsp+80h] [rbp-80h] BYREF
  __int64 v137; // [rsp+88h] [rbp-78h] BYREF
  const char **v138; // [rsp+90h] [rbp-70h]
  __int64 v139; // [rsp+98h] [rbp-68h]
  _BYTE *p_pvarg; // [rsp+A0h] [rbp-60h]
  __int64 v141; // [rsp+A8h] [rbp-58h]
  _QWORD v142[2]; // [rsp+B0h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v144[7]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v145[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v146[28]; // [rsp+160h] [rbp+60h]
  char v147; // [rsp+17Ch] [rbp+7Ch] BYREF
  __int16 v148; // [rsp+27Ch] [rbp+17Ch]
  VARIANTARG pvarg; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE *v150; // [rsp+9E8h] [rbp+8E8h]
  __int64 v151; // [rsp+9F0h] [rbp+8F0h]

  ActivityId = *(GUID *)((char *)this + 804);
  EventActivityIdControl(4u, &ActivityId);
  v6 = *((_QWORD *)this + 11);
  if ( !memcmp_0(PROPERTY_TYPE_CONNECTION_GUID, a2, 0x10u) )
  {
    v129[0] = 0;
    v138 = &v132;
    v137 = 3679315;
    p_pvarg = v129;
    LODWORD(v132) = 1;
    v139 = 4;
    v141 = 1;
    v124 = WDLIB_ExchangeConfigDataEx(v6, &v137);
    v12 = v124 | 0x10000000;
    if ( v124 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_173;
      LODWORD(v135) = 11253;
      v108 = byte_180290C81;
LABEL_167:
      v142[0] = "WDLIB_ExchangeConfigDataEx";
      v136 = "GetConnectionProperty";
      v133 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v134 = "Error HResult failed";
      v128 = (const char **)v142;
      v127 = &v136;
      v126 = &v133;
      v109 = &v134;
      goto LABEL_168;
    }
    v123 = TERMINAL_TYPE_RDP_REMOTEAPP;
    if ( v129[0] != 2 )
      v123 = (__int64 *)&TERMINAL_TYPE_REGULAR_DESKTOP;
LABEL_171:
    v9 = SetGuidProperty(a3, (const struct _GUID *)v123);
    goto LABEL_172;
  }
  if ( !memcmp_0(PROPERTY_TYPE_CORRELATIONID_GUID, a2, 0x10u) )
  {
    v7 = *(_OWORD *)((char *)this + 804);
    *(_WORD *)a3 = 4;
    *(_OWORD *)((char *)a3 + 8) = v7;
LABEL_138:
    v12 = 0;
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_LICENSE_GUID, a2, 0x10u) )
  {
    memset_0(v144, 0, 0x610u);
    v137 = 3670319;
    p_pvarg = v144;
    v139 = 0;
    v138 = 0;
    v141 = 1552;
    if ( (int)WDLIB_LoadBalanceQueryInfo(v6, &v137) < 0
      || (v144[0] & 2) == 0
      || (v123 = LICENSE_TYPE_BUILTIN, DWORD1(v144[0])) )
    {
      v123 = LICENSE_TYPE_DEFAULT;
    }
    goto LABEL_171;
  }
  if ( !memcmp_0(PROPERTY_TYPE_AUDIODRIVER_CLSID, a2, 0x10u) )
  {
    v8 = L"{455f6102-c83a-4d07-ba36-b6da9d589ae2}";
LABEL_7:
    v9 = SetStringProperty(a3, v8);
LABEL_172:
    v12 = v9;
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_VIDEODRIVER_CLSID, a2, 0x10u) )
  {
    v8 = L"{cd3aa379-93f4-421b-9802-aeab68b06771}";
    goto LABEL_7;
  }
  if ( !memcmp_0(PROPERTY_TYPE_LOGON_REDIRECTOR_CLSID, a2, 0x10u) )
  {
    v129[0] = 0;
    v138 = &v132;
    v137 = 3679315;
    p_pvarg = v129;
    LODWORD(v132) = 1;
    v139 = 4;
    v141 = 1;
    v122 = WDLIB_ExchangeConfigDataEx(v6, &v137);
    v12 = v122 | 0x10000000;
    if ( v122 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_173;
      LODWORD(v135) = 11303;
      v108 = byte_18028C45D;
      goto LABEL_167;
    }
    if ( (v129[0] & 0xFD) != 0 )
      goto LABEL_158;
    v123 = qword_18024CF38;
    goto LABEL_171;
  }
  if ( !memcmp_0(PROPERTY_TYPE_LOGON_SCREEN_SIZE, a2, 0x10u) )
  {
    *(_WORD *)a3 = 1;
    *((_DWORD *)a3 + 2) = 0;
    goto LABEL_138;
  }
  if ( !memcmp_0(PROPERTY_TYPE_WPF_ENABLE_CLSID, a2, 0x10u) )
  {
    v12 = -805306355;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v131) = 11326;
      v132 = "WDLIB_GetWPFPipeStatus";
      v130 = -805306355;
      v135 = "GetConnectionProperty";
      v134 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v133 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -805306355,
        (unsigned int)&unk_18028FCF0,
        v10,
        v11,
        (__int64)&v133,
        (__int64)&v130,
        (__int64)&v134,
        (__int64)&v131,
        (__int64)&v135,
        (__int64)&v132);
    }
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_REMOTEAPPS_ENABLE_CLSID, a2, 0x10u) )
  {
    v12 = -805306355;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v130 = 11339;
      v133 = "WDLIB_GetRemoteAppsStatus";
      LODWORD(v131) = -805306355;
      v134 = "GetConnectionProperty";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v135 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -805306355,
        (unsigned int)&word_18028C5C6,
        v13,
        v14,
        (__int64)&v135,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v134,
        (__int64)&v133);
    }
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_CLIENT_ALLOWS_DWM_CLSID, a2, 0x10u) )
  {
    v12 = -805306355;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v130 = 11352;
      v133 = "WDLIB_GetClientAllowsDWMStatus";
      LODWORD(v131) = -805306355;
      v134 = "GetConnectionProperty";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v135 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -805306355,
        (unsigned int)&dword_180291DA4,
        v15,
        v16,
        (__int64)&v135,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v134,
        (__int64)&v133);
    }
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_CLIENT_ALLOWS_THEMES_CLSID, a2, 0x10u) )
  {
    v12 = -805306355;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v130 = 11365;
      v133 = "WDLIB_GetClientAllowThemesStatus";
      LODWORD(v131) = -805306355;
      v134 = "GetConnectionProperty";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v135 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -805306355,
        (unsigned int)&unk_18028FE50,
        v17,
        v18,
        (__int64)&v135,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v134,
        (__int64)&v133);
    }
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_CLIENT_ALLOWS_AUDIO_CAPTURE_CLSID, a2, 0x10u) )
  {
    v137 = 3679315;
    p_pvarg = &pvarg;
    v139 = 0;
    v138 = 0;
    v141 = 28;
    ClientAllowsAudioCapture = WDLIB_GetClientAllowsAudioCapture(v6, &v137);
    v12 = ClientAllowsAudioCapture | 0x10000000;
    if ( ClientAllowsAudioCapture < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v132) = 11378;
        v142[0] = "WDLIB_GetClientAllowsAudioCapture";
        LODWORD(v135) = ClientAllowsAudioCapture | 0x10000000;
        v136 = "GetConnectionProperty";
        v133 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v134 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v119,
          (unsigned int)&dword_18028B3A4,
          v120,
          v121,
          (__int64)&v134,
          (__int64)&v135,
          (__int64)&v133,
          (__int64)&v132,
          (__int64)&v136,
          (__int64)v142);
      }
      goto LABEL_173;
    }
    goto LABEL_142;
  }
  if ( !memcmp_0(PROPERTY_TYPE_VIDEO_PLAYBACK_MODE, a2, 0x10u) )
  {
    v137 = 3679315;
    p_pvarg = &pvarg;
    v139 = 0;
    v138 = 0;
    v141 = 28;
    ClientVideoPlaybackMode = WDLIB_GetClientVideoPlaybackMode(v6, &v137);
    v12 = ClientVideoPlaybackMode | 0x10000000;
    if ( ClientVideoPlaybackMode < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v132) = 11391;
        v142[0] = "WDLIB_GetClientVideoPlaybackMode";
        LODWORD(v135) = ClientVideoPlaybackMode | 0x10000000;
        v136 = "GetConnectionProperty";
        v133 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v134 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v115,
          (unsigned int)word_180290D82,
          v116,
          v117,
          (__int64)&v134,
          (__int64)&v135,
          (__int64)&v133,
          (__int64)&v132,
          (__int64)&v136,
          (__int64)v142);
      }
      goto LABEL_173;
    }
    goto LABEL_142;
  }
  if ( !memcmp_0(PROPERTY_TYPE_REMOTE_MM_FILTERS, a2, 0x10u) )
  {
    *(_WORD *)a3 = 3;
    *((_DWORD *)a3 + 2) = 16;
    v19 = LocalAlloc(0x40u, 0x10u);
    *((_QWORD *)a3 + 2) = v19;
    if ( v19 )
    {
      *v19 = xmmword_18024CF58;
      goto LABEL_138;
    }
    goto LABEL_84;
  }
  if ( !memcmp_0(PROPERTY_TYPE_IS_PNP_DISABLED, a2, 0x10u) )
  {
    v137 = 3679327;
    v138 = &v135;
    v139 = 4;
    p_pvarg = &v131;
    LODWORD(v131) = 0;
    LODWORD(v135) = 0;
    v141 = 4;
    v110 = WDLIB_TShareQueryPreRDPVirtualChannelPolicy(v6, &v137);
    v12 = v110 | 0x10000000;
    if ( v110 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v130 = 11422;
        v136 = "WDLIB_TShareQueryPreRDPVirtualChannelPolicy";
        LODWORD(v132) = v110 | 0x10000000;
        v133 = "GetConnectionProperty";
        v134 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v142[0] = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v111,
          (unsigned int)&byte_18028C76F,
          v112,
          v113,
          (__int64)v142,
          (__int64)&v132,
          (__int64)&v134,
          (__int64)&v130,
          (__int64)&v133,
          (__int64)&v136);
      }
      goto LABEL_173;
    }
    if ( (_DWORD)v131 != 1 )
      goto LABEL_173;
    *((_DWORD *)a3 + 2) = 1;
LABEL_137:
    *(_WORD *)a3 = 1;
    goto LABEL_138;
  }
  if ( !memcmp_0(PROPERTY_TYPE_RAIL_CLIENT_CAPABILITIES, a2, 0x10u) )
  {
    v137 = 3679315;
    p_pvarg = &pvarg;
    v139 = 0;
    v138 = 0;
    v141 = 28;
    RailClientCapabilities = WDLIB_GetRailClientCapabilities(v6, &v137);
    v12 = RailClientCapabilities | 0x10000000;
    if ( RailClientCapabilities < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_173;
      LODWORD(v135) = 11437;
      v136 = "WDLIB_GetRailClientCapabilities";
      v108 = byte_18028FB5B;
      v133 = "GetConnectionProperty";
      v134 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v132 = "Error HResult failed";
      v128 = &v136;
      v127 = &v133;
      v126 = &v134;
      v109 = &v132;
LABEL_168:
      v130 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v105,
        (_DWORD)v108,
        v106,
        v107,
        (__int64)v109,
        (__int64)&v130,
        (__int64)v126,
        (__int64)&v135,
        (__int64)v127,
        (__int64)v128);
      goto LABEL_173;
    }
LABEL_142:
    *((_DWORD *)a3 + 2) = pvarg.lVal;
    *(_WORD *)a3 = 1;
    goto LABEL_138;
  }
  if ( !memcmp_0(PROPERTY_TYPE_WINDOW_CAPABILITYSET, a2, 0x10u) )
  {
    *(_WORD *)a3 = 3;
    *((_DWORD *)a3 + 2) = 11;
    v20 = LocalAlloc(0x40u, 0xBu);
    *((_QWORD *)a3 + 2) = v20;
    if ( v20 )
    {
      memset(v142, 0, 11);
      TSWindowCapabilitySet = WDLIB_QueryTSWindowCapabilitySet(v6, v142);
      v22 = (char *)*((_QWORD *)a3 + 2);
      v12 = TSWindowCapabilitySet | 0x10000000;
      if ( TSWindowCapabilitySet >= 0 )
      {
        v23 = *(_DWORD *)((char *)v142 + 7);
        *(_QWORD *)v22 = v142[0];
        *(_DWORD *)(v22 + 7) = v23;
        goto LABEL_138;
      }
      goto LABEL_40;
    }
LABEL_84:
    v12 = -2147024882;
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_MBUTTON_DOWN_POSITION, a2, 0x10u) )
  {
    *(_WORD *)a3 = 3;
    *((_DWORD *)a3 + 2) = 8;
    v24 = LocalAlloc(0x40u, 8u);
    *((_QWORD *)a3 + 2) = v24;
    if ( !v24 )
      goto LABEL_84;
    *(_QWORD *)&pvarg.vt = 3675255;
    *(_OWORD *)&pvarg.decVal.Lo32 = 0u;
    v150 = v24;
    v151 = 8;
    v25 = WDLIB_DDGetMouseButtonDown(v6, &pvarg);
    v12 = v25 | 0x10000000;
    if ( v25 >= 0 )
      goto LABEL_173;
    goto LABEL_39;
  }
  if ( !memcmp_0(&PROPERTY_DYNAMIC_TIME_ZONE_INFORMATION, a2, 0x10u) )
  {
    *(_WORD *)a3 = 3;
    *((_DWORD *)a3 + 2) = 432;
    v26 = (struct _WRDS_DYNAMIC_TIME_ZONE_INFORMATION *)LocalAlloc(0x40u, 0x1B0u);
    *((_QWORD *)a3 + 2) = v26;
    v27 = v26;
    if ( v26 )
    {
      memset_0(v144, 0, 0x1B0u);
      v28 = (_OWORD *)(v6 + 1568);
      v29 = 2;
      v30 = *(_OWORD *)(v6 + 848);
      v31 = &v147;
      v144[0] = *(_OWORD *)(v6 + 832);
      v32 = *(_OWORD *)(v6 + 864);
      v144[1] = v30;
      v33 = *(_OWORD *)(v6 + 880);
      v144[2] = v32;
      v34 = *(_OWORD *)(v6 + 896);
      v144[3] = v33;
      v35 = *(_OWORD *)(v6 + 912);
      v144[4] = v34;
      v36 = *(_OWORD *)(v6 + 928);
      v144[5] = v35;
      v37 = *(_OWORD *)(v6 + 944);
      v144[6] = v36;
      v38 = *(_OWORD *)(v6 + 960);
      v145[0] = v37;
      v39 = *(_OWORD *)(v6 + 976);
      v145[1] = v38;
      v40 = *(_OWORD *)(v6 + 988);
      *(_OWORD *)v146 = v39;
      *(_OWORD *)&v146[12] = v40;
      do
      {
        v41 = v28[1];
        *(_OWORD *)v31 = *v28;
        v42 = v28[2];
        *((_OWORD *)v31 + 1) = v41;
        v43 = v28[3];
        *((_OWORD *)v31 + 2) = v42;
        v44 = v28[4];
        *((_OWORD *)v31 + 3) = v43;
        v45 = v28[5];
        *((_OWORD *)v31 + 4) = v44;
        v46 = v28[6];
        *((_OWORD *)v31 + 5) = v45;
        v47 = v28[7];
        v28 += 8;
        *((_OWORD *)v31 + 6) = v46;
        *((_OWORD *)v31 + 7) = v47;
        v31 += 128;
        --v29;
      }
      while ( v29 );
      v148 = *(_WORD *)(v6 + 1824);
      ConvertDTZIFromWDLIBToWRDS((struct tagWDLIB_DYNAMIC_TIME_ZONE_INFORMATION *)v144, v27);
      goto LABEL_138;
    }
    goto LABEL_84;
  }
  if ( !memcmp_0(PROPERTY_TYPE_GET_REMOTEAPP_HD_SUPPORT_LEVEL, a2, 0x10u) )
  {
    LODWORD(v131) = 0;
    v48 = WDLIB_QueryHiDefRemoteAppMode(v6, &v131);
    v12 = v48 | 0x10000000;
    if ( v48 >= 0 )
    {
      v52 = 0;
      v53 = (unsigned int)v131 & 0x2000000;
      if ( ((unsigned int)v131 & 0x2000000) != 0 )
      {
        if ( ((unsigned int)v131 & 0x1000000) != 0 )
          v52 = 3;
        else
          v52 = (((unsigned int)v131 & 0x800000) != 0) + 1;
      }
      *(_WORD *)a3 = 1;
      v12 = 0;
      *((_DWORD *)a3 + 2) = v52;
      if ( *((_DWORD *)this + 206) )
      {
        v54 = (__int64 *)*((_QWORD *)this + 95);
        if ( v54 )
        {
          v55 = *v54;
          if ( v53 )
            v56 = *(void (**)(void))(v55 + 24);
          else
            v56 = *(void (**)(void))(v55 + 32);
          v56();
          *((_DWORD *)this + 206) = 0;
        }
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v130 = v52;
        v133 = "Returning HiDef RAIL level";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          4,
          (unsigned int)byte_18029254B,
          v50,
          v51,
          (__int64)&v133,
          (__int64)&v130);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v130 = 11532;
      v133 = "Failed to get the HiDef session support";
      LODWORD(v131) = v48 | 0x10000000;
      v134 = "GetConnectionProperty";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v135 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v49,
        (unsigned int)&dword_18028DDBC,
        v50,
        v51,
        (__int64)&v135,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v134,
        (__int64)&v133);
    }
    goto LABEL_173;
  }
  if ( !memcmp_0(PROPERTY_TYPE_GET_REMOTEAPP_FEATURE_FLAGS, a2, 0x10u) )
  {
    v57 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 70);
    v132 = 0;
    v58 = 0;
    LODWORD(v131) = 0;
    if ( v57 )
    {
      v59 = (**v57)(v57, &IID_IRDPCollection, &v132);
      if ( v59 < 0 && (unsigned int)CallbackContext > 3 )
      {
        v130 = v59;
        v133 = "GetConnectionProperty";
        v134 = "Failed to QI for RDP Collection from Platfornm Context";
        v135 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_18028E361,
          v60,
          v61,
          (__int64)&v135,
          (__int64)&v134,
          (__int64)&v130,
          (__int64)&v133);
      }
      if ( v132
        && (*(int (__fastcall **)(const char *, const wchar_t *, RdpNanoTransportLinkTypeHelpers **))(*(_QWORD *)v132 + 32LL))(
             v132,
             L"RDP::RemoteApp::EnableRAILDVC",
             &v131) >= 0
        && (_DWORD)v131 )
      {
        v58 = 1;
      }
    }
    goto LABEL_116;
  }
  if ( !memcmp_0(PROPERTY_TYPE_ENABLE_UNIVERSAL_APPS_FOR_CUSTOM_SHELL, a2, 0x10u) )
  {
    v129[0] = 0;
    pvarg.llVal = (LONGLONG)&v130;
    *(_QWORD *)&pvarg.vt = 3679315;
    v150 = v129;
    v130 = 1;
    pvarg.pRecInfo = (IRecordInfo *)4;
    v151 = 1;
    v95 = WDLIB_ExchangeConfigDataEx(v6, &pvarg);
    v12 = v95 | 0x10000000;
    if ( v95 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v131) = 11606;
        v133 = "WDLIB_ExchangeConfigDataEx";
        LODWORD(v135) = v95 | 0x10000000;
        v134 = "GetConnectionProperty";
        v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v136 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v96,
          (unsigned int)&dword_18028F4F4,
          v97,
          v98,
          (__int64)&v136,
          (__int64)&v135,
          (__int64)&v132,
          (__int64)&v131,
          (__int64)&v134,
          (__int64)&v133);
      }
      goto LABEL_173;
    }
    v99 = 0;
    if ( v129[0] == 2 )
    {
      v100 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 70);
      v132 = 0;
      LODWORD(v131) = 0;
      if ( v100 )
      {
        v101 = (**v100)(v100, &IID_IRDPCollection, &v132);
        if ( v101 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v135) = v101;
          v136 = "GetConnectionProperty";
          v133 = "Failed to QI for RDP Collection from Platfornm Context";
          v134 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_18029060D,
            v102,
            v103,
            (__int64)&v134,
            (__int64)&v133,
            (__int64)&v135,
            (__int64)&v136);
        }
        if ( v132
          && (*(int (__fastcall **)(const char *, const wchar_t *, RdpNanoTransportLinkTypeHelpers **))(*(_QWORD *)v132 + 32LL))(
               v132,
               L"RDP::RemoteApp::EnableRAILShellAppRuntime",
               &v131) >= 0
          && (_DWORD)v131 )
        {
          v99 = 1;
        }
      }
      wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v132);
    }
    *((_DWORD *)a3 + 2) = v99;
    goto LABEL_137;
  }
  if ( memcmp_0(PROPERTY_TYPE_GET_MONITOR_CONFIG, a2, 0x10u) )
  {
    if ( !memcmp_0(PROPERTY_TYPE_GET_RESTRICTED_LOGON, a2, 0x10u) )
    {
      *(_QWORD *)&pvarg.vt = 3670171;
      pvarg.pRecInfo = 0;
      memset_0(v144, 0, 0x8F8u);
      pvarg.llVal = 0;
      v150 = v144;
      v151 = 2296;
      v88 = WDLIB_IcaStackQueryClientData(v6, &pvarg);
      v12 = v88 | 0x10000000;
      if ( v88 >= 0 )
      {
        v92 = (char *)v145 + 12;
        v93 = (LODWORD(v144[0]) >> 12) & 1;
        *(_WORD *)a3 = 1;
        *((_DWORD *)a3 + 2) = v93;
        v12 = 0;
        v94 = 30;
        do
        {
          *v92++ = 0;
          --v94;
        }
        while ( v94 );
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v130 = 11680;
        v133 = "Failed to get PROPERTY_TYPE_GET_RESTRICTED_LOGON because WDLIB_IcaStackQueryClientData failed";
        LODWORD(v131) = v88 | 0x10000000;
        v134 = "GetConnectionProperty";
        v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v135 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v89,
          (unsigned int)&dword_1802928BC,
          v90,
          v91,
          (__int64)&v135,
          (__int64)&v131,
          (__int64)&v132,
          (__int64)&v130,
          (__int64)&v134,
          (__int64)&v133);
      }
      goto LABEL_173;
    }
    if ( !memcmp_0(PROPERTY_TYPE_GET_REDIRECTED_AUTHENTICATION, a2, 0x10u) )
    {
      *(_QWORD *)&pvarg.vt = 3670171;
      pvarg.pRecInfo = 0;
      memset_0(v144, 0, 0x8F8u);
      pvarg.llVal = 0;
      v150 = v144;
      v151 = 2296;
      v71 = WDLIB_IcaStackQueryClientData(v6, &pvarg);
      v12 = v71 | 0x10000000;
      if ( v71 >= 0 )
      {
        v75 = (char *)v145 + 12;
        v76 = (LODWORD(v144[0]) >> 13) & 1;
        *(_WORD *)a3 = 1;
        *((_DWORD *)a3 + 2) = v76;
        v12 = 0;
        v77 = 30;
        do
        {
          *v75++ = 0;
          --v77;
        }
        while ( v77 );
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v130 = 11694;
        v133 = "Failed to get PROPERTY_TYPE_GET_REDIRECTED_AUTHENTICATION because WDLIB_IcaStackQueryClientData failed";
        LODWORD(v131) = v71 | 0x10000000;
        v134 = "GetConnectionProperty";
        v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v135 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v72,
          (unsigned int)byte_18028A60D,
          v73,
          v74,
          (__int64)&v135,
          (__int64)&v131,
          (__int64)&v132,
          (__int64)&v130,
          (__int64)&v134,
          (__int64)&v133);
      }
      goto LABEL_173;
    }
    if ( !memcmp_0(PROPERTY_TYPE_GET_ACTIVE_TRANSPORT_TYPE, a2, 0x10u) )
    {
      v78 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 70);
      v79 = 0;
      v132 = 0;
      v58 = 0;
      if ( v78 )
      {
        v80 = (**v78)(v78, &IID_IRDPCollection, &v132);
        if ( v80 < 0 && (unsigned int)CallbackContext > 3 )
        {
          v130 = v80;
          v133 = "GetConnectionProperty";
          v134 = "Failed to QI for RDP Collection from Platfornm Context";
          v135 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)word_18028DD52,
            v81,
            v82,
            (__int64)&v135,
            (__int64)&v134,
            (__int64)&v130,
            (__int64)&v133);
        }
        v79 = v132;
      }
      if ( !*((_DWORD *)this + 123) )
        v58 = (*((_DWORD *)this + 138) != 0) + 1;
      if ( !*((_DWORD *)this + 126) )
        goto LABEL_116;
      LODWORD(v131) = 0;
      if ( v79
        && (*(int (__fastcall **)(const char *, const wchar_t *, RdpNanoTransportLinkTypeHelpers **))(*(_QWORD *)v79 + 40LL))(
             v79,
             L"ActiveTransportLinkType",
             &v131) >= 0
        && (_DWORD)v131 )
      {
        if ( (_WORD)v131 == 64 )
        {
          v58 |= 2u;
LABEL_116:
          *((_DWORD *)a3 + 2) = v58;
          v12 = 0;
          *(_WORD *)a3 = 1;
          TCntPtr<IRdpVCMgr>::SafeRelease(&v132);
          goto LABEL_173;
        }
        if ( (_WORD)v131 != 1 )
        {
          if ( (_DWORD)v131 == 131074
            || RdpNanoTransportLinkTypeHelpers::IsReflexive((RdpNanoTransportLinkTypeHelpers *)(unsigned int)v131, v83) )
          {
            v58 |= 8u;
          }
          else if ( RdpNanoTransportLinkTypeHelpers::IsRelayed((RdpNanoTransportLinkTypeHelpers *)v85, v84) )
          {
            v58 |= 0x10u;
          }
          else if ( (unsigned int)CallbackContext > 4 )
          {
            v130 = (int)v131;
            v133 = "GetConnectionProperty(PROPERTY_TYPE_GET_ACTIVE_TRANSPORT_TYPE) - unrecognized current side transport link type.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              4,
              (unsigned int)byte_18028ED2B,
              v86,
              v87,
              (__int64)&v133,
              (__int64)&v130);
          }
          goto LABEL_116;
        }
      }
      v58 |= 4u;
      goto LABEL_116;
    }
LABEL_158:
    v12 = -2147467263;
    goto LABEL_173;
  }
  *(_WORD *)a3 = 3;
  *((_DWORD *)a3 + 2) = 12;
  v62 = LocalAlloc(0x40u, 0xCu);
  *((_QWORD *)a3 + 2) = v62;
  if ( !v62 )
    goto LABEL_84;
  if ( !*((_QWORD *)this + 8) )
  {
    v12 = -2147418113;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v130 = -2147418113;
      v133 = "GetConnectionProperty";
      v134 = "m_spConnProperties is NULL";
      v132 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v63,
        (unsigned int)byte_180289AEB,
        v64,
        v65,
        (__int64)&v132,
        (__int64)&v134,
        (__int64)&v130,
        (__int64)&v133);
    }
    goto LABEL_39;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 8) + 24LL))(
          *((_QWORD *)this + 8),
          L"MonitorConfig",
          &pvarg);
  if ( v12 >= 0 )
  {
    llVal = pvarg.llVal;
    v70 = *((_QWORD *)a3 + 2);
    *(_QWORD *)v70 = *pvarg.pllVal;
    *(_DWORD *)(v70 + 8) = *(_DWORD *)(llVal + 8);
  }
  else if ( (unsigned int)CallbackContext > 3 )
  {
    v130 = v12;
    v133 = "GetConnectionProperty";
    v134 = "GetProperty for CONN_PROPERTY_MONITOR_CONFIG failed";
    v132 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v66,
      (unsigned int)&byte_1802918BF,
      v67,
      v68,
      (__int64)&v132,
      (__int64)&v134,
      (__int64)&v130,
      (__int64)&v133);
  }
  VariantClear(&pvarg);
  if ( v12 < 0 )
  {
LABEL_39:
    v22 = (char *)*((_QWORD *)a3 + 2);
LABEL_40:
    LocalFree(v22);
    *((_QWORD *)a3 + 2) = 0;
  }
LABEL_173:
  EventActivityIdControl(2u, &ActivityId);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180066030  mov     [rsp-8+arg_8], rbx
0x180066035  push    rbp
0x180066036  push    rsi
0x180066037  push    rdi
0x180066038  push    r12
0x18006603a  push    r13
0x18006603c  push    r14
0x18006603e  push    r15
0x180066040  lea     rbp, [rsp-900h]
0x180066048  sub     rsp, 0A00h
0x18006604f  mov     rax, cs:__security_cookie
0x180066056  xor     rax, rsp
0x180066059  mov     [rbp+930h+var_38], rax
0x180066060  movups  xmm0, xmmword ptr [rcx+324h]
0x180066067  mov     rbx, rdx
0x18006606a  mov     r13, rcx
0x18006606d  lea     rdx, [rbp+930h+ActivityId]; ActivityId
0x180066071  mov     ecx, 4; ControlCode
0x180066076  movdqu  xmmword ptr [rbp+930h+ActivityId.Data1], xmm0
0x18006607b  mov     rdi, r8
0x18006607e  call    cs:__imp_EventActivityIdControl
0x180066084  mov     r15, [r13+58h]
0x180066088  lea     rcx, PROPERTY_TYPE_CONNECTION_GUID; Buf1
0x18006608f  mov     esi, 10h
0x180066094  mov     rdx, rbx; Buf2
0x180066097  mov     r8d, esi; Size
0x18006609a  call    memcmp_0
0x18006609f  xor     r12d, r12d
0x1800660a2  lea     r14d, [rsi-0Eh]
0x1800660a6  test    eax, eax
0x1800660a8  jz      loc_1800675ED
0x1800660ae  mov     r8d, esi; Size
0x1800660b1  lea     rcx, PROPERTY_TYPE_CORRELATIONID_GUID; Buf1
0x1800660b8  mov     rdx, rbx; Buf2
0x1800660bb  call    memcmp_0
0x1800660c0  test    eax, eax
0x1800660c2  jnz     short loc_1800660DB
0x1800660c4  movups  xmm0, xmmword ptr [r13+324h]
0x1800660cc  mov     word ptr [rdi], 4
0x1800660d1  movdqu  xmmword ptr [rdi+8], xmm0
0x1800660d6  jmp     loc_1800671A0
0x1800660db  mov     r8, rsi; Size
0x1800660de  lea     rcx, PROPERTY_TYPE_LICENSE_GUID; Buf1
0x1800660e5  mov     rdx, rbx; Buf2
0x1800660e8  call    memcmp_0
0x1800660ed  test    eax, eax
0x1800660ef  jz      loc_180067587
0x1800660f5  mov     r8, rsi; Size
0x1800660f8  lea     rcx, PROPERTY_TYPE_AUDIODRIVER_CLSID; Buf1
0x1800660ff  mov     rdx, rbx; Buf2
0x180066102  call    memcmp_0
0x180066107  test    eax, eax
0x180066109  jnz     short loc_18006611F
0x18006610b  lea     rdx, a455f6102C83a4d; "{455f6102-c83a-4d07-ba36-b6da9d589ae2}"
0x180066112  mov     rcx, rdi; struct __PROPERTY_VALUE *
0x180066115  call    ?SetStringProperty@@YAJPEAU__PROPERTY_VALUE@@PEBG@Z; SetStringProperty(__PROPERTY_VALUE *,ushort const *)
0x18006611a  jmp     loc_1800676EB
0x18006611f  mov     r8, rsi; Size
0x180066122  lea     rcx, PROPERTY_TYPE_VIDEODRIVER_CLSID; Buf1
0x180066129  mov     rdx, rbx; Buf2
0x18006612c  call    memcmp_0
0x180066131  test    eax, eax
0x180066133  jnz     short loc_18006613E
0x180066135  lea     rdx, aCd3aa37993f442; "{cd3aa379-93f4-421b-9802-aeab68b06771}"
0x18006613c  jmp     short loc_180066112
0x18006613e  mov     r8, rsi; Size
0x180066141  lea     rcx, PROPERTY_TYPE_LOGON_REDIRECTOR_CLSID; Buf1
0x180066148  mov     rdx, rbx; Buf2
0x18006614b  call    memcmp_0
0x180066150  test    eax, eax
0x180066152  jz      loc_1800674FD
0x180066158  mov     r8, rsi; Size
0x18006615b  lea     rcx, PROPERTY_TYPE_LOGON_SCREEN_SIZE; Buf1
0x180066162  mov     rdx, rbx; Buf2
0x180066165  call    memcmp_0
0x18006616a  test    eax, eax
0x18006616c  jnz     short loc_18006617C
0x18006616e  mov     word ptr [rdi], 1
0x180066173  mov     [rdi+8], r12d
0x180066177  jmp     loc_1800671A0
0x18006617c  mov     r8, rsi; Size
0x18006617f  lea     rcx, PROPERTY_TYPE_WPF_ENABLE_CLSID; Buf1
0x180066186  mov     rdx, rbx; Buf2
0x180066189  call    memcmp_0
0x18006618e  test    eax, eax
0x180066190  jnz     loc_18006622B
0x180066196  mov     eax, cs:CallbackContext
0x18006619c  mov     ecx, 0D000000Dh
0x1800661a1  mov     ebx, ecx
0x1800661a3  cmp     eax, r14d
0x1800661a6  jbe     loc_1800676ED
0x1800661ac  lea     rax, aWdlibGetwpfpip; "WDLIB_GetWPFPipeStatus"
0x1800661b3  mov     dword ptr [rsp+0A30h+var_9D8], 2C3Eh
0x1800661bb  mov     [rsp+0A30h+var_9D0], rax
0x1800661c0  lea     rdx, unk_18028FCF0
0x1800661c7  lea     rax, aGetconnectionp_0; "GetConnectionProperty"
0x1800661ce  mov     [rsp+0A30h+var_9DC], ecx
0x1800661d2  mov     [rsp+0A30h+var_9B8], rax
0x1800661d7  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800661de  mov     [rsp+0A30h+var_9C0], rax
0x1800661e3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800661ea  mov     [rsp+0A30h+var_9C8], rax
0x1800661ef  lea     rax, [rsp+0A30h+var_9D0]
0x1800661f4  mov     [rsp+0A30h+var_9E8], rax
0x1800661f9  lea     rax, [rsp+0A30h+var_9B8]
0x1800661fe  mov     [rsp+0A30h+var_9F0], rax
0x180066203  lea     rax, [rsp+0A30h+var_9D8]
0x180066208  mov     [rsp+0A30h+var_9F8], rax
0x18006620d  lea     rax, [rsp+0A30h+var_9C0]
0x180066212  mov     [rsp+0A30h+var_A00], rax
0x180066217  lea     rax, [rsp+0A30h+var_9DC]
0x18006621c  mov     [rsp+0A30h+var_A08], rax
0x180066221  lea     rax, [rsp+0A30h+var_9C8]
0x180066226  jmp     loc_1800676C0
0x18006622b  mov     r8, rsi; Size
0x18006622e  lea     rcx, PROPERTY_TYPE_REMOTEAPPS_ENABLE_CLSID; Buf1
0x180066235  mov     rdx, rbx; Buf2
0x180066238  call    memcmp_0
0x18006623d  test    eax, eax
0x18006623f  jnz     loc_1800662DA
0x180066245  mov     eax, cs:CallbackContext
0x18006624b  mov     ecx, 0D000000Dh
0x180066250  mov     ebx, ecx
0x180066252  cmp     eax, r14d
0x180066255  jbe     loc_1800676ED
0x18006625b  lea     rax, aWdlibGetremote; "WDLIB_GetRemoteAppsStatus"
0x180066262  mov     [rsp+0A30h+var_9DC], 2C4Bh
0x18006626a  mov     [rsp+0A30h+var_9C8], rax
0x18006626f  lea     rdx, word_18028C5C6
0x180066276  lea     rax, aGetconnectionp_0; "GetConnectionProperty"
0x18006627d  mov     dword ptr [rsp+0A30h+var_9D8], ecx
0x180066281  mov     [rsp+0A30h+var_9C0], rax
0x180066286  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006628d  mov     [rsp+0A30h+var_9D0], rax
0x180066292  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180066299  mov     [rsp+0A30h+var_9B8], rax
0x18006629e  lea     rax, [rsp+0A30h+var_9C8]
0x1800662a3  mov     [rsp+0A30h+var_9E8], rax
0x1800662a8  lea     rax, [rsp+0A30h+var_9C0]
0x1800662ad  mov     [rsp+0A30h+var_9F0], rax
0x1800662b2  lea     rax, [rsp+0A30h+var_9DC]
0x1800662b7  mov     [rsp+0A30h+var_9F8], rax
0x1800662bc  lea     rax, [rsp+0A30h+var_9D0]
0x1800662c1  mov     [rsp+0A30h+var_A00], rax
0x1800662c6  lea     rax, [rsp+0A30h+var_9D8]
0x1800662cb  mov     [rsp+0A30h+var_A08], rax
0x1800662d0  lea     rax, [rsp+0A30h+var_9B8]
0x1800662d5  jmp     loc_1800676C0
0x1800662da  mov     r8, rsi; Size
0x1800662dd  lea     rcx, PROPERTY_TYPE_CLIENT_ALLOWS_DWM_CLSID; Buf1
0x1800662e4  mov     rdx, rbx; Buf2
0x1800662e7  call    memcmp_0
0x1800662ec  test    eax, eax
0x1800662ee  jnz     loc_180066389
0x1800662f4  mov     eax, cs:CallbackContext
0x1800662fa  mov     ecx, 0D000000Dh
0x1800662ff  mov     ebx, ecx
0x180066301  cmp     eax, r14d
0x180066304  jbe     loc_1800676ED
0x18006630a  lea     rax, aWdlibGetclient; "WDLIB_GetClientAllowsDWMStatus"
0x180066311  mov     [rsp+0A30h+var_9DC], 2C58h
0x180066319  mov     [rsp+0A30h+var_9C8], rax
0x18006631e  lea     rdx, dword_180291DA4
0x180066325  lea     rax, aGetconnectionp_0; "GetConnectionProperty"
0x18006632c  mov     dword ptr [rsp+0A30h+var_9D8], ecx
0x180066330  mov     [rsp+0A30h+var_9C0], rax
0x180066335  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006633c  mov     [rsp+0A30h+var_9D0], rax
0x180066341  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180066348  mov     [rsp+0A30h+var_9B8], rax
0x18006634d  lea     rax, [rsp+0A30h+var_9C8]
0x180066352  mov     [rsp+0A30h+var_9E8], rax
0x180066357  lea     rax, [rsp+0A30h+var_9C0]
0x18006635c  mov     [rsp+0A30h+var_9F0], rax
0x180066361  lea     rax, [rsp+0A30h+var_9DC]
0x180066366  mov     [rsp+0A30h+var_9F8], rax
0x18006636b  lea     rax, [rsp+0A30h+var_9D0]
0x180066370  mov     [rsp+0A30h+var_A00], rax
0x180066375  lea     rax, [rsp+0A30h+var_9D8]
0x18006637a  mov     [rsp+0A30h+var_A08], rax
0x18006637f  lea     rax, [rsp+0A30h+var_9B8]
0x180066384  jmp     loc_1800676C0
0x180066389  mov     r8, rsi; Size
0x18006638c  lea     rcx, PROPERTY_TYPE_CLIENT_ALLOWS_THEMES_CLSID; Buf1
0x180066393  mov     rdx, rbx; Buf2
0x180066396  call    memcmp_0
0x18006639b  test    eax, eax
0x18006639d  jnz     loc_180066438
0x1800663a3  mov     eax, cs:CallbackContext
0x1800663a9  mov     ecx, 0D000000Dh
0x1800663ae  mov     ebx, ecx
0x1800663b0  cmp     eax, r14d
0x1800663b3  jbe     loc_1800676ED
0x1800663b9  lea     rax, aWdlibGetclient_2; "WDLIB_GetClientAllowThemesStatus"
0x1800663c0  mov     [rsp+0A30h+var_9DC], 2C65h
0x1800663c8  mov     [rsp+0A30h+var_9C8], rax
0x1800663cd  lea     rdx, unk_18028FE50
0x1800663d4  lea     rax, aGetconnectionp_0; "GetConnectionProperty"
0x1800663db  mov     dword ptr [rsp+0A30h+var_9D8], ecx
0x1800663df  mov     [rsp+0A30h+var_9C0], rax
0x1800663e4  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800663eb  mov     [rsp+0A30h+var_9D0], rax
0x1800663f0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800663f7  mov     [rsp+0A30h+var_9B8], rax
0x1800663fc  lea     rax, [rsp+0A30h+var_9C8]
0x180066401  mov     [rsp+0A30h+var_9E8], rax
0x180066406  lea     rax, [rsp+0A30h+var_9C0]
0x18006640b  mov     [rsp+0A30h+var_9F0], rax
0x180066410  lea     rax, [rsp+0A30h+var_9DC]
0x180066415  mov     [rsp+0A30h+var_9F8], rax
0x18006641a  lea     rax, [rsp+0A30h+var_9D0]
0x18006641f  mov     [rsp+0A30h+var_A00], rax
0x180066424  lea     rax, [rsp+0A30h+var_9D8]
0x180066429  mov     [rsp+0A30h+var_A08], rax
0x18006642e  lea     rax, [rsp+0A30h+var_9B8]
0x180066433  jmp     loc_1800676C0
0x180066438  mov     r8, rsi; Size
0x18006643b  lea     rcx, PROPERTY_TYPE_CLIENT_ALLOWS_AUDIO_CAPTURE_CLSID; Buf1
0x180066442  mov     rdx, rbx; Buf2
0x180066445  call    memcmp_0
0x18006644a  test    eax, eax
0x18006644c  jz      loc_180067436
0x180066452  mov     r8, rsi; Size
0x180066455  lea     rcx, PROPERTY_TYPE_VIDEO_PLAYBACK_MODE; Buf1
0x18006645c  mov     rdx, rbx; Buf2
0x18006645f  call    memcmp_0
0x180066464  test    eax, eax
0x180066466  jz      loc_18006736F
0x18006646c  mov     r8, rsi; Size
0x18006646f  lea     rcx, PROPERTY_TYPE_REMOTE_MM_FILTERS; Buf1
0x180066476  mov     rdx, rbx; Buf2
0x180066479  call    memcmp_0
0x18006647e  test    eax, eax
0x180066480  jnz     short loc_1800664B3
0x180066482  mov     rdx, rsi; uBytes
0x180066485  mov     word ptr [rdi], 3
0x18006648a  lea     ecx, [rax+40h]; uFlags
0x18006648d  mov     [rdi+8], esi
0x180066490  call    cs:__imp_LocalAlloc
0x180066496  mov     [rdi+10h], rax
0x18006649a  test    rax, rax
0x18006649d  jz      loc_180066B7C
0x1800664a3  movups  xmm0, cs:xmmword_18024CF58
0x1800664aa  movdqu  xmmword ptr [rax], xmm0
0x1800664ae  jmp     loc_1800671A0
0x1800664b3  mov     r8, rsi; Size
0x1800664b6  lea     rcx, PROPERTY_TYPE_IS_PNP_DISABLED; Buf1
0x1800664bd  mov     rdx, rbx; Buf2
0x1800664c0  call    memcmp_0
0x1800664c5  test    eax, eax
0x1800664c7  jz      loc_180067280
0x1800664cd  mov     r8, rsi; Size
0x1800664d0  lea     rcx, PROPERTY_TYPE_RAIL_CLIENT_CAPABILITIES; Buf1
0x1800664d7  mov     rdx, rbx; Buf2
0x1800664da  call    memcmp_0
0x1800664df  test    eax, eax
0x1800664e1  jz      loc_1800671A8
0x1800664e7  mov     r8, rsi; Size
0x1800664ea  lea     rcx, PROPERTY_TYPE_WINDOW_CAPABILITYSET; Buf1
0x1800664f1  mov     rdx, rbx; Buf2
0x1800664f4  call    memcmp_0
0x1800664f9  test    eax, eax
0x1800664fb  jnz     short loc_18006655D
0x1800664fd  lea     edx, [rax+0Bh]; uBytes
0x180066500  mov     word ptr [rdi], 3
0x180066505  lea     ecx, [rax+40h]; uFlags
0x180066508  mov     [rdi+8], edx
0x18006650b  call    cs:__imp_LocalAlloc
0x180066511  mov     [rdi+10h], rax
0x180066515  test    rax, rax
0x180066518  jz      loc_180066B7C
0x18006651e  xor     eax, eax
0x180066520  lea     rdx, [rbp+930h+var_980]
0x180066524  mov     rcx, r15
0x180066527  mov     [rbp+930h+var_980], rax
0x18006652b  mov     [rbp+930h+var_978], ax
0x18006652f  mov     [rbp+930h+var_976], al
0x180066532  call    WDLIB_QueryTSWindowCapabilitySet
0x180066537  mov     rcx, [rdi+10h]
0x18006653b  mov     ebx, eax
0x18006653d  or      ebx, 10000000h
0x180066543  jl      loc_1800665E8
0x180066549  movsd   xmm0, [rbp+930h+var_980]
0x18006654e  mov     eax, dword ptr [rbp+930h+var_980+7]
0x180066551  movsd   qword ptr [rcx], xmm0
0x180066555  mov     [rcx+7], eax
0x180066558  jmp     loc_1800671A0
0x18006655d  mov     r8, rsi; Size
0x180066560  lea     rcx, PROPERTY_TYPE_MBUTTON_DOWN_POSITION; Buf1
0x180066567  mov     rdx, rbx; Buf2
0x18006656a  call    memcmp_0
0x18006656f  test    eax, eax
0x180066571  jnz     loc_1800665F7
0x180066577  lea     edx, [rax+8]; uBytes
0x18006657a  mov     word ptr [rdi], 3
0x18006657f  lea     ecx, [rax+40h]; uFlags
0x180066582  mov     dword ptr [rdi+8], 8
0x180066589  call    cs:__imp_LocalAlloc
0x18006658f  mov     [rdi+10h], rax
0x180066593  test    rax, rax
  ... truncated ...
```
