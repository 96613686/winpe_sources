# CRDPWDUMXStack::WDCreateAndConfigureStack(ulong)

- ea: `0x180068a9c`
- end: `0x180069c3f`
- name: `?WDCreateAndConfigureStack@CRDPWDUMXStack@@IEAAJK@Z`
- size: `4515`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010fc30`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000146c`
- `0x180001574`
- `0x180001f84`
- `0x18000202c`
- `0x1800023e4`
- `0x18000ce04`
- `0x18004a928`
- `0x18004bc38`
- `0x18004ff70`
- `0x180050dbc`
- `0x180068a9c`
- `0x18006fa5c`
- `0x18006fcdc`
- `0x1800706d8`
- `0x180071214`
- `0x180071c4c`
- `0x18007e9e0`
- `0x18007f348`
- `0x18007f42c`
- `0x180177a50`
- `0x18017a520`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x180069253`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18006951d`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x180069253`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18006951d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069bd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069bd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b89`
- `OLEAUT32!__imp_VariantInit` at `0x180068b4d`
- `OLEAUT32!__imp_VariantInit` at `0x180068b57`
- `OLEAUT32!__imp_VariantInit` at `0x180068b61`
- `OLEAUT32!__imp_VariantInit` at `0x180068b6b`
- `OLEAUT32!__imp_VariantInit` at `0x180068b75`
- `OLEAUT32!__imp_VariantInit` at `0x180068b4d`
- `OLEAUT32!__imp_VariantInit` at `0x180068b57`
- `OLEAUT32!__imp_VariantInit` at `0x180068b61`
- `OLEAUT32!__imp_VariantInit` at `0x180068b6b`
- `OLEAUT32!__imp_VariantInit` at `0x180068b75`
- `OLEAUT32!__imp_VariantClear` at `0x180069bdc`
- `OLEAUT32!__imp_VariantClear` at `0x180069be6`
- `OLEAUT32!__imp_VariantClear` at `0x180069bf0`
- `OLEAUT32!__imp_VariantClear` at `0x180069bfa`
- `OLEAUT32!__imp_VariantClear` at `0x180069c04`
- `OLEAUT32!__imp_VariantClear` at `0x180069bdc`
- `OLEAUT32!__imp_VariantClear` at `0x180069be6`
- `OLEAUT32!__imp_VariantClear` at `0x180069bf0`
- `OLEAUT32!__imp_VariantClear` at `0x180069bfa`
- `OLEAUT32!__imp_VariantClear` at `0x180069c04`

## string_xrefs

