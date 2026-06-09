# CRdpIdAdapter::ProcessIoctl(RDPIDD_FILEOBJECT_CONTEXT *,std::span<uchar,-1> const &,std::span<uchar,-1> const &,uint *)

- ea: `0x1800185bc`
- end: `0x18001a256`
- name: `?ProcessIoctl@CRdpIdAdapter@@QEAAXPEAURDPIDD_FILEOBJECT_CONTEXT@@AEBV?$span@E$0?0@std@@1PEAI@Z`
- size: `7322`
- prototype: `__int64 __usercall@<rax>(CRdpIdAdapter *this@<rcx>, struct RDPIDD_FILEOBJECT_CONTEXT *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011088`

## callees

- `0x180001af0`
- `0x180001f14`
- `0x18000203c`
- `0x180002178`
- `0x1800027b8`
- `0x180002a40`
- `0x180002b90`
- `0x180002cf4`
- `0x1800032f0`
- `0x1800041fc`
- `0x180007b20`
- `0x18000d614`
- `0x18000eb00`
- `0x180011584`
- `0x180016834`
- `0x180017e5c`
- `0x18001818c`
- `0x1800184b4`
- `0x1800185bc`
- `0x18001a25c`
- `0x18001a5c0`
- `0x18001a6bc`
- `0x18001a784`
- `0x18001a860`
- `0x18001adec`
- `0x18001afa8`
- `0x18001b104`
- `0x18001b1a0`
- `0x18001b530`
- `0x18001b584`
- `0x18001b644`
- `0x18001cd04`
- `0x18001dd70`
- `0x18001de3c`
- `0x180020d00`
- `0x18002142c`
- `0x180021570`
- `0x180034180`

## string_xrefs

