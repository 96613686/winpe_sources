# CRdpIdAdapter::UpdateDisplayConfigNative(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)

- ea: `0x18001f2a0`
- end: `0x18001fd72`
- name: `?UpdateDisplayConfigNative@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z`
- size: `2770`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001de94`
- `0x18001fd78`

## callees

- `0x180001af0`
- `0x1800035f8`
- `0x180003744`
- `0x1800038a4`
- `0x180003bc0`
- `0x180003d80`
- `0x180006f60`
- `0x180007b38`
- `0x18000d614`
- `0x180013c70`
- `0x18001534c`
- `0x18001ddf4`
- `0x18001e284`
- `0x18001f2a0`
- `0x180020e2c`
- `0x180021570`
- `0x18002262c`
- `0x180022724`
- `0x180027398`
- `0x18002784c`
- `0x180027c78`
- `0x180027d70`
- `0x18003f010`

## string_xrefs

- `0x18001f4cb`: `CRdpIdAdapter::UpdateDisplayConfigNative`
- `0x18001f66a`: `CRdpIdAdapter::UpdateDisplayConfigNative`
- `0x18001f7e0`: `CRdpIdAdapter::UpdateDisplayConfigNative`
- `0x18001fa77`: `CRdpIdAdapter::UpdateDisplayConfigNative`
- `0x18001fbf6`: `CRdpIdAdapter::UpdateDisplayConfigNative`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRdpIdAdapter::UpdateDisplayConfigNative(__int64 a1, __int64 **a2)
{
  unsigned int v4; // r12d
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned int v7; // r15d
  __int64 v8; // rdi
  __int64 v9; // rax
  int v10; // ecx
  _DWORD *v11; // r8
  int v12; // r8d
  int v13; // r9d
  _DWORD *v14; // rcx
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 IddCxDisplayMode; // rax
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  _DWORD *v23; // r8
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  _DWORD *v27; // r8
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // rcx
  _DWORD *v32; // r8
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // rcx
  __int128 *IddCxColorimetry; // rax
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm2
  __int128 v40; // xmm3
  __int64 v41; // rax
  _DWORD *v42; // r8
  int v43; // r8d
  int v44; // r9d
  unsigned int v45; // eax
  _QWORD *v46; // rdx
  char *v48; // [rsp+28h] [rbp-138h]
  __int64 v49; // [rsp+30h] [rbp-130h]
  __int64 v50; // [rsp+38h] [rbp-128h]
  __int64 v51; // [rsp+40h] [rbp-120h]
  const char *v52; // [rsp+E0h] [rbp-80h] BYREF
  GUID *v53; // [rsp+E8h] [rbp-78h] BYREF
  GUID *v54; // [rsp+F0h] [rbp-70h] BYREF
  const char *v55; // [rsp+F8h] [rbp-68h] BYREF
  _QWORD v56[3]; // [rsp+100h] [rbp-60h] BYREF
  int v57; // [rsp+118h] [rbp-48h] BYREF
  int v58; // [rsp+11Ch] [rbp-44h] BYREF
  int v59; // [rsp+120h] [rbp-40h] BYREF
  int v60; // [rsp+124h] [rbp-3Ch] BYREF
  int v61; // [rsp+128h] [rbp-38h] BYREF
  int v62; // [rsp+12Ch] [rbp-34h] BYREF
  int v63; // [rsp+130h] [rbp-30h] BYREF
  int v64; // [rsp+134h] [rbp-2Ch] BYREF
  int v65; // [rsp+138h] [rbp-28h] BYREF
  int v66; // [rsp+13Ch] [rbp-24h] BYREF
  int v67; // [rsp+140h] [rbp-20h] BYREF
  int v68; // [rsp+144h] [rbp-1Ch] BYREF
  int v69; // [rsp+148h] [rbp-18h] BYREF
  int v70; // [rsp+14Ch] [rbp-14h] BYREF
  int v71; // [rsp+150h] [rbp-10h] BYREF
  int v72; // [rsp+154h] [rbp-Ch] BYREF
  int v73; // [rsp+158h] [rbp-8h] BYREF
  int v74; // [rsp+15Ch] [rbp-4h] BYREF
  int v75; // [rsp+160h] [rbp+0h] BYREF
  int v76; // [rsp+164h] [rbp+4h] BYREF
  int v77; // [rsp+168h] [rbp+8h] BYREF
  int v78; // [rsp+16Ch] [rbp+Ch] BYREF
  int v79; // [rsp+170h] [rbp+10h] BYREF
  int v80; // [rsp+174h] [rbp+14h] BYREF
  int v81; // [rsp+178h] [rbp+18h] BYREF
  int v82; // [rsp+17Ch] [rbp+1Ch] BYREF
  int v83; // [rsp+180h] [rbp+20h] BYREF
  int v84; // [rsp+184h] [rbp+24h] BYREF
  int v85; // [rsp+188h] [rbp+28h] BYREF
  int v86; // [rsp+18Ch] [rbp+2Ch] BYREF
  int v87; // [rsp+190h] [rbp+30h] BYREF
  int v88; // [rsp+194h] [rbp+34h] BYREF
  int v89; // [rsp+198h] [rbp+38h] BYREF
  int v90; // [rsp+19Ch] [rbp+3Ch] BYREF
  int v91; // [rsp+1A0h] [rbp+40h] BYREF
  int v92; // [rsp+1A4h] [rbp+44h] BYREF
  int v93; // [rsp+1A8h] [rbp+48h] BYREF
  __int64 v94; // [rsp+1B0h] [rbp+50h] BYREF
  _QWORD v95[2]; // [rsp+1B8h] [rbp+58h] BYREF
  __int64 v96; // [rsp+1C8h] [rbp+68h] BYREF
  __int64 v97; // [rsp+1D0h] [rbp+70h] BYREF
  __int64 v98; // [rsp+1D8h] [rbp+78h] BYREF
  __int64 v99; // [rsp+1E0h] [rbp+80h] BYREF
  __int64 v100; // [rsp+1E8h] [rbp+88h] BYREF
  _BYTE v101[64]; // [rsp+1F0h] [rbp+90h] BYREF
  _QWORD v102[7]; // [rsp+230h] [rbp+D0h] BYREF
  _QWORD *v103; // [rsp+268h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+148h]

  v4 = 0;
  std::vector<IDDCX_DISPLAYCONFIGPATH2>::vector<IDDCX_DISPLAYCONFIGPATH2>(v56, a2[1]);
  v5 = **a2;
  v94 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v6 = *(_QWORD *)(v5 + 48);
    v7 = 0;
    v8 = 136LL * v4;
    memset_0((void *)(v8 + v56[0]), 0, 0x88u);
    *(_DWORD *)(v56[0] + v8) = 136;
    *(_QWORD *)(v56[0] + v8 + 8) = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 224LL);
    v9 = *(_QWORD *)(v6 + 208);
    v10 = *(_DWORD *)(v9 + 24);
    *(_DWORD *)(v9 + 24) = 0;
    *(_DWORD *)(v56[0] + v8 + 4) = v10;
    if ( (v10 & 1) != 0 )
    {
      v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x470000000000LL) )
      {
        v14 = *(_DWORD **)(v6 + 208);
        v89 = v14[31];
        v90 = v14[27];
        v91 = v14[25];
        v92 = v14[24];
        v93 = v14[23];
        v57 = v14[22];
        v58 = *(_DWORD *)(a1 + 516);
        v59 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v52 = "Display mode";
        v53 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v54 = (GUID *)"RdpIdd";
        v100 = 0x1000000;
        v55 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_18004D2CD,
          v12,
          v13,
          (__int64)&v55,
          (__int64)&v100,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v93,
          (__int64)&v92,
          (__int64)&v91,
          (__int64)&v90,
          (__int64)&v89);
      }
      v15 = *(_DWORD **)(v6 + 208);
      LODWORD(v51) = v15[31];
      LODWORD(v50) = v15[25];
      LODWORD(v49) = v15[24];
      LODWORD(v48) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, resolution: %dx%d, color mode: %d",
        "CRdpIdAdapter::UpdateDisplayConfigNative",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x6F9u,
        v48,
        v49,
        v50,
        v51);
      LOBYTE(v16) = 1;
      IddCxDisplayMode = CMonitorConfig::GetIddCxDisplayMode(*(_QWORD *)(v6 + 208), v101, v16);
      v18 = *(_OWORD *)IddCxDisplayMode;
      v19 = *(_OWORD *)(IddCxDisplayMode + 16);
      v20 = *(_DWORD *)(IddCxDisplayMode + 32);
      v21 = v56[0];
      *(_OWORD *)(v56[0] + v8 + 16) = v18;
      *(_OWORD *)(v21 + v8 + 32) = v19;
      *(_DWORD *)(v21 + v8 + 48) = v20;
      CRdpIdMonitor::SetDisplayModeProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 = 1;
    }
    v22 = v56[0];
    if ( (*(_BYTE *)(v56[0] + v8 + 4) & 2) != 0 )
    {
      v23 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v23 > 4u && (unsigned __int8)tlgKeywordOn(v23, 0x470000000000LL) )
      {
        v26 = *(_QWORD *)(v6 + 208);
        v96 = *(_QWORD *)(v26 + 256);
        v60 = *(_DWORD *)(v26 + 140);
        v61 = *(_DWORD *)(v26 + 136);
        v62 = *(_DWORD *)(a1 + 516);
        v63 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v55 = "Scale factor";
        v54 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v53 = (GUID *)"RdpIdd";
        v97 = 0x1000000;
        v52 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v24,
          (unsigned int)byte_18004D221,
          v24,
          v25,
          (__int64)&v52,
          (__int64)&v97,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v63,
          (__int64)&v62,
          (__int64)&v61,
          (__int64)&v60,
          (__int64)&v96);
      }
      LODWORD(v48) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, scale factor: %d",
        "CRdpIdAdapter::UpdateDisplayConfigNative",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x711u);
      *(_DWORD *)(v56[0] + v8 + 52) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 136LL);
      CRdpIdMonitor::SetScaleFactorProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 2u;
      v22 = v56[0];
    }
    if ( (*(_BYTE *)(v22 + v8 + 4) & 4) != 0 )
    {
      v27 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v27 > 4u && (unsigned __int8)tlgKeywordOn(v27, 0x470000000000LL) )
      {
        v30 = *(_QWORD *)(v6 + 208);
        v64 = *(_DWORD *)(v30 + 156);
        v65 = *(_DWORD *)(v30 + 152);
        v66 = *(_DWORD *)(a1 + 516);
        v67 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v55 = "Physical size";
        v54 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v53 = (GUID *)"RdpIdd";
        v98 = 0x1000000;
        v52 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)&word_18004D196,
          v28,
          v29,
          (__int64)&v52,
          (__int64)&v98,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v67,
          (__int64)&v66,
          (__int64)&v65,
          (__int64)&v64);
      }
      v31 = *(_QWORD *)(v6 + 208);
      LODWORD(v50) = *(_DWORD *)(v31 + 156);
      LODWORD(v49) = *(_DWORD *)(v31 + 152);
      LODWORD(v48) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, physical size: %dx%d",
        "CRdpIdAdapter::UpdateDisplayConfigNative",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x729u,
        v48,
        v49,
        v50);
      *(_DWORD *)(v56[0] + v8 + 56) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 152LL);
      *(_DWORD *)(v56[0] + v8 + 60) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 156LL);
      v22 = v56[0];
    }
    if ( (*(_BYTE *)(v22 + v8 + 4) & 8) != 0 )
    {
      v32 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v32 > 4u && (unsigned __int8)tlgKeywordOn(v32, 0x470000000000LL) )
      {
        v35 = *(_DWORD **)(v6 + 208);
        v68 = v35[57];
        v69 = v35[56];
        v70 = v35[55];
        v71 = v35[54];
        v72 = v35[53];
        v73 = v35[52];
        v74 = v35[51];
        v75 = v35[50];
        v76 = v35[49];
        v77 = v35[48];
        v78 = v35[47];
        v79 = v35[46];
        v80 = v35[45];
        v81 = v35[44];
        v82 = v35[43];
        v83 = v35[42];
        v84 = *(_DWORD *)(a1 + 516);
        v85 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
        v55 = "Colorimetry";
        v54 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v53 = (GUID *)"RdpIdd";
        v99 = 0x1000000;
        v52 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v33,
          (unsigned int)byte_18004D061,
          v33,
          v34,
          (__int64)&v52,
          (__int64)&v99,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v55,
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
          (__int64)&v71,
          (__int64)&v70,
          (__int64)&v69,
          (__int64)&v68);
      }
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 212LL);
      LODWORD(v48) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, colorimetry Rgb(bpc): %d",
        "CRdpIdAdapter::UpdateDisplayConfigNative",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x752u,
        v48,
        v49);
      IddCxColorimetry = (__int128 *)CMonitorConfig::GetIddCxColorimetry(*(_QWORD *)(v6 + 208), v101);
      v37 = *IddCxColorimetry;
      v38 = IddCxColorimetry[1];
      v39 = IddCxColorimetry[2];
      v40 = IddCxColorimetry[3];
      v41 = v56[0];
      *(_OWORD *)(v56[0] + v8 + 64) = v37;
      *(_OWORD *)(v41 + v8 + 80) = v38;
      *(_OWORD *)(v41 + v8 + 96) = v39;
      *(_OWORD *)(v41 + v8 + 112) = v40;
      CRdpIdMonitor::SetColorimetryProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 4u;
      v22 = v56[0];
    }
    if ( (*(_BYTE *)(v22 + v8 + 4) & 0x10) != 0 )
    {
      v42 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v42 > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v42, 0x470000000000LL) )
        {
          v86 = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
          v87 = *(_DWORD *)(a1 + 516);
          v88 = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
          v55 = "SDR white level";
          v54 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
          v53 = (GUID *)"RdpIdd";
          v95[0] = 0x1000000;
          v52 = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v43,
            (unsigned int)&word_18004CFDE,
            v43,
            v44,
            (__int64)&v52,
            (__int64)v95,
            (__int64)&v53,
            (__int64)&v54,
            (__int64)&v55,
            (__int64)&v88,
            (__int64)&v87,
            (__int64)&v86);
        }
      }
      LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
      LODWORD(v48) = *(_DWORD *)(*(_QWORD *)(v5 + 48) + 280LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Id %d, SDR white level: %d",
        "CRdpIdAdapter::UpdateDisplayConfigNative",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x768u,
        v48,
        v49);
      *(_DWORD *)(v56[0] + v8 + 128) = *(_DWORD *)(*(_QWORD *)(v6 + 208) + 244LL);
      CRdpIdMonitor::SetSdrWhiteLevelProperties(*(CRdpIdMonitor **)(v5 + 48));
      v7 |= 8u;
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v5 + 48) + 312LL) + 64LL))(
            *(_QWORD *)(*(_QWORD *)(v5 + 48) + 312LL),
            v7);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x773,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v45,
      (int)"Failed to change monitor mode",
      v48);
    ++v4;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(&v94);
    v5 = v94;
  }
  if ( !*(_BYTE *)(a1 + 592) )
  {
    v95[0] = -252645135 * (unsigned int)((__int64)(v56[1] - v56[0]) >> 3);
    v95[1] = v56[0];
    v102[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(IDDCX_ADAPTER__ *,IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2 const *),IDDCX_ADAPTER__ * &,IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2 *>,long,>::`vftable';
    v102[1] = IddCxAdapterDisplayConfigUpdate2;
    v102[2] = v95;
    v102[3] = *(_QWORD *)(a1 + 464);
    v103 = v102;
    CRdpIdAdapter::UpdateDisplayConfig(a1, (__int64)v102);
    if ( v103 )
    {
      v46 = v102;
      LOBYTE(v46) = v103 != v102;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v103 + 32LL))(v103, v46);
    }
  }
  return std::vector<IDDCX_DISPLAYCONFIGPATH2>::_Tidy(v56);
}

