# CRdpIdSwapchain::SwapchainProcessorMainProc<CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>>(void)

- ea: `0x180028cdc`
- end: `0x1800291a7`
- name: `??$SwapchainProcessorMainProc@V?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@@CRdpIdSwapchain@@AEAA_NXZ`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d2f0`

## callees

- `0x180001bc4`
- `0x180004fa8`
- `0x1800050e4`
- `0x180006f60`
- `0x1800089f0`
- `0x18000d614`
- `0x18000ead8`
- `0x18001cd04`
- `0x18001dd50`
- `0x18001ddf4`
- `0x180021570`
- `0x180028564`
- `0x180028cdc`
- `0x180029e84`
- `0x18002c5e0`
- `0x18003f010`

## string_xrefs

- `0x180029058`: `Render device removed reason: %#x`
- `0x180028e24`: `ReleaseAndAcquireReady failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CRdpIdSwapchain::SwapchainProcessorMainProc<CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>>(
        __int64 a1)
{
  int v2; // r12d
  _DWORD *v3; // r8
  int v4; // r9d
  unsigned int v5; // eax
  wil *v6; // rcx
  char result; // al
  _DWORD *v8; // r8
  int v9; // r9d
  int v10; // esi
  _QWORD *v11; // rcx
  int v12; // r15d
  _DWORD *v13; // r8
  int v14; // r9d
  __int64 v15; // rcx
  _DWORD *v16; // r8
  int v17; // r9d
  unsigned int v18; // eax
  int v19; // ebx
  const char *v20; // r9
  _DWORD *v21; // r8
  int v22; // r9d
  _DWORD *v23; // rdi
  _DWORD *v24; // r8
  int v25; // r9d
  __int64 v26; // rbx
  wil *v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // [rsp+28h] [rbp-180h]
  int v30; // [rsp+20h] [rbp-188h]
  const char *v31; // [rsp+28h] [rbp-180h]
  int v32; // [rsp+70h] [rbp-138h] BYREF
  int v33; // [rsp+74h] [rbp-134h] BYREF
  int v34; // [rsp+78h] [rbp-130h] BYREF
  const char *v35; // [rsp+80h] [rbp-128h] BYREF
  const char *v36; // [rsp+88h] [rbp-120h] BYREF
  const char *v37; // [rsp+90h] [rbp-118h] BYREF
  int v38; // [rsp+98h] [rbp-110h] BYREF
  int v39; // [rsp+9Ch] [rbp-10Ch] BYREF
  int v40; // [rsp+A0h] [rbp-108h] BYREF
  const char *v41; // [rsp+A8h] [rbp-100h] BYREF
  const char *v42; // [rsp+B0h] [rbp-F8h] BYREF
  const char *v43; // [rsp+B8h] [rbp-F0h] BYREF
  int v44; // [rsp+C0h] [rbp-E8h]
  _DWORD *v45; // [rsp+C8h] [rbp-E0h]
  _BYTE v46[24]; // [rsp+D0h] [rbp-D8h] BYREF
  int v47; // [rsp+E8h] [rbp-C0h]
  __int64 v48; // [rsp+158h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v45 = (_DWORD *)a1;
  v2 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 232LL) + 516LL);
  v44 = v2;
  v3 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v3 > 5u )
  {
    v38 = v2;
    v32 = *(_DWORD *)(*(_QWORD *)a1 + 280LL);
    v43 = "New frame available event triggered";
    v42 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
    v33 = 436;
    v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v3,
      (unsigned int)byte_18004F5F3,
      (_DWORD)v3,
      v4,
      (__int64)&v41,
      (__int64)&v33,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v32,
      (__int64)&v38);
  }
  try
  {
    CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>();
    while ( 1 )
    {
      *(_DWORD *)(a1 + 28) = 129;
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 56LL))(v48);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\Swapchain.h",
        (const char *)v5,
        (int)"ReleaseAndAcquireReady failed",
        v31);
      *(_DWORD *)(a1 + 28) = 130;
      if ( !(unsigned __int8)CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::ReleaseAndAcquire(
                               v46,
                               *(_QWORD *)(a1 + 32)) )
        break;
      v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v8 > 5u )
      {
        v33 = v47;
        v32 = v2;
        v38 = *(_DWORD *)(*(_QWORD *)a1 + 280LL);
        v35 = "Got new frame buffer to process";
        v36 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v39 = 466;
        v37 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v8,
          (unsigned int)word_18004F58A,
          (_DWORD)v8,
          v9,
          (__int64)&v37,
          (__int64)&v39,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v38,
          (__int64)&v32,
          (__int64)&v33);
      }
      v10 = CRdpIdSwapchain::ProcessSwapChainBuffer<CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>>(
              a1,
              v46);
      if ( v10 < 0 )
      {
        v11 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)a1 + 264LL) + 16LL);
        v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v11 + 312LL))(v11, *v11);
        if ( v12 < 0 )
        {
          v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
          if ( *v13 > 2u )
          {
            v33 = v12;
            v32 = v2;
            v40 = *(_DWORD *)(*(_QWORD *)a1 + 280LL);
            v34 = v10;
            v37 = "Render device encountered an error";
            v36 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
            LODWORD(v41) = 486;
            v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (_DWORD)v13,
              (unsigned int)qword_18004F520,
              (_DWORD)v13,
              v14,
              (__int64)&v35,
              (__int64)&v41,
              (__int64)&v36,
              (__int64)&v37,
              (__int64)&v34,
              (__int64)&v40,
              (__int64)&v32,
              (__int64)&v33);
          }
          LODWORD(v31) = v12;
          Rdp::Modern::Utils::CInflightRecorder::pushN(
            (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
            (wchar_t *)L"Render device removed reason: %#x",
            "CRdpIdSwapchain::SwapchainProcessorMainProc",
            "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
            0x1E7u);
          v15 = *(_QWORD *)(*(_QWORD *)a1 + 232LL);
          if ( *(_BYTE *)(v15 + 512) )
          {
            v18 = wil::verify_hresult<long>((unsigned int)v10);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1EB,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
              (const char *)v18,
              v30);
          }
          CRdpIdAdapter::ReportCriticalError(v15, 3, *(unsigned int *)(a1 + 28), (unsigned int)v10);
        }
      }
      *(_DWORD *)(a1 + 28) = 131;
      v16 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v16 > 5u )
      {
        v33 = v47;
        v32 = v2;
        LODWORD(v42) = *(_DWORD *)(*(_QWORD *)a1 + 280LL);
        v37 = "Finished processing frame";
        v36 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        LODWORD(v43) = 513;
        v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (unsigned int)&byte_18004F4B7,
          (_DWORD)v16,
          v17,
          (__int64)&v35,
          (__int64)&v43,
          (__int64)&v36,
          (__int64)&v37,
          (__int64)&v42,
          (__int64)&v32,
          (__int64)&v33);
      }
    }
    wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v48);
    result = 1;
  }
  catch ( ... )
  {
    v19 = wil::ResultFromCaughtException(v6);
    if ( v19 == -2005270490 )
    {
      v21 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      v23 = v45;
      if ( *v21 > 4u )
      {
        LODWORD(v43) = v45[7];
        LODWORD(v42) = v44;
        LODWORD(v41) = *(_DWORD *)(*(_QWORD *)v45 + 280LL);
        v37 = "The swapchain was abandoned";
        v36 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v34 = 530;
        v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v21,
          (unsigned int)qword_18004F460,
          (_DWORD)v21,
          v22,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v36,
          (__int64)&v37,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43);
      }
    }
    else
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        v20);
      v24 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v24 <= 2u )
      {
        v23 = v45;
      }
      else
      {
        LODWORD(v43) = v19;
        v23 = v45;
        LODWORD(v42) = v45[7];
        LODWORD(v41) = v44;
        v34 = *(_DWORD *)(*(_QWORD *)v45 + 280LL);
        v40 = v19;
        v37 = "The swapchain needs to be closed due to an error";
        v36 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v39 = 541;
        v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (unsigned int)byte_18004F3F5,
          (_DWORD)v24,
          v25,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v36,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v34,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43);
      }
      LODWORD(v29) = v19;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Closing swapchain: hr: %#x",
        "CRdpIdSwapchain::SwapchainProcessorMainProc",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        0x21Eu,
        v29);
      v26 = *(_QWORD *)v23;
      v28 = wil::ResultFromCaughtException(v27);
      CRdpIdMonitor::OnSwapchainFailure(v26, (unsigned int)v23[7], v28);
    }
    (*(void (__fastcall **)(__int64, _QWORD))(WdfFunctions_02025 + 1032))(WdfDriverGlobals, *((_QWORD *)v23 + 4));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180028cdc  push    rbx
0x180028cde  push    rsi
0x180028cdf  push    rdi
0x180028ce0  push    r12
0x180028ce2  push    r14
0x180028ce4  push    r15
0x180028ce6  sub     rsp, 178h
0x180028ced  mov     rax, cs:__security_cookie
0x180028cf4  xor     rax, rsp
0x180028cf7  mov     [rsp+1A8h+var_48], rax
0x180028cff  mov     rbx, rcx
0x180028d02  mov     [rsp+1A8h+var_E0], rcx
0x180028d0a  mov     rax, [rcx]
0x180028d0d  mov     rdx, [rax+0E8h]
0x180028d14  mov     r12d, [rdx+204h]
0x180028d1b  mov     [rsp+1A8h+var_E8], r12d
0x180028d23  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180028d28  mov     r8, [rax+8]
0x180028d2c  mov     eax, [r8]
0x180028d2f  cmp     eax, 5
0x180028d32  jbe     loc_180028DDB
0x180028d38  mov     [rsp+1A8h+var_110], r12d
0x180028d40  mov     rax, [rbx]
0x180028d43  mov     ecx, [rax+118h]
0x180028d49  mov     [rsp+1A8h+var_138], ecx
0x180028d4d  lea     rax, aNewFrameAvaila; "New frame available event triggered"
0x180028d54  mov     [rsp+1A8h+var_F0], rax
0x180028d5c  lea     r14, aCrdpidswapchai_3; "CRdpIdSwapchain::SwapchainProcessorMain"...
0x180028d63  mov     [rsp+1A8h+var_F8], r14
0x180028d6b  mov     [rsp+1A8h+var_134], 1B4h
0x180028d73  lea     rdi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180028d7a  mov     [rsp+1A8h+var_100], rdi
0x180028d82  lea     rax, [rsp+1A8h+var_110]
0x180028d8a  mov     [rsp+1A8h+var_160], rax
0x180028d8f  lea     rax, [rsp+1A8h+var_138]
0x180028d94  mov     [rsp+1A8h+var_168], rax
0x180028d99  lea     rax, [rsp+1A8h+var_F0]
0x180028da1  mov     [rsp+1A8h+var_170], rax
0x180028da6  lea     rax, [rsp+1A8h+var_F8]
0x180028dae  mov     [rsp+1A8h+var_178], rax
0x180028db3  lea     rax, [rsp+1A8h+var_134]
0x180028db8  mov     [rsp+1A8h+var_180], rax
0x180028dbd  lea     rax, [rsp+1A8h+var_100]
0x180028dc5  mov     qword ptr [rsp+1A8h+var_188], rax
0x180028dca  lea     rdx, byte_18004F5F3
0x180028dd1  mov     rcx, r8
0x180028dd4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180028dd9  jmp     short loc_180028DE9
0x180028ddb  lea     r14, aCrdpidswapchai_3; "CRdpIdSwapchain::SwapchainProcessorMain"...
0x180028de2  lea     rdi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180028de9  mov     rdx, [rbx]
0x180028dec  add     rdx, 130h
0x180028df3  lea     rcx, [rsp+1A8h+var_D8]
0x180028dfb  call    ??0?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@QEAA@AEBV?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>(wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy> const &)
0x180028e00  nop
0x180028e01  mov     dword ptr [rbx+1Ch], 81h
0x180028e08  mov     rcx, [rsp+1A8h+var_50]
0x180028e10  mov     rax, [rcx]
0x180028e13  mov     rax, [rax+38h]
0x180028e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e1c  mov     rcx, [rsp+1A8h]; this
0x180028e24  lea     rdx, aReleaseandacqu; "ReleaseAndAcquireReady failed"
0x180028e2b  mov     qword ptr [rsp+1A8h+var_188], rdx; int
0x180028e30  mov     r9d, eax; char *
0x180028e33  lea     r8, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180028e3a  mov     edx, 76h ; 'v'; void *
0x180028e3f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180028e44  mov     dword ptr [rbx+1Ch], 82h
0x180028e4b  mov     rdx, [rbx+20h]
0x180028e4f  lea     rcx, [rsp+1A8h+var_D8]
0x180028e57  call    ?ReleaseAndAcquire@?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@QEAA_NPEAUIDDCX_SWAPCHAIN__@@@Z; CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::ReleaseAndAcquire(IDDCX_SWAPCHAIN__ *)
0x180028e5c  test    al, al
0x180028e5e  jnz     short loc_180028E75
0x180028e60  lea     rcx, [rsp+1A8h+var_50]
0x180028e68  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180028e6d  nop
0x180028e6e  mov     al, 1
0x180028e70  jmp     loc_180029164
0x180028e75  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180028e7a  mov     r8, [rax+8]
0x180028e7e  mov     eax, [r8]
0x180028e81  cmp     eax, 5
0x180028e84  jbe     loc_180028F38
0x180028e8a  mov     eax, [rsp+1A8h+var_C0]
0x180028e91  mov     [rsp+1A8h+var_134], eax
0x180028e95  mov     [rsp+1A8h+var_138], r12d
0x180028e9a  mov     rax, [rbx]
0x180028e9d  mov     ecx, [rax+118h]
0x180028ea3  mov     [rsp+1A8h+var_110], ecx
0x180028eaa  lea     rax, aGotNewFrameBuf; "Got new frame buffer to process"
0x180028eb1  mov     [rsp+1A8h+var_128], rax
0x180028eb9  mov     [rsp+1A8h+var_120], r14
0x180028ec1  mov     [rsp+1A8h+var_10C], 1D2h
0x180028ecc  mov     [rsp+1A8h+var_118], rdi
0x180028ed4  lea     rax, [rsp+1A8h+var_134]
0x180028ed9  mov     [rsp+1A8h+var_158], rax
0x180028ede  lea     rax, [rsp+1A8h+var_138]
0x180028ee3  mov     [rsp+1A8h+var_160], rax
0x180028ee8  lea     rax, [rsp+1A8h+var_110]
0x180028ef0  mov     [rsp+1A8h+var_168], rax
0x180028ef5  lea     rax, [rsp+1A8h+var_128]
0x180028efd  mov     [rsp+1A8h+var_170], rax
0x180028f02  lea     rax, [rsp+1A8h+var_120]
0x180028f0a  mov     [rsp+1A8h+var_178], rax
0x180028f0f  lea     rax, [rsp+1A8h+var_10C]
0x180028f17  mov     [rsp+1A8h+var_180], rax
0x180028f1c  lea     rax, [rsp+1A8h+var_118]
0x180028f24  mov     qword ptr [rsp+1A8h+var_188], rax
0x180028f29  lea     rdx, word_18004F58A
0x180028f30  mov     rcx, r8
0x180028f33  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180028f38  lea     rdx, [rsp+1A8h+var_D8]
0x180028f40  mov     rcx, rbx
0x180028f43  call    ??$ProcessSwapChainBuffer@V?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@@CRdpIdSwapchain@@AEAAJAEAV?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@@Z; CRdpIdSwapchain::ProcessSwapChainBuffer<CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>>(CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer> &)
0x180028f48  mov     esi, eax
0x180028f4a  test    eax, eax
0x180028f4c  jns     loc_180029093
0x180028f52  mov     rcx, [rbx]
0x180028f55  mov     rdx, [rcx+108h]
0x180028f5c  mov     rcx, [rdx+10h]
0x180028f60  mov     rdx, [rcx]
0x180028f63  mov     rax, [rdx+138h]
0x180028f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f6f  mov     r15d, eax
0x180028f72  test    eax, eax
0x180028f74  jns     loc_180029093
0x180028f7a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180028f7f  mov     r8, [rax+8]
0x180028f83  mov     ecx, [r8]
0x180028f86  cmp     ecx, 2
0x180028f89  jbe     loc_180029045
0x180028f8f  mov     [rsp+1A8h+var_134], r15d
0x180028f94  mov     [rsp+1A8h+var_138], r12d
0x180028f99  mov     rax, [rbx]
0x180028f9c  mov     ecx, [rax+118h]
0x180028fa2  mov     [rsp+1A8h+var_108], ecx
0x180028fa9  mov     [rsp+1A8h+var_130], esi
0x180028fad  lea     rax, aRenderDeviceEn; "Render device encountered an error"
0x180028fb4  mov     [rsp+1A8h+var_118], rax
0x180028fbc  mov     [rsp+1A8h+var_120], r14
0x180028fc4  mov     dword ptr [rsp+1A8h+var_100], 1E6h
0x180028fcf  mov     [rsp+1A8h+var_128], rdi
0x180028fd7  lea     rax, [rsp+1A8h+var_134]
0x180028fdc  mov     [rsp+1A8h+var_150], rax
0x180028fe1  lea     rax, [rsp+1A8h+var_138]
0x180028fe6  mov     [rsp+1A8h+var_158], rax
0x180028feb  lea     rax, [rsp+1A8h+var_108]
0x180028ff3  mov     [rsp+1A8h+var_160], rax
0x180028ff8  lea     rax, [rsp+1A8h+var_130]
0x180028ffd  mov     [rsp+1A8h+var_168], rax
0x180029002  lea     rax, [rsp+1A8h+var_118]
0x18002900a  mov     [rsp+1A8h+var_170], rax
0x18002900f  lea     rax, [rsp+1A8h+var_120]
0x180029017  mov     [rsp+1A8h+var_178], rax
0x18002901c  lea     rax, [rsp+1A8h+var_100]
0x180029024  mov     [rsp+1A8h+var_180], rax
0x180029029  lea     rax, [rsp+1A8h+var_128]
0x180029031  mov     qword ptr [rsp+1A8h+var_188], rax
0x180029036  lea     rdx, qword_18004F520
0x18002903d  mov     rcx, r8
0x180029040  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029045  mov     dword ptr [rsp+1A8h+var_180], r15d
0x18002904a  mov     [rsp+1A8h+var_188], 1E7h; int
0x180029052  mov     r9, rdi; char *
0x180029055  mov     r8, r14; char *
0x180029058  lea     rdx, aRenderDeviceRe; "Render device removed reason: %#x"
0x18002905f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180029066  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002906b  mov     rax, [rbx]
0x18002906e  mov     rcx, [rax+0E8h]
0x180029075  cmp     byte ptr [rcx+200h], 0
0x18002907c  jnz     loc_180029186
0x180029082  mov     r9d, esi
0x180029085  mov     r8d, [rbx+1Ch]
0x180029089  mov     edx, 3
0x18002908e  call    ?ReportCriticalError@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalError(FailFastMajorCode,uint,long)
0x180029093  mov     dword ptr [rbx+1Ch], 83h
0x18002909a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002909f  mov     r8, [rax+8]
0x1800290a3  mov     eax, [r8]
0x1800290a6  cmp     eax, 5
0x1800290a9  jbe     loc_180028E01
0x1800290af  mov     eax, [rsp+1A8h+var_C0]
0x1800290b6  mov     [rsp+1A8h+var_134], eax
0x1800290ba  mov     [rsp+1A8h+var_138], r12d
0x1800290bf  mov     rax, [rbx]
0x1800290c2  mov     ecx, [rax+118h]
0x1800290c8  mov     dword ptr [rsp+1A8h+var_F8], ecx
0x1800290cf  lea     rax, aFinishedProces; "Finished processing frame"
0x1800290d6  mov     [rsp+1A8h+var_118], rax
0x1800290de  mov     [rsp+1A8h+var_120], r14
0x1800290e6  mov     dword ptr [rsp+1A8h+var_F0], 201h
0x1800290f1  mov     [rsp+1A8h+var_128], rdi
0x1800290f9  lea     rax, [rsp+1A8h+var_134]
0x1800290fe  mov     [rsp+1A8h+var_158], rax
0x180029103  lea     rax, [rsp+1A8h+var_138]
0x180029108  mov     [rsp+1A8h+var_160], rax
0x18002910d  lea     rax, [rsp+1A8h+var_F8]
0x180029115  mov     [rsp+1A8h+var_168], rax
0x18002911a  lea     rax, [rsp+1A8h+var_118]
0x180029122  mov     [rsp+1A8h+var_170], rax
0x180029127  lea     rax, [rsp+1A8h+var_120]
0x18002912f  mov     [rsp+1A8h+var_178], rax
0x180029134  lea     rax, [rsp+1A8h+var_F0]
0x18002913c  mov     [rsp+1A8h+var_180], rax
0x180029141  lea     rax, [rsp+1A8h+var_128]
0x180029149  mov     qword ptr [rsp+1A8h+var_188], rax
0x18002914e  lea     rdx, byte_18004F4B7
0x180029155  mov     rcx, r8
0x180029158  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002915d  jmp     loc_180028E01
0x180029162  xor     al, al
0x180029164  mov     rcx, [rsp+1A8h+var_48]
0x18002916c  xor     rcx, rsp; StackCookie
0x18002916f  call    __security_check_cookie
0x180029174  add     rsp, 178h
0x18002917b  pop     r15
0x18002917d  pop     r14
0x18002917f  pop     r12
0x180029181  pop     rdi
0x180029182  pop     rsi
0x180029183  pop     rbx
0x180029184  retn
0x180029186  mov     ecx, esi
0x180029188  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002918d  mov     r9d, eax; char *
0x180029190  mov     rcx, [rsp+1A8h]; this
0x180029198  mov     r8, rdi; unsigned int
0x18002919b  mov     edx, 1EBh; void *
0x1800291a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
