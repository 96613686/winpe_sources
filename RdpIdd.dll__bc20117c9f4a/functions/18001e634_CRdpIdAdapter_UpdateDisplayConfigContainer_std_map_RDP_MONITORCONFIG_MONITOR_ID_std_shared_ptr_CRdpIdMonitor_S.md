# CRdpIdAdapter::UpdateDisplayConfigContainer(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)

- ea: `0x18001e634`
- end: `0x18001f29a`
- name: `?UpdateDisplayConfigContainer@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z`
- size: `3174`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001de94`
- `0x18001fd78`

## callees

- `0x180001af0`
- `0x180003468`
- `0x1800035f8`
- `0x180003744`
- `0x1800038a4`
- `0x180003a18`
- `0x180003d80`
- `0x180006f60`
- `0x180007b38`
- `0x18000d614`
- `0x180013d14`
- `0x18001534c`
- `0x18001dd70`
- `0x18001ddf4`
- `0x18001e284`
- `0x18001e634`
- `0x180020e88`
- `0x180021570`
- `0x18002262c`
- `0x180022724`
- `0x180027398`
- `0x18002784c`
- `0x180027c78`
- `0x180027d70`
- `0x18003f010`

## string_xrefs

- `0x18001e9e1`: `CRdpIdAdapter::UpdateDisplayConfigContainer`
- `0x18001eb8c`: `CRdpIdAdapter::UpdateDisplayConfigContainer`
- `0x18001ed08`: `CRdpIdAdapter::UpdateDisplayConfigContainer`
- `0x18001ef9f`: `CRdpIdAdapter::UpdateDisplayConfigContainer`
- `0x18001f11e`: `CRdpIdAdapter::UpdateDisplayConfigContainer`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRdpIdAdapter::UpdateDisplayConfigContainer(__int64 a1, __int64 **a2)
{
  __int64 v4; // r12
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned int v7; // r15d
  _DWORD *v8; // r8
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rax
  int v14; // ecx
  _DWORD *v15; // r8
  int v16; // r8d
  int v17; // r9d
  _DWORD *v18; // rcx
  __int64 IddCxDisplayMode; // rax
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rax
  _DWORD *v25; // r8
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rcx
  _DWORD *v29; // r8
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rcx
  _DWORD *v33; // r8
  int v34; // r8d
  int v35; // r9d
  _DWORD *v36; // rcx
  __int128 *IddCxColorimetry; // rax
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm2
  __int128 v41; // xmm3
  __int64 v42; // rax
  _DWORD *v43; // r8
  int v44; // r8d
  int v45; // r9d
  unsigned int v46; // eax
  _QWORD *v47; // rdx
  char *v49; // [rsp+28h] [rbp-138h]
  const char *v50; // [rsp+30h] [rbp-130h]
  const char *v51; // [rsp+E0h] [rbp-80h] BYREF
  GUID *v52; // [rsp+E8h] [rbp-78h] BYREF
  GUID *v53; // [rsp+F0h] [rbp-70h] BYREF
  const char *v54; // [rsp+F8h] [rbp-68h] BYREF
  _QWORD v55[3]; // [rsp+100h] [rbp-60h] BYREF
  int v56; // [rsp+118h] [rbp-48h] BYREF
  int v57; // [rsp+11Ch] [rbp-44h] BYREF
  int v58; // [rsp+120h] [rbp-40h] BYREF
  int v59; // [rsp+124h] [rbp-3Ch] BYREF
  int v60; // [rsp+128h] [rbp-38h] BYREF
  int v61; // [rsp+12Ch] [rbp-34h] BYREF
  int v62; // [rsp+130h] [rbp-30h] BYREF
  int v63; // [rsp+134h] [rbp-2Ch] BYREF
  int v64; // [rsp+138h] [rbp-28h] BYREF
  int v65; // [rsp+13Ch] [rbp-24h] BYREF
  int v66; // [rsp+140h] [rbp-20h] BYREF
  int v67; // [rsp+144h] [rbp-1Ch] BYREF
  int v68; // [rsp+148h] [rbp-18h] BYREF
  int v69; // [rsp+14Ch] [rbp-14h] BYREF
  int v70; // [rsp+150h] [rbp-10h] BYREF
  int v71; // [rsp+154h] [rbp-Ch] BYREF
  int v72; // [rsp+158h] [rbp-8h] BYREF
  int v73; // [rsp+15Ch] [rbp-4h] BYREF
  int v74; // [rsp+160h] [rbp+0h] BYREF
  int v75; // [rsp+164h] [rbp+4h] BYREF
  int v76; // [rsp+168h] [rbp+8h] BYREF
  int v77; // [rsp+16Ch] [rbp+Ch] BYREF
  int v78; // [rsp+170h] [rbp+10h] BYREF
  int v79; // [rsp+174h] [rbp+14h] BYREF
  int v80; // [rsp+178h] [rbp+18h] BYREF
  int v81; // [rsp+17Ch] [rbp+1Ch] BYREF
  int v82; // [rsp+180h] [rbp+20h] BYREF
  int v83; // [rsp+184h] [rbp+24h] BYREF
  int v84; // [rsp+188h] [rbp+28h] BYREF
  int v85; // [rsp+18Ch] [rbp+2Ch] BYREF
  int v86; // [rsp+190h] [rbp+30h] BYREF
  int v87; // [rsp+194h] [rbp+34h] BYREF
  int v88; // [rsp+198h] [rbp+38h] BYREF
  int v89; // [rsp+19Ch] [rbp+3Ch] BYREF
  int v90; // [rsp+1A0h] [rbp+40h] BYREF
  int v91; // [rsp+1A4h] [rbp+44h] BYREF
  int v92; // [rsp+1A8h] [rbp+48h] BYREF
  int v93; // [rsp+1ACh] [rbp+4Ch] BYREF
  int v94; // [rsp+1B0h] [rbp+50h] BYREF
  int v95; // [rsp+1B4h] [rbp+54h] BYREF
  int v96; // [rsp+1B8h] [rbp+58h] BYREF
  _QWORD v97[2]; // [rsp+1C0h] [rbp+60h] BYREF
  __int64 v98; // [rsp+1D0h] [rbp+70h] BYREF
  __int64 v99; // [rsp+1D8h] [rbp+78h] BYREF
  __int64 v100; // [rsp+1E0h] [rbp+80h] BYREF
  __int64 v101; // [rsp+1E8h] [rbp+88h] BYREF
  __int64 v102; // [rsp+1F0h] [rbp+90h] BYREF
  __int64 v103; // [rsp+1F8h] [rbp+98h] BYREF
  __int64 v104; // [rsp+200h] [rbp+A0h] BYREF
  __int64 v105; // [rsp+208h] [rbp+A8h] BYREF
  _BYTE v106[64]; // [rsp+210h] [rbp+B0h] BYREF
  _QWORD v107[7]; // [rsp+250h] [rbp+F0h] BYREF
  _QWORD *v108; // [rsp+288h] [rbp+128h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+168h]

  v4 = 0;
  std::vector<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2>::vector<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2>(v55, a2[1]);
  v5 = **a2;
  v98 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v6 = *(_QWORD *)(v5 + 48);
    v7 = 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5FD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0x80070057LL,
      (*(_DWORD *)(*(_QWORD *)(v6 + 208) + 28LL) & 0x80) == 0,
      (bool)"Container info structure should be present",
      v50);
    v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v8 > 4u && (unsigned __int8)tlgKeywordOn(v8, 0x470000000000LL) )
    {
      v11 = *(_QWORD *)(v6 + 208);
      v92 = *(_DWORD *)(v11 + 276);
      v93 = *(_DWORD *)(v11 + 272);
      v94 = *(_DWORD *)(v11 + 268);
      v100 = *(_QWORD *)(v11 + 256);
      v95 = *(_DWORD *)(a1 + 516);
      v96 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      v51 = "Container info";
      v52 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v53 = (GUID *)"RdpIdd";
      v99 = 0x1000000;
      v54 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&dword_18004D73C,
        v9,
        v10,
        (__int64)&v54,
        (__int64)&v99,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&v96,
        (__int64)&v95,
        (__int64)&v100,
        (__int64)&v94,
        (__int64)&v93,
        (__int64)&v92);
    }
    v12 = 160 * v4;
    memset_0((void *)(160 * v4 + v55[0]), 0, 0xA0u);
    *(_DWORD *)(v55[0] + 160 * v4) = 160;
    *(_QWORD *)(v55[0] + v12 + 144) = *(_QWORD *)(*(_QWORD *)(v6 + 208) + 256LL);
    *(_DWORD *)(v55[0] + v12 + 152) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 268LL);
    *(_DWORD *)(v55[0] + v12 + 8) = 136;
    *(_QWORD *)(v55[0] + v12 + 16) = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 224LL);
    v13 = *(_QWORD *)(v6 + 208);
    v14 = *(_DWORD *)(v13 + 24);
    *(_DWORD *)(v13 + 24) = 0;
    *(_DWORD *)(v55[0] + v12 + 12) = v14;
    if ( (v14 & 1) != 0 )
    {
      v15 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v15 > 4u && (unsigned __int8)tlgKeywordOn(v15, 0x470000000000LL) )
      {
        v18 = *(_DWORD **)(v6 + 208);
        v56 = v18[27];
        v57 = v18[25];
        v58 = v18[24];
        v59 = v18[23];
        v60 = v18[22];
        v61 = *(_DWORD *)(a1 + 516);
        v62 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v54 = "Display mode";
        v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v52 = (GUID *)"RdpIdd";
        v101 = 0x1000000;
        v51 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&word_18004D686,
          v16,
          v17,
          (__int64)&v51,
          (__int64)&v101,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v62,
          (__int64)&v61,
          (__int64)&v60,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v56);
      }
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 96LL);
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, resolution: %dx%d",
        "CRdpIdAdapter::UpdateDisplayConfigContainer",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x62Bu,
        v49);
      IddCxDisplayMode = CMonitorConfig::GetIddCxDisplayMode(*(_QWORD *)(v6 + 208), v106, 0);
      v20 = *(_OWORD *)IddCxDisplayMode;
      v21 = *(_OWORD *)(IddCxDisplayMode + 16);
      v22 = *(_DWORD *)(IddCxDisplayMode + 32);
      v23 = v55[0];
      *(_OWORD *)(v55[0] + v12 + 24) = v20;
      *(_OWORD *)(v23 + v12 + 40) = v21;
      *(_DWORD *)(v23 + v12 + 56) = v22;
      CRdpIdMonitor::SetDisplayModeProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 = 1;
    }
    v24 = v55[0];
    if ( (*(_BYTE *)(v55[0] + v12 + 12) & 2) != 0 )
    {
      v25 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v25 > 4u && (unsigned __int8)tlgKeywordOn(v25, 0x470000000000LL) )
      {
        v28 = *(_QWORD *)(v6 + 208);
        v102 = *(_QWORD *)(v28 + 256);
        v63 = *(_DWORD *)(v28 + 140);
        v64 = *(_DWORD *)(v28 + 136);
        v65 = *(_DWORD *)(a1 + 516);
        v66 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v54 = "Scale factor";
        v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v52 = (GUID *)"RdpIdd";
        v103 = 0x1000000;
        v51 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v26,
          (unsigned int)&byte_18004D5D7,
          v26,
          v27,
          (__int64)&v51,
          (__int64)&v103,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v66,
          (__int64)&v65,
          (__int64)&v64,
          (__int64)&v63,
          (__int64)&v102);
      }
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 136LL);
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, scale factor: %d",
        "CRdpIdAdapter::UpdateDisplayConfigContainer",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x643u,
        v49);
      *(_DWORD *)(v55[0] + v12 + 60) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 136LL);
      CRdpIdMonitor::SetScaleFactorProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 2u;
      v24 = v55[0];
    }
    if ( (*(_BYTE *)(v24 + v12 + 12) & 4) != 0 )
    {
      v29 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v29 > 4u && (unsigned __int8)tlgKeywordOn(v29, 0x470000000000LL) )
      {
        v32 = *(_QWORD *)(v6 + 208);
        v67 = *(_DWORD *)(v32 + 156);
        v68 = *(_DWORD *)(v32 + 152);
        v69 = *(_DWORD *)(a1 + 516);
        v70 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v54 = "Physical size";
        v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v52 = (GUID *)"RdpIdd";
        v104 = 0x1000000;
        v51 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v30,
          (unsigned int)byte_18004D549,
          v30,
          v31,
          (__int64)&v51,
          (__int64)&v104,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v70,
          (__int64)&v69,
          (__int64)&v68,
          (__int64)&v67);
      }
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 152LL);
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, physical size: %dx%d",
        "CRdpIdAdapter::UpdateDisplayConfigContainer",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x65Bu,
        v49);
      *(_DWORD *)(v55[0] + v12 + 64) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 152LL);
      *(_DWORD *)(v55[0] + v12 + 68) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 156LL);
      v24 = v55[0];
    }
    if ( (*(_BYTE *)(v24 + v12 + 12) & 8) != 0 )
    {
      v33 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 0x470000000000LL) )
      {
        v36 = *(_DWORD **)(v6 + 208);
        v71 = v36[57];
        v72 = v36[56];
        v73 = v36[55];
        v74 = v36[54];
        v75 = v36[53];
        v76 = v36[52];
        v77 = v36[51];
        v78 = v36[50];
        v79 = v36[49];
        v80 = v36[48];
        v81 = v36[47];
        v82 = v36[46];
        v83 = v36[45];
        v84 = v36[44];
        v85 = v36[43];
        v86 = v36[42];
        v87 = *(_DWORD *)(a1 + 516);
        v88 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v54 = "Colorimetry";
        v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v52 = (GUID *)"RdpIdd";
        v105 = 0x1000000;
        v51 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v34,
          (unsigned int)byte_18004D411,
          v34,
          v35,
          (__int64)&v51,
          (__int64)&v105,
          (__int64)&v52,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v88,
          (__int64)&v87,
          (__int64)&v86,
          (__int64)&v85,
          (__int64)&v84,
          (__int64)&v83,
          (__int64)&v82,
          (__int64)&v81,
          (__int64)&v80,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v77,
          (__int64)&v76,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v72,
          (__int64)&v71);
      }
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 212LL);
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, colorimetry Rgb(bpc): %d",
        "CRdpIdAdapter::UpdateDisplayConfigContainer",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x684u,
        v49);
      IddCxColorimetry = (__int128 *)CMonitorConfig::GetIddCxColorimetry(*(_QWORD *)(v6 + 208), v106);
      v38 = *IddCxColorimetry;
      v39 = IddCxColorimetry[1];
      v40 = IddCxColorimetry[2];
      v41 = IddCxColorimetry[3];
      v42 = v55[0];
      *(_OWORD *)(v55[0] + v12 + 72) = v38;
      *(_OWORD *)(v42 + v12 + 88) = v39;
      *(_OWORD *)(v42 + v12 + 104) = v40;
      *(_OWORD *)(v42 + v12 + 120) = v41;
      CRdpIdMonitor::SetColorimetryProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 4u;
      v24 = v55[0];
    }
    if ( (*(_BYTE *)(v24 + v12 + 12) & 0x10) != 0 )
    {
      v43 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v43 > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v43, 0x470000000000LL) )
        {
          v89 = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
          v90 = *(_DWORD *)(a1 + 516);
          v91 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
          v54 = "SDR white level";
          v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
          v52 = (GUID *)"RdpIdd";
          v97[0] = 0x1000000;
          v51 = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v44,
            (unsigned int)byte_18004D38B,
            v44,
            v45,
            (__int64)&v51,
            (__int64)v97,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)&v54,
            (__int64)&v91,
            (__int64)&v90,
            (__int64)&v89);
        }
      }
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, SDR white level: %d",
        "CRdpIdAdapter::UpdateDisplayConfigContainer",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x69Au,
        v49);
      *(_DWORD *)(v55[0] + v12 + 136) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
      CRdpIdMonitor::SetSdrWhiteLevelProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 8u;
    }
    v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v5 + 48) + 312LL) + 64LL))(
            *(_QWORD *)(*(_QWORD *)(v5 + 48) + 312LL),
            v7);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x6A5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v46,
      (int)"Failed to change monitor mode",
      v49);
    v4 = (unsigned int)(v4 + 1);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(&v98);
    v5 = v98;
  }
  if ( !*(_BYTE *)(a1 + 592) )
  {
    v97[0] = -858993459 * (unsigned int)((__int64)(v55[1] - v55[0]) >> 5);
    v97[1] = v55[0];
    v107[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(IDDCX_ADAPTER__ *,IDARG_IN_ADAPTERDISPLAYCONFIGUPDATEFORCONTAINER2 const *),IDDCX_ADAPTER__ * &,IDARG_IN_ADAPTERDISPLAYCONFIGUPDATEFORCONTAINER2 *>,long,>::`vftable';
    v107[1] = IddCxAdapterDisplayConfigUpdateForContainer2;
    v107[2] = v97;
    v107[3] = *(_QWORD *)(a1 + 464);
    v108 = v107;
    CRdpIdAdapter::UpdateDisplayConfig(a1, (__int64)v107);
    if ( v108 )
    {
      v47 = v107;
      LOBYTE(v47) = v108 != v107;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v108 + 32LL))(v108, v47);
    }
  }
  return std::vector<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2>::_Tidy(v55);
}

