# CRdpIdMonitor::OnSwapchainFailure(SwapChainThreadStage,long)

- ea: `0x180025528`
- end: `0x1800257ac`
- name: `?OnSwapchainFailure@CRdpIdMonitor@@QEAAXW4SwapChainThreadStage@@J@Z`
- size: `644`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18003cf01`
- `0x18003d1ae`
- `0x18003d5a2`

## callees

- `0x180001af0`
- `0x180001bc4`
- `0x18000495c`
- `0x18000d614`
- `0x180015424`
- `0x18001638c`
- `0x180021570`
- `0x180025528`
- `0x180028144`

## string_xrefs

- `0x180025697`: `Swapchain failed and will be deleted`

## pseudocode

```c
__int64 __fastcall CRdpIdMonitor::OnSwapchainFailure(__int64 a1, unsigned int a2, int a3)
{
  __int64 *v6; // rsi
  int *v7; // rdi
  _DWORD *v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  int v11; // ecx
  __int64 result; // rax
  _DWORD *v13; // r8
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // [rsp+28h] [rbp-51h]
  __int64 v20; // [rsp+30h] [rbp-49h]
  int v21; // [rsp+70h] [rbp-9h] BYREF
  const char *v22; // [rsp+78h] [rbp-1h] BYREF
  const char *v23; // [rsp+80h] [rbp+7h] BYREF
  const char *v24; // [rsp+88h] [rbp+Fh] BYREF
  GUID *v25; // [rsp+90h] [rbp+17h] BYREF
  const char *v26; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+A0h] [rbp+27h] BYREF
  const char *v28; // [rsp+A8h] [rbp+2Fh] BYREF
  int v29; // [rsp+E0h] [rbp+67h] BYREF
  int v30; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( ++*(_DWORD *)(a1 + 20) == 5 )
  {
    v6 = (__int64 *)(a1 + 232);
    v7 = (int *)(a1 + 280);
    v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v8 > 4u )
    {
      v10 = *v6;
      v22 = "CRdpIdMonitor::OnSwapchainFailure";
      v24 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
      v11 = *(_DWORD *)(v10 + 516);
      v30 = *v7;
      v23 = "Falling back to WARP";
      v29 = v11;
      v21 = 1525;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v8,
        (unsigned int)&dword_18004E64C,
        (_DWORD)v8,
        v9,
        (__int64)&v24,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v29);
    }
    LODWORD(v19) = *v7;
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Falling back to WARP: Id %d",
      "CRdpIdMonitor::OnSwapchainFailure",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      0x5F8u,
      v19);
    result = CRdpIdAdapter::FallbackToWarp(*v6, a2, (__int64 *)(a1 + 256));
    *(_DWORD *)(a1 + 20) = 0;
  }
  else
  {
    v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v13 > 2u && (unsigned __int8)tlgKeywordOn(v13, 0x470000000000LL) )
    {
      v30 = *(_DWORD *)(a1 + 20);
      LODWORD(v22) = *(_DWORD *)(a1 + 280);
      v16 = *(_QWORD *)(a1 + 232);
      v29 = a3;
      v21 = a2;
      v17 = *(_DWORD *)(v16 + 516);
      v24 = "Swapchain failed and will be deleted";
      v25 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v26 = "RdpIdd";
      v28 = "Checkpoint";
      LODWORD(v23) = v17;
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_18004E5B9,
        v14,
        v15,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v29);
    }
    LODWORD(v20) = a3;
    LODWORD(v19) = *(_DWORD *)(a1 + 280);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"SwapchainFailure: Id %d, hr: %#x",
      "CRdpIdMonitor::OnSwapchainFailure",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      0x608u,
      v19,
      v20);
    v18 = *(_QWORD *)(a1 + 256);
    *(_QWORD *)(a1 + 256) = 0;
    if ( v18 )
      std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>::operator()();
    return std::shared_ptr<Rdp::Utils::Graphics::CRenderDevice>::reset(a1 + 264);
  }
  return result;
}

