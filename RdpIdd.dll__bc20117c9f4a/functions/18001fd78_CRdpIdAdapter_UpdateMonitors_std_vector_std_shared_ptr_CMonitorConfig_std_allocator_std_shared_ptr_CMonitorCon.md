# CRdpIdAdapter::UpdateMonitors(std::vector<std::shared_ptr<CMonitorConfig>,std::allocator<std::shared_ptr<CMonitorConfig>>> const &)

- ea: `0x18001fd78`
- end: `0x1800200e4`
- name: `?UpdateMonitors@CRdpIdAdapter@@AEAAXAEBV?$vector@V?$shared_ptr@VCMonitorConfig@@@std@@V?$allocator@V?$shared_ptr@VCMonitorConfig@@@std@@@2@@std@@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a860`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x1800089f0`
- `0x18000cb5c`
- `0x18000d614`
- `0x18000e190`
- `0x18000ea9c`
- `0x18001072c`
- `0x180012d18`
- `0x180013b68`
- `0x180013bb0`
- `0x180017674`
- `0x18001ddbc`
- `0x18001ddf4`
- `0x18001e634`
- `0x18001f2a0`
- `0x18001fd78`
- `0x180021058`
- `0x180021570`
- `0x18003f010`

## string_xrefs

- `0x18001fe71`: `CRdpIdAdapter::UpdateMonitors`
- `0x180020038`: `CRdpIdAdapter::UpdateMonitors`
- `0x18001fe78`: `AdapterUpdateMonitors: %d`
- `0x18001ff68`: `Failed to commit monitors`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRdpIdAdapter::UpdateMonitors(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rdi
  _QWORD *v8; // r14
  _DWORD *v9; // r15
  __int64 *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // eax
  CMonitorConfig *v16; // rax
  const struct RDP_MONITORCONFIG_MONITOR_ID *MonitorId; // r13
  int v18; // ebx
  int v19; // edi
  int v20; // esi
  int v21; // r14d
  int v22; // r15d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  int v27; // r10d
  int v28; // r11d
  int v29; // ebx
  int v30; // edi
  int v31; // esi
  int v32; // r14d
  int v33; // r15d
  int v34; // r12d
  unsigned int v35; // eax
  int v36; // edx
  int v37; // r10d
  int v38; // r11d
  char *v39; // [rsp+28h] [rbp-71h]
  char *v40; // [rsp+28h] [rbp-71h]
  __int64 v41; // [rsp+30h] [rbp-69h]
  __int64 v42; // [rsp+30h] [rbp-69h]
  __int64 v43; // [rsp+38h] [rbp-61h]
  __int64 v44; // [rsp+38h] [rbp-61h]
  __int64 v45; // [rsp+40h] [rbp-59h]
  __int64 v46; // [rsp+40h] [rbp-59h]
  __int64 v47; // [rsp+48h] [rbp-51h]
  __int64 v48; // [rsp+48h] [rbp-51h]
  int v49; // [rsp+50h] [rbp-49h]
  __int64 v50; // [rsp+50h] [rbp-49h]
  int v51; // [rsp+58h] [rbp-41h]
  __int64 v52; // [rsp+58h] [rbp-41h]
  int v53; // [rsp+60h] [rbp-39h]
  __int64 v54; // [rsp+60h] [rbp-39h]
  int v55; // [rsp+68h] [rbp-31h]
  __int64 v56; // [rsp+68h] [rbp-31h]
  int v57; // [rsp+70h] [rbp-29h]
  __int64 v58; // [rsp+70h] [rbp-29h]
  int v59; // [rsp+78h] [rbp-21h]
  __int64 v60; // [rsp+78h] [rbp-21h]
  const char *v61; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v62[2]; // [rsp+88h] [rbp-11h] BYREF
  const char *v63; // [rsp+98h] [rbp-1h] BYREF
  std::_Ref_count_base *v64; // [rsp+A0h] [rbp+7h]
  __int64 *v65[9]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  const struct RDP_MONITORCONFIG_MONITOR_ID *v67; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v68; // [rsp+110h] [rbp+77h] BYREF
  GUID *v69; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x470000000000LL) )
  {
    v68 = (__int64)(a2[1] - *a2) >> 4;
    LODWORD(v67) = *(_DWORD *)(a1 + 516);
    v69 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v61 = "RdpIdd";
    v62[0] = 0x1000000;
    v63 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&word_18004D9CE,
      v5,
      v6,
      (__int64)&v63,
      (__int64)v62,
      (__int64)&v61,
      (__int64)&v69,
      (__int64)&v67,
      (__int64)&v68);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterUpdateMonitors: %d",
    "CRdpIdAdapter::UpdateMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x461u,
    (__int64)(a2[1] - *a2) >> 4);
  std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>(v65);
  v7 = (_QWORD *)*a2;
  v8 = (_QWORD *)a2[1];
  if ( (_QWORD *)*a2 != v8 )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(
        a1 + 160,
        &v67,
        *v7 + 36LL);
      if ( v67 == *(const struct RDP_MONITORCONFIG_MONITOR_ID **)(a1 + 160) )
      {
        v16 = (CMonitorConfig *)std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(v7);
        MonitorId = CMonitorConfig::GetMonitorId(v16);
        v67 = MonitorId;
        v18 = *((unsigned __int8 *)MonitorId + 10);
        v19 = *((unsigned __int8 *)MonitorId + 9);
        v20 = *((unsigned __int8 *)MonitorId + 8);
        v21 = *((unsigned __int16 *)MonitorId + 3);
        v22 = *((unsigned __int16 *)MonitorId + 2);
        Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
        v59 = v24;
        v57 = v25;
        v55 = v26;
        v53 = v27;
        v51 = v28;
        v49 = v18;
        LODWORD(v47) = v19;
        LODWORD(v45) = v20;
        LODWORD(v43) = v21;
        LODWORD(v41) = v22;
        LODWORD(v39) = *(_DWORD *)MonitorId;
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          Ifr,
          (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
          "CRdpIdAdapter::UpdateMonitors",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          0x476u,
          v39,
          v41,
          v43,
          v45,
          v47,
          v49,
          v51,
          v53,
          v55,
          v57,
          v59);
        v29 = *((unsigned __int8 *)MonitorId + 12);
        v30 = *((unsigned __int8 *)MonitorId + 11);
        v31 = *((unsigned __int8 *)MonitorId + 10);
        v32 = *((unsigned __int8 *)MonitorId + 9);
        v33 = *((unsigned __int8 *)MonitorId + 8);
        v34 = *((unsigned __int16 *)MonitorId + 3);
        LODWORD(MonitorId) = *((unsigned __int16 *)MonitorId + 2);
        v35 = wil::verify_hresult<long>(2147943568LL);
        LODWORD(v60) = v36;
        LODWORD(v58) = v37;
        LODWORD(v56) = v38;
        LODWORD(v54) = v29;
        LODWORD(v52) = v30;
        LODWORD(v50) = v31;
        LODWORD(v48) = v32;
        LODWORD(v46) = v33;
        LODWORD(v44) = v34;
        LODWORD(v42) = (_DWORD)MonitorId;
        LODWORD(v40) = *(_DWORD *)v67;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x47D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
          (const char *)v35,
          (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
          v40,
          v42,
          v44,
          v46,
          v48,
          v50,
          v52,
          v54,
          v56,
          v58,
          v60);
      }
      v9 = (_DWORD *)((char *)v67 + 32);
      v10 = (__int64 *)std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(&v63, v7);
      v11 = *v10;
      *v10 = *(_QWORD *)(v12 + 208);
      *(_QWORD *)(v12 + 208) = v11;
      v13 = v10[1];
      v10[1] = *(_QWORD *)(v12 + 216);
      *(_QWORD *)(v12 + 216) = v13;
      if ( v64 )
        std::_Ref_count_base::_Decref(v64);
      std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Emplace<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &>(
        v65,
        v62,
        v9);
      v7 += 2;
    }
    while ( v7 != v8 );
  }
  if ( *(_DWORD *)(a1 + 440) == 3 )
    CRdpIdAdapter::UpdateDisplayConfigContainer(a1, v65);
  else
    CRdpIdAdapter::UpdateDisplayConfigNative(a1, v65);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 560) + 64LL))(*(_QWORD *)(a1 + 560));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x495,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v14,
    (int)"Failed to commit monitors",
    v39);
  return std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::~_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>(v65);
}

```