- `0x180068d29`: `MonitorConfig`
- `0x1800690ec`: `UseSoftSyncExtensions`
- `0x18006921e`: `UserConfiguredTransportMode`
- `0x180068be1`: `WDCreateAndConfigureStack`
- `0x180068c85`: `WDCreateAndConfigureStack`
- `0x180068e0d`: `WDCreateAndConfigureStack`
- `0x180068e8a`: `WDCreateAndConfigureStack`
- `0x180068d0c`: `StackConfig`
- `0x180068cb7`: `Failed to open the WD stack`
- `0x180068e3f`: `Failed to set the config data`
- `0x18006908d`: `Udp::MinClientProtocolVersion`
- `0x18006905f`: `Failed to read the WD stack encoding mode. Using the non-remote session default.`
- `0x180069118`: `Failed to read soft sync extensions from property. Disabling soft sync extensions.`
- `0x1800690bf`: `Failed to read the UDP minimum client protocol version property. Using UDP without client protocol version limitation.`
- `0x180069177`: `Failed to read Microsoft Entra Auth enforcement from property. Disabling Microsoft Entra Auth enforcement.`
- `0x1800692db`: `PROPERTY_USER_CONFIG_TRANSPORT okay`
- `0x18006930d`: `PROPERTY_USER_CONFIG_TRANSPORT read failed`
- `0x1800693c1`: `Failed to read ulDisableConnMonitor property...default ConnMonitor OFF.`
- `0x180069437`: `Server-side ConnMonitor`
- `0x18006953f`: `fRdpRelativeMouseModeSupportEnabled set to FALSE by registry`
- `0x18006961f`: `Failed to read listener name`
- `0x180069bac`: `Failed to read listener name`
- `0x1800695c3`: `Failed to set RDP the config data`
- `0x1800696ef`: `Skip legacy protocol is set to TRUE. Enforcing TLS (skip negotiation).`
- `0x180069663`: `SecurityConfig`
- `0x180069682`: `SecurityConfig`
- `0x180069810`: `Failed to set the security config`
- `0x180069766`: `ExpectedUserSid`
- `0x18006989a`: `Getting CONN_PROPERTY_CLIENT_SUPPORTED_AUTHENTICATION_PROTOCOLS failed`
- `0x180069869`: `ClientSupportedAuthenticationProtocols`
- `0x180069925`: `Getting CONN_PROPERTY_SERVER_SELECTED_AUTHENTICATION_PROTOCOL failed`
- `0x1800698f5`: `ServerSelectedAuthenticationProtocol`
- `0x180069966`: `WDLIB_SetAuthenticationProtocols failed`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::WDCreateAndConfigureStack(CRDPWDUMXStack *this, char a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  _QWORD *v9; // r12
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rcx
  LONG *plVal; // rbx
  LONG *v15; // rdi
  int v16; // ecx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rcx
  bool v24; // zf
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // eax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int *v42; // rdx
  const char *v43; // rax
  int v44; // eax
  int v45; // eax
  int v46; // ebx
  int v47; // r8d
  int v48; // r9d
  int v49; // eax
  int v50; // ecx
  int v51; // edx
  int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  LONGLONG llVal; // rbx
  int v66; // r8d
  int v67; // r9d
  __int64 v68; // rcx
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  char v72; // cl
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  int v76; // eax
  int v77; // r8d
  int v78; // r9d
  int v79; // eax
  int v80; // r8d
  int v81; // r9d
  int v82; // ecx
  __int16 *v83; // rdx
  const char *v84; // rax
  __int64 v85; // rcx
  int v86; // edx
  int v87; // eax
  int v88; // ecx
  int v89; // r8d
  int v90; // r9d
  int v91; // ecx
  int v92; // r8d
  int v93; // r9d
  int v94; // ecx
  int v95; // r8d
  int v96; // r9d
  int v97; // ecx
  int v98; // r8d
  int v99; // r9d
  __int64 v100; // rcx
  int v102; // [rsp+50h] [rbp-B0h] BYREF
  const char *pcVal; // [rsp+58h] [rbp-A8h] BYREF
  int v104; // [rsp+60h] [rbp-A0h] BYREF
  const char *v105; // [rsp+68h] [rbp-98h] BYREF
  const char *v106; // [rsp+70h] [rbp-90h] BYREF
  char v107; // [rsp+78h] [rbp-88h] BYREF
  const char *v108; // [rsp+80h] [rbp-80h] BYREF
  __int64 v109; // [rsp+88h] [rbp-78h] BYREF
  __int64 v110; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v111; // [rsp+98h] [rbp-68h] BYREF
  int v112; // [rsp+9Ch] [rbp-64h] BYREF
  int v113; // [rsp+A0h] [rbp-60h] BYREF
  int v114; // [rsp+A4h] [rbp-5Ch] BYREF
  __int128 v115; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v116; // [rsp+B8h] [rbp-48h]
  __int64 v117; // [rsp+C8h] [rbp-38h]
  int v118; // [rsp+D0h] [rbp-30h] BYREF
  int v119; // [rsp+D4h] [rbp-2Ch] BYREF
  int v120; // [rsp+D8h] [rbp-28h] BYREF
  int v121; // [rsp+DCh] [rbp-24h] BYREF
  VARIANTARG v122; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v123; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v124; // [rsp+110h] [rbp+10h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+128h] [rbp+28h]
  __int128 v126; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG pvarg; // [rsp+140h] [rbp+40h] BYREF
  VARIANTARG v128; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v129[4]; // [rsp+170h] [rbp+70h] BYREF
  BOOL v130; // [rsp+174h] [rbp+74h]
  int v131; // [rsp+178h] [rbp+78h]
  int v132; // [rsp+180h] [rbp+80h]
  char v133; // [rsp+184h] [rbp+84h]
  int v134; // [rsp+188h] [rbp+88h]
  __int64 v135; // [rsp+18Ch] [rbp+8Ch]
  BOOL v136; // [rsp+19Ch] [rbp+9Ch]
  int v137; // [rsp+1A0h] [rbp+A0h]
  __int64 v138; // [rsp+1A4h] [rbp+A4h]
  int v139; // [rsp+1ACh] [rbp+ACh]
  BOOL v140; // [rsp+1B0h] [rbp+B0h]
  int v141; // [rsp+1B4h] [rbp+B4h]
  int v142; // [rsp+1B8h] [rbp+B8h]
  int v143; // [rsp+1BCh] [rbp+BCh]
  char v144; // [rsp+1C0h] [rbp+C0h] BYREF
  char v145; // [rsp+1C1h] [rbp+C1h]
  char v146; // [rsp+1C2h] [rbp+C2h]
  __int128 v147; // [rsp+1C4h] [rbp+C4h]
  int v148; // [rsp+1D4h] [rbp+D4h]
  unsigned __int16 v149[161]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int16 v150[259]; // [rsp+31Ah] [rbp+21Ah] BYREF
  char v151; // [rsp+520h] [rbp+420h] BYREF

  v117 = 0;
  v110 = 0;
  v115 = 0;
  v116 = 0;
  memset_0(&v144, 0, 0x35Au);
  v107 = 0;
  memset_0(v129, 0, 0x50u);
  v109 = 0;
  v126 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v122, 0, sizeof(v122));
  memset(&v128, 0, sizeof(v128));
  memset(&v123, 0, sizeof(v123));
  memset(&v124, 0, sizeof(v124));
  VariantInit(&pvarg);
  VariantInit(&v122);
  VariantInit(&v128);
  VariantInit(&v123);
  VariantInit(&v124);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  if ( (*((_BYTE *)this + 108) & 0x10) != 0 )
  {
    v4 = -1073086458;
    goto LABEL_136;
  }
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = this;
  v5 = WDLIB_Load();
  v4 = v5;
  if ( v5 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v102 = 3859;
      v108 = "WDCreateAndConfigureStack";
      v106 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v104 = NTSTATUS2HR(v5);
      v105 = "Failed to load the WD stack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)&dword_18028D404,
        v7,
        v8,
        (__int64)&v105,
        (__int64)&v104,
        (__int64)&v106,
        (__int64)&v102,
        (__int64)&v108);
    }
    goto LABEL_136;
  }
  v9 = (_QWORD *)*((_QWORD *)this + 19);
  v4 = WDLIB_Open((__int64)v9);
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v102 = 3874;
      v105 = "WDCreateAndConfigureStack";
      v106 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v104 = NTSTATUS2HR(v4);
      v108 = "Failed to open the WD stack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)byte_180290391,
        v11,
        v12,
        (__int64)&v108,
        (__int64)&v104,
        (__int64)&v106,
        (__int64)&v102,
        (__int64)&v105);
    }
    goto LABEL_136;
  }
  v13 = *((_QWORD *)this + 16);
  plVal = 0;
  v15 = 0;
  if ( v13 )
  {
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 24LL))(
           v13,
           L"StackConfig",
           &pvarg) >= 0 )
      plVal = pvarg.plVal;
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 24LL))(
           *((_QWORD *)this + 16),
           L"MonitorConfig",
           &v128) >= 0 )
      v15 = v128.plVal;
  }
  v110 = 0;
  if ( plVal )
    v16 = (unsigned __int8)*plVal;
  else
    v16 = *((_DWORD *)this + 58) != 0 ? 165 : 141;
  LODWORD(v110) = v16;
  if ( v15 )
  {
    LODWORD(v110) = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)((unsigned __int16)*v15 << 8)) & 0xFF00;
    HIDWORD(v110) = v15[1] * v15[2];
  }
  else
  {
    HIDWORD(v110) = 0x4000000;
    LODWORD(v110) = v16 & 0xFFFF00FF | 0x100;
  }
  LODWORD(v116) = 8;
  *((_QWORD *)&v115 + 1) = &v110;
  LODWORD(v115) = 3670215;
  *((_QWORD *)&v116 + 1) = 0;
  v117 = 0;
  v4 = WDLIB_IcaStackSetConfigData(v9, &v115);
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v102 = 3933;
      v105 = "WDCreateAndConfigureStack";
      v106 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v104 = NTSTATUS2HR(v4);
      v108 = "Failed to set the config data";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)&word_18028D2A6,
        v18,
        v19,
        (__int64)&v108,
        (__int64)&v104,
        (__int64)&v106,
        (__int64)&v102,
        (__int64)&v105);
    }
    goto LABEL_136;
  }
  v4 = WDLIB_IcaStackSetLogger(v9, *((_QWORD *)this + 102));
  if ( v4 && (unsigned int)CallbackContext > 2 )
  {
    v105 = "WDCreateAndConfigureStack";
    v102 = 3940;
    v106 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    v104 = NTSTATUS2HR(v4);
    v108 = "Failed to set the event logger";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v20,
      (unsigned int)&word_18028A1E6,
      v21,
      v22,
      (__int64)&v108,
      (__int64)&v104,
      (__int64)&v106,
      (__int64)&v102,
      (__int64)&v105);
  }
  memset_0(v129, 0, 0x50u);
  v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 78);
  v129[0] = a2;
  v132 = 1;
  v24 = *((_DWORD *)this + 59) == 0;
  v133 = 0;
  v134 = -1;
  v130 = v24;
  v131 = *((_DWORD *)this + 61);
  v137 = *((_DWORD *)this + 63);
  v141 = *((_DWORD *)this + 66);
  v135 = 0;
  v138 = 0;
  v25 = (**v23)(v23, &IID_IRDPCollection, &v109);
  if ( v25 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v104 = v25;
      v105 = "Failed to QI for Platform Context";
      pcVal = "Error HResult failed";
      v106 = "WDCreateAndConfigureStack";
      v102 = 3965;
      v108 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)"Failed to QI for Platform Context",
        (unsigned int)&dword_18028EA14,
        v26,
        v27,
        (__int64)&pcVal,
        (__int64)&v104,
        (__int64)&v108,
        (__int64)&v102,
        (__int64)&v106,
        (__int64)&v105);
    }
    goto LABEL_136;
  }
  v118 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
         v109,
         L"RDPWDRemoteDesktopMode",
         &v118) < 0
    && (unsigned int)CallbackContext > 4 )
  {
    pcVal = "Failed to read the WD stack encoding mode. Using the non-remote session default.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v28,
      (unsigned int)&byte_180291897,
      v29,
      v30,
      (__int64)&pcVal);
  }
  v119 = 0;
  v140 = v118 == 1;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
         v109,
         L"Udp::MinClientProtocolVersion",
         &v119) < 0
    && (unsigned int)CallbackContext > 4 )
  {
    pcVal = "Failed to read the UDP minimum client protocol version property. Using UDP without client protocol version limitation.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v31,
      (unsigned int)&unk_18028D730,
      v32,
      v33,
      (__int64)&pcVal);
  }
  v142 = v119;
  v114 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
         v109,
         L"UseSoftSyncExtensions",
         &v114) < 0
    && (unsigned int)CallbackContext > 3 )
  {
    pcVal = "Failed to read soft sync extensions from property. Disabling soft sync extensions.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v34,
      (unsigned int)&dword_18028CBE4,
      v35,
      v36,
      (__int64)&pcVal);
  }
  v111 = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v109 + 32LL))(
          v109,
          L"EnableMicrosoftEntraIdAuthenticationEnforcement",
          &v111);
  if ( v37 < 0 )
  {
    v41 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 3 )
      goto LABEL_48;
    v102 = v37;
    v42 = &dword_18028D584;
    v43 = "Failed to read Microsoft Entra Auth enforcement from property. Disabling Microsoft Entra Auth enforcement.";
    goto LABEL_47;
  }
  if ( v111 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v102 = v111;
      pcVal = "bEnableMicrosoftEntraIdAuthEnforcement property is set to ";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v38,
        (unsigned int)byte_18028A661,
        v39,
        v40,
        (__int64)&pcVal,
        (__int64)&v102);
    }
    v44 = WDLIB_SetMicrosoftEntraIdAuthEnforced(v9, v111);
    if ( v44 < 0 )
    {
      v41 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext > 3 )
      {
        v102 = v44;
        v42 = (int *)byte_18028A9DB;
        v43 = "Failed to set Microsoft Entra Auth enforcement to the stack. Disabling Microsoft Entra Auth enforcement.";
LABEL_47:
        pcVal = v43;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v41,
          (_DWORD)v42,
          v39,
          v40,
          (__int64)&pcVal,
          (__int64)&v102);
      }
    }
  }
