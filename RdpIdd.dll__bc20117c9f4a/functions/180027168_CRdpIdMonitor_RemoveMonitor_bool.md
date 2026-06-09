# CRdpIdMonitor::RemoveMonitor(bool)

- ea: `0x180027168`
- end: `0x180027390`
- name: `?RemoveMonitor@CRdpIdMonitor@@QEAAX_N@Z`
- size: `552`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015850`
- `0x180015a88`

## callees

- `0x180001af0`
- `0x180004c5c`
- `0x18000d614`
- `0x180010ff8`
- `0x1800153c4`
- `0x180015424`
- `0x180017ac8`
- `0x180021570`
- `0x180021750`
- `0x180024e68`
- `0x180027168`
- `0x180028144`
- `0x18003f010`

## string_xrefs

- `0x180027240`: `CRdpIdMonitor::RemoveMonitor`
- `0x180027247`: `MonitorRemove: Id %d`

## pseudocode

```c
void __fastcall CRdpIdMonitor::RemoveMonitor(CRdpIdMonitor *this, char a2)
{
  _DWORD *v3; // r8
  int v4; // r8d
  int v5; // r9d
  int v6; // ecx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  char *v14; // [rsp+28h] [rbp-38h]
  char *v15; // [rsp+28h] [rbp-38h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  const char *v17; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v19; // [rsp+80h] [rbp+20h] BYREF
  int v20; // [rsp+88h] [rbp+28h] BYREF
  GUID *v21; // [rsp+90h] [rbp+30h] BYREF
  const char *v22; // [rsp+98h] [rbp+38h] BYREF

  LOBYTE(v20) = a2;
  v3 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v3 > 4u && (unsigned __int8)tlgKeywordOn(v3, 0x470000000000LL) )
  {
    v6 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
    v19 = *((_DWORD *)this + 70);
    v21 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v22 = "RdpIdd";
    v17 = "Checkpoint";
    v20 = v6;
    v16 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)qword_18004ED68,
      v4,
      v5,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v19,
      (__int64)&v20);
  }
  LODWORD(v14) = *((_DWORD *)this + 70);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"MonitorRemove: Id %d",
    "CRdpIdMonitor::RemoveMonitor",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    0x13Cu,
    v14);
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    std::default_delete<CRdpIdCursor>::operator()();
  if ( *((_BYTE *)this + 16) )
  {
    v8 = ((__int64 (__fastcall *)(__int64, _QWORD))qword_180057B38)(IddDriverGlobals, *((_QWORD *)this + 28));
    wil::details::in1diag3::Log_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x149,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v8,
      (int)"Failed to unplug monitor",
      v15);
  }
  *((_QWORD *)this + 28) = 0;
  *((_BYTE *)this + 16) = 0;
  CRdpIdMonitor::DestroySwapchain(this);
  v9 = *((_QWORD *)this + 38);
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v10,
      (int)"Failed to stop frame processor",
      v15);
    wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 304);
  }
  v11 = *((_QWORD *)this + 39);
  if ( v11 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)v12,
      (int)"Failed to stop monitor encoding context",
      v15);
    wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 312);
  }
  v13 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v13 )
    std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>::operator()();
  std::shared_ptr<Rdp::Utils::Graphics::CRenderDevice>::reset((char *)this + 264);
}