## disassembly

```asm
0x18001fd78  mov     [rsp-8+arg_0], rbx
0x18001fd7d  push    rbp
0x18001fd7e  push    rsi
0x18001fd7f  push    rdi
0x18001fd80  push    r12
0x18001fd82  push    r13
0x18001fd84  push    r14
0x18001fd86  push    r15
0x18001fd88  lea     rbp, [rsp-27h]
0x18001fd8d  sub     rsp, 0C0h
0x18001fd94  mov     rsi, rdx
0x18001fd97  mov     rbx, rcx
0x18001fd9a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001fd9f  mov     r8, [rax+8]
0x18001fda3  mov     eax, [r8]
0x18001fda6  cmp     eax, 4
0x18001fda9  jbe     loc_18001FE4F
0x18001fdaf  mov     rdx, 470000000000h
0x18001fdb9  mov     rcx, r8
0x18001fdbc  call    _tlgKeywordOn
0x18001fdc1  test    al, al
0x18001fdc3  jz      loc_18001FE4F
0x18001fdc9  mov     rax, [rsi+8]
0x18001fdcd  sub     rax, [rsi]
0x18001fdd0  sar     rax, 4
0x18001fdd4  mov     [rbp+57h+arg_10], rax
0x18001fdd8  mov     eax, [rbx+204h]
0x18001fdde  mov     dword ptr [rbp+57h+arg_8], eax
0x18001fde1  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001fde8  mov     [rbp+57h+arg_18], rax
0x18001fdec  lea     rax, aRdpidd; "RdpIdd"
0x18001fdf3  mov     [rbp+57h+var_70], rax
0x18001fdf7  mov     [rbp+57h+var_68], 1000000h
0x18001fdff  lea     rax, aCheckpoint; "Checkpoint"
0x18001fe06  mov     [rbp+57h+var_58], rax
0x18001fe0a  lea     rax, [rbp+57h+arg_10]
0x18001fe0e  mov     [rsp+0F0h+var_A8], rax
0x18001fe13  lea     rax, [rbp+57h+arg_8]
0x18001fe17  mov     [rsp+0F0h+var_B0], rax
0x18001fe1c  lea     rax, [rbp+57h+arg_18]
0x18001fe20  mov     [rsp+0F0h+var_B8], rax
0x18001fe25  lea     rax, [rbp+57h+var_70]
0x18001fe29  mov     [rsp+0F0h+var_C0], rax
0x18001fe2e  lea     rax, [rbp+57h+var_68]
0x18001fe32  mov     [rsp+0F0h+var_C8], rax
0x18001fe37  lea     rax, [rbp+57h+var_58]
0x18001fe3b  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18001fe40  lea     rdx, word_18004D9CE
0x18001fe47  mov     rcx, r8
0x18001fe4a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001fe4f  mov     rax, [rsi+8]
0x18001fe53  sub     rax, [rsi]
0x18001fe56  sar     rax, 4
0x18001fe5a  mov     [rsp+0F0h+var_C8], rax; char *
0x18001fe5f  mov     [rsp+0F0h+var_D0], 461h; unsigned int
0x18001fe67  lea     r12, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001fe6e  mov     r9, r12; char *
0x18001fe71  lea     r8, aCrdpidadapterU_1; "CRdpIdAdapter::UpdateMonitors"
0x18001fe78  lea     rdx, aAdapterupdatem; "AdapterUpdateMonitors: %d"
0x18001fe7f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001fe86  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001fe8b  lea     rcx, [rbp+57h+var_48]
0x18001fe8f  call    ??0?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@QEAA@XZ; std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>(void)
0x18001fe94  nop
0x18001fe95  mov     rdi, [rsi]
0x18001fe98  mov     r14, [rsi+8]
0x18001fe9c  cmp     rdi, r14
0x18001fe9f  jz      loc_18001FF35
0x18001fea5  lea     rsi, [rbx+0A0h]
0x18001feac  mov     r8, [rdi]
0x18001feaf  add     r8, 24h ; '$'
0x18001feb3  lea     rdx, [rbp+57h+arg_8]
0x18001feb7  mov     rcx, rsi
0x18001feba  call    ?find@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@@2@AEBURDP_MONITORCONFIG_MONITOR_ID@@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::find(RDP_MONITORCONFIG_MONITOR_ID const &)
0x18001febf  mov     rax, [rbp+57h+arg_8]
0x18001fec3  cmp     rax, [rsi]
0x18001fec6  jz      loc_18001FFAA
0x18001fecc  lea     r15, [rax+20h]
0x18001fed0  mov     r8, [r15+10h]
0x18001fed4  mov     rdx, rdi
0x18001fed7  lea     rcx, [rbp+57h+var_58]
0x18001fedb  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001fee0  mov     rdx, [rax]
0x18001fee3  mov     rcx, [r8+0D0h]
0x18001feea  mov     [rax], rcx
0x18001feed  mov     [r8+0D0h], rdx
0x18001fef4  mov     rdx, [rax+8]
0x18001fef8  mov     rcx, [r8+0D8h]
0x18001feff  mov     [rax+8], rcx
0x18001ff03  mov     [r8+0D8h], rdx
0x18001ff0a  mov     rcx, [rbp+57h+var_50]; this
0x18001ff0e  test    rcx, rcx
0x18001ff11  jz      short loc_18001FF18
0x18001ff13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ff18  mov     r8, r15
0x18001ff1b  lea     rdx, [rbp+57h+var_68]
0x18001ff1f  lea     rcx, [rbp+57h+var_48]
0x18001ff23  call    ??$_Emplace@AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@_N@1@AEAU?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::_Emplace<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &>(std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>> &)
0x18001ff28  add     rdi, 10h
0x18001ff2c  cmp     rdi, r14
0x18001ff2f  jnz     loc_18001FEAC
0x18001ff35  lea     rdx, [rbp+57h+var_48]
0x18001ff39  mov     rcx, rbx
0x18001ff3c  cmp     dword ptr [rbx+1B8h], 3
0x18001ff43  jnz     short loc_18001FF4C
0x18001ff45  call    ?UpdateDisplayConfigContainer@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z; CRdpIdAdapter::UpdateDisplayConfigContainer(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)
0x18001ff4a  jmp     short loc_18001FF51
0x18001ff4c  call    ?UpdateDisplayConfigNative@CRdpIdAdapter@@AEAAXAEBV?$map@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@@std@@@Z; CRdpIdAdapter::UpdateDisplayConfigNative(std::map<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>> const &)
0x18001ff51  mov     rcx, [rbx+230h]
0x18001ff58  mov     rax, [rcx]
0x18001ff5b  mov     rax, [rax+40h]
0x18001ff5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff64  mov     rcx, [rbp+5Fh]; this
0x18001ff68  lea     rdx, aFailedToCommit; "Failed to commit monitors"
0x18001ff6f  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x18001ff74  mov     r9d, eax; char *
0x18001ff77  mov     r8, r12; unsigned int
0x18001ff7a  mov     edx, 495h; void *
0x18001ff7f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001ff84  nop
0x18001ff85  lea     rcx, [rbp+57h+var_48]
0x18001ff89  call    ??1?$_Tree@V?$_Tmap_traits@URDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@U?$StdComparer@URDP_MONITORCONFIG_MONITOR_ID@@@@V?$allocator@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>::~_Tree<std::_Tmap_traits<RDP_MONITORCONFIG_MONITOR_ID,std::shared_ptr<CRdpIdMonitor>,StdComparer<RDP_MONITORCONFIG_MONITOR_ID>,std::allocator<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>,0>>(void)
0x18001ff8e  mov     rbx, [rsp+0F0h+arg_0]
0x18001ff96  add     rsp, 0C0h
0x18001ff9d  pop     r15
0x18001ff9f  pop     r14
0x18001ffa1  pop     r13
0x18001ffa3  pop     r12
0x18001ffa5  pop     rdi
0x18001ffa6  pop     rsi
0x18001ffa7  pop     rbp
0x18001ffa8  retn
0x18001ffaa  mov     rcx, rdi
0x18001ffad  call    ??$?CVCRdpIdMonitor@@$0A@@?$shared_ptr@VCRdpIdMonitor@@@std@@QEBAPEAVCRdpIdMonitor@@XZ; std::shared_ptr<CRdpIdMonitor>::operator-><CRdpIdMonitor,0>(void)
0x18001ffb2  mov     rcx, rax; this
0x18001ffb5  call    ?GetMonitorId@CMonitorConfig@@QEBAAEBURDP_MONITORCONFIG_MONITOR_ID@@XZ; CMonitorConfig::GetMonitorId(void)
0x18001ffba  mov     r13, rax
0x18001ffbd  mov     [rbp+57h+arg_8], rax
0x18001ffc1  movzx   edx, byte ptr [rax+0Fh]
0x18001ffc5  movzx   r8d, byte ptr [rax+0Eh]
0x18001ffca  movzx   r9d, byte ptr [rax+0Dh]
0x18001ffcf  movzx   r10d, byte ptr [rax+0Ch]
0x18001ffd4  movzx   r11d, byte ptr [rax+0Bh]
0x18001ffd9  movzx   ebx, byte ptr [rax+0Ah]
0x18001ffdd  movzx   edi, byte ptr [rax+9]
0x18001ffe1  movzx   esi, byte ptr [rax+8]
0x18001ffe5  movzx   r14d, word ptr [rax+6]
0x18001ffea  movzx   r15d, word ptr [rax+4]
0x18001ffef  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x18001fff4  mov     rcx, rax; this
0x18001fff7  mov     dword ptr [rsp+0F0h+var_78], edx
0x18001fffb  mov     dword ptr [rsp+0F0h+var_80], r8d
0x180020000  mov     dword ptr [rsp+0F0h+var_88], r9d
0x180020005  mov     dword ptr [rsp+0F0h+var_90], r10d
0x18002000a  mov     dword ptr [rsp+0F0h+var_98], r11d
0x18002000f  mov     dword ptr [rsp+0F0h+var_A0], ebx
0x180020013  mov     dword ptr [rsp+0F0h+var_A8], edi
0x180020017  mov     dword ptr [rsp+0F0h+var_B0], esi
0x18002001b  mov     dword ptr [rsp+0F0h+var_B8], r14d
0x180020020  mov     dword ptr [rsp+0F0h+var_C0], r15d
0x180020025  mov     eax, [r13+0]
0x180020029  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18002002d  mov     [rsp+0F0h+var_D0], 476h; unsigned int
0x180020035  mov     r9, r12; char *
0x180020038  lea     r8, aCrdpidadapterU_1; "CRdpIdAdapter::UpdateMonitors"
0x18002003f  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x180020046  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002004b  movzx   edx, byte ptr [r13+0Fh]
0x180020050  movzx   r10d, byte ptr [r13+0Eh]
0x180020055  movzx   r11d, byte ptr [r13+0Dh]
0x18002005a  movzx   ebx, byte ptr [r13+0Ch]
0x18002005f  movzx   edi, byte ptr [r13+0Bh]
0x180020064  movzx   esi, byte ptr [r13+0Ah]
0x180020069  movzx   r14d, byte ptr [r13+9]
0x18002006e  movzx   r15d, byte ptr [r13+8]
0x180020073  movzx   r12d, word ptr [r13+6]
0x180020078  movzx   r13d, word ptr [r13+4]
0x18002007d  mov     ecx, 80070490h
0x180020082  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180020087  mov     r9d, eax; char *
0x18002008a  mov     rcx, [rbp+5Fh]; this
0x18002008e  mov     dword ptr [rsp+0F0h+var_78], edx
0x180020092  mov     dword ptr [rsp+0F0h+var_80], r10d
0x180020097  mov     dword ptr [rsp+0F0h+var_88], r11d
0x18002009c  mov     dword ptr [rsp+0F0h+var_90], ebx
0x1800200a0  mov     dword ptr [rsp+0F0h+var_98], edi
0x1800200a4  mov     dword ptr [rsp+0F0h+var_A0], esi
0x1800200a8  mov     dword ptr [rsp+0F0h+var_A8], r14d
0x1800200ad  mov     dword ptr [rsp+0F0h+var_B0], r15d
0x1800200b2  mov     dword ptr [rsp+0F0h+var_B8], r12d
0x1800200b7  mov     dword ptr [rsp+0F0h+var_C0], r13d
0x1800200bc  mov     rax, [rbp+57h+arg_8]
0x1800200c0  mov     eax, [rax]
0x1800200c2  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x1800200c6  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x1800200cd  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800200d2  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800200d9  mov     edx, 47Dh; void *
0x1800200de  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
