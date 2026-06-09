# Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameDxBuffer>(Rdp::Avenc::IFrameDxBuffer &,bool *)

- ea: `0x18005cc8c`
- end: `0x18005e1f7`
- name: `??$ProcessFrameInternal@UIFrameDxBuffer@Avenc@Rdp@@@CYuvFrameProcessor@Yuv@Avenc@Rdp@@IEAAJAEAUIFrameDxBuffer@23@PEA_N@Z`
- size: `5483`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800625e0`

## callees

- `0x180001008`
- `0x1800032cc`
- `0x1800038c4`
- `0x18000490c`
- `0x1800058c8`
- `0x180005b28`
- `0x180006580`
- `0x1800080cc`
- `0x18000a1b4`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x1800199cc`
- `0x18002dd40`
- `0x18005b5c4`
- `0x18005cc8c`
- `0x1800602ac`
- `0x180060520`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18005ce80`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18005ce80`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18005cefb`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18005cf42`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18005cefb`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18005cf42`

## string_xrefs

- `0x18005e154`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005e169`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005e1b5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005cfaa`: `Failed to get moves and dirties`
- `0x18005e1a0`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`
- `0x18005d56f`: `NV12 conversion : Failed to create shader resource view`
- `0x18005d6e3`: `NV12 conversion : Failed to create Chroma Unordered Access View`
- `0x18005d63b`: `NV12 conversion : Failed to create Luma Unordered Access View`
- `0x18005da7a`: `Failed to signal shared fence after RGB copy`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal<Rdp::Avenc::IFrameDxBuffer>(
        __int64 a1,
        __int64 a2,
        bool *a3)
{
  __int64 v6; // rcx
  int v7; // r14d
  int v8; // edi
  int v9; // r8d
  int v10; // r9d
  volatile signed __int32 *v11; // r14
  int v12; // r8d
  int v13; // r9d
  volatile signed __int32 *v14; // r15
  __int64 v15; // rax
  unsigned int v16; // eax
  struct tagRECT *v17; // rdi
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rax
  int v20; // eax
  __int64 v21; // r8
  struct tagRECT *v22; // rdx
  unsigned int v23; // r9d
  unsigned int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const char *v32; // rdi
  int v33; // r8d
  int v34; // r9d
  __int64 *v35; // rcx
  __int64 v36; // rax
  unsigned int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  unsigned int v40; // eax
  Rdp::Avenc::Yuv::CYuvProcessor *v41; // rax
  __int64 v42; // rcx
  unsigned int v43; // eax
  _QWORD *v44; // rax
  int v45; // r8d
  int v46; // r9d
  int v47; // r8d
  int v48; // r9d
  _QWORD *v49; // rax
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // eax
  volatile signed __int32 *v53; // r12
  volatile signed __int32 *v54; // r12
  unsigned int v55; // r14d
  bool *v56; // r12
  unsigned int v57; // edi
  int v58; // eax
  int v59; // r8d
  int v60; // r9d
  int v61; // r8d
  int v62; // r9d
  unsigned int v63; // eax
  int v64; // edx
  unsigned int v65; // eax
  int v66; // [rsp+20h] [rbp-288h]
  int v67; // [rsp+20h] [rbp-288h]
  _QWORD **v68; // [rsp+20h] [rbp-288h]
  char *v69; // [rsp+28h] [rbp-280h]
  char *v70; // [rsp+28h] [rbp-280h]
  char *v71; // [rsp+28h] [rbp-280h]
  char *v72; // [rsp+28h] [rbp-280h]
  char *v73; // [rsp+28h] [rbp-280h]
  char *v74; // [rsp+28h] [rbp-280h]
  char *v75; // [rsp+28h] [rbp-280h]
  unsigned int v76; // [rsp+50h] [rbp-258h]
  int v77; // [rsp+90h] [rbp-218h] BYREF
  char v78[8]; // [rsp+98h] [rbp-210h] BYREF
  char v79[4]; // [rsp+A0h] [rbp-208h] BYREF
  int v80; // [rsp+A4h] [rbp-204h]
  const char *v81; // [rsp+A8h] [rbp-200h] BYREF
  Rdp::Avenc::Yuv::CYuvProcessor *v82; // [rsp+B0h] [rbp-1F8h] BYREF
  unsigned __int64 v83; // [rsp+B8h] [rbp-1F0h] BYREF
  struct tagRECT *v84; // [rsp+C0h] [rbp-1E8h] BYREF
  int v85[2]; // [rsp+C8h] [rbp-1E0h] BYREF
  unsigned __int64 v86; // [rsp+D0h] [rbp-1D8h] BYREF
  unsigned int v87; // [rsp+D8h] [rbp-1D0h]
  __int64 v88; // [rsp+E0h] [rbp-1C8h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-1C0h] BYREF
  const char *v90; // [rsp+F0h] [rbp-1B8h] BYREF
  const char *v91; // [rsp+F8h] [rbp-1B0h] BYREF
  unsigned int v92; // [rsp+100h] [rbp-1A8h] BYREF
  const char *v93; // [rsp+108h] [rbp-1A0h] BYREF
  __int64 v94; // [rsp+110h] [rbp-198h] BYREF
  const char *v95; // [rsp+118h] [rbp-190h] BYREF
  __int64 v96; // [rsp+120h] [rbp-188h] BYREF
  __int64 v97; // [rsp+128h] [rbp-180h]
  struct tagRECT *v98; // [rsp+130h] [rbp-178h] BYREF
  __int64 v99; // [rsp+138h] [rbp-170h] BYREF
  _QWORD *v100; // [rsp+140h] [rbp-168h] BYREF
  volatile signed __int32 *v101; // [rsp+148h] [rbp-160h]
  __int64 *v102; // [rsp+150h] [rbp-158h] BYREF
  volatile signed __int32 *v103; // [rsp+158h] [rbp-150h]
  __int64 v104; // [rsp+160h] [rbp-148h] BYREF
  bool *v105; // [rsp+168h] [rbp-140h]
  __int64 v106; // [rsp+170h] [rbp-138h]
  __int64 v107; // [rsp+178h] [rbp-130h]
  volatile signed __int32 *v108; // [rsp+180h] [rbp-128h]
  __int64 v109; // [rsp+188h] [rbp-120h]
  volatile signed __int32 *v110; // [rsp+190h] [rbp-118h]
  unsigned __int8 v111[4]; // [rsp+198h] [rbp-110h] BYREF
  int v112; // [rsp+19Ch] [rbp-10Ch]
  __int64 v113; // [rsp+1A0h] [rbp-108h]
  _DWORD v114[4]; // [rsp+1A8h] [rbp-100h] BYREF
  __int64 v115; // [rsp+1B8h] [rbp-F0h]
  int v116; // [rsp+1C0h] [rbp-E8h] BYREF
  __int64 v117; // [rsp+1C4h] [rbp-E4h]
  int v118; // [rsp+1D8h] [rbp-D0h] BYREF
  __int64 v119; // [rsp+1DCh] [rbp-CCh]
  _QWORD v120[2]; // [rsp+1F0h] [rbp-B8h] BYREF
  _OWORD v121[3]; // [rsp+200h] [rbp-A8h] BYREF
  _OWORD v122[3]; // [rsp+230h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v105 = a3;
  v95 = (const char *)a1;
  v106 = a2;
  v96 = (__int64)a3;
  if ( a3 )
  {
    v87 = 0;
    v97 = a1 + 16;
    v6 = *(_QWORD *)(a1 + 16);
    v7 = *(_DWORD *)(*(_QWORD *)(v6 + 112) + 152LL);
    v80 = v7;
    v8 = *(_DWORD *)(v6 + 136);
    LODWORD(v91) = v8;
    v112 = 0;
    ++*(_DWORD *)(a1 + 8);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
      LODWORD(v93) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      LODWORD(v88) = v7;
      *(_DWORD *)v79 = v8;
      v77 = *(_DWORD *)(a1 + 8);
      v81 = "NewFrame";
      *(_QWORD *)v85 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
      *(_DWORD *)v78 = 259;
      v89 = (__int64)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800B4827,
        v9,
        v10,
        (__int64)&v89,
        (__int64)v78,
        (__int64)v85,
        (__int64)&v81,
        (__int64)&v77,
        (__int64)v79,
        (__int64)&v88,
        (__int64)&v93,
        (__int64)&v86);
    }
    v104 = 0;
    GetSystemTimePreciseAsFileTime(&v104);
    *(_DWORD *)v111 = 0;
    v113 = v104;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 40LL))(a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 80LL))(a2);
    v11 = (volatile signed __int32 *)std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((volatile void *)(a1 + 40));
    v107 = *(_QWORD *)(a1 + 32);
    v108 = v11;
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    if ( (_InterlockedExchange64((volatile __int64 *)(a1 + 40), (__int64)v11) & 3) == 2 )
      WakeByAddressAll((PVOID)(a1 + 40));
    v14 = (volatile signed __int32 *)std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((volatile void *)(a1 + 56));
    v15 = *(_QWORD *)(a1 + 48);
    v109 = v15;
    v110 = v14;
    if ( v14 )
      _InterlockedIncrement(v14 + 2);
    if ( (_InterlockedExchange64((volatile __int64 *)(a1 + 56), (__int64)v14) & 3) == 2 )
    {
      WakeByAddressAll((PVOID)(a1 + 56));
      v15 = v109;
    }
    if ( v107 && v15 )
    {
      v92 = 0;
      v98 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct tagRECT **, unsigned int *))(*(_QWORD *)a2 + 136LL))(
              a2,
              0,
              0,
              &v98,
              &v92);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
        (const char *)v16,
        (int)"Failed to get moves and dirties",
        v69);
      v89 = v92;
      v17 = v98;
      v99 = 0;
      v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
              a2,
              &GUID_5ce16a4c_4058_480b_8806_9c82986f8662,
              &v99);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v18,
          v67);
      v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 216LL))(v99);
      v94 = 0;
      v20 = (**v19)(v19, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v94);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v20,
          v67);
      memset(v121, 0, 44);
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v94 + 80LL))(v94, v121);
      if ( LODWORD(v121[1]) == 10 )
      {
        v21 = 8;
      }
      else
      {
        if ( LODWORD(v121[1]) != 87 )
        {
          v63 = wil::verify_hresult<long>(2147942487LL);
          LODWORD(v70) = v64;
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
            (const char *)v63,
            (int)"Unsupported DXGI_FORMAT: %d",
            v70);
        }
        v21 = 4;
      }
      v22 = &v17[v89];
      if ( v17 != v22 )
      {
        v23 = v87;
        do
        {
          v24 = v23 + (v17->right - v17->left) * (v17->bottom - v17->top);
          if ( !((_DWORD)v21 * (v17->right - v17->left) * (v17->bottom - v17->top)) )
            v24 = v23;
          v23 = v24;
          ++v17;
        }
        while ( v17 != v22 );
        v87 = v24;
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v89 = (*(__int64 (__fastcall **)(__int64, struct tagRECT *, __int64))(*(_QWORD *)a2 + 128LL))(a2, v22, v21);
        *(_DWORD *)v78 = v80;
        v77 = (int)v91;
        v86 = (unsigned __int64)"Start";
        v81 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
        *(_DWORD *)v79 = 332;
        *(_QWORD *)v85 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800B4722,
          v25,
          v26,
          (__int64)v85,
          (__int64)v79,
          (__int64)&v81,
          (__int64)&v86,
          (__int64)&v77,
          (__int64)v78,
          (__int64)&v89);
      }
      Rdp::Utils::Graphics::CSharedResourcePoolConsumer<Rdp::Utils::Graphics::CSharedTexture>::GetResource(v107, &v102);
      wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
        retaddr,
        335,
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
        2147943568LL);
      memset(v122, 0, 44);
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v102 + 80LL))(*v102, v122);
      Rdp::Utils::Graphics::CSharedResourcePoolConsumer<Rdp::Utils::Graphics::CSharedFence>::GetResource(v109, &v100);
      v71 = "Failed to obtain shared fence";
      v68 = &v100;
      wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
        retaddr,
        340,
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
        2147943568LL);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v89 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
        v86 = (unsigned __int64)"End";
        v81 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
        *(_DWORD *)v78 = 345;
        *(_QWORD *)v85 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)byte_1800B4791,
          v27,
          v28,
          (__int64)v85,
          (__int64)v78,
          (__int64)&v81,
          (__int64)&v86,
          (__int64)&v89);
      }
      v89 = 0;
      *(_QWORD *)v78 = 0;
      v29 = *(__int64 **)(a1 + 24);
      v30 = *v29;
      *(_QWORD *)v78 = 0;
      (*(void (__fastcall **)(__int64 *, char *))(v30 + 320))(v29, v78);
      v81 = 0;
      v31 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, const char **))v78)(
              *(_QWORD *)v78,
              &GUID_917600da_f58c_4c33_98d8_3e15b390fa24,
              &v81);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v31,
          (int)v68);
      v32 = v81;
      v89 = (__int64)v81;
      if ( *(_QWORD *)v78 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v78 + 16LL))(*(_QWORD *)v78);
      if ( LODWORD(v122[1]) == 103 )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
          *(_DWORD *)v78 = v80;
          v77 = (int)v91;
          v93 = "Start";
          v90 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
          *(_DWORD *)v79 = 361;
          v82 = (Rdp::Avenc::Yuv::CYuvProcessor *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800B46B2,
            v33,
            v34,
            (__int64)&v82,
            (__int64)v79,
            (__int64)&v90,
            (__int64)&v93,
            (__int64)&v77,
            (__int64)v78,
            (__int64)&v86);
        }
        v115 = 0;
        v114[0] = v121[1];
        v114[1] = 4;
        v114[2] = DWORD2(v121[0]) - 1;
        v114[3] = DWORD2(v121[0]);
        v81 = 0;
        v35 = *(__int64 **)(a1 + 24);
        v36 = *v35;
        v81 = 0;
        v37 = (*(__int64 (__fastcall **)(__int64 *, __int64, _DWORD *, const char **, _QWORD **, char *))(v36 + 56))(
                v35,
                v94,
                v114,
                &v81,
                v68,
                v71);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x173,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
          (const char *)v37,
          (int)"NV12 conversion : Failed to create shader resource view",
          v72);
        v83 = (unsigned __int64)v81;
        (*(void (__fastcall **)(const char *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)v32 + 536LL))(
          v32,
          0,
          1,
          &v83);
        (*(void (__fastcall **)(const char *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v32 + 552LL))(
          v32,
          *(_QWORD *)(a1 + 64),
          0,
          0);
        *(_QWORD *)v85 = 0;
        v88 = 0;
        v116 = 61;
        v117 = 4;
        v38 = *(__int64 **)(a1 + 24);
        v39 = *v38;
        *(_QWORD *)v85 = 0;
        v40 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *, int *))(v39 + 64))(v38, *v102, &v116, v85);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x17F,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
          (const char *)v40,
          (int)"NV12 conversion : Failed to create Luma Unordered Access View",
          v73);
        v118 = 49;
        v119 = 4;
        v90 = *(const char **)(a1 + 24);
        v41 = *(Rdp::Avenc::Yuv::CYuvProcessor **)(*(_QWORD *)v90 + 64LL);
        v82 = v41;
        v42 = v88;
        v88 = 0;
        if ( v42 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          v41 = v82;
        }
        v43 = ((__int64 (__fastcall *)(const char *, __int64, int *, __int64 *))v41)(v90, *v102, &v118, &v88);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
          (const char *)v43,
          (int)"NV12 conversion : Failed to create Chroma Unordered Access View",
          v74);
        v120[0] = *(_QWORD *)v85;
        v120[1] = v88;
        (*(void (__fastcall **)(const char *, _QWORD, __int64, _QWORD *, _QWORD))(*(_QWORD *)v32 + 544LL))(
          v32,
          0,
          2,
          v120,
          0);
        (*(void (__fastcall **)(const char *, _QWORD, _QWORD, __int64))(*(_QWORD *)v32 + 328LL))(
          v32,
          (unsigned int)(*(_DWORD *)(*(_QWORD *)v97 + 148LL) + 15) >> 4,
          (unsigned int)(*(_DWORD *)(*(_QWORD *)v97 + 152LL) + 15) >> 4,
          1);
        v44 = v100;
        ++v100[2];
        v86 = v44[2];
        LODWORD(v93) = (*(__int64 (__fastcall **)(const char *, _QWORD, unsigned __int64))(*(_QWORD *)v32 + 1176LL))(
                         v32,
                         *v100,
                         v86);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
          (const char *)(unsigned int)v93,
          (int)"Failed to signal shared fence after NV12 conversion",
          v75);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v82 = (Rdp::Avenc::Yuv::CYuvProcessor *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
          *(_DWORD *)v78 = v80;
          v77 = (int)v91;
          v90 = "DispatchDone";
          v91 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
          *(_DWORD *)v79 = 409;
          v84 = (struct tagRECT *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800B4642,
            v45,
            v46,
            (__int64)&v84,
            (__int64)v79,
            (__int64)&v91,
            (__int64)&v90,
            (__int64)&v77,
            (__int64)v78,
            (__int64)&v82);
        }
        if ( v88 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        if ( *(_QWORD *)v85 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v85 + 16LL))(*(_QWORD *)v85);
        if ( v81 )
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v81 + 16LL))(v81);
      }
      else
      {
        if ( LODWORD(v121[1]) != LODWORD(v122[1]) )
        {
          v65 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1B5,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
            (const char *)v65,
            (int)"Unsupported texture format conversion",
            v71);
        }
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v84 = (struct tagRECT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
          *(_DWORD *)v78 = v80;
          v77 = (int)v91;
          v83 = (unsigned __int64)"Start";
          v82 = (Rdp::Avenc::Yuv::CYuvProcessor *)"Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
          *(_DWORD *)v79 = 418;
          v90 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)qword_1800B4570,
            v47,
            v48,
            (__int64)&v90,
            (__int64)v79,
            (__int64)&v82,
            (__int64)&v83,
            (__int64)&v77,
            (__int64)v78,
            (__int64)&v84);
        }
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v32 + 376LL))(v32, *v102, v94);
        v49 = v100;
        ++v100[2];
        v86 = v49[2];
        LODWORD(v93) = (*(__int64 (__fastcall **)(const char *, _QWORD, unsigned __int64))(*(_QWORD *)v32 + 1176LL))(
                         v32,
                         *v100,
                         v86);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
          (const char *)(unsigned int)v93,
          (int)"Failed to signal shared fence after RGB copy",
          v71);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v84 = (struct tagRECT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
          *(_DWORD *)v78 = v80;
          v77 = (int)v91;
          v83 = (unsigned __int64)"DispatchDone";
          v82 = (Rdp::Avenc::Yuv::CYuvProcessor *)"Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
          *(_DWORD *)v79 = 433;
          v90 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800B45D9,
            v50,
            v51,
            (__int64)&v90,
            (__int64)v79,
            (__int64)&v82,
            (__int64)&v83,
            (__int64)&v77,
            (__int64)v78,
            (__int64)&v84);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 88LL))(a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 48LL))(a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2);
      v82 = *(Rdp::Avenc::Yuv::CYuvProcessor **)(*(_QWORD *)v97 + 112LL);
      v84 = v98;
      *(_DWORD *)v78 = v92;
      v83 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
      v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      Rdp::Avenc::Yuv::CYuvProcessor::OnResourceUpdate(
        (Rdp::Avenc::CFcWireEncoder **)v82,
        (struct _GUID *)(*(_QWORD *)v97 + 120LL),
        a1,
        v102[1],
        (void *)v100[1],
        v52,
        (const char *)v83,
        *(unsigned int *)v78,
        v84,
        v86,
        v76,
        v111);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 64LL))(a2);
      *(_DWORD *)v78 = 1;
      if ( v32 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v32 + 16LL))(v32);
      v53 = v101;
      if ( v101 )
      {
        if ( _InterlockedExchangeAdd(v101 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
          if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
        }
      }
      v54 = v103;
      if ( v103 )
      {
        if ( _InterlockedExchangeAdd(v103 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v99 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      v55 = (unsigned int)v93;
      v56 = v105;
      v57 = *(_DWORD *)v78;
      if ( v87 )
      {
        v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 112LL))(
                a2,
                *(unsigned int *)v78,
                v87,
                0);
        if ( v58 < 0 && (unsigned int)dword_1800C1058 > 2 )
        {
          *(_DWORD *)v78 = v58;
          v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
          *(_DWORD *)v79 = v80;
          v96 = *(_QWORD *)v97 + 120LL;
          v95 = "Failed to report frame statistics";
          v84 = (struct tagRECT *)"Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
          LODWORD(v88) = 513;
          v83 = (unsigned __int64)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&dword_1800B44FC,
            v59,
            v60,
            (__int64)&v83,
            (__int64)&v88,
            (__int64)&v84,
            (__int64)&v95,
            (__int64)&v96,
            (__int64)v79,
            (__int64)&v77,
            (__int64)v78);
        }
      }
      *v56 = v57 != 1;
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        *(_DWORD *)v78 = *v56;
        v96 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
        v95 = "Finished";
        v84 = (struct tagRECT *)"Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
        v77 = 523;
        v83 = (unsigned __int64)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&unk_1800B4410,
          v61,
          v62,
          (__int64)&v83,
          (__int64)&v77,
          (__int64)&v84,
          (__int64)&v95,
          (__int64)&v96,
          (__int64)v78);
      }
      return v55;
    }
    else
    {
      if ( (unsigned int)dword_1800C1058 > 3 )
      {
        v84 = (struct tagRECT *)"Failed to obtain shared resource pools, skipping frame";
        v83 = (unsigned __int64)"Rdp::Avenc::Yuv::CYuvFrameProcessor::ProcessFrameInternal";
        *(_DWORD *)v78 = 283;
        v82 = (Rdp::Avenc::Yuv::CYuvProcessor *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800B47EA,
          v12,
          v13,
          (__int64)&v82,
          (__int64)v78,
          (__int64)&v83,
          (__int64)&v84);
      }
      *v105 = 0;
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
      (const char *)0x80004003LL,
      v66);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18005cc8c  push    rbx
0x18005cc8e  push    rsi
0x18005cc8f  push    rdi
0x18005cc90  push    r12
0x18005cc92  push    r13
0x18005cc94  push    r14
0x18005cc96  push    r15
0x18005cc98  sub     rsp, 270h
0x18005cc9f  mov     rax, cs:__security_cookie
0x18005cca6  xor     rax, rsp
0x18005cca9  mov     [rsp+2A8h+var_48], rax
0x18005ccb1  mov     rax, r8
0x18005ccb4  mov     [rsp+2A8h+var_140], rax
0x18005ccbc  mov     rsi, rdx
0x18005ccbf  mov     r12, rcx
0x18005ccc2  mov     [rsp+2A8h+var_190], rcx
0x18005ccca  mov     [rsp+2A8h+var_138], rdx
0x18005ccd2  mov     [rsp+2A8h+var_188], rax
0x18005ccda  xor     ebx, ebx
0x18005ccdc  test    r8, r8
0x18005ccdf  jnz     short loc_18005CD09
0x18005cce1  mov     rcx, [rsp+2A8h]; this
0x18005cce9  mov     ebx, 80004003h
0x18005ccee  mov     r9d, ebx; char *
0x18005ccf1  lea     r8, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005ccf8  mov     edx, 0EEh; void *
0x18005ccfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd02  mov     eax, ebx
0x18005cd04  jmp     loc_18005E12E
0x18005cd09  mov     [rsp+2A8h+var_1D0], ebx
0x18005cd10  lea     rax, [rcx+10h]
0x18005cd14  mov     [rsp+2A8h+var_180], rax
0x18005cd1c  mov     rcx, [rax]
0x18005cd1f  mov     rax, [rcx+70h]
0x18005cd23  mov     r14d, [rax+98h]
0x18005cd2a  mov     [rsp+2A8h+var_204], r14d
0x18005cd32  mov     edi, [rcx+88h]
0x18005cd38  mov     dword ptr [rsp+2A8h+var_1B0], edi
0x18005cd3f  xor     eax, eax
0x18005cd41  mov     [rsp+2A8h+var_10C], eax
0x18005cd48  inc     dword ptr [r12+8]
0x18005cd4d  mov     eax, cs:dword_1800C1058
0x18005cd53  cmp     eax, 5
0x18005cd56  jbe     loc_18005CE69
0x18005cd5c  mov     rax, [rdx]
0x18005cd5f  mov     rcx, rsi
0x18005cd62  mov     rax, [rax+80h]
0x18005cd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd6e  mov     [rsp+2A8h+var_1D8], rax
0x18005cd76  mov     rax, [rsi]
0x18005cd79  mov     rcx, rsi
0x18005cd7c  mov     rax, [rax+78h]
0x18005cd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd85  mov     dword ptr [rsp+2A8h+var_1A0], eax
0x18005cd8c  mov     dword ptr [rsp+2A8h+var_1C8], r14d
0x18005cd94  mov     dword ptr [rsp+2A8h+var_208], edi
0x18005cd9b  mov     eax, [r12+8]
0x18005cda0  mov     [rsp+2A8h+var_218], eax
0x18005cda7  lea     rax, aNewframe; "NewFrame"
0x18005cdae  mov     [rsp+2A8h+var_200], rax
0x18005cdb6  lea     rdi, aRdpAvencYuvCyu_8; "Rdp::Avenc::Yuv::CYuvFrameProcessor::Pr"...
0x18005cdbd  mov     qword ptr [rsp+2A8h+var_1E0], rdi
0x18005cdc5  mov     dword ptr [rsp+2A8h+var_210], 103h
0x18005cdd0  lea     r13, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005cdd7  mov     [rsp+2A8h+var_1C0], r13
0x18005cddf  lea     rax, [rsp+2A8h+var_1D8]
0x18005cde7  mov     [rsp+2A8h+var_248], rax
0x18005cdec  lea     rax, [rsp+2A8h+var_1A0]
0x18005cdf4  mov     [rsp+2A8h+var_250], rax
0x18005cdf9  lea     rax, [rsp+2A8h+var_1C8]
0x18005ce01  mov     qword ptr [rsp+2A8h+var_258], rax
0x18005ce06  lea     rax, [rsp+2A8h+var_208]
0x18005ce0e  mov     [rsp+2A8h+var_260], rax
0x18005ce13  lea     rax, [rsp+2A8h+var_218]
0x18005ce1b  mov     [rsp+2A8h+var_268], rax
0x18005ce20  lea     rax, [rsp+2A8h+var_200]
0x18005ce28  mov     qword ptr [rsp+2A8h+var_270], rax
0x18005ce2d  lea     rax, [rsp+2A8h+var_1E0]
0x18005ce35  mov     [rsp+2A8h+var_278], rax
0x18005ce3a  lea     rax, [rsp+2A8h+var_210]
0x18005ce42  mov     [rsp+2A8h+var_280], rax
0x18005ce47  lea     rax, [rsp+2A8h+var_1C0]
0x18005ce4f  mov     [rsp+2A8h+var_288], rax
0x18005ce54  lea     rdx, byte_1800B4827
0x18005ce5b  lea     rcx, dword_1800C1058
0x18005ce62  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334444AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005ce67  jmp     short loc_18005CE70
0x18005ce69  lea     r13, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005ce70  mov     [rsp+2A8h+var_148], rbx
0x18005ce78  lea     rcx, [rsp+2A8h+var_148]
0x18005ce80  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18005ce86  mov     dword ptr [rsp+2A8h+var_110], ebx
0x18005ce8d  mov     rax, [rsp+2A8h+var_148]
0x18005ce95  mov     [rsp+2A8h+var_108], rax
0x18005ce9d  mov     rax, [rsi]
0x18005cea0  mov     rcx, rsi
0x18005cea3  mov     rax, [rax+28h]
0x18005cea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceac  mov     rax, [rsi]
0x18005ceaf  mov     rcx, rsi
0x18005ceb2  mov     rax, [rax+50h]
0x18005ceb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cebb  lea     rdi, [r12+28h]
0x18005cec0  mov     rcx, rdi; Address
0x18005cec3  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18005cec8  mov     r14, rax
0x18005cecb  mov     rax, [r12+20h]
0x18005ced0  mov     [rsp+2A8h+var_130], rax
0x18005ced8  mov     [rsp+2A8h+var_128], r14
0x18005cee0  test    r14, r14
0x18005cee3  jz      short loc_18005CEEA
0x18005cee5  lock inc dword ptr [r14+8]
0x18005ceea  mov     rcx, r14
0x18005ceed  xchg    rcx, [rdi]
0x18005cef0  and     cl, 3
0x18005cef3  cmp     cl, 2
0x18005cef6  jnz     short loc_18005CF02
0x18005cef8  mov     rcx, rdi; Address
0x18005cefb  call    cs:__imp_WakeByAddressAll
0x18005cf01  nop
0x18005cf02  lea     rdi, [r12+38h]
0x18005cf07  mov     rcx, rdi; Address
0x18005cf0a  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18005cf0f  mov     r15, rax
0x18005cf12  mov     rax, [r12+30h]
0x18005cf17  mov     [rsp+2A8h+var_120], rax
0x18005cf1f  mov     [rsp+2A8h+var_118], r15
0x18005cf27  test    r15, r15
0x18005cf2a  jz      short loc_18005CF31
0x18005cf2c  lock inc dword ptr [r15+8]
0x18005cf31  mov     rcx, r15
0x18005cf34  xchg    rcx, [rdi]
0x18005cf37  and     cl, 3
0x18005cf3a  cmp     cl, 2
0x18005cf3d  jnz     short loc_18005CF50
0x18005cf3f  mov     rcx, rdi; Address
0x18005cf42  call    cs:__imp_WakeByAddressAll
0x18005cf48  mov     rax, [rsp+2A8h+var_120]
0x18005cf50  cmp     [rsp+2A8h+var_130], rbx
0x18005cf58  jz      loc_18005DE03
0x18005cf5e  test    rax, rax
0x18005cf61  jz      loc_18005DE03
0x18005cf67  mov     [rsp+2A8h+var_1A8], ebx
0x18005cf6e  mov     [rsp+2A8h+var_178], rbx
0x18005cf76  mov     rax, [rsi]
0x18005cf79  lea     rcx, [rsp+2A8h+var_1A8]
0x18005cf81  mov     [rsp+2A8h+var_288], rcx
0x18005cf86  lea     r9, [rsp+2A8h+var_178]
0x18005cf8e  xor     r8d, r8d
0x18005cf91  xor     edx, edx
0x18005cf93  mov     rcx, rsi
0x18005cf96  mov     rax, [rax+88h]
0x18005cf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfa2  mov     rcx, [rsp+2A8h]; this
0x18005cfaa  lea     rdx, aFailedToGetMov; "Failed to get moves and dirties"
0x18005cfb1  mov     [rsp+2A8h+var_288], rdx; int
0x18005cfb6  mov     r9d, eax; char *
0x18005cfb9  mov     r8, r13; unsigned int
0x18005cfbc  mov     edx, 12Ch; void *
0x18005cfc1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005cfc6  mov     eax, [rsp+2A8h+var_1A8]
0x18005cfcd  mov     [rsp+2A8h+var_1C0], rax
0x18005cfd5  mov     rdi, [rsp+2A8h+var_178]
0x18005cfdd  mov     [rsp+2A8h+var_170], rbx
0x18005cfe5  mov     rax, [rsi]
0x18005cfe8  lea     r8, [rsp+2A8h+var_170]
0x18005cff0  lea     rdx, _GUID_5ce16a4c_4058_480b_8806_9c82986f8662
0x18005cff7  mov     rcx, rsi
0x18005cffa  mov     rax, [rax]
0x18005cffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d002  mov     rcx, [rsp+2A8h]; this
0x18005d00a  test    eax, eax
0x18005d00c  js      loc_18005E151
0x18005d012  mov     rcx, [rsp+2A8h+var_170]
0x18005d01a  mov     rax, [rcx]
0x18005d01d  mov     rax, [rax+0D8h]
0x18005d024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d029  mov     r9, rax
0x18005d02c  mov     [rsp+2A8h+var_198], rbx
0x18005d034  mov     rcx, [rax]
0x18005d037  mov     rax, [rcx]
0x18005d03a  lea     r8, [rsp+2A8h+var_198]
0x18005d042  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18005d049  mov     rcx, r9
0x18005d04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d051  mov     rcx, [rsp+2A8h]; this
0x18005d059  test    eax, eax
0x18005d05b  js      loc_18005E166
0x18005d061  xorps   xmm0, xmm0
0x18005d064  movups  [rsp+2A8h+var_A8], xmm0
0x18005d06c  movups  xmmword ptr [rsp+2A8h+var_98], xmm0
0x18005d074  movups  xmmword ptr [rsp+2A8h+var_98+0Ch], xmm0
0x18005d07c  mov     rcx, [rsp+2A8h+var_198]
0x18005d084  mov     rax, [rcx]
0x18005d087  lea     rdx, [rsp+2A8h+var_A8]
0x18005d08f  mov     rax, [rax+50h]
0x18005d093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d098  mov     edx, dword ptr [rsp+2A8h+var_98]
0x18005d09f  cmp     edx, 0Ah
0x18005d0a2  jz      short loc_18005D0B5
0x18005d0a4  cmp     edx, 57h ; 'W'
0x18005d0a7  jnz     loc_18005E17B
0x18005d0ad  mov     r8d, 4
0x18005d0b3  jmp     short loc_18005D0BB
0x18005d0b5  mov     r8d, 8
0x18005d0bb  mov     rdx, [rsp+2A8h+var_1C0]
0x18005d0c3  shl     rdx, 4
0x18005d0c7  add     rdx, rdi
0x18005d0ca  cmp     rdi, rdx
0x18005d0cd  jz      short loc_18005D107
0x18005d0cf  mov     r9d, [rsp+2A8h+var_1D0]
0x18005d0d7  mov     ecx, [rdi+0Ch]
0x18005d0da  sub     ecx, [rdi+4]
0x18005d0dd  mov     eax, [rdi+8]
0x18005d0e0  sub     eax, [rdi]
0x18005d0e2  imul    ecx, eax
0x18005d0e5  mov     eax, ecx
0x18005d0e7  imul    eax, r8d
0x18005d0eb  add     ecx, r9d
0x18005d0ee  test    eax, eax
0x18005d0f0  cmovz   ecx, r9d
0x18005d0f4  mov     r9d, ecx
0x18005d0f7  add     rdi, 10h
0x18005d0fb  cmp     rdi, rdx
0x18005d0fe  jnz     short loc_18005D0D7
0x18005d100  mov     [rsp+2A8h+var_1D0], ecx
0x18005d107  mov     eax, cs:dword_1800C1058
0x18005d10d  cmp     eax, 5
0x18005d110  jbe     loc_18005D1ED
0x18005d116  mov     rax, [rsi]
0x18005d119  mov     rcx, rsi
0x18005d11c  mov     rax, [rax+80h]
0x18005d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d128  mov     [rsp+2A8h+var_1C0], rax
0x18005d130  mov     eax, [rsp+2A8h+var_204]
0x18005d137  mov     dword ptr [rsp+2A8h+var_210], eax
0x18005d13e  mov     eax, dword ptr [rsp+2A8h+var_1B0]
0x18005d145  mov     [rsp+2A8h+var_218], eax
0x18005d14c  lea     rdi, aStart; "Start"
0x18005d153  mov     [rsp+2A8h+var_1D8], rdi
0x18005d15b  lea     rdi, aRdpAvencYuvCyu_8; "Rdp::Avenc::Yuv::CYuvFrameProcessor::Pr"...
0x18005d162  mov     [rsp+2A8h+var_200], rdi
0x18005d16a  mov     dword ptr [rsp+2A8h+var_208], 14Ch
0x18005d175  mov     qword ptr [rsp+2A8h+var_1E0], r13
0x18005d17d  lea     rax, [rsp+2A8h+var_1C0]
0x18005d185  mov     qword ptr [rsp+2A8h+var_258], rax
0x18005d18a  lea     rax, [rsp+2A8h+var_210]
0x18005d192  mov     [rsp+2A8h+var_260], rax
0x18005d197  lea     rax, [rsp+2A8h+var_218]
0x18005d19f  mov     [rsp+2A8h+var_268], rax
0x18005d1a4  lea     rax, [rsp+2A8h+var_1D8]
0x18005d1ac  mov     qword ptr [rsp+2A8h+var_270], rax
0x18005d1b1  lea     rax, [rsp+2A8h+var_200]
0x18005d1b9  mov     [rsp+2A8h+var_278], rax
0x18005d1be  lea     rax, [rsp+2A8h+var_208]
0x18005d1c6  mov     [rsp+2A8h+var_280], rax
0x18005d1cb  lea     rax, [rsp+2A8h+var_1E0]
0x18005d1d3  mov     [rsp+2A8h+var_288], rax
0x18005d1d8  lea     rdx, word_1800B4722
0x18005d1df  lea     rcx, dword_1800C1058
0x18005d1e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005d1eb  jmp     short loc_18005D1F4
0x18005d1ed  lea     rdi, aRdpAvencYuvCyu_8; "Rdp::Avenc::Yuv::CYuvFrameProcessor::Pr"...
0x18005d1f4  lea     rdx, [rsp+2A8h+var_158]
0x18005d1fc  mov     rcx, [rsp+2A8h+var_130]
0x18005d204  call    ?GetResource@?$CSharedResourcePoolConsumer@VCSharedTexture@Graphics@Utils@Rdp@@@Graphics@Utils@Rdp@@QEAA?AV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@I@Z; Rdp::Utils::Graphics::CSharedResourcePoolConsumer<Rdp::Utils::Graphics::CSharedTexture>::GetResource(uint)
0x18005d209  nop
0x18005d20a  mov     rcx, [rsp+2A8h]
0x18005d212  lea     rax, aFailedToObtain; "Failed to obtain shared texture"
0x18005d219  mov     [rsp+2A8h+var_280], rax
0x18005d21e  lea     rax, [rsp+2A8h+var_158]
0x18005d226  mov     [rsp+2A8h+var_288], rax
0x18005d22b  mov     r9d, 80070490h
0x18005d231  mov     r8, r13
0x18005d234  mov     edx, 14Fh
0x18005d239  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18005d23e  xorps   xmm0, xmm0
0x18005d241  movups  [rsp+2A8h+var_78], xmm0
0x18005d249  movups  xmmword ptr [rsp+2A8h+var_68], xmm0
0x18005d251  movups  xmmword ptr [rsp+2A8h+var_68+0Ch], xmm0
0x18005d259  mov     rax, [rsp+2A8h+var_158]
0x18005d261  mov     rcx, [rax]
0x18005d264  mov     rax, [rcx]
0x18005d267  lea     rdx, [rsp+2A8h+var_78]
0x18005d26f  mov     rax, [rax+50h]
0x18005d273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d278  lea     rdx, [rsp+2A8h+var_168]
0x18005d280  mov     rcx, [rsp+2A8h+var_120]
0x18005d288  call    ?GetResource@?$CSharedResourcePoolConsumer@VCSharedFence@Graphics@Utils@Rdp@@@Graphics@Utils@Rdp@@QEAA?AV?$shared_ptr@VCSharedFence@Graphics@Utils@Rdp@@@std@@I@Z; Rdp::Utils::Graphics::CSharedResourcePoolConsumer<Rdp::Utils::Graphics::CSharedFence>::GetResource(uint)
0x18005d28d  nop
0x18005d28e  mov     rcx, [rsp+2A8h]
0x18005d296  lea     rax, aFailedToObtain_0; "Failed to obtain shared fence"
0x18005d29d  mov     [rsp+2A8h+var_280], rax
0x18005d2a2  lea     rax, [rsp+2A8h+var_168]
0x18005d2aa  mov     [rsp+2A8h+var_288], rax
0x18005d2af  mov     r9d, 80070490h
0x18005d2b5  mov     r8, r13
0x18005d2b8  mov     edx, 154h
0x18005d2bd  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18005d2c2  mov     eax, cs:dword_1800C1058
  ... truncated ...
```
