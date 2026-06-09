# CRdpIdAdapter::AddMonitors(std::vector<std::shared_ptr<CMonitorConfig>,std::allocator<std::shared_ptr<CMonitorConfig>>> const &)

- ea: `0x18001556c`
- end: `0x180015774`
- name: `?AddMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a860`
- `0x18001adec`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x18000d614`
- `0x18001072c`
- `0x1800136b8`
- `0x180013a08`
- `0x18001556c`
- `0x18001dd70`
- `0x180021570`
- `0x180021830`
- `0x180025180`

## string_xrefs

- `0x180015662`: `AdapterCreateMonitors: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CRdpIdAdapter::AddMonitors(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rsi
  _QWORD *v8; // r15
  __int64 v9; // rax
  CRdpIdMonitor *v10; // rbx
  __int64 v11; // rdx
  CRdpIdMonitor *v12; // rax
  std::_Ref_count_base *v13; // rcx
  char *v14; // [rsp+30h] [rbp-29h]
  __int64 v15; // [rsp+50h] [rbp-9h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-1h]
  CRdpIdMonitor *v17[2]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v18[64]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v20; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+6Fh] BYREF
  GUID *v22; // [rsp+D0h] [rbp+77h] BYREF
  const char *v23; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x470000000000LL) )
  {
    v21 = (__int64)(a2[1] - *a2) >> 4;
    v20 = *(_DWORD *)(a1 + 516);
    v22 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v23 = "RdpIdd";
    v15 = 0x1000000;
    v17[0] = (CRdpIdMonitor *)"Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&word_18004DB8E,
      v5,
      v6,
      (__int64)v17,
      (__int64)&v15,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterCreateMonitors: %d",
    "CRdpIdAdapter::AddMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x3B5u,
    (__int64)(a2[1] - *a2) >> 4);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x3BB,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x8000FFFFLL,
    (__int64)(*(_QWORD *)(a1 + 184) - *(_QWORD *)(a1 + 176)) >> 2 < (unsigned __int64)((__int64)(a2[1] - *a2) >> 4),
    (bool)"Exhausted available virtual monitor connectors",
    v14);
  v7 = (_QWORD *)*a2;
  v8 = (_QWORD *)a2[1];
  while ( v7 != v8 )
  {
    v9 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(a1, &v15);
    std::make_shared<CRdpIdMonitor,unsigned int &,std::shared_ptr<CMonitorConfig> const &,std::shared_ptr<CRdpIdAdapter>>(
      v17,
      *(_QWORD *)(a1 + 184) - 4LL,
      v7,
      v9);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    *(_QWORD *)(a1 + 184) -= 4LL;
    v10 = v17[0];
    CRdpIdMonitor::HPDMonitor(v17[0]);
    v11 = *(_QWORD *)std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Try_emplace<RDP_MONITORCONFIG_MONITOR_ID const &,>(
                       a1 + 160,
                       v18,
                       *v7 + 36LL);
    v12 = v17[1];
    *(_OWORD *)v17 = 0;
    *(_QWORD *)(v11 + 48) = v10;
    v13 = *(std::_Ref_count_base **)(v11 + 56);
    *(_QWORD *)(v11 + 56) = v12;
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    v7 += 2;
  }
}

