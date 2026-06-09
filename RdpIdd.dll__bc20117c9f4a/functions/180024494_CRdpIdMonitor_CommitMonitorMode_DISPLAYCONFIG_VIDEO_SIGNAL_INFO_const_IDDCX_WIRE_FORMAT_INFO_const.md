# CRdpIdMonitor::CommitMonitorMode(DISPLAYCONFIG_VIDEO_SIGNAL_INFO const &,IDDCX_WIRE_FORMAT_INFO const &)

- ea: `0x180024494`
- end: `0x180024766`
- name: `?CommitMonitorMode@CRdpIdMonitor@@QEAAXAEBUDISPLAYCONFIG_VIDEO_SIGNAL_INFO@@AEBUIDDCX_WIRE_FORMAT_INFO@@@Z`
- size: `722`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, const struct DISPLAYCONFIG_VIDEO_SIGNAL_INFO *, const struct IDDCX_WIRE_FORMAT_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb40`

## callees

- `0x180001af0`
- `0x180004d68`
- `0x18000d614`
- `0x180017ac8`
- `0x18001cd04`
- `0x180021570`
- `0x180024494`
- `0x180027e24`
- `0x18003f010`

## string_xrefs

- `0x180024667`: `CRdpIdMonitor::CommitMonitorMode`
- `0x18002466e`: `MonitorCommitMode: Id %d`

## pseudocode

```c
void __fastcall CRdpIdMonitor::CommitMonitorMode(
        CRdpIdMonitor *this,
        const struct DISPLAYCONFIG_VIDEO_SIGNAL_INFO *a2,
        const struct IDDCX_WIRE_FORMAT_INFO *a3)
{
  _DWORD *v6; // r9
  int v7; // r8d
  int v8; // r9d
  _DWORD *v9; // rcx
  UINT32 v10; // edx
  UINT32 v11; // eax
  unsigned int v12; // eax
  char *v13; // [rsp+28h] [rbp-118h]
  char *v14; // [rsp+28h] [rbp-118h]
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  UINT32 cy; // [rsp+C4h] [rbp-7Ch] BYREF
  UINT32 cx; // [rsp+C8h] [rbp-78h] BYREF
  UINT32 v18; // [rsp+CCh] [rbp-74h] BYREF
  UINT32 v19; // [rsp+D0h] [rbp-70h] BYREF
  UINT32 Denominator; // [rsp+D4h] [rbp-6Ch] BYREF
  UINT32 Numerator; // [rsp+D8h] [rbp-68h] BYREF
  UINT32 v22; // [rsp+DCh] [rbp-64h] BYREF
  UINT32 v23; // [rsp+E0h] [rbp-60h] BYREF
  int v24; // [rsp+E4h] [rbp-5Ch] BYREF
  int v25; // [rsp+E8h] [rbp-58h] BYREF
  UINT64 pixelRate; // [rsp+F0h] [rbp-50h] BYREF
  GUID *v27; // [rsp+F8h] [rbp-48h] BYREF
  const char *v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  const char *v30; // [rsp+110h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+8h]
  int v32; // [rsp+150h] [rbp+10h] BYREF
  int v33; // [rsp+158h] [rbp+18h] BYREF
  int v34; // [rsp+160h] [rbp+20h] BYREF
  int v35; // [rsp+168h] [rbp+28h] BYREF

  v6 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v6 > 4u && (unsigned __int8)tlgKeywordOn(v6, 0x470000000000LL) )
  {
    v32 = *((_DWORD *)a3 + 4);
    v33 = *((_DWORD *)a3 + 3);
    v34 = *((_DWORD *)a3 + 2);
    v35 = *((_DWORD *)a3 + 1);
    v15 = *(_DWORD *)a3;
    cy = a2->totalSize.cy;
    cx = a2->totalSize.cx;
    v18 = a2->activeSize.cy;
    v19 = a2->activeSize.cx;
    Denominator = a2->vSyncFreq.Denominator;
    Numerator = a2->vSyncFreq.Numerator;
    v22 = a2->hSyncFreq.Denominator;
    v23 = a2->hSyncFreq.Numerator;
    pixelRate = a2->pixelRate;
    v24 = *(_DWORD *)(*((_QWORD *)this + 29) + 516LL);
    v25 = *((_DWORD *)this + 70);
    v27 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v28 = "RdpIdd";
    v29 = 0x1000000;
    v30 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)word_18004E69A,
      v7,
      v8,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&pixelRate,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&Numerator,
      (__int64)&Denominator,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&cx,
      (__int64)&cy,
      (__int64)&v15,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32);
  }
  LODWORD(v13) = *((_DWORD *)this + 70);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"MonitorCommitMode: Id %d",
    "CRdpIdMonitor::CommitMonitorMode",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    0x5A0u,
    v13);
  v9 = (_DWORD *)*((_QWORD *)this + 26);
  v10 = v9[24];
  v11 = v9[25];
  if ( *(_DWORD *)(*((_QWORD *)this + 29) + 440LL) == 3 && (v9[27] == 270 || v9[27] == 90) )
  {
    v10 = v9[25];
    v11 = v9[24];
  }
  if ( !a2->activeSize.cx || !a2->activeSize.cy || a2->activeSize.cx > v10 || a2->activeSize.cy > v11 )
    CRdpIdAdapter::ReportCriticalError(*((_QWORD *)this + 29), 2, 3, 2147500037LL);
  *(_OWORD *)((char *)this + 136) = *(_OWORD *)&a2->pixelRate;
  *(_OWORD *)((char *)this + 152) = *(_OWORD *)&a2->vSyncFreq.Numerator;
  *(_OWORD *)((char *)this + 168) = *(_OWORD *)&a2->totalSize.cx;
  *(_OWORD *)((char *)this + 184) = *(_OWORD *)a3;
  *((_DWORD *)this + 50) = *((_DWORD *)a3 + 4);
  CRdpIdMonitor::SetWireFormatInfoProperties(this);
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 39) + 64LL))(*((_QWORD *)this + 39), 16);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x5D1,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)v12,
    (int)"Failed to set wire format info",
    v14);
}