LABEL_48:
  v112 = 0;
  v45 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
          v109,
          L"UserConfiguredTransportMode",
          &v112);
  v113 = 1;
  v46 = v45;
  v24 = (unsigned int)RDPENCHLPREG_ReadValueDWORD(
                        -2147483646,
                        L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                        L"ForceDisableUDPL",
                        &v113) == 0;
  v49 = 1;
  if ( v24 )
  {
    v50 = 1;
    v113 = 1;
  }
  else
  {
    v50 = v113;
  }
  if ( v46 >= 0 )
  {
    if ( v112 == 2 )
    {
      LODWORD(v138) = 1;
      v51 = 769;
      v49 = 257;
    }
    else
    {
      if ( v112 == 1 )
      {
        v138 = 1;
LABEL_61:
        if ( (unsigned int)CallbackContext > 4 )
        {
          v102 = v112;
          pcVal = "PROPERTY_USER_CONFIG_TRANSPORT okay";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v50,
            (unsigned int)&unk_18028E230,
            v47,
            v48,
            (__int64)&pcVal,
            (__int64)&v102);
        }
        goto LABEL_65;
      }
      LODWORD(v138) = 1;
      v51 = 513;
    }
    if ( v114 )
      v49 = v51;
    HIDWORD(v138) = v49;
    if ( !v50 )
      HIDWORD(v138) = v49 | 4;
    goto LABEL_61;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    pcVal = "PROPERTY_USER_CONFIG_TRANSPORT read failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v50,
      (unsigned int)word_180288D22,
      v47,
      v48,
      (__int64)&pcVal);
  }