- `0x18001a20a`: `RDPIDD_OPCODE_TYPE_RAIL_MONITOR_SURFACE_UPDATE is supported only for RAIL scenarios`
- `0x18001a232`: `Input buffer size is too small to cast to RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE`
- `0x180019bd4`: `Input buffer size is too small to access RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE structure array`
- `0x180019b25`: `Receive RDPIDD_OPCODE_TYPE_RAIL_MONITOR_SURFACE_UPDATE`
- `0x18001a11a`: `RDPIDD_OPCODE_BIND_DRIVER is requested by non-privileged process`
- `0x180019f5e`: `RDPIDD_OPCODE_TYPE_UNBIND_DRIVER is requested by non-privileged process`
- `0x180019d09`: `Input buffer size is too small to access array of RDP_MONITOR_INFO structures`
- `0x180019da6`: `RDPIDD_OPCODE_TYPE_LOAD_AVENC is requested by non-privileged process`
- `0x180019fae`: `RDPIDD_OPCODE_TYPE_UNLOAD_AVENC is requested by non-privileged process`
- `0x180019c69`: `RDPIDD_OPCODE_START_AVENC_PROCESSOR is requested by non-privileged process`
- `0x180019c19`: `RDPIDD_OPCODE_STOP_AVENC_PROCESSOR is requested by non-privileged process`
- `0x180019e1e`: `RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL is requested by non-privileged process`
- `0x180019e46`: `Input buffer size is too small to cast to RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL`
- `0x180018e9b`: `Receive RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL`
- `0x180018fb6`: `ConfigFileIo: mode %x, {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180019298`: `FileIo channel has not been created`
- `0x180019ffe`: `Input buffer size is too small to cast to RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION`
- `0x18001a026`: `Input buffer size is too small to access array of RDP_MONITOR_CONFIGURATION structures`
- `0x18001a04e`: `Output buffer size is too small to cast to RDPIDD_OUT_SET_MONITOR_CONFIGURATION`
- `0x1800195a1`: `Receive RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION`
- `0x180019639`: `SetMonitorConfiguration`
- `0x180019ebe`: `RDPIDD_OPCODE_TYPE_SET_PROPERTY_BAG is requested by non-privileged process`
- `0x180019f0e`: `Input buffer size is too small to access array of RDPIDD_PROPERTY_BAG_ENTRY structures`
- `0x180019e6e`: `RDPIDD_OPCODE_TYPE_SET_STATIC_REENCODE_FRAME_COUNT is requested by non-privileged process`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRdpIdAdapter::ProcessIoctl(
        CRdpIdAdapter *this,
        struct RDPIDD_FILEOBJECT_CONTEXT *a2,
        _QWORD *a3,
        struct _RDPIDD_FILE_CHANNEL_PEEK_BUFFER **a4,
        CFileIoChannel *a5)
{
  CFileIoChannel *v9; // r13
  unsigned int *v10; // r15
  unsigned int v11; // edx
  _DWORD *v12; // r8
  int v13; // r8d
  int v14; // r9d
  const struct _GUID *v15; // r15
  _DWORD *v16; // r8
  int v17; // r8d
  int v18; // r9d
  _DWORD *v19; // r8
  int v20; // r8d
  int v21; // r9d
  _DWORD *v22; // r8
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  struct _RDPIDD_OUT_LOAD_AVENC *v29; // rbx
  _DWORD *v30; // r8
  int v31; // r8d
  int v32; // r9d
  _DWORD *v33; // r8
  int v34; // r8d
  int v35; // r9d
  _DWORD *v36; // r8
  int v37; // r8d
  int v38; // r9d
  _DWORD *v39; // r8
  int v40; // r8d
  int v41; // r9d
  struct _RDPIDD_FILE_CHANNEL_PEEK_BUFFER *v42; // rdi
  CFileIoChannel *v43; // rbx
  _DWORD *v44; // r8
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rdx
  _DWORD *v48; // r8
  int v49; // r8d
  int v50; // r9d
  __int64 v51; // rax
  struct _RDPIDD_FILE_CHANNEL_PEEK_BUFFER *v52; // rbx
  _DWORD *v53; // r8
  int v54; // r8d
  int v55; // r9d
  int v56; // eax
  _DWORD *v57; // r8
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // rdx
  __int64 v61; // r8
  const void *v62; // rax
  __int64 v63; // r8
  _DWORD *v64; // rcx
  int v65; // r8d
  int v66; // r9d
  _DWORD *v67; // r8
  int v68; // r8d
  int v69; // r9d
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rbx
  _DWORD *v72; // rcx
  int v73; // r8d
  int v74; // r9d
  _DWORD *v75; // rcx
  int v76; // r8d
  int v77; // r9d
  int v78; // [rsp+20h] [rbp-A1h]
  char *v79; // [rsp+28h] [rbp-99h]
  const char *v80; // [rsp+30h] [rbp-91h]
  __int64 v81; // [rsp+38h] [rbp-89h]
  __int64 v82; // [rsp+40h] [rbp-81h]
  __int64 v83; // [rsp+48h] [rbp-79h]
  __int64 v84; // [rsp+50h] [rbp-71h]
  __int64 v85; // [rsp+58h] [rbp-69h]
  __int64 v86; // [rsp+60h] [rbp-61h]
  const char *v87; // [rsp+90h] [rbp-31h] BYREF
  const char *v88; // [rsp+98h] [rbp-29h] BYREF
  __int64 v89; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-19h] BYREF
  const char *v91; // [rsp+B0h] [rbp-11h] BYREF
  char v92[8]; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v93; // [rsp+C0h] [rbp-1h] BYREF
  _QWORD v94[9]; // [rsp+C8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]
  const struct _GUID *v96; // [rsp+130h] [rbp+6Fh] BYREF

  v9 = a5;
  *(_DWORD *)a5 = 0;
  v10 = (unsigned int *)*a3;
  v11 = *(_DWORD *)(*a3 + 8LL);
  if ( v11 > 0x200 )
  {
    if ( v11 == 513 )
    {
      if ( *((_DWORD *)this + 110) != 2 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x803,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC00000BBLL,
          (int)"RDPIDD_OPCODE_TYPE_RAIL_MONITOR_SURFACE_UPDATE is supported only for RAIL scenarios",
          v79);
      if ( a3[1] < 0x24u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x80B,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE",
          v79);
      if ( a3[1] < (unsigned __int64)*v10 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x815,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to access RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE structure array",
          v79);
      v75 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v75 > 5u )
      {
        v94[0] = *((_QWORD *)this + 65);
        LODWORD(a5) = *((_DWORD *)this + 129);
        v91 = "Receive RDPIDD_OPCODE_TYPE_RAIL_MONITOR_SURFACE_UPDATE";
        v88 = "CRdpIdAdapter::ProcessIoctl";
        LODWORD(v96) = 2077;
        v87 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (_DWORD)v75,
          (unsigned int)byte_18004CEB1,
          v76,
          v77,
          (__int64)&v87,
          (__int64)&v96,
          (__int64)&v88,
          (__int64)&v91,
          (__int64)&a5,
          (__int64)v94);
      }
      if ( *((_DWORD *)this + 110) == 3 )
        CRdpIdAdapter::ReportCriticalError(this, 1, 2, 2147549183LL);
      CRdpIdAdapter::ProcessMonitorSurfaceUpdate(this, (struct _RDPIDD_OPCODE_RAIL_MONITOR_SURFACE_UPDATE *const)v10);
      return;
    }
    if ( v11 == 514 )
    {
      if ( *((_DWORD *)this + 110) != 2 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x7E0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC00000BBLL,
          (int)"RDPIDD_OPCODE_TYPE_RAIL_RDP_PASSTHROUGH_DATA is supported only for RAIL scenarios",
          v79);
      v70 = a3[1];
      if ( v70 < 0xD )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x7E8,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_RAIL_RDP_PASSTHROUGH_DATA",
          v79);
      v71 = v70 - 12;
      v72 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v72 > 5u )
      {
        LODWORD(a5) = v71;
        v94[0] = *((_QWORD *)this + 65);
        LODWORD(v96) = *((_DWORD *)this + 129);
        v91 = "Receive RDPIDD_OPCODE_TYPE_RAIL_RDP_PASSTHROUGH_DATA";
        v88 = "CRdpIdAdapter::ProcessIoctl";
        LODWORD(v89) = 2036;
        v87 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (_DWORD)v72,
          (unsigned int)byte_18004CF01,
          v73,
          v74,
          (__int64)&v87,
          (__int64)&v89,
          (__int64)&v88,
          (__int64)&v91,
          (__int64)&v96,
          (__int64)v94,
          (__int64)&a5);
      }
      CRdpIdAdapter::ProcessRdpPassthroughData(this, (struct _RDPIDD_OPCODE_RAIL_RDP_PASSTHROUGH_DATA *const)v10, v71);
      return;
    }
    if ( v11 != 1032 )
      goto LABEL_171;
    if ( !*((_BYTE *)a2 + 45) )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x877,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000022LL,
        (int)"RDPIDD_OPCODE_BIND_DRIVER is requested by non-privileged process",
        v79);
    if ( a3[1] < 0x14u )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x87E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_BIND_DRIVER",
        v79);
    if ( (unsigned __int64)a4[1] < 0xC )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x885,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Output buffer size is too small to cast to RDPIDD_OUT_BIND_DRIVER",
        v79);
    if ( a3[1] < (unsigned __int64)*v10 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x88F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is smaller than payload of RDPIDD_OPCODE_BIND_DRIVER",
        v79);
    v52 = *a4;
    v67 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v67 > 4u && (unsigned __int8)tlgKeywordOn(v67, 0x470000000000LL) )
    {
      v96 = (const struct _GUID *)*((_QWORD *)this + 65);
      LODWORD(a5) = *((_DWORD *)this + 129);
      v94[0] = "Receive RDPIDD_OPCODE_BIND_DRIVER";
      v91 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v88 = "RdpIdd";
      v87 = (const char *)0x1000000;
      v90 = (__int64)"Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v68,
        (unsigned int)&byte_18004CDF7,
        v68,
        v69,
        (__int64)&v90,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v91,
        (__int64)v94,
        (__int64)&a5,
        (__int64)&v96);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"BindDriver",
      "CRdpIdAdapter::ProcessIoctl",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      0x898u);
    CRdpIdAdapter::ProcessBindDriver(this, (struct _RDPIDD_OPCODE_BIND_DRIVER *const)v10, v52, a2);
    goto LABEL_123;
  }
  if ( v11 == 512 )
  {
    if ( *((_DWORD *)this + 110) != 2 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x7BB,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC00000BBLL,
        (int)"RDPIDD_OPCODE_TYPE_RAIL_FRAME_MARKER is supported only for RAIL scenarios",
        v79);
    if ( a3[1] < 0x24u )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x7C2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_RAIL_FRAME_MARKER",
        v79);
    v64 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v64 > 5u )
    {
      LODWORD(a5) = v10[5];
      v91 = *(const char **)(v10 + 7);
      LODWORD(v96) = v10[4];
      LODWORD(v93) = v10[3];
      v88 = (const char *)*((_QWORD *)this + 65);
      *(_DWORD *)v92 = *((_DWORD *)this + 129);
      v87 = "Receive RDPIDD_OPCODE_RAIL_FRAME_MARKER";
      v90 = (__int64)"CRdpIdAdapter::ProcessIoctl";
      LODWORD(v89) = 2001;
      v94[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v64,
        (unsigned int)&byte_18004CF5F,
        v65,
        v66,
        (__int64)v94,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v87,
        (__int64)v92,
        (__int64)&v88,
        (__int64)&v93,
        (__int64)&v96,
        (__int64)&v91,
        (__int64)&a5);
    }
    CRdpIdAdapter::ProcessFrameMarker(this, (const struct DRV_FRAME_MARKER *)v10, a2);
    return;
  }
  if ( v11 > 8 )
  {
    if ( v11 == 9 )
    {
      if ( (unsigned __int64)a4[1] < 0x224 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x9D8,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Output buffer size is too small to cast to RDPIDD_OUT_QUERY_DRIVER_VERSION",
          v79);
      v57 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v57 > 4u && (unsigned __int8)tlgKeywordOn(v57, 0x400000000000LL) )
      {
        v96 = (const struct _GUID *)*((_QWORD *)this + 65);
        LODWORD(a5) = *((_DWORD *)this + 129);
        v91 = "Receive RDPIDD_OPCODE_QUERY_DRIVER_VERSION";
        v88 = (const char *)0x1000000;
        v87 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v58,
          (unsigned int)byte_18004CA21,
          v58,
          v59,
          (__int64)&v87,
          (__int64)&v88,
          (__int64)&v91,
          (__int64)&a5,
          (__int64)&v96);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"QueryDriverVersion",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x9E1u);
      v52 = *a4;
      *(_DWORD *)v52 = 548;
      *((_DWORD *)v52 + 1) = *((_DWORD *)this + 86);
      *((_DWORD *)v52 + 2) = *((_DWORD *)this + 87);
      *((_DWORD *)v52 + 3) = *((_DWORD *)this + 89);
      *((_DWORD *)v52 + 4) = *((_DWORD *)this + 90);
      *((_DWORD *)v52 + 5) = *((_DWORD *)this + 93);
      *((_DWORD *)v52 + 6) = *((_DWORD *)this + 94);
      v61 = 260;
      if ( *((_QWORD *)this + 50) < 0x104u )
        v61 = *((_QWORD *)this + 50);
      v62 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 384, v60, v61);
      memcpy_0((char *)v52 + 28, v62, 2 * v63);
    }
    else
    {
      if ( v11 != 10 )
      {
        switch ( v11 )
        {
          case 0xBu:
            if ( !*((_BYTE *)a2 + 45) )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0x934,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000022LL,
                (int)"RDPIDD_OPCODE_TYPE_UNLOAD_AVENC is requested by non-privileged process",
                v79);
            if ( a3[1] < 0xCu )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0x93B,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_UNLOAD_AVENC",
                v79);
            v48 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
            if ( *v48 > 4u && (unsigned __int8)tlgKeywordOn(v48, 0x470000000000LL) )
            {
              v96 = (const struct _GUID *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                            (char *)this + 384,
                                            v47,
                                            v48);
              v91 = (const char *)*((_QWORD *)this + 65);
              LODWORD(a5) = *((_DWORD *)this + 129);
              v88 = "Receive RDPIDD_OPCODE_UNLOAD_AVENC";
              v87 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
              v90 = (__int64)"RdpIdd";
              v89 = 0x1000000;
              *(_QWORD *)v92 = "Checkpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
                v49,
                (unsigned int)&byte_18004CBCF,
                v49,
                v50,
                (__int64)v92,
                (__int64)&v89,
                (__int64)&v90,
                (__int64)&v87,
                (__int64)&v88,
                (__int64)&a5,
                (__int64)&v91,
                (__int64)&v96);
            }
            v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 384, v47, v48);
            Rdp::Modern::Utils::CInflightRecorder::pushN(
              (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
              (wchar_t *)L"UnloadAvenc: %s",
              "CRdpIdAdapter::ProcessIoctl",
              "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              0x945u,
              v51);
            CRdpIdAdapter::ProcessUnloadAvenc(this);
            break;
          case 0xCu:
            if ( !*((_BYTE *)a2 + 45) )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0x8A7,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000022LL,
                (int)"RDPIDD_OPCODE_TYPE_UNBIND_DRIVER is requested by non-privileged process",
                v79);
            if ( a3[1] < 0xCu )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0x8AE,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_UNBIND_DRIVER",
                v79);
            v44 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
            if ( *v44 > 4u && (unsigned __int8)tlgKeywordOn(v44, 0x470000000000LL) )
            {
              v96 = (const struct _GUID *)*((_QWORD *)this + 65);
              LODWORD(a5) = *((_DWORD *)this + 129);
              v91 = "Receive RDPIDD_OPCODE_UNBIND_DRIVER";
              v88 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
              v87 = "RdpIdd";
              v90 = 0x1000000;
              v89 = (__int64)"Checkpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                v45,
                (unsigned int)&dword_18004CD94,
                v45,
                v46,
                (__int64)&v89,
                (__int64)&v90,
                (__int64)&v87,
                (__int64)&v88,
                (__int64)&v91,
                (__int64)&a5,
                (__int64)&v96);
            }
            Rdp::Modern::Utils::CInflightRecorder::pushN(
              (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
              (wchar_t *)L"UnbindDriver",
              "CRdpIdAdapter::ProcessIoctl",
              "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              0x8B7u);
            CRdpIdAdapter::ProcessUnbindDriver(this, a2);
            break;
          case 0xDu:
            if ( (unsigned __int64)a4[1] < 0x18 )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0x9BE,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Output buffer size is too small to cast to RDPIDD_FILE_CHANNEL_PEEK_BUFFER",
                v79);
            v42 = *a4;
            CRdpIdAdapter::FindFileIoChannel(this, &a5, a2, 0);
            v43 = a5;
            wil::details::in1diag3::Throw_HrIfMsg(
              retaddr,
              (void *)0x9CA,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              (const char *)0x80070057LL,
              a5 == 0,
              (bool)"FileIo channel has not been created",
              v80);
            CFileIoChannel::OnPeek(v43, v42);
            *(_DWORD *)v9 = 24;
            wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&a5);
            break;
          case 0xEu:
            if ( !*((_BYTE *)a2 + 45) )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0xA19,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000022LL,
                (int)"RDPIDD_OPCODE_TYPE_SET_PROPERTY_BAG is requested by non-privileged process",
                v79);
            if ( a3[1] < 0x1Cu )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0xA21,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_SET_PROPERTY_BAG",
                v79);
            if ( a3[1] < (unsigned __int64)*v10 )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0xA2B,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Input buffer size is too small to access array of RDPIDD_PROPERTY_BAG_ENTRY structures",
                v79);
            v39 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
            if ( *v39 > 4u && (unsigned __int8)tlgKeywordOn(v39, 0x470000000000LL) )
            {
              v96 = (const struct _GUID *)*((_QWORD *)this + 65);
              LODWORD(a5) = *((_DWORD *)this + 129);
              v91 = "Receive RDPIDD_OPCODE_SET_PROPERTY_BAG";
              v88 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
              v87 = "RdpIdd";
              v90 = 0x1000000;
              v89 = (__int64)"Checkpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                v40,
                (unsigned int)byte_18004C95B,
                v40,
                v41,
                (__int64)&v89,
                (__int64)&v90,
                (__int64)&v87,
                (__int64)&v88,
                (__int64)&v91,
                (__int64)&a5,
                (__int64)&v96);
            }
            Rdp::Modern::Utils::CInflightRecorder::push0(
              (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
              L"SetPropertyBag",
              "CRdpIdAdapter::ProcessIoctl",
              "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              0xA34u);
            CRdpIdAdapter::ProcessSetPropertyBag(this, (struct _RDPIDD_OPCODE_SET_PROPERTY_BAG *const)v10);
            break;
          case 0xFu:
            if ( !*((_BYTE *)a2 + 45) )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0xA3F,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000022LL,
                (int)"RDPIDD_OPCODE_TYPE_SET_STATIC_REENCODE_FRAME_COUNT is requested by non-privileged process",
                v79);
            if ( a3[1] < 0x10u )
              wil::details::in1diag3::Throw_NtStatusMsg(
                retaddr,
                (void *)0xA46,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
                (const char *)0xC0000023LL,
                (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_SET_STATIC_REENCODE_FRAME_COUNT",
                v79);
            v36 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
            if ( *v36 > 4u && (unsigned __int8)tlgKeywordOn(v36, 0x470000000000LL) )
            {
              LODWORD(a5) = v10[3];
              v91 = (const char *)*((_QWORD *)this + 65);
              LODWORD(v96) = *((_DWORD *)this + 129);
              v88 = "Receive RDPIDD_OPCODE_TYPE_SET_STATIC_REENCODE_FRAME_COUNT";
              v87 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
              v90 = (__int64)"RdpIdd";
              v89 = 0x1000000;
              *(_QWORD *)v92 = "Checkpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                v37,
                (unsigned int)&dword_18004C8E4,
                v37,
                v38,
                (__int64)v92,
                (__int64)&v89,
                (__int64)&v90,
                (__int64)&v87,
                (__int64)&v88,
                (__int64)&v96,
                (__int64)&v91,
                (__int64)&a5);
            }
            LODWORD(v79) = v10[3];
            Rdp::Modern::Utils::CInflightRecorder::pushN(
              (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
              (wchar_t *)L"SetStaticReencodeFrameCount: %u",
              "CRdpIdAdapter::ProcessIoctl",
              "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
              0xA52u,
              v79);
            CRdpIdAdapter::ProcessSetStaticReencodeFrameCount(
              this,
              (struct _RDPIDD_OPCODE_SET_STATIC_REENCODE_FRAME_COUNT *const)v10);
            break;
          default:
            goto LABEL_171;
        }
        return;
      }
      if ( a3[1] < 0x18u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x9F0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION",
          v79);
      if ( a3[1] < (unsigned __int64)*v10 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x9FA,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to access array of RDP_MONITOR_CONFIGURATION structures",
          v79);
      if ( (unsigned __int64)a4[1] - 1 <= 0x12 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0xA02,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Output buffer size is too small to cast to RDPIDD_OUT_SET_MONITOR_CONFIGURATION",
          v79);
      v52 = *a4;
      v53 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v53 > 4u && (unsigned __int8)tlgKeywordOn(v53, 0x470000000000LL) )
      {
        v96 = (const struct _GUID *)*((_QWORD *)this + 65);
        LODWORD(a5) = *((_DWORD *)this + 129);
        v91 = "Receive RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION";
        v88 = (const char *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v87 = "RdpIdd";
        v90 = 0x1000000;
        v89 = (__int64)"Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v54,
          (unsigned int)&word_18004C9BE,
          v54,
          v55,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&v88,
          (__int64)&v91,
          (__int64)&a5,
          (__int64)&v96);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"SetMonitorConfiguration",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0xA0Du);
      CRdpIdAdapter::ProcessSetMonitorConfiguration(
        this,
        (struct _RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION *const)v10,
        v52);
      if ( !v52 )
      {
        v56 = 0;
LABEL_124:
        *(_DWORD *)v9 = v56;
        return;
      }
    }
