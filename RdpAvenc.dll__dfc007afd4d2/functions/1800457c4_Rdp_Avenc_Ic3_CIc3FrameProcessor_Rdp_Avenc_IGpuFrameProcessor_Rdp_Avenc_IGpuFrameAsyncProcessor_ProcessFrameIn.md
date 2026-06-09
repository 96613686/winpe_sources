# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameBuffer1>(Rdp::Avenc::IFrameBuffer1 *)

- ea: `0x1800457c4`
- end: `0x18004693c`
- name: `??$ProcessFrameInternal@UIFrameBuffer1@Avenc@Rdp@@@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJPEAUIFrameBuffer1@23@@Z`
- size: `4472`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180044730`

## callees

- `0x180001f30`
- `0x180004660`
- `0x18000490c`
- `0x180004a44`
- `0x180004cd4`
- `0x180004e20`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800203d4`
- `0x1800455f0`
- `0x1800457c4`
- `0x180047df4`
- `0x180048f2c`
- `0x180049498`
- `0x18004f6f4`
- `0x180054820`
- `0x18005842c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004600d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004600d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180045c99`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800462eb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180045c99`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800462eb`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180045ccf`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180046321`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180045ccf`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180046321`

## string_xrefs

- `0x180046929`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800459dd`: `Failed to get moves and dirties`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameBuffer1>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  __int64 v5; // r12
  int v6; // r14d
  int v7; // r15d
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // r14d
  __int64 v11; // rbx
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r15
  const char *v15; // r15
  __int64 v16; // r14
  int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rax
  int v20; // r8d
  struct Rdp::Avenc::Ic3::CDsStreamSample *v21; // rbx
  __int64 v22; // rcx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // r14
  char *v26; // rcx
  __int64 v27; // rcx
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v28; // r14
  char *v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r9d
  int v33; // r8d
  int v34; // r9d
  bool v35; // r15
  __int64 v36; // rax
  __int64 v37; // r8
  char *v38; // rcx
  __int64 v39; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v41; // rcx
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v42; // r14
  __int64 v43; // rbx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, const char **); // rax
  int v45; // eax
  void (__fastcall ***v46)(_QWORD); // rax
  int v47; // r8d
  _QWORD *v48; // rbx
  __int64 v49; // r14
  __int64 v50; // r14
  __int64 v51; // rax
  int v52; // r8d
  int v53; // r9d
  int v54; // r8d
  int v55; // r9d
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // rax
  __int64 v59; // r8
  int v60; // esi
  int v61; // r8d
  int v62; // r9d
  wil *v64; // rcx
  int v65; // r13d
  int v66; // eax
  __int64 v67; // rcx
  int v68; // [rsp+20h] [rbp-138h]
  char *v69; // [rsp+28h] [rbp-130h]
  char *v70; // [rsp+28h] [rbp-130h]
  char *v71; // [rsp+28h] [rbp-130h]
  const char *v72; // [rsp+90h] [rbp-C8h] BYREF
  const char *v73; // [rsp+98h] [rbp-C0h] BYREF
  const char *v74; // [rsp+A0h] [rbp-B8h] BYREF
  int v75; // [rsp+A8h] [rbp-B0h]
  int v76; // [rsp+ACh] [rbp-ACh]
  const char *v77; // [rsp+B0h] [rbp-A8h] BYREF
  const char *v78; // [rsp+B8h] [rbp-A0h] BYREF
  const char *v79; // [rsp+C0h] [rbp-98h] BYREF
  struct IVirtualVideoSink *Sink; // [rsp+C8h] [rbp-90h] BYREF
  const char *v81; // [rsp+D0h] [rbp-88h] BYREF
  const char *v82; // [rsp+D8h] [rbp-80h] BYREF
  int v83; // [rsp+E0h] [rbp-78h] BYREF
  const char *v84; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-68h] BYREF
  __int64 *v86; // [rsp+F8h] [rbp-60h]
  Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *v87; // [rsp+100h] [rbp-58h]
  __int64 v88; // [rsp+108h] [rbp-50h]
  char v89; // [rsp+110h] [rbp-48h]
  __int64 v90; // [rsp+118h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  __int64 v92; // [rsp+160h] [rbp+8h] BYREF
  __int64 v93; // [rsp+168h] [rbp+10h]
  __int64 v94; // [rsp+170h] [rbp+18h] BYREF
  int v95; // [rsp+178h] [rbp+20h] BYREF

  v93 = a2;
  v92 = a1;
  v2 = a2;
  LODWORD(v94) = 0;
  v4 = a1 + 176;
  v86 = (__int64 *)(a1 + 176);
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL);
  v85 = v5;
  v90 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  try
  {
    v6 = *(_DWORD *)(v5 + 136);
    v75 = v6;
    v7 = *(_DWORD *)(*(_QWORD *)v4 + 128LL);
    v76 = v7;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v79 = (const char *)(*(_QWORD *)v4 + 112LL);
      v73 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LODWORD(v94) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 192LL))(v2);
      v95 = v6;
      LODWORD(v81) = v7;
      v74 = "NewFrame";
      v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncP"
            "rocessor>::ProcessFrameInternal";
      LODWORD(Sink) = 810;
      v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&unk_1800B20C8,
        v8,
        v9,
        (__int64)&v72,
        (__int64)&Sink,
        (__int64)&v77,
        (__int64)&v74,
        (__int64)&v81,
        (__int64)&v95,
        (__int64)&v94,
        (__int64)&v73,
        (__int64)&v79);
    }
    v83 = 0;
    v84 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const char **, int *))(*(_QWORD *)v2 + 208LL))(
            v2,
            0,
            0,
            &v84,
            &v83);
    v95 = v10;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x33D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)v10,
      (int)"Failed to get moves and dirties",
      v69);
    v11 = a1 + 256;
    v88 = a1 + 256;
    v89 = 0;
    if ( (unsigned int)mtx_do_lock(a1 + 256) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 332) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 332) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v89 = 1;
    if ( *(_QWORD *)(a1 + 208) )
    {
      v13 = *(_QWORD *)(a1 + 232);
      if ( v13 && (v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13)) != 0 )
        v15 = (const char *)(v14
                           - anonymous_namespace_::GetTimePassedSinceAcquisition_Rdp::Avenc::IFrameSystemBuffer1_(v2));
      else
        v15 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      v72 = (const char *)operator new(0xA8u);
      v82 = v72;
      if ( *(_BYTE *)(*v86 + 288) )
        v16 = 0;
      else
        v16 = *v86;
      v17 = *(_DWORD *)(*v86 + 128);
      v79 = (const char *)v2;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      LODWORD(v94) = 1;
      v19 = Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample((__int64)v72, &v79, v17, v18, a1 + 448, v16, (__int64)v15);
      v21 = (struct Rdp::Avenc::Ic3::CDsStreamSample *)v19;
      v82 = (const char *)v19;
      if ( v19 )
      {
        v22 = v19 + *(int *)(*(_QWORD *)(v19 + 8) + 4LL) + 8LL;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      }
      if ( v79 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v79 + 16LL))(v79);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v72 = v15;
        v77 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v79 = "Match";
        v73 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v94) = 857;
        v74 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B205F,
          v23,
          v24,
          (__int64)&v74,
          (__int64)&v94,
          (__int64)&v73,
          (__int64)&v79,
          (__int64)&v77,
          (__int64)&v72);
      }
      if ( *(_BYTE *)(v5 + 288) )
      {
        v25 = *(_QWORD *)(a1 + 240);
        *(_QWORD *)(a1 + 240) = v21;
        if ( v21 )
        {
          v26 = (char *)v21 + *(int *)(*((_QWORD *)v21 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 8LL))(v26);
        }
        if ( v25 )
        {
          v27 = v25 + *(int *)(*(_QWORD *)(v25 + 8) + 4LL) + 8LL;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v94 = 0;
        GetSystemTimePreciseAsFileTime(&v94);
        *(_QWORD *)(a1 + 424) = ((unsigned __int64)HIDWORD(v94) << 32) - 116444736000000000LL + (unsigned int)v94;
        WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 344));
      }
      v28 = *(Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession **)(*(_QWORD *)(a1 + 208) + 280LL);
      v87 = v28;
      if ( v28 )
      {
        v29 = (char *)v28 + *(int *)(*((_QWORD *)v28 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 8LL))(v29);
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        LOBYTE(v94) = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                        a1,
                        v30,
                        v15);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          v95 = v75;
          LODWORD(Sink) = v76;
          v77 = "Start";
          v79 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v81) = 877;
          v73 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800B1FF3,
            v31,
            v32,
            (__int64)&v73,
            (__int64)&v81,
            (__int64)&v79,
            (__int64)&v77,
            (__int64)&Sink,
            (__int64)&v95,
            (__int64)&v72);
        }
        v95 = Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(v28, v21);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x370,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          (const char *)(unsigned int)v95,
          (int)"ProcessFrame failed",
          v70);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          LODWORD(Sink) = v95 == 0;
          v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          LODWORD(v81) = v75;
          LODWORD(v74) = v76;
          v77 = "End";
          v79 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v73) = 889;
          v78 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&byte_1800B1F27,
            v33,
            v34,
            (__int64)&v78,
            (__int64)&v73,
            (__int64)&v79,
            (__int64)&v77,
            (__int64)&v74,
            (__int64)&v81,
            (__int64)&v72,
            (__int64)&Sink);
        }
        if ( (_BYTE)v94 )
        {
          v35 = v95 >= 0;
          v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
          LOBYTE(v37) = v35;
          Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
            a1,
            v36,
            v37);
        }
      }
      else if ( !*(_BYTE *)(a1 + 200) )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          LODWORD(v94) = v75;
          LODWORD(v73) = v76;
          v78 = "Stream processing session stopped";
          v72 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAs"
                "yncProcessor>::ProcessFrameInternal";
          LODWORD(v74) = 905;
          v77 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&word_1800B1F9E,
            v20,
            (_DWORD)v12,
            (__int64)&v77,
            (__int64)&v74,
            (__int64)&v72,
            (__int64)&v78,
            (__int64)&v73,
            (__int64)&v94);
        }
        *(_BYTE *)(a1 + 200) = 1;
      }
      if ( v28 )
      {
        v38 = (char *)v28 + *(int *)(*((_QWORD *)v28 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v38 + 16LL))(v38);
      }
      if ( v21 )
      {
        v39 = (__int64)v21 + *(int *)(*((_QWORD *)v21 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v10 = v95;
LABEL_39:
      v11 = v88;
      goto LABEL_40;
    }
    v41 = *(Rdp::Avenc::Ic3::CVideoSourceProvider **)(a1 + 216);
    if ( !v41 )
    {
LABEL_40:
      if ( (*(_DWORD *)(v11 + 76))-- == 1 )
      {
        *(_DWORD *)(v11 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 16));
      }
      goto LABEL_90;
    }
    Sink = Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(v41);
    v42 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)operator new(0xD0u);
    v87 = v42;
    v78 = (const char *)anonymous_namespace_::GetTimePassedSinceAcquisition_Rdp::Avenc::IFrameSystemBuffer1_(v2);
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 176) + 288LL) )
      v43 = 0;
    else
      v43 = *(_QWORD *)(a1 + 176);
    LODWORD(v73) = *(_DWORD *)(*(_QWORD *)(a1 + 176) + 128LL);
    v74 = (const char *)v2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    LODWORD(v94) = 2;
    v44 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 216LL))(v2);
    v79 = 0;
    v45 = (**v44)(v44, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v79);
    if ( v45 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v45,
        v68);
    LODWORD(v94) = 14;
    v46 = (void (__fastcall ***)(_QWORD))Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(
                                           (__int64)v42,
                                           (__int64 *)&v79,
                                           a1 + 448,
                                           &v74,
                                           v68,
                                           SLODWORD(FLOAT_60_0),
                                           (unsigned int)v73,
                                           v43,
                                           (__int64)v78);
    v48 = v46;
    v87 = (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)v46;
    if ( v46 )
      (**v46)(v46);
    LODWORD(v94) = 10;
    if ( v79 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v79 + 16LL))(v79);
    if ( v74 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( *(_BYTE *)(v5 + 288) )
    {
      v49 = *(_QWORD *)(a1 + 248);
      *(_QWORD *)(a1 + 248) = v48;
      if ( v48 )
        (*(void (__fastcall **)(_QWORD *))*v48)(v48);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
      v94 = 0;
      GetSystemTimePreciseAsFileTime(&v94);
      *(_QWORD *)(a1 + 424) = ((unsigned __int64)HIDWORD(v94) << 32) - 116444736000000000LL + (unsigned int)v94;
      WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 344));
    }
    if ( Sink )
    {
      v48[24] = (*(__int64 (__fastcall **)(struct IVirtualVideoSink *))(*(_QWORD *)Sink + 16LL))(Sink) - v48[25];
      v50 = (*(__int64 (__fastcall **)(_QWORD *))(*v48 + 64LL))(v48);
      v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LOBYTE(v94) = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                      a1,
                      v51,
                      v50);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v78 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v95 = v75;
        LODWORD(v73) = v76;
        v72 = "Start";
        v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v74) = 950;
        v81 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800B1E54,
          v52,
          v53,
          (__int64)&v81,
          (__int64)&v74,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&v73,
          (__int64)&v95,
          (__int64)&v78);
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v78 = (const char *)(*(__int64 (__fastcall **)(_QWORD *))(*v48 + 64LL))(v48);
        v72 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        v77 = "Match";
        v73 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        v95 = 957;
        v74 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&word_1800B1EBE,
          v54,
          v55,
          (__int64)&v74,
          (__int64)&v95,
          (__int64)&v73,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&v78);
      }
      v10 = (*(__int64 (__fastcall **)(struct IVirtualVideoSink *, _QWORD *))(*(_QWORD *)Sink + 128LL))(Sink, v48);
      v95 = v10;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x3C1,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        (const char *)v10,
        (int)"DeliverFrame failed",
        v71);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v73) = v10 == 0;
        v78 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
        LODWORD(v74) = v75;
        LODWORD(Sink) = v76;
        v72 = "End";
        v77 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v81) = 970;
        v82 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B1DDF,
          v56,
          v57,
          (__int64)&v82,
          (__int64)&v81,
          (__int64)&v77,
          (__int64)&v72,
          (__int64)&Sink,
          (__int64)&v74,
          (__int64)&v78,
          (__int64)&v73);
      }
      if ( !(_BYTE)v94 )
        goto LABEL_78;
      v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
      LOBYTE(v59) = (v10 & 0x80000000) == 0;
      Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
        a1,
        v58,
        v59);
    }
    else if ( !*(_BYTE *)(a1 + 200) )
    {
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v94) = v75;
        LODWORD(v73) = v76;
        v82 = "Lost virtual video sink";
        v78 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::ProcessFrameInternal";
        LODWORD(v74) = 986;
        v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)qword_1800B1D88,
          v47,
          (_DWORD)v12,
          (__int64)&v72,
          (__int64)&v74,
          (__int64)&v78,
          (__int64)&v82,
          (__int64)&v73,
          (__int64)&v94);
      }
      *(_BYTE *)(a1 + 200) = 1;
    }
    v10 = v95;
LABEL_78:
    if ( v48 )
      (*(void (__fastcall **)(_QWORD *))(*v48 + 8LL))(v48);
    goto LABEL_39;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      v12);
    v65 = wil::ResultFromCaughtException(v64);
    LODWORD(v94) = v65;
    v66 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v93 + 192LL))(v93);
    v67 = *(_QWORD *)(v92 + 176);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Frame dropped: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, FrameNumber: %d, Error: %#x",
      "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcess"
      "or>::ProcessFrameInternal",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      0x3EDu,
      *(_DWORD *)(v67 + 112),
      *(unsigned __int16 *)(v67 + 116),
      *(unsigned __int16 *)(v67 + 118),
      *(unsigned __int8 *)(v67 + 120),
      *(unsigned __int8 *)(v67 + 121),
      *(unsigned __int8 *)(v67 + 122),
      *(unsigned __int8 *)(v67 + 123),
      *(unsigned __int8 *)(v67 + 124),
      *(unsigned __int8 *)(v67 + 125),
      *(unsigned __int8 *)(v67 + 126),
      *(unsigned __int8 *)(v67 + 127),
      v66,
      v65);
    Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CompleteFrame<Rdp::Avenc::IFrameBuffer1>(
      v92,
      v93);
    v2 = v93;
    v10 = v94;
    v5 = v85;
  }
LABEL_90:
  v60 = v75;
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v85 = *v86 + 112;
    v82 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
    LODWORD(v92) = v60;
    LODWORD(v94) = v76;
    v78 = "Finished";
    v84 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncPro"
          "cessor>::ProcessFrameInternal";
    v95 = 1016;
    v72 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B1C81,
      v61,
      v62,
      (__int64)&v72,
      (__int64)&v95,
      (__int64)&v84,
      (__int64)&v78,
      (__int64)&v94,
      (__int64)&v92,
      (__int64)&v82,
      (__int64)&v85);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v10;
}

```