LABEL_65:
  if ( (unsigned int)CallbackContext > 4 )
  {
    v102 = HIDWORD(v138);
    v104 = v138;
    pcVal = "RdpStack.Multitransport.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v50,
      (unsigned int)&unk_18028D478,
      v47,
      v48,
      (__int64)&pcVal,
      (__int64)&v104,
      (__int64)&v102);
  }
  v120 = 1;
  v52 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
          v109,
          L"DisableConnectionMonitor",
          &v120);
  if ( v52 < 0 )
  {
    v53 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v102 = v52;
      v105 = "Failed to read ulDisableConnMonitor property...default ConnMonitor OFF.";
      v106 = "HResult failed but continue";
      pcVal = "WDCreateAndConfigureStack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_18028F613,
        v54,
        v55,
        (__int64)&v106,
        (__int64)&v105,
        (__int64)&v102,
        (__int64)&pcVal);
    }
  }
  v136 = v120 == 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v102 = v136;
    pcVal = "Server-side ConnMonitor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v53,
      (unsigned int)byte_18028F6A1,
      v54,
      v55,
      (__int64)&pcVal,
      (__int64)&v102);
  }
  v104 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
         v109,
         L"RDP::RemoteApp::fEnableRemoteFXAdvancedRemoteApp",
         &v104) < 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      pcVal = "HiDef RAIL support not enabled - stack property not set.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v56,
        (unsigned int)&word_180288B66,
        v57,
        v58,
        (__int64)&pcVal);
    }
    v139 = 0;
  }
  else
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v102 = v104;
      pcVal = "HiDef RAIL support level property is set to ";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)byte_18028F803,
        v57,
        v58,
        (__int64)&pcVal,
        (__int64)&v102);
    }
    v139 = v104;
  }
  v143 = 1;
  v121 = 0;
  if ( (unsigned int)RDPENCHLPREG_ReadValueDWORD(
                       -2147483646,
                       L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                       L"ForceDisableRdpRelativeMouse",
                       &v121) )
  {
    if ( v121 )
    {
      v143 = 0;
      if ( (unsigned int)CallbackContext > 4 )
      {
        pcVal = "fRdpRelativeMouseModeSupportEnabled set to FALSE by registry";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v59,
          (unsigned int)&unk_18028CC58,
          v60,
          v61,
          (__int64)&pcVal);
      }
    }
  }
  LODWORD(v115) = 3679311;
  *((_QWORD *)&v115 + 1) = v129;
  LODWORD(v116) = 80;
  *((_QWORD *)&v116 + 1) = 0;
  v117 = 0;
  v4 = WDLIB_SetRDPConfigDataEx(v9, &v115);
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      pcVal = "WDCreateAndConfigureStack";
      v102 = 4151;
      v105 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v104 = NTSTATUS2HR(v4);
      v106 = "Failed to set RDP the config data";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v62,
        (unsigned int)byte_18028BA19,
        v63,
        v64,
        (__int64)&v106,
        (__int64)&v104,
        (__int64)&v105,
        (__int64)&v102,
        (__int64)&pcVal);
    }
    goto LABEL_136;
  }
  llVal = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 24LL))(
         v109,
         L"RDP::TerminalName",
         &v123) < 0
    && (unsigned int)CallbackContext > 4 )
  {
    pcVal = "Failed to read listener name";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)"Failed to read listener name",
      (unsigned int)word_18028ABCA,
      v66,
      v67,
      (__int64)&pcVal);
  }
  v68 = *((_QWORD *)this + 16);
  if ( v68
    && (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v68 + 24LL))(
         v68,
         L"SecurityConfig",
         &v122) >= 0 )
  {
    llVal = v122.llVal;
  }
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 24LL))(
         v109,
         L"SecurityConfig",
         &v122) >= 0 )
    llVal = v122.llVal;
  memset_0(&v144, 0, 0x35Au);
  v107 = 0;
  if ( llVal )
  {
    v145 = *(_BYTE *)llVal;
    v146 = *(_BYTE *)(llVal + 1);
    v144 = *(_BYTE *)(llVal + 284);
    if ( *((_DWORD *)this + 148) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        pcVal = "Skip legacy protocol is set to TRUE. Enforcing TLS (skip negotiation).";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v69,
          (unsigned int)&word_18028B246,
          v70,
          v71,
          (__int64)&pcVal);
      }
      if ( v144 )
      {
        v144 = 0;
        v72 = v145;
        if ( (unsigned __int8)v145 <= 1u )
          v72 = 2;
        v145 = v72;
      }
    }
    v147 = *(_OWORD *)(llVal + 2);
    v148 = *(_DWORD *)(llVal + 18);
    StringCbCopyW(v149, 0x100u, (const unsigned __int16 *)(llVal + 28));
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 24LL))(
           v109,
           L"ExpectedUserSid",
           &v124) >= 0
      && v124.vt == 8
      && v124.llVal )
    {
      StringCbCopyW(v150, 0x200u, v124.bstrVal);
    }
  }
  LODWORD(v115) = 3670383;
  *((_QWORD *)&v115 + 1) = &v144;
  LODWORD(v116) = 858;
  *((_QWORD *)&v116 + 1) = &v107;
  v117 = 1;
  v4 = WDLIB_IcaStackSetSecurityConfig(v9, &v115);
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      pcVal = "WDCreateAndConfigureStack";
      v102 = 4232;
      v105 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v104 = NTSTATUS2HR(v4);
      v106 = "Failed to set the security config";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v73,
        (unsigned int)&word_180290066,
        v74,
        v75,
        (__int64)&v106,
        (__int64)&v104,
        (__int64)&v105,
        (__int64)&v102,
        (__int64)&pcVal);
    }
    goto LABEL_136;
  }
  if ( *((_DWORD *)this + 148) )
  {
    v102 = 0;
    v104 = 0;
    v76 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
            v109,
            L"ClientSupportedAuthenticationProtocols",
            &v104);
    if ( v76 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v108) = v76;
      pcVal = "WDCreateAndConfigureStack";
      v105 = "Getting CONN_PROPERTY_CLIENT_SUPPORTED_AUTHENTICATION_PROTOCOLS failed";
      v106 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_180289BE9,
        v77,
        v78,
        (__int64)&v106,
        (__int64)&v105,
        (__int64)&v108,
        (__int64)&pcVal);
    }
    v79 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v109 + 40LL))(
            v109,
            L"ServerSelectedAuthenticationProtocol",
            &v102);
    if ( v79 < 0 )
    {
      v82 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 3 )
        goto LABEL_120;
      LODWORD(v108) = v79;
      v83 = (__int16 *)&unk_18028F6D0;
      v84 = "Getting CONN_PROPERTY_SERVER_SELECTED_AUTHENTICATION_PROTOCOL failed";
      goto LABEL_119;
    }
    v85 = *v9;
    v86 = v104;
    *(_DWORD *)(v85 + 1344) = v102;
    *(_DWORD *)(v85 + 1340) = v86;
    v87 = NTSTATUS2HR(0);
    if ( v87 < 0 )
    {
      v82 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v108) = v87;
        v83 = &word_18028DB06;
        v84 = "WDLIB_SetAuthenticationProtocols failed";