LABEL_123:
    v56 = *(_DWORD *)v52;
    goto LABEL_124;
  }
  switch ( v11 )
  {
    case 8u:
      if ( !*((_BYTE *)a2 + 45) )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x999,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000022LL,
          (int)"RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL is requested by non-privileged process",
          v79);
      if ( a3[1] < 0x40u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x9A0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL",
          v79);
      v33 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 0x470000000000LL) )
      {
        LODWORD(a5) = v10[7];
        v88 = (const char *)(v10 + 3);
        v87 = (const char *)*((_QWORD *)this + 65);
        LODWORD(v96) = *((_DWORD *)this + 129);
        v90 = (__int64)"Receive RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL";
        v89 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        *(_QWORD *)v92 = "RdpIdd";
        v93 = 0x1000000;
        v91 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v34,
          (unsigned int)byte_18004CA73,
          v34,
          v35,
          (__int64)&v91,
          (__int64)&v93,
          (__int64)v92,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v96,
          (__int64)&v87,
          (__int64)&v88,
          (__int64)&a5);
      }
      LODWORD(v86) = *((unsigned __int8 *)v10 + 23);
      LODWORD(v85) = *((unsigned __int8 *)v10 + 22);
      LODWORD(v84) = *((unsigned __int8 *)v10 + 21);
      LODWORD(v83) = *((unsigned __int8 *)v10 + 20);
      LODWORD(v82) = *((unsigned __int16 *)v10 + 9);
      LODWORD(v81) = *((unsigned __int16 *)v10 + 8);
      LODWORD(v80) = v10[3];
      LODWORD(v79) = v10[7];
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"ConfigFileIo: mode %x, {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x9B3u,
        v79,
        v80,
        v81,
        v82,
        v83,
        v84,
        v85,
        v86,
        *((unsigned __int8 *)v10 + 24),
        *((unsigned __int8 *)v10 + 25),
        *((unsigned __int8 *)v10 + 26),
        *((unsigned __int8 *)v10 + 27));
      CRdpIdAdapter::ProcessConfigFileIoChannel(this, (struct _RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL *const)v10, a2);
      break;
    case 1u:
      if ( !*((_BYTE *)a2 + 45) )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x908,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000022LL,
          (int)"RDPIDD_OPCODE_TYPE_LOAD_AVENC is requested by non-privileged process",
          v79);
      if ( a3[1] < 0x224u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x90F,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_LOAD_AVENC",
          v79);
      v29 = 0;
      if ( a4[1] )
      {
        if ( (unsigned __int64)a4[1] < 0x14 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x91B,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
            (const char *)0xC0000023LL,
            (int)"Output buffer size is too small to cast to RDPIDD_OUT_LOAD_AVENC",
            v79);
        v29 = *a4;
        *(_DWORD *)v9 = 20;
      }
      v30 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v30 > 4u && (unsigned __int8)tlgKeywordOn(v30, 0x470000000000LL) )
      {
        v96 = (const struct _GUID *)(v10 + 3);
        v88 = (const char *)*((_QWORD *)this + 65);
        LODWORD(a5) = *((_DWORD *)this + 129);
        v87 = "Receive RDPIDD_OPCODE_LOAD_AVENC";
        v90 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v89 = (__int64)"RdpIdd";
        *(_QWORD *)v92 = 0x1000000;
        v93 = (__int64)"Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v31,
          (unsigned int)word_18004CC42,
          v31,
          v32,
          (__int64)&v93,
          (__int64)v92,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&a5,
          (__int64)&v88,
          (__int64)&v96);
      }
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"LoadAvenc: %s",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x929u,
        v10 + 3);
      CRdpIdAdapter::ProcessLoadAvenc(this, (struct _RDPIDD_OPCODE_LOAD_AVENC *const)v10, v29);
      break;
    case 2u:
      if ( a3[1] >= 0xCu )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x86D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC00000BBLL,
          v78);
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x858,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_DRIVER_BUGCHECK",
        v79);
    case 3u:
      if ( a3[1] < 0x10u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x838,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_CONTROL_DWM_FRAME_DUMP",
          v79);
      if ( !*((_BYTE *)this + 504) )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x84E,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000022LL,
          v78);
      v26 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v26 > 4u )
      {
        LODWORD(a5) = v10[3];
        v88 = (const char *)*((_QWORD *)this + 65);
        LODWORD(v96) = *((_DWORD *)this + 129);
        v87 = "Receive RDPIDD_OPCODE_CONTROL_DWM_FRAME_DUMP";
        v90 = (__int64)"CRdpIdAdapter::ProcessIoctl";
        LODWORD(v93) = 2117;
        v89 = (__int64)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (_DWORD)v26,
          (unsigned int)word_18004CE5A,
          v27,
          v28,
          (__int64)&v89,
          (__int64)&v93,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&v96,
          (__int64)&v88,
          (__int64)&a5);
      }
      *((_BYTE *)this + 505) = v10[3] != 0;
      break;
    case 4u:
      if ( a3[1] < 0x10u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x8C3,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_SET_MONITOR_LAYOUT",
          v79);
      v22 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v22 > 4u && (unsigned __int8)tlgKeywordOn(v22, 0x470000000000LL) )
      {
        LODWORD(a5) = v10[3];
        v88 = (const char *)*((_QWORD *)this + 65);
        LODWORD(v96) = *((_DWORD *)this + 129);
        v87 = "Receive RDPIDD_OPCODE_SET_MONITOR_LAYOUT";
        v90 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v89 = (__int64)"RdpIdd";
        *(_QWORD *)v92 = 0x1000000;
        v93 = (__int64)"Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v23,
          (unsigned int)&dword_18004CD24,
          v23,
          v24,
          (__int64)&v93,
          (__int64)v92,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&v96,
          (__int64)&v88,
          (__int64)&a5);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"SetMonitorLayout",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x8CFu);
      v25 = v10[3];
      if ( (unsigned int)(v25 - 1) > 0xF )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x8D7,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC000000DLL,
          (int)"Invalid number of monitors specified",
          v79);
      if ( a3[1] < (unsigned __int64)(592 * v25 + 16) )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x8DF,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to access array of RDP_MONITOR_INFO structures",
          v79);
      CRdpIdAdapter::ProcessSetMonitorLayout(this, (struct Rdp::Idd::v20::_RDPIDD_OPCODE_SET_MONITOR_LAYOUT *const)v10);
      break;
    case 5u:
      if ( a3[1] < 0x10u )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x8EE,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_SET_CURSOR_MODE",
          v79);
      v19 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v19 > 4u && (unsigned __int8)tlgKeywordOn(v19, 0x470000000000LL) )
      {
        LODWORD(a5) = v10[3];
        v88 = (const char *)*((_QWORD *)this + 65);
        LODWORD(v96) = *((_DWORD *)this + 129);
        v87 = "Receive RDPIDD_OPCODE_SET_CURSOR_MODE";
        v90 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v89 = (__int64)"RdpIdd";
        *(_QWORD *)v92 = 0x1000000;
        v93 = (__int64)"Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_18004CCB5,
          v20,
          v21,
          (__int64)&v93,
          (__int64)v92,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&v96,
          (__int64)&v88,
          (__int64)&a5);
      }
      LODWORD(v79) = v10[3];
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"SetCursorMode: %d",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x8FAu,
        v79);
      CRdpIdAdapter::ProcessSetCursorMode(this, (struct _RDPIDD_OPCODE_SET_CURSOR_MODE *const)v10);
      break;
    case 6u:
      if ( !*((_BYTE *)a2 + 45) )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x950,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000022LL,
          (int)"RDPIDD_OPCODE_START_AVENC_PROCESSOR is requested by non-privileged process",
          v79);
      if ( a3[1] < 0x1Cu )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x957,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_START_AVENC_PROCESSOR",
          v79);
      v15 = (const struct _GUID *)(v10 + 3);
      v16 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v16 > 4u && (unsigned __int8)tlgKeywordOn(v16, 0x470000000000LL) )
      {
        v96 = v15;
        v88 = (const char *)*((_QWORD *)this + 65);
        LODWORD(a5) = *((_DWORD *)this + 129);
        v87 = "Receive RDPIDD_OPCODE_START_AVENC_PROCESSOR";
        v90 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v89 = (__int64)"RdpIdd";
        *(_QWORD *)v92 = 0x1000000;
        v93 = (__int64)"Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
          v17,
          (unsigned int)&dword_18004CB5C,
          v17,
          v18,
          (__int64)&v93,
          (__int64)v92,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v87,
          (__int64)&a5,
          (__int64)&v88,
          (__int64)&v96);
      }
      LODWORD(v85) = v15->Data4[3];
      LODWORD(v84) = v15->Data4[2];
      LODWORD(v83) = v15->Data4[1];
      LODWORD(v82) = v15->Data4[0];
      LODWORD(v81) = v15->Data3;
      LODWORD(v80) = v15->Data2;
      LODWORD(v79) = v15->Data1;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Start processor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x968u,
        v79,
        v80,
        v81,
        v82,
        v83,
        v84,
        v85,
        v15->Data4[4],
        v15->Data4[5],
        v15->Data4[6],
        v15->Data4[7]);
      CRdpIdAdapter::ProcessStartProcessor(this, v15);
      break;
    case 7u:
      if ( !*((_BYTE *)a2 + 45) )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x976,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000022LL,
          (int)"RDPIDD_OPCODE_STOP_AVENC_PROCESSOR is requested by non-privileged process",
          v79);
      if ( a3[1] < 0xCu )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x97D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)0xC0000023LL,
          (int)"Input buffer size is too small to cast to RDPIDD_OPCODE_STOP_AVENC_PROCESSOR",
          v79);
      v12 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v12 > 4u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v12, 0x470000000000LL) )
        {
          v96 = (const struct _GUID *)((char *)this + 544);
          v89 = *((_QWORD *)this + 65);
          LODWORD(a5) = *((_DWORD *)this + 129);
          *(_QWORD *)v92 = "Receive RDPIDD_OPCODE_STOP_AVENC_PROCESSOR";
          v93 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
          v90 = (__int64)"RdpIdd";
          v87 = (const char *)0x1000000;
          v88 = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
            v13,
            (unsigned int)byte_18004CAE9,
            v13,
            v14,
            (__int64)&v88,
            (__int64)&v87,
            (__int64)&v90,
            (__int64)&v93,
            (__int64)v92,
            (__int64)&a5,
            (__int64)&v89,
            (__int64)&v96);
        }
      }
      LODWORD(v85) = *((unsigned __int8 *)this + 555);
      LODWORD(v84) = *((unsigned __int8 *)this + 554);
      LODWORD(v83) = *((unsigned __int8 *)this + 553);
      LODWORD(v82) = *((unsigned __int8 *)this + 552);
      LODWORD(v81) = *((unsigned __int16 *)this + 275);
      LODWORD(v80) = *((unsigned __int16 *)this + 274);
      LODWORD(v79) = *((_DWORD *)this + 136);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Stop processor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
        "CRdpIdAdapter::ProcessIoctl",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x98Bu,
        v79,
        v80,
        v81,
        v82,
        v83,
        v84,
        v85,
        *((unsigned __int8 *)this + 556),
        *((unsigned __int8 *)this + 557),
        *((unsigned __int8 *)this + 558),
        *((unsigned __int8 *)this + 559));
      CRdpIdAdapter::ProcessStopProcessor(this);
      return;
    default:
