# CRdpIdSwapchain::Initialize(_LUID const &)

- ea: `0x18002badc`
- end: `0x18002c0d9`
- name: `?Initialize@CRdpIdSwapchain@@QEAA_NAEBU_LUID@@@Z`
- size: `1533`
- prototype: `bool(CRdpIdSwapchain *__hidden this, const struct _LUID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a054`

## callees

- `0x180001bc4`
- `0x180004588`
- `0x1800053a8`
- `0x1800089f0`
- `0x18000d614`
- `0x18001072c`
- `0x180013bb0`
- `0x18001cd04`
- `0x18001ddbc`
- `0x18001ddf4`
- `0x180021570`
- `0x180023b6c`
- `0x18002b6c8`
- `0x18002badc`
- `0x18003f010`

## string_xrefs

- `0x18002bb88`: `AssignRenderAdapter complete`
- `0x18002bc4c`: `AssignRenderAdapter complete: %x.%x, Id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CRdpIdSwapchain::Initialize(CRdpIdMonitor **this, const struct _LUID *a2)
{
  __int64 v4; // rsi
  _DWORD *v5; // r8
  int v6; // r9d
  unsigned int v7; // eax
  _DWORD *v8; // r8
  int v9; // r9d
  const char *v10; // r9
  bool result; // al
  int v12; // eax
  _DWORD *v13; // r8
  int v14; // r9d
  CRdpIdMonitor *v15; // rcx
  int v16; // eax
  _DWORD *v17; // r8
  int v18; // r9d
  unsigned int v19; // eax
  __int64 v20; // rbx
  wil *v21; // rcx
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-B8h]
  char *v24; // [rsp+28h] [rbp-B0h]
  char *v25; // [rsp+28h] [rbp-B0h]
  char *v26; // [rsp+28h] [rbp-B0h]
  __int64 v27; // [rsp+30h] [rbp-A8h]
  __int64 v28; // [rsp+38h] [rbp-A0h]
  int v29; // [rsp+60h] [rbp-78h] BYREF
  const char *v30; // [rsp+68h] [rbp-70h] BYREF
  const char *v31; // [rsp+70h] [rbp-68h] BYREF
  const char *v32; // [rsp+78h] [rbp-60h] BYREF
  struct IDXGIDevice2 *v33; // [rsp+80h] [rbp-58h] BYREF
  const char *v34; // [rsp+88h] [rbp-50h] BYREF
  struct IDXGIDevice2 *DxgiDevice; // [rsp+90h] [rbp-48h] BYREF
  const char *v36; // [rsp+98h] [rbp-40h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-38h] BYREF
  std::_Ref_count_base *v38; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v41; // [rsp+F0h] [rbp+18h] BYREF
  int v42; // [rsp+F8h] [rbp+20h] BYREF

  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(&v37, (char *)*this + 232);
  try
  {
    v4 = v37;
    if ( *(_DWORD *)(v37 + 440) == 3 )
      CRdpIdAdapter::ReportCriticalError(v37, 3, 1, 2147549183LL);
    CRdpIdMonitor::AssignRenderAdapter(*this, a2, (enum SwapChainThreadStage *)((char *)this + 28));
    v5 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v5 > 4u )
    {
      v33 = *(struct IDXGIDevice2 **)(v4 + 520);
      v41 = *((_DWORD *)*this + 70);
      v42 = *(_DWORD *)(v4 + 516);
      v30 = "AssignRenderAdapter complete";
      v31 = "CRdpIdSwapchain::Initialize";
      v29 = 156;
      v32 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v5,
        (unsigned int)&dword_18004F7FC,
        (_DWORD)v5,
        v6,
        (__int64)&v32,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v33);
    }
    LODWORD(v28) = *((_DWORD *)*this + 70);
    LODWORD(v27) = a2->LowPart;
    LODWORD(v24) = a2->HighPart;
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"AssignRenderAdapter complete: %x.%x, Id %d",
      "CRdpIdSwapchain::Initialize",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
      0xA0u,
      v24,
      v27,
      v28);
    *((_DWORD *)this + 7) = 4;
    DxgiDevice = 0;
    DxgiDevice = Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(*((Rdp::Utils::Graphics::CRenderDevice **)*this + 33));
    v7 = ((__int64 (__fastcall *)(__int64, CRdpIdMonitor *, struct IDXGIDevice2 **))qword_180057B60)(
           IddDriverGlobals,
           this[4],
           &DxgiDevice);
    if ( v7 == -2005270490 )
    {
      v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v8 > 4u )
      {
        v41 = *((_DWORD *)*this + 70);
        v42 = *(_DWORD *)(v4 + 516);
        v32 = "The swapchain was abandoned, aborting initialization";
        v31 = "CRdpIdSwapchain::Initialize";
        v29 = 183;
        v30 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v8,
          (unsigned int)&dword_18004F7AC,
          (_DWORD)v8,
          v9,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v31,
          (__int64)&v32,
          (__int64)&v42,
          (__int64)&v41);
      }
      LODWORD(v25) = *((_DWORD *)*this + 70);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"Swapchain was abandoned. Id %d",
        "CRdpIdSwapchain::Initialize",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        0xBAu,
        v25);
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
      return 0;
    }
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
      (const char *)v7,
      (int)"IddCxSwapChainSetDevice failed",
      v25);
    v12 = *(_DWORD *)(v4 + 536);
    if ( v12 == 1 )
    {
      if ( *(_BYTE *)(*((_QWORD *)*this + 33) + 8LL) )
        goto LABEL_22;
    }
    else if ( v12 != 2 )
    {
      goto LABEL_22;
    }
    v33 = 0;
    v33 = Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(*((Rdp::Utils::Graphics::CRenderDevice **)*this + 33));
    if ( IddClientVersionHigherThanFramework && (unsigned int)IddFunctionCount <= 0x1E )
    {
      (*(void (__fastcall **)(__int64, _QWORD, wchar_t *))(WdfFunctions_02025 + 2128))(
        WdfDriverGlobals,
        *(_QWORD *)WdfDriverGlobals,
        IddFrameworkExtensionName);
    }
    else
    {
      v16 = qword_180057C00(IddDriverGlobals, this[4], &v33);
      if ( v16 < 0 )
      {
        if ( v16 != -2147467263 )
        {
          v19 = wil::verify_hresult<long>((unsigned int)v16);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xCE,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
            (const char *)v19,
            (int)"IddCxSetRealtimeGPUPriority failed for Wddm 2.x or above",
            v26);
        }
        v17 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v17 > 3u )
        {
          v32 = *(const char **)(v4 + 520);
          v41 = *((_DWORD *)*this + 70);
          v42 = *(_DWORD *)(v4 + 516);
          v31 = "Setting realtime GPU priority is not supported on WDDM 1.x devices";
          v30 = "CRdpIdSwapchain::Initialize";
          v29 = 214;
          v34 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (_DWORD)v17,
            (unsigned int)&word_18004F74E,
            (_DWORD)v17,
            v18,
            (__int64)&v34,
            (__int64)&v29,
            (__int64)&v30,
            (__int64)&v31,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v32);
        }
        LODWORD(v26) = *((_DWORD *)*this + 70);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"Setting realtime GPU priority is not supported on WDDM 1.x devices, Id %d",
          "CRdpIdSwapchain::Initialize",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
          0xD9u,
          v26);
        goto LABEL_22;
      }
    }
    v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v13 > 4u )
    {
      v15 = *this;
      v34 = (const char *)(*((_QWORD *)*this + 32) + 8LL);
      v32 = *(const char **)(v4 + 520);
      v41 = *((_DWORD *)v15 + 70);
      v42 = *(_DWORD *)(v4 + 516);
      v31 = "GPU priority is set to realtime";
      v30 = "CRdpIdSwapchain::Initialize";
      v29 = 227;
      v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v13,
        (unsigned int)byte_18004F6E3,
        (_DWORD)v13,
        v14,
        (__int64)&v36,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v32,
        (__int64)&v34);
    }
    LODWORD(v26) = *((_DWORD *)*this + 70);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"GPU priority is set to realtime, Id %d",
      "CRdpIdSwapchain::Initialize",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
      0xE6u,
      v26);
LABEL_22:
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    result = 1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
      v10);
    v20 = std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(this);
    v22 = wil::ResultFromCaughtException(v21);
    CRdpIdMonitor::OnSwapchainFailure(v20, *((unsigned int *)this + 7), v22);
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
      (const char *)0xC01E0012LL,
      v23);
  }
  return result;
}

```