```

## disassembly

```asm
0x18001e634  mov     [rsp-8+arg_10], rbx
0x18001e639  mov     [rsp-8+arg_18], rsi
0x18001e63e  push    rbp
0x18001e63f  push    rdi
0x18001e640  push    r12
0x18001e642  push    r14
0x18001e644  push    r15
0x18001e646  lea     rbp, [rsp-140h]
0x18001e64e  sub     rsp, 2A0h
0x18001e655  mov     rax, cs:__security_cookie
0x18001e65c  xor     rax, rsp
0x18001e65f  mov     [rbp+160h+var_30], rax
0x18001e666  mov     rbx, rdx
0x18001e669  mov     r14, rcx
0x18001e66c  xor     r12d, r12d
0x18001e66f  mov     rdx, [rdx+8]
0x18001e673  lea     rcx, [rbp+160h+var_1C0]
0x18001e677  call    ??0?$vector@UIDDCX_DISPLAYCONFIGPATHFORCONTAINER2@@V?$allocator@UIDDCX_DISPLAYCONFIGPATHFORCONTAINER2@@@std@@@std@@QEAA@_KAEBV?$allocator@UIDDCX_DISPLAYCONFIGPATHFORCONTAINER2@@@1@@Z; std::vector<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2>::vector<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2>(unsigned __int64,std::allocator<IDDCX_DISPLAYCONFIGPATHFORCONTAINER2> const &)
0x18001e67c  nop
0x18001e67d  mov     rbx, [rbx]
0x18001e680  mov     rbx, [rbx]
0x18001e683  mov     [rbp+160h+var_F0], rbx
0x18001e687  lea     rdi, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001e68e  cmp     byte ptr [rbx+19h], 0
0x18001e692  jnz     loc_18001F1B3
0x18001e698  mov     rsi, [rbx+30h]
0x18001e69c  xor     r15d, r15d
0x18001e69f  mov     rax, [rsi+0D0h]
0x18001e6a6  mov     edx, [rax+1Ch]
0x18001e6a9  shr     edx, 7
0x18001e6ac  not     dl
0x18001e6ae  and     dl, 1
0x18001e6b1  mov     rcx, [rbp+168h]; this
0x18001e6b8  lea     rax, aContainerInfoS; "Container info structure should be pres"...
0x18001e6bf  mov     [rsp+2C0h+var_298], rax; bool
0x18001e6c4  mov     [rsp+2C0h+var_2A0], dl; char
0x18001e6c8  mov     r9d, 80070057h; char *
0x18001e6ce  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001e6d5  mov     edx, 5FDh; void *
0x18001e6da  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001e6df  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001e6e4  mov     r8, [rax+8]
0x18001e6e8  mov     eax, [r8]
0x18001e6eb  cmp     eax, 4
0x18001e6ee  jbe     loc_18001E7F7
0x18001e6f4  mov     rdx, 470000000000h
0x18001e6fe  mov     rcx, r8
0x18001e701  call    _tlgKeywordOn
0x18001e706  test    al, al
0x18001e708  jz      loc_18001E7F7
0x18001e70e  mov     rcx, [rsi+0D0h]
0x18001e715  mov     eax, [rcx+114h]
0x18001e71b  mov     [rbp+160h+var_118], eax
0x18001e71e  mov     eax, [rcx+110h]
0x18001e724  mov     [rbp+160h+var_114], eax
0x18001e727  mov     eax, [rcx+10Ch]
0x18001e72d  mov     [rbp+160h+var_110], eax
0x18001e730  mov     rax, [rcx+100h]
0x18001e737  mov     [rbp+160h+var_E0], rax
0x18001e73e  mov     eax, [r14+204h]
0x18001e745  mov     [rbp+160h+var_10C], eax
0x18001e748  mov     rax, [rbx+30h]
0x18001e74c  mov     ecx, [rax+118h]
0x18001e752  mov     [rbp+160h+var_108], ecx
0x18001e755  lea     rax, aContainerInfo; "Container info"
0x18001e75c  mov     [rbp+160h+var_1E0], rax
0x18001e760  mov     [rbp+160h+var_1D8], rdi
0x18001e764  lea     rax, aRdpidd; "RdpIdd"
0x18001e76b  mov     [rbp+160h+var_1D0], rax
0x18001e76f  mov     [rbp+160h+var_E8], 1000000h
0x18001e777  lea     rax, aCheckpoint; "Checkpoint"
0x18001e77e  mov     [rbp+160h+var_1C8], rax
0x18001e782  lea     rax, [rbp+160h+var_118]
0x18001e786  mov     [rsp+2C0h+var_250], rax
0x18001e78b  lea     rax, [rbp+160h+var_114]
0x18001e78f  mov     [rsp+2C0h+var_258], rax
0x18001e794  lea     rax, [rbp+160h+var_110]
0x18001e798  mov     [rsp+2C0h+var_260], rax
0x18001e79d  lea     rax, [rbp+160h+var_E0]
0x18001e7a4  mov     [rsp+2C0h+var_268], rax
0x18001e7a9  lea     rax, [rbp+160h+var_10C]
0x18001e7ad  mov     [rsp+2C0h+var_270], rax
0x18001e7b2  lea     rax, [rbp+160h+var_108]
0x18001e7b6  mov     [rsp+2C0h+var_278], rax
0x18001e7bb  lea     rax, [rbp+160h+var_1E0]
0x18001e7bf  mov     [rsp+2C0h+var_280], rax
0x18001e7c4  lea     rax, [rbp+160h+var_1D8]
0x18001e7c8  mov     [rsp+2C0h+var_288], rax
0x18001e7cd  lea     rax, [rbp+160h+var_1D0]
0x18001e7d1  mov     [rsp+2C0h+var_290], rax
0x18001e7d6  lea     rax, [rbp+160h+var_E8]
0x18001e7da  mov     [rsp+2C0h+var_298], rax
0x18001e7df  lea     rax, [rbp+160h+var_1C8]
0x18001e7e3  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001e7e8  lea     rdx, dword_18004D73C
0x18001e7ef  mov     rcx, r8
0x18001e7f2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U2@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@64666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e7f7  lea     rdi, [r12+r12*4]
0x18001e7fb  shl     rdi, 5
0x18001e7ff  mov     rcx, [rbp+160h+var_1C0]
0x18001e803  add     rcx, rdi; void *
0x18001e806  xor     edx, edx; Val
0x18001e808  mov     r8d, 0A0h; Size
0x18001e80e  call    memset_0
0x18001e813  mov     rax, [rbp+160h+var_1C0]
0x18001e817  mov     dword ptr [rax+rdi], 0A0h
0x18001e81e  mov     rax, [rsi+0D0h]
0x18001e825  mov     rcx, [rax+100h]
0x18001e82c  mov     rax, [rbp+160h+var_1C0]
0x18001e830  mov     [rax+rdi+90h], rcx
0x18001e838  mov     rax, [rsi+0D0h]
0x18001e83f  mov     ecx, [rax+10Ch]
0x18001e845  mov     rax, [rbp+160h+var_1C0]
0x18001e849  mov     [rax+rdi+98h], ecx
0x18001e850  mov     rax, [rbp+160h+var_1C0]
0x18001e854  mov     dword ptr [rax+rdi+8], 88h
0x18001e85c  mov     rax, [rbx+30h]
0x18001e860  mov     rcx, [rax+0E0h]
0x18001e867  mov     rax, [rbp+160h+var_1C0]
0x18001e86b  mov     [rax+rdi+10h], rcx
0x18001e870  mov     rax, [rsi+0D0h]
0x18001e877  mov     ecx, [rax+18h]
0x18001e87a  mov     [rax+18h], r15d
0x18001e87e  mov     rax, [rbp+160h+var_1C0]
0x18001e882  mov     [rax+rdi+0Ch], ecx
0x18001e886  test    cl, 1
0x18001e889  jz      loc_18001EA3C
0x18001e88f  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001e894  mov     r8, [rax+8]
0x18001e898  mov     eax, [r8]
0x18001e89b  cmp     eax, 4
0x18001e89e  jbe     loc_18001E9AF
0x18001e8a4  mov     rdx, 470000000000h
0x18001e8ae  mov     rcx, r8
0x18001e8b1  call    _tlgKeywordOn
0x18001e8b6  test    al, al
0x18001e8b8  jz      loc_18001E9AF
0x18001e8be  mov     rcx, [rsi+0D0h]
0x18001e8c5  mov     eax, [rcx+6Ch]
0x18001e8c8  mov     [rbp+160h+var_1A8], eax
0x18001e8cb  mov     eax, [rcx+64h]
0x18001e8ce  mov     [rbp+160h+var_1A4], eax
0x18001e8d1  mov     eax, [rcx+60h]
0x18001e8d4  mov     [rbp+160h+var_1A0], eax
0x18001e8d7  mov     eax, [rcx+5Ch]
0x18001e8da  mov     [rbp+160h+var_19C], eax
0x18001e8dd  mov     eax, [rcx+58h]
0x18001e8e0  mov     [rbp+160h+var_198], eax
0x18001e8e3  mov     eax, [r14+204h]
0x18001e8ea  mov     [rbp+160h+var_194], eax
0x18001e8ed  mov     rax, [rbx+30h]
0x18001e8f1  mov     ecx, [rax+118h]
0x18001e8f7  mov     [rbp+160h+var_190], ecx
0x18001e8fa  lea     rax, aDisplayMode; "Display mode"
0x18001e901  mov     [rbp+160h+var_1C8], rax
0x18001e905  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001e90c  mov     [rbp+160h+var_1D0], rax
0x18001e910  lea     rax, aRdpidd; "RdpIdd"
0x18001e917  mov     [rbp+160h+var_1D8], rax
0x18001e91b  mov     [rbp+160h+var_D8], 1000000h
0x18001e926  lea     rax, aCheckpoint; "Checkpoint"
0x18001e92d  mov     [rbp+160h+var_1E0], rax
0x18001e931  lea     rax, [rbp+160h+var_1A8]
0x18001e935  mov     [rsp+2C0h+var_248], rax
0x18001e93a  lea     rax, [rbp+160h+var_1A4]
0x18001e93e  mov     [rsp+2C0h+var_250], rax
0x18001e943  lea     rax, [rbp+160h+var_1A0]
0x18001e947  mov     [rsp+2C0h+var_258], rax
0x18001e94c  lea     rax, [rbp+160h+var_19C]
0x18001e950  mov     [rsp+2C0h+var_260], rax
0x18001e955  lea     rax, [rbp+160h+var_198]
0x18001e959  mov     [rsp+2C0h+var_268], rax
0x18001e95e  lea     rax, [rbp+160h+var_194]
0x18001e962  mov     [rsp+2C0h+var_270], rax
0x18001e967  lea     rax, [rbp+160h+var_190]
0x18001e96b  mov     [rsp+2C0h+var_278], rax
0x18001e970  lea     rax, [rbp+160h+var_1C8]
0x18001e974  mov     [rsp+2C0h+var_280], rax
0x18001e979  lea     rax, [rbp+160h+var_1D0]
0x18001e97d  mov     [rsp+2C0h+var_288], rax
0x18001e982  lea     rax, [rbp+160h+var_1D8]
0x18001e986  mov     [rsp+2C0h+var_290], rax
0x18001e98b  lea     rax, [rbp+160h+var_D8]
0x18001e992  mov     [rsp+2C0h+var_298], rax
0x18001e997  lea     rax, [rbp+160h+var_1E0]
0x18001e99b  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001e9a0  lea     rdx, word_18004D686
0x18001e9a7  mov     rcx, r8
0x18001e9aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@666666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e9af  mov     rcx, [rsi+0D0h]
0x18001e9b6  mov     rdx, [rbx+30h]
0x18001e9ba  mov     eax, [rcx+64h]
0x18001e9bd  mov     dword ptr [rsp+2C0h+var_288], eax
0x18001e9c1  mov     eax, [rcx+60h]
0x18001e9c4  mov     dword ptr [rsp+2C0h+var_290], eax
0x18001e9c8  mov     eax, [rdx+118h]
0x18001e9ce  mov     dword ptr [rsp+2C0h+var_298], eax
0x18001e9d2  mov     dword ptr [rsp+2C0h+var_2A0], 62Bh; unsigned int
0x18001e9da  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001e9e1  lea     r8, aCrdpidadapterU; "CRdpIdAdapter::UpdateDisplayConfigConta"...
0x18001e9e8  lea     rdx, aIdDResolutionD; "Id %d, resolution: %dx%d"
0x18001e9ef  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e9f6  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e9fb  xor     r8d, r8d
0x18001e9fe  lea     rdx, [rbp+160h+var_B0]
0x18001ea05  mov     rcx, [rsi+0D0h]
0x18001ea0c  call    ?GetIddCxDisplayMode@CMonitorConfig@@QEBA?BUIDDCX_DISPLAYCONFIG_MODE@@_N@Z; CMonitorConfig::GetIddCxDisplayMode(bool)
0x18001ea11  movups  xmm0, xmmword ptr [rax]
0x18001ea14  movups  xmm1, xmmword ptr [rax+10h]
0x18001ea18  mov     ecx, [rax+20h]
0x18001ea1b  mov     rax, [rbp+160h+var_1C0]
0x18001ea1f  movups  xmmword ptr [rax+rdi+18h], xmm0
0x18001ea24  movups  xmmword ptr [rax+rdi+28h], xmm1
0x18001ea29  mov     [rax+rdi+38h], ecx
0x18001ea2d  mov     rcx, [rbx+30h]; this
0x18001ea31  call    ?SetDisplayModeProperties@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::SetDisplayModeProperties(void)
0x18001ea36  mov     r15d, 1
0x18001ea3c  mov     rax, [rbp+160h+var_1C0]
0x18001ea40  test    byte ptr [rax+rdi+0Ch], 2
0x18001ea45  jz      loc_18001EBCC
0x18001ea4b  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001ea50  mov     r8, [rax+8]
0x18001ea54  mov     eax, [r8]
0x18001ea57  cmp     eax, 4
0x18001ea5a  jbe     loc_18001EB5E
0x18001ea60  mov     rdx, 470000000000h
0x18001ea6a  mov     rcx, r8
0x18001ea6d  call    _tlgKeywordOn
0x18001ea72  test    al, al
0x18001ea74  jz      loc_18001EB5E
0x18001ea7a  mov     rcx, [rsi+0D0h]
0x18001ea81  mov     rax, [rcx+100h]
0x18001ea88  mov     [rbp+160h+var_D0], rax
0x18001ea8f  mov     eax, [rcx+8Ch]
0x18001ea95  mov     [rbp+160h+var_18C], eax
0x18001ea98  mov     eax, [rcx+88h]
0x18001ea9e  mov     [rbp+160h+var_188], eax
0x18001eaa1  mov     eax, [r14+204h]
0x18001eaa8  mov     [rbp+160h+var_184], eax
0x18001eaab  mov     rax, [rbx+30h]
0x18001eaaf  mov     ecx, [rax+118h]
0x18001eab5  mov     [rbp+160h+var_180], ecx
0x18001eab8  lea     rax, aScaleFactor; "Scale factor"
0x18001eabf  mov     [rbp+160h+var_1C8], rax
0x18001eac3  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001eaca  mov     [rbp+160h+var_1D0], rax
0x18001eace  lea     rax, aRdpidd; "RdpIdd"
0x18001ead5  mov     [rbp+160h+var_1D8], rax
0x18001ead9  mov     [rbp+160h+var_C8], 1000000h
0x18001eae4  lea     rax, aCheckpoint; "Checkpoint"
0x18001eaeb  mov     [rbp+160h+var_1E0], rax
0x18001eaef  lea     rax, [rbp+160h+var_D0]
0x18001eaf6  mov     [rsp+2C0h+var_258], rax
0x18001eafb  lea     rax, [rbp+160h+var_18C]
0x18001eaff  mov     [rsp+2C0h+var_260], rax
0x18001eb04  lea     rax, [rbp+160h+var_188]
0x18001eb08  mov     [rsp+2C0h+var_268], rax
0x18001eb0d  lea     rax, [rbp+160h+var_184]
0x18001eb11  mov     [rsp+2C0h+var_270], rax
0x18001eb16  lea     rax, [rbp+160h+var_180]
0x18001eb1a  mov     [rsp+2C0h+var_278], rax
0x18001eb1f  lea     rax, [rbp+160h+var_1C8]
0x18001eb23  mov     [rsp+2C0h+var_280], rax
0x18001eb28  lea     rax, [rbp+160h+var_1D0]
0x18001eb2c  mov     [rsp+2C0h+var_288], rax
0x18001eb31  lea     rax, [rbp+160h+var_1D8]
0x18001eb35  mov     [rsp+2C0h+var_290], rax
0x18001eb3a  lea     rax, [rbp+160h+var_C8]
0x18001eb41  mov     [rsp+2C0h+var_298], rax
0x18001eb46  lea     rax, [rbp+160h+var_1E0]
0x18001eb4a  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001eb4f  lea     rdx, byte_18004D5D7
0x18001eb56  mov     rcx, r8
0x18001eb59  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001eb5e  mov     rax, [rsi+0D0h]
0x18001eb65  mov     rcx, [rbx+30h]
0x18001eb69  mov     eax, [rax+88h]
0x18001eb6f  mov     dword ptr [rsp+2C0h+var_290], eax
0x18001eb73  mov     eax, [rcx+118h]
0x18001eb79  mov     dword ptr [rsp+2C0h+var_298], eax
0x18001eb7d  mov     dword ptr [rsp+2C0h+var_2A0], 643h; unsigned int
0x18001eb85  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001eb8c  lea     r8, aCrdpidadapterU; "CRdpIdAdapter::UpdateDisplayConfigConta"...
0x18001eb93  lea     rdx, aIdDScaleFactor; "Id %d, scale factor: %d"
0x18001eb9a  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001eba1  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001eba6  mov     rax, [rsi+0D0h]
0x18001ebad  mov     ecx, [rax+88h]
0x18001ebb3  mov     rax, [rbp+160h+var_1C0]
0x18001ebb7  mov     [rax+rdi+3Ch], ecx
0x18001ebbb  mov     rcx, [rbx+30h]; this
0x18001ebbf  call    ?SetScaleFactorProperties@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::SetScaleFactorProperties(void)
0x18001ebc4  or      r15d, 2
0x18001ebc8  mov     rax, [rbp+160h+var_1C0]
0x18001ebcc  test    byte ptr [rax+rdi+0Ch], 4
0x18001ebd1  jz      loc_18001ED50
0x18001ebd7  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001ebdc  mov     r8, [rax+8]
0x18001ebe0  mov     eax, [r8]
0x18001ebe3  cmp     eax, 4
  ... truncated ...
```