```

## disassembly

```asm
0x180025528  mov     [rsp-8+arg_8], rbx
0x18002552d  mov     [rsp-8+arg_10], rsi
0x180025532  push    rbp
0x180025533  push    rdi
0x180025534  push    r12
0x180025536  push    r14
0x180025538  push    r15
0x18002553a  lea     rbp, [rsp-37h]
0x18002553f  sub     rsp, 0B0h
0x180025546  inc     dword ptr [rcx+14h]
0x180025549  mov     edi, r8d
0x18002554c  cmp     dword ptr [rcx+14h], 5
0x180025550  mov     r12d, edx
0x180025553  mov     rbx, rcx
0x180025556  jnz     loc_18002563E
0x18002555c  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180025561  lea     rsi, [rbx+0E8h]
0x180025568  lea     rdi, [rbx+118h]
0x18002556f  lea     r14, aCrdpidmonitorO; "CRdpIdMonitor::OnSwapchainFailure"
0x180025576  mov     r8, [rax+8]
0x18002557a  lea     r15, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180025581  mov     eax, [r8]
0x180025584  cmp     eax, 4
0x180025587  jbe     short loc_1800255F9
0x180025589  mov     rax, [rsi]
0x18002558c  lea     rdx, dword_18004E64C
0x180025593  mov     [rbp+57h+var_58], r14
0x180025597  mov     [rbp+57h+var_48], r15
0x18002559b  mov     ecx, [rax+204h]
0x1800255a1  mov     eax, [rdi]
0x1800255a3  mov     [rbp+57h+arg_18], eax
0x1800255a6  lea     rax, aFallingBackToW_0; "Falling back to WARP"
0x1800255ad  mov     [rbp+57h+var_50], rax
0x1800255b1  lea     rax, [rbp+57h+arg_0]
0x1800255b5  mov     [rsp+0D0h+var_88], rax
0x1800255ba  lea     rax, [rbp+57h+arg_18]
0x1800255be  mov     [rsp+0D0h+var_90], rax
0x1800255c3  lea     rax, [rbp+57h+var_50]
0x1800255c7  mov     [rsp+0D0h+var_98], rax
0x1800255cc  lea     rax, [rbp+57h+var_58]
0x1800255d0  mov     [rsp+0D0h+var_A0], rax
0x1800255d5  lea     rax, [rbp+57h+var_60]
0x1800255d9  mov     [rsp+0D0h+var_A8], rax
0x1800255de  lea     rax, [rbp+57h+var_48]
0x1800255e2  mov     [rbp+57h+arg_0], ecx
0x1800255e5  mov     rcx, r8
0x1800255e8  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800255ed  mov     [rbp+57h+var_60], 5F5h
0x1800255f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800255f9  mov     eax, [rdi]
0x1800255fb  lea     rdx, aFallingBackToW; "Falling back to WARP: Id %d"
0x180025602  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180025606  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002560d  mov     r9, r15; char *
0x180025610  mov     [rsp+0D0h+var_B0], 5F8h; unsigned int
0x180025618  mov     r8, r14; char *
0x18002561b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180025620  mov     rcx, [rsi]
0x180025623  lea     r8, [rbx+100h]
0x18002562a  mov     edx, r12d
0x18002562d  call    ?FallbackToWarp@CRdpIdAdapter@@QEAAXW4SwapChainThreadStage@@AEBV?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@@Z; CRdpIdAdapter::FallbackToWarp(SwapChainThreadStage,std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter> const &)
0x180025632  mov     dword ptr [rbx+14h], 0
0x180025639  jmp     loc_18002578F
0x18002563e  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180025643  mov     r8, [rax+8]
0x180025647  mov     eax, [r8]
0x18002564a  cmp     eax, 2
0x18002564d  jbe     loc_180025730
0x180025653  mov     rdx, 470000000000h
0x18002565d  mov     rcx, r8
0x180025660  call    _tlgKeywordOn
0x180025665  test    al, al
0x180025667  jz      loc_180025730
0x18002566d  mov     eax, [rbx+14h]
0x180025670  lea     rdx, byte_18004E5B9
0x180025677  mov     [rbp+57h+arg_18], eax
0x18002567a  mov     eax, [rbx+118h]
0x180025680  mov     dword ptr [rbp+57h+var_58], eax
0x180025683  mov     rax, [rbx+0E8h]
0x18002568a  mov     [rbp+57h+arg_0], edi
0x18002568d  mov     [rbp+57h+var_60], r12d
0x180025691  mov     ecx, [rax+204h]
0x180025697  lea     rax, aSwapchainFaile; "Swapchain failed and will be deleted"
0x18002569e  mov     [rbp+57h+var_48], rax
0x1800256a2  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800256a9  mov     [rbp+57h+var_40], rax
0x1800256ad  lea     rax, aRdpidd; "RdpIdd"
0x1800256b4  mov     [rbp+57h+var_38], rax
0x1800256b8  lea     rax, aCheckpoint; "Checkpoint"
0x1800256bf  mov     [rbp+57h+var_28], rax
0x1800256c3  lea     rax, [rbp+57h+arg_0]
0x1800256c7  mov     [rsp+0D0h+var_68], rax
0x1800256cc  lea     rax, [rbp+57h+arg_18]
0x1800256d0  mov     [rsp+0D0h+var_70], rax
0x1800256d5  lea     rax, [rbp+57h+var_60]
0x1800256d9  mov     [rsp+0D0h+var_78], rax
0x1800256de  lea     rax, [rbp+57h+var_58]
0x1800256e2  mov     [rsp+0D0h+var_80], rax
0x1800256e7  lea     rax, [rbp+57h+var_50]
0x1800256eb  mov     [rsp+0D0h+var_88], rax
0x1800256f0  lea     rax, [rbp+57h+var_48]
0x1800256f4  mov     [rsp+0D0h+var_90], rax
0x1800256f9  lea     rax, [rbp+57h+var_40]
0x1800256fd  mov     [rsp+0D0h+var_98], rax
0x180025702  lea     rax, [rbp+57h+var_38]
0x180025706  mov     [rsp+0D0h+var_A0], rax
0x18002570b  lea     rax, [rbp+57h+var_30]
0x18002570f  mov     [rsp+0D0h+var_A8], rax
0x180025714  lea     rax, [rbp+57h+var_28]
0x180025718  mov     dword ptr [rbp+57h+var_50], ecx
0x18002571b  mov     rcx, r8
0x18002571e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180025723  mov     [rbp+57h+var_30], 1000000h
0x18002572b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025730  mov     eax, [rbx+118h]
0x180025736  lea     r9, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002573d  mov     dword ptr [rsp+0D0h+var_A0], edi
0x180025741  lea     r8, aCrdpidmonitorO; "CRdpIdMonitor::OnSwapchainFailure"
0x180025748  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18002574c  lea     rdx, aSwapchainfailu; "SwapchainFailure: Id %d, hr: %#x"
0x180025753  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002575a  mov     [rsp+0D0h+var_B0], 608h; unsigned int
0x180025762  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180025767  mov     rdx, [rbx+100h]
0x18002576e  mov     qword ptr [rbx+100h], 0
0x180025779  test    rdx, rdx
0x18002577c  jz      short loc_180025783
0x18002577e  call    ??R?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@QEBAXPEAVCRenderAdapter@Graphics@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>::operator()(Rdp::Utils::Graphics::CRenderAdapter *)
0x180025783  lea     rcx, [rbx+108h]
0x18002578a  call    ?reset@?$shared_ptr@VCRenderDevice@Graphics@Utils@Rdp@@@std@@QEAAXXZ; std::shared_ptr<Rdp::Utils::Graphics::CRenderDevice>::reset(void)
0x18002578f  lea     r11, [rsp+0D0h+var_20]
0x180025797  mov     rbx, [r11+38h]
0x18002579b  mov     rsi, [r11+40h]
0x18002579f  mov     rsp, r11
0x1800257a2  pop     r15
0x1800257a4  pop     r14
0x1800257a6  pop     r12
0x1800257a8  pop     rdi
0x1800257a9  pop     rbp
0x1800257aa  retn
```