## disassembly

```asm
0x18002badc  mov     rax, rsp
0x18002badf  mov     [rax+10h], rbx
0x18002bae3  mov     [rax+8], rcx
0x18002bae7  push    rsi
0x18002bae8  push    rdi
0x18002bae9  push    r12
0x18002baeb  push    r14
0x18002baed  push    r15
0x18002baef  sub     rsp, 0B0h
0x18002baf6  mov     r15, rdx
0x18002baf9  mov     rbx, rcx
0x18002bafc  mov     rdx, [rcx]
0x18002baff  add     rdx, 0E8h
0x18002bb06  lea     rcx, [rax-38h]
0x18002bb0a  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18002bb0f  nop
0x18002bb10  mov     rsi, [rsp+0D8h+var_38]
0x18002bb18  cmp     dword ptr [rsi+1B8h], 3
0x18002bb1f  jnz     short loc_18002BB38
0x18002bb21  mov     edx, 3
0x18002bb26  mov     r9d, 8000FFFFh
0x18002bb2c  lea     r8d, [rdx-2]
0x18002bb30  mov     rcx, rsi
0x18002bb33  call    ?ReportCriticalError@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalError(FailFastMajorCode,uint,long)
0x18002bb38  lea     r8, [rbx+1Ch]; enum SwapChainThreadStage *
0x18002bb3c  mov     rdx, r15; struct _LUID *
0x18002bb3f  mov     rcx, [rbx]; this
0x18002bb42  call    ?AssignRenderAdapter@CRdpIdMonitor@@QEAAXAEBU_LUID@@AEAW4SwapChainThreadStage@@@Z; CRdpIdMonitor::AssignRenderAdapter(_LUID const &,SwapChainThreadStage &)
0x18002bb47  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002bb4c  mov     r8, [rax+8]
0x18002bb50  mov     eax, [r8]
0x18002bb53  cmp     eax, 4
0x18002bb56  jbe     loc_18002BC14
0x18002bb5c  mov     rax, [rsi+208h]
0x18002bb63  mov     [rsp+0D8h+var_58], rax
0x18002bb6b  mov     rax, [rbx]
0x18002bb6e  mov     ecx, [rax+118h]
0x18002bb74  mov     [rsp+0D8h+arg_10], ecx
0x18002bb7b  mov     eax, [rsi+204h]
0x18002bb81  mov     [rsp+0D8h+arg_18], eax
0x18002bb88  lea     rax, aAssignrenderad_0; "AssignRenderAdapter complete"
0x18002bb8f  mov     [rsp+0D8h+var_70], rax
0x18002bb94  lea     r14, aCrdpidswapchai_0; "CRdpIdSwapchain::Initialize"
0x18002bb9b  mov     [rsp+0D8h+var_68], r14
0x18002bba0  mov     [rsp+0D8h+var_78], 9Ch
0x18002bba8  lea     rdi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002bbaf  mov     [rsp+0D8h+var_60], rdi
0x18002bbb4  lea     rax, [rsp+0D8h+var_58]
0x18002bbbc  mov     [rsp+0D8h+var_88], rax
0x18002bbc1  lea     rax, [rsp+0D8h+arg_10]
0x18002bbc9  mov     [rsp+0D8h+var_90], rax
0x18002bbce  lea     rax, [rsp+0D8h+arg_18]
0x18002bbd6  mov     [rsp+0D8h+var_98], rax
0x18002bbdb  lea     rax, [rsp+0D8h+var_70]
0x18002bbe0  mov     [rsp+0D8h+var_A0], rax
0x18002bbe5  lea     rax, [rsp+0D8h+var_68]
0x18002bbea  mov     [rsp+0D8h+var_A8], rax
0x18002bbef  lea     rax, [rsp+0D8h+var_78]
0x18002bbf4  mov     [rsp+0D8h+var_B0], rax
0x18002bbf9  lea     rax, [rsp+0D8h+var_60]
0x18002bbfe  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18002bc03  lea     rdx, dword_18004F7FC
0x18002bc0a  mov     rcx, r8
0x18002bc0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002bc12  jmp     short loc_18002BC22
0x18002bc14  lea     r14, aCrdpidswapchai_0; "CRdpIdSwapchain::Initialize"
0x18002bc1b  lea     rdi, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002bc22  mov     rax, [rbx]
0x18002bc25  mov     ecx, [rax+118h]
0x18002bc2b  mov     dword ptr [rsp+0D8h+var_A0], ecx
0x18002bc2f  mov     eax, [r15]
0x18002bc32  mov     dword ptr [rsp+0D8h+var_A8], eax
0x18002bc36  mov     eax, [r15+4]
0x18002bc3a  mov     dword ptr [rsp+0D8h+var_B0], eax; char *
0x18002bc3e  mov     [rsp+0D8h+var_B8], 0A0h; unsigned int
0x18002bc46  mov     r9, rdi; char *
0x18002bc49  mov     r8, r14; char *
0x18002bc4c  lea     rdx, aAssignrenderad; "AssignRenderAdapter complete: %x.%x, Id"...
0x18002bc53  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002bc5a  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002bc5f  mov     dword ptr [rbx+1Ch], 4
0x18002bc66  xor     r15d, r15d
0x18002bc69  mov     [rsp+0D8h+var_48], r15
0x18002bc71  mov     rcx, [rbx]
0x18002bc74  mov     rcx, [rcx+108h]; this
0x18002bc7b  call    ?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ; Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)
0x18002bc80  mov     [rsp+0D8h+var_48], rax
0x18002bc88  lea     r8, [rsp+0D8h+var_48]
0x18002bc90  mov     rdx, [rbx+20h]
0x18002bc94  mov     rcx, cs:IddDriverGlobals
0x18002bc9b  mov     rax, cs:qword_180057B60
0x18002bca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bca7  cmp     eax, 887A0026h
0x18002bcac  jnz     loc_18002BD9B
0x18002bcb2  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002bcb7  mov     r8, [rax+8]
0x18002bcbb  mov     eax, [r8]
0x18002bcbe  cmp     eax, 4
0x18002bcc1  jbe     loc_18002BD53
0x18002bcc7  mov     rax, [rbx]
0x18002bcca  mov     ecx, [rax+118h]
0x18002bcd0  mov     [rsp+0D8h+arg_10], ecx
0x18002bcd7  mov     eax, [rsi+204h]
0x18002bcdd  mov     [rsp+0D8h+arg_18], eax
0x18002bce4  lea     rax, aTheSwapchainWa_0; "The swapchain was abandoned, aborting i"...
0x18002bceb  mov     [rsp+0D8h+var_60], rax
0x18002bcf0  mov     [rsp+0D8h+var_68], r14
0x18002bcf5  mov     [rsp+0D8h+var_78], 0B7h
0x18002bcfd  mov     [rsp+0D8h+var_70], rdi
0x18002bd02  lea     rax, [rsp+0D8h+arg_10]
0x18002bd0a  mov     [rsp+0D8h+var_90], rax
0x18002bd0f  lea     rax, [rsp+0D8h+arg_18]
0x18002bd17  mov     [rsp+0D8h+var_98], rax
0x18002bd1c  lea     rax, [rsp+0D8h+var_60]
0x18002bd21  mov     [rsp+0D8h+var_A0], rax
0x18002bd26  lea     rax, [rsp+0D8h+var_68]
0x18002bd2b  mov     [rsp+0D8h+var_A8], rax
0x18002bd30  lea     rax, [rsp+0D8h+var_78]
0x18002bd35  mov     [rsp+0D8h+var_B0], rax
0x18002bd3a  lea     rax, [rsp+0D8h+var_70]
0x18002bd3f  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18002bd44  lea     rdx, dword_18004F7AC
0x18002bd4b  mov     rcx, r8
0x18002bd4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002bd53  mov     rax, [rbx]
0x18002bd56  mov     edx, [rax+118h]
0x18002bd5c  mov     dword ptr [rsp+0D8h+var_B0], edx
0x18002bd60  mov     [rsp+0D8h+var_B8], 0BAh; unsigned int
0x18002bd68  mov     r9, rdi; char *
0x18002bd6b  mov     r8, r14; char *
0x18002bd6e  lea     rdx, aSwapchainWasAb; "Swapchain was abandoned. Id %d"
0x18002bd75  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002bd7c  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002bd81  nop
0x18002bd82  mov     rcx, [rsp+0D8h+var_30]; this
0x18002bd8a  test    rcx, rcx
0x18002bd8d  jz      short loc_18002BD94
0x18002bd8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bd94  xor     al, al
0x18002bd96  jmp     loc_18002BF71
0x18002bd9b  mov     rcx, [rsp+0D8h]; this
0x18002bda3  lea     rdx, aIddcxswapchain_1; "IddCxSwapChainSetDevice failed"
0x18002bdaa  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18002bdaf  mov     r9d, eax; char *
0x18002bdb2  mov     r8, rdi; unsigned int
0x18002bdb5  mov     edx, 0BEh; void *
0x18002bdba  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002bdbf  mov     eax, [rsi+218h]
0x18002bdc5  cmp     eax, 1
0x18002bdc8  jnz     short loc_18002BDDF
0x18002bdca  mov     rax, [rbx]
0x18002bdcd  mov     rcx, [rax+108h]
0x18002bdd4  cmp     [rcx+8], r15b
0x18002bdd8  jz      short loc_18002BDE8
0x18002bdda  jmp     loc_18002BF5C
0x18002bddf  cmp     eax, 2
0x18002bde2  jnz     loc_18002BF5C
0x18002bde8  mov     [rsp+0D8h+var_58], r15
0x18002bdf0  mov     rcx, [rbx]
0x18002bdf3  mov     rcx, [rcx+108h]; this
0x18002bdfa  call    ?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ; Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)
0x18002bdff  mov     [rsp+0D8h+var_58], rax
0x18002be07  cmp     cs:IddClientVersionHigherThanFramework, r15b
0x18002be0e  jz      loc_18002BF8A
0x18002be14  mov     r9d, 1Eh
0x18002be1a  cmp     cs:IddFunctionCount, r9d
0x18002be21  ja      loc_18002BF8A
0x18002be27  mov     rax, cs:WdfFunctions_02025
0x18002be2e  mov     byte ptr [rsp+0D8h+var_B8], r15b
0x18002be33  mov     r8, cs:IddFrameworkExtensionName
0x18002be3a  mov     rcx, cs:WdfDriverGlobals
0x18002be41  mov     rdx, [rcx]
0x18002be44  mov     rax, [rax+850h]
0x18002be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be50  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002be55  mov     r8, [rax+8]
0x18002be59  mov     eax, [r8]
0x18002be5c  cmp     eax, 4
0x18002be5f  jbe     loc_18002BF2D
0x18002be65  mov     rcx, [rbx]
0x18002be68  mov     rax, [rcx+100h]
0x18002be6f  add     rax, 8
0x18002be73  mov     [rsp+0D8h+var_50], rax
0x18002be7b  mov     rax, [rsi+208h]
0x18002be82  mov     [rsp+0D8h+var_60], rax
0x18002be87  mov     eax, [rcx+118h]
0x18002be8d  mov     [rsp+0D8h+arg_10], eax
0x18002be94  mov     eax, [rsi+204h]
0x18002be9a  mov     [rsp+0D8h+arg_18], eax
0x18002bea1  lea     rax, aGpuPriorityIsS; "GPU priority is set to realtime"
0x18002bea8  mov     [rsp+0D8h+var_68], rax
0x18002bead  mov     [rsp+0D8h+var_70], r14
0x18002beb2  mov     [rsp+0D8h+var_78], 0E3h
0x18002beba  mov     [rsp+0D8h+var_40], rdi
0x18002bec2  lea     rax, [rsp+0D8h+var_50]
0x18002beca  mov     [rsp+0D8h+var_80], rax
0x18002becf  lea     rax, [rsp+0D8h+var_60]
0x18002bed4  mov     [rsp+0D8h+var_88], rax
0x18002bed9  lea     rax, [rsp+0D8h+arg_10]
0x18002bee1  mov     [rsp+0D8h+var_90], rax
0x18002bee6  lea     rax, [rsp+0D8h+arg_18]
0x18002beee  mov     [rsp+0D8h+var_98], rax
0x18002bef3  lea     rax, [rsp+0D8h+var_68]
0x18002bef8  mov     [rsp+0D8h+var_A0], rax
0x18002befd  lea     rax, [rsp+0D8h+var_70]
0x18002bf02  mov     [rsp+0D8h+var_A8], rax
0x18002bf07  lea     rax, [rsp+0D8h+var_78]
0x18002bf0c  mov     [rsp+0D8h+var_B0], rax
0x18002bf11  lea     rax, [rsp+0D8h+var_40]
0x18002bf19  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18002bf1e  lea     rdx, byte_18004F6E3
0x18002bf25  mov     rcx, r8
0x18002bf28  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18002bf2d  mov     rax, [rbx]
0x18002bf30  mov     ecx, [rax+118h]
0x18002bf36  mov     dword ptr [rsp+0D8h+var_B0], ecx
0x18002bf3a  mov     [rsp+0D8h+var_B8], 0E6h; unsigned int
0x18002bf42  mov     r9, rdi; char *
0x18002bf45  mov     r8, r14; char *
0x18002bf48  lea     rdx, aGpuPriorityIsS_0; "GPU priority is set to realtime, Id %d"
0x18002bf4f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002bf56  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002bf5b  nop
0x18002bf5c  mov     rcx, [rsp+0D8h+var_30]; this
0x18002bf64  test    rcx, rcx
0x18002bf67  jz      short loc_18002BF6F
0x18002bf69  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bf6e  nop
0x18002bf6f  mov     al, 1
0x18002bf71  mov     rbx, [rsp+0D8h+arg_8]
0x18002bf79  add     rsp, 0B0h
0x18002bf80  pop     r15
0x18002bf82  pop     r14
0x18002bf84  pop     r12
0x18002bf86  pop     rdi
0x18002bf87  pop     rsi
0x18002bf88  retn
0x18002bf8a  lea     r8, [rsp+0D8h+var_58]
0x18002bf92  mov     rdx, [rbx+20h]
0x18002bf96  mov     rcx, cs:IddDriverGlobals
0x18002bf9d  mov     rax, cs:qword_180057C00
0x18002bfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfa9  test    eax, eax
0x18002bfab  jns     loc_18002BE50
0x18002bfb1  cmp     eax, 80004001h
0x18002bfb6  jnz     loc_18002C0AC
0x18002bfbc  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002bfc1  mov     r8, [rax+8]
0x18002bfc5  mov     eax, [r8]
0x18002bfc8  cmp     eax, 3
0x18002bfcb  jbe     loc_18002C079
0x18002bfd1  mov     rax, [rsi+208h]
0x18002bfd8  mov     [rsp+0D8h+var_60], rax
0x18002bfdd  mov     rax, [rbx]
0x18002bfe0  mov     ecx, [rax+118h]
0x18002bfe6  mov     [rsp+0D8h+arg_10], ecx
0x18002bfed  mov     eax, [rsi+204h]
0x18002bff3  mov     [rsp+0D8h+arg_18], eax
0x18002bffa  lea     rax, aSettingRealtim; "Setting realtime GPU priority is not su"...
0x18002c001  mov     [rsp+0D8h+var_68], rax
0x18002c006  mov     [rsp+0D8h+var_70], r14
0x18002c00b  mov     [rsp+0D8h+var_78], 0D6h
0x18002c013  mov     [rsp+0D8h+var_50], rdi
0x18002c01b  lea     rax, [rsp+0D8h+var_60]
0x18002c020  mov     [rsp+0D8h+var_88], rax
0x18002c025  lea     rax, [rsp+0D8h+arg_10]
0x18002c02d  mov     [rsp+0D8h+var_90], rax
0x18002c032  lea     rax, [rsp+0D8h+arg_18]
0x18002c03a  mov     [rsp+0D8h+var_98], rax
0x18002c03f  lea     rax, [rsp+0D8h+var_68]
0x18002c044  mov     [rsp+0D8h+var_A0], rax
0x18002c049  lea     rax, [rsp+0D8h+var_70]
0x18002c04e  mov     [rsp+0D8h+var_A8], rax
0x18002c053  lea     rax, [rsp+0D8h+var_78]
0x18002c058  mov     [rsp+0D8h+var_B0], rax
0x18002c05d  lea     rax, [rsp+0D8h+var_50]
0x18002c065  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18002c06a  lea     rdx, word_18004F74E
0x18002c071  mov     rcx, r8
0x18002c074  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002c079  mov     rax, [rbx]
0x18002c07c  mov     ecx, [rax+118h]
0x18002c082  mov     dword ptr [rsp+0D8h+var_B0], ecx
0x18002c086  mov     [rsp+0D8h+var_B8], 0D9h; unsigned int
0x18002c08e  mov     r9, rdi; char *
0x18002c091  mov     r8, r14; char *
0x18002c094  lea     rdx, aSettingRealtim_0; "Setting realtime GPU priority is not su"...
0x18002c09b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002c0a2  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002c0a7  jmp     loc_18002BF5C
0x18002c0ac  mov     ecx, eax
0x18002c0ae  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002c0b3  mov     r9d, eax; char *
0x18002c0b6  mov     rcx, [rsp+0D8h]; this
0x18002c0be  lea     rax, aIddcxsetrealti; "IddCxSetRealtimeGPUPriority failed for "...
0x18002c0c5  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x18002c0ca  mov     r8, rdi; unsigned int
0x18002c0cd  mov     edx, 0CEh; void *
0x18002c0d2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
