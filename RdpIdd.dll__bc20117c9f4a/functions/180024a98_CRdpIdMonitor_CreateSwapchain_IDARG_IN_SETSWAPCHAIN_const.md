# CRdpIdMonitor::CreateSwapchain(IDARG_IN_SETSWAPCHAIN const *)

- ea: `0x180024a98`
- end: `0x180024e62`
- name: `?CreateSwapchain@CRdpIdMonitor@@QEAAXPEBUIDARG_IN_SETSWAPCHAIN@@@Z`
- size: `970`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, const struct IDARG_IN_SETSWAPCHAIN *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180025f90`

## callees

- `0x180001af0`
- `0x180004810`
- `0x180004ad0`
- `0x180004c5c`
- `0x180006f84`
- `0x18000d614`
- `0x18001072c`
- `0x180014c20`
- `0x1800153f4`
- `0x180021570`
- `0x180021830`
- `0x180024a98`
- `0x18002a054`

## string_xrefs

- `0x180024b8b`: `CRdpIdMonitor::CreateSwapchain`
- `0x180024b95`: `MonitorCreateSwapChain: Id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdMonitor::CreateSwapchain(CRdpIdMonitor *this, const struct IDARG_IN_SETSWAPCHAIN *a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  __int64 v6; // r9
  __int64 v7; // r10
  GUID *v8; // r11
  _DWORD *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  _DWORD *v13; // r8
  int v14; // r8d
  int v15; // r9d
  wchar_t *v16; // rdx
  unsigned int v17; // ecx
  _DWORD *v18; // r8
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // [rsp+28h] [rbp-61h]
  __int64 v24; // [rsp+28h] [rbp-61h]
  __int64 v25; // [rsp+30h] [rbp-59h]
  __int64 v26; // [rsp+38h] [rbp-51h]
  __int64 v27; // [rsp+70h] [rbp-19h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h] BYREF
  GUID *v29; // [rsp+80h] [rbp-9h] BYREF
  __int64 v30; // [rsp+88h] [rbp-1h] BYREF
  const char *v31; // [rsp+90h] [rbp+7h] BYREF
  const char *v32; // [rsp+98h] [rbp+Fh] BYREF
  std::_Ref_count_base *v33; // [rsp+A0h] [rbp+17h]
  void *v34; // [rsp+F0h] [rbp+67h] BYREF
  int v35; // [rsp+100h] [rbp+77h] BYREF
  __int64 v36; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x470000000000LL) )
  {
    LODWORD(v34) = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
    v35 = *((_DWORD *)this + 70);
    v36 = v6;
    v27 = v7;
    v28 = 0x1000000;
    v29 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_18004E94B,
      v5,
      v6,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34);
  }
  v9 = (_DWORD *)((char *)this + 280);
  LODWORD(v23) = *((_DWORD *)this + 70);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"MonitorCreateSwapChain: Id %d",
    "CRdpIdMonitor::CreateSwapchain",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    0x4B2u,
    v23);
  v10 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v32);
  v34 = operator new(0x40u);
  v11 = CRdpIdSwapchain::CRdpIdSwapchain(v34, v10, a2);
  v34 = 0;
  v12 = *((_QWORD *)this + 31);
  *((_QWORD *)this + 31) = v11;
  if ( v12 )
    std::default_delete<CRdpIdSwapchain>::operator()();
  std::unique_ptr<CRdpIdSwapchain>::~unique_ptr<CRdpIdSwapchain>(&v34);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  if ( **((_BYTE **)this + 32) )
  {
    v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v13 > 4u && (unsigned __int8)tlgKeywordOn(v13, 0x470000000000LL) )
    {
      v36 = *(_QWORD *)(*((_QWORD *)this + 32) + 304LL);
      LODWORD(v34) = *v9;
      v35 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
      v29 = (GUID *)"Monitor is rendered by WARP";
      v28 = (__int64)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v27 = (__int64)"RdpIdd";
      v30 = 0x1000000;
      v31 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)word_18004E8D2,
        v14,
        v15,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v36);
    }
    v16 = L"WARPRenderAdapter: Id %d, LUID {%#x,%#x}";
    v17 = 1227;
  }
  else
  {
    v18 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v18 > 4u && (unsigned __int8)tlgKeywordOn(v18, 0x470000000000LL) )
    {
      v21 = *((_QWORD *)this + 32);
      v36 = *(_QWORD *)(v21 + 304);
      v31 = (const char *)(v21 + 8);
      LODWORD(v34) = *v9;
      v35 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
      v30 = (__int64)"Monitor is rendered by H/W GPU video adapter";
      v29 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v28 = (__int64)"RdpIdd";
      v27 = 0x1000000;
      v32 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v19,
        (unsigned int)&word_18004E84E,
        v19,
        v20,
        (__int64)&v32,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v31,
        (__int64)&v36);
    }
    v16 = (wchar_t *)L"HwRenderAdapter: Id %d, LUID {%#x,%#x}";
    v17 = 1241;
  }
  v22 = *((_QWORD *)this + 32);
  LODWORD(v26) = *(_DWORD *)(v22 + 304);
  LODWORD(v25) = *(_DWORD *)(v22 + 308);
  LODWORD(v24) = *v9;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    v16,
    "CRdpIdMonitor::CreateSwapchain",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    v17,
    v24,
    v25,
    v26);
}

