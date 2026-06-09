# CRdpIdAdapter::DeleteMonitors(std::vector<std::shared_ptr<CMonitorConfig>,std::allocator<std::shared_ptr<CMonitorConfig>>> const &)

- ea: `0x180015a88`
- end: `0x180015d77`
- name: `?DeleteMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a860`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x1800089f0`
- `0x18000cb5c`
- `0x18000d614`
- `0x18000e190`
- `0x18000e6a0`
- `0x180012f34`
- `0x180015a88`
- `0x180017674`
- `0x18001ddbc`
- `0x180020704`
- `0x180021058`
- `0x180021570`
- `0x180027168`

## string_xrefs

- `0x180015b6e`: `CRdpIdAdapter::DeleteMonitors`
- `0x180015c9a`: `CRdpIdAdapter::DeleteMonitors`
- `0x180015b79`: `AdapterDeleteMonitors: %d`

## pseudocode

```c
void __fastcall CRdpIdAdapter::DeleteMonitors(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rbx
  _QWORD *v8; // rsi
  bool v9; // dl
  __int64 v10; // rdi
  _DWORD *v11; // rdx
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rcx
  CMonitorConfig *v15; // rax
  const struct RDP_MONITORCONFIG_MONITOR_ID *MonitorId; // r13
  int v17; // ebx
  int v18; // edi
  int v19; // esi
  int v20; // r14d
  int v21; // r15d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  int v26; // r10d
  int v27; // r11d
  int v28; // ebx
  int v29; // edi
  int v30; // esi
  int v31; // r14d
  int v32; // r15d
  int v33; // r12d
  unsigned int v34; // eax
  int v35; // edx
  int v36; // r10d
  int v37; // r11d
  char *v38; // [rsp+28h] [rbp-51h]
  char *v39; // [rsp+28h] [rbp-51h]
  __int64 v40; // [rsp+30h] [rbp-49h]
  __int64 v41; // [rsp+30h] [rbp-49h]
  __int64 v42; // [rsp+38h] [rbp-41h]
  __int64 v43; // [rsp+38h] [rbp-41h]
  __int64 v44; // [rsp+40h] [rbp-39h]
  __int64 v45; // [rsp+40h] [rbp-39h]
  __int64 v46; // [rsp+48h] [rbp-31h]
  __int64 v47; // [rsp+48h] [rbp-31h]
  __int64 v48; // [rsp+50h] [rbp-29h]
  __int64 v49; // [rsp+58h] [rbp-21h]
  __int64 v50; // [rsp+60h] [rbp-19h]
  __int64 v51; // [rsp+68h] [rbp-11h]
  __int64 v52; // [rsp+70h] [rbp-9h]
  __int64 v53; // [rsp+78h] [rbp-1h]
  const char *v54; // [rsp+80h] [rbp+7h] BYREF
  __int64 v55; // [rsp+88h] [rbp+Fh] BYREF
  const char *v56; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  const struct RDP_MONITORCONFIG_MONITOR_ID *v58; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v59; // [rsp+F0h] [rbp+77h] BYREF
  GUID *v60; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x470000000000LL) )
  {
    v59 = (__int64)(a2[1] - *a2) >> 4;
    LODWORD(v58) = *(_DWORD *)(a1 + 516);
    v60 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v54 = "RdpIdd";
    v56 = "Checkpoint";
    v55 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&unk_18004DAF8,
      v5,
      v6,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v54,
      (__int64)&v60,
      (__int64)&v58,
      (__int64)&v59);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterDeleteMonitors: %d",
    "CRdpIdAdapter::DeleteMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x3EEu,
    (__int64)(a2[1] - *a2) >> 4);
  v7 = (_QWORD *)a2[1];
  v8 = (_QWORD *)*a2;
  while ( v7 != v8 )
  {
    v7 -= 2;
    std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
      a1 + 160,
      &v59,
      *v7 + 36LL);
    v10 = v59;
    if ( v59 == *(_QWORD *)(a1 + 160) )
    {
      v15 = (CMonitorConfig *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(v7);
      MonitorId = CMonitorConfig::GetMonitorId(v15);
      v58 = MonitorId;
      v17 = *((unsigned __int8 *)MonitorId + 10);
      v18 = *((unsigned __int8 *)MonitorId + 9);
      v19 = *((unsigned __int8 *)MonitorId + 8);
      v20 = *((unsigned __int16 *)MonitorId + 3);
      v21 = *((unsigned __int16 *)MonitorId + 2);
      Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
      LODWORD(v46) = v18;
      LODWORD(v44) = v19;
      LODWORD(v42) = v20;
      LODWORD(v40) = v21;
      LODWORD(v38) = *(_DWORD *)MonitorId;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        Ifr,
        (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        "CRdpIdAdapter::DeleteMonitors",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x3FEu,
        v38,
        v40,
        v42,
        v44,
        v46,
        v17,
        v27,
        v26,
        v25,
        v24,
        v23);
      v28 = *((unsigned __int8 *)MonitorId + 12);
      v29 = *((unsigned __int8 *)MonitorId + 11);
      v30 = *((unsigned __int8 *)MonitorId + 10);
      v31 = *((unsigned __int8 *)MonitorId + 9);
      v32 = *((unsigned __int8 *)MonitorId + 8);
      v33 = *((unsigned __int16 *)MonitorId + 3);
      LODWORD(MonitorId) = *((unsigned __int16 *)MonitorId + 2);
      v34 = wil::verify_hresult<long>(2147943568LL);
      LODWORD(v53) = v35;
      LODWORD(v52) = v36;
      LODWORD(v51) = v37;
      LODWORD(v50) = v28;
      LODWORD(v49) = v29;
      LODWORD(v48) = v30;
      LODWORD(v47) = v31;
      LODWORD(v45) = v32;
      LODWORD(v43) = v33;
      LODWORD(v41) = (_DWORD)MonitorId;
      LODWORD(v39) = *(_DWORD *)v58;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x405,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)v34,
        (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        v39,
        v41,
        v43,
        v45,
        v47,
        v48,
        v49,
        v50,
        v51,
        v52,
        v53);
    }
    CRdpIdMonitor::RemoveMonitor(*(CRdpIdMonitor **)(v59 + 48), v9);
    v11 = *(_DWORD **)(a1 + 184);
    v12 = *(_DWORD *)(*(_QWORD *)(v10 + 48) + 284LL);
    LODWORD(v58) = v12;
    if ( v11 == *(_DWORD **)(a1 + 192) )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a1 + 176, v11, &v58);
    }
    else
    {
      *v11 = v12;
      *(_QWORD *)(a1 + 184) += 4LL;
    }
    v13 = std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Extract(
            a1 + 160,
            v10);
    std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(
      v14,
      v13);
  }
}