LABEL_119:
        v105 = v84;
        pcVal = "WDCreateAndConfigureStack";
        v106 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v82,
          (_DWORD)v83,
          v80,
          v81,
          (__int64)&v106,
          (__int64)&v105,
          (__int64)&v108,
          (__int64)&pcVal);
      }
    }
  }
LABEL_120:
  *(_QWORD *)&v126 = 0;
  *((_QWORD *)&v115 + 1) = &v126;
  DWORD2(v126) = 20;
  LODWORD(v115) = 3675139;
  LODWORD(v116) = 16;
  *((_QWORD *)&v116 + 1) = 0;
  v117 = 0;
  v4 = MCSIcaT120Request(*v9, &v115);
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      pcVal = "WDCreateAndConfigureStack";
      LODWORD(v108) = 4278;
      v105 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      v102 = NTSTATUS2HR(v4);
      v106 = "Failed to start T120";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v88,
        (unsigned int)byte_18028C3BD,
        v89,
        v90,
        (__int64)&v106,
        (__int64)&v102,
        (__int64)&v105,
        (__int64)&v108,
        (__int64)&pcVal);
    }
  }
  else
  {
    LODWORD(v115) = 3670291;
    *((_QWORD *)&v116 + 1) = &v151;
    *((_QWORD *)&v115 + 1) = 0;
    LODWORD(v116) = 0;
    v117 = 448;
    v4 = WDLIB_IcaVirtualQueryBindings(v9, &v115);
    if ( v4 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        pcVal = "WDCreateAndConfigureStack";
        LODWORD(v108) = 4296;
        v105 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v102 = NTSTATUS2HR(v4);
        v106 = "Failed to query the initial bindings";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v91,
          (unsigned int)&unk_18028D850,
          v92,
          v93,
          (__int64)&v106,
          (__int64)&v102,
          (__int64)&v105,
          (__int64)&v108,
          (__int64)&pcVal);
      }
    }
    else if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 24LL))(
                v109,
                L"RDP::TerminalName",
                &v123) < 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        pcVal = "Failed to read listener name";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v94,
          (unsigned int)byte_180290691,
          v95,
          v96,
          (__int64)&pcVal);
      }
    }
    else if ( wcsicmp(v123.bstrVal, L"rdp-tcp") )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        pcVal = v123.pcVal;
        v105 = "Won't log encryption warning for listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v97,
          (unsigned int)byte_180287F45,
          v98,
          v99,
          (__int64)&v105,
          (__int64)&pcVal);
      }
    }
    else
    {
      v100 = *((_QWORD *)this + 101);
      if ( v100 && (unsigned __int8)v145 <= 1u && !v146 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 88LL))(v100);
    }
  }
LABEL_136:
  LeaveCriticalSection(lpCriticalSection);
  VariantClear(&pvarg);
  VariantClear(&v128);
  VariantClear(&v122);
  VariantClear(&v123);
  VariantClear(&v124);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v109);
  return v4;
}