```

## disassembly

```asm
0x180027168  mov     byte ptr [rsp-18h+arg_8], dl
0x18002716c  push    rbp
0x18002716d  push    rbx
0x18002716e  push    rdi
0x18002716f  mov     rbp, rsp
0x180027172  sub     rsp, 60h
0x180027176  mov     rbx, rcx
0x180027179  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002717e  mov     r8, [rax+8]
0x180027182  mov     eax, [r8]
0x180027185  cmp     eax, 4
0x180027188  jbe     loc_18002722F
0x18002718e  mov     rdx, 470000000000h
0x180027198  mov     rcx, r8
0x18002719b  call    _tlgKeywordOn
0x1800271a0  test    al, al
0x1800271a2  jz      loc_18002722F
0x1800271a8  mov     rax, [rbx+0E8h]
0x1800271af  lea     rdx, qword_18004ED68
0x1800271b6  mov     ecx, [rax+204h]
0x1800271bc  mov     eax, [rbx+118h]
0x1800271c2  mov     [rbp+arg_0], eax
0x1800271c5  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800271cc  mov     [rbp+arg_10], rax
0x1800271d0  lea     rax, aRdpidd; "RdpIdd"
0x1800271d7  mov     [rbp+arg_18], rax
0x1800271db  lea     rax, aCheckpoint; "Checkpoint"
0x1800271e2  mov     [rbp+var_8], rax
0x1800271e6  lea     rax, [rbp+arg_8]
0x1800271ea  mov     [rsp+60h+var_18], rax
0x1800271ef  lea     rax, [rbp+arg_0]
0x1800271f3  mov     [rsp+60h+var_20], rax
0x1800271f8  lea     rax, [rbp+arg_10]
0x1800271fc  mov     [rsp+60h+var_28], rax
0x180027201  lea     rax, [rbp+arg_18]
0x180027205  mov     [rsp+60h+var_30], rax
0x18002720a  lea     rax, [rbp+var_10]
0x18002720e  mov     [rsp+60h+var_38], rax
0x180027213  lea     rax, [rbp+var_8]
0x180027217  mov     [rbp+arg_8], ecx
0x18002721a  mov     rcx, r8
0x18002721d  mov     qword ptr [rsp+60h+var_40], rax
0x180027222  mov     [rbp+var_10], 1000000h
0x18002722a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002722f  mov     eax, [rbx+118h]
0x180027235  lea     r9, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002723c  mov     dword ptr [rsp+60h+var_38], eax; char *
0x180027240  lea     r8, aCrdpidmonitorR; "CRdpIdMonitor::RemoveMonitor"
0x180027247  lea     rdx, aMonitorremoveI; "MonitorRemove: Id %d"
0x18002724e  mov     [rsp+60h+var_40], 13Ch; unsigned int
0x180027256  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002725d  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180027262  mov     rdx, [rbx+18h]
0x180027266  mov     qword ptr [rbx+18h], 0
0x18002726e  test    rdx, rdx
0x180027271  jz      short loc_180027278
0x180027273  call    ??R?$default_delete@VCRdpIdCursor@@@std@@QEBAXPEAVCRdpIdCursor@@@Z; std::default_delete<CRdpIdCursor>::operator()(CRdpIdCursor *)
0x180027278  cmp     byte ptr [rbx+10h], 0
0x18002727c  jz      short loc_1800272BC
0x18002727e  mov     rdx, [rbx+0E0h]
0x180027285  mov     rcx, cs:IddDriverGlobals
0x18002728c  mov     rax, cs:qword_180057B38
0x180027293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027298  mov     rcx, [rbp+18h]; this
0x18002729c  lea     rdx, aFailedToUnplug; "Failed to unplug monitor"
0x1800272a3  mov     qword ptr [rsp+60h+var_40], rdx; int
0x1800272a8  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800272af  mov     edx, 149h; void *
0x1800272b4  mov     r9d, eax; char *
0x1800272b7  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800272bc  mov     rcx, rbx; this
0x1800272bf  mov     qword ptr [rbx+0E0h], 0
0x1800272ca  mov     byte ptr [rbx+10h], 0
0x1800272ce  call    ?DestroySwapchain@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::DestroySwapchain(void)
0x1800272d3  lea     rdi, [rbx+130h]
0x1800272da  mov     rcx, [rdi]
0x1800272dd  test    rcx, rcx
0x1800272e0  jz      short loc_18002731A
0x1800272e2  mov     rax, [rcx]
0x1800272e5  mov     rax, [rax+28h]
0x1800272e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272ee  mov     rcx, [rbp+18h]; this
0x1800272f2  lea     rdx, aFailedToStopFr; "Failed to stop frame processor"
0x1800272f9  mov     qword ptr [rsp+60h+var_40], rdx; int
0x1800272fe  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027305  mov     edx, 15Ch; void *
0x18002730a  mov     r9d, eax; char *
0x18002730d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027312  mov     rcx, rdi
0x180027315  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x18002731a  lea     rdi, [rbx+138h]
0x180027321  mov     rcx, [rdi]
0x180027324  test    rcx, rcx
0x180027327  jz      short loc_180027361
0x180027329  mov     rax, [rcx]
0x18002732c  mov     rax, [rax+28h]
0x180027330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027335  mov     rcx, [rbp+18h]; this
0x180027339  lea     rdx, aFailedToStopMo; "Failed to stop monitor encoding context"
0x180027340  mov     qword ptr [rsp+60h+var_40], rdx; int
0x180027345  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002734c  mov     edx, 166h; void *
0x180027351  mov     r9d, eax; char *
0x180027354  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027359  mov     rcx, rdi
0x18002735c  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x180027361  mov     rdx, [rbx+100h]
0x180027368  mov     qword ptr [rbx+100h], 0
0x180027373  test    rdx, rdx
0x180027376  jz      short loc_18002737D
0x180027378  call    ??R?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@QEBAXPEAVCRenderAdapter@Graphics@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>::operator()(Rdp::Utils::Graphics::CRenderAdapter *)
0x18002737d  lea     rcx, [rbx+108h]
0x180027384  add     rsp, 60h
0x180027388  pop     rdi
0x180027389  pop     rbx
0x18002738a  pop     rbp
0x18002738b  jmp     ?reset@?$shared_ptr@VCRenderDevice@Graphics@Utils@Rdp@@@std@@QEAAXXZ; std::shared_ptr<Rdp::Utils::Graphics::CRenderDevice>::reset(void)
```