```

## disassembly

```asm
0x180015a88  mov     [rsp-8+arg_0], rbx
0x180015a8d  push    rbp
0x180015a8e  push    rsi
0x180015a8f  push    rdi
0x180015a90  push    r12
0x180015a92  push    r13
0x180015a94  push    r14
0x180015a96  push    r15
0x180015a98  lea     rbp, [rsp-27h]
0x180015a9d  sub     rsp, 0A0h
0x180015aa4  mov     rsi, rdx
0x180015aa7  mov     r15, rcx
0x180015aaa  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180015aaf  mov     r8, [rax+8]
0x180015ab3  mov     eax, [r8]
0x180015ab6  cmp     eax, 4
0x180015ab9  jbe     loc_180015B60
0x180015abf  mov     rdx, 470000000000h
0x180015ac9  mov     rcx, r8
0x180015acc  call    _tlgKeywordOn
0x180015ad1  test    al, al
0x180015ad3  jz      loc_180015B60
0x180015ad9  mov     rax, [rsi+8]
0x180015add  lea     rdx, unk_18004DAF8
0x180015ae4  sub     rax, [rsi]
0x180015ae7  mov     rcx, r8
0x180015aea  sar     rax, 4
0x180015aee  mov     [rbp+57h+arg_10], rax
0x180015af2  mov     eax, [r15+204h]
0x180015af9  mov     dword ptr [rbp+57h+arg_8], eax
0x180015afc  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180015b03  mov     [rbp+57h+arg_18], rax
0x180015b07  lea     rax, aRdpidd; "RdpIdd"
0x180015b0e  mov     [rbp+57h+var_50], rax
0x180015b12  lea     rax, aCheckpoint; "Checkpoint"
0x180015b19  mov     [rbp+57h+var_40], rax
0x180015b1d  lea     rax, [rbp+57h+arg_10]
0x180015b21  mov     [rsp+0D0h+var_88], rax
0x180015b26  lea     rax, [rbp+57h+arg_8]
0x180015b2a  mov     [rsp+0D0h+var_90], rax
0x180015b2f  lea     rax, [rbp+57h+arg_18]
0x180015b33  mov     [rsp+0D0h+var_98], rax
0x180015b38  lea     rax, [rbp+57h+var_50]
0x180015b3c  mov     [rsp+0D0h+var_A0], rax
0x180015b41  lea     rax, [rbp+57h+var_48]
0x180015b45  mov     [rsp+0D0h+var_A8], rax
0x180015b4a  lea     rax, [rbp+57h+var_40]
0x180015b4e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180015b53  mov     [rbp+57h+var_48], 1000000h
0x180015b5b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180015b60  mov     rax, [rsi+8]
0x180015b64  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180015b6b  sub     rax, [rsi]
0x180015b6e  lea     r8, aCrdpidadapterD; "CRdpIdAdapter::DeleteMonitors"
0x180015b75  sar     rax, 4
0x180015b79  lea     rdx, aAdapterdeletem; "AdapterDeleteMonitors: %d"
0x180015b80  mov     [rsp+0D0h+var_A8], rax
0x180015b85  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180015b8c  mov     [rsp+0D0h+var_B0], 3EEh; unsigned int
0x180015b94  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180015b99  mov     rbx, [rsi+8]
0x180015b9d  mov     rsi, [rsi]
0x180015ba0  cmp     rbx, rsi
0x180015ba3  jz      short loc_180015C1D
0x180015ba5  add     rbx, 0FFFFFFFFFFFFFFF0h
0x180015ba9  lea     r14, [r15+0A0h]
0x180015bb0  lea     rdx, [rbp+57h+arg_10]
0x180015bb4  mov     rcx, r14
0x180015bb7  mov     r8, [rbx]
0x180015bba  add     r8, 24h ; '$'
0x180015bbe  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x180015bc3  mov     rdi, [rbp+57h+arg_10]
0x180015bc7  cmp     rdi, [r14]
0x180015bca  jz      short loc_180015C39
0x180015bcc  mov     rcx, [rdi+30h]; this
0x180015bd0  call    ?RemoveMonitor@CRdpIdMonitor@@QEAAX_N@Z; CRdpIdMonitor::RemoveMonitor(bool)
0x180015bd5  mov     rax, [rdi+30h]
0x180015bd9  lea     rcx, [r15+0B0h]
0x180015be0  mov     rdx, [rcx+8]
0x180015be4  mov     r8d, [rax+11Ch]
0x180015beb  mov     dword ptr [rbp+57h+arg_8], r8d
0x180015bef  cmp     rdx, [rcx+10h]
0x180015bf3  jz      short loc_180015BFF
0x180015bf5  mov     [rdx], r8d
0x180015bf8  add     qword ptr [rcx+8], 4
0x180015bfd  jmp     short loc_180015C08
0x180015bff  lea     r8, [rbp+57h+arg_8]
0x180015c03  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x180015c08  mov     rdx, rdi
0x180015c0b  mov     rcx, r14
0x180015c0e  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>)
0x180015c13  mov     rdx, rax
0x180015c16  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>> &,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180015c1b  jmp     short loc_180015BA0
0x180015c1d  mov     rbx, [rsp+0D0h+arg_0]
0x180015c25  add     rsp, 0A0h
0x180015c2c  pop     r15
0x180015c2e  pop     r14
0x180015c30  pop     r13
0x180015c32  pop     r12
0x180015c34  pop     rdi
0x180015c35  pop     rsi
0x180015c36  pop     rbp
0x180015c37  retn
0x180015c39  mov     rcx, rbx
0x180015c3c  call    ??$?CVCRdpIdMonitor@@$0A@@?$shared_ptr@VCRdpIdMonitor@@@std@@QEBAPEAVCRdpIdMonitor@@XZ; std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(void)
0x180015c41  mov     rcx, rax; this
0x180015c44  call    ?GetMonitorId@CMonitorConfig@@QEBAAEBURDP_MONITORCONFIG_MONITOR_ID@@XZ; CMonitorConfig::GetMonitorId(void)
0x180015c49  mov     r13, rax
0x180015c4c  mov     [rbp+57h+arg_8], rax
0x180015c50  movzx   edx, byte ptr [rax+0Fh]
0x180015c54  movzx   r8d, byte ptr [rax+0Eh]
0x180015c59  movzx   r9d, byte ptr [rax+0Dh]
0x180015c5e  movzx   r10d, byte ptr [rax+0Ch]
0x180015c63  movzx   r11d, byte ptr [rax+0Bh]
0x180015c68  movzx   ebx, byte ptr [rax+0Ah]
0x180015c6c  movzx   edi, byte ptr [rax+9]
0x180015c70  movzx   esi, byte ptr [rax+8]
0x180015c74  movzx   r14d, word ptr [rax+6]
0x180015c79  movzx   r15d, word ptr [rax+4]
0x180015c7e  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x180015c83  mov     dword ptr [rsp+0D0h+var_58], edx
0x180015c87  mov     rcx, rax; this
0x180015c8a  mov     eax, [r13+0]
0x180015c8e  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x180015c95  mov     dword ptr [rsp+0D0h+var_60], r8d
0x180015c9a  lea     r8, aCrdpidadapterD; "CRdpIdAdapter::DeleteMonitors"
0x180015ca1  mov     dword ptr [rsp+0D0h+var_68], r9d
0x180015ca6  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180015cad  mov     dword ptr [rsp+0D0h+var_70], r10d
0x180015cb2  mov     dword ptr [rsp+0D0h+var_78], r11d
0x180015cb7  mov     dword ptr [rsp+0D0h+var_80], ebx
0x180015cbb  mov     dword ptr [rsp+0D0h+var_88], edi
0x180015cbf  mov     dword ptr [rsp+0D0h+var_90], esi
0x180015cc3  mov     dword ptr [rsp+0D0h+var_98], r14d
0x180015cc8  mov     dword ptr [rsp+0D0h+var_A0], r15d
0x180015ccd  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180015cd1  mov     [rsp+0D0h+var_B0], 3FEh; unsigned int
0x180015cd9  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180015cde  movzx   edx, byte ptr [r13+0Fh]
0x180015ce3  mov     ecx, 80070490h
0x180015ce8  movzx   r10d, byte ptr [r13+0Eh]
0x180015ced  movzx   r11d, byte ptr [r13+0Dh]
0x180015cf2  movzx   ebx, byte ptr [r13+0Ch]
0x180015cf7  movzx   edi, byte ptr [r13+0Bh]
0x180015cfc  movzx   esi, byte ptr [r13+0Ah]
0x180015d01  movzx   r14d, byte ptr [r13+9]
0x180015d06  movzx   r15d, byte ptr [r13+8]
0x180015d0b  movzx   r12d, word ptr [r13+6]
0x180015d10  movzx   r13d, word ptr [r13+4]
0x180015d15  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180015d1a  mov     rcx, [rbp+5Fh]; this
0x180015d1e  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180015d25  mov     dword ptr [rsp+0D0h+var_58], edx
0x180015d29  mov     r9d, eax; char *
0x180015d2c  mov     rax, [rbp+57h+arg_8]
0x180015d30  mov     edx, 405h; void *
0x180015d35  mov     dword ptr [rsp+0D0h+var_60], r10d
0x180015d3a  mov     dword ptr [rsp+0D0h+var_68], r11d
0x180015d3f  mov     dword ptr [rsp+0D0h+var_70], ebx
0x180015d43  mov     eax, [rax]
0x180015d45  mov     dword ptr [rsp+0D0h+var_78], edi
0x180015d49  mov     dword ptr [rsp+0D0h+var_80], esi
0x180015d4d  mov     dword ptr [rsp+0D0h+var_88], r14d
0x180015d52  mov     dword ptr [rsp+0D0h+var_90], r15d
0x180015d57  mov     dword ptr [rsp+0D0h+var_98], r12d
0x180015d5c  mov     dword ptr [rsp+0D0h+var_A0], r13d
0x180015d61  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180015d65  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x180015d6c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180015d71  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
