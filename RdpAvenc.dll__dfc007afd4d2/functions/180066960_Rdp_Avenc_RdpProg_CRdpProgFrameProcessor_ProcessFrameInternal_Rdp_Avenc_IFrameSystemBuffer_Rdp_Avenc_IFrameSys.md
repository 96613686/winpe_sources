# Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(Rdp::Avenc::IFrameSystemBuffer &,bool *)

- ea: `0x180066960`
- end: `0x180067500`
- name: `??$ProcessFrameInternal@UIFrameSystemBuffer@Avenc@Rdp@@@CRdpProgFrameProcessor@RdpProg@Avenc@Rdp@@IEAAJAEAUIFrameSystemBuffer@23@PEA_N@Z`
- size: `2976`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180065bd0`

## callees

- `0x180001114`
- `0x1800032cc`
- `0x180003418`
- `0x180003544`
- `0x180003804`
- `0x1800038c4`
- `0x180006580`
- `0x18000a1b4`
- `0x18000ec04`
- `0x180026864`
- `0x180028840`
- `0x180066960`
- `0x180067508`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1800672ce`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x180067320`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x18006738d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1800673d0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x180067425`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x18006748e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1800672ce`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x180067320`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x18006738d`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1800673d0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x180067425`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x18006748e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x180067246`
- `api-ms-win-core-perfcounters-l1-1-0!PerfIncrementULongCounterValue` at `0x180067246`

## string_xrefs

- `0x1800674d8`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800674ed`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180067263`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PerfMon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(
        Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *this,
        const char *a2,
        _BYTE *a3)
{
  const char *v3; // rsi
  Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned int v7; // eax
  __int64 v8; // r14
  unsigned __int64 v9; // r15
  const struct _tlgProvider_t *v10; // rax
  int v11; // eax
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // r13d
  unsigned int v17; // ecx
  int v18; // r9d
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // r15
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  const struct _tlgProvider_t *v25; // rax
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rax
  const char *v29; // r9
  unsigned int v30; // r15d
  int v31; // eax
  int v32; // r8d
  int v33; // r9d
  unsigned __int64 v34; // r14
  __int64 v35; // rcx
  ULONG v36; // eax
  unsigned int v37; // edx
  _DWORD *v38; // rsi
  unsigned __int64 v39; // rax
  ULONG v40; // eax
  ULONG v41; // eax
  int v42; // ecx
  unsigned int v43; // r8d
  ULONG v44; // eax
  ULONG v45; // eax
  ULONG v46; // eax
  unsigned __int64 v47; // rax
  ULONG v48; // eax
  unsigned __int64 v49; // rcx
  ULONG v50; // eax
  wil *v51; // rcx
  Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *v52; // r13
  __int64 v53; // rcx
  int v54; // [rsp+20h] [rbp-198h]
  char *v55; // [rsp+28h] [rbp-190h]
  char *v56; // [rsp+28h] [rbp-190h]
  char *v57; // [rsp+28h] [rbp-190h]
  char *v58; // [rsp+28h] [rbp-190h]
  char *v59; // [rsp+28h] [rbp-190h]
  char *v60; // [rsp+28h] [rbp-190h]
  char *v61; // [rsp+28h] [rbp-190h]
  int v62; // [rsp+90h] [rbp-128h] BYREF
  unsigned int v63; // [rsp+94h] [rbp-124h] BYREF
  int v64[2]; // [rsp+98h] [rbp-120h] BYREF
  unsigned int v65; // [rsp+A0h] [rbp-118h] BYREF
  char v66[4]; // [rsp+A4h] [rbp-114h] BYREF
  const char *v67; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-100h] BYREF
  unsigned __int64 v70; // [rsp+C0h] [rbp-F8h] BYREF
  unsigned __int64 v71; // [rsp+C8h] [rbp-F0h] BYREF
  char *v72; // [rsp+D0h] [rbp-E8h]
  const char *v73; // [rsp+D8h] [rbp-E0h] BYREF
  const char *v74; // [rsp+E0h] [rbp-D8h] BYREF
  const char *v75; // [rsp+E8h] [rbp-D0h] BYREF
  const char *v76; // [rsp+F0h] [rbp-C8h] BYREF
  unsigned __int64 v77; // [rsp+F8h] [rbp-C0h] BYREF
  const char *v78; // [rsp+100h] [rbp-B8h] BYREF
  const char *v79; // [rsp+108h] [rbp-B0h] BYREF
  const char *v80; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v81; // [rsp+118h] [rbp-A0h] BYREF
  Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *v82; // [rsp+120h] [rbp-98h]
  _BYTE *v83; // [rsp+128h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v84; // [rsp+130h] [rbp-88h] BYREF
  __int128 v85; // [rsp+140h] [rbp-78h]
  int *v86; // [rsp+150h] [rbp-68h]
  __int64 v87; // [rsp+158h] [rbp-60h]
  unsigned __int64 *v88; // [rsp+160h] [rbp-58h]
  __int64 v89; // [rsp+168h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v83 = a3;
  v3 = a2;
  v4 = this;
  v82 = this;
  v79 = a2;
  v78 = a3;
  LODWORD(v5) = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      (const char *)0x80004003LL,
      v54);
    return 2147500035LL;
  }
  v63 = 0;
  v7 = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)a2 + 120LL))(a2);
  v8 = v7;
  *(_DWORD *)v66 = v7;
  v9 = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v3 + 128LL))(v3);
  v77 = v9;
  v10 = RdpGrfxPipelinePerfProvider::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    v71 = v9;
    v62 = v8;
    v88 = &v71;
    v89 = 8;
    v86 = &v62;
    v87 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)v10, (unsigned __int8 *)&dword_1800B5264, 0, 0, 4u, &v84);
  }
  v72 = (char *)v4 + 128;
  v81 = *((_QWORD *)v4 + 16) + 112LL;
  v71 = *(_QWORD *)v81;
  v80 = (const char *)v71;
  try
  {
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 40LL))(v3);
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 56LL))(v3);
    v68 = 0;
    v11 = (**(__int64 (__fastcall ***)(const char *, GUID *, __int64 *))v3)(
            v3,
            &GUID_6f1d2ec1_7a85_4103_8765_11cba40c6a1f,
            &v68);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        v54);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v68 + 248LL))(v68) )
    {
      ++*((_DWORD *)v4 + 89);
      if ( !*((_BYTE *)v4 + 365) || *((_DWORD *)v4 + 89) < 3u )
        goto LABEL_13;
    }
    else
    {
      *((_DWORD *)v4 + 89) = 0;
    }
    *((_BYTE *)v4 + 365) = 0;
LABEL_13:
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 80LL))(v3);
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 96LL))(v3);
    v12 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      v70 = v9;
      v69 = v8;
      *(_QWORD *)v64 = "Begin";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)&unk_1800B5210,
        v13,
        v14,
        (__int64)v64,
        (__int64)&v69,
        (__int64)&v70);
    }
    *((_BYTE *)v4 + 364) = 0;
    v73 = 0;
    v64[0] = 0;
    v70 = 0;
    v62 = 0;
    v69 = 0;
    v15 = (**(__int64 (__fastcall ***)(const char *, GUID *, __int64 *))v3)(
            v3,
            &GUID_5ce16a4c_4058_480b_8806_9c82986f8662,
            &v69);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v15,
        v54);
    (*(void (__fastcall **)(__int64, const char **, int *, unsigned __int64 *, int *))(*(_QWORD *)v69 + 208LL))(
      v69,
      &v73,
      v64,
      &v70,
      &v62);
    v84 = 0;
    v85 = 0;
    v86 = 0;
    v84.Ptr = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v3 + 184LL))(v3);
    v84.Size = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v3 + 152LL))(v3);
    v84.Reserved = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v3 + 160LL))(v3);
    LODWORD(v85) = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v3 + 168LL))(v3);
    *((_QWORD *)&v85 + 1) = v70;
    LODWORD(v86) = v62;
    v65 = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, struct _EVENT_DATA_DESCRIPTOR *, unsigned int *))(**((_QWORD **)v4 + 39)
                                                                                             + 16LL))(
            *((_QWORD *)v4 + 39),
            &v84,
            &v65);
    if ( v16 >= 0 )
    {
      v17 = v65;
      if ( v65 )
      {
        v18 = *((_DWORD *)v4 + 88);
        *((_DWORD *)v4 + 88) = v18 + 1;
        if ( v18 == -1 )
          *((_DWORD *)v4 + 88) = 1;
        v16 = Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::SendFrame(v4, v8, v9, v18, v17);
        if ( v16 >= 0 )
        {
          *((_DWORD *)v4 + 46) += v65;
          if ( (unsigned int)dword_1800C1058 > 4 )
          {
            v74 = (const char *)v65;
            v75 = "Size of output buffer";
            v76 = "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal";
            v63 = 383;
            v67 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              (unsigned int)&dword_1800C1058,
              (unsigned int)word_1800B51D2,
              v19,
              v20,
              (__int64)&v67,
              (__int64)&v63,
              (__int64)&v76,
              (__int64)&v75,
              (__int64)&v74);
          }
          v63 = v65;
        }
      }
    }
    if ( v69 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 104LL))(v3);
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 88LL))(v3);
    v21 = v68;
    v67 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 176LL))(v68);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 184LL))(v21);
    *((_QWORD *)v4 + 20) += v22 - (_QWORD)v67;
    ++*((_DWORD *)v4 + 39);
    *((_DWORD *)v4 + 90) = 0;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v67 = *(const char **)(*((_QWORD *)v4 + 17) + 136LL);
      v76 = (const char *)(*(_QWORD *)v72 + 120LL);
      v75 = "FrameRate";
      v74 = "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal";
      v64[0] = 404;
      v73 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800B512E,
        v23,
        v24,
        (__int64)&v73,
        (__int64)v64,
        (__int64)&v74,
        (__int64)&v75,
        (__int64)&v76,
        (__int64)&v67);
    }
    v25 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v25 > 5u )
    {
      v64[0] = *(_DWORD *)v66;
      v67 = "End";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v25,
        (unsigned int)&word_1800B517E,
        v26,
        v27,
        (__int64)&v67,
        (__int64)v64,
        (__int64)&v77);
    }
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 64LL))(v3);
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v3 + 48LL))(v3);
    v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 120LL))(v68);
    if ( !*((_QWORD *)v4 + 21) )
      *((_QWORD *)v4 + 21) = v28;
    v30 = 1;
    *((_QWORD *)v4 + 22) = v28;
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      v29);
    v62 = wil::ResultFromCaughtException(v51);
    v64[0] = 2;
    v52 = v82;
    v53 = *((_QWORD *)v82 + 16);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Frame dropped: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, FrameNumber: %d, Error: %#x",
      "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      0x1ACu,
      *(_DWORD *)(v53 + 120),
      *(unsigned __int16 *)(v53 + 124),
      *(unsigned __int16 *)(v53 + 126),
      *(unsigned __int8 *)(v53 + 128),
      *(unsigned __int8 *)(v53 + 129),
      *(unsigned __int8 *)(v53 + 130),
      *(unsigned __int8 *)(v53 + 131),
      *(unsigned __int8 *)(v53 + 132),
      *(unsigned __int8 *)(v53 + 133),
      *(unsigned __int8 *)(v53 + 134),
      *(unsigned __int8 *)(v53 + 135),
      *(_DWORD *)v66,
      v62);
    ++*((_DWORD *)v52 + 38);
    *((_DWORD *)v52 + 47) = 0;
    LODWORD(v5) = 0;
    v30 = v64[0];
    v16 = v62;
    v83 = v78;
    v4 = v82;
    v3 = v79;
    v71 = (unsigned __int64)v80;
  }
  v31 = (*(__int64 (__fastcall **)(const char *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v3 + 112LL))(v3, v30, v63, 0);
  if ( v31 < 0 && (unsigned int)dword_1800C1058 > 2 )
  {
    v64[0] = v31;
    v63 = *(_DWORD *)v66;
    v62 = *(_DWORD *)(*(_QWORD *)v81 + 160LL);
    v81 = *(_QWORD *)v72 + 120LL;
    v80 = "Failed to report frame statistics";
    v79 = "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::ProcessFrameInternal";
    *(_DWORD *)v66 = 451;
    v78 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800B50B6,
      v32,
      v33,
      (__int64)&v78,
      (__int64)v66,
      (__int64)&v79,
      (__int64)&v80,
      (__int64)&v81,
      (__int64)&v62,
      (__int64)&v63,
      (__int64)v64);
  }
  *v83 = v30 != 1;
  v34 = v71;
  v35 = *(_QWORD *)(v71 + 312);
  if ( v35 )
  {
    v36 = PerfIncrementULongCounterValue(*(HANDLE *)v35, *(PPERF_COUNTERSET_INSTANCE *)(v35 + 24), 1u, 1u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v36,
      (unsigned int)"PerfIncrementULongCounterValue failed",
      v55);
    v37 = *((_DWORD *)v4 + 46);
    v38 = (_DWORD *)((char *)v4 + 156);
    if ( v37 )
      v39 = (unsigned int)*v38
          * ((unsigned __int64)(unsigned int)(3
                                            * *(_DWORD *)(*(_QWORD *)v72 + 148LL)
                                            * *(_DWORD *)(*(_QWORD *)v72 + 152LL)) >> 1)
          / v37;
    else
      LODWORD(v39) = 0;
    v40 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            2u,
            v39);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v40,
      (unsigned int)"PerfSetULongCounterValue failed",
      v56);
    v41 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            3u,
            (int)*(double *)(*((_QWORD *)v4 + 17) + 136LL));
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v41,
      (unsigned int)"PerfSetULongCounterValue failed",
      v57);
    v42 = *((_DWORD *)v4 + 38);
    v43 = v42 + *((_DWORD *)v4 + 39);
    if ( v43 )
      v44 = v42 * (int)*(double *)(*((_QWORD *)v4 + 17) + 136LL) / v43;
    else
      v44 = 0;
    v45 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            6u,
            v44);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v45,
      (unsigned int)"PerfSetULongCounterValue failed",
      v58);
    v46 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            7u,
            *((_DWORD *)v4 + 47));
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v46,
      (unsigned int)"PerfSetULongCounterValue failed",
      v59);
    if ( *v38 )
      v47 = *((_QWORD *)v4 + 20) / (unsigned __int64)(unsigned int)*v38;
    else
      LODWORD(v47) = 0;
    v48 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            8u,
            v47);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v48,
      (unsigned int)"PerfSetULongCounterValue failed",
      v60);
    v49 = *((_QWORD *)v4 + 22) - *((_QWORD *)v4 + 21);
    if ( v49 )
      v5 = (unsigned int)(10000000 * (*((_DWORD *)v4 + 38) + *((_DWORD *)v4 + 39))) / v49;
    v50 = PerfSetULongCounterValue(
            **(HANDLE **)(v34 + 312),
            *(PPERF_COUNTERSET_INSTANCE *)(*(_QWORD *)(v34 + 312) + 24LL),
            9u,
            v5);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PerfMon.h",
      (const char *)v50,
      (unsigned int)"PerfSetULongCounterValue failed",
      v61);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180066960  push    rbx
0x180066962  push    rsi
0x180066963  push    rdi
0x180066964  push    r12
0x180066966  push    r13
0x180066968  push    r14
0x18006696a  push    r15
0x18006696c  sub     rsp, 180h
0x180066973  mov     rax, cs:__security_cookie
0x18006697a  xor     rax, rsp
0x18006697d  mov     [rsp+1B8h+var_48], rax
0x180066985  mov     rax, r8
0x180066988  mov     [rsp+1B8h+var_90], rax
0x180066990  mov     rsi, rdx
0x180066993  mov     rdi, rcx
0x180066996  mov     [rsp+1B8h+var_98], rcx
0x18006699e  mov     [rsp+1B8h+var_B0], rdx
0x1800669a6  mov     [rsp+1B8h+var_B8], rax
0x1800669ae  xor     ebx, ebx
0x1800669b0  test    r8, r8
0x1800669b3  jnz     short loc_1800669DD
0x1800669b5  mov     rcx, [rsp+1B8h]; this
0x1800669bd  mov     ebx, 80004003h
0x1800669c2  mov     r9d, ebx; char *
0x1800669c5  lea     r8, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800669cc  mov     edx, 0DBh; void *
0x1800669d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800669d6  mov     eax, ebx
0x1800669d8  jmp     loc_1800674B2
0x1800669dd  mov     [rsp+1B8h+var_124], ebx
0x1800669e4  mov     rax, [rdx]
0x1800669e7  mov     rcx, rsi
0x1800669ea  mov     rax, [rax+78h]
0x1800669ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669f3  mov     r14d, eax
0x1800669f6  mov     dword ptr [rsp+1B8h+var_114], r14d
0x1800669fe  mov     rcx, [rsi]
0x180066a01  mov     rax, [rcx+80h]
0x180066a08  mov     rcx, rsi
0x180066a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a10  mov     r15, rax
0x180066a13  mov     [rsp+1B8h+var_C0], rax
0x180066a1b  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x180066a20  mov     ecx, [rax]
0x180066a22  cmp     ecx, 5
0x180066a25  jbe     short loc_180066A99
0x180066a27  mov     [rsp+1B8h+var_F0], r15
0x180066a2f  mov     [rsp+1B8h+var_128], r14d
0x180066a37  lea     rcx, [rsp+1B8h+var_F0]
0x180066a3f  mov     [rsp+1B8h+var_58], rcx
0x180066a47  mov     [rsp+1B8h+var_50], 8
0x180066a53  lea     rcx, [rsp+1B8h+var_128]
0x180066a5b  mov     [rsp+1B8h+var_68], rcx
0x180066a63  mov     [rsp+1B8h+var_60], 4
0x180066a6f  lea     rcx, [rsp+1B8h+var_88]
0x180066a77  mov     [rsp+1B8h+var_190], rcx
0x180066a7c  mov     [rsp+1B8h+var_198], 4; int
0x180066a84  xor     r9d, r9d
0x180066a87  xor     r8d, r8d
0x180066a8a  lea     rdx, dword_1800B5264
0x180066a91  mov     rcx, rax
0x180066a94  call    _tlgWriteTransfer_EventWriteTransfer
0x180066a99  lea     rax, [rdi+80h]
0x180066aa0  mov     [rsp+1B8h+var_E8], rax
0x180066aa8  mov     rax, [rax]
0x180066aab  add     rax, 70h ; 'p'
0x180066aaf  mov     [rsp+1B8h+var_A0], rax
0x180066ab7  mov     rax, [rax]
0x180066aba  mov     [rsp+1B8h+var_F0], rax
0x180066ac2  mov     [rsp+1B8h+var_A8], rax
0x180066aca  mov     rax, [rsi]
0x180066acd  mov     rcx, rsi
0x180066ad0  mov     rax, [rax+28h]
0x180066ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ad9  mov     rax, [rsi]
0x180066adc  mov     rcx, rsi
0x180066adf  mov     rax, [rax+38h]
0x180066ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ae8  mov     [rsp+1B8h+var_108], rbx
0x180066af0  mov     rax, [rsi]
0x180066af3  lea     r8, [rsp+1B8h+var_108]
0x180066afb  lea     rdx, _GUID_6f1d2ec1_7a85_4103_8765_11cba40c6a1f
0x180066b02  mov     rcx, rsi
0x180066b05  mov     rax, [rax]
0x180066b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b0d  mov     rcx, [rsp+1B8h]; this
0x180066b15  test    eax, eax
0x180066b17  js      loc_1800674D5
0x180066b1d  mov     rcx, [rsp+1B8h+var_108]
0x180066b25  mov     rax, [rcx]
0x180066b28  mov     rax, [rax+0F8h]
0x180066b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b34  test    al, al
0x180066b36  jz      short loc_180066B51
0x180066b38  inc     dword ptr [rdi+164h]
0x180066b3e  cmp     [rdi+16Dh], bl
0x180066b44  jz      short loc_180066B5D
0x180066b46  cmp     dword ptr [rdi+164h], 3
0x180066b4d  jb      short loc_180066B5D
0x180066b4f  jmp     short loc_180066B57
0x180066b51  mov     [rdi+164h], ebx
0x180066b57  mov     [rdi+16Dh], bl
0x180066b5d  mov     rax, [rsi]
0x180066b60  mov     rcx, rsi
0x180066b63  mov     rax, [rax+50h]
0x180066b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b6c  mov     rax, [rsi]
0x180066b6f  mov     rcx, rsi
0x180066b72  mov     rax, [rax+60h]
0x180066b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b7b  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x180066b80  mov     ecx, [rax]
0x180066b82  cmp     ecx, 5
0x180066b85  jbe     short loc_180066BDC
0x180066b87  mov     [rsp+1B8h+var_F8], r15
0x180066b8f  mov     [rsp+1B8h+var_100], r14
0x180066b97  lea     rcx, aBegin; "Begin"
0x180066b9e  mov     qword ptr [rsp+1B8h+var_120], rcx
0x180066ba6  lea     rcx, [rsp+1B8h+var_F8]
0x180066bae  mov     [rsp+1B8h+var_188], rcx
0x180066bb3  lea     rcx, [rsp+1B8h+var_100]
0x180066bbb  mov     [rsp+1B8h+var_190], rcx
0x180066bc0  lea     rcx, [rsp+1B8h+var_120]
0x180066bc8  mov     qword ptr [rsp+1B8h+var_198], rcx; int
0x180066bcd  lea     rdx, unk_1800B5210
0x180066bd4  mov     rcx, rax
0x180066bd7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180066bdc  mov     [rdi+16Ch], bl
0x180066be2  mov     [rsp+1B8h+var_E0], rbx
0x180066bea  mov     [rsp+1B8h+var_120], ebx
0x180066bf1  mov     [rsp+1B8h+var_F8], rbx
0x180066bf9  mov     [rsp+1B8h+var_128], ebx
0x180066c00  mov     [rsp+1B8h+var_100], rbx
0x180066c08  mov     rax, [rsi]
0x180066c0b  lea     r8, [rsp+1B8h+var_100]
0x180066c13  lea     rdx, _GUID_5ce16a4c_4058_480b_8806_9c82986f8662
0x180066c1a  mov     rcx, rsi
0x180066c1d  mov     rax, [rax]
0x180066c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c25  mov     rcx, [rsp+1B8h]; this
0x180066c2d  test    eax, eax
0x180066c2f  js      loc_1800674EA
0x180066c35  mov     rcx, [rsp+1B8h+var_100]
0x180066c3d  mov     rax, [rcx]
0x180066c40  lea     rdx, [rsp+1B8h+var_128]
0x180066c48  mov     qword ptr [rsp+1B8h+var_198], rdx
0x180066c4d  lea     r9, [rsp+1B8h+var_F8]
0x180066c55  lea     r8, [rsp+1B8h+var_120]
0x180066c5d  lea     rdx, [rsp+1B8h+var_E0]
0x180066c65  mov     rax, [rax+0D0h]
0x180066c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c71  xorps   xmm0, xmm0
0x180066c74  xor     eax, eax
0x180066c76  movups  [rsp+1B8h+var_88], xmm0
0x180066c7e  movups  [rsp+1B8h+var_78], xmm0
0x180066c86  mov     [rsp+1B8h+var_68], rax
0x180066c8e  mov     rax, [rsi]
0x180066c91  mov     rcx, rsi
0x180066c94  mov     rax, [rax+0B8h]
0x180066c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ca0  mov     qword ptr [rsp+1B8h+var_88], rax
0x180066ca8  mov     rax, [rsi]
0x180066cab  mov     rcx, rsi
0x180066cae  mov     rax, [rax+98h]
0x180066cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cba  mov     dword ptr [rsp+1B8h+var_88+8], eax
0x180066cc1  mov     rax, [rsi]
0x180066cc4  mov     rcx, rsi
0x180066cc7  mov     rax, [rax+0A0h]
0x180066cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cd3  mov     dword ptr [rsp+1B8h+var_88+0Ch], eax
0x180066cda  mov     rax, [rsi]
0x180066cdd  mov     rcx, rsi
0x180066ce0  mov     rax, [rax+0A8h]
0x180066ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cec  mov     dword ptr [rsp+1B8h+var_78], eax
0x180066cf3  mov     rax, [rsp+1B8h+var_F8]
0x180066cfb  mov     qword ptr [rsp+1B8h+var_78+8], rax
0x180066d03  mov     eax, [rsp+1B8h+var_128]
0x180066d0a  mov     dword ptr [rsp+1B8h+var_68], eax
0x180066d11  mov     [rsp+1B8h+var_118], ebx
0x180066d18  mov     rcx, [rdi+138h]
0x180066d1f  mov     rax, [rcx]
0x180066d22  lea     r8, [rsp+1B8h+var_118]
0x180066d2a  lea     rdx, [rsp+1B8h+var_88]
0x180066d32  mov     rax, [rax+10h]
0x180066d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d3b  mov     r13d, eax
0x180066d3e  test    eax, eax
0x180066d40  js      loc_180066E68
0x180066d46  mov     ecx, [rsp+1B8h+var_118]
0x180066d4d  test    ecx, ecx
0x180066d4f  jz      loc_180066E68
0x180066d55  mov     r9d, [rdi+160h]; unsigned int
0x180066d5c  lea     eax, [r9+1]
0x180066d60  mov     [rdi+160h], eax
0x180066d66  test    eax, eax
0x180066d68  jnz     short loc_180066D74
0x180066d6a  mov     dword ptr [rdi+160h], 1
0x180066d74  mov     [rsp+1B8h+var_198], ecx; unsigned int
0x180066d78  mov     r8, r15; unsigned __int64
0x180066d7b  mov     edx, r14d; unsigned int
0x180066d7e  mov     rcx, rdi; this
0x180066d81  call    ?SendFrame@CRdpProgFrameProcessor@RdpProg@Avenc@Rdp@@IEAAJI_KII@Z; Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::SendFrame(uint,unsigned __int64,uint,uint)
0x180066d86  mov     r13d, eax
0x180066d89  test    eax, eax
0x180066d8b  js      loc_180066E68
0x180066d91  mov     eax, [rsp+1B8h+var_118]
0x180066d98  add     [rdi+0B8h], eax
0x180066d9e  mov     eax, cs:dword_1800C1058
0x180066da4  cmp     eax, 4
0x180066da7  jbe     loc_180066E4A
0x180066dad  mov     eax, [rsp+1B8h+var_118]
0x180066db4  mov     [rsp+1B8h+var_D8], rax
0x180066dbc  lea     rax, aSizeOfOutputBu; "Size of output buffer"
0x180066dc3  mov     [rsp+1B8h+var_D0], rax
0x180066dcb  lea     r12, aRdpAvencRdppro_9; "Rdp::Avenc::RdpProg::CRdpProgFrameProce"...
0x180066dd2  mov     [rsp+1B8h+var_C8], r12
0x180066dda  mov     [rsp+1B8h+var_124], 17Fh
0x180066de5  lea     r14, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180066dec  mov     [rsp+1B8h+var_110], r14
0x180066df4  lea     rax, [rsp+1B8h+var_D8]
0x180066dfc  mov     [rsp+1B8h+var_178], rax
0x180066e01  lea     rax, [rsp+1B8h+var_D0]
0x180066e09  mov     [rsp+1B8h+var_180], rax
0x180066e0e  lea     rax, [rsp+1B8h+var_C8]
0x180066e16  mov     [rsp+1B8h+var_188], rax
0x180066e1b  lea     rax, [rsp+1B8h+var_124]
0x180066e23  mov     [rsp+1B8h+var_190], rax
0x180066e28  lea     rax, [rsp+1B8h+var_110]
0x180066e30  mov     qword ptr [rsp+1B8h+var_198], rax
0x180066e35  lea     rdx, word_1800B51D2
0x180066e3c  lea     rcx, dword_1800C1058
0x180066e43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180066e48  jmp     short loc_180066E58
0x180066e4a  lea     r14, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180066e51  lea     r12, aRdpAvencRdppro_9; "Rdp::Avenc::RdpProg::CRdpProgFrameProce"...
0x180066e58  mov     eax, [rsp+1B8h+var_118]
0x180066e5f  mov     [rsp+1B8h+var_124], eax
0x180066e66  jmp     short loc_180066E76
0x180066e68  lea     r14, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180066e6f  lea     r12, aRdpAvencRdppro_9; "Rdp::Avenc::RdpProg::CRdpProgFrameProce"...
0x180066e76  mov     rcx, [rsp+1B8h+var_100]
0x180066e7e  test    rcx, rcx
0x180066e81  jz      short loc_180066E90
0x180066e83  mov     rax, [rcx]
0x180066e86  mov     rax, [rax+10h]
0x180066e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e8f  nop
0x180066e90  mov     rax, [rsi]
0x180066e93  mov     rcx, rsi
0x180066e96  mov     rax, [rax+68h]
0x180066e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e9f  mov     rax, [rsi]
0x180066ea2  mov     rcx, rsi
0x180066ea5  mov     rax, [rax+58h]
0x180066ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066eae  mov     r15, [rsp+1B8h+var_108]
0x180066eb6  mov     rax, [r15]
0x180066eb9  mov     rcx, r15
0x180066ebc  mov     rax, [rax+0B0h]
0x180066ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ec8  mov     [rsp+1B8h+var_110], rax
0x180066ed0  mov     rcx, [r15]
0x180066ed3  mov     rax, [rcx+0B8h]
0x180066eda  mov     rcx, r15
0x180066edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ee2  sub     rax, [rsp+1B8h+var_110]
0x180066eea  add     [rdi+0A0h], rax
0x180066ef1  inc     dword ptr [rdi+9Ch]
0x180066ef7  mov     [rdi+168h], ebx
0x180066efd  mov     eax, cs:dword_1800C1058
0x180066f03  cmp     eax, 5
0x180066f06  jbe     loc_180066FC6
0x180066f0c  mov     rax, [rdi+88h]
0x180066f13  movsd   xmm0, qword ptr [rax+88h]
0x180066f1b  movsd   [rsp+1B8h+var_110], xmm0
0x180066f24  mov     rax, [rsp+1B8h+var_E8]
0x180066f2c  mov     rax, [rax]
0x180066f2f  add     rax, 78h ; 'x'
0x180066f33  mov     [rsp+1B8h+var_C8], rax
0x180066f3b  lea     rax, aFramerate; "FrameRate"
0x180066f42  mov     [rsp+1B8h+var_D0], rax
0x180066f4a  mov     [rsp+1B8h+var_D8], r12
0x180066f52  mov     [rsp+1B8h+var_120], 194h
0x180066f5d  mov     [rsp+1B8h+var_E0], r14
0x180066f65  lea     rax, [rsp+1B8h+var_110]
0x180066f6d  mov     [rsp+1B8h+var_170], rax
0x180066f72  lea     rax, [rsp+1B8h+var_C8]
0x180066f7a  mov     [rsp+1B8h+var_178], rax
0x180066f7f  lea     rax, [rsp+1B8h+var_D0]
0x180066f87  mov     [rsp+1B8h+var_180], rax
0x180066f8c  lea     rax, [rsp+1B8h+var_D8]
0x180066f94  mov     [rsp+1B8h+var_188], rax
0x180066f99  lea     rax, [rsp+1B8h+var_120]
0x180066fa1  mov     [rsp+1B8h+var_190], rax
0x180066fa6  lea     rax, [rsp+1B8h+var_E0]
0x180066fae  mov     qword ptr [rsp+1B8h+var_198], rax
0x180066fb3  lea     rdx, word_1800B512E
0x180066fba  lea     rcx, dword_1800C1058
  ... truncated ...
```