```

## disassembly

```asm
0x18001f2a0  mov     [rsp-8+arg_10], rbx
0x18001f2a5  mov     [rsp-8+arg_18], rsi
0x18001f2aa  push    rbp
0x18001f2ab  push    rdi
0x18001f2ac  push    r12
0x18001f2ae  push    r14
0x18001f2b0  push    r15
0x18001f2b2  lea     rbp, [rsp-120h]
0x18001f2ba  sub     rsp, 280h
0x18001f2c1  mov     rax, cs:__security_cookie
0x18001f2c8  xor     rax, rsp
0x18001f2cb  mov     [rbp+140h+var_30], rax
0x18001f2d2  mov     rbx, rdx
0x18001f2d5  mov     r14, rcx
0x18001f2d8  xor     r12d, r12d
0x18001f2db  mov     rdx, [rdx+8]
0x18001f2df  lea     rcx, [rbp+140h+var_1A0]
0x18001f2e3  call    ??0?$vector@UIDDCX_DISPLAYCONFIGPATH2@@V?$allocator@UIDDCX_DISPLAYCONFIGPATH2@@@std@@@std@@QEAA@_KAEBV?$allocator@UIDDCX_DISPLAYCONFIGPATH2@@@1@@Z; std::vector<IDDCX_DISPLAYCONFIGPATH2>::vector<IDDCX_DISPLAYCONFIGPATH2>(unsigned __int64,std::allocator<IDDCX_DISPLAYCONFIGPATH2> const &)
0x18001f2e8  nop
0x18001f2e9  mov     rbx, [rbx]
0x18001f2ec  mov     rbx, [rbx]
0x18001f2ef  mov     [rbp+140h+var_F0], rbx
0x18001f2f3  cmp     byte ptr [rbx+19h], 0
0x18001f2f7  jnz     loc_18001FC8B
0x18001f2fd  mov     rsi, [rbx+30h]
0x18001f301  xor     r15d, r15d
0x18001f304  mov     eax, r12d
0x18001f307  imul    rdi, rax, 88h
0x18001f30e  mov     rcx, [rbp+140h+var_1A0]
0x18001f312  add     rcx, rdi; void *
0x18001f315  xor     edx, edx; Val
0x18001f317  mov     r8d, 88h; Size
0x18001f31d  call    memset_0
0x18001f322  mov     rax, [rbp+140h+var_1A0]
0x18001f326  mov     dword ptr [rax+rdi], 88h
0x18001f32d  mov     rax, [rbx+30h]
0x18001f331  mov     rcx, [rax+0E0h]
0x18001f338  mov     rax, [rbp+140h+var_1A0]
0x18001f33c  mov     [rax+rdi+8], rcx
0x18001f341  mov     rax, [rsi+0D0h]
0x18001f348  mov     ecx, [rax+18h]
0x18001f34b  mov     [rax+18h], r15d
0x18001f34f  mov     rax, [rbp+140h+var_1A0]
0x18001f353  mov     [rax+rdi+4], ecx
0x18001f357  test    cl, 1
0x18001f35a  jz      loc_18001F526
0x18001f360  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001f365  mov     r8, [rax+8]
0x18001f369  mov     eax, [r8]
0x18001f36c  cmp     eax, 4
0x18001f36f  jbe     loc_18001F492
0x18001f375  mov     rdx, 470000000000h
0x18001f37f  mov     rcx, r8
0x18001f382  call    _tlgKeywordOn
0x18001f387  test    al, al
0x18001f389  jz      loc_18001F492
0x18001f38f  mov     rcx, [rsi+0D0h]
0x18001f396  mov     eax, [rcx+7Ch]
0x18001f399  mov     [rbp+140h+var_108], eax
0x18001f39c  mov     eax, [rcx+6Ch]
0x18001f39f  mov     [rbp+140h+var_104], eax
0x18001f3a2  mov     eax, [rcx+64h]
0x18001f3a5  mov     [rbp+140h+var_100], eax
0x18001f3a8  mov     eax, [rcx+60h]
0x18001f3ab  mov     [rbp+140h+var_FC], eax
0x18001f3ae  mov     eax, [rcx+5Ch]
0x18001f3b1  mov     [rbp+140h+var_F8], eax
0x18001f3b4  mov     eax, [rcx+58h]
0x18001f3b7  mov     [rbp+140h+var_188], eax
0x18001f3ba  mov     eax, [r14+204h]
0x18001f3c1  mov     [rbp+140h+var_184], eax
0x18001f3c4  mov     rax, [rbx+30h]
0x18001f3c8  mov     ecx, [rax+118h]
0x18001f3ce  mov     [rbp+140h+var_180], ecx
0x18001f3d1  lea     rax, aDisplayMode; "Display mode"
0x18001f3d8  mov     [rbp+140h+var_1C0], rax
0x18001f3dc  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001f3e3  mov     [rbp+140h+var_1B8], rax
0x18001f3e7  lea     rax, aRdpidd; "RdpIdd"
0x18001f3ee  mov     [rbp+140h+var_1B0], rax
0x18001f3f2  mov     [rbp+140h+var_B8], 1000000h
0x18001f3fd  lea     rax, aCheckpoint; "Checkpoint"
0x18001f404  mov     [rbp+140h+var_1A8], rax
0x18001f408  lea     rax, [rbp+140h+var_108]
0x18001f40c  mov     [rsp+2A0h+var_220], rax
0x18001f414  lea     rax, [rbp+140h+var_104]
0x18001f418  mov     [rsp+2A0h+var_228], rax
0x18001f41d  lea     rax, [rbp+140h+var_100]
0x18001f421  mov     [rsp+2A0h+var_230], rax
0x18001f426  lea     rax, [rbp+140h+var_FC]
0x18001f42a  mov     [rsp+2A0h+var_238], rax
0x18001f42f  lea     rax, [rbp+140h+var_F8]
0x18001f433  mov     [rsp+2A0h+var_240], rax
0x18001f438  lea     rax, [rbp+140h+var_188]
0x18001f43c  mov     [rsp+2A0h+var_248], rax
0x18001f441  lea     rax, [rbp+140h+var_184]
0x18001f445  mov     [rsp+2A0h+var_250], rax
0x18001f44a  lea     rax, [rbp+140h+var_180]
0x18001f44e  mov     [rsp+2A0h+var_258], rax
0x18001f453  lea     rax, [rbp+140h+var_1C0]
0x18001f457  mov     [rsp+2A0h+var_260], rax
0x18001f45c  lea     rax, [rbp+140h+var_1B8]
0x18001f460  mov     [rsp+2A0h+var_268], rax
0x18001f465  lea     rax, [rbp+140h+var_1B0]
0x18001f469  mov     [rsp+2A0h+var_270], rax
0x18001f46e  lea     rax, [rbp+140h+var_B8]
0x18001f475  mov     [rsp+2A0h+var_278], rax
0x18001f47a  lea     rax, [rbp+140h+var_1A8]
0x18001f47e  mov     qword ptr [rsp+2A0h+var_280], rax
0x18001f483  lea     rdx, byte_18004D2CD
0x18001f48a  mov     rcx, r8
0x18001f48d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6666666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f492  mov     rcx, [rsi+0D0h]
0x18001f499  mov     rdx, [rbx+30h]
0x18001f49d  mov     eax, [rcx+7Ch]
0x18001f4a0  mov     dword ptr [rsp+2A0h+var_260], eax
0x18001f4a4  mov     eax, [rcx+64h]
0x18001f4a7  mov     dword ptr [rsp+2A0h+var_268], eax
0x18001f4ab  mov     eax, [rcx+60h]
0x18001f4ae  mov     dword ptr [rsp+2A0h+var_270], eax
0x18001f4b2  mov     eax, [rdx+118h]
0x18001f4b8  mov     dword ptr [rsp+2A0h+var_278], eax
0x18001f4bc  mov     [rsp+2A0h+var_280], 6F9h; unsigned int
0x18001f4c4  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001f4cb  lea     r8, aCrdpidadapterU_0; "CRdpIdAdapter::UpdateDisplayConfigNativ"...
0x18001f4d2  lea     rdx, aIdDResolutionD_0; "Id %d, resolution: %dx%d, color mode: %"...
0x18001f4d9  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001f4e0  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001f4e5  mov     r8b, 1
0x18001f4e8  lea     rdx, [rbp+140h+var_B0]
0x18001f4ef  mov     rcx, [rsi+0D0h]
0x18001f4f6  call    ?GetIddCxDisplayMode@CMonitorConfig@@QEBA?BUIDDCX_DISPLAYCONFIG_MODE@@_N@Z; CMonitorConfig::GetIddCxDisplayMode(bool)
0x18001f4fb  movups  xmm0, xmmword ptr [rax]
0x18001f4fe  movups  xmm1, xmmword ptr [rax+10h]
0x18001f502  mov     ecx, [rax+20h]
0x18001f505  mov     rax, [rbp+140h+var_1A0]
0x18001f509  movups  xmmword ptr [rax+rdi+10h], xmm0
0x18001f50e  movups  xmmword ptr [rax+rdi+20h], xmm1
0x18001f513  mov     [rax+rdi+30h], ecx
0x18001f517  mov     rcx, [rbx+30h]; this
0x18001f51b  call    ?SetDisplayModeProperties@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::SetDisplayModeProperties(void)
0x18001f520  mov     r15d, 1
0x18001f526  mov     rax, [rbp+140h+var_1A0]
0x18001f52a  test    byte ptr [rax+rdi+4], 2
0x18001f52f  jz      loc_18001F6AA
0x18001f535  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001f53a  mov     r8, [rax+8]
0x18001f53e  mov     eax, [r8]
0x18001f541  cmp     eax, 4
0x18001f544  jbe     loc_18001F63C
0x18001f54a  mov     rdx, 470000000000h
0x18001f554  mov     rcx, r8
0x18001f557  call    _tlgKeywordOn
0x18001f55c  test    al, al
0x18001f55e  jz      loc_18001F63C
0x18001f564  mov     rcx, [rsi+0D0h]
0x18001f56b  mov     rax, [rcx+100h]
0x18001f572  mov     [rbp+140h+var_D8], rax
0x18001f576  mov     eax, [rcx+8Ch]
0x18001f57c  mov     [rbp+140h+var_17C], eax
0x18001f57f  mov     eax, [rcx+88h]
0x18001f585  mov     [rbp+140h+var_178], eax
0x18001f588  mov     eax, [r14+204h]
0x18001f58f  mov     [rbp+140h+var_174], eax
0x18001f592  mov     rax, [rbx+30h]
0x18001f596  mov     ecx, [rax+118h]
0x18001f59c  mov     [rbp+140h+var_170], ecx
0x18001f59f  lea     rax, aScaleFactor; "Scale factor"
0x18001f5a6  mov     [rbp+140h+var_1A8], rax
0x18001f5aa  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001f5b1  mov     [rbp+140h+var_1B0], rax
0x18001f5b5  lea     rax, aRdpidd; "RdpIdd"
0x18001f5bc  mov     [rbp+140h+var_1B8], rax
0x18001f5c0  mov     [rbp+140h+var_D0], 1000000h
0x18001f5c8  lea     rax, aCheckpoint; "Checkpoint"
0x18001f5cf  mov     [rbp+140h+var_1C0], rax
0x18001f5d3  lea     rax, [rbp+140h+var_D8]
0x18001f5d7  mov     [rsp+2A0h+var_238], rax
0x18001f5dc  lea     rax, [rbp+140h+var_17C]
0x18001f5e0  mov     [rsp+2A0h+var_240], rax
0x18001f5e5  lea     rax, [rbp+140h+var_178]
0x18001f5e9  mov     [rsp+2A0h+var_248], rax
0x18001f5ee  lea     rax, [rbp+140h+var_174]
0x18001f5f2  mov     [rsp+2A0h+var_250], rax
0x18001f5f7  lea     rax, [rbp+140h+var_170]
0x18001f5fb  mov     [rsp+2A0h+var_258], rax
0x18001f600  lea     rax, [rbp+140h+var_1A8]
0x18001f604  mov     [rsp+2A0h+var_260], rax
0x18001f609  lea     rax, [rbp+140h+var_1B0]
0x18001f60d  mov     [rsp+2A0h+var_268], rax
0x18001f612  lea     rax, [rbp+140h+var_1B8]
0x18001f616  mov     [rsp+2A0h+var_270], rax
0x18001f61b  lea     rax, [rbp+140h+var_D0]
0x18001f61f  mov     [rsp+2A0h+var_278], rax
0x18001f624  lea     rax, [rbp+140h+var_1C0]
0x18001f628  mov     qword ptr [rsp+2A0h+var_280], rax
0x18001f62d  lea     rdx, byte_18004D221
0x18001f634  mov     rcx, r8
0x18001f637  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001f63c  mov     rax, [rsi+0D0h]
0x18001f643  mov     rcx, [rbx+30h]
0x18001f647  mov     eax, [rax+88h]
0x18001f64d  mov     dword ptr [rsp+2A0h+var_270], eax
0x18001f651  mov     eax, [rcx+118h]
0x18001f657  mov     dword ptr [rsp+2A0h+var_278], eax
0x18001f65b  mov     [rsp+2A0h+var_280], 711h; unsigned int
0x18001f663  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001f66a  lea     r8, aCrdpidadapterU_0; "CRdpIdAdapter::UpdateDisplayConfigNativ"...
0x18001f671  lea     rdx, aIdDScaleFactor; "Id %d, scale factor: %d"
0x18001f678  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001f67f  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001f684  mov     rax, [rsi+0D0h]
0x18001f68b  mov     ecx, [rax+88h]
0x18001f691  mov     rax, [rbp+140h+var_1A0]
0x18001f695  mov     [rax+rdi+34h], ecx
0x18001f699  mov     rcx, [rbx+30h]; this
0x18001f69d  call    ?SetScaleFactorProperties@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::SetScaleFactorProperties(void)
0x18001f6a2  or      r15d, 2
0x18001f6a6  mov     rax, [rbp+140h+var_1A0]
0x18001f6aa  test    byte ptr [rax+rdi+4], 4
0x18001f6af  jz      loc_18001F828
0x18001f6b5  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001f6ba  mov     r8, [rax+8]
0x18001f6be  mov     eax, [r8]
0x18001f6c1  cmp     eax, 4
0x18001f6c4  jbe     loc_18001F7A8
0x18001f6ca  mov     rdx, 470000000000h
0x18001f6d4  mov     rcx, r8
0x18001f6d7  call    _tlgKeywordOn
0x18001f6dc  test    al, al
0x18001f6de  jz      loc_18001F7A8
0x18001f6e4  mov     rcx, [rsi+0D0h]
0x18001f6eb  mov     eax, [rcx+9Ch]
0x18001f6f1  mov     [rbp+140h+var_16C], eax
0x18001f6f4  mov     eax, [rcx+98h]
0x18001f6fa  mov     [rbp+140h+var_168], eax
0x18001f6fd  mov     eax, [r14+204h]
0x18001f704  mov     [rbp+140h+var_164], eax
0x18001f707  mov     rax, [rbx+30h]
0x18001f70b  mov     ecx, [rax+118h]
0x18001f711  mov     [rbp+140h+var_160], ecx
0x18001f714  lea     rax, aPhysicalSize; "Physical size"
0x18001f71b  mov     [rbp+140h+var_1A8], rax
0x18001f71f  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001f726  mov     [rbp+140h+var_1B0], rax
0x18001f72a  lea     rax, aRdpidd; "RdpIdd"
0x18001f731  mov     [rbp+140h+var_1B8], rax
0x18001f735  mov     [rbp+140h+var_C8], 1000000h
0x18001f73d  lea     rax, aCheckpoint; "Checkpoint"
0x18001f744  mov     [rbp+140h+var_1C0], rax
0x18001f748  lea     rax, [rbp+140h+var_16C]
0x18001f74c  mov     [rsp+2A0h+var_240], rax
0x18001f751  lea     rax, [rbp+140h+var_168]
0x18001f755  mov     [rsp+2A0h+var_248], rax
0x18001f75a  lea     rax, [rbp+140h+var_164]
0x18001f75e  mov     [rsp+2A0h+var_250], rax
0x18001f763  lea     rax, [rbp+140h+var_160]
0x18001f767  mov     [rsp+2A0h+var_258], rax
0x18001f76c  lea     rax, [rbp+140h+var_1A8]
0x18001f770  mov     [rsp+2A0h+var_260], rax
0x18001f775  lea     rax, [rbp+140h+var_1B0]
0x18001f779  mov     [rsp+2A0h+var_268], rax
0x18001f77e  lea     rax, [rbp+140h+var_1B8]
0x18001f782  mov     [rsp+2A0h+var_270], rax
0x18001f787  lea     rax, [rbp+140h+var_C8]
0x18001f78b  mov     [rsp+2A0h+var_278], rax
0x18001f790  lea     rax, [rbp+140h+var_1C0]
0x18001f794  mov     qword ptr [rsp+2A0h+var_280], rax
0x18001f799  lea     rdx, word_18004D196
0x18001f7a0  mov     rcx, r8
0x18001f7a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f7a8  mov     rcx, [rsi+0D0h]
0x18001f7af  mov     rdx, [rbx+30h]
0x18001f7b3  mov     eax, [rcx+9Ch]
0x18001f7b9  mov     dword ptr [rsp+2A0h+var_268], eax
0x18001f7bd  mov     eax, [rcx+98h]
0x18001f7c3  mov     dword ptr [rsp+2A0h+var_270], eax
0x18001f7c7  mov     eax, [rdx+118h]
0x18001f7cd  mov     dword ptr [rsp+2A0h+var_278], eax
0x18001f7d1  mov     [rsp+2A0h+var_280], 729h; unsigned int
0x18001f7d9  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001f7e0  lea     r8, aCrdpidadapterU_0; "CRdpIdAdapter::UpdateDisplayConfigNativ"...
0x18001f7e7  lea     rdx, aIdDPhysicalSiz; "Id %d, physical size: %dx%d"
0x18001f7ee  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001f7f5  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001f7fa  mov     rax, [rsi+0D0h]
0x18001f801  mov     ecx, [rax+98h]
0x18001f807  mov     rax, [rbp+140h+var_1A0]
0x18001f80b  mov     [rax+rdi+38h], ecx
0x18001f80f  mov     rax, [rsi+0D0h]
0x18001f816  mov     ecx, [rax+9Ch]
0x18001f81c  mov     rax, [rbp+140h+var_1A0]
0x18001f820  mov     [rax+rdi+3Ch], ecx
0x18001f824  mov     rax, [rbp+140h+var_1A0]
0x18001f828  test    byte ptr [rax+rdi+4], 8
0x18001f82d  jz      loc_18001FADC
0x18001f833  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001f838  mov     r8, [rax+8]
0x18001f83c  mov     eax, [r8]
0x18001f83f  cmp     eax, 4
  ... truncated ...
```