```

## disassembly

```asm
0x180024a98  mov     [rsp-8+arg_8], rbx
0x180024a9d  push    rbp
0x180024a9e  push    rsi
0x180024a9f  push    rdi
0x180024aa0  push    r12
0x180024aa2  push    r13
0x180024aa4  push    r14
0x180024aa6  push    r15
0x180024aa8  lea     rbp, [rsp-27h]
0x180024aad  sub     rsp, 0B0h
0x180024ab4  mov     r13, rdx
0x180024ab7  mov     rdi, rcx
0x180024aba  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180024abf  mov     r8, [rax+8]
0x180024ac3  mov     eax, [r8]
0x180024ac6  lea     r9, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180024acd  lea     r10, aRdpidd; "RdpIdd"
0x180024ad4  lea     r11, aCheckpoint; "Checkpoint"
0x180024adb  cmp     eax, 4
0x180024ade  jbe     loc_180024B6C
0x180024ae4  mov     rdx, 470000000000h
0x180024aee  mov     rcx, r8
0x180024af1  call    _tlgKeywordOn
0x180024af6  test    al, al
0x180024af8  jz      short loc_180024B6C
0x180024afa  mov     rax, [rdi+0E8h]
0x180024b01  mov     ecx, [rax+204h]
0x180024b07  mov     dword ptr [rbp+57h+arg_0], ecx
0x180024b0a  mov     eax, [rdi+118h]
0x180024b10  mov     [rbp+57h+arg_10], eax
0x180024b13  mov     [rbp+57h+arg_18], r9
0x180024b17  mov     [rbp+57h+var_70], r10
0x180024b1b  mov     [rbp+57h+var_68], 1000000h
0x180024b23  mov     [rbp+57h+var_60], r11
0x180024b27  lea     rax, [rbp+57h+arg_0]
0x180024b2b  mov     [rsp+0E0h+var_98], rax
0x180024b30  lea     rax, [rbp+57h+arg_10]
0x180024b34  mov     [rsp+0E0h+var_A0], rax
0x180024b39  lea     rax, [rbp+57h+arg_18]
0x180024b3d  mov     [rsp+0E0h+var_A8], rax
0x180024b42  lea     rax, [rbp+57h+var_70]
0x180024b46  mov     [rsp+0E0h+var_B0], rax
0x180024b4b  lea     rax, [rbp+57h+var_68]
0x180024b4f  mov     [rsp+0E0h+var_B8], rax
0x180024b54  lea     rax, [rbp+57h+var_60]
0x180024b58  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180024b5d  lea     rdx, byte_18004E94B
0x180024b64  mov     rcx, r8
0x180024b67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180024b6c  lea     rsi, [rdi+118h]
0x180024b73  mov     eax, [rsi]
0x180024b75  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180024b79  mov     [rsp+0E0h+var_C0], 4B2h; unsigned int
0x180024b81  lea     r12, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180024b88  mov     r9, r12; char *
0x180024b8b  lea     r15, aCrdpidmonitorC; "CRdpIdMonitor::CreateSwapchain"
0x180024b92  mov     r8, r15; char *
0x180024b95  lea     rdx, aMonitorcreates; "MonitorCreateSwapChain: Id %d"
0x180024b9c  lea     r14, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; Rdp::Modern::Utils::CInflightRecorder Rdp::Modern::Utils::CInflightRecorder::g_Ifr
0x180024ba3  mov     rcx, r14; this
0x180024ba6  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180024bab  lea     rdx, [rbp+57h+var_48]
0x180024baf  mov     rcx, rdi
0x180024bb2  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x180024bb7  mov     rbx, rax
0x180024bba  mov     ecx, 40h ; '@'; Size
0x180024bbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024bc4  mov     [rbp+57h+arg_0], rax
0x180024bc8  mov     r8, r13
0x180024bcb  mov     rdx, rbx
0x180024bce  mov     rcx, rax
0x180024bd1  call    ??0CRdpIdSwapchain@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEBUIDARG_IN_SETSWAPCHAIN@@@Z; CRdpIdSwapchain::CRdpIdSwapchain(std::shared_ptr<CRdpIdMonitor> const &,IDARG_IN_SETSWAPCHAIN const *)
0x180024bd6  nop
0x180024bd7  mov     [rbp+57h+arg_0], 0
0x180024bdf  mov     rdx, [rdi+0F8h]
0x180024be6  mov     [rdi+0F8h], rax
0x180024bed  test    rdx, rdx
0x180024bf0  jz      short loc_180024BF7
0x180024bf2  call    ??R?$default_delete@VCRdpIdSwapchain@@@std@@QEBAXPEAVCRdpIdSwapchain@@@Z; std::default_delete<CRdpIdSwapchain>::operator()(CRdpIdSwapchain *)
0x180024bf7  lea     rcx, [rbp+57h+arg_0]
0x180024bfb  call    ??1?$unique_ptr@VCRdpIdSwapchain@@U?$default_delete@VCRdpIdSwapchain@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRdpIdSwapchain>::~unique_ptr<CRdpIdSwapchain>(void)
0x180024c00  nop
0x180024c01  mov     rcx, [rbp+57h+var_40]; this
0x180024c05  test    rcx, rcx
0x180024c08  jz      short loc_180024C0F
0x180024c0a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180024c0f  mov     rax, [rdi+100h]
0x180024c16  cmp     byte ptr [rax], 0
0x180024c19  jz      loc_180024D11
0x180024c1f  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180024c24  mov     r8, [rax+8]
0x180024c28  mov     eax, [r8]
0x180024c2b  cmp     eax, 4
0x180024c2e  jbe     loc_180024D00
0x180024c34  mov     rdx, 470000000000h
0x180024c3e  mov     rcx, r8
0x180024c41  call    _tlgKeywordOn
0x180024c46  test    al, al
0x180024c48  jz      loc_180024D00
0x180024c4e  mov     rax, [rdi+100h]
0x180024c55  mov     rcx, [rax+130h]
0x180024c5c  mov     [rbp+57h+arg_18], rcx
0x180024c60  mov     eax, [rsi]
0x180024c62  mov     dword ptr [rbp+57h+arg_0], eax
0x180024c65  mov     rax, [rdi+0E8h]
0x180024c6c  mov     ecx, [rax+204h]
0x180024c72  mov     [rbp+57h+arg_10], ecx
0x180024c75  lea     rax, aMonitorIsRende; "Monitor is rendered by WARP"
0x180024c7c  mov     [rbp+57h+var_60], rax
0x180024c80  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180024c87  mov     [rbp+57h+var_68], rax
0x180024c8b  lea     rax, aRdpidd; "RdpIdd"
0x180024c92  mov     [rbp+57h+var_70], rax
0x180024c96  mov     [rbp+57h+var_58], 1000000h
0x180024c9e  lea     rax, aCheckpoint; "Checkpoint"
0x180024ca5  mov     [rbp+57h+var_50], rax
0x180024ca9  lea     rax, [rbp+57h+arg_18]
0x180024cad  mov     [rsp+0E0h+var_88], rax
0x180024cb2  lea     rax, [rbp+57h+arg_0]
0x180024cb6  mov     [rsp+0E0h+var_90], rax
0x180024cbb  lea     rax, [rbp+57h+arg_10]
0x180024cbf  mov     [rsp+0E0h+var_98], rax
0x180024cc4  lea     rax, [rbp+57h+var_60]
0x180024cc8  mov     [rsp+0E0h+var_A0], rax
0x180024ccd  lea     rax, [rbp+57h+var_68]
0x180024cd1  mov     [rsp+0E0h+var_A8], rax
0x180024cd6  lea     rax, [rbp+57h+var_70]
0x180024cda  mov     [rsp+0E0h+var_B0], rax
0x180024cdf  lea     rax, [rbp+57h+var_58]
0x180024ce3  mov     [rsp+0E0h+var_B8], rax
0x180024ce8  lea     rax, [rbp+57h+var_50]
0x180024cec  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180024cf1  lea     rdx, word_18004E8D2
0x180024cf8  mov     rcx, r8
0x180024cfb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@64@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180024d00  lea     rdx, aWarprenderadap; "WARPRenderAdapter: Id %d, LUID {%#x,%#x"...
0x180024d07  mov     ecx, 4CBh
0x180024d0c  jmp     loc_180024E0F
0x180024d11  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180024d16  mov     r8, [rax+8]
0x180024d1a  mov     eax, [r8]
0x180024d1d  cmp     eax, 4
0x180024d20  jbe     loc_180024E03
0x180024d26  mov     rdx, 470000000000h
0x180024d30  mov     rcx, r8
0x180024d33  call    _tlgKeywordOn
0x180024d38  test    al, al
0x180024d3a  jz      loc_180024E03
0x180024d40  mov     rcx, [rdi+100h]
0x180024d47  mov     rax, [rcx+130h]
0x180024d4e  mov     [rbp+57h+arg_18], rax
0x180024d52  lea     rax, [rcx+8]
0x180024d56  mov     [rbp+57h+var_50], rax
0x180024d5a  mov     eax, [rsi]
0x180024d5c  mov     dword ptr [rbp+57h+arg_0], eax
0x180024d5f  mov     rax, [rdi+0E8h]
0x180024d66  mov     ecx, [rax+204h]
0x180024d6c  mov     [rbp+57h+arg_10], ecx
0x180024d6f  lea     rax, aMonitorIsRende_0; "Monitor is rendered by H/W GPU video ad"...
0x180024d76  mov     [rbp+57h+var_58], rax
0x180024d7a  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180024d81  mov     [rbp+57h+var_60], rax
0x180024d85  lea     rax, aRdpidd; "RdpIdd"
0x180024d8c  mov     [rbp+57h+var_68], rax
0x180024d90  mov     [rbp+57h+var_70], 1000000h
0x180024d98  lea     rax, aCheckpoint; "Checkpoint"
0x180024d9f  mov     [rbp+57h+var_48], rax
0x180024da3  lea     rax, [rbp+57h+arg_18]
0x180024da7  mov     [rsp+0E0h+var_80], rax
0x180024dac  lea     rax, [rbp+57h+var_50]
0x180024db0  mov     [rsp+0E0h+var_88], rax
0x180024db5  lea     rax, [rbp+57h+arg_0]
0x180024db9  mov     [rsp+0E0h+var_90], rax
0x180024dbe  lea     rax, [rbp+57h+arg_10]
0x180024dc2  mov     [rsp+0E0h+var_98], rax
0x180024dc7  lea     rax, [rbp+57h+var_58]
0x180024dcb  mov     [rsp+0E0h+var_A0], rax
0x180024dd0  lea     rax, [rbp+57h+var_60]
0x180024dd4  mov     [rsp+0E0h+var_A8], rax
0x180024dd9  lea     rax, [rbp+57h+var_68]
0x180024ddd  mov     [rsp+0E0h+var_B0], rax
0x180024de2  lea     rax, [rbp+57h+var_70]
0x180024de6  mov     [rsp+0E0h+var_B8], rax
0x180024deb  lea     rax, [rbp+57h+var_48]
0x180024def  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180024df4  lea     rdx, word_18004E84E
0x180024dfb  mov     rcx, r8
0x180024dfe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180024e03  lea     rdx, aHwrenderadapte; "HwRenderAdapter: Id %d, LUID {%#x,%#x}"
0x180024e0a  mov     ecx, 4D9h
0x180024e0f  mov     rax, [rdi+100h]
0x180024e16  mov     r9d, [rax+130h]
0x180024e1d  mov     r8d, [rax+134h]
0x180024e24  mov     dword ptr [rsp+0E0h+var_A8], r9d
0x180024e29  mov     dword ptr [rsp+0E0h+var_B0], r8d
0x180024e2e  mov     eax, [rsi]
0x180024e30  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180024e34  mov     [rsp+0E0h+var_C0], ecx; unsigned int
0x180024e38  mov     r9, r12; char *
0x180024e3b  mov     r8, r15; char *
0x180024e3e  mov     rcx, r14; this
0x180024e41  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180024e46  mov     rbx, [rsp+0E0h+arg_8]
0x180024e4e  add     rsp, 0B0h
0x180024e55  pop     r15
0x180024e57  pop     r14
0x180024e59  pop     r13
0x180024e5b  pop     r12
0x180024e5d  pop     rdi
0x180024e5e  pop     rsi
0x180024e5f  pop     rbp
0x180024e60  retn
```