```

## disassembly

```asm
0x180024494  push    rbp
0x180024496  push    rbx
0x180024497  push    rsi
0x180024498  push    rdi
0x180024499  lea     rbp, [rsp+18h]
0x18002449e  sub     rsp, 128h
0x1800244a5  mov     rsi, r8
0x1800244a8  mov     rdi, rdx
0x1800244ab  mov     rbx, rcx
0x1800244ae  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800244b3  mov     r9, [rax+8]
0x1800244b7  mov     eax, [r9]
0x1800244ba  cmp     eax, 4
0x1800244bd  jbe     loc_18002464E
0x1800244c3  mov     rdx, 470000000000h
0x1800244cd  mov     rcx, r9
0x1800244d0  call    _tlgKeywordOn
0x1800244d5  test    al, al
0x1800244d7  jz      loc_18002464E
0x1800244dd  mov     eax, [rsi+10h]
0x1800244e0  mov     [rbp+arg_0], eax
0x1800244e3  mov     eax, [rsi+0Ch]
0x1800244e6  mov     [rbp+arg_8], eax
0x1800244e9  mov     eax, [rsi+8]
0x1800244ec  mov     [rbp+arg_10], eax
0x1800244ef  mov     eax, [rsi+4]
0x1800244f2  mov     [rbp+arg_18], eax
0x1800244f5  mov     eax, [rsi]
0x1800244f7  mov     [rbp+var_80], eax
0x1800244fa  mov     eax, [rdi+24h]
0x1800244fd  mov     [rbp+var_7C], eax
0x180024500  mov     eax, [rdi+20h]
0x180024503  mov     [rbp+var_78], eax
0x180024506  mov     eax, [rdi+1Ch]
0x180024509  mov     [rbp+var_74], eax
0x18002450c  mov     eax, [rdi+18h]
0x18002450f  mov     [rbp+var_70], eax
0x180024512  mov     eax, [rdi+14h]
0x180024515  mov     [rbp+var_6C], eax
0x180024518  mov     eax, [rdi+10h]
0x18002451b  mov     [rbp+var_68], eax
0x18002451e  mov     eax, [rdi+0Ch]
0x180024521  mov     [rbp+var_64], eax
0x180024524  mov     eax, [rdi+8]
0x180024527  mov     [rbp+var_60], eax
0x18002452a  mov     rax, [rdi]
0x18002452d  mov     [rbp+var_50], rax
0x180024531  mov     rax, [rbx+0E8h]
0x180024538  mov     ecx, [rax+204h]
0x18002453e  mov     [rbp+var_5C], ecx
0x180024541  mov     eax, [rbx+118h]
0x180024547  mov     [rbp+var_58], eax
0x18002454a  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180024551  mov     [rbp+var_48], rax
0x180024555  lea     rax, aRdpidd; "RdpIdd"
0x18002455c  mov     [rbp+var_40], rax
0x180024560  mov     [rbp+var_38], 1000000h
0x180024568  lea     rax, aCheckpoint; "Checkpoint"
0x18002456f  mov     [rbp+var_30], rax
0x180024573  lea     rax, [rbp+arg_0]
0x180024577  mov     [rsp+140h+var_88], rax
0x18002457f  lea     rax, [rbp+arg_8]
0x180024583  mov     [rsp+140h+var_90], rax
0x18002458b  lea     rax, [rbp+arg_10]
0x18002458f  mov     [rsp+140h+var_98], rax
0x180024597  lea     rax, [rbp+arg_18]
0x18002459b  mov     [rsp+140h+var_A0], rax
0x1800245a3  lea     rax, [rbp+var_80]
0x1800245a7  mov     [rsp+140h+var_A8], rax
0x1800245af  lea     rax, [rbp+var_7C]
0x1800245b3  mov     [rsp+140h+var_B0], rax
0x1800245bb  lea     rax, [rbp+var_78]
0x1800245bf  mov     [rsp+140h+var_B8], rax
0x1800245c7  lea     rax, [rbp+var_74]
0x1800245cb  mov     [rsp+140h+var_C0], rax
0x1800245d3  lea     rax, [rbp+var_70]
0x1800245d7  mov     [rsp+140h+var_C8], rax
0x1800245dc  lea     rax, [rbp+var_6C]
0x1800245e0  mov     [rsp+140h+var_D0], rax
0x1800245e5  lea     rax, [rbp+var_68]
0x1800245e9  mov     [rsp+140h+var_D8], rax
0x1800245ee  lea     rax, [rbp+var_64]
0x1800245f2  mov     [rsp+140h+var_E0], rax
0x1800245f7  lea     rax, [rbp+var_60]
0x1800245fb  mov     [rsp+140h+var_E8], rax
0x180024600  lea     rax, [rbp+var_50]
0x180024604  mov     [rsp+140h+var_F0], rax
0x180024609  lea     rax, [rbp+var_5C]
0x18002460d  mov     [rsp+140h+var_F8], rax
0x180024612  lea     rax, [rbp+var_58]
0x180024616  mov     [rsp+140h+var_100], rax
0x18002461b  lea     rax, [rbp+var_48]
0x18002461f  mov     [rsp+140h+var_108], rax
0x180024624  lea     rax, [rbp+var_40]
0x180024628  mov     [rsp+140h+var_110], rax
0x18002462d  lea     rax, [rbp+var_38]
0x180024631  mov     [rsp+140h+var_118], rax
0x180024636  lea     rax, [rbp+var_30]
0x18002463a  mov     qword ptr [rsp+140h+var_120], rax
0x18002463f  lea     rdx, word_18004E69A
0x180024646  mov     rcx, r9
0x180024649  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@U2@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@646666666666666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002464e  mov     eax, [rbx+118h]
0x180024654  mov     dword ptr [rsp+140h+var_118], eax; char *
0x180024658  mov     [rsp+140h+var_120], 5A0h; unsigned int
0x180024660  lea     r9, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180024667  lea     r8, aCrdpidmonitorC_0; "CRdpIdMonitor::CommitMonitorMode"
0x18002466e  lea     rdx, aMonitorcommitm; "MonitorCommitMode: Id %d"
0x180024675  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002467c  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180024681  mov     rcx, [rbx+0D0h]
0x180024688  mov     edx, [rcx+60h]
0x18002468b  mov     eax, [rcx+64h]
0x18002468e  mov     r10, [rbx+0E8h]
0x180024695  mov     r8d, 3
0x18002469b  cmp     [r10+1B8h], r8d
0x1800246a2  jnz     short loc_1800246B8
0x1800246a4  cmp     dword ptr [rcx+6Ch], 10Eh
0x1800246ab  jz      short loc_1800246B3
0x1800246ad  cmp     dword ptr [rcx+6Ch], 5Ah ; 'Z'
0x1800246b1  jnz     short loc_1800246B8
0x1800246b3  mov     edx, eax
0x1800246b5  mov     eax, [rcx+60h]
0x1800246b8  cmp     dword ptr [rdi+18h], 0
0x1800246bc  jz      short loc_1800246CE
0x1800246be  cmp     dword ptr [rdi+1Ch], 0
0x1800246c2  jz      short loc_1800246CE
0x1800246c4  cmp     [rdi+18h], edx
0x1800246c7  ja      short loc_1800246CE
0x1800246c9  cmp     [rdi+1Ch], eax
0x1800246cc  jbe     short loc_1800246E1
0x1800246ce  mov     edx, 2
0x1800246d3  mov     r9d, 80004005h
0x1800246d9  mov     rcx, r10
0x1800246dc  call    ?ReportCriticalError@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalError(FailFastMajorCode,uint,long)
0x1800246e1  movups  xmm0, xmmword ptr [rdi]
0x1800246e4  movups  xmmword ptr [rbx+88h], xmm0
0x1800246eb  movups  xmm1, xmmword ptr [rdi+10h]
0x1800246ef  movups  xmmword ptr [rbx+98h], xmm1
0x1800246f6  movups  xmm0, xmmword ptr [rdi+20h]
0x1800246fa  movups  xmmword ptr [rbx+0A8h], xmm0
0x180024701  movups  xmm0, xmmword ptr [rsi]
0x180024704  movups  xmmword ptr [rbx+0B8h], xmm0
0x18002470b  mov     eax, [rsi+10h]
0x18002470e  mov     [rbx+0C8h], eax
0x180024714  mov     rcx, rbx; this
0x180024717  call    ?SetWireFormatInfoProperties@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::SetWireFormatInfoProperties(void)
0x18002471c  mov     rcx, [rbx+138h]
0x180024723  mov     rax, [rcx]
0x180024726  mov     edx, 10h
0x18002472b  mov     rax, [rax+40h]
0x18002472f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024734  mov     rcx, [rbp+8]; this
0x180024738  lea     rdx, aFailedToSetWir; "Failed to set wire format info"
0x18002473f  mov     qword ptr [rsp+140h+var_120], rdx; int
0x180024744  mov     r9d, eax; char *
0x180024747  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002474e  mov     edx, 5D1h; void *
0x180024753  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024758  nop
0x180024759  add     rsp, 128h
0x180024760  pop     rdi
0x180024761  pop     rsi
0x180024762  pop     rbx
0x180024763  pop     rbp
0x180024764  retn
```