## disassembly

```asm
0x1800457c4  mov     r11, rsp
0x1800457c7  mov     [r11+10h], rdx
0x1800457cb  mov     [r11+8], rcx
0x1800457cf  push    rbx
0x1800457d0  push    rsi
0x1800457d1  push    rdi
0x1800457d2  push    r12
0x1800457d4  push    r13
0x1800457d6  push    r14
0x1800457d8  push    r15
0x1800457da  sub     rsp, 120h
0x1800457e1  mov     rdi, rdx
0x1800457e4  mov     rsi, rcx
0x1800457e7  mov     dword ptr [r11+18h], 0
0x1800457ef  lea     rbx, [rcx+0B0h]
0x1800457f6  mov     [rsp+158h+var_60], rbx
0x1800457fe  mov     rax, [rbx]
0x180045801  mov     r12, [rax+68h]
0x180045805  mov     [rsp+158h+var_68], r12
0x18004580d  mov     [r11-40h], r12
0x180045811  test    r12, r12
0x180045814  jz      short loc_180045827
0x180045816  mov     rax, [r12]
0x18004581a  mov     rcx, r12
0x18004581d  mov     rax, [rax+8]
0x180045821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045826  nop
0x180045827  mov     r14d, [r12+88h]
0x18004582f  mov     [rsp+158h+var_B0], r14d
0x180045837  mov     rax, [rbx]
0x18004583a  mov     r15d, [rax+80h]
0x180045841  mov     [rsp+158h+var_AC], r15d
0x180045849  mov     eax, cs:dword_1800C1058
0x18004584f  mov     r13d, 5
0x180045855  cmp     eax, r13d
0x180045858  jbe     loc_180045972
0x18004585e  mov     rax, [rbx]
0x180045861  add     rax, 70h ; 'p'
0x180045865  mov     [rsp+158h+var_98], rax
0x18004586d  mov     rax, [rdi]
0x180045870  mov     rcx, rdi
0x180045873  mov     rax, [rax+0C8h]
0x18004587a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004587f  mov     [rsp+158h+var_C0], rax
0x180045887  mov     rax, [rdi]
0x18004588a  mov     rcx, rdi
0x18004588d  mov     rax, [rax+0C0h]
0x180045894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045899  mov     dword ptr [rsp+158h+arg_10], eax
0x1800458a0  mov     [rsp+158h+arg_18], r14d
0x1800458a8  mov     dword ptr [rsp+158h+var_88], r15d
0x1800458b0  lea     rax, aNewframe; "NewFrame"
0x1800458b7  mov     [rsp+158h+var_B8], rax
0x1800458bf  lea     rbx, aRdpAvencIc3Cic_5; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x1800458c6  mov     [rsp+158h+var_A8], rbx
0x1800458ce  mov     dword ptr [rsp+158h+var_90], 32Ah
0x1800458d9  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800458e0  mov     [rsp+158h+var_C8], r15
0x1800458e8  lea     rax, [rsp+158h+var_98]
0x1800458f0  mov     [rsp+158h+var_F8], rax
0x1800458f5  lea     rax, [rsp+158h+var_C0]
0x1800458fd  mov     [rsp+158h+var_100], rax
0x180045902  lea     rax, [rsp+158h+arg_10]
0x18004590a  mov     [rsp+158h+var_108], rax
0x18004590f  lea     rax, [rsp+158h+arg_18]
0x180045917  mov     [rsp+158h+var_110], rax
0x18004591c  lea     rax, [rsp+158h+var_88]
0x180045924  mov     [rsp+158h+var_118], rax
0x180045929  lea     rax, [rsp+158h+var_B8]
0x180045931  mov     [rsp+158h+var_120], rax
0x180045936  lea     rax, [rsp+158h+var_A8]
0x18004593e  mov     [rsp+158h+var_128], rax
0x180045943  lea     rax, [rsp+158h+var_90]
0x18004594b  mov     [rsp+158h+var_130], rax
0x180045950  lea     rax, [rsp+158h+var_C8]
0x180045958  mov     qword ptr [rsp+158h+var_138], rax
0x18004595d  lea     rdx, unk_1800B20C8
0x180045964  lea     rcx, dword_1800C1058
0x18004596b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x180045970  jmp     short loc_180045979
0x180045972  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180045979  mov     [rsp+158h+var_78], 0
0x180045984  mov     [rsp+158h+var_70], 0
0x180045990  mov     rax, [rdi]
0x180045993  mov     rcx, rdi
0x180045996  mov     rax, [rax+28h]
0x18004599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004599f  mov     rax, [rdi]
0x1800459a2  lea     rcx, [rsp+158h+var_78]
0x1800459aa  mov     qword ptr [rsp+158h+var_138], rcx
0x1800459af  lea     r9, [rsp+158h+var_70]
0x1800459b7  xor     r8d, r8d
0x1800459ba  xor     edx, edx
0x1800459bc  mov     rcx, rdi
0x1800459bf  mov     rax, [rax+0D0h]
0x1800459c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459cb  mov     r14d, eax
0x1800459ce  mov     [rsp+158h+arg_18], eax
0x1800459d5  mov     rcx, [rsp+158h]; this
0x1800459dd  lea     rax, aFailedToGetMov; "Failed to get moves and dirties"
0x1800459e4  mov     qword ptr [rsp+158h+var_138], rax; int
0x1800459e9  mov     r9d, r14d; char *
0x1800459ec  mov     r8, r15; unsigned int
0x1800459ef  mov     edx, 33Dh; void *
0x1800459f4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800459f9  lea     rbx, [rsi+100h]
0x180045a00  mov     [rsp+158h+var_50], rbx
0x180045a08  mov     [rsp+158h+var_48], 0
0x180045a10  mov     rcx, rbx
0x180045a13  call    mtx_do_lock
0x180045a18  test    eax, eax
0x180045a1a  jnz     loc_18004690E
0x180045a20  mov     eax, [rbx+4Ch]
0x180045a23  cmp     eax, 7FFFFFFFh
0x180045a28  jz      loc_180046916
0x180045a2e  mov     [rsp+158h+var_48], 1
0x180045a36  cmp     qword ptr [rsi+0D0h], 0
0x180045a3e  jz      loc_1800460FB
0x180045a44  mov     rcx, [rsi+0E8h]
0x180045a4b  test    rcx, rcx
0x180045a4e  jz      short loc_180045A71
0x180045a50  mov     rax, [rcx]
0x180045a53  mov     rax, [rax+18h]
0x180045a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a5c  mov     r15, rax
0x180045a5f  test    rax, rax
0x180045a62  jz      short loc_180045A71
0x180045a64  mov     rcx, rdi
0x180045a67  call    _anonymous_namespace___GetTimePassedSinceAcquisition_Rdp__Avenc__IFrameSystemBuffer1_
0x180045a6c  sub     r15, rax
0x180045a6f  jmp     short loc_180045A86
0x180045a71  mov     rax, [rdi]
0x180045a74  mov     rcx, rdi
0x180045a77  mov     rax, [rax+0C8h]
0x180045a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a83  mov     r15, rax
0x180045a86  mov     ecx, 0A8h; Size
0x180045a8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045a90  mov     [rsp+158h+var_C8], rax
0x180045a98  mov     [rsp+158h+var_80], rax
0x180045aa0  mov     rax, [rsp+158h+var_60]
0x180045aa8  mov     rcx, [rax]
0x180045aab  mov     dl, [rcx+120h]
0x180045ab1  nop
0x180045ab2  test    dl, dl
0x180045ab4  jz      short loc_180045ABB
0x180045ab6  xor     r14d, r14d
0x180045ab9  jmp     short loc_180045ABE
0x180045abb  mov     r14, [rax]
0x180045abe  mov     rax, [rax]
0x180045ac1  mov     ebx, [rax+80h]
0x180045ac7  mov     [rsp+158h+var_98], rdi
0x180045acf  mov     rax, [rdi]
0x180045ad2  mov     rcx, rdi
0x180045ad5  mov     rax, [rax+8]
0x180045ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ade  nop
0x180045adf  mov     dword ptr [rsp+158h+arg_10], 1
0x180045aea  lea     rax, [rsi+1C0h]
0x180045af1  mov     [rsp+158h+var_128], r15
0x180045af6  mov     [rsp+158h+var_130], r14
0x180045afb  mov     qword ptr [rsp+158h+var_138], rax
0x180045b00  mov     r8d, ebx
0x180045b03  lea     rdx, [rsp+158h+var_98]
0x180045b0b  mov     rcx, [rsp+158h+var_C8]
0x180045b13  call    ??0CDsStreamSample@Ic3@Avenc@Rdp@@QEAA@AEBV?$com_ptr_t@UIFrameBuffer1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@IIAEBV?$com_ptr_t@UIFrameAsyncProcessorEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@5@PEAVCMonitorContext@123@_K@Z; Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(wil::com_ptr_t<Rdp::Avenc::IFrameBuffer1,wil::err_exception_policy> const &,uint,uint,wil::com_ptr_t<Rdp::Avenc::IFrameAsyncProcessorEvents,wil::err_exception_policy> const &,Rdp::Avenc::Ic3::CMonitorContext *,unsigned __int64)
0x180045b18  mov     rbx, rax
0x180045b1b  mov     [rsp+158h+var_80], rax
0x180045b23  test    rax, rax
0x180045b26  jz      short loc_180045B44
0x180045b28  mov     rcx, [rax+8]
0x180045b2c  movsxd  rcx, dword ptr [rcx+4]
0x180045b30  add     rcx, 8
0x180045b34  add     rcx, rax
0x180045b37  mov     rdx, [rcx]
0x180045b3a  mov     rax, [rdx+8]
0x180045b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b43  nop
0x180045b44  mov     rcx, [rsp+158h+var_98]
0x180045b4c  test    rcx, rcx
0x180045b4f  jz      short loc_180045B5E
0x180045b51  mov     rax, [rcx]
0x180045b54  mov     rax, [rax+10h]
0x180045b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b5d  nop
0x180045b5e  mov     eax, cs:dword_1800C1058
0x180045b64  cmp     eax, r13d
0x180045b67  jbe     loc_180045C28
0x180045b6d  mov     [rsp+158h+var_C8], r15
0x180045b75  mov     rax, [rdi]
0x180045b78  mov     rcx, rdi
0x180045b7b  mov     rax, [rax+0C8h]
0x180045b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b87  mov     [rsp+158h+var_A8], rax
0x180045b8f  lea     rax, aMatch; "Match"
0x180045b96  mov     [rsp+158h+var_98], rax
0x180045b9e  lea     rax, aRdpAvencIc3Cic_5; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180045ba5  mov     [rsp+158h+var_C0], rax
0x180045bad  mov     dword ptr [rsp+158h+arg_10], 359h
0x180045bb8  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180045bbf  mov     [rsp+158h+var_B8], rax
0x180045bc7  lea     rax, [rsp+158h+var_C8]
0x180045bcf  mov     [rsp+158h+var_110], rax
0x180045bd4  lea     rax, [rsp+158h+var_A8]
0x180045bdc  mov     [rsp+158h+var_118], rax
0x180045be1  lea     rax, [rsp+158h+var_98]
0x180045be9  mov     [rsp+158h+var_120], rax
0x180045bee  lea     rax, [rsp+158h+var_C0]
0x180045bf6  mov     [rsp+158h+var_128], rax
0x180045bfb  lea     rax, [rsp+158h+arg_10]
0x180045c03  mov     [rsp+158h+var_130], rax; char *
0x180045c08  lea     rax, [rsp+158h+var_B8]
0x180045c10  mov     qword ptr [rsp+158h+var_138], rax
0x180045c15  lea     rdx, byte_1800B205F
0x180045c1c  lea     rcx, dword_1800C1058
0x180045c23  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180045c28  cmp     byte ptr [r12+120h], 0
0x180045c31  jz      loc_180045CD5
0x180045c37  mov     r14, [rsi+0F0h]
0x180045c3e  mov     [rsi+0F0h], rbx
0x180045c45  test    rbx, rbx
0x180045c48  jz      short loc_180045C65
0x180045c4a  mov     rax, [rbx+8]
0x180045c4e  movsxd  rcx, dword ptr [rax+4]
0x180045c52  add     rcx, 8
0x180045c56  add     rcx, rbx
0x180045c59  mov     rax, [rcx]
0x180045c5c  mov     rax, [rax+8]
0x180045c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c65  test    r14, r14
0x180045c68  jz      short loc_180045C85
0x180045c6a  mov     rax, [r14+8]
0x180045c6e  movsxd  rcx, dword ptr [rax+4]
0x180045c72  add     rcx, 8
0x180045c76  add     rcx, r14
0x180045c79  mov     rax, [rcx]
0x180045c7c  mov     rax, [rax+10h]
0x180045c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c85  mov     [rsp+158h+arg_10], 0
0x180045c91  lea     rcx, [rsp+158h+arg_10]
0x180045c99  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180045c9f  mov     eax, dword ptr [rsp+158h+arg_10+4]
0x180045ca6  shl     rax, 20h
0x180045caa  mov     ecx, dword ptr [rsp+158h+arg_10]
0x180045cb1  mov     rdx, 0FE624E212AC18000h
0x180045cbb  add     rax, rdx
0x180045cbe  add     rcx, rax
0x180045cc1  mov     [rsi+1A8h], rcx
0x180045cc8  lea     rcx, [rsi+158h]; ConditionVariable
0x180045ccf  call    cs:__imp_WakeConditionVariable
0x180045cd5  mov     rax, [rsi+0D0h]
0x180045cdc  mov     r14, [rax+118h]
0x180045ce3  mov     [rsp+158h+var_58], r14
0x180045ceb  test    r14, r14
0x180045cee  jz      short loc_180045D0C
0x180045cf0  mov     rax, [r14+8]
0x180045cf4  movsxd  rcx, dword ptr [rax+4]
0x180045cf8  add     rcx, 8
0x180045cfc  add     rcx, r14
0x180045cff  mov     rax, [rcx]
0x180045d02  mov     rax, [rax+8]
0x180045d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d0b  nop
0x180045d0c  test    r14, r14
0x180045d0f  jz      loc_180046019
0x180045d15  mov     rax, [rdi]
0x180045d18  mov     rcx, rdi
0x180045d1b  mov     rax, [rax+0C8h]
0x180045d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d27  mov     r8, r15
0x180045d2a  mov     rdx, rax
0x180045d2d  mov     rcx, rsi
0x180045d30  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x180045d35  mov     byte ptr [rsp+158h+arg_10], al
0x180045d3c  mov     ecx, cs:dword_1800C1058
0x180045d42  cmp     ecx, r13d
0x180045d45  jbe     loc_180045E29
0x180045d4b  mov     rcx, [rdi]
0x180045d4e  mov     rax, [rcx+0C8h]
0x180045d55  mov     rcx, rdi
0x180045d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d5d  mov     [rsp+158h+var_C8], rax
0x180045d65  mov     eax, [rsp+158h+var_B0]
0x180045d6c  mov     [rsp+158h+arg_18], eax
0x180045d73  mov     eax, [rsp+158h+var_AC]
0x180045d7a  mov     dword ptr [rsp+158h+var_90], eax
0x180045d81  lea     rax, aStart; "Start"
0x180045d88  mov     [rsp+158h+var_A8], rax
0x180045d90  lea     rax, aRdpAvencIc3Cic_5; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180045d97  mov     [rsp+158h+var_98], rax
0x180045d9f  mov     dword ptr [rsp+158h+var_88], 36Dh
0x180045daa  lea     r15, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180045db1  mov     [rsp+158h+var_C0], r15
0x180045db9  lea     rax, [rsp+158h+var_C8]
0x180045dc1  mov     [rsp+158h+var_108], rax
0x180045dc6  lea     rax, [rsp+158h+arg_18]
0x180045dce  mov     [rsp+158h+var_110], rax
0x180045dd3  lea     rax, [rsp+158h+var_90]
0x180045ddb  mov     [rsp+158h+var_118], rax
0x180045de0  lea     rax, [rsp+158h+var_A8]
  ... truncated ...
```