```

## disassembly

```asm
0x18001556c  push    rbp
0x18001556e  push    rbx
0x18001556f  push    rsi
0x180015570  push    rdi
0x180015571  push    r14
0x180015573  push    r15
0x180015575  lea     rbp, [rsp-2Fh]
0x18001557a  sub     rsp, 88h
0x180015581  mov     rbx, rdx
0x180015584  mov     rdi, rcx
0x180015587  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001558c  mov     r8, [rax+8]
0x180015590  mov     eax, [r8]
0x180015593  cmp     eax, 4
0x180015596  jbe     loc_18001563C
0x18001559c  mov     rdx, 470000000000h
0x1800155a6  mov     rcx, r8
0x1800155a9  call    _tlgKeywordOn
0x1800155ae  test    al, al
0x1800155b0  jz      loc_18001563C
0x1800155b6  mov     rax, [rbx+8]
0x1800155ba  sub     rax, [rbx]
0x1800155bd  sar     rax, 4
0x1800155c1  mov     [rbp+57h+arg_8], rax
0x1800155c5  mov     eax, [rdi+204h]
0x1800155cb  mov     [rbp+57h+arg_0], eax
0x1800155ce  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800155d5  mov     [rbp+57h+arg_10], rax
0x1800155d9  lea     rax, aRdpidd; "RdpIdd"
0x1800155e0  mov     [rbp+57h+arg_18], rax
0x1800155e4  mov     [rbp+57h+var_60], 1000000h
0x1800155ec  lea     rax, aCheckpoint; "Checkpoint"
0x1800155f3  mov     [rbp+57h+var_50], rax
0x1800155f7  lea     rax, [rbp+57h+arg_8]
0x1800155fb  mov     [rsp+0B0h+var_68], rax
0x180015600  lea     rax, [rbp+57h+arg_0]
0x180015604  mov     [rsp+0B0h+var_70], rax
0x180015609  lea     rax, [rbp+57h+arg_10]
0x18001560d  mov     [rsp+0B0h+var_78], rax
0x180015612  lea     rax, [rbp+57h+arg_18]
0x180015616  mov     [rsp+0B0h+var_80], rax; char *
0x18001561b  lea     rax, [rbp+57h+var_60]
0x18001561f  mov     qword ptr [rsp+0B0h+var_88], rax
0x180015624  lea     rax, [rbp+57h+var_50]
0x180015628  mov     qword ptr [rsp+0B0h+var_90], rax
0x18001562d  lea     rdx, word_18004DB8E
0x180015634  mov     rcx, r8
0x180015637  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001563c  mov     rax, [rbx+8]
0x180015640  sub     rax, [rbx]
0x180015643  sar     rax, 4
0x180015647  mov     qword ptr [rsp+0B0h+var_88], rax
0x18001564c  mov     dword ptr [rsp+0B0h+var_90], 3B5h; unsigned int
0x180015654  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001565b  lea     r8, aCrdpidadapterA; "CRdpIdAdapter::AddMonitors"
0x180015662  lea     rdx, aAdaptercreatem; "AdapterCreateMonitors: %d"
0x180015669  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180015670  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180015675  mov     rcx, [rdi+0B8h]
0x18001567c  sub     rcx, [rdi+0B0h]
0x180015683  sar     rcx, 2
0x180015687  mov     rax, [rbx+8]
0x18001568b  sub     rax, [rbx]
0x18001568e  sar     rax, 4
0x180015692  cmp     rcx, rax
0x180015695  setb    al
0x180015698  mov     rcx, [rbp+5Fh]; this
0x18001569c  lea     rdx, aExhaustedAvail; "Exhausted available virtual monitor con"...
0x1800156a3  mov     qword ptr [rsp+0B0h+var_88], rdx; bool
0x1800156a8  mov     [rsp+0B0h+var_90], al; char
0x1800156ac  mov     r9d, 8000FFFFh; char *
0x1800156b2  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800156b9  mov     edx, 3BBh; void *
0x1800156be  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800156c3  mov     rsi, [rbx]
0x1800156c6  mov     r15, [rbx+8]
0x1800156ca  jmp     loc_18001575A
0x1800156cf  lea     rdx, [rbp+57h+var_60]
0x1800156d3  mov     rcx, rdi
0x1800156d6  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x1800156db  nop
0x1800156dc  mov     rdx, [rdi+0B8h]
0x1800156e3  sub     rdx, 4
0x1800156e7  mov     r9, rax
0x1800156ea  mov     r8, rsi
0x1800156ed  lea     rcx, [rbp+57h+var_50]
0x1800156f1  call    ??$make_shared@VCRdpIdMonitor@@AEAIAEBV?$shared_ptr@VCMonitorConfig@@@std@@V?$shared_ptr@VCRdpIdAdapter@@@3@@std@@YA?AV?$shared_ptr@VCRdpIdMonitor@@@0@AEAIAEBV?$shared_ptr@VCMonitorConfig@@@0@$$QEAV?$shared_ptr@VCRdpIdAdapter@@@0@@Z; std::make_shared<CRdpIdMonitor,uint &,std::shared_ptr<CMonitorConfig> const &,std::shared_ptr<CRdpIdAdapter>>(uint &,std::shared_ptr<CMonitorConfig> const &,std::shared_ptr<CRdpIdAdapter> &&)
0x1800156f6  nop
0x1800156f7  mov     rcx, [rbp+57h+var_58]; this
0x1800156fb  test    rcx, rcx
0x1800156fe  jz      short loc_180015705
0x180015700  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015705  sub     qword ptr [rdi+0B8h], 4
0x18001570d  mov     rbx, [rbp+57h+var_50]
0x180015711  mov     rcx, rbx; this
0x180015714  call    ?HPDMonitor@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::HPDMonitor(void)
0x180015719  mov     r8, [rsi]
0x18001571c  add     r8, 24h ; '$'
0x180015720  lea     rdx, [rbp+57h+var_40]
0x180015724  lea     rcx, [rdi+0A0h]
0x18001572b  call    ??$_Try_emplace@AEBURDP_MONITORCONFIG_MONITOR_ID@@$$V@?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@_N@1@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Try_emplace<RDP_MONITORCONFIG_MONITOR_ID const &,>(RDP_MONITORCONFIG_MONITOR_ID const &)
0x180015730  mov     rdx, [rax]
0x180015733  mov     rax, [rbp+57h+var_50+8]
0x180015737  xorps   xmm0, xmm0
0x18001573a  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18001573f  mov     [rdx+30h], rbx
0x180015743  mov     rcx, [rdx+38h]; this
0x180015747  mov     [rdx+38h], rax
0x18001574b  test    rcx, rcx
0x18001574e  jz      short loc_180015756
0x180015750  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015755  nop
0x180015756  add     rsi, 10h
0x18001575a  cmp     rsi, r15
0x18001575d  jnz     loc_1800156CF
0x180015763  add     rsp, 88h
0x18001576a  pop     r15
0x18001576c  pop     r14
0x18001576e  pop     rdi
0x18001576f  pop     rsi
0x180015770  pop     rbx
0x180015771  pop     rbp
0x180015772  retn
```
