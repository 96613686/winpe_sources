# CRdpIdSwapchain::SwapchainProcessorMainProc<CSwapChainProcessor<Rdp::Avenc::IGpuFrameProcessor,CFrameDxBuffer>>(void)

- ea: `0x1800291b0`
- end: `0x1800296f6`
- name: `??$SwapchainProcessorMainProc@V?$CSwapChainProcessor@UIGpuFrameProcessor@Avenc@Rdp@@VCFrameDxBuffer@@@@@CRdpIdSwapchain@@AEAA_NXZ`
- size: `1350`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d360`

## callees

- `0x180001bc4`
- `0x180004fa8`
- `0x1800050e4`
- `0x180006f60`
- `0x180007b38`
- `0x1800089f0`
- `0x18000d614`
- `0x18000ead8`
- `0x18001cd04`
- `0x18001dd50`
- `0x18001ddf4`
- `0x180021570`
- `0x180028830`
- `0x1800291b0`
- `0x18002c5e0`
- `0x18003f010`

## string_xrefs

- `0x1800296c3`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180029592`: `Render device removed reason: %#x`
- `0x18002935e`: `ReleaseAndAcquireReady failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CRdpIdSwapchain::SwapchainProcessorMainProc<CSwapChainProcessor<Rdp::Avenc::IGpuFrameProcessor,CFrameDxBuffer>>(
        __int64 *a1)
{
  int v2; // r12d
  _DWORD *v3; // r8
  int v4; // r9d
  __int64 v5; // rbx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  unsigned int v8; // eax
  wil *v9; // rcx
  char result; // al
  _DWORD *v11; // r8
  int v12; // r9d
  int v13; // ebx
  _QWORD *v14; // rcx
  int v15; // r15d
  _DWORD *v16; // r8
  int v17; // r9d
  __int64 v18; // rcx
  _DWORD *v19; // r8
  int v20; // r9d
  unsigned int v21; // eax
  int v22; // ebx
  const char *v23; // r9
  _DWORD *v24; // r8
  int v25; // r9d
  _DWORD *v26; // rdi
  _DWORD *v27; // r8
  int v28; // r9d
  __int64 v29; // rbx
  wil *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // [rsp+28h] [rbp-180h]
  int v33; // [rsp+20h] [rbp-188h]
  int v34; // [rsp+20h] [rbp-188h]
  const char *v35; // [rsp+28h] [rbp-180h]
  int v36; // [rsp+70h] [rbp-138h] BYREF
  int v37; // [rsp+74h] [rbp-134h] BYREF
  int v38; // [rsp+78h] [rbp-130h] BYREF
  const char *v39; // [rsp+80h] [rbp-128h] BYREF
  const char *v40; // [rsp+88h] [rbp-120h] BYREF
  const char *v41; // [rsp+90h] [rbp-118h] BYREF
  int v42; // [rsp+98h] [rbp-110h] BYREF
  int v43; // [rsp+9Ch] [rbp-10Ch] BYREF
  int v44; // [rsp+A0h] [rbp-108h] BYREF
  const char *v45; // [rsp+A8h] [rbp-100h] BYREF
  const char *v46; // [rsp+B0h] [rbp-F8h] BYREF
  const char *v47; // [rsp+B8h] [rbp-F0h] BYREF
  int v48; // [rsp+C0h] [rbp-E8h]
  _DWORD *v49; // [rsp+C8h] [rbp-E0h]
  __int128 v50; // [rsp+D0h] [rbp-D8h] BYREF
  _BYTE v51[8]; // [rsp+E0h] [rbp-C8h] BYREF
  int v52; // [rsp+E8h] [rbp-C0h]
  __int64 v53; // [rsp+158h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v49 = a1;
  v2 = *(_DWORD *)(*(_QWORD *)(*a1 + 232) + 516LL);
  v48 = v2;
  v3 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v3 > 5u )
  {
    v42 = v2;
    v36 = *(_DWORD *)(*a1 + 280);
    v47 = "New frame available event triggered";
    v46 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
    v37 = 436;
    v45 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v3,
      (unsigned int)byte_18004F3A5,
      (_DWORD)v3,
      v4,
      (__int64)&v45,
      (__int64)&v37,
      (__int64)&v46,
      (__int64)&v47,
      (__int64)&v36,
      (__int64)&v42);
  }
  v5 = *a1;
  v50 = 0;
  memset_0(v51, 0, 0x78u);
  try
  {
    *(_QWORD *)&v50 = 16;
    v53 = 0;
    v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 304);
    if ( v6 )
    {
      v7 = (**v6)(v6, &GUID_69d16ddb_b90e_47d0_865d_b8f17e7dad6d, &v53);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
          (const char *)(unsigned int)v7,
          v33);
    }
    else
    {
      v53 = 0;
    }
    while ( 1 )
    {
      *((_DWORD *)a1 + 7) = 129;
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 56LL))(v53);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\Swapchain.h",
        (const char *)v8,
        (int)"ReleaseAndAcquireReady failed",
        v35);
      *((_DWORD *)a1 + 7) = 130;
      if ( !(unsigned __int8)CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::ReleaseAndAcquire(
                               &v50,
                               a1[4]) )
        break;
      v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v11 > 5u )
      {
        v37 = v52;
        v36 = v2;
        v42 = *(_DWORD *)(*a1 + 280);
        v39 = "Got new frame buffer to process";
        v40 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v43 = 466;
        v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v11,
          (unsigned int)&dword_18004F33C,
          (_DWORD)v11,
          v12,
          (__int64)&v41,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v42,
          (__int64)&v36,
          (__int64)&v37);
      }
      v13 = CRdpIdSwapchain::ProcessSwapChainBuffer<CSwapChainProcessor<Rdp::Avenc::IGpuFrameProcessor,CFrameDxBuffer>>(
              a1,
              &v50);
      if ( v13 < 0 )
      {
        v14 = *(_QWORD **)(*(_QWORD *)(*a1 + 264) + 16LL);
        v15 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v14 + 312LL))(v14, *v14);
        if ( v15 < 0 )
        {
          v16 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
          if ( *v16 > 2u )
          {
            v37 = v15;
            v36 = v2;
            v44 = *(_DWORD *)(*a1 + 280);
            v38 = v13;
            v41 = "Render device encountered an error";
            v40 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
            LODWORD(v45) = 486;
            v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (_DWORD)v16,
              (unsigned int)word_18004F2D2,
              (_DWORD)v16,
              v17,
              (__int64)&v39,
              (__int64)&v45,
              (__int64)&v40,
              (__int64)&v41,
              (__int64)&v38,
              (__int64)&v44,
              (__int64)&v36,
              (__int64)&v37);
          }
          LODWORD(v35) = v15;
          Rdp::Modern::Utils::CInflightRecorder::pushN(
            (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
            (wchar_t *)L"Render device removed reason: %#x",
            "CRdpIdSwapchain::SwapchainProcessorMainProc",
            "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
            0x1E7u);
          v18 = *(_QWORD *)(*a1 + 232);
          if ( *(_BYTE *)(v18 + 512) )
          {
            v21 = wil::verify_hresult<long>((unsigned int)v13);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1EB,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
              (const char *)v21,
              v34);
          }
          CRdpIdAdapter::ReportCriticalError(v18, 3, *((unsigned int *)a1 + 7), (unsigned int)v13);
        }
      }
      *((_DWORD *)a1 + 7) = 131;
      v19 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v19 > 5u )
      {
        v37 = v52;
        v36 = v2;
        LODWORD(v46) = *(_DWORD *)(*a1 + 280);
        v41 = "Finished processing frame";
        v40 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        LODWORD(v47) = 513;
        v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v19,
          (unsigned int)byte_18004F269,
          (_DWORD)v19,
          v20,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v46,
          (__int64)&v36,
          (__int64)&v37);
      }
    }
    wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v53);
    result = 1;
  }
  catch ( ... )
  {
    v22 = wil::ResultFromCaughtException(v9);
    if ( v22 == -2005270490 )
    {
      v24 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      v26 = v49;
      if ( *v24 > 4u )
      {
        LODWORD(v47) = v49[7];
        LODWORD(v46) = v48;
        LODWORD(v45) = *(_DWORD *)(*(_QWORD *)v49 + 280LL);
        v41 = "The swapchain was abandoned";
        v40 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v38 = 530;
        v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (unsigned int)word_18004F212,
          (_DWORD)v24,
          v25,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47);
      }
    }
    else
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        v23);
      v27 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v27 <= 2u )
      {
        v26 = v49;
      }
      else
      {
        LODWORD(v47) = v22;
        v26 = v49;
        LODWORD(v46) = v49[7];
        LODWORD(v45) = v48;
        v38 = *(_DWORD *)(*(_QWORD *)v49 + 280LL);
        v44 = v22;
        v41 = "The swapchain needs to be closed due to an error";
        v40 = "CRdpIdSwapchain::SwapchainProcessorMainProc";
        v43 = 541;
        v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v27,
          (unsigned int)&byte_18004F1A7,
          (_DWORD)v27,
          v28,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v44,
          (__int64)&v38,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47);
      }
      LODWORD(v32) = v22;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Closing swapchain: hr: %#x",
        "CRdpIdSwapchain::SwapchainProcessorMainProc",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        0x21Eu,
        v32);
      v29 = *(_QWORD *)v26;
      v31 = wil::ResultFromCaughtException(v30);
      CRdpIdMonitor::OnSwapchainFailure(v29, (unsigned int)v26[7], v31);
    }
    (*(void (__fastcall **)(__int64, _QWORD))(WdfFunctions_02025 + 1032))(WdfDriverGlobals, *((_QWORD *)v26 + 4));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800291b0  push    rbx
0x1800291b2  push    rsi
0x1800291b3  push    rdi
0x1800291b4  push    r12
0x1800291b6  push    r14
0x1800291b8  push    r15
0x1800291ba  sub     rsp, 178h
0x1800291c1  mov     rax, cs:__security_cookie
0x1800291c8  xor     rax, rsp
0x1800291cb  mov     [rsp+1A8h+var_48], rax
0x1800291d3  mov     rdi, rcx
0x1800291d6  mov     [rsp+1A8h+var_E0], rcx
0x1800291de  mov     rax, [rcx]
0x1800291e1  mov     rdx, [rax+0E8h]
0x1800291e8  mov     r12d, [rdx+204h]
0x1800291ef  mov     [rsp+1A8h+var_E8], r12d
0x1800291f7  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800291fc  mov     r8, [rax+8]
0x180029200  mov     eax, [r8]
0x180029203  cmp     eax, 5
0x180029206  jbe     loc_1800292AF
0x18002920c  mov     [rsp+1A8h+var_110], r12d
0x180029214  mov     rax, [rdi]
0x180029217  mov     ecx, [rax+118h]
0x18002921d  mov     [rsp+1A8h+var_138], ecx
0x180029221  lea     rax, aNewFrameAvaila; "New frame available event triggered"
0x180029228  mov     [rsp+1A8h+var_F0], rax
0x180029230  lea     r14, aCrdpidswapchai_3; "CRdpIdSwapchain::SwapchainProcessorMain"...
0x180029237  mov     [rsp+1A8h+var_F8], r14
0x18002923f  mov     [rsp+1A8h+var_134], 1B4h
0x180029247  lea     rsi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002924e  mov     [rsp+1A8h+var_100], rsi
0x180029256  lea     rax, [rsp+1A8h+var_110]
0x18002925e  mov     [rsp+1A8h+var_160], rax
0x180029263  lea     rax, [rsp+1A8h+var_138]
0x180029268  mov     [rsp+1A8h+var_168], rax
0x18002926d  lea     rax, [rsp+1A8h+var_F0]
0x180029275  mov     [rsp+1A8h+var_170], rax
0x18002927a  lea     rax, [rsp+1A8h+var_F8]
0x180029282  mov     [rsp+1A8h+var_178], rax
0x180029287  lea     rax, [rsp+1A8h+var_134]
0x18002928c  mov     [rsp+1A8h+var_180], rax
0x180029291  lea     rax, [rsp+1A8h+var_100]
0x180029299  mov     qword ptr [rsp+1A8h+var_188], rax
0x18002929e  lea     rdx, byte_18004F3A5
0x1800292a5  mov     rcx, r8
0x1800292a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800292ad  jmp     short loc_1800292BD
0x1800292af  lea     r14, aCrdpidswapchai_3; "CRdpIdSwapchain::SwapchainProcessorMain"...
0x1800292b6  lea     rsi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800292bd  mov     rbx, [rdi]
0x1800292c0  xorps   xmm0, xmm0
0x1800292c3  movups  [rsp+1A8h+var_D8], xmm0
0x1800292cb  xor     edx, edx; Val
0x1800292cd  lea     r8d, [rdx+78h]; Size
0x1800292d1  lea     rcx, [rsp+1A8h+var_C8]; void *
0x1800292d9  call    memset_0
0x1800292de  nop
0x1800292df  mov     qword ptr [rsp+1A8h+var_D8], 10h
0x1800292eb  mov     [rsp+1A8h+var_50], 0
0x1800292f7  mov     rcx, [rbx+130h]
0x1800292fe  test    rcx, rcx
0x180029301  jz      short loc_18002932F
0x180029303  mov     rax, [rcx]
0x180029306  lea     r8, [rsp+1A8h+var_50]
0x18002930e  lea     rdx, _GUID_69d16ddb_b90e_47d0_865d_b8f17e7dad6d
0x180029315  mov     rax, [rax]
0x180029318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002931d  mov     rcx, [rsp+1A8h]; this
0x180029325  test    eax, eax
0x180029327  js      loc_1800296C0
0x18002932d  jmp     short loc_18002933B
0x18002932f  mov     [rsp+1A8h+var_50], 0
0x18002933b  mov     dword ptr [rdi+1Ch], 81h
0x180029342  mov     rcx, [rsp+1A8h+var_50]
0x18002934a  mov     rax, [rcx]
0x18002934d  mov     rax, [rax+38h]
0x180029351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029356  mov     rcx, [rsp+1A8h]; this
0x18002935e  lea     rdx, aReleaseandacqu; "ReleaseAndAcquireReady failed"
0x180029365  mov     qword ptr [rsp+1A8h+var_188], rdx; int
0x18002936a  mov     r9d, eax; char *
0x18002936d  lea     r8, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180029374  mov     edx, 76h ; 'v'; void *
0x180029379  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002937e  mov     dword ptr [rdi+1Ch], 82h
0x180029385  mov     rdx, [rdi+20h]
0x180029389  lea     rcx, [rsp+1A8h+var_D8]
0x180029391  call    ?ReleaseAndAcquire@?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@QEAA_NPEAUIDDCX_SWAPCHAIN__@@@Z; CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::ReleaseAndAcquire(IDDCX_SWAPCHAIN__ *)
0x180029396  test    al, al
0x180029398  jnz     short loc_1800293AF
0x18002939a  lea     rcx, [rsp+1A8h+var_50]
0x1800293a2  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800293a7  nop
0x1800293a8  mov     al, 1
0x1800293aa  jmp     loc_18002969E
0x1800293af  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800293b4  mov     r8, [rax+8]
0x1800293b8  mov     eax, [r8]
0x1800293bb  cmp     eax, 5
0x1800293be  jbe     loc_180029472
0x1800293c4  mov     eax, [rsp+1A8h+var_C0]
0x1800293cb  mov     [rsp+1A8h+var_134], eax
0x1800293cf  mov     [rsp+1A8h+var_138], r12d
0x1800293d4  mov     rax, [rdi]
0x1800293d7  mov     ecx, [rax+118h]
0x1800293dd  mov     [rsp+1A8h+var_110], ecx
0x1800293e4  lea     rax, aGotNewFrameBuf; "Got new frame buffer to process"
0x1800293eb  mov     [rsp+1A8h+var_128], rax
0x1800293f3  mov     [rsp+1A8h+var_120], r14
0x1800293fb  mov     [rsp+1A8h+var_10C], 1D2h
0x180029406  mov     [rsp+1A8h+var_118], rsi
0x18002940e  lea     rax, [rsp+1A8h+var_134]
0x180029413  mov     [rsp+1A8h+var_158], rax
0x180029418  lea     rax, [rsp+1A8h+var_138]
0x18002941d  mov     [rsp+1A8h+var_160], rax
0x180029422  lea     rax, [rsp+1A8h+var_110]
0x18002942a  mov     [rsp+1A8h+var_168], rax
0x18002942f  lea     rax, [rsp+1A8h+var_128]
0x180029437  mov     [rsp+1A8h+var_170], rax
0x18002943c  lea     rax, [rsp+1A8h+var_120]
0x180029444  mov     [rsp+1A8h+var_178], rax
0x180029449  lea     rax, [rsp+1A8h+var_10C]
0x180029451  mov     [rsp+1A8h+var_180], rax
0x180029456  lea     rax, [rsp+1A8h+var_118]
0x18002945e  mov     qword ptr [rsp+1A8h+var_188], rax
0x180029463  lea     rdx, dword_18004F33C
0x18002946a  mov     rcx, r8
0x18002946d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029472  lea     rdx, [rsp+1A8h+var_D8]
0x18002947a  mov     rcx, rdi
0x18002947d  call    ??$ProcessSwapChainBuffer@V?$CSwapChainProcessor@UIGpuFrameProcessor@Avenc@Rdp@@VCFrameDxBuffer@@@@@CRdpIdSwapchain@@AEAAJAEAV?$CSwapChainProcessor@UIGpuFrameProcessor@Avenc@Rdp@@VCFrameDxBuffer@@@@@Z; CRdpIdSwapchain::ProcessSwapChainBuffer<CSwapChainProcessor<Rdp::Avenc::IGpuFrameProcessor,CFrameDxBuffer>>(CSwapChainProcessor<Rdp::Avenc::IGpuFrameProcessor,CFrameDxBuffer> &)
0x180029482  mov     ebx, eax
0x180029484  test    eax, eax
0x180029486  jns     loc_1800295CD
0x18002948c  mov     rcx, [rdi]
0x18002948f  mov     rdx, [rcx+108h]
0x180029496  mov     rcx, [rdx+10h]
0x18002949a  mov     rdx, [rcx]
0x18002949d  mov     rax, [rdx+138h]
0x1800294a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294a9  mov     r15d, eax
0x1800294ac  test    eax, eax
0x1800294ae  jns     loc_1800295CD
0x1800294b4  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800294b9  mov     r8, [rax+8]
0x1800294bd  mov     ecx, [r8]
0x1800294c0  cmp     ecx, 2
0x1800294c3  jbe     loc_18002957F
0x1800294c9  mov     [rsp+1A8h+var_134], r15d
0x1800294ce  mov     [rsp+1A8h+var_138], r12d
0x1800294d3  mov     rax, [rdi]
0x1800294d6  mov     ecx, [rax+118h]
0x1800294dc  mov     [rsp+1A8h+var_108], ecx
0x1800294e3  mov     [rsp+1A8h+var_130], ebx
0x1800294e7  lea     rax, aRenderDeviceEn; "Render device encountered an error"
0x1800294ee  mov     [rsp+1A8h+var_118], rax
0x1800294f6  mov     [rsp+1A8h+var_120], r14
0x1800294fe  mov     dword ptr [rsp+1A8h+var_100], 1E6h
0x180029509  mov     [rsp+1A8h+var_128], rsi
0x180029511  lea     rax, [rsp+1A8h+var_134]
0x180029516  mov     [rsp+1A8h+var_150], rax
0x18002951b  lea     rax, [rsp+1A8h+var_138]
0x180029520  mov     [rsp+1A8h+var_158], rax
0x180029525  lea     rax, [rsp+1A8h+var_108]
0x18002952d  mov     [rsp+1A8h+var_160], rax
0x180029532  lea     rax, [rsp+1A8h+var_130]
0x180029537  mov     [rsp+1A8h+var_168], rax
0x18002953c  lea     rax, [rsp+1A8h+var_118]
0x180029544  mov     [rsp+1A8h+var_170], rax
0x180029549  lea     rax, [rsp+1A8h+var_120]
0x180029551  mov     [rsp+1A8h+var_178], rax
0x180029556  lea     rax, [rsp+1A8h+var_100]
0x18002955e  mov     [rsp+1A8h+var_180], rax
0x180029563  lea     rax, [rsp+1A8h+var_128]
0x18002956b  mov     qword ptr [rsp+1A8h+var_188], rax
0x180029570  lea     rdx, word_18004F2D2
0x180029577  mov     rcx, r8
0x18002957a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002957f  mov     dword ptr [rsp+1A8h+var_180], r15d
0x180029584  mov     [rsp+1A8h+var_188], 1E7h; int
0x18002958c  mov     r9, rsi; char *
0x18002958f  mov     r8, r14; char *
0x180029592  lea     rdx, aRenderDeviceRe; "Render device removed reason: %#x"
0x180029599  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800295a0  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800295a5  mov     rax, [rdi]
0x1800295a8  mov     rcx, [rax+0E8h]
0x1800295af  cmp     byte ptr [rcx+200h], 0
0x1800295b6  jnz     loc_1800296D5
0x1800295bc  mov     r9d, ebx
0x1800295bf  mov     r8d, [rdi+1Ch]
0x1800295c3  mov     edx, 3
0x1800295c8  call    ?ReportCriticalError@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalError(FailFastMajorCode,uint,long)
0x1800295cd  mov     dword ptr [rdi+1Ch], 83h
0x1800295d4  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800295d9  mov     r8, [rax+8]
0x1800295dd  mov     eax, [r8]
0x1800295e0  cmp     eax, 5
0x1800295e3  jbe     loc_18002933B
0x1800295e9  mov     eax, [rsp+1A8h+var_C0]
0x1800295f0  mov     [rsp+1A8h+var_134], eax
0x1800295f4  mov     [rsp+1A8h+var_138], r12d
0x1800295f9  mov     rax, [rdi]
0x1800295fc  mov     ecx, [rax+118h]
0x180029602  mov     dword ptr [rsp+1A8h+var_F8], ecx
0x180029609  lea     rax, aFinishedProces; "Finished processing frame"
0x180029610  mov     [rsp+1A8h+var_118], rax
0x180029618  mov     [rsp+1A8h+var_120], r14
0x180029620  mov     dword ptr [rsp+1A8h+var_F0], 201h
0x18002962b  mov     [rsp+1A8h+var_128], rsi
0x180029633  lea     rax, [rsp+1A8h+var_134]
0x180029638  mov     [rsp+1A8h+var_158], rax
0x18002963d  lea     rax, [rsp+1A8h+var_138]
0x180029642  mov     [rsp+1A8h+var_160], rax
0x180029647  lea     rax, [rsp+1A8h+var_F8]
0x18002964f  mov     [rsp+1A8h+var_168], rax
0x180029654  lea     rax, [rsp+1A8h+var_118]
0x18002965c  mov     [rsp+1A8h+var_170], rax
0x180029661  lea     rax, [rsp+1A8h+var_120]
0x180029669  mov     [rsp+1A8h+var_178], rax
0x18002966e  lea     rax, [rsp+1A8h+var_F0]
0x180029676  mov     [rsp+1A8h+var_180], rax
0x18002967b  lea     rax, [rsp+1A8h+var_128]
0x180029683  mov     qword ptr [rsp+1A8h+var_188], rax
0x180029688  lea     rdx, byte_18004F269
0x18002968f  mov     rcx, r8
0x180029692  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029697  jmp     loc_18002933B
0x18002969c  xor     al, al
0x18002969e  mov     rcx, [rsp+1A8h+var_48]
0x1800296a6  xor     rcx, rsp; StackCookie
0x1800296a9  call    __security_check_cookie
0x1800296ae  add     rsp, 178h
0x1800296b5  pop     r15
0x1800296b7  pop     r14
0x1800296b9  pop     r12
0x1800296bb  pop     rdi
0x1800296bc  pop     rsi
0x1800296bd  pop     rbx
0x1800296be  retn
0x1800296c0  mov     r9d, eax; char *
0x1800296c3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800296ca  mov     edx, 1CBEh; void *
0x1800296cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800296d5  mov     ecx, ebx
0x1800296d7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800296dc  mov     r9d, eax; char *
0x1800296df  mov     rcx, [rsp+1A8h]; this
0x1800296e7  mov     r8, rsi; unsigned int
0x1800296ea  mov     edx, 1EBh; void *
0x1800296ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