```

## disassembly

```asm
0x180068a9c  mov     [rsp-8+arg_10], rbx
0x180068aa1  push    rbp
0x180068aa2  push    rsi
0x180068aa3  push    rdi
0x180068aa4  push    r12
0x180068aa6  push    r13
0x180068aa8  push    r14
0x180068aaa  push    r15
0x180068aac  lea     rbp, [rsp-5F0h]
0x180068ab4  sub     rsp, 6F0h
0x180068abb  mov     rax, cs:__security_cookie
0x180068ac2  xor     rax, rsp
0x180068ac5  mov     [rbp+620h+var_40], rax
0x180068acc  xorps   xmm0, xmm0
0x180068acf  mov     r13d, edx
0x180068ad2  mov     r14, rcx
0x180068ad5  xor     eax, eax
0x180068ad7  xor     esi, esi
0x180068ad9  mov     [rbp+620h+var_658], rax
0x180068add  xor     edx, edx; Val
0x180068adf  mov     [rbp+620h+var_690], rsi
0x180068ae3  lea     rcx, [rbp+620h+var_560]; void *
0x180068aea  mov     r8d, 35Ah; Size
0x180068af0  movups  [rbp+620h+var_678], xmm0
0x180068af4  movups  [rbp+620h+var_668], xmm0
0x180068af8  call    memset_0
0x180068afd  xor     edx, edx; Val
0x180068aff  mov     [rsp+720h+var_6A8], sil
0x180068b04  lea     r8d, [rsi+50h]; Size
0x180068b08  lea     rcx, [rbp+620h+var_5B0]; void *
0x180068b0c  call    memset_0
0x180068b11  xor     eax, eax
0x180068b13  mov     [rbp+620h+var_698], rsi
0x180068b17  xorps   xmm0, xmm0
0x180068b1a  mov     qword ptr [rbp+620h+pvarg+10h], rax
0x180068b1e  xorps   xmm1, xmm1
0x180068b21  mov     qword ptr [rbp+620h+var_640+10h], rax
0x180068b25  lea     rcx, [rbp+620h+pvarg]; pvarg
0x180068b29  mov     qword ptr [rbp+620h+var_5C8+10h], rax
0x180068b2d  movups  [rbp+620h+var_5F0], xmm0
0x180068b31  mov     qword ptr [rbp+620h+var_628+10h], rax
0x180068b35  movups  xmmword ptr [rbp+620h+pvarg], xmm1
0x180068b39  mov     qword ptr [rbp+620h+var_610+10h], rax
0x180068b3d  movups  xmmword ptr [rbp+620h+var_640], xmm0
0x180068b41  movups  xmmword ptr [rbp+620h+var_5C8], xmm1
0x180068b45  movups  xmmword ptr [rbp+620h+var_628], xmm0
0x180068b49  movups  xmmword ptr [rbp+620h+var_610], xmm1
0x180068b4d  call    cs:__imp_VariantInit
0x180068b53  lea     rcx, [rbp+620h+var_640]; pvarg
0x180068b57  call    cs:__imp_VariantInit
0x180068b5d  lea     rcx, [rbp+620h+var_5C8]; pvarg
0x180068b61  call    cs:__imp_VariantInit
0x180068b67  lea     rcx, [rbp+620h+var_628]; pvarg
0x180068b6b  call    cs:__imp_VariantInit
0x180068b71  lea     rcx, [rbp+620h+var_610]; pvarg
0x180068b75  call    cs:__imp_VariantInit
0x180068b7b  lea     rax, [r14+0A8h]
0x180068b82  mov     rcx, rax; lpCriticalSection
0x180068b85  mov     [rbp+620h+lpCriticalSection], rax
0x180068b89  call    cs:__imp_EnterCriticalSection
0x180068b8f  test    byte ptr [r14+6Ch], 10h
0x180068b94  jz      short loc_180068BA0
0x180068b96  mov     ebx, 0C00A0006h
0x180068b9b  jmp     loc_180069BCE
0x180068ba0  lea     rcx, [r14+88h]
0x180068ba7  mov     [r14+90h], rsi
0x180068bae  mov     [rcx], rsi
0x180068bb1  mov     [r14+98h], rsi
0x180068bb8  mov     [r14+0A0h], r14
0x180068bbf  call    WDLIB_Load
0x180068bc4  mov     ebx, eax
0x180068bc6  test    eax, eax
0x180068bc8  jz      loc_180068C59
0x180068bce  mov     ecx, cs:CallbackContext
0x180068bd4  mov     edi, 2
0x180068bd9  cmp     ecx, edi
0x180068bdb  jbe     loc_180069BCE
0x180068be1  lea     rsi, aWdcreateandcon; "WDCreateAndConfigureStack"
0x180068be8  mov     [rsp+720h+var_6D0], 0F13h
0x180068bf0  lea     r15, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180068bf7  mov     [rbp+620h+var_6A0], rsi
0x180068bfb  mov     ecx, eax; int
0x180068bfd  mov     [rsp+720h+var_6B0], r15
0x180068c02  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180068c07  mov     [rsp+720h+var_6C0], eax
0x180068c0b  lea     rdx, dword_18028D404
0x180068c12  lea     rax, aFailedToLoadTh; "Failed to load the WD stack"
0x180068c19  mov     [rsp+720h+var_6B8], rax
0x180068c1e  lea     rax, [rbp+620h+var_6A0]
0x180068c22  mov     [rsp+720h+var_6E0], rax
0x180068c27  lea     rax, [rsp+720h+var_6D0]
0x180068c2c  mov     [rsp+720h+var_6E8], rax
0x180068c31  lea     rax, [rsp+720h+var_6B0]
0x180068c36  mov     [rsp+720h+var_6F0], rax
0x180068c3b  lea     rax, [rsp+720h+var_6C0]
0x180068c40  mov     [rsp+720h+var_6F8], rax
0x180068c45  lea     rax, [rsp+720h+var_6B8]
0x180068c4a  mov     [rsp+720h+var_700], rax
0x180068c4f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180068c54  jmp     loc_180069BCE
0x180068c59  mov     r12, [r14+98h]
0x180068c60  mov     rcx, r12
0x180068c63  call    WDLIB_Open
0x180068c68  mov     ebx, eax
0x180068c6a  test    eax, eax
0x180068c6c  jz      loc_180068CF3
0x180068c72  mov     eax, cs:CallbackContext
0x180068c78  mov     edi, 2
0x180068c7d  cmp     eax, edi
0x180068c7f  jbe     loc_180069BCE
0x180068c85  lea     rsi, aWdcreateandcon; "WDCreateAndConfigureStack"
0x180068c8c  mov     [rsp+720h+var_6D0], 0F22h
0x180068c94  lea     r15, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180068c9b  mov     [rsp+720h+var_6B8], rsi
0x180068ca0  mov     ecx, ebx; int
0x180068ca2  mov     [rsp+720h+var_6B0], r15
0x180068ca7  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180068cac  mov     [rsp+720h+var_6C0], eax
0x180068cb0  lea     rdx, byte_180290391
0x180068cb7  lea     rax, aFailedToOpenTh_0; "Failed to open the WD stack"
0x180068cbe  mov     [rbp+620h+var_6A0], rax
0x180068cc2  lea     rax, [rsp+720h+var_6B8]
0x180068cc7  mov     [rsp+720h+var_6E0], rax
0x180068ccc  lea     rax, [rsp+720h+var_6D0]
0x180068cd1  mov     [rsp+720h+var_6E8], rax
0x180068cd6  lea     rax, [rsp+720h+var_6B0]
0x180068cdb  mov     [rsp+720h+var_6F0], rax
0x180068ce0  lea     rax, [rsp+720h+var_6C0]
0x180068ce5  mov     [rsp+720h+var_6F8], rax
0x180068cea  lea     rax, [rbp+620h+var_6A0]
0x180068cee  jmp     loc_180068C4A
0x180068cf3  mov     rcx, [r14+80h]
0x180068cfa  mov     rbx, rsi
0x180068cfd  mov     rdi, rsi
0x180068d00  test    rcx, rcx
0x180068d03  jz      short loc_180068D48
0x180068d05  mov     rax, [rcx]
0x180068d08  lea     r8, [rbp+620h+pvarg]
0x180068d0c  lea     rdx, aStackconfig; "StackConfig"
0x180068d13  mov     rax, [rax+18h]
0x180068d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d1c  mov     rcx, [r14+80h]
0x180068d23  lea     r8, [rbp+620h+var_5C8]
0x180068d27  test    eax, eax
0x180068d29  lea     rdx, aMonitorconfig; "MonitorConfig"
0x180068d30  cmovns  rbx, qword ptr [rbp+620h+pvarg+8]
0x180068d35  mov     rax, [rcx]
0x180068d38  mov     rax, [rax+18h]
0x180068d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d41  test    eax, eax
0x180068d43  cmovns  rdi, qword ptr [rbp+620h+var_5C8+8]
0x180068d48  mov     [rbp+620h+var_690], rsi
0x180068d4c  mov     edx, 8
0x180068d51  test    rbx, rbx
0x180068d54  jz      short loc_180068D7D
0x180068d56  mov     eax, [rbx]
0x180068d58  and     eax, 7
0x180068d5b  mov     dword ptr [rbp+620h+var_690], eax
0x180068d5e  mov     ecx, [rbx]
0x180068d60  and     ecx, 70h
0x180068d63  or      ecx, eax
0x180068d65  mov     dword ptr [rbp+620h+var_690], ecx
0x180068d68  mov     eax, [rbx]
0x180068d6a  and     eax, edx
0x180068d6c  or      eax, ecx
0x180068d6e  mov     dword ptr [rbp+620h+var_690], eax
0x180068d71  mov     ecx, [rbx]
0x180068d73  and     ecx, 80h
0x180068d79  or      ecx, eax
0x180068d7b  jmp     short loc_180068D91
0x180068d7d  mov     eax, [r14+0E8h]
0x180068d84  neg     eax
0x180068d86  sbb     ecx, ecx
0x180068d88  and     ecx, 18h
0x180068d8b  add     ecx, 8Dh
0x180068d91  mov     dword ptr [rbp+620h+var_690], ecx
0x180068d94  test    rdi, rdi
0x180068d97  jz      short loc_180068DB6
0x180068d99  mov     eax, [rdi]
0x180068d9b  shl     eax, 8
0x180068d9e  xor     eax, ecx
0x180068da0  and     eax, 0FF00h
0x180068da5  xor     eax, ecx
0x180068da7  mov     dword ptr [rbp+620h+var_690], eax
0x180068daa  mov     eax, [rdi+8]
0x180068dad  imul    eax, [rdi+4]
0x180068db1  mov     dword ptr [rbp+620h+var_690+4], eax
0x180068db4  jmp     short loc_180068DCA
0x180068db6  and     ecx, 0FFFF01FFh
0x180068dbc  mov     dword ptr [rbp+620h+var_690+4], 4000000h
0x180068dc3  bts     ecx, 8
0x180068dc7  mov     dword ptr [rbp+620h+var_690], ecx
0x180068dca  lea     rax, [rbp+620h+var_690]
0x180068dce  mov     dword ptr [rbp+620h+var_668], edx
0x180068dd1  lea     rdx, [rbp+620h+var_678]
0x180068dd5  mov     qword ptr [rbp+620h+var_678+8], rax
0x180068dd9  mov     rcx, r12
0x180068ddc  mov     dword ptr [rbp+620h+var_678], 3800C7h
0x180068de3  mov     qword ptr [rbp+620h+var_668+8], rsi
0x180068de7  mov     [rbp+620h+var_658], rsi
0x180068deb  call    WDLIB_IcaStackSetConfigData
0x180068df0  mov     ebx, eax
0x180068df2  test    eax, eax
0x180068df4  jz      loc_180068E7B
0x180068dfa  mov     eax, cs:CallbackContext
0x180068e00  mov     edi, 2
0x180068e05  cmp     eax, edi
0x180068e07  jbe     loc_180069BCE
0x180068e0d  lea     rsi, aWdcreateandcon; "WDCreateAndConfigureStack"
0x180068e14  mov     [rsp+720h+var_6D0], 0F5Dh
0x180068e1c  lea     r15, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180068e23  mov     [rsp+720h+var_6B8], rsi
0x180068e28  mov     ecx, ebx; int
0x180068e2a  mov     [rsp+720h+var_6B0], r15
0x180068e2f  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180068e34  mov     [rsp+720h+var_6C0], eax
0x180068e38  lea     rdx, word_18028D2A6
0x180068e3f  lea     rax, aFailedToSetThe_16; "Failed to set the config data"
0x180068e46  mov     [rbp+620h+var_6A0], rax
0x180068e4a  lea     rax, [rsp+720h+var_6B8]
0x180068e4f  mov     [rsp+720h+var_6E0], rax
0x180068e54  lea     rax, [rsp+720h+var_6D0]
0x180068e59  mov     [rsp+720h+var_6E8], rax
0x180068e5e  lea     rax, [rsp+720h+var_6B0]
0x180068e63  mov     [rsp+720h+var_6F0], rax
0x180068e68  lea     rax, [rsp+720h+var_6C0]
0x180068e6d  mov     [rsp+720h+var_6F8], rax
0x180068e72  lea     rax, [rbp+620h+var_6A0]
0x180068e76  jmp     loc_180068C4A
0x180068e7b  mov     rdx, [r14+330h]
0x180068e82  mov     rcx, r12
0x180068e85  call    WDLIB_IcaStackSetLogger
0x180068e8a  lea     rsi, aWdcreateandcon; "WDCreateAndConfigureStack"
0x180068e91  mov     ebx, eax
0x180068e93  lea     r15, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180068e9a  mov     edi, 2
0x180068e9f  test    eax, eax
0x180068ea1  jz      short loc_180068F12
0x180068ea3  mov     eax, cs:CallbackContext
0x180068ea9  cmp     eax, edi
0x180068eab  jbe     short loc_180068F12
0x180068ead  mov     ecx, ebx; int
0x180068eaf  mov     [rsp+720h+var_6B8], rsi
0x180068eb4  mov     [rsp+720h+var_6D0], 0F64h
0x180068ebc  mov     [rsp+720h+var_6B0], r15
0x180068ec1  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180068ec6  mov     [rsp+720h+var_6C0], eax
0x180068eca  lea     rdx, word_18028A1E6
0x180068ed1  lea     rax, aFailedToSetThe_4; "Failed to set the event logger"
0x180068ed8  mov     [rbp+620h+var_6A0], rax
0x180068edc  lea     rax, [rsp+720h+var_6B8]
0x180068ee1  mov     [rsp+720h+var_6E0], rax
0x180068ee6  lea     rax, [rsp+720h+var_6D0]
0x180068eeb  mov     [rsp+720h+var_6E8], rax
0x180068ef0  lea     rax, [rsp+720h+var_6B0]
0x180068ef5  mov     [rsp+720h+var_6F0], rax
0x180068efa  lea     rax, [rsp+720h+var_6C0]
0x180068eff  mov     [rsp+720h+var_6F8], rax
0x180068f04  lea     rax, [rbp+620h+var_6A0]
0x180068f08  mov     [rsp+720h+var_700], rax
0x180068f0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180068f12  xor     edx, edx; Val
0x180068f14  lea     rcx, [rbp+620h+var_5B0]; void *
0x180068f18  lea     r8d, [rdx+50h]; Size
0x180068f1c  call    memset_0
0x180068f21  mov     rcx, [r14+270h]
0x180068f28  lea     r8, [rbp+620h+var_698]
0x180068f2c  mov     [rbp+620h+var_5B0], r13b
0x180068f30  lea     rdx, IID_IRDPCollection
0x180068f37  xor     r13d, r13d
0x180068f3a  mov     [rbp+620h+var_5A0], 1
0x180068f44  cmp     [r14+0ECh], r13d
0x180068f4b  mov     eax, r13d
0x180068f4e  mov     [rbp+620h+var_59C], r13b
0x180068f55  setz    al
0x180068f58  mov     [rbp+620h+var_598], 0FFFFFFFFh
0x180068f62  mov     [rbp+620h+var_5AC], eax
0x180068f65  mov     eax, [r14+0F4h]
0x180068f6c  mov     [rbp+620h+var_5A8], eax
0x180068f6f  mov     eax, [r14+0FCh]
0x180068f76  mov     [rbp+620h+var_580], eax
0x180068f7c  mov     eax, [r14+108h]
0x180068f83  mov     [rbp+620h+var_56C], eax
0x180068f89  mov     [rbp+620h+var_594], r13
0x180068f90  mov     [rbp+620h+var_57C], r13
0x180068f97  mov     rax, [rcx]
0x180068f9a  mov     rax, [rax]
0x180068f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fa2  test    eax, eax
0x180068fa4  jns     loc_180069031
0x180068faa  mov     ecx, cs:CallbackContext
0x180068fb0  cmp     ecx, edi
0x180068fb2  jbe     loc_180069BCE
0x180068fb8  mov     [rsp+720h+var_6C0], eax
0x180068fbc  lea     rcx, aFailedToQiForP; "Failed to QI for Platform Context"
0x180068fc3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180068fca  mov     [rsp+720h+var_6B8], rcx
0x180068fcf  mov     [rsp+720h+var_6C8], rax
0x180068fd4  lea     rdx, dword_18028EA14
0x180068fdb  lea     rax, [rsp+720h+var_6B8]
  ... truncated ...
```