LABEL_171:
      LODWORD(v79) = *(_DWORD *)(*a3 + 8LL);
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0xA58,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)0xC00000BBLL,
        (int)"Unknown Ioctl 0x%lx",
        v79);
  }
}

```

## disassembly

```asm
0x1800185bc  push    rbp
0x1800185be  push    rbx
0x1800185bf  push    rsi
0x1800185c0  push    rdi
0x1800185c1  push    r12
0x1800185c3  push    r13
0x1800185c5  push    r14
0x1800185c7  push    r15
0x1800185c9  lea     rbp, [rsp-17h]
0x1800185ce  sub     rsp, 0D8h
0x1800185d5  mov     rdi, r9
0x1800185d8  mov     rbx, r8
0x1800185db  mov     r12, rdx
0x1800185de  mov     r14, rcx
0x1800185e1  xor     esi, esi
0x1800185e3  mov     r13, [rbp+4Fh+arg_20]
0x1800185e7  mov     [r13+0], esi
0x1800185eb  mov     r15, [r8]
0x1800185ee  mov     edx, [r15+8]
0x1800185f2  mov     eax, 200h
0x1800185f7  cmp     edx, eax
0x1800185f9  ja      loc_1800198AD
0x1800185ff  jz      loc_1800197AE
0x180018605  cmp     edx, 8
0x180018608  ja      loc_180018FDC
0x18001860e  jz      loc_180018E32
0x180018614  mov     eax, edx
0x180018616  sub     eax, 1
0x180018619  jz      loc_180018CDC
0x18001861f  sub     eax, 1
0x180018622  jz      loc_180018CC1
0x180018628  sub     eax, 1
0x18001862b  jz      loc_180018BF1
0x180018631  sub     eax, 1
0x180018634  jz      loc_180018AAF
0x18001863a  sub     eax, 1
0x18001863d  jz      loc_18001898D
0x180018643  sub     eax, 1
0x180018646  jz      loc_180018802
0x18001864c  cmp     eax, 1
0x18001864f  jnz     loc_18001A0EA
0x180018655  cmp     [r12+2Dh], sil
0x18001865a  jz      loc_180019C15
0x180018660  cmp     qword ptr [r8+8], 0Ch
0x180018665  jb      loc_180019C3D
0x18001866b  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180018670  mov     r8, [rax+8]
0x180018674  mov     eax, [r8]
0x180018677  cmp     eax, 4
0x18001867a  jbe     loc_180018745
0x180018680  mov     rdx, 470000000000h
0x18001868a  mov     rcx, r8
0x18001868d  call    _tlgKeywordOn
0x180018692  test    al, al
0x180018694  jz      loc_180018745
0x18001869a  lea     rax, [r14+220h]
0x1800186a1  mov     [rbp+4Fh+arg_10], rax
0x1800186a5  mov     rax, [r14+208h]
0x1800186ac  mov     [rbp+4Fh+var_70], rax
0x1800186b0  mov     eax, [r14+204h]
0x1800186b7  mov     dword ptr [rbp+4Fh+arg_20], eax
0x1800186ba  lea     rax, aReceiveRdpiddO_1; "Receive RDPIDD_OPCODE_STOP_AVENC_PROCES"...
0x1800186c1  mov     qword ptr [rbp+4Fh+var_58], rax
0x1800186c5  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800186cc  mov     [rbp+4Fh+var_50], rax
0x1800186d0  lea     rax, aRdpidd; "RdpIdd"
0x1800186d7  mov     [rbp+4Fh+var_68], rax
0x1800186db  mov     [rbp+4Fh+var_80], 1000000h
0x1800186e3  lea     rax, aCheckpoint; "Checkpoint"
0x1800186ea  mov     [rbp+4Fh+var_78], rax
0x1800186ee  lea     rax, [rbp+4Fh+arg_10]
0x1800186f2  mov     [rsp+110h+var_B8], rax
0x1800186f7  lea     rax, [rbp+4Fh+var_70]
0x1800186fb  mov     [rsp+110h+var_C0], rax
0x180018700  lea     rax, [rbp+4Fh+arg_20]
0x180018704  mov     [rsp+110h+var_C8], rax
0x180018709  lea     rax, [rbp+4Fh+var_58]
0x18001870d  mov     [rsp+110h+var_D0], rax
0x180018712  lea     rax, [rbp+4Fh+var_50]
0x180018716  mov     [rsp+110h+var_D8], rax
0x18001871b  lea     rax, [rbp+4Fh+var_68]
0x18001871f  mov     [rsp+110h+var_E0], rax
0x180018724  lea     rax, [rbp+4Fh+var_80]
0x180018728  mov     [rsp+110h+var_E8], rax
0x18001872d  lea     rax, [rbp+4Fh+var_78]
0x180018731  mov     qword ptr [rsp+110h+var_F0], rax
0x180018736  lea     rdx, byte_18004CAE9
0x18001873d  mov     rcx, r8
0x180018740  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x180018745  movzx   eax, byte ptr [r14+22Fh]
0x18001874d  movzx   ecx, byte ptr [r14+22Eh]
0x180018755  movzx   edx, byte ptr [r14+22Dh]
0x18001875d  movzx   r8d, byte ptr [r14+22Ch]
0x180018765  movzx   r9d, byte ptr [r14+22Bh]
0x18001876d  movzx   r10d, byte ptr [r14+22Ah]
0x180018775  movzx   r11d, byte ptr [r14+229h]
0x18001877d  movzx   ebx, byte ptr [r14+228h]
0x180018785  movzx   edi, word ptr [r14+226h]
0x18001878d  movzx   esi, word ptr [r14+224h]
0x180018795  mov     [rsp+110h+var_98], eax
0x180018799  mov     [rsp+110h+var_A0], ecx
0x18001879d  mov     dword ptr [rsp+110h+var_A8], edx
0x1800187a1  mov     dword ptr [rsp+110h+var_B0], r8d
0x1800187a6  mov     dword ptr [rsp+110h+var_B8], r9d
0x1800187ab  mov     dword ptr [rsp+110h+var_C0], r10d
0x1800187b0  mov     dword ptr [rsp+110h+var_C8], r11d
0x1800187b5  mov     dword ptr [rsp+110h+var_D0], ebx
0x1800187b9  mov     dword ptr [rsp+110h+var_D8], edi
0x1800187bd  mov     dword ptr [rsp+110h+var_E0], esi
0x1800187c1  mov     eax, [r14+220h]
0x1800187c8  mov     dword ptr [rsp+110h+var_E8], eax
0x1800187cc  mov     dword ptr [rsp+110h+var_F0], 98Bh; unsigned int
0x1800187d4  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800187db  lea     r8, aCrdpidadapterP; "CRdpIdAdapter::ProcessIoctl"
0x1800187e2  lea     rdx, aStopProcessor0; "Stop processor {%08lX-%04hX-%04hX-%02hh"...
0x1800187e9  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800187f0  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800187f5  mov     rcx, r14; this
0x1800187f8  call    ?ProcessStopProcessor@CRdpIdAdapter@@AEAAXXZ; CRdpIdAdapter::ProcessStopProcessor(void)
0x1800187fd  jmp     loc_180019BBB
0x180018802  cmp     [r12+2Dh], sil
0x180018807  jz      loc_180019C65
0x18001880d  cmp     qword ptr [r8+8], 1Ch
0x180018812  jb      loc_180019C8D
0x180018818  add     r15, 0Ch
0x18001881c  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180018821  mov     r8, [rax+8]
0x180018825  mov     eax, [r8]
0x180018828  cmp     eax, 4
0x18001882b  jbe     loc_1800188EF
0x180018831  mov     rdx, 470000000000h
0x18001883b  mov     rcx, r8
0x18001883e  call    _tlgKeywordOn
0x180018843  test    al, al
0x180018845  jz      loc_1800188EF
0x18001884b  mov     [rbp+4Fh+arg_10], r15
0x18001884f  mov     rax, [r14+208h]
0x180018856  mov     [rbp+4Fh+var_78], rax
0x18001885a  mov     eax, [r14+204h]
0x180018861  mov     dword ptr [rbp+4Fh+arg_20], eax
0x180018864  lea     rax, aReceiveRdpiddO_5; "Receive RDPIDD_OPCODE_START_AVENC_PROCE"...
0x18001886b  mov     [rbp+4Fh+var_80], rax
0x18001886f  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180018876  mov     [rbp+4Fh+var_68], rax
0x18001887a  lea     rax, aRdpidd; "RdpIdd"
0x180018881  mov     [rbp+4Fh+var_70], rax
0x180018885  mov     qword ptr [rbp+4Fh+var_58], 1000000h
0x18001888d  lea     rax, aCheckpoint; "Checkpoint"
0x180018894  mov     [rbp+4Fh+var_50], rax
0x180018898  lea     rax, [rbp+4Fh+arg_10]
0x18001889c  mov     [rsp+110h+var_B8], rax
0x1800188a1  lea     rax, [rbp+4Fh+var_78]
0x1800188a5  mov     [rsp+110h+var_C0], rax
0x1800188aa  lea     rax, [rbp+4Fh+arg_20]
0x1800188ae  mov     [rsp+110h+var_C8], rax
0x1800188b3  lea     rax, [rbp+4Fh+var_80]
0x1800188b7  mov     [rsp+110h+var_D0], rax
0x1800188bc  lea     rax, [rbp+4Fh+var_68]
0x1800188c0  mov     [rsp+110h+var_D8], rax
0x1800188c5  lea     rax, [rbp+4Fh+var_70]
0x1800188c9  mov     [rsp+110h+var_E0], rax
0x1800188ce  lea     rax, [rbp+4Fh+var_58]
0x1800188d2  mov     [rsp+110h+var_E8], rax
0x1800188d7  lea     rax, [rbp+4Fh+var_50]
0x1800188db  mov     qword ptr [rsp+110h+var_F0], rax
0x1800188e0  lea     rdx, dword_18004CB5C
0x1800188e7  mov     rcx, r8
0x1800188ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x1800188ef  movzx   eax, byte ptr [r15+0Fh]
0x1800188f4  movzx   ecx, byte ptr [r15+0Eh]
0x1800188f9  movzx   edx, byte ptr [r15+0Dh]
0x1800188fe  movzx   r8d, byte ptr [r15+0Ch]
0x180018903  movzx   r9d, byte ptr [r15+0Bh]
0x180018908  movzx   r10d, byte ptr [r15+0Ah]
0x18001890d  movzx   r11d, byte ptr [r15+9]
0x180018912  movzx   ebx, byte ptr [r15+8]
0x180018917  movzx   edi, word ptr [r15+6]
0x18001891c  movzx   esi, word ptr [r15+4]
0x180018921  mov     [rsp+110h+var_98], eax
0x180018925  mov     [rsp+110h+var_A0], ecx
0x180018929  mov     dword ptr [rsp+110h+var_A8], edx
0x18001892d  mov     dword ptr [rsp+110h+var_B0], r8d
0x180018932  mov     dword ptr [rsp+110h+var_B8], r9d
0x180018937  mov     dword ptr [rsp+110h+var_C0], r10d
0x18001893c  mov     dword ptr [rsp+110h+var_C8], r11d
0x180018941  mov     dword ptr [rsp+110h+var_D0], ebx
0x180018945  mov     dword ptr [rsp+110h+var_D8], edi
0x180018949  mov     dword ptr [rsp+110h+var_E0], esi
0x18001894d  mov     eax, [r15]
0x180018950  mov     dword ptr [rsp+110h+var_E8], eax
0x180018954  mov     dword ptr [rsp+110h+var_F0], 968h; unsigned int
0x18001895c  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180018963  lea     r8, aCrdpidadapterP; "CRdpIdAdapter::ProcessIoctl"
0x18001896a  lea     rdx, aStartProcessor; "Start processor {%08lX-%04hX-%04hX-%02h"...
0x180018971  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180018978  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001897d  mov     rdx, r15; struct _GUID *
0x180018980  mov     rcx, r14; this
0x180018983  call    ?ProcessStartProcessor@CRdpIdAdapter@@AEAAXAEBU_GUID@@@Z; CRdpIdAdapter::ProcessStartProcessor(_GUID const &)
0x180018988  jmp     loc_180019BBB
0x18001898d  cmp     qword ptr [r8+8], 10h
0x180018992  jb      loc_180019CB5
0x180018998  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001899d  mov     r8, [rax+8]
0x1800189a1  mov     eax, [r8]
0x1800189a4  cmp     eax, 4
0x1800189a7  jbe     loc_180018A6E
0x1800189ad  mov     rdx, 470000000000h
0x1800189b7  mov     rcx, r8
0x1800189ba  call    _tlgKeywordOn
0x1800189bf  test    al, al
0x1800189c1  jz      loc_180018A6E
0x1800189c7  mov     eax, [r15+0Ch]
0x1800189cb  mov     dword ptr [rbp+4Fh+arg_20], eax
0x1800189ce  mov     rax, [r14+208h]
0x1800189d5  mov     [rbp+4Fh+var_78], rax
0x1800189d9  mov     eax, [r14+204h]
0x1800189e0  mov     dword ptr [rbp+4Fh+arg_10], eax
0x1800189e3  lea     rax, aReceiveRdpiddO_8; "Receive RDPIDD_OPCODE_SET_CURSOR_MODE"
0x1800189ea  mov     [rbp+4Fh+var_80], rax
0x1800189ee  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800189f5  mov     [rbp+4Fh+var_68], rax
0x1800189f9  lea     rax, aRdpidd; "RdpIdd"
0x180018a00  mov     [rbp+4Fh+var_70], rax
0x180018a04  mov     qword ptr [rbp+4Fh+var_58], 1000000h
0x180018a0c  lea     rax, aCheckpoint; "Checkpoint"
0x180018a13  mov     [rbp+4Fh+var_50], rax
0x180018a17  lea     rax, [rbp+4Fh+arg_20]
0x180018a1b  mov     [rsp+110h+var_B8], rax
0x180018a20  lea     rax, [rbp+4Fh+var_78]
0x180018a24  mov     [rsp+110h+var_C0], rax
0x180018a29  lea     rax, [rbp+4Fh+arg_10]
0x180018a2d  mov     [rsp+110h+var_C8], rax
0x180018a32  lea     rax, [rbp+4Fh+var_80]
0x180018a36  mov     [rsp+110h+var_D0], rax
0x180018a3b  lea     rax, [rbp+4Fh+var_68]
0x180018a3f  mov     [rsp+110h+var_D8], rax
0x180018a44  lea     rax, [rbp+4Fh+var_70]
0x180018a48  mov     [rsp+110h+var_E0], rax
0x180018a4d  lea     rax, [rbp+4Fh+var_58]
0x180018a51  mov     [rsp+110h+var_E8], rax
0x180018a56  lea     rax, [rbp+4Fh+var_50]
0x180018a5a  mov     qword ptr [rsp+110h+var_F0], rax
0x180018a5f  lea     rdx, byte_18004CCB5
0x180018a66  mov     rcx, r8
0x180018a69  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@46@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018a6e  mov     eax, [r15+0Ch]
0x180018a72  mov     dword ptr [rsp+110h+var_E8], eax
0x180018a76  mov     dword ptr [rsp+110h+var_F0], 8FAh; unsigned int
0x180018a7e  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180018a85  lea     r8, aCrdpidadapterP; "CRdpIdAdapter::ProcessIoctl"
0x180018a8c  lea     rdx, aSetcursormodeD; "SetCursorMode: %d"
0x180018a93  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180018a9a  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180018a9f  mov     rdx, r15; struct _RDPIDD_OPCODE_SET_CURSOR_MODE *
0x180018aa2  mov     rcx, r14; this
0x180018aa5  call    ?ProcessSetCursorMode@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_SET_CURSOR_MODE@@@Z; CRdpIdAdapter::ProcessSetCursorMode(_RDPIDD_OPCODE_SET_CURSOR_MODE * const)
0x180018aaa  jmp     loc_180019BBB
0x180018aaf  cmp     qword ptr [r8+8], 10h
0x180018ab4  jb      loc_180019CDD
0x180018aba  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180018abf  mov     r8, [rax+8]
0x180018ac3  mov     eax, [r8]
0x180018ac6  cmp     eax, 4
0x180018ac9  jbe     loc_180018B90
0x180018acf  mov     rdx, 470000000000h
0x180018ad9  mov     rcx, r8
0x180018adc  call    _tlgKeywordOn
0x180018ae1  test    al, al
0x180018ae3  jz      loc_180018B90
0x180018ae9  mov     eax, [r15+0Ch]
0x180018aed  mov     dword ptr [rbp+4Fh+arg_20], eax
0x180018af0  mov     rax, [r14+208h]
0x180018af7  mov     [rbp+4Fh+var_78], rax
0x180018afb  mov     eax, [r14+204h]
0x180018b02  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180018b05  lea     rax, aReceiveRdpiddO_0; "Receive RDPIDD_OPCODE_SET_MONITOR_LAYOU"...
0x180018b0c  mov     [rbp+4Fh+var_80], rax
0x180018b10  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180018b17  mov     [rbp+4Fh+var_68], rax
0x180018b1b  lea     rax, aRdpidd; "RdpIdd"
0x180018b22  mov     [rbp+4Fh+var_70], rax
0x180018b26  mov     qword ptr [rbp+4Fh+var_58], 1000000h
0x180018b2e  lea     rax, aCheckpoint; "Checkpoint"
0x180018b35  mov     [rbp+4Fh+var_50], rax
0x180018b39  lea     rax, [rbp+4Fh+arg_20]
0x180018b3d  mov     [rsp+110h+var_B8], rax
0x180018b42  lea     rax, [rbp+4Fh+var_78]
0x180018b46  mov     [rsp+110h+var_C0], rax
0x180018b4b  lea     rax, [rbp+4Fh+arg_10]
0x180018b4f  mov     [rsp+110h+var_C8], rax
0x180018b54  lea     rax, [rbp+4Fh+var_80]
0x180018b58  mov     [rsp+110h+var_D0], rax
0x180018b5d  lea     rax, [rbp+4Fh+var_68]
0x180018b61  mov     [rsp+110h+var_D8], rax
0x180018b66  lea     rax, [rbp+4Fh+var_70]
0x180018b6a  mov     [rsp+110h+var_E0], rax
0x180018b6f  lea     rax, [rbp+4Fh+var_58]
0x180018b73  mov     [rsp+110h+var_E8], rax; char *
0x180018b78  lea     rax, [rbp+4Fh+var_50]
  ... truncated ...
```
